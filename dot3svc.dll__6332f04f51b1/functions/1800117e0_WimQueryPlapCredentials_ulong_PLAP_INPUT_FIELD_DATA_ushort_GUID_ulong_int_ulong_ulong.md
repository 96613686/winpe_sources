# WimQueryPlapCredentials(ulong *,_PLAP_INPUT_FIELD_DATA * *,ushort * *,_GUID *,ulong *,int *,ulong *,ulong *)

- ea: `0x1800117e0`
- end: `0x180011d20`
- name: `?WimQueryPlapCredentials@@YAKPEAKPEAPEAU_PLAP_INPUT_FIELD_DATA@@PEAPEAGPEAU_GUID@@0PEAH00@Z`
- size: `1344`
- prototype: `unsigned int(unsigned int *, struct _PLAP_INPUT_FIELD_DATA **, unsigned __int16 **, struct _GUID *, unsigned int *, int *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x180015d90`

## callees

- `0x1800030fc`
- `0x1800037b4`
- `0x18000a7ec`
- `0x18000a9c0`
- `0x18000c230`
- `0x18000f184`
- `0x18000f294`
- `0x18000f36c`
- `0x180010024`
- `0x1800117e0`
- `0x180025410`
- `0x180030ddc`
- `0x180032d9c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011cd0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011cd0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011cc2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011cc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a8e`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x180011897`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x180011897`
- `ext-ms-win-wlan-scard-l1-1-0!SCardEstablishContext` at `0x180011b43`
- `ext-ms-win-wlan-scard-l1-1-0!SCardEstablishContext` at `0x180011b43`
- `ext-ms-win-wlan-scard-l1-1-0!SCardReleaseContext` at `0x180011b76`
- `ext-ms-win-wlan-scard-l1-1-0!SCardReleaseContext` at `0x180011b76`
- `ext-ms-win-wlan-scard-l1-1-0!SCardListReadersW` at `0x180011b5a`
- `ext-ms-win-wlan-scard-l1-1-0!SCardListReadersW` at `0x180011b5a`

## pseudocode

```c
__int64 __fastcall WimQueryPlapCredentials(
        unsigned int *a1,
        struct _PLAP_INPUT_FIELD_DATA **a2,
        unsigned __int16 **a3,
        struct _GUID *a4,
        unsigned int *a5,
        int *a6,
        unsigned int *a7,
        unsigned int *a8)
{
  SCARDCONTEXT v9; // r13
  unsigned int *v13; // rsi
  int *v14; // rdi
  DWORD PrimaryDomainInformation; // eax
  unsigned int CredentialFields; // ebx
  struct _LIST_ENTRY *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r9
  unsigned int *v20; // r14
  unsigned int Profile; // eax
  struct _LIST_ENTRY *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r9
  DWORD AuthTimeoutValue; // eax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rax
  SIZE_T v29; // rsi
  unsigned __int16 *v30; // rax
  LONG v31; // edi
  __int64 v32; // rcx
  struct _LIST_ENTRY *v33; // rcx
  void *v34; // rdi
  HANDLE ProcessHeap; // rax
  DWORD pcchReaders; // [rsp+20h] [rbp-20h] BYREF
  SCARDCONTEXT phContext; // [rsp+28h] [rbp-18h] BYREF
  PBYTE Buffer; // [rsp+30h] [rbp-10h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-8h] BYREF
  int v42; // [rsp+98h] [rbp+58h] BYREF

  v9 = 0;
  phContext = 0;
  Buffer = 0;
  lpMem = 0;
  v42 = 0;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 108, WPP_41caf6f8117b3ad837214700da2680fc_Traceguids);
  }
  if ( !a4 || !a1 || !a2 || !a3 || (v13 = a5) == 0 || (v14 = (int *)a8) == 0 )
  {
    CredentialFields = 87;
    goto LABEL_82;
  }
  PrimaryDomainInformation = DsRoleGetPrimaryDomainInformation(0, DsRolePrimaryDomainInfoBasic, &Buffer);
  CredentialFields = PrimaryDomainInformation;
  if ( PrimaryDomainInformation )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || !BYTE1(WPP_GLOBAL_Control[1].Blink)
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_17;
    }
    v18 = 109;
    v19 = PrimaryDomainInformation;
LABEL_16:
    WPP_SF_d(v17[1].Flink, v18, WPP_41caf6f8117b3ad837214700da2680fc_Traceguids, v19);
LABEL_17:
    v20 = a1;
    goto LABEL_83;
  }
  if ( (*(_DWORD *)Buffer & 0xFFFFFFFD) == 0 )
  {
    Dot3LogPrelogonSkip(1);
    CredentialFields = 50;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 3u
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 110, WPP_41caf6f8117b3ad837214700da2680fc_Traceguids);
    }
    goto LABEL_17;
  }
  Profile = WimFindProfile(1, (struct _PM_PROFILE **)&phContext, &v42, a4);
  v9 = phContext;
  CredentialFields = Profile;
  if ( Profile || !phContext )
  {
    if ( !v42 )
    {
      Dot3LogPrelogonSkip(2);
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || !BYTE1(WPP_GLOBAL_Control[1].Blink)
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
      {
        goto LABEL_17;
      }
      v18 = 111;
      v19 = CredentialFields;
      goto LABEL_16;
    }
    if ( !phContext )
    {
LABEL_82:
      v20 = a1;
      goto LABEL_83;
    }
  }
  v20 = a1;
  CredentialFields = LanQueryCredentialFields((struct _PM_PROFILE *)phContext, a1, a2);
  if ( !CredentialFields && *a1 || (Dot3LogPrelogonSkip(5), !CredentialFields) )
  {
    AuthTimeoutValue = LanGetAuthTimeoutValue((struct _PM_PROFILE *)v9, v13, a6, a7);
    CredentialFields = AuthTimeoutValue;
    if ( AuthTimeoutValue )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || !BYTE1(WPP_GLOBAL_Control[1].Blink)
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
      {
        goto LABEL_83;
      }
      v23 = 113;
    }
    else
    {
      AuthTimeoutValue = LanIsUserBasedVLan((struct _PM_PROFILE *)v9, v14);
      CredentialFields = AuthTimeoutValue;
      if ( AuthTimeoutValue )
      {
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || !BYTE1(WPP_GLOBAL_Control[1].Blink)
          || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
        {
          goto LABEL_83;
        }
        v23 = 114;
      }
      else
      {
        v28 = -1;
        do
          ++v28;
        while ( *(_WORD *)(v9 + 2 * v28 + 24) );
        v29 = (unsigned int)(2 * v28 + 2);
        v30 = (unsigned __int16 *)Dot3Alloc(v29, v26, v27);
        *a3 = v30;
        if ( v30 )
        {
          memcpy_0(v30, (const void *)(v9 + 24), v29);
          if ( *a1 && *(_DWORD *)*a2 == 4 )
          {
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control[1].Flink, 116, WPP_41caf6f8117b3ad837214700da2680fc_Traceguids);
            }
            pcchReaders = 0;
            phContext = 0;
            if ( !(unsigned __int8)IsSCardEstablishContextPresent() || SCardEstablishContext(0, 0, 0, &phContext) )
              goto LABEL_73;
            v31 = SCardListReadersW(phContext, 0, 0, &pcchReaders);
            if ( !v31 && pcchReaders <= 2 )
              v31 = -2146435049;
            SCardReleaseContext(phContext);
            if ( v31 )
            {
LABEL_73:
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && BYTE1(WPP_GLOBAL_Control[1].Blink)
                && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
              {
                WPP_SF_(WPP_GLOBAL_Control[1].Flink, 117, WPP_41caf6f8117b3ad837214700da2680fc_Traceguids);
              }
              v32 = 6;
            }
            else
            {
              if ( !(unsigned int)SCCardPresent((wchar_t **)&lpMem) )
                goto LABEL_83;
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && BYTE1(WPP_GLOBAL_Control[1].Blink)
                && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
              {
                WPP_SF_(WPP_GLOBAL_Control[1].Flink, 118, WPP_41caf6f8117b3ad837214700da2680fc_Traceguids);
              }
              v32 = 7;
            }
            CredentialFields = 50;
            Dot3LogPrelogonSkip(v32);
            goto LABEL_83;
          }
          goto LABEL_83;
        }
        AuthTimeoutValue = GetLastError();
        CredentialFields = AuthTimeoutValue;
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || !BYTE1(WPP_GLOBAL_Control[1].Blink)
          || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
        {
          goto LABEL_83;
        }
        v23 = 115;
      }
    }
    v24 = AuthTimeoutValue;
    goto LABEL_34;
  }
  v22 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink)
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    v23 = 112;
    v24 = CredentialFields;
LABEL_34:
    WPP_SF_d(v22[1].Flink, v23, WPP_41caf6f8117b3ad837214700da2680fc_Traceguids, v24);
  }
LABEL_83:
  LpFreeProfile((void *)v9);
  if ( CredentialFields || !v20 || *v20 )
  {
    v33 = WPP_GLOBAL_Control;
  }
  else
  {
    v33 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink)
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 119, WPP_41caf6f8117b3ad837214700da2680fc_Traceguids, 0);
      v33 = WPP_GLOBAL_Control;
    }
    CredentialFields = 50;
  }
  v34 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v34);
    v33 = WPP_GLOBAL_Control;
  }
  if ( v33 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v33[1].Blink) >= 4u && (BYTE4(v33[1].Blink) & 1) != 0 )
    WPP_SF_d(v33[1].Flink, 120, WPP_41caf6f8117b3ad837214700da2680fc_Traceguids, CredentialFields);
  return CredentialFields;
}

```

## disassembly

```asm
0x1800117e0  mov     [rsp-38h+arg_8], rbx
0x1800117e5  mov     [rsp-38h+arg_0], rcx
0x1800117ea  push    rbp
0x1800117eb  push    rsi
0x1800117ec  push    rdi
0x1800117ed  push    r12
0x1800117ef  push    r13
0x1800117f1  push    r14
0x1800117f3  push    r15
0x1800117f5  mov     rbp, rsp
0x1800117f8  sub     rsp, 40h
0x1800117fc  xor     eax, eax
0x1800117fe  mov     r14, r9
0x180011801  mov     r13d, eax
0x180011804  mov     [rbp+phContext], rax
0x180011808  mov     [rbp+Buffer], rax
0x18001180c  mov     r12, r8
0x18001180f  mov     [rbp+lpMem], rax
0x180011813  mov     r15, rdx
0x180011816  mov     [rbp+arg_18], eax
0x180011819  mov     rbx, rcx
0x18001181c  mov     rcx, cs:WPP_GLOBAL_Control
0x180011823  lea     rdx, WPP_GLOBAL_Control
0x18001182a  cmp     rcx, rdx
0x18001182d  jz      short loc_18001184E
0x18001182f  cmp     byte ptr [rcx+19h], 4
0x180011833  jb      short loc_18001184E
0x180011835  test    byte ptr [rcx+1Ch], 1
0x180011839  jz      short loc_18001184E
0x18001183b  mov     rcx, [rcx+10h]
0x18001183f  lea     edx, [rax+6Ch]
0x180011842  lea     r8, WPP_41caf6f8117b3ad837214700da2680fc_Traceguids
0x180011849  call    WPP_SF_
0x18001184e  test    r14, r14
0x180011851  jz      loc_180011C4E
0x180011857  test    rbx, rbx
0x18001185a  jz      loc_180011C4E
0x180011860  test    r15, r15
0x180011863  jz      loc_180011C4E
0x180011869  test    r12, r12
0x18001186c  jz      loc_180011C4E
0x180011872  mov     rsi, [rbp+arg_20]
0x180011876  test    rsi, rsi
0x180011879  jz      loc_180011C4E
0x18001187f  mov     rdi, [rbp+arg_38]
0x180011883  test    rdi, rdi
0x180011886  jz      loc_180011C4E
0x18001188c  lea     r8, [rbp+Buffer]; Buffer
0x180011890  mov     edx, 1; InfoLevel
0x180011895  xor     ecx, ecx; lpServer
0x180011897  call    cs:__imp_DsRoleGetPrimaryDomainInformation
0x18001189d  mov     ebx, eax
0x18001189f  test    eax, eax
0x1800118a1  jz      short loc_1800118E3
0x1800118a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800118aa  lea     rsi, WPP_GLOBAL_Control
0x1800118b1  cmp     rcx, rsi
0x1800118b4  jz      short loc_1800118DA
0x1800118b6  cmp     byte ptr [rcx+19h], 1
0x1800118ba  jb      short loc_1800118DA
0x1800118bc  test    byte ptr [rcx+1Ch], 1
0x1800118c0  jz      short loc_1800118DA
0x1800118c2  mov     edx, 6Dh ; 'm'
0x1800118c7  mov     r9d, eax
0x1800118ca  mov     rcx, [rcx+10h]
0x1800118ce  lea     r8, WPP_41caf6f8117b3ad837214700da2680fc_Traceguids
0x1800118d5  call    WPP_SF_d
0x1800118da  mov     r14, [rbp+arg_0]
0x1800118de  jmp     loc_180011C5E
0x1800118e3  mov     rax, [rbp+Buffer]
0x1800118e7  mov     ecx, 1; int
0x1800118ec  test    dword ptr [rax], 0FFFFFFFDh
0x1800118f2  jz      loc_180011C01
0x1800118f8  mov     r9, r14; struct _GUID *
0x1800118fb  lea     r8, [rbp+arg_18]; int *
0x1800118ff  lea     rdx, [rbp+phContext]; struct _PM_PROFILE **
0x180011903  call    ?WimFindProfile@@YAKHPEAPEAU_PM_PROFILE@@PEAHPEAU_GUID@@@Z; WimFindProfile(int,_PM_PROFILE * *,int *,_GUID *)
0x180011908  mov     r13, [rbp+phContext]
0x18001190c  mov     ebx, eax
0x18001190e  xor     eax, eax
0x180011910  test    ebx, ebx
0x180011912  jnz     short loc_180011919
0x180011914  test    r13, r13
0x180011917  jnz     short loc_18001195D
0x180011919  cmp     [rbp+arg_18], eax
0x18001191c  jnz     short loc_180011954
0x18001191e  mov     ecx, 2
0x180011923  call    ?Dot3LogPrelogonSkip@@YAKW4_PRELOGON_SKIP_REASON@@@Z; Dot3LogPrelogonSkip(_PRELOGON_SKIP_REASON)
0x180011928  mov     rcx, cs:WPP_GLOBAL_Control
0x18001192f  lea     rsi, WPP_GLOBAL_Control
0x180011936  cmp     rcx, rsi
0x180011939  jz      short loc_1800118DA
0x18001193b  cmp     byte ptr [rcx+19h], 1
0x18001193f  jb      short loc_1800118DA
0x180011941  test    byte ptr [rcx+1Ch], 1
0x180011945  jz      short loc_1800118DA
0x180011947  mov     edx, 6Fh ; 'o'
0x18001194c  mov     r9d, ebx
0x18001194f  jmp     loc_1800118CA
0x180011954  test    r13, r13
0x180011957  jz      loc_180011C53
0x18001195d  mov     r14, [rbp+arg_0]
0x180011961  mov     r8, r15; struct _PLAP_INPUT_FIELD_DATA **
0x180011964  mov     rdx, r14; unsigned int *
0x180011967  mov     rcx, r13; struct _PM_PROFILE *
0x18001196a  call    ?LanQueryCredentialFields@@YAKPEAU_PM_PROFILE@@PEAKPEAPEAU_PLAP_INPUT_FIELD_DATA@@@Z; LanQueryCredentialFields(_PM_PROFILE *,ulong *,_PLAP_INPUT_FIELD_DATA * *)
0x18001196f  mov     ebx, eax
0x180011971  test    eax, eax
0x180011973  jnz     short loc_18001197A
0x180011975  cmp     [r14], eax
0x180011978  jnz     short loc_1800119D0
0x18001197a  mov     ecx, 5
0x18001197f  call    ?Dot3LogPrelogonSkip@@YAKW4_PRELOGON_SKIP_REASON@@@Z; Dot3LogPrelogonSkip(_PRELOGON_SKIP_REASON)
0x180011984  test    ebx, ebx
0x180011986  jz      short loc_1800119D0
0x180011988  mov     rcx, cs:WPP_GLOBAL_Control
0x18001198f  lea     rsi, WPP_GLOBAL_Control
0x180011996  cmp     rcx, rsi
0x180011999  jz      loc_180011C5E
0x18001199f  cmp     byte ptr [rcx+19h], 1
0x1800119a3  jb      loc_180011C5E
0x1800119a9  test    byte ptr [rcx+1Ch], 1
0x1800119ad  jz      loc_180011C5E
0x1800119b3  mov     edx, 70h ; 'p'
0x1800119b8  mov     r9d, ebx
0x1800119bb  mov     rcx, [rcx+10h]
0x1800119bf  lea     r8, WPP_41caf6f8117b3ad837214700da2680fc_Traceguids
0x1800119c6  call    WPP_SF_d
0x1800119cb  jmp     loc_180011C5E
0x1800119d0  mov     r9, [rbp+arg_30]; unsigned int *
0x1800119d4  mov     rdx, rsi; unsigned int *
0x1800119d7  mov     r8, [rbp+arg_28]; int *
0x1800119db  mov     rcx, r13; struct _PM_PROFILE *
0x1800119de  call    ?LanGetAuthTimeoutValue@@YAKPEAU_PM_PROFILE@@PEAKPEAH1@Z; LanGetAuthTimeoutValue(_PM_PROFILE *,ulong *,int *,ulong *)
0x1800119e3  xor     esi, esi
0x1800119e5  mov     ebx, eax
0x1800119e7  test    eax, eax
0x1800119e9  jz      short loc_180011A20
0x1800119eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800119f2  lea     rsi, WPP_GLOBAL_Control
0x1800119f9  cmp     rcx, rsi
0x1800119fc  jz      loc_180011C5E
0x180011a02  cmp     byte ptr [rcx+19h], 1
0x180011a06  jb      loc_180011C5E
0x180011a0c  test    byte ptr [rcx+1Ch], 1
0x180011a10  jz      loc_180011C5E
0x180011a16  mov     edx, 71h ; 'q'
0x180011a1b  mov     r9d, eax
0x180011a1e  jmp     short loc_1800119BB
0x180011a20  mov     rdx, rdi; int *
0x180011a23  mov     rcx, r13; struct _PM_PROFILE *
0x180011a26  call    ?LanIsUserBasedVLan@@YAKPEAU_PM_PROFILE@@PEAH@Z; LanIsUserBasedVLan(_PM_PROFILE *,int *)
0x180011a2b  mov     ebx, eax
0x180011a2d  test    eax, eax
0x180011a2f  jz      short loc_180011A63
0x180011a31  mov     rcx, cs:WPP_GLOBAL_Control
0x180011a38  lea     rsi, WPP_GLOBAL_Control
0x180011a3f  cmp     rcx, rsi
0x180011a42  jz      loc_180011C5E
0x180011a48  cmp     byte ptr [rcx+19h], 1
0x180011a4c  jb      loc_180011C5E
0x180011a52  test    byte ptr [rcx+1Ch], 1
0x180011a56  jz      loc_180011C5E
0x180011a5c  mov     edx, 72h ; 'r'
0x180011a61  jmp     short loc_180011A1B
0x180011a63  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011a67  inc     rax
0x180011a6a  cmp     [r13+rax*2+18h], si
0x180011a70  jnz     short loc_180011A67
0x180011a72  lea     eax, ds:2[rax*2]
0x180011a79  mov     ecx, eax; dwBytes
0x180011a7b  mov     esi, eax
0x180011a7d  call    ?Dot3Alloc@@YAPEAX_K@Z; Dot3Alloc(unsigned __int64)
0x180011a82  mov     [r12], rax
0x180011a86  xor     r12d, r12d
0x180011a89  test    rax, rax
0x180011a8c  jnz     short loc_180011ACB
0x180011a8e  call    cs:__imp_GetLastError
0x180011a94  mov     ebx, eax
0x180011a96  mov     rcx, cs:WPP_GLOBAL_Control
0x180011a9d  lea     rsi, WPP_GLOBAL_Control
0x180011aa4  cmp     rcx, rsi
0x180011aa7  jz      loc_180011C5E
0x180011aad  cmp     byte ptr [rcx+19h], 1
0x180011ab1  jb      loc_180011C5E
0x180011ab7  test    byte ptr [rcx+1Ch], 1
0x180011abb  jz      loc_180011C5E
0x180011ac1  lea     edx, [r12+73h]
0x180011ac6  jmp     loc_180011A1B
0x180011acb  mov     r8, rsi; Size
0x180011ace  lea     rdx, [r13+18h]; Src
0x180011ad2  mov     rcx, rax; void *
0x180011ad5  call    memcpy_0
0x180011ada  cmp     [r14], r12d
0x180011add  jz      loc_180011C57
0x180011ae3  mov     rax, [r15]
0x180011ae6  cmp     dword ptr [rax], 4
0x180011ae9  jnz     loc_180011C57
0x180011aef  mov     rcx, cs:WPP_GLOBAL_Control
0x180011af6  lea     rsi, WPP_GLOBAL_Control
0x180011afd  cmp     rcx, rsi
0x180011b00  jz      short loc_180011B23
0x180011b02  cmp     byte ptr [rcx+19h], 4
0x180011b06  jb      short loc_180011B23
0x180011b08  test    byte ptr [rcx+1Ch], 1
0x180011b0c  jz      short loc_180011B23
0x180011b0e  mov     rcx, [rcx+10h]
0x180011b12  lea     r8, WPP_41caf6f8117b3ad837214700da2680fc_Traceguids
0x180011b19  mov     edx, 74h ; 't'
0x180011b1e  call    WPP_SF_
0x180011b23  mov     [rbp+pcchReaders], r12d
0x180011b27  mov     [rbp+phContext], r12
0x180011b2b  call    IsSCardEstablishContextPresent
0x180011b30  test    al, al
0x180011b32  jz      loc_180011BC3
0x180011b38  lea     r9, [rbp+phContext]; phContext
0x180011b3c  xor     r8d, r8d; pvReserved2
0x180011b3f  xor     edx, edx; pvReserved1
0x180011b41  xor     ecx, ecx; dwScope
0x180011b43  call    cs:__imp_SCardEstablishContext
0x180011b49  test    eax, eax
0x180011b4b  jnz     short loc_180011BC3
0x180011b4d  mov     rcx, [rbp+phContext]; hContext
0x180011b51  lea     r9, [rbp+pcchReaders]; pcchReaders
0x180011b55  xor     r8d, r8d; mszReaders
0x180011b58  xor     edx, edx; mszGroups
0x180011b5a  call    cs:__imp_SCardListReadersW
0x180011b60  mov     edi, eax
0x180011b62  test    eax, eax
0x180011b64  jnz     short loc_180011B72
0x180011b66  cmp     [rbp+pcchReaders], 2
0x180011b6a  mov     eax, 80100017h
0x180011b6f  cmovbe  edi, eax
0x180011b72  mov     rcx, [rbp+phContext]; hContext
0x180011b76  call    cs:__imp_SCardReleaseContext
0x180011b7c  test    edi, edi
0x180011b7e  jnz     short loc_180011BC3
0x180011b80  lea     rcx, [rbp+lpMem]
0x180011b84  call    SCCardPresent
0x180011b89  test    eax, eax
0x180011b8b  jz      loc_180011C5E
0x180011b91  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b98  cmp     rcx, rsi
0x180011b9b  jz      short loc_180011BBC
0x180011b9d  cmp     byte ptr [rcx+19h], 1
0x180011ba1  jb      short loc_180011BBC
0x180011ba3  test    byte ptr [rcx+1Ch], 1
0x180011ba7  jz      short loc_180011BBC
0x180011ba9  mov     rcx, [rcx+10h]
0x180011bad  lea     edx, [rdi+76h]
0x180011bb0  lea     r8, WPP_41caf6f8117b3ad837214700da2680fc_Traceguids
0x180011bb7  call    WPP_SF_
0x180011bbc  mov     ecx, 7
0x180011bc1  jmp     short loc_180011BF5
0x180011bc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180011bca  cmp     rcx, rsi
0x180011bcd  jz      short loc_180011BF0
0x180011bcf  cmp     byte ptr [rcx+19h], 1
0x180011bd3  jb      short loc_180011BF0
0x180011bd5  test    byte ptr [rcx+1Ch], 1
0x180011bd9  jz      short loc_180011BF0
0x180011bdb  mov     rcx, [rcx+10h]
0x180011bdf  lea     r8, WPP_41caf6f8117b3ad837214700da2680fc_Traceguids
0x180011be6  mov     edx, 75h ; 'u'
0x180011beb  call    WPP_SF_
0x180011bf0  mov     ecx, 6
0x180011bf5  mov     ebx, 32h ; '2'
0x180011bfa  call    ?Dot3LogPrelogonSkip@@YAKW4_PRELOGON_SKIP_REASON@@@Z; Dot3LogPrelogonSkip(_PRELOGON_SKIP_REASON)
0x180011bff  jmp     short loc_180011C5E
0x180011c01  call    ?Dot3LogPrelogonSkip@@YAKW4_PRELOGON_SKIP_REASON@@@Z; Dot3LogPrelogonSkip(_PRELOGON_SKIP_REASON)
0x180011c06  mov     ebx, 32h ; '2'
0x180011c0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180011c12  lea     rsi, WPP_GLOBAL_Control
0x180011c19  cmp     rcx, rsi
0x180011c1c  jz      loc_1800118DA
0x180011c22  cmp     byte ptr [rcx+19h], 3
0x180011c26  jb      loc_1800118DA
0x180011c2c  test    byte ptr [rcx+1Ch], 1
0x180011c30  jz      loc_1800118DA
0x180011c36  mov     rcx, [rcx+10h]
0x180011c3a  lea     edx, [rbx+3Ch]
0x180011c3d  lea     r8, WPP_41caf6f8117b3ad837214700da2680fc_Traceguids
0x180011c44  call    WPP_SF_
0x180011c49  jmp     loc_1800118DA
0x180011c4e  mov     ebx, 57h ; 'W'
0x180011c53  mov     r14, [rbp+arg_0]
0x180011c57  lea     rsi, WPP_GLOBAL_Control
0x180011c5e  mov     rcx, r13; lpMem
0x180011c61  call    LpFreeProfile
0x180011c66  xor     eax, eax
0x180011c68  test    ebx, ebx
0x180011c6a  jnz     short loc_180011CB2
0x180011c6c  test    r14, r14
0x180011c6f  jz      short loc_180011CB2
0x180011c71  cmp     [r14], eax
0x180011c74  jnz     short loc_180011CB2
0x180011c76  mov     rcx, cs:WPP_GLOBAL_Control
0x180011c7d  cmp     rcx, rsi
0x180011c80  jz      short loc_180011CAB
0x180011c82  cmp     byte ptr [rcx+19h], 1
  ... truncated ...
```
