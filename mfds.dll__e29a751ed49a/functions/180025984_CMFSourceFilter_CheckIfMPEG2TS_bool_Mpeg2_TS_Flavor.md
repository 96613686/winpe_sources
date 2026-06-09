# CMFSourceFilter::_CheckIfMPEG2TS(bool *,Mpeg2_TS_Flavor *)

- ea: `0x180025984`
- end: `0x180025c32`
- name: `?_CheckIfMPEG2TS@CMFSourceFilter@@QEAAJPEA_NPEAW4Mpeg2_TS_Flavor@@@Z`
- size: `686`
- prototype: `__int64 __fastcall(CMFSourceFilter *__hidden this, bool *, enum Mpeg2_TS_Flavor *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024bcc`

## callees

- `0x1800227e0`
- `0x180024b98`
- `0x180025984`
- `0x180074160`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025bfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025bfc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180025a3e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180025a65`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180025aa2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180025a3e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180025a65`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180025aa2`

## pseudocode

```c
__int64 __fastcall CMFSourceFilter::_CheckIfMPEG2TS(CMFSourceFilter *this, bool *a2, enum Mpeg2_TS_Flavor *a3)
{
  __int64 v6; // rcx
  int v7; // ebx
  unsigned __int64 v8; // rax
  int v9; // edx
  char *v10; // rsi
  LPCWCH lpString1; // [rsp+30h] [rbp-50h] BYREF
  _BYTE v13[8]; // [rsp+38h] [rbp-48h] BYREF
  __int64 v14; // [rsp+40h] [rbp-40h] BYREF
  int v15; // [rsp+48h] [rbp-38h] BYREF
  int v16; // [rsp+4Ch] [rbp-34h] BYREF
  char v17; // [rsp+50h] [rbp-30h]
  int v18; // [rsp+58h] [rbp-28h] BYREF
  char v19; // [rsp+5Ch] [rbp-24h]
  char v20; // [rsp+66h] [rbp-1Ah]
  char v21; // [rsp+6Ah] [rbp-16h]

  *a2 = 0;
  *(_DWORD *)a3 = 0;
  v6 = *((_QWORD *)this + 27);
  v7 = 0;
  lpString1 = 0;
  v15 = 0;
  if ( v6 )
  {
    v14 = 0;
    if ( (int)SafeQueryInterface<IMFAttributes>(v6, &v14) < 0 )
      goto LABEL_12;
    v7 = (*(__int64 (__fastcall **)(__int64, const IID *, LPCWCH *, int *))(*(_QWORD *)v14 + 104LL))(
           v14,
           &MF_BYTESTREAM_CONTENT_TYPE,
           &lpString1,
           &v15);
    if ( v7 < 0
      || !lpString1
      || CompareStringOrdinal(lpString1, -1, L"video/mpeg", -1, 1) == 2
      || CompareStringOrdinal(lpString1, -1, L"video/vnd.dlna.mpeg-tts", -1, 1) == 2 )
    {
      goto LABEL_12;
    }
    v8 = -1;
    do
      ++v8;
    while ( lpString1[v8] );
    v9 = 21;
    if ( v8 < 0x15 )
      v9 = v8;
    if ( CompareStringOrdinal(lpString1, v9, L"application/X-arib-cp", -1, 1) == 2 )
    {
LABEL_12:
      v10 = (char *)this + 256;
      v13[0] = 0;
      v7 = (*(__int64 (__fastcall **)(char *, _QWORD, __int64, int *))(*(_QWORD *)v10 + 56LL))(v10, 0, 19, &v18);
      if ( !v7 )
      {
        if ( (_BYTE)v18 == 71 )
        {
          v7 = (*(__int64 (__fastcall **)(char *, __int64, __int64, _BYTE *))(*(_QWORD *)v10 + 56LL))(v10, 188, 1, v13);
          if ( !v7 && v13[0] == 71 )
          {
            *a2 = 1;
            *(_DWORD *)a3 = 0;
          }
        }
        else if ( v19 == 71 )
        {
          v7 = (*(__int64 (__fastcall **)(char *, __int64, __int64, int *))(*(_QWORD *)v10 + 56LL))(v10, 192, 5, &v16);
          if ( !v7 && v17 == 71 )
          {
            if ( v18 || v16 )
              *(_DWORD *)a3 = 1;
            else
              *(_DWORD *)a3 = 2;
          }
        }
        else if ( !(_BYTE)v18 )
        {
          if ( v20 == 71 )
          {
            v7 = (*(__int64 (__fastcall **)(char *, __int64, __int64, _BYTE *))(*(_QWORD *)v10 + 56LL))(
                   v10,
                   202,
                   1,
                   v13);
            if ( !v7 && v13[0] == 71 )
              *(_DWORD *)a3 = 8;
          }
          else if ( v21 == 71 )
          {
            v7 = (*(__int64 (__fastcall **)(char *, __int64, __int64, _BYTE *))(*(_QWORD *)v10 + 56LL))(
                   v10,
                   210,
                   1,
                   v13);
            if ( !v7 && v13[0] == 71 )
              *(_DWORD *)a3 = 4;
          }
        }
      }
    }
    ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(&v14);
  }
  if ( (*(_BYTE *)a3 & 0xF) != 0 )
    *a2 = 1;
  CoTaskMemFree((LPVOID)lpString1);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180025984  mov     [rsp-38h+arg_18], rbx
0x180025989  push    rbp
0x18002598a  push    rsi
0x18002598b  push    rdi
0x18002598c  push    r12
0x18002598e  push    r13
0x180025990  push    r14
0x180025992  push    r15
0x180025994  mov     rbp, rsp
0x180025997  sub     rsp, 80h
0x18002599e  mov     rax, cs:__security_cookie
0x1800259a5  xor     rax, rsp
0x1800259a8  mov     [rbp+var_10], rax
0x1800259ac  xor     r15d, r15d
0x1800259af  mov     rsi, rcx
0x1800259b2  mov     [rdx], r15b
0x1800259b5  mov     rdi, r8
0x1800259b8  mov     [r8], r15d
0x1800259bb  mov     r14, rdx
0x1800259be  mov     rcx, [rcx+0D8h]
0x1800259c5  mov     ebx, r15d
0x1800259c8  mov     [rbp+lpString1], r15
0x1800259cc  lea     r13d, [r15+1]
0x1800259d0  mov     [rbp+var_38], r15d
0x1800259d4  test    rcx, rcx
0x1800259d7  jz      loc_180025BF0
0x1800259dd  lea     rdx, [rbp+var_40]
0x1800259e1  mov     [rbp+var_40], r15
0x1800259e5  call    ??$SafeQueryInterface@UIMFAttributes@@@@YAJPEAUIUnknown@@PEAPEAUIMFAttributes@@@Z
0x1800259ea  test    eax, eax
0x1800259ec  js      loc_180025AB7
0x1800259f2  mov     rcx, [rbp+var_40]
0x1800259f6  lea     r9, [rbp+var_38]
0x1800259fa  lea     r8, [rbp+lpString1]
0x1800259fe  lea     rdx, MF_BYTESTREAM_CONTENT_TYPE
0x180025a05  mov     rax, [rcx]
0x180025a08  mov     rax, [rax+68h]
0x180025a0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a11  mov     ebx, eax
0x180025a13  test    eax, eax
0x180025a15  js      loc_180025AB7
0x180025a1b  mov     rcx, [rbp+lpString1]; lpString1
0x180025a1f  test    rcx, rcx
0x180025a22  jz      loc_180025AB7
0x180025a28  or      r12, 0FFFFFFFFFFFFFFFFh
0x180025a2c  mov     [rsp+80h+bIgnoreCase], r13d; bIgnoreCase
0x180025a31  mov     r9d, r12d; cchCount2
0x180025a34  lea     r8, String2
0x180025a3b  mov     edx, r12d; cchCount1
0x180025a3e  call    cs:__imp_CompareStringOrdinal
0x180025a45  nop     dword ptr [rax+rax+00h]
0x180025a4a  cmp     eax, 2
0x180025a4d  jz      short loc_180025AB7
0x180025a4f  mov     rcx, [rbp+lpString1]; lpString1
0x180025a53  lea     r8, aVideoVndDlnaMp
0x180025a5a  mov     r9d, r12d; cchCount2
0x180025a5d  mov     [rsp+80h+bIgnoreCase], r13d; bIgnoreCase
0x180025a62  mov     edx, r12d; cchCount1
0x180025a65  call    cs:__imp_CompareStringOrdinal
0x180025a6c  nop     dword ptr [rax+rax+00h]
0x180025a71  cmp     eax, 2
0x180025a74  jz      short loc_180025AB7
0x180025a76  mov     rcx, [rbp+lpString1]; lpString1
0x180025a7a  mov     rax, r12
0x180025a7d  inc     rax
0x180025a80  cmp     [rcx+rax*2], r15w
0x180025a85  jnz     short loc_180025A7D
0x180025a87  mov     edx, 15h
0x180025a8c  mov     [rsp+80h+bIgnoreCase], r13d; bIgnoreCase
0x180025a91  cmp     rax, rdx
0x180025a94  lea     r8, aApplicationXAr
0x180025a9b  mov     r9d, r12d; cchCount2
0x180025a9e  cmovb   rdx, rax; cchCount1
0x180025aa2  call    cs:__imp_CompareStringOrdinal
0x180025aa9  nop     dword ptr [rax+rax+00h]
0x180025aae  cmp     eax, 2
0x180025ab1  jnz     loc_180025BE7
0x180025ab7  add     rsi, 100h
0x180025abe  mov     [rbp+var_48], r15b
0x180025ac2  xor     edx, edx
0x180025ac4  lea     r9, [rbp+var_28]
0x180025ac8  mov     rcx, rsi
0x180025acb  mov     rax, [rsi]
0x180025ace  lea     r8d, [rdx+13h]
0x180025ad2  mov     rax, [rax+38h]
0x180025ad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025adb  mov     ebx, eax
0x180025add  test    eax, eax
0x180025adf  jnz     loc_180025BE7
0x180025ae5  mov     eax, [rbp+var_28]
0x180025ae8  mov     r12b, 47h ; 'G'
0x180025aeb  cmp     al, r12b
0x180025aee  jnz     short loc_180025B2A
0x180025af0  mov     rax, [rsi]
0x180025af3  lea     r9, [rbp+var_48]
0x180025af7  mov     r8d, r13d
0x180025afa  mov     edx, 0BCh
0x180025aff  mov     rcx, rsi
0x180025b02  mov     rax, [rax+38h]
0x180025b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b0b  mov     ebx, eax
0x180025b0d  test    eax, eax
0x180025b0f  jnz     loc_180025BE7
0x180025b15  cmp     [rbp+var_48], r12b
0x180025b19  jnz     loc_180025BE7
0x180025b1f  mov     [r14], r13b
0x180025b22  mov     [rdi], r15d
0x180025b25  jmp     loc_180025BE7
0x180025b2a  cmp     [rbp+var_24], r12b
0x180025b2e  jnz     short loc_180025B7B
0x180025b30  mov     rax, [rsi]
0x180025b33  lea     r9, [rbp+var_34]
0x180025b37  mov     edx, 0C0h
0x180025b3c  mov     r8d, 5
0x180025b42  mov     rcx, rsi
0x180025b45  mov     rax, [rax+38h]
0x180025b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b4e  mov     ebx, eax
0x180025b50  test    eax, eax
0x180025b52  jnz     loc_180025BE7
0x180025b58  cmp     [rbp+var_30], r12b
0x180025b5c  jnz     loc_180025BE7
0x180025b62  cmp     [rbp+var_28], r15d
0x180025b66  jnz     short loc_180025B76
0x180025b68  cmp     [rbp+var_34], r15d
0x180025b6c  jnz     short loc_180025B76
0x180025b6e  mov     dword ptr [rdi], 2
0x180025b74  jmp     short loc_180025BE7
0x180025b76  mov     [rdi], r13d
0x180025b79  jmp     short loc_180025BE7
0x180025b7b  test    al, al
0x180025b7d  jnz     short loc_180025BE7
0x180025b7f  cmp     [rbp+var_1A], r12b
0x180025b83  jnz     short loc_180025BB4
0x180025b85  mov     rax, [rsi]
0x180025b88  lea     r9, [rbp+var_48]
0x180025b8c  mov     r8d, r13d
0x180025b8f  mov     edx, 0CAh
0x180025b94  mov     rcx, rsi
0x180025b97  mov     rax, [rax+38h]
0x180025b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ba0  mov     ebx, eax
0x180025ba2  test    eax, eax
0x180025ba4  jnz     short loc_180025BE7
0x180025ba6  cmp     [rbp+var_48], r12b
0x180025baa  jnz     short loc_180025BE7
0x180025bac  mov     dword ptr [rdi], 8
0x180025bb2  jmp     short loc_180025BE7
0x180025bb4  cmp     [rbp+var_16], r12b
0x180025bb8  jnz     short loc_180025BE7
0x180025bba  mov     rax, [rsi]
0x180025bbd  lea     r9, [rbp+var_48]
0x180025bc1  mov     r8d, r13d
0x180025bc4  mov     edx, 0D2h
0x180025bc9  mov     rcx, rsi
0x180025bcc  mov     rax, [rax+38h]
0x180025bd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025bd5  mov     ebx, eax
0x180025bd7  test    eax, eax
0x180025bd9  jnz     short loc_180025BE7
0x180025bdb  cmp     [rbp+var_48], r12b
0x180025bdf  jnz     short loc_180025BE7
0x180025be1  mov     dword ptr [rdi], 4
0x180025be7  lea     rcx, [rbp+var_40]; void *
0x180025beb  call    ??1?$CComPtrBase@UIMediaSeeking@@@ATL@@QEAA@XZ
0x180025bf0  test    byte ptr [rdi], 0Fh
0x180025bf3  jz      short loc_180025BF8
0x180025bf5  mov     [r14], r13b
0x180025bf8  mov     rcx, [rbp+lpString1]; pv
0x180025bfc  call    cs:__imp_CoTaskMemFree
0x180025c03  nop     dword ptr [rax+rax+00h]
0x180025c08  mov     eax, ebx
0x180025c0a  mov     rcx, [rbp+var_10]
0x180025c0e  xor     rcx, rsp; StackCookie
0x180025c11  call    __security_check_cookie
0x180025c16  mov     rbx, [rsp+80h+arg_18]
0x180025c1e  add     rsp, 80h
0x180025c25  pop     r15
0x180025c27  pop     r14
0x180025c29  pop     r13
0x180025c2b  pop     r12
0x180025c2d  pop     rdi
0x180025c2e  pop     rsi
0x180025c2f  pop     rbp
0x180025c30  retn
```
