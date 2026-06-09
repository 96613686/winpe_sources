# container::Registry::OpenKey(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong)

- ea: `0x180029888`
- end: `0x180029934`
- name: `?OpenKey@Registry@container@@YAPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z`
- size: `172`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18000e5a0`
- `0x180029bc0`
- `0x18002a390`

## callees

- `0x180002ad0`
- `0x1800051b0`
- `0x18000b4bc`
- `0x180026830`
- `0x180029888`

## import_xrefs

- `ntdll!NtOpenKey` at `0x1800298d8`
- `ntdll!NtOpenKey` at `0x1800298d8`

## string_xrefs

- `0x180029922`: `onecore\base\gendrv\silos\container\registry_provider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall container::Registry::OpenKey(int a1, ACCESS_MASK a2)
{
  NTSTATUS v3; // eax
  void *v4; // rbx
  int v6; // [rsp+20h] [rbp-98h]
  void *KeyHandle; // [rsp+30h] [rbp-88h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-78h] BYREF
  _BYTE v9[32]; // [rsp+80h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  KeyHandle = 0;
  windows_wrappers::ObjectAttributes::ObjectAttributes((unsigned int)&ObjectAttributes, a1, 64, 0, 0);
  v3 = NtOpenKey(&KeyHandle, a2, &ObjectAttributes);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x471,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\registry_provider.cpp",
      (const char *)(unsigned int)v3,
      v6);
  v4 = KeyHandle;
  std::wstring::~wstring(v9);
  return v4;
}

```

## disassembly

```asm
0x180029888  push    rbx
0x18002988a  sub     rsp, 0B0h
0x180029891  mov     rax, cs:__security_cookie
0x180029898  xor     rax, rsp
0x18002989b  mov     [rsp+0B8h+var_18], rax
0x1800298a3  mov     ebx, edx
0x1800298a5  mov     [rsp+0B8h+KeyHandle], 0
0x1800298ae  mov     qword ptr [rsp+0B8h+var_98], 0; int
0x1800298b7  xor     r9d, r9d
0x1800298ba  lea     r8d, [r9+40h]
0x1800298be  mov     rdx, rcx
0x1800298c1  lea     rcx, [rsp+0B8h+ObjectAttributes]
0x1800298c6  call    ??0ObjectAttributes@windows_wrappers@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KQEAX1@Z; windows_wrappers::ObjectAttributes::ObjectAttributes(std::wstring const &,ulong,void * const,void * const)
0x1800298cb  nop
0x1800298cc  lea     r8, [rsp+0B8h+ObjectAttributes]; ObjectAttributes
0x1800298d1  mov     edx, ebx; DesiredAccess
0x1800298d3  lea     rcx, [rsp+0B8h+KeyHandle]; KeyHandle
0x1800298d8  call    cs:__imp_NtOpenKey
0x1800298df  nop     dword ptr [rax+rax+00h]
0x1800298e4  mov     rcx, [rsp+0B8h]; this
0x1800298ec  test    eax, eax
0x1800298ee  js      short loc_18002991F
0x1800298f0  mov     rbx, [rsp+0B8h+KeyHandle]
0x1800298f5  lea     rcx, [rsp+0B8h+var_38]
0x1800298fd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029902  mov     rax, rbx
0x180029905  mov     rcx, [rsp+0B8h+var_18]
0x18002990d  xor     rcx, rsp; StackCookie
0x180029910  call    __security_check_cookie
0x180029915  add     rsp, 0B0h
0x18002991c  pop     rbx
0x18002991d  retn
0x18002991f  mov     r9d, eax; char *
0x180029922  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\container"...
0x180029929  mov     edx, 471h; void *
0x18002992e  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
```
