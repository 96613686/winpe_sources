# CFLACBytestreamHandler::BeginCreateObject(IMFByteStream *,ushort const *,ulong,IPropertyStore *,IUnknown * *,IMFAsyncCallback *,IUnknown *)

- ea: `0x18001fff0`
- end: `0x180020235`
- name: `?BeginCreateObject@CFLACBytestreamHandler@@UEAAJPEAUIMFByteStream@@PEBGKPEAUIPropertyStore@@PEAPEAUIUnknown@@PEAUIMFAsyncCallback@@PEAU4@@Z`
- size: `581`
- prototype: `int(CFLACBytestreamHandler *__hidden this, struct IMFByteStream *, const unsigned __int16 *, unsigned int, struct IPropertyStore *, struct IUnknown **, struct IMFAsyncCallback *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180016e48`
- `0x180017e64`
- `0x18001fff0`
- `0x180020398`
- `0x180020484`
- `0x180021588`
- `0x1800221ec`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800200ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020204`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800200ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020204`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020046`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020046`
- `MFPlat!MFCreateAsyncResult` at `0x180020179`
- `MFPlat!MFCreateAsyncResult` at `0x180020179`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CFLACBytestreamHandler::BeginCreateObject(
        CFLACBytestreamHandler *this,
        struct IMFByteStream *a2,
        const unsigned __int16 *a3,
        char a4,
        struct IPropertyStore *a5,
        struct IUnknown **a6,
        struct IMFAsyncCallback *pCallback,
        struct IUnknown *punkState)
{
  struct IMFAsyncCallback *v11; // rdi
  struct _RTL_CRITICAL_SECTION *v12; // rsi
  int v13; // ecx
  __int64 v14; // rdx
  CFLACSource *v16; // rbx
  int v17; // ecx
  __int64 v18; // rdx
  struct IUnknown *v19; // r9
  unsigned int v20; // ebx
  IMFAsyncResult *ppAsyncResult; // [rsp+30h] [rbp-30h] BYREF
  struct CFLACSource *v22[5]; // [rsp+38h] [rbp-28h] BYREF
  HRESULT Instance; // [rsp+90h] [rbp+30h] BYREF
  __int64 v24; // [rsp+98h] [rbp+38h] BYREF

  Instance = 0;
  v11 = (struct IMFAsyncCallback *)((char *)this - 8);
  v22[2] = (CFLACBytestreamHandler *)((char *)this - 8);
  v22[3] = (struct CFLACSource *)&Instance;
  ppAsyncResult = 0;
  v24 = 0;
  v22[0] = 0;
  v12 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
  v22[1] = (CFLACBytestreamHandler *)((char *)this + 64);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( a2 )
  {
    if ( !pCallback )
    {
      Instance = -2147467261;
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_28;
      v14 = 12;
      goto LABEL_4;
    }
    if ( (a4 & 1) == 0 )
    {
      LeaveCriticalSection(v12);
      ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(&v24);
      ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(&ppAsyncResult);
      return 2147942487LL;
    }
    if ( a6 )
      *a6 = 0;
    Instance = CFLACSource::CreateInstance(v22);
    v16 = v22[0];
    if ( Instance < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_26;
      v18 = 13;
      goto LABEL_15;
    }
    if ( (**(int (__fastcall ***)(struct CFLACSource *, GUID *, __int64 *))v22[0])(
           v22[0],
           &IID_IMFTelemetryComponent,
           &v24) >= 0 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 32LL))(v24, *((_QWORD *)this + 7));
    Instance = MFCreateAsyncResult(0, pCallback, punkState, &ppAsyncResult);
    if ( Instance >= 0 )
    {
      Instance = CFLACSource::BeginOpen(v16, a2, v11, v19);
      if ( Instance >= 0 )
      {
        v11[6].lpVtbl = (struct IMFAsyncCallbackVtbl *)v16;
        (*(void (__fastcall **)(CFLACSource *))(*(_QWORD *)v16 + 8LL))(v16);
        if ( *((IMFAsyncResult **)this + 6) != ppAsyncResult )
          ATL::AtlComPtrAssign((struct IUnknown **)this + 6, (struct IUnknown *)ppAsyncResult);
        goto LABEL_26;
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v18 = 15;
        goto LABEL_15;
      }
    }
    else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v18 = 14;
LABEL_15:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, &WPP_4cd7cbc1e4fa3d19ea6227db4bb61af4_Traceguids, v11, v17);
    }
LABEL_26:
    if ( v16 )
      (*(void (__fastcall **)(CFLACSource *))(*(_QWORD *)v16 + 16LL))(v16);
    goto LABEL_28;
  }
  Instance = -2147467261;
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v14 = 11;
LABEL_4:
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_4cd7cbc1e4fa3d19ea6227db4bb61af4_Traceguids, v11, v13);
  }
LABEL_28:
  v20 = Instance;
  LeaveCriticalSection(v12);
  ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(&v24);
  ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(&ppAsyncResult);
  return v20;
}

```

## disassembly

```asm
0x18001fff0  mov     [rsp-28h+arg_10], rbx
0x18001fff5  push    rbp
0x18001fff6  push    rsi
0x18001fff7  push    rdi
0x18001fff8  push    r12
0x18001fffa  push    r14
0x18001fffc  mov     rbp, rsp
0x18001ffff  sub     rsp, 60h
0x180020003  mov     ebx, r9d
0x180020006  mov     r12, rdx
0x180020009  mov     r14, rcx
0x18002000c  mov     [rbp+arg_0], 0
0x180020013  lea     rdi, [rcx-8]
0x180020017  mov     [rbp+var_18], rdi
0x18002001b  lea     rax, [rbp+arg_0]
0x18002001f  mov     [rbp+var_10], rax
0x180020023  mov     [rbp+ppAsyncResult], 0
0x18002002b  mov     [rbp+arg_8], 0
0x180020033  mov     [rbp+var_28], 0
0x18002003b  lea     rsi, [rcx+40h]
0x18002003f  mov     [rbp+var_20], rsi
0x180020043  mov     rcx, rsi; lpCriticalSection
0x180020046  call    cs:__imp_EnterCriticalSection
0x18002004c  nop
0x18002004d  test    r12, r12
0x180020050  jnz     short loc_18002008F
0x180020052  mov     ecx, 80004003h
0x180020057  mov     [rbp+arg_0], ecx
0x18002005a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002005f  cmp     al, 1
0x180020061  jb      loc_1800201FE
0x180020067  lea     edx, [r12+0Bh]
0x18002006c  mov     [rsp+60h+var_40], ecx
0x180020070  mov     r9, rdi
0x180020073  lea     r8, WPP_4cd7cbc1e4fa3d19ea6227db4bb61af4_Traceguids
0x18002007a  mov     rcx, cs:WPP_GLOBAL_Control
0x180020081  mov     rcx, [rcx+10h]
0x180020085  call    WPP_SF_qd
0x18002008a  jmp     loc_1800201FE
0x18002008f  cmp     [rbp+pCallback], 0
0x180020094  jnz     short loc_1800200B2
0x180020096  mov     ecx, 80004003h
0x18002009b  mov     [rbp+arg_0], ecx
0x18002009e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800200a3  cmp     al, 1
0x1800200a5  jb      loc_1800201FE
0x1800200ab  mov     edx, 0Ch
0x1800200b0  jmp     short loc_18002006C
0x1800200b2  test    bl, 1
0x1800200b5  jnz     short loc_1800200DF
0x1800200b7  mov     rcx, rsi; lpCriticalSection
0x1800200ba  call    cs:__imp_LeaveCriticalSection
0x1800200c0  nop
0x1800200c1  lea     rcx, [rbp+arg_8]
0x1800200c5  call    ??1?$CComPtrBase@UIMFTelemetryComponent@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(void)
0x1800200ca  nop
0x1800200cb  lea     rcx, [rbp+ppAsyncResult]
0x1800200cf  call    ??1?$CComPtrBase@UIMFTelemetryComponent@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(void)
0x1800200d4  nop
0x1800200d5  mov     eax, 80070057h
0x1800200da  jmp     loc_180020221
0x1800200df  mov     rax, [rbp+arg_28]
0x1800200e3  test    rax, rax
0x1800200e6  jz      short loc_1800200EF
0x1800200e8  mov     qword ptr [rax], 0
0x1800200ef  lea     rcx, [rbp+var_28]; struct CFLACSource **
0x1800200f3  call    ?CreateInstance@CFLACSource@@SAJPEAPEAV1@@Z; CFLACSource::CreateInstance(CFLACSource * *)
0x1800200f8  mov     ecx, eax
0x1800200fa  mov     [rbp+arg_0], eax
0x1800200fd  mov     rbx, [rbp+var_28]
0x180020101  test    eax, eax
0x180020103  jns     short loc_18002013A
0x180020105  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002010a  cmp     al, 1
0x18002010c  jb      loc_1800201EA
0x180020112  mov     edx, 0Dh
0x180020117  mov     [rsp+60h+var_40], ecx
0x18002011b  mov     r9, rdi
0x18002011e  lea     r8, WPP_4cd7cbc1e4fa3d19ea6227db4bb61af4_Traceguids
0x180020125  mov     rcx, cs:WPP_GLOBAL_Control
0x18002012c  mov     rcx, [rcx+10h]
0x180020130  call    WPP_SF_qd
0x180020135  jmp     loc_1800201EA
0x18002013a  mov     rax, [rbx]
0x18002013d  lea     r8, [rbp+arg_8]
0x180020141  lea     rdx, IID_IMFTelemetryComponent
0x180020148  mov     rcx, rbx
0x18002014b  mov     rax, [rax]
0x18002014e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020153  test    eax, eax
0x180020155  js      short loc_18002016B
0x180020157  mov     rcx, [rbp+arg_8]
0x18002015b  mov     rax, [rcx]
0x18002015e  mov     rdx, [r14+38h]
0x180020162  mov     rax, [rax+20h]
0x180020166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002016b  lea     r9, [rbp+ppAsyncResult]; ppAsyncResult
0x18002016f  mov     r8, [rbp+punkState]; punkState
0x180020173  mov     rdx, [rbp+pCallback]; pCallback
0x180020177  xor     ecx, ecx; punkObject
0x180020179  call    cs:__imp_MFCreateAsyncResult
0x18002017f  mov     ecx, eax
0x180020181  mov     [rbp+arg_0], eax
0x180020184  test    eax, eax
0x180020186  jns     short loc_18002019B
0x180020188  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002018d  cmp     al, 1
0x18002018f  jb      short loc_1800201EA
0x180020191  mov     edx, 0Eh
0x180020196  jmp     loc_180020117
0x18002019b  mov     r8, rdi; struct IMFAsyncCallback *
0x18002019e  mov     rdx, r12; struct IMFByteStream *
0x1800201a1  mov     rcx, rbx; this
0x1800201a4  call    ?BeginOpen@CFLACSource@@QEAAJPEAUIMFByteStream@@PEAUIMFAsyncCallback@@PEAUIUnknown@@@Z; CFLACSource::BeginOpen(IMFByteStream *,IMFAsyncCallback *,IUnknown *)
0x1800201a9  mov     ecx, eax
0x1800201ab  mov     [rbp+arg_0], eax
0x1800201ae  test    eax, eax
0x1800201b0  jns     short loc_1800201C5
0x1800201b2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800201b7  cmp     al, 1
0x1800201b9  jb      short loc_1800201EA
0x1800201bb  mov     edx, 0Fh
0x1800201c0  jmp     loc_180020117
0x1800201c5  mov     [rdi+30h], rbx
0x1800201c9  mov     rax, [rbx]
0x1800201cc  mov     rcx, rbx
0x1800201cf  mov     rax, [rax+8]
0x1800201d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201d8  lea     rcx, [r14+30h]; struct IUnknown **
0x1800201dc  mov     rdx, [rbp+ppAsyncResult]; struct IUnknown *
0x1800201e0  cmp     [rcx], rdx
0x1800201e3  jz      short loc_1800201EA
0x1800201e5  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800201ea  test    rbx, rbx
0x1800201ed  jz      short loc_1800201FE
0x1800201ef  mov     rax, [rbx]
0x1800201f2  mov     rcx, rbx
0x1800201f5  mov     rax, [rax+10h]
0x1800201f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201fe  mov     ebx, [rbp+arg_0]
0x180020201  mov     rcx, rsi; lpCriticalSection
0x180020204  call    cs:__imp_LeaveCriticalSection
0x18002020a  nop
0x18002020b  lea     rcx, [rbp+arg_8]
0x18002020f  call    ??1?$CComPtrBase@UIMFTelemetryComponent@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(void)
0x180020214  nop
0x180020215  lea     rcx, [rbp+ppAsyncResult]
0x180020219  call    ??1?$CComPtrBase@UIMFTelemetryComponent@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMFTelemetryComponent>::~CComPtrBase<IMFTelemetryComponent>(void)
0x18002021e  nop
0x18002021f  mov     eax, ebx
0x180020221  mov     rbx, [rsp+60h+arg_10]
0x180020229  add     rsp, 60h
0x18002022d  pop     r14
0x18002022f  pop     r12
0x180020231  pop     rdi
0x180020232  pop     rsi
0x180020233  pop     rbp
0x180020234  retn
```
