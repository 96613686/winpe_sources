# CConnectivityWatcher::UnregisterForConnectivityNotification(void)

- ea: `0x1800105e4`
- end: `0x180010684`
- name: `?UnregisterForConnectivityNotification@CConnectivityWatcher@@QEAAJXZ`
- size: `160`
- prototype: `__int64 __fastcall(CConnectivityWatcher *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800066f8`

## callees

- `0x18000fe98`
- `0x1800105e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800105fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800105fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010658`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010658`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001064a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001064a`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001063d`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001066c`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001063d`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001066c`

## pseudocode

```c
__int64 __fastcall CConnectivityWatcher::UnregisterForConnectivityNotification(CConnectivityWatcher *this)
{
  char *v1; // rbx
  _QWORD *v3; // rdi
  __int64 v4; // rcx
  void *v5; // rbx
  HANDLE ProcessHeap; // rax
  char *v8; // [rsp+30h] [rbp+8h] BYREF

  v1 = (char *)this + 16;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v3 = (_QWORD *)*((_QWORD *)this + 10);
  v8 = v1;
  LODWORD(v1) = *((_DWORD *)this + 14);
  *((_DWORD *)this + 14) = 1;
  *((_QWORD *)this + 10) = 0;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v8);
  if ( !(_DWORD)v1 )
  {
    while ( v3 )
    {
      if ( *(_DWORD *)v3 )
      {
        v4 = v3[4];
        *(_DWORD *)v3 = 0;
        RtlUnsubscribeWnfNotificationWaitForCompletion(v4);
      }
      v5 = v3;
      v3 = (_QWORD *)v3[5];
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v5);
    }
    if ( *((_DWORD *)this + 15) )
      RtlUnsubscribeWnfNotificationWaitForCompletion(*((_QWORD *)this + 9));
  }
  return 0;
}

```

## disassembly

```asm
0x1800105e4  mov     [rsp+arg_8], rbx
0x1800105e9  mov     [rsp+arg_10], rsi
0x1800105ee  push    rdi
0x1800105ef  sub     rsp, 20h
0x1800105f3  lea     rbx, [rcx+10h]
0x1800105f7  mov     rsi, rcx
0x1800105fa  mov     rcx, rbx; lpCriticalSection
0x1800105fd  call    cs:__imp_EnterCriticalSection
0x180010603  mov     rdi, [rsi+50h]
0x180010607  lea     rcx, [rsp+28h+arg_0]
0x18001060c  mov     [rsp+28h+arg_0], rbx
0x180010611  mov     ebx, [rsi+38h]
0x180010614  mov     dword ptr [rsi+38h], 1
0x18001061b  mov     qword ptr [rsi+50h], 0
0x180010623  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180010628  test    ebx, ebx
0x18001062a  jnz     short loc_180010672
0x18001062c  jmp     short loc_18001065E
0x18001062e  cmp     dword ptr [rdi], 0
0x180010631  jz      short loc_180010643
0x180010633  mov     rcx, [rdi+20h]
0x180010637  mov     dword ptr [rdi], 0
0x18001063d  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180010643  mov     rbx, rdi
0x180010646  mov     rdi, [rdi+28h]
0x18001064a  call    cs:__imp_GetProcessHeap
0x180010650  mov     r8, rbx; lpMem
0x180010653  xor     edx, edx; dwFlags
0x180010655  mov     rcx, rax; hHeap
0x180010658  call    cs:__imp_HeapFree
0x18001065e  test    rdi, rdi
0x180010661  jnz     short loc_18001062E
0x180010663  cmp     [rsi+3Ch], edi
0x180010666  jz      short loc_180010672
0x180010668  mov     rcx, [rsi+48h]
0x18001066c  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180010672  mov     rbx, [rsp+28h+arg_8]
0x180010677  xor     eax, eax
0x180010679  mov     rsi, [rsp+28h+arg_10]
0x18001067e  add     rsp, 20h
0x180010682  pop     rdi
0x180010683  retn
```
