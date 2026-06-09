# CThumbnailRequest::_DecodeThumbnailImage(IStream *,IWICBitmapDecoder * *)

- ea: `0x1800214dc`
- end: `0x180021659`
- name: `?_DecodeThumbnailImage@CThumbnailRequest@@AEAAJPEAUIStream@@PEAPEAUIWICBitmapDecoder@@@Z`
- size: `381`
- prototype: `__int64 __fastcall(CThumbnailRequest *__hidden this, struct IStream *, struct IWICBitmapDecoder **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f40c`

## callees

- `0x180001710`
- `0x1800214dc`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180021565`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180021565`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CThumbnailRequest::_DecodeThumbnailImage(
        CThumbnailRequest *this,
        struct IStream *a2,
        struct IWICBitmapDecoder **a3)
{
  HRESULT Instance; // ebx
  LPVOID *ppv; // rdi
  struct IWICBitmapDecoder *v8; // rax
  struct IWICBitmapDecoder *v9; // rcx
  __int64 v10; // rcx
  _QWORD v12[2]; // [rsp+30h] [rbp-10h] BYREF
  int v13; // [rsp+68h] [rbp+28h] BYREF
  struct IWICBitmapDecoder *v14; // [rsp+78h] [rbp+38h] BYREF

  v12[0] = 0;
  v14 = 0;
  v12[1] = 0;
  v13 = 0;
  Instance = ((__int64 (__fastcall *)(struct IStream *, _QWORD, _QWORD, _QWORD))a2->lpVtbl->Seek)(a2, 0, 0, 0);
  if ( Instance >= 0 )
  {
    ppv = (LPVOID *)((char *)this + 56);
    if ( *ppv
      || (Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(ppv),
          Instance = CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70, ppv),
          Instance >= 0) )
    {
      Instance = (*(__int64 (__fastcall **)(LPVOID, _QWORD *))(*(_QWORD *)*ppv + 112LL))(*ppv, v12);
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(_QWORD, struct IStream *))(*(_QWORD *)v12[0] + 112LL))(v12[0], a2);
        if ( Instance >= 0 )
        {
          Instance = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, __int64, struct IWICBitmapDecoder **))(*(_QWORD *)*ppv + 32LL))(
                       *ppv,
                       v12[0],
                       0,
                       1,
                       &v14);
          if ( Instance >= 0 )
          {
            Instance = ((__int64 (__fastcall *)(struct IWICBitmapDecoder *, int *))v14->lpVtbl->GetFrameCount)(
                         v14,
                         &v13);
            if ( Instance >= 0 )
            {
              if ( v13 )
              {
                v8 = v14;
                v14 = 0;
                *a3 = v8;
              }
              else
              {
                Instance = -2147024809;
              }
            }
          }
        }
      }
    }
  }
  v9 = v14;
  if ( v14 )
  {
    v14 = 0;
    ((void (__fastcall *)(struct IWICBitmapDecoder *))v9->lpVtbl->Release)(v9);
  }
  v10 = v12[0];
  if ( v12[0] )
  {
    v12[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800214dc  mov     [rsp-18h+arg_0], rbx
0x1800214e1  mov     [rsp-18h+arg_10], rsi
0x1800214e6  push    rbp
0x1800214e7  push    rdi
0x1800214e8  push    r14
0x1800214ea  mov     rbp, rsp
0x1800214ed  sub     rsp, 40h
0x1800214f1  mov     r14, r8
0x1800214f4  mov     rsi, rdx
0x1800214f7  mov     rdi, rcx
0x1800214fa  mov     [rbp+var_10], 0
0x180021502  mov     [rbp+arg_18], 0
0x18002150a  mov     [rbp+var_8], 0
0x180021512  mov     [rbp+arg_8], 0
0x180021519  xor     edx, edx
0x18002151b  mov     rax, [rsi]
0x18002151e  xor     r9d, r9d
0x180021521  xor     r8d, r8d
0x180021524  mov     rcx, rsi
0x180021527  mov     rax, [rax+28h]
0x18002152b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021530  mov     ebx, eax
0x180021532  test    eax, eax
0x180021534  js      loc_180021608
0x18002153a  add     rdi, 38h ; '8'
0x18002153e  cmp     qword ptr [rdi], 0
0x180021542  jnz     short loc_180021575
0x180021544  mov     rcx, rdi
0x180021547  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18002154c  mov     [rsp+40h+ppv], rdi; ppv
0x180021551  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x180021558  xor     edx, edx; pUnkOuter
0x18002155a  lea     r8d, [rdx+1]; dwClsContext
0x18002155e  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x180021565  call    cs:__imp_CoCreateInstance
0x18002156b  mov     ebx, eax
0x18002156d  test    eax, eax
0x18002156f  js      loc_180021608
0x180021575  mov     rcx, [rdi]
0x180021578  mov     rax, [rcx]
0x18002157b  lea     rdx, [rbp+var_10]
0x18002157f  mov     rax, [rax+70h]
0x180021583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021588  mov     ebx, eax
0x18002158a  test    eax, eax
0x18002158c  js      short loc_180021608
0x18002158e  mov     rcx, [rbp+var_10]
0x180021592  mov     rax, [rcx]
0x180021595  mov     rdx, rsi
0x180021598  mov     rax, [rax+70h]
0x18002159c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800215a1  mov     ebx, eax
0x1800215a3  test    eax, eax
0x1800215a5  js      short loc_180021608
0x1800215a7  mov     rcx, [rdi]
0x1800215aa  mov     rax, [rcx]
0x1800215ad  lea     rdx, [rbp+arg_18]
0x1800215b1  mov     [rsp+40h+ppv], rdx
0x1800215b6  mov     r9d, 1
0x1800215bc  xor     r8d, r8d
0x1800215bf  mov     rdx, [rbp+var_10]
0x1800215c3  mov     rax, [rax+20h]
0x1800215c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800215cc  mov     ebx, eax
0x1800215ce  test    eax, eax
0x1800215d0  js      short loc_180021608
0x1800215d2  mov     rcx, [rbp+arg_18]
0x1800215d6  mov     rax, [rcx]
0x1800215d9  lea     rdx, [rbp+arg_8]
0x1800215dd  mov     rax, [rax+60h]
0x1800215e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800215e6  mov     ebx, eax
0x1800215e8  test    eax, eax
0x1800215ea  js      short loc_180021608
0x1800215ec  cmp     [rbp+arg_8], 0
0x1800215f0  jnz     short loc_1800215F9
0x1800215f2  mov     ebx, 80070057h
0x1800215f7  jmp     short loc_180021608
0x1800215f9  mov     rax, [rbp+arg_18]
0x1800215fd  mov     [rbp+arg_18], 0
0x180021605  mov     [r14], rax
0x180021608  mov     rcx, [rbp+arg_18]
0x18002160c  test    rcx, rcx
0x18002160f  jz      short loc_180021626
0x180021611  mov     [rbp+arg_18], 0
0x180021619  mov     rax, [rcx]
0x18002161c  mov     rax, [rax+10h]
0x180021620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021625  nop
0x180021626  mov     rcx, [rbp+var_10]
0x18002162a  test    rcx, rcx
0x18002162d  jz      short loc_180021644
0x18002162f  mov     [rbp+var_10], 0
0x180021637  mov     rax, [rcx]
0x18002163a  mov     rax, [rax+10h]
0x18002163e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021643  nop
0x180021644  mov     eax, ebx
0x180021646  mov     rbx, [rsp+40h+arg_0]
0x18002164b  mov     rsi, [rsp+40h+arg_10]
0x180021650  add     rsp, 40h
0x180021654  pop     r14
0x180021656  pop     rdi
0x180021657  pop     rbp
0x180021658  retn
```
