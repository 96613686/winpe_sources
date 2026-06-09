# CscLViewUpdateInfoWorker

- ea: `0x140076458`
- end: `0x140076756`
- name: `CscLViewUpdateInfoWorker`
- size: `766`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140075b10`

## callees

- `0x1400017c0`
- `0x14000dfc0`
- `0x14000e030`
- `0x14001404c`
- `0x1400169d4`
- `0x140018930`
- `0x1400190ec`
- `0x14001aa9c`
- `0x140049fc8`
- `0x140076458`
- `0x14007675c`

## import_xrefs

- `rdbss!RxGetShareRights` at `0x14007660c`
- `rdbss!RxGetShareRights` at `0x14007660c`

## pseudocode

```c
__int64 __fastcall CscLViewUpdateInfoWorker(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, _BYTE *a5, char a6)
{
  __int64 v6; // r12
  __int64 v10; // r15
  char v11; // al
  __int64 v12; // r9
  char v13; // bl
  char v14; // di
  int v15; // ebx
  int v16; // edi
  char v17; // bl
  PDEVICE_OBJECT v18; // rcx
  __int64 v19; // rdx
  struct _DEVICE_OBJECT *v20; // r8
  int v21; // eax
  __int64 v22; // r8
  __int64 v24; // [rsp+40h] [rbp-20h] BYREF
  __int64 v25; // [rsp+48h] [rbp-18h] BYREF
  __int64 v26; // [rsp+50h] [rbp-10h]
  int v27; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v28; // [rsp+A8h] [rbp+48h] BYREF
  __int64 v29; // [rsp+B0h] [rbp+50h]

  v29 = a3;
  v6 = *(_QWORD *)(a1 + 48);
  v24 = 0;
  v26 = *(_QWORD *)(a2 + 48);
  v28 = 0;
  v27 = 0;
  v25 = 0;
  v10 = _InterlockedCompareExchange64((volatile signed __int64 *)(v6 + 40), 0, 0);
  v11 = CscCheckOrAddVNetRootLogicalViewCache(v26, v6, 0);
  v13 = v11;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
  {
    LOBYTE(v12) = v11 != 0 ? 78 : 89;
    WPP_SF_c(WPP_GLOBAL_Control->AttachedDevice, 72, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids, v12);
  }
  v14 = a6;
  if ( !a6 && v13 )
  {
    v15 = 0;
    v16 = 2963;
    goto LABEL_35;
  }
  v17 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 73, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids);
  if ( v14 )
    HIDWORD(v24) |= 0x4000u;
  if ( a5 )
  {
    if ( *a5 )
    {
      HIDWORD(v28) |= 1u;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0 )
        goto LABEL_21;
      v19 = 74;
    }
    else
    {
      LODWORD(v28) = v28 | 1;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0 )
        goto LABEL_21;
      v19 = 75;
    }
    WPP_SF_(v18->AttachedDevice, v19, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids);
LABEL_21:
    v17 = 1;
  }
  v27 = CscConvertSmbCacheModeToStoreCacheMode(a4);
  if ( v27 )
  {
    v21 = CscStoreSetInformationEntry(
            v10,
            (unsigned __int64)&v24 & -(__int64)(v14 != 0),
            (unsigned __int64)&v28 & -(__int64)(v17 != 0),
            (__int64)&v27,
            0,
            0,
            0);
    if ( v21 < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        77,
        WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids,
        (unsigned int)v21);
    }
  }
  else if ( WPP_GLOBAL_Control != v20 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 76, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids, a4);
  }
  if ( (unsigned __int8)RxGetShareRights(a2, &v25) )
  {
    v15 = CscStoreSetExplicitAccessEntry(v10, 1, v29, v25, 1);
    if ( v15 >= 0 )
    {
      v16 = 0;
      CscAcquireLViewLock(a1);
      *(_DWORD *)(*(_QWORD *)(a1 + 48) + 4LL) &= ~0x800u;
      CscReleaseLViewLock(a1);
      LOBYTE(v22) = 1;
      CscCheckOrAddVNetRootLogicalViewCache(v26, v6, v22);
    }
    else
    {
      v16 = 3034;
    }
  }
  else
  {
    v15 = -1073740768;
    v16 = 3042;
  }
LABEL_35:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      78,
      WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids,
      (unsigned int)v15,
      v16);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x140076458  mov     [rsp-38h+arg_18], rbx
0x14007645d  mov     [rsp-38h+arg_10], r8
0x140076462  push    rbp
0x140076463  push    rsi
0x140076464  push    rdi
0x140076465  push    r12
0x140076467  push    r13
0x140076469  push    r14
0x14007646b  push    r15
0x14007646d  mov     rbp, rsp
0x140076470  sub     rsp, 60h
0x140076474  mov     r12, [rcx+30h]
0x140076478  mov     esi, r9d
0x14007647b  mov     r14, rcx
0x14007647e  mov     [rbp+var_20], 0
0x140076486  mov     rcx, [rdx+30h]
0x14007648a  xor     r9d, r9d
0x14007648d  mov     [rbp+var_10], rcx
0x140076491  xor     eax, eax
0x140076493  mov     r13, rdx
0x140076496  mov     [rbp+arg_8], 0
0x14007649e  mov     [rbp+arg_0], 0
0x1400764a5  mov     [rbp+var_18], 0
0x1400764ad  lock cmpxchg [r12+28h], r9
0x1400764b4  xor     r8d, r8d
0x1400764b7  mov     rdx, r12
0x1400764ba  mov     r15, rax
0x1400764bd  call    CscCheckOrAddVNetRootLogicalViewCache
0x1400764c2  mov     bl, al
0x1400764c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400764cb  lea     r8, WPP_GLOBAL_Control
0x1400764d2  cmp     rcx, r8
0x1400764d5  jz      short loc_14007650A
0x1400764d7  mov     edx, [rcx+2Ch]
0x1400764da  test    dl, 40h
0x1400764dd  jz      short loc_14007650A
0x1400764df  mov     rcx, [rcx+18h]
0x1400764e3  lea     r8, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids
0x1400764ea  mov     dl, al
0x1400764ec  neg     dl
0x1400764ee  mov     edx, 48h ; 'H'
0x1400764f3  sbb     r9b, r9b
0x1400764f6  and     r9b, 0F5h
0x1400764fa  add     r9b, 59h ; 'Y'
0x1400764fe  call    WPP_SF_c
0x140076503  lea     r8, WPP_GLOBAL_Control
0x14007650a  mov     dil, [rbp+arg_28]
0x14007650e  test    dil, dil
0x140076511  jnz     short loc_14007652A
0x140076513  test    bl, bl
0x140076515  jz      short loc_14007652A
0x140076517  xor     ebx, ebx
0x140076519  lea     rsi, WPP_GLOBAL_Control
0x140076520  mov     edi, 0B93h
0x140076525  jmp     loc_14007670C
0x14007652a  mov     rcx, cs:WPP_GLOBAL_Control
0x140076531  xor     bl, bl
0x140076533  cmp     rcx, r8
0x140076536  jz      short loc_14007655B
0x140076538  mov     eax, [rcx+2Ch]
0x14007653b  test    al, 40h
0x14007653d  jz      short loc_14007655B
0x14007653f  mov     rcx, [rcx+18h]
0x140076543  lea     r8, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids
0x14007654a  mov     edx, 49h ; 'I'
0x14007654f  call    WPP_SF_
0x140076554  lea     r8, WPP_GLOBAL_Control
0x14007655b  test    dil, dil
0x14007655e  jz      short loc_140076565
0x140076560  bts     dword ptr [rbp+var_20+4], 0Eh
0x140076565  mov     rax, [rbp+arg_20]
0x140076569  test    rax, rax
0x14007656c  jz      short loc_1400765C5
0x14007656e  cmp     [rax], bl
0x140076570  jz      short loc_140076590
0x140076572  or      dword ptr [rbp+arg_8+4], 1
0x140076576  mov     rcx, cs:WPP_GLOBAL_Control
0x14007657d  cmp     rcx, r8
0x140076580  jz      short loc_1400765C3
0x140076582  mov     eax, [rcx+2Ch]
0x140076585  test    al, 40h
0x140076587  jz      short loc_1400765C3
0x140076589  mov     edx, 4Ah ; 'J'
0x14007658e  jmp     short loc_1400765AC
0x140076590  or      dword ptr [rbp+arg_8], 1
0x140076594  mov     rcx, cs:WPP_GLOBAL_Control
0x14007659b  cmp     rcx, r8
0x14007659e  jz      short loc_1400765C3
0x1400765a0  mov     eax, [rcx+2Ch]
0x1400765a3  test    al, 40h
0x1400765a5  jz      short loc_1400765C3
0x1400765a7  mov     edx, 4Bh ; 'K'
0x1400765ac  mov     rcx, [rcx+18h]
0x1400765b0  lea     r8, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids
0x1400765b7  call    WPP_SF_
0x1400765bc  lea     r8, WPP_GLOBAL_Control
0x1400765c3  mov     bl, 1
0x1400765c5  mov     ecx, esi
0x1400765c7  call    CscConvertSmbCacheModeToStoreCacheMode
0x1400765cc  mov     [rbp+arg_0], eax
0x1400765cf  test    eax, eax
0x1400765d1  jnz     short loc_14007664E
0x1400765d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400765da  cmp     rcx, r8
0x1400765dd  jz      short loc_1400765FE
0x1400765df  mov     eax, [rcx+2Ch]
0x1400765e2  test    al, 20h
0x1400765e4  jz      short loc_1400765FE
0x1400765e6  mov     rcx, [rcx+18h]
0x1400765ea  lea     r8, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids
0x1400765f1  mov     edx, 4Ch ; 'L'
0x1400765f6  mov     r9d, esi
0x1400765f9  call    WPP_SF_d
0x1400765fe  lea     rsi, WPP_GLOBAL_Control
0x140076605  lea     rdx, [rbp+var_18]
0x140076609  mov     rcx, r13
0x14007660c  call    cs:__imp_RxGetShareRights
0x140076613  nop     dword ptr [rax+rax+00h]
0x140076618  test    al, al
0x14007661a  jz      loc_140076702
0x140076620  mov     r9d, dword ptr [rbp+var_18]
0x140076624  mov     edx, 1
0x140076629  mov     r8, [rbp+arg_10]
0x14007662d  mov     rcx, r15
0x140076630  mov     byte ptr [rsp+60h+var_40], 1
0x140076635  call    CscStoreSetExplicitAccessEntry
0x14007663a  mov     ebx, eax
0x14007663c  test    eax, eax
0x14007663e  jns     loc_1400766D6
0x140076644  mov     edi, 0BDAh
0x140076649  jmp     loc_14007670C
0x14007664e  neg     bl
0x140076650  mov     [rsp+60h+var_30], 0
0x140076659  lea     rax, [rbp+arg_8]
0x14007665d  mov     [rsp+60h+var_38], 0
0x140076666  sbb     r8, r8
0x140076669  mov     [rsp+60h+var_40], 0
0x140076672  and     r8, rax
0x140076675  lea     r9, [rbp+arg_0]
0x140076679  lea     rax, [rbp+var_20]
0x14007667d  neg     dil
0x140076680  mov     rcx, r15
0x140076683  sbb     rdx, rdx
0x140076686  and     rdx, rax
0x140076689  call    CscStoreSetInformationEntry
0x14007668e  test    eax, eax
0x140076690  jns     loc_1400765FE
0x140076696  mov     rcx, cs:WPP_GLOBAL_Control
0x14007669d  lea     rsi, WPP_GLOBAL_Control
0x1400766a4  cmp     rcx, rsi
0x1400766a7  jz      loc_140076605
0x1400766ad  mov     edx, [rcx+2Ch]
0x1400766b0  test    dl, 20h
0x1400766b3  jz      loc_140076605
0x1400766b9  mov     rcx, [rcx+18h]
0x1400766bd  lea     r8, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids
0x1400766c4  mov     edx, 4Dh ; 'M'
0x1400766c9  mov     r9d, eax
0x1400766cc  call    WPP_SF_d
0x1400766d1  jmp     loc_140076605
0x1400766d6  mov     rcx, r14
0x1400766d9  xor     edi, edi
0x1400766db  call    CscAcquireLViewLock
0x1400766e0  mov     rax, [r14+30h]
0x1400766e4  mov     rcx, r14
0x1400766e7  btr     dword ptr [rax+4], 0Bh
0x1400766ec  call    CscReleaseLViewLock
0x1400766f1  mov     rcx, [rbp+var_10]
0x1400766f5  mov     r8b, 1
0x1400766f8  mov     rdx, r12
0x1400766fb  call    CscCheckOrAddVNetRootLogicalViewCache
0x140076700  jmp     short loc_14007670C
0x140076702  mov     ebx, 0C0000420h
0x140076707  mov     edi, 0BE2h
0x14007670c  mov     rcx, cs:WPP_GLOBAL_Control
0x140076713  cmp     rcx, rsi
0x140076716  jz      short loc_14007673B
0x140076718  mov     eax, [rcx+2Ch]
0x14007671b  test    al, 20h
0x14007671d  jz      short loc_14007673B
0x14007671f  mov     rcx, [rcx+18h]
0x140076723  lea     r8, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids
0x14007672a  mov     edx, 4Eh ; 'N'
0x14007672f  mov     dword ptr [rsp+60h+var_40], edi
0x140076733  mov     r9d, ebx
0x140076736  call    WPP_SF_Dd
0x14007673b  mov     eax, ebx
0x14007673d  mov     rbx, [rsp+60h+arg_18]
0x140076745  add     rsp, 60h
0x140076749  pop     r15
0x14007674b  pop     r14
0x14007674d  pop     r13
0x14007674f  pop     r12
0x140076751  pop     rdi
0x140076752  pop     rsi
0x140076753  pop     rbp
0x140076754  retn
```
