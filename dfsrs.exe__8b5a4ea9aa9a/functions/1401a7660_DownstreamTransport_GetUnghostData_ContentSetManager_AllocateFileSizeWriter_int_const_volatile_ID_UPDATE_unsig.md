# DownstreamTransport::GetUnghostData(ContentSetManager *,AllocateFileSizeWriter &,int const volatile &,ID_UPDATE &,unsigned __int64,unsigned __int64)

- ea: `0x1401a7660`
- end: `0x1401a7cb7`
- name: `?GetUnghostData@DownstreamTransport@@UEAAPEAVFrsStatus@@PEAVContentSetManager@@AEAVAllocateFileSizeWriter@@AEDHAEAVID_UPDATE@@_K4@Z`
- size: `1623`
- prototype: `struct FrsStatus *__fastcall(DownstreamTransport *__hidden this, struct ContentSetManager *, struct AllocateFileSizeWriter *, const volatile int *, struct ID_UPDATE *, unsigned __int64, unsigned __int64)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, installer_update`

## callees

- `0x1400036a0`
- `0x1400046cc`
- `0x14000e34c`
- `0x14002c548`
- `0x1400888ac`
- `0x140088c6c`
- `0x1400c3488`
- `0x1401a3730`
- `0x1401a37e4`
- `0x1401a7660`
- `0x1401a82ac`
- `0x1401ace34`
- `0x1401ad14c`
- `0x1401ae578`
- `0x1401af7b0`
- `0x1401b9494`
- `0x1401bda10`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1401a7701`
- `KERNEL32!GetCurrentThreadId` at `0x1401a775e`
- `KERNEL32!GetCurrentThreadId` at `0x1401a77f6`
- `KERNEL32!GetCurrentThreadId` at `0x1401a7859`
- `KERNEL32!GetCurrentThreadId` at `0x1401a7975`
- `KERNEL32!GetCurrentThreadId` at `0x1401a79ba`
- `KERNEL32!GetCurrentThreadId` at `0x1401a7b23`
- `KERNEL32!GetCurrentThreadId` at `0x1401a7c47`
- `KERNEL32!GetCurrentThreadId` at `0x1401a7701`
- `KERNEL32!GetCurrentThreadId` at `0x1401a775e`
- `KERNEL32!GetCurrentThreadId` at `0x1401a77f6`
- `KERNEL32!GetCurrentThreadId` at `0x1401a7859`
- `KERNEL32!GetCurrentThreadId` at `0x1401a7975`
- `KERNEL32!GetCurrentThreadId` at `0x1401a79ba`
- `KERNEL32!GetCurrentThreadId` at `0x1401a7b23`
- `KERNEL32!GetCurrentThreadId` at `0x1401a7c47`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct FrsStatus *__fastcall DownstreamTransport::GetUnghostData(
        DownstreamTransport *this,
        struct ContentSetManager *a2,
        struct AllocateFileSizeWriter *a3,
        const volatile int *a4,
        struct ID_UPDATE *a5,
        unsigned __int64 a6,
        unsigned __int64 a7)
{
  __int64 v9; // rdi
  __int64 v10; // rbx
  unsigned int v11; // r15d
  DWORD v12; // eax
  __int64 v13; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v15; // rcx
  struct FrsStatus *v16; // r8
  struct FrsStatus *v17; // rbx
  DWORD v18; // eax
  int v19; // r8d
  int v20; // eax
  DWORD v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rdx
  unsigned int *v24; // rbx
  _QWORD *v25; // rax
  __int64 v26; // rcx
  struct ContentSetManager *v27; // r15
  __int64 v28; // rax
  __int64 v29; // rsi
  _QWORD *v30; // rcx
  __int64 v31; // rcx
  DWORD v32; // eax
  __int64 v33; // rcx
  DWORD v34; // eax
  __int64 v35; // rcx
  int v37; // [rsp+30h] [rbp-D0h]
  unsigned int v38; // [rsp+50h] [rbp-B0h]
  int v39; // [rsp+54h] [rbp-ACh]
  struct FrsStatus *v40; // [rsp+58h] [rbp-A8h]
  int v41; // [rsp+60h] [rbp-A0h]
  __int64 v42; // [rsp+68h] [rbp-98h]
  struct ID_UPDATE *v43; // [rsp+70h] [rbp-90h]
  const wchar_t *v44; // [rsp+78h] [rbp-88h] BYREF
  int v45; // [rsp+80h] [rbp-80h]
  int v46; // [rsp+84h] [rbp-7Ch]
  const wchar_t *v47; // [rsp+88h] [rbp-78h]
  const volatile int *v48; // [rsp+90h] [rbp-70h]
  struct ContentSetManager *v49; // [rsp+98h] [rbp-68h]
  struct FrsStatus *v50; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v51[684]; // [rsp+B0h] [rbp-50h] BYREF
  int v52; // [rsp+35Ch] [rbp+25Ch]

  v48 = a4;
  v49 = a2;
  v43 = a5;
  v9 = 0;
  v42 = 0;
  v10 = 0;
  memset_0(v51, 0, 0x2B0u);
  v41 = 0;
  v11 = 0x40000;
  if ( (unsigned int)Settings::GenericDwordSetting::operator()(&Settings::RpcFileBufferSize) <= 0x40000 )
    v11 = Settings::GenericDwordSetting::operator()(&Settings::RpcFileBufferSize);
  v39 = 0;
  v38 = 0;
  if ( Settings::GhostingEnabled
    || (v12 = GetCurrentThreadId(),
        (v10 = FrsStatusList::PushNewError(
                 v13,
                 9305,
                 0,
                 3,
                 "base\\fs\\remotefs\\frs\\src\\transport\\downstreamtransport.cpp",
                 "DownstreamTransport::GetUnghostData",
                 4858,
                 v12,
                 0)) == 0) )
  {
    if ( *((_DWORD *)this + 137) < 0x50001u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v10 = FrsStatusList::PushNewError(
              v15,
              9050,
              0,
              3,
              "base\\fs\\remotefs\\frs\\src\\transport\\downstreamtransport.cpp",
              "DownstreamTransport::GetUnghostData",
              4865,
              CurrentThreadId,
              0);
    }
  }
  v16 = (struct FrsStatus *)operator_new(v11);
  v40 = v16;
  v50 = v16;
  if ( !v10 )
  {
    ID_UPDATE::Get(a5, (struct _FRS_UPDATE *)v51);
    v17 = BandwidthThrottler::ThrottleBytes((DownstreamTransport *)((char *)this + 176), v38 + 700LL, 0x2E4u, 1);
    v18 = GetCurrentThreadId();
    v10 = LogTranslatedRemoteError(
            50,
            0,
            v19,
            (unsigned int)"DownstreamTransport::GetUnghostData",
            4909,
            v18,
            v37,
            (__int64)v17);
    if ( !v10 )
    {
      v20 = v52;
      if ( *((_DWORD *)this + 137) < 0x50001u )
        v20 = 0;
      v52 = v20;
      ID_UPDATE::Set(a5, (const struct _FRS_UPDATE *)v51);
      if ( v38 > v11 )
      {
        v21 = GetCurrentThreadId();
        v10 = FrsStatusList::PushNewError(
                v22,
                13,
                0,
                1,
                "base\\fs\\remotefs\\frs\\src\\transport\\downstreamtransport.cpp",
                "DownstreamTransport::GetUnghostData",
                4925,
                v21,
                0);
      }
    }
    v16 = v40;
  }
  v24 = (unsigned int *)RpcFinalizeContext(v42, v10, v16);
  if ( v24 )
    goto LABEL_27;
  v25 = (_QWORD *)*((_QWORD *)this + 70);
  v26 = v25 ? *v25 : 0LL;
  DfsrPerf::IncrementCounter(v26, 53, a7);
  v27 = v49;
  DfsrPerf::IncrementCounter(*((_QWORD *)v49 + 244), 38, a7);
  v28 = (*(__int64 (__fastcall **)(struct AllocateFileSizeWriter *))(*(_QWORD *)a3 + 16LL))(a3);
  v29 = v28;
  v30 = (_QWORD *)*((_QWORD *)this + 70);
  v31 = v30 ? *v30 : 0LL;
  DfsrPerf::IncrementCounter(v31, 54, v28);
  DfsrPerf::IncrementCounter(*((_QWORD *)v27 + 244), 39, v29);
  if ( *v48
    && (v32 = GetCurrentThreadId(),
        (v24 = (unsigned int *)FrsStatusList::PushNewError(
                                 v33,
                                 9033,
                                 0,
                                 3,
                                 "base\\fs\\remotefs\\frs\\src\\transport\\downstreamtransport.cpp",
                                 "DownstreamTransport::GetUnghostData",
                                 5032,
                                 v32,
                                 0)) != 0) )
  {
LABEL_27:
    if ( !g_DebugLog )
    {
LABEL_32:
      v34 = GetCurrentThreadId();
      v9 = FrsStatusList::PushNewError(
             v35,
             v24[1],
             v24[2],
             *v24,
             "base\\fs\\remotefs\\frs\\src\\transport\\downstreamtransport.cpp",
             "DownstreamTransport::GetUnghostData",
             5046,
             v34,
             v24);
      goto LABEL_33;
    }
    if ( LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
    {
      v44 = L"DownstreamTransport::GetUnghostData";
      v45 = 5036;
      v46 = 2;
      v47 = L"DOWN";
      dbgobj::DbgPrint<unsigned short,_GUID,ID_UPDATE,FrsStatus>(
        (unsigned int)&v44,
        v23,
        (_DWORD)this + 32,
        (_DWORD)v43,
        (__int64)v24);
    }
  }
  else
  {
    if ( !g_DebugLog || !LODWORD(g_DebugLog[1].LockSemaphore) || SLODWORD(g_DebugLog[1].OwningThread) < 5 )
      goto LABEL_33;
    v44 = L"DownstreamTransport::GetUnghostData";
    v45 = 5043;
    v46 = 5;
    v47 = L"DOWN";
    dbgobj::DbgPrint<unsigned short,_GUID,ID_UPDATE>(&v44, v23, (char *)this + 32, v43);
  }
  if ( v24 )
    goto LABEL_32;
LABEL_33:
  scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(&v50);
  return (struct FrsStatus *)v9;
}

```

## disassembly

```asm
0x1401a7660  mov     [rsp-8+arg_18], rbx
0x1401a7665  push    rbp
0x1401a7666  push    rsi
0x1401a7667  push    rdi
0x1401a7668  push    r12
0x1401a766a  push    r13
0x1401a766c  push    r14
0x1401a766e  push    r15
0x1401a7670  lea     rbp, [rsp-270h]
0x1401a7678  sub     rsp, 370h
0x1401a767f  mov     rax, cs:__security_cookie
0x1401a7686  xor     rax, rsp
0x1401a7689  mov     [rbp+2A0h+var_40], rax
0x1401a7690  mov     [rbp+2A0h+var_310], r9
0x1401a7694  mov     r13, r8
0x1401a7697  mov     [rbp+2A0h+var_308], rdx
0x1401a769b  mov     r14, rcx
0x1401a769e  mov     rsi, [rbp+2A0h+arg_20]
0x1401a76a5  mov     [rsp+3A0h+var_330], rsi
0x1401a76aa  xor     edi, edi
0x1401a76ac  mov     [rsp+3A0h+var_338], rdi
0x1401a76b1  mov     ebx, edi
0x1401a76b3  xor     edx, edx; Val
0x1401a76b5  mov     r8d, 2B0h; Size
0x1401a76bb  lea     rcx, [rbp+2A0h+var_2F0]; void *
0x1401a76bf  call    memset_0
0x1401a76c4  mov     [rsp+3A0h+var_340], edi
0x1401a76c8  lea     rcx, ?RpcFileBufferSize@Settings@@3VCRpcFileBufferSize@1@A; Settings::CRpcFileBufferSize Settings::RpcFileBufferSize
0x1401a76cf  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x1401a76d4  mov     r15d, 40000h
0x1401a76da  cmp     eax, r15d
0x1401a76dd  ja      short loc_1401A76EE
0x1401a76df  lea     rcx, ?RpcFileBufferSize@Settings@@3VCRpcFileBufferSize@1@A; Settings::CRpcFileBufferSize Settings::RpcFileBufferSize
0x1401a76e6  call    ??RGenericDwordSetting@Settings@@QEAAKXZ; Settings::GenericDwordSetting::operator()(void)
0x1401a76eb  mov     r15d, eax
0x1401a76ee  mov     [rsp+3A0h+var_34C], edi
0x1401a76f2  mov     [rsp+3A0h+var_350], edi
0x1401a76f6  mov     r12, rdi
0x1401a76f9  cmp     cs:?GhostingEnabled@Settings@@3VGenericBoolSetting@1@A, edi; Settings::GenericBoolSetting Settings::GhostingEnabled
0x1401a76ff  jnz     short loc_1401A7751
0x1401a7701  call    cs:__imp_GetCurrentThreadId
0x1401a7708  nop     dword ptr [rax+rax+00h]
0x1401a770d  mov     [rsp+3A0h+var_360], rdi
0x1401a7712  mov     dword ptr [rsp+3A0h+var_368], eax
0x1401a7716  mov     [rsp+3A0h+var_370], 12FAh
0x1401a771e  lea     rax, aDownstreamtran_36; "DownstreamTransport::GetUnghostData"
0x1401a7725  mov     [rsp+3A0h+var_378], rax
0x1401a772a  lea     rax, aBaseFsRemotefs_70; "base\\fs\\remotefs\\frs\\src\\transport"...
0x1401a7731  mov     [rsp+3A0h+var_380], rax
0x1401a7736  mov     r9d, 3
0x1401a773c  xor     r8d, r8d
0x1401a773f  mov     edx, 2459h
0x1401a7744  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401a7749  mov     rbx, rax
0x1401a774c  test    rax, rax
0x1401a774f  jnz     short loc_1401A77A9
0x1401a7751  cmp     dword ptr [r14+224h], 50001h
0x1401a775c  jnb     short loc_1401A77A9
0x1401a775e  call    cs:__imp_GetCurrentThreadId
0x1401a7765  nop     dword ptr [rax+rax+00h]
0x1401a776a  mov     [rsp+3A0h+var_360], rdi
0x1401a776f  mov     dword ptr [rsp+3A0h+var_368], eax
0x1401a7773  mov     [rsp+3A0h+var_370], 1301h
0x1401a777b  lea     rax, aDownstreamtran_36; "DownstreamTransport::GetUnghostData"
0x1401a7782  mov     [rsp+3A0h+var_378], rax
0x1401a7787  lea     rax, aBaseFsRemotefs_70; "base\\fs\\remotefs\\frs\\src\\transport"...
0x1401a778e  mov     [rsp+3A0h+var_380], rax
0x1401a7793  mov     r9d, 3
0x1401a7799  xor     r8d, r8d
0x1401a779c  mov     edx, 235Ah
0x1401a77a1  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401a77a6  mov     rbx, rax
0x1401a77a9  mov     ecx, r15d; unsigned __int64
0x1401a77ac  call    ?operator_new@@YAPEAX_K@Z; operator_new(unsigned __int64)
0x1401a77b1  mov     r8, rax
0x1401a77b4  mov     [rsp+3A0h+var_348], rax
0x1401a77b9  mov     [rbp+2A0h+var_300], rax
0x1401a77bd  test    rbx, rbx
0x1401a77c0  jnz     loc_1401A78A5
0x1401a77c6  lea     rdx, [rbp+2A0h+var_2F0]; struct _FRS_UPDATE *
0x1401a77ca  mov     rcx, rsi; this
0x1401a77cd  call    ?Get@ID_UPDATE@@QEBAXAEAU_FRS_UPDATE@@@Z; ID_UPDATE::Get(_FRS_UPDATE &)
0x1401a77d2  mov     edx, [rsp+3A0h+var_350]
0x1401a77d6  add     rdx, 2BCh; unsigned __int64
0x1401a77dd  lea     rcx, [r14+0B0h]; this
0x1401a77e4  lea     r9d, [rbx+1]; int
0x1401a77e8  mov     r8d, 2E4h; unsigned __int64
0x1401a77ee  call    ?ThrottleBytes@BandwidthThrottler@@QEAAPEAVFrsStatus@@_K0H@Z; BandwidthThrottler::ThrottleBytes(unsigned __int64,unsigned __int64,int)
0x1401a77f3  mov     rbx, rax
0x1401a77f6  call    cs:__imp_GetCurrentThreadId
0x1401a77fd  nop     dword ptr [rax+rax+00h]
0x1401a7802  mov     [rsp+3A0h+var_368], rbx
0x1401a7807  mov     dword ptr [rsp+3A0h+var_378], eax
0x1401a780b  mov     dword ptr [rsp+3A0h+var_380], 132Dh
0x1401a7813  lea     r9, aDownstreamtran_36; "DownstreamTransport::GetUnghostData"
0x1401a781a  xor     edx, edx
0x1401a781c  lea     ecx, [rdx+32h]
0x1401a781f  call    LogTranslatedRemoteError
0x1401a7824  mov     rbx, rax
0x1401a7827  test    rax, rax
0x1401a782a  jnz     short loc_1401A78A0
0x1401a782c  mov     eax, [rbp+2A0h+var_44]
0x1401a7832  cmp     dword ptr [r14+224h], 50001h
0x1401a783d  cmovb   eax, edi
0x1401a7840  mov     [rbp+2A0h+var_44], eax
0x1401a7846  lea     rdx, [rbp+2A0h+var_2F0]; struct _FRS_UPDATE *
0x1401a784a  mov     rcx, rsi; this
0x1401a784d  call    ?Set@ID_UPDATE@@QEAAXAEBU_FRS_UPDATE@@@Z; ID_UPDATE::Set(_FRS_UPDATE const &)
0x1401a7852  cmp     [rsp+3A0h+var_350], r15d
0x1401a7857  jbe     short loc_1401A78A0
0x1401a7859  call    cs:__imp_GetCurrentThreadId
0x1401a7860  nop     dword ptr [rax+rax+00h]
0x1401a7865  mov     [rsp+3A0h+var_360], rdi
0x1401a786a  mov     dword ptr [rsp+3A0h+var_368], eax
0x1401a786e  mov     [rsp+3A0h+var_370], 133Dh
0x1401a7876  lea     rax, aDownstreamtran_36; "DownstreamTransport::GetUnghostData"
0x1401a787d  mov     [rsp+3A0h+var_378], rax
0x1401a7882  lea     rax, aBaseFsRemotefs_70; "base\\fs\\remotefs\\frs\\src\\transport"...
0x1401a7889  mov     [rsp+3A0h+var_380], rax
0x1401a788e  lea     r9d, [rbx+1]
0x1401a7892  xor     r8d, r8d
0x1401a7895  lea     edx, [rbx+0Dh]
0x1401a7898  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401a789d  mov     rbx, rax
0x1401a78a0  mov     r8, [rsp+3A0h+var_348]
0x1401a78a5  mov     esi, [rsp+3A0h+var_350]
0x1401a78a9  test    rbx, rbx
0x1401a78ac  jnz     loc_1401A7A77
0x1401a78b2  test    esi, esi
0x1401a78b4  jz      short loc_1401A790A
0x1401a78b6  mov     rax, [rsp+3A0h+var_330]
0x1401a78bb  test    byte ptr [rax+98h], 1
0x1401a78c2  jz      short loc_1401A7901
0x1401a78c4  mov     [rsp+3A0h+var_34C], edi
0x1401a78c8  mov     rax, [r13+0]
0x1401a78cc  mov     edx, [rsp+3A0h+var_350]
0x1401a78d0  sub     edx, esi
0x1401a78d2  add     rdx, r8
0x1401a78d5  lea     r9, [rsp+3A0h+var_34C]
0x1401a78da  mov     r8d, esi
0x1401a78dd  mov     rcx, r13
0x1401a78e0  mov     rax, [rax+8]
0x1401a78e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401a78e9  mov     rbx, rax
0x1401a78ec  sub     esi, [rsp+3A0h+var_34C]
0x1401a78f0  mov     eax, [rsp+3A0h+var_34C]
0x1401a78f4  add     r12, rax
0x1401a78f7  test    rbx, rbx
0x1401a78fa  mov     r8, [rsp+3A0h+var_348]
0x1401a78ff  jz      short loc_1401A78B2
0x1401a7901  test    rbx, rbx
0x1401a7904  jnz     loc_1401A7A49
0x1401a790a  cmp     [rsp+3A0h+var_340], edi
0x1401a790e  jnz     loc_1401A7A49
0x1401a7914  mov     rax, [rbp+2A0h+var_310]
0x1401a7918  mov     eax, [rax]
0x1401a791a  test    eax, eax
0x1401a791c  jnz     loc_1401A7A49
0x1401a7922  cmp     [rsp+3A0h+var_338], rdi
0x1401a7927  jz      loc_1401A7A49
0x1401a792d  lea     rax, [rsp+3A0h+var_340]
0x1401a7932  mov     [rsp+3A0h+var_380], rax
0x1401a7937  lea     r9, [rsp+3A0h+var_350]
0x1401a793c  mov     r8d, r15d
0x1401a793f  mov     rdx, [rsp+3A0h+var_348]
0x1401a7944  lea     rcx, [rsp+3A0h+var_338]
0x1401a7949  call    RpcRawGetFileData
0x1401a794e  mov     esi, eax
0x1401a7950  mov     r8d, [rsp+3A0h+var_350]
0x1401a7955  add     r8, 10h; unsigned __int64
0x1401a7959  lea     rcx, [r14+0B0h]; this
0x1401a7960  mov     edx, 0Ch; unsigned __int64
0x1401a7965  lea     r9d, [rdx-0Bh]; int
0x1401a7969  call    ?ThrottleBytes@BandwidthThrottler@@QEAAPEAVFrsStatus@@_K0H@Z; BandwidthThrottler::ThrottleBytes(unsigned __int64,unsigned __int64,int)
0x1401a796e  mov     rbx, rax
0x1401a7971  test    esi, esi
0x1401a7973  jz      short loc_1401A79AE
0x1401a7975  call    cs:__imp_GetCurrentThreadId
0x1401a797c  nop     dword ptr [rax+rax+00h]
0x1401a7981  mov     edx, edi
0x1401a7983  cmp     esi, 4D5h
0x1401a7989  setz    dl
0x1401a798c  mov     [rsp+3A0h+var_368], rbx
0x1401a7991  mov     dword ptr [rsp+3A0h+var_378], eax
0x1401a7995  mov     dword ptr [rsp+3A0h+var_380], 1366h
0x1401a799d  lea     r9, aDownstreamtran_36; "DownstreamTransport::GetUnghostData"
0x1401a79a4  mov     ecx, esi
0x1401a79a6  call    LogTranslatedRemoteError
0x1401a79ab  mov     rbx, rax
0x1401a79ae  test    rbx, rbx
0x1401a79b1  jnz     short loc_1401A7A01
0x1401a79b3  cmp     [rsp+3A0h+var_350], r15d
0x1401a79b8  jbe     short loc_1401A7A01
0x1401a79ba  call    cs:__imp_GetCurrentThreadId
0x1401a79c1  nop     dword ptr [rax+rax+00h]
0x1401a79c6  mov     [rsp+3A0h+var_360], rdi
0x1401a79cb  mov     dword ptr [rsp+3A0h+var_368], eax
0x1401a79cf  mov     [rsp+3A0h+var_370], 136Bh
0x1401a79d7  lea     rax, aDownstreamtran_36; "DownstreamTransport::GetUnghostData"
0x1401a79de  mov     [rsp+3A0h+var_378], rax
0x1401a79e3  lea     rax, aBaseFsRemotefs_70; "base\\fs\\remotefs\\frs\\src\\transport"...
0x1401a79ea  mov     [rsp+3A0h+var_380], rax
0x1401a79ef  lea     r9d, [rbx+1]
0x1401a79f3  xor     r8d, r8d
0x1401a79f6  lea     edx, [rbx+0Dh]
0x1401a79f9  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401a79fe  mov     rbx, rax
0x1401a7a01  mov     esi, [rsp+3A0h+var_350]
0x1401a7a05  jmp     short loc_1401A7A44
0x1401a7a07  test    esi, esi
0x1401a7a09  jz      loc_1401A790A
0x1401a7a0f  mov     [rsp+3A0h+var_34C], edi
0x1401a7a13  mov     rax, [r13+0]
0x1401a7a17  mov     edx, [rsp+3A0h+var_350]
0x1401a7a1b  sub     edx, esi
0x1401a7a1d  add     rdx, [rsp+3A0h+var_348]
0x1401a7a22  lea     r9, [rsp+3A0h+var_34C]
0x1401a7a27  mov     r8d, esi
0x1401a7a2a  mov     rcx, r13
0x1401a7a2d  mov     rax, [rax+8]
0x1401a7a31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401a7a36  mov     rbx, rax
0x1401a7a39  sub     esi, [rsp+3A0h+var_34C]
0x1401a7a3d  mov     eax, [rsp+3A0h+var_34C]
0x1401a7a41  add     r12, rax
0x1401a7a44  test    rbx, rbx
0x1401a7a47  jz      short loc_1401A7A07
0x1401a7a49  test    r12, r12
0x1401a7a4c  jz      short loc_1401A7A77
0x1401a7a4e  mov     rax, [r13+0]
0x1401a7a52  mov     rcx, r13
0x1401a7a55  mov     rax, [rax+20h]
0x1401a7a59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401a7a5e  mov     [rsp+3A0h+var_348], rax
0x1401a7a63  test    rbx, rbx
0x1401a7a66  jnz     short loc_1401A7A6D
0x1401a7a68  mov     rbx, rax
0x1401a7a6b  jmp     short loc_1401A7A77
0x1401a7a6d  lea     rcx, [rsp+3A0h+var_348]; struct FrsStatus **
0x1401a7a72  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x1401a7a77  mov     rdx, rbx
0x1401a7a7a  mov     rcx, [rsp+3A0h+var_338]
0x1401a7a7f  call    RpcFinalizeContext
0x1401a7a84  mov     rbx, rax
0x1401a7a87  test    rax, rax
0x1401a7a8a  jnz     loc_1401A7BE0
0x1401a7a90  mov     rax, [r14+230h]
0x1401a7a97  test    rax, rax
0x1401a7a9a  jz      short loc_1401A7AA1
0x1401a7a9c  mov     rcx, [rax]
0x1401a7a9f  jmp     short loc_1401A7AA4
0x1401a7aa1  mov     rcx, rdi
0x1401a7aa4  mov     r8, [rbp+2A0h+arg_30]
0x1401a7aab  mov     edx, 35h ; '5'
0x1401a7ab0  call    ?IncrementCounter@DfsrPerf@@SAXPEAU_PERF_COUNTERSET_INSTANCE@@W4DfsrCounters64@@_K@Z; DfsrPerf::IncrementCounter(_PERF_COUNTERSET_INSTANCE *,DfsrCounters64,unsigned __int64)
0x1401a7ab5  mov     r8, [rbp+2A0h+arg_30]
0x1401a7abc  mov     edx, 26h ; '&'
0x1401a7ac1  mov     r15, [rbp+2A0h+var_308]
0x1401a7ac5  mov     rcx, [r15+7A0h]
0x1401a7acc  call    ?IncrementCounter@DfsrPerf@@SAXPEAU_PERF_COUNTERSET_INSTANCE@@W4DfsrCounters64@@_K@Z; DfsrPerf::IncrementCounter(_PERF_COUNTERSET_INSTANCE *,DfsrCounters64,unsigned __int64)
0x1401a7ad1  mov     rax, [r13+0]
0x1401a7ad5  mov     rcx, r13
0x1401a7ad8  mov     rax, [rax+10h]
0x1401a7adc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401a7ae1  mov     rsi, rax
0x1401a7ae4  mov     rcx, [r14+230h]
0x1401a7aeb  test    rcx, rcx
0x1401a7aee  jz      short loc_1401A7AF5
0x1401a7af0  mov     rcx, [rcx]
0x1401a7af3  jmp     short loc_1401A7AF8
0x1401a7af5  mov     rcx, rdi
0x1401a7af8  mov     r8, rsi
0x1401a7afb  mov     edx, 36h ; '6'
0x1401a7b00  call    ?IncrementCounter@DfsrPerf@@SAXPEAU_PERF_COUNTERSET_INSTANCE@@W4DfsrCounters64@@_K@Z; DfsrPerf::IncrementCounter(_PERF_COUNTERSET_INSTANCE *,DfsrCounters64,unsigned __int64)
0x1401a7b05  mov     r8, rsi
0x1401a7b08  mov     edx, 27h ; '''
0x1401a7b0d  mov     rcx, [r15+7A0h]
0x1401a7b14  call    ?IncrementCounter@DfsrPerf@@SAXPEAU_PERF_COUNTERSET_INSTANCE@@W4DfsrCounters64@@_K@Z; DfsrPerf::IncrementCounter(_PERF_COUNTERSET_INSTANCE *,DfsrCounters64,unsigned __int64)
0x1401a7b19  mov     rcx, [rbp+2A0h+var_310]
0x1401a7b1d  mov     eax, [rcx]
0x1401a7b1f  test    eax, eax
0x1401a7b21  jz      short loc_1401A7B75
0x1401a7b23  call    cs:__imp_GetCurrentThreadId
0x1401a7b2a  nop     dword ptr [rax+rax+00h]
0x1401a7b2f  mov     [rsp+3A0h+var_360], rdi
0x1401a7b34  mov     dword ptr [rsp+3A0h+var_368], eax
0x1401a7b38  mov     [rsp+3A0h+var_370], 13A8h
0x1401a7b40  lea     rsi, aDownstreamtran_36; "DownstreamTransport::GetUnghostData"
0x1401a7b47  mov     [rsp+3A0h+var_378], rsi
0x1401a7b4c  lea     r15, aBaseFsRemotefs_70; "base\\fs\\remotefs\\frs\\src\\transport"...
0x1401a7b53  mov     [rsp+3A0h+var_380], r15
0x1401a7b58  mov     r9d, 3
0x1401a7b5e  xor     r8d, r8d
0x1401a7b61  mov     edx, 2349h
0x1401a7b66  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401a7b6b  mov     rbx, rax
0x1401a7b6e  test    rax, rax
0x1401a7b71  jnz     short loc_1401A7BEE
0x1401a7b73  jmp     short loc_1401A7B83
0x1401a7b75  lea     rsi, aDownstreamtran_36; "DownstreamTransport::GetUnghostData"
  ... truncated ...
```
