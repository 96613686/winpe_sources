# CoreWebViewHostProcess::~CoreWebViewHostProcess(void)

- ea: `0x180017bec`
- end: `0x180017c74`
- name: `??1CoreWebViewHostProcess@@UEAA@XZ`
- size: `136`
- prototype: `void __fastcall(CoreWebViewHostProcess *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003f850`

## callees

- `0x18000b0ec`
- `0x180017bec`
- `0x180017c7c`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180017c43`
- `OLEAUT32!__imp_SysFreeString` at `0x180017c52`
- `OLEAUT32!__imp_SysFreeString` at `0x180017c61`
- `OLEAUT32!__imp_SysFreeString` at `0x180017c43`
- `OLEAUT32!__imp_SysFreeString` at `0x180017c52`
- `OLEAUT32!__imp_SysFreeString` at `0x180017c61`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017bfc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017bfc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017c25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017c25`

## pseudocode

```c
void __fastcall CoreWebViewHostProcess::~CoreWebViewHostProcess(CoreWebViewHostProcess *this)
{
  void *v2; // rcx
  OLECHAR *v3; // rcx
  OLECHAR *v4; // rcx
  OLECHAR *v5; // rcx

  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 160);
  v2 = (void *)*((_QWORD *)this + 18);
  *((_QWORD *)this + 18) = 0;
  if ( v2 )
    LocalFree(v2);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 136);
  v3 = (OLECHAR *)*((_QWORD *)this + 16);
  if ( v3 )
    SysFreeString(v3);
  v4 = (OLECHAR *)*((_QWORD *)this + 15);
  if ( v4 )
    SysFreeString(v4);
  v5 = (OLECHAR *)*((_QWORD *)this + 13);
  if ( v5 )
    SysFreeString(v5);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICoreWebViewHostProcess,ICoreWebViewHostProcessInternal,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICoreWebViewHostProcess,ICoreWebViewHostProcessInternal,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x180017bec  push    rbx
0x180017bee  sub     rsp, 20h
0x180017bf2  mov     rbx, rcx
0x180017bf5  add     rcx, 0A8h; lpCriticalSection
0x180017bfc  call    cs:__imp_DeleteCriticalSection
0x180017c02  lea     rcx, [rbx+0A0h]
0x180017c09  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180017c0e  mov     rcx, [rbx+90h]; hMem
0x180017c15  mov     qword ptr [rbx+90h], 0
0x180017c20  test    rcx, rcx
0x180017c23  jz      short loc_180017C2B
0x180017c25  call    cs:__imp_LocalFree
0x180017c2b  lea     rcx, [rbx+88h]
0x180017c32  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180017c37  mov     rcx, [rbx+80h]; bstrString
0x180017c3e  test    rcx, rcx
0x180017c41  jz      short loc_180017C49
0x180017c43  call    cs:__imp_SysFreeString
0x180017c49  mov     rcx, [rbx+78h]; bstrString
0x180017c4d  test    rcx, rcx
0x180017c50  jz      short loc_180017C58
0x180017c52  call    cs:__imp_SysFreeString
0x180017c58  mov     rcx, [rbx+68h]; bstrString
0x180017c5c  test    rcx, rcx
0x180017c5f  jz      short loc_180017C67
0x180017c61  call    cs:__imp_SysFreeString
0x180017c67  mov     rcx, rbx
0x180017c6a  add     rsp, 20h
0x180017c6e  pop     rbx
0x180017c6f  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UICoreWebViewHostProcess@@UICoreWebViewHostProcessInternal@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICoreWebViewHostProcess,ICoreWebViewHostProcessInternal,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICoreWebViewHostProcess,ICoreWebViewHostProcessInternal,Microsoft::WRL::FtmBase>(void)
```
