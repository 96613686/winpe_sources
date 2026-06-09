# CDefragEngine::FinalConstruct(void)

- ea: `0x18001a160`
- end: `0x18001a455`
- name: `?FinalConstruct@CDefragEngine@@QEAAJXZ`
- size: `757`
- prototype: `__int64 __fastcall(CDefragEngine *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x180028c84`
- `0x1800325c4`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18001727c`
- `0x180017e50`
- `0x180017ed8`
- `0x18001a160`
- `0x18001a630`
- `0x18001a890`
- `0x18001ab20`
- `0x18001ac0c`
- `0x180038c3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001a201`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001a231`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001a262`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001a201`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001a231`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001a262`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a334`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a33f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a34a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a3b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a3ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a3ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a334`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a33f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a34a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a3b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a3ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a3ee`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CDefragEngine::FinalConstruct(CDfVolumeList **this)
{
  char *EventW; // rbx
  CDfVolumeList *v3; // rsi
  CDfVolumeList *v4; // rdi
  volatile signed __int32 *v5; // r15
  __int16 v6; // ax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  unsigned int v19; // r14d
  CDfVolumeList *v21; // rcx
  struct CDfClientList *v22; // r12
  CDfClientList *v23; // rcx
  CDfVolumeList *v24; // rcx
  CDfVolumeList *v25; // rcx
  CDfVolumeList *v26; // rcx
  int LastFailureAsHRESULT; // [rsp+30h] [rbp-40h] BYREF
  __int16 v28; // [rsp+34h] [rbp-3Ch]
  __int16 v29; // [rsp+36h] [rbp-3Ah]
  struct CDfClientList *v30; // [rsp+B8h] [rbp+48h] BYREF
  struct CDfVolumeList *v31; // [rsp+C0h] [rbp+50h] BYREF
  char *v32; // [rsp+C8h] [rbp+58h]

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&LastFailureAsHRESULT,
    "CDefragEngine::FinalConstruct",
    117,
    1);
  EventW = 0;
  v3 = 0;
  v4 = 0;
  v31 = 0;
  v30 = 0;
  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_bf5248634d2b3b92b4f78ef82fe4291c_Traceguids);
  }
  LastFailureAsHRESULT = CDfVolumeList::CreateInstance(&v31);
  v5 = (volatile signed __int32 *)v31;
  v6 = 126;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_8;
  v28 = 126;
  LastFailureAsHRESULT = CDfClientList::CreateInstance(&v30);
  v6 = 127;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_8;
  v28 = 127;
  EventW = (char *)CreateEventW(0, 0, 0, 0);
  v32 = EventW;
  if ( !EventW )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v8, v7, v9, v10);
    v6 = 130;
LABEL_8:
    v29 = v6;
    goto LABEL_9;
  }
  LastFailureAsHRESULT = 0;
  v28 = 130;
  v3 = (CDfVolumeList *)CreateEventW(0, 0, 0, 0);
  if ( !v3 )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v12, v11, v13, v14);
    v6 = 133;
    goto LABEL_8;
  }
  LastFailureAsHRESULT = 0;
  v28 = 133;
  v4 = (CDfVolumeList *)CreateEventW(0, 1, 0, 0);
  if ( !v4 )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v16, v15, v17, v18);
    v6 = 136;
    goto LABEL_8;
  }
  LastFailureAsHRESULT = 0;
  v28 = 136;
  LastFailureAsHRESULT = CDefragEngine::_SetPriority(this, 0);
  v6 = 139;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_8;
  v28 = 139;
  *((_DWORD *)this + 39) = 1;
  LastFailureAsHRESULT = CDefragEngine::_RefreshVolumeList((CDefragEngine *)this, (struct CDfVolumeList *)v5);
  v6 = 144;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_8;
  v28 = 144;
  if ( v5 )
    _InterlockedAdd(v5 + 10, 1u);
  v21 = this[13];
  if ( v21 )
  {
    this[13] = 0;
    CDfVolumeList::Release(v21);
  }
  this[13] = (CDfVolumeList *)v5;
  v22 = v30;
  if ( v30 )
    _InterlockedIncrement((volatile signed __int32 *)v30 + 10);
  v23 = this[14];
  if ( v23 )
  {
    this[14] = 0;
    CDfClientList::Release(v23);
  }
  this[14] = v22;
  v24 = this[15];
  if ( (unsigned __int64)v24 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v24);
  this[15] = (CDfVolumeList *)EventW;
  EventW = 0;
  v25 = this[16];
  if ( (unsigned __int64)v25 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v25);
  this[16] = v3;
  v3 = 0;
  v26 = this[17];
  if ( (unsigned __int64)v26 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v26);
  this[17] = v4;
  v4 = 0;
LABEL_9:
  v19 = LastFailureAsHRESULT;
  if ( v30 )
    CDfClientList::Release(v30);
  if ( v5 )
    CDfVolumeList::Release((CDfVolumeList *)v5);
  if ( (unsigned __int64)v4 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v4);
  if ( (unsigned __int64)v3 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v3);
  if ( (unsigned __int64)(EventW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(EventW);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v19;
}

```

## disassembly

```asm
0x18001a160  push    rbp
0x18001a162  push    rbx
0x18001a163  push    rsi
0x18001a164  push    rdi
0x18001a165  push    r12
0x18001a167  push    r14
0x18001a169  push    r15
0x18001a16b  mov     rbp, rsp
0x18001a16e  sub     rsp, 70h
0x18001a172  mov     r14, rcx
0x18001a175  mov     r12d, 1
0x18001a17b  mov     r9d, r12d; unsigned __int16
0x18001a17e  lea     r8d, [r12+74h]; unsigned __int16
0x18001a183  lea     rdx, aCdefragengineF_0; "CDefragEngine::FinalConstruct"
0x18001a18a  lea     rcx, [rbp+var_40]; this
0x18001a18e  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001a193  nop
0x18001a194  xor     ebx, ebx
0x18001a196  xor     esi, esi
0x18001a198  xor     edi, edi
0x18001a19a  mov     [rbp+arg_10], rdi
0x18001a19e  mov     [rbp+arg_8], rdi
0x18001a1a2  lea     rax, WPP_GLOBAL_Control
0x18001a1a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a1b0  cmp     rcx, rax
0x18001a1b3  jnz     loc_18001A402
0x18001a1b9  lea     rcx, [rbp+arg_10]; struct CDfVolumeList **
0x18001a1bd  call    ?CreateInstance@CDfVolumeList@@SAJPEAPEAV1@@Z; CDfVolumeList::CreateInstance(CDfVolumeList * *)
0x18001a1c2  mov     [rbp+var_40], eax
0x18001a1c5  mov     r15, [rbp+arg_10]
0x18001a1c9  test    eax, eax
0x18001a1cb  mov     eax, 7Eh ; '~'
0x18001a1d0  js      loc_18001A2A2
0x18001a1d6  mov     [rbp+var_3C], ax
0x18001a1da  lea     rcx, [rbp+arg_8]; struct CDfClientList **
0x18001a1de  call    ?CreateInstance@CDfClientList@@SAJPEAPEAV1@@Z; CDfClientList::CreateInstance(CDfClientList * *)
0x18001a1e3  mov     [rbp+var_40], eax
0x18001a1e6  test    eax, eax
0x18001a1e8  mov     eax, 7Fh
0x18001a1ed  js      loc_18001A2A2
0x18001a1f3  mov     [rbp+var_3C], ax
0x18001a1f7  xor     r9d, r9d; lpName
0x18001a1fa  xor     r8d, r8d; bInitialState
0x18001a1fd  xor     edx, edx; bManualReset
0x18001a1ff  xor     ecx, ecx; lpEventAttributes
0x18001a201  call    cs:__imp_CreateEventW
0x18001a207  mov     rbx, rax
0x18001a20a  mov     [rbp+arg_18], rax
0x18001a20e  test    rax, rax
0x18001a211  jz      loc_18001A300
0x18001a217  mov     [rbp+var_40], 0
0x18001a21e  mov     eax, 82h
0x18001a223  mov     [rbp+var_3C], ax
0x18001a227  xor     r9d, r9d; lpName
0x18001a22a  xor     r8d, r8d; bInitialState
0x18001a22d  xor     edx, edx; bManualReset
0x18001a22f  xor     ecx, ecx; lpEventAttributes
0x18001a231  call    cs:__imp_CreateEventW
0x18001a237  mov     rsi, rax
0x18001a23a  mov     [rbp+var_50], rax
0x18001a23e  test    rax, rax
0x18001a241  jz      loc_18001A310
0x18001a247  mov     [rbp+var_40], 0
0x18001a24e  mov     eax, 85h
0x18001a253  mov     [rbp+var_3C], ax
0x18001a257  xor     r9d, r9d; lpName
0x18001a25a  xor     r8d, r8d; bInitialState
0x18001a25d  mov     edx, r12d; bManualReset
0x18001a260  xor     ecx, ecx; lpEventAttributes
0x18001a262  call    cs:__imp_CreateEventW
0x18001a268  mov     rdi, rax
0x18001a26b  mov     [rbp+var_48], rax
0x18001a26f  test    rax, rax
0x18001a272  jz      loc_18001A31F
0x18001a278  mov     [rbp+var_40], 0
0x18001a27f  mov     eax, 88h
0x18001a284  mov     [rbp+var_3C], ax
0x18001a288  xor     edx, edx
0x18001a28a  mov     rcx, r14
0x18001a28d  call    ?_SetPriority@CDefragEngine@@AEAAJW4__MIDL___MIDL_itf_dfengine_0000_0000_0003@@@Z; CDefragEngine::_SetPriority(__MIDL___MIDL_itf_dfengine_0000_0000_0003)
0x18001a292  mov     [rbp+var_40], eax
0x18001a295  test    eax, eax
0x18001a297  mov     eax, 8Bh
0x18001a29c  jns     loc_18001A429
0x18001a2a2  mov     [rbp+var_3A], ax
0x18001a2a6  mov     r14d, [rbp+var_40]
0x18001a2aa  mov     rcx, [rbp+arg_8]; this
0x18001a2ae  test    rcx, rcx
0x18001a2b1  jz      short loc_18001A2B9
0x18001a2b3  call    ?Release@CDfClientList@@QEAAKXZ; CDfClientList::Release(void)
0x18001a2b8  nop
0x18001a2b9  test    r15, r15
0x18001a2bc  jz      short loc_18001A2C7
0x18001a2be  mov     rcx, r15; this
0x18001a2c1  call    ?Release@CDfVolumeList@@QEAAKXZ; CDfVolumeList::Release(void)
0x18001a2c6  nop
0x18001a2c7  lea     rax, [rdi-1]
0x18001a2cb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001a2cf  jbe     short loc_18001A331
0x18001a2d1  lea     rax, [rsi-1]
0x18001a2d5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001a2d9  jbe     short loc_18001A33C
0x18001a2db  lea     rcx, [rbx-1]
0x18001a2df  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18001a2e3  jbe     short loc_18001A347
0x18001a2e5  lea     rcx, [rbp+var_40]; this
0x18001a2e9  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001a2ee  mov     eax, r14d
0x18001a2f1  add     rsp, 70h
0x18001a2f5  pop     r15
0x18001a2f7  pop     r14
0x18001a2f9  pop     r12
0x18001a2fb  pop     rdi
0x18001a2fc  pop     rsi
0x18001a2fd  pop     rbx
0x18001a2fe  pop     rbp
0x18001a2ff  retn
0x18001a300  call    GetLastFailureAsHRESULT
0x18001a305  nop
0x18001a306  mov     [rbp+var_40], eax
0x18001a309  mov     eax, 82h
0x18001a30e  jmp     short loc_18001A2A2
0x18001a310  call    GetLastFailureAsHRESULT
0x18001a315  mov     [rbp+var_40], eax
0x18001a318  mov     eax, 85h
0x18001a31d  jmp     short loc_18001A2A2
0x18001a31f  call    GetLastFailureAsHRESULT
0x18001a324  mov     [rbp+var_40], eax
0x18001a327  mov     eax, 88h
0x18001a32c  jmp     loc_18001A2A2
0x18001a331  mov     rcx, rdi; hObject
0x18001a334  call    cs:__imp_CloseHandle
0x18001a33a  jmp     short loc_18001A2D1
0x18001a33c  mov     rcx, rsi; hObject
0x18001a33f  call    cs:__imp_CloseHandle
0x18001a345  jmp     short loc_18001A2DB
0x18001a347  mov     rcx, rbx; hObject
0x18001a34a  call    cs:__imp_CloseHandle
0x18001a350  jmp     short loc_18001A2E5
0x18001a352  mov     [rbp+var_3C], ax
0x18001a356  test    r15, r15
0x18001a359  jz      short loc_18001A360
0x18001a35b  lock add [r15+28h], r12d
0x18001a360  mov     rcx, [r14+68h]; this
0x18001a364  test    rcx, rcx
0x18001a367  jz      short loc_18001A376
0x18001a369  mov     qword ptr [r14+68h], 0
0x18001a371  call    ?Release@CDfVolumeList@@QEAAKXZ; CDfVolumeList::Release(void)
0x18001a376  mov     [r14+68h], r15
0x18001a37a  mov     r12, [rbp+arg_8]
0x18001a37e  test    r12, r12
0x18001a381  jz      short loc_18001A389
0x18001a383  lock inc dword ptr [r12+28h]
0x18001a389  mov     rcx, [r14+70h]; this
0x18001a38d  test    rcx, rcx
0x18001a390  jz      short loc_18001A39F
0x18001a392  mov     qword ptr [r14+70h], 0
0x18001a39a  call    ?Release@CDfClientList@@QEAAKXZ; CDfClientList::Release(void)
0x18001a39f  mov     [r14+70h], r12
0x18001a3a3  mov     rcx, [r14+78h]; hObject
0x18001a3a7  lea     rax, [rcx-1]
0x18001a3ab  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001a3af  ja      short loc_18001A3B7
0x18001a3b1  call    cs:__imp_CloseHandle
0x18001a3b7  mov     [r14+78h], rbx
0x18001a3bb  xor     ebx, ebx
0x18001a3bd  mov     rcx, [r14+80h]; hObject
0x18001a3c4  lea     rax, [rcx-1]
0x18001a3c8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001a3cc  ja      short loc_18001A3D4
0x18001a3ce  call    cs:__imp_CloseHandle
0x18001a3d4  mov     [r14+80h], rsi
0x18001a3db  xor     esi, esi
0x18001a3dd  mov     rcx, [r14+88h]; hObject
0x18001a3e4  lea     rax, [rcx-1]
0x18001a3e8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001a3ec  ja      short loc_18001A3F4
0x18001a3ee  call    cs:__imp_CloseHandle
0x18001a3f4  mov     [r14+88h], rdi
0x18001a3fb  xor     edi, edi
0x18001a3fd  jmp     loc_18001A2A6
0x18001a402  test    dword ptr [rcx+1Ch], 8000000h
0x18001a409  jz      loc_18001A1B9
0x18001a40f  mov     edx, 0Bh
0x18001a414  lea     r8, WPP_bf5248634d2b3b92b4f78ef82fe4291c_Traceguids
0x18001a41b  mov     rcx, [rcx+10h]
0x18001a41f  call    WPP_SF_
0x18001a424  jmp     loc_18001A1B9
0x18001a429  mov     [rbp+var_3C], ax
0x18001a42d  mov     [r14+9Ch], r12d
0x18001a434  mov     rdx, r15; struct CDfVolumeList *
0x18001a437  mov     rcx, r14; this
0x18001a43a  call    ?_RefreshVolumeList@CDefragEngine@@AEAAJPEAVCDfVolumeList@@@Z; CDefragEngine::_RefreshVolumeList(CDfVolumeList *)
0x18001a43f  mov     [rbp+var_40], eax
0x18001a442  test    eax, eax
0x18001a444  mov     eax, 90h
0x18001a449  js      loc_18001A2A2
0x18001a44f  jmp     loc_18001A352
```
