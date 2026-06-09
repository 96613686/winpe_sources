# CompleteNetBufferList

- ea: `0x1400353d0`
- end: `0x1400355cd`
- name: `CompleteNetBufferList`
- size: `509`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140002530`
- `0x140002770`
- `0x140005568`
- `0x14000b818`
- `0x14002fe1c`
- `0x1400312a0`
- `0x1400318c0`

## callees

- `0x14000a744`
- `0x140016230`
- `0x14002e898`
- `0x1400353d0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14003548a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003548a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140035452`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140035452`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x1400355a5`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x1400355a5`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x1400354ae`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x1400354ae`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x1400354ea`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x1400354ea`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x14003552b`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x14003552b`
- `NDIS!NdisFreeNetBufferListContext` at `0x140035509`
- `NDIS!NdisFreeNetBufferListContext` at `0x140035509`
- `NDIS!NdisFreeNetBufferList` at `0x140035593`
- `NDIS!NdisFreeNetBufferList` at `0x140035593`

## pseudocode

```c
void __fastcall CompleteNetBufferList(__int64 a1, __int64 a2, struct _NET_BUFFER_LIST *a3, NDIS_STATUS a4)
{
  __int64 v6; // rbp
  char *v9; // rsi
  __int64 v10; // r13
  ULONG v11; // edx
  __int16 v12; // [rsp+68h] [rbp+10h]

  v6 = *(_QWORD *)(a2 + 64);
  v12 = *(_WORD *)(a2 + 214);
  v9 = (char *)a3->Context + a3->Context->Offset;
  v10 = *((_QWORD *)v9 + 11);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_8fab404a276b37b5b154f85d9d785092_Traceguids, a2, a3);
  }
  _InterlockedDecrement((volatile signed __int32 *)(a2 + 104));
  if ( *(_WORD *)(a2 + 212) == 0xAB00 )
  {
    NdisFreeNetBufferList(a3);
  }
  else
  {
    *(_BYTE *)(v6 + 1776) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v6 + 1768));
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a2 + 24), 0xFFFFFFFF) == 1 )
      (*(void (**)(void))(a2 + 32))();
    KeReleaseSpinLock((PKSPIN_LOCK)(v6 + 1768), *(_BYTE *)(v6 + 1776));
    if ( (*((_DWORD *)v9 + 11) & 0x20) != 0 )
      NdisAdvanceNetBufferListDataStart(a3, *((_DWORD *)v9 + 30), 0, 0);
    if ( (*((_DWORD *)v9 + 11) & 0x10) != 0 )
    {
      v11 = 12;
      if ( v12 != 171 )
        v11 = 14;
      NdisRetreatNetBufferListDataStart(a3, v11, 0, 0, 0);
    }
    a3->SourceHandle = (NDIS_HANDLE)*((_QWORD *)v9 + 17);
    NdisFreeNetBufferListContext(a3, 0x80u);
    a3->Status = a4;
    if ( v10 )
    {
      NdisMCoSendNetBufferListsComplete(*(NDIS_HANDLE *)(v10 + 40), a3, 0);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v10 + 24), 0xFFFFFFFF) == 1 )
        DoDerefCmVcCBWork(v10);
    }
    else
    {
      NdisMSendNetBufferListsComplete(*(NDIS_HANDLE *)(a1 + 40), a3, 0);
    }
    _InterlockedIncrement(&glSendCompleteCount);
  }
}

```

## disassembly

```asm
0x1400353d0  mov     [rsp+arg_10], rbx
0x1400353d5  mov     [rsp+arg_18], rbp
0x1400353da  push    rsi
0x1400353db  push    rdi
0x1400353dc  push    r12
0x1400353de  push    r13
0x1400353e0  push    r15
0x1400353e2  sub     rsp, 30h
0x1400353e6  movzx   eax, word ptr [rdx+0D6h]
0x1400353ed  mov     rbx, r8
0x1400353f0  mov     r8, [r8+10h]
0x1400353f4  mov     r12d, r9d
0x1400353f7  mov     rbp, [rdx+40h]
0x1400353fb  mov     rdi, rdx
0x1400353fe  mov     r15, rcx
0x140035401  mov     [rsp+58h+arg_8], ax
0x140035406  movzx   esi, word ptr [r8+0Ah]
0x14003540b  add     rsi, r8
0x14003540e  mov     r13, [rsi+58h]
0x140035412  mov     rcx, cs:WPP_GLOBAL_Control
0x140035419  lea     rax, WPP_GLOBAL_Control
0x140035420  cmp     rcx, rax
0x140035423  jz      short loc_140035430
0x140035425  mov     eax, [rcx+2Ch]
0x140035428  test    al, 8
0x14003542a  jnz     loc_140035564
0x140035430  lock dec dword ptr [rdi+68h]
0x140035434  mov     eax, 0AB00h
0x140035439  cmp     [rdi+0D4h], ax
0x140035440  jz      loc_140035590
0x140035446  lea     rcx, [rbp+6E8h]; SpinLock
0x14003544d  mov     [rsp+58h+arg_0], r14
0x140035452  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140035459  nop     dword ptr [rax+rax+00h]
0x14003545e  lea     rcx, [rdi+18h]
0x140035462  mov     edi, 0FFFFFFFFh
0x140035467  mov     [rbp+6F0h], al
0x14003546d  mov     eax, edi
0x14003546f  lock xadd [rcx], eax
0x140035473  cmp     eax, 1
0x140035476  jz      loc_140035556
0x14003547c  movzx   edx, byte ptr [rbp+6F0h]; NewIrql
0x140035483  lea     rcx, [rbp+6E8h]; SpinLock
0x14003548a  call    cs:__imp_KeReleaseSpinLock
0x140035491  nop     dword ptr [rax+rax+00h]
0x140035496  mov     eax, [rsi+2Ch]
0x140035499  mov     r14, [rsp+58h+arg_0]
0x14003549e  test    al, 20h
0x1400354a0  jz      short loc_1400354BA
0x1400354a2  mov     edx, [rsi+78h]; DataOffsetDelta
0x1400354a5  xor     r9d, r9d; FreeMdlMdlHandler
0x1400354a8  xor     r8d, r8d; FreeMdl
0x1400354ab  mov     rcx, rbx; NetBufferList
0x1400354ae  call    cs:__imp_NdisAdvanceNetBufferListDataStart
0x1400354b5  nop     dword ptr [rax+rax+00h]
0x1400354ba  mov     eax, [rsi+2Ch]
0x1400354bd  test    al, 10h
0x1400354bf  jz      short loc_1400354F6
0x1400354c1  mov     ecx, 0ABh
0x1400354c6  mov     [rsp+58h+FreeMdlHandler], 0; FreeMdlHandler
0x1400354cf  cmp     [rsp+58h+arg_8], cx
0x1400354d4  mov     edx, 0Ch
0x1400354d9  mov     eax, 0Eh
0x1400354de  mov     rcx, rbx; NetBufferList
0x1400354e1  cmovnz  edx, eax; DataOffsetDelta
0x1400354e4  xor     r9d, r9d; AllocateMdlHandler
0x1400354e7  xor     r8d, r8d; DataBackFill
0x1400354ea  call    cs:__imp_NdisRetreatNetBufferListDataStart
0x1400354f1  nop     dword ptr [rax+rax+00h]
0x1400354f6  mov     rax, [rsi+88h]
0x1400354fd  mov     edx, 80h; ContextSize
0x140035502  mov     rcx, rbx; NetBufferList
0x140035505  mov     [rbx+78h], rax
0x140035509  call    cs:__imp_NdisFreeNetBufferListContext
0x140035510  nop     dword ptr [rax+rax+00h]
0x140035515  xor     r8d, r8d; SendCompleteFlags
0x140035518  mov     [rbx+8Ch], r12d
0x14003551f  mov     rdx, rbx; NetBufferLists
0x140035522  test    r13, r13
0x140035525  jnz     short loc_1400355A1
0x140035527  mov     rcx, [r15+28h]; MiniportAdapterHandle
0x14003552b  call    cs:__imp_NdisMSendNetBufferListsComplete
0x140035532  nop     dword ptr [rax+rax+00h]
0x140035537  lock inc cs:glSendCompleteCount
0x14003553e  mov     rbx, [rsp+58h+arg_10]
0x140035543  mov     rbp, [rsp+58h+arg_18]
0x140035548  add     rsp, 30h
0x14003554c  pop     r15
0x14003554e  pop     r13
0x140035550  pop     r12
0x140035552  pop     rdi
0x140035553  pop     rsi
0x140035554  retn
0x140035556  mov     rax, [rcx+8]
0x14003555a  call    _guard_dispatch_icall
0x14003555f  jmp     loc_14003547C
0x140035564  cmp     byte ptr [rcx+29h], 5
0x140035568  jb      loc_140035430
0x14003556e  mov     rcx, [rcx+18h]
0x140035572  lea     r8, WPP_8fab404a276b37b5b154f85d9d785092_Traceguids
0x140035579  mov     edx, 33h ; '3'
0x14003557e  mov     [rsp+58h+FreeMdlHandler], rbx
0x140035583  mov     r9, rdi
0x140035586  call    WPP_SF_qq
0x14003558b  jmp     loc_140035430
0x140035590  mov     rcx, rbx; NetBufferList
0x140035593  call    cs:__imp_NdisFreeNetBufferList
0x14003559a  nop     dword ptr [rax+rax+00h]
0x14003559f  jmp     short loc_14003553E
0x1400355a1  mov     rcx, [r13+28h]; NdisVcHandle
0x1400355a5  call    cs:__imp_NdisMCoSendNetBufferListsComplete
0x1400355ac  nop     dword ptr [rax+rax+00h]
0x1400355b1  lock xadd [r13+18h], edi
0x1400355b7  cmp     edi, 1
0x1400355ba  jnz     loc_140035537
0x1400355c0  mov     rcx, r13
0x1400355c3  call    DoDerefCmVcCBWork
0x1400355c8  jmp     loc_140035537
```
