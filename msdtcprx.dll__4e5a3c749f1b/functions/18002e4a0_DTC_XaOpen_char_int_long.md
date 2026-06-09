# DTC_XaOpen(char *,int,long)

- ea: `0x18002e4a0`
- end: `0x18002e875`
- name: `?DTC_XaOpen@@YAHPEADHJ@Z`
- size: `981`
- prototype: `__int64 __fastcall(char *, unsigned int, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180023810`
- `0x18002e4a0`
- `0x18002f5d4`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e7fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e7fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e569`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e569`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002e5a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002e5a4`
- `msvcrt!fopen` at `0x18002e608`
- `msvcrt!fopen` at `0x18002e608`

## string_xrefs

- `0x18002e4b7`: `Entering DTC_XaOpen, rmid=0x%x, flags=0x%x`
- `0x18002e4d4`: `DTC_XaOpen`
- `0x18002e4c9`: `com\complus\dtc\dtc\msdtcprx\src\dtcxamap.cpp`
- `0x18002e53c`: `DTC_XaOpen - invalid TMASYNC flag.`
- `0x18002e832`: `DTC_XaOpen - invalid arguments.`
- `0x18002e5dc`: `First XaOpen call, retrieved g_pIXaMapFac=%p`
- `0x18002e623`: `First XaOpen call, failed to retrieve g_pIXaMapFac`
- `0x18002e69a`: `Already called XaOpen before, using existing g_pIXaMapFac=%p`
- `0x18002e6bd`: `Attempting to create or retrieve an IXaMapper`
- `0x18002e760`: `XAER_INVAL: (XaOpen) Invalid Argument is passed.`
- `0x18002e79e`: `XAER_RMERR: (XaOpen) Failed to contact the DTC TM`
- `0x18002e64e`: `XAER_RMERR: (XaOpen) A DLL may not be available or MS DTC is          not installed`
- `0x18002e65a`: `XaOpen failed to obtain an XaMapFactory`
- `0x18002e804`: `Exiting DTC_XaOpen, error=%d`

## pseudocode

```c
__int64 __fastcall DTC_XaOpen(char *a1, unsigned int a2, int a3)
{
  const wchar_t *v6; // rax
  unsigned int v7; // ebx
  __int64 v8; // r9
  int TransactionManagerCore; // ebx
  FILE *v10; // rax
  int v11; // edi
  __int64 v13; // [rsp+28h] [rbp-40h]
  __int64 v14; // [rsp+28h] [rbp-40h]
  __int64 v15; // [rsp+28h] [rbp-40h]
  __int64 v16; // [rsp+28h] [rbp-40h]
  __int64 v17; // [rsp+38h] [rbp-30h]
  _QWORD v18[3]; // [rsp+50h] [rbp-18h] BYREF
  __int64 v19; // [rsp+C8h] [rbp+60h] BYREF

  v19 = 0;
  v18[0] = 0;
  TraceStringInline(
    11,
    4,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcxamap.cpp",
    118,
    L"DTC_XaOpen",
    0,
    L"Entering DTC_XaOpen, rmid=0x%x, flags=0x%x",
    a2,
    a3);
  TraceStringInline(
    11,
    4,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcxamap.cpp",
    121,
    L"DTC_XaOpen",
    0,
    L"xa_info=\"%S\"",
    a1);
  if ( a3 < 0 )
  {
    v6 = L"DTC_XaOpen - invalid TMASYNC flag.";
    v7 = -2;
    v8 = 128;
LABEL_21:
    LODWORD(v13) = v7;
    TraceStringInline(11, 1, L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcxamap.cpp", v8, L"DTC_XaOpen", v13, v6);
    return v7;
  }
  if ( !a1 || a3 )
  {
    v6 = L"DTC_XaOpen - invalid arguments.";
    v7 = -2147024809;
    v8 = 135;
    goto LABEL_21;
  }
  EnterCriticalSection(&stru_1800D5FD0);
  if ( g_pIXaMapFac )
  {
    v19 = (__int64)g_pIXaMapFac;
    (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)g_pIXaMapFac + 8LL))(g_pIXaMapFac);
    TraceStringInline(
      11,
      4,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcxamap.cpp",
      191,
      L"DTC_XaOpen",
      0,
      L"Already called XaOpen before, using existing g_pIXaMapFac=%p",
      g_pIXaMapFac);
  }
  else
  {
    TransactionManagerCore = DllGetTransactionManagerCore(0, 0, (__int64)&v19);
    if ( TransactionManagerCore )
    {
      LODWORD(v14) = TransactionManagerCore;
      TraceStringInline(
        11,
        1,
        L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcxamap.cpp",
        179,
        L"DTC_XaOpen",
        v14,
        L"First XaOpen call, failed to retrieve g_pIXaMapFac");
      XALogWrite("XAER_RMERR: (XaOpen) A DLL may not be available or MS DTC is          not installed");
      LODWORD(v15) = TransactionManagerCore;
      TraceStringInline(
        11,
        1,
        L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcxamap.cpp",
        238,
        L"DTC_XaOpen",
        v15,
        L"XaOpen failed to obtain an XaMapFactory");
      goto LABEL_16;
    }
    g_dwProcId = GetCurrentProcessId();
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
    g_pIXaMapFac = (unsigned __int16 *)v19;
    TraceStringInline(
      11,
      4,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcxamap.cpp",
      167,
      L"DTC_XaOpen",
      0,
      L"First XaOpen call, retrieved g_pIXaMapFac=%p",
      v19);
    v10 = fopen("dtcxa.log", "a+");
    if ( v10 )
      g_pfile = v10;
  }
  TraceStringInline(
    11,
    4,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcxamap.cpp",
    201,
    L"DTC_XaOpen",
    0,
    L"Attempting to create or retrieve an IXaMapper");
  v11 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD, _QWORD, _QWORD *))(*(_QWORD *)v19 + 24LL))(
          v19,
          a1,
          a2,
          0,
          v18);
  if ( v11 )
  {
    if ( v11 == -2147024809 )
    {
      XALogWrite("XAER_INVAL: (XaOpen) Invalid Argument is passed.");
      LODWORD(v16) = -2147024809;
      TraceStringInline(
        11,
        1,
        L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcxamap.cpp",
        219,
        L"DTC_XaOpen",
        v16,
        L"Failed to obtain an IXaMapper, invalid arguments");
      v7 = -5;
      goto LABEL_17;
    }
    XALogWrite("XAER_RMERR: (XaOpen) Failed to contact the DTC TM");
    LODWORD(v16) = v11;
    TraceStringInline(
      11,
      1,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcxamap.cpp",
      228,
      L"DTC_XaOpen",
      v16,
      L"Failed to obtain an IXaMapper, couldn't contact DTC TM");
LABEL_16:
    v7 = -3;
    goto LABEL_17;
  }
  v7 = 0;
  TraceStringInline(
    11,
    4,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcxamap.cpp",
    209,
    L"DTC_XaOpen",
    0,
    L"Succeeded in obtaining an IXaMapper");
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v18[0] + 16LL))(v18[0]);
  v18[0] = 0;
LABEL_17:
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  LeaveCriticalSection(&stru_1800D5FD0);
  LODWORD(v17) = v7;
  TraceStringInline(
    11,
    4,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcxamap.cpp",
    265,
    L"DTC_XaOpen",
    0,
    L"Exiting DTC_XaOpen, error=%d",
    v17);
  return v7;
}

```

## disassembly

```asm
0x18002e4a0  push    rbp
0x18002e4a2  push    rbx
0x18002e4a3  push    rsi
0x18002e4a4  push    rdi
0x18002e4a5  push    r12
0x18002e4a7  push    r13
0x18002e4a9  push    r14
0x18002e4ab  push    r15
0x18002e4ad  mov     rbp, rsp
0x18002e4b0  sub     rsp, 68h
0x18002e4b4  xor     r14d, r14d
0x18002e4b7  lea     rax, aEnteringDtcXao; "Entering DTC_XaOpen, rmid=0x%x, flags=0"...
0x18002e4be  mov     ebx, r8d
0x18002e4c1  mov     [rbp+arg_18], r14
0x18002e4c5  mov     [rsp+68h+var_28], ebx
0x18002e4c9  lea     r15, aComComplusDtcD_31; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18002e4d0  mov     dword ptr [rsp+68h+var_30], edx
0x18002e4d4  lea     r13, aDtcXaopen_0; "DTC_XaOpen"
0x18002e4db  mov     [rsp+68h+var_38], rax
0x18002e4e0  lea     r12d, [r14+0Bh]
0x18002e4e4  mov     esi, edx
0x18002e4e6  mov     [rsp+68h+var_40], r14
0x18002e4eb  mov     rdi, rcx
0x18002e4ee  mov     [rbp+var_18], r14
0x18002e4f2  mov     ecx, r12d
0x18002e4f5  mov     [rsp+68h+var_48], r13
0x18002e4fa  lea     r9d, [r14+76h]
0x18002e4fe  mov     r8, r15
0x18002e501  lea     edx, [r14+4]
0x18002e505  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18002e50a  mov     [rsp+68h+var_30], rdi
0x18002e50f  lea     rax, aXaInfoS; "xa_info=\"%S\""
0x18002e516  mov     [rsp+68h+var_38], rax
0x18002e51b  lea     r9d, [r14+79h]
0x18002e51f  mov     [rsp+68h+var_40], r14
0x18002e524  lea     edx, [r14+4]
0x18002e528  mov     r8, r15
0x18002e52b  mov     [rsp+68h+var_48], r13
0x18002e530  mov     ecx, r12d
0x18002e533  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18002e538  test    ebx, ebx
0x18002e53a  jns     short loc_18002E551
0x18002e53c  lea     rax, aDtcXaopenInval_0; "DTC_XaOpen - invalid TMASYNC flag."
0x18002e543  lea     ebx, [r14-2]
0x18002e547  lea     r9d, [r12+75h]
0x18002e54c  jmp     loc_18002E844
0x18002e551  test    rdi, rdi
0x18002e554  jz      loc_18002E832
0x18002e55a  test    ebx, ebx
0x18002e55c  jnz     loc_18002E832
0x18002e562  lea     rcx, stru_1800D5FD0; lpCriticalSection
0x18002e569  call    cs:__imp_EnterCriticalSection
0x18002e56f  mov     rcx, cs:?g_pIXaMapFac@@3PEAUIXaMapperFactory@@EA; unsigned __int16 *
0x18002e576  test    rcx, rcx
0x18002e579  jnz     loc_18002E675
0x18002e57f  lea     rax, [rbp+arg_18]
0x18002e583  xor     r9d, r9d
0x18002e586  mov     [rsp+68h+var_40], rax; __int64
0x18002e58b  lea     r8, IID_IXaMapperFactory
0x18002e592  xor     edx, edx
0x18002e594  mov     [rsp+68h+var_48], r14; void *
0x18002e599  call    DllGetTransactionManagerCore
0x18002e59e  mov     ebx, eax
0x18002e5a0  test    eax, eax
0x18002e5a2  jnz     short loc_18002E623
0x18002e5a4  call    cs:__imp_GetCurrentProcessId
0x18002e5aa  mov     rcx, [rbp+arg_18]
0x18002e5ae  mov     cs:?g_dwProcId@@3KA, eax; ulong g_dwProcId
0x18002e5b4  mov     rax, [rcx]
0x18002e5b7  mov     rax, [rax+8]
0x18002e5bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e5c0  mov     rax, [rbp+arg_18]
0x18002e5c4  lea     edx, [rbx+4]
0x18002e5c7  mov     [rsp+68h+var_30], rax
0x18002e5cc  mov     r9d, 0A7h
0x18002e5d2  mov     cs:?g_pIXaMapFac@@3PEAUIXaMapperFactory@@EA, rax; IXaMapperFactory * g_pIXaMapFac
0x18002e5d9  mov     r8, r15
0x18002e5dc  lea     rax, aFirstXaopenCal; "First XaOpen call, retrieved g_pIXaMapF"...
0x18002e5e3  mov     ecx, r12d
0x18002e5e6  mov     [rsp+68h+var_38], rax
0x18002e5eb  mov     [rsp+68h+var_40], r14
0x18002e5f0  mov     [rsp+68h+var_48], r13
0x18002e5f5  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18002e5fa  lea     rdx, Mode; "a+"
0x18002e601  lea     rcx, FileName; "dtcxa.log"
0x18002e608  call    cs:__imp_fopen
0x18002e60e  test    rax, rax
0x18002e611  jz      loc_18002E6BD
0x18002e617  mov     cs:?g_pfile@@3PEAU_iobuf@@EA, rax; _iobuf * g_pfile
0x18002e61e  jmp     loc_18002E6BD
0x18002e623  lea     rax, aFirstXaopenCal_0; "First XaOpen call, failed to retrieve g"...
0x18002e62a  mov     r9d, 0B3h
0x18002e630  mov     [rsp+68h+var_38], rax
0x18002e635  mov     r8, r15
0x18002e638  mov     dword ptr [rsp+68h+var_40], ebx
0x18002e63c  mov     edx, 1
0x18002e641  mov     ecx, r12d
0x18002e644  mov     [rsp+68h+var_48], r13
0x18002e649  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18002e64e  lea     rcx, aXaerRmerrXaope_0; "XAER_RMERR: (XaOpen) A DLL may not be a"...
0x18002e655  call    XALogWrite
0x18002e65a  lea     rax, aXaopenFailedTo; "XaOpen failed to obtain an XaMapFactory"
0x18002e661  mov     r9d, 0EEh
0x18002e667  mov     [rsp+68h+var_38], rax
0x18002e66c  mov     dword ptr [rsp+68h+var_40], ebx
0x18002e670  jmp     loc_18002E7C0
0x18002e675  mov     [rbp+arg_18], rcx
0x18002e679  mov     rax, [rcx]
0x18002e67c  mov     rax, [rax+8]
0x18002e680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e685  mov     rax, cs:?g_pIXaMapFac@@3PEAUIXaMapperFactory@@EA; IXaMapperFactory * g_pIXaMapFac
0x18002e68c  mov     r9d, 0BFh
0x18002e692  mov     [rsp+68h+var_30], rax
0x18002e697  mov     r8, r15
0x18002e69a  lea     rax, aAlreadyCalledX; "Already called XaOpen before, using exi"...
0x18002e6a1  mov     edx, 4
0x18002e6a6  mov     [rsp+68h+var_38], rax
0x18002e6ab  mov     ecx, r12d
0x18002e6ae  mov     [rsp+68h+var_40], r14
0x18002e6b3  mov     [rsp+68h+var_48], r13
0x18002e6b8  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18002e6bd  lea     rax, aAttemptingToCr; "Attempting to create or retrieve an IXa"...
0x18002e6c4  mov     r9d, 0C9h
0x18002e6ca  mov     [rsp+68h+var_38], rax
0x18002e6cf  mov     r8, r15
0x18002e6d2  mov     [rsp+68h+var_40], r14
0x18002e6d7  mov     edx, 4
0x18002e6dc  mov     ecx, r12d
0x18002e6df  mov     [rsp+68h+var_48], r13
0x18002e6e4  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18002e6e9  mov     rcx, [rbp+arg_18]
0x18002e6ed  lea     rdx, [rbp+var_18]
0x18002e6f1  mov     [rsp+68h+var_48], rdx
0x18002e6f6  xor     r9d, r9d
0x18002e6f9  mov     r8d, esi
0x18002e6fc  mov     rdx, rdi
0x18002e6ff  mov     rax, [rcx]
0x18002e702  mov     rax, [rax+18h]
0x18002e706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e70b  mov     edi, eax
0x18002e70d  test    eax, eax
0x18002e70f  jnz     short loc_18002E757
0x18002e711  lea     rax, aSucceededInObt; "Succeeded in obtaining an IXaMapper"
0x18002e718  mov     r9d, 0D1h
0x18002e71e  mov     [rsp+68h+var_38], rax
0x18002e723  lea     edx, [rdi+4]
0x18002e726  mov     [rsp+68h+var_40], r14
0x18002e72b  mov     r8, r15
0x18002e72e  mov     ecx, r12d
0x18002e731  mov     [rsp+68h+var_48], r13
0x18002e736  mov     ebx, r14d
0x18002e739  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18002e73e  mov     rcx, [rbp+var_18]
0x18002e742  mov     rax, [rcx]
0x18002e745  mov     rax, [rax+10h]
0x18002e749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e74e  mov     [rbp+var_18], r14
0x18002e752  jmp     loc_18002E7DA
0x18002e757  mov     ebx, 80070057h
0x18002e75c  cmp     edi, ebx
0x18002e75e  jnz     short loc_18002E79E
0x18002e760  lea     rcx, aXaerInvalXaope; "XAER_INVAL: (XaOpen) Invalid Argument i"...
0x18002e767  call    XALogWrite
0x18002e76c  lea     rax, aFailedToObtain_0; "Failed to obtain an IXaMapper, invalid "...
0x18002e773  mov     r9d, 0DBh
0x18002e779  mov     [rsp+68h+var_38], rax
0x18002e77e  mov     r8, r15
0x18002e781  mov     dword ptr [rsp+68h+var_40], ebx
0x18002e785  mov     edx, 1
0x18002e78a  mov     ecx, r12d
0x18002e78d  mov     [rsp+68h+var_48], r13
0x18002e792  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18002e797  mov     ebx, 0FFFFFFFBh
0x18002e79c  jmp     short loc_18002E7DA
0x18002e79e  lea     rcx, aXaerRmerrXaope; "XAER_RMERR: (XaOpen) Failed to contact "...
0x18002e7a5  call    XALogWrite
0x18002e7aa  lea     rax, aFailedToObtain; "Failed to obtain an IXaMapper, couldn't"...
0x18002e7b1  mov     r9d, 0E4h
0x18002e7b7  mov     [rsp+68h+var_38], rax
0x18002e7bc  mov     dword ptr [rsp+68h+var_40], edi
0x18002e7c0  mov     r8, r15
0x18002e7c3  mov     [rsp+68h+var_48], r13
0x18002e7c8  mov     edx, 1
0x18002e7cd  mov     ecx, r12d
0x18002e7d0  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18002e7d5  mov     ebx, 0FFFFFFFDh
0x18002e7da  mov     rcx, [rbp+arg_18]
0x18002e7de  test    rcx, rcx
0x18002e7e1  jz      short loc_18002E7F3
0x18002e7e3  mov     rax, [rcx]
0x18002e7e6  mov     rax, [rax+10h]
0x18002e7ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e7ef  mov     [rbp+arg_18], r14
0x18002e7f3  lea     rcx, stru_1800D5FD0; lpCriticalSection
0x18002e7fa  call    cs:__imp_LeaveCriticalSection
0x18002e800  mov     dword ptr [rsp+68h+var_30], ebx
0x18002e804  lea     rax, aExitingDtcXaop; "Exiting DTC_XaOpen, error=%d"
0x18002e80b  mov     [rsp+68h+var_38], rax
0x18002e810  mov     r9d, 109h
0x18002e816  mov     [rsp+68h+var_40], r14
0x18002e81b  mov     r8, r15
0x18002e81e  mov     edx, 4
0x18002e823  mov     [rsp+68h+var_48], r13
0x18002e828  mov     ecx, r12d
0x18002e82b  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18002e830  jmp     short loc_18002E862
0x18002e832  lea     rax, aDtcXaopenInval; "DTC_XaOpen - invalid arguments."
0x18002e839  mov     ebx, 80070057h
0x18002e83e  mov     r9d, 87h
0x18002e844  mov     [rsp+68h+var_38], rax
0x18002e849  mov     r8, r15
0x18002e84c  mov     dword ptr [rsp+68h+var_40], ebx
0x18002e850  mov     edx, 1
0x18002e855  mov     ecx, r12d
0x18002e858  mov     [rsp+68h+var_48], r13
0x18002e85d  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18002e862  mov     eax, ebx
0x18002e864  add     rsp, 68h
0x18002e868  pop     r15
0x18002e86a  pop     r14
0x18002e86c  pop     r13
0x18002e86e  pop     r12
0x18002e870  pop     rdi
0x18002e871  pop     rsi
0x18002e872  pop     rbx
0x18002e873  pop     rbp
0x18002e874  retn
```
