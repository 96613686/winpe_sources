# CXmlHelper::CXmlHelper(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x1800f6aa4`
- end: `0x1800f6ca5`
- name: `??0CXmlHelper@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `513`
- prototype: `__int64 __fastcall(void **ppvObject)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800dac60`

## callees

- `0x18000933c`
- `0x18000cea4`
- `0x18000ef98`
- `0x1800a979c`
- `0x1800f6aa4`
- `0x1800f82f0`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800f6b58`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800f6b58`
- `XmlLite!CreateXmlReader` at `0x1800f6b1f`
- `XmlLite!CreateXmlReader` at `0x1800f6b1f`

## string_xrefs

- `0x1800f6bc7`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\XmlHelper.cpp`
- `0x1800f6c54`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\XmlHelper.cpp`
- `0x1800f6c69`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\XmlHelper.cpp`
- `0x1800f6c7e`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\XmlHelper.cpp`
- `0x1800f6c93`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\XmlHelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void **__fastcall CXmlHelper::CXmlHelper(void **ppvObject, _QWORD *a2)
{
  LPSTREAM *v3; // r14
  __int64 v4; // r8
  void *v5; // rcx
  HRESULT XmlReader; // eax
  LPSTREAM v7; // rcx
  HRESULT StreamOnHGlobal; // eax
  _QWORD *v9; // rdx
  int v10; // eax
  int v11; // eax
  int v12; // edi
  __int64 v13; // rdx
  int v15; // [rsp+20h] [rbp-58h]
  _QWORD v16[2]; // [rsp+40h] [rbp-38h] BYREF
  int v17; // [rsp+50h] [rbp-28h]
  unsigned __int64 v18; // [rsp+58h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  *ppvObject = 0;
  v3 = (LPSTREAM *)(ppvObject + 1);
  ppvObject[1] = 0;
  v4 = a2[2];
  if ( a2[3] > 0xFu )
    a2 = (_QWORD *)*a2;
  UTF8toWstr(v16, a2, v4);
  v5 = *ppvObject;
  if ( *ppvObject )
  {
    *ppvObject = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v5 + 16LL))(v5);
  }
  XmlReader = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, ppvObject, 0);
  if ( XmlReader < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\XmlHelper.cpp",
      (const char *)(unsigned int)XmlReader,
      v15);
  v7 = *v3;
  if ( *v3 )
  {
    *v3 = 0;
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v7 + 16LL))(v7);
  }
  StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, v3);
  if ( StreamOnHGlobal < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\XmlHelper.cpp",
      (const char *)(unsigned int)StreamOnHGlobal,
      v15);
  v9 = v16;
  if ( v18 > 7 )
    v9 = (_QWORD *)v16[0];
  v10 = (*(__int64 (__fastcall **)(LPSTREAM, _QWORD *, _QWORD, _QWORD))(*(_QWORD *)*v3 + 32LL))(
          *v3,
          v9,
          (unsigned int)(2 * v17),
          0);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\XmlHelper.cpp",
      (const char *)(unsigned int)v10,
      v15);
  v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*ppvObject + 24LL))(*ppvObject, 0);
  v12 = v11;
  if ( v11 < 0 )
  {
    v13 = 20;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\XmlHelper.cpp",
      (const char *)(unsigned int)v11,
      v15);
    goto LABEL_20;
  }
  v11 = (*(__int64 (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)*v3 + 40LL))(*v3, 0, 0, 0);
  v12 = v11;
  if ( v11 < 0 )
  {
    v13 = 22;
    goto LABEL_14;
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD, LPSTREAM))(*(_QWORD *)*ppvObject + 24LL))(*ppvObject, *v3);
  v12 = v11;
  if ( v11 < 0 )
  {
    v13 = 23;
    goto LABEL_14;
  }
  v12 = 0;
LABEL_20:
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\XmlHelper.cpp",
      (const char *)(unsigned int)v12,
      v15);
  std::wstring::~wstring(v16);
  return ppvObject;
}

```

## disassembly

```asm
0x1800f6aa4  mov     [rsp+arg_10], rsi
0x1800f6aa9  mov     [rsp+arg_18], rdi
0x1800f6aae  push    r14
0x1800f6ab0  sub     rsp, 70h
0x1800f6ab4  mov     rax, cs:__security_cookie
0x1800f6abb  xor     rax, rsp
0x1800f6abe  mov     [rsp+78h+var_18], rax
0x1800f6ac3  mov     rsi, rcx
0x1800f6ac6  mov     [rsp+78h+var_40], rcx
0x1800f6acb  mov     qword ptr [rcx], 0
0x1800f6ad2  lea     r14, [rcx+8]
0x1800f6ad6  mov     qword ptr [r14], 0
0x1800f6add  mov     r8, [rdx+10h]
0x1800f6ae1  cmp     qword ptr [rdx+18h], 0Fh
0x1800f6ae6  jbe     short loc_1800F6AEB
0x1800f6ae8  mov     rdx, [rdx]
0x1800f6aeb  lea     rcx, [rsp+78h+var_38]
0x1800f6af0  call    ?UTF8toWstr@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBD_K@Z; UTF8toWstr(char const *,unsigned __int64)
0x1800f6af5  nop
0x1800f6af6  mov     rcx, [rsi]
0x1800f6af9  test    rcx, rcx
0x1800f6afc  jz      short loc_1800F6B12
0x1800f6afe  mov     qword ptr [rsi], 0
0x1800f6b05  mov     rax, [rcx]
0x1800f6b08  mov     rax, [rax+10h]
0x1800f6b0c  call    _guard_dispatch_icall
0x1800f6b11  nop
0x1800f6b12  xor     r8d, r8d; pMalloc
0x1800f6b15  mov     rdx, rsi; ppvObject
0x1800f6b18  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x1800f6b1f  call    cs:__imp_CreateXmlReader
0x1800f6b25  mov     rcx, [rsp+78h]; this
0x1800f6b2a  test    eax, eax
0x1800f6b2c  js      loc_1800F6C66
0x1800f6b32  mov     rcx, [r14]
0x1800f6b35  test    rcx, rcx
0x1800f6b38  jz      short loc_1800F6B4E
0x1800f6b3a  mov     qword ptr [r14], 0
0x1800f6b41  mov     rax, [rcx]
0x1800f6b44  mov     rax, [rax+10h]
0x1800f6b48  call    _guard_dispatch_icall
0x1800f6b4d  nop
0x1800f6b4e  mov     r8, r14; ppstm
0x1800f6b51  mov     edx, 1; fDeleteOnRelease
0x1800f6b56  xor     ecx, ecx; hGlobal
0x1800f6b58  call    cs:__imp_CreateStreamOnHGlobal
0x1800f6b5e  mov     rcx, [rsp+78h]; this
0x1800f6b63  test    eax, eax
0x1800f6b65  js      loc_1800F6C7B
0x1800f6b6b  mov     rcx, [r14]
0x1800f6b6e  mov     rax, [rcx]
0x1800f6b71  lea     rdx, [rsp+78h+var_38]
0x1800f6b76  cmp     [rsp+78h+var_20], 7
0x1800f6b7c  cmova   rdx, [rsp+78h+var_38]
0x1800f6b82  mov     r8d, [rsp+78h+var_28]
0x1800f6b87  add     r8d, r8d
0x1800f6b8a  xor     r9d, r9d
0x1800f6b8d  mov     rax, [rax+20h]
0x1800f6b91  call    _guard_dispatch_icall
0x1800f6b96  mov     rcx, [rsp+78h]; this
0x1800f6b9b  test    eax, eax
0x1800f6b9d  js      loc_1800F6C90
0x1800f6ba3  mov     rcx, [rsi]
0x1800f6ba6  mov     rax, [rcx]
0x1800f6ba9  xor     edx, edx
0x1800f6bab  mov     rax, [rax+18h]
0x1800f6baf  call    _guard_dispatch_icall
0x1800f6bb4  mov     edi, eax
0x1800f6bb6  test    eax, eax
0x1800f6bb8  jns     short loc_1800F6BD5
0x1800f6bba  mov     edx, 14h; void *
0x1800f6bbf  mov     rcx, [rsp+78h]; this
0x1800f6bc4  mov     r9d, eax; char *
0x1800f6bc7  lea     r8, aCW1SSrcDeliver; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800f6bce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f6bd3  jmp     short loc_1800F6C1A
0x1800f6bd5  mov     rcx, [r14]
0x1800f6bd8  mov     rax, [rcx]
0x1800f6bdb  xor     r9d, r9d
0x1800f6bde  xor     r8d, r8d
0x1800f6be1  xor     edx, edx
0x1800f6be3  mov     rax, [rax+28h]
0x1800f6be7  call    _guard_dispatch_icall
0x1800f6bec  mov     edi, eax
0x1800f6bee  test    eax, eax
0x1800f6bf0  jns     short loc_1800F6BF9
0x1800f6bf2  mov     edx, 16h
0x1800f6bf7  jmp     short loc_1800F6BBF
0x1800f6bf9  mov     rcx, [rsi]
0x1800f6bfc  mov     rax, [rcx]
0x1800f6bff  mov     rdx, [r14]
0x1800f6c02  mov     rax, [rax+18h]
0x1800f6c06  call    _guard_dispatch_icall
0x1800f6c0b  mov     edi, eax
0x1800f6c0d  test    eax, eax
0x1800f6c0f  jns     short loc_1800F6C18
0x1800f6c11  mov     edx, 17h
0x1800f6c16  jmp     short loc_1800F6BBF
0x1800f6c18  xor     edi, edi
0x1800f6c1a  mov     rcx, [rsp+78h]; this
0x1800f6c1f  test    edi, edi
0x1800f6c21  js      short loc_1800F6C51
0x1800f6c23  lea     rcx, [rsp+78h+var_38]
0x1800f6c28  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800f6c2d  nop
0x1800f6c2e  mov     rax, rsi
0x1800f6c31  mov     rcx, [rsp+78h+var_18]
0x1800f6c36  xor     rcx, rsp; StackCookie
0x1800f6c39  call    __security_check_cookie
0x1800f6c3e  lea     r11, [rsp+78h+var_8]
0x1800f6c43  mov     rsi, [r11+20h]
0x1800f6c47  mov     rdi, [r11+28h]
0x1800f6c4b  mov     rsp, r11
0x1800f6c4e  pop     r14
0x1800f6c50  retn
0x1800f6c51  mov     r9d, edi; char *
0x1800f6c54  lea     r8, aCW1SSrcDeliver; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800f6c5b  mov     edx, 0Fh; void *
0x1800f6c60  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f6c66  mov     r9d, eax; char *
0x1800f6c69  lea     r8, aCW1SSrcDeliver; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800f6c70  mov     edx, 0Ch; void *
0x1800f6c75  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f6c7b  mov     r9d, eax; char *
0x1800f6c7e  lea     r8, aCW1SSrcDeliver; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800f6c85  mov     edx, 0Dh; void *
0x1800f6c8a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f6c90  mov     r9d, eax; char *
0x1800f6c93  lea     r8, aCW1SSrcDeliver; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800f6c9a  mov     edx, 0Eh; void *
0x1800f6c9f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
