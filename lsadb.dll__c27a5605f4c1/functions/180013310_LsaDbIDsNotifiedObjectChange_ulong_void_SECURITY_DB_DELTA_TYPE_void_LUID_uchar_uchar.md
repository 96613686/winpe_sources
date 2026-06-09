# LsaDbIDsNotifiedObjectChange(ulong,void *,_SECURITY_DB_DELTA_TYPE,void *,_LUID,uchar,uchar)

- ea: `0x180013310`
- end: `0x18001361a`
- name: `?LsaDbIDsNotifiedObjectChange@@YAJKPEAXW4_SECURITY_DB_DELTA_TYPE@@0U_LUID@@EE@Z`
- size: `778`
- prototype: `int __high(unsigned int, void *, enum _SECURITY_DB_DELTA_TYPE, void *, struct _LUID, unsigned __int8, unsigned __int8)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000c140`
- `0x18000fd18`
- `0x18000fd40`
- `0x18000fd80`
- `0x180010ec8`
- `0x180013310`
- `0x18001512c`
- `0x1800152e8`
- `0x18003ad30`

## import_xrefs

- `LSASRV!LsapDbExpAcquireWriteLockTrustedDomainList` at `0x18001348c`
- `LSASRV!LsapDbExpAcquireWriteLockTrustedDomainList` at `0x18001348c`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x1800134bf`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x1800134bf`
- `LSASRV!LsapDbExpMakeCacheInvalid` at `0x1800134b9`
- `LSASRV!LsapDbExpMakeCacheInvalid` at `0x1800134b9`
- `LSASRV!LsapAllocateLsaHeap` at `0x180013400`
- `LSASRV!LsapAllocateLsaHeap` at `0x180013525`
- `LSASRV!LsapAllocateLsaHeap` at `0x180013400`
- `LSASRV!LsapAllocateLsaHeap` at `0x180013525`
- `LSASRV!LsapFreeLsaHeap` at `0x1800135fc`
- `LSASRV!LsapFreeLsaHeap` at `0x180013606`
- `LSASRV!LsapFreeLsaHeap` at `0x18001360f`
- `LSASRV!LsapFreeLsaHeap` at `0x1800135fc`
- `LSASRV!LsapFreeLsaHeap` at `0x180013606`
- `LSASRV!LsapFreeLsaHeap` at `0x18001360f`
- `ntdll!RtlLengthSid` at `0x18001351d`
- `ntdll!RtlLengthSid` at `0x180013540`
- `ntdll!RtlLengthSid` at `0x18001351d`
- `ntdll!RtlLengthSid` at `0x180013540`
- `ntdll!RtlValidSid` at `0x180013510`
- `ntdll!RtlValidSid` at `0x180013510`

## pseudocode

```c
__int64 __fastcall LsaDbIDsNotifiedObjectChange(
        int a1,
        struct _DSNAME *a2,
        int a3,
        void *a4,
        __int64 a5,
        char a6,
        unsigned __int8 a7)
{
  int v8; // r11d
  _QWORD *v11; // rcx
  unsigned __int64 v12; // rdi
  char v14; // r12
  __int64 LsaHeap; // rax
  __int64 v16; // rsi
  int v17; // edi
  void *v18; // rcx
  unsigned int v19; // r15d
  unsigned int v20; // eax
  int v21; // ebx
  __int64 v22; // rcx
  ULONG v23; // eax
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r8
  ULONG v27; // eax
  unsigned int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // rdx
  __int64 v32; // r8

  v8 = a3;
  v11 = WPP_GLOBAL_Control;
  v12 = (unsigned __int64)a2 + 56;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_DSDDDdd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v12 & ((unsigned __int128)-(__int128)(unsigned __int64)a2 >> 64),
      a7,
      a1,
      v12 & ((unsigned __int128)-(__int128)(unsigned __int64)a2 >> 64),
      a3,
      SBYTE4(a5),
      a5,
      a6,
      a7);
    v11 = WPP_GLOBAL_Control;
    v8 = a3;
  }
  if ( a1 == 1507375 )
  {
    if ( v8 != 2 )
    {
      if ( (*((_BYTE *)v11 + 28) & 4) != 0 )
        WPP_SF_S(v11[2], 26, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids, v12 & -(__int64)(a2 != 0));
      return 0;
    }
    goto LABEL_10;
  }
  if ( a1 != 655394 && a1 != 196619 )
  {
LABEL_10:
    v14 = 1;
    goto LABEL_12;
  }
  v14 = 0;
LABEL_12:
  LsaHeap = LsapAllocateLsaHeap(56);
  v16 = LsaHeap;
  if ( !LsaHeap )
  {
    v17 = -1073741670;
    v18 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids);
    v19 = a3;
    goto LABEL_16;
  }
  *(_OWORD *)LsaHeap = 0;
  *(_OWORD *)(LsaHeap + 16) = 0;
  *(_OWORD *)(LsaHeap + 32) = 0;
  *(_QWORD *)(LsaHeap + 48) = 0;
  if ( !RtlValidSid(a4) )
    goto LABEL_37;
  v23 = RtlLengthSid(a4);
  v24 = LsapAllocateLsaHeap(v23);
  *(_QWORD *)(v16 + 24) = v24;
  if ( v24 )
  {
    v17 = 0;
    v27 = RtlLengthSid(a4);
    memcpy_0(*(void **)(v16 + 24), a4, v27);
  }
  else
  {
    v17 = -1073741670;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      28,
      &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids,
      (unsigned int)v17);
  if ( v17 < 0 )
  {
    v19 = a3;
  }
  else
  {
LABEL_37:
    v28 = LsaDbpDsCopyDsNameLsa((struct _DSNAME **)(v16 + 32), a2);
    v17 = v28;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids, v28);
    v19 = a3;
    if ( v17 >= 0 )
    {
      *(_BYTE *)(v16 + 48) = a6;
      *(_BYTE *)(v16 + 49) = a7;
      *(_DWORD *)(v16 + 40) = a1;
      *(_DWORD *)(v16 + 44) = a3;
      *(_QWORD *)(v16 + 16) = a5;
      if ( (unsigned int)LsaDbpDsQueueFixupRequest((struct _LSAP_DSFU_NOTIFICATION_NODE *)v16) )
      {
        v14 = 1;
        goto LABEL_16;
      }
      v17 = -1073741670;
    }
  }
  LsapFreeLsaHeap(*(_QWORD *)(v16 + 24), v25, v26);
  LsapFreeLsaHeap(*(_QWORD *)(v16 + 32), v29, v30);
  LsapFreeLsaHeap(v16, v31, v32);
LABEL_16:
  if ( !a6 && a1 == dword_180047D04 )
  {
    v20 = LsaDbpNotifyNetlogonOfTrustChange(0, v19);
    v21 = v20;
    v18 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids, v20);
    if ( v17 >= 0 )
      v17 = v21;
  }
  if ( !v14 && (int)LsapDbExpAcquireWriteLockTrustedDomainList(v18) >= 0 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids);
    LsapDbExpMakeCacheInvalid(2);
    LsapDbExpReleaseLockTrustedDomainList(v22);
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      32,
      &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids,
      (unsigned int)v17);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180013310  mov     [rsp+arg_10], r8d
0x180013315  push    rbx
0x180013316  push    rbp
0x180013317  push    rsi
0x180013318  push    rdi
0x180013319  push    r12
0x18001331b  push    r13
0x18001331d  push    r14
0x18001331f  push    r15
0x180013321  sub     rsp, 58h
0x180013325  mov     r13, r9
0x180013328  mov     r11d, r8d
0x18001332b  mov     r15, rdx
0x18001332e  mov     r14d, ecx
0x180013331  mov     rcx, cs:WPP_GLOBAL_Control
0x180013338  lea     rdi, [rdx+38h]
0x18001333c  mov     rbx, [rsp+98h+arg_20]
0x180013344  test    byte ptr [rcx+1Ch], 4
0x180013348  jz      short loc_1800133A7
0x18001334a  movzx   r9d, [rsp+98h+arg_28]
0x180013353  mov     rax, rdx
0x180013356  movzx   r8d, [rsp+98h+arg_30]
0x18001335f  mov     r10, rbx
0x180013362  mov     rcx, [rcx+10h]
0x180013366  mov     [rsp+98h+var_50], r8d
0x18001336b  mov     [rsp+98h+var_58], r9d
0x180013370  mov     r9d, r14d
0x180013373  shr     r10, 20h
0x180013377  mov     [rsp+98h+var_60], ebx
0x18001337b  neg     rax
0x18001337e  mov     [rsp+98h+var_68], r10d
0x180013383  sbb     rdx, rdx
0x180013386  mov     [rsp+98h+var_70], r11d
0x18001338b  and     rdx, rdi
0x18001338e  mov     [rsp+98h+var_78], rdx
0x180013393  call    WPP_SF_DSDDDdd
0x180013398  mov     rcx, cs:WPP_GLOBAL_Control
0x18001339f  mov     r11d, [rsp+98h+arg_10]
0x1800133a7  cmp     r14d, 17002Fh
0x1800133ae  jnz     short loc_1800133E1
0x1800133b0  cmp     r11d, 2
0x1800133b4  jz      short loc_1800133F3
0x1800133b6  test    byte ptr [rcx+1Ch], 4
0x1800133ba  jz      short loc_1800133DA
0x1800133bc  mov     rcx, [rcx+10h]
0x1800133c0  lea     r8, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x1800133c7  neg     r15
0x1800133ca  mov     edx, 1Ah
0x1800133cf  sbb     r9, r9
0x1800133d2  and     r9, rdi
0x1800133d5  call    WPP_SF_S
0x1800133da  xor     eax, eax
0x1800133dc  jmp     loc_1800134E8
0x1800133e1  cmp     r14d, 0A0022h
0x1800133e8  jz      short loc_1800133F8
0x1800133ea  cmp     r14d, 3000Bh
0x1800133f1  jz      short loc_1800133F8
0x1800133f3  mov     r12b, 1
0x1800133f6  jmp     short loc_1800133FB
0x1800133f8  xor     r12b, r12b
0x1800133fb  mov     ecx, 38h ; '8'
0x180013400  call    cs:__imp_LsapAllocateLsaHeap
0x180013406  lea     rbp, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x18001340d  mov     rsi, rax
0x180013410  test    rax, rax
0x180013413  jnz     loc_1800134F9
0x180013419  mov     edi, 0C000009Ah
0x18001341e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013425  test    byte ptr [rcx+1Ch], 4
0x180013429  jz      short loc_18001343A
0x18001342b  mov     rcx, [rcx+10h]
0x18001342f  lea     edx, [rax+1Bh]
0x180013432  mov     r8, rbp
0x180013435  call    WPP_SF_
0x18001343a  mov     r15d, [rsp+98h+arg_10]
0x180013442  cmp     [rsp+98h+arg_28], 0
0x18001344a  jnz     short loc_180013487
0x18001344c  cmp     r14d, cs:dword_180047D04
0x180013453  jnz     short loc_180013487
0x180013455  mov     edx, r15d
0x180013458  xor     ecx, ecx
0x18001345a  call    ?LsaDbpNotifyNetlogonOfTrustChange@@YAJPEAXW4_SECURITY_DB_DELTA_TYPE@@@Z; LsaDbpNotifyNetlogonOfTrustChange(void *,_SECURITY_DB_DELTA_TYPE)
0x18001345f  mov     ebx, eax
0x180013461  mov     rcx, cs:WPP_GLOBAL_Control
0x180013468  test    byte ptr [rcx+1Ch], 4
0x18001346c  jz      short loc_180013482
0x18001346e  mov     rcx, [rcx+10h]
0x180013472  mov     edx, 1Eh
0x180013477  mov     r9d, eax
0x18001347a  mov     r8, rbp
0x18001347d  call    WPP_SF_d
0x180013482  test    edi, edi
0x180013484  cmovns  edi, ebx
0x180013487  test    r12b, r12b
0x18001348a  jnz     short loc_1800134C5
0x18001348c  call    cs:__imp_LsapDbExpAcquireWriteLockTrustedDomainList
0x180013492  test    eax, eax
0x180013494  js      short loc_1800134C5
0x180013496  mov     rcx, cs:WPP_GLOBAL_Control
0x18001349d  test    byte ptr [rcx+1Ch], 4
0x1800134a1  jz      short loc_1800134B4
0x1800134a3  mov     rcx, [rcx+10h]
0x1800134a7  mov     edx, 1Fh
0x1800134ac  mov     r8, rbp
0x1800134af  call    WPP_SF_
0x1800134b4  mov     ecx, 2
0x1800134b9  call    cs:__imp_LsapDbExpMakeCacheInvalid
0x1800134bf  call    cs:__imp_LsapDbExpReleaseLockTrustedDomainList
0x1800134c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800134cc  test    byte ptr [rcx+1Ch], 4
0x1800134d0  jz      short loc_1800134E6
0x1800134d2  mov     rcx, [rcx+10h]
0x1800134d6  mov     edx, 20h ; ' '
0x1800134db  mov     r9d, edi
0x1800134de  mov     r8, rbp
0x1800134e1  call    WPP_SF_d
0x1800134e6  mov     eax, edi
0x1800134e8  add     rsp, 58h
0x1800134ec  pop     r15
0x1800134ee  pop     r14
0x1800134f0  pop     r13
0x1800134f2  pop     r12
0x1800134f4  pop     rdi
0x1800134f5  pop     rsi
0x1800134f6  pop     rbp
0x1800134f7  pop     rbx
0x1800134f8  retn
0x1800134f9  xorps   xmm0, xmm0
0x1800134fc  xor     eax, eax
0x1800134fe  movups  xmmword ptr [rsi], xmm0
0x180013501  mov     rcx, r13; Sid
0x180013504  movups  xmmword ptr [rsi+10h], xmm0
0x180013508  movups  xmmword ptr [rsi+20h], xmm0
0x18001350c  mov     [rsi+30h], rax
0x180013510  call    cs:__imp_RtlValidSid
0x180013516  test    al, al
0x180013518  jz      short loc_18001357A
0x18001351a  mov     rcx, r13; Sid
0x18001351d  call    cs:__imp_RtlLengthSid
0x180013523  mov     ecx, eax
0x180013525  call    cs:__imp_LsapAllocateLsaHeap
0x18001352b  mov     [rsi+18h], rax
0x18001352f  test    rax, rax
0x180013532  jnz     short loc_18001353B
0x180013534  mov     edi, 0C000009Ah
0x180013539  jmp     short loc_180013555
0x18001353b  mov     rcx, r13; Sid
0x18001353e  xor     edi, edi
0x180013540  call    cs:__imp_RtlLengthSid
0x180013546  mov     rcx, [rsi+18h]; void *
0x18001354a  mov     rdx, r13; Src
0x18001354d  mov     r8d, eax; Size
0x180013550  call    memcpy_0
0x180013555  mov     rcx, cs:WPP_GLOBAL_Control
0x18001355c  test    byte ptr [rcx+1Ch], 4
0x180013560  jz      short loc_180013576
0x180013562  mov     rcx, [rcx+10h]
0x180013566  mov     edx, 1Ch
0x18001356b  mov     r9d, edi
0x18001356e  mov     r8, rbp
0x180013571  call    WPP_SF_d
0x180013576  test    edi, edi
0x180013578  js      short loc_1800135F0
0x18001357a  lea     rcx, [rsi+20h]; struct _DSNAME **
0x18001357e  mov     rdx, r15; struct _DSNAME *
0x180013581  call    ?LsaDbpDsCopyDsNameLsa@@YAJPEAPEAU_DSNAME@@PEAU1@@Z; LsaDbpDsCopyDsNameLsa(_DSNAME * *,_DSNAME *)
0x180013586  mov     edi, eax
0x180013588  mov     rcx, cs:WPP_GLOBAL_Control
0x18001358f  test    byte ptr [rcx+1Ch], 4
0x180013593  jz      short loc_1800135A9
0x180013595  mov     rcx, [rcx+10h]
0x180013599  mov     edx, 1Dh
0x18001359e  mov     r9d, eax
0x1800135a1  mov     r8, rbp
0x1800135a4  call    WPP_SF_d
0x1800135a9  mov     r15d, [rsp+98h+arg_10]
0x1800135b1  test    edi, edi
0x1800135b3  js      short loc_1800135F8
0x1800135b5  mov     al, [rsp+98h+arg_28]
0x1800135bc  mov     rcx, rsi; struct _LSAP_DSFU_NOTIFICATION_NODE *
0x1800135bf  mov     [rsi+30h], al
0x1800135c2  mov     al, [rsp+98h+arg_30]
0x1800135c9  mov     [rsi+31h], al
0x1800135cc  mov     [rsi+28h], r14d
0x1800135d0  mov     [rsi+2Ch], r15d
0x1800135d4  mov     [rsi+10h], rbx
0x1800135d8  call    ?LsaDbpDsQueueFixupRequest@@YAHPEAU_LSAP_DSFU_NOTIFICATION_NODE@@@Z; LsaDbpDsQueueFixupRequest(_LSAP_DSFU_NOTIFICATION_NODE *)
0x1800135dd  test    eax, eax
0x1800135df  jz      short loc_1800135E9
0x1800135e1  mov     r12b, 1
0x1800135e4  jmp     loc_180013442
0x1800135e9  mov     edi, 0C000009Ah
0x1800135ee  jmp     short loc_1800135F8
0x1800135f0  mov     r15d, [rsp+98h+arg_10]
0x1800135f8  mov     rcx, [rsi+18h]
0x1800135fc  call    cs:__imp_LsapFreeLsaHeap
0x180013602  mov     rcx, [rsi+20h]
0x180013606  call    cs:__imp_LsapFreeLsaHeap
0x18001360c  mov     rcx, rsi
0x18001360f  call    cs:__imp_LsapFreeLsaHeap
0x180013615  jmp     loc_180013442
```
