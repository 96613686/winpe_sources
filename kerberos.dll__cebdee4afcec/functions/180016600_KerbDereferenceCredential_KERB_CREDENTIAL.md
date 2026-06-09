# KerbDereferenceCredential(_KERB_CREDENTIAL *)

- ea: `0x180016600`
- end: `0x180016739`
- name: `?KerbDereferenceCredential@@YAXPEAU_KERB_CREDENTIAL@@@Z`
- size: `313`
- prototype: `void __fastcall(struct _KERB_CREDENTIAL *)`
- caller_count: `26`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180006680`
- `0x180006ddc`
- `0x180021574`
- `0x18002bd40`
- `0x18002db10`
- `0x18003a1f0`
- `0x18005d250`
- `0x18005db10`
- `0x18005dbf0`
- `0x18007e540`
- `0x180082ef4`
- `0x180084b74`
- `0x18008ac68`
- `0x1800911f0`
- `0x1800a56e0`
- `0x1800a7640`
- `0x1800abf4c`
- `0x1800af650`
- `0x1800b2c30`
- `0x1800c0c80`
- `0x1800cae6c`
- `0x1800caeb0`
- `0x1800cb1f8`
- `0x1800cbb50`
- `0x1800ce714`
- `0x1800cf46c`

## callees

- `0x1800068d0`
- `0x1800069a0`
- `0x180016600`
- `0x1800305ac`
- `0x18006517c`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800166fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800166f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800166fa`
- `ntdll!NtClose` at `0x180016670`
- `ntdll!NtClose` at `0x180016670`
- `ntdll!RtlEnterCriticalSection` at `0x180016618`
- `ntdll!RtlEnterCriticalSection` at `0x180016618`
- `ntdll!RtlLeaveCriticalSection` at `0x18001662f`
- `ntdll!RtlLeaveCriticalSection` at `0x1800166da`
- `ntdll!RtlLeaveCriticalSection` at `0x18001662f`
- `ntdll!RtlLeaveCriticalSection` at `0x1800166da`
- `CRYPT32!CertFreeCertificateContext` at `0x180016726`
- `CRYPT32!CertFreeCertificateContext` at `0x180016726`
- `LSASRV!LsaIFreeSupplementalTokenInfo` at `0x180016661`
- `LSASRV!LsaIFreeSupplementalTokenInfo` at `0x180016661`

## pseudocode

```c
void __fastcall KerbDereferenceCredential(struct _KERB_CREDENTIAL *a1)
{
  struct _KERB_PRIMARY_CREDENTIAL *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  __int64 v6; // rdi
  const CERT_CONTEXT *v7; // rcx

  if ( a1 )
  {
    RtlEnterCriticalSection(&stru_180144A70);
    if ( (*((_DWORD *)a1 + 4))-- == 1 )
    {
      RtlLeaveCriticalSection(&stru_180144A70);
      if ( !*(_QWORD *)a1 )
      {
        v3 = (struct _KERB_PRIMARY_CREDENTIAL *)*((_QWORD *)a1 + 9);
        *((_DWORD *)a1 + 22) = 1147433539;
        if ( v3 )
          KerbFreePrimaryCredentials(v3, 1);
        if ( *((_QWORD *)a1 + 12) )
          LsaIFreeSupplementalTokenInfo();
        v4 = (void *)*((_QWORD *)a1 + 13);
        if ( v4 )
          NtClose(v4);
        if ( a1 != (struct _KERB_CREDENTIAL *)-48LL )
        {
          v5 = (void *)*((_QWORD *)a1 + 7);
          if ( v5 )
          {
            if ( KerbGlobalPackageState == 1 )
              ((void (*)(void))LsaFunctions->FreeLsaHeap)();
            else
              LocalFree(v5);
          }
          *((_OWORD *)a1 + 3) = 0;
        }
        v6 = *((_QWORD *)a1 + 17);
        if ( v6 )
        {
          KerbFreeProxyServer((struct _KERB_PROXY_SERVER *)(v6 + 16));
          KerbFreeString(v6 + 56);
          KerbFreeString(v6 + 72);
          v7 = *(const CERT_CONTEXT **)(v6 + 88);
          if ( v7 )
            CertFreeCertificateContext(v7);
          KerbFree(v6);
        }
        if ( KerbGlobalPackageState == 1 )
          ((void (__fastcall *)(struct _KERB_CREDENTIAL *))LsaFunctions->FreeLsaHeap)(a1);
        else
          LocalFree(a1);
      }
    }
    else
    {
      RtlLeaveCriticalSection(&stru_180144A70);
    }
  }
}

```

## disassembly

```asm
0x180016600  test    rcx, rcx
0x180016603  jz      locret_1800166D9
0x180016609  push    rbx
0x18001660a  sub     rsp, 20h
0x18001660e  mov     rbx, rcx
0x180016611  lea     rcx, stru_180144A70; CriticalSection
0x180016618  call    cs:__imp_RtlEnterCriticalSection
0x18001661e  add     dword ptr [rbx+10h], 0FFFFFFFFh
0x180016622  lea     rcx, stru_180144A70; CriticalSection
0x180016629  jnz     loc_1800166DA
0x18001662f  call    cs:__imp_RtlLeaveCriticalSection
0x180016635  cmp     qword ptr [rbx], 0
0x180016639  jnz     loc_1800166D4
0x18001663f  mov     rcx, [rbx+48h]; this
0x180016643  mov     [rsp+28h+arg_8], rdi
0x180016648  mov     dword ptr [rbx+58h], 44647243h
0x18001664f  test    rcx, rcx
0x180016652  jnz     loc_1800166E2
0x180016658  mov     rcx, [rbx+60h]
0x18001665c  test    rcx, rcx
0x18001665f  jz      short loc_180016667
0x180016661  call    cs:__imp_LsaIFreeSupplementalTokenInfo
0x180016667  mov     rcx, [rbx+68h]; Handle
0x18001666b  test    rcx, rcx
0x18001666e  jz      short loc_180016676
0x180016670  call    cs:__imp_NtClose
0x180016676  lea     rdi, [rbx+30h]
0x18001667a  test    rdi, rdi
0x18001667d  jz      short loc_1800166A7
0x18001667f  mov     rcx, [rdi+8]; hMem
0x180016683  test    rcx, rcx
0x180016686  jz      short loc_1800166A1
0x180016688  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1; KerberosState KerbGlobalPackageState
0x18001668f  jnz     short loc_1800166FA
0x180016691  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x180016698  mov     rax, [rax+30h]
0x18001669c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166a1  xorps   xmm0, xmm0
0x1800166a4  movups  xmmword ptr [rdi], xmm0
0x1800166a7  mov     rdi, [rbx+88h]
0x1800166ae  test    rdi, rdi
0x1800166b1  jnz     short loc_180016702
0x1800166b3  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1; KerberosState KerbGlobalPackageState
0x1800166ba  mov     rcx, rbx
0x1800166bd  mov     rdi, [rsp+28h+arg_8]
0x1800166c2  jnz     short loc_1800166EE
0x1800166c4  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x1800166cb  mov     rax, [rax+30h]
0x1800166cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166d4  add     rsp, 20h
0x1800166d8  pop     rbx
0x1800166d9  retn
0x1800166da  call    cs:__imp_RtlLeaveCriticalSection
0x1800166e0  jmp     short loc_1800166D4
0x1800166e2  mov     dl, 1; unsigned __int8
0x1800166e4  call    ?KerbFreePrimaryCredentials@@YAXPEAU_KERB_PRIMARY_CREDENTIAL@@E@Z; KerbFreePrimaryCredentials(_KERB_PRIMARY_CREDENTIAL *,uchar)
0x1800166e9  jmp     loc_180016658
0x1800166ee  add     rsp, 20h
0x1800166f2  pop     rbx
0x1800166f3  jmp     cs:__imp_LocalFree
0x1800166fa  call    cs:__imp_LocalFree
0x180016700  jmp     short loc_1800166A1
0x180016702  lea     rcx, [rdi+10h]; struct _KERB_PROXY_SERVER *
0x180016706  call    ?KerbFreeProxyServer@@YAXPEAU_KERB_PROXY_SERVER@@@Z; KerbFreeProxyServer(_KERB_PROXY_SERVER *)
0x18001670b  lea     rcx, [rdi+38h]
0x18001670f  call    KerbFreeString
0x180016714  lea     rcx, [rdi+48h]
0x180016718  call    KerbFreeString
0x18001671d  mov     rcx, [rdi+58h]; pCertContext
0x180016721  test    rcx, rcx
0x180016724  jz      short loc_18001672C
0x180016726  call    cs:__imp_CertFreeCertificateContext
0x18001672c  mov     rcx, rdi
0x18001672f  call    KerbFree
0x180016734  jmp     loc_1800166B3
```
