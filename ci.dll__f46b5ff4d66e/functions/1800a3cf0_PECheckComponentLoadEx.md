# PECheckComponentLoadEx

- ea: `0x1800a3cf0`
- end: `0x1800a3fae`
- name: `PECheckComponentLoadEx`
- size: `702`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800a3ae8`

## callees

- `0x18000ea44`
- `0x18000ec18`
- `0x18000ee04`
- `0x180020474`
- `0x18002bef0`
- `0x18007ee50`
- `0x1800a3cf0`
- `0x1800a3fb4`
- `0x1800a40b4`
- `0x1800a43b4`
- `0x1800a452c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1800a3de6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800a3de6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a3e47`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a3e47`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1800a3dfb`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1800a3dfb`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a3e3b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a3e3b`
- `ntoskrnl!PsIsCurrentThreadPrefetching` at `0x1800a3f65`
- `ntoskrnl!PsIsCurrentThreadPrefetching` at `0x1800a3f65`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1800a3d61`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1800a3d61`

## pseudocode

```c
__int64 __fastcall PECheckComponentLoadEx(
        void *a1,
        __int64 a2,
        const UNICODE_STRING *a3,
        unsigned int a4,
        int a5,
        _DWORD *a6)
{
  int v8; // esi
  int DPLForInterrupt; // ebx
  int v10; // eax
  unsigned int v11; // edi
  int v12; // r14d
  unsigned int v13; // ebx
  const UNICODE_STRING *v14; // r14
  unsigned int v15; // edi
  __int64 *v16; // rdx
  int v18; // esi
  char v19[4]; // [rsp+30h] [rbp-48h] BYREF
  __int16 SystemInformation; // [rsp+34h] [rbp-44h] BYREF
  char v21; // [rsp+36h] [rbp-42h]
  int v22; // [rsp+38h] [rbp-40h] BYREF
  int v23; // [rsp+3Ch] [rbp-3Ch] BYREF
  const UNICODE_STRING *v24; // [rsp+40h] [rbp-38h]
  void *Source2; // [rsp+48h] [rbp-30h]
  __int128 v26; // [rsp+50h] [rbp-28h] BYREF
  int v27; // [rsp+60h] [rbp-18h]

  v24 = a3;
  Source2 = a1;
  v27 = 0;
  v23 = 0;
  v26 = 0;
  v8 = 0;
  v22 = 0;
  v19[0] = 0;
  if ( g_PEAuthStateVariables )
  {
    SystemInformation = 0;
    v21 = 0;
    if ( ZwQuerySystemInformation(SystemFileCacheInformation|0x80, &SystemInformation, 3u, 0) < 0
      || (_BYTE)SystemInformation
      || (DPLForInterrupt = GetDPLForInterrupt(1), v10 = GetDPLForInterrupt(65), DPLForInterrupt)
      || v10
      || (unsigned __int8)GetDR7Value() )
    {
      PEAuthStoreParameter(1, 0);
      g_PEAuthStateVariables = 0;
    }
  }
  v11 = I_PELoadGRL(a1, a2, a3);
  v12 = 2;
  if ( a2 )
  {
    v13 = v11 | I_PECheckMincryptPolicy(a2, a4, (unsigned int)&v26, (unsigned int)&v23, (__int64)&v22);
    if ( v13 )
    {
      v8 = v22;
    }
    else
    {
      KeEnterCriticalRegion();
      ExAcquireResourceSharedLite(&g_GRLContextLock, 1u);
      if ( qword_180048410 )
        v13 = (unsigned int)MFIsHashInGRL(qword_180048410, Source2, a4 == 0) != 0 ? 0x2000 : 0;
      else
        v13 |= 0x1000u;
      ExReleaseResourceLite(&g_GRLContextLock);
      KeLeaveCriticalRegion();
      v8 = v22;
      if ( v22 == 0x10002 )
      {
        if ( (int)PEAuthGetDebugCredentialsData(v19) < 0 )
        {
          PEAuthStoreParameter(1, 0);
          g_PEAuthStateVariables = 0;
          PEAuthStoreParameter(2, 0);
        }
        if ( !v19[0] )
          v13 |= 0x10000u;
      }
    }
  }
  else
  {
    v13 = v11;
  }
  if ( v13 )
  {
    v15 = -1073740760;
    v18 = 1;
    if ( (v13 & 0xFFFFEFCF) == 0 )
    {
      v15 = 0;
      v18 = 0;
      *a6 |= v13;
    }
    if ( a4 )
    {
      v15 = 0;
      PEAuthStoreParameter(1, 0);
      g_PEAuthStateVariables = 0;
    }
    else
    {
      v12 = 1;
    }
    v13 |= v12;
    if ( PsIsCurrentThreadPrefetching() )
    {
      v18 = 0;
    }
    else if ( (g_PEAuthConfigOptions & 1) != 0 )
    {
      v14 = v24;
      I_PEWriteComponentLoadExEvents(v13, *(unsigned int *)(a2 + 8), v24, a4);
LABEL_24:
      if ( !v18 )
        return v15;
      goto LABEL_16;
    }
    v14 = v24;
    goto LABEL_24;
  }
  v14 = v24;
  v15 = 0;
  if ( (v8 & 0x10000) != 0 )
    *a6 |= 0x1000000u;
LABEL_16:
  if ( Source2 )
  {
    v16 = (__int64 *)&v26;
    if ( !v23 )
      v16 = g_rgEmptyHash;
    I_PEUpdateHashCache(Source2, (__int64)v16, v14, v13, a4, a5);
  }
  return v15;
}

```

## disassembly

```asm
0x1800a3cf0  push    rbp
0x1800a3cf2  push    rbx
0x1800a3cf3  push    rsi
0x1800a3cf4  push    rdi
0x1800a3cf5  push    r12
0x1800a3cf7  push    r13
0x1800a3cf9  push    r14
0x1800a3cfb  push    r15
0x1800a3cfd  mov     rbp, rsp
0x1800a3d00  sub     rsp, 78h
0x1800a3d04  mov     rax, cs:__security_cookie
0x1800a3d0b  xor     rax, rsp
0x1800a3d0e  mov     [rbp+var_10], rax
0x1800a3d12  mov     r15, [rbp+arg_28]
0x1800a3d16  xor     edi, edi
0x1800a3d18  xor     eax, eax
0x1800a3d1a  mov     [rbp+var_38], r8
0x1800a3d1e  cmp     cs:g_PEAuthStateVariables, edi
0x1800a3d24  xorps   xmm0, xmm0
0x1800a3d27  mov     r12d, r9d
0x1800a3d2a  mov     [rbp+Source2], rcx
0x1800a3d2e  mov     r13, rdx
0x1800a3d31  mov     [rbp+var_18], eax
0x1800a3d34  lea     r14d, [rax+1]
0x1800a3d38  mov     [rbp+var_3C], edi
0x1800a3d3b  movups  [rbp+var_28], xmm0
0x1800a3d3f  mov     esi, edi
0x1800a3d41  mov     [rbp+var_40], edi
0x1800a3d44  mov     [rbp+var_48], dil
0x1800a3d48  jz      short loc_1800A3DAA
0x1800a3d4a  xor     r9d, r9d; ReturnLength
0x1800a3d4d  mov     [rbp+SystemInformation], ax
0x1800a3d51  lea     r8d, [rax+3]; SystemInformationLength
0x1800a3d55  mov     [rbp+var_42], al
0x1800a3d58  lea     rdx, [rbp+SystemInformation]; SystemInformation
0x1800a3d5c  mov     ecx, 95h; SystemInformationClass
0x1800a3d61  call    cs:__imp_ZwQuerySystemInformation
0x1800a3d68  nop     dword ptr [rax+rax+00h]
0x1800a3d6d  test    eax, eax
0x1800a3d6f  js      short loc_1800A3D9A
0x1800a3d71  cmp     byte ptr [rbp+SystemInformation], dil
0x1800a3d75  jnz     short loc_1800A3D9A
0x1800a3d77  mov     ecx, r14d
0x1800a3d7a  call    GetDPLForInterrupt
0x1800a3d7f  lea     ecx, [rdi+41h]
0x1800a3d82  mov     ebx, eax
0x1800a3d84  call    GetDPLForInterrupt
0x1800a3d89  test    ebx, ebx
0x1800a3d8b  jnz     short loc_1800A3D9A
0x1800a3d8d  test    eax, eax
0x1800a3d8f  jnz     short loc_1800A3D9A
0x1800a3d91  call    GetDR7Value
0x1800a3d96  test    al, al
0x1800a3d98  jz      short loc_1800A3DAA
0x1800a3d9a  xor     edx, edx
0x1800a3d9c  mov     ecx, r14d
0x1800a3d9f  call    PEAuthStoreParameter
0x1800a3da4  mov     cs:g_PEAuthStateVariables, edi
0x1800a3daa  call    I_PELoadGRL
0x1800a3daf  mov     edi, eax
0x1800a3db1  mov     r14d, 2
0x1800a3db7  test    r13, r13
0x1800a3dba  jz      loc_1800A3ED3
0x1800a3dc0  lea     rax, [rbp+var_40]
0x1800a3dc4  mov     edx, r12d
0x1800a3dc7  lea     r9, [rbp+var_3C]
0x1800a3dcb  mov     qword ptr [rsp+78h+var_58], rax
0x1800a3dd0  lea     r8, [rbp+var_28]
0x1800a3dd4  mov     rcx, r13
0x1800a3dd7  call    I_PECheckMincryptPolicy
0x1800a3ddc  mov     ebx, eax
0x1800a3dde  or      ebx, edi
0x1800a3de0  jnz     loc_1800A3EE0
0x1800a3de6  call    cs:__imp_KeEnterCriticalRegion
0x1800a3ded  nop     dword ptr [rax+rax+00h]
0x1800a3df2  mov     dl, 1; Wait
0x1800a3df4  lea     rcx, g_GRLContextLock; Resource
0x1800a3dfb  call    cs:__imp_ExAcquireResourceSharedLite
0x1800a3e02  nop     dword ptr [rax+rax+00h]
0x1800a3e07  mov     rcx, cs:qword_180048410
0x1800a3e0e  test    rcx, rcx
0x1800a3e11  jz      loc_1800A3ED7
0x1800a3e17  mov     rdx, [rbp+Source2]
0x1800a3e1b  xor     r8d, r8d
0x1800a3e1e  test    r12d, r12d
0x1800a3e21  setz    r8b
0x1800a3e25  call    MFIsHashInGRL
0x1800a3e2a  neg     eax
0x1800a3e2c  sbb     ebx, ebx
0x1800a3e2e  and     ebx, 2000h
0x1800a3e34  lea     rcx, g_GRLContextLock; Resource
0x1800a3e3b  call    cs:__imp_ExReleaseResourceLite
0x1800a3e42  nop     dword ptr [rax+rax+00h]
0x1800a3e47  call    cs:__imp_KeLeaveCriticalRegion
0x1800a3e4e  nop     dword ptr [rax+rax+00h]
0x1800a3e53  mov     esi, [rbp+var_40]
0x1800a3e56  mov     eax, esi
0x1800a3e58  xor     eax, 10002h
0x1800a3e5d  jz      loc_1800A3EEE
0x1800a3e63  test    ebx, ebx
0x1800a3e65  jnz     loc_1800A3F2C
0x1800a3e6b  mov     r14, [rbp+var_38]
0x1800a3e6f  xor     edi, edi
0x1800a3e71  bt      esi, 10h
0x1800a3e75  jb      loc_1800A3FA4
0x1800a3e7b  mov     rax, [rbp+Source2]
0x1800a3e7f  test    rax, rax
0x1800a3e82  jz      short loc_1800A3EB3
0x1800a3e84  cmp     [rbp+var_3C], 0
0x1800a3e88  lea     r8, g_rgEmptyHash
0x1800a3e8f  mov     r10d, [rbp+arg_20]
0x1800a3e93  lea     rdx, [rbp+var_28]
0x1800a3e97  cmovz   rdx, r8
0x1800a3e9b  mov     [rsp+78h+var_50], r10d; int
0x1800a3ea0  mov     r8, r14
0x1800a3ea3  mov     [rsp+78h+var_58], r12d; int
0x1800a3ea8  mov     r9d, ebx
0x1800a3eab  mov     rcx, rax; Source2
0x1800a3eae  call    I_PEUpdateHashCache
0x1800a3eb3  mov     eax, edi
0x1800a3eb5  mov     rcx, [rbp+var_10]
0x1800a3eb9  xor     rcx, rsp; StackCookie
0x1800a3ebc  call    __security_check_cookie
0x1800a3ec1  add     rsp, 78h
0x1800a3ec5  pop     r15
0x1800a3ec7  pop     r14
0x1800a3ec9  pop     r13
0x1800a3ecb  pop     r12
0x1800a3ecd  pop     rdi
0x1800a3ece  pop     rsi
0x1800a3ecf  pop     rbx
0x1800a3ed0  pop     rbp
0x1800a3ed1  retn
0x1800a3ed3  mov     ebx, edi
0x1800a3ed5  jmp     short loc_1800A3E63
0x1800a3ed7  bts     ebx, 0Ch
0x1800a3edb  jmp     loc_1800A3E34
0x1800a3ee0  mov     esi, [rbp+var_40]
0x1800a3ee3  jmp     loc_1800A3E63
0x1800a3ee8  test    esi, esi
0x1800a3eea  jz      short loc_1800A3EB3
0x1800a3eec  jmp     short loc_1800A3E7B
0x1800a3eee  lea     rcx, [rbp+var_48]
0x1800a3ef2  call    PEAuthGetDebugCredentialsData
0x1800a3ef7  test    eax, eax
0x1800a3ef9  jns     short loc_1800A3F19
0x1800a3efb  xor     edx, edx
0x1800a3efd  lea     ecx, [rdx+1]
0x1800a3f00  call    PEAuthStoreParameter
0x1800a3f05  xor     edx, edx
0x1800a3f07  mov     cs:g_PEAuthStateVariables, 0
0x1800a3f11  mov     ecx, r14d
0x1800a3f14  call    PEAuthStoreParameter
0x1800a3f19  cmp     [rbp+var_48], 0
0x1800a3f1d  ja      loc_1800A3E63
0x1800a3f23  bts     ebx, 10h
0x1800a3f27  jmp     loc_1800A3E63
0x1800a3f2c  mov     eax, 1
0x1800a3f31  mov     edi, 0C0000428h
0x1800a3f36  mov     esi, eax
0x1800a3f38  test    ebx, 0FFFFEFCFh
0x1800a3f3e  jnz     short loc_1800A3F47
0x1800a3f40  xor     edi, edi
0x1800a3f42  xor     esi, esi
0x1800a3f44  or      [r15], ebx
0x1800a3f47  test    r12d, r12d
0x1800a3f4a  jz      short loc_1800A3F5F
0x1800a3f4c  xor     edi, edi
0x1800a3f4e  xor     edx, edx
0x1800a3f50  mov     ecx, eax
0x1800a3f52  call    PEAuthStoreParameter
0x1800a3f57  mov     cs:g_PEAuthStateVariables, edi
0x1800a3f5d  jmp     short loc_1800A3F62
0x1800a3f5f  mov     r14d, eax
0x1800a3f62  or      ebx, r14d
0x1800a3f65  call    cs:__imp_PsIsCurrentThreadPrefetching
0x1800a3f6c  nop     dword ptr [rax+rax+00h]
0x1800a3f71  test    al, al
0x1800a3f73  jz      short loc_1800A3F80
0x1800a3f75  xor     esi, esi
0x1800a3f77  mov     r14, [rbp+var_38]
0x1800a3f7b  jmp     loc_1800A3EE8
0x1800a3f80  mov     eax, cs:g_PEAuthConfigOptions
0x1800a3f86  test    al, 1
0x1800a3f88  jz      short loc_1800A3F77
0x1800a3f8a  mov     r14, [rbp+var_38]
0x1800a3f8e  mov     r9d, r12d
0x1800a3f91  mov     edx, [r13+8]
0x1800a3f95  mov     r8, r14
0x1800a3f98  mov     ecx, ebx
0x1800a3f9a  call    I_PEWriteComponentLoadExEvents
0x1800a3f9f  jmp     loc_1800A3EE8
0x1800a3fa4  bts     dword ptr [r15], 18h
0x1800a3fa9  jmp     loc_1800A3E7B
```
