# CCscWmiPinMethod::_Execute(IWbemServices *,IWbemContext *,IWbemObjectSink *,long,IWbemClassObject *,IOfflineFilesCache *)

- ea: `0x18001a490`
- end: `0x18001a7ec`
- name: `?_Execute@CCscWmiPinMethod@@UEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemObjectSink@@JPEAUIWbemClassObject@@PEAUIOfflineFilesCache@@@Z`
- size: `860`
- prototype: `__int64 __fastcall(CCscWmiPinMethod *this, struct IWbemServices *, struct IWbemContext *, struct IWbemObjectSink *, int, struct IWbemClassObject *, struct IOfflineFilesCache *)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800084e0`
- `0x180009864`
- `0x18000f5cc`
- `0x180014068`
- `0x1800140c8`
- `0x1800183b0`
- `0x1800183f0`
- `0x180018440`
- `0x1800185b4`
- `0x180018ac8`
- `0x180019708`
- `0x18001a490`
- `0x18001bb28`
- `0x18001c0a0`
- `0x18002a8a8`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001a575`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001a575`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a7e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a7e1`

## string_xrefs

- `0x18001a500`: `Paths`

## pseudocode

```c
__int64 __fastcall CCscWmiPinMethod::_Execute(
        CCscWmiPinMethod *this,
        struct IWbemServices *a2,
        struct IWbemContext *a3,
        struct IWbemObjectSink *a4,
        int a5,
        struct IWbemClassObject *a6,
        struct IOfflineFilesCache *a7)
{
  const wchar_t *v11; // rsi
  const wchar_t *v12; // r9
  const unsigned __int16 *v13; // rdx
  int v14; // r8d
  int Error; // ebx
  UstVarLib *v16; // rcx
  HANDLE EventW; // rdi
  int v19; // eax
  CCscWmiMethod *v20; // rcx
  void *v21; // r15
  struct IOfflineFilesCacheVtbl *lpVtbl; // r10
  unsigned int v23; // eax
  void *v24; // rdx
  CCscWmiMethod *v25; // rcx
  __int64 v26; // rdx
  unsigned int v27; // [rsp+50h] [rbp-B0h] BYREF
  struct IOfflineFilesSyncProgress *v28; // [rsp+58h] [rbp-A8h] BYREF
  void *lpMem; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v30; // [rsp+68h] [rbp-98h] BYREF
  int v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+78h] [rbp-88h]
  _BYTE v33[8]; // [rsp+80h] [rbp-80h] BYREF
  __int16 v34; // [rsp+88h] [rbp-78h]
  _BYTE v35[8]; // [rsp+C0h] [rbp-40h] BYREF
  int v36; // [rsp+C8h] [rbp-38h]
  struct tagVARIANT v37; // [rsp+100h] [rbp+0h] BYREF

  v11 = L"Pin";
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    v12 = L"Pin";
    if ( !*((_DWORD *)this + 16) )
      v12 = L"Unpin";
    WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 71, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids, v12);
  }
  CCscWmiMethodParam::CCscWmiMethodParam((CCscWmiMethodParam *)&v37, L"Paths");
  CCscWmiMethodParam::CCscWmiMethodParam((CCscWmiMethodParam *)v35, v13, v14);
  CCscWmiMethodParam::CCscWmiMethodParam((CCscWmiMethodParam *)v33, L"Deep", 0);
  Error = CCscWmiMethodParam::Query((CCscWmiMethodParam *)&v37, a6);
  if ( Error >= 0 )
  {
    Error = CCscWmiMethodParam::Query((CCscWmiMethodParam *)v35, a6);
    if ( Error >= 0 )
    {
      Error = CCscWmiMethodParam::Query((CCscWmiMethodParam *)v33, a6);
      if ( Error >= 0 )
      {
        EventW = CreateEventW(0, 1, 0, 0);
        if ( !EventW )
        {
          Error = UstVarLib::ResultFromLastError(v16);
          goto LABEL_11;
        }
        v28 = 0;
        v19 = CCscWmiSyncProgress::CreateInstance(a2, a3, a4, EventW, &v28);
        Error = v19;
        if ( v19 < 0 )
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
            WPP_SF_d(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              74,
              WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids,
              (unsigned int)v19);
          goto LABEL_34;
        }
        v30 = 0;
        v31 = -1;
        v32 = 0;
        lpMem = 0;
        v27 = 0;
        Error = CCscWmiMethod::_PathArrayFromArrayVariant(v20, &v37, &v30, (const unsigned __int16 ***)&lpMem, &v27);
        if ( Error < 0 )
        {
LABEL_30:
          ((void (__fastcall *)(struct IOfflineFilesSyncProgress *))v28->lpVtbl->Release)(v28);
          CVarCvtBuffer::~CVarCvtBuffer((CVarCvtBuffer *)&v30);
LABEL_34:
          CloseHandle(EventW);
          goto LABEL_11;
        }
        v21 = lpMem;
        lpVtbl = a7->lpVtbl;
        if ( *((_DWORD *)this + 16) )
        {
          v23 = ((__int64 (__fastcall *)(struct IOfflineFilesCache *, _QWORD, void *, _QWORD, bool, int, int, struct IOfflineFilesSyncProgress *))lpVtbl->Pin)(
                  a7,
                  0,
                  lpMem,
                  v27,
                  v34 == -1,
                  1,
                  v36,
                  v28);
          Error = v23;
          v25 = (CCscWmiMethod *)WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) == 0 )
          {
            goto LABEL_27;
          }
          v26 = 72;
        }
        else
        {
          v23 = ((__int64 (__fastcall *)(struct IOfflineFilesCache *, _QWORD, void *, _QWORD, bool, int, int, struct IOfflineFilesSyncProgress *))lpVtbl->Unpin)(
                  a7,
                  0,
                  lpMem,
                  v27,
                  v34 == -1,
                  1,
                  v36,
                  v28);
          Error = v23;
          v25 = (CCscWmiMethod *)WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) == 0 )
          {
            goto LABEL_27;
          }
          v26 = 73;
        }
        WPP_SF_d(*((_QWORD *)v25 + 2), v26, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids, v23);
LABEL_27:
        if ( Error >= 0 )
          Error = CCscWmiMethod::_WaitForEventAndProcessComMessages(v25, EventW);
        CscUtil_HeapFree(v21, v24);
        goto LABEL_30;
      }
    }
  }
LABEL_11:
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    if ( !*((_DWORD *)this + 16) )
      v11 = L"Unpin";
    WPP_SF_SD(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      75,
      (unsigned int)WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids,
      (_DWORD)v11,
      Error);
  }
  CCscWmiMethodParam::~CCscWmiMethodParam((CCscWmiMethodParam *)v33);
  CCscWmiMethodParam::~CCscWmiMethodParam((CCscWmiMethodParam *)v35);
  CCscWmiMethodParam::~CCscWmiMethodParam((CCscWmiMethodParam *)&v37);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18001a490  push    rbp
0x18001a492  push    rbx
0x18001a493  push    rsi
0x18001a494  push    rdi
0x18001a495  push    r12
0x18001a497  push    r13
0x18001a499  push    r14
0x18001a49b  push    r15
0x18001a49d  lea     rbp, [rsp-48h]
0x18001a4a2  sub     rsp, 148h
0x18001a4a9  mov     r15, r9
0x18001a4ac  mov     r12, r8
0x18001a4af  mov     r13, rdx
0x18001a4b2  mov     r14, rcx
0x18001a4b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a4bc  lea     rax, WPP_GLOBAL_Control
0x18001a4c3  lea     rdx, aUnpin_0; "Unpin"
0x18001a4ca  lea     rsi, aPin_0; "Pin"
0x18001a4d1  cmp     rcx, rax
0x18001a4d4  jz      short loc_18001A500
0x18001a4d6  test    dword ptr [rcx+1Ch], 4000000h
0x18001a4dd  jz      short loc_18001A500
0x18001a4df  cmp     dword ptr [r14+40h], 0
0x18001a4e4  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001a4eb  mov     rcx, [rcx+10h]
0x18001a4ef  mov     r9, rsi
0x18001a4f2  cmovz   r9, rdx
0x18001a4f6  mov     edx, 47h ; 'G'
0x18001a4fb  call    WPP_SF_S
0x18001a500  lea     rdx, CSCWMI_STR_PARAM_PATHS; "Paths"
0x18001a507  lea     rcx, [rbp+80h+var_80]; this
0x18001a50b  call    ??0CCscWmiMethodParam@@QEAA@PEBG@Z; CCscWmiMethodParam::CCscWmiMethodParam(ushort const *)
0x18001a510  lea     rcx, [rbp+80h+var_C0]; this
0x18001a514  call    ??0CCscWmiMethodParam@@QEAA@PEBGJ@Z; CCscWmiMethodParam::CCscWmiMethodParam(ushort const *,long)
0x18001a519  xor     r8d, r8d; __int16
0x18001a51c  lea     rdx, CSCWMI_STR_PARAM_DEEP; "Deep"
0x18001a523  lea     rcx, [rbp+80h+var_100]; this
0x18001a527  call    ??0CCscWmiMethodParam@@QEAA@PEBGF@Z; CCscWmiMethodParam::CCscWmiMethodParam(ushort const *,short)
0x18001a52c  mov     rdi, [rbp+80h+arg_28]
0x18001a533  lea     rcx, [rbp+80h+var_80]; this
0x18001a537  mov     rdx, rdi; struct IWbemClassObject *
0x18001a53a  call    ?Query@CCscWmiMethodParam@@QEAAJPEAUIWbemClassObject@@@Z; CCscWmiMethodParam::Query(IWbemClassObject *)
0x18001a53f  mov     ebx, eax
0x18001a541  test    eax, eax
0x18001a543  js      short loc_18001A58E
0x18001a545  mov     rdx, rdi; struct IWbemClassObject *
0x18001a548  lea     rcx, [rbp+80h+var_C0]; this
0x18001a54c  call    ?Query@CCscWmiMethodParam@@QEAAJPEAUIWbemClassObject@@@Z; CCscWmiMethodParam::Query(IWbemClassObject *)
0x18001a551  mov     ebx, eax
0x18001a553  test    eax, eax
0x18001a555  js      short loc_18001A58E
0x18001a557  mov     rdx, rdi; struct IWbemClassObject *
0x18001a55a  lea     rcx, [rbp+80h+var_100]; this
0x18001a55e  call    ?Query@CCscWmiMethodParam@@QEAAJPEAUIWbemClassObject@@@Z; CCscWmiMethodParam::Query(IWbemClassObject *)
0x18001a563  mov     ebx, eax
0x18001a565  test    eax, eax
0x18001a567  js      short loc_18001A58E
0x18001a569  xor     r9d, r9d; lpName
0x18001a56c  xor     r8d, r8d; bInitialState
0x18001a56f  xor     ecx, ecx; lpEventAttributes
0x18001a571  lea     edx, [r9+1]; bManualReset
0x18001a575  call    cs:__imp_CreateEventW
0x18001a57b  mov     rdi, rax
0x18001a57e  test    rax, rax
0x18001a581  jnz     loc_18001A607
0x18001a587  call    ?ResultFromLastError@UstVarLib@@YAJXZ; UstVarLib::ResultFromLastError(void)
0x18001a58c  mov     ebx, eax
0x18001a58e  lea     r12, WPP_GLOBAL_Control
0x18001a595  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a59c  cmp     rcx, r12
0x18001a59f  jz      short loc_18001A5D6
0x18001a5a1  test    dword ptr [rcx+1Ch], 4000000h
0x18001a5a8  jz      short loc_18001A5D6
0x18001a5aa  cmp     dword ptr [r14+40h], 0
0x18001a5af  lea     rax, aUnpin_0; "Unpin"
0x18001a5b6  mov     rcx, [rcx+10h]
0x18001a5ba  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001a5c1  cmovz   rsi, rax
0x18001a5c5  mov     dword ptr [rsp+180h+var_160], ebx
0x18001a5c9  mov     r9, rsi
0x18001a5cc  mov     edx, 4Bh ; 'K'
0x18001a5d1  call    WPP_SF_SD
0x18001a5d6  lea     rcx, [rbp+80h+var_100]; this
0x18001a5da  call    ??1CCscWmiMethodParam@@QEAA@XZ; CCscWmiMethodParam::~CCscWmiMethodParam(void)
0x18001a5df  lea     rcx, [rbp+80h+var_C0]; this
0x18001a5e3  call    ??1CCscWmiMethodParam@@QEAA@XZ; CCscWmiMethodParam::~CCscWmiMethodParam(void)
0x18001a5e8  lea     rcx, [rbp+80h+var_80]; this
0x18001a5ec  call    ??1CCscWmiMethodParam@@QEAA@XZ; CCscWmiMethodParam::~CCscWmiMethodParam(void)
0x18001a5f1  mov     eax, ebx
0x18001a5f3  add     rsp, 148h
0x18001a5fa  pop     r15
0x18001a5fc  pop     r14
0x18001a5fe  pop     r13
0x18001a600  pop     r12
0x18001a602  pop     rdi
0x18001a603  pop     rsi
0x18001a604  pop     rbx
0x18001a605  pop     rbp
0x18001a606  retn
0x18001a607  lea     rax, [rsp+180h+var_128]
0x18001a60c  mov     [rsp+180h+var_128], 0
0x18001a615  mov     r9, rdi; void *
0x18001a618  mov     [rsp+180h+var_160], rax; struct IOfflineFilesSyncProgress **
0x18001a61d  mov     r8, r15; struct IWbemObjectSink *
0x18001a620  mov     rdx, r12; struct IWbemContext *
0x18001a623  mov     rcx, r13; struct IWbemServices *
0x18001a626  call    ?CreateInstance@CCscWmiSyncProgress@@SAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemObjectSink@@PEAXPEAPEAUIOfflineFilesSyncProgress@@@Z; CCscWmiSyncProgress::CreateInstance(IWbemServices *,IWbemContext *,IWbemObjectSink *,void *,IOfflineFilesSyncProgress * *)
0x18001a62b  mov     ebx, eax
0x18001a62d  test    eax, eax
0x18001a62f  js      loc_18001A7AD
0x18001a635  lea     rax, [rsp+180h+var_130]
0x18001a63a  mov     [rsp+180h+var_118], 0
0x18001a643  lea     r9, [rsp+180h+lpMem]; unsigned __int16 ***
0x18001a648  mov     [rsp+180h+var_160], rax; unsigned int *
0x18001a64d  lea     r8, [rsp+180h+var_118]; struct CVarCvtBuffer *
0x18001a652  mov     [rsp+180h+var_110], 0FFFFFFFFh
0x18001a65a  lea     rdx, [rbp+80h+var_80]; struct tagVARIANT *
0x18001a65e  mov     [rsp+180h+var_108], 0
0x18001a667  mov     [rsp+180h+lpMem], 0
0x18001a670  mov     [rsp+180h+var_130], 0
0x18001a678  call    ?_PathArrayFromArrayVariant@CCscWmiMethod@@IEAAJAEBUtagVARIANT@@AEAVCVarCvtBuffer@@PEAPEAPEBGPEAK@Z; CCscWmiMethod::_PathArrayFromArrayVariant(tagVARIANT const &,CVarCvtBuffer &,ushort const * * *,ulong *)
0x18001a67d  mov     ebx, eax
0x18001a67f  test    eax, eax
0x18001a681  js      loc_18001A789
0x18001a687  mov     rax, [rbp+80h+arg_30]
0x18001a68e  or      ecx, 0FFFFFFFFh
0x18001a691  cmp     dword ptr [r14+40h], 0
0x18001a696  mov     r9d, [rsp+180h+var_130]
0x18001a69b  mov     r15, [rsp+180h+lpMem]
0x18001a6a0  mov     r10, [rax]
0x18001a6a3  jz      short loc_18001A704
0x18001a6a5  mov     rdx, [rsp+180h+var_128]
0x18001a6aa  xor     r8d, r8d
0x18001a6ad  cmp     cx, [rbp+80h+var_F8]
0x18001a6b1  mov     rcx, rax
0x18001a6b4  mov     rax, [r10+30h]
0x18001a6b8  mov     [rsp+180h+var_148], rdx
0x18001a6bd  setz    r8b
0x18001a6c1  mov     edx, [rbp+80h+var_B8]
0x18001a6c4  mov     [rsp+180h+var_150], edx
0x18001a6c8  xor     edx, edx
0x18001a6ca  mov     [rsp+180h+var_158], 1
0x18001a6d2  mov     dword ptr [rsp+180h+var_160], r8d
0x18001a6d7  mov     r8, r15
0x18001a6da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a6df  mov     ebx, eax
0x18001a6e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a6e8  lea     r12, WPP_GLOBAL_Control
0x18001a6ef  cmp     rcx, r12
0x18001a6f2  jz      short loc_18001A771
0x18001a6f4  test    dword ptr [rcx+1Ch], 4000000h
0x18001a6fb  jz      short loc_18001A771
0x18001a6fd  mov     edx, 48h ; 'H'
0x18001a702  jmp     short loc_18001A75E
0x18001a704  xor     edx, edx
0x18001a706  mov     r8, r15
0x18001a709  cmp     cx, [rbp+80h+var_F8]
0x18001a70d  mov     rcx, [rsp+180h+var_128]
0x18001a712  mov     [rsp+180h+var_148], rcx
0x18001a717  setz    dl
0x18001a71a  mov     ecx, [rbp+80h+var_B8]
0x18001a71d  mov     [rsp+180h+var_150], ecx
0x18001a721  mov     rcx, rax
0x18001a724  mov     rax, [r10+38h]
0x18001a728  mov     [rsp+180h+var_158], 1
0x18001a730  mov     dword ptr [rsp+180h+var_160], edx
0x18001a734  xor     edx, edx
0x18001a736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a73b  mov     ebx, eax
0x18001a73d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a744  lea     r12, WPP_GLOBAL_Control
0x18001a74b  cmp     rcx, r12
0x18001a74e  jz      short loc_18001A771
0x18001a750  test    dword ptr [rcx+1Ch], 4000000h
0x18001a757  jz      short loc_18001A771
0x18001a759  mov     edx, 49h ; 'I'
0x18001a75e  mov     rcx, [rcx+10h]
0x18001a762  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001a769  mov     r9d, eax
0x18001a76c  call    WPP_SF_d
0x18001a771  test    ebx, ebx
0x18001a773  js      short loc_18001A77F
0x18001a775  mov     rdx, rdi; void *
0x18001a778  call    ?_WaitForEventAndProcessComMessages@CCscWmiMethod@@IEAAJPEAX@Z; CCscWmiMethod::_WaitForEventAndProcessComMessages(void *)
0x18001a77d  mov     ebx, eax
0x18001a77f  mov     rcx, r15; lpMem
0x18001a782  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x18001a787  jmp     short loc_18001A790
0x18001a789  lea     r12, WPP_GLOBAL_Control
0x18001a790  mov     rcx, [rsp+180h+var_128]
0x18001a795  mov     rax, [rcx]
0x18001a798  mov     rax, [rax+10h]
0x18001a79c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a7a1  lea     rcx, [rsp+180h+var_118]; this
0x18001a7a6  call    ??1CVarCvtBuffer@@QEAA@XZ; CVarCvtBuffer::~CVarCvtBuffer(void)
0x18001a7ab  jmp     short loc_18001A7DE
0x18001a7ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a7b4  lea     r12, WPP_GLOBAL_Control
0x18001a7bb  cmp     rcx, r12
0x18001a7be  jz      short loc_18001A7DE
0x18001a7c0  test    byte ptr [rcx+1Ch], 2
0x18001a7c4  jz      short loc_18001A7DE
0x18001a7c6  mov     rcx, [rcx+10h]
0x18001a7ca  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001a7d1  mov     edx, 4Ah ; 'J'
0x18001a7d6  mov     r9d, eax
0x18001a7d9  call    WPP_SF_d
0x18001a7de  mov     rcx, rdi; hObject
0x18001a7e1  call    cs:__imp_CloseHandle
0x18001a7e7  jmp     loc_18001A595
```
