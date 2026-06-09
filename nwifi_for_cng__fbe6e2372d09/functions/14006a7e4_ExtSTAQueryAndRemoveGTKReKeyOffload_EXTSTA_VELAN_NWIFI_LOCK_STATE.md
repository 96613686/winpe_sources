# ExtSTAQueryAndRemoveGTKReKeyOffload(EXTSTA_VELAN *,_NWIFI_LOCK_STATE *)

- ea: `0x14006a7e4`
- end: `0x14006aa9e`
- name: `?ExtSTAQueryAndRemoveGTKReKeyOffload@@YAXPEAUEXTSTA_VELAN@@PEAU_NWIFI_LOCK_STATE@@@Z`
- size: `698`
- prototype: `void __fastcall(struct EXTSTA_VELAN *, PLOCK_STATE_EX LockState)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140063480`
- `0x140063520`

## callees

- `0x14000d21c`
- `0x140019bbc`
- `0x140020dc0`
- `0x140048874`
- `0x14006a7e4`
- `0x14006aaa4`
- `0x14009bbb0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006a86b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006a86b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006aa29`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006aa29`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006aa3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006aa3d`
- `NDIS!NdisAcquireRWLockWrite` at `0x14006a9ff`
- `NDIS!NdisAcquireRWLockWrite` at `0x14006a9ff`
- `NDIS!NdisReleaseRWLock` at `0x14006a8be`
- `NDIS!NdisReleaseRWLock` at `0x14006a8be`

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
0x14006a7e4  mov     [rsp+arg_10], rbx
0x14006a7e9  push    rbp
0x14006a7ea  push    rsi
0x14006a7eb  push    rdi
0x14006a7ec  push    r12
0x14006a7ee  push    r13
0x14006a7f0  push    r14
0x14006a7f2  push    r15
0x14006a7f4  sub     rsp, 140h
0x14006a7fb  mov     rax, cs:__security_cookie
0x14006a802  xor     rax, rsp
0x14006a805  mov     [rsp+178h+var_48], rax
0x14006a80d  mov     eax, [rcx+6B8h]
0x14006a813  mov     r12, rdx
0x14006a816  mov     rbx, rcx
0x14006a819  test    al, 8
0x14006a81b  jz      loc_14006AA72
0x14006a821  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a828  lea     r13, WPP_GLOBAL_Control
0x14006a82f  cmp     rcx, r13
0x14006a832  jz      short loc_14006A849
0x14006a834  mov     rcx, [rcx+18h]
0x14006a838  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x14006a83f  mov     edx, 2Dh ; '-'
0x14006a844  call    WPP_SF_
0x14006a849  mov     rax, [rbx+0A38h]
0x14006a850  lea     rbp, Lookaside
0x14006a857  mov     esi, [rbx+714h]
0x14006a85d  mov     rcx, [rax+10h]
0x14006a861  mov     r15d, [rcx+53Ch]
0x14006a868  mov     rcx, rbp; Lookaside
0x14006a86b  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14006a872  nop     dword ptr [rax+rax+00h]
0x14006a877  mov     rdi, rax
0x14006a87a  test    rax, rax
0x14006a87d  jz      loc_14006AA4B
0x14006a883  lea     rcx, [rax+18h]; void *
0x14006a887  mov     [rax], rbp
0x14006a88a  xor     edx, edx; Val
0x14006a88c  mov     dword ptr [rax+8], 32697377h
0x14006a893  mov     r8d, 36Ch; Size
0x14006a899  lea     r14, [rax+10h]
0x14006a89d  call    memset
0x14006a8a2  mov     dword ptr [r14], 680180h
0x14006a8a9  mov     rdx, r12; LockState
0x14006a8ac  mov     [r14+4], esi
0x14006a8b0  mov     rcx, [rbx+0A38h]
0x14006a8b7  mov     rcx, [rcx+90h]; Lock
0x14006a8be  call    cs:__imp_NdisReleaseRWLock
0x14006a8c5  nop     dword ptr [rax+rax+00h]
0x14006a8ca  mov     rbp, [rbx+0A38h]
0x14006a8d1  cmp     r15d, 10106h
0x14006a8d8  jb      short loc_14006A91A
0x14006a8da  mov     rcx, [rbp+10h]; struct _ADAPT *
0x14006a8de  mov     r9, r14; void *
0x14006a8e1  mov     edx, 0Ch; unsigned int
0x14006a8e6  mov     [rsp+178h+var_158], 374h; unsigned int
0x14006a8ee  mov     r8d, 0E01036Eh; unsigned int
0x14006a8f4  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x14006a8f9  mov     esi, eax
0x14006a8fb  test    eax, eax
0x14006a8fd  jz      loc_14006A9A8
0x14006a903  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a90a  cmp     rcx, r13
0x14006a90d  jz      loc_14006A9A8
0x14006a913  mov     edx, 2Fh ; '/'
0x14006a918  jmp     short loc_14006A995
0x14006a91a  xor     edx, edx; Val
0x14006a91c  lea     rcx, [rsp+178h+var_147]; void *
0x14006a921  mov     r8d, 0FFh; Size
0x14006a927  call    memset
0x14006a92c  mov     [rsp+30h], esi
0x14006a930  lea     r9, [rsp+178h+var_148]; void *
0x14006a935  mov     rcx, [rbp+10h]; struct _ADAPT *
0x14006a939  mov     edx, 0Ch; unsigned int
0x14006a93e  mov     r8d, 0FD01010Eh; unsigned int
0x14006a944  mov     [rsp+178h+var_158], 100h; unsigned int
0x14006a94c  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x14006a951  mov     esi, eax
0x14006a953  test    eax, eax
0x14006a955  jnz     short loc_14006A984
0x14006a957  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a95e  cmp     rcx, r13
0x14006a961  jz      short loc_14006A976
0x14006a963  mov     rcx, [rcx+18h]
0x14006a967  lea     edx, [rax+30h]
0x14006a96a  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x14006a971  call    WPP_SF_
0x14006a976  mov     rax, [rsp+178h+var_80]
0x14006a97e  mov     [r14+10h], rax
0x14006a982  jmp     short loc_14006A9A8
0x14006a984  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a98b  cmp     rcx, r13
0x14006a98e  jz      short loc_14006A9A8
0x14006a990  mov     edx, 31h ; '1'
0x14006a995  mov     rcx, [rcx+18h]
0x14006a999  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x14006a9a0  mov     r9d, eax
0x14006a9a3  call    WPP_SF_d
0x14006a9a8  mov     rax, [rbx+0A38h]
0x14006a9af  mov     rcx, [rax+10h]
0x14006a9b3  cmp     qword ptr [rcx+610h], 0
0x14006a9bb  jnz     short loc_14006A9EB
0x14006a9bd  mov     rcx, rbx; struct EXTSTA_VELAN *
0x14006a9c0  call    ?ExtSTARemoveGTKReKeyOffload@@YAHPEAUEXTSTA_VELAN@@@Z; ExtSTARemoveGTKReKeyOffload(EXTSTA_VELAN *)
0x14006a9c5  mov     esi, eax
0x14006a9c7  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a9ce  cmp     rcx, r13
0x14006a9d1  jz      short loc_14006A9EB
0x14006a9d3  mov     rcx, [rcx+18h]
0x14006a9d7  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x14006a9de  mov     edx, 32h ; '2'
0x14006a9e3  mov     r9d, eax
0x14006a9e6  call    WPP_SF_d
0x14006a9eb  mov     rcx, [rbx+0A38h]
0x14006a9f2  xor     r8d, r8d; Flags
0x14006a9f5  mov     rdx, r12; LockState
0x14006a9f8  mov     rcx, [rcx+90h]; Lock
0x14006a9ff  call    cs:__imp_NdisAcquireRWLockWrite
0x14006aa06  nop     dword ptr [rax+rax+00h]
0x14006aa0b  test    esi, esi
0x14006aa0d  jnz     short loc_14006AA1E
0x14006aa0f  mov     rcx, [rbx+0A38h]; struct _VELAN *
0x14006aa16  mov     r8, r14; struct _DOT11_CIPHER_KEY_PARAMETERS *
0x14006aa19  call    ?Dot11RsnaSetGTKUploadState@@YAXPEAU_VELAN@@KPEBU_DOT11_CIPHER_KEY_PARAMETERS@@@Z; Dot11RsnaSetGTKUploadState(_VELAN *,ulong,_DOT11_CIPHER_KEY_PARAMETERS const *)
0x14006aa1e  mov     rcx, [rdi]; Lookaside
0x14006aa21  test    rcx, rcx
0x14006aa24  jz      short loc_14006AA37
0x14006aa26  mov     rdx, rdi; Entry
0x14006aa29  call    cs:__imp_ExFreeToNPagedLookasideList
0x14006aa30  nop     dword ptr [rax+rax+00h]
0x14006aa35  jmp     short loc_14006AA72
0x14006aa37  mov     edx, [rdi+8]; Tag
0x14006aa3a  mov     rcx, rdi; P
0x14006aa3d  call    cs:__imp_ExFreePoolWithTag
0x14006aa44  nop     dword ptr [rax+rax+00h]
0x14006aa49  jmp     short loc_14006AA72
0x14006aa4b  mov     rcx, cs:WPP_GLOBAL_Control
0x14006aa52  cmp     rcx, r13
0x14006aa55  jz      short loc_14006AA72
0x14006aa57  mov     rcx, [rcx+18h]
0x14006aa5b  lea     r8, WPP_8214f21e4c8f326fdc66318b31fdb087_Traceguids
0x14006aa62  mov     edx, 2Eh ; '.'
0x14006aa67  mov     r9d, 374h
0x14006aa6d  call    WPP_SF_d
0x14006aa72  mov     rcx, [rsp+178h+var_48]
0x14006aa7a  xor     rcx, rsp; StackCookie
0x14006aa7d  call    __security_check_cookie
0x14006aa82  mov     rbx, [rsp+178h+arg_10]
0x14006aa8a  add     rsp, 140h
0x14006aa91  pop     r15
0x14006aa93  pop     r14
0x14006aa95  pop     r13
0x14006aa97  pop     r12
0x14006aa99  pop     rdi
0x14006aa9a  pop     rsi
0x14006aa9b  pop     rbp
0x14006aa9c  retn
```
