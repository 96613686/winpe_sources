# PsScriptFile::ReadContent(ulong *,ushort * *)

- ea: `0x180002ae8`
- end: `0x180002beb`
- name: `?ReadContent@PsScriptFile@@QEAAKPEAKPEAPEAG@Z`
- size: `259`
- prototype: `unsigned int __fastcall(PsScriptFile *__hidden this, unsigned int *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180001fa0`
- `0x180002c00`

## callees

- `0x180002ae8`
- `0x1800054c6`

## pseudocode

```c
__int64 __fastcall PsScriptFile::ReadContent(PsScriptFile *this, unsigned int *a2, unsigned __int16 **a3)
{
  unsigned __int16 *v6; // rbp
  unsigned int v7; // edi
  __int64 v8; // r8
  __int64 v9; // rdx
  unsigned int v10; // ebx
  char v11; // r9
  const wchar_t *v12; // r14

  if ( a2 && a3 )
  {
    v6 = (unsigned __int16 *)*((_QWORD *)this + 11);
    *a3 = 0;
    *a2 = 0;
    if ( v6 )
    {
      v8 = *((unsigned int *)this + 20);
      v9 = *((_QWORD *)this + 9);
      if ( (unsigned __int64)v6 < v9 + 2 * v8 )
      {
        v7 = 0;
        v10 = 0;
        v11 = 0;
        v12 = v6;
        if ( (unsigned int)(((__int64)v6 - v9) >> 1) < (unsigned int)v8 )
        {
          do
          {
            if ( v10 >= 0x200 )
              break;
            if ( *v12 == 10 || *v12 == 13 )
            {
              v11 = 1;
            }
            else if ( v11 )
            {
              break;
            }
            ++v12;
            ++v10;
          }
          while ( (unsigned int)(((__int64)v12 - v9) >> 1) < (unsigned int)v8 );
          if ( v10 >= 2
            && !wcsncmp_0(
                  v12,
                  (const wchar_t *)qword_180009840[10 * *((unsigned int *)this + 14) + 2],
                  HIDWORD(qword_180009840[10 * *((unsigned int *)this + 14) + 7])) )
          {
            v10 -= 2;
          }
        }
        *a2 = v10;
        *a3 = v6;
        *((_QWORD *)this + 11) = v12;
      }
      else
      {
        return 259;
      }
    }
    else
    {
      return 13;
    }
  }
  else
  {
    return 87;
  }
  return v7;
}

```

## disassembly

```asm
0x180002ae8  push    rbx
0x180002aea  push    rbp
0x180002aeb  push    rsi
0x180002aec  push    rdi
0x180002aed  push    r12
0x180002aef  push    r14
0x180002af1  push    r15
0x180002af3  sub     rsp, 20h
0x180002af7  mov     r15, r8
0x180002afa  mov     r12, rdx
0x180002afd  mov     rsi, rcx
0x180002b00  test    rdx, rdx
0x180002b03  jz      loc_180002BD5
0x180002b09  test    r8, r8
0x180002b0c  jz      loc_180002BD5
0x180002b12  mov     rbp, [rcx+58h]
0x180002b16  mov     qword ptr [r8], 0
0x180002b1d  mov     dword ptr [rdx], 0
0x180002b23  test    rbp, rbp
0x180002b26  jnz     short loc_180002B30
0x180002b28  lea     edi, [rbp+0Dh]
0x180002b2b  jmp     loc_180002BDA
0x180002b30  mov     r8d, [rcx+50h]
0x180002b34  mov     rdx, [rcx+48h]
0x180002b38  lea     rax, [rdx+r8*2]
0x180002b3c  cmp     rbp, rax
0x180002b3f  jb      short loc_180002B4B
0x180002b41  mov     edi, 103h
0x180002b46  jmp     loc_180002BDA
0x180002b4b  mov     rax, rbp
0x180002b4e  xor     edi, edi
0x180002b50  sub     rax, rdx
0x180002b53  xor     ebx, ebx
0x180002b55  sar     rax, 1
0x180002b58  xor     r9b, r9b
0x180002b5b  mov     r14, rbp
0x180002b5e  cmp     eax, r8d
0x180002b61  jnb     short loc_180002BC8
0x180002b63  lea     ecx, [rdi+0Dh]
0x180002b66  cmp     ebx, 200h
0x180002b6c  jnb     short loc_180002B99
0x180002b6e  cmp     word ptr [r14], 0Ah
0x180002b73  jz      short loc_180002B82
0x180002b75  cmp     [r14], cx
0x180002b79  jz      short loc_180002B82
0x180002b7b  test    r9b, r9b
0x180002b7e  jnz     short loc_180002B99
0x180002b80  jmp     short loc_180002B85
0x180002b82  mov     r9b, 1
0x180002b85  add     r14, 2
0x180002b89  inc     ebx
0x180002b8b  mov     rax, r14
0x180002b8e  sub     rax, rdx
0x180002b91  sar     rax, 1
0x180002b94  cmp     eax, r8d
0x180002b97  jb      short loc_180002B66
0x180002b99  cmp     ebx, 2
0x180002b9c  jb      short loc_180002BC8
0x180002b9e  mov     eax, [rsi+38h]
0x180002ba1  mov     rcx, r14; String1
0x180002ba4  lea     rdx, [rax+rax*4]
0x180002ba8  add     rdx, rdx
0x180002bab  lea     rax, qword_180009840
0x180002bb2  mov     r8d, [rax+rdx*8+3Ch]; MaxCount
0x180002bb7  mov     rdx, [rax+rdx*8+10h]; String2
0x180002bbc  call    wcsncmp_0
0x180002bc1  test    eax, eax
0x180002bc3  jnz     short loc_180002BC8
0x180002bc5  add     ebx, 0FFFFFFFEh
0x180002bc8  mov     [r12], ebx
0x180002bcc  mov     [r15], rbp
0x180002bcf  mov     [rsi+58h], r14
0x180002bd3  jmp     short loc_180002BDA
0x180002bd5  mov     edi, 57h ; 'W'
0x180002bda  mov     eax, edi
0x180002bdc  add     rsp, 20h
0x180002be0  pop     r15
0x180002be2  pop     r14
0x180002be4  pop     r12
0x180002be6  pop     rdi
0x180002be7  pop     rsi
0x180002be8  pop     rbp
0x180002be9  pop     rbx
0x180002bea  retn
```
