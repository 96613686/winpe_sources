# OWEFallbackToGroup19(_VELAN *,_NWIFI_LOCK_STATE *)

- ea: `0x140019648`
- end: `0x1400197a1`
- name: `?OWEFallbackToGroup19@@YAJPEAU_VELAN@@PEAU_NWIFI_LOCK_STATE@@@Z`
- size: `345`
- prototype: `int(struct _VELAN *, struct _NWIFI_LOCK_STATE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140039c90`

## callees

- `0x140019648`
- `0x140019bbc`
- `0x140020dc0`
- `0x140030244`
- `0x140039f6c`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001974a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001974a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001975b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001975b`
- `NDIS!NdisAcquireRWLockWrite` at `0x140019727`
- `NDIS!NdisAcquireRWLockWrite` at `0x140019727`
- `NDIS!NdisReleaseRWLock` at `0x1400196ec`
- `NDIS!NdisReleaseRWLock` at `0x1400196ec`

## pseudocode

```c
__int64 __fastcall OWEFallbackToGroup19(struct _VELAN *a1, struct _NWIFI_LOCK_STATE *a2, __int64 a3)
{
  struct _OWE_CONTEXT *pOWEContext; // rdx
  __int64 result; // rax
  unsigned int v7; // edi
  PNPAGED_LOOKASIDE_LIST *v8; // rsi
  unsigned int v9; // edi
  unsigned int v10; // [rsp+50h] [rbp+8h] BYREF
  void *v11; // [rsp+60h] [rbp+18h] BYREF

  v11 = 0;
  pOWEContext = a1->pOWEContext;
  v10 = 0;
  LOBYTE(a3) = 1;
  result = OWEGetAuthParams(19, pOWEContext, a3, &v10, &v11);
  if ( !(_DWORD)result )
  {
    v7 = v10;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_lll(
        WPP_GLOBAL_Control->AttachedDevice,
        71,
        WPP_7a6055a1655f3139d52915d863ce14fd_Traceguids,
        *((unsigned int *)a1->pOWEContext + 2),
        19,
        v10);
    *((_DWORD *)a1->pOWEContext + 2) = 19;
    NdisReleaseRWLock(a1->pRWLock, &a2->lockStateEx);
    v8 = (PNPAGED_LOOKASIDE_LIST *)v11;
    v9 = PtRequestAdapterSync(a1->pAdapt, 1u, 0xE010174u, v11, v7);
    NdisAcquireRWLockWrite(a1->pRWLock, &a2->lockStateEx, 0);
    if ( v8 )
    {
      if ( *(v8 - 2) )
        ExFreeToNPagedLookasideList(*(v8 - 2), v8 - 2);
      else
        ExFreePoolWithTag(v8 - 2, *((_DWORD *)v8 - 2));
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 72, WPP_7a6055a1655f3139d52915d863ce14fd_Traceguids, v9);
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x140019648  mov     r11, rsp
0x14001964b  mov     [r11+10h], rbx
0x14001964f  mov     [r11+20h], rbp
0x140019653  push    rsi
0x140019654  push    rdi
0x140019655  push    r14
0x140019657  sub     rsp, 30h
0x14001965b  mov     rbp, rdx
0x14001965e  mov     qword ptr [r11+18h], 0
0x140019666  mov     rdx, [rcx+2170h]
0x14001966d  lea     rax, [r11+18h]
0x140019671  mov     rbx, rcx
0x140019674  mov     [rsp+48h+arg_0], 0
0x14001967c  mov     esi, 13h
0x140019681  mov     [r11-28h], rax
0x140019685  mov     ecx, esi
0x140019687  lea     r9, [r11+8]
0x14001968b  mov     r8b, 1
0x14001968e  call    ?OWEGetAuthParams@@YAJW4OWE_GROUP@@PEAU_OWE_CONTEXT@@EPEAKPEAPEAU_DOT11_OWE_AUTH_PARAMS@@@Z; OWEGetAuthParams(OWE_GROUP,_OWE_CONTEXT *,uchar,ulong *,_DOT11_OWE_AUTH_PARAMS * *)
0x140019693  test    eax, eax
0x140019695  jnz     loc_14001978D
0x14001969b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400196a2  lea     r14, WPP_GLOBAL_Control
0x1400196a9  mov     edi, [rsp+48h+arg_0]
0x1400196ad  cmp     rcx, r14
0x1400196b0  jz      short loc_1400196D8
0x1400196b2  mov     r9, [rbx+2170h]
0x1400196b9  lea     edx, [rsi+34h]
0x1400196bc  mov     rcx, [rcx+18h]
0x1400196c0  lea     r8, WPP_7a6055a1655f3139d52915d863ce14fd_Traceguids
0x1400196c7  mov     [rsp+48h+var_20], edi
0x1400196cb  mov     [rsp+48h+var_28], esi
0x1400196cf  mov     r9d, [r9+8]
0x1400196d3  call    WPP_SF_lll
0x1400196d8  mov     rax, [rbx+2170h]
0x1400196df  mov     rdx, rbp; LockState
0x1400196e2  mov     [rax+8], esi
0x1400196e5  mov     rcx, [rbx+90h]; Lock
0x1400196ec  call    cs:__imp_NdisReleaseRWLock
0x1400196f3  nop     dword ptr [rax+rax+00h]
0x1400196f8  mov     rsi, [rsp+48h+arg_10]
0x1400196fd  mov     edx, 1; unsigned int
0x140019702  mov     rcx, [rbx+10h]; struct _ADAPT *
0x140019706  mov     r9, rsi; void *
0x140019709  mov     r8d, 0E010174h; unsigned int
0x14001970f  mov     [rsp+48h+var_28], edi; unsigned int
0x140019713  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x140019718  mov     rcx, [rbx+90h]; Lock
0x14001971f  xor     r8d, r8d; Flags
0x140019722  mov     rdx, rbp; LockState
0x140019725  mov     edi, eax
0x140019727  call    cs:__imp_NdisAcquireRWLockWrite
0x14001972e  nop     dword ptr [rax+rax+00h]
0x140019733  test    rsi, rsi
0x140019736  jz      short loc_140019767
0x140019738  lea     rcx, [rsi-10h]; P
0x14001973c  mov     r8, [rcx]
0x14001973f  test    r8, r8
0x140019742  jz      short loc_140019758
0x140019744  mov     rdx, rcx; Entry
0x140019747  mov     rcx, r8; Lookaside
0x14001974a  call    cs:__imp_ExFreeToNPagedLookasideList
0x140019751  nop     dword ptr [rax+rax+00h]
0x140019756  jmp     short loc_140019767
0x140019758  mov     edx, [rcx+8]; Tag
0x14001975b  call    cs:__imp_ExFreePoolWithTag
0x140019762  nop     dword ptr [rax+rax+00h]
0x140019767  mov     rcx, cs:WPP_GLOBAL_Control
0x14001976e  cmp     rcx, r14
0x140019771  jz      short loc_14001978B
0x140019773  mov     rcx, [rcx+18h]
0x140019777  lea     r8, WPP_7a6055a1655f3139d52915d863ce14fd_Traceguids
0x14001977e  mov     edx, 48h ; 'H'
0x140019783  mov     r9d, edi
0x140019786  call    WPP_SF_d
0x14001978b  mov     eax, edi
0x14001978d  mov     rbx, [rsp+48h+arg_8]
0x140019792  mov     rbp, [rsp+48h+arg_18]
0x140019797  add     rsp, 30h
0x14001979b  pop     r14
0x14001979d  pop     rdi
0x14001979e  pop     rsi
0x14001979f  retn
```
