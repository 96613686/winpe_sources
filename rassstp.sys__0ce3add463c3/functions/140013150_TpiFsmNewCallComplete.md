# TpiFsmNewCallComplete

- ea: `0x140013150`
- end: `0x140013341`
- name: `TpiFsmNewCallComplete`
- size: `497`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400133f0`

## callees

- `0x1400018b0`
- `0x140002030`
- `0x140002f88`
- `0x140002fc4`
- `0x140013150`
- `0x140013ad0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400131af`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001325a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001326c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400131af`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001325a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001326c`
- `ntoskrnl!IofCompleteRequest` at `0x140013243`
- `ntoskrnl!IofCompleteRequest` at `0x140013243`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400131e0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400132b7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400131e0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400132b7`
- `NDIS!NdisMCmActivateVc` at `0x1400132ce`
- `NDIS!NdisMCmActivateVc` at `0x1400132ce`

## pseudocode

```c
void __fastcall TpiFsmNewCallComplete(__int64 a1, int a2)
{
  KIRQL v4; // al
  __int64 v5; // rdi
  KIRQL v6; // al
  __int64 v7; // r8
  unsigned int v8; // ecx
  bool v9; // zf
  NDIS_STATUS v10; // eax
  int v11; // edi

  if ( a2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF__guid_D(
        WPP_GLOBAL_Control->AttachedDevice,
        78,
        WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids,
        a1 + 484,
        a2);
    }
    v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 32));
    v5 = *(_QWORD *)(a1 + 64);
    *(_DWORD *)(a1 + 21088) &= ~2u;
    *(_DWORD *)(a1 + 21096) = a2;
    *(_QWORD *)(a1 + 64) = 0;
    *(_BYTE *)(a1 + 507) = 1;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 32), v4);
    if ( v5 )
    {
      if ( _InterlockedExchange64((volatile __int64 *)(v5 + 104), 0) )
      {
        *(_DWORD *)(v5 + 48) = a2;
        *(_QWORD *)(v5 + 56) = 0;
        IofCompleteRequest((PIRP)v5, 2);
        DereferenceRefCount(a1);
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) )
          WPP_SF__guid_(
            WPP_GLOBAL_Control->AttachedDevice,
            79,
            WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids,
            a1 + 484);
      }
    }
    v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 32));
    goto LABEL_15;
  }
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 32));
  v8 = *(_DWORD *)(a1 + 21088) & 0xFFFFFFF9 | 4;
  v9 = *(_BYTE *)(a1 + 21092) == 0;
  *(_DWORD *)(a1 + 21088) = v8;
  if ( !v9 )
  {
LABEL_15:
    LOBYTE(v7) = v6;
    InitiateSstpContextCleanup(a1, 4, v7);
    return;
  }
  *(_DWORD *)(a1 + 21088) = v8 | 8;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 32), v6);
  v10 = NdisMCmActivateVc(*(NDIS_HANDLE *)(a1 + 40), *(PCO_CALL_PARAMETERS *)(a1 + 21048));
  v11 = v10;
  if ( v10 != 259 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF__guid_D(
        WPP_GLOBAL_Control->AttachedDevice,
        80,
        WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids,
        a1 + 484,
        v10);
    }
    ScmCmActivateVcComplete(v11, a1);
  }
}

```

## disassembly

```asm
0x140013150  push    rbx
0x140013152  push    rbp
0x140013153  push    rsi
0x140013154  push    rdi
0x140013155  push    r14
0x140013157  sub     rsp, 30h
0x14001315b  mov     ebp, edx
0x14001315d  mov     rbx, rcx
0x140013160  test    edx, edx
0x140013162  jz      loc_140013268
0x140013168  mov     rcx, cs:WPP_GLOBAL_Control
0x14001316f  lea     rsi, WPP_GLOBAL_Control
0x140013176  cmp     rcx, rsi
0x140013179  jz      short loc_1400131A8
0x14001317b  mov     eax, [rcx+2Ch]
0x14001317e  test    al, 2
0x140013180  jz      short loc_1400131A8
0x140013182  cmp     byte ptr [rcx+29h], 1
0x140013186  jb      short loc_1400131A8
0x140013188  mov     rcx, [rcx+18h]
0x14001318c  lea     r9, [rbx+1E4h]
0x140013193  mov     edx, 4Eh ; 'N'
0x140013198  mov     [rsp+58h+var_38], ebp
0x14001319c  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x1400131a3  call    WPP_SF__guid_D
0x1400131a8  lea     r14, [rbx+20h]
0x1400131ac  mov     rcx, r14; SpinLock
0x1400131af  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400131b6  nop     dword ptr [rax+rax+00h]
0x1400131bb  mov     rdi, [rbx+40h]
0x1400131bf  mov     rcx, r14; SpinLock
0x1400131c2  and     dword ptr [rbx+5260h], 0FFFFFFFDh
0x1400131c9  mov     dl, al; NewIrql
0x1400131cb  mov     [rbx+5268h], ebp
0x1400131d1  mov     qword ptr [rbx+40h], 0
0x1400131d9  mov     byte ptr [rbx+1FBh], 1
0x1400131e0  call    cs:__imp_KeReleaseSpinLock
0x1400131e7  nop     dword ptr [rax+rax+00h]
0x1400131ec  test    rdi, rdi
0x1400131ef  jz      short loc_140013257
0x1400131f1  xor     eax, eax
0x1400131f3  xchg    rax, [rdi+68h]
0x1400131f7  test    rax, rax
0x1400131fa  jnz     short loc_140013233
0x1400131fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140013203  cmp     rcx, rsi
0x140013206  jz      short loc_140013257
0x140013208  mov     eax, [rcx+2Ch]
0x14001320b  test    al, 2
0x14001320d  jz      short loc_140013257
0x14001320f  cmp     byte ptr [rcx+29h], 1
0x140013213  jb      short loc_140013257
0x140013215  mov     rcx, [rcx+18h]
0x140013219  lea     r9, [rbx+1E4h]
0x140013220  mov     edx, 4Fh ; 'O'
0x140013225  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x14001322c  call    WPP_SF__guid_
0x140013231  jmp     short loc_140013257
0x140013233  mov     dl, 2; PriorityBoost
0x140013235  mov     [rdi+30h], ebp
0x140013238  mov     rcx, rdi; Irp
0x14001323b  mov     qword ptr [rdi+38h], 0
0x140013243  call    cs:__imp_IofCompleteRequest
0x14001324a  nop     dword ptr [rax+rax+00h]
0x14001324f  mov     rcx, rbx
0x140013252  call    DereferenceRefCount
0x140013257  mov     rcx, r14; SpinLock
0x14001325a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013261  nop     dword ptr [rax+rax+00h]
0x140013266  jmp     short loc_140013293
0x140013268  add     rcx, 20h ; ' '; SpinLock
0x14001326c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013273  nop     dword ptr [rax+rax+00h]
0x140013278  mov     ecx, [rbx+5260h]
0x14001327e  and     ecx, 0FFFFFFFDh
0x140013281  or      ecx, 4
0x140013284  cmp     byte ptr [rbx+5264h], 0
0x14001328b  mov     [rbx+5260h], ecx
0x140013291  jz      short loc_1400132A8
0x140013293  mov     r8b, al
0x140013296  mov     edx, 4
0x14001329b  mov     rcx, rbx
0x14001329e  call    InitiateSstpContextCleanup
0x1400132a3  jmp     loc_140013335
0x1400132a8  or      ecx, 8
0x1400132ab  mov     dl, al; NewIrql
0x1400132ad  mov     [rbx+5260h], ecx
0x1400132b3  lea     rcx, [rbx+20h]; SpinLock
0x1400132b7  call    cs:__imp_KeReleaseSpinLock
0x1400132be  nop     dword ptr [rax+rax+00h]
0x1400132c3  mov     rdx, [rbx+5238h]; CallParameters
0x1400132ca  mov     rcx, [rbx+28h]; NdisVcHandle
0x1400132ce  call    cs:__imp_NdisMCmActivateVc
0x1400132d5  nop     dword ptr [rax+rax+00h]
0x1400132da  mov     edi, eax
0x1400132dc  cmp     eax, 103h
0x1400132e1  jz      short loc_140013335
0x1400132e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400132ea  lea     rsi, WPP_GLOBAL_Control
0x1400132f1  cmp     rcx, rsi
0x1400132f4  jz      short loc_140013324
0x1400132f6  mov     edx, [rcx+2Ch]
0x1400132f9  test    dl, 1
0x1400132fc  jz      short loc_140013324
0x1400132fe  cmp     byte ptr [rcx+29h], 1
0x140013302  jb      short loc_140013324
0x140013304  mov     rcx, [rcx+18h]
0x140013308  lea     r9, [rbx+1E4h]
0x14001330f  mov     edx, 50h ; 'P'
0x140013314  mov     [rsp+58h+var_38], eax
0x140013318  lea     r8, WPP_03dd624b1eee3570f1d216fd473d0bee_Traceguids
0x14001331f  call    WPP_SF__guid_D
0x140013324  mov     r8, [rbx+5238h]
0x14001332b  mov     rdx, rbx
0x14001332e  mov     ecx, edi
0x140013330  call    ScmCmActivateVcComplete
0x140013335  add     rsp, 30h
0x140013339  pop     r14
0x14001333b  pop     rdi
0x14001333c  pop     rsi
0x14001333d  pop     rbp
0x14001333e  pop     rbx
0x14001333f  retn
```
