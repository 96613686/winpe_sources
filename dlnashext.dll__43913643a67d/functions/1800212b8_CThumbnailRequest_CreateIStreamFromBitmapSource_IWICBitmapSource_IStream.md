# CThumbnailRequest::_CreateIStreamFromBitmapSource(IWICBitmapSource *,IStream * *)

- ea: `0x1800212b8`
- end: `0x1800214d4`
- name: `?_CreateIStreamFromBitmapSource@CThumbnailRequest@@AEAAJPEAUIWICBitmapSource@@PEAPEAUIStream@@@Z`
- size: `540`
- prototype: `__int64 __fastcall(CThumbnailRequest *__hidden this, struct IWICBitmapSource *, struct IStream **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180021770`

## callees

- `0x180001710`
- `0x180011930`
- `0x1800212b8`
- `0x180035010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180021304`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x180021304`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CThumbnailRequest::_CreateIStreamFromBitmapSource(
        CThumbnailRequest *this,
        struct IWICBitmapSource *a2,
        struct IStream **a3)
{
  struct IStream *v6; // rdi
  int v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v11; // [rsp+30h] [rbp-40h] BYREF
  __int64 v12; // [rsp+38h] [rbp-38h] BYREF
  struct IStream *v13; // [rsp+40h] [rbp-30h] BYREF
  __int128 v14; // [rsp+48h] [rbp-28h] BYREF
  GUID v15; // [rsp+58h] [rbp-18h] BYREF

  v12 = 0;
  v11 = 0;
  v14 = 0;
  v15 = GUID_WICPixelFormat32bppBGRA;
  v6 = SHCreateMemStream(0, 0);
  v13 = v6;
  if ( v6 )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, GUID *, _QWORD, __int64 *))(**((_QWORD **)this + 7) + 64LL))(
           *((_QWORD *)this + 7),
           &GUID_ContainerFormatBmp,
           0,
           &v12);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, struct IStream *, __int64))(*(_QWORD *)v12 + 24LL))(v12, v6, 2);
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v12 + 80LL))(v12, &v11, 0);
        if ( v7 >= 0 )
        {
          v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v11 + 24LL))(v11, 0);
          if ( v7 >= 0 )
          {
            v7 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v11 + 48LL))(v11, &v15);
            if ( v7 >= 0 )
            {
              v7 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, char *, char *))a2->lpVtbl->GetSize)(
                     a2,
                     (char *)&v14 + 8,
                     (char *)&v14 + 12);
              if ( v7 >= 0 )
              {
                v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v11 + 32LL))(
                       v11,
                       DWORD2(v14),
                       HIDWORD(v14));
                if ( v7 >= 0 )
                {
                  v7 = (*(__int64 (__fastcall **)(__int64, struct IWICBitmapSource *, __int128 *))(*(_QWORD *)v11 + 88LL))(
                         v11,
                         a2,
                         &v14);
                  if ( v7 >= 0 )
                  {
                    v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 96LL))(v11);
                    if ( v7 >= 0 )
                    {
                      v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 88LL))(v12);
                      if ( v7 >= 0 )
                      {
                        v7 = ((__int64 (__fastcall *)(struct IStream *, _QWORD, _QWORD, _QWORD))v6->lpVtbl->Seek)(
                               v6,
                               0,
                               0,
                               0);
                        if ( v7 >= 0 )
                        {
                          v13 = 0;
                          *a3 = v6;
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    v7 = -2147024882;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v13);
  v8 = v11;
  if ( v11 )
  {
    v11 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  v9 = v12;
  if ( v12 )
  {
    v12 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800212b8  push    rbp
0x1800212ba  push    rbx
0x1800212bb  push    rsi
0x1800212bc  push    rdi
0x1800212bd  push    r14
0x1800212bf  mov     rbp, rsp
0x1800212c2  sub     rsp, 70h
0x1800212c6  mov     rax, cs:__security_cookie
0x1800212cd  xor     rax, rsp
0x1800212d0  mov     [rbp+var_8], rax
0x1800212d4  mov     r14, r8
0x1800212d7  mov     rsi, rdx
0x1800212da  mov     rbx, rcx
0x1800212dd  mov     [rbp+var_38], 0
0x1800212e5  mov     [rbp+var_40], 0
0x1800212ed  xorps   xmm0, xmm0
0x1800212f0  movups  [rbp+var_28], xmm0
0x1800212f4  movups  xmm1, xmmword ptr cs:GUID_WICPixelFormat32bppBGRA.Data1
0x1800212fb  movdqu  [rbp+var_18], xmm1
0x180021300  xor     edx, edx; cbInit
0x180021302  xor     ecx, ecx; pInit
0x180021304  call    cs:__imp_SHCreateMemStream
0x18002130a  mov     rdi, rax
0x18002130d  mov     [rbp+var_30], rax
0x180021311  test    rax, rax
0x180021314  jnz     short loc_180021320
0x180021316  mov     ebx, 8007000Eh
0x18002131b  jmp     loc_180021475
0x180021320  mov     rcx, [rbx+38h]
0x180021324  mov     rax, [rcx]
0x180021327  lea     r9, [rbp+var_38]
0x18002132b  xor     r8d, r8d
0x18002132e  lea     rdx, GUID_ContainerFormatBmp
0x180021335  mov     rax, [rax+40h]
0x180021339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002133e  mov     ebx, eax
0x180021340  test    eax, eax
0x180021342  js      loc_180021475
0x180021348  mov     rcx, [rbp+var_38]
0x18002134c  mov     rax, [rcx]
0x18002134f  mov     r8d, 2
0x180021355  mov     rdx, rdi
0x180021358  mov     rax, [rax+18h]
0x18002135c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021361  mov     ebx, eax
0x180021363  test    eax, eax
0x180021365  js      loc_180021475
0x18002136b  mov     rcx, [rbp+var_38]
0x18002136f  mov     rax, [rcx]
0x180021372  xor     r8d, r8d
0x180021375  lea     rdx, [rbp+var_40]
0x180021379  mov     rax, [rax+50h]
0x18002137d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021382  mov     ebx, eax
0x180021384  test    eax, eax
0x180021386  js      loc_180021475
0x18002138c  mov     rcx, [rbp+var_40]
0x180021390  mov     rax, [rcx]
0x180021393  xor     edx, edx
0x180021395  mov     rax, [rax+18h]
0x180021399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002139e  mov     ebx, eax
0x1800213a0  test    eax, eax
0x1800213a2  js      loc_180021475
0x1800213a8  mov     rcx, [rbp+var_40]
0x1800213ac  mov     rax, [rcx]
0x1800213af  lea     rdx, [rbp+var_18]
0x1800213b3  mov     rax, [rax+30h]
0x1800213b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213bc  mov     ebx, eax
0x1800213be  test    eax, eax
0x1800213c0  js      loc_180021475
0x1800213c6  mov     rax, [rsi]
0x1800213c9  lea     r8, [rbp+var_28+0Ch]
0x1800213cd  lea     rdx, [rbp+var_28+8]
0x1800213d1  mov     rcx, rsi
0x1800213d4  mov     rax, [rax+18h]
0x1800213d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213dd  mov     ebx, eax
0x1800213df  test    eax, eax
0x1800213e1  js      loc_180021475
0x1800213e7  mov     rcx, [rbp+var_40]
0x1800213eb  mov     rax, [rcx]
0x1800213ee  mov     r8d, dword ptr [rbp+var_28+0Ch]
0x1800213f2  mov     edx, dword ptr [rbp+var_28+8]
0x1800213f5  mov     rax, [rax+20h]
0x1800213f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213fe  mov     ebx, eax
0x180021400  test    eax, eax
0x180021402  js      short loc_180021475
0x180021404  mov     rcx, [rbp+var_40]
0x180021408  mov     rax, [rcx]
0x18002140b  lea     r8, [rbp+var_28]
0x18002140f  mov     rdx, rsi
0x180021412  mov     rax, [rax+58h]
0x180021416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002141b  mov     ebx, eax
0x18002141d  test    eax, eax
0x18002141f  js      short loc_180021475
0x180021421  mov     rcx, [rbp+var_40]
0x180021425  mov     rax, [rcx]
0x180021428  mov     rax, [rax+60h]
0x18002142c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021431  mov     ebx, eax
0x180021433  test    eax, eax
0x180021435  js      short loc_180021475
0x180021437  mov     rcx, [rbp+var_38]
0x18002143b  mov     rax, [rcx]
0x18002143e  mov     rax, [rax+58h]
0x180021442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021447  mov     ebx, eax
0x180021449  test    eax, eax
0x18002144b  js      short loc_180021475
0x18002144d  xor     edx, edx
0x18002144f  mov     rax, [rdi]
0x180021452  xor     r9d, r9d
0x180021455  xor     r8d, r8d
0x180021458  mov     rcx, rdi
0x18002145b  mov     rax, [rax+28h]
0x18002145f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021464  mov     ebx, eax
0x180021466  test    eax, eax
0x180021468  js      short loc_180021475
0x18002146a  mov     [rbp+var_30], 0
0x180021472  mov     [r14], rdi
0x180021475  lea     rcx, [rbp+var_30]
0x180021479  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18002147e  nop
0x18002147f  mov     rcx, [rbp+var_40]
0x180021483  test    rcx, rcx
0x180021486  jz      short loc_18002149D
0x180021488  mov     [rbp+var_40], 0
0x180021490  mov     rax, [rcx]
0x180021493  mov     rax, [rax+10h]
0x180021497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002149c  nop
0x18002149d  mov     rcx, [rbp+var_38]
0x1800214a1  test    rcx, rcx
0x1800214a4  jz      short loc_1800214BB
0x1800214a6  mov     [rbp+var_38], 0
0x1800214ae  mov     rax, [rcx]
0x1800214b1  mov     rax, [rax+10h]
0x1800214b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214ba  nop
0x1800214bb  mov     eax, ebx
0x1800214bd  mov     rcx, [rbp+var_8]
0x1800214c1  xor     rcx, rsp; StackCookie
0x1800214c4  call    __security_check_cookie
0x1800214c9  add     rsp, 70h
0x1800214cd  pop     r14
0x1800214cf  pop     rdi
0x1800214d0  pop     rsi
0x1800214d1  pop     rbx
0x1800214d2  pop     rbp
0x1800214d3  retn
```
