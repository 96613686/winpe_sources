# CWiGigDAFProviderAssociation::InitAssociation(ushort const *,ulong,IAepAssociationCallback *,ulong,_DAF_ASSOCIATION_PARAMETER const *)

- ea: `0x18000a040`
- end: `0x18000a38f`
- name: `?InitAssociation@CWiGigDAFProviderAssociation@@UEAAJPEBGKPEAUIAepAssociationCallback@@KPEBU_DAF_ASSOCIATION_PARAMETER@@@Z`
- size: `847`
- prototype: `__int64 __fastcall(CWiGigDAFProviderAssociation *this, const unsigned __int16 *, __int64, struct IAepAssociationCallback *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000a040`
- `0x18000adb4`
- `0x18000c308`
- `0x18000c348`
- `0x180012110`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a0b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a0b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a0c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a0c6`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000a27e`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000a27e`

## pseudocode

```c
__int64 __fastcall CWiGigDAFProviderAssociation::InitAssociation(
        CWiGigDAFProviderAssociation *this,
        const unsigned __int16 *a2,
        __int64 a3,
        struct IAepAssociationCallback *a4)
{
  _BYTE *v7; // rcx
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // rax
  _WORD *v12; // r8
  __int64 v13; // rdx
  _WORD *v14; // rcx
  NTSTATUS v15; // eax
  NTSTATUS v16; // ebx
  struct IAepAssociationCallback *v17; // rcx
  bool v19; // [rsp+78h] [rbp+10h] BYREF

  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this);
    v7 = WPP_GLOBAL_Control;
  }
  if ( !a2 || !a4 )
  {
    v9 = -2147024809;
    if ( v7 == (_BYTE *)&WPP_GLOBAL_Control || v7[25] < 4u || (v7[28] & 1) == 0 )
      return v9;
    v10 = 35;
    goto LABEL_61;
  }
  if ( *((_QWORD *)this + 7) )
  {
    v9 = -2147023649;
    if ( v7 == (_BYTE *)&WPP_GLOBAL_Control || v7[25] < 4u || (v7[28] & 1) == 0 )
      return v9;
    v10 = 36;
    goto LABEL_61;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  *((_DWORD *)this + 826) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( (int)DockCache::GetScanResultEvenIfStale(
              *((DockCache **)this + 410),
              a2,
              (CWiGigDAFProviderAssociation *)((char *)this + 360)) < 0 )
  {
    v19 = 0;
    v8 = CWiGigDAFProviderAssociation::SearchProfiles(
           this,
           a2,
           (CWiGigDAFProviderAssociation *)((char *)this + 360),
           (CWiGigDAFProviderAssociation *)((char *)this + 1512),
           &v19);
    v9 = v8;
    if ( v8 < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v9;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this, v8);
        v7 = WPP_GLOBAL_Control;
      }
      if ( v7 == (_BYTE *)&WPP_GLOBAL_Control || v7[25] < 4u || (v7[28] & 1) == 0 )
        return v9;
      v10 = 38;
      goto LABEL_61;
    }
    if ( v19 )
    {
      v7 = WPP_GLOBAL_Control;
      v9 = 1168;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v9;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this);
        v7 = WPP_GLOBAL_Control;
      }
      if ( v7 == (_BYTE *)&WPP_GLOBAL_Control || v7[25] < 4u || (v7[28] & 1) == 0 )
        return v9;
      v10 = 40;
      goto LABEL_61;
    }
  }
  v11 = 2147483646;
  v12 = (_WORD *)((char *)this + 2688);
  v13 = 293;
  do
  {
    if ( !v11 )
      break;
    if ( !*a2 )
      break;
    *v12++ = *a2++;
    --v11;
    --v13;
  }
  while ( v13 );
  v14 = v12 - 1;
  v9 = v13 == 0 ? 0x8007007A : 0;
  if ( v13 )
    v14 = v12;
  *v14 = 0;
  if ( !v13 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      return v9;
    }
    v10 = 41;
LABEL_61:
    WPP_SF_qD(*((_QWORD *)v7 + 2), v10, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this, v9);
    return v9;
  }
  v15 = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)this + 335, L"RNG", 0, 0);
  v16 = v15;
  if ( v15 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        &WPP_c2da2149000737c368804296c411cd66_Traceguids,
        this,
        v15 | 0x10000000);
    }
    return v16 | 0x10000000u;
  }
  v17 = (struct IAepAssociationCallback *)*((_QWORD *)this + 7);
  if ( v17 != a4 )
  {
    if ( v17 )
      (*(void (__fastcall **)(struct IAepAssociationCallback *))(*(_QWORD *)v17 + 16LL))(v17);
    *((_QWORD *)this + 7) = a4;
    (*(void (__fastcall **)(struct IAepAssociationCallback *))(*(_QWORD *)a4 + 8LL))(a4);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18000a040  push    rbx
0x18000a042  push    rbp
0x18000a043  push    rsi
0x18000a044  push    rdi
0x18000a045  push    r12
0x18000a047  push    r14
0x18000a049  sub     rsp, 38h
0x18000a04d  mov     r14, r9
0x18000a050  mov     rsi, rdx
0x18000a053  mov     rdi, rcx
0x18000a056  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a05d  lea     r12, WPP_GLOBAL_Control
0x18000a064  cmp     rcx, r12
0x18000a067  jz      short loc_18000A094
0x18000a069  cmp     byte ptr [rcx+19h], 4
0x18000a06d  jb      short loc_18000A094
0x18000a06f  test    byte ptr [rcx+1Ch], 1
0x18000a073  jz      short loc_18000A094
0x18000a075  mov     rcx, [rcx+10h]
0x18000a079  lea     r8, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000a080  mov     edx, 22h ; '"'
0x18000a085  mov     r9, rdi
0x18000a088  call    WPP_SF_q
0x18000a08d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a094  xor     ebp, ebp
0x18000a096  test    rsi, rsi
0x18000a099  jz      loc_18000A34E
0x18000a09f  test    r14, r14
0x18000a0a2  jz      loc_18000A34E
0x18000a0a8  cmp     [rdi+38h], rbp
0x18000a0ac  jnz     loc_18000A331
0x18000a0b2  lea     rcx, [rdi+8]; lpCriticalSection
0x18000a0b6  call    cs:__imp_EnterCriticalSection
0x18000a0bc  lea     rcx, [rdi+8]; lpCriticalSection
0x18000a0c0  mov     [rdi+0CE8h], ebp
0x18000a0c6  call    cs:__imp_LeaveCriticalSection
0x18000a0cc  mov     rcx, [rdi+0CD0h]; this
0x18000a0d3  lea     rbx, [rdi+168h]
0x18000a0da  mov     r8, rbx; struct _VISIBLE_DOCK *
0x18000a0dd  mov     rdx, rsi; unsigned __int16 *
0x18000a0e0  call    ?GetScanResultEvenIfStale@DockCache@@QEAAJPEBGPEAU_VISIBLE_DOCK@@@Z; DockCache::GetScanResultEvenIfStale(ushort const *,_VISIBLE_DOCK *)
0x18000a0e5  test    eax, eax
0x18000a0e7  jns     loc_18000A1E9
0x18000a0ed  lea     rax, [rsp+68h+arg_8]
0x18000a0f2  mov     [rsp+68h+arg_8], bpl
0x18000a0f7  lea     r9, [rdi+5E8h]; struct _DOCK_PROFILE *
0x18000a0fe  mov     [rsp+68h+var_48], rax; bool *
0x18000a103  mov     r8, rbx; struct _VISIBLE_DOCK *
0x18000a106  mov     rdx, rsi; unsigned __int16 *
0x18000a109  mov     rcx, rdi; this
0x18000a10c  call    ?SearchProfiles@CWiGigDAFProviderAssociation@@AEAAJPEBGPEAU_VISIBLE_DOCK@@PEAU_DOCK_PROFILE@@PEA_N@Z; CWiGigDAFProviderAssociation::SearchProfiles(ushort const *,_VISIBLE_DOCK *,_DOCK_PROFILE *,bool *)
0x18000a111  mov     ebx, eax
0x18000a113  test    eax, eax
0x18000a115  jns     short loc_18000A17B
0x18000a117  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a11e  cmp     rcx, r12
0x18000a121  jz      loc_18000A380
0x18000a127  cmp     byte ptr [rcx+19h], 1
0x18000a12b  jb      short loc_18000A154
0x18000a12d  test    byte ptr [rcx+1Ch], 1
0x18000a131  jz      short loc_18000A154
0x18000a133  mov     rcx, [rcx+10h]
0x18000a137  lea     edx, [rbp+25h]
0x18000a13a  mov     r9, rdi
0x18000a13d  mov     dword ptr [rsp+68h+var_48], eax
0x18000a141  lea     r8, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000a148  call    WPP_SF_qD
0x18000a14d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a154  cmp     rcx, r12
0x18000a157  jz      loc_18000A380
0x18000a15d  cmp     byte ptr [rcx+19h], 4
0x18000a161  jb      loc_18000A380
0x18000a167  test    byte ptr [rcx+1Ch], 1
0x18000a16b  jz      loc_18000A380
0x18000a171  mov     edx, 26h ; '&'
0x18000a176  jmp     loc_18000A369
0x18000a17b  cmp     [rsp+68h+arg_8], bpl
0x18000a180  jz      short loc_18000A1E9
0x18000a182  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a189  mov     ebx, 490h
0x18000a18e  cmp     rcx, r12
0x18000a191  jz      loc_18000A380
0x18000a197  cmp     byte ptr [rcx+19h], 2
0x18000a19b  jb      short loc_18000A1C2
0x18000a19d  test    byte ptr [rcx+1Ch], 1
0x18000a1a1  jz      short loc_18000A1C2
0x18000a1a3  mov     rcx, [rcx+10h]
0x18000a1a7  lea     r8, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000a1ae  mov     edx, 27h ; '''
0x18000a1b3  mov     r9, rdi
0x18000a1b6  call    WPP_SF_q
0x18000a1bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a1c2  cmp     rcx, r12
0x18000a1c5  jz      loc_18000A380
0x18000a1cb  cmp     byte ptr [rcx+19h], 4
0x18000a1cf  jb      loc_18000A380
0x18000a1d5  test    byte ptr [rcx+1Ch], 1
0x18000a1d9  jz      loc_18000A380
0x18000a1df  mov     edx, 28h ; '('
0x18000a1e4  jmp     loc_18000A369
0x18000a1e9  mov     eax, 7FFFFFFEh
0x18000a1ee  lea     r8, [rdi+0A80h]
0x18000a1f5  mov     edx, 125h
0x18000a1fa  test    rax, rax
0x18000a1fd  jz      short loc_18000A21C
0x18000a1ff  movzx   ecx, word ptr [rsi]
0x18000a202  test    cx, cx
0x18000a205  jz      short loc_18000A21C
0x18000a207  mov     [r8], cx
0x18000a20b  add     rsi, 2
0x18000a20f  add     r8, 2
0x18000a213  dec     rax
0x18000a216  sub     rdx, 1
0x18000a21a  jnz     short loc_18000A1FA
0x18000a21c  mov     rax, rdx
0x18000a21f  lea     rcx, [r8-2]
0x18000a223  neg     rax
0x18000a226  sbb     ebx, ebx
0x18000a228  not     ebx
0x18000a22a  and     ebx, 8007007Ah
0x18000a230  test    rdx, rdx
0x18000a233  cmovnz  rcx, r8
0x18000a237  mov     [rcx], bp
0x18000a23a  jnz     short loc_18000A26A
0x18000a23c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a243  cmp     rcx, r12
0x18000a246  jz      loc_18000A380
0x18000a24c  cmp     byte ptr [rcx+19h], 4
0x18000a250  jb      loc_18000A380
0x18000a256  test    byte ptr [rcx+1Ch], 1
0x18000a25a  jz      loc_18000A380
0x18000a260  mov     edx, 29h ; ')'
0x18000a265  jmp     loc_18000A369
0x18000a26a  lea     rcx, [rdi+0A78h]; phAlgorithm
0x18000a271  xor     r9d, r9d; dwFlags
0x18000a274  xor     r8d, r8d; pszImplementation
0x18000a277  lea     rdx, pszAlgId; "RNG"
0x18000a27e  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18000a284  mov     ebx, eax
0x18000a286  test    eax, eax
0x18000a288  jz      short loc_18000A2CC
0x18000a28a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a291  mov     esi, 10000000h
0x18000a296  cmp     rcx, r12
0x18000a299  jz      short loc_18000A2C5
0x18000a29b  cmp     byte ptr [rcx+19h], 4
0x18000a29f  jb      short loc_18000A2C5
0x18000a2a1  test    byte ptr [rcx+1Ch], 1
0x18000a2a5  jz      short loc_18000A2C5
0x18000a2a7  mov     rcx, [rcx+10h]
0x18000a2ab  lea     r8, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000a2b2  or      eax, esi
0x18000a2b4  mov     edx, 2Ah ; '*'
0x18000a2b9  mov     r9, rdi
0x18000a2bc  mov     dword ptr [rsp+68h+var_48], eax
0x18000a2c0  call    WPP_SF_qD
0x18000a2c5  or      ebx, esi
0x18000a2c7  jmp     loc_18000A380
0x18000a2cc  mov     rcx, [rdi+38h]
0x18000a2d0  cmp     rcx, r14
0x18000a2d3  jz      short loc_18000A2F9
0x18000a2d5  test    rcx, rcx
0x18000a2d8  jz      short loc_18000A2E6
0x18000a2da  mov     rax, [rcx]
0x18000a2dd  mov     rax, [rax+10h]
0x18000a2e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2e6  mov     [rdi+38h], r14
0x18000a2ea  mov     rcx, r14
0x18000a2ed  mov     rax, [r14]
0x18000a2f0  mov     rax, [rax+8]
0x18000a2f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a300  cmp     rcx, r12
0x18000a303  jz      short loc_18000A32D
0x18000a305  cmp     byte ptr [rcx+19h], 4
0x18000a309  jb      short loc_18000A32D
0x18000a30b  test    byte ptr [rcx+1Ch], 1
0x18000a30f  jz      short loc_18000A32D
0x18000a311  mov     rcx, [rcx+10h]
0x18000a315  lea     r8, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000a31c  mov     edx, 2Bh ; '+'
0x18000a321  mov     dword ptr [rsp+68h+var_48], ebp
0x18000a325  mov     r9, rdi
0x18000a328  call    WPP_SF_qD
0x18000a32d  xor     eax, eax
0x18000a32f  jmp     short loc_18000A382
0x18000a331  mov     ebx, 800704DFh
0x18000a336  cmp     rcx, r12
0x18000a339  jz      short loc_18000A380
0x18000a33b  cmp     byte ptr [rcx+19h], 4
0x18000a33f  jb      short loc_18000A380
0x18000a341  test    byte ptr [rcx+1Ch], 1
0x18000a345  jz      short loc_18000A380
0x18000a347  mov     edx, 24h ; '$'
0x18000a34c  jmp     short loc_18000A369
0x18000a34e  mov     ebx, 80070057h
0x18000a353  cmp     rcx, r12
0x18000a356  jz      short loc_18000A380
0x18000a358  cmp     byte ptr [rcx+19h], 4
0x18000a35c  jb      short loc_18000A380
0x18000a35e  test    byte ptr [rcx+1Ch], 1
0x18000a362  jz      short loc_18000A380
0x18000a364  mov     edx, 23h ; '#'
0x18000a369  mov     rcx, [rcx+10h]
0x18000a36d  lea     r8, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000a374  mov     r9, rdi
0x18000a377  mov     dword ptr [rsp+68h+var_48], ebx
0x18000a37b  call    WPP_SF_qD
0x18000a380  mov     eax, ebx
0x18000a382  add     rsp, 38h
0x18000a386  pop     r14
0x18000a388  pop     r12
0x18000a38a  pop     rdi
0x18000a38b  pop     rsi
0x18000a38c  pop     rbp
0x18000a38d  pop     rbx
0x18000a38e  retn
```
