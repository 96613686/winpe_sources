# PublicNetworkListManager::RemoveGITandRegistrationCookie(std::map<ulong,CLIENT_CALLBACK_INTERFACE,std::less<ulong>,std::allocator<std::pair<ulong const,CLIENT_CALLBACK_INTERFACE>>> *,_RTL_CRITICAL_SECTION *,ulong,ulong *,int *)

- ea: `0x180028c24`
- end: `0x180028cfd`
- name: `?RemoveGITandRegistrationCookie@PublicNetworkListManager@@CAJPEAV?$map@KUCLIENT_CALLBACK_INTERFACE@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKUCLIENT_CALLBACK_INTERFACE@@@std@@@3@@std@@PEAU_RTL_CRITICAL_SECTION@@KPEAKPEAH@Z`
- size: `217`
- prototype: ``
- caller_count: `10`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180027630`
- `0x1800277e0`
- `0x180027900`
- `0x180027ab0`
- `0x180027bd0`
- `0x180027e10`
- `0x180027f80`
- `0x180028130`
- `0x180028250`
- `0x180028400`

## callees

- `0x180008218`
- `0x1800091b4`
- `0x18000924c`
- `0x180009d28`
- `0x18000a45c`
- `0x180028c24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028ca0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028ca0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028c4f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028c4f`

## pseudocode

```c
__int64 __fastcall PublicNetworkListManager::RemoveGITandRegistrationCookie(
        _QWORD *a1,
        struct _RTL_CRITICAL_SECTION *a2,
        int a3,
        _DWORD *a4,
        _DWORD *a5)
{
  __int64 v9; // rax
  AsyncEventDispatcher *v10; // rbx
  unsigned int v11; // edi
  __int64 v12; // r8
  unsigned int v13; // edx
  _DWORD v15[18]; // [rsp+30h] [rbp-48h] BYREF

  v15[0] = a3;
  EnterCriticalSection(a2);
  v9 = std::_Tree<std::_Tmap_traits<unsigned long,CLIENT_CALLBACK_INTERFACE,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,CLIENT_CALLBACK_INTERFACE>>,0>>::_Find<unsigned long>(
         a1,
         v15);
  if ( v9 == *a1 )
  {
    v10 = 0;
    v11 = -2147221500;
  }
  else
  {
    *a4 = *(_DWORD *)(v9 + 48);
    v10 = *(AsyncEventDispatcher **)(v9 + 40);
    std::_Tree<std::_Tmap_traits<unsigned long,CLIENT_CALLBACK_INTERFACE,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,CLIENT_CALLBACK_INTERFACE>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,CLIENT_CALLBACK_INTERFACE>>>>,0>(
      a1,
      v15,
      v9);
    v11 = 0;
  }
  if ( a5 )
    *a5 = a1[1] == 0;
  LeaveCriticalSection(a2);
  if ( !v11 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, v12, (unsigned int)*a4, a3);
    AsyncEventDispatcher::Shutdown(v10);
    if ( v10 )
      AsyncEventDispatcher::`scalar deleting destructor'(v10, v13);
  }
  return v11;
}

```

## disassembly

```asm
0x180028c24  push    rbx
0x180028c26  push    rbp
0x180028c27  push    rsi
0x180028c28  push    rdi
0x180028c29  push    r12
0x180028c2b  push    r14
0x180028c2d  push    r15
0x180028c2f  sub     rsp, 40h
0x180028c33  mov     r14, [rsp+78h+arg_20]
0x180028c3b  mov     rsi, rcx
0x180028c3e  mov     rcx, rdx; lpCriticalSection
0x180028c41  mov     [rsp+78h+var_48], r8d
0x180028c46  mov     r15, r9
0x180028c49  mov     r12d, r8d
0x180028c4c  mov     rbp, rdx
0x180028c4f  call    cs:__imp_EnterCriticalSection
0x180028c55  lea     rdx, [rsp+78h+var_48]
0x180028c5a  mov     rcx, rsi
0x180028c5d  call    ??$_Find@K@?$_Tree@V?$_Tmap_traits@KUCLIENT_CALLBACK_INTERFACE@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKUCLIENT_CALLBACK_INTERFACE@@@std@@@3@$0A@@std@@@std@@AEBAPEAU?$_Tree_node@U?$pair@$$CBKUCLIENT_CALLBACK_INTERFACE@@@std@@PEAX@1@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,CLIENT_CALLBACK_INTERFACE,std::less<ulong>,std::allocator<std::pair<ulong const,CLIENT_CALLBACK_INTERFACE>>,0>>::_Find<ulong>(ulong const &)
0x180028c62  cmp     rax, [rsi]
0x180028c65  jz      short loc_180028C85
0x180028c67  mov     ecx, [rax+30h]
0x180028c6a  lea     rdx, [rsp+78h+var_48]
0x180028c6f  mov     [r15], ecx
0x180028c72  mov     r8, rax
0x180028c75  mov     rbx, [rax+28h]
0x180028c79  mov     rcx, rsi
0x180028c7c  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKUCLIENT_CALLBACK_INTERFACE@@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@KUCLIENT_CALLBACK_INTERFACE@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKUCLIENT_CALLBACK_INTERFACE@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKUCLIENT_CALLBACK_INTERFACE@@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<ulong,CLIENT_CALLBACK_INTERFACE,std::less<ulong>,std::allocator<std::pair<ulong const,CLIENT_CALLBACK_INTERFACE>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,CLIENT_CALLBACK_INTERFACE>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,CLIENT_CALLBACK_INTERFACE>>>>)
0x180028c81  xor     edi, edi
0x180028c83  jmp     short loc_180028C8C
0x180028c85  xor     ebx, ebx
0x180028c87  mov     edi, 80040004h
0x180028c8c  test    r14, r14
0x180028c8f  jz      short loc_180028C9D
0x180028c91  xor     eax, eax
0x180028c93  cmp     [rsi+8], rax
0x180028c97  setz    al
0x180028c9a  mov     [r14], eax
0x180028c9d  mov     rcx, rbp; lpCriticalSection
0x180028ca0  call    cs:__imp_LeaveCriticalSection
0x180028ca6  test    edi, edi
0x180028ca8  jnz     short loc_180028CEC
0x180028caa  mov     rcx, cs:WPP_GLOBAL_Control
0x180028cb1  lea     rax, WPP_GLOBAL_Control
0x180028cb8  cmp     rcx, rax
0x180028cbb  jz      short loc_180028CD7
0x180028cbd  test    byte ptr [rcx+1Ch], 8
0x180028cc1  jz      short loc_180028CD7
0x180028cc3  mov     r9d, [r15]
0x180028cc6  lea     edx, [rdi+66h]
0x180028cc9  mov     rcx, [rcx+10h]
0x180028ccd  mov     [rsp+78h+var_58], r12d
0x180028cd2  call    WPP_SF_DD
0x180028cd7  mov     rcx, rbx; this
0x180028cda  call    ?Shutdown@AsyncEventDispatcher@@QEAAXXZ; AsyncEventDispatcher::Shutdown(void)
0x180028cdf  test    rbx, rbx
0x180028ce2  jz      short loc_180028CEC
0x180028ce4  mov     rcx, rbx; this
0x180028ce7  call    ??_GAsyncEventDispatcher@@QEAAPEAXI@Z; AsyncEventDispatcher::`scalar deleting destructor'(uint)
0x180028cec  mov     eax, edi
0x180028cee  add     rsp, 40h
0x180028cf2  pop     r15
0x180028cf4  pop     r14
0x180028cf6  pop     r12
0x180028cf8  pop     rdi
0x180028cf9  pop     rsi
0x180028cfa  pop     rbp
0x180028cfb  pop     rbx
0x180028cfc  retn
```
