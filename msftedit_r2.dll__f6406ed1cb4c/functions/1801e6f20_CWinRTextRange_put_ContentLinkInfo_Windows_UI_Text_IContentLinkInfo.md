# CWinRTextRange::put_ContentLinkInfo(Windows::UI::Text::IContentLinkInfo *)

- ea: `0x1801e6f20`
- end: `0x1801e7152`
- name: `?put_ContentLinkInfo@CWinRTextRange@@UEAAJPEAUIContentLinkInfo@Text@UI@Windows@@@Z`
- size: `562`
- prototype: `__int64 __fastcall(CWinRTextRange *__hidden this, struct Windows::UI::Text::IContentLinkInfo *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180043e7c`
- `0x18006ad18`
- `0x180138ae4`
- `0x1801e4254`
- `0x1801e6f20`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e7097`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e70b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e7097`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801e70b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e7123`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e7123`

## pseudocode

```c
__int64 __fastcall CWinRTextRange::put_ContentLinkInfo(
        CWinRTextRange *this,
        struct Windows::UI::Text::IContentLinkInfo *a2)
{
  char *v5; // r14
  void (__fastcall ***v6)(_QWORD, GUID *, __int64 *); // rdi
  void (__fastcall *v7)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v8; // rax
  void (__fastcall *v9)(struct Windows::UI::Text::IContentLinkInfo *, __int64 *); // rax
  __int64 v10; // rax
  __int64 v11; // rax
  const unsigned __int16 *StringRawBuffer; // rax
  const unsigned __int16 *v13; // rax
  unsigned int v14; // ebx
  HSTRING string; // [rsp+30h] [rbp-29h] BYREF
  __int64 v16; // [rsp+38h] [rbp-21h] BYREF
  __int64 v17; // [rsp+40h] [rbp-19h] BYREF
  HSTRING v18; // [rsp+48h] [rbp-11h] BYREF
  __int64 v19; // [rsp+50h] [rbp-9h] BYREF
  __int128 v20; // [rsp+58h] [rbp-1h] BYREF
  unsigned __int16 *v21[2]; // [rsp+68h] [rbp+Fh] BYREF
  unsigned __int16 *v22; // [rsp+78h] [rbp+1Fh]
  _QWORD v23[6]; // [rsp+80h] [rbp+27h] BYREF
  unsigned int v24; // [rsp+C8h] [rbp+6Fh] BYREF
  unsigned int v25; // [rsp+D0h] [rbp+77h] BYREF
  __int64 v26; // [rsp+D8h] [rbp+7Fh] BYREF

  if ( !a2 )
    return 2147942487LL;
  v5 = (char *)this - 16;
  v26 = 0;
  v6 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 4);
  v7 = **v6;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  v7(v6, &GUID_8d33f741_cf58_11ce_a89d_00aa006cadc5, &v26);
  v8 = *(_QWORD *)a2;
  v16 = 0;
  string = 0;
  v17 = 0;
  v9 = *(void (__fastcall **)(struct Windows::UI::Text::IContentLinkInfo *, __int64 *))(v8 + 64);
  v18 = 0;
  v19 = 0;
  v9(a2, &v17);
  (*(void (__fastcall **)(struct Windows::UI::Text::IContentLinkInfo *, HSTRING *))(*(_QWORD *)a2 + 80LL))(a2, &v18);
  (*(void (__fastcall **)(struct Windows::UI::Text::IContentLinkInfo *, __int64 *))(*(_QWORD *)a2 + 96LL))(a2, &v16);
  (*(void (__fastcall **)(struct Windows::UI::Text::IContentLinkInfo *, __int64 *))(*(_QWORD *)a2 + 112LL))(a2, &v19);
  (*(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v16 + 128LL))(v16, &string);
  if ( v17 )
    (*(void (__fastcall **)(char *, _QWORD))(*(_QWORD *)v5 + 440LL))(v5, 0);
  v10 = *(_QWORD *)v5;
  v24 = 0;
  v25 = 0;
  (*(void (__fastcall **)(char *, unsigned int *))(v10 + 168))(v5, &v24);
  (*(void (__fastcall **)(char *, unsigned int *))(*(_QWORD *)v5 + 96LL))(v5, &v25);
  v22 = 0;
  v20 = 0;
  *(_QWORD *)((char *)&v20 + 4) = __PAIR64__(v25, v24);
  v11 = *(_QWORD *)a2;
  *(_OWORD *)v21 = 0;
  (*(void (__fastcall **)(struct Windows::UI::Text::IContentLinkInfo *, unsigned __int16 **))(v11 + 48))(a2, v21);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v21[1] = CW32System::SysAllocString(StringRawBuffer);
  v13 = WindowsGetStringRawBuffer(v18, 0);
  v22 = CW32System::SysAllocString(v13);
  CWinRTContentLinkInfo::GetLinkContentKindEnum((char *)this + 40, v19, (char *)&v20 + 12);
  v23[0] = 0;
  v14 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int128 *, _QWORD *))(*(_QWORD *)v26 + 24LL))(
          v26,
          1390,
          0,
          &v20,
          v23);
  CW32System::SysFreeString(v21[1]);
  CW32System::SysFreeString(v22);
  WindowsDeleteString(string);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  return v14;
}

```

## disassembly

```asm
0x1801e6f20  mov     [rsp-8+arg_0], rbx
0x1801e6f25  push    rbp
0x1801e6f26  push    rsi
0x1801e6f27  push    rdi
0x1801e6f28  push    r14
0x1801e6f2a  push    r15
0x1801e6f2c  lea     rbp, [rsp-37h]
0x1801e6f31  sub     rsp, 90h
0x1801e6f38  mov     rsi, rdx
0x1801e6f3b  mov     r15, rcx
0x1801e6f3e  test    rdx, rdx
0x1801e6f41  jnz     short loc_1801E6F4D
0x1801e6f43  mov     eax, 80070057h
0x1801e6f48  jmp     loc_1801E713A
0x1801e6f4d  lea     r14, [rcx-10h]
0x1801e6f51  mov     [rbp+57h+arg_18], 0
0x1801e6f59  mov     rdi, [r14+30h]
0x1801e6f5d  lea     rcx, [rbp+57h+arg_18]
0x1801e6f61  mov     rax, [rdi]
0x1801e6f64  mov     rbx, [rax]
0x1801e6f67  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801e6f6c  lea     r8, [rbp+57h+arg_18]
0x1801e6f70  mov     rcx, rdi
0x1801e6f73  lea     rdx, _GUID_8d33f741_cf58_11ce_a89d_00aa006cadc5
0x1801e6f7a  mov     rax, rbx
0x1801e6f7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e6f82  mov     rax, [rsi]
0x1801e6f85  lea     rdx, [rbp+57h+var_70]
0x1801e6f89  mov     rcx, rsi
0x1801e6f8c  mov     [rbp+57h+var_78], 0
0x1801e6f94  mov     [rbp+57h+string], 0
0x1801e6f9c  mov     [rbp+57h+var_70], 0
0x1801e6fa4  mov     rax, [rax+40h]
0x1801e6fa8  mov     [rbp+57h+var_68], 0
0x1801e6fb0  mov     [rbp+57h+var_60], 0
0x1801e6fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e6fbd  mov     rax, [rsi]
0x1801e6fc0  lea     rdx, [rbp+57h+var_68]
0x1801e6fc4  mov     rcx, rsi
0x1801e6fc7  mov     rax, [rax+50h]
0x1801e6fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e6fd0  mov     rax, [rsi]
0x1801e6fd3  lea     rdx, [rbp+57h+var_78]
0x1801e6fd7  mov     rcx, rsi
0x1801e6fda  mov     rax, [rax+60h]
0x1801e6fde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e6fe3  mov     rax, [rsi]
0x1801e6fe6  lea     rdx, [rbp+57h+var_60]
0x1801e6fea  mov     rcx, rsi
0x1801e6fed  mov     rax, [rax+70h]
0x1801e6ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e6ff6  mov     rcx, [rbp+57h+var_78]
0x1801e6ffa  lea     rdx, [rbp+57h+string]
0x1801e6ffe  mov     rax, [rcx]
0x1801e7001  mov     rax, [rax+80h]
0x1801e7008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e700d  mov     r8, [rbp+57h+var_70]
0x1801e7011  test    r8, r8
0x1801e7014  jz      short loc_1801E702A
0x1801e7016  mov     rax, [r14]
0x1801e7019  xor     edx, edx
0x1801e701b  mov     rcx, r14
0x1801e701e  mov     rax, [rax+1B8h]
0x1801e7025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e702a  mov     rax, [r14]
0x1801e702d  lea     rdx, [rbp+57h+arg_8]
0x1801e7031  mov     rcx, r14
0x1801e7034  mov     [rbp+57h+arg_8], 0
0x1801e703b  mov     [rbp+57h+arg_10], 0
0x1801e7042  mov     rax, [rax+0A8h]
0x1801e7049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e704e  mov     rax, [r14]
0x1801e7051  lea     rdx, [rbp+57h+arg_10]
0x1801e7055  mov     rcx, r14
0x1801e7058  mov     rax, [rax+60h]
0x1801e705c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e7061  xor     eax, eax
0x1801e7063  lea     rdx, [rbp+57h+var_48]
0x1801e7067  mov     [rbp+57h+var_38], rax
0x1801e706b  xorps   xmm0, xmm0
0x1801e706e  mov     eax, [rbp+57h+arg_8]
0x1801e7071  mov     rcx, rsi
0x1801e7074  movups  [rbp+57h+var_58], xmm0
0x1801e7078  mov     dword ptr [rbp+57h+var_58+4], eax
0x1801e707b  mov     eax, [rbp+57h+arg_10]
0x1801e707e  mov     dword ptr [rbp+57h+var_58+8], eax
0x1801e7081  mov     rax, [rsi]
0x1801e7084  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x1801e7088  mov     rax, [rax+30h]
0x1801e708c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e7091  mov     rcx, [rbp+57h+string]; string
0x1801e7095  xor     edx, edx; length
0x1801e7097  call    cs:__imp_WindowsGetStringRawBuffer
0x1801e709e  nop     dword ptr [rax+rax+00h]
0x1801e70a3  mov     rcx, rax; unsigned __int16 *
0x1801e70a6  call    ?SysAllocString@CW32System@@SAPEAGPEBG@Z; CW32System::SysAllocString(ushort const *)
0x1801e70ab  mov     rcx, [rbp+57h+var_68]; string
0x1801e70af  xor     edx, edx; length
0x1801e70b1  mov     [rbp+57h+var_48+8], rax
0x1801e70b5  call    cs:__imp_WindowsGetStringRawBuffer
0x1801e70bc  nop     dword ptr [rax+rax+00h]
0x1801e70c1  mov     rcx, rax; unsigned __int16 *
0x1801e70c4  call    ?SysAllocString@CW32System@@SAPEAGPEBG@Z; CW32System::SysAllocString(ushort const *)
0x1801e70c9  mov     rdx, [rbp+57h+var_60]
0x1801e70cd  lea     rcx, [r15+28h]
0x1801e70d1  lea     r8, [rbp+57h+var_58+0Ch]
0x1801e70d5  mov     [rbp+57h+var_38], rax
0x1801e70d9  call    ?GetLinkContentKindEnum@CWinRTContentLinkInfo@@SAJQEBU?$pair@IV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAUHSTRING__@@PEAI@Z; CWinRTContentLinkInfo::GetLinkContentKindEnum(std::pair<uint,std::wstring> const * const,HSTRING__ *,uint *)
0x1801e70de  mov     rcx, [rbp+57h+arg_18]
0x1801e70e2  lea     rdx, [rbp+57h+var_30]
0x1801e70e6  mov     [rbp+57h+var_30], 0
0x1801e70ee  lea     r9, [rbp+57h+var_58]
0x1801e70f2  mov     [rsp+0B0h+var_90], rdx
0x1801e70f7  xor     r8d, r8d
0x1801e70fa  mov     edx, 56Eh
0x1801e70ff  mov     rax, [rcx]
0x1801e7102  mov     rax, [rax+18h]
0x1801e7106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e710b  mov     rcx, [rbp+57h+var_48+8]; unsigned __int16 *
0x1801e710f  mov     ebx, eax
0x1801e7111  call    ?SysFreeString@CW32System@@SAXPEAG@Z; CW32System::SysFreeString(ushort *)
0x1801e7116  mov     rcx, [rbp+57h+var_38]; unsigned __int16 *
0x1801e711a  call    ?SysFreeString@CW32System@@SAXPEAG@Z; CW32System::SysFreeString(ushort *)
0x1801e711f  mov     rcx, [rbp+57h+string]; string
0x1801e7123  call    cs:__imp_WindowsDeleteString
0x1801e712a  nop     dword ptr [rax+rax+00h]
0x1801e712f  lea     rcx, [rbp+57h+arg_18]
0x1801e7133  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801e7138  mov     eax, ebx
0x1801e713a  mov     rbx, [rsp+0B0h+arg_0]
0x1801e7142  add     rsp, 90h
0x1801e7149  pop     r15
0x1801e714b  pop     r14
0x1801e714d  pop     rdi
0x1801e714e  pop     rsi
0x1801e714f  pop     rbp
0x1801e7150  retn
```
