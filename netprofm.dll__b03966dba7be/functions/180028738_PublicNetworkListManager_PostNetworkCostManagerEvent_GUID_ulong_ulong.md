# PublicNetworkListManager::PostNetworkCostManagerEvent(_GUID,ulong,ulong)

- ea: `0x180028738`
- end: `0x180028839`
- name: `?PostNetworkCostManagerEvent@PublicNetworkListManager@@IEAAJU_GUID@@KK@Z`
- size: `257`
- prototype: `__int64 __fastcall(PublicNetworkListManager *__hidden this, struct _GUID *__struct_ptr, unsigned int, unsigned int)`
- caller_count: `6`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000d0b4`
- `0x180020388`
- `0x1800220c8`
- `0x180022650`
- `0x18002e800`
- `0x18002e920`

## callees

- `0x180006f60`
- `0x180008160`
- `0x180008530`
- `0x180028738`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028820`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028820`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028761`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028761`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800287f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800287f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028788`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028788`

## pseudocode

```c
__int64 __fastcall PublicNetworkListManager::PostNetworkCostManagerEvent(
        PublicNetworkListManager *this,
        struct _GUID *a2,
        unsigned int a3,
        int a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // r14
  unsigned int v6; // esi
  __int64 v10; // rbx
  struct _GUID *v11; // rax
  __int64 v12; // r8
  struct _GUID *v13; // rdi
  __int64 v15[11]; // [rsp+30h] [rbp-58h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 504);
  v6 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 504));
  v10 = **((_QWORD **)this + 68);
  for ( v15[0] = v10; v10 != *((_QWORD *)this + 68); v10 = v15[0] )
  {
    v11 = (struct _GUID *)CoTaskMemAlloc(0x18u);
    v13 = v11;
    if ( v11 )
    {
      *v11 = *a2;
      v11[1].Data1 = a3;
      *(_DWORD *)&v11[1].Data2 = a4;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_LLL(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, v12, *(unsigned int *)(v10 + 32), a3, a4);
      v6 = AsyncEventDispatcher::Dispatch(
             *(AsyncEventDispatcher **)(v10 + 40),
             (__int64)this,
             *(unsigned int *)(v10 + 32),
             (__int64)v13);
      if ( v6 )
        CoTaskMemFree(v13);
    }
    else
    {
      v6 = -2147024882;
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,CLIENT_CALLBACK_INTERFACE>>>,std::_Iterator_base0>::operator++(v15);
    if ( v6 )
      break;
  }
  LeaveCriticalSection(v4);
  return v6;
}

```

## disassembly

```asm
0x180028738  push    rbx
0x18002873a  push    rbp
0x18002873b  push    rsi
0x18002873c  push    rdi
0x18002873d  push    r12
0x18002873f  push    r13
0x180028741  push    r14
0x180028743  push    r15
0x180028745  sub     rsp, 48h
0x180028749  lea     r14, [rcx+1F8h]
0x180028750  mov     rbp, rcx
0x180028753  mov     rcx, r14; lpCriticalSection
0x180028756  xor     esi, esi
0x180028758  mov     r15d, r9d
0x18002875b  mov     r12d, r8d
0x18002875e  mov     r13, rdx
0x180028761  call    cs:__imp_EnterCriticalSection
0x180028767  mov     rbx, [rbp+220h]
0x18002876e  mov     rbx, [rbx]
0x180028771  mov     [rsp+88h+var_58], rbx
0x180028776  cmp     rbx, [rbp+220h]
0x18002877d  jz      loc_18002881D
0x180028783  mov     ecx, 18h; cb
0x180028788  call    cs:__imp_CoTaskMemAlloc
0x18002878e  mov     rdi, rax
0x180028791  test    rax, rax
0x180028794  jz      short loc_180028800
0x180028796  movaps  xmm0, xmmword ptr [r13+0]
0x18002879b  movdqu  xmmword ptr [rax], xmm0
0x18002879f  mov     [rax+10h], r12d
0x1800287a3  mov     [rax+14h], r15d
0x1800287a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800287ae  lea     rax, WPP_GLOBAL_Control
0x1800287b5  cmp     rcx, rax
0x1800287b8  jz      short loc_1800287DC
0x1800287ba  test    byte ptr [rcx+1Ch], 8
0x1800287be  jz      short loc_1800287DC
0x1800287c0  mov     r9d, [rbx+20h]
0x1800287c4  mov     edx, 79h ; 'y'
0x1800287c9  mov     rcx, [rcx+10h]
0x1800287cd  mov     [rsp+88h+var_60], r15d
0x1800287d2  mov     [rsp+88h+var_68], r12d
0x1800287d7  call    WPP_SF_LLL
0x1800287dc  mov     r8d, [rbx+20h]; unsigned __int64
0x1800287e0  mov     r9, rdi; unsigned __int64
0x1800287e3  mov     rcx, [rbx+28h]; this
0x1800287e7  mov     rdx, rbp; unsigned __int64
0x1800287ea  call    ?Dispatch@AsyncEventDispatcher@@QEAAJ_K00@Z; AsyncEventDispatcher::Dispatch(unsigned __int64,unsigned __int64,unsigned __int64)
0x1800287ef  mov     esi, eax
0x1800287f1  test    eax, eax
0x1800287f3  jz      short loc_180028805
0x1800287f5  mov     rcx, rdi; pv
0x1800287f8  call    cs:__imp_CoTaskMemFree
0x1800287fe  jmp     short loc_180028805
0x180028800  mov     esi, 8007000Eh
0x180028805  lea     rcx, [rsp+88h+var_58]
0x18002880a  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKUCLIENT_CALLBACK_INTERFACE@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,CLIENT_CALLBACK_INTERFACE>>>,std::_Iterator_base0>::operator++(void)
0x18002880f  test    esi, esi
0x180028811  jnz     short loc_18002881D
0x180028813  mov     rbx, [rsp+88h+var_58]
0x180028818  jmp     loc_180028776
0x18002881d  mov     rcx, r14; lpCriticalSection
0x180028820  call    cs:__imp_LeaveCriticalSection
0x180028826  mov     eax, esi
0x180028828  add     rsp, 48h
0x18002882c  pop     r15
0x18002882e  pop     r14
0x180028830  pop     r13
0x180028832  pop     r12
0x180028834  pop     rdi
0x180028835  pop     rsi
0x180028836  pop     rbp
0x180028837  pop     rbx
0x180028838  retn
```
