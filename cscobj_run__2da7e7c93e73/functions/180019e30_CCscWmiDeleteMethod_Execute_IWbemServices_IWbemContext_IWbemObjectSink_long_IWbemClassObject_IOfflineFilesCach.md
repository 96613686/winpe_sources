# CCscWmiDeleteMethod::_Execute(IWbemServices *,IWbemContext *,IWbemObjectSink *,long,IWbemClassObject *,IOfflineFilesCache *)

- ea: `0x180019e30`
- end: `0x18001a099`
- name: `?_Execute@CCscWmiDeleteMethod@@UEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemObjectSink@@JPEAUIWbemClassObject@@PEAUIOfflineFilesCache@@@Z`
- size: `617`
- prototype: `__int64 __fastcall(CCscWmiDeleteMethod *this, struct IWbemServices *, struct IWbemContext *, struct IWbemObjectSink *, int, struct IWbemClassObject *, struct IOfflineFilesCache *)`
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
- `0x180018a28`
- `0x180019708`
- `0x180019e30`
- `0x18001bb28`
- `0x18001c0a0`
- `0x18002a8a8`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180019eca`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180019eca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a08e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a08e`

## string_xrefs

- `0x180019e7f`: `Paths`

## pseudocode

```c
__int64 __fastcall CCscWmiDeleteMethod::_Execute(
        CCscWmiDeleteMethod *this,
        struct IWbemServices *a2,
        struct IWbemContext *a3,
        struct IWbemObjectSink *a4,
        int a5,
        struct IWbemClassObject *a6,
        struct IOfflineFilesCache *a7)
{
  const unsigned __int16 *v10; // rdx
  int v11; // r8d
  int Error; // ebx
  UstVarLib *v13; // rcx
  HANDLE EventW; // rdi
  int v16; // eax
  CCscWmiMethod *v17; // rcx
  unsigned int v18; // eax
  void *v19; // rdx
  CCscWmiMethod *v20; // rcx
  unsigned int v21; // [rsp+40h] [rbp-A1h] BYREF
  void *lpMem; // [rsp+48h] [rbp-99h] BYREF
  struct IOfflineFilesSimpleProgress *v23; // [rsp+50h] [rbp-91h] BYREF
  unsigned __int16 *v24; // [rsp+58h] [rbp-89h] BYREF
  int v25; // [rsp+60h] [rbp-81h]
  __int64 v26; // [rsp+68h] [rbp-79h]
  _BYTE v27[8]; // [rsp+70h] [rbp-71h] BYREF
  unsigned int v28; // [rsp+78h] [rbp-69h]
  struct tagVARIANT v29; // [rsp+B0h] [rbp-31h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 76, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids);
  }
  CCscWmiMethodParam::CCscWmiMethodParam((CCscWmiMethodParam *)&v29, L"Paths");
  CCscWmiMethodParam::CCscWmiMethodParam((CCscWmiMethodParam *)v27, v10, v11);
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
        v16 = CCscWmiSimpleProgress::CreateInstance(a2, a3, a4, EventW, &v23);
        Error = v16;
        if ( v16 < 0 )
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
            WPP_SF_d(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              78,
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
            v18 = ((__int64 (__fastcall *)(struct IOfflineFilesCache *, void *, _QWORD, _QWORD, int, struct IOfflineFilesSimpleProgress *))a7->lpVtbl->DeleteItems)(
                    a7,
                    lpMem,
                    v21,
                    v28,
                    1,
                    v23);
            Error = v18;
            v20 = (CCscWmiMethod *)WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
            {
              WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 77, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids, v18);
            }
            if ( Error >= 0 )
              Error = CCscWmiMethod::_WaitForEventAndProcessComMessages(v20, EventW);
            CscUtil_HeapFree(lpMem, v19);
          }
          ((void (__fastcall *)(struct IOfflineFilesSimpleProgress *))v23->lpVtbl->Release)(v23);
          CVarCvtBuffer::~CVarCvtBuffer((CVarCvtBuffer *)&v24);
        }
        CloseHandle(EventW);
      }
      else
      {
        Error = UstVarLib::ResultFromLastError(v13);
      }
    }
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      79,
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
0x180019e30  push    rbp
0x180019e32  push    rbx
0x180019e33  push    rsi
0x180019e34  push    rdi
0x180019e35  push    r14
0x180019e37  push    r15
0x180019e39  lea     rbp, [rsp-17h]
0x180019e3e  sub     rsp, 0F8h
0x180019e45  mov     rsi, r9
0x180019e48  mov     r14, r8
0x180019e4b  mov     r15, rdx
0x180019e4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180019e55  lea     rax, WPP_GLOBAL_Control
0x180019e5c  cmp     rcx, rax
0x180019e5f  jz      short loc_180019E7F
0x180019e61  test    dword ptr [rcx+1Ch], 4000000h
0x180019e68  jz      short loc_180019E7F
0x180019e6a  mov     rcx, [rcx+10h]
0x180019e6e  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x180019e75  mov     edx, 4Ch ; 'L'
0x180019e7a  call    WPP_SF_
0x180019e7f  lea     rdx, CSCWMI_STR_PARAM_PATHS; "Paths"
0x180019e86  lea     rcx, [rbp+3Fh+var_70]; this
0x180019e8a  call    ??0CCscWmiMethodParam@@QEAA@PEBG@Z; CCscWmiMethodParam::CCscWmiMethodParam(ushort const *)
0x180019e8f  lea     rcx, [rbp+3Fh+var_B0]; this
0x180019e93  call    ??0CCscWmiMethodParam@@QEAA@PEBGJ@Z; CCscWmiMethodParam::CCscWmiMethodParam(ushort const *,long)
0x180019e98  mov     rdx, [rbp+3Fh+arg_28]; struct IWbemClassObject *
0x180019e9c  lea     rcx, [rbp+3Fh+var_70]; this
0x180019ea0  call    ?Query@CCscWmiMethodParam@@QEAAJPEAUIWbemClassObject@@@Z; CCscWmiMethodParam::Query(IWbemClassObject *)
0x180019ea5  mov     ebx, eax
0x180019ea7  test    eax, eax
0x180019ea9  js      short loc_180019EDF
0x180019eab  mov     rdx, [rbp+3Fh+arg_28]; struct IWbemClassObject *
0x180019eaf  lea     rcx, [rbp+3Fh+var_B0]; this
0x180019eb3  call    ?Query@CCscWmiMethodParam@@QEAAJPEAUIWbemClassObject@@@Z; CCscWmiMethodParam::Query(IWbemClassObject *)
0x180019eb8  mov     ebx, eax
0x180019eba  test    eax, eax
0x180019ebc  js      short loc_180019EDF
0x180019ebe  xor     r9d, r9d; lpName
0x180019ec1  xor     r8d, r8d; bInitialState
0x180019ec4  xor     ecx, ecx; lpEventAttributes
0x180019ec6  lea     edx, [r9+1]; bManualReset
0x180019eca  call    cs:__imp_CreateEventW
0x180019ed0  mov     rdi, rax
0x180019ed3  test    rax, rax
0x180019ed6  jnz     short loc_180019F37
0x180019ed8  call    ?ResultFromLastError@UstVarLib@@YAJXZ; UstVarLib::ResultFromLastError(void)
0x180019edd  mov     ebx, eax
0x180019edf  lea     rsi, WPP_GLOBAL_Control
0x180019ee6  mov     rcx, cs:WPP_GLOBAL_Control
0x180019eed  cmp     rcx, rsi
0x180019ef0  jz      short loc_180019F13
0x180019ef2  test    dword ptr [rcx+1Ch], 4000000h
0x180019ef9  jz      short loc_180019F13
0x180019efb  mov     rcx, [rcx+10h]
0x180019eff  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x180019f06  mov     edx, 4Fh ; 'O'
0x180019f0b  mov     r9d, ebx
0x180019f0e  call    WPP_SF_d
0x180019f13  lea     rcx, [rbp+3Fh+var_B0]; this
0x180019f17  call    ??1CCscWmiMethodParam@@QEAA@XZ; CCscWmiMethodParam::~CCscWmiMethodParam(void)
0x180019f1c  lea     rcx, [rbp+3Fh+var_70]; this
0x180019f20  call    ??1CCscWmiMethodParam@@QEAA@XZ; CCscWmiMethodParam::~CCscWmiMethodParam(void)
0x180019f25  mov     eax, ebx
0x180019f27  add     rsp, 0F8h
0x180019f2e  pop     r15
0x180019f30  pop     r14
0x180019f32  pop     rdi
0x180019f33  pop     rsi
0x180019f34  pop     rbx
0x180019f35  pop     rbp
0x180019f36  retn
0x180019f37  lea     rax, [rsp+120h+var_D0]
0x180019f3c  mov     [rsp+120h+var_D0], 0
0x180019f45  mov     r9, rdi; void *
0x180019f48  mov     [rsp+120h+var_100], rax; struct IOfflineFilesSimpleProgress **
0x180019f4d  mov     r8, rsi; struct IWbemObjectSink *
0x180019f50  mov     rdx, r14; struct IWbemContext *
0x180019f53  mov     rcx, r15; struct IWbemServices *
0x180019f56  call    ?CreateInstance@CCscWmiSimpleProgress@@SAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemObjectSink@@PEAXPEAPEAUIOfflineFilesSimpleProgress@@@Z; CCscWmiSimpleProgress::CreateInstance(IWbemServices *,IWbemContext *,IWbemObjectSink *,void *,IOfflineFilesSimpleProgress * *)
0x180019f5b  mov     ebx, eax
0x180019f5d  test    eax, eax
0x180019f5f  js      loc_18001A05A
0x180019f65  lea     rax, [rsp+120h+var_E0]
0x180019f6a  mov     [rsp+120h+var_C8], 0
0x180019f73  lea     r9, [rsp+120h+lpMem]; unsigned __int16 ***
0x180019f78  mov     [rsp+120h+var_100], rax; unsigned int *
0x180019f7d  lea     r8, [rsp+120h+var_C8]; struct CVarCvtBuffer *
0x180019f82  mov     [rsp+120h+var_C0], 0FFFFFFFFh
0x180019f8a  lea     rdx, [rbp+3Fh+var_70]; struct tagVARIANT *
0x180019f8e  mov     [rbp+3Fh+var_B8], 0
0x180019f96  mov     [rsp+120h+lpMem], 0
0x180019f9f  mov     [rsp+120h+var_E0], 0
0x180019fa7  call    ?_PathArrayFromArrayVariant@CCscWmiMethod@@IEAAJAEBUtagVARIANT@@AEAVCVarCvtBuffer@@PEAPEAPEBGPEAK@Z; CCscWmiMethod::_PathArrayFromArrayVariant(tagVARIANT const &,CVarCvtBuffer &,ushort const * * *,ulong *)
0x180019fac  mov     ebx, eax
0x180019fae  test    eax, eax
0x180019fb0  js      loc_18001A036
0x180019fb6  mov     rdx, [rsp+120h+var_D0]
0x180019fbb  mov     rcx, [rbp+3Fh+arg_30]
0x180019fbf  mov     r9d, [rbp+3Fh+var_A8]
0x180019fc3  mov     r8d, [rsp+120h+var_E0]
0x180019fc8  mov     [rsp+120h+var_F8], rdx
0x180019fcd  mov     rax, [rcx]
0x180019fd0  mov     rdx, [rsp+120h+lpMem]
0x180019fd5  mov     dword ptr [rsp+120h+var_100], 1
0x180019fdd  mov     rax, [rax+20h]
0x180019fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fe6  mov     ebx, eax
0x180019fe8  mov     rcx, cs:WPP_GLOBAL_Control
0x180019fef  lea     rsi, WPP_GLOBAL_Control
0x180019ff6  cmp     rcx, rsi
0x180019ff9  jz      short loc_18001A01C
0x180019ffb  test    dword ptr [rcx+1Ch], 4000000h
0x18001a002  jz      short loc_18001A01C
0x18001a004  mov     rcx, [rcx+10h]
0x18001a008  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001a00f  mov     edx, 4Dh ; 'M'
0x18001a014  mov     r9d, eax
0x18001a017  call    WPP_SF_d
0x18001a01c  test    ebx, ebx
0x18001a01e  js      short loc_18001A02A
0x18001a020  mov     rdx, rdi; void *
0x18001a023  call    ?_WaitForEventAndProcessComMessages@CCscWmiMethod@@IEAAJPEAX@Z; CCscWmiMethod::_WaitForEventAndProcessComMessages(void *)
0x18001a028  mov     ebx, eax
0x18001a02a  mov     rcx, [rsp+120h+lpMem]; lpMem
0x18001a02f  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x18001a034  jmp     short loc_18001A03D
0x18001a036  lea     rsi, WPP_GLOBAL_Control
0x18001a03d  mov     rcx, [rsp+120h+var_D0]
0x18001a042  mov     rax, [rcx]
0x18001a045  mov     rax, [rax+10h]
0x18001a049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a04e  lea     rcx, [rsp+120h+var_C8]; this
0x18001a053  call    ??1CVarCvtBuffer@@QEAA@XZ; CVarCvtBuffer::~CVarCvtBuffer(void)
0x18001a058  jmp     short loc_18001A08B
0x18001a05a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a061  lea     rsi, WPP_GLOBAL_Control
0x18001a068  cmp     rcx, rsi
0x18001a06b  jz      short loc_18001A08B
0x18001a06d  test    byte ptr [rcx+1Ch], 2
0x18001a071  jz      short loc_18001A08B
0x18001a073  mov     rcx, [rcx+10h]
0x18001a077  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001a07e  mov     edx, 4Eh ; 'N'
0x18001a083  mov     r9d, eax
0x18001a086  call    WPP_SF_d
0x18001a08b  mov     rcx, rdi; hObject
0x18001a08e  call    cs:__imp_CloseHandle
0x18001a094  jmp     loc_180019EE6
```
