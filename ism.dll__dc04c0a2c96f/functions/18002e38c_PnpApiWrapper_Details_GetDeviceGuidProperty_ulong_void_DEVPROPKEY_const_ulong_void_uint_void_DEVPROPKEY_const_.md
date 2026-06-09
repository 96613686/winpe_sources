# PnpApiWrapper::Details::GetDeviceGuidProperty(ulong (*)(void *,_DEVPROPKEY const *,ulong *,void *,uint &),void *,_DEVPROPKEY const *,_GUID &)

- ea: `0x18002e38c`
- end: `0x18002e4c4`
- name: `?GetDeviceGuidProperty@Details@PnpApiWrapper@@YAJP6AKPEAXPEBU_DEVPROPKEY@@PEAK0AEAI@Z01AEAU_GUID@@@Z`
- size: `312`
- prototype: `__int64 __fastcall(PnpApiWrapper::Details *__hidden this, unsigned int (*)(void *, const struct _DEVPROPKEY *, unsigned int *, void *, unsigned int *), void *, const struct _DEVPROPKEY *, struct _GUID *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180124b00`
- `0x180124ddc`

## callees

- `0x18002e38c`
- `0x18002e4cc`
- `0x18002e7b8`
- `0x18008ead4`
- `0x1801c3ea4`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e3f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e44d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e47d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e3f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e44d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e47d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002e430`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002e430`

## pseudocode

```c
__int64 __fastcall PnpApiWrapper::Details::GetDeviceGuidProperty(
        PnpApiWrapper::Details *this,
        unsigned int (*a2)(void *, const struct _DEVPROPKEY *, unsigned int *, void *, unsigned int *),
        void *a3,
        const struct _DEVPROPKEY *a4)
{
  unsigned int v6; // eax
  unsigned int v7; // edx
  unsigned int v8; // edi
  int DeviceStringProperty; // eax
  unsigned int v10; // ebx
  HSTRING v11; // rcx
  const wchar_t *StringRawBuffer; // rax
  __int64 result; // rax
  int v14; // [rsp+30h] [rbp-28h] BYREF
  int v15; // [rsp+38h] [rbp-20h] BYREF
  HSTRING string; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+20h]
  HSTRING v18; // [rsp+80h] [rbp+28h] BYREF

  v14 = 0;
  LODWORD(v18) = 16;
  v6 = ((__int64 (__fastcall *)(unsigned int (*)(void *, const struct _DEVPROPKEY *, unsigned int *, void *, unsigned int *), void *, int *))this)(
         a2,
         a3,
         &v14);
  v8 = v6;
  if ( !v6 )
    return 0;
  a4->fmtid = GUID_NULL;
  if ( v6 == 37 )
  {
    string = 0;
    WindowsDeleteString(0);
    string = 0;
    v15 = *(_DWORD *)a2;
    DeviceStringProperty = PnpApiWrapper::Details::GetDeviceStringProperty(
                             (PnpApiWrapper::Details *)Adapters::GetDeviceNodeProperty,
                             (unsigned int (*)(void *, const struct _DEVPROPKEY *, unsigned int *, void *, unsigned int *))&v15,
                             (void *)&DEVPKEY_Device_InstanceId,
                             &string);
    v10 = DeviceStringProperty;
    v11 = string;
    if ( string )
    {
      if ( DeviceStringProperty < 0 )
      {
LABEL_13:
        WindowsDeleteString(v11);
        return v10;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      if ( wcscmp_0(StringRawBuffer, L"HTREE\\ROOT\\0") )
      {
        WindowsDeleteString(string);
        goto LABEL_7;
      }
      v10 = 1;
    }
    else
    {
      if ( DeviceStringProperty < 0 )
        goto LABEL_13;
      v10 = -2147467259;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x300,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\pnpapiwrapper.cpp",
        (const char *)0x80004005LL,
        (int)&v18);
    }
    v11 = string;
    goto LABEL_13;
  }
LABEL_7:
  v10 = PnpApiWrapper::Details::ConfigretToHresult((PnpApiWrapper::Details *)v8, v7);
  result = 2147943568LL;
  if ( v10 == -2147023728 )
    return result;
  if ( (v10 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x183,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\pnpapiwrapper.cpp",
      (const char *)v10,
      (int)&v18);
    return v10;
  }
  return 0;
}

```

## disassembly

```asm
0x18002e38c  push    rbp
0x18002e38e  push    rbx
0x18002e38f  push    rsi
0x18002e390  push    rdi
0x18002e391  mov     rbp, rsp
0x18002e394  sub     rsp, 58h
0x18002e398  mov     rbx, r9
0x18002e39b  mov     rax, r8
0x18002e39e  mov     rsi, rdx
0x18002e3a1  mov     r10, rcx
0x18002e3a4  mov     [rbp+var_28], 0
0x18002e3ab  mov     dword ptr [rbp+arg_0], 10h
0x18002e3b2  lea     rcx, [rbp+arg_0]
0x18002e3b6  mov     [rsp+58h+var_38], rcx; int
0x18002e3bb  lea     r8, [rbp+var_28]
0x18002e3bf  mov     rdx, rax
0x18002e3c2  mov     rcx, rsi
0x18002e3c5  mov     rax, r10
0x18002e3c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e3cd  mov     edi, eax
0x18002e3cf  test    eax, eax
0x18002e3d1  jz      loc_18002E469
0x18002e3d7  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002e3de  movdqu  xmmword ptr [rbx], xmm0
0x18002e3e2  cmp     eax, 25h ; '%'
0x18002e3e5  jnz     short loc_18002E453
0x18002e3e7  mov     [rbp+string], 0
0x18002e3ef  xor     ecx, ecx; string
0x18002e3f1  call    cs:__imp_WindowsDeleteString
0x18002e3f7  mov     [rbp+string], 0
0x18002e3ff  mov     ecx, [rsi]
0x18002e401  mov     [rbp+var_20], ecx
0x18002e404  lea     r9, [rbp+string]; struct _DEVPROPKEY *
0x18002e408  lea     r8, DEVPKEY_Device_InstanceId; void *
0x18002e40f  lea     rdx, [rbp+var_20]; unsigned int (*)(void *, const struct _DEVPROPKEY *, unsigned int *, void *, unsigned int *)
0x18002e413  lea     rcx, ?GetDeviceNodeProperty@Adapters@@YAKPEAXPEBU_DEVPROPKEY@@PEAK0AEAI@Z; this
0x18002e41a  call    ?GetDeviceStringProperty@Details@PnpApiWrapper@@YAJP6AKPEAXPEBU_DEVPROPKEY@@PEAK0AEAI@Z01AEAPEAUHSTRING__@@@Z; PnpApiWrapper::Details::GetDeviceStringProperty(ulong (*)(void *,_DEVPROPKEY const *,ulong *,void *,uint &),void *,_DEVPROPKEY const *,HSTRING__ * &)
0x18002e41f  mov     ebx, eax
0x18002e421  mov     rcx, [rbp+string]; string
0x18002e425  test    rcx, rcx
0x18002e428  jz      short loc_18002E487
0x18002e42a  test    eax, eax
0x18002e42c  js      short loc_18002E47D
0x18002e42e  xor     edx, edx; length
0x18002e430  call    cs:__imp_WindowsGetStringRawBuffer
0x18002e436  lea     rdx, aHtreeRoot0; "HTREE\\ROOT\\0"
0x18002e43d  mov     rcx, rax; String1
0x18002e440  call    wcscmp_0
0x18002e445  test    eax, eax
0x18002e447  jz      short loc_18002E474
0x18002e449  mov     rcx, [rbp+string]; string
0x18002e44d  call    cs:__imp_WindowsDeleteString
0x18002e453  mov     ecx, edi; this
0x18002e455  call    ?ConfigretToHresult@Details@PnpApiWrapper@@YAJK@Z; PnpApiWrapper::Details::ConfigretToHresult(ulong)
0x18002e45a  mov     ebx, eax
0x18002e45c  mov     eax, 80070490h
0x18002e461  cmp     ebx, eax
0x18002e463  jz      short loc_18002E46B
0x18002e465  test    ebx, ebx
0x18002e467  js      short loc_18002E4AA
0x18002e469  xor     eax, eax
0x18002e46b  add     rsp, 58h
0x18002e46f  pop     rdi
0x18002e470  pop     rsi
0x18002e471  pop     rbx
0x18002e472  pop     rbp
0x18002e473  retn
0x18002e474  mov     ebx, 1
0x18002e479  mov     rcx, [rbp+string]; string
0x18002e47d  call    cs:__imp_WindowsDeleteString
0x18002e483  mov     eax, ebx
0x18002e485  jmp     short loc_18002E46B
0x18002e487  test    eax, eax
0x18002e489  js      short loc_18002E47D
0x18002e48b  mov     rcx, [rbp+20h]; this
0x18002e48f  mov     ebx, 80004005h
0x18002e494  mov     r9d, ebx; char *
0x18002e497  lea     r8, aOnecoreuapWind_228; "onecoreuap\\windows\\moderncore\\inputv"...
0x18002e49e  mov     edx, 300h; void *
0x18002e4a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e4a8  jmp     short loc_18002E479
0x18002e4aa  mov     rcx, [rbp+20h]; this
0x18002e4ae  mov     r9d, ebx; char *
0x18002e4b1  lea     r8, aOnecoreuapWind_228; "onecoreuap\\windows\\moderncore\\inputv"...
0x18002e4b8  mov     edx, 183h; void *
0x18002e4bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e4c2  jmp     short loc_18002E483
```
