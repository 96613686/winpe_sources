# Pku2uUnLoadDH(void)

- ea: `0x180030e28`
- end: `0x180030ef4`
- name: `?Pku2uUnLoadDH@@YAXXZ`
- size: `204`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800370d0`

## callees

- `0x18001a1d0`
- `0x18001fc04`
- `0x180021a54`
- `0x180030e28`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x180030ed8`
- `ntdll!RtlDeleteCriticalSection` at `0x180030ed8`
- `ntdll!RtlLeaveCriticalSection` at `0x180030ea5`
- `ntdll!RtlLeaveCriticalSection` at `0x180030ea5`
- `ntdll!RtlEnterCriticalSection` at `0x180030e66`
- `ntdll!RtlEnterCriticalSection` at `0x180030e66`
- `CRYPTSP!CryptReleaseContext` at `0x180030e41`
- `CRYPTSP!CryptReleaseContext` at `0x180030e41`

## pseudocode

```c
void Pku2uUnLoadDH(void)
{
  __int64 i; // rbx

  if ( Pku2uGlobalCSPProvider )
  {
    CryptReleaseContext(Pku2uGlobalCSPProvider, 0);
    Pku2uGlobalCSPProvider = 0;
  }
  if ( Pku2uGlobalWellknownDomainParamtersLockInitialized )
  {
    RtlEnterCriticalSection(&Pku2uGlobalWellknownDomainParamtersLock);
    for ( i = 0; (unsigned int)i < Pku2uGlobalWellknownDomainParamtersCount; i = (unsigned int)(i + 1) )
      Pku2uFreeDHParameters((struct _CERT_X942_DH_PARAMETERS *)&Pku2uGlobalWellknownDomainParamters + i);
    Pku2uGlobalWellknownDomainParamtersCount = 0;
    RtlLeaveCriticalSection(&Pku2uGlobalWellknownDomainParamtersLock);
    memset_0(&Pku2uGlobalWellknownDomainParamters, 0, 0x1C20u);
    if ( Pku2uGlobalEmpheralDHAlg )
      KerbFreeData(0xDu, Pku2uGlobalEmpheralDHAlg);
    RtlDeleteCriticalSection(&Pku2uGlobalWellknownDomainParamtersLock);
    Pku2uGlobalWellknownDomainParamtersLockInitialized = 0;
  }
}

```

## disassembly

```asm
0x180030e28  mov     [rsp+arg_0], rbx
0x180030e2d  push    r14
0x180030e2f  sub     rsp, 20h
0x180030e33  mov     rcx, cs:?Pku2uGlobalCSPProvider@@3_KA; hProv
0x180030e3a  test    rcx, rcx
0x180030e3d  jz      short loc_180030E52
0x180030e3f  xor     edx, edx; dwFlags
0x180030e41  call    cs:__imp_CryptReleaseContext
0x180030e47  mov     cs:?Pku2uGlobalCSPProvider@@3_KA, 0; unsigned __int64 Pku2uGlobalCSPProvider
0x180030e52  cmp     cs:?Pku2uGlobalWellknownDomainParamtersLockInitialized@@3HA, 0; int Pku2uGlobalWellknownDomainParamtersLockInitialized
0x180030e59  jz      loc_180030EE8
0x180030e5f  lea     rcx, ?Pku2uGlobalWellknownDomainParamtersLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180030e66  call    cs:__imp_RtlEnterCriticalSection
0x180030e6c  xor     ebx, ebx
0x180030e6e  lea     r14, ?Pku2uGlobalWellknownDomainParamters@@3PAU_CERT_X942_DH_PARAMETERS@@A; _CERT_X942_DH_PARAMETERS near * Pku2uGlobalWellknownDomainParamters
0x180030e75  cmp     cs:?Pku2uGlobalWellknownDomainParamtersCount@@3KA, ebx; ulong Pku2uGlobalWellknownDomainParamtersCount
0x180030e7b  jbe     short loc_180030E94
0x180030e7d  lea     rdx, [rbx+rbx*8]
0x180030e81  lea     rcx, [r14+rdx*8]; struct _CERT_X942_DH_PARAMETERS *
0x180030e85  call    ?Pku2uFreeDHParameters@@YAXPEAU_CERT_X942_DH_PARAMETERS@@@Z; Pku2uFreeDHParameters(_CERT_X942_DH_PARAMETERS *)
0x180030e8a  inc     ebx
0x180030e8c  cmp     ebx, cs:?Pku2uGlobalWellknownDomainParamtersCount@@3KA; ulong Pku2uGlobalWellknownDomainParamtersCount
0x180030e92  jb      short loc_180030E7D
0x180030e94  lea     rcx, ?Pku2uGlobalWellknownDomainParamtersLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180030e9b  mov     cs:?Pku2uGlobalWellknownDomainParamtersCount@@3KA, 0; ulong Pku2uGlobalWellknownDomainParamtersCount
0x180030ea5  call    cs:__imp_RtlLeaveCriticalSection
0x180030eab  xor     edx, edx; Val
0x180030ead  mov     r8d, 1C20h; Size
0x180030eb3  mov     rcx, r14; void *
0x180030eb6  call    memset_0
0x180030ebb  mov     rdx, cs:?Pku2uGlobalEmpheralDHAlg@@3PEAUKERB_ALGORITHM_IDENTIFIER@@EA; void *
0x180030ec2  test    rdx, rdx
0x180030ec5  jz      short loc_180030ED1
0x180030ec7  mov     ecx, 0Dh; unsigned int
0x180030ecc  call    ?KerbFreeData@@YAXKPEAX@Z; KerbFreeData(ulong,void *)
0x180030ed1  lea     rcx, ?Pku2uGlobalWellknownDomainParamtersLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180030ed8  call    cs:__imp_RtlDeleteCriticalSection
0x180030ede  mov     cs:?Pku2uGlobalWellknownDomainParamtersLockInitialized@@3HA, 0; int Pku2uGlobalWellknownDomainParamtersLockInitialized
0x180030ee8  mov     rbx, [rsp+28h+arg_0]
0x180030eed  add     rsp, 20h
0x180030ef1  pop     r14
0x180030ef3  retn
```
