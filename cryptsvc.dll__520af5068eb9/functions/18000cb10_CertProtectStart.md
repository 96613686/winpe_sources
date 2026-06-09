# CertProtectStart

- ea: `0x18000cb10`
- end: `0x18000cc60`
- name: `CertProtectStart`
- size: `336`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000a690`

## callees

- `0x18000cb10`
- `0x18000d548`
- `0x18000e2f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cbd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cbd2`
- `RPCRT4!RpcServerRegisterIf3` at `0x18000cc2d`
- `RPCRT4!RpcServerRegisterIf3` at `0x18000cc2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cc3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cc3f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000cbeb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000cbeb`

## pseudocode

```c
__int64 CertProtectStart()
{
  __int64 v0; // rdx
  WCHAR *v1; // rax
  const wchar_t *v2; // rcx
  __int128 v3; // xmm1
  __int128 v4; // xmm0
  __int128 v5; // xmm1
  __int128 v6; // xmm0
  __int128 v7; // xmm1
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  DWORD LastError; // eax
  DWORD v17; // ebx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-198h] BYREF
  WCHAR StringSecurityDescriptor[184]; // [rsp+50h] [rbp-188h] BYREF

  v0 = 2;
  SecurityDescriptor = 0;
  v1 = StringSecurityDescriptor;
  v2 = L"D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GR;;;AC)(A;;GR;;;S-1-15-3-1024-3203351429-212044378"
        "4-2872670797-1918958302-2829055647-4275794519-765664414-2751773334)";
  do
  {
    v3 = *((_OWORD *)v2 + 1);
    *(_OWORD *)v1 = *(_OWORD *)v2;
    v4 = *((_OWORD *)v2 + 2);
    *((_OWORD *)v1 + 1) = v3;
    v5 = *((_OWORD *)v2 + 3);
    *((_OWORD *)v1 + 2) = v4;
    v6 = *((_OWORD *)v2 + 4);
    *((_OWORD *)v1 + 3) = v5;
    v7 = *((_OWORD *)v2 + 5);
    *((_OWORD *)v1 + 4) = v6;
    v8 = *((_OWORD *)v2 + 6);
    *((_OWORD *)v1 + 5) = v7;
    v9 = *((_OWORD *)v2 + 7);
    v2 += 64;
    *((_OWORD *)v1 + 6) = v8;
    *((_OWORD *)v1 + 7) = v9;
    v1 += 64;
    --v0;
  }
  while ( v0 );
  v10 = *((_OWORD *)v2 + 1);
  *(_OWORD *)v1 = *(_OWORD *)v2;
  v11 = *((_OWORD *)v2 + 2);
  *((_OWORD *)v1 + 1) = v10;
  v12 = *((_OWORD *)v2 + 3);
  *((_OWORD *)v1 + 2) = v11;
  v13 = *((_OWORD *)v2 + 4);
  *((_OWORD *)v1 + 3) = v12;
  v14 = *((_OWORD *)v2 + 5);
  *((_OWORD *)v1 + 4) = v13;
  v15 = *(_OWORD *)(v2 + 45);
  *((_OWORD *)v1 + 5) = v14;
  *(_OWORD *)(v1 + 45) = v15;
  if ( (unsigned int)CryptnetUrlCacheSvcServiceStart()
    && ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
  {
    LastError = RpcServerRegisterIf3(qword_180019300, 0, 0, 33, 10, 0, CryptSvcSecurityCallback, SecurityDescriptor);
  }
  else
  {
    LastError = GetLastError();
  }
  v17 = LastError;
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return v17;
}

```

## disassembly

```asm
0x18000cb10  push    rbx
0x18000cb12  sub     rsp, 1D0h
0x18000cb19  mov     rax, cs:__security_cookie
0x18000cb20  xor     rax, rsp
0x18000cb23  mov     [rsp+1D8h+var_18], rax
0x18000cb2b  mov     edx, 2
0x18000cb30  mov     [rsp+1D8h+SecurityDescriptor], 0
0x18000cb39  lea     rax, [rsp+1D8h+StringSecurityDescriptor]
0x18000cb3e  lea     rcx, aDAGrgwgxWdAGrg; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x18000cb45  lea     r8d, [rdx+7Eh]
0x18000cb49  movups  xmm0, xmmword ptr [rcx]
0x18000cb4c  movups  xmm1, xmmword ptr [rcx+10h]
0x18000cb50  movups  xmmword ptr [rax], xmm0
0x18000cb53  movups  xmm0, xmmword ptr [rcx+20h]
0x18000cb57  movups  xmmword ptr [rax+10h], xmm1
0x18000cb5b  movups  xmm1, xmmword ptr [rcx+30h]
0x18000cb5f  movups  xmmword ptr [rax+20h], xmm0
0x18000cb63  movups  xmm0, xmmword ptr [rcx+40h]
0x18000cb67  movups  xmmword ptr [rax+30h], xmm1
0x18000cb6b  movups  xmm1, xmmword ptr [rcx+50h]
0x18000cb6f  movups  xmmword ptr [rax+40h], xmm0
0x18000cb73  movups  xmm0, xmmword ptr [rcx+60h]
0x18000cb77  movups  xmmword ptr [rax+50h], xmm1
0x18000cb7b  movups  xmm1, xmmword ptr [rcx+70h]
0x18000cb7f  add     rcx, r8
0x18000cb82  movups  xmmword ptr [rax+60h], xmm0
0x18000cb86  movups  xmmword ptr [rax+70h], xmm1
0x18000cb8a  add     rax, r8
0x18000cb8d  sub     rdx, 1
0x18000cb91  jnz     short loc_18000CB49
0x18000cb93  movups  xmm0, xmmword ptr [rcx]
0x18000cb96  movups  xmm1, xmmword ptr [rcx+10h]
0x18000cb9a  movups  xmmword ptr [rax], xmm0
0x18000cb9d  movups  xmm0, xmmword ptr [rcx+20h]
0x18000cba1  movups  xmmword ptr [rax+10h], xmm1
0x18000cba5  movups  xmm1, xmmword ptr [rcx+30h]
0x18000cba9  movups  xmmword ptr [rax+20h], xmm0
0x18000cbad  movups  xmm0, xmmword ptr [rcx+40h]
0x18000cbb1  movups  xmmword ptr [rax+30h], xmm1
0x18000cbb5  movups  xmm1, xmmword ptr [rcx+50h]
0x18000cbb9  movups  xmmword ptr [rax+40h], xmm0
0x18000cbbd  movups  xmm0, xmmword ptr [rcx+5Ah]
0x18000cbc1  movups  xmmword ptr [rax+50h], xmm1
0x18000cbc5  movups  xmmword ptr [rax+5Ah], xmm0
0x18000cbc9  call    CryptnetUrlCacheSvcServiceStart
0x18000cbce  test    eax, eax
0x18000cbd0  jnz     short loc_18000CBDA
0x18000cbd2  call    cs:__imp_GetLastError
0x18000cbd8  jmp     short loc_18000CC33
0x18000cbda  xor     r9d, r9d; SecurityDescriptorSize
0x18000cbdd  lea     r8, [rsp+1D8h+SecurityDescriptor]; SecurityDescriptor
0x18000cbe2  lea     rcx, [rsp+1D8h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18000cbe7  lea     edx, [r9+1]; StringSDRevision
0x18000cbeb  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000cbf1  test    eax, eax
0x18000cbf3  jz      short loc_18000CBD2
0x18000cbf5  mov     rax, [rsp+1D8h+SecurityDescriptor]
0x18000cbfa  lea     rcx, qword_180019300
0x18000cc01  mov     [rsp+1D8h+var_1A0], rax
0x18000cc06  mov     r9d, 21h ; '!'
0x18000cc0c  lea     rax, CryptSvcSecurityCallback
0x18000cc13  xor     r8d, r8d
0x18000cc16  mov     [rsp+1D8h+var_1A8], rax
0x18000cc1b  xor     edx, edx
0x18000cc1d  mov     [rsp+1D8h+var_1B0], 0
0x18000cc25  mov     [rsp+1D8h+var_1B8], 0Ah
0x18000cc2d  call    cs:__imp_RpcServerRegisterIf3
0x18000cc33  mov     ebx, eax
0x18000cc35  mov     rcx, [rsp+1D8h+SecurityDescriptor]; hMem
0x18000cc3a  test    rcx, rcx
0x18000cc3d  jz      short loc_18000CC45
0x18000cc3f  call    cs:__imp_LocalFree
0x18000cc45  mov     eax, ebx
0x18000cc47  mov     rcx, [rsp+1D8h+var_18]
0x18000cc4f  xor     rcx, rsp; StackCookie
0x18000cc52  call    __security_check_cookie
0x18000cc57  add     rsp, 1D0h
0x18000cc5e  pop     rbx
0x18000cc5f  retn
```
