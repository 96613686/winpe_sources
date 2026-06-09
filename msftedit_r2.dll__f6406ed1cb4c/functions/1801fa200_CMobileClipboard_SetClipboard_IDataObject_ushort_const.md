# CMobileClipboard::SetClipboard(IDataObject *,ushort const *)

- ea: `0x1801fa200`
- end: `0x1801fa438`
- name: `?SetClipboard@CMobileClipboard@@UEAAJPEAUIDataObject@@PEBG@Z`
- size: `568`
- prototype: `__int64 __fastcall(CMobileClipboard *__hidden this, struct IDataObject *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x18006ad18`
- `0x18006af48`
- `0x18006b190`
- `0x18009abd0`
- `0x180149110`
- `0x1801f9834`
- `0x1801f9b5c`
- `0x1801f9d48`
- `0x1801fa200`
- `0x180209568`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801fa334`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801fa334`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fa27b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fa3af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fa3c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fa27b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fa3af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fa3c3`

## pseudocode

```c
__int64 __fastcall CMobileClipboard::SetClipboard(
        CMobileClipboard *this,
        struct IDataObject *a2,
        const unsigned __int16 *a3)
{
  unsigned int ClipboardStatics; // ebx
  unsigned int v6; // edi
  __int64 v7; // r14
  struct IDataObjectVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetData)(IDataObject *, FORMATETC *, STGMEDIUM *); // rax
  unsigned int v10; // eax
  __int64 v11; // rcx
  HSTRING v13; // [rsp+20h] [rbp-60h] BYREF
  __int64 v14; // [rsp+28h] [rbp-58h] BYREF
  __int64 v15; // [rsp+30h] [rbp-50h] BYREF
  HSTRING v16; // [rsp+38h] [rbp-48h] BYREF
  struct tagSTGMEDIUM v17; // [rsp+40h] [rbp-40h] BYREF
  __int16 v18; // [rsp+58h] [rbp-28h] BYREF
  int v19; // [rsp+5Ah] [rbp-26h]
  __int16 v20; // [rsp+5Eh] [rbp-22h]
  __int64 v21; // [rsp+60h] [rbp-20h]
  int v22; // [rsp+68h] [rbp-18h]
  int v23; // [rsp+6Ch] [rbp-14h]
  __int64 v24; // [rsp+70h] [rbp-10h]
  HSTRING string; // [rsp+C8h] [rbp+48h] BYREF

  ClipboardStatics = CMobileClipboard::GetClipboardStatics(this);
  v14 = 0;
  if ( !ClipboardStatics )
  {
    ClipboardStatics = OSGetDataPackage(&v14);
    if ( !ClipboardStatics )
    {
      if ( *((_QWORD *)this + 3) )
      {
        ClipboardStatics = 0;
      }
      else
      {
        string = 0;
        ClipboardStatics = Microsoft::WRL::Wrappers::HString::Set(
                             (Microsoft::WRL::Wrappers::HString *)&string,
                             L"Windows.Foundation.PropertyValue",
                             0x20u);
        if ( !ClipboardStatics )
          ClipboardStatics = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(
                               string,
                               (char *)this + 24);
        WindowsDeleteString(string);
      }
    }
  }
  v6 = 0;
  while ( !ClipboardStatics )
  {
    v7 = 2LL * v6;
    v19 = 0;
    v20 = 0;
    v24 = 1;
    v18 = *(_WORD *)((char *)&SupportedFormats + v7 * 8);
    lpVtbl = a2->lpVtbl;
    v22 = 1;
    v23 = -1;
    v21 = 0;
    GetData = lpVtbl->GetData;
    memset(&v17, 0, sizeof(v17));
    ClipboardStatics = ((__int64 (__fastcall *)(struct IDataObject *, __int16 *, struct tagSTGMEDIUM *))GetData)(
                         a2,
                         &v18,
                         &v17);
    if ( ClipboardStatics )
    {
      if ( ClipboardStatics == -2147221404 )
        ClipboardStatics = 0;
    }
    else
    {
      if ( v17.tymed == 1 )
      {
        v16 = 0;
        v13 = 0;
        LODWORD(string) = 0;
        Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&v13, &(&off_1802A0E28)[v7]);
        WindowsGetStringRawBuffer(v13, (UINT32 *)&string);
        if ( (_DWORD)string )
        {
          v10 = CW32System::GlobalSize(v17.hBitmap);
          ClipboardStatics = Microsoft::WRL::Wrappers::HString::Set(
                               (Microsoft::WRL::Wrappers::HString *)&v16,
                               v17.lpszFileName,
                               v10 >> 1);
          if ( !ClipboardStatics )
          {
            v11 = *((_QWORD *)this + 3);
            v15 = 0;
            if ( !(*(unsigned int (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v11 + 144LL))(v11, v16, &v15) )
              (*(void (__fastcall **)(__int64, HSTRING, __int64))(*(_QWORD *)v14 + 112LL))(v14, v13, v15);
            Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(&v15);
          }
        }
        WindowsDeleteString(v13);
        v13 = 0;
        WindowsDeleteString(v16);
      }
      CW32System::ReleaseStgMedium(&v17);
    }
    if ( ++v6 >= 3 )
    {
      if ( !ClipboardStatics )
        ClipboardStatics = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 2) + 56LL))(
                             *((_QWORD *)this + 2),
                             v14);
      break;
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  return ClipboardStatics;
}

```

## disassembly

```asm
0x1801fa200  mov     [rsp-28h+arg_0], rbx
0x1801fa205  mov     [rsp-28h+arg_8], rsi
0x1801fa20a  push    rbp
0x1801fa20b  push    rdi
0x1801fa20c  push    r12
0x1801fa20e  push    r14
0x1801fa210  push    r15
0x1801fa212  mov     rbp, rsp
0x1801fa215  sub     rsp, 80h
0x1801fa21c  mov     r15, rdx
0x1801fa21f  mov     rsi, rcx
0x1801fa222  call    ?GetClipboardStatics@CMobileClipboard@@AEAAJXZ; CMobileClipboard::GetClipboardStatics(void)
0x1801fa227  xor     r12d, r12d
0x1801fa22a  mov     ebx, eax
0x1801fa22c  mov     [rbp+var_58], r12
0x1801fa230  test    eax, eax
0x1801fa232  jnz     short loc_1801FA28C
0x1801fa234  lea     rcx, [rbp+var_58]
0x1801fa238  call    OSGetDataPackage
0x1801fa23d  mov     ebx, eax
0x1801fa23f  test    eax, eax
0x1801fa241  jnz     short loc_1801FA28C
0x1801fa243  cmp     [rsi+18h], r12
0x1801fa247  jnz     short loc_1801FA289
0x1801fa249  lea     r8d, [r12+20h]; unsigned int
0x1801fa24e  mov     [rbp+string], r12
0x1801fa252  lea     rdx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x1801fa259  lea     rcx, [rbp+string]; this
0x1801fa25d  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1801fa262  mov     ebx, eax
0x1801fa264  test    eax, eax
0x1801fa266  jnz     short loc_1801FA277
0x1801fa268  mov     rcx, [rbp+string]
0x1801fa26c  lea     rdx, [rsi+18h]
0x1801fa270  call    ??$GetActivationFactory@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>)
0x1801fa275  mov     ebx, eax
0x1801fa277  mov     rcx, [rbp+string]; string
0x1801fa27b  call    cs:__imp_WindowsDeleteString
0x1801fa282  nop     dword ptr [rax+rax+00h]
0x1801fa287  jmp     short loc_1801FA28C
0x1801fa289  mov     ebx, r12d
0x1801fa28c  mov     edi, r12d
0x1801fa28f  lea     rcx, ?SupportedFormats@@3QBUSupportedFormat@@B; SupportedFormat const near * const SupportedFormats
0x1801fa296  test    ebx, ebx
0x1801fa298  jnz     loc_1801FA410
0x1801fa29e  xorps   xmm0, xmm0
0x1801fa2a1  mov     r14d, edi
0x1801fa2a4  shl     r14, 4
0x1801fa2a8  lea     r8, [rbp+var_40]
0x1801fa2ac  lea     rdx, [rbp+var_28]
0x1801fa2b0  mov     [rbp+var_26], r12d
0x1801fa2b4  mov     [rbp+var_22], r12w
0x1801fa2b9  mov     [rbp+var_10], 1
0x1801fa2c1  movzx   eax, word ptr [r14+rcx]
0x1801fa2c6  mov     rcx, r15
0x1801fa2c9  mov     [rbp+var_28], ax
0x1801fa2cd  xor     eax, eax
0x1801fa2cf  mov     [rbp+var_40.pUnkForRelease], rax
0x1801fa2d3  mov     rax, [r15]
0x1801fa2d6  mov     [rbp+var_18], 1
0x1801fa2dd  mov     [rbp+var_14], 0FFFFFFFFh
0x1801fa2e4  mov     [rbp+var_20], r12
0x1801fa2e8  mov     rax, [rax+18h]
0x1801fa2ec  movups  xmmword ptr [rbp+var_40.tymed], xmm0
0x1801fa2f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fa2f5  mov     ebx, eax
0x1801fa2f7  test    eax, eax
0x1801fa2f9  jnz     loc_1801FA3DA
0x1801fa2ff  cmp     [rbp+var_40.tymed], 1
0x1801fa303  jnz     loc_1801FA3CF
0x1801fa309  lea     rdx, ?SupportedFormats@@3QBUSupportedFormat@@B; SupportedFormat const near * const SupportedFormats
0x1801fa310  mov     [rbp+var_48], r12
0x1801fa314  add     rdx, 8
0x1801fa318  mov     [rbp+var_60], r12
0x1801fa31c  add     rdx, r14
0x1801fa31f  mov     dword ptr [rbp+string], r12d
0x1801fa323  lea     rcx, [rbp+var_60]
0x1801fa327  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801fa32c  mov     rcx, [rbp+var_60]; string
0x1801fa330  lea     rdx, [rbp+string]; length
0x1801fa334  call    cs:__imp_WindowsGetStringRawBuffer
0x1801fa33b  nop     dword ptr [rax+rax+00h]
0x1801fa340  cmp     dword ptr [rbp+string], r12d
0x1801fa344  jz      short loc_1801FA3AB
0x1801fa346  mov     rcx, qword ptr [rbp+var_40.8]; void *
0x1801fa34a  call    ?GlobalSize@CW32System@@SAKPEAX@Z; CW32System::GlobalSize(void *)
0x1801fa34f  mov     rdx, qword ptr [rbp+var_40.8]; unsigned __int16 *
0x1801fa353  lea     rcx, [rbp+var_48]; this
0x1801fa357  shr     eax, 1
0x1801fa359  mov     r8d, eax; unsigned int
0x1801fa35c  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1801fa361  mov     ebx, eax
0x1801fa363  test    eax, eax
0x1801fa365  jnz     short loc_1801FA3AB
0x1801fa367  mov     rcx, [rsi+18h]
0x1801fa36b  lea     r8, [rbp+var_50]
0x1801fa36f  mov     rdx, [rbp+var_48]
0x1801fa373  mov     [rbp+var_50], r12
0x1801fa377  mov     rax, [rcx]
0x1801fa37a  mov     rax, [rax+90h]
0x1801fa381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fa386  test    eax, eax
0x1801fa388  jnz     short loc_1801FA3A2
0x1801fa38a  mov     rcx, [rbp+var_58]
0x1801fa38e  mov     r8, [rbp+var_50]
0x1801fa392  mov     rdx, [rbp+var_60]
0x1801fa396  mov     rax, [rcx]
0x1801fa399  mov     rax, [rax+70h]
0x1801fa39d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fa3a2  lea     rcx, [rbp+var_50]; void *
0x1801fa3a6  call    ??1?$TCntPtr@UIDataObject@@@Resp@@QEAA@XZ; Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(void)
0x1801fa3ab  mov     rcx, [rbp+var_60]; string
0x1801fa3af  call    cs:__imp_WindowsDeleteString
0x1801fa3b6  nop     dword ptr [rax+rax+00h]
0x1801fa3bb  mov     rcx, [rbp+var_48]; string
0x1801fa3bf  mov     [rbp+var_60], r12
0x1801fa3c3  call    cs:__imp_WindowsDeleteString
0x1801fa3ca  nop     dword ptr [rax+rax+00h]
0x1801fa3cf  lea     rcx, [rbp+var_40]; struct tagSTGMEDIUM *
0x1801fa3d3  call    ?ReleaseStgMedium@CW32System@@SAXPEAUtagSTGMEDIUM@@@Z; CW32System::ReleaseStgMedium(tagSTGMEDIUM *)
0x1801fa3d8  jmp     short loc_1801FA3E4
0x1801fa3da  cmp     ebx, 80040064h
0x1801fa3e0  cmovz   ebx, r12d
0x1801fa3e4  inc     edi
0x1801fa3e6  lea     rcx, ?SupportedFormats@@3QBUSupportedFormat@@B; SupportedFormat const near * const SupportedFormats
0x1801fa3ed  cmp     edi, 3
0x1801fa3f0  jb      loc_1801FA296
0x1801fa3f6  test    ebx, ebx
0x1801fa3f8  jnz     short loc_1801FA410
0x1801fa3fa  mov     rcx, [rsi+10h]
0x1801fa3fe  mov     rdx, [rbp+var_58]
0x1801fa402  mov     rax, [rcx]
0x1801fa405  mov     rax, [rax+38h]
0x1801fa409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fa40e  mov     ebx, eax
0x1801fa410  lea     rcx, [rbp+var_58]
0x1801fa414  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801fa419  lea     r11, [rsp+80h+var_s0]
0x1801fa421  mov     eax, ebx
0x1801fa423  mov     rbx, [r11+30h]
0x1801fa427  mov     rsi, [r11+38h]
0x1801fa42b  mov     rsp, r11
0x1801fa42e  pop     r15
0x1801fa430  pop     r14
0x1801fa432  pop     r12
0x1801fa434  pop     rdi
0x1801fa435  pop     rbp
0x1801fa436  retn
```
