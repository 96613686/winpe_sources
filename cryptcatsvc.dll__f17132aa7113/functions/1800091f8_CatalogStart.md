# CatalogStart

- ea: `0x1800091f8`
- end: `0x18000934a`
- name: `CatalogStart`
- size: `338`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800091a0`

## callees

- `0x1800091f8`
- `0x18000ad54`
- `0x18000be40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800092bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800092bc`
- `RPCRT4!RpcServerRegisterIf3` at `0x180009317`
- `RPCRT4!RpcServerRegisterIf3` at `0x180009317`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009329`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009329`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800092d5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800092d5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 CatalogStart()
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
  if ( (unsigned int)_CatDBInitializeShutdown(0, 0)
    && ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
  {
    LastError = RpcServerRegisterIf3(qword_180023A60, 0, 0, 33, 1234, -1, CryptSvcSecurityCallback, SecurityDescriptor);
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
0x1800091f8  push    rbx
0x1800091fa  sub     rsp, 1D0h
0x180009201  mov     rax, cs:__security_cookie
0x180009208  xor     rax, rsp
0x18000920b  mov     [rsp+1D8h+var_18], rax
0x180009213  mov     edx, 2
0x180009218  mov     [rsp+1D8h+SecurityDescriptor], 0
0x180009221  lea     rax, [rsp+1D8h+StringSecurityDescriptor]
0x180009226  lea     rcx, aDAGrgwgxWdAGrg; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x18000922d  lea     r8d, [rdx+7Eh]
0x180009231  movups  xmm0, xmmword ptr [rcx]
0x180009234  movups  xmm1, xmmword ptr [rcx+10h]
0x180009238  movups  xmmword ptr [rax], xmm0
0x18000923b  movups  xmm0, xmmword ptr [rcx+20h]
0x18000923f  movups  xmmword ptr [rax+10h], xmm1
0x180009243  movups  xmm1, xmmword ptr [rcx+30h]
0x180009247  movups  xmmword ptr [rax+20h], xmm0
0x18000924b  movups  xmm0, xmmword ptr [rcx+40h]
0x18000924f  movups  xmmword ptr [rax+30h], xmm1
0x180009253  movups  xmm1, xmmword ptr [rcx+50h]
0x180009257  movups  xmmword ptr [rax+40h], xmm0
0x18000925b  movups  xmm0, xmmword ptr [rcx+60h]
0x18000925f  movups  xmmword ptr [rax+50h], xmm1
0x180009263  movups  xmm1, xmmword ptr [rcx+70h]
0x180009267  add     rcx, r8
0x18000926a  movups  xmmword ptr [rax+60h], xmm0
0x18000926e  movups  xmmword ptr [rax+70h], xmm1
0x180009272  add     rax, r8
0x180009275  sub     rdx, 1; int
0x180009279  jnz     short loc_180009231
0x18000927b  movups  xmm0, xmmword ptr [rcx]
0x18000927e  movups  xmm1, xmmword ptr [rcx+10h]
0x180009282  movups  xmmword ptr [rax], xmm0
0x180009285  movups  xmm0, xmmword ptr [rcx+20h]
0x180009289  movups  xmmword ptr [rax+10h], xmm1
0x18000928d  movups  xmm1, xmmword ptr [rcx+30h]
0x180009291  movups  xmmword ptr [rax+20h], xmm0
0x180009295  movups  xmm0, xmmword ptr [rcx+40h]
0x180009299  movups  xmmword ptr [rax+30h], xmm1
0x18000929d  movups  xmm1, xmmword ptr [rcx+50h]
0x1800092a1  movups  xmmword ptr [rax+40h], xmm0
0x1800092a5  movups  xmm0, xmmword ptr [rcx+5Ah]
0x1800092a9  xor     ecx, ecx; int
0x1800092ab  movups  xmmword ptr [rax+50h], xmm1
0x1800092af  movups  xmmword ptr [rax+5Ah], xmm0
0x1800092b3  call    ?_CatDBInitializeShutdown@@YAHHH@Z; _CatDBInitializeShutdown(int,int)
0x1800092b8  test    eax, eax
0x1800092ba  jnz     short loc_1800092C4
0x1800092bc  call    cs:__imp_GetLastError
0x1800092c2  jmp     short loc_18000931D
0x1800092c4  xor     r9d, r9d; SecurityDescriptorSize
0x1800092c7  lea     r8, [rsp+1D8h+SecurityDescriptor]; SecurityDescriptor
0x1800092cc  lea     rcx, [rsp+1D8h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800092d1  lea     edx, [r9+1]; StringSDRevision
0x1800092d5  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800092db  test    eax, eax
0x1800092dd  jz      short loc_1800092BC
0x1800092df  mov     rax, [rsp+1D8h+SecurityDescriptor]
0x1800092e4  lea     rcx, qword_180023A60
0x1800092eb  mov     [rsp+1D8h+var_1A0], rax
0x1800092f0  mov     r9d, 21h ; '!'
0x1800092f6  lea     rax, CryptSvcSecurityCallback
0x1800092fd  xor     r8d, r8d
0x180009300  mov     [rsp+1D8h+var_1A8], rax
0x180009305  xor     edx, edx
0x180009307  mov     [rsp+1D8h+var_1B0], 0FFFFFFFFh
0x18000930f  mov     [rsp+1D8h+var_1B8], 4D2h
0x180009317  call    cs:__imp_RpcServerRegisterIf3
0x18000931d  mov     ebx, eax
0x18000931f  mov     rcx, [rsp+1D8h+SecurityDescriptor]; hMem
0x180009324  test    rcx, rcx
0x180009327  jz      short loc_18000932F
0x180009329  call    cs:__imp_LocalFree
0x18000932f  mov     eax, ebx
0x180009331  mov     rcx, [rsp+1D8h+var_18]
0x180009339  xor     rcx, rsp; StackCookie
0x18000933c  call    __security_check_cookie
0x180009341  add     rsp, 1D0h
0x180009348  pop     rbx
0x180009349  retn
```
