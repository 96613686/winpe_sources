# CWiGigDAFProviderAssociation::RemoveAssociation(void)

- ea: `0x18000a810`
- end: `0x18000adab`
- name: `?RemoveAssociation@CWiGigDAFProviderAssociation@@QEAAJXZ`
- size: `1435`
- prototype: `__int64 __fastcall(CWiGigDAFProviderAssociation *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x18000c1c0`

## callees

- `0x180009040`
- `0x18000a810`
- `0x18000adb4`
- `0x18000c308`
- `0x18000c348`
- `0x18000fbc8`
- `0x180011c2c`
- `0x180011ee8`
- `0x180011ff8`
- `0x180012ba0`
- `0x18001471c`
- `0x180014a78`
- `0x180014be4`
- `0x18001ca3e`
- `0x18001ca70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a923`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aa1a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a923`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aa1a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a950`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a96c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aa42`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aa60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a950`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a96c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aa42`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aa60`

## pseudocode

```c
__int64 __fastcall CWiGigDAFProviderAssociation::RemoveAssociation(CWiGigDAFProviderAssociation *this)
{
  _QWORD *v2; // rcx
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  bool v5; // r14
  int Profile; // ebx
  int v7; // eax
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  int Dock; // esi
  _BYTE *v10; // rcx
  __int64 v11; // rdx
  int v12; // eax
  __int64 v13; // rcx
  unsigned int v14; // ebx
  int v15; // eax
  int v16; // eax
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  int v19; // eax
  bool v20; // [rsp+30h] [rbp-D0h] BYREF
  Dock *v21; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v22[1144]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v23; // [rsp+4B8h] [rbp+3B8h]
  _BYTE v24[1152]; // [rsp+4D0h] [rbp+3D0h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 130, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this);
    v2 = WPP_GLOBAL_Control;
  }
  if ( *((_BYTE *)this + 3288) )
  {
    if ( v2 != &WPP_GLOBAL_Control )
    {
      if ( *((_BYTE *)v2 + 25) >= 3u && (*((_BYTE *)v2 + 28) & 1) != 0 )
      {
        WPP_SF_q(v2[2], 131, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this);
        v2 = WPP_GLOBAL_Control;
      }
      if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 25) >= 4u && (*((_BYTE *)v2 + 28) & 1) != 0 )
        WPP_SF_q(v2[2], 132, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this);
    }
    return CWiGigDAFProviderAssociation::CancelCleanup(this);
  }
  memset_0(v24, 0, sizeof(v24));
  memset_0(v22, 0, 0x488u);
  v4 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 410);
  v5 = 0;
  v20 = 0;
  EnterCriticalSection(v4);
  v21 = 0;
  if ( DockCache::FindDock((DockCache *)v4, (const unsigned __int16 *)this + 1344, &v21) >= 0 )
  {
    Profile = Dock::GetProfile(v21, (struct _DOCK_PROFILE *)v22);
    LeaveCriticalSection(v4);
    if ( Profile >= 0 )
      goto LABEL_49;
  }
  else
  {
    LeaveCriticalSection(v4);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 133, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this);
  }
  v7 = CWiGigDAFProviderAssociation::SearchProfiles(
         this,
         (const unsigned __int16 *)this + 1344,
         (struct _VISIBLE_DOCK *)v24,
         (struct _DOCK_PROFILE *)v22,
         &v20);
  if ( v7 < 0 || (v5 = v20) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 134, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this, v7);
    }
    v8 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 410);
    EnterCriticalSection(v8);
    v21 = 0;
    Dock = DockCache::FindDock((DockCache *)v8, (const unsigned __int16 *)this + 1344, &v21);
    if ( Dock < 0 )
    {
      LeaveCriticalSection(v8);
      goto LABEL_31;
    }
    Dock = Dock::GetScanResult(v21, (struct _VISIBLE_DOCK *)v24);
    LeaveCriticalSection(v8);
    if ( Dock < 0 )
    {
LABEL_31:
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return 0;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          135,
          &WPP_c2da2149000737c368804296c411cd66_Traceguids,
          this,
          Dock);
        v10 = WPP_GLOBAL_Control;
      }
      if ( v10 == (_BYTE *)&WPP_GLOBAL_Control || v10[25] < 4u || (v10[28] & 1) == 0 )
        return 0;
      v11 = 136;
      goto LABEL_83;
    }
    v12 = DockingDevnodeHelpers::VisibleDockToConnectedDock(
            (const struct _VISIBLE_DOCK *)v24,
            (struct _DOCK_PROFILE *)v22);
    if ( v12 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return 0;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 137, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this, v12);
        v10 = WPP_GLOBAL_Control;
      }
      if ( v10 == (_BYTE *)&WPP_GLOBAL_Control || v10[25] < 4u || (v10[28] & 1) == 0 )
        return 0;
      v11 = 138;
      goto LABEL_83;
    }
    v5 = 1;
  }
LABEL_49:
  v13 = *((_QWORD *)this + 334);
  v14 = -2147024809;
  if ( v23 >= *(unsigned int *)(v13 + 16) )
  {
    v15 = -2147024809;
  }
  else
  {
    v15 = DockingProvider::ConfigureAutoConnect(
            *(DockingProvider **)(*(_QWORD *)(v13 + 24) + 8 * v23),
            (struct _DOCK_PROFILE *)v22,
            0);
    if ( v15 >= 0 )
      goto LABEL_57;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this, v15);
  }
LABEL_57:
  v16 = DockingProviders::DisconnectDock(*((PSRWLOCK *)this + 334), 0xEA60u, (struct _DOCK_PROFILE *)v22);
  if ( v16 == -2147022646 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 140, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this);
LABEL_67:
      v17 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    if ( v16 >= 0 )
      goto LABEL_67;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 141, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this, v16);
      goto LABEL_67;
    }
  }
  v18 = *((_QWORD *)this + 334);
  if ( v23 < *(unsigned int *)(v18 + 16) )
  {
    v19 = DockingProvider::DeleteProfile(
            *(DockingProvider **)(*(_QWORD *)(v18 + 24) + 8 * v23),
            (struct _DOCK_PROFILE *)v22);
    v17 = WPP_GLOBAL_Control;
    v14 = v19;
    if ( v19 >= 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 145, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this);
      }
LABEL_79:
      DockCache::UnpairedDock(*((DockCache **)this + 410), (const unsigned __int16 *)this + 1344);
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        return 0;
      }
      v11 = 146;
LABEL_83:
      WPP_SF_qD(*((_QWORD *)v10 + 2), v11, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this, 0);
      return 0;
    }
  }
  if ( v5 )
  {
    if ( v17 != &WPP_GLOBAL_Control && *((_BYTE *)v17 + 25) >= 2u && (*((_BYTE *)v17 + 28) & 1) != 0 )
      WPP_SF_qD(v17[2], 142, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this, v14);
    goto LABEL_79;
  }
  if ( v17 != &WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)v17 + 25) >= 2u && (*((_BYTE *)v17 + 28) & 1) != 0 )
    {
      WPP_SF_qD(v17[2], 143, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this, v14);
      v17 = WPP_GLOBAL_Control;
    }
    if ( v17 != &WPP_GLOBAL_Control && *((_BYTE *)v17 + 25) >= 4u && (*((_BYTE *)v17 + 28) & 1) != 0 )
      WPP_SF_qD(v17[2], 144, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this, v14);
  }
  return v14;
}

```

## disassembly

```asm
0x18000a810  push    rbp
0x18000a812  push    rbx
0x18000a813  push    rsi
0x18000a814  push    rdi
0x18000a815  push    r12
0x18000a817  push    r13
0x18000a819  push    r14
0x18000a81b  push    r15
0x18000a81d  lea     rbp, [rsp-868h]
0x18000a825  sub     rsp, 968h
0x18000a82c  mov     rax, cs:__security_cookie
0x18000a833  xor     rax, rsp
0x18000a836  mov     [rbp+8A0h+var_50], rax
0x18000a83d  mov     rdi, rcx
0x18000a840  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a847  lea     r13, WPP_GLOBAL_Control
0x18000a84e  lea     rbx, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000a855  mov     r12b, 1
0x18000a858  cmp     rcx, r13
0x18000a85b  jz      short loc_18000A884
0x18000a85d  cmp     byte ptr [rcx+19h], 4
0x18000a861  jb      short loc_18000A884
0x18000a863  test    [rcx+1Ch], r12b
0x18000a867  jz      short loc_18000A884
0x18000a869  mov     rcx, [rcx+10h]
0x18000a86d  mov     edx, 82h
0x18000a872  mov     r9, rdi
0x18000a875  mov     r8, rbx
0x18000a878  call    WPP_SF_q
0x18000a87d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a884  cmp     byte ptr [rdi+0CD8h], 0
0x18000a88b  jz      short loc_18000A8EB
0x18000a88d  cmp     rcx, r13
0x18000a890  jz      short loc_18000A8DE
0x18000a892  cmp     byte ptr [rcx+19h], 3
0x18000a896  jb      short loc_18000A8B9
0x18000a898  test    [rcx+1Ch], r12b
0x18000a89c  jz      short loc_18000A8B9
0x18000a89e  mov     rcx, [rcx+10h]
0x18000a8a2  mov     edx, 83h
0x18000a8a7  mov     r9, rdi
0x18000a8aa  mov     r8, rbx
0x18000a8ad  call    WPP_SF_q
0x18000a8b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a8b9  cmp     rcx, r13
0x18000a8bc  jz      short loc_18000A8DE
0x18000a8be  cmp     byte ptr [rcx+19h], 4
0x18000a8c2  jb      short loc_18000A8DE
0x18000a8c4  test    [rcx+1Ch], r12b
0x18000a8c8  jz      short loc_18000A8DE
0x18000a8ca  mov     rcx, [rcx+10h]
0x18000a8ce  mov     edx, 84h
0x18000a8d3  mov     r9, rdi
0x18000a8d6  mov     r8, rbx
0x18000a8d9  call    WPP_SF_q
0x18000a8de  mov     rcx, rdi; this
0x18000a8e1  call    ?CancelCleanup@CWiGigDAFProviderAssociation@@AEAAJXZ; CWiGigDAFProviderAssociation::CancelCleanup(void)
0x18000a8e6  jmp     loc_18000AD88
0x18000a8eb  xor     edx, edx; Val
0x18000a8ed  lea     rcx, [rbp+8A0h+var_4D0]; void *
0x18000a8f4  mov     r8d, 480h; Size
0x18000a8fa  call    memset_0
0x18000a8ff  xor     edx, edx; Val
0x18000a901  lea     rcx, [rsp+9A0h+var_960]; void *
0x18000a906  mov     r8d, 488h; Size
0x18000a90c  call    memset_0
0x18000a911  mov     rsi, [rdi+0CD0h]
0x18000a918  xor     r14b, r14b
0x18000a91b  mov     rcx, rsi; lpCriticalSection
0x18000a91e  mov     [rsp+9A0h+var_970], r14b
0x18000a923  call    cs:__imp_EnterCriticalSection
0x18000a929  lea     r15, [rdi+0A80h]
0x18000a930  mov     [rsp+9A0h+var_968], 0
0x18000a939  mov     rdx, r15; unsigned __int16 *
0x18000a93c  lea     r8, [rsp+9A0h+var_968]; struct Dock **
0x18000a941  mov     rcx, rsi; this
0x18000a944  call    ?FindDock@DockCache@@AEAAJPEBGPEAPEAVDock@@@Z; DockCache::FindDock(ushort const *,Dock * *)
0x18000a949  test    eax, eax
0x18000a94b  jns     short loc_18000A958
0x18000a94d  mov     rcx, rsi; lpCriticalSection
0x18000a950  call    cs:__imp_LeaveCriticalSection
0x18000a956  jmp     short loc_18000A981
0x18000a958  mov     rcx, [rsp+9A0h+var_968]; this
0x18000a95d  lea     rdx, [rsp+9A0h+var_960]; struct _DOCK_PROFILE *
0x18000a962  call    ?GetProfile@Dock@@QEAAJPEAU_DOCK_PROFILE@@@Z; Dock::GetProfile(_DOCK_PROFILE *)
0x18000a967  mov     rcx, rsi; lpCriticalSection
0x18000a96a  mov     ebx, eax
0x18000a96c  call    cs:__imp_LeaveCriticalSection
0x18000a972  test    ebx, ebx
0x18000a974  jns     loc_18000AB4E
0x18000a97a  lea     rbx, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000a981  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a988  cmp     rcx, r13
0x18000a98b  jz      short loc_18000A9AD
0x18000a98d  cmp     byte ptr [rcx+19h], 2
0x18000a991  jb      short loc_18000A9AD
0x18000a993  test    [rcx+1Ch], r12b
0x18000a997  jz      short loc_18000A9AD
0x18000a999  mov     rcx, [rcx+10h]
0x18000a99d  mov     edx, 85h
0x18000a9a2  mov     r9, rdi
0x18000a9a5  mov     r8, rbx
0x18000a9a8  call    WPP_SF_q
0x18000a9ad  lea     rax, [rsp+9A0h+var_970]
0x18000a9b2  mov     rdx, r15; unsigned __int16 *
0x18000a9b5  lea     r9, [rsp+9A0h+var_960]; struct _DOCK_PROFILE *
0x18000a9ba  mov     [rsp+9A0h+var_980], rax; bool *
0x18000a9bf  lea     r8, [rbp+8A0h+var_4D0]; struct _VISIBLE_DOCK *
0x18000a9c6  mov     rcx, rdi; this
0x18000a9c9  call    ?SearchProfiles@CWiGigDAFProviderAssociation@@AEAAJPEBGPEAU_VISIBLE_DOCK@@PEAU_DOCK_PROFILE@@PEA_N@Z; CWiGigDAFProviderAssociation::SearchProfiles(ushort const *,_VISIBLE_DOCK *,_DOCK_PROFILE *,bool *)
0x18000a9ce  test    eax, eax
0x18000a9d0  js      short loc_18000A9E0
0x18000a9d2  mov     r14b, [rsp+9A0h+var_970]
0x18000a9d7  test    r14b, r14b
0x18000a9da  jz      loc_18000AB4E
0x18000a9e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a9e7  cmp     rcx, r13
0x18000a9ea  jz      short loc_18000AA10
0x18000a9ec  cmp     byte ptr [rcx+19h], 2
0x18000a9f0  jb      short loc_18000AA10
0x18000a9f2  test    [rcx+1Ch], r12b
0x18000a9f6  jz      short loc_18000AA10
0x18000a9f8  mov     rcx, [rcx+10h]
0x18000a9fc  mov     edx, 86h
0x18000aa01  mov     r9, rdi
0x18000aa04  mov     dword ptr [rsp+9A0h+var_980], eax
0x18000aa08  mov     r8, rbx
0x18000aa0b  call    WPP_SF_qD
0x18000aa10  mov     rbx, [rdi+0CD0h]
0x18000aa17  mov     rcx, rbx; lpCriticalSection
0x18000aa1a  call    cs:__imp_EnterCriticalSection
0x18000aa20  lea     r8, [rsp+9A0h+var_968]; struct Dock **
0x18000aa25  mov     [rsp+9A0h+var_968], 0
0x18000aa2e  mov     rdx, r15; unsigned __int16 *
0x18000aa31  mov     rcx, rbx; this
0x18000aa34  call    ?FindDock@DockCache@@AEAAJPEBGPEAPEAVDock@@@Z; DockCache::FindDock(ushort const *,Dock * *)
0x18000aa39  mov     esi, eax
0x18000aa3b  test    eax, eax
0x18000aa3d  jns     short loc_18000AA4A
0x18000aa3f  mov     rcx, rbx; lpCriticalSection
0x18000aa42  call    cs:__imp_LeaveCriticalSection
0x18000aa48  jmp     short loc_18000AA6A
0x18000aa4a  mov     rcx, [rsp+9A0h+var_968]; this
0x18000aa4f  lea     rdx, [rbp+8A0h+var_4D0]; struct _VISIBLE_DOCK *
0x18000aa56  call    ?GetScanResult@Dock@@QEAAJPEAU_VISIBLE_DOCK@@@Z; Dock::GetScanResult(_VISIBLE_DOCK *)
0x18000aa5b  mov     rcx, rbx; lpCriticalSection
0x18000aa5e  mov     esi, eax
0x18000aa60  call    cs:__imp_LeaveCriticalSection
0x18000aa66  test    esi, esi
0x18000aa68  jns     short loc_18000AAD0
0x18000aa6a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa71  cmp     rcx, r13
0x18000aa74  jz      loc_18000AD21
0x18000aa7a  cmp     byte ptr [rcx+19h], 2
0x18000aa7e  jb      short loc_18000AAA9
0x18000aa80  test    [rcx+1Ch], r12b
0x18000aa84  jz      short loc_18000AAA9
0x18000aa86  mov     rcx, [rcx+10h]
0x18000aa8a  lea     r8, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000aa91  mov     edx, 87h
0x18000aa96  mov     dword ptr [rsp+9A0h+var_980], esi
0x18000aa9a  mov     r9, rdi
0x18000aa9d  call    WPP_SF_qD
0x18000aaa2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aaa9  cmp     rcx, r13
0x18000aaac  jz      loc_18000AD21
0x18000aab2  cmp     byte ptr [rcx+19h], 4
0x18000aab6  jb      loc_18000AD21
0x18000aabc  test    [rcx+1Ch], r12b
0x18000aac0  jz      loc_18000AD21
0x18000aac6  mov     edx, 88h
0x18000aacb  jmp     loc_18000AD06
0x18000aad0  lea     rdx, [rsp+9A0h+var_960]; struct _DOCK_PROFILE *
0x18000aad5  lea     rcx, [rbp+8A0h+var_4D0]; struct _VISIBLE_DOCK *
0x18000aadc  call    ?VisibleDockToConnectedDock@DockingDevnodeHelpers@@SAJAEBU_VISIBLE_DOCK@@PEAU_DOCK_PROFILE@@@Z; DockingDevnodeHelpers::VisibleDockToConnectedDock(_VISIBLE_DOCK const &,_DOCK_PROFILE *)
0x18000aae1  test    eax, eax
0x18000aae3  jns     short loc_18000AB4B
0x18000aae5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aaec  cmp     rcx, r13
0x18000aaef  jz      loc_18000AD21
0x18000aaf5  cmp     byte ptr [rcx+19h], 2
0x18000aaf9  jb      short loc_18000AB24
0x18000aafb  test    [rcx+1Ch], r12b
0x18000aaff  jz      short loc_18000AB24
0x18000ab01  mov     rcx, [rcx+10h]
0x18000ab05  lea     r8, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000ab0c  mov     edx, 89h
0x18000ab11  mov     dword ptr [rsp+9A0h+var_980], eax
0x18000ab15  mov     r9, rdi
0x18000ab18  call    WPP_SF_qD
0x18000ab1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab24  cmp     rcx, r13
0x18000ab27  jz      loc_18000AD21
0x18000ab2d  cmp     byte ptr [rcx+19h], 4
0x18000ab31  jb      loc_18000AD21
0x18000ab37  test    [rcx+1Ch], r12b
0x18000ab3b  jz      loc_18000AD21
0x18000ab41  mov     edx, 8Ah
0x18000ab46  jmp     loc_18000AD06
0x18000ab4b  mov     r14b, r12b
0x18000ab4e  mov     rcx, [rdi+0A70h]
0x18000ab55  mov     ebx, 80070057h
0x18000ab5a  mov     r9, [rbp+8A0h+var_4E8]
0x18000ab61  mov     eax, [rcx+10h]
0x18000ab64  cmp     r9, rax
0x18000ab67  jnb     short loc_18000AB84
0x18000ab69  mov     rcx, [rcx+18h]
0x18000ab6d  lea     rdx, [rsp+9A0h+var_960]; struct _DOCK_PROFILE *
0x18000ab72  xor     r8d, r8d; int
0x18000ab75  mov     rcx, [rcx+r9*8]; this
0x18000ab79  call    ?ConfigureAutoConnect@DockingProvider@@QEAAJPEAU_DOCK_PROFILE@@H@Z; DockingProvider::ConfigureAutoConnect(_DOCK_PROFILE *,int)
0x18000ab7e  test    eax, eax
0x18000ab80  jns     short loc_18000ABBA
0x18000ab82  jmp     short loc_18000AB86
0x18000ab84  mov     eax, ebx
0x18000ab86  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab8d  cmp     rcx, r13
0x18000ab90  jz      short loc_18000ABBA
0x18000ab92  cmp     byte ptr [rcx+19h], 2
0x18000ab96  jb      short loc_18000ABBA
0x18000ab98  test    [rcx+1Ch], r12b
0x18000ab9c  jz      short loc_18000ABBA
0x18000ab9e  mov     rcx, [rcx+10h]
0x18000aba2  lea     r8, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000aba9  mov     edx, 8Bh
0x18000abae  mov     dword ptr [rsp+9A0h+var_980], eax
0x18000abb2  mov     r9, rdi
0x18000abb5  call    WPP_SF_qD
0x18000abba  mov     rcx, [rdi+0A70h]; SRWLock
0x18000abc1  lea     r8, [rsp+9A0h+var_960]; struct _DOCK_PROFILE *
0x18000abc6  mov     edx, 0EA60h; unsigned int
0x18000abcb  call    ?DisconnectDock@DockingProviders@@QEAAJKPEAU_DOCK_PROFILE@@@Z; DockingProviders::DisconnectDock(ulong,_DOCK_PROFILE *)
0x18000abd0  cmp     eax, 800708CAh
0x18000abd5  jnz     short loc_18000AC09
0x18000abd7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000abde  cmp     rcx, r13
0x18000abe1  jz      short loc_18000AC48
0x18000abe3  cmp     byte ptr [rcx+19h], 2
0x18000abe7  jb      short loc_18000AC48
0x18000abe9  test    [rcx+1Ch], r12b
0x18000abed  jz      short loc_18000AC48
0x18000abef  mov     rcx, [rcx+10h]
0x18000abf3  lea     r8, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000abfa  mov     edx, 8Ch
0x18000abff  mov     r9, rdi
0x18000ac02  call    WPP_SF_q
0x18000ac07  jmp     short loc_18000AC41
0x18000ac09  test    eax, eax
0x18000ac0b  jns     short loc_18000AC41
0x18000ac0d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ac14  cmp     rcx, r13
0x18000ac17  jz      short loc_18000AC48
0x18000ac19  cmp     byte ptr [rcx+19h], 2
0x18000ac1d  jb      short loc_18000AC48
0x18000ac1f  test    [rcx+1Ch], r12b
0x18000ac23  jz      short loc_18000AC48
0x18000ac25  mov     rcx, [rcx+10h]
0x18000ac29  lea     r8, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000ac30  mov     edx, 8Dh
0x18000ac35  mov     dword ptr [rsp+9A0h+var_980], eax
0x18000ac39  mov     r9, rdi
0x18000ac3c  call    WPP_SF_qD
0x18000ac41  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ac48  mov     rdx, [rdi+0A70h]
0x18000ac4f  mov     r8, [rbp+8A0h+var_4E8]
0x18000ac56  mov     eax, [rdx+10h]
0x18000ac59  cmp     r8, rax
0x18000ac5c  jnb     short loc_18000ACA8
0x18000ac5e  mov     rcx, [rdx+18h]
0x18000ac62  lea     rdx, [rsp+9A0h+var_960]; struct _DOCK_PROFILE *
0x18000ac67  mov     rcx, [rcx+r8*8]; this
0x18000ac6b  call    ?DeleteProfile@DockingProvider@@QEAAJPEAU_DOCK_PROFILE@@@Z; DockingProvider::DeleteProfile(_DOCK_PROFILE *)
0x18000ac70  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ac77  mov     ebx, eax
0x18000ac79  test    eax, eax
0x18000ac7b  js      short loc_18000ACA8
0x18000ac7d  cmp     rcx, r13
0x18000ac80  jz      short loc_18000ACDA
0x18000ac82  cmp     byte ptr [rcx+19h], 3
0x18000ac86  jb      short loc_18000ACDA
0x18000ac88  test    [rcx+1Ch], r12b
0x18000ac8c  jz      short loc_18000ACDA
0x18000ac8e  mov     rcx, [rcx+10h]
0x18000ac92  lea     r8, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000ac99  mov     edx, 91h
0x18000ac9e  mov     r9, rdi
0x18000aca1  call    WPP_SF_q
0x18000aca6  jmp     short loc_18000ACDA
0x18000aca8  test    r14b, r14b
0x18000acab  jz      short loc_18000AD25
0x18000acad  cmp     rcx, r13
0x18000acb0  jz      short loc_18000ACDA
0x18000acb2  cmp     byte ptr [rcx+19h], 2
0x18000acb6  jb      short loc_18000ACDA
0x18000acb8  test    [rcx+1Ch], r12b
0x18000acbc  jz      short loc_18000ACDA
0x18000acbe  mov     rcx, [rcx+10h]
0x18000acc2  lea     r8, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000acc9  mov     edx, 8Eh
0x18000acce  mov     dword ptr [rsp+9A0h+var_980], ebx
  ... truncated ...
```
