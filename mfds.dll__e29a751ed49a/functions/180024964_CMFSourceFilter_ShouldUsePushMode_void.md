# CMFSourceFilter::_ShouldUsePushMode(void)

- ea: `0x180024964`
- end: `0x180024b91`
- name: `?_ShouldUsePushMode@CMFSourceFilter@@QEAAHXZ`
- size: `557`
- prototype: `__int64 __fastcall(CMFSourceFilter *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024710`
- `0x180054830`

## callees

- `0x180010350`
- `0x1800227e0`
- `0x180024964`
- `0x180024b98`
- `0x180074160`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memcmp` at `0x1800249ed`
- `api-ms-win-crt-private-l1-1-0!memcmp` at `0x180024a0f`
- `api-ms-win-crt-private-l1-1-0!memcmp` at `0x1800249ed`
- `api-ms-win-crt-private-l1-1-0!memcmp` at `0x180024a0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024a95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024b5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024a95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024b5c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024a7e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180024a7e`

## pseudocode

```c
__int64 __fastcall CMFSourceFilter::_ShouldUsePushMode(CMFSourceFilter *this)
{
  char *v2; // r14
  unsigned int v3; // esi
  __int64 v4; // rcx
  int v5; // r14d
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  LPCWCH lpString1; // [rsp+30h] [rbp-38h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-30h] BYREF
  __int64 v12; // [rsp+40h] [rbp-28h] BYREF
  __int64 v13; // [rsp+48h] [rbp-20h] BYREF

  if ( *((_DWORD *)this + 505) )
    return 1;
  v2 = (char *)this + 1912;
  if ( (unsigned __int8)_((char *)this + 1912, &MEDIASUBTYPE_MPEG2_TRANSPORT)
    || (unsigned __int8)_(v2, &MEDIASUBTYPE_MPEG2_TRANSPORT_STRIDE) )
  {
    return 1;
  }
  v3 = 0;
  if ( !*((_DWORD *)this + 52) && *((_QWORD *)this + 27) )
  {
    if ( !memcmp(&MEDIASUBTYPE_MPEG2_PROGRAM, v2, 0x10u) )
      goto LABEL_14;
    if ( !memcmp(&GUID_00000000_0000_0000_0000_000000000000, v2, 0x10u) )
    {
      v4 = *((_QWORD *)this + 27);
      v5 = 0;
      v12 = 0;
      if ( (int)SafeQueryInterface<IMFAttributes>(v4, &v12) >= 0 )
      {
        lpString1 = 0;
        if ( (*(int (__fastcall **)(__int64, const IID *, LPCWCH *, _QWORD))(*(_QWORD *)v12 + 104LL))(
               v12,
               &MF_BYTESTREAM_CONTENT_TYPE,
               &lpString1,
               0) >= 0 )
        {
          LOBYTE(v5) = CompareStringOrdinal(lpString1, -1, L"video/mpeg", 10, 1) == 2;
          CoTaskMemFree((LPVOID)lpString1);
        }
      }
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      if ( v5 )
      {
LABEL_14:
        v6 = *((_QWORD *)this + 27);
        v13 = 0;
        if ( (*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v6 + 32LL))(v6, &v13) != -1072875781 )
        {
          v7 = *((_QWORD *)this + 27);
          LODWORD(lpString1) = 0;
          if ( (*(int (__fastcall **)(__int64, LPCWCH *))(*(_QWORD *)v7 + 24LL))(v7, &lpString1) < 0
            || ((unsigned __int16)lpString1 & 0x104) == 4 )
          {
            v8 = *((_QWORD *)this + 27);
            v12 = 0;
            if ( (int)SafeQueryInterface<IMFAttributes>(v8, &v12) >= 0 )
            {
              pv = 0;
              if ( (*(int (__fastcall **)(__int64, const IID *, LPVOID *, _QWORD))(*(_QWORD *)v12 + 104LL))(
                     v12,
                     &MF_BYTESTREAM_IFO_FILE_URI,
                     &pv,
                     0) >= 0 )
              {
                if ( pv )
                {
                  v3 = 1;
                  CoTaskMemFree(pv);
                }
              }
            }
            ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v12);
            return v3;
          }
        }
        return 1;
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180024964  push    rbp
0x180024966  push    rbx
0x180024967  push    rsi
0x180024968  push    r14
0x18002496a  mov     rbp, rsp
0x18002496d  sub     rsp, 68h
0x180024971  mov     rax, cs:__security_cookie
0x180024978  xor     rax, rsp
0x18002497b  mov     [rbp+var_18], rax
0x18002497f  cmp     dword ptr [rcx+7E4h], 0
0x180024986  mov     rbx, rcx
0x180024989  jnz     loc_180024B73
0x18002498f  lea     r14, [rcx+778h]
0x180024996  mov     rcx, r14
0x180024999  lea     rdx, MEDIASUBTYPE_MPEG2_TRANSPORT
0x1800249a0  call    __
0x1800249a5  test    al, al
0x1800249a7  jnz     loc_180024B73
0x1800249ad  lea     rdx, MEDIASUBTYPE_MPEG2_TRANSPORT_STRIDE
0x1800249b4  mov     rcx, r14
0x1800249b7  call    __
0x1800249bc  test    al, al
0x1800249be  jnz     loc_180024B73
0x1800249c4  xor     esi, esi
0x1800249c6  cmp     [rbx+0D0h], esi
0x1800249cc  jnz     loc_180024B78
0x1800249d2  cmp     [rbx+0D8h], rsi
0x1800249d9  jz      loc_180024B78
0x1800249df  lea     r8d, [rsi+10h]; Size
0x1800249e3  mov     rdx, r14; Buf2
0x1800249e6  lea     rcx, MEDIASUBTYPE_MPEG2_PROGRAM; Buf1
0x1800249ed  call    cs:__imp_memcmp
0x1800249f4  nop     dword ptr [rax+rax+00h]
0x1800249f9  test    eax, eax
0x1800249fb  jz      loc_180024ABF
0x180024a01  lea     r8d, [rsi+10h]; Size
0x180024a05  mov     rdx, r14; Buf2
0x180024a08  lea     rcx, _GUID_00000000_0000_0000_0000_000000000000; Buf1
0x180024a0f  call    cs:__imp_memcmp
0x180024a16  nop     dword ptr [rax+rax+00h]
0x180024a1b  test    eax, eax
0x180024a1d  jnz     loc_180024B78
0x180024a23  mov     rcx, [rbx+0D8h]
0x180024a2a  lea     rdx, [rbp+var_28]
0x180024a2e  xor     r14d, r14d
0x180024a31  mov     [rbp+var_28], rsi
0x180024a35  call    ??$SafeQueryInterface@UIMFAttributes@@@@YAJPEAUIUnknown@@PEAPEAUIMFAttributes@@@Z; SafeQueryInterface<IMFAttributes>(IUnknown *,IMFAttributes * *)
0x180024a3a  test    eax, eax
0x180024a3c  js      short loc_180024AA1
0x180024a3e  mov     rcx, [rbp+var_28]
0x180024a42  lea     r8, [rbp+lpString1]
0x180024a46  mov     [rbp+lpString1], rsi
0x180024a4a  lea     rdx, MF_BYTESTREAM_CONTENT_TYPE
0x180024a51  xor     r9d, r9d
0x180024a54  mov     rax, [rcx]
0x180024a57  mov     rax, [rax+68h]
0x180024a5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a60  test    eax, eax
0x180024a62  js      short loc_180024AA1
0x180024a64  mov     rcx, [rbp+lpString1]; lpString1
0x180024a68  lea     r9d, [rsi+0Ah]; cchCount2
0x180024a6c  lea     r8, String2; "video/mpeg"
0x180024a73  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x180024a7b  or      edx, 0FFFFFFFFh; cchCount1
0x180024a7e  call    cs:__imp_CompareStringOrdinal
0x180024a85  nop     dword ptr [rax+rax+00h]
0x180024a8a  mov     rcx, [rbp+lpString1]; pv
0x180024a8e  cmp     eax, 2
0x180024a91  setz    r14b
0x180024a95  call    cs:__imp_CoTaskMemFree
0x180024a9c  nop     dword ptr [rax+rax+00h]
0x180024aa1  mov     rcx, [rbp+var_28]
0x180024aa5  test    rcx, rcx
0x180024aa8  jz      short loc_180024AB6
0x180024aaa  mov     rax, [rcx]
0x180024aad  mov     rax, [rax+10h]
0x180024ab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ab6  test    r14d, r14d
0x180024ab9  jz      loc_180024B78
0x180024abf  mov     rcx, [rbx+0D8h]
0x180024ac6  lea     rdx, [rbp+var_20]
0x180024aca  mov     [rbp+var_20], rsi
0x180024ace  mov     rax, [rcx]
0x180024ad1  mov     rax, [rax+20h]
0x180024ad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ada  cmp     eax, 0C00D36FBh
0x180024adf  jz      loc_180024B73
0x180024ae5  mov     rcx, [rbx+0D8h]
0x180024aec  lea     rdx, [rbp+lpString1]
0x180024af0  mov     dword ptr [rbp+lpString1], esi
0x180024af3  mov     rax, [rcx]
0x180024af6  mov     rax, [rax+18h]
0x180024afa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024aff  test    eax, eax
0x180024b01  js      short loc_180024B10
0x180024b03  mov     eax, dword ptr [rbp+lpString1]
0x180024b06  and     eax, 104h
0x180024b0b  cmp     eax, 4
0x180024b0e  jnz     short loc_180024B73
0x180024b10  mov     rcx, [rbx+0D8h]
0x180024b17  lea     rdx, [rbp+var_28]
0x180024b1b  mov     [rbp+var_28], rsi
0x180024b1f  call    ??$SafeQueryInterface@UIMFAttributes@@@@YAJPEAUIUnknown@@PEAPEAUIMFAttributes@@@Z; SafeQueryInterface<IMFAttributes>(IUnknown *,IMFAttributes * *)
0x180024b24  test    eax, eax
0x180024b26  js      short loc_180024B68
0x180024b28  mov     rcx, [rbp+var_28]
0x180024b2c  lea     r8, [rbp+pv]
0x180024b30  mov     [rbp+pv], rsi
0x180024b34  lea     rdx, MF_BYTESTREAM_IFO_FILE_URI
0x180024b3b  xor     r9d, r9d
0x180024b3e  mov     rax, [rcx]
0x180024b41  mov     rax, [rax+68h]
0x180024b45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024b4a  test    eax, eax
0x180024b4c  js      short loc_180024B68
0x180024b4e  mov     rcx, [rbp+pv]; pv
0x180024b52  test    rcx, rcx
0x180024b55  jz      short loc_180024B68
0x180024b57  mov     esi, 1
0x180024b5c  call    cs:__imp_CoTaskMemFree
0x180024b63  nop     dword ptr [rax+rax+00h]
0x180024b68  lea     rcx, [rbp+var_28]; void *
0x180024b6c  call    ??1?$CComPtrBase@UIMediaSeeking@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(void)
0x180024b71  jmp     short loc_180024B78
0x180024b73  mov     esi, 1
0x180024b78  mov     eax, esi
0x180024b7a  mov     rcx, [rbp+var_18]
0x180024b7e  xor     rcx, rsp; StackCookie
0x180024b81  call    __security_check_cookie
0x180024b86  add     rsp, 68h
0x180024b8a  pop     r14
0x180024b8c  pop     rsi
0x180024b8d  pop     rbx
0x180024b8e  pop     rbp
0x180024b8f  retn
```
