# ContactToNameObject(IProperties *)

- ea: `0x180006880`
- end: `0x180006cbb`
- name: `?ContactToNameObject@@YAPEAUINameObject@@PEAUIProperties@@@Z`
- size: `1083`
- prototype: `struct INameObject *__fastcall(struct IProperties *)`
- caller_count: `5`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180014ac8`
- `0x180017358`
- `0x180021504`
- `0x18004de14`
- `0x1800750c4`

## callees

- `0x180006054`
- `0x180006880`
- `0x180011ac0`
- `0x180011b88`
- `0x18001d138`
- `0x18001d178`
- `0x180053868`
- `0x180081d92`
- `0x180081dd0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006a0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006a0b`
- `RPCRT4!RpcStringFreeA` at `0x18000696e`
- `RPCRT4!RpcStringFreeA` at `0x18000696e`
- `RPCRT4!UuidToStringA` at `0x180006910`
- `RPCRT4!UuidToStringA` at `0x180006910`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180006c15`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180006c15`
- `msvcrt!atoi` at `0x180006b64`
- `msvcrt!atoi` at `0x180006b64`
- `msvcrt!fclose` at `0x180006c8c`
- `msvcrt!fclose` at `0x180006c8c`
- `msvcrt!fprintf` at `0x180006c7a`
- `msvcrt!fprintf` at `0x180006c7a`
- `msvcrt!fflush` at `0x180006c83`
- `msvcrt!fflush` at `0x180006c83`

## string_xrefs

- `0x1800068f4`: `com\complus\dtc\dtc\adme\namesvc.cpp`
- `0x180006ae5`: `com\complus\dtc\dtc\adme\namesvc.cpp`
- `0x180006b36`: `com\complus\dtc\dtc\adme\namesvc.cpp`
- `0x180006c2c`: `com\complus\dtc\dtc\adme\namesvc.cpp`
- `0x180006c37`: `failed in DllGetDTCUtilObject`
- `0x180006aec`: `failed in CreateNew`
- `0x180006b3d`: `failed in GetProtocol`
- `0x180006c6e`: `%02ld-%02ld-%04ld %02ld:%02ld : DTC Install error = %d, %s, %s (%d) \n`

## pseudocode

```c
struct INameObject *__fastcall ContactToNameObject(struct IProperties *a1)
{
  __int64 v1; // rax
  __int64 (__fastcall *v3)(struct IProperties *, UUID *); // rax
  RPC_STATUS v4; // eax
  unsigned int v5; // r9d
  char *v6; // rdx
  RPC_CSTR v7; // r8
  _BYTE *v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rdx
  _BYTE *v11; // rax
  __int64 v12; // rax
  void *v13; // rax
  CClassFactoryDTCUtil *v14; // rax
  CClassFactoryDTCUtil *v15; // rbx
  int v16; // edi
  int v17; // eax
  int v18; // eax
  int v19; // ebx
  __int64 v20; // rdx
  __int64 v21; // rax
  FILE *v23; // rbx
  __int64 v24; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v25; // [rsp+68h] [rbp-98h] BYREF
  __int64 v26; // [rsp+70h] [rbp-90h] BYREF
  RPC_CSTR StringUuid; // [rsp+78h] [rbp-88h] BYREF
  __int64 v28; // [rsp+80h] [rbp-80h] BYREF
  LPVOID pv[2]; // [rsp+88h] [rbp-78h] BYREF
  UUID Uuid; // [rsp+98h] [rbp-68h] BYREF
  char String[16]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v32[40]; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 v33[264]; // [rsp+E0h] [rbp-20h] BYREF

  v1 = *(_QWORD *)a1;
  StringUuid = 0;
  v24 = 0;
  v3 = *(__int64 (__fastcall **)(struct IProperties *, UUID *))(v1 + 24);
  Uuid = 0;
  v25 = 0;
  v32[0] = 0;
  v33[0] = 0;
  v4 = v3(a1, &Uuid);
  if ( v4 )
  {
    v5 = 1685;
    v6 = "failed in GetContactId";
LABEL_3:
    TraceFile(v4, v6, "com\\complus\\dtc\\dtc\\adme\\namesvc.cpp", v5);
    return 0;
  }
  v4 = UuidToStringA(&Uuid, &StringUuid);
  if ( v4 )
  {
    v5 = 1693;
    v6 = "failed in UuidToString";
    goto LABEL_3;
  }
  v7 = StringUuid;
  v8 = v32;
  v9 = 2147483646;
  v10 = 37;
  do
  {
    if ( !v9 )
      break;
    if ( !*v7 )
      break;
    *v8++ = *v7++;
    --v9;
    --v10;
  }
  while ( v10 );
  v11 = v8 - 1;
  if ( v10 )
    v11 = v8;
  *v11 = 0;
  RpcStringFreeA(&StringUuid);
  v4 = (*(__int64 (__fastcall **)(struct IProperties *, unsigned __int16 *, __int64))(*(_QWORD *)a1 + 72LL))(
         a1,
         v33,
         257);
  if ( v4 < 0 )
  {
    v5 = 1708;
    v6 = "failed in i_pContact->GetHostW";
    goto LABEL_3;
  }
  if ( !v33[0] )
  {
    v12 = *(_QWORD *)a1;
    pv[0] = 0;
    v26 = 0;
    (*(void (__fastcall **)(struct IProperties *, __int64 *))(v12 + 176))(a1, &v26);
    (*(void (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v26 + 40LL))(v26, pv);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v26 = 0;
    StringCchCopyW(v33, 0x101u, (const unsigned __int16 *)pv[0]);
    CoTaskMemFree(pv[0]);
  }
  v24 = 0;
  if ( memcmp_0(&CLSID_DTCUtil, &CLSID_DTCUtil, 0x10u) )
  {
    v16 = -2147221231;
    goto LABEL_35;
  }
  v13 = operator new(0x10u);
  pv[0] = v13;
  if ( !v13 || (v14 = CClassFactoryDTCUtil::CClassFactoryDTCUtil((CClassFactoryDTCUtil *)v13), (v15 = v14) == 0) )
  {
    v16 = -2147024882;
    goto LABEL_35;
  }
  v16 = (**(__int64 (__fastcall ***)(CClassFactoryDTCUtil *, GUID *, __int64 *))v14)(v14, &IID_IClassFactory, &v24);
  if ( v16 < 0 )
  {
    operator delete(v15);
    goto LABEL_35;
  }
  v16 = (*(__int64 (__fastcall **)(CClassFactoryDTCUtil *, _QWORD, GUID *, __int64 *))(*(_QWORD *)v15 + 24LL))(
          v15,
          0,
          &IID_INameService,
          &v24);
  (*(void (__fastcall **)(CClassFactoryDTCUtil *))(*(_QWORD *)v15 + 16LL))(v15);
  if ( v16 )
  {
LABEL_35:
    *(_OWORD *)pv = 0;
    GetLocalTime((LPSYSTEMTIME)pv);
    v23 = OpenTraceFile();
    if ( v23 )
    {
      fprintf(
        v23,
        "%02ld-%02ld-%04ld %02ld:%02ld : DTC Install error = %d, %s, %s (%d) \n",
        WORD1(pv[0]),
        HIWORD(pv[0]),
        LOWORD(pv[0]),
        LOWORD(pv[1]),
        WORD1(pv[1]),
        v16,
        "failed in DllGetDTCUtilObject",
        "com\\complus\\dtc\\dtc\\adme\\namesvc.cpp",
        1730);
      fflush(v23);
      fclose(v23);
    }
    return 0;
  }
  v17 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, _BYTE *, __int64 *))(*(_QWORD *)v24 + 24LL))(
          v24,
          v33,
          v32,
          &v25);
  if ( v17 )
  {
    TraceFile(v17, "failed in CreateNew", "com\\complus\\dtc\\dtc\\adme\\namesvc.cpp", 0x6CBu);
LABEL_24:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    return 0;
  }
  v18 = (*(__int64 (__fastcall **)(struct IProperties *, char *, __int64))(*(_QWORD *)a1 + 128LL))(a1, String, 10);
  if ( v18 < 0 )
  {
    TraceFile(v18, "failed in GetProtocol", "com\\complus\\dtc\\dtc\\adme\\namesvc.cpp", 0x6DBu);
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v25 + 48LL))(v25, 0);
    goto LABEL_24;
  }
  v19 = atoi(String);
  if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v25 + 80LL))(v25) )
  {
    if ( v19 == 1 )
      v20 = 33;
    else
      v20 = 0;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 48LL))(v25, v20);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  v21 = *(_QWORD *)a1;
  v28 = 0;
  (*(void (__fastcall **)(struct IProperties *, __int64 *))(v21 + 176))(a1, &v28);
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 280LL))(v25, v28);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  return (struct INameObject *)v25;
}

```

## disassembly

```asm
0x180006880  mov     [rsp-8+arg_8], rbx
0x180006885  mov     [rsp-8+arg_10], rsi
0x18000688a  push    rbp
0x18000688b  push    rdi
0x18000688c  push    r14
0x18000688e  lea     rbp, [rsp-200h]
0x180006896  sub     rsp, 300h
0x18000689d  mov     rax, cs:__security_cookie
0x1800068a4  xor     rax, rsp
0x1800068a7  mov     [rbp+210h+var_20], rax
0x1800068ae  mov     rax, [rcx]
0x1800068b1  lea     rdx, [rbp+210h+Uuid]
0x1800068b5  xor     r14d, r14d
0x1800068b8  xorps   xmm0, xmm0
0x1800068bb  mov     rsi, rcx
0x1800068be  mov     [rsp+310h+StringUuid], r14
0x1800068c3  mov     [rsp+310h+var_2B0], r14
0x1800068c8  mov     rax, [rax+18h]
0x1800068cc  movups  xmmword ptr [rbp+210h+Uuid.Data1], xmm0
0x1800068d0  mov     [rsp+310h+var_2A8], r14
0x1800068d5  mov     [rbp+210h+var_258], r14b
0x1800068d9  mov     [rbp+210h+var_230], r14w
0x1800068de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068e3  test    eax, eax
0x1800068e5  jz      short loc_180006907
0x1800068e7  mov     r9d, 695h; unsigned int
0x1800068ed  lea     rdx, aFailedInGetcon; "failed in GetContactId"
0x1800068f4  lea     r8, aComComplusDtcD_39; "com\\complus\\dtc\\dtc\\adme\\namesvc.c"...
0x1800068fb  mov     ecx, eax; int
0x1800068fd  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180006902  jmp     loc_180006C92
0x180006907  lea     rdx, [rsp+310h+StringUuid]; StringUuid
0x18000690c  lea     rcx, [rbp+210h+Uuid]; Uuid
0x180006910  call    cs:__imp_UuidToStringA
0x180006916  test    eax, eax
0x180006918  jz      short loc_180006929
0x18000691a  mov     r9d, 69Dh
0x180006920  lea     rdx, aFailedInUuidto; "failed in UuidToString"
0x180006927  jmp     short loc_1800068F4
0x180006929  mov     r8, [rsp+310h+StringUuid]
0x18000692e  lea     rcx, [rbp+210h+var_258]
0x180006932  mov     eax, 7FFFFFFEh
0x180006937  mov     edx, 25h ; '%'
0x18000693c  test    rax, rax
0x18000693f  jz      short loc_18000695B
0x180006941  mov     r9b, [r8]
0x180006944  test    r9b, r9b
0x180006947  jz      short loc_18000695B
0x180006949  mov     [rcx], r9b
0x18000694c  inc     r8
0x18000694f  inc     rcx
0x180006952  dec     rax
0x180006955  sub     rdx, 1
0x180006959  jnz     short loc_18000693C
0x18000695b  lea     rax, [rcx-1]
0x18000695f  test    rdx, rdx
0x180006962  cmovnz  rax, rcx
0x180006966  lea     rcx, [rsp+310h+StringUuid]; String
0x18000696b  mov     [rax], r14b
0x18000696e  call    cs:__imp_RpcStringFreeA
0x180006974  mov     rax, [rsi]
0x180006977  lea     rdx, [rbp+210h+var_230]
0x18000697b  mov     ebx, 101h
0x180006980  mov     rcx, rsi
0x180006983  mov     r8d, ebx
0x180006986  mov     rax, [rax+48h]
0x18000698a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000698f  test    eax, eax
0x180006991  jns     short loc_1800069A5
0x180006993  mov     r9d, 6ACh
0x180006999  lea     rdx, aFailedInIPcont; "failed in i_pContact->GetHostW"
0x1800069a0  jmp     loc_1800068F4
0x1800069a5  cmp     [rbp+210h+var_230], r14w
0x1800069aa  jnz     short loc_180006A11
0x1800069ac  mov     rax, [rsi]
0x1800069af  lea     rdx, [rsp+310h+var_2A0]
0x1800069b4  mov     rcx, rsi
0x1800069b7  mov     [rbp+210h+pv], r14
0x1800069bb  mov     [rsp+310h+var_2A0], r14
0x1800069c0  mov     rax, [rax+0B0h]
0x1800069c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069cc  mov     rcx, [rsp+310h+var_2A0]
0x1800069d1  lea     rdx, [rbp+210h+pv]
0x1800069d5  mov     rax, [rcx]
0x1800069d8  mov     rax, [rax+28h]
0x1800069dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069e1  mov     rcx, [rsp+310h+var_2A0]
0x1800069e6  mov     rax, [rcx]
0x1800069e9  mov     rax, [rax+10h]
0x1800069ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069f2  mov     r8, [rbp+210h+pv]; unsigned __int16 *
0x1800069f6  lea     rcx, [rbp+210h+var_230]; unsigned __int16 *
0x1800069fa  mov     rdx, rbx; unsigned __int64
0x1800069fd  mov     [rsp+310h+var_2A0], r14
0x180006a02  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180006a07  mov     rcx, [rbp+210h+pv]; pv
0x180006a0b  call    cs:__imp_CoTaskMemFree
0x180006a11  lea     rcx, CLSID_DTCUtil; Buf1
0x180006a18  mov     [rsp+310h+var_2B0], r14
0x180006a1d  mov     ebx, 10h
0x180006a22  mov     rdx, rcx; Buf2
0x180006a25  mov     r8d, ebx; Size
0x180006a28  call    memcmp_0
0x180006a2d  test    eax, eax
0x180006a2f  jnz     loc_180006C05
0x180006a35  mov     ecx, ebx; Size
0x180006a37  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006a3c  mov     [rbp+210h+pv], rax
0x180006a40  test    rax, rax
0x180006a43  jz      loc_180006BFE
0x180006a49  mov     rcx, rax; this
0x180006a4c  call    ??0CClassFactoryDTCUtil@@QEAA@XZ; CClassFactoryDTCUtil::CClassFactoryDTCUtil(void)
0x180006a51  mov     rbx, rax
0x180006a54  test    rax, rax
0x180006a57  jz      loc_180006BFE
0x180006a5d  mov     rcx, [rax]
0x180006a60  lea     r8, [rsp+310h+var_2B0]
0x180006a65  lea     rdx, IID_IClassFactory
0x180006a6c  mov     rax, [rcx]
0x180006a6f  mov     rcx, rbx
0x180006a72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a77  mov     edi, eax
0x180006a79  mov     rcx, rbx; Block
0x180006a7c  test    eax, eax
0x180006a7e  jns     short loc_180006A8A
0x180006a80  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006a85  jmp     loc_180006C0A
0x180006a8a  mov     rax, [rbx]
0x180006a8d  lea     r9, [rsp+310h+var_2B0]
0x180006a92  lea     r8, IID_INameService
0x180006a99  xor     edx, edx
0x180006a9b  mov     rax, [rax+18h]
0x180006a9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006aa4  mov     edi, eax
0x180006aa6  mov     rcx, rbx
0x180006aa9  mov     rax, [rbx]
0x180006aac  mov     rax, [rax+10h]
0x180006ab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ab5  test    edi, edi
0x180006ab7  jnz     loc_180006C0A
0x180006abd  mov     rcx, [rsp+310h+var_2B0]
0x180006ac2  lea     r9, [rsp+310h+var_2A8]
0x180006ac7  lea     r8, [rbp+210h+var_258]
0x180006acb  lea     rdx, [rbp+210h+var_230]
0x180006acf  mov     rax, [rcx]
0x180006ad2  mov     rax, [rax+18h]
0x180006ad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006adb  test    eax, eax
0x180006add  jz      short loc_180006B10
0x180006adf  mov     r9d, 6CBh; unsigned int
0x180006ae5  lea     r8, aComComplusDtcD_39; "com\\complus\\dtc\\dtc\\adme\\namesvc.c"...
0x180006aec  lea     rdx, aFailedInCreate; "failed in CreateNew"
0x180006af3  mov     ecx, eax; int
0x180006af5  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180006afa  mov     rcx, [rsp+310h+var_2B0]
0x180006aff  mov     rax, [rcx]
0x180006b02  mov     rax, [rax+10h]
0x180006b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b0b  jmp     loc_180006C92
0x180006b10  mov     rax, [rsi]
0x180006b13  lea     rdx, [rbp+210h+String]
0x180006b17  mov     r8d, 0Ah
0x180006b1d  mov     rcx, rsi
0x180006b20  mov     rax, [rax+80h]
0x180006b27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b2c  test    eax, eax
0x180006b2e  jns     short loc_180006B60
0x180006b30  mov     r9d, 6DBh; unsigned int
0x180006b36  lea     r8, aComComplusDtcD_39; "com\\complus\\dtc\\dtc\\adme\\namesvc.c"...
0x180006b3d  lea     rdx, aFailedInGetpro; "failed in GetProtocol"
0x180006b44  mov     ecx, eax; int
0x180006b46  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180006b4b  mov     rcx, [rsp+310h+var_2A8]
0x180006b50  xor     edx, edx
0x180006b52  mov     rax, [rcx]
0x180006b55  mov     rax, [rax+30h]
0x180006b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b5e  jmp     short loc_180006AFA
0x180006b60  lea     rcx, [rbp+210h+String]; String
0x180006b64  call    cs:__imp_atoi
0x180006b6a  mov     rdx, [rsp+310h+var_2A8]
0x180006b6f  mov     ebx, eax
0x180006b71  mov     rcx, [rdx]
0x180006b74  mov     rax, [rcx+50h]
0x180006b78  mov     rcx, rdx
0x180006b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b80  test    eax, eax
0x180006b82  jnz     short loc_180006BA1
0x180006b84  mov     rcx, [rsp+310h+var_2A8]
0x180006b89  mov     rax, [rcx]
0x180006b8c  mov     rax, [rax+30h]
0x180006b90  cmp     ebx, 1
0x180006b93  jnz     short loc_180006B9A
0x180006b95  lea     edx, [rbx+20h]
0x180006b98  jmp     short loc_180006B9C
0x180006b9a  xor     edx, edx
0x180006b9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ba1  mov     rcx, [rsp+310h+var_2B0]
0x180006ba6  mov     rax, [rcx]
0x180006ba9  mov     rax, [rax+10h]
0x180006bad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bb2  mov     rax, [rsi]
0x180006bb5  lea     rdx, [rbp+210h+var_290]
0x180006bb9  mov     rcx, rsi
0x180006bbc  mov     [rbp+210h+var_290], r14
0x180006bc0  mov     rax, [rax+0B0h]
0x180006bc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bcc  mov     rcx, [rsp+310h+var_2A8]
0x180006bd1  mov     rdx, [rbp+210h+var_290]
0x180006bd5  mov     rax, [rcx]
0x180006bd8  mov     rax, [rax+118h]
0x180006bdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006be4  mov     rcx, [rbp+210h+var_290]
0x180006be8  mov     rax, [rcx]
0x180006beb  mov     rax, [rax+10h]
0x180006bef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bf4  mov     rax, [rsp+310h+var_2A8]
0x180006bf9  jmp     loc_180006C94
0x180006bfe  mov     edi, 8007000Eh
0x180006c03  jmp     short loc_180006C0A
0x180006c05  mov     edi, 80040111h
0x180006c0a  xorps   xmm0, xmm0
0x180006c0d  lea     rcx, [rbp+210h+pv]; lpSystemTime
0x180006c11  movups  xmmword ptr [rbp+210h+pv], xmm0
0x180006c15  call    cs:__imp_GetLocalTime
0x180006c1b  call    ?OpenTraceFile@@YAPEAU_iobuf@@XZ; OpenTraceFile(void)
0x180006c20  mov     rbx, rax
0x180006c23  test    rax, rax
0x180006c26  jz      short loc_180006C92
0x180006c28  movzx   ecx, word ptr [rbp+210h+pv+0Ah]
0x180006c2c  lea     r11, aComComplusDtcD_39; "com\\complus\\dtc\\dtc\\adme\\namesvc.c"...
0x180006c33  movzx   edx, word ptr [rbp+210h+pv+8]
0x180006c37  lea     rax, aFailedInDllget; "failed in DllGetDTCUtilObject"
0x180006c3e  movzx   r10d, word ptr [rbp+210h+pv]
0x180006c43  movzx   r9d, word ptr [rbp+210h+pv+6]
0x180006c48  movzx   r8d, word ptr [rbp+210h+pv+2]
0x180006c4d  mov     [rsp+310h+var_2C0], 6C2h
0x180006c55  mov     [rsp+310h+var_2C8], r11
0x180006c5a  mov     [rsp+310h+var_2D0], rax
0x180006c5f  mov     [rsp+310h+var_2D8], edi
0x180006c63  mov     [rsp+310h+var_2E0], ecx
0x180006c67  mov     rcx, rbx; Stream
0x180006c6a  mov     [rsp+310h+var_2E8], edx
0x180006c6e  lea     rdx, Format; "%02ld-%02ld-%04ld %02ld:%02ld : DTC Ins"...
0x180006c75  mov     [rsp+310h+var_2F0], r10d
0x180006c7a  call    cs:__imp_fprintf
0x180006c80  mov     rcx, rbx; Stream
0x180006c83  call    cs:__imp_fflush
0x180006c89  mov     rcx, rbx; Stream
0x180006c8c  call    cs:__imp_fclose
0x180006c92  xor     eax, eax
0x180006c94  mov     rcx, [rbp+210h+var_20]
0x180006c9b  xor     rcx, rsp; StackCookie
0x180006c9e  call    __security_check_cookie
0x180006ca3  lea     r11, [rsp+310h+var_10]
0x180006cab  mov     rbx, [r11+28h]
0x180006caf  mov     rsi, [r11+30h]
0x180006cb3  mov     rsp, r11
0x180006cb6  pop     r14
0x180006cb8  pop     rdi
0x180006cb9  pop     rbp
0x180006cba  retn
```
