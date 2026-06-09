# uf::details::GetHkcuKeyImpersonated(void)

- ea: `0x180062934`
- end: `0x180062993`
- name: `?GetHkcuKeyImpersonated@details@uf@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ`
- size: `95`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800232a0`
- `0x180060ac4`
- `0x180060c14`
- `0x180066a9c`

## callees

- `0x1800108cc`
- `0x180039c50`
- `0x180062934`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180062965`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180062965`

## string_xrefs

- `0x180062977`: `shellcommon\internal\shell\inc\UndockedFlighting\Impersonation.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall uf::details::GetHkcuKeyImpersonated(_QWORD *a1)
{
  HKEY *v2; // rax
  unsigned int v3; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *a1 = 0;
  v2 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(a1);
  v3 = RegOpenCurrentUser(0x2001Fu, v2);
  if ( v3 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x30,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\UndockedFlighting\\Impersonation.h",
      (const char *)v3,
      1u);
  return a1;
}

```

## disassembly

```asm
0x180062934  mov     [rsp+arg_0], rcx
0x180062939  push    rbx
0x18006293a  sub     rsp, 30h
0x18006293e  mov     rbx, rcx
0x180062941  mov     [rsp+38h+var_18], 0
0x180062949  mov     qword ptr [rcx], 0
0x180062950  mov     [rsp+38h+var_18], 1; unsigned int
0x180062958  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18006295d  mov     rdx, rax; phkResult
0x180062960  mov     ecx, 2001Fh; samDesired
0x180062965  call    cs:__imp_RegOpenCurrentUser
0x18006296b  test    eax, eax
0x18006296d  jz      short loc_180062989
0x18006296f  mov     rcx, [rsp+38h]; this
0x180062974  mov     r9d, eax; char *
0x180062977  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\Undo"...
0x18006297e  mov     edx, 30h ; '0'; void *
0x180062983  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180062989  mov     rax, rbx
0x18006298c  add     rsp, 30h
0x180062990  pop     rbx
0x180062991  retn
```
