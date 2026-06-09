# wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::create_key(ushort const *,HKEY__ * *,wil::reg::key_access)

- ea: `0x1800294c8`
- end: `0x180029565`
- name: `?create_key@?$reg_view_t@Uerr_exception_policy@wil@@@reg_view_details@reg@wil@@QEBAXPEBGPEAPEAUHKEY__@@W4key_access@34@@Z`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x1800635f0`

## callees

- `0x180029474`
- `0x1800294c8`
- `0x18003cf0c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002952a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002952a`

## string_xrefs

- `0x180029503`: `SYSTEM\CurrentControlSet\Services\RasMan\Profiles\`
- `0x180029545`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
int __fastcall wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::create_key(
        HKEY *a1,
        __int64 a2,
        HKEY *a3)
{
  REGSAM samDesired; // eax
  int result; // eax
  bool v7; // sf
  DWORD dwOptions; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD dwDisposition; // [rsp+78h] [rbp+20h] BYREF

  *a3 = 0;
  dwDisposition = 0;
  samDesired = wil::reg::reg_view_details::get_access_flags(1);
  result = RegCreateKeyExW(
             *a1,
             L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Profiles\\",
             0,
             0,
             0,
             samDesired,
             0,
             a3,
             &dwDisposition);
  v7 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v7 = result < 0;
  }
  if ( v7 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)result,
      dwOptions);
  return result;
}

```

## disassembly

```asm
0x1800294c8  mov     [rsp+arg_0], rbx
0x1800294cd  mov     [rsp+dwDisposition], r9d
0x1800294d2  push    rdi
0x1800294d3  sub     rsp, 50h
0x1800294d7  mov     rdi, rcx
0x1800294da  mov     qword ptr [r8], 0
0x1800294e1  mov     ecx, 1
0x1800294e6  mov     [rsp+58h+dwDisposition], 0
0x1800294ee  mov     rbx, r8
0x1800294f1  call    ?get_access_flags@reg_view_details@reg@wil@@YAKW4key_access@23@@Z; wil::reg::reg_view_details::get_access_flags(wil::reg::key_access)
0x1800294f6  lea     rcx, [rsp+58h+dwDisposition]
0x1800294fb  xor     r9d, r9d; lpClass
0x1800294fe  mov     [rsp+58h+lpdwDisposition], rcx; lpdwDisposition
0x180029503  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x18002950a  mov     rcx, [rdi]; hKey
0x18002950d  xor     r8d, r8d; Reserved
0x180029510  mov     [rsp+58h+phkResult], rbx; phkResult
0x180029515  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002951e  mov     [rsp+58h+samDesired], eax; samDesired
0x180029522  mov     [rsp+58h+dwOptions], 0; int
0x18002952a  call    cs:__imp_RegCreateKeyExW
0x180029530  test    eax, eax
0x180029532  jle     short loc_18002953E
0x180029534  movzx   eax, ax
0x180029537  or      eax, 80070000h
0x18002953c  test    eax, eax
0x18002953e  jns     short loc_18002955A
0x180029540  mov     rcx, [rsp+58h]; this
0x180029545  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002954c  mov     r9d, eax; char *
0x18002954f  mov     edx, 1CBEh; void *
0x180029554  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002955a  mov     rbx, [rsp+58h+arg_0]
0x18002955f  add     rsp, 50h
0x180029563  pop     rdi
0x180029564  retn
```
