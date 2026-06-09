# DialupConnection::HrEnsureHNetPropertiesCached(void)

- ea: `0x18002c748`
- end: `0x18002c864`
- name: `?HrEnsureHNetPropertiesCached@DialupConnection@@QEAAJXZ`
- size: `284`
- prototype: `__int64 __fastcall(DialupConnection *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002b2d0`
- `0x18002c86c`

## callees

- `0x180001710`
- `0x1800084fc`
- `0x18002c748`
- `0x18002cd44`
- `0x1800306f8`
- `0x180036010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18002c76e`
- `KERNEL32!EnterCriticalSection` at `0x18002c76e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c80c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c80c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DialupConnection::HrEnsureHNetPropertiesCached(DialupConnection *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  int v3; // ebx
  _DWORD *v4; // rcx
  struct _RTL_CRITICAL_SECTION *v6; // [rsp+20h] [rbp-28h] BYREF
  struct IUnknown *v7; // [rsp+28h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-18h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 320);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 8);
  v6 = v2;
  if ( !*((_DWORD *)this + 74) || (v3 = 0, *((_DWORD *)this + 75) != g_lHNetModifiedEra) )
  {
    if ( _InterlockedExchange((volatile __int32 *)this + 76, 1) )
    {
      v3 = 1;
    }
    else
    {
      v7 = 0;
      pv = 0;
      if ( (int)DialupConnection::HrGetIHNetConnection(this, (struct IHNetConnection **)&v7) < 0 )
      {
        v3 = 1;
      }
      else
      {
        v3 = ((__int64 (__fastcall *)(struct IUnknown *, LPVOID *))v7->lpVtbl[2].AddRef)(v7, &pv);
        ReleaseObj(v7);
        if ( v3 >= 0 )
        {
          v4 = pv;
          *(_QWORD *)((char *)this + 308) = *(_QWORD *)pv;
          *((_DWORD *)this + 79) = v4[2];
          CoTaskMemFree(v4);
          _InterlockedExchange((volatile __int32 *)this + 75, g_lHNetModifiedEra);
          *((_DWORD *)this + 74) = 1;
          v3 = 0;
        }
      }
      _InterlockedExchange((volatile __int32 *)this + 76, 0);
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v6);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002c748  mov     [rsp+arg_8], rbx
0x18002c74d  push    rdi
0x18002c74e  sub     rsp, 40h
0x18002c752  mov     rax, cs:__security_cookie
0x18002c759  xor     rax, rsp
0x18002c75c  mov     [rsp+48h+var_10], rax
0x18002c761  mov     rdi, rcx
0x18002c764  lea     rbx, [rcx+140h]
0x18002c76b  mov     rcx, rbx; lpCriticalSection
0x18002c76e  call    cs:__imp_EnterCriticalSection
0x18002c774  mov     [rsp+48h+var_28], rbx
0x18002c779  cmp     dword ptr [rdi+128h], 0
0x18002c780  jz      short loc_18002C796
0x18002c782  xor     ebx, ebx
0x18002c784  mov     eax, cs:?g_lHNetModifiedEra@@3JA; long g_lHNetModifiedEra
0x18002c78a  cmp     [rdi+12Ch], eax
0x18002c790  jz      loc_18002C840
0x18002c796  mov     eax, 1
0x18002c79b  xchg    eax, [rdi+130h]
0x18002c7a1  test    eax, eax
0x18002c7a3  jnz     loc_18002C83B
0x18002c7a9  mov     [rsp+48h+var_20], 0
0x18002c7b2  mov     [rsp+48h+pv], 0
0x18002c7bb  lea     rdx, [rsp+48h+var_20]; struct IHNetConnection **
0x18002c7c0  mov     rcx, rdi; this
0x18002c7c3  call    ?HrGetIHNetConnection@DialupConnection@@QEAAJPEAPEAUIHNetConnection@@@Z; DialupConnection::HrGetIHNetConnection(IHNetConnection * *)
0x18002c7c8  test    eax, eax
0x18002c7ca  js      short loc_18002C82C
0x18002c7cc  mov     rcx, [rsp+48h+var_20]
0x18002c7d1  mov     rax, [rcx]
0x18002c7d4  lea     rdx, [rsp+48h+pv]
0x18002c7d9  mov     rax, [rax+38h]
0x18002c7dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c7e2  mov     ebx, eax
0x18002c7e4  mov     rcx, [rsp+48h+var_20]; struct IUnknown *
0x18002c7e9  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18002c7ee  test    ebx, ebx
0x18002c7f0  js      short loc_18002C831
0x18002c7f2  mov     rcx, [rsp+48h+pv]; pv
0x18002c7f7  movsd   xmm0, qword ptr [rcx]
0x18002c7fb  movsd   qword ptr [rdi+134h], xmm0
0x18002c803  mov     eax, [rcx+8]
0x18002c806  mov     [rdi+13Ch], eax
0x18002c80c  call    cs:__imp_CoTaskMemFree
0x18002c812  mov     eax, cs:?g_lHNetModifiedEra@@3JA; long g_lHNetModifiedEra
0x18002c818  xchg    eax, [rdi+12Ch]
0x18002c81e  mov     dword ptr [rdi+128h], 1
0x18002c828  xor     ebx, ebx
0x18002c82a  jmp     short loc_18002C831
0x18002c82c  mov     ebx, 1
0x18002c831  xor     eax, eax
0x18002c833  xchg    eax, [rdi+130h]
0x18002c839  jmp     short loc_18002C840
0x18002c83b  mov     ebx, 1
0x18002c840  lea     rcx, [rsp+48h+var_28]
0x18002c845  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002c84a  mov     eax, ebx
0x18002c84c  mov     rcx, [rsp+48h+var_10]
0x18002c851  xor     rcx, rsp; StackCookie
0x18002c854  call    __security_check_cookie
0x18002c859  mov     rbx, [rsp+48h+arg_8]
0x18002c85e  add     rsp, 40h
0x18002c862  pop     rdi
0x18002c863  retn
```
