# CapabilityAccessHelper::Shutdown(void)

- ea: `0x1800443d0`
- end: `0x180044456`
- name: `?Shutdown@CapabilityAccessHelper@@UEAAJXZ`
- size: `134`
- prototype: `__int64 __fastcall(CapabilityAccessHelper *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180043dbc`

## callees

- `0x1800081e4`
- `0x180016344`
- `0x1800443d0`
- `0x180045010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800443e4`
- `KERNEL32!EnterCriticalSection` at `0x1800443e4`

## string_xrefs

- `0x18004441e`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\capabilityaccesshelper.cpp`

## pseudocode

```c
__int64 __fastcall CapabilityAccessHelper::Shutdown(CapabilityAccessHelper *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  __int64 v3; // rdx
  __int64 v4; // rcx
  int v5; // eax
  unsigned int v6; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  struct _RTL_CRITICAL_SECTION *v9; // [rsp+30h] [rbp+8h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v3 = *((_QWORD *)this + 15);
  v9 = v1;
  if ( !v3 )
    goto LABEL_6;
  v4 = *((_QWORD *)this + 14);
  if ( !v4 )
    goto LABEL_6;
  v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 88LL))(v4);
  v6 = v5;
  if ( v5 >= 0 )
  {
    *((_QWORD *)this + 15) = 0;
LABEL_6:
    v6 = 0;
    goto LABEL_7;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x55,
    (int)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\capabilityaccesshelper.cpp",
    (const char *)(unsigned int)v5);
LABEL_7:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v9);
  return v6;
}

```

## disassembly

```asm
0x1800443d0  mov     [rsp+arg_8], rbx
0x1800443d5  push    rdi; int
0x1800443d6  sub     rsp, 20h
0x1800443da  lea     rbx, [rcx+40h]
0x1800443de  mov     rdi, rcx
0x1800443e1  mov     rcx, rbx; lpCriticalSection
0x1800443e4  call    cs:__imp_EnterCriticalSection
0x1800443eb  nop     dword ptr [rax+rax+00h]
0x1800443f0  mov     rdx, [rdi+78h]
0x1800443f4  mov     [rsp+28h+arg_0], rbx
0x1800443f9  test    rdx, rdx
0x1800443fc  jz      short loc_18004443C
0x1800443fe  mov     rcx, [rdi+70h]
0x180044402  test    rcx, rcx
0x180044405  jz      short loc_18004443C
0x180044407  mov     rax, [rcx]
0x18004440a  mov     rax, [rax+58h]
0x18004440e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044413  mov     ebx, eax
0x180044415  test    eax, eax
0x180044417  jns     short loc_180044434
0x180044419  mov     rcx, [rsp+28h]; this
0x18004441e  lea     r8, aMultimediaDsho_4; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x180044425  mov     r9d, eax; char *
0x180044428  mov     edx, 55h ; 'U'; void *
0x18004442d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044432  jmp     short loc_18004443E
0x180044434  mov     qword ptr [rdi+78h], 0
0x18004443c  xor     ebx, ebx
0x18004443e  lea     rcx, [rsp+28h+arg_0]
0x180044443  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180044448  mov     eax, ebx
0x18004444a  mov     rbx, [rsp+28h+arg_8]
0x18004444f  add     rsp, 20h
0x180044453  pop     rdi
0x180044454  retn
```
