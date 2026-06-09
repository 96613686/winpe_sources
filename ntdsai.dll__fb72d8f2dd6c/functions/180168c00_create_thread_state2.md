# create_thread_state2

- ea: `0x180168c00`
- end: `0x180169069`
- name: `create_thread_state2`
- size: `1129`
- prototype: ``
- caller_count: `5`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180037924`
- `0x1800389f0`
- `0x1800a504c`
- `0x180168aa4`
- `0x180290b34`

## callees

- `0x1800067d0`
- `0x18000b0b0`
- `0x18000bb20`
- `0x18000bb80`
- `0x18000e1d0`
- `0x18000ed84`
- `0x18000ff94`
- `0x180010510`
- `0x18001a264`
- `0x18016641c`
- `0x1801666d8`
- `0x1801667c8`
- `0x180166840`
- `0x180166a60`
- `0x1801672fc`
- `0x1801689a4`
- `0x180168c00`
- `0x18047b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180168d7b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180168d7b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180168c2e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180168c2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180168e61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180168e61`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180168df0`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180168df0`
- `RPCRT4!UuidCreate` at `0x180168ea1`
- `RPCRT4!UuidCreate` at `0x180168eb1`
- `RPCRT4!UuidCreate` at `0x180168ea1`
- `RPCRT4!UuidCreate` at `0x180168eb1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180168f0d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180168f0d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180168f07`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180168f07`
- `ntdll!EtwEventActivityIdControl` at `0x180168ec6`
- `ntdll!EtwEventActivityIdControl` at `0x180168ec6`

## pseudocode

```c
LPVOID __fastcall create_thread_state2(__int64 a1)
{
  int v1; // esi
  LPVOID Value; // rbp
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // r8
  __int64 v9; // r9
  BOOL v10; // ebx
  __int64 v12; // rbp
  __int64 v13; // rax
  __int64 v14; // rdi
  __int64 v15; // rax
  _QWORD *v16; // rax
  __int64 v17; // rdi
  __int64 v18; // rdx
  __int64 v19; // rbx
  DWORD v20; // ecx
  unsigned int v21; // eax
  DWORD CurrentThreadId; // eax
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  void (__fastcall *v26)(__int64); // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 v33; // r8
  __int64 v34; // r9
  BOOL v35; // r14d
  int v36; // edx
  int v37; // r8d
  int v38; // r9d
  _BYTE v39[88]; // [rsp+70h] [rbp-58h] BYREF
  unsigned int v40; // [rsp+D8h] [rbp+10h] BYREF

  v1 = 1;
  if ( dsaUserMode == 1 )
    return 0;
  Value = TlsGetValue(dwTSindex);
  if ( Value )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(3)
      || (unsigned int)THStateCheckForTraceOverride(v5, v4)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v5, v4)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier(v5, v4, v6, v7)
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3)) )
    {
      v10 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride(v5, v4)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier(v5, v4, v8, v9)
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 3));
      if ( !(unsigned int)THStateCheckForTraceOverride(v5, v4)
        && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 3) )
      {
        v1 = 0;
      }
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        453446015,
        3,
        3,
        v1,
        v10,
        19,
        &WPP_55164eae81f83cda967edabb4935dabf_Traceguids);
    }
    return Value;
  }
  v12 = 0;
  if ( a1 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *(_WORD *)(a1 + 2 * v13) );
    v14 = v13 + 1;
    v15 = THAlloc_(0, (int)v13 + 1, 2, 0, 0, 453446027);
    v12 = v15;
    if ( !v15 )
      return 0;
    _o_wcscpy_s(v15, v14, a1);
  }
  v16 = (_QWORD *)GrabHeap(v39);
  v17 = v16[1];
  if ( !v17 )
  {
    if ( !v12 )
      return 0;
    v18 = 453446043;
LABEL_29:
    DSFreeAux(v12, v18);
    return 0;
  }
  v19 = *v16;
  THInitQuota(*v16);
  ++*(_DWORD *)(v19 + 5544);
  v20 = dwTSindex;
  *(_DWORD *)(v19 + 5504) = *(_DWORD *)(v19 + 5544);
  *(_QWORD *)(v19 + 5480) = v17;
  *(_QWORD *)(v19 + 5496) = 0;
  if ( !TlsSetValue(v20, (LPVOID)v19) )
  {
    RecycleHeap(v19);
    if ( !v12 )
      return 0;
    v18 = 453446069;
    goto LABEL_29;
  }
  v40 = 0;
  DsNuma2GetCurrentProcessor(&v40);
  v21 = v40;
  v40 = 0;
  *(_DWORD *)(v19 + 5548) = v21 % gulDSProcessorHeaps;
  DsNuma2GetCurrentProcessor(&v40);
  *(_DWORD *)(v19 + 5552) = v40;
  *(_QWORD *)(v19 + 5592) = -1;
  CurrentThreadId = GetCurrentThreadId();
  v23 = xmmword_18051D108;
  *(_DWORD *)(v19 + 5600) = CurrentThreadId;
  v24 = xmmword_18051D118;
  *(_OWORD *)(v19 + 6024) = v23;
  v25 = xmmword_18051D128;
  *(_OWORD *)(v19 + 6040) = v24;
  *(_OWORD *)(v19 + 6056) = v25;
  UuidCreate((UUID *)(v19 + 6072));
  UuidCreate((UUID *)(v19 + 6088));
  if ( (Microsoft_Windows_Active_Directory_InstrumentationEnableBits & 2) != 0 )
    EtwEventActivityIdControl(2, v19 + 6072);
  *(_DWORD *)(v19 + 5612) &= ~0x80u;
  *(_DWORD *)(v19 + 5704) = 1033;
  *(_DWORD *)(v19 + 6128) = -1;
  *(_DWORD *)(v19 + 6232) = -1;
  *(_DWORD *)(v19 + 6236) = -1;
  *(_DWORD *)(v19 + 6308) = -1;
  *(_DWORD *)(v19 + 6272) = 0;
  GetSystemTimeAsFileTime((LPFILETIME)(v19 + 5748));
  *(_DWORD *)(v19 + 5768) = GetTickCount();
  v26 = (void (__fastcall *)(__int64))g_pfnPFNInitTHState2;
  *(_QWORD *)(v19 + 5960) = 0;
  *(_QWORD *)(v19 + 5968) = 0;
  *(_QWORD *)(v19 + 6016) = 0;
  *(_QWORD *)(v19 + 6104) = 0;
  *(_DWORD *)(v19 + 6160) = 0;
  if ( v26 )
    v26(v19);
  MapThreadState(v19);
  if ( (unsigned int)THStateCheckForTraceOverride(v28, v27)
    || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3)
    || gfTraceToSecondProvider
    && ((unsigned int)THStateCheckForTraceOverride(v30, v29)
     || (unsigned int)ThStateCheckIfTraceToSecondProvier(v30, v29, v31, v32)
     && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3)) )
  {
    v35 = gfTraceToSecondProvider
       && ((unsigned int)THStateCheckForTraceOverride(v30, v29)
        || (unsigned int)ThStateCheckIfTraceToSecondProvier(v30, v29, v33, v34)
        && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 4, 3));
    if ( !(unsigned int)THStateCheckForTraceOverride(v30, v29)
      && !(unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 4, 3) )
    {
      v1 = 0;
    }
    WPP_SF_qd_guid__guid_S(*((_QWORD *)WPP_GLOBAL_Control + 2), v36, v37, v38, v1, v35);
  }
  SetActiveThreadStateInfoDSAllocString(v19, v12);
  SetActiveThreadStateLdapDn(v19, 0);
  InsertActiveThreadList(v19);
  return (LPVOID)v19;
}

```

## disassembly

```asm
0x180168c00  push    rbx
0x180168c02  push    rbp
0x180168c03  push    rsi
0x180168c04  push    rdi
0x180168c05  push    r12
0x180168c07  push    r13
0x180168c09  push    r14
0x180168c0b  push    r15
0x180168c0d  sub     rsp, 88h
0x180168c14  mov     esi, 1
0x180168c19  mov     rbx, rcx
0x180168c1c  cmp     cs:dsaUserMode, esi
0x180168c22  jz      loc_180168DA6
0x180168c28  mov     ecx, cs:dwTSindex; dwTlsIndex
0x180168c2e  call    cs:__imp_TlsGetValue
0x180168c34  xor     r13d, r13d
0x180168c37  mov     rbp, rax
0x180168c3a  test    rax, rax
0x180168c3d  jz      loc_180168D2C
0x180168c43  lea     edi, [rsi+2]
0x180168c46  mov     ecx, edi
0x180168c48  call    IncrementWPPPerfCountersForLevel
0x180168c4d  test    eax, eax
0x180168c4f  jnz     short loc_180168CA2
0x180168c51  call    THStateCheckForTraceOverride
0x180168c56  test    eax, eax
0x180168c58  jnz     short loc_180168CA2
0x180168c5a  mov     r8d, edi
0x180168c5d  mov     edx, edi
0x180168c5f  xor     ecx, ecx
0x180168c61  call    CheckWPPLevelFlagsEnabledForProvider
0x180168c66  test    eax, eax
0x180168c68  jnz     short loc_180168CA2
0x180168c6a  mov     eax, cs:gfTraceToSecondProvider
0x180168c70  test    eax, eax
0x180168c72  jz      loc_180168D27
0x180168c78  call    THStateCheckForTraceOverride
0x180168c7d  test    eax, eax
0x180168c7f  jnz     short loc_180168CA2
0x180168c81  call    ThStateCheckIfTraceToSecondProvier
0x180168c86  test    eax, eax
0x180168c88  jz      loc_180168D27
0x180168c8e  mov     r8d, edi
0x180168c91  mov     edx, edi
0x180168c93  mov     ecx, esi
0x180168c95  call    CheckWPPLevelFlagsEnabledForProvider
0x180168c9a  test    eax, eax
0x180168c9c  jz      loc_180168D27
0x180168ca2  mov     eax, cs:gfTraceToSecondProvider
0x180168ca8  test    eax, eax
0x180168caa  jz      short loc_180168CD2
0x180168cac  call    THStateCheckForTraceOverride
0x180168cb1  test    eax, eax
0x180168cb3  jnz     short loc_180168CCE
0x180168cb5  call    ThStateCheckIfTraceToSecondProvier
0x180168cba  test    eax, eax
0x180168cbc  jz      short loc_180168CD2
0x180168cbe  mov     r8d, edi
0x180168cc1  mov     edx, edi
0x180168cc3  mov     ecx, esi
0x180168cc5  call    CheckWPPLevelFlagsEnabledForProvider
0x180168cca  test    eax, eax
0x180168ccc  jz      short loc_180168CD2
0x180168cce  mov     ebx, esi
0x180168cd0  jmp     short loc_180168CD5
0x180168cd2  mov     ebx, r13d
0x180168cd5  call    THStateCheckForTraceOverride
0x180168cda  test    eax, eax
0x180168cdc  jnz     short loc_180168CF1
0x180168cde  mov     r8d, edi
0x180168ce1  mov     edx, edi
0x180168ce3  xor     ecx, ecx
0x180168ce5  call    CheckWPPLevelFlagsEnabledForProvider
0x180168cea  test    eax, eax
0x180168cec  jnz     short loc_180168CF1
0x180168cee  mov     esi, r13d
0x180168cf1  mov     rcx, cs:WPP_GLOBAL_Control
0x180168cf8  lea     rax, WPP_55164eae81f83cda967edabb4935dabf_Traceguids
0x180168cff  mov     [rsp+0C8h+var_90], rax; LPCGUID
0x180168d04  mov     r9d, edi; int
0x180168d07  mov     [rsp+0C8h+var_98], 13h; __int16
0x180168d0e  mov     r8d, edi; int
0x180168d11  mov     [rsp+0C8h+var_A0], ebx; int
0x180168d15  mov     edx, 1B07097Fh; int
0x180168d1a  mov     rcx, [rcx+10h]; int
0x180168d1e  mov     [rsp+0C8h+var_A8], esi; int
0x180168d22  call    WPP_SF_
0x180168d27  mov     rax, rbp
0x180168d2a  jmp     short loc_180168DA8
0x180168d2c  or      r15, 0FFFFFFFFFFFFFFFFh
0x180168d30  mov     rbp, r13
0x180168d33  lea     r14d, [r15+3]
0x180168d37  test    rbx, rbx
0x180168d3a  jz      short loc_180168D81
0x180168d3c  mov     rax, r15
0x180168d3f  inc     rax
0x180168d42  cmp     [rbx+rax*2], r13w
0x180168d47  jnz     short loc_180168D3F
0x180168d49  lea     rdi, [rax+1]
0x180168d4d  mov     [rsp+0C8h+var_A0], 1B07098Bh
0x180168d55  mov     rdx, rdi
0x180168d58  mov     [rsp+0C8h+var_A8], r13d
0x180168d5d  xor     r9d, r9d
0x180168d60  mov     r8, r14
0x180168d63  xor     ecx, ecx
0x180168d65  call    THAlloc_
0x180168d6a  mov     rbp, rax
0x180168d6d  test    rax, rax
0x180168d70  jz      short loc_180168DA6
0x180168d72  mov     r8, rbx
0x180168d75  mov     rdx, rdi
0x180168d78  mov     rcx, rax
0x180168d7b  call    cs:__imp__o_wcscpy_s
0x180168d81  lea     rcx, [rsp+0C8h+var_58]
0x180168d86  call    GrabHeap
0x180168d8b  mov     rdi, [rax+8]
0x180168d8f  test    rdi, rdi
0x180168d92  jnz     short loc_180168DBC
0x180168d94  test    rbp, rbp
0x180168d97  jz      short loc_180168DA6
0x180168d99  mov     edx, 1B07099Bh
0x180168d9e  mov     rcx, rbp
0x180168da1  call    DSFreeAux
0x180168da6  xor     eax, eax
0x180168da8  add     rsp, 88h
0x180168daf  pop     r15
0x180168db1  pop     r14
0x180168db3  pop     r13
0x180168db5  pop     r12
0x180168db7  pop     rdi
0x180168db8  pop     rsi
0x180168db9  pop     rbp
0x180168dba  pop     rbx
0x180168dbb  retn
0x180168dbc  mov     rbx, [rax]
0x180168dbf  mov     rcx, rbx
0x180168dc2  call    THInitQuota
0x180168dc7  add     [rbx+15A8h], esi
0x180168dcd  mov     rdx, rbx; lpTlsValue
0x180168dd0  mov     eax, [rbx+15A8h]
0x180168dd6  mov     ecx, cs:dwTSindex; dwTlsIndex
0x180168ddc  mov     [rbx+1580h], eax
0x180168de2  mov     [rbx+1568h], rdi
0x180168de9  mov     [rbx+1578h], r13
0x180168df0  call    cs:__imp_TlsSetValue
0x180168df6  test    eax, eax
0x180168df8  jnz     short loc_180168E0E
0x180168dfa  mov     rcx, rbx
0x180168dfd  call    RecycleHeap
0x180168e02  test    rbp, rbp
0x180168e05  jz      short loc_180168DA6
0x180168e07  mov     edx, 1B0709B5h
0x180168e0c  jmp     short loc_180168D9E
0x180168e0e  lea     rcx, [rsp+0C8h+arg_8]
0x180168e16  mov     [rsp+0C8h+arg_8], r13d
0x180168e1e  call    DsNuma2GetCurrentProcessor
0x180168e23  mov     eax, [rsp+0C8h+arg_8]
0x180168e2a  lea     rcx, [rsp+0C8h+arg_8]
0x180168e32  xor     edx, edx
0x180168e34  mov     [rsp+0C8h+arg_8], r13d
0x180168e3c  div     cs:gulDSProcessorHeaps
0x180168e42  mov     [rbx+15ACh], edx
0x180168e48  call    DsNuma2GetCurrentProcessor
0x180168e4d  mov     eax, [rsp+0C8h+arg_8]
0x180168e54  mov     [rbx+15B0h], eax
0x180168e5a  mov     [rbx+15D8h], r15
0x180168e61  call    cs:__imp_GetCurrentThreadId
0x180168e67  movups  xmm0, cs:xmmword_18051D108
0x180168e6e  lea     r15, [rbx+17B8h]
0x180168e75  mov     [rbx+15E0h], eax
0x180168e7b  movups  xmm1, cs:xmmword_18051D118
0x180168e82  mov     rcx, r15; Uuid
0x180168e85  movups  xmmword ptr [rbx+1788h], xmm0
0x180168e8c  movups  xmm0, cs:xmmword_18051D128
0x180168e93  movups  xmmword ptr [rbx+1798h], xmm1
0x180168e9a  movups  xmmword ptr [rbx+17A8h], xmm0
0x180168ea1  call    cs:__imp_UuidCreate
0x180168ea7  lea     r12, [rbx+17C8h]
0x180168eae  mov     rcx, r12; Uuid
0x180168eb1  call    cs:__imp_UuidCreate
0x180168eb7  test    cs:Microsoft_Windows_Active_Directory_InstrumentationEnableBits, r14b
0x180168ebe  jz      short loc_180168ECC
0x180168ec0  mov     rdx, r15
0x180168ec3  mov     ecx, r14d
0x180168ec6  call    cs:__imp_EtwEventActivityIdControl
0x180168ecc  btr     dword ptr [rbx+15ECh], 7
0x180168ed4  lea     rcx, [rbx+1674h]; lpSystemTimeAsFileTime
0x180168edb  or      eax, 0FFFFFFFFh
0x180168ede  mov     dword ptr [rbx+1648h], 409h
0x180168ee8  mov     [rbx+17F0h], eax
0x180168eee  mov     [rbx+1858h], eax
0x180168ef4  mov     [rbx+185Ch], eax
0x180168efa  mov     [rbx+18A4h], eax
0x180168f00  mov     [rbx+1880h], r13d
0x180168f07  call    cs:__imp_GetSystemTimeAsFileTime
0x180168f0d  call    cs:__imp_GetTickCount
0x180168f13  mov     [rbx+1688h], eax
0x180168f19  mov     rax, cs:g_pfnPFNInitTHState2
0x180168f20  mov     [rbx+1748h], r13
0x180168f27  mov     [rbx+1750h], r13
0x180168f2e  mov     [rbx+1780h], r13
0x180168f35  mov     [rbx+17D8h], r13
0x180168f3c  mov     [rbx+1810h], r13d
0x180168f43  test    rax, rax
0x180168f46  jz      short loc_180168F50
0x180168f48  mov     rcx, rbx
0x180168f4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180168f50  mov     rcx, rbx
0x180168f53  call    MapThreadState
0x180168f58  call    THStateCheckForTraceOverride
0x180168f5d  mov     edi, 3
0x180168f62  lea     r14d, [rdi+1]
0x180168f66  test    eax, eax
0x180168f68  jnz     short loc_180168FB4
0x180168f6a  mov     r8d, edi
0x180168f6d  mov     edx, r14d
0x180168f70  xor     ecx, ecx
0x180168f72  call    CheckWPPLevelFlagsEnabledForProvider
0x180168f77  test    eax, eax
0x180168f79  jnz     short loc_180168FB4
0x180168f7b  mov     eax, cs:gfTraceToSecondProvider
0x180168f81  test    eax, eax
0x180168f83  jz      loc_180169044
0x180168f89  call    THStateCheckForTraceOverride
0x180168f8e  test    eax, eax
0x180168f90  jnz     short loc_180168FB4
0x180168f92  call    ThStateCheckIfTraceToSecondProvier
0x180168f97  test    eax, eax
0x180168f99  jz      loc_180169044
0x180168f9f  mov     r8d, edi
0x180168fa2  mov     edx, r14d
0x180168fa5  mov     ecx, esi
0x180168fa7  call    CheckWPPLevelFlagsEnabledForProvider
0x180168fac  test    eax, eax
0x180168fae  jz      loc_180169044
0x180168fb4  mov     eax, cs:gfTraceToSecondProvider
0x180168fba  test    eax, eax
0x180168fbc  jz      short loc_180168FE6
0x180168fbe  call    THStateCheckForTraceOverride
0x180168fc3  test    eax, eax
0x180168fc5  jnz     short loc_180168FE1
0x180168fc7  call    ThStateCheckIfTraceToSecondProvier
0x180168fcc  test    eax, eax
0x180168fce  jz      short loc_180168FE6
0x180168fd0  mov     r8d, edi
0x180168fd3  mov     edx, r14d
0x180168fd6  mov     ecx, esi
0x180168fd8  call    CheckWPPLevelFlagsEnabledForProvider
0x180168fdd  test    eax, eax
0x180168fdf  jz      short loc_180168FE6
0x180168fe1  mov     r14d, esi
0x180168fe4  jmp     short loc_180168FE9
0x180168fe6  mov     r14d, r13d
0x180168fe9  call    THStateCheckForTraceOverride
0x180168fee  test    eax, eax
0x180168ff0  jnz     short loc_180169006
0x180168ff2  mov     r8d, edi
0x180168ff5  lea     edx, [rax+4]
0x180168ff8  xor     ecx, ecx
0x180168ffa  call    CheckWPPLevelFlagsEnabledForProvider
0x180168fff  test    eax, eax
0x180169001  jnz     short loc_180169006
0x180169003  mov     esi, r13d
0x180169006  mov     rax, [rbx+1558h]
0x18016900d  mov     rcx, cs:WPP_GLOBAL_Control
0x180169014  mov     [rsp+0C8h+var_68], rax
0x180169019  mov     eax, [rbx+15ACh]
0x18016901f  mov     [rsp+0C8h+var_70], r12
0x180169024  mov     rcx, [rcx+10h]
0x180169028  mov     [rsp+0C8h+var_78], r15
0x18016902d  mov     [rsp+0C8h+var_80], eax
0x180169031  mov     [rsp+0C8h+var_88], rbx
0x180169036  mov     [rsp+0C8h+var_A0], r14d
0x18016903b  mov     [rsp+0C8h+var_A8], esi
0x18016903f  call    WPP_SF_qd_guid__guid_S
0x180169044  mov     rdx, rbp
0x180169047  mov     rcx, rbx
0x18016904a  call    SetActiveThreadStateInfoDSAllocString
0x18016904f  xor     edx, edx
0x180169051  mov     rcx, rbx
0x180169054  call    SetActiveThreadStateLdapDn
0x180169059  mov     rcx, rbx
0x18016905c  call    InsertActiveThreadList
0x180169061  mov     rax, rbx
0x180169064  jmp     loc_180168DA8
```
