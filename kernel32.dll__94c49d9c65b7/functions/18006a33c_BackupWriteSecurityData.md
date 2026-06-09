# BackupWriteSecurityData

- ea: `0x18006a33c`
- end: `0x18006a47f`
- name: `BackupWriteSecurityData`
- size: `323`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180069e20`

## callees

- `0x18000f920`
- `0x180050a38`
- `0x18006a33c`

## import_xrefs

- `ntdll!NtSetSecurityObject` at `0x18006a3da`
- `ntdll!NtSetSecurityObject` at `0x18006a3f0`
- `ntdll!NtSetSecurityObject` at `0x18006a411`
- `ntdll!NtSetSecurityObject` at `0x18006a42b`
- `ntdll!NtSetSecurityObject` at `0x18006a442`
- `ntdll!NtSetSecurityObject` at `0x18006a459`
- `ntdll!NtSetSecurityObject` at `0x18006a3da`
- `ntdll!NtSetSecurityObject` at `0x18006a3f0`
- `ntdll!NtSetSecurityObject` at `0x18006a411`
- `ntdll!NtSetSecurityObject` at `0x18006a42b`
- `ntdll!NtSetSecurityObject` at `0x18006a442`
- `ntdll!NtSetSecurityObject` at `0x18006a459`

## pseudocode

```c
_BOOL8 __fastcall BackupWriteSecurityData(HANDLE Handle, __int64 a2, __int64 a3)
{
  int v6; // eax
  int v7; // eax
  __int64 v9; // r8
  __int16 v10; // dx
  SECURITY_INFORMATION v11; // ebx
  __int64 v12; // rcx
  __int16 v13; // ax
  NTSTATUS v14; // esi
  SECURITY_INFORMATION v15; // ebx
  NTSTATUS v16; // eax

  v6 = BackupWriteBuffer(a2, a3);
  if ( !v6 )
    return 0;
  v7 = v6 - 1;
  if ( v7 )
    return v7 == 1;
  if ( !*(_BYTE *)(a3 + 20) )
    return 1;
  v9 = *(_QWORD *)(a2 + 1088);
  v10 = *(_WORD *)(v9 + 2);
  v11 = v10 & 4 | 0x7B;
  if ( (v10 & 0x10) == 0 )
    v11 = *(_WORD *)(v9 + 2) & 4 | 3;
  if ( (v10 & 0x400) != 0 )
    *(_WORD *)(v9 + 2) = v10 | 0x100;
  v12 = *(_QWORD *)(a2 + 1088);
  v13 = *(_WORD *)(v12 + 2);
  if ( (v13 & 0x800) != 0 )
    *(_WORD *)(v12 + 2) = v13 | 0x200;
  if ( NtSetSecurityObject(Handle, v11 | 0x10000, *(PSECURITY_DESCRIPTOR *)(a2 + 1088)) >= 0 )
    return 1;
  v14 = NtSetSecurityObject(Handle, v11, *(PSECURITY_DESCRIPTOR *)(a2 + 1088));
  if ( v14 >= 0 )
    return 1;
  if ( (v11 & 0x48) != 0 )
    NtSetSecurityObject(Handle, v11 & 0x48, *(PSECURITY_DESCRIPTOR *)(a2 + 1088));
  if ( (v11 & 0x10) != 0 )
    NtSetSecurityObject(Handle, 0x10u, *(PSECURITY_DESCRIPTOR *)(a2 + 1088));
  v15 = v11 & 0x24;
  if ( v15 )
    v14 = NtSetSecurityObject(Handle, v15, *(PSECURITY_DESCRIPTOR *)(a2 + 1088));
  v16 = NtSetSecurityObject(Handle, 3u, *(PSECURITY_DESCRIPTOR *)(a2 + 1088));
  if ( v14 >= 0 )
  {
    if ( v16 >= 0 )
      return 1;
    v14 = v16;
  }
  BaseSetLastNTError((unsigned int)v14);
  return 0;
}

```

## disassembly

```asm
0x18006a33c  push    rbx
0x18006a33e  push    rbp
0x18006a33f  push    rsi
0x18006a340  push    rdi
0x18006a341  sub     rsp, 28h
0x18006a345  mov     rdi, rdx
0x18006a348  mov     rbp, rcx
0x18006a34b  mov     rcx, rdi
0x18006a34e  mov     rdx, r8
0x18006a351  mov     rbx, r8
0x18006a354  call    BackupWriteBuffer
0x18006a359  test    eax, eax
0x18006a35b  jz      loc_18006A474
0x18006a361  sub     eax, 1
0x18006a364  jz      short loc_18006A370
0x18006a366  cmp     eax, 1
0x18006a369  jz      short loc_18006A376
0x18006a36b  jmp     loc_18006A474
0x18006a370  cmp     byte ptr [rbx+14h], 0
0x18006a374  jnz     short loc_18006A380
0x18006a376  mov     eax, 1
0x18006a37b  jmp     loc_18006A476
0x18006a380  mov     r8, [rdi+440h]
0x18006a387  movzx   edx, word ptr [r8+2]
0x18006a38c  mov     ecx, edx
0x18006a38e  and     ecx, 4
0x18006a391  or      ecx, 3
0x18006a394  mov     ebx, ecx
0x18006a396  or      ebx, 78h
0x18006a399  test    dl, 10h
0x18006a39c  cmovz   ebx, ecx
0x18006a39f  bt      dx, 0Ah
0x18006a3a4  jnb     short loc_18006A3B0
0x18006a3a6  or      dx, 100h
0x18006a3ab  mov     [r8+2], dx
0x18006a3b0  mov     rcx, [rdi+440h]
0x18006a3b7  movzx   eax, word ptr [rcx+2]
0x18006a3bb  bt      ax, 0Bh
0x18006a3c0  jnb     short loc_18006A3CA
0x18006a3c2  or      ax, 200h
0x18006a3c6  mov     [rcx+2], ax
0x18006a3ca  mov     r8, [rdi+440h]; SecurityDescriptor
0x18006a3d1  mov     edx, ebx
0x18006a3d3  bts     edx, 10h; SecurityInformation
0x18006a3d7  mov     rcx, rbp; Handle
0x18006a3da  call    cs:__imp_NtSetSecurityObject
0x18006a3e0  test    eax, eax
0x18006a3e2  jns     short loc_18006A376
0x18006a3e4  mov     r8, [rdi+440h]; SecurityDescriptor
0x18006a3eb  mov     edx, ebx; SecurityInformation
0x18006a3ed  mov     rcx, rbp; Handle
0x18006a3f0  call    cs:__imp_NtSetSecurityObject
0x18006a3f6  mov     esi, eax
0x18006a3f8  test    eax, eax
0x18006a3fa  jns     loc_18006A376
0x18006a400  mov     edx, ebx
0x18006a402  and     edx, 48h; SecurityInformation
0x18006a405  jz      short loc_18006A417
0x18006a407  mov     r8, [rdi+440h]; SecurityDescriptor
0x18006a40e  mov     rcx, rbp; Handle
0x18006a411  call    cs:__imp_NtSetSecurityObject
0x18006a417  test    bl, 10h
0x18006a41a  jz      short loc_18006A431
0x18006a41c  mov     r8, [rdi+440h]; SecurityDescriptor
0x18006a423  mov     edx, 10h; SecurityInformation
0x18006a428  mov     rcx, rbp; Handle
0x18006a42b  call    cs:__imp_NtSetSecurityObject
0x18006a431  and     ebx, 24h
0x18006a434  jz      short loc_18006A44A
0x18006a436  mov     r8, [rdi+440h]; SecurityDescriptor
0x18006a43d  mov     edx, ebx; SecurityInformation
0x18006a43f  mov     rcx, rbp; Handle
0x18006a442  call    cs:__imp_NtSetSecurityObject
0x18006a448  mov     esi, eax
0x18006a44a  mov     r8, [rdi+440h]; SecurityDescriptor
0x18006a451  mov     edx, 3; SecurityInformation
0x18006a456  mov     rcx, rbp; Handle
0x18006a459  call    cs:__imp_NtSetSecurityObject
0x18006a45f  test    esi, esi
0x18006a461  js      short loc_18006A46D
0x18006a463  test    eax, eax
0x18006a465  jns     loc_18006A376
0x18006a46b  mov     esi, eax
0x18006a46d  mov     ecx, esi
0x18006a46f  call    BaseSetLastNTError
0x18006a474  xor     eax, eax
0x18006a476  add     rsp, 28h
0x18006a47a  pop     rdi
0x18006a47b  pop     rsi
0x18006a47c  pop     rbp
0x18006a47d  pop     rbx
0x18006a47e  retn
```
