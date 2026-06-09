# ThreadProcHelper::CheckAccess(void)

- ea: `0x180007050`
- end: `0x18000710b`
- name: `?CheckAccess@ThreadProcHelper@@UEAAJXZ`
- size: `187`
- prototype: `__int64 __fastcall(ThreadProcHelper *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180007050`
- `0x1800081e4`
- `0x180016344`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800070a7`
- `KERNEL32!LeaveCriticalSection` at `0x1800070f1`
- `KERNEL32!LeaveCriticalSection` at `0x1800070a7`
- `KERNEL32!LeaveCriticalSection` at `0x1800070f1`
- `KERNEL32!EnterCriticalSection` at `0x180007064`
- `KERNEL32!EnterCriticalSection` at `0x180007064`

## string_xrefs

- `0x180007086`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\threadprochelper.cpp`
- `0x1800070c2`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\threadprochelper.cpp`

## pseudocode

```c
__int64 __fastcall ThreadProcHelper::CheckAccess(ThreadProcHelper *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  bool v3; // zf
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  struct _RTL_CRITICAL_SECTION *v7; // [rsp+30h] [rbp+8h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v3 = *((_DWORD *)this + 23) == 1;
  v7 = v1;
  if ( !v3 || *((_DWORD *)this + 25) == 4 )
  {
    if ( *((_DWORD *)this + 24) )
    {
      if ( v1 )
        LeaveCriticalSection(v1);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7E,
        (unsigned int)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\threadprochelper.cpp",
        (const char *)0xC00D3EA2LL,
        v5);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v7);
      return 3222093474LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7C,
      (unsigned int)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\threadprochelper.cpp",
      (const char *)0x80070005LL,
      v5);
    if ( v1 )
      LeaveCriticalSection(v1);
    return 2147942405LL;
  }
}

```

## disassembly

```asm
0x180007050  mov     [rsp+arg_8], rbx
0x180007055  push    rdi; int
0x180007056  sub     rsp, 20h
0x18000705a  lea     rbx, [rcx+30h]
0x18000705e  mov     rdi, rcx
0x180007061  mov     rcx, rbx; lpCriticalSection
0x180007064  call    cs:__imp_EnterCriticalSection
0x18000706b  nop     dword ptr [rax+rax+00h]
0x180007070  cmp     dword ptr [rdi+5Ch], 1
0x180007074  mov     [rsp+28h+arg_0], rbx
0x180007079  jnz     short loc_1800070B7
0x18000707b  cmp     dword ptr [rdi+64h], 4
0x18000707f  jz      short loc_1800070B7
0x180007081  mov     rcx, [rsp+28h]; this
0x180007086  lea     r8, aMultimediaDsho_3; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x18000708d  mov     edi, 80070005h
0x180007092  mov     edx, 7Ch ; '|'; void *
0x180007097  mov     r9d, edi; char *
0x18000709a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000709f  test    rbx, rbx
0x1800070a2  jz      short loc_1800070B3
0x1800070a4  mov     rcx, rbx; lpCriticalSection
0x1800070a7  call    cs:__imp_LeaveCriticalSection
0x1800070ae  nop     dword ptr [rax+rax+00h]
0x1800070b3  mov     eax, edi
0x1800070b5  jmp     short loc_1800070FF
0x1800070b7  cmp     dword ptr [rdi+60h], 0
0x1800070bb  jnz     short loc_1800070E9
0x1800070bd  mov     rcx, [rsp+28h]; this
0x1800070c2  lea     r8, aMultimediaDsho_3; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x1800070c9  mov     ebx, 0C00D3EA2h
0x1800070ce  mov     edx, 7Eh ; '~'; void *
0x1800070d3  mov     r9d, ebx; char *
0x1800070d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800070db  lea     rcx, [rsp+28h+arg_0]
0x1800070e0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800070e5  mov     eax, ebx
0x1800070e7  jmp     short loc_1800070FF
0x1800070e9  test    rbx, rbx
0x1800070ec  jz      short loc_1800070FD
0x1800070ee  mov     rcx, rbx; lpCriticalSection
0x1800070f1  call    cs:__imp_LeaveCriticalSection
0x1800070f8  nop     dword ptr [rax+rax+00h]
0x1800070fd  xor     eax, eax
0x1800070ff  mov     rbx, [rsp+28h+arg_8]
0x180007104  add     rsp, 20h
0x180007108  pop     rdi
0x180007109  retn
```
