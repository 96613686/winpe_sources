# PublicNetworkListManager::PostNetworkListManagerEvent(ulong,ulong)

- ea: `0x180028948`
- end: `0x180028a43`
- name: `?PostNetworkListManagerEvent@PublicNetworkListManager@@IEAAJKK@Z`
- size: `251`
- prototype: `__int64 __fastcall(PublicNetworkListManager *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18002e700`

## callees

- `0x180006f60`
- `0x180008160`
- `0x180008530`
- `0x180028948`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028a2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028a2e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028967`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028967`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028a06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028a06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002898e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002898e`

## pseudocode

```c
__int64 __fastcall PublicNetworkListManager::PostNetworkListManagerEvent(
        struct _RTL_CRITICAL_SECTION *this,
        __int64 a2,
        int a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // r14
  unsigned int v5; // esi
  __int64 v7; // rbx
  GUID *v8; // rax
  __int64 v9; // r8
  GUID *v10; // rdi
  __int64 v12[9]; // [rsp+30h] [rbp-48h] BYREF

  v3 = this + 7;
  v5 = 0;
  EnterCriticalSection(this + 7);
  v7 = *(_QWORD *)this[8].DebugInfo;
  for ( v12[0] = v7; (PRTL_CRITICAL_SECTION_DEBUG)v7 != this[8].DebugInfo; v7 = v12[0] )
  {
    v8 = (GUID *)CoTaskMemAlloc(0x18u);
    v10 = v8;
    if ( v8 )
    {
      v8[1].Data1 = 1;
      *(_DWORD *)&v8[1].Data2 = a3;
      *v8 = GUID_NULL;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_LLL(*((_QWORD *)WPP_GLOBAL_Control + 2), 111, v9, *(unsigned int *)(v7 + 32), 1, a3);
      v5 = AsyncEventDispatcher::Dispatch(
             *(AsyncEventDispatcher **)(v7 + 40),
             (__int64)this,
             *(unsigned int *)(v7 + 32),
             (__int64)v10);
      if ( v5 )
        CoTaskMemFree(v10);
    }
    else
    {
      v5 = -2147024882;
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,CLIENT_CALLBACK_INTERFACE>>>,std::_Iterator_base0>::operator++(v12);
    if ( v5 )
      break;
  }
  LeaveCriticalSection(v3);
  return v5;
}

```

## disassembly

```asm
0x180028948  push    rbx
0x18002894a  push    rbp
0x18002894b  push    rsi
0x18002894c  push    rdi
0x18002894d  push    r14
0x18002894f  push    r15
0x180028951  sub     rsp, 48h
0x180028955  lea     r14, [rcx+118h]
0x18002895c  mov     rbp, rcx
0x18002895f  mov     rcx, r14; lpCriticalSection
0x180028962  xor     esi, esi
0x180028964  mov     r15d, r8d
0x180028967  call    cs:__imp_EnterCriticalSection
0x18002896d  mov     rbx, [rbp+140h]
0x180028974  mov     rbx, [rbx]
0x180028977  mov     [rsp+78h+var_48], rbx
0x18002897c  cmp     rbx, [rbp+140h]
0x180028983  jz      loc_180028A2B
0x180028989  mov     ecx, 18h; cb
0x18002898e  call    cs:__imp_CoTaskMemAlloc
0x180028994  mov     rdi, rax
0x180028997  test    rax, rax
0x18002899a  jz      short loc_180028A0E
0x18002899c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800289a3  mov     dword ptr [rax+10h], 1
0x1800289aa  mov     [rax+14h], r15d
0x1800289ae  movdqu  xmmword ptr [rax], xmm0
0x1800289b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800289b9  lea     rax, WPP_GLOBAL_Control
0x1800289c0  cmp     rcx, rax
0x1800289c3  jz      short loc_1800289EA
0x1800289c5  test    byte ptr [rcx+1Ch], 8
0x1800289c9  jz      short loc_1800289EA
0x1800289cb  mov     r9d, [rbx+20h]
0x1800289cf  mov     edx, 6Fh ; 'o'
0x1800289d4  mov     rcx, [rcx+10h]
0x1800289d8  mov     [rsp+78h+var_50], r15d
0x1800289dd  mov     [rsp+78h+var_58], 1
0x1800289e5  call    WPP_SF_LLL
0x1800289ea  mov     r8d, [rbx+20h]; unsigned __int64
0x1800289ee  mov     r9, rdi; unsigned __int64
0x1800289f1  mov     rcx, [rbx+28h]; this
0x1800289f5  mov     rdx, rbp; unsigned __int64
0x1800289f8  call    ?Dispatch@AsyncEventDispatcher@@QEAAJ_K00@Z; AsyncEventDispatcher::Dispatch(unsigned __int64,unsigned __int64,unsigned __int64)
0x1800289fd  mov     esi, eax
0x1800289ff  test    eax, eax
0x180028a01  jz      short loc_180028A13
0x180028a03  mov     rcx, rdi; pv
0x180028a06  call    cs:__imp_CoTaskMemFree
0x180028a0c  jmp     short loc_180028A13
0x180028a0e  mov     esi, 8007000Eh
0x180028a13  lea     rcx, [rsp+78h+var_48]
0x180028a18  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKUCLIENT_CALLBACK_INTERFACE@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,CLIENT_CALLBACK_INTERFACE>>>,std::_Iterator_base0>::operator++(void)
0x180028a1d  test    esi, esi
0x180028a1f  jnz     short loc_180028A2B
0x180028a21  mov     rbx, [rsp+78h+var_48]
0x180028a26  jmp     loc_18002897C
0x180028a2b  mov     rcx, r14; lpCriticalSection
0x180028a2e  call    cs:__imp_LeaveCriticalSection
0x180028a34  mov     eax, esi
0x180028a36  add     rsp, 48h
0x180028a3a  pop     r15
0x180028a3c  pop     r14
0x180028a3e  pop     rdi
0x180028a3f  pop     rsi
0x180028a40  pop     rbp
0x180028a41  pop     rbx
0x180028a42  retn
```
