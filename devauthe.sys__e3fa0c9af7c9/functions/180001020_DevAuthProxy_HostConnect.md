# DevAuthProxy_HostConnect

- ea: `0x180001020`
- end: `0x1800010dc`
- name: `DevAuthProxy_HostConnect`
- size: `188`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000118c`
- `0x180001980`

## callees

- `0x180001020`
- `0x18000258c`
- `0x180006cc0`

## pseudocode

```c
__int64 __fastcall DevAuthProxy_HostConnect(unsigned __int8 *a1)
{
  int v2; // ecx
  int v3; // ecx
  unsigned int v5; // edi

  v2 = *a1;
  if ( v2 && (v3 = v2 - 1) != 0 )
  {
    if ( v3 == 1 )
    {
      if ( a1 == (unsigned __int8 *)-8LL )
        return 0;
      if ( !*((_DWORD *)a1 + 3) )
        memset(a1 + 10, 0, 0x44Eu);
      a1[9] = 33;
      v5 = 1;
      a1[8] = 1;
      if ( a1 == (unsigned __int8 *)-1104LL || !(unsigned int)DevAuthCreateHash(0, 0, (BCRYPT_HANDLE **)a1 + 138) )
        return 0;
      return v5;
    }
    else
    {
      return 0;
    }
  }
  else
  {
    if ( !*((_DWORD *)a1 + 3) )
      memset(a1 + 10, 0, 0x4CEu);
    *((_WORD *)a1 + 4) = 257;
    return (unsigned int)DevAuthCreateHash(0, 0, (BCRYPT_HANDLE **)a1 + 154) != 0;
  }
}

```

## disassembly

```asm
0x180001020  mov     [rsp+arg_0], rbx
0x180001025  mov     [rsp+arg_8], rsi
0x18000102a  push    rdi
0x18000102b  sub     rsp, 20h
0x18000102f  mov     rbx, rcx
0x180001032  movzx   ecx, byte ptr [rcx]
0x180001035  test    ecx, ecx
0x180001037  jz      short loc_180001095
0x180001039  sub     ecx, 1
0x18000103c  jz      short loc_180001095
0x18000103e  cmp     ecx, 1
0x180001041  jz      short loc_18000104A
0x180001043  xor     eax, eax
0x180001045  jmp     loc_1800010CB
0x18000104a  lea     rsi, [rbx+8]
0x18000104e  test    rsi, rsi
0x180001051  jz      short loc_18000108F
0x180001053  cmp     dword ptr [rsi+4], 0
0x180001057  jnz     short loc_18000106A
0x180001059  lea     rcx, [rbx+0Ah]; void *
0x18000105d  xor     edx, edx; Val
0x18000105f  mov     r8d, 44Eh; Size
0x180001065  call    memset
0x18000106a  lea     r8, [rbx+450h]
0x180001071  mov     byte ptr [rbx+9], 21h ; '!'
0x180001075  mov     edi, 1
0x18000107a  mov     [rsi], dil
0x18000107d  test    r8, r8
0x180001080  jz      short loc_18000108F
0x180001082  xor     edx, edx; cbSecret
0x180001084  xor     ecx, ecx; pbSecret
0x180001086  call    DevAuthCreateHash
0x18000108b  test    eax, eax
0x18000108d  jnz     short loc_180001091
0x18000108f  xor     edi, edi
0x180001091  mov     eax, edi
0x180001093  jmp     short loc_1800010CB
0x180001095  cmp     dword ptr [rbx+0Ch], 0
0x180001099  jnz     short loc_1800010AC
0x18000109b  lea     rcx, [rbx+0Ah]; void *
0x18000109f  xor     edx, edx; Val
0x1800010a1  mov     r8d, 4CEh; Size
0x1800010a7  call    memset
0x1800010ac  lea     r8, [rbx+4D0h]
0x1800010b3  mov     word ptr [rbx+8], 101h
0x1800010b9  xor     edx, edx; cbSecret
0x1800010bb  xor     ecx, ecx; pbSecret
0x1800010bd  call    DevAuthCreateHash
0x1800010c2  xor     ecx, ecx
0x1800010c4  test    eax, eax
0x1800010c6  setnz   cl
0x1800010c9  mov     eax, ecx
0x1800010cb  mov     rbx, [rsp+28h+arg_0]
0x1800010d0  mov     rsi, [rsp+28h+arg_8]
0x1800010d5  add     rsp, 20h
0x1800010d9  pop     rdi
0x1800010da  retn
```
