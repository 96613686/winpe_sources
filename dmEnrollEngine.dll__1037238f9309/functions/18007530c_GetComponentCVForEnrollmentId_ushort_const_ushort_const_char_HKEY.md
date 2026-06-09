# GetComponentCVForEnrollmentId(ushort const *,ushort const *,char *,HKEY__ *)

- ea: `0x18007530c`
- end: `0x18007544f`
- name: `?GetComponentCVForEnrollmentId@@YAJPEBG0PEADPEAUHKEY__@@@Z`
- size: `323`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, char *, HKEY)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e2ec`
- `0x180075458`

## callees

- `0x1800071c0`
- `0x180016c54`
- `0x18002e1a0`
- `0x180032fac`
- `0x18003d458`
- `0x18007530c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180075365`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180075365`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180075399`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180075399`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180075428`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180075428`
- `DMCmnUtils!UnicodeToMB` at `0x1800753dc`
- `DMCmnUtils!UnicodeToMB` at `0x1800753dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetComponentCVForEnrollmentId(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        char *a3,
        HKEY a4)
{
  int v7; // ebx
  char *v8; // rcx
  char *v10; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v13; // [rsp+44h] [rbp-BCh] BYREF
  char **v14; // [rsp+48h] [rbp-B8h] BYREF
  char *v15; // [rsp+50h] [rbp-B0h] BYREF
  char v16; // [rsp+58h] [rbp-A8h]
  unsigned __int16 Data[136]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  RegOpenKeyExW(a4, a2, 0, 0x20019u, &hKey);
  cbData = 258;
  if ( !RegQueryValueExW(hKey, L"OmaDmSession", 0, 0, (LPBYTE)Data, &cbData) )
  {
    v10 = 0;
    v13 = 0;
    v14 = &v10;
    v15 = 0;
    v16 = 1;
    v7 = UnicodeToMB(Data, 0xFDE9u, &v15, &v13);
    wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>((__int64)&v14);
    if ( v7 >= 0 )
      StringCchCopyA(a3, 0x81u, v10);
    v8 = v10;
    v10 = 0;
    if ( v8 )
      MemoryFree(v8);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18007530c  mov     [rsp-8+arg_0], rbx
0x180075311  push    rbp
0x180075312  push    rsi
0x180075313  push    rdi
0x180075314  lea     rbp, [rsp-80h]
0x180075319  sub     rsp, 180h
0x180075320  mov     rax, cs:__security_cookie
0x180075327  xor     rax, rsp
0x18007532a  mov     [rbp+90h+var_20], rax
0x18007532e  mov     rdi, r9
0x180075331  mov     rsi, r8
0x180075334  mov     rbx, rdx
0x180075337  mov     [rsp+190h+hKey], 0
0x180075340  xor     edx, edx
0x180075342  lea     rcx, [rsp+190h+hKey]
0x180075347  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18007534c  lea     rax, [rsp+190h+hKey]
0x180075351  mov     [rsp+190h+phkResult], rax; phkResult
0x180075356  mov     r9d, 20019h; samDesired
0x18007535c  xor     r8d, r8d; ulOptions
0x18007535f  mov     rdx, rbx; lpSubKey
0x180075362  mov     rcx, rdi; hKey
0x180075365  call    cs:__imp_RegOpenKeyExW
0x18007536b  mov     [rsp+190h+cbData], 102h
0x180075373  lea     rax, [rsp+190h+cbData]
0x180075378  mov     [rsp+190h+lpcbData], rax; lpcbData
0x18007537d  lea     rax, [rsp+190h+Data]
0x180075382  mov     [rsp+190h+phkResult], rax; lpData
0x180075387  xor     r9d, r9d; lpType
0x18007538a  xor     r8d, r8d; lpReserved
0x18007538d  lea     rdx, c_szCvValueNameOmaDmSession; "OmaDmSession"
0x180075394  mov     rcx, [rsp+190h+hKey]; hKey
0x180075399  call    cs:__imp_RegQueryValueExW
0x18007539f  test    eax, eax
0x1800753a1  jnz     short loc_18007541E
0x1800753a3  mov     [rsp+190h+var_160], 0
0x1800753ac  mov     [rsp+190h+var_14C], eax
0x1800753b0  lea     rax, [rsp+190h+var_160]
0x1800753b5  mov     [rsp+190h+var_148], rax
0x1800753ba  mov     [rsp+190h+var_140], 0
0x1800753c3  mov     [rsp+190h+var_138], 1
0x1800753c8  lea     r9, [rsp+190h+var_14C]
0x1800753cd  lea     r8, [rsp+190h+var_140]
0x1800753d2  mov     edx, 0FDE9h
0x1800753d7  lea     rcx, [rsp+190h+Data]
0x1800753dc  call    cs:__imp_?UnicodeToMB@@YAJPEBGIPEAPEADPEAK@Z; UnicodeToMB(ushort const *,uint,char * *,ulong *)
0x1800753e2  mov     ebx, eax
0x1800753e4  lea     rcx, [rsp+190h+var_148]
0x1800753e9  call    ??1?$out_param_t@V?$unique_ptr@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort,wil::process_heap_deleter>>(void)
0x1800753ee  test    ebx, ebx
0x1800753f0  js      short loc_180075405
0x1800753f2  mov     r8, [rsp+190h+var_160]; char *
0x1800753f7  mov     edx, 81h; unsigned __int64
0x1800753fc  mov     rcx, rsi; char *
0x1800753ff  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180075404  nop
0x180075405  mov     rcx, [rsp+190h+var_160]; void *
0x18007540a  mov     [rsp+190h+var_160], 0
0x180075413  test    rcx, rcx
0x180075416  jz      short loc_18007541E
0x180075418  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18007541d  nop
0x18007541e  mov     rcx, [rsp+190h+hKey]; hKey
0x180075423  test    rcx, rcx
0x180075426  jz      short loc_18007542E
0x180075428  call    cs:__imp_RegCloseKey
0x18007542e  xor     eax, eax
0x180075430  mov     rcx, [rbp+90h+var_20]
0x180075434  xor     rcx, rsp; StackCookie
0x180075437  call    __security_check_cookie
0x18007543c  mov     rbx, [rsp+190h+arg_0]
0x180075444  add     rsp, 180h
0x18007544b  pop     rdi
0x18007544c  pop     rsi
0x18007544d  pop     rbp
0x18007544e  retn
```
