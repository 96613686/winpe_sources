# ReadICS

- ea: `0x18007d4e0`
- end: `0x18007d60d`
- name: `ReadICS`
- size: `301`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x180074560`
- `0x18007d2d0`

## callees

- `0x1800363f0`
- `0x180078870`
- `0x180078d40`
- `0x180078f40`
- `0x180079090`
- `0x18007d4e0`
- `0x18007e8c0`
- `0x18007f350`
- `0x18007f9e0`
- `0x180080100`
- `0x180080800`

## pseudocode

```c
__int64 __fastcall ReadICS(int *a1, char *a2)
{
  bool v4; // zf
  __int64 result; // rax
  unsigned __int8 v6; // si

  if ( (unsigned int)*a1 < 8 )
    FillBitCache(a1, 8u);
  *a1 -= 8;
  v4 = a2[24] == 0;
  a2[928] = (unsigned int)a1[1] >> *a1;
  if ( !v4 || (result = IcsRead(a1), !(_DWORD)result) )
  {
    if ( a2[27] == 2 )
    {
      CShortBlock_Init(a2);
      v6 = a2[928];
      result = CShortBlock_ReadSectionData(a1, a2);
      if ( !(_DWORD)result )
      {
        CShortBlock_ReadScaleFactorData(a1, a2, v6);
        CPulseData_Read(a1, a2 + 915);
        if ( !*a1 )
          FillBitCache(a1, 1u);
        a2[42] = ((unsigned int)a1[1] >> --*a1) & 1;
        result = CTns_Read(a1, a2);
        if ( !(_DWORD)result )
        {
          if ( !*a1 )
            FillBitCache(a1, 1u);
          if ( (((unsigned int)a1[1] >> --*a1) & 1) == 0 )
            return CShortBlock_ReadSpectralData(a1, a2);
          result = CGC_Read(a1, a2);
          if ( !(_DWORD)result )
            return CShortBlock_ReadSpectralData(a1, a2);
        }
      }
    }
    else
    {
      return CLongBlock_Read(a1, a2, (unsigned __int8)a2[928]);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18007d4e0  mov     [rsp+arg_8], rbx
0x18007d4e5  push    rdi
0x18007d4e6  sub     rsp, 20h
0x18007d4ea  cmp     dword ptr [rcx], 8
0x18007d4ed  mov     rdi, rdx
0x18007d4f0  mov     rbx, rcx
0x18007d4f3  jnb     short loc_18007D4FF
0x18007d4f5  mov     edx, 8
0x18007d4fa  call    FillBitCache
0x18007d4ff  add     dword ptr [rbx], 0FFFFFFF8h
0x18007d502  lea     rdx, [rdi+18h]
0x18007d506  mov     eax, [rbx+4]
0x18007d509  mov     ecx, [rbx]
0x18007d50b  shr     eax, cl
0x18007d50d  cmp     byte ptr [rdx], 0
0x18007d510  mov     [rdi+3A0h], al
0x18007d516  jnz     short loc_18007D528
0x18007d518  mov     rcx, rbx
0x18007d51b  call    IcsRead
0x18007d520  test    eax, eax
0x18007d522  jnz     loc_18007D601
0x18007d528  cmp     byte ptr [rdi+1Bh], 2
0x18007d52c  jz      short loc_18007D54B
0x18007d52e  movzx   r8d, byte ptr [rdi+3A0h]
0x18007d536  mov     rdx, rdi
0x18007d539  mov     rcx, rbx
0x18007d53c  mov     rbx, [rsp+28h+arg_8]
0x18007d541  add     rsp, 20h
0x18007d545  pop     rdi
0x18007d546  jmp     CLongBlock_Read
0x18007d54b  mov     rcx, rdi
0x18007d54e  mov     [rsp+28h+arg_0], rsi
0x18007d553  call    CShortBlock_Init
0x18007d558  movzx   esi, byte ptr [rdi+3A0h]
0x18007d55f  mov     rdx, rdi
0x18007d562  mov     rcx, rbx
0x18007d565  call    CShortBlock_ReadSectionData
0x18007d56a  test    eax, eax
0x18007d56c  jnz     loc_18007D5FC
0x18007d572  movzx   r8d, sil
0x18007d576  mov     rdx, rdi
0x18007d579  mov     rcx, rbx
0x18007d57c  call    CShortBlock_ReadScaleFactorData
0x18007d581  lea     rdx, [rdi+393h]
0x18007d588  mov     rcx, rbx
0x18007d58b  call    CPulseData_Read
0x18007d590  cmp     dword ptr [rbx], 1
0x18007d593  jnb     short loc_18007D5A2
0x18007d595  mov     edx, 1
0x18007d59a  mov     rcx, rbx
0x18007d59d  call    FillBitCache
0x18007d5a2  dec     dword ptr [rbx]
0x18007d5a4  mov     rdx, rdi
0x18007d5a7  mov     ecx, [rbx]
0x18007d5a9  mov     eax, [rbx+4]
0x18007d5ac  shr     eax, cl
0x18007d5ae  mov     rcx, rbx
0x18007d5b1  and     al, 1
0x18007d5b3  mov     [rdi+2Ah], al
0x18007d5b6  call    CTns_Read
0x18007d5bb  test    eax, eax
0x18007d5bd  jnz     short loc_18007D5FC
0x18007d5bf  cmp     dword ptr [rbx], 1
0x18007d5c2  jnb     short loc_18007D5D1
0x18007d5c4  mov     edx, 1
0x18007d5c9  mov     rcx, rbx
0x18007d5cc  call    FillBitCache
0x18007d5d1  dec     dword ptr [rbx]
0x18007d5d3  mov     eax, [rbx+4]
0x18007d5d6  mov     ecx, [rbx]
0x18007d5d8  shr     eax, cl
0x18007d5da  test    al, 1
0x18007d5dc  jz      short loc_18007D5ED
0x18007d5de  mov     rdx, rdi
0x18007d5e1  mov     rcx, rbx
0x18007d5e4  call    CGC_Read
0x18007d5e9  test    eax, eax
0x18007d5eb  jnz     short loc_18007D5FC
0x18007d5ed  mov     rdx, rdi
0x18007d5f0  mov     rcx, rbx
0x18007d5f3  call    CShortBlock_ReadSpectralData
0x18007d5f8  test    eax, eax
0x18007d5fa  jnz     short $+2
0x18007d5fc  mov     rsi, [rsp+28h+arg_0]
0x18007d601  mov     rbx, [rsp+28h+arg_8]
0x18007d606  add     rsp, 20h
0x18007d60a  pop     rdi
0x18007d60b  retn
```
