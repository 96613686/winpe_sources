# CWinRTHelper::GetActivationFactory(ushort const *,_GUID const &,void * *)

- ea: `0x180016400`
- end: `0x180016463`
- name: `?GetActivationFactory@CWinRTHelper@@SAJPEBGAEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: `static int(const unsigned __int16 *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180014f24`

## callees

- `0x180016400`
- `0x1800730c8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001642b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001642b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016450`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016450`

## string_xrefs

- `0x180016424`: `Windows.Security.Cryptography.CryptographicBuffer`

## pseudocode

```c
__int64 __fastcall CWinRTHelper::GetActivationFactory(
        const unsigned __int16 *a1,
        const struct _GUID *a2,
        const struct _GUID *a3)
{
  HSTRING v4; // rdx
  HRESULT ActivationFactoryHelper; // ebx
  void **v6; // r9
  HSTRING string; // [rsp+38h] [rbp+10h] BYREF

  string = 0;
  ActivationFactoryHelper = WindowsCreateString(L"Windows.Security.Cryptography.CryptographicBuffer", 0x31u, &string);
  if ( ActivationFactoryHelper >= 0 )
    ActivationFactoryHelper = IEWinRTUtil::GetActivationFactoryHelper((IEWinRTUtil *)string, v4, a3, v6);
  if ( string )
    WindowsDeleteString(string);
  return (unsigned int)ActivationFactoryHelper;
}

```

## disassembly

```asm
0x180016400  mov     rax, rsp
0x180016403  mov     [rax+8], rbx
0x180016407  mov     [rax+10h], rdx
0x18001640b  push    rdi
0x18001640c  sub     rsp, 20h
0x180016410  mov     rdi, r8
0x180016413  mov     qword ptr [rax+10h], 0
0x18001641b  lea     r8, [rax+10h]; string
0x18001641f  mov     edx, 31h ; '1'; length
0x180016424  lea     rcx, ?RuntimeClass_Windows_Security_Cryptography_CryptographicBuffer@@3QBGB; "Windows.Security.Cryptography.Cryptogra"...
0x18001642b  call    cs:__imp_WindowsCreateString
0x180016431  mov     ebx, eax
0x180016433  test    eax, eax
0x180016435  js      short loc_180016446
0x180016437  mov     rcx, [rsp+28h+string]; this
0x18001643c  mov     r8, rdi; struct _GUID *
0x18001643f  call    ?GetActivationFactoryHelper@IEWinRTUtil@@YAJPEAUHSTRING__@@AEBU_GUID@@PEAPEAX@Z; IEWinRTUtil::GetActivationFactoryHelper(HSTRING__ *,_GUID const &,void * *)
0x180016444  mov     ebx, eax
0x180016446  mov     rcx, [rsp+28h+string]; string
0x18001644b  test    rcx, rcx
0x18001644e  jz      short loc_180016456
0x180016450  call    cs:__imp_WindowsDeleteString
0x180016456  mov     eax, ebx
0x180016458  mov     rbx, [rsp+28h+arg_0]
0x18001645d  add     rsp, 20h
0x180016461  pop     rdi
0x180016462  retn
```
