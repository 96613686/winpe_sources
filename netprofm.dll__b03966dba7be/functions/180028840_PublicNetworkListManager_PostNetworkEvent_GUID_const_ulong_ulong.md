# PublicNetworkListManager::PostNetworkEvent(_GUID const &,ulong,ulong)

- ea: `0x180028840`
- end: `0x180028941`
- name: `?PostNetworkEvent@PublicNetworkListManager@@IEAAJAEBU_GUID@@KK@Z`
- size: `257`
- prototype: `__int64 __fastcall(PublicNetworkListManager *__hidden this, const struct _GUID *, unsigned int, unsigned int)`
- caller_count: `6`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18002e570`
- `0x18002ea30`
- `0x18002ecd0`
- `0x18002ee80`
- `0x18002ef90`
- `0x18002f270`

## callees

- `0x180006f60`
- `0x180008160`
- `0x180008530`
- `0x180028840`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028928`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028928`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028869`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028869`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028900`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028900`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028890`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028890`

## pseudocode

```c
__int64 __fastcall PublicNetworkListManager::PostNetworkEvent(
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

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 336);
  v6 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 336));
  v10 = **((_QWORD **)this + 47);
  for ( v16[0] = v10; v10 != *((_QWORD *)this + 47); v10 = v16[0] )
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
        WPP_SF_LLL(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, v12, *(unsigned int *)(v10 + 32), a3, a4);
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
0x180028840  push    rbx
0x180028842  push    rbp
0x180028843  push    rsi
0x180028844  push    rdi
0x180028845  push    r12
0x180028847  push    r13
0x180028849  push    r14
0x18002884b  push    r15
0x18002884d  sub     rsp, 48h
0x180028851  lea     r14, [rcx+150h]
0x180028858  mov     rbp, rcx
0x18002885b  mov     rcx, r14; lpCriticalSection
0x18002885e  xor     esi, esi
0x180028860  mov     r15d, r9d
0x180028863  mov     r12d, r8d
0x180028866  mov     r13, rdx
0x180028869  call    cs:__imp_EnterCriticalSection
0x18002886f  mov     rbx, [rbp+178h]
0x180028876  mov     rbx, [rbx]
0x180028879  mov     [rsp+88h+var_58], rbx
0x18002887e  cmp     rbx, [rbp+178h]
0x180028885  jz      loc_180028925
0x18002888b  mov     ecx, 18h; cb
0x180028890  call    cs:__imp_CoTaskMemAlloc
0x180028896  mov     rdi, rax
0x180028899  test    rax, rax
0x18002889c  jz      short loc_180028908
0x18002889e  movups  xmm0, xmmword ptr [r13+0]
0x1800288a3  mov     [rax+10h], r12d
0x1800288a7  mov     [rax+14h], r15d
0x1800288ab  movdqu  xmmword ptr [rax], xmm0
0x1800288af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800288b6  lea     rax, WPP_GLOBAL_Control
0x1800288bd  cmp     rcx, rax
0x1800288c0  jz      short loc_1800288E4
0x1800288c2  test    byte ptr [rcx+1Ch], 8
0x1800288c6  jz      short loc_1800288E4
0x1800288c8  mov     r9d, [rbx+20h]
0x1800288cc  mov     edx, 70h ; 'p'
0x1800288d1  mov     rcx, [rcx+10h]
0x1800288d5  mov     [rsp+88h+var_60], r15d
0x1800288da  mov     [rsp+88h+var_68], r12d
0x1800288df  call    WPP_SF_LLL
0x1800288e4  mov     r8d, [rbx+20h]; unsigned __int64
0x1800288e8  mov     r9, rdi; unsigned __int64
0x1800288eb  mov     rcx, [rbx+28h]; this
0x1800288ef  mov     rdx, rbp; unsigned __int64
0x1800288f2  call    ?Dispatch@AsyncEventDispatcher@@QEAAJ_K00@Z; AsyncEventDispatcher::Dispatch(unsigned __int64,unsigned __int64,unsigned __int64)
0x1800288f7  mov     esi, eax
0x1800288f9  test    eax, eax
0x1800288fb  jz      short loc_18002890D
0x1800288fd  mov     rcx, rdi; pv
0x180028900  call    cs:__imp_CoTaskMemFree
0x180028906  jmp     short loc_18002890D
0x180028908  mov     esi, 8007000Eh
0x18002890d  lea     rcx, [rsp+88h+var_58]
0x180028912  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKUCLIENT_CALLBACK_INTERFACE@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,CLIENT_CALLBACK_INTERFACE>>>,std::_Iterator_base0>::operator++(void)
0x180028917  test    esi, esi
0x180028919  jnz     short loc_180028925
0x18002891b  mov     rbx, [rsp+88h+var_58]
0x180028920  jmp     loc_18002887E
0x180028925  mov     rcx, r14; lpCriticalSection
0x180028928  call    cs:__imp_LeaveCriticalSection
0x18002892e  mov     eax, esi
0x180028930  add     rsp, 48h
0x180028934  pop     r15
0x180028936  pop     r14
0x180028938  pop     r13
0x18002893a  pop     r12
0x18002893c  pop     rdi
0x18002893d  pop     rsi
0x18002893e  pop     rbp
0x18002893f  pop     rbx
0x180028940  retn
```
