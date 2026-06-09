# CCscWmiEncryptMethod::_Execute(IWbemServices *,IWbemContext *,IWbemObjectSink *,long,IWbemClassObject *,IOfflineFilesCache *)

- ea: `0x18001a2a0`
- end: `0x18001a48a`
- name: `?_Execute@CCscWmiEncryptMethod@@UEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemObjectSink@@JPEAUIWbemClassObject@@PEAUIOfflineFilesCache@@@Z`
- size: `490`
- prototype: `int(CCscWmiEncryptMethod *__hidden this, struct IWbemServices *, struct IWbemContext *, struct IWbemObjectSink *, int, struct IWbemClassObject *, struct IOfflineFilesCache *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task`

## callees

- `0x180009864`
- `0x18000f5a4`
- `0x18000f5cc`
- `0x1800183f0`
- `0x180018440`
- `0x1800185b4`
- `0x180018ac8`
- `0x180019708`
- `0x18001a2a0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001a348`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001a348`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a431`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a431`

## pseudocode

```c
__int64 __fastcall CCscWmiEncryptMethod::_Execute(
        CCscWmiEncryptMethod *this,
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
  int v15; // eax
  unsigned int v16; // eax
  struct IOfflineFilesSyncProgress *v18; // [rsp+40h] [rbp-81h] BYREF
  struct tagVARIANT v19[2]; // [rsp+50h] [rbp-71h] BYREF
  struct tagVARIANT v20[4]; // [rsp+90h] [rbp-31h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 80, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids);
  }
  CCscWmiMethodParam::CCscWmiMethodParam((CCscWmiMethodParam *)v20, L"Encrypt", -1);
  CCscWmiMethodParam::CCscWmiMethodParam((CCscWmiMethodParam *)v19, v10, v11);
  Error = CCscWmiMethodParam::Query(v20, a6);
  if ( Error >= 0 )
  {
    Error = CCscWmiMethodParam::Query(v19, a6);
    if ( Error >= 0 )
    {
      EventW = CreateEventW(0, 1, 0, 0);
      if ( EventW )
      {
        v18 = 0;
        v15 = CCscWmiSyncProgress::CreateInstance(a2, a3, a4, EventW, &v18);
        Error = v15;
        if ( v15 < 0 )
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
            WPP_SF_d(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              82,
              WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids,
              (unsigned int)v15);
        }
        else
        {
          v16 = ((__int64 (__fastcall *)(struct IOfflineFilesCache *, _QWORD, bool, _QWORD, int, struct IOfflineFilesSyncProgress *))a7->lpVtbl->Encrypt)(
                  a7,
                  0,
                  v20[0].iVal == 0xFFFF,
                  v19[0].cyVal.Lo,
                  1,
                  v18);
          Error = v16;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
          {
            WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 81, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids, v16);
          }
          ((void (__fastcall *)(struct IOfflineFilesSyncProgress *))v18->lpVtbl->Release)(v18);
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
      83,
      WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids,
      (unsigned int)Error);
  }
  CCscWmiMethodParam::~CCscWmiMethodParam((CCscWmiMethodParam *)v19);
  CCscWmiMethodParam::~CCscWmiMethodParam((CCscWmiMethodParam *)v20);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18001a2a0  push    rbp
0x18001a2a2  push    rbx
0x18001a2a3  push    rsi
0x18001a2a4  push    rdi
0x18001a2a5  push    r13
0x18001a2a7  push    r14
0x18001a2a9  push    r15
0x18001a2ab  lea     rbp, [rsp-0Fh]
0x18001a2b0  sub     rsp, 0D0h
0x18001a2b7  mov     rsi, r9
0x18001a2ba  mov     r14, r8
0x18001a2bd  mov     r15, rdx
0x18001a2c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a2c7  lea     r13, WPP_GLOBAL_Control
0x18001a2ce  cmp     rcx, r13
0x18001a2d1  jz      short loc_18001A2F1
0x18001a2d3  test    dword ptr [rcx+1Ch], 4000000h
0x18001a2da  jz      short loc_18001A2F1
0x18001a2dc  mov     rcx, [rcx+10h]
0x18001a2e0  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001a2e7  mov     edx, 50h ; 'P'
0x18001a2ec  call    WPP_SF_
0x18001a2f1  or      r8d, 0FFFFFFFFh; __int16
0x18001a2f5  lea     rdx, CSCWMI_STR_PARAM_ENCRYPT; "Encrypt"
0x18001a2fc  lea     rcx, [rbp+3Fh+var_70]; this
0x18001a300  call    ??0CCscWmiMethodParam@@QEAA@PEBGF@Z; CCscWmiMethodParam::CCscWmiMethodParam(ushort const *,short)
0x18001a305  lea     rcx, [rbp+3Fh+var_B0]; this
0x18001a309  call    ??0CCscWmiMethodParam@@QEAA@PEBGJ@Z; CCscWmiMethodParam::CCscWmiMethodParam(ushort const *,long)
0x18001a30e  mov     rdx, [rbp+3Fh+arg_28]; struct IWbemClassObject *
0x18001a312  lea     rcx, [rbp+3Fh+var_70]; this
0x18001a316  call    ?Query@CCscWmiMethodParam@@QEAAJPEAUIWbemClassObject@@@Z; CCscWmiMethodParam::Query(IWbemClassObject *)
0x18001a31b  mov     ebx, eax
0x18001a31d  test    eax, eax
0x18001a31f  js      loc_18001A437
0x18001a325  mov     rdx, [rbp+3Fh+arg_28]; struct IWbemClassObject *
0x18001a329  lea     rcx, [rbp+3Fh+var_B0]; this
0x18001a32d  call    ?Query@CCscWmiMethodParam@@QEAAJPEAUIWbemClassObject@@@Z; CCscWmiMethodParam::Query(IWbemClassObject *)
0x18001a332  mov     ebx, eax
0x18001a334  test    eax, eax
0x18001a336  js      loc_18001A437
0x18001a33c  xor     r9d, r9d; lpName
0x18001a33f  xor     r8d, r8d; bInitialState
0x18001a342  xor     ecx, ecx; lpEventAttributes
0x18001a344  lea     edx, [r9+1]; bManualReset
0x18001a348  call    cs:__imp_CreateEventW
0x18001a34e  mov     rdi, rax
0x18001a351  test    rax, rax
0x18001a354  jnz     short loc_18001A362
0x18001a356  call    ?ResultFromLastError@UstVarLib@@YAJXZ; UstVarLib::ResultFromLastError(void)
0x18001a35b  mov     ebx, eax
0x18001a35d  jmp     loc_18001A437
0x18001a362  lea     rax, [rsp+100h+var_C0]
0x18001a367  mov     [rsp+100h+var_C0], 0
0x18001a370  mov     r9, rdi; void *
0x18001a373  mov     [rsp+100h+var_E0], rax; struct IOfflineFilesSyncProgress **
0x18001a378  mov     r8, rsi; struct IWbemObjectSink *
0x18001a37b  mov     rdx, r14; struct IWbemContext *
0x18001a37e  mov     rcx, r15; struct IWbemServices *
0x18001a381  call    ?CreateInstance@CCscWmiSyncProgress@@SAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemObjectSink@@PEAXPEAPEAUIOfflineFilesSyncProgress@@@Z; CCscWmiSyncProgress::CreateInstance(IWbemServices *,IWbemContext *,IWbemObjectSink *,void *,IOfflineFilesSyncProgress * *)
0x18001a386  mov     ebx, eax
0x18001a388  test    eax, eax
0x18001a38a  js      short loc_18001A404
0x18001a38c  mov     rcx, [rbp+3Fh+arg_30]
0x18001a390  or      edx, 0FFFFFFFFh
0x18001a393  mov     r9d, [rbp+3Fh+var_A8]
0x18001a397  xor     r8d, r8d
0x18001a39a  cmp     dx, [rbp+3Fh+var_68]
0x18001a39e  mov     rdx, [rsp+100h+var_C0]
0x18001a3a3  mov     rax, [rcx]
0x18001a3a6  setz    r8b
0x18001a3aa  mov     [rsp+100h+var_D8], rdx
0x18001a3af  xor     edx, edx
0x18001a3b1  mov     dword ptr [rsp+100h+var_E0], 1
0x18001a3b9  mov     rax, [rax+48h]
0x18001a3bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3c2  mov     ebx, eax
0x18001a3c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a3cb  cmp     rcx, r13
0x18001a3ce  jz      short loc_18001A3F1
0x18001a3d0  test    dword ptr [rcx+1Ch], 4000000h
0x18001a3d7  jz      short loc_18001A3F1
0x18001a3d9  mov     rcx, [rcx+10h]
0x18001a3dd  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001a3e4  mov     edx, 51h ; 'Q'
0x18001a3e9  mov     r9d, eax
0x18001a3ec  call    WPP_SF_d
0x18001a3f1  mov     rcx, [rsp+100h+var_C0]
0x18001a3f6  mov     rax, [rcx]
0x18001a3f9  mov     rax, [rax+10h]
0x18001a3fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a402  jmp     short loc_18001A42E
0x18001a404  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a40b  cmp     rcx, r13
0x18001a40e  jz      short loc_18001A42E
0x18001a410  test    byte ptr [rcx+1Ch], 2
0x18001a414  jz      short loc_18001A42E
0x18001a416  mov     rcx, [rcx+10h]
0x18001a41a  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001a421  mov     edx, 52h ; 'R'
0x18001a426  mov     r9d, eax
0x18001a429  call    WPP_SF_d
0x18001a42e  mov     rcx, rdi; hObject
0x18001a431  call    cs:__imp_CloseHandle
0x18001a437  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a43e  cmp     rcx, r13
0x18001a441  jz      short loc_18001A464
0x18001a443  test    dword ptr [rcx+1Ch], 4000000h
0x18001a44a  jz      short loc_18001A464
0x18001a44c  mov     rcx, [rcx+10h]
0x18001a450  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001a457  mov     edx, 53h ; 'S'
0x18001a45c  mov     r9d, ebx
0x18001a45f  call    WPP_SF_d
0x18001a464  lea     rcx, [rbp+3Fh+var_B0]; this
0x18001a468  call    ??1CCscWmiMethodParam@@QEAA@XZ; CCscWmiMethodParam::~CCscWmiMethodParam(void)
0x18001a46d  lea     rcx, [rbp+3Fh+var_70]; this
0x18001a471  call    ??1CCscWmiMethodParam@@QEAA@XZ; CCscWmiMethodParam::~CCscWmiMethodParam(void)
0x18001a476  mov     eax, ebx
0x18001a478  add     rsp, 0D0h
0x18001a47f  pop     r15
0x18001a481  pop     r14
0x18001a483  pop     r13
0x18001a485  pop     rdi
0x18001a486  pop     rsi
0x18001a487  pop     rbx
0x18001a488  pop     rbp
0x18001a489  retn
```
