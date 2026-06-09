# ConnectionManager::RegChangeNotifyHandler(void *,uchar)

- ea: `0x18001ccd0`
- end: `0x18001d2e3`
- name: `?RegChangeNotifyHandler@ConnectionManager@@CAXPEAXE@Z`
- size: `1555`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001710`
- `0x1800043a8`
- `0x1800045f4`
- `0x1800052b4`
- `0x18000538c`
- `0x180019200`
- `0x180019c68`
- `0x180019c9c`
- `0x180019cc8`
- `0x180019f60`
- `0x18001ccd0`
- `0x18001d698`
- `0x18001db78`
- `0x18001fe84`
- `0x18002fe40`
- `0x180030434`
- `0x18003060c`
- `0x180032c3c`
- `0x180036010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18001cf6e`
- `ADVAPI32!RegCloseKey` at `0x18001cf6e`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x18001d268`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x18001d268`
- `KERNEL32!LeaveCriticalSection` at `0x18001d2b3`
- `KERNEL32!LeaveCriticalSection` at `0x18001d2b3`
- `KERNEL32!EnterCriticalSection` at `0x18001cd81`
- `KERNEL32!EnterCriticalSection` at `0x18001cd81`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001ce8d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001ce8d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d0ed`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d0ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ConnectionManager::RegChangeNotifyHandler(unsigned __int64 a1, unsigned __int8 a2)
{
  unsigned int v2; // ebx
  PVOID *v4; // rcx
  _QWORD *v5; // rax
  int v6; // ebx
  signed int ValueWithAlloc; // r13d
  OLECHAR *v8; // rdi
  char v9; // dl
  const OLECHAR *v10; // rbx
  PVOID *v11; // rcx
  __int64 v12; // rax
  LPCOLESTR *v13; // r10
  LPCOLESTR v14; // rbx
  const IID *v15; // r9
  const IID *i; // rax
  unsigned int v17; // eax
  _QWORD *v18; // rax
  const IID *v19; // rbx
  PVOID *v20; // rcx
  char *v21; // r11
  _QWORD *v22; // rax
  unsigned int Instance; // eax
  _QWORD *v24; // rax
  __int64 v25; // rcx
  LPCOLESTR v26; // rdi
  int Win32Error; // eax
  _QWORD **v28; // rcx
  _QWORD *v29; // rcx
  _QWORD *v30; // rbx
  char v31; // [rsp+30h] [rbp-98h]
  int v32; // [rsp+34h] [rbp-94h]
  char *v33; // [rsp+38h] [rbp-90h]
  unsigned int v34; // [rsp+40h] [rbp-88h] BYREF
  unsigned int v35[3]; // [rsp+44h] [rbp-84h] BYREF
  unsigned __int64 v36; // [rsp+50h] [rbp-78h]
  unsigned __int64 v37; // [rsp+58h] [rbp-70h] BYREF
  LPCOLESTR v38; // [rsp+60h] [rbp-68h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+68h] [rbp-60h]
  __int64 v40; // [rsp+70h] [rbp-58h]
  LPCOLESTR lpsz; // [rsp+78h] [rbp-50h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-48h] BYREF
  __int128 v43; // [rsp+88h] [rbp-40h] BYREF
  GUID pclsid; // [rsp+98h] [rbp-30h] BYREF

  v2 = a2;
  v36 = a1;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
      WPP_SF_d(v4[2], 68, &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids, v2);
  }
  v37 = a1;
  v40 = (a1 + 72) & ((unsigned __int128)-(__int128)a1 >> 64);
  lpCriticalSection = (LPCRITICAL_SECTION)(v40 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(v40 + 8));
  v43 = 0;
  v5 = MemAlloc(0x20u);
  *v5 = v5;
  v5[1] = v5;
  *(_QWORD *)&v43 = v5;
  v6 = 0;
  v32 = 0;
  hKey = 0;
  ValueWithAlloc = HrRegOpenKeyEx(
                     HKEY_LOCAL_MACHINE,
                     L"System\\CurrentControlSet\\Control\\Network\\Connections",
                     0x20019u,
                     &hKey);
  if ( ValueWithAlloc < 0 )
  {
    Win32Error = HrFromLastWin32Error();
    if ( Win32Error < 0 )
    {
      v20 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_73;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_70;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        76,
        &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids,
        (unsigned int)Win32Error);
    }
    v20 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_70;
  }
  v33 = (char *)a1;
  v35[0] = 0;
  lpsz = 0;
  v34 = 0;
  ValueWithAlloc = HrRegGetValueWithAlloc(hKey, L"ClassManagers", v35, (unsigned __int8 **)&lpsz, &v34);
  if ( ValueWithAlloc )
    goto LABEL_27;
  if ( v35[0] == 7 )
  {
    v8 = (OLECHAR *)lpsz;
    v38 = lpsz;
    v9 = 0;
    v31 = 0;
    v10 = lpsz;
    v34 = 0;
    v11 = (PVOID *)WPP_GLOBAL_Control;
    while ( 1 )
    {
      lpsz = v10;
      if ( !*v10 )
      {
        if ( v9 && v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 8) != 0 )
          WPP_SF_(v11[2], 70, &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids);
        MemFree(v8);
        goto LABEL_27;
      }
      pclsid = 0;
      if ( CLSIDFromString(v10, &pclsid) >= 0 )
        break;
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids, v10);
LABEL_17:
        v11 = (PVOID *)WPP_GLOBAL_Control;
      }
      v9 = v31;
LABEL_19:
      v12 = -1;
      do
        ++v12;
      while ( v10[v12] );
      v10 += v12 + 1;
    }
    try
    {
      std::list<_GUID>::_Emplace<_GUID const &>(&v43, v43, &pclsid);
    }
    catch ( std::bad_alloc )
    {
      v31 = 1;
      v36 = v37;
      v32 = 0;
      ValueWithAlloc = v34;
      v8 = (OLECHAR *)v38;
      v9 = 1;
      v10 = lpsz;
      v11 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_19;
    }
    goto LABEL_17;
  }
  MemFree((void *)lpsz);
  ValueWithAlloc = -2147023092;
LABEL_27:
  RegCloseKey(hKey);
  while ( 1 )
  {
    v13 = (LPCOLESTR *)*((_QWORD *)v33 + 16);
    v14 = *v13;
    lpsz = *v13;
    v15 = (const IID *)v43;
LABEL_29:
    if ( v14 == (LPCOLESTR)v13 )
      break;
    for ( i = *(const IID **)&v15->Data1; i != v15; i = *(const IID **)&i->Data1 )
    {
      if ( *(_QWORD *)&i[1].Data1 == *((_QWORD *)v14 + 4) && *(_QWORD *)i[1].Data4 == *((_QWORD *)v14 + 5) )
      {
        if ( i != v15 )
        {
          std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IUnknown * const,NotifySourceInfo *>>>,std::_Iterator_base0>::operator++(&lpsz);
          v14 = lpsz;
          goto LABEL_29;
        }
        break;
      }
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids);
    v32 = 1;
    v17 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v14 + 6) + 16LL))(*((_QWORD *)v14 + 6));
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids, v17);
    v18 = (_QWORD *)std::_Tree_val<std::_Tree_simple_types<std::pair<IUnknown * const,NotifySourceInfo *>>>::_Extract(
                      v33 + 128,
                      v14);
    std::_Deallocate<16>(v18, 0x38u);
  }
  v19 = *(const IID **)&v15->Data1;
  v20 = (PVOID *)WPP_GLOBAL_Control;
  v21 = v33;
  while ( v19 != v15 )
  {
    v22 = (_QWORD *)std::_Tree<std::_Tmap_traits<_GUID,INetConnectionManager *,std::less<_GUID>,std::allocator<std::pair<_GUID const,INetConnectionManager *>>,0>>::find(
                      v21 + 128,
                      &v38,
                      &v19[1]);
    v21 = v33;
    if ( *v22 == *((_QWORD *)v33 + 16) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids);
      v32 = 1;
      lpsz = 0;
      Instance = CoCreateInstance(v19 + 1, 0, 0x417u, &GUID_c08956a2_1cd3_11d1_b1c5_00805fc1270e, (LPVOID *)&lpsz);
      ValueWithAlloc = Instance;
      v20 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids, Instance);
        v20 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( ValueWithAlloc >= 0 )
      {
        if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 8) != 0 )
          WPP_SF_(v20[2], 75, &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids);
        v24 = (_QWORD *)std::_Tree<std::_Tmap_traits<_GUID,INetConnectionManager *,std::less<_GUID>,std::allocator<std::pair<_GUID const,INetConnectionManager *>>,0>>::find(
                          v33 + 128,
                          &v37,
                          &v19[1]);
        v25 = *((_QWORD *)v33 + 16);
        if ( *v24 != v25 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs(v25);
          v20 = (PVOID *)WPP_GLOBAL_Control;
          v21 = v33;
          goto LABEL_61;
        }
        v26 = lpsz;
        *(_QWORD *)(*(_QWORD *)std::map<_GUID,INetConnectionManager *>::_Try_emplace<_GUID const &,>(
                                 v33 + 128,
                                 &pclsid,
                                 &v19[1])
                  + 48LL) = v26;
        v20 = (PVOID *)WPP_GLOBAL_Control;
      }
      v21 = v33;
    }
    else
    {
      v20 = (PVOID *)WPP_GLOBAL_Control;
    }
LABEL_61:
    v19 = *(const IID **)&v19->Data1;
    v15 = (const IID *)v43;
  }
  v6 = v32;
  if ( ValueWithAlloc < 0 )
  {
LABEL_70:
    if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 1) != 0 )
      WPP_SF_d(v20[2], 77, &WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids, (unsigned int)ValueWithAlloc);
  }
LABEL_73:
  if ( v6 )
    LanEventNotify(7, 0);
  RegNotifyChangeKeyValue(*(HKEY *)(v36 + 200), 0, 4u, *(HANDLE *)(v36 + 184), 1);
  v28 = (_QWORD **)v43;
  **(_QWORD **)(v43 + 8) = 0;
  v29 = *v28;
  if ( v29 )
  {
    do
    {
      v30 = (_QWORD *)*v29;
      std::_Deallocate<16>(v29, 0x20u);
      v29 = v30;
    }
    while ( v30 );
  }
  std::_Deallocate<16>((_QWORD *)v43, 0x20u);
  LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x18001ccd0  mov     [rsp+arg_10], rbx
0x18001ccd5  mov     [rsp+arg_18], rsi
0x18001ccda  push    rdi
0x18001ccdb  push    r12
0x18001ccdd  push    r13
0x18001ccdf  sub     rsp, 0B0h
0x18001cce6  mov     rax, cs:__security_cookie
0x18001cced  xor     rax, rsp
0x18001ccf0  mov     [rsp+0C8h+var_20], rax
0x18001ccf8  movzx   ebx, dl
0x18001ccfb  mov     rdi, rcx
0x18001ccfe  mov     [rsp+0C8h+var_78], rcx
0x18001cd03  lea     r12, WPP_GLOBAL_Control
0x18001cd0a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd11  cmp     rcx, r12
0x18001cd14  jz      short loc_18001CD5B
0x18001cd16  test    byte ptr [rcx+1Ch], 8
0x18001cd1a  jz      short loc_18001CD38
0x18001cd1c  mov     edx, 43h ; 'C'
0x18001cd21  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001cd28  mov     rcx, [rcx+10h]
0x18001cd2c  call    WPP_SF_
0x18001cd31  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd38  cmp     rcx, r12
0x18001cd3b  jz      short loc_18001CD5B
0x18001cd3d  test    byte ptr [rcx+1Ch], 8
0x18001cd41  jz      short loc_18001CD5B
0x18001cd43  mov     r9d, ebx
0x18001cd46  mov     edx, 44h ; 'D'
0x18001cd4b  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001cd52  mov     rcx, [rcx+10h]
0x18001cd56  call    WPP_SF_d
0x18001cd5b  mov     [rsp+0C8h+var_70], rdi
0x18001cd60  mov     rax, rdi
0x18001cd63  lea     rcx, [rdi+48h]
0x18001cd67  neg     rax
0x18001cd6a  sbb     rdx, rdx
0x18001cd6d  and     rdx, rcx
0x18001cd70  mov     [rsp+0C8h+var_58], rdx
0x18001cd75  lea     rax, [rdx+8]
0x18001cd79  mov     [rsp+0C8h+lpCriticalSection], rax
0x18001cd7e  mov     rcx, rax; lpCriticalSection
0x18001cd81  call    cs:__imp_EnterCriticalSection
0x18001cd87  nop
0x18001cd88  xorps   xmm1, xmm1
0x18001cd8b  movdqu  [rsp+0C8h+var_40], xmm1
0x18001cd94  mov     ecx, 20h ; ' '; unsigned __int64
0x18001cd99  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18001cd9e  mov     [rax], rax
0x18001cda1  mov     [rax+8], rax
0x18001cda5  mov     qword ptr [rsp+0C8h+var_40], rax
0x18001cdad  xor     esi, esi
0x18001cdaf  mov     ebx, esi
0x18001cdb1  mov     [rsp+0C8h+var_94], ebx
0x18001cdb5  mov     [rsp+0C8h+hKey], rsi
0x18001cdbd  lea     r9, [rsp+0C8h+hKey]; HKEY *
0x18001cdc5  mov     r8d, 20019h; unsigned int
0x18001cdcb  lea     rdx, ?c_szRegKeyClassManagers@@3QBGB; "System\\CurrentControlSet\\Control\\Net"...
0x18001cdd2  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18001cdd9  call    ?HrRegOpenKeyEx@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; HrRegOpenKeyEx(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x18001cdde  mov     r13d, eax
0x18001cde1  test    eax, eax
0x18001cde3  js      loc_18001D1DC
0x18001cde9  mov     [rsp+0C8h+var_90], rdi
0x18001cdee  mov     [rsp+0C8h+var_84], esi
0x18001cdf2  mov     [rsp+0C8h+lpsz], rsi
0x18001cdf7  mov     [rsp+0C8h+var_88], esi
0x18001cdfb  lea     rax, [rsp+0C8h+var_88]
0x18001ce00  mov     [rsp+0C8h+ppv], rax; unsigned int *
0x18001ce05  lea     r9, [rsp+0C8h+lpsz]; unsigned __int8 **
0x18001ce0a  lea     r8, [rsp+0C8h+var_84]; unsigned int *
0x18001ce0f  lea     rdx, ?c_szRegValClassManagers@@3QBGB; "ClassManagers"
0x18001ce16  mov     rcx, [rsp+0C8h+hKey]; HKEY
0x18001ce1e  call    ?HrRegGetValueWithAlloc@@YAJPEAUHKEY__@@PEBGPEAKPEAPEAE2@Z; HrRegGetValueWithAlloc(HKEY__ *,ushort const *,ulong *,uchar * *,ulong *)
0x18001ce23  mov     r13d, eax
0x18001ce26  test    eax, eax
0x18001ce28  jnz     loc_18001CF66
0x18001ce2e  cmp     [rsp+0C8h+var_84], 7
0x18001ce33  jz      short loc_18001CE4A
0x18001ce35  mov     rcx, [rsp+0C8h+lpsz]; lpMem
0x18001ce3a  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18001ce3f  mov     r13d, 8007070Ch
0x18001ce45  jmp     loc_18001CF66
0x18001ce4a  mov     rdi, [rsp+0C8h+lpsz]
0x18001ce4f  mov     [rsp+0C8h+var_68], rdi
0x18001ce54  mov     dl, sil
0x18001ce57  mov     [rsp+0C8h+var_98], dl
0x18001ce5b  mov     rbx, rdi
0x18001ce5e  mov     [rsp+0C8h+var_88], eax
0x18001ce62  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ce69  mov     [rsp+0C8h+lpsz], rbx
0x18001ce6e  cmp     [rbx], si
0x18001ce71  jz      loc_18001CF3A
0x18001ce77  xorps   xmm0, xmm0
0x18001ce7a  movups  xmmword ptr [rsp+0C8h+pclsid.Data1], xmm0
0x18001ce82  lea     rdx, [rsp+0C8h+pclsid]; pclsid
0x18001ce8a  mov     rcx, rbx; lpsz
0x18001ce8d  call    cs:__imp_CLSIDFromString
0x18001ce93  test    eax, eax
0x18001ce95  jns     short loc_18001CEE3
0x18001ce97  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ce9e  cmp     rcx, r12
0x18001cea1  jz      short loc_18001CEC8
0x18001cea3  test    byte ptr [rcx+1Ch], 8
0x18001cea7  jz      short loc_18001CEC8
0x18001cea9  mov     edx, 45h ; 'E'
0x18001ceae  mov     r9, rbx
0x18001ceb1  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001ceb8  mov     rcx, [rcx+10h]
0x18001cebc  call    WPP_SF_S
0x18001cec1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cec8  mov     dl, [rsp+0C8h+var_98]
0x18001cecc  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ced0  inc     rax
0x18001ced3  cmp     [rbx+rax*2], si
0x18001ced7  jnz     short loc_18001CED0
0x18001ced9  lea     rbx, [rbx+rax*2]
0x18001cedd  add     rbx, 2
0x18001cee1  jmp     short loc_18001CE69
0x18001cee3  lea     r8, [rsp+0C8h+pclsid]
0x18001ceeb  mov     rdx, qword ptr [rsp+0C8h+var_40]
0x18001cef3  lea     rcx, [rsp+0C8h+var_40]
0x18001cefb  call    ??$_Emplace@AEBU_GUID@@@?$list@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAAPEAU?$_List_node@U_GUID@@PEAX@1@QEAU21@AEBU_GUID@@@Z; std::list<_GUID>::_Emplace<_GUID const &>(std::_List_node<_GUID,void *> * const,_GUID const &)
0x18001cf00  nop
0x18001cf01  jmp     short loc_18001CEC1
0x18001cf03  lea     r12, WPP_GLOBAL_Control
0x18001cf0a  xor     esi, esi
0x18001cf0c  mov     rax, [rsp+0C8h+var_70]
0x18001cf11  mov     [rsp+0C8h+var_78], rax
0x18001cf16  mov     [rsp+0C8h+var_94], esi
0x18001cf1a  mov     r13d, [rsp+0C8h+var_88]
0x18001cf1f  mov     rdi, [rsp+0C8h+var_68]
0x18001cf24  mov     dl, [rsp+0C8h+var_98]
0x18001cf28  mov     [rsp+0C8h+var_98], dl
0x18001cf2c  mov     rbx, [rsp+0C8h+lpsz]
0x18001cf31  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf38  jmp     short loc_18001CECC
0x18001cf3a  test    dl, dl
0x18001cf3c  jz      short loc_18001CF5E
0x18001cf3e  cmp     rcx, r12
0x18001cf41  jz      short loc_18001CF5E
0x18001cf43  test    byte ptr [rcx+1Ch], 8
0x18001cf47  jz      short loc_18001CF5E
0x18001cf49  mov     edx, 46h ; 'F'
0x18001cf4e  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001cf55  mov     rcx, [rcx+10h]
0x18001cf59  call    WPP_SF_
0x18001cf5e  mov     rcx, rdi; lpMem
0x18001cf61  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18001cf66  mov     rcx, [rsp+0C8h+hKey]; hKey
0x18001cf6e  call    cs:__imp_RegCloseKey
0x18001cf74  mov     rdi, [rsp+0C8h+var_90]
0x18001cf79  mov     r10, [rdi+80h]
0x18001cf80  mov     rbx, [r10]
0x18001cf83  mov     [rsp+0C8h+lpsz], rbx
0x18001cf88  mov     r9, qword ptr [rsp+0C8h+var_40]
0x18001cf90  cmp     rbx, r10
0x18001cf93  jz      loc_18001D05A
0x18001cf99  mov     rax, [r9]
0x18001cf9c  cmp     rax, r9
0x18001cf9f  jz      short loc_18001CFD0
0x18001cfa1  mov     rcx, [rax+10h]
0x18001cfa5  cmp     rcx, [rbx+20h]
0x18001cfa9  jnz     short loc_18001CFB5
0x18001cfab  mov     rcx, [rax+18h]
0x18001cfaf  cmp     rcx, [rbx+28h]
0x18001cfb3  jz      short loc_18001CFBA
0x18001cfb5  mov     rax, [rax]
0x18001cfb8  jmp     short loc_18001CF9C
0x18001cfba  cmp     rax, r9
0x18001cfbd  jz      short loc_18001CFD0
0x18001cfbf  lea     rcx, [rsp+0C8h+lpsz]
0x18001cfc4  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUIUnknown@@PEAVNotifySourceInfo@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IUnknown * const,NotifySourceInfo *>>>,std::_Iterator_base0>::operator++(void)
0x18001cfc9  mov     rbx, [rsp+0C8h+lpsz]
0x18001cfce  jmp     short loc_18001CF90
0x18001cfd0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cfd7  cmp     rcx, r12
0x18001cfda  jz      short loc_18001CFF7
0x18001cfdc  test    byte ptr [rcx+1Ch], 8
0x18001cfe0  jz      short loc_18001CFF7
0x18001cfe2  mov     edx, 47h ; 'G'
0x18001cfe7  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001cfee  mov     rcx, [rcx+10h]
0x18001cff2  call    WPP_SF_
0x18001cff7  mov     [rsp+0C8h+var_94], 1
0x18001cfff  mov     rcx, [rbx+30h]
0x18001d003  mov     rax, [rcx]
0x18001d006  mov     rax, [rax+10h]
0x18001d00a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d00f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d016  cmp     rcx, r12
0x18001d019  jz      short loc_18001D039
0x18001d01b  test    byte ptr [rcx+1Ch], 8
0x18001d01f  jz      short loc_18001D039
0x18001d021  mov     edx, 48h ; 'H'
0x18001d026  mov     r9d, eax
0x18001d029  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001d030  mov     rcx, [rcx+10h]
0x18001d034  call    WPP_SF_d
0x18001d039  mov     rdx, rbx
0x18001d03c  lea     rcx, [rdi+80h]
0x18001d043  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUIUnknown@@PEAVNotifySourceInfo@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEAUIUnknown@@PEAVNotifySourceInfo@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUIUnknown@@PEAVNotifySourceInfo@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<IUnknown * const,NotifySourceInfo *>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<IUnknown * const,NotifySourceInfo *>>>,std::_Iterator_base0>)
0x18001d048  mov     edx, 38h ; '8'
0x18001d04d  mov     rcx, rax
0x18001d050  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001d055  jmp     loc_18001CF79
0x18001d05a  mov     rbx, [r9]
0x18001d05d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d064  mov     r11, rdi
0x18001d067  cmp     rbx, r9
0x18001d06a  jz      loc_18001D1D1
0x18001d070  lea     rdi, [rbx+10h]
0x18001d074  mov     r8, rdi
0x18001d077  lea     rdx, [rsp+0C8h+var_68]
0x18001d07c  lea     rcx, [r11+80h]
0x18001d083  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@PEAUINetConnectionManager@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAUINetConnectionManager@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAUINetConnectionManager@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,INetConnectionManager *,std::less<_GUID>,std::allocator<std::pair<_GUID const,INetConnectionManager *>>,0>>::find(_GUID const &)
0x18001d088  mov     r11, [rsp+0C8h+var_90]
0x18001d08d  mov     rcx, [r11+80h]
0x18001d094  cmp     [rax], rcx
0x18001d097  jnz     loc_18001D1C8
0x18001d09d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d0a4  cmp     rcx, r12
0x18001d0a7  jz      short loc_18001D0C4
0x18001d0a9  test    byte ptr [rcx+1Ch], 8
0x18001d0ad  jz      short loc_18001D0C4
0x18001d0af  mov     edx, 49h ; 'I'
0x18001d0b4  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001d0bb  mov     rcx, [rcx+10h]
0x18001d0bf  call    WPP_SF_
0x18001d0c4  mov     [rsp+0C8h+var_94], 1
0x18001d0cc  mov     [rsp+0C8h+lpsz], rsi
0x18001d0d1  lea     rax, [rsp+0C8h+lpsz]
0x18001d0d6  mov     [rsp+0C8h+ppv], rax; ppv
0x18001d0db  lea     r9, _GUID_c08956a2_1cd3_11d1_b1c5_00805fc1270e; riid
0x18001d0e2  xor     edx, edx; pUnkOuter
0x18001d0e4  mov     r8d, 417h; dwClsContext
0x18001d0ea  mov     rcx, rdi; rclsid
0x18001d0ed  call    cs:__imp_CoCreateInstance
0x18001d0f3  mov     r13d, eax
0x18001d0f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d0fd  cmp     rcx, r12
0x18001d100  jz      short loc_18001D127
0x18001d102  test    byte ptr [rcx+1Ch], 8
0x18001d106  jz      short loc_18001D127
0x18001d108  mov     edx, 4Ah ; 'J'
0x18001d10d  mov     r9d, eax
0x18001d110  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001d117  mov     rcx, [rcx+10h]
0x18001d11b  call    WPP_SF_d
0x18001d120  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d127  test    r13d, r13d
0x18001d12a  js      loc_18001D1B3
0x18001d130  cmp     rcx, r12
0x18001d133  jz      short loc_18001D150
0x18001d135  test    byte ptr [rcx+1Ch], 8
0x18001d139  jz      short loc_18001D150
0x18001d13b  mov     edx, 4Bh ; 'K'
0x18001d140  lea     r8, WPP_222c4f5b31d53f1a68824fa239ddbced_Traceguids
0x18001d147  mov     rcx, [rcx+10h]
0x18001d14b  call    WPP_SF_
0x18001d150  mov     r8, rdi
0x18001d153  lea     rdx, [rsp+0C8h+var_70]
0x18001d158  mov     rdi, [rsp+0C8h+var_90]
0x18001d15d  lea     rcx, [rdi+80h]
0x18001d164  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@PEAUINetConnectionManager@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAUINetConnectionManager@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAUINetConnectionManager@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,INetConnectionManager *,std::less<_GUID>,std::allocator<std::pair<_GUID const,INetConnectionManager *>>,0>>::find(_GUID const &)
0x18001d169  mov     rcx, [rdi+80h]
0x18001d170  cmp     [rax], rcx
0x18001d173  jz      short loc_18001D186
0x18001d175  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001d17a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d181  mov     r11, rdi
0x18001d184  jmp     short loc_18001D1B8
0x18001d186  mov     rdi, [rsp+0C8h+lpsz]
0x18001d18b  lea     r8, [rbx+10h]
0x18001d18f  lea     rdx, [rsp+0C8h+pclsid]
0x18001d197  mov     rcx, [rsp+0C8h+var_90]
0x18001d19c  sub     rcx, 0FFFFFFFFFFFFFF80h
0x18001d1a0  call    ??$_Try_emplace@AEBU_GUID@@$$V@?$map@U_GUID@@PEAUINetConnectionManager@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAUINetConnectionManager@@@std@@@4@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@PEAUINetConnectionManager@@@std@@PEAX@std@@_N@1@AEBU_GUID@@@Z; std::map<_GUID,INetConnectionManager *>::_Try_emplace<_GUID const &,>(_GUID const &)
0x18001d1a5  mov     rcx, [rax]
0x18001d1a8  mov     [rcx+30h], rdi
0x18001d1ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d1b3  mov     r11, [rsp+0C8h+var_90]
0x18001d1b8  mov     rbx, [rbx]
0x18001d1bb  mov     r9, qword ptr [rsp+0C8h+var_40]
0x18001d1c3  jmp     loc_18001D067
0x18001d1c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d1cf  jmp     short loc_18001D1B8
0x18001d1d1  mov     ebx, [rsp+0C8h+var_94]
0x18001d1d5  test    r13d, r13d
0x18001d1d8  jns     short loc_18001D239
0x18001d1da  jmp     short loc_18001D216
0x18001d1dc  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18001d1e1  test    eax, eax
0x18001d1e3  jns     short loc_18001D20F
0x18001d1e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d1ec  cmp     rcx, r12
0x18001d1ef  jz      short loc_18001D239
0x18001d1f1  test    byte ptr [rcx+1Ch], 1
0x18001d1f5  jz      short loc_18001D216
0x18001d1f7  mov     edx, 4Ch ; 'L'
  ... truncated ...
```
