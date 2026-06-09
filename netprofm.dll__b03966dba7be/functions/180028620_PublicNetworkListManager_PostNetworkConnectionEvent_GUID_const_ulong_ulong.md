# PublicNetworkListManager::PostNetworkConnectionEvent(_GUID const &,ulong,ulong)

- ea: `0x180028620`
- end: `0x180028731`
- name: `?PostNetworkConnectionEvent@PublicNetworkListManager@@IEAAJAEBU_GUID@@KK@Z`
- size: `273`
- prototype: `__int64 __fastcall(PublicNetworkListManager *__hidden this, const struct _GUID *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18002e22c`
- `0x18002f150`

## callees

- `0x180006f60`
- `0x180008160`
- `0x180008530`
- `0x180028620`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028710`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028710`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002864b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002864b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800286e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800286e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028672`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028672`

## pseudocode

```c
__int64 __fastcall PublicNetworkListManager::PostNetworkConnectionEvent(
        PublicNetworkListManager *this,
        const struct _GUID *a2,
        __int64 a3,
        int a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // r14
  unsigned int v6; // esi
  __int64 v9; // rbx
  _OWORD *v10; // rax
  __int64 v11; // r8
  void *v12; // rdi
  __int128 v13; // xmm0
  __int64 i; // [rsp+30h] [rbp-38h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 392);
  v6 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 392));
  v9 = **((_QWORD **)this + 54);
  for ( i = v9; v9 != *((_QWORD *)this + 54); v9 = i )
  {
    v10 = CoTaskMemAlloc(0x18u);
    v12 = v10;
    if ( v10 )
    {
      v13 = (__int128)*a2;
      *((_DWORD *)v10 + 4) = 513;
      *((_DWORD *)v10 + 5) = a4;
      *v10 = v13;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_LLL(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, v11, *(unsigned int *)(v9 + 32), 513, a4);
      v6 = AsyncEventDispatcher::Dispatch(
             *(AsyncEventDispatcher **)(v9 + 40),
             (__int64)this,
             *(unsigned int *)(v9 + 32),
             (__int64)v12);
      if ( v6 )
        CoTaskMemFree(v12);
    }
    else
    {
      v6 = -2147024882;
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,CLIENT_CALLBACK_INTERFACE>>>,std::_Iterator_base0>::operator++(&i);
    if ( v6 )
      break;
  }
  LeaveCriticalSection(v4);
  return v6;
}

```

## disassembly

```asm
0x180028620  mov     [rsp+arg_8], rbx
0x180028625  mov     [rsp+arg_10], rbp
0x18002862a  push    rsi
0x18002862b  push    rdi
0x18002862c  push    r12
0x18002862e  push    r14
0x180028630  push    r15
0x180028632  sub     rsp, 40h
0x180028636  lea     r14, [rcx+188h]
0x18002863d  mov     rbp, rcx
0x180028640  mov     rcx, r14; lpCriticalSection
0x180028643  xor     esi, esi
0x180028645  mov     r15d, r9d
0x180028648  mov     r12, rdx
0x18002864b  call    cs:__imp_EnterCriticalSection
0x180028651  mov     rbx, [rbp+1B0h]
0x180028658  mov     rbx, [rbx]
0x18002865b  mov     [rsp+68h+var_38], rbx
0x180028660  cmp     rbx, [rbp+1B0h]
0x180028667  jz      loc_18002870D
0x18002866d  mov     ecx, 18h; cb
0x180028672  call    cs:__imp_CoTaskMemAlloc
0x180028678  mov     rdi, rax
0x18002867b  test    rax, rax
0x18002867e  jz      short loc_1800286F0
0x180028680  movups  xmm0, xmmword ptr [r12]
0x180028685  mov     dword ptr [rax+10h], 201h
0x18002868c  mov     [rax+14h], r15d
0x180028690  movdqu  xmmword ptr [rax], xmm0
0x180028694  mov     rcx, cs:WPP_GLOBAL_Control
0x18002869b  lea     rax, WPP_GLOBAL_Control
0x1800286a2  cmp     rcx, rax
0x1800286a5  jz      short loc_1800286CC
0x1800286a7  test    byte ptr [rcx+1Ch], 8
0x1800286ab  jz      short loc_1800286CC
0x1800286ad  mov     r9d, [rbx+20h]
0x1800286b1  mov     edx, 71h ; 'q'
0x1800286b6  mov     rcx, [rcx+10h]
0x1800286ba  mov     [rsp+68h+var_40], r15d
0x1800286bf  mov     [rsp+68h+var_48], 201h
0x1800286c7  call    WPP_SF_LLL
0x1800286cc  mov     r8d, [rbx+20h]; unsigned __int64
0x1800286d0  mov     r9, rdi; unsigned __int64
0x1800286d3  mov     rcx, [rbx+28h]; this
0x1800286d7  mov     rdx, rbp; unsigned __int64
0x1800286da  call    ?Dispatch@AsyncEventDispatcher@@QEAAJ_K00@Z; AsyncEventDispatcher::Dispatch(unsigned __int64,unsigned __int64,unsigned __int64)
0x1800286df  mov     esi, eax
0x1800286e1  test    eax, eax
0x1800286e3  jz      short loc_1800286F5
0x1800286e5  mov     rcx, rdi; pv
0x1800286e8  call    cs:__imp_CoTaskMemFree
0x1800286ee  jmp     short loc_1800286F5
0x1800286f0  mov     esi, 8007000Eh
0x1800286f5  lea     rcx, [rsp+68h+var_38]
0x1800286fa  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKUCLIENT_CALLBACK_INTERFACE@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,CLIENT_CALLBACK_INTERFACE>>>,std::_Iterator_base0>::operator++(void)
0x1800286ff  test    esi, esi
0x180028701  jnz     short loc_18002870D
0x180028703  mov     rbx, [rsp+68h+var_38]
0x180028708  jmp     loc_180028660
0x18002870d  mov     rcx, r14; lpCriticalSection
0x180028710  call    cs:__imp_LeaveCriticalSection
0x180028716  lea     r11, [rsp+68h+var_28]
0x18002871b  mov     eax, esi
0x18002871d  mov     rbx, [r11+38h]
0x180028721  mov     rbp, [r11+40h]
0x180028725  mov     rsp, r11
0x180028728  pop     r15
0x18002872a  pop     r14
0x18002872c  pop     r12
0x18002872e  pop     rdi
0x18002872f  pop     rsi
0x180028730  retn
```
