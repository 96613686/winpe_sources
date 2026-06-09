# ExtSTAQueryAndRemoveGTKReKeyOffload(EXTSTA_VELAN *,_NWIFI_LOCK_STATE *)

- ea: `0x140068fb4`
- end: `0x14006926e`
- name: `?ExtSTAQueryAndRemoveGTKReKeyOffload@@YAXPEAUEXTSTA_VELAN@@PEAU_NWIFI_LOCK_STATE@@@Z`
- size: `698`
- prototype: `void __fastcall(struct EXTSTA_VELAN *, PLOCK_STATE_EX LockState)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140061c50`
- `0x140061cf0`

## callees

- `0x14000d22c`
- `0x140019bbc`
- `0x140020dc0`
- `0x1400475fc`
- `0x140068fb4`
- `0x140069274`
- `0x14009a3d0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006903b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006903b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400691f9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400691f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006920d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006920d`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400691cf`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400691cf`
- `NDIS!NdisReleaseRWLock` at `0x14006908e`
- `NDIS!NdisReleaseRWLock` at `0x14006908e`

## pseudocode

```c
void __fastcall ExtSTAQueryAndRemoveGTKReKeyOffload(struct EXTSTA_VELAN *a1, PLOCK_STATE_EX LockState)
{
  unsigned int uRsnReKeyProtocolId; // esi
  unsigned int uIhvWdiVersion; // r15d
  _DWORD *v6; // rax
  PNPAGED_LOOKASIDE_LIST *v7; // rdi
  char *v8; // r14
  _VELAN *pGenVElan; // rbp
  unsigned int v10; // eax
  unsigned int v11; // esi
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  unsigned int v14; // eax
  unsigned int v15; // edx
  _BYTE v16[256]; // [rsp+30h] [rbp-148h] BYREF

  if ( (*(_DWORD *)&a1->Rw & 8) == 0 )
    return;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids);
  uRsnReKeyProtocolId = a1->Rw.uRsnReKeyProtocolId;
  uIhvWdiVersion = a1->pGenVElan->pAdapt->AdapterEnhancedCapabilities.uIhvWdiVersion;
  v6 = ExAllocateFromNPagedLookasideList(&Lookaside);
  v7 = (PNPAGED_LOOKASIDE_LIST *)v6;
  if ( v6 )
  {
    *(_QWORD *)v6 = &Lookaside;
    v6[2] = 845771639;
    v8 = (char *)(v6 + 4);
    memset(v6 + 6, 0, 0x36Cu);
    *(_DWORD *)v8 = 6816128;
    *((_DWORD *)v8 + 1) = uRsnReKeyProtocolId;
    NdisReleaseRWLock(a1->pGenVElan->pRWLock, LockState);
    pGenVElan = a1->pGenVElan;
    if ( uIhvWdiVersion < 0x10106 )
    {
      memset(&v16[1], 0, 0xFFu);
      *(_DWORD *)v16 = uRsnReKeyProtocolId;
      v10 = PtRequestAdapterSync(pGenVElan->pAdapt, 0xCu, 0xFD01010E, v16, 0x100u);
      v11 = v10;
      if ( !v10 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids);
        *((_QWORD *)v8 + 2) = *(_QWORD *)&v16[200];
        goto LABEL_16;
      }
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
LABEL_16:
        if ( !a1->pGenVElan->pAdapt->AdapterEnhancedCapabilities.uWindowsWifiCxVersion )
        {
          v14 = ExtSTARemoveGTKReKeyOffload(a1);
          v11 = v14;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids, v14);
        }
        NdisAcquireRWLockWrite(a1->pGenVElan->pRWLock, LockState, 0);
        if ( !v11 )
          Dot11RsnaSetGTKUploadState(a1->pGenVElan, v15, (const struct _DOT11_CIPHER_KEY_PARAMETERS *)v8);
        if ( *v7 )
          ExFreeToNPagedLookasideList(*v7, v7);
        else
          ExFreePoolWithTag(v7, *((_DWORD *)v7 + 2));
        return;
      }
      v13 = 49;
    }
    else
    {
      v10 = PtRequestAdapterSync(pGenVElan->pAdapt, 0xCu, 0xE01036Eu, v8, 0x374u);
      v11 = v10;
      if ( !v10 )
        goto LABEL_16;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_16;
      v13 = 47;
    }
    WPP_SF_d(v12->AttachedDevice, v13, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids, v10);
    goto LABEL_16;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids, 884);
}

```

## disassembly

```asm
0x140068fb4  mov     [rsp+arg_10], rbx
0x140068fb9  push    rbp
0x140068fba  push    rsi
0x140068fbb  push    rdi
0x140068fbc  push    r12
0x140068fbe  push    r13
0x140068fc0  push    r14
0x140068fc2  push    r15
0x140068fc4  sub     rsp, 140h
0x140068fcb  mov     rax, cs:__security_cookie
0x140068fd2  xor     rax, rsp
0x140068fd5  mov     [rsp+178h+var_48], rax
0x140068fdd  mov     eax, [rcx+6B8h]
0x140068fe3  mov     r12, rdx
0x140068fe6  mov     rbx, rcx
0x140068fe9  test    al, 8
0x140068feb  jz      loc_140069242
0x140068ff1  mov     rcx, cs:WPP_GLOBAL_Control
0x140068ff8  lea     r13, WPP_GLOBAL_Control
0x140068fff  cmp     rcx, r13
0x140069002  jz      short loc_140069019
0x140069004  mov     rcx, [rcx+18h]
0x140069008  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x14006900f  mov     edx, 2Dh ; '-'
0x140069014  call    WPP_SF_
0x140069019  mov     rax, [rbx+0A38h]
0x140069020  lea     rbp, Lookaside
0x140069027  mov     esi, [rbx+714h]
0x14006902d  mov     rcx, [rax+10h]
0x140069031  mov     r15d, [rcx+53Ch]
0x140069038  mov     rcx, rbp; Lookaside
0x14006903b  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140069042  nop     dword ptr [rax+rax+00h]
0x140069047  mov     rdi, rax
0x14006904a  test    rax, rax
0x14006904d  jz      loc_14006921B
0x140069053  lea     rcx, [rax+18h]; void *
0x140069057  mov     [rax], rbp
0x14006905a  xor     edx, edx; Val
0x14006905c  mov     dword ptr [rax+8], 32697377h
0x140069063  mov     r8d, 36Ch; Size
0x140069069  lea     r14, [rax+10h]
0x14006906d  call    memset
0x140069072  mov     dword ptr [r14], 680180h
0x140069079  mov     rdx, r12; LockState
0x14006907c  mov     [r14+4], esi
0x140069080  mov     rcx, [rbx+0A38h]
0x140069087  mov     rcx, [rcx+90h]; Lock
0x14006908e  call    cs:__imp_NdisReleaseRWLock
0x140069095  nop     dword ptr [rax+rax+00h]
0x14006909a  mov     rbp, [rbx+0A38h]
0x1400690a1  cmp     r15d, 10106h
0x1400690a8  jb      short loc_1400690EA
0x1400690aa  mov     rcx, [rbp+10h]; struct _ADAPT *
0x1400690ae  mov     r9, r14; void *
0x1400690b1  mov     edx, 0Ch; unsigned int
0x1400690b6  mov     [rsp+178h+var_158], 374h; unsigned int
0x1400690be  mov     r8d, 0E01036Eh; unsigned int
0x1400690c4  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x1400690c9  mov     esi, eax
0x1400690cb  test    eax, eax
0x1400690cd  jz      loc_140069178
0x1400690d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400690da  cmp     rcx, r13
0x1400690dd  jz      loc_140069178
0x1400690e3  mov     edx, 2Fh ; '/'
0x1400690e8  jmp     short loc_140069165
0x1400690ea  xor     edx, edx; Val
0x1400690ec  lea     rcx, [rsp+178h+var_147]; void *
0x1400690f1  mov     r8d, 0FFh; Size
0x1400690f7  call    memset
0x1400690fc  mov     [rsp+30h], esi
0x140069100  lea     r9, [rsp+178h+var_148]; void *
0x140069105  mov     rcx, [rbp+10h]; struct _ADAPT *
0x140069109  mov     edx, 0Ch; unsigned int
0x14006910e  mov     r8d, 0FD01010Eh; unsigned int
0x140069114  mov     [rsp+178h+var_158], 100h; unsigned int
0x14006911c  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x140069121  mov     esi, eax
0x140069123  test    eax, eax
0x140069125  jnz     short loc_140069154
0x140069127  mov     rcx, cs:WPP_GLOBAL_Control
0x14006912e  cmp     rcx, r13
0x140069131  jz      short loc_140069146
0x140069133  mov     rcx, [rcx+18h]
0x140069137  lea     edx, [rax+30h]
0x14006913a  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x140069141  call    WPP_SF_
0x140069146  mov     rax, [rsp+178h+var_80]
0x14006914e  mov     [r14+10h], rax
0x140069152  jmp     short loc_140069178
0x140069154  mov     rcx, cs:WPP_GLOBAL_Control
0x14006915b  cmp     rcx, r13
0x14006915e  jz      short loc_140069178
0x140069160  mov     edx, 31h ; '1'
0x140069165  mov     rcx, [rcx+18h]
0x140069169  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x140069170  mov     r9d, eax
0x140069173  call    WPP_SF_d
0x140069178  mov     rax, [rbx+0A38h]
0x14006917f  mov     rcx, [rax+10h]
0x140069183  cmp     qword ptr [rcx+610h], 0
0x14006918b  jnz     short loc_1400691BB
0x14006918d  mov     rcx, rbx; struct EXTSTA_VELAN *
0x140069190  call    ?ExtSTARemoveGTKReKeyOffload@@YAHPEAUEXTSTA_VELAN@@@Z; ExtSTARemoveGTKReKeyOffload(EXTSTA_VELAN *)
0x140069195  mov     esi, eax
0x140069197  mov     rcx, cs:WPP_GLOBAL_Control
0x14006919e  cmp     rcx, r13
0x1400691a1  jz      short loc_1400691BB
0x1400691a3  mov     rcx, [rcx+18h]
0x1400691a7  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x1400691ae  mov     edx, 32h ; '2'
0x1400691b3  mov     r9d, eax
0x1400691b6  call    WPP_SF_d
0x1400691bb  mov     rcx, [rbx+0A38h]
0x1400691c2  xor     r8d, r8d; Flags
0x1400691c5  mov     rdx, r12; LockState
0x1400691c8  mov     rcx, [rcx+90h]; Lock
0x1400691cf  call    cs:__imp_NdisAcquireRWLockWrite
0x1400691d6  nop     dword ptr [rax+rax+00h]
0x1400691db  test    esi, esi
0x1400691dd  jnz     short loc_1400691EE
0x1400691df  mov     rcx, [rbx+0A38h]; struct _VELAN *
0x1400691e6  mov     r8, r14; struct _DOT11_CIPHER_KEY_PARAMETERS *
0x1400691e9  call    ?Dot11RsnaSetGTKUploadState@@YAXPEAU_VELAN@@KPEBU_DOT11_CIPHER_KEY_PARAMETERS@@@Z; Dot11RsnaSetGTKUploadState(_VELAN *,ulong,_DOT11_CIPHER_KEY_PARAMETERS const *)
0x1400691ee  mov     rcx, [rdi]; Lookaside
0x1400691f1  test    rcx, rcx
0x1400691f4  jz      short loc_140069207
0x1400691f6  mov     rdx, rdi; Entry
0x1400691f9  call    cs:__imp_ExFreeToNPagedLookasideList
0x140069200  nop     dword ptr [rax+rax+00h]
0x140069205  jmp     short loc_140069242
0x140069207  mov     edx, [rdi+8]; Tag
0x14006920a  mov     rcx, rdi; P
0x14006920d  call    cs:__imp_ExFreePoolWithTag
0x140069214  nop     dword ptr [rax+rax+00h]
0x140069219  jmp     short loc_140069242
0x14006921b  mov     rcx, cs:WPP_GLOBAL_Control
0x140069222  cmp     rcx, r13
0x140069225  jz      short loc_140069242
0x140069227  mov     rcx, [rcx+18h]
0x14006922b  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x140069232  mov     edx, 2Eh ; '.'
0x140069237  mov     r9d, 374h
0x14006923d  call    WPP_SF_d
0x140069242  mov     rcx, [rsp+178h+var_48]
0x14006924a  xor     rcx, rsp; StackCookie
0x14006924d  call    __security_check_cookie
0x140069252  mov     rbx, [rsp+178h+arg_10]
0x14006925a  add     rsp, 140h
0x140069261  pop     r15
0x140069263  pop     r14
0x140069265  pop     r13
0x140069267  pop     r12
0x140069269  pop     rdi
0x14006926a  pop     rsi
0x14006926b  pop     rbp
0x14006926c  retn
```
