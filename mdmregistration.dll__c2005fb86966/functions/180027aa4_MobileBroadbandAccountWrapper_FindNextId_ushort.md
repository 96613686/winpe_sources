# MobileBroadbandAccountWrapper::FindNextId(ushort * *)

- ea: `0x180027aa4`
- end: `0x180027e06`
- name: `?FindNextId@MobileBroadbandAccountWrapper@@QEAAJPEAPEAG@Z`
- size: `866`
- prototype: `__int64 __fastcall(MobileBroadbandAccountWrapper *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180022e74`

## callees

- `0x180027aa4`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180027d23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180027d23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180027ba5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180027ba5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027af1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027b03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027b12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027bc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027c24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027d44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027d55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027d67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027d76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027af1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027b03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027b12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027bc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027c24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027d44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027d55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027d67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027d76`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180027c75`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180027c75`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall MobileBroadbandAccountWrapper::FindNextId(HSTRING *this, PCWSTR *a2)
{
  HSTRING v4; // rbx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  HRESULT ActivationFactory; // edi
  HSTRING v10; // r15
  HSTRING v11; // rdi
  __int64 (__fastcall *v12)(HSTRING, _QWORD, __int64 *); // rsi
  __int64 v13; // rcx
  __int64 v14; // rsi
  __int64 (__fastcall *v15)(__int64, HSTRING *); // rdi
  __int64 v16; // rcx
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, HSTRING, __int64 *); // rsi
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // [rsp+20h] [rbp-30h] BYREF
  HSTRING v25; // [rsp+28h] [rbp-28h] BYREF
  HSTRING string[4]; // [rsp+30h] [rbp-20h] BYREF
  __int64 v27; // [rsp+90h] [rbp+40h] BYREF
  __int64 v28; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v29; // [rsp+A8h] [rbp+58h] BYREF

  v24 = 0;
  v29 = 0;
  v28 = 0;
  v27 = 0;
  string[1] = 0;
  string[2] = 0;
  v25 = 0;
  v4 = 0;
  if ( *((_DWORD *)this + 5) <= *((_DWORD *)this + 4) )
  {
    string[0] = 0;
    ActivationFactory = WindowsCreateString(L"Windows.Networking.NetworkOperators.MobileBroadbandModem", 0x38u, string);
    if ( ActivationFactory < 0 )
    {
      v10 = 0;
    }
    else
    {
      v4 = string[0];
      string[3] = string[0];
      WindowsDeleteString(0);
      v10 = v4;
      v11 = *this;
      v12 = *(__int64 (__fastcall **)(HSTRING, _QWORD, __int64 *))(*(_QWORD *)*this + 48LL);
      v13 = v29;
      if ( v29 )
      {
        v29 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
      ActivationFactory = v12(v11, *((unsigned int *)this + 5), &v29);
      if ( ActivationFactory >= 0 )
      {
        v14 = v29;
        v15 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v29 + 48LL);
        WindowsDeleteString(v25);
        v25 = 0;
        ActivationFactory = v15(v14, &v25);
        if ( ActivationFactory >= 0 )
        {
          v16 = v28;
          if ( v28 )
          {
            v28 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
          }
          ActivationFactory = RoGetActivationFactory(v4, &GUID_f99ed637_d6f1_4a78_8cbc_6421a65063c8, &v28);
          if ( ActivationFactory >= 0 )
          {
            v17 = v28;
            v18 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v28 + 56LL);
            v19 = v27;
            if ( v27 )
            {
              v27 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
            }
            ActivationFactory = v18(v17, v25, &v27);
            if ( ActivationFactory >= 0 )
            {
              ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 56LL))(v27, &v24);
              if ( ActivationFactory >= 0 )
              {
                ActivationFactory = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v24 + 104LL))(
                                      v24,
                                      (char *)this + 24);
                if ( ActivationFactory >= 0 )
                  *a2 = WindowsGetStringRawBuffer(this[3], 0);
              }
            }
          }
        }
      }
    }
    ++*((_DWORD *)this + 5);
    if ( v10 )
      WindowsDeleteString(v4);
    WindowsDeleteString(v25);
    v25 = 0;
    WindowsDeleteString(0);
    WindowsDeleteString(0);
    v20 = v27;
    if ( v27 )
    {
      v27 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    v21 = v28;
    if ( v28 )
    {
      v28 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    v22 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    v23 = v24;
    if ( v24 )
    {
      v24 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    return (unsigned int)ActivationFactory;
  }
  else
  {
    WindowsDeleteString(0);
    v25 = 0;
    WindowsDeleteString(0);
    WindowsDeleteString(0);
    v5 = v27;
    if ( v27 )
    {
      v27 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    v6 = v28;
    if ( v28 )
    {
      v28 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    v7 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    return 2147942418LL;
  }
}

```

## disassembly

```asm
0x180027aa4  mov     [rsp-38h+arg_8], rbx
0x180027aa9  push    rbp
0x180027aaa  push    rsi
0x180027aab  push    rdi
0x180027aac  push    r12
0x180027aae  push    r13
0x180027ab0  push    r14
0x180027ab2  push    r15
0x180027ab4  mov     rbp, rsp
0x180027ab7  sub     rsp, 50h
0x180027abb  mov     r12, rdx
0x180027abe  mov     r14, rcx
0x180027ac1  xor     r13d, r13d
0x180027ac4  mov     [rbp+var_30], r13
0x180027ac8  mov     [rbp+arg_18], r13
0x180027acc  mov     [rbp+arg_10], r13
0x180027ad0  mov     [rbp+arg_0], r13
0x180027ad4  mov     [rbp+var_18], r13
0x180027ad8  mov     [rbp+var_10], r13
0x180027adc  mov     [rbp+var_28], r13
0x180027ae0  mov     ebx, r13d
0x180027ae3  mov     eax, [rcx+10h]
0x180027ae6  cmp     [rcx+14h], eax
0x180027ae9  jbe     loc_180027B91
0x180027aef  xor     ecx, ecx; string
0x180027af1  call    cs:__imp_WindowsDeleteString
0x180027af8  nop     dword ptr [rax+rax+00h]
0x180027afd  mov     [rbp+var_28], r13
0x180027b01  xor     ecx, ecx; string
0x180027b03  call    cs:__imp_WindowsDeleteString
0x180027b0a  nop     dword ptr [rax+rax+00h]
0x180027b0f  nop
0x180027b10  xor     ecx, ecx; string
0x180027b12  call    cs:__imp_WindowsDeleteString
0x180027b19  nop     dword ptr [rax+rax+00h]
0x180027b1e  nop
0x180027b1f  mov     rcx, [rbp+arg_0]
0x180027b23  test    rcx, rcx
0x180027b26  jz      short loc_180027B39
0x180027b28  mov     [rbp+arg_0], r13
0x180027b2c  mov     rax, [rcx]
0x180027b2f  mov     rax, [rax+10h]
0x180027b33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b38  nop
0x180027b39  mov     rcx, [rbp+arg_10]
0x180027b3d  test    rcx, rcx
0x180027b40  jz      short loc_180027B53
0x180027b42  mov     [rbp+arg_10], r13
0x180027b46  mov     rax, [rcx]
0x180027b49  mov     rax, [rax+10h]
0x180027b4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b52  nop
0x180027b53  mov     rcx, [rbp+arg_18]
0x180027b57  test    rcx, rcx
0x180027b5a  jz      short loc_180027B6D
0x180027b5c  mov     [rbp+arg_18], r13
0x180027b60  mov     rax, [rcx]
0x180027b63  mov     rax, [rax+10h]
0x180027b67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b6c  nop
0x180027b6d  mov     rcx, [rbp+var_30]
0x180027b71  test    rcx, rcx
0x180027b74  jz      short loc_180027B87
0x180027b76  mov     [rbp+var_30], r13
0x180027b7a  mov     rax, [rcx]
0x180027b7d  mov     rax, [rax+10h]
0x180027b81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b86  nop
0x180027b87  mov     eax, 80070012h
0x180027b8c  jmp     loc_180027DED
0x180027b91  mov     [rbp+string], r13
0x180027b95  lea     r8, [rbp+string]; string
0x180027b99  mov     edx, 38h ; '8'; length
0x180027b9e  lea     rcx, ?RuntimeClass_Windows_Networking_NetworkOperators_MobileBroadbandModem@@3QBGB; "Windows.Networking.NetworkOperators.Mob"...
0x180027ba5  call    cs:__imp_WindowsCreateString
0x180027bac  nop     dword ptr [rax+rax+00h]
0x180027bb1  mov     edi, eax
0x180027bb3  test    eax, eax
0x180027bb5  js      loc_180027D35
0x180027bbb  mov     rbx, [rbp+string]
0x180027bbf  mov     [rbp+var_8], rbx
0x180027bc3  xor     ecx, ecx; string
0x180027bc5  call    cs:__imp_WindowsDeleteString
0x180027bcc  nop     dword ptr [rax+rax+00h]
0x180027bd1  mov     r15, rbx
0x180027bd4  mov     rdi, [r14]
0x180027bd7  mov     rax, [rdi]
0x180027bda  mov     rsi, [rax+30h]
0x180027bde  mov     rcx, [rbp+arg_18]
0x180027be2  test    rcx, rcx
0x180027be5  jz      short loc_180027BF8
0x180027be7  mov     [rbp+arg_18], r13
0x180027beb  mov     rdx, [rcx]
0x180027bee  mov     rax, [rdx+10h]
0x180027bf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027bf7  nop
0x180027bf8  lea     r8, [rbp+arg_18]
0x180027bfc  mov     edx, [r14+14h]
0x180027c00  mov     rcx, rdi
0x180027c03  mov     rax, rsi
0x180027c06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c0b  mov     edi, eax
0x180027c0d  test    eax, eax
0x180027c0f  js      loc_180027D38
0x180027c15  mov     rsi, [rbp+arg_18]
0x180027c19  mov     rax, [rsi]
0x180027c1c  mov     rdi, [rax+30h]
0x180027c20  mov     rcx, [rbp+var_28]; string
0x180027c24  call    cs:__imp_WindowsDeleteString
0x180027c2b  nop     dword ptr [rax+rax+00h]
0x180027c30  mov     [rbp+var_28], r13
0x180027c34  lea     rdx, [rbp+var_28]
0x180027c38  mov     rcx, rsi
0x180027c3b  mov     rax, rdi
0x180027c3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c43  mov     edi, eax
0x180027c45  test    eax, eax
0x180027c47  js      loc_180027D38
0x180027c4d  mov     rcx, [rbp+arg_10]
0x180027c51  test    rcx, rcx
0x180027c54  jz      short loc_180027C67
0x180027c56  mov     [rbp+arg_10], r13
0x180027c5a  mov     rax, [rcx]
0x180027c5d  mov     rax, [rax+10h]
0x180027c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c66  nop
0x180027c67  lea     r8, [rbp+arg_10]
0x180027c6b  lea     rdx, _GUID_f99ed637_d6f1_4a78_8cbc_6421a65063c8
0x180027c72  mov     rcx, rbx
0x180027c75  call    cs:__imp_RoGetActivationFactory
0x180027c7c  nop     dword ptr [rax+rax+00h]
0x180027c81  mov     edi, eax
0x180027c83  test    eax, eax
0x180027c85  js      loc_180027D38
0x180027c8b  mov     rdi, [rbp+arg_10]
0x180027c8f  mov     rax, [rdi]
0x180027c92  mov     rsi, [rax+38h]
0x180027c96  mov     rcx, [rbp+arg_0]
0x180027c9a  test    rcx, rcx
0x180027c9d  jz      short loc_180027CB0
0x180027c9f  mov     [rbp+arg_0], r13
0x180027ca3  mov     rdx, [rcx]
0x180027ca6  mov     rax, [rdx+10h]
0x180027caa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027caf  nop
0x180027cb0  lea     r8, [rbp+arg_0]
0x180027cb4  mov     rdx, [rbp+var_28]
0x180027cb8  mov     rcx, rdi
0x180027cbb  mov     rax, rsi
0x180027cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027cc3  mov     edi, eax
0x180027cc5  test    eax, eax
0x180027cc7  js      short loc_180027D38
0x180027cc9  mov     rdi, [rbp+arg_0]
0x180027ccd  mov     rax, [rdi]
0x180027cd0  mov     rsi, [rax+38h]
0x180027cd4  mov     rcx, [rbp+var_30]
0x180027cd8  test    rcx, rcx
0x180027cdb  jz      short loc_180027CEE
0x180027cdd  mov     [rbp+var_30], r13
0x180027ce1  mov     rdx, [rcx]
0x180027ce4  mov     rax, [rdx+10h]
0x180027ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ced  nop
0x180027cee  lea     rdx, [rbp+var_30]
0x180027cf2  mov     rcx, rdi
0x180027cf5  mov     rax, rsi
0x180027cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027cfd  mov     edi, eax
0x180027cff  test    eax, eax
0x180027d01  js      short loc_180027D38
0x180027d03  mov     rcx, [rbp+var_30]
0x180027d07  mov     rax, [rcx]
0x180027d0a  lea     rdx, [r14+18h]
0x180027d0e  mov     rax, [rax+68h]
0x180027d12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d17  mov     edi, eax
0x180027d19  test    eax, eax
0x180027d1b  js      short loc_180027D38
0x180027d1d  xor     edx, edx; length
0x180027d1f  mov     rcx, [r14+18h]; string
0x180027d23  call    cs:__imp_WindowsGetStringRawBuffer
0x180027d2a  nop     dword ptr [rax+rax+00h]
0x180027d2f  mov     [r12], rax
0x180027d33  jmp     short loc_180027D38
0x180027d35  mov     r15, r13
0x180027d38  inc     dword ptr [r14+14h]
0x180027d3c  test    r15, r15
0x180027d3f  jz      short loc_180027D51
0x180027d41  mov     rcx, rbx; string
0x180027d44  call    cs:__imp_WindowsDeleteString
0x180027d4b  nop     dword ptr [rax+rax+00h]
0x180027d50  nop
0x180027d51  mov     rcx, [rbp+var_28]; string
0x180027d55  call    cs:__imp_WindowsDeleteString
0x180027d5c  nop     dword ptr [rax+rax+00h]
0x180027d61  mov     [rbp+var_28], r13
0x180027d65  xor     ecx, ecx; string
0x180027d67  call    cs:__imp_WindowsDeleteString
0x180027d6e  nop     dword ptr [rax+rax+00h]
0x180027d73  nop
0x180027d74  xor     ecx, ecx; string
0x180027d76  call    cs:__imp_WindowsDeleteString
0x180027d7d  nop     dword ptr [rax+rax+00h]
0x180027d82  nop
0x180027d83  mov     rcx, [rbp+arg_0]
0x180027d87  test    rcx, rcx
0x180027d8a  jz      short loc_180027D9D
0x180027d8c  mov     [rbp+arg_0], r13
0x180027d90  mov     rax, [rcx]
0x180027d93  mov     rax, [rax+10h]
0x180027d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d9c  nop
0x180027d9d  mov     rcx, [rbp+arg_10]
0x180027da1  test    rcx, rcx
0x180027da4  jz      short loc_180027DB7
0x180027da6  mov     [rbp+arg_10], r13
0x180027daa  mov     rax, [rcx]
0x180027dad  mov     rax, [rax+10h]
0x180027db1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027db6  nop
0x180027db7  mov     rcx, [rbp+arg_18]
0x180027dbb  test    rcx, rcx
0x180027dbe  jz      short loc_180027DD1
0x180027dc0  mov     [rbp+arg_18], r13
0x180027dc4  mov     rax, [rcx]
0x180027dc7  mov     rax, [rax+10h]
0x180027dcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027dd0  nop
0x180027dd1  mov     rcx, [rbp+var_30]
0x180027dd5  test    rcx, rcx
0x180027dd8  jz      short loc_180027DEB
0x180027dda  mov     [rbp+var_30], r13
0x180027dde  mov     rax, [rcx]
0x180027de1  mov     rax, [rax+10h]
0x180027de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027dea  nop
0x180027deb  mov     eax, edi
0x180027ded  mov     rbx, [rsp+50h+arg_8]
0x180027df5  add     rsp, 50h
0x180027df9  pop     r15
0x180027dfb  pop     r14
0x180027dfd  pop     r13
0x180027dff  pop     r12
0x180027e01  pop     rdi
0x180027e02  pop     rsi
0x180027e03  pop     rbp
0x180027e04  retn
```
