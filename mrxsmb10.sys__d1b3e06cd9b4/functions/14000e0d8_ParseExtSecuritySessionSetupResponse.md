# ParseExtSecuritySessionSetupResponse

- ea: `0x14000e0d8`
- end: `0x14000e2c3`
- name: `ParseExtSecuritySessionSetupResponse`
- size: `491`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000e2d0`
- `0x14000e320`

## callees

- `0x14000af80`
- `0x14000dfd8`
- `0x14000e0d8`
- `0x1400166c0`

## pseudocode

```c
__int64 __fastcall ParseExtSecuritySessionSetupResponse(__int64 a1, unsigned int a2, unsigned int a3, __int64 a4)
{
  unsigned int SmbResponseNtStatus; // edx
  __int64 v9; // r10
  char v10; // al
  __int64 v11; // r9
  size_t v12; // rcx
  int v13; // eax
  size_t v14; // r8
  void *v15; // rcx
  int v17; // [rsp+58h] [rbp+10h] BYREF

  v17 = 0;
  if ( a2 < 0x20 )
  {
    SmbResponseNtStatus = -1073741629;
    *(_DWORD *)(a1 + 48) = -1073741629;
    return SmbResponseNtStatus;
  }
  SmbResponseNtStatus = GetSmbResponseNtStatus(a4, a1, &v17);
  if ( SmbResponseNtStatus == -1073741629 && v17 == -1073741802 )
    SmbResponseNtStatus = -1073741802;
  *(_DWORD *)(a1 + 48) = SmbResponseNtStatus;
  if ( (int)(SmbResponseNtStatus + 0x80000000) < 0 || SmbResponseNtStatus == -1073741802 )
  {
    if ( a2 < 0x2B )
    {
LABEL_9:
      SmbResponseNtStatus = -1073741629;
      *(_DWORD *)(a1 + 48) = -1073741629;
      return SmbResponseNtStatus;
    }
    v10 = *(_BYTE *)(a4 + 32);
    if ( v10 == 4 )
    {
      *(_WORD *)(v9 + 132) = *(_WORD *)(a4 + 28);
      if ( (*(_BYTE *)(a4 + 37) & 1) != 0 )
        *(_DWORD *)(v9 + 136) |= 0x10u;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_43394d5f7d713bd5b3e6605c91e75025_Traceguids, a2);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_43394d5f7d713bd5b3e6605c91e75025_Traceguids, a3);
        }
      }
      v11 = (unsigned int)*(unsigned __int16 *)(a4 + 41) + 43;
      *(_DWORD *)(a1 + 396) = v11;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_43394d5f7d713bd5b3e6605c91e75025_Traceguids, v11);
      }
      v12 = *(unsigned int *)(a1 + 396);
      if ( (unsigned int)v12 > a3 )
        goto LABEL_9;
      if ( (unsigned int)v12 > *(_DWORD *)(a1 + 392) )
      {
        SmbResponseNtStatus = -2147483643;
        *(_DWORD *)(a1 + 48) = -2147483643;
        return SmbResponseNtStatus;
      }
      if ( a2 < (unsigned int)v12 )
        return (unsigned int)-1073741802;
      *(_DWORD *)(a1 + 408) = 43;
      v13 = *(unsigned __int16 *)(a4 + 39);
      *(_DWORD *)(a1 + 412) = v13;
      if ( v13 + 43 > (unsigned int)v12 )
        goto LABEL_9;
      v14 = v12;
      v15 = *(void **)(a1 + 376);
      *(_DWORD *)(a1 + 412) = *(unsigned __int16 *)(a4 + 39);
      memmove(v15, (const void *)a4, v14);
    }
    else
    {
      if ( v10 )
        goto LABEL_9;
      *(_DWORD *)(a1 + 412) = 0;
    }
    return 0;
  }
  return SmbResponseNtStatus;
}

```

## disassembly

```asm
0x14000e0d8  mov     [rsp+arg_0], rbx
0x14000e0dd  mov     [rsp+arg_10], rbp
0x14000e0e2  push    rsi
0x14000e0e3  push    rdi
0x14000e0e4  push    r13
0x14000e0e6  push    r14
0x14000e0e8  push    r15
0x14000e0ea  sub     rsp, 20h
0x14000e0ee  mov     [rsp+48h+arg_8], 0
0x14000e0f6  mov     rsi, r9
0x14000e0f9  mov     r14d, r8d
0x14000e0fc  mov     ebp, edx
0x14000e0fe  mov     rbx, rcx
0x14000e101  cmp     edx, 20h ; ' '
0x14000e104  jnb     short loc_14000E115
0x14000e106  mov     edi, 0C00000C3h
0x14000e10b  mov     edx, edi
0x14000e10d  mov     [rcx+30h], edi
0x14000e110  jmp     loc_14000E2A9
0x14000e115  mov     r10, [rcx+58h]
0x14000e119  test    r10, r10
0x14000e11c  jz      short loc_14000E122
0x14000e11e  mov     r10, [r10+60h]
0x14000e122  lea     r8, [rsp+48h+arg_8]
0x14000e127  mov     rdx, rbx
0x14000e12a  mov     rcx, rsi
0x14000e12d  call    GetSmbResponseNtStatus
0x14000e132  mov     edi, 0C00000C3h
0x14000e137  mov     edx, eax
0x14000e139  mov     r15d, 0C0000016h
0x14000e13f  cmp     eax, edi
0x14000e141  jnz     short loc_14000E14C
0x14000e143  cmp     [rsp+48h+arg_8], r15d
0x14000e148  cmovz   edx, r15d
0x14000e14c  mov     ecx, 80000000h
0x14000e151  mov     [rbx+30h], edx
0x14000e154  lea     eax, [rdx+rcx]
0x14000e157  test    ecx, eax
0x14000e159  jnz     short loc_14000E164
0x14000e15b  cmp     edx, r15d
0x14000e15e  jnz     loc_14000E2A9
0x14000e164  cmp     ebp, 2Bh ; '+'
0x14000e167  jnb     short loc_14000E173
0x14000e169  mov     edx, edi
0x14000e16b  mov     [rbx+30h], edi
0x14000e16e  jmp     loc_14000E2A9
0x14000e173  mov     al, [rsi+20h]
0x14000e176  cmp     al, 4
0x14000e178  jz      short loc_14000E18D
0x14000e17a  test    al, al
0x14000e17c  jnz     short loc_14000E169
0x14000e17e  mov     dword ptr [rbx+19Ch], 0
0x14000e188  jmp     loc_14000E2A7
0x14000e18d  movzx   eax, word ptr [rsi+1Ch]
0x14000e191  mov     [r10+84h], ax
0x14000e199  test    byte ptr [rsi+25h], 1
0x14000e19d  jz      short loc_14000E1A7
0x14000e19f  or      dword ptr [r10+88h], 10h
0x14000e1a7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000e1ae  lea     r13, WPP_GLOBAL_Control
0x14000e1b5  cmp     rcx, r13
0x14000e1b8  jz      short loc_14000E208
0x14000e1ba  test    dword ptr [rcx+2Ch], 400h
0x14000e1c1  jz      short loc_14000E1DB
0x14000e1c3  mov     rcx, [rcx+18h]
0x14000e1c7  lea     r8, WPP_43394d5f7d713bd5b3e6605c91e75025_Traceguids
0x14000e1ce  mov     edx, 0Dh
0x14000e1d3  mov     r9d, ebp
0x14000e1d6  call    WPP_SF_d
0x14000e1db  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000e1e2  cmp     rcx, r13
0x14000e1e5  jz      short loc_14000E208
0x14000e1e7  test    dword ptr [rcx+2Ch], 400h
0x14000e1ee  jz      short loc_14000E208
0x14000e1f0  mov     rcx, [rcx+18h]
0x14000e1f4  lea     r8, WPP_43394d5f7d713bd5b3e6605c91e75025_Traceguids
0x14000e1fb  mov     edx, 0Eh
0x14000e200  mov     r9d, r14d
0x14000e203  call    WPP_SF_d
0x14000e208  movzx   r9d, word ptr [rsi+29h]
0x14000e20d  add     r9d, 2Bh ; '+'
0x14000e211  mov     [rbx+18Ch], r9d
0x14000e218  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000e21f  cmp     rcx, r13
0x14000e222  jz      short loc_14000E242
0x14000e224  test    dword ptr [rcx+2Ch], 400h
0x14000e22b  jz      short loc_14000E242
0x14000e22d  mov     rcx, [rcx+18h]
0x14000e231  lea     r8, WPP_43394d5f7d713bd5b3e6605c91e75025_Traceguids
0x14000e238  mov     edx, 0Fh
0x14000e23d  call    WPP_SF_d
0x14000e242  mov     ecx, [rbx+18Ch]
0x14000e248  cmp     ecx, r14d
0x14000e24b  ja      loc_14000E169
0x14000e251  cmp     ecx, [rbx+188h]
0x14000e257  jbe     short loc_14000E263
0x14000e259  mov     edx, 80000005h
0x14000e25e  mov     [rbx+30h], edx
0x14000e261  jmp     short loc_14000E2A9
0x14000e263  cmp     ebp, ecx
0x14000e265  jnb     short loc_14000E26C
0x14000e267  mov     edx, r15d
0x14000e26a  jmp     short loc_14000E2A9
0x14000e26c  mov     dword ptr [rbx+198h], 2Bh ; '+'
0x14000e276  movzx   eax, word ptr [rsi+27h]
0x14000e27a  mov     [rbx+19Ch], eax
0x14000e280  add     eax, 2Bh ; '+'
0x14000e283  cmp     eax, ecx
0x14000e285  ja      loc_14000E169
0x14000e28b  movzx   eax, word ptr [rsi+27h]
0x14000e28f  mov     r8, rcx; Size
0x14000e292  mov     rcx, [rbx+178h]; void *
0x14000e299  mov     rdx, rsi; Src
0x14000e29c  mov     [rbx+19Ch], eax
0x14000e2a2  call    memmove
0x14000e2a7  xor     edx, edx
0x14000e2a9  mov     rbx, [rsp+48h+arg_0]
0x14000e2ae  mov     eax, edx
0x14000e2b0  mov     rbp, [rsp+48h+arg_10]
0x14000e2b5  add     rsp, 20h
0x14000e2b9  pop     r15
0x14000e2bb  pop     r14
0x14000e2bd  pop     r13
0x14000e2bf  pop     rdi
0x14000e2c0  pop     rsi
0x14000e2c1  retn
```
