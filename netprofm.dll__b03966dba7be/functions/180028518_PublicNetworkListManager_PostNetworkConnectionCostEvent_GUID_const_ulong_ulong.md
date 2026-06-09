# PublicNetworkListManager::PostNetworkConnectionCostEvent(_GUID const &,ulong,ulong)

- ea: `0x180028518`
- end: `0x180028619`
- name: `?PostNetworkConnectionCostEvent@PublicNetworkListManager@@IEAAJAEBU_GUID@@KK@Z`
- size: `257`
- prototype: `__int64 __fastcall(PublicNetworkListManager *__hidden this, const struct _GUID *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18002e3b0`
- `0x18002ea30`

## callees

- `0x180006f60`
- `0x180008160`
- `0x180008530`
- `0x180028518`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028600`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028600`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028541`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028541`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800285d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800285d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028568`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028568`

## pseudocode

```c
__int64 __fastcall PublicNetworkListManager::PostNetworkConnectionCostEvent(
        PublicNetworkListManager *this,
        const struct _GUID *a2,
        int a3,
        int a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // r14
  unsigned int v6; // esi
  __int64 v10; // rbx
  _OWORD *v11; // rax
  __int64 v12; // r8
  void *v13; // rdi
  __int128 v14; // xmm0
  _QWORD v16[11]; // [rsp+30h] [rbp-58h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 448);
  v6 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 448));
  v10 = **((_QWORD **)this + 61);
  for ( v16[0] = v10; v10 != *((_QWORD *)this + 61); v10 = v16[0] )
  {
    v11 = CoTaskMemAlloc(0x18u);
    v13 = v11;
    if ( v11 )
    {
      v14 = (__int128)*a2;
      *((_DWORD *)v11 + 4) = a3;
      *((_DWORD *)v11 + 5) = a4;
      *v11 = v14;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_LLL(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, v12, *(unsigned int *)(v10 + 32), a3, a4);
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
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,CLIENT_CALLBACK_INTERFACE>>>,std::_Iterator_base0>::operator++(v16);
    if ( v6 )
      break;
  }
  LeaveCriticalSection(v4);
  return v6;
}

```

## disassembly

```asm
0x180028518  push    rbx
0x18002851a  push    rbp
0x18002851b  push    rsi
0x18002851c  push    rdi
0x18002851d  push    r12
0x18002851f  push    r13
0x180028521  push    r14
0x180028523  push    r15
0x180028525  sub     rsp, 48h
0x180028529  lea     r14, [rcx+1C0h]
0x180028530  mov     rbp, rcx
0x180028533  mov     rcx, r14; lpCriticalSection
0x180028536  xor     esi, esi
0x180028538  mov     r15d, r9d
0x18002853b  mov     r12d, r8d
0x18002853e  mov     r13, rdx
0x180028541  call    cs:__imp_EnterCriticalSection
0x180028547  mov     rbx, [rbp+1E8h]
0x18002854e  mov     rbx, [rbx]
0x180028551  mov     [rsp+88h+var_58], rbx
0x180028556  cmp     rbx, [rbp+1E8h]
0x18002855d  jz      loc_1800285FD
0x180028563  mov     ecx, 18h; cb
0x180028568  call    cs:__imp_CoTaskMemAlloc
0x18002856e  mov     rdi, rax
0x180028571  test    rax, rax
0x180028574  jz      short loc_1800285E0
0x180028576  movups  xmm0, xmmword ptr [r13+0]
0x18002857b  mov     [rax+10h], r12d
0x18002857f  mov     [rax+14h], r15d
0x180028583  movdqu  xmmword ptr [rax], xmm0
0x180028587  mov     rcx, cs:WPP_GLOBAL_Control
0x18002858e  lea     rax, WPP_GLOBAL_Control
0x180028595  cmp     rcx, rax
0x180028598  jz      short loc_1800285BC
0x18002859a  test    byte ptr [rcx+1Ch], 8
0x18002859e  jz      short loc_1800285BC
0x1800285a0  mov     r9d, [rbx+20h]
0x1800285a4  mov     edx, 76h ; 'v'
0x1800285a9  mov     rcx, [rcx+10h]
0x1800285ad  mov     [rsp+88h+var_60], r15d
0x1800285b2  mov     [rsp+88h+var_68], r12d
0x1800285b7  call    WPP_SF_LLL
0x1800285bc  mov     r8d, [rbx+20h]; unsigned __int64
0x1800285c0  mov     r9, rdi; unsigned __int64
0x1800285c3  mov     rcx, [rbx+28h]; this
0x1800285c7  mov     rdx, rbp; unsigned __int64
0x1800285ca  call    ?Dispatch@AsyncEventDispatcher@@QEAAJ_K00@Z; AsyncEventDispatcher::Dispatch(unsigned __int64,unsigned __int64,unsigned __int64)
0x1800285cf  mov     esi, eax
0x1800285d1  test    eax, eax
0x1800285d3  jz      short loc_1800285E5
0x1800285d5  mov     rcx, rdi; pv
0x1800285d8  call    cs:__imp_CoTaskMemFree
0x1800285de  jmp     short loc_1800285E5
0x1800285e0  mov     esi, 8007000Eh
0x1800285e5  lea     rcx, [rsp+88h+var_58]
0x1800285ea  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKUCLIENT_CALLBACK_INTERFACE@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,CLIENT_CALLBACK_INTERFACE>>>,std::_Iterator_base0>::operator++(void)
0x1800285ef  test    esi, esi
0x1800285f1  jnz     short loc_1800285FD
0x1800285f3  mov     rbx, [rsp+88h+var_58]
0x1800285f8  jmp     loc_180028556
0x1800285fd  mov     rcx, r14; lpCriticalSection
0x180028600  call    cs:__imp_LeaveCriticalSection
0x180028606  mov     eax, esi
0x180028608  add     rsp, 48h
0x18002860c  pop     r15
0x18002860e  pop     r14
0x180028610  pop     r13
0x180028612  pop     r12
0x180028614  pop     rdi
0x180028615  pop     rsi
0x180028616  pop     rbp
0x180028617  pop     rbx
0x180028618  retn
```
