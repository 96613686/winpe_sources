# TerminateComAdmindata

- ea: `0x18000a6c0`
- end: `0x18000abb6`
- name: `TerminateComAdmindata`
- size: `1270`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1800010a4`
- `0x18000a6c0`
- `0x18000b2d4`
- `0x18000dc5c`
- `0x18000dd4c`
- `0x180010010`

## import_xrefs

- `ole32!CoRevokeClassObject` at `0x18000a7a4`
- `ole32!CoRevokeClassObject` at `0x18000a7a4`
- `KERNEL32!Sleep` at `0x18000a95e`
- `KERNEL32!Sleep` at `0x18000a95e`
- `IisRTL!PuDbgPrint` at `0x18000a70c`
- `IisRTL!PuDbgPrint` at `0x18000a748`
- `IisRTL!PuDbgPrint` at `0x18000a794`
- `IisRTL!PuDbgPrint` at `0x18000a7e2`
- `IisRTL!PuDbgPrint` at `0x18000a839`
- `IisRTL!PuDbgPrint` at `0x18000a8b4`
- `IisRTL!PuDbgPrint` at `0x18000a913`
- `IisRTL!PuDbgPrint` at `0x18000a953`
- `IisRTL!PuDbgPrint` at `0x18000a99b`
- `IisRTL!PuDbgPrint` at `0x18000aa06`
- `IisRTL!PuDbgPrint` at `0x18000aa4c`
- `IisRTL!PuDbgPrint` at `0x18000aad5`
- `IisRTL!PuDbgPrint` at `0x18000ab1e`
- `IisRTL!PuDbgPrint` at `0x18000aba1`
- `IisRTL!PuDbgPrint` at `0x18000a70c`
- `IisRTL!PuDbgPrint` at `0x18000a748`
- `IisRTL!PuDbgPrint` at `0x18000a794`
- `IisRTL!PuDbgPrint` at `0x18000a7e2`
- `IisRTL!PuDbgPrint` at `0x18000a839`
- `IisRTL!PuDbgPrint` at `0x18000a8b4`
- `IisRTL!PuDbgPrint` at `0x18000a913`
- `IisRTL!PuDbgPrint` at `0x18000a953`
- `IisRTL!PuDbgPrint` at `0x18000a99b`
- `IisRTL!PuDbgPrint` at `0x18000aa06`
- `IisRTL!PuDbgPrint` at `0x18000aa4c`
- `IisRTL!PuDbgPrint` at `0x18000aad5`
- `IisRTL!PuDbgPrint` at `0x18000ab1e`
- `IisRTL!PuDbgPrint` at `0x18000aba1`
- `abocomp!TerminateAboCompatibilityLayer` at `0x18000a9d8`
- `abocomp!TerminateAboCompatibilityLayer` at `0x18000a9d8`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x18000a86a`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x18000a8e5`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x18000aa8d`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x18000ab69`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x18000a86a`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x18000a8e5`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x18000aa8d`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x18000ab69`

## string_xrefs

- `0x18000a6f4`: `[TerminateComAdmindata] Terminating ABO.\n`
- `0x18000a6d3`: `TerminateComAdmindata`
- `0x18000a730`: `[TerminateComAdmindata] Not initialized!\n`
- `0x18000a77c`: `[TerminateComAdmindata] Disabled the ACL cache.\n`
- `0x18000a7cc`: `[TerminateComAdmindata] Revoked the ABO class factory %d with hr = 0x%08x.\n`
- `0x18000a82a`: `[TerminateComAdmindata] Sent shutdown notifications with hr = 0x%08x.\n`
- `0x18000a8a5`: `[TerminateComAdmindata] Stopped EWR with hr = 0x%08x.\n`
- `0x18000a8fb`: `[TerminateComAdmindata] Terminating all ABO objects.\n`
- `0x18000a937`: `[TerminateComAdmindata] Waiting on factory shutdown, i = %d\n`
- `0x18000a983`: `[TerminateComAdmindata] Terminated all ABO objects.\n`
- `0x18000a9ee`: `[TerminateComAdmindata] Terminated ABO wrapper.\n`
- `0x18000aa34`: `[TerminateComAdmindata] Terminated ABO ROT.\n`
- `0x18000aac6`: `[TerminateComAdmindata] Shutdown metadata with hr = 0x%08x.\n`
- `0x18000ab0f`: `[TerminateComAdmindata] Terminated metadata with hr = 0x%08x.\n`
- `0x18000ab85`: `[TerminateComAdmindata] Done with hr = 0x%08x.\n`

## pseudocode

```c
__int64 TerminateComAdmindata()
{
  char v0; // al
  unsigned int v1; // edi
  HRESULT v2; // eax
  int v3; // eax
  unsigned int v4; // eax
  int i; // ebx
  LPVOID v6; // rdx
  int v7; // eax
  unsigned int v8; // eax

  v0 = g_dwDebugFlags;
  v1 = 0;
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\coadmin\\loadadm.cxx",
      255,
      "TerminateComAdmindata",
      "[TerminateComAdmindata] Terminating ABO.\n");
    v0 = g_dwDebugFlags;
  }
  if ( g_bInitialized )
  {
    g_bInitialized = 0;
    _InterlockedDecrement(g_AclCache);
    CAdminAclCache::Flush((CAdminAclCache *)g_AclCache);
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\coadmin\\loadadm.cxx",
        273,
        "TerminateComAdmindata",
        "[TerminateComAdmindata] Disabled the ACL cache.\n");
    if ( g_dwComRegisterW )
    {
      v2 = CoRevokeClassObject(g_dwComRegisterW);
      v1 = v2;
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\coadmin\\loadadm.cxx",
          281,
          "TerminateComAdmindata",
          "[TerminateComAdmindata] Revoked the ABO class factory %d with hr = 0x%08x.\n",
          g_dwComRegisterW,
          v2);
      g_dwComRegisterW = 0;
    }
    if ( g_pcCom )
    {
      v3 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)g_pcCom + 520LL))(g_pcCom);
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\coadmin\\loadadm.cxx",
          290,
          "TerminateComAdmindata",
          "[TerminateComAdmindata] Sent shutdown notifications with hr = 0x%08x.\n",
          v3);
      if ( *((_DWORD *)g_pEtwCoAdminTracer + 2)
        && (*((_BYTE *)g_pEtwCoAdminTracer + 40) & 2) != 0
        && *((_DWORD *)g_pEtwCoAdminTracer + 11) >= 4u )
      {
        CEtwTracer::EtwTraceEvent(g_pEtwCoAdminTracer, (const struct _GUID *)IISAdminShutdownGuid, 0xAu);
      }
      v4 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)g_pcCom + 512LL))(g_pcCom);
      v1 = v4;
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\coadmin\\loadadm.cxx",
          306,
          "TerminateComAdmindata",
          "[TerminateComAdmindata] Stopped EWR with hr = 0x%08x.\n",
          v4);
      if ( *((_DWORD *)g_pEtwCoAdminTracer + 2)
        && (*((_BYTE *)g_pEtwCoAdminTracer + 40) & 2) != 0
        && *((_DWORD *)g_pEtwCoAdminTracer + 11) >= 4u )
      {
        CEtwTracer::EtwTraceEvent(g_pEtwCoAdminTracer, (const struct _GUID *)IISAdminShutdownGuid, 0xBu);
      }
    }
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\coadmin\\loadadm.cxx",
        321,
        "TerminateComAdmindata",
        "[TerminateComAdmindata] Terminating all ABO objects.\n");
    CADMCOMW::ShutDownObjects();
    for ( i = 0; g_dwRefCount && i < 5; ++i )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\coadmin\\loadadm.cxx",
          330,
          "TerminateComAdmindata",
          "[TerminateComAdmindata] Waiting on factory shutdown, i = %d\n",
          i);
      Sleep(0x3E8u);
    }
    CADMCOMW::ShutDownObjects();
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\coadmin\\loadadm.cxx",
        338,
        "TerminateComAdmindata",
        "[TerminateComAdmindata] Terminated all ABO objects.\n");
    if ( g_pAboSink )
    {
      operator delete(g_pAboSink);
      g_pAboSink = 0;
    }
    if ( CADMCOMW::s_pAboWrapper )
    {
      (*(void (__fastcall **)(struct IAboWrapper *))(*(_QWORD *)CADMCOMW::s_pAboWrapper + 16LL))(CADMCOMW::s_pAboWrapper);
      CADMCOMW::s_pAboWrapper = 0;
      TerminateAboCompatibilityLayer();
    }
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\coadmin\\loadadm.cxx",
        342,
        "TerminateComAdmindata",
        "[TerminateComAdmindata] Terminated ABO wrapper.\n");
    _InterlockedDecrement(g_AclCache);
    CAdminAclCache::Flush((CAdminAclCache *)g_AclCache);
    CADMCOMW::TerminateObjectList();
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\coadmin\\loadadm.cxx",
        350,
        "TerminateComAdmindata",
        "[TerminateComAdmindata] Terminated ABO ROT.\n");
    v6 = g_pcCom;
    if ( g_pcCom )
    {
      if ( *((_DWORD *)g_pEtwCoAdminTracer + 2)
        && (*((_BYTE *)g_pEtwCoAdminTracer + 40) & 2) != 0
        && *((_DWORD *)g_pEtwCoAdminTracer + 11) >= 4u )
      {
        CEtwTracer::EtwTraceEvent(g_pEtwCoAdminTracer, (const struct _GUID *)IISAdminShutdownGuid, 0x10u);
        v6 = g_pcCom;
      }
      v7 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 40LL))(v6);
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\coadmin\\loadadm.cxx",
          368,
          "TerminateComAdmindata",
          "[TerminateComAdmindata] Shutdown metadata with hr = 0x%08x.\n",
          v7);
      v8 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)g_pcCom + 32LL))(g_pcCom, 0);
      v1 = v8;
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\coadmin\\loadadm.cxx",
          372,
          "TerminateComAdmindata",
          "[TerminateComAdmindata] Terminated metadata with hr = 0x%08x.\n",
          v8);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)g_pcCom + 16LL))(g_pcCom);
      g_pcCom = 0;
      if ( *((_DWORD *)g_pEtwCoAdminTracer + 2)
        && (*((_BYTE *)g_pEtwCoAdminTracer + 40) & 2) != 0
        && *((_DWORD *)g_pEtwCoAdminTracer + 11) >= 4u )
      {
        CEtwTracer::EtwTraceEvent(g_pEtwCoAdminTracer, (const struct _GUID *)IISAdminShutdownGuid, 0x11u);
      }
    }
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\coadmin\\loadadm.cxx",
        392,
        "TerminateComAdmindata",
        "[TerminateComAdmindata] Done with hr = 0x%08x.\n",
        v1);
  }
  else if ( (v0 & 3) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\coadmin\\loadadm.cxx",
      260,
      "TerminateComAdmindata",
      "[TerminateComAdmindata] Not initialized!\n");
  }
  return v1;
}

```

## disassembly

```asm
0x18000a6c0  push    rbx
0x18000a6c2  push    rbp
0x18000a6c3  push    rsi
0x18000a6c4  push    rdi
0x18000a6c5  push    r14
0x18000a6c7  push    r15
0x18000a6c9  sub     rsp, 48h
0x18000a6cd  mov     eax, cs:g_dwDebugFlags
0x18000a6d3  lea     r14, aTerminatecomad_9; "TerminateComAdmindata"
0x18000a6da  xor     esi, esi
0x18000a6dc  lea     r15, aInetsrvIisMbCo_1; "inetsrv\\iis\\mb\\coadmin\\loadadm.cxx"
0x18000a6e3  mov     bpl, 3
0x18000a6e6  mov     edi, esi
0x18000a6e8  test    bpl, al
0x18000a6eb  jz      short loc_18000A718
0x18000a6ed  mov     rcx, cs:g_pDebug
0x18000a6f4  lea     rax, aTerminatecomad_10; "[TerminateComAdmindata] Terminating ABO"...
0x18000a6fb  mov     r9, r14
0x18000a6fe  mov     [rsp+78h+var_58], rax
0x18000a703  mov     r8d, 0FFh
0x18000a709  mov     rdx, r15
0x18000a70c  call    cs:__imp_PuDbgPrint
0x18000a712  mov     eax, cs:g_dwDebugFlags
0x18000a718  cmp     cs:?g_bInitialized@@3KA, esi; ulong g_bInitialized
0x18000a71e  jnz     short loc_18000A753
0x18000a720  test    bpl, al
0x18000a723  jz      loc_18000ABA7
0x18000a729  mov     rcx, cs:g_pDebug
0x18000a730  lea     rax, aTerminatecomad_8; "[TerminateComAdmindata] Not initialized"...
0x18000a737  mov     r9, r14
0x18000a73a  mov     [rsp+78h+var_58], rax
0x18000a73f  mov     r8d, 104h
0x18000a745  mov     rdx, r15
0x18000a748  call    cs:__imp_PuDbgPrint
0x18000a74e  jmp     loc_18000ABA7
0x18000a753  mov     cs:?g_bInitialized@@3KA, esi; ulong g_bInitialized
0x18000a759  lea     rcx, ?g_AclCache@@3VCAdminAclCache@@A; this
0x18000a760  lock dec cs:?g_AclCache@@3VCAdminAclCache@@A; CAdminAclCache g_AclCache
0x18000a767  call    ?Flush@CAdminAclCache@@QEAAJXZ; CAdminAclCache::Flush(void)
0x18000a76c  test    byte ptr cs:g_dwDebugFlags, bpl
0x18000a773  jz      short loc_18000A79A
0x18000a775  mov     rcx, cs:g_pDebug
0x18000a77c  lea     rax, aTerminatecomad_1; "[TerminateComAdmindata] Disabled the AC"...
0x18000a783  mov     r9, r14
0x18000a786  mov     [rsp+78h+var_58], rax
0x18000a78b  mov     r8d, 111h
0x18000a791  mov     rdx, r15
0x18000a794  call    cs:__imp_PuDbgPrint
0x18000a79a  mov     ecx, cs:?g_dwComRegisterW@@3KA; dwRegister
0x18000a7a0  test    ecx, ecx
0x18000a7a2  jz      short loc_18000A7EE
0x18000a7a4  call    cs:__imp_CoRevokeClassObject
0x18000a7aa  test    byte ptr cs:g_dwDebugFlags, bpl
0x18000a7b1  mov     edi, eax
0x18000a7b3  jz      short loc_18000A7E8
0x18000a7b5  mov     ecx, cs:?g_dwComRegisterW@@3KA; ulong g_dwComRegisterW
0x18000a7bb  mov     r9, r14
0x18000a7be  mov     [rsp+78h+var_48], eax
0x18000a7c2  mov     r8d, 119h
0x18000a7c8  mov     [rsp+78h+var_50], ecx
0x18000a7cc  lea     rax, aTerminatecomad_13; "[TerminateComAdmindata] Revoked the ABO"...
0x18000a7d3  mov     rcx, cs:g_pDebug
0x18000a7da  mov     rdx, r15
0x18000a7dd  mov     [rsp+78h+var_58], rax
0x18000a7e2  call    cs:__imp_PuDbgPrint
0x18000a7e8  mov     cs:?g_dwComRegisterW@@3KA, esi; ulong g_dwComRegisterW
0x18000a7ee  mov     rcx, cs:?g_pcCom@@3PEAUIMDCOM3@@EA; IMDCOM3 * g_pcCom
0x18000a7f5  test    rcx, rcx
0x18000a7f8  jz      loc_18000A8EB
0x18000a7fe  mov     rax, [rcx]
0x18000a801  mov     rax, [rax+208h]
0x18000a808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a80d  test    byte ptr cs:g_dwDebugFlags, bpl
0x18000a814  jz      short loc_18000A83F
0x18000a816  mov     rcx, cs:g_pDebug
0x18000a81d  mov     r9, r14
0x18000a820  mov     [rsp+78h+var_50], eax
0x18000a824  mov     r8d, 122h
0x18000a82a  lea     rax, aTerminatecomad_2; "[TerminateComAdmindata] Sent shutdown n"...
0x18000a831  mov     rdx, r15
0x18000a834  mov     [rsp+78h+var_58], rax
0x18000a839  call    cs:__imp_PuDbgPrint
0x18000a83f  mov     rcx, cs:?g_pEtwCoAdminTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwCoAdminTracer
0x18000a846  cmp     [rcx+8], esi
0x18000a849  jz      short loc_18000A870
0x18000a84b  test    byte ptr [rcx+28h], 2
0x18000a84f  jz      short loc_18000A870
0x18000a851  cmp     dword ptr [rcx+2Ch], 4
0x18000a855  jb      short loc_18000A870
0x18000a857  xor     r9d, r9d
0x18000a85a  mov     [rsp+78h+var_58], rsi
0x18000a85f  lea     rdx, IISAdminShutdownGuid
0x18000a866  lea     r8d, [r9+0Ah]
0x18000a86a  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ; CEtwTracer::EtwTraceEvent(_GUID const *,ulong,...)
0x18000a870  mov     rcx, cs:?g_pcCom@@3PEAUIMDCOM3@@EA; IMDCOM3 * g_pcCom
0x18000a877  mov     rax, [rcx]
0x18000a87a  mov     rax, [rax+200h]
0x18000a881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a886  test    byte ptr cs:g_dwDebugFlags, bpl
0x18000a88d  mov     edi, eax
0x18000a88f  jz      short loc_18000A8BA
0x18000a891  mov     rcx, cs:g_pDebug
0x18000a898  mov     r9, r14
0x18000a89b  mov     [rsp+78h+var_50], eax
0x18000a89f  mov     r8d, 132h
0x18000a8a5  lea     rax, aTerminatecomad_6; "[TerminateComAdmindata] Stopped EWR wit"...
0x18000a8ac  mov     rdx, r15
0x18000a8af  mov     [rsp+78h+var_58], rax
0x18000a8b4  call    cs:__imp_PuDbgPrint
0x18000a8ba  mov     rcx, cs:?g_pEtwCoAdminTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwCoAdminTracer
0x18000a8c1  cmp     [rcx+8], esi
0x18000a8c4  jz      short loc_18000A8EB
0x18000a8c6  test    byte ptr [rcx+28h], 2
0x18000a8ca  jz      short loc_18000A8EB
0x18000a8cc  cmp     dword ptr [rcx+2Ch], 4
0x18000a8d0  jb      short loc_18000A8EB
0x18000a8d2  xor     r9d, r9d
0x18000a8d5  mov     [rsp+78h+var_58], rsi
0x18000a8da  lea     rdx, IISAdminShutdownGuid
0x18000a8e1  lea     r8d, [r9+0Bh]
0x18000a8e5  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ; CEtwTracer::EtwTraceEvent(_GUID const *,ulong,...)
0x18000a8eb  test    byte ptr cs:g_dwDebugFlags, bpl
0x18000a8f2  jz      short loc_18000A919
0x18000a8f4  mov     rcx, cs:g_pDebug
0x18000a8fb  lea     rax, aTerminatecomad_3; "[TerminateComAdmindata] Terminating all"...
0x18000a902  mov     r9, r14
0x18000a905  mov     [rsp+78h+var_58], rax
0x18000a90a  mov     r8d, 141h
0x18000a910  mov     rdx, r15
0x18000a913  call    cs:__imp_PuDbgPrint
0x18000a919  call    ?ShutDownObjects@CADMCOMW@@SAXXZ; CADMCOMW::ShutDownObjects(void)
0x18000a91e  mov     ebx, esi
0x18000a920  jmp     short loc_18000A966
0x18000a922  cmp     ebx, 5
0x18000a925  jge     short loc_18000A96E
0x18000a927  test    byte ptr cs:g_dwDebugFlags, bpl
0x18000a92e  jz      short loc_18000A959
0x18000a930  mov     rcx, cs:g_pDebug
0x18000a937  lea     rax, aTerminatecomad_14; "[TerminateComAdmindata] Waiting on fact"...
0x18000a93e  mov     [rsp+78h+var_50], ebx
0x18000a942  mov     r9, r14
0x18000a945  mov     r8d, 14Ah
0x18000a94b  mov     [rsp+78h+var_58], rax
0x18000a950  mov     rdx, r15
0x18000a953  call    cs:__imp_PuDbgPrint
0x18000a959  mov     ecx, 3E8h; dwMilliseconds
0x18000a95e  call    cs:__imp_Sleep
0x18000a964  inc     ebx
0x18000a966  cmp     cs:?g_dwRefCount@@3KA, esi; ulong g_dwRefCount
0x18000a96c  ja      short loc_18000A922
0x18000a96e  call    ?ShutDownObjects@CADMCOMW@@SAXXZ; CADMCOMW::ShutDownObjects(void)
0x18000a973  test    byte ptr cs:g_dwDebugFlags, bpl
0x18000a97a  jz      short loc_18000A9A1
0x18000a97c  mov     rcx, cs:g_pDebug
0x18000a983  lea     rax, aTerminatecomad_5; "[TerminateComAdmindata] Terminated all "...
0x18000a98a  mov     r9, r14
0x18000a98d  mov     [rsp+78h+var_58], rax
0x18000a992  mov     r8d, 152h
0x18000a998  mov     rdx, r15
0x18000a99b  call    cs:__imp_PuDbgPrint
0x18000a9a1  mov     rcx, cs:?g_pAboSink@@3PEAVCAboSink@@EA; Block
0x18000a9a8  test    rcx, rcx
0x18000a9ab  jz      short loc_18000A9B9
0x18000a9ad  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a9b2  mov     cs:?g_pAboSink@@3PEAVCAboSink@@EA, rsi; CAboSink * g_pAboSink
0x18000a9b9  mov     rcx, cs:?s_pAboWrapper@CADMCOMW@@0PEAVIAboWrapper@@EA; IAboWrapper * CADMCOMW::s_pAboWrapper
0x18000a9c0  test    rcx, rcx
0x18000a9c3  jz      short loc_18000A9DE
0x18000a9c5  mov     rax, [rcx]
0x18000a9c8  mov     rax, [rax+10h]
0x18000a9cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9d1  mov     cs:?s_pAboWrapper@CADMCOMW@@0PEAVIAboWrapper@@EA, rsi; IAboWrapper * CADMCOMW::s_pAboWrapper
0x18000a9d8  call    cs:__imp_?TerminateAboCompatibilityLayer@@YAXXZ; TerminateAboCompatibilityLayer(void)
0x18000a9de  test    byte ptr cs:g_dwDebugFlags, bpl
0x18000a9e5  jz      short loc_18000AA0C
0x18000a9e7  mov     rcx, cs:g_pDebug
0x18000a9ee  lea     rax, aTerminatecomad_11; "[TerminateComAdmindata] Terminated ABO "...
0x18000a9f5  mov     r9, r14
0x18000a9f8  mov     [rsp+78h+var_58], rax
0x18000a9fd  mov     r8d, 156h
0x18000aa03  mov     rdx, r15
0x18000aa06  call    cs:__imp_PuDbgPrint
0x18000aa0c  lock dec cs:?g_AclCache@@3VCAdminAclCache@@A; CAdminAclCache g_AclCache
0x18000aa13  lea     rcx, ?g_AclCache@@3VCAdminAclCache@@A; this
0x18000aa1a  call    ?Flush@CAdminAclCache@@QEAAJXZ; CAdminAclCache::Flush(void)
0x18000aa1f  call    ?TerminateObjectList@CADMCOMW@@SAXXZ; CADMCOMW::TerminateObjectList(void)
0x18000aa24  test    byte ptr cs:g_dwDebugFlags, bpl
0x18000aa2b  jz      short loc_18000AA52
0x18000aa2d  mov     rcx, cs:g_pDebug
0x18000aa34  lea     rax, aTerminatecomad_7; "[TerminateComAdmindata] Terminated ABO "...
0x18000aa3b  mov     r9, r14
0x18000aa3e  mov     [rsp+78h+var_58], rax
0x18000aa43  mov     r8d, 15Eh
0x18000aa49  mov     rdx, r15
0x18000aa4c  call    cs:__imp_PuDbgPrint
0x18000aa52  mov     rdx, cs:?g_pcCom@@3PEAUIMDCOM3@@EA; IMDCOM3 * g_pcCom
0x18000aa59  test    rdx, rdx
0x18000aa5c  jz      loc_18000AB6F
0x18000aa62  mov     rcx, cs:?g_pEtwCoAdminTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwCoAdminTracer
0x18000aa69  cmp     [rcx+8], esi
0x18000aa6c  jz      short loc_18000AA9A
0x18000aa6e  test    byte ptr [rcx+28h], 2
0x18000aa72  jz      short loc_18000AA9A
0x18000aa74  cmp     dword ptr [rcx+2Ch], 4
0x18000aa78  jb      short loc_18000AA9A
0x18000aa7a  xor     r9d, r9d
0x18000aa7d  mov     [rsp+78h+var_58], rsi
0x18000aa82  lea     rdx, IISAdminShutdownGuid
0x18000aa89  lea     r8d, [r9+10h]
0x18000aa8d  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ; CEtwTracer::EtwTraceEvent(_GUID const *,ulong,...)
0x18000aa93  mov     rdx, cs:?g_pcCom@@3PEAUIMDCOM3@@EA; IMDCOM3 * g_pcCom
0x18000aa9a  mov     rax, [rdx]
0x18000aa9d  mov     rcx, rdx
0x18000aaa0  mov     rax, [rax+28h]
0x18000aaa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aaa9  test    byte ptr cs:g_dwDebugFlags, bpl
0x18000aab0  jz      short loc_18000AADB
0x18000aab2  mov     rcx, cs:g_pDebug
0x18000aab9  mov     r9, r14
0x18000aabc  mov     [rsp+78h+var_50], eax
0x18000aac0  mov     r8d, 170h
0x18000aac6  lea     rax, aTerminatecomad_0; "[TerminateComAdmindata] Shutdown metada"...
0x18000aacd  mov     rdx, r15
0x18000aad0  mov     [rsp+78h+var_58], rax
0x18000aad5  call    cs:__imp_PuDbgPrint
0x18000aadb  mov     rcx, cs:?g_pcCom@@3PEAUIMDCOM3@@EA; IMDCOM3 * g_pcCom
0x18000aae2  xor     edx, edx
0x18000aae4  mov     rax, [rcx]
0x18000aae7  mov     rax, [rax+20h]
0x18000aaeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aaf0  test    byte ptr cs:g_dwDebugFlags, bpl
0x18000aaf7  mov     edi, eax
0x18000aaf9  jz      short loc_18000AB24
0x18000aafb  mov     rcx, cs:g_pDebug
0x18000ab02  mov     r9, r14
0x18000ab05  mov     [rsp+78h+var_50], eax
0x18000ab09  mov     r8d, 174h
0x18000ab0f  lea     rax, aTerminatecomad_12; "[TerminateComAdmindata] Terminated meta"...
0x18000ab16  mov     rdx, r15
0x18000ab19  mov     [rsp+78h+var_58], rax
0x18000ab1e  call    cs:__imp_PuDbgPrint
0x18000ab24  mov     rcx, cs:?g_pcCom@@3PEAUIMDCOM3@@EA; IMDCOM3 * g_pcCom
0x18000ab2b  mov     rax, [rcx]
0x18000ab2e  mov     rax, [rax+10h]
0x18000ab32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab37  mov     rcx, cs:?g_pEtwCoAdminTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwCoAdminTracer
0x18000ab3e  mov     cs:?g_pcCom@@3PEAUIMDCOM3@@EA, rsi; IMDCOM3 * g_pcCom
0x18000ab45  cmp     [rcx+8], esi
0x18000ab48  jz      short loc_18000AB6F
0x18000ab4a  test    byte ptr [rcx+28h], 2
0x18000ab4e  jz      short loc_18000AB6F
0x18000ab50  cmp     dword ptr [rcx+2Ch], 4
0x18000ab54  jb      short loc_18000AB6F
0x18000ab56  xor     r9d, r9d
0x18000ab59  mov     [rsp+78h+var_58], rsi
0x18000ab5e  lea     rdx, IISAdminShutdownGuid
0x18000ab65  lea     r8d, [r9+11h]
0x18000ab69  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ; CEtwTracer::EtwTraceEvent(_GUID const *,ulong,...)
0x18000ab6f  mov     eax, cs:dword_1800160F4
0x18000ab75  test    byte ptr cs:g_dwDebugFlags, bpl
0x18000ab7c  jz      short loc_18000ABA7
0x18000ab7e  mov     rcx, cs:g_pDebug
0x18000ab85  lea     rax, aTerminatecomad_4; "[TerminateComAdmindata] Done with hr = "...
0x18000ab8c  mov     [rsp+78h+var_50], edi
0x18000ab90  mov     r9, r14
0x18000ab93  mov     r8d, 188h
0x18000ab99  mov     [rsp+78h+var_58], rax
0x18000ab9e  mov     rdx, r15
0x18000aba1  call    cs:__imp_PuDbgPrint
0x18000aba7  mov     eax, edi
0x18000aba9  add     rsp, 48h
0x18000abad  pop     r15
0x18000abaf  pop     r14
0x18000abb1  pop     rdi
0x18000abb2  pop     rsi
0x18000abb3  pop     rbp
0x18000abb4  pop     rbx
0x18000abb5  retn
```
