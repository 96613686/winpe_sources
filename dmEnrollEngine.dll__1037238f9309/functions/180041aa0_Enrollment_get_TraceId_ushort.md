# Enrollment::get_TraceId(ushort * *)

- ea: `0x180041aa0`
- end: `0x180041c3c`
- name: `?get_TraceId@Enrollment@@UEAAJPEAPEAG@Z`
- size: `412`
- prototype: `__int64 __fastcall(Enrollment *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180007040`
- `0x1800071c0`
- `0x18001f438`
- `0x18002d998`
- `0x18002e1a0`
- `0x18002ec8c`
- `0x180032f20`
- `0x180041aa0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180041bfe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180041bfe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041bee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041bee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180041bb2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180041bb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041c0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041c0e`
- `OLEAUT32!__imp_SysAllocString` at `0x180041be5`
- `OLEAUT32!__imp_SysAllocString` at `0x180041be5`

## pseudocode

```c
__int64 __fastcall Enrollment::get_TraceId(Enrollment *this, unsigned __int16 **a2)
{
  const unsigned __int16 *v4; // rax
  signed int String; // ebx
  unsigned __int64 v6; // rcx
  __int64 v7; // rax
  LSTATUS v8; // eax
  HKEY v9; // rcx
  HANDLE ProcessHeap; // rax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  OLECHAR *psz; // [rsp+38h] [rbp-C8h]
  WCHAR SubKey[264]; // [rsp+40h] [rbp-C0h] BYREF

  memset_0(SubKey, 0, 0x208u);
  hKey = 0;
  psz = 0;
  v4 = (const unsigned __int16 *)DMGetKnownRegPath(2);
  String = StringCchCopyW(SubKey, 0x104u, v4);
  if ( String < 0 )
    goto LABEL_12;
  String = StringCchCatW(SubKey, 0x104u, L"Status");
  if ( String < 0 )
    goto LABEL_12;
  String = StringCchCatW(SubKey, 0x104u, L"\\");
  if ( String < 0 )
    goto LABEL_12;
  v6 = (unsigned __int64)this + 150;
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(v6 + 2 * v7) );
  String = StringCchCatW(SubKey, 0x104u, (const unsigned __int16 *)(v6 & -(__int64)(v7 != 0)));
  if ( String < 0 )
  {
LABEL_12:
    v9 = hKey;
    goto LABEL_13;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey);
  String = v8;
  if ( v8 > 0 )
    String = (unsigned __int16)v8 | 0x80070000;
  v9 = hKey;
  if ( String >= 0 )
  {
    String = RegistryAllocAndGetString(hKey);
    if ( String >= 0 )
    {
      *a2 = SysAllocString(psz);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, psz);
    }
    goto LABEL_12;
  }
LABEL_13:
  if ( v9 )
    RegCloseKey(v9);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x180041aa0  mov     [rsp-8+arg_10], rbx
0x180041aa5  push    rbp
0x180041aa6  push    rsi
0x180041aa7  push    rdi
0x180041aa8  push    r14
0x180041aaa  push    r15
0x180041aac  lea     rbp, [rsp-160h]
0x180041ab4  sub     rsp, 260h
0x180041abb  mov     rax, cs:__security_cookie
0x180041ac2  xor     rax, rsp
0x180041ac5  mov     [rbp+180h+var_30], rax
0x180041acc  mov     rsi, rdx
0x180041acf  mov     rdi, rcx
0x180041ad2  xor     edx, edx; Val
0x180041ad4  lea     rcx, [rsp+280h+SubKey]; void *
0x180041ad9  mov     r8d, 208h; Size
0x180041adf  call    memset_0
0x180041ae4  xor     r14d, r14d
0x180041ae7  mov     [rsp+280h+hKey], r14
0x180041aec  mov     [rsp+280h+psz], r14
0x180041af1  lea     ecx, [r14+2]
0x180041af5  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x180041afa  mov     r15d, 104h
0x180041b00  lea     rcx, [rsp+280h+SubKey]; unsigned __int16 *
0x180041b05  mov     edx, r15d; unsigned __int64
0x180041b08  mov     r8, rax; unsigned __int16 *
0x180041b0b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180041b10  mov     ebx, eax
0x180041b12  test    eax, eax
0x180041b14  js      loc_180041C04
0x180041b1a  lea     r8, aStatus; "Status"
0x180041b21  mov     edx, r15d; unsigned __int64
0x180041b24  lea     rcx, [rsp+280h+SubKey]; unsigned __int16 *
0x180041b29  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180041b2e  mov     ebx, eax
0x180041b30  test    eax, eax
0x180041b32  js      loc_180041C04
0x180041b38  lea     r8, asc_18007FF94; "\\"
0x180041b3f  mov     edx, r15d; unsigned __int64
0x180041b42  lea     rcx, [rsp+280h+SubKey]; unsigned __int16 *
0x180041b47  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180041b4c  mov     ebx, eax
0x180041b4e  test    eax, eax
0x180041b50  js      loc_180041C04
0x180041b56  lea     rcx, [rdi+96h]
0x180041b5d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180041b61  inc     rax
0x180041b64  cmp     [rcx+rax*2], r14w
0x180041b69  jnz     short loc_180041B61
0x180041b6b  neg     rax
0x180041b6e  mov     rdx, r15; unsigned __int64
0x180041b71  sbb     r8, r8
0x180041b74  and     r8, rcx; unsigned __int16 *
0x180041b77  lea     rcx, [rsp+280h+SubKey]; unsigned __int16 *
0x180041b7c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180041b81  mov     ebx, eax
0x180041b83  test    eax, eax
0x180041b85  js      short loc_180041C04
0x180041b87  xor     edx, edx
0x180041b89  lea     rcx, [rsp+280h+hKey]
0x180041b8e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180041b93  lea     rax, [rsp+280h+hKey]
0x180041b98  mov     r9d, 1; samDesired
0x180041b9e  xor     r8d, r8d; ulOptions
0x180041ba1  mov     [rsp+280h+phkResult], rax; phkResult
0x180041ba6  lea     rdx, [rsp+280h+SubKey]; lpSubKey
0x180041bab  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180041bb2  call    cs:__imp_RegOpenKeyExW
0x180041bb8  mov     ebx, eax
0x180041bba  test    eax, eax
0x180041bbc  jle     short loc_180041BC7
0x180041bbe  movzx   ebx, ax
0x180041bc1  or      ebx, 80070000h
0x180041bc7  mov     rcx, [rsp+280h+hKey]; hKey
0x180041bcc  test    ebx, ebx
0x180041bce  js      short loc_180041C09
0x180041bd0  lea     r8, [rsp+280h+psz]
0x180041bd5  call    RegistryAllocAndGetString
0x180041bda  mov     ebx, eax
0x180041bdc  test    eax, eax
0x180041bde  js      short loc_180041C04
0x180041be0  mov     rcx, [rsp+280h+psz]; psz
0x180041be5  call    cs:__imp_SysAllocString
0x180041beb  mov     [rsi], rax
0x180041bee  call    cs:__imp_GetProcessHeap
0x180041bf4  mov     r8, [rsp+280h+psz]; lpMem
0x180041bf9  xor     edx, edx; dwFlags
0x180041bfb  mov     rcx, rax; hHeap
0x180041bfe  call    cs:__imp_HeapFree
0x180041c04  mov     rcx, [rsp+280h+hKey]; hKey
0x180041c09  test    rcx, rcx
0x180041c0c  jz      short loc_180041C14
0x180041c0e  call    cs:__imp_RegCloseKey
0x180041c14  mov     eax, ebx
0x180041c16  mov     rcx, [rbp+180h+var_30]
0x180041c1d  xor     rcx, rsp; StackCookie
0x180041c20  call    __security_check_cookie
0x180041c25  mov     rbx, [rsp+280h+arg_10]
0x180041c2d  add     rsp, 260h
0x180041c34  pop     r15
0x180041c36  pop     r14
0x180041c38  pop     rdi
0x180041c39  pop     rsi
0x180041c3a  pop     rbp
0x180041c3b  retn
```
