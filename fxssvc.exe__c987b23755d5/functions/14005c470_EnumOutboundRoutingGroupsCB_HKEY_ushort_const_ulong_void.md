# EnumOutboundRoutingGroupsCB(HKEY__ *,ushort const *,ulong,void *)

- ea: `0x14005c470`
- end: `0x14005c6fc`
- name: `?EnumOutboundRoutingGroupsCB@@YAHPEAUHKEY__@@PEBGKPEAX@Z`
- size: `652`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, unsigned int, void *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x140001b8c`
- `0x140004b30`
- `0x140004b58`
- `0x140004df0`
- `0x14000e888`
- `0x14005c120`
- `0x14005c470`
- `0x14005c8e8`
- `0x140065df8`
- `0x1400708c4`
- `0x140070f1c`

## import_xrefs

- `ADVAPI32!RegDeleteKeyW` at `0x14005c601`
- `ADVAPI32!RegDeleteKeyW` at `0x14005c601`
- `KERNEL32!GetLastError` at `0x14005c5c5`
- `KERNEL32!GetLastError` at `0x14005c5c5`
- `msvcrt!_wcsicmp` at `0x14005c511`
- `msvcrt!_wcsicmp` at `0x14005c511`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EnumOutboundRoutingGroupsCB(HKEY a1, const unsigned __int16 *a2, __int64 a3, _DWORD *a4)
{
  CMapDeviceId *v7; // rcx
  _QWORD **v8; // rax
  _QWORD **v9; // rdi
  _QWORD *v10; // rcx
  _QWORD *v11; // rbx
  __int64 v12; // rcx
  _QWORD *v13; // rcx
  _QWORD *v14; // rbx
  unsigned int v16; // eax
  unsigned int v17; // edi
  int v18; // ebp
  HKEY v19; // rax
  DWORD LastError; // eax
  LSTATUS v21; // eax
  __int64 v22; // r9
  unsigned int v23; // eax
  _QWORD *v24; // rdi
  _QWORD *v25; // rcx
  _QWORD *v26; // rbx
  void *Block[2]; // [rsp+30h] [rbp-38h] BYREF

  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_b9c408ceb555301912c179a0f26e2108_Traceguids);
  }
  Block[1] = 0;
  v8 = (_QWORD **)std::_List_alloc<0,std::_List_base_types<unsigned long>>::_Buynode0(v7, 0, 0);
  v9 = v8;
  Block[0] = v8;
  if ( !a2 )
  {
    v10 = *v8;
    *v8 = v8;
    v8[1] = v8;
    if ( v10 != v8 )
    {
      do
      {
        v11 = (_QWORD *)*v10;
        operator delete(v10);
        v10 = v11;
      }
      while ( v11 != v9 );
    }
LABEL_13:
    operator delete(v9);
    return 1;
  }
  if ( _wcsicmp(a2, L"<All devices>") && !(unsigned int)IsServerSku(v12) )
  {
    v13 = *v9;
    *v9 = v9;
    v9[1] = v9;
    if ( v13 != v9 )
    {
      do
      {
        v14 = (_QWORD *)*v13;
        operator delete(v13);
        v13 = v14;
      }
      while ( v14 != v9 );
    }
    goto LABEL_13;
  }
  v16 = COutboundRoutingGroup::Load((COutboundRoutingGroup *)Block, a1, a2);
  v17 = v16;
  if ( v16 )
  {
    v18 = 0;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        81,
        (unsigned int)WPP_b9c408ceb555301912c179a0f26e2108_Traceguids,
        (_DWORD)a2,
        v16);
    }
    v19 = OpenRegistryKey(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\Outbound Routing\\Groups", 0, 0x3001Fu);
    if ( v19 )
    {
      v21 = RegDeleteKeyW(v19, a2);
      if ( v21 )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            83,
            (unsigned int)WPP_b9c408ceb555301912c179a0f26e2108_Traceguids,
            (_DWORD)a2,
            v21);
        }
      }
      else
      {
        v18 = 1;
      }
    }
    else
    {
      LastError = GetLastError();
      v17 = LastError;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_b9c408ceb555301912c179a0f26e2108_Traceguids, LastError);
      }
    }
    if ( !v17 )
      goto LABEL_40;
    if ( v18 )
    {
      v22 = 3221257539LL;
LABEL_39:
      FaxLog(1, 1, 1, v22);
      goto LABEL_40;
    }
LABEL_38:
    v22 = 3221257542LL;
    goto LABEL_39;
  }
  v23 = COutboundRoutingGroupsMap::AddGroup(g_pGroupsMap, a2, (struct COutboundRoutingGroup *)Block);
  if ( v23 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        84,
        (unsigned int)WPP_b9c408ceb555301912c179a0f26e2108_Traceguids,
        (_DWORD)a2,
        v23);
    }
    goto LABEL_38;
  }
LABEL_40:
  *a4 = 0;
  v24 = Block[0];
  v25 = *(_QWORD **)Block[0];
  *(_QWORD *)Block[0] = Block[0];
  v24[1] = v24;
  if ( v25 != v24 )
  {
    do
    {
      v26 = (_QWORD *)*v25;
      operator delete(v25);
      v25 = v26;
    }
    while ( v26 != v24 );
  }
  operator delete(v24);
  return 1;
}

```

## disassembly

```asm
0x14005c470  mov     [rsp+arg_0], rbx
0x14005c475  mov     [rsp+arg_10], rbp
0x14005c47a  push    rsi
0x14005c47b  push    rdi
0x14005c47c  push    r12
0x14005c47e  push    r13
0x14005c480  push    r14
0x14005c482  sub     rsp, 40h
0x14005c486  mov     r14, r9
0x14005c489  mov     rbx, rdx
0x14005c48c  mov     rsi, rcx
0x14005c48f  lea     r12, WPP_GLOBAL_Control
0x14005c496  lea     r13, WPP_b9c408ceb555301912c179a0f26e2108_Traceguids
0x14005c49d  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c4a4  cmp     rcx, r12
0x14005c4a7  jz      short loc_14005C4C6
0x14005c4a9  test    byte ptr [rcx+1Ch], 4
0x14005c4ad  jz      short loc_14005C4C6
0x14005c4af  cmp     byte ptr [rcx+19h], 5
0x14005c4b3  jb      short loc_14005C4C6
0x14005c4b5  mov     edx, 50h ; 'P'
0x14005c4ba  mov     r8, r13
0x14005c4bd  mov     rcx, [rcx+10h]
0x14005c4c1  call    WPP_SF_
0x14005c4c6  mov     [rsp+68h+var_30], 0
0x14005c4cf  xor     r8d, r8d
0x14005c4d2  xor     edx, edx
0x14005c4d4  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@KV?$allocator@K@std@@@std@@@std@@QEAAPEAU?$_List_node@KPEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<ulong>>::_Buynode0(std::_List_node<ulong,void *> *,std::_List_node<ulong,void *> *)
0x14005c4d9  mov     rdi, rax
0x14005c4dc  mov     [rsp+68h+Block], rax
0x14005c4e1  test    rbx, rbx
0x14005c4e4  jnz     short loc_14005C507
0x14005c4e6  mov     rcx, [rax]; Block
0x14005c4e9  mov     [rax], rax
0x14005c4ec  mov     [rax+8], rax
0x14005c4f0  cmp     rcx, rax
0x14005c4f3  jz      short loc_14005C543
0x14005c4f5  mov     rbx, [rcx]
0x14005c4f8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14005c4fd  mov     rcx, rbx
0x14005c500  cmp     rbx, rdi
0x14005c503  jnz     short loc_14005C4F5
0x14005c505  jmp     short loc_14005C543
0x14005c507  lea     rdx, aAllDevices; "<All devices>"
0x14005c50e  mov     rcx, rbx; String1
0x14005c511  call    cs:__imp__wcsicmp
0x14005c517  test    eax, eax
0x14005c519  jz      short loc_14005C555
0x14005c51b  call    IsServerSku
0x14005c520  test    eax, eax
0x14005c522  jnz     short loc_14005C555
0x14005c524  mov     rcx, [rdi]; Block
0x14005c527  mov     [rdi], rdi
0x14005c52a  mov     [rdi+8], rdi
0x14005c52e  cmp     rcx, rdi
0x14005c531  jz      short loc_14005C543
0x14005c533  mov     rbx, [rcx]
0x14005c536  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14005c53b  mov     rcx, rbx
0x14005c53e  cmp     rbx, rdi
0x14005c541  jnz     short loc_14005C533
0x14005c543  mov     rcx, rdi; Block
0x14005c546  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14005c54b  mov     eax, 1
0x14005c550  jmp     loc_14005C6E3
0x14005c555  mov     r8, rbx; unsigned __int16 *
0x14005c558  mov     rdx, rsi; HKEY
0x14005c55b  lea     rcx, [rsp+68h+Block]; this
0x14005c560  call    ?Load@COutboundRoutingGroup@@QEAAKPEAUHKEY__@@PEBG@Z; COutboundRoutingGroup::Load(HKEY__ *,ushort const *)
0x14005c565  mov     edi, eax
0x14005c567  mov     esi, 1
0x14005c56c  test    eax, eax
0x14005c56e  jz      loc_14005C64F
0x14005c574  xor     ebp, ebp
0x14005c576  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c57d  cmp     rcx, r12
0x14005c580  jz      short loc_14005C5A4
0x14005c582  test    byte ptr [rcx+1Ch], 4
0x14005c586  jz      short loc_14005C5A4
0x14005c588  cmp     byte ptr [rcx+19h], 2
0x14005c58c  jb      short loc_14005C5A4
0x14005c58e  lea     edx, [rsi+50h]
0x14005c591  mov     dword ptr [rsp+68h+var_48], eax
0x14005c595  mov     r9, rbx
0x14005c598  mov     r8, r13
0x14005c59b  mov     rcx, [rcx+10h]
0x14005c59f  call    WPP_SF_Sd
0x14005c5a4  mov     r9d, 3001Fh
0x14005c5aa  xor     r8d, r8d
0x14005c5ad  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Fax\\Outbound Rout"...
0x14005c5b4  mov     rcx, 0FFFFFFFF80000002h
0x14005c5bb  call    OpenRegistryKey
0x14005c5c0  test    rax, rax
0x14005c5c3  jnz     short loc_14005C5FB
0x14005c5c5  call    cs:__imp_GetLastError
0x14005c5cb  mov     edi, eax
0x14005c5cd  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c5d4  cmp     rcx, r12
0x14005c5d7  jz      short loc_14005C63F
0x14005c5d9  test    byte ptr [rcx+1Ch], 4
0x14005c5dd  jz      short loc_14005C63F
0x14005c5df  cmp     byte ptr [rcx+19h], 2
0x14005c5e3  jb      short loc_14005C63F
0x14005c5e5  mov     edx, 52h ; 'R'
0x14005c5ea  mov     r9d, eax
0x14005c5ed  mov     r8, r13
0x14005c5f0  mov     rcx, [rcx+10h]
0x14005c5f4  call    WPP_SF_d
0x14005c5f9  jmp     short loc_14005C63F
0x14005c5fb  mov     rdx, rbx; lpSubKey
0x14005c5fe  mov     rcx, rax; hKey
0x14005c601  call    cs:__imp_RegDeleteKeyW
0x14005c607  test    eax, eax
0x14005c609  jz      short loc_14005C63D
0x14005c60b  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c612  cmp     rcx, r12
0x14005c615  jz      short loc_14005C63F
0x14005c617  test    byte ptr [rcx+1Ch], 4
0x14005c61b  jz      short loc_14005C63F
0x14005c61d  cmp     byte ptr [rcx+19h], 2
0x14005c621  jb      short loc_14005C63F
0x14005c623  mov     edx, 53h ; 'S'
0x14005c628  mov     dword ptr [rsp+68h+var_48], eax
0x14005c62c  mov     r9, rbx
0x14005c62f  mov     r8, r13
0x14005c632  mov     rcx, [rcx+10h]
0x14005c636  call    WPP_SF_Sd
0x14005c63b  jmp     short loc_14005C63F
0x14005c63d  mov     ebp, esi
0x14005c63f  test    edi, edi
0x14005c641  jz      short loc_14005C6AE
0x14005c643  test    ebp, ebp
0x14005c645  jz      short loc_14005C697
0x14005c647  mov     r9d, 0C0007D43h
0x14005c64d  jmp     short loc_14005C69D
0x14005c64f  lea     r8, [rsp+68h+Block]; struct COutboundRoutingGroup *
0x14005c654  mov     rdx, rbx; unsigned __int16 *
0x14005c657  mov     rcx, cs:?g_pGroupsMap@@3PEAVCOutboundRoutingGroupsMap@@EA; this
0x14005c65e  call    ?AddGroup@COutboundRoutingGroupsMap@@QEAAKPEBGPEAVCOutboundRoutingGroup@@@Z; COutboundRoutingGroupsMap::AddGroup(ushort const *,COutboundRoutingGroup *)
0x14005c663  test    eax, eax
0x14005c665  jz      short loc_14005C6AE
0x14005c667  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c66e  cmp     rcx, r12
0x14005c671  jz      short loc_14005C697
0x14005c673  test    byte ptr [rcx+1Ch], 4
0x14005c677  jz      short loc_14005C697
0x14005c679  cmp     byte ptr [rcx+19h], 2
0x14005c67d  jb      short loc_14005C697
0x14005c67f  mov     edx, 54h ; 'T'
0x14005c684  mov     dword ptr [rsp+68h+var_48], eax
0x14005c688  mov     r9, rbx
0x14005c68b  mov     r8, r13
0x14005c68e  mov     rcx, [rcx+10h]
0x14005c692  call    WPP_SF_Sd
0x14005c697  mov     r9d, 0C0007D46h
0x14005c69d  mov     [rsp+68h+var_48], rbx
0x14005c6a2  mov     r8d, esi
0x14005c6a5  mov     edx, esi
0x14005c6a7  mov     ecx, esi
0x14005c6a9  call    FaxLog
0x14005c6ae  mov     dword ptr [r14], 0
0x14005c6b5  mov     rdi, [rsp+68h+Block]
0x14005c6ba  mov     rcx, [rdi]; Block
0x14005c6bd  mov     [rdi], rdi
0x14005c6c0  mov     [rdi+8], rdi
0x14005c6c4  cmp     rcx, rdi
0x14005c6c7  jz      short loc_14005C6D9
0x14005c6c9  mov     rbx, [rcx]
0x14005c6cc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14005c6d1  mov     rcx, rbx
0x14005c6d4  cmp     rbx, rdi
0x14005c6d7  jnz     short loc_14005C6C9
0x14005c6d9  mov     rcx, rdi; Block
0x14005c6dc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14005c6e1  mov     eax, esi
0x14005c6e3  lea     r11, [rsp+68h+var_28]
0x14005c6e8  mov     rbx, [r11+30h]
0x14005c6ec  mov     rbp, [r11+40h]
0x14005c6f0  mov     rsp, r11
0x14005c6f3  pop     r14
0x14005c6f5  pop     r13
0x14005c6f7  pop     r12
0x14005c6f9  pop     rdi
0x14005c6fa  pop     rsi
0x14005c6fb  retn
```
