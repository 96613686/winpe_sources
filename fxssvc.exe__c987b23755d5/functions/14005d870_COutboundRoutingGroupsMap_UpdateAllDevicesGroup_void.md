# COutboundRoutingGroupsMap::UpdateAllDevicesGroup(void)

- ea: `0x14005d870`
- end: `0x14005dca5`
- name: `?UpdateAllDevicesGroup@COutboundRoutingGroupsMap@@QEAAHXZ`
- size: `1077`
- prototype: `__int64 __fastcall(COutboundRoutingGroupsMap *__hidden this)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, installer_update`

## callers

- `0x1400472a0`
- `0x1400492fc`

## callees

- `0x140001b8c`
- `0x140004b30`
- `0x140004b58`
- `0x140004df0`
- `0x14000e888`
- `0x14005bfbc`
- `0x14005c120`
- `0x14005c2a8`
- `0x14005c704`
- `0x14005cf08`
- `0x14005d01c`
- `0x14005d870`
- `0x140065dbc`
- `0x14007de30`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14005dc70`
- `ADVAPI32!RegCloseKey` at `0x14005dc70`
- `KERNEL32!GetLastError` at `0x14005d8f1`
- `KERNEL32!GetLastError` at `0x14005d9da`
- `KERNEL32!GetLastError` at `0x14005db6c`
- `KERNEL32!GetLastError` at `0x14005d8f1`
- `KERNEL32!GetLastError` at `0x14005d9da`
- `KERNEL32!GetLastError` at `0x14005db6c`
- `KERNEL32!SetLastError` at `0x14005d98c`
- `KERNEL32!SetLastError` at `0x14005daa5`
- `KERNEL32!SetLastError` at `0x14005dc89`
- `KERNEL32!SetLastError` at `0x14005d98c`
- `KERNEL32!SetLastError` at `0x14005daa5`
- `KERNEL32!SetLastError` at `0x14005dc89`
- `KERNEL32!EnterCriticalSection` at `0x14005daba`
- `KERNEL32!EnterCriticalSection` at `0x14005daba`
- `KERNEL32!LeaveCriticalSection` at `0x14005dc7d`
- `KERNEL32!LeaveCriticalSection` at `0x14005dc7d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BOOL8 __fastcall COutboundRoutingGroupsMap::UpdateAllDevicesGroup(COutboundRoutingGroupsMap *this)
{
  COutboundRoutingGroupsMap *v1; // rdi
  COutboundRoutingGroup *Group; // rsi
  DWORD LastError; // eax
  __int64 v4; // rcx
  unsigned int v6; // eax
  DWORD v7; // ebx
  _QWORD *v8; // rdi
  _QWORD *v9; // rcx
  _QWORD *v10; // rbx
  DWORD v11; // eax
  _QWORD *v12; // rcx
  _QWORD *v13; // rbx
  _QWORD *v14; // rdi
  _QWORD *v15; // rcx
  _QWORD *v16; // rbx
  unsigned int v17; // eax
  DWORD v18; // ebx
  HKEY v19; // r14
  __int64 v20; // rdi
  _DWORD *v21; // r12
  unsigned int v22; // r15d
  unsigned int v23; // edx
  DWORD_PTR v24; // rax
  unsigned int v25; // ebx
  DWORD_PTR v26; // rax
  DWORD_PTR *v27; // rdi
  HKEY v28; // rax
  CMapDeviceId *v29; // rcx
  __int64 v30; // rdx
  void *Block[2]; // [rsp+30h] [rbp-10h] BYREF
  COutboundRoutingGroupsMap *v32; // [rsp+80h] [rbp+40h] BYREF
  LPVOID lpMem; // [rsp+88h] [rbp+48h] BYREF

  v32 = this;
  v1 = g_pGroupsMap;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_b9c408ceb555301912c179a0f26e2108_Traceguids);
  }
  lpMem = 0;
  LODWORD(v32) = 0;
  Group = COutboundRoutingGroupsMap::FindGroup(v1, L"<All devices>");
  if ( !Group )
  {
    LastError = GetLastError();
    if ( LastError != 7002 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_b9c408ceb555301912c179a0f26e2108_Traceguids, LastError);
      }
      return 0;
    }
    Block[1] = 0;
    Block[0] = (void *)std::_List_alloc<0,std::_List_base_types<unsigned long>>::_Buynode0(v4, 0, 0);
    v6 = COutboundRoutingGroupsMap::AddGroup(v1, L"<All devices>", (struct COutboundRoutingGroup *)Block);
    v7 = v6;
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_b9c408ceb555301912c179a0f26e2108_Traceguids, v6);
      }
      SetLastError(v7);
      v8 = Block[0];
      v9 = *(_QWORD **)Block[0];
      *(_QWORD *)Block[0] = Block[0];
      v8[1] = v8;
      if ( v9 != v8 )
      {
        do
        {
          v10 = (_QWORD *)*v9;
          operator delete(v9);
          v9 = v10;
        }
        while ( v10 != v8 );
      }
LABEL_19:
      operator delete(v8);
      return 0;
    }
    Group = COutboundRoutingGroupsMap::FindGroup(v1, L"<All devices>");
    if ( !Group )
    {
      v11 = GetLastError();
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_b9c408ceb555301912c179a0f26e2108_Traceguids, v11);
      }
      v8 = Block[0];
      v12 = *(_QWORD **)Block[0];
      *(_QWORD *)Block[0] = Block[0];
      v8[1] = v8;
      if ( v12 != v8 )
      {
        do
        {
          v13 = (_QWORD *)*v12;
          operator delete(v12);
          v12 = v13;
        }
        while ( v13 != v8 );
      }
      goto LABEL_19;
    }
    v14 = Block[0];
    v15 = *(_QWORD **)Block[0];
    *(_QWORD *)Block[0] = Block[0];
    v14[1] = v14;
    if ( v15 != v14 )
    {
      do
      {
        v16 = (_QWORD *)*v15;
        operator delete(v15);
        v15 = v16;
      }
      while ( v16 != v14 );
    }
    operator delete(v14);
  }
  v17 = COutboundRoutingGroup::SerializeDevices(Group, (unsigned int **)&lpMem, (unsigned int *)&v32, 1);
  v18 = v17;
  if ( v17 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_b9c408ceb555301912c179a0f26e2108_Traceguids, v17);
    }
    SetLastError(v18);
    return 0;
  }
  v19 = 0;
  EnterCriticalSection(&g_CsLine);
  v20 = 0;
  v21 = lpMem;
  v22 = (unsigned int)v32;
  if ( (_DWORD)v32 )
  {
    while ( 1 )
    {
      v23 = v21[v20];
      v24 = g_TapiLinesListHead;
      if ( g_TapiLinesListHead )
      {
        while ( (DWORD_PTR *)v24 != &g_TapiLinesListHead )
        {
          if ( *(_DWORD *)(v24 + 24) == v23 )
          {
            if ( v24 )
              goto LABEL_46;
            break;
          }
          v24 = *(_QWORD *)v24;
        }
      }
      v25 = COutboundRoutingGroup::DelDevice(Group, v23);
      if ( v25 )
        break;
LABEL_46:
      v20 = (unsigned int)(v20 + 1);
      if ( (unsigned int)v20 >= v22 )
        goto LABEL_47;
    }
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_69;
    }
    v30 = 71;
    goto LABEL_59;
  }
LABEL_47:
  v26 = g_TapiLinesListHead;
  if ( (DWORD_PTR *)g_TapiLinesListHead != &g_TapiLinesListHead )
  {
    while ( 1 )
    {
      v27 = *(DWORD_PTR **)v26;
      v25 = COutboundRoutingGroup::AddDevice(Group, *(_DWORD *)(v26 + 24));
      if ( v25 )
        break;
      v26 = (DWORD_PTR)v27;
      if ( v27 == &g_TapiLinesListHead )
        goto LABEL_50;
    }
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_69;
    }
    v30 = 72;
    goto LABEL_59;
  }
LABEL_50:
  v28 = (HKEY)OpenOutboundGroupKey(L"<All devices>", 1);
  v19 = v28;
  if ( v28 )
  {
    v25 = COutboundRoutingGroup::Save(Group, v28);
    if ( v25
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        74,
        (unsigned int)WPP_b9c408ceb555301912c179a0f26e2108_Traceguids,
        (unsigned int)L"<All devices>",
        v25);
    }
    goto LABEL_69;
  }
  v25 = GetLastError();
  v29 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v30 = 73;
LABEL_59:
    WPP_SF_d(*((_QWORD *)v29 + 2), v30, WPP_b9c408ceb555301912c179a0f26e2108_Traceguids, v25);
  }
LABEL_69:
  pMemFree(v21);
  if ( v19 )
    RegCloseKey(v19);
  LeaveCriticalSection(&g_CsLine);
  if ( v25 )
    SetLastError(v25);
  return v25 == 0;
}

```

## disassembly

```asm
0x14005d870  mov     [rsp-38h+arg_0], rcx
0x14005d875  push    rbp
0x14005d876  push    rbx
0x14005d877  push    rsi
0x14005d878  push    rdi
0x14005d879  push    r12
0x14005d87b  push    r14
0x14005d87d  push    r15
0x14005d87f  mov     rbp, rsp
0x14005d882  sub     rsp, 40h
0x14005d886  mov     rdi, cs:?g_pGroupsMap@@3PEAVCOutboundRoutingGroupsMap@@EA; COutboundRoutingGroupsMap * g_pGroupsMap
0x14005d88d  lea     r15, WPP_GLOBAL_Control
0x14005d894  lea     r12, WPP_b9c408ceb555301912c179a0f26e2108_Traceguids
0x14005d89b  mov     r14b, 4
0x14005d89e  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d8a5  cmp     rcx, r15
0x14005d8a8  jz      short loc_14005D8C7
0x14005d8aa  test    [rcx+1Ch], r14b
0x14005d8ae  jz      short loc_14005D8C7
0x14005d8b0  cmp     byte ptr [rcx+19h], 5
0x14005d8b4  jb      short loc_14005D8C7
0x14005d8b6  mov     edx, 42h ; 'B'
0x14005d8bb  mov     r8, r12
0x14005d8be  mov     rcx, [rcx+10h]
0x14005d8c2  call    WPP_SF_
0x14005d8c7  mov     [rbp+lpMem], 0
0x14005d8cf  mov     dword ptr [rbp+arg_0], 0
0x14005d8d6  lea     rdx, aAllDevices; "<All devices>"
0x14005d8dd  mov     rcx, rdi; this
0x14005d8e0  call    ?FindGroup@COutboundRoutingGroupsMap@@QEAAPEAVCOutboundRoutingGroup@@PEBG@Z; COutboundRoutingGroupsMap::FindGroup(ushort const *)
0x14005d8e5  mov     rsi, rax
0x14005d8e8  test    rax, rax
0x14005d8eb  jnz     loc_14005DA5B
0x14005d8f1  call    cs:__imp_GetLastError
0x14005d8f7  cmp     eax, 1B5Ah
0x14005d8fc  jz      short loc_14005D92F
0x14005d8fe  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d905  cmp     rcx, r15
0x14005d908  jz      short loc_14005D928
0x14005d90a  test    [rcx+1Ch], r14b
0x14005d90e  jz      short loc_14005D928
0x14005d910  cmp     byte ptr [rcx+19h], 2
0x14005d914  jb      short loc_14005D928
0x14005d916  lea     edx, [rsi+43h]
0x14005d919  mov     r9d, eax
0x14005d91c  mov     r8, r12
0x14005d91f  mov     rcx, [rcx+10h]
0x14005d923  call    WPP_SF_d
0x14005d928  xor     eax, eax
0x14005d92a  jmp     loc_14005DC96
0x14005d92f  mov     [rbp+var_8], 0
0x14005d937  xor     r8d, r8d
0x14005d93a  xor     edx, edx
0x14005d93c  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@KV?$allocator@K@std@@@std@@@std@@QEAAPEAU?$_List_node@KPEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<ulong>>::_Buynode0(std::_List_node<ulong,void *> *,std::_List_node<ulong,void *> *)
0x14005d941  mov     [rbp+Block], rax
0x14005d945  lea     r8, [rbp+Block]; struct COutboundRoutingGroup *
0x14005d949  lea     rdx, aAllDevices; "<All devices>"
0x14005d950  mov     rcx, rdi; this
0x14005d953  call    ?AddGroup@COutboundRoutingGroupsMap@@QEAAKPEBGPEAVCOutboundRoutingGroup@@@Z; COutboundRoutingGroupsMap::AddGroup(ushort const *,COutboundRoutingGroup *)
0x14005d958  mov     ebx, eax
0x14005d95a  test    eax, eax
0x14005d95c  jz      short loc_14005D9C3
0x14005d95e  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d965  cmp     rcx, r15
0x14005d968  jz      short loc_14005D98A
0x14005d96a  test    [rcx+1Ch], r14b
0x14005d96e  jz      short loc_14005D98A
0x14005d970  cmp     byte ptr [rcx+19h], 2
0x14005d974  jb      short loc_14005D98A
0x14005d976  mov     edx, 44h ; 'D'
0x14005d97b  mov     r9d, eax
0x14005d97e  mov     r8, r12
0x14005d981  mov     rcx, [rcx+10h]
0x14005d985  call    WPP_SF_d
0x14005d98a  mov     ecx, ebx; dwErrCode
0x14005d98c  call    cs:__imp_SetLastError
0x14005d992  nop
0x14005d993  mov     rdi, [rbp+Block]
0x14005d997  mov     rcx, [rdi]; Block
0x14005d99a  mov     [rdi], rdi
0x14005d99d  mov     [rdi+8], rdi
0x14005d9a1  cmp     rcx, rdi
0x14005d9a4  jz      short loc_14005D9B6
0x14005d9a6  mov     rbx, [rcx]
0x14005d9a9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14005d9ae  mov     rcx, rbx
0x14005d9b1  cmp     rbx, rdi
0x14005d9b4  jnz     short loc_14005D9A6
0x14005d9b6  mov     rcx, rdi; Block
0x14005d9b9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14005d9be  jmp     loc_14005D928
0x14005d9c3  lea     rdx, aAllDevices; "<All devices>"
0x14005d9ca  mov     rcx, rdi; this
0x14005d9cd  call    ?FindGroup@COutboundRoutingGroupsMap@@QEAAPEAVCOutboundRoutingGroup@@PEBG@Z; COutboundRoutingGroupsMap::FindGroup(ushort const *)
0x14005d9d2  mov     rsi, rax
0x14005d9d5  test    rax, rax
0x14005d9d8  jnz     short loc_14005DA30
0x14005d9da  call    cs:__imp_GetLastError
0x14005d9e0  mov     rcx, cs:WPP_GLOBAL_Control
0x14005d9e7  cmp     rcx, r15
0x14005d9ea  jz      short loc_14005DA0B
0x14005d9ec  test    [rcx+1Ch], r14b
0x14005d9f0  jz      short loc_14005DA0B
0x14005d9f2  cmp     byte ptr [rcx+19h], 2
0x14005d9f6  jb      short loc_14005DA0B
0x14005d9f8  lea     edx, [rsi+45h]
0x14005d9fb  mov     r9d, eax
0x14005d9fe  mov     r8, r12
0x14005da01  mov     rcx, [rcx+10h]
0x14005da05  call    WPP_SF_d
0x14005da0a  nop
0x14005da0b  mov     rdi, [rbp+Block]
0x14005da0f  mov     rcx, [rdi]; Block
0x14005da12  mov     [rdi], rdi
0x14005da15  mov     [rdi+8], rdi
0x14005da19  cmp     rcx, rdi
0x14005da1c  jz      short loc_14005D9B6
0x14005da1e  mov     rbx, [rcx]
0x14005da21  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14005da26  mov     rcx, rbx
0x14005da29  cmp     rbx, rdi
0x14005da2c  jnz     short loc_14005DA1E
0x14005da2e  jmp     short loc_14005D9B6
0x14005da30  mov     rdi, [rbp+Block]
0x14005da34  mov     rcx, [rdi]; Block
0x14005da37  mov     [rdi], rdi
0x14005da3a  mov     [rdi+8], rdi
0x14005da3e  cmp     rcx, rdi
0x14005da41  jz      short loc_14005DA53
0x14005da43  mov     rbx, [rcx]
0x14005da46  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14005da4b  mov     rcx, rbx
0x14005da4e  cmp     rbx, rdi
0x14005da51  jnz     short loc_14005DA43
0x14005da53  mov     rcx, rdi; Block
0x14005da56  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14005da5b  mov     r9d, 1; int
0x14005da61  lea     r8, [rbp+arg_0]; unsigned int *
0x14005da65  lea     rdx, [rbp+lpMem]; unsigned int **
0x14005da69  mov     rcx, rsi; this
0x14005da6c  call    ?SerializeDevices@COutboundRoutingGroup@@QEBAKPEAPEAKPEAKH@Z; COutboundRoutingGroup::SerializeDevices(ulong * *,ulong *,int)
0x14005da71  mov     ebx, eax
0x14005da73  test    eax, eax
0x14005da75  jz      short loc_14005DAB0
0x14005da77  mov     rcx, cs:WPP_GLOBAL_Control
0x14005da7e  cmp     rcx, r15
0x14005da81  jz      short loc_14005DAA3
0x14005da83  test    [rcx+1Ch], r14b
0x14005da87  jz      short loc_14005DAA3
0x14005da89  cmp     byte ptr [rcx+19h], 2
0x14005da8d  jb      short loc_14005DAA3
0x14005da8f  mov     edx, 46h ; 'F'
0x14005da94  mov     r9d, eax
0x14005da97  mov     r8, r12
0x14005da9a  mov     rcx, [rcx+10h]
0x14005da9e  call    WPP_SF_d
0x14005daa3  mov     ecx, ebx; dwErrCode
0x14005daa5  call    cs:__imp_SetLastError
0x14005daab  jmp     loc_14005D928
0x14005dab0  xor     r14d, r14d
0x14005dab3  lea     rcx, ?g_CsLine@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14005daba  call    cs:__imp_EnterCriticalSection
0x14005dac0  xor     edi, edi
0x14005dac2  lea     rcx, ?g_TapiLinesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_TapiLinesListHead
0x14005dac9  mov     r12, [rbp+lpMem]
0x14005dacd  mov     r15d, dword ptr [rbp+arg_0]
0x14005dad1  test    r15d, r15d
0x14005dad4  jz      short loc_14005DB1C
0x14005dad6  mov     edx, [r12+rdi*4]; unsigned int
0x14005dada  mov     rax, cs:?g_TapiLinesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_TapiLinesListHead
0x14005dae1  test    rax, rax
0x14005dae4  jz      short loc_14005DAFC
0x14005dae6  jmp     short loc_14005DAF0
0x14005dae8  cmp     [rax+18h], edx
0x14005daeb  jz      short loc_14005DAF7
0x14005daed  mov     rax, [rax]
0x14005daf0  cmp     rax, rcx
0x14005daf3  jnz     short loc_14005DAE8
0x14005daf5  jmp     short loc_14005DAFC
0x14005daf7  test    rax, rax
0x14005dafa  jnz     short loc_14005DB15
0x14005dafc  mov     rcx, rsi; this
0x14005daff  call    ?DelDevice@COutboundRoutingGroup@@QEAAKK@Z; COutboundRoutingGroup::DelDevice(ulong)
0x14005db04  mov     ebx, eax
0x14005db06  test    eax, eax
0x14005db08  jnz     loc_14005DBA5
0x14005db0e  lea     rcx, ?g_TapiLinesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_TapiLinesListHead
0x14005db15  inc     edi
0x14005db17  cmp     edi, r15d
0x14005db1a  jb      short loc_14005DAD6
0x14005db1c  mov     rax, cs:?g_TapiLinesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_TapiLinesListHead
0x14005db23  cmp     rax, rcx
0x14005db26  jz      short loc_14005DB4F
0x14005db28  lea     r15, ?g_TapiLinesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_TapiLinesListHead
0x14005db2f  mov     rdi, [rax]
0x14005db32  mov     edx, [rax+18h]; unsigned int
0x14005db35  mov     rcx, rsi; this
0x14005db38  call    ?AddDevice@COutboundRoutingGroup@@QEAAKK@Z; COutboundRoutingGroup::AddDevice(ulong)
0x14005db3d  mov     ebx, eax
0x14005db3f  test    eax, eax
0x14005db41  jnz     loc_14005DBEA
0x14005db47  mov     rax, rdi
0x14005db4a  cmp     rdi, r15
0x14005db4d  jnz     short loc_14005DB2F
0x14005db4f  mov     edx, 1
0x14005db54  lea     rcx, aAllDevices; "<All devices>"
0x14005db5b  call    OpenOutboundGroupKey
0x14005db60  mov     r14, rax
0x14005db63  test    rax, rax
0x14005db66  jnz     loc_14005DC10
0x14005db6c  call    cs:__imp_GetLastError
0x14005db72  mov     ebx, eax
0x14005db74  mov     rcx, cs:WPP_GLOBAL_Control
0x14005db7b  lea     rax, WPP_GLOBAL_Control
0x14005db82  cmp     rcx, rax
0x14005db85  jz      loc_14005DC60
0x14005db8b  test    byte ptr [rcx+1Ch], 4
0x14005db8f  jz      loc_14005DC60
0x14005db95  cmp     byte ptr [rcx+19h], 2
0x14005db99  jb      loc_14005DC60
0x14005db9f  lea     edx, [r14+49h]
0x14005dba3  jmp     short loc_14005DBD5
0x14005dba5  mov     rcx, cs:WPP_GLOBAL_Control
0x14005dbac  lea     rax, WPP_GLOBAL_Control
0x14005dbb3  cmp     rcx, rax
0x14005dbb6  jz      loc_14005DC60
0x14005dbbc  test    byte ptr [rcx+1Ch], 4
0x14005dbc0  jz      loc_14005DC60
0x14005dbc6  cmp     byte ptr [rcx+19h], 2
0x14005dbca  jb      loc_14005DC60
0x14005dbd0  mov     edx, 47h ; 'G'
0x14005dbd5  mov     r9d, ebx
0x14005dbd8  lea     r8, WPP_b9c408ceb555301912c179a0f26e2108_Traceguids
0x14005dbdf  mov     rcx, [rcx+10h]
0x14005dbe3  call    WPP_SF_d
0x14005dbe8  jmp     short loc_14005DC60
0x14005dbea  mov     rcx, cs:WPP_GLOBAL_Control
0x14005dbf1  lea     rax, WPP_GLOBAL_Control
0x14005dbf8  cmp     rcx, rax
0x14005dbfb  jz      short loc_14005DC60
0x14005dbfd  test    byte ptr [rcx+1Ch], 4
0x14005dc01  jz      short loc_14005DC60
0x14005dc03  cmp     byte ptr [rcx+19h], 2
0x14005dc07  jb      short loc_14005DC60
0x14005dc09  mov     edx, 48h ; 'H'
0x14005dc0e  jmp     short loc_14005DBD5
0x14005dc10  mov     rdx, rax; HKEY
0x14005dc13  mov     rcx, rsi; this
0x14005dc16  call    ?Save@COutboundRoutingGroup@@QEBAKPEAUHKEY__@@@Z; COutboundRoutingGroup::Save(HKEY__ *)
0x14005dc1b  mov     ebx, eax
0x14005dc1d  test    eax, eax
0x14005dc1f  jz      short loc_14005DC60
0x14005dc21  mov     rcx, cs:WPP_GLOBAL_Control
0x14005dc28  lea     rax, WPP_GLOBAL_Control
0x14005dc2f  cmp     rcx, rax
0x14005dc32  jz      short loc_14005DC60
0x14005dc34  test    byte ptr [rcx+1Ch], 4
0x14005dc38  jz      short loc_14005DC60
0x14005dc3a  cmp     byte ptr [rcx+19h], 2
0x14005dc3e  jb      short loc_14005DC60
0x14005dc40  mov     edx, 4Ah ; 'J'
0x14005dc45  mov     [rsp+40h+var_20], ebx
0x14005dc49  lea     r9, aAllDevices; "<All devices>"
0x14005dc50  lea     r8, WPP_b9c408ceb555301912c179a0f26e2108_Traceguids
0x14005dc57  mov     rcx, [rcx+10h]
0x14005dc5b  call    WPP_SF_Sd
0x14005dc60  mov     rcx, r12; lpMem
0x14005dc63  call    pMemFree
0x14005dc68  test    r14, r14
0x14005dc6b  jz      short loc_14005DC76
0x14005dc6d  mov     rcx, r14; hKey
0x14005dc70  call    cs:__imp_RegCloseKey
0x14005dc76  lea     rcx, ?g_CsLine@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14005dc7d  call    cs:__imp_LeaveCriticalSection
0x14005dc83  test    ebx, ebx
0x14005dc85  jz      short loc_14005DC8F
0x14005dc87  mov     ecx, ebx; dwErrCode
0x14005dc89  call    cs:__imp_SetLastError
0x14005dc8f  xor     eax, eax
0x14005dc91  test    ebx, ebx
0x14005dc93  setz    al
0x14005dc96  add     rsp, 40h
0x14005dc9a  pop     r15
0x14005dc9c  pop     r14
0x14005dc9e  pop     r12
0x14005dca0  pop     rdi
0x14005dca1  pop     rsi
0x14005dca2  pop     rbx
0x14005dca3  pop     rbp
0x14005dca4  retn
```
