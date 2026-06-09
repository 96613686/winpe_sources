# HvServiceUtil::HvServiceUtil(void)

- ea: `0x180006ebc`
- end: `0x180006f76`
- name: `??0HvServiceUtil@@QEAA@XZ`
- size: `186`
- prototype: `HvServiceUtil *__fastcall(HvServiceUtil *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180001a80`
- `0x1800084f4`

## callees

- `0x180006ebc`
- `0x180007064`
- `0x180007f3c`
- `0x180008058`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180006efe`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180006efe`

## string_xrefs

- `0x180006f56`: `onecore\hv\common\inc\HvServiceUtil.h`
- `0x180006ef7`: `\\.\HvServiceDevice`

## pseudocode

```c
HvServiceUtil *__fastcall HvServiceUtil::HvServiceUtil(HvServiceUtil *this)
{
  HANDLE FileW; // rdi
  const char *v3; // r9
  _QWORD v5[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *(_QWORD *)this = -1;
  FileW = CreateFileW(L"\\\\.\\HvServiceDevice", 0xC0000000, 0, 0, 3u, 0x80u, 0);
  v5[0] = FileW;
  if ( this != (HvServiceUtil *)v5 )
  {
    if ( (unsigned __int64)(*(_QWORD *)this - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*(HANDLE *)this);
    *(_QWORD *)this = FileW;
    v5[0] = -1;
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v5);
  if ( ((*(_QWORD *)this + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x45,
      (unsigned int)"onecore\\hv\\common\\inc\\HvServiceUtil.h",
      v3);
  return this;
}

```

## disassembly

```asm
0x180006ebc  mov     rax, rsp
0x180006ebf  mov     [rax+10h], rbx
0x180006ec3  mov     [rax+8], rcx
0x180006ec7  push    rdi
0x180006ec8  sub     rsp, 50h
0x180006ecc  mov     rbx, rcx
0x180006ecf  mov     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x180006ed6  mov     qword ptr [rax-28h], 0
0x180006ede  mov     dword ptr [rax-30h], 80h
0x180006ee5  mov     dword ptr [rax-38h], 3
0x180006eec  xor     r9d, r9d; lpSecurityAttributes
0x180006eef  xor     r8d, r8d; dwShareMode
0x180006ef2  mov     edx, 0C0000000h; dwDesiredAccess
0x180006ef7  lea     rcx, FileName; "\\\\.\\HvServiceDevice"
0x180006efe  call    cs:__imp_CreateFileW
0x180006f04  mov     rdi, rax
0x180006f07  mov     [rsp+58h+var_18], rax
0x180006f0c  lea     rax, [rsp+58h+var_18]
0x180006f11  cmp     rbx, rax
0x180006f14  jz      short loc_180006F34
0x180006f16  mov     rcx, [rbx]; hObject
0x180006f19  lea     rdx, [rcx-1]
0x180006f1d  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180006f21  ja      short loc_180006F28
0x180006f23  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x180006f28  mov     [rbx], rdi
0x180006f2b  mov     [rsp+58h+var_18], 0FFFFFFFFFFFFFFFFh
0x180006f34  lea     rcx, [rsp+58h+var_18]
0x180006f39  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180006f3e  mov     rax, [rbx]
0x180006f41  inc     rax
0x180006f44  test    rax, 0FFFFFFFFFFFFFFFEh
0x180006f4a  setz    al
0x180006f4d  mov     rcx, [rsp+58h]; this
0x180006f52  test    al, al
0x180006f54  jz      short loc_180006F68
0x180006f56  lea     r8, aOnecoreHvCommo; "onecore\\hv\\common\\inc\\HvServiceUtil"...
0x180006f5d  mov     edx, 45h ; 'E'; void *
0x180006f62  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180006f68  mov     rax, rbx
0x180006f6b  mov     rbx, [rsp+58h+arg_8]
0x180006f70  add     rsp, 50h
0x180006f74  pop     rdi
0x180006f75  retn
```
