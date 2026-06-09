# CCscWmiSyncMethod::_Execute(IWbemServices *,IWbemContext *,IWbemObjectSink *,long,IWbemClassObject *,IOfflineFilesCache *)

- ea: `0x18001ae00`
- end: `0x18001b098`
- name: `?_Execute@CCscWmiSyncMethod@@UEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemObjectSink@@JPEAUIWbemClassObject@@PEAUIOfflineFilesCache@@@Z`
- size: `664`
- prototype: `__int64 __fastcall(CCscWmiSyncMethod *this, struct IWbemServices *, struct IWbemContext *, struct IWbemObjectSink *, int, struct IWbemClassObject *, struct IOfflineFilesCache *)`
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800084e0`
- `0x180009864`
- `0x18000f5a4`
- `0x18000f5cc`
- `0x1800183b0`
- `0x180018440`
- `0x1800185b4`
- `0x180018ac8`
- `0x180019708`
- `0x18001ae00`
- `0x18001bb28`
- `0x18001c0a0`
- `0x18002a8a8`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001aece`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001aece`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b03f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b03f`

## string_xrefs

- `0x18001ae7b`: `Paths`

## pseudocode

```c
__int64 __fastcall CCscWmiSyncMethod::_Execute(
        CCscWmiSyncMethod *this,
        struct IWbemServices *a2,
        struct IWbemContext *a3,
        struct IWbemObjectSink *a4,
        int a5,
        struct IWbemClassObject *a6,
        struct IOfflineFilesCache *a7)
{
  __int64 v10; // rcx
  const unsigned __int16 *v11; // rdx
  int v12; // r8d
  int Error; // ebx
  UstVarLib *v14; // rcx
  HANDLE EventW; // rdi
  int v16; // eax
  CCscWmiMethod *v17; // rcx
  void *v18; // rdx
  CCscWmiMethod *v19; // rcx
  unsigned int v21; // [rsp+50h] [rbp-A1h] BYREF
  void *lpMem; // [rsp+58h] [rbp-99h] BYREF
  struct IOfflineFilesSyncProgress *v23; // [rsp+60h] [rbp-91h] BYREF
  unsigned __int16 *v24; // [rsp+68h] [rbp-89h] BYREF
  int v25; // [rsp+70h] [rbp-81h]
  __int64 v26; // [rsp+78h] [rbp-79h]
  _BYTE v27[8]; // [rsp+80h] [rbp-71h] BYREF
  int v28; // [rsp+88h] [rbp-69h]
  struct tagVARIANT v29; // [rsp+C0h] [rbp-31h] BYREF

  v10 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 66, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids);
      v10 = WPP_GLOBAL_Control;
    }
    if ( (_UNKNOWN *)v10 != &WPP_GLOBAL_Control && (*(_DWORD *)(v10 + 28) & 0x4000000) != 0 )
      WPP_SF_(*(_QWORD *)(v10 + 16), 67, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids);
  }
  CCscWmiMethodParam::CCscWmiMethodParam((CCscWmiMethodParam *)&v29, L"Paths");
  CCscWmiMethodParam::CCscWmiMethodParam((CCscWmiMethodParam *)v27, v11, v12);
  Error = CCscWmiMethodParam::Query((CCscWmiMethodParam *)&v29, a6);
  if ( Error >= 0 )
  {
    Error = CCscWmiMethodParam::Query((CCscWmiMethodParam *)v27, a6);
    if ( Error >= 0 )
    {
      EventW = CreateEventW(0, 1, 0, 0);
      if ( EventW )
      {
        v23 = 0;
        v16 = CCscWmiSyncProgress::CreateInstance(a2, a3, a4, EventW, &v23);
        Error = v16;
        if ( v16 < 0 )
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
            WPP_SF_d(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              69,
              WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids,
              (unsigned int)v16);
        }
        else
        {
          v24 = 0;
          v25 = -1;
          v26 = 0;
          lpMem = 0;
          v21 = 0;
          Error = CCscWmiMethod::_PathArrayFromArrayVariant(v17, &v29, &v24, (const unsigned __int16 ***)&lpMem, &v21);
          if ( Error >= 0 )
          {
            Error = ((__int64 (__fastcall *)(struct IOfflineFilesCache *, _QWORD, void *, _QWORD, int, int, _QWORD, struct IOfflineFilesSyncProgress *, _QWORD))a7->lpVtbl->Synchronize)(
                      a7,
                      0,
                      lpMem,
                      v21,
                      1,
                      v28,
                      0,
                      v23,
                      0);
            if ( Error >= 0 )
              Error = CCscWmiMethod::_WaitForEventAndProcessComMessages(v19, EventW);
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
            {
              WPP_SF_d(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                68,
                WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids,
                (unsigned int)Error);
            }
            CscUtil_HeapFree(lpMem, v18);
          }
          ((void (__fastcall *)(struct IOfflineFilesSyncProgress *))v23->lpVtbl->Release)(v23);
          CVarCvtBuffer::~CVarCvtBuffer((CVarCvtBuffer *)&v24);
        }
        CloseHandle(EventW);
      }
      else
      {
        Error = UstVarLib::ResultFromLastError(v14);
      }
    }
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      70,
      WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids,
      (unsigned int)Error);
  }
  CCscWmiMethodParam::~CCscWmiMethodParam((CCscWmiMethodParam *)v27);
  CCscWmiMethodParam::~CCscWmiMethodParam((CCscWmiMethodParam *)&v29);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18001ae00  push    rbp
0x18001ae02  push    rbx
0x18001ae03  push    rsi
0x18001ae04  push    rdi
0x18001ae05  push    r13
0x18001ae07  push    r14
0x18001ae09  push    r15
0x18001ae0b  lea     rbp, [rsp-0Fh]
0x18001ae10  sub     rsp, 100h
0x18001ae17  mov     rsi, r9
0x18001ae1a  mov     r14, r8
0x18001ae1d  mov     r15, rdx
0x18001ae20  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ae27  lea     r13, WPP_GLOBAL_Control
0x18001ae2e  cmp     rcx, r13
0x18001ae31  jz      short loc_18001AE7B
0x18001ae33  test    dword ptr [rcx+1Ch], 4000000h
0x18001ae3a  jz      short loc_18001AE58
0x18001ae3c  mov     rcx, [rcx+10h]
0x18001ae40  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001ae47  mov     edx, 42h ; 'B'
0x18001ae4c  call    WPP_SF_
0x18001ae51  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ae58  cmp     rcx, r13
0x18001ae5b  jz      short loc_18001AE7B
0x18001ae5d  test    dword ptr [rcx+1Ch], 4000000h
0x18001ae64  jz      short loc_18001AE7B
0x18001ae66  mov     rcx, [rcx+10h]
0x18001ae6a  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001ae71  mov     edx, 43h ; 'C'
0x18001ae76  call    WPP_SF_
0x18001ae7b  lea     rdx, CSCWMI_STR_PARAM_PATHS; "Paths"
0x18001ae82  lea     rcx, [rbp+3Fh+var_70]; this
0x18001ae86  call    ??0CCscWmiMethodParam@@QEAA@PEBG@Z; CCscWmiMethodParam::CCscWmiMethodParam(ushort const *)
0x18001ae8b  lea     rcx, [rbp+3Fh+var_B0]; this
0x18001ae8f  call    ??0CCscWmiMethodParam@@QEAA@PEBGJ@Z; CCscWmiMethodParam::CCscWmiMethodParam(ushort const *,long)
0x18001ae94  mov     rdx, [rbp+3Fh+arg_28]; struct IWbemClassObject *
0x18001ae98  lea     rcx, [rbp+3Fh+var_70]; this
0x18001ae9c  call    ?Query@CCscWmiMethodParam@@QEAAJPEAUIWbemClassObject@@@Z; CCscWmiMethodParam::Query(IWbemClassObject *)
0x18001aea1  mov     ebx, eax
0x18001aea3  test    eax, eax
0x18001aea5  js      loc_18001B045
0x18001aeab  mov     rdx, [rbp+3Fh+arg_28]; struct IWbemClassObject *
0x18001aeaf  lea     rcx, [rbp+3Fh+var_B0]; this
0x18001aeb3  call    ?Query@CCscWmiMethodParam@@QEAAJPEAUIWbemClassObject@@@Z; CCscWmiMethodParam::Query(IWbemClassObject *)
0x18001aeb8  mov     ebx, eax
0x18001aeba  test    eax, eax
0x18001aebc  js      loc_18001B045
0x18001aec2  xor     r9d, r9d; lpName
0x18001aec5  xor     r8d, r8d; bInitialState
0x18001aec8  xor     ecx, ecx; lpEventAttributes
0x18001aeca  lea     edx, [r9+1]; bManualReset
0x18001aece  call    cs:__imp_CreateEventW
0x18001aed4  mov     rdi, rax
0x18001aed7  test    rax, rax
0x18001aeda  jnz     short loc_18001AEE8
0x18001aedc  call    ?ResultFromLastError@UstVarLib@@YAJXZ; UstVarLib::ResultFromLastError(void)
0x18001aee1  mov     ebx, eax
0x18001aee3  jmp     loc_18001B045
0x18001aee8  lea     rax, [rsp+130h+var_D0]
0x18001aeed  mov     [rsp+130h+var_D0], 0
0x18001aef6  mov     r9, rdi; void *
0x18001aef9  mov     [rsp+130h+var_110], rax; struct IOfflineFilesSyncProgress **
0x18001aefe  mov     r8, rsi; struct IWbemObjectSink *
0x18001af01  mov     rdx, r14; struct IWbemContext *
0x18001af04  mov     rcx, r15; struct IWbemServices *
0x18001af07  call    ?CreateInstance@CCscWmiSyncProgress@@SAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemObjectSink@@PEAXPEAPEAUIOfflineFilesSyncProgress@@@Z; CCscWmiSyncProgress::CreateInstance(IWbemServices *,IWbemContext *,IWbemObjectSink *,void *,IOfflineFilesSyncProgress * *)
0x18001af0c  mov     ebx, eax
0x18001af0e  test    eax, eax
0x18001af10  js      loc_18001B012
0x18001af16  lea     rax, [rsp+130h+var_E0]
0x18001af1b  mov     [rsp+130h+var_C8], 0
0x18001af24  lea     r9, [rsp+130h+lpMem]; unsigned __int16 ***
0x18001af29  mov     [rsp+130h+var_110], rax; unsigned int *
0x18001af2e  lea     r8, [rsp+130h+var_C8]; struct CVarCvtBuffer *
0x18001af33  mov     [rsp+130h+var_C0], 0FFFFFFFFh
0x18001af3b  lea     rdx, [rbp+3Fh+var_70]; struct tagVARIANT *
0x18001af3f  mov     [rbp+3Fh+var_B8], 0
0x18001af47  mov     [rsp+130h+lpMem], 0
0x18001af50  mov     [rsp+130h+var_E0], 0
0x18001af58  call    ?_PathArrayFromArrayVariant@CCscWmiMethod@@IEAAJAEBUtagVARIANT@@AEAVCVarCvtBuffer@@PEAPEAPEBGPEAK@Z; CCscWmiMethod::_PathArrayFromArrayVariant(tagVARIANT const &,CVarCvtBuffer &,ushort const * * *,ulong *)
0x18001af5d  mov     ebx, eax
0x18001af5f  test    eax, eax
0x18001af61  js      loc_18001AFF5
0x18001af67  mov     rdx, [rsp+130h+var_D0]
0x18001af6c  mov     rcx, [rbp+3Fh+arg_30]
0x18001af70  mov     r9d, [rsp+130h+var_E0]
0x18001af75  mov     r8, [rsp+130h+lpMem]
0x18001af7a  mov     [rsp+130h+var_F0], 0
0x18001af83  mov     rax, [rcx]
0x18001af86  mov     [rsp+130h+var_F8], rdx
0x18001af8b  mov     edx, [rbp+3Fh+var_A8]
0x18001af8e  mov     [rsp+130h+var_100], 0
0x18001af97  mov     rax, [rax+18h]
0x18001af9b  mov     [rsp+130h+var_108], edx
0x18001af9f  xor     edx, edx
0x18001afa1  mov     dword ptr [rsp+130h+var_110], 1
0x18001afa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001afae  mov     ebx, eax
0x18001afb0  test    eax, eax
0x18001afb2  js      short loc_18001AFBE
0x18001afb4  mov     rdx, rdi; void *
0x18001afb7  call    ?_WaitForEventAndProcessComMessages@CCscWmiMethod@@IEAAJPEAX@Z; CCscWmiMethod::_WaitForEventAndProcessComMessages(void *)
0x18001afbc  mov     ebx, eax
0x18001afbe  mov     rcx, cs:WPP_GLOBAL_Control
0x18001afc5  cmp     rcx, r13
0x18001afc8  jz      short loc_18001AFEB
0x18001afca  test    dword ptr [rcx+1Ch], 4000000h
0x18001afd1  jz      short loc_18001AFEB
0x18001afd3  mov     rcx, [rcx+10h]
0x18001afd7  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001afde  mov     edx, 44h ; 'D'
0x18001afe3  mov     r9d, ebx
0x18001afe6  call    WPP_SF_d
0x18001afeb  mov     rcx, [rsp+130h+lpMem]; lpMem
0x18001aff0  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x18001aff5  mov     rcx, [rsp+130h+var_D0]
0x18001affa  mov     rax, [rcx]
0x18001affd  mov     rax, [rax+10h]
0x18001b001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b006  lea     rcx, [rsp+130h+var_C8]; this
0x18001b00b  call    ??1CVarCvtBuffer@@QEAA@XZ; CVarCvtBuffer::~CVarCvtBuffer(void)
0x18001b010  jmp     short loc_18001B03C
0x18001b012  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b019  cmp     rcx, r13
0x18001b01c  jz      short loc_18001B03C
0x18001b01e  test    byte ptr [rcx+1Ch], 2
0x18001b022  jz      short loc_18001B03C
0x18001b024  mov     rcx, [rcx+10h]
0x18001b028  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001b02f  mov     edx, 45h ; 'E'
0x18001b034  mov     r9d, eax
0x18001b037  call    WPP_SF_d
0x18001b03c  mov     rcx, rdi; hObject
0x18001b03f  call    cs:__imp_CloseHandle
0x18001b045  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b04c  cmp     rcx, r13
0x18001b04f  jz      short loc_18001B072
0x18001b051  test    dword ptr [rcx+1Ch], 4000000h
0x18001b058  jz      short loc_18001B072
0x18001b05a  mov     rcx, [rcx+10h]
0x18001b05e  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001b065  mov     edx, 46h ; 'F'
0x18001b06a  mov     r9d, ebx
0x18001b06d  call    WPP_SF_d
0x18001b072  lea     rcx, [rbp+3Fh+var_B0]; this
0x18001b076  call    ??1CCscWmiMethodParam@@QEAA@XZ; CCscWmiMethodParam::~CCscWmiMethodParam(void)
0x18001b07b  lea     rcx, [rbp+3Fh+var_70]; this
0x18001b07f  call    ??1CCscWmiMethodParam@@QEAA@XZ; CCscWmiMethodParam::~CCscWmiMethodParam(void)
0x18001b084  mov     eax, ebx
0x18001b086  add     rsp, 100h
0x18001b08d  pop     r15
0x18001b08f  pop     r14
0x18001b091  pop     r13
0x18001b093  pop     rdi
0x18001b094  pop     rsi
0x18001b095  pop     rbx
0x18001b096  pop     rbp
0x18001b097  retn
```
