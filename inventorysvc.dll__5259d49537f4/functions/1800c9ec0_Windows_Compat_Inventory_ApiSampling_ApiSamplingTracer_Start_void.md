# Windows::Compat::Inventory::ApiSampling::ApiSamplingTracer::Start(void)

- ea: `0x1800c9ec0`
- end: `0x1800ca01e`
- name: `?Start@ApiSamplingTracer@ApiSampling@Inventory@Compat@Windows@@UEAAJXZ`
- size: `350`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::ApiSampling::ApiSamplingTracer *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180002c40`
- `0x1800152d0`
- `0x180031b3c`
- `0x1800c7cec`
- `0x1800c9150`
- `0x1800c9ec0`
- `0x1800ca1ac`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c9f20`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c9f20`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c9f69`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c9fed`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c9f69`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c9fed`

## string_xrefs

- `0x1800c9fa7`: `Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::ApiSamplingStart`
- `0x1800c9fd2`: `Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::ApiSamplingStart`
- `0x1800c9f51`: `Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::Start`
- `0x1800c9f80`: `Windows::Compat::Inventory::ApiSampling::ApiSamplingTracer::Start`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Compat::Inventory::ApiSampling::ApiSamplingTracer::Start(
        Windows::Compat::Inventory::ApiSampling::ApiSamplingTracer *this)
{
  Windows::Compat::Inventory::ApiSampling::ApiSamplingHost *v2; // rax
  void (__fastcall ***v3)(_QWORD, __int64); // rcx
  __int64 v4; // rsi
  int v5; // eax
  unsigned int v6; // ebx
  __int64 (*v7)(void); // rax
  __int64 v8; // rcx
  int v9; // eax
  Windows::Compat::Inventory::ApiSampling::ApiSamplingHost *v11; // [rsp+50h] [rbp+8h]

  if ( !*((_QWORD *)this + 3) )
  {
    v11 = (Windows::Compat::Inventory::ApiSampling::ApiSamplingHost *)operator new(0x88u);
    v2 = Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::ApiSamplingHost(v11);
    v3 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 3);
    *((_QWORD *)this + 3) = v2;
    if ( v3 )
      (**v3)(v3, 1);
  }
  v4 = *((_QWORD *)this + 3);
  AcquireSRWLockExclusive((PSRWLOCK)(v4 + 48));
  if ( *(_QWORD *)(v4 + 88)
    || (v5 = Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::LazyApiSamplingInitialize((Windows::Compat::Inventory::ApiSampling::ApiSamplingHost *)v4),
        v6 = v5,
        v5 >= 0) )
  {
    v7 = *(__int64 (**)(void))(v4 + 120);
    if ( v7 )
    {
      v9 = v7();
      if ( v9 < 0 )
        AslLogCallPrintf(
          1,
          "Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::ApiSamplingStart",
          156,
          "APISamplingStart failed [%#x]",
          v9);
    }
    else
    {
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::ApiSamplingStart",
        148,
        "m_pfnApiSamplingStart is null");
    }
    *(_BYTE *)(v4 + 42) = 1;
    if ( v4 != -48 )
      ReleaseSRWLockExclusive((PSRWLOCK)(v4 + 48));
    Windows::Compat::Inventory::ApiSampling::ApiSamplingTracer::WriteStateToRegistry(v8, 2);
    v6 = 0;
  }
  else
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::Start",
      226,
      "APISamplingInitialize failed [%#x]",
      v5);
    if ( v4 != -48 )
      ReleaseSRWLockExclusive((PSRWLOCK)(v4 + 48));
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::ApiSampling::ApiSamplingTracer::Start",
      948,
      "Failed to start ApiSamplingHost [%#x]",
      v6);
  }
  Windows::Compat::Inventory::Service::Tracer::LogStart(this, v6);
  return v6;
}

```

## disassembly

```asm
0x1800c9ec0  mov     [rsp+arg_8], rbx
0x1800c9ec5  mov     [rsp+arg_10], rbp
0x1800c9eca  push    rsi
0x1800c9ecb  push    rdi
0x1800c9ecc  push    r15
0x1800c9ece  sub     rsp, 30h
0x1800c9ed2  mov     rbp, rcx
0x1800c9ed5  mov     r15d, 1
0x1800c9edb  cmp     qword ptr [rcx+18h], 0
0x1800c9ee0  jnz     short loc_1800C9F15
0x1800c9ee2  mov     ecx, 88h; Size
0x1800c9ee7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c9eec  mov     [rsp+48h+arg_0], rax
0x1800c9ef1  mov     rcx, rax; this
0x1800c9ef4  call    ??0ApiSamplingHost@ApiSampling@Inventory@Compat@Windows@@QEAA@XZ; Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::ApiSamplingHost(void)
0x1800c9ef9  nop
0x1800c9efa  mov     rcx, [rbp+18h]
0x1800c9efe  mov     [rbp+18h], rax
0x1800c9f02  test    rcx, rcx
0x1800c9f05  jz      short loc_1800C9F15
0x1800c9f07  mov     rax, [rcx]
0x1800c9f0a  mov     edx, r15d
0x1800c9f0d  mov     rax, [rax]
0x1800c9f10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9f15  mov     rsi, [rbp+18h]
0x1800c9f19  lea     rdi, [rsi+30h]
0x1800c9f1d  mov     rcx, rdi; SRWLock
0x1800c9f20  call    cs:__imp_AcquireSRWLockExclusive
0x1800c9f26  mov     [rsp+48h+arg_0], rdi
0x1800c9f2b  cmp     qword ptr [rsi+58h], 0
0x1800c9f30  jnz     short loc_1800C9F91
0x1800c9f32  mov     rcx, rsi; this
0x1800c9f35  call    ?LazyApiSamplingInitialize@ApiSamplingHost@ApiSampling@Inventory@Compat@Windows@@AEAAJXZ; Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::LazyApiSamplingInitialize(void)
0x1800c9f3a  mov     ebx, eax
0x1800c9f3c  test    eax, eax
0x1800c9f3e  jns     short loc_1800C9F91
0x1800c9f40  mov     [rsp+48h+var_28], eax
0x1800c9f44  lea     r9, aApisamplingini; "APISamplingInitialize failed [%#x]"
0x1800c9f4b  mov     r8d, 0E2h
0x1800c9f51  lea     rdx, aWindowsCompatI_50; "Windows::Compat::Inventory::ApiSampling"...
0x1800c9f58  mov     ecx, r15d
0x1800c9f5b  call    AslLogCallPrintf
0x1800c9f60  nop
0x1800c9f61  test    rdi, rdi
0x1800c9f64  jz      short loc_1800C9F6F
0x1800c9f66  mov     rcx, rdi; SRWLock
0x1800c9f69  call    cs:__imp_ReleaseSRWLockExclusive
0x1800c9f6f  mov     [rsp+48h+var_28], ebx
0x1800c9f73  lea     r9, aFailedToStartA; "Failed to start ApiSamplingHost [%#x]"
0x1800c9f7a  mov     r8d, 3B4h
0x1800c9f80  lea     rdx, aWindowsCompatI_39; "Windows::Compat::Inventory::ApiSampling"...
0x1800c9f87  mov     ecx, r15d
0x1800c9f8a  call    AslLogCallPrintf
0x1800c9f8f  jmp     short loc_1800C9FFF
0x1800c9f91  mov     rax, [rsi+78h]
0x1800c9f95  test    rax, rax
0x1800c9f98  jnz     short loc_1800C9FB8
0x1800c9f9a  lea     r9, aMPfnapisamplin; "m_pfnApiSamplingStart is null"
0x1800c9fa1  mov     r8d, 94h
0x1800c9fa7  lea     rdx, aWindowsCompatI_30; "Windows::Compat::Inventory::ApiSampling"...
0x1800c9fae  mov     ecx, r15d
0x1800c9fb1  call    AslLogCallPrintf
0x1800c9fb6  jmp     short loc_1800C9FE1
0x1800c9fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9fbd  test    eax, eax
0x1800c9fbf  jns     short loc_1800C9FE1
0x1800c9fc1  mov     [rsp+48h+var_28], eax
0x1800c9fc5  lea     r9, aApisamplingsta_0; "APISamplingStart failed [%#x]"
0x1800c9fcc  mov     r8d, 9Ch
0x1800c9fd2  lea     rdx, aWindowsCompatI_30; "Windows::Compat::Inventory::ApiSampling"...
0x1800c9fd9  mov     ecx, r15d
0x1800c9fdc  call    AslLogCallPrintf
0x1800c9fe1  mov     [rsi+2Ah], r15b
0x1800c9fe5  test    rdi, rdi
0x1800c9fe8  jz      short loc_1800C9FF3
0x1800c9fea  mov     rcx, rdi; SRWLock
0x1800c9fed  call    cs:__imp_ReleaseSRWLockExclusive
0x1800c9ff3  mov     edx, 2
0x1800c9ff8  call    ?WriteStateToRegistry@ApiSamplingTracer@ApiSampling@Inventory@Compat@Windows@@AEAAJW4ApiSamplingState@12345@@Z; Windows::Compat::Inventory::ApiSampling::ApiSamplingTracer::WriteStateToRegistry(Windows::Compat::Inventory::ApiSampling::ApiSamplingTracer::ApiSamplingState)
0x1800c9ffd  xor     ebx, ebx
0x1800c9fff  mov     edx, ebx; int
0x1800ca001  mov     rcx, rbp; this
0x1800ca004  call    ?LogStart@Tracer@Service@Inventory@Compat@Windows@@IEAAJJ@Z; Windows::Compat::Inventory::Service::Tracer::LogStart(long)
0x1800ca009  mov     eax, ebx
0x1800ca00b  mov     rbx, [rsp+48h+arg_8]
0x1800ca010  mov     rbp, [rsp+48h+arg_10]
0x1800ca015  add     rsp, 30h
0x1800ca019  pop     r15
0x1800ca01b  pop     rdi
0x1800ca01c  pop     rsi
0x1800ca01d  retn
```
