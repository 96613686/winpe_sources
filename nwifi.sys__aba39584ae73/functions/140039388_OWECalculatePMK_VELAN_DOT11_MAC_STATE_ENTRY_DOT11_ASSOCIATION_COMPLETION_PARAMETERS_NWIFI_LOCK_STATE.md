# OWECalculatePMK(_VELAN *,DOT11_MAC_STATE_ENTRY *,DOT11_ASSOCIATION_COMPLETION_PARAMETERS *,_NWIFI_LOCK_STATE *)

- ea: `0x140039388`
- end: `0x14003961b`
- name: `?OWECalculatePMK@@YAXPEAU_VELAN@@PEAUDOT11_MAC_STATE_ENTRY@@PEAUDOT11_ASSOCIATION_COMPLETION_PARAMETERS@@PEAU_NWIFI_LOCK_STATE@@@Z`
- size: `659`
- prototype: `void(struct _VELAN *, struct DOT11_MAC_STATE_ENTRY *, struct DOT11_ASSOCIATION_COMPLETION_PARAMETERS *, struct _NWIFI_LOCK_STATE *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140039630`

## callees

- `0x14000d21c`
- `0x140020dc0`
- `0x140039388`
- `0x140039b60`
- `0x14003a554`
- `0x14003a6b8`
- `0x14003a73c`
- `0x140043c60`
- `0x14008f978`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400395a7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400395a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400395b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400395b8`
- `NDIS!NdisAcquireRWLockWrite` at `0x140039489`
- `NDIS!NdisAcquireRWLockWrite` at `0x140039489`
- `NDIS!NdisReleaseRWLock` at `0x140039440`
- `NDIS!NdisReleaseRWLock` at `0x140039440`

## pseudocode

```c
void __fastcall OWECalculatePMK(
        struct _VELAN *a1,
        struct DOT11_MAC_STATE_ENTRY *a2,
        struct DOT11_ASSOCIATION_COMPLETION_PARAMETERS *a3,
        struct _NWIFI_LOCK_STATE *a4)
{
  struct _OWE_CONTEXT *pOWEContext; // r14
  unsigned int *v8; // rsi
  int v9; // eax
  int v10; // edi
  _QWORD *v11; // rbx
  struct OWE_CRYPTO *v12; // r15
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  bool v16; // zf
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rax
  struct OWE_CRYPTO *v20; // [rsp+80h] [rbp+8h] BYREF
  struct DOT11_MAC_STATE_ENTRY *v21; // [rsp+88h] [rbp+10h]

  v21 = a2;
  pOWEContext = a1->pOWEContext;
  v20 = 0;
  v8 = (unsigned int *)((char *)pOWEContext + 144);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 60, WPP_7a6055a1655f3139d52915d863ce14fd_Traceguids);
  v9 = OWEPrepareKeyExchangeData(pOWEContext, a3, &v20);
  v10 = v9;
  if ( v9 >= 0 )
  {
    *(_DWORD *)pOWEContext = 1;
    NdisReleaseRWLock(a1->pRWLock, &a4->lockStateEx);
    v12 = v20;
    v11 = (_QWORD *)((char *)pOWEContext + 256);
    v10 = Dot11CryptDHComputeSharedSecret(
            *((_QWORD *)v20 + 2),
            *((_QWORD *)v20 + 3),
            *v8,
            (char *)pOWEContext + 148,
            (char *)pOWEContext + 252,
            (char *)pOWEContext + 256);
    NdisAcquireRWLockWrite(a1->pRWLock, &a4->lockStateEx, 0);
    if ( v10 >= 0 )
    {
      v16 = *((_DWORD *)pOWEContext + 1) == 0;
      *(_DWORD *)pOWEContext = 0;
      if ( !v16 )
      {
        OWEReset(pOWEContext);
        goto LABEL_21;
      }
      v17 = OWEDerivePMK(
              *((_DWORD *)v12 + 9),
              *((const struct _SYMCRYPT_MAC **)v12 + 5),
              (struct _OWE_CONTEXT *)((char *)pOWEContext + 144));
      v10 = v17;
      if ( v17 >= 0 )
      {
        v17 = OWESendAuthInfoToCache(
                **(unsigned int **)v12,
                &a1->Dot11PmkCache,
                a3->MacAddr,
                *((unsigned int *)pOWEContext + 66),
                (char *)pOWEContext + 268,
                *((_DWORD *)pOWEContext + 92),
                (char *)pOWEContext + 372);
        v10 = v17;
        if ( v17 >= 0 )
        {
          Dot11OnPMKCalculatedByWorker(a1, v21, a4);
          goto LABEL_21;
        }
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_21;
        v14 = 64;
      }
      else
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_21;
        v14 = 63;
      }
      v15 = (unsigned int)v17;
    }
    else
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_21;
      v14 = 62;
      v15 = (unsigned int)v10;
    }
    WPP_SF_d(v13->AttachedDevice, v14, WPP_7a6055a1655f3139d52915d863ce14fd_Traceguids, v15);
    goto LABEL_21;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 61, WPP_7a6055a1655f3139d52915d863ce14fd_Traceguids, (unsigned int)v9);
  v11 = (_QWORD *)((char *)pOWEContext + 256);
LABEL_21:
  if ( *v11 )
  {
    v18 = *v11 - 16LL;
    if ( *(_QWORD *)v18 )
      ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v18, (PVOID)(*v11 - 16LL));
    else
      ExFreePoolWithTag((PVOID)v18, *(_DWORD *)(v18 + 8));
    *v11 = 0;
  }
  v19 = 296;
  do
  {
    *(_BYTE *)v8 = 0;
    v8 = (unsigned int *)((char *)v8 + 1);
    --v19;
  }
  while ( v19 );
  if ( v10 < 0 && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 65, WPP_7a6055a1655f3139d52915d863ce14fd_Traceguids, (unsigned int)v10);
}

```

## disassembly

```asm
0x140039388  mov     rax, rsp
0x14003938b  mov     [rax+18h], rbx
0x14003938f  mov     [rax+10h], rdx
0x140039393  push    rbp
0x140039394  push    rsi
0x140039395  push    rdi
0x140039396  push    r12
0x140039398  push    r13
0x14003939a  push    r14
0x14003939c  push    r15
0x14003939e  sub     rsp, 40h
0x1400393a2  mov     r14, [rcx+2170h]
0x1400393a9  mov     r12, r9
0x1400393ac  mov     r13, r8
0x1400393af  mov     qword ptr [rax+8], 0
0x1400393b7  mov     rbp, rcx
0x1400393ba  lea     rsi, [r14+90h]
0x1400393c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400393c8  lea     r15, WPP_GLOBAL_Control
0x1400393cf  cmp     rcx, r15
0x1400393d2  jz      short loc_1400393E9
0x1400393d4  mov     rcx, [rcx+18h]
0x1400393d8  lea     r8, WPP_7a6055a1655f3139d52915d863ce14fd_Traceguids
0x1400393df  mov     edx, 3Ch ; '<'
0x1400393e4  call    WPP_SF_
0x1400393e9  lea     r8, [rsp+78h+arg_0]; struct OWE_CRYPTO **
0x1400393f1  mov     rdx, r13; struct DOT11_ASSOCIATION_COMPLETION_PARAMETERS *
0x1400393f4  mov     rcx, r14; struct _OWE_CONTEXT *
0x1400393f7  call    ?OWEPrepareKeyExchangeData@@YAJPEAU_OWE_CONTEXT@@PEAUDOT11_ASSOCIATION_COMPLETION_PARAMETERS@@PEAPEAUOWE_CRYPTO@@@Z; OWEPrepareKeyExchangeData(_OWE_CONTEXT *,DOT11_ASSOCIATION_COMPLETION_PARAMETERS *,OWE_CRYPTO * *)
0x1400393fc  mov     edi, eax
0x1400393fe  test    eax, eax
0x140039400  jns     short loc_14003942F
0x140039402  mov     rcx, cs:WPP_GLOBAL_Control
0x140039409  cmp     rcx, r15
0x14003940c  jz      short loc_140039426
0x14003940e  mov     rcx, [rcx+18h]
0x140039412  lea     r8, WPP_7a6055a1655f3139d52915d863ce14fd_Traceguids
0x140039419  mov     edx, 3Dh ; '='
0x14003941e  mov     r9d, eax
0x140039421  call    WPP_SF_d
0x140039426  lea     rbx, [rsi+70h]
0x14003942a  jmp     loc_14003958D
0x14003942f  mov     dword ptr [r14], 1
0x140039436  mov     rdx, r12; LockState
0x140039439  mov     rcx, [rbp+90h]; Lock
0x140039440  call    cs:__imp_NdisReleaseRWLock
0x140039447  nop     dword ptr [rax+rax+00h]
0x14003944c  mov     r15, [rsp+78h+arg_0]
0x140039454  lea     rax, [rsi+6Ch]
0x140039458  mov     r8d, [rsi]
0x14003945b  lea     rbx, [rsi+70h]
0x14003945f  lea     r9, [rsi+4]
0x140039463  mov     [rsp+78h+var_50], rbx
0x140039468  mov     [rsp+78h+var_58], rax
0x14003946d  mov     rdx, [r15+18h]
0x140039471  mov     rcx, [r15+10h]
0x140039475  call    Dot11CryptDHComputeSharedSecret
0x14003947a  mov     rcx, [rbp+90h]; Lock
0x140039481  xor     r8d, r8d; Flags
0x140039484  mov     rdx, r12; LockState
0x140039487  mov     edi, eax
0x140039489  call    cs:__imp_NdisAcquireRWLockWrite
0x140039490  nop     dword ptr [rax+rax+00h]
0x140039495  test    edi, edi
0x140039497  jns     short loc_1400394CD
0x140039499  mov     rcx, cs:WPP_GLOBAL_Control
0x1400394a0  lea     r15, WPP_GLOBAL_Control
0x1400394a7  cmp     rcx, r15
0x1400394aa  jz      loc_14003958D
0x1400394b0  mov     edx, 3Eh ; '>'
0x1400394b5  mov     r9d, edi
0x1400394b8  mov     rcx, [rcx+18h]
0x1400394bc  lea     r8, WPP_7a6055a1655f3139d52915d863ce14fd_Traceguids
0x1400394c3  call    WPP_SF_d
0x1400394c8  jmp     loc_14003958D
0x1400394cd  cmp     dword ptr [r14+4], 0
0x1400394d2  mov     dword ptr [r14], 0
0x1400394d9  jz      short loc_1400394E8
0x1400394db  mov     rcx, r14; struct _OWE_CONTEXT *
0x1400394de  call    ?OWEReset@@YAJPEAU_OWE_CONTEXT@@@Z; OWEReset(_OWE_CONTEXT *)
0x1400394e3  jmp     loc_140039586
0x1400394e8  mov     rdx, [r15+28h]; struct _SYMCRYPT_MAC *
0x1400394ec  mov     r8, rsi; struct KEY_EXCHANGE_DATA *
0x1400394ef  mov     ecx, [r15+24h]; unsigned int
0x1400394f3  call    ?OWEDerivePMK@@YAJKPEBU_SYMCRYPT_MAC@@PEAUKEY_EXCHANGE_DATA@@@Z; OWEDerivePMK(ulong,_SYMCRYPT_MAC const *,KEY_EXCHANGE_DATA *)
0x1400394f8  mov     edi, eax
0x1400394fa  test    eax, eax
0x1400394fc  jns     short loc_14003951B
0x1400394fe  mov     rcx, cs:WPP_GLOBAL_Control
0x140039505  lea     r15, WPP_GLOBAL_Control
0x14003950c  cmp     rcx, r15
0x14003950f  jz      short loc_14003958D
0x140039511  mov     edx, 3Fh ; '?'
0x140039516  mov     r9d, eax
0x140039519  jmp     short loc_1400394B8
0x14003951b  mov     rcx, [r15]
0x14003951e  lea     rax, [rsi+0E4h]
0x140039525  mov     [rsp+78h+var_48], rax
0x14003952a  lea     r9, [rsi+7Ch]
0x14003952e  mov     eax, [rsi+0E0h]
0x140039534  lea     r8, [r13+4]
0x140039538  mov     dword ptr [rsp+78h+var_50], eax
0x14003953c  lea     rdx, [rbp+1FE8h]
0x140039543  mov     ecx, [rcx]
0x140039545  mov     [rsp+78h+var_58], r9
0x14003954a  mov     r9d, [rsi+78h]
0x14003954e  call    ?OWESendAuthInfoToCache@@YAJW4OWE_GROUP@@PEAU_DOT11_PMK_CACHE@@PEAY05EKPEAEK3@Z; OWESendAuthInfoToCache(OWE_GROUP,_DOT11_PMK_CACHE *,uchar (*)[6],ulong,uchar *,ulong,uchar *)
0x140039553  mov     edi, eax
0x140039555  test    eax, eax
0x140039557  jns     short loc_140039573
0x140039559  mov     rcx, cs:WPP_GLOBAL_Control
0x140039560  lea     r15, WPP_GLOBAL_Control
0x140039567  cmp     rcx, r15
0x14003956a  jz      short loc_14003958D
0x14003956c  mov     edx, 40h ; '@'
0x140039571  jmp     short loc_140039516
0x140039573  mov     rdx, [rsp+78h+arg_8]; struct DOT11_MAC_STATE_ENTRY *
0x14003957b  mov     r8, r12; struct _NWIFI_LOCK_STATE *
0x14003957e  mov     rcx, rbp; struct _VELAN *
0x140039581  call    ?Dot11OnPMKCalculatedByWorker@@YAXPEAU_VELAN@@PEAUDOT11_MAC_STATE_ENTRY@@PEAU_NWIFI_LOCK_STATE@@@Z; Dot11OnPMKCalculatedByWorker(_VELAN *,DOT11_MAC_STATE_ENTRY *,_NWIFI_LOCK_STATE *)
0x140039586  lea     r15, WPP_GLOBAL_Control
0x14003958d  mov     rcx, [rbx]
0x140039590  test    rcx, rcx
0x140039593  jz      short loc_1400395CB
0x140039595  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140039599  mov     rax, [rcx]
0x14003959c  test    rax, rax
0x14003959f  jz      short loc_1400395B5
0x1400395a1  mov     rdx, rcx; Entry
0x1400395a4  mov     rcx, rax; Lookaside
0x1400395a7  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400395ae  nop     dword ptr [rax+rax+00h]
0x1400395b3  jmp     short loc_1400395C4
0x1400395b5  mov     edx, [rcx+8]; Tag
0x1400395b8  call    cs:__imp_ExFreePoolWithTag
0x1400395bf  nop     dword ptr [rax+rax+00h]
0x1400395c4  mov     qword ptr [rbx], 0
0x1400395cb  mov     eax, 128h
0x1400395d0  mov     byte ptr [rsi], 0
0x1400395d3  inc     rsi
0x1400395d6  sub     rax, 1
0x1400395da  jnz     short loc_1400395D0
0x1400395dc  test    edi, edi
0x1400395de  jns     short loc_140039602
0x1400395e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400395e7  cmp     rcx, r15
0x1400395ea  jz      short loc_140039602
0x1400395ec  mov     rcx, [rcx+18h]
0x1400395f0  lea     edx, [rax+41h]
0x1400395f3  mov     r9d, edi
0x1400395f6  lea     r8, WPP_7a6055a1655f3139d52915d863ce14fd_Traceguids
0x1400395fd  call    WPP_SF_d
0x140039602  mov     rbx, [rsp+78h+arg_10]
0x14003960a  add     rsp, 40h
0x14003960e  pop     r15
0x140039610  pop     r14
0x140039612  pop     r13
0x140039614  pop     r12
0x140039616  pop     rdi
0x140039617  pop     rsi
0x140039618  pop     rbp
0x140039619  retn
```
