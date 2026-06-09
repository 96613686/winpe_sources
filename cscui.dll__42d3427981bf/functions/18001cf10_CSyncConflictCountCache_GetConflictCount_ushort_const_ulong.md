# CSyncConflictCountCache::GetConflictCount(ushort const *,ulong *)

- ea: `0x18001cf10`
- end: `0x18001d06e`
- name: `?GetConflictCount@CSyncConflictCountCache@@QEAAJPEBGPEAK@Z`
- size: `350`
- prototype: `__int64 __fastcall(CSyncConflictCountCache *__hidden this, PCNZWCH lpString1, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001d0d0`

## callees

- `0x180013d9c`
- `0x18001cf10`
- `0x18001f3f4`
- `0x18001f57c`
- `0x18001fec4`
- `0x18004aa4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d02b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d02b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cf68`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cf68`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001cfe6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001cfe6`

## pseudocode

```c
__int64 __fastcall CSyncConflictCountCache::GetConflictCount(
        CSyncConflictCountCache *this,
        PCNZWCH lpString1,
        unsigned int *a3)
{
  int SyncItemInfo; // edi
  unsigned int *v7; // rax
  unsigned int v8; // r12d
  unsigned int i; // esi
  PCNZWCH *ItemPtr; // rax
  PCNZWCH *v11; // r15
  int v12; // edx
  int v13; // r8d

  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_bafd4961db7d3885dd5128069fc3a0ad_Traceguids, lpString1);
  }
  *a3 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)this);
  SyncItemInfo = 0;
  if ( !*((_DWORD *)this + 11) )
  {
    SyncItemInfo = CSyncConflictCountCache::_LoadSyncItemInfo(this);
    if ( SyncItemInfo < 0 )
      goto LABEL_20;
    SyncItemInfo = CSyncConflictCountCache::_LoadConflictInfo(this);
    if ( SyncItemInfo < 0 )
      goto LABEL_20;
    *((_DWORD *)this + 11) = 1;
  }
  v7 = (unsigned int *)*((_QWORD *)this + 6);
  if ( v7 )
    v8 = *v7;
  else
    v8 = 0;
  for ( i = 0; i < v8; ++i )
  {
    ItemPtr = (PCNZWCH *)DSA_GetItemPtr(*((HDSA *)this + 6), i);
    v11 = ItemPtr;
    if ( ItemPtr && CompareStringW(0x7Fu, 1u, lpString1, -1, *ItemPtr, -1) == 2 )
    {
      *a3 = *((_DWORD *)v11 + 4);
      goto LABEL_20;
    }
  }
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_bafd4961db7d3885dd5128069fc3a0ad_Traceguids, lpString1);
  }
LABEL_20:
  LeaveCriticalSection((LPCRITICAL_SECTION)this);
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
  {
    WPP_SF_dSD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, v13, *a3, (__int64)lpString1, SyncItemInfo);
  }
  return (unsigned int)SyncItemInfo;
}

```

## disassembly

```asm
0x18001cf10  push    rbx
0x18001cf12  push    rbp
0x18001cf13  push    rsi
0x18001cf14  push    rdi
0x18001cf15  push    r12
0x18001cf17  push    r13
0x18001cf19  push    r14
0x18001cf1b  push    r15
0x18001cf1d  sub     rsp, 38h
0x18001cf21  mov     r14, r8
0x18001cf24  mov     rbp, rdx
0x18001cf27  mov     rbx, rcx
0x18001cf2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf31  lea     r13, WPP_GLOBAL_Control
0x18001cf38  cmp     rcx, r13
0x18001cf3b  jz      short loc_18001CF5E
0x18001cf3d  test    dword ptr [rcx+1Ch], 200000h
0x18001cf44  jz      short loc_18001CF5E
0x18001cf46  mov     rcx, [rcx+10h]
0x18001cf4a  lea     r8, WPP_bafd4961db7d3885dd5128069fc3a0ad_Traceguids
0x18001cf51  mov     edx, 33h ; '3'
0x18001cf56  mov     r9, rbp
0x18001cf59  call    WPP_SF_S
0x18001cf5e  mov     rcx, rbx; lpCriticalSection
0x18001cf61  mov     dword ptr [r14], 0
0x18001cf68  call    cs:__imp_EnterCriticalSection
0x18001cf6e  xor     edi, edi
0x18001cf70  cmp     [rbx+2Ch], edi
0x18001cf73  jnz     short loc_18001CFA0
0x18001cf75  mov     rcx, rbx; this
0x18001cf78  call    ?_LoadSyncItemInfo@CSyncConflictCountCache@@AEAAJXZ; CSyncConflictCountCache::_LoadSyncItemInfo(void)
0x18001cf7d  mov     edi, eax
0x18001cf7f  test    eax, eax
0x18001cf81  js      loc_18001D028
0x18001cf87  mov     rcx, rbx; this
0x18001cf8a  call    ?_LoadConflictInfo@CSyncConflictCountCache@@AEAAJXZ; CSyncConflictCountCache::_LoadConflictInfo(void)
0x18001cf8f  mov     edi, eax
0x18001cf91  test    eax, eax
0x18001cf93  js      loc_18001D028
0x18001cf99  mov     dword ptr [rbx+2Ch], 1
0x18001cfa0  mov     rax, [rbx+30h]
0x18001cfa4  test    rax, rax
0x18001cfa7  jz      short loc_18001CFAE
0x18001cfa9  mov     r12d, [rax]
0x18001cfac  jmp     short loc_18001CFB1
0x18001cfae  xor     r12d, r12d
0x18001cfb1  xor     esi, esi
0x18001cfb3  cmp     esi, r12d
0x18001cfb6  jnb     short loc_18001CFFE
0x18001cfb8  mov     rcx, [rbx+30h]; hdsa
0x18001cfbc  mov     edx, esi; i
0x18001cfbe  call    DSA_GetItemPtr
0x18001cfc3  mov     r15, rax
0x18001cfc6  test    rax, rax
0x18001cfc9  jz      short loc_18001CFF1
0x18001cfcb  mov     rcx, [r15]
0x18001cfce  or      eax, 0FFFFFFFFh
0x18001cfd1  mov     [rsp+78h+cchCount2], eax; cchCount2
0x18001cfd5  mov     r9d, eax; cchCount1
0x18001cfd8  mov     [rsp+78h+lpString2], rcx; lpString2
0x18001cfdd  mov     r8, rbp; lpString1
0x18001cfe0  lea     edx, [rax+2]; dwCmpFlags
0x18001cfe3  lea     ecx, [rdx+7Eh]; Locale
0x18001cfe6  call    cs:__imp_CompareStringW
0x18001cfec  cmp     eax, 2
0x18001cfef  jz      short loc_18001CFF5
0x18001cff1  inc     esi
0x18001cff3  jmp     short loc_18001CFB3
0x18001cff5  mov     eax, [r15+10h]
0x18001cff9  mov     [r14], eax
0x18001cffc  jmp     short loc_18001D028
0x18001cffe  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d005  cmp     rcx, r13
0x18001d008  jz      short loc_18001D028
0x18001d00a  test    byte ptr [rcx+1Ch], 2
0x18001d00e  jz      short loc_18001D028
0x18001d010  mov     rcx, [rcx+10h]
0x18001d014  lea     r8, WPP_bafd4961db7d3885dd5128069fc3a0ad_Traceguids
0x18001d01b  mov     edx, 34h ; '4'
0x18001d020  mov     r9, rbp
0x18001d023  call    WPP_SF_S
0x18001d028  mov     rcx, rbx; lpCriticalSection
0x18001d02b  call    cs:__imp_LeaveCriticalSection
0x18001d031  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d038  cmp     rcx, r13
0x18001d03b  jz      short loc_18001D05B
0x18001d03d  test    dword ptr [rcx+1Ch], 200000h
0x18001d044  jz      short loc_18001D05B
0x18001d046  mov     r9d, [r14]
0x18001d049  mov     rcx, [rcx+10h]
0x18001d04d  mov     [rsp+78h+cchCount2], edi
0x18001d051  mov     [rsp+78h+lpString2], rbp
0x18001d056  call    WPP_SF_dSD
0x18001d05b  mov     eax, edi
0x18001d05d  add     rsp, 38h
0x18001d061  pop     r15
0x18001d063  pop     r14
0x18001d065  pop     r13
0x18001d067  pop     r12
0x18001d069  pop     rdi
0x18001d06a  pop     rsi
0x18001d06b  pop     rbp
0x18001d06c  pop     rbx
0x18001d06d  retn
```
