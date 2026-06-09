# DialupConnection::GetPropertiesEx(tagNETCON_PROPERTIES_EX * *)

- ea: `0x18002c0c0`
- end: `0x18002c218`
- name: `?GetPropertiesEx@DialupConnection@@UEAAJPEAPEAUtagNETCON_PROPERTIES_EX@@@Z`
- size: `344`
- prototype: `__int64 __fastcall(DialupConnection *__hidden this, struct tagNETCON_PROPERTIES_EX **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001710`
- `0x180002320`
- `0x18000538c`
- `0x1800084fc`
- `0x18002c0c0`
- `0x180030714`
- `0x180031d0c`
- `0x180036010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18002c0f2`
- `KERNEL32!EnterCriticalSection` at `0x18002c0f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c129`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c129`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c1ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c1ad`
- `OLEAUT32!__imp_SysAllocString` at `0x18002c18f`
- `OLEAUT32!__imp_SysAllocString` at `0x18002c18f`

## pseudocode

```c
__int64 __fastcall DialupConnection::GetPropertiesEx(
        struct _RTL_CRITICAL_SECTION *this,
        struct tagNETCON_PROPERTIES_EX **a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  bool v5; // zf
  int v6; // ebx
  struct tagNETCON_PROPERTIES_EX *v7; // rax
  struct tagNETCON_PROPERTIES_EX *v8; // rdi
  const OLECHAR *p_OwningThread; // rcx
  struct _RTL_CRITICAL_SECTION *v11; // [rsp+20h] [rbp-38h] BYREF
  struct tagNETCON_PROPERTIES *pv; // [rsp+28h] [rbp-30h] BYREF

  v2 = this + 7;
  EnterCriticalSection(this + 7);
  *a2 = 0;
  v5 = LODWORD(this[1].LockSemaphore) == 0;
  v11 = v2;
  if ( v5 )
  {
    v6 = -2147418113;
LABEL_12:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        &WPP_72e8a2b6c4a334b644d76a8a8dce3e8a_Traceguids,
        (unsigned int)v6);
    goto LABEL_15;
  }
  pv = 0;
  v7 = (struct tagNETCON_PROPERTIES_EX *)CoTaskMemAlloc(0x68u);
  v8 = v7;
  if ( !v7 )
  {
    v6 = -2147024882;
    goto LABEL_12;
  }
  memset_0(v7, 0, 0x68u);
  v6 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *, struct tagNETCON_PROPERTIES **))this[-1].DebugInfo[1].CriticalSection)(
         &this[-1],
         &pv);
  if ( v6 < 0 )
    goto LABEL_10;
  v6 = HrBuildPropertiesExFromProperties(
         pv,
         v8,
         (struct IPersistNetConnection *)((unsigned __int64)&this[-1].OwningThread
                                        & -(__int64)(this != (struct _RTL_CRITICAL_SECTION *)40)));
  if ( v6 >= 0 )
  {
    p_OwningThread = (const OLECHAR *)&this[5].OwningThread;
    if ( this[6].DebugInfo > (PRTL_CRITICAL_SECTION_DEBUG)7 )
      p_OwningThread = *(const OLECHAR **)p_OwningThread;
    *((_QWORD *)v8 + 11) = SysAllocString(p_OwningThread);
    *a2 = v8;
  }
  FreeNetconProperties(pv);
  if ( v6 < 0 )
  {
LABEL_10:
    CoTaskMemFree(v8);
    goto LABEL_12;
  }
LABEL_15:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v11);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002c0c0  mov     [rsp+arg_10], rbx
0x18002c0c5  mov     [rsp+arg_18], rsi
0x18002c0ca  push    rdi
0x18002c0cb  push    r14
0x18002c0cd  push    r15
0x18002c0cf  sub     rsp, 40h
0x18002c0d3  mov     rax, cs:__security_cookie
0x18002c0da  xor     rax, rsp
0x18002c0dd  mov     [rsp+58h+var_28], rax
0x18002c0e2  lea     rbx, [rcx+118h]
0x18002c0e9  mov     rsi, rcx
0x18002c0ec  mov     rcx, rbx; lpCriticalSection
0x18002c0ef  mov     r15, rdx
0x18002c0f2  call    cs:__imp_EnterCriticalSection
0x18002c0f8  lea     r14, [rsi-28h]
0x18002c0fc  mov     qword ptr [r15], 0
0x18002c103  cmp     dword ptr [r14+68h], 0
0x18002c108  mov     [rsp+58h+var_38], rbx
0x18002c10d  jnz     short loc_18002C119
0x18002c10f  mov     ebx, 8000FFFFh
0x18002c114  jmp     loc_18002C1BA
0x18002c119  mov     ebx, 68h ; 'h'
0x18002c11e  mov     [rsp+58h+pv], 0
0x18002c127  mov     ecx, ebx; cb
0x18002c129  call    cs:__imp_CoTaskMemAlloc
0x18002c12f  mov     rdi, rax
0x18002c132  test    rax, rax
0x18002c135  jz      short loc_18002C1B5
0x18002c137  mov     r8d, ebx; Size
0x18002c13a  xor     edx, edx; Val
0x18002c13c  mov     rcx, rax; void *
0x18002c13f  call    memset_0
0x18002c144  mov     rax, [r14]
0x18002c147  lea     rdx, [rsp+58h+pv]
0x18002c14c  mov     rcx, r14
0x18002c14f  mov     rax, [rax+38h]
0x18002c153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c158  mov     ebx, eax
0x18002c15a  test    eax, eax
0x18002c15c  js      short loc_18002C1AA
0x18002c15e  mov     rcx, [rsp+58h+pv]; struct tagNETCON_PROPERTIES *
0x18002c163  lea     rax, [rsi-18h]
0x18002c167  neg     r14
0x18002c16a  mov     rdx, rdi; struct tagNETCON_PROPERTIES_EX *
0x18002c16d  sbb     r8, r8
0x18002c170  and     r8, rax; struct IPersistNetConnection *
0x18002c173  call    ?HrBuildPropertiesExFromProperties@@YAJPEAUtagNETCON_PROPERTIES@@PEAUtagNETCON_PROPERTIES_EX@@PEAUIPersistNetConnection@@@Z; HrBuildPropertiesExFromProperties(tagNETCON_PROPERTIES *,tagNETCON_PROPERTIES_EX *,IPersistNetConnection *)
0x18002c178  mov     ebx, eax
0x18002c17a  test    eax, eax
0x18002c17c  js      short loc_18002C19C
0x18002c17e  lea     rcx, [rsi+0D8h]
0x18002c185  cmp     qword ptr [rcx+18h], 7
0x18002c18a  jbe     short loc_18002C18F
0x18002c18c  mov     rcx, [rcx]; psz
0x18002c18f  call    cs:__imp_SysAllocString
0x18002c195  mov     [rdi+58h], rax
0x18002c199  mov     [r15], rdi
0x18002c19c  mov     rcx, [rsp+58h+pv]; pv
0x18002c1a1  call    ?FreeNetconProperties@@YAXPEAUtagNETCON_PROPERTIES@@@Z; FreeNetconProperties(tagNETCON_PROPERTIES *)
0x18002c1a6  test    ebx, ebx
0x18002c1a8  jns     short loc_18002C1EB
0x18002c1aa  mov     rcx, rdi; pv
0x18002c1ad  call    cs:__imp_CoTaskMemFree
0x18002c1b3  jmp     short loc_18002C1BA
0x18002c1b5  mov     ebx, 8007000Eh
0x18002c1ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c1c1  lea     rax, WPP_GLOBAL_Control
0x18002c1c8  cmp     rcx, rax
0x18002c1cb  jz      short loc_18002C1EB
0x18002c1cd  test    byte ptr [rcx+1Ch], 1
0x18002c1d1  jz      short loc_18002C1EB
0x18002c1d3  mov     rcx, [rcx+10h]
0x18002c1d7  lea     r8, WPP_72e8a2b6c4a334b644d76a8a8dce3e8a_Traceguids
0x18002c1de  mov     edx, 29h ; ')'
0x18002c1e3  mov     r9d, ebx
0x18002c1e6  call    WPP_SF_d
0x18002c1eb  lea     rcx, [rsp+58h+var_38]
0x18002c1f0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002c1f5  mov     eax, ebx
0x18002c1f7  mov     rcx, [rsp+58h+var_28]
0x18002c1fc  xor     rcx, rsp; StackCookie
0x18002c1ff  call    __security_check_cookie
0x18002c204  mov     rbx, [rsp+58h+arg_10]
0x18002c209  mov     rsi, [rsp+58h+arg_18]
0x18002c20e  add     rsp, 40h
0x18002c212  pop     r15
0x18002c214  pop     r14
0x18002c216  pop     rdi
0x18002c217  retn
```
