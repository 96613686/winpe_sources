# KsProxyCameraAccessHandler::Close(void)

- ea: `0x1800428e0`
- end: `0x180042943`
- name: `?Close@KsProxyCameraAccessHandler@@UEAAJXZ`
- size: `99`
- prototype: `__int64 __fastcall(KsProxyCameraAccessHandler *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x1800081e4`
- `0x180016344`
- `0x1800428e0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800428f4`
- `KERNEL32!EnterCriticalSection` at `0x1800428f4`

## string_xrefs

- `0x180042912`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\ksproxycameraaccesshandler.cpp`

## pseudocode

```c
__int64 __fastcall KsProxyCameraAccessHandler::Close(KsProxyCameraAccessHandler *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  unsigned int v3; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  struct _RTL_CRITICAL_SECTION *v6; // [rsp+30h] [rbp+8h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v6 = v1;
  v3 = 0;
  if ( !*((_QWORD *)this + 2) )
  {
    v3 = -2147483634;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46,
      (int)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\ksproxycameraaccesshandler.cpp",
      (const char *)0x8000000ELL);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v6);
  return v3;
}

```

## disassembly

```asm
0x1800428e0  mov     [rsp+arg_8], rbx
0x1800428e5  push    rdi; int
0x1800428e6  sub     rsp, 20h
0x1800428ea  lea     rbx, [rcx+18h]
0x1800428ee  mov     rdi, rcx
0x1800428f1  mov     rcx, rbx; lpCriticalSection
0x1800428f4  call    cs:__imp_EnterCriticalSection
0x1800428fb  nop     dword ptr [rax+rax+00h]
0x180042900  mov     [rsp+28h+arg_0], rbx
0x180042905  xor     ebx, ebx
0x180042907  cmp     [rdi+10h], rbx
0x18004290b  jnz     short loc_18004292B
0x18004290d  mov     rcx, [rsp+28h]; this
0x180042912  lea     r8, aMultimediaDsho_2; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x180042919  mov     ebx, 8000000Eh
0x18004291e  mov     edx, 46h ; 'F'; void *
0x180042923  mov     r9d, ebx; char *
0x180042926  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004292b  lea     rcx, [rsp+28h+arg_0]
0x180042930  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180042935  mov     eax, ebx
0x180042937  mov     rbx, [rsp+28h+arg_8]
0x18004293c  add     rsp, 20h
0x180042940  pop     rdi
0x180042941  retn
```
