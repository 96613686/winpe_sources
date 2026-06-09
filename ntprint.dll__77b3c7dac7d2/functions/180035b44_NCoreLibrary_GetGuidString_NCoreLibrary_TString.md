# NCoreLibrary::GetGuidString(NCoreLibrary::TString &)

- ea: `0x180035b44`
- end: `0x180035bcc`
- name: `?GetGuidString@NCoreLibrary@@YAJAEAVTString@1@@Z`
- size: `136`
- prototype: `__int64 __fastcall(NCoreLibrary *__hidden this, struct TString *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18002a5ac`

## callees

- `0x180002300`
- `0x180025d10`
- `0x180035b44`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035bac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035bac`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x180035b8c`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x180035b8c`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180035b6d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180035b6d`

## pseudocode

```c
__int64 __fastcall NCoreLibrary::GetGuidString(NCoreLibrary *this, struct TString *a2)
{
  HRESULT v3; // ebx
  LPOLESTR lpsz; // [rsp+20h] [rbp-28h] BYREF
  GUID pguid; // [rsp+28h] [rbp-20h] BYREF

  pguid = 0;
  v3 = CoCreateGuid(&pguid);
  if ( v3 >= 0 )
  {
    lpsz = 0;
    v3 = StringFromIID(&pguid, &lpsz);
    if ( v3 >= 0 )
    {
      v3 = NCoreLibrary::TString::Update(this, lpsz);
      CoTaskMemFree(lpsz);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180035b44  mov     [rsp+arg_8], rbx
0x180035b49  push    rdi
0x180035b4a  sub     rsp, 40h
0x180035b4e  mov     rax, cs:__security_cookie
0x180035b55  xor     rax, rsp
0x180035b58  mov     [rsp+48h+var_10], rax
0x180035b5d  mov     rdi, rcx
0x180035b60  xorps   xmm0, xmm0
0x180035b63  lea     rcx, [rsp+48h+pguid]; pguid
0x180035b68  movups  xmmword ptr [rsp+48h+pguid.Data1], xmm0
0x180035b6d  call    cs:__imp_CoCreateGuid
0x180035b73  mov     ebx, eax
0x180035b75  test    eax, eax
0x180035b77  js      short loc_180035BB2
0x180035b79  lea     rdx, [rsp+48h+lpsz]; lplpsz
0x180035b7e  mov     [rsp+48h+lpsz], 0
0x180035b87  lea     rcx, [rsp+48h+pguid]; rclsid
0x180035b8c  call    cs:__imp_StringFromIID
0x180035b92  mov     ebx, eax
0x180035b94  test    eax, eax
0x180035b96  js      short loc_180035BB2
0x180035b98  mov     rdx, [rsp+48h+lpsz]; unsigned __int16 *
0x180035b9d  mov     rcx, rdi; this
0x180035ba0  call    ?Update@TString@NCoreLibrary@@QEAAJPEBG@Z; NCoreLibrary::TString::Update(ushort const *)
0x180035ba5  mov     rcx, [rsp+48h+lpsz]; pv
0x180035baa  mov     ebx, eax
0x180035bac  call    cs:__imp_CoTaskMemFree
0x180035bb2  mov     eax, ebx
0x180035bb4  mov     rcx, [rsp+48h+var_10]
0x180035bb9  xor     rcx, rsp; StackCookie
0x180035bbc  call    __security_check_cookie
0x180035bc1  mov     rbx, [rsp+48h+arg_8]
0x180035bc6  add     rsp, 40h
0x180035bca  pop     rdi
0x180035bcb  retn
```
