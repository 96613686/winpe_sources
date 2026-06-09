# OWECalculatePMK(_VELAN *,DOT11_MAC_STATE_ENTRY *,DOT11_ASSOCIATION_COMPLETION_PARAMETERS *,_NWIFI_LOCK_STATE *)

- ea: `0x140039168`
- end: `0x1400393fb`
- name: `?OWECalculatePMK@@YAXPEAU_VELAN@@PEAUDOT11_MAC_STATE_ENTRY@@PEAUDOT11_ASSOCIATION_COMPLETION_PARAMETERS@@PEAU_NWIFI_LOCK_STATE@@@Z`
- size: `659`
- prototype: `void(struct _VELAN *, struct DOT11_MAC_STATE_ENTRY *, struct DOT11_ASSOCIATION_COMPLETION_PARAMETERS *, struct _NWIFI_LOCK_STATE *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140039410`

## callees

- `0x14000d22c`
- `0x140020dc0`
- `0x140039168`
- `0x140039940`
- `0x14003a334`
- `0x14003a498`
- `0x14003a51c`
- `0x1400430e0`
- `0x14008e198`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140039387`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140039387`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039398`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039398`
- `NDIS!NdisAcquireRWLockWrite` at `0x140039269`
- `NDIS!NdisAcquireRWLockWrite` at `0x140039269`
- `NDIS!NdisReleaseRWLock` at `0x140039220`
- `NDIS!NdisReleaseRWLock` at `0x140039220`

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
0x140039168  mov     rax, rsp
0x14003916b  mov     [rax+18h], rbx
0x14003916f  mov     [rax+10h], rdx
0x140039173  push    rbp
0x140039174  push    rsi
0x140039175  push    rdi
0x140039176  push    r12
0x140039178  push    r13
0x14003917a  push    r14
0x14003917c  push    r15
0x14003917e  sub     rsp, 40h
0x140039182  mov     r14, [rcx+2170h]
0x140039189  mov     r12, r9
0x14003918c  mov     r13, r8
0x14003918f  mov     qword ptr [rax+8], 0
0x140039197  mov     rbp, rcx
0x14003919a  lea     rsi, [r14+90h]
0x1400391a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400391a8  lea     r15, WPP_GLOBAL_Control
0x1400391af  cmp     rcx, r15
0x1400391b2  jz      short loc_1400391C9
0x1400391b4  mov     rcx, [rcx+18h]
0x1400391b8  lea     r8, WPP_7a6055a1655f3139d52915d863ce14fd_Traceguids
0x1400391bf  mov     edx, 3Ch ; '<'
0x1400391c4  call    WPP_SF_
0x1400391c9  lea     r8, [rsp+78h+arg_0]; struct OWE_CRYPTO **
0x1400391d1  mov     rdx, r13; struct DOT11_ASSOCIATION_COMPLETION_PARAMETERS *
0x1400391d4  mov     rcx, r14; struct _OWE_CONTEXT *
0x1400391d7  call    ?OWEPrepareKeyExchangeData@@YAJPEAU_OWE_CONTEXT@@PEAUDOT11_ASSOCIATION_COMPLETION_PARAMETERS@@PEAPEAUOWE_CRYPTO@@@Z; OWEPrepareKeyExchangeData(_OWE_CONTEXT *,DOT11_ASSOCIATION_COMPLETION_PARAMETERS *,OWE_CRYPTO * *)
0x1400391dc  mov     edi, eax
0x1400391de  test    eax, eax
0x1400391e0  jns     short loc_14003920F
0x1400391e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400391e9  cmp     rcx, r15
0x1400391ec  jz      short loc_140039206
0x1400391ee  mov     rcx, [rcx+18h]
0x1400391f2  lea     r8, WPP_7a6055a1655f3139d52915d863ce14fd_Traceguids
0x1400391f9  mov     edx, 3Dh ; '='
0x1400391fe  mov     r9d, eax
0x140039201  call    WPP_SF_d
0x140039206  lea     rbx, [rsi+70h]
0x14003920a  jmp     loc_14003936D
0x14003920f  mov     dword ptr [r14], 1
0x140039216  mov     rdx, r12; LockState
0x140039219  mov     rcx, [rbp+90h]; Lock
0x140039220  call    cs:__imp_NdisReleaseRWLock
0x140039227  nop     dword ptr [rax+rax+00h]
0x14003922c  mov     r15, [rsp+78h+arg_0]
0x140039234  lea     rax, [rsi+6Ch]
0x140039238  mov     r8d, [rsi]
0x14003923b  lea     rbx, [rsi+70h]
0x14003923f  lea     r9, [rsi+4]
0x140039243  mov     [rsp+78h+var_50], rbx
0x140039248  mov     [rsp+78h+var_58], rax
0x14003924d  mov     rdx, [r15+18h]
0x140039251  mov     rcx, [r15+10h]
0x140039255  call    Dot11CryptDHComputeSharedSecret
0x14003925a  mov     rcx, [rbp+90h]; Lock
0x140039261  xor     r8d, r8d; Flags
0x140039264  mov     rdx, r12; LockState
0x140039267  mov     edi, eax
0x140039269  call    cs:__imp_NdisAcquireRWLockWrite
0x140039270  nop     dword ptr [rax+rax+00h]
0x140039275  test    edi, edi
0x140039277  jns     short loc_1400392AD
0x140039279  mov     rcx, cs:WPP_GLOBAL_Control
0x140039280  lea     r15, WPP_GLOBAL_Control
0x140039287  cmp     rcx, r15
0x14003928a  jz      loc_14003936D
0x140039290  mov     edx, 3Eh ; '>'
0x140039295  mov     r9d, edi
0x140039298  mov     rcx, [rcx+18h]
0x14003929c  lea     r8, WPP_7a6055a1655f3139d52915d863ce14fd_Traceguids
0x1400392a3  call    WPP_SF_d
0x1400392a8  jmp     loc_14003936D
0x1400392ad  cmp     dword ptr [r14+4], 0
0x1400392b2  mov     dword ptr [r14], 0
0x1400392b9  jz      short loc_1400392C8
0x1400392bb  mov     rcx, r14; struct _OWE_CONTEXT *
0x1400392be  call    ?OWEReset@@YAJPEAU_OWE_CONTEXT@@@Z; OWEReset(_OWE_CONTEXT *)
0x1400392c3  jmp     loc_140039366
0x1400392c8  mov     rdx, [r15+28h]; struct _SYMCRYPT_MAC *
0x1400392cc  mov     r8, rsi; struct KEY_EXCHANGE_DATA *
0x1400392cf  mov     ecx, [r15+24h]; unsigned int
0x1400392d3  call    ?OWEDerivePMK@@YAJKPEBU_SYMCRYPT_MAC@@PEAUKEY_EXCHANGE_DATA@@@Z; OWEDerivePMK(ulong,_SYMCRYPT_MAC const *,KEY_EXCHANGE_DATA *)
0x1400392d8  mov     edi, eax
0x1400392da  test    eax, eax
0x1400392dc  jns     short loc_1400392FB
0x1400392de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400392e5  lea     r15, WPP_GLOBAL_Control
0x1400392ec  cmp     rcx, r15
0x1400392ef  jz      short loc_14003936D
0x1400392f1  mov     edx, 3Fh ; '?'
0x1400392f6  mov     r9d, eax
0x1400392f9  jmp     short loc_140039298
0x1400392fb  mov     rcx, [r15]
0x1400392fe  lea     rax, [rsi+0E4h]
0x140039305  mov     [rsp+78h+var_48], rax
0x14003930a  lea     r9, [rsi+7Ch]
0x14003930e  mov     eax, [rsi+0E0h]
0x140039314  lea     r8, [r13+4]
0x140039318  mov     dword ptr [rsp+78h+var_50], eax
0x14003931c  lea     rdx, [rbp+1FE8h]
0x140039323  mov     ecx, [rcx]
0x140039325  mov     [rsp+78h+var_58], r9
0x14003932a  mov     r9d, [rsi+78h]
0x14003932e  call    ?OWESendAuthInfoToCache@@YAJW4OWE_GROUP@@PEAU_DOT11_PMK_CACHE@@PEAY05EKPEAEK3@Z; OWESendAuthInfoToCache(OWE_GROUP,_DOT11_PMK_CACHE *,uchar (*)[6],ulong,uchar *,ulong,uchar *)
0x140039333  mov     edi, eax
0x140039335  test    eax, eax
0x140039337  jns     short loc_140039353
0x140039339  mov     rcx, cs:WPP_GLOBAL_Control
0x140039340  lea     r15, WPP_GLOBAL_Control
0x140039347  cmp     rcx, r15
0x14003934a  jz      short loc_14003936D
0x14003934c  mov     edx, 40h ; '@'
0x140039351  jmp     short loc_1400392F6
0x140039353  mov     rdx, [rsp+78h+arg_8]; struct DOT11_MAC_STATE_ENTRY *
0x14003935b  mov     r8, r12; struct _NWIFI_LOCK_STATE *
0x14003935e  mov     rcx, rbp; struct _VELAN *
0x140039361  call    ?Dot11OnPMKCalculatedByWorker@@YAXPEAU_VELAN@@PEAUDOT11_MAC_STATE_ENTRY@@PEAU_NWIFI_LOCK_STATE@@@Z; Dot11OnPMKCalculatedByWorker(_VELAN *,DOT11_MAC_STATE_ENTRY *,_NWIFI_LOCK_STATE *)
0x140039366  lea     r15, WPP_GLOBAL_Control
0x14003936d  mov     rcx, [rbx]
0x140039370  test    rcx, rcx
0x140039373  jz      short loc_1400393AB
0x140039375  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140039379  mov     rax, [rcx]
0x14003937c  test    rax, rax
0x14003937f  jz      short loc_140039395
0x140039381  mov     rdx, rcx; Entry
0x140039384  mov     rcx, rax; Lookaside
0x140039387  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003938e  nop     dword ptr [rax+rax+00h]
0x140039393  jmp     short loc_1400393A4
0x140039395  mov     edx, [rcx+8]; Tag
0x140039398  call    cs:__imp_ExFreePoolWithTag
0x14003939f  nop     dword ptr [rax+rax+00h]
0x1400393a4  mov     qword ptr [rbx], 0
0x1400393ab  mov     eax, 128h
0x1400393b0  mov     byte ptr [rsi], 0
0x1400393b3  inc     rsi
0x1400393b6  sub     rax, 1
0x1400393ba  jnz     short loc_1400393B0
0x1400393bc  test    edi, edi
0x1400393be  jns     short loc_1400393E2
0x1400393c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400393c7  cmp     rcx, r15
0x1400393ca  jz      short loc_1400393E2
0x1400393cc  mov     rcx, [rcx+18h]
0x1400393d0  lea     edx, [rax+41h]
0x1400393d3  mov     r9d, edi
0x1400393d6  lea     r8, WPP_7a6055a1655f3139d52915d863ce14fd_Traceguids
0x1400393dd  call    WPP_SF_d
0x1400393e2  mov     rbx, [rsp+78h+arg_10]
0x1400393ea  add     rsp, 40h
0x1400393ee  pop     r15
0x1400393f0  pop     r14
0x1400393f2  pop     r13
0x1400393f4  pop     r12
0x1400393f6  pop     rdi
0x1400393f7  pop     rsi
0x1400393f8  pop     rbp
0x1400393f9  retn
```
