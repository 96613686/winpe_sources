# CModule::ShouldShowNotification(ulong,ulong)

- ea: `0x180090b0c`
- end: `0x180090c45`
- name: `?ShouldShowNotification@CModule@@QEAA_NKK@Z`
- size: `313`
- prototype: `bool __fastcall(CModule *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180090c4c`

## callees

- `0x18008a1ec`
- `0x180090b0c`
- `0x180091ea0`
- `0x180092b0c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180090b9d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180090b9d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180090b78`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180090b78`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180090be3`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180090be3`

## string_xrefs

- `0x180090c33`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall CModule::ShouldShowNotification(CModule *this, int a2, DWORD a3)
{
  LSTATUS ValueW; // eax
  unsigned int v5; // edi
  unsigned __int64 v6; // rbx
  unsigned int v7; // edi
  int v8; // eax
  int pdwType; // [rsp+20h] [rbp-30h]
  unsigned __int64 pvData; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+70h] [rbp+20h] BYREF
  DWORD pcbData; // [rsp+80h] [rbp+30h] BYREF
  HKEY hkey; // [rsp+88h] [rbp+38h] BYREF

  pcbData = a3;
  SystemTimeAsFileTime = (struct _FILETIME)this;
  if ( (unsigned int)(a2 - 19) >= 2 )
    return 1;
  wil::reg::create_unique_key(&hkey);
  pvData = 0;
  pcbData = 8;
  ValueW = RegGetValueW(hkey, 0, L"AutoSRLastNotificationTime", 0x40u, 0, &pvData, &pcbData);
  v5 = ValueW;
  if ( ValueW > 0 )
    v5 = (unsigned __int16)ValueW | 0x80070000;
  v6 = pvData;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( *(_QWORD *)&SystemTimeAsFileTime <= v6 )
    goto LABEL_6;
  v7 = v5 >> 31;
  if ( (_BYTE)v7 )
    goto LABEL_7;
  if ( *(_QWORD *)&SystemTimeAsFileTime - v6 > 0x29E8D60800LL )
  {
LABEL_6:
    LOBYTE(v7) = 1;
LABEL_7:
    v8 = RegSetKeyValueW(hkey, 0, L"AutoSRLastNotificationTime", 0xBu, &SystemTimeAsFileTime, 8u);
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    if ( v8 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result_macros.h",
        (const char *)(unsigned int)v8,
        pdwType);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return v7;
}

```

## disassembly

```asm
0x180090b0c  mov     [rsp-18h+arg_10], r8d
0x180090b11  mov     qword ptr [rsp-18h+SystemTimeAsFileTime.dwLowDateTime], rcx
0x180090b16  push    rbp
0x180090b17  push    rbx
0x180090b18  push    rdi
0x180090b19  mov     rbp, rsp
0x180090b1c  sub     rsp, 50h
0x180090b20  sub     edx, 13h
0x180090b23  jz      short loc_180090B31
0x180090b25  cmp     edx, 1
0x180090b28  jz      short loc_180090B31
0x180090b2a  mov     al, 1
0x180090b2c  jmp     loc_180090C28
0x180090b31  lea     rcx, [rbp+hkey]
0x180090b35  call    ?create_unique_key@reg@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@PEAUHKEY__@@PEBGW4key_access@12@@Z; wil::reg::create_unique_key(HKEY__ *,ushort const *,wil::reg::key_access)
0x180090b3a  nop
0x180090b3b  mov     [rbp+var_10], 0
0x180090b43  mov     [rbp+arg_10], 8
0x180090b4a  lea     rax, [rbp+arg_10]
0x180090b4e  mov     [rsp+50h+pcbData], rax; pcbData
0x180090b53  lea     rax, [rbp+var_10]
0x180090b57  mov     [rsp+50h+pvData], rax; pvData
0x180090b5c  mov     [rsp+50h+pdwType], 0; pdwType
0x180090b65  mov     r9d, 40h ; '@'; dwFlags
0x180090b6b  lea     r8, aAutosrlastnoti; "AutoSRLastNotificationTime"
0x180090b72  xor     edx, edx; lpSubKey
0x180090b74  mov     rcx, [rbp+hkey]; hkey
0x180090b78  call    cs:__imp_RegGetValueW
0x180090b7e  mov     edi, eax
0x180090b80  test    eax, eax
0x180090b82  jle     short loc_180090B8D
0x180090b84  movzx   edi, ax
0x180090b87  or      edi, 80070000h
0x180090b8d  mov     rbx, [rbp+var_10]
0x180090b91  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180090b99  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180090b9d  call    cs:__imp_GetSystemTimeAsFileTime
0x180090ba3  mov     eax, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180090ba6  mov     ecx, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x180090ba9  mov     [rbp+SystemTimeAsFileTime.dwLowDateTime], eax
0x180090bac  mov     [rbp+SystemTimeAsFileTime.dwHighDateTime], ecx
0x180090baf  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180090bb3  cmp     rax, rbx
0x180090bb6  ja      short loc_180090BFF
0x180090bb8  mov     dil, 1
0x180090bbb  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180090bbf  mov     dword ptr [rsp+50h+pvData], 8; cbData
0x180090bc7  lea     rax, [rbp+SystemTimeAsFileTime]
0x180090bcb  mov     [rsp+50h+pdwType], rax; int
0x180090bd0  mov     r9d, 0Bh; dwType
0x180090bd6  lea     r8, aAutosrlastnoti; "AutoSRLastNotificationTime"
0x180090bdd  xor     edx, edx; lpSubKey
0x180090bdf  mov     rcx, [rbp+hkey]; hKey
0x180090be3  call    cs:__imp_RegSetKeyValueW
0x180090be9  test    eax, eax
0x180090beb  jle     short loc_180090BF5
0x180090bed  movzx   eax, ax
0x180090bf0  or      eax, 80070000h
0x180090bf5  mov     rcx, [rbp+18h]; this
0x180090bf9  test    eax, eax
0x180090bfb  js      short loc_180090C30
0x180090bfd  jmp     short loc_180090C1C
0x180090bff  shr     edi, 1Fh
0x180090c02  test    dil, dil
0x180090c05  jnz     short loc_180090BBB
0x180090c07  mov     rcx, rax
0x180090c0a  sub     rcx, rbx
0x180090c0d  mov     rdx, 29E8D60800h
0x180090c17  cmp     rcx, rdx
0x180090c1a  ja      short loc_180090BB8
0x180090c1c  lea     rcx, [rbp+hkey]
0x180090c20  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180090c25  mov     al, dil
0x180090c28  add     rsp, 50h
0x180090c2c  pop     rdi
0x180090c2d  pop     rbx
0x180090c2e  pop     rbp
0x180090c2f  retn
0x180090c30  mov     r9d, eax; char *
0x180090c33  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180090c3a  mov     edx, 1CBEh; void *
0x180090c3f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
