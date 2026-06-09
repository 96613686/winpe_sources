# ATL::CComVariant::operator==(tagVARIANT const &)

- ea: `0x180018d80`
- end: `0x180018ea7`
- name: `??8CComVariant@ATL@@QEAA_NAEBUtagVARIANT@@@Z`
- size: `295`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002d030`

## callees

- `0x180018d80`
- `0x18002f086`

## import_xrefs

- `OLEAUT32!__imp_SysStringByteLen` at `0x180018e12`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180018e24`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180018e3a`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180018e12`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180018e24`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180018e3a`

## pseudocode

```c
char __fastcall ATL::CComVariant::operator==(unsigned __int16 *a1, __int64 a2)
{
  unsigned int v4; // eax
  char v6; // di
  bool v7; // zf
  UINT v9; // ebx
  UINT v10; // eax

  if ( a1 != (unsigned __int16 *)a2 )
  {
    v4 = *a1;
    if ( (_WORD)v4 != *(_WORD *)a2 )
      return 0;
    if ( v4 > 8 )
    {
      if ( v4 != 9 )
      {
        if ( v4 == 10 )
          return *((_DWORD *)a1 + 2) == *(_DWORD *)(a2 + 8);
        if ( v4 == 11 )
          return a1[4] == *(_WORD *)(a2 + 8);
        if ( v4 != 13 )
        {
          if ( v4 == 17 )
            return *((_BYTE *)a1 + 8) == *(_BYTE *)(a2 + 8);
          if ( v4 != 20 )
            return 0;
        }
      }
      return *((_QWORD *)a1 + 1) == *(_QWORD *)(a2 + 8);
    }
    if ( v4 == 8 )
    {
      v9 = SysStringByteLen(*(BSTR *)(a2 + 8));
      v6 = 0;
      if ( SysStringByteLen(*((BSTR *)a1 + 1)) != v9 )
        return v6;
      v10 = SysStringByteLen(*((BSTR *)a1 + 1));
      v7 = memcmp_0(*((const void **)a1 + 1), *(const void **)(a2 + 8), v10) == 0;
LABEL_14:
      if ( v7 )
        return 1;
      return v6;
    }
    v6 = 0;
    if ( *a1 && v4 != 1 )
    {
      if ( v4 != 2 )
      {
        if ( v4 != 3 )
        {
          if ( v4 == 4 )
          {
            v7 = *((float *)a1 + 2) == *(float *)(a2 + 8);
          }
          else
          {
            if ( v4 != 5 )
              return 0;
            v7 = *((double *)a1 + 1) == *(double *)(a2 + 8);
          }
          goto LABEL_14;
        }
        return *((_DWORD *)a1 + 2) == *(_DWORD *)(a2 + 8);
      }
      return a1[4] == *(_WORD *)(a2 + 8);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180018d80  push    rbx
0x180018d82  push    rbp
0x180018d83  push    rsi
0x180018d84  push    rdi
0x180018d85  sub     rsp, 28h
0x180018d89  mov     rbp, rdx
0x180018d8c  mov     rsi, rcx
0x180018d8f  cmp     rcx, rdx
0x180018d92  jz      loc_180018E9B
0x180018d98  movzx   eax, word ptr [rcx]
0x180018d9b  cmp     ax, [rdx]
0x180018d9e  jz      short loc_180018DA7
0x180018da0  xor     al, al
0x180018da2  jmp     loc_180018E9D
0x180018da7  mov     ecx, eax
0x180018da9  cmp     eax, 8
0x180018dac  ja      loc_180018E5A
0x180018db2  jz      short loc_180018E0E
0x180018db4  xor     edi, edi
0x180018db6  test    eax, eax
0x180018db8  jz      loc_180018E9B
0x180018dbe  sub     ecx, 1
0x180018dc1  jz      loc_180018E9B
0x180018dc7  sub     ecx, 1
0x180018dca  jz      loc_180018E8E
0x180018dd0  sub     ecx, 1
0x180018dd3  jz      short loc_180018E03
0x180018dd5  sub     ecx, 1
0x180018dd8  jz      short loc_180018DEB
0x180018dda  cmp     ecx, 1
0x180018ddd  jnz     short loc_180018DA0
0x180018ddf  movsd   xmm0, qword ptr [rsi+8]
0x180018de4  ucomisd xmm0, qword ptr [rdx+8]
0x180018de9  jmp     short loc_180018DF4
0x180018deb  movss   xmm0, dword ptr [rsi+8]
0x180018df0  ucomiss xmm0, dword ptr [rdx+8]
0x180018df4  jp      short loc_180018DFB
0x180018df6  jnz     short loc_180018DFB
0x180018df8  mov     dil, 1
0x180018dfb  mov     al, dil
0x180018dfe  jmp     loc_180018E9D
0x180018e03  mov     eax, [rdx+8]
0x180018e06  cmp     [rsi+8], eax
0x180018e09  jmp     loc_180018E96
0x180018e0e  mov     rcx, [rdx+8]; bstr
0x180018e12  call    cs:__imp_SysStringByteLen
0x180018e19  nop     dword ptr [rax+rax+00h]
0x180018e1e  mov     rcx, [rsi+8]; bstr
0x180018e22  mov     ebx, eax
0x180018e24  call    cs:__imp_SysStringByteLen
0x180018e2b  nop     dword ptr [rax+rax+00h]
0x180018e30  xor     edi, edi
0x180018e32  cmp     eax, ebx
0x180018e34  jnz     short loc_180018DFB
0x180018e36  mov     rcx, [rsi+8]; bstr
0x180018e3a  call    cs:__imp_SysStringByteLen
0x180018e41  nop     dword ptr [rax+rax+00h]
0x180018e46  mov     rdx, [rbp+8]; Buf2
0x180018e4a  mov     rcx, [rsi+8]; Buf1
0x180018e4e  mov     r8d, eax; Size
0x180018e51  call    memcmp_0
0x180018e56  test    eax, eax
0x180018e58  jmp     short loc_180018DF6
0x180018e5a  sub     ecx, 9
0x180018e5d  jz      short loc_180018E7C
0x180018e5f  sub     ecx, 1
0x180018e62  jz      short loc_180018E03
0x180018e64  sub     ecx, 1
0x180018e67  jz      short loc_180018E8E
0x180018e69  sub     ecx, 2
0x180018e6c  jz      short loc_180018E7C
0x180018e6e  sub     ecx, 4
0x180018e71  jz      short loc_180018E86
0x180018e73  cmp     ecx, 3
0x180018e76  jnz     loc_180018DA0
0x180018e7c  mov     rax, [rdx+8]
0x180018e80  cmp     [rsi+8], rax
0x180018e84  jmp     short loc_180018E96
0x180018e86  mov     al, [rdx+8]
0x180018e89  cmp     [rsi+8], al
0x180018e8c  jmp     short loc_180018E96
0x180018e8e  movzx   eax, word ptr [rdx+8]
0x180018e92  cmp     [rsi+8], ax
0x180018e96  setz    al
0x180018e99  jmp     short loc_180018E9D
0x180018e9b  mov     al, 1
0x180018e9d  add     rsp, 28h
0x180018ea1  pop     rdi
0x180018ea2  pop     rsi
0x180018ea3  pop     rbp
0x180018ea4  pop     rbx
0x180018ea5  retn
```
