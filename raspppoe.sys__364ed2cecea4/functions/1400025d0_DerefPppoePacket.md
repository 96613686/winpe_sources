# DerefPppoePacket

- ea: `0x1400025d0`
- end: `0x14000278e`
- name: `DerefPppoePacket`
- size: `446`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000110c`
- `0x1400025d0`
- `0x140006b80`

## import_xrefs

- `NDIS!NdisFreeNetBufferList` at `0x140002703`
- `NDIS!NdisFreeNetBufferList` at `0x140002703`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x140002655`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x140002655`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x140002696`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x140002696`
- `NDIS!NdisFreeNetBufferListContext` at `0x140002669`
- `NDIS!NdisFreeNetBufferListContext` at `0x140002767`
- `NDIS!NdisFreeNetBufferListContext` at `0x140002669`
- `NDIS!NdisFreeNetBufferListContext` at `0x140002767`
- `NDIS!NdisReturnNetBufferLists` at `0x140002780`
- `NDIS!NdisReturnNetBufferLists` at `0x140002780`
- `NDIS!NdisFreeCloneNetBufferList` at `0x14000267d`
- `NDIS!NdisFreeCloneNetBufferList` at `0x14000267d`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x1400026eb`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x1400026eb`

## pseudocode

```c
void __fastcall DerefPppoePacket(__int64 a1)
{
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  struct _NET_BUFFER_LIST *v5; // rbx
  PVOID v6; // rsi
  struct _NET_BUFFER_LIST *v7; // rdi
  struct _NET_BUFFER_LIST *v8; // rdi
  struct _NET_BUFFER_LIST *v9; // rcx
  __int64 v10; // rbx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 117, WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids);
  }
  v2 = *(_DWORD *)(a1 + 144);
  if ( !v2 )
  {
    v8 = *(struct _NET_BUFFER_LIST **)(a1 + 136);
    v9 = v8;
    if ( (*(_DWORD *)(a1 + 128) & 2) == 0 )
    {
      v10 = *(_QWORD *)(a1 + 152);
      goto LABEL_22;
    }
LABEL_14:
    NdisFreeNetBufferList(v9);
    goto LABEL_15;
  }
  v3 = v2 - 1;
  if ( !v3 )
  {
    v9 = *(struct _NET_BUFFER_LIST **)(a1 + 136);
    goto LABEL_14;
  }
  v4 = v3 - 1;
  if ( !v4 )
  {
    v8 = *(struct _NET_BUFFER_LIST **)(a1 + 136);
    v9 = v8;
    if ( (*(_DWORD *)(a1 + 128) & 2) == 0 )
    {
      v10 = *(_QWORD *)(a1 + 152);
      NdisRetreatNetBufferListDataStart(v8, 0x14u, 0, 0, 0);
      v9 = v8;
LABEL_22:
      NdisFreeNetBufferListContext(v9, 0xA0u);
      NdisReturnNetBufferLists(*(NDIS_HANDLE *)(v10 + 344), v8, 0);
      goto LABEL_15;
    }
    goto LABEL_14;
  }
  if ( v4 == 1 )
  {
    v5 = *(struct _NET_BUFFER_LIST **)(a1 + 136);
    v6 = v5->ProtocolReserved[1];
    v7 = (struct _NET_BUFFER_LIST *)v5->ProtocolReserved[2];
    NdisAdvanceNetBufferListDataStart(v5, 0x14u, 1u, 0);
    NdisFreeNetBufferListContext(v5, 0xA0u);
    NdisFreeCloneNetBufferList(v5, 2u);
    NdisMCoSendNetBufferListsComplete(*((NDIS_HANDLE *)v6 + 21), v7, 0);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v6 + 10, 0xFFFFFFFF) == 1 )
      (*((void (**)(void))v6 + 6))();
  }
LABEL_15:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 118, WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids);
  }
}

```

## disassembly

```asm
0x1400025d0  push    rbx
0x1400025d2  push    rbp
0x1400025d3  push    rsi
0x1400025d4  push    rdi
0x1400025d5  sub     rsp, 38h
0x1400025d9  mov     rbx, rcx
0x1400025dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400025e3  lea     rbp, WPP_GLOBAL_Control
0x1400025ea  cmp     rcx, rbp
0x1400025ed  jz      short loc_140002611
0x1400025ef  mov     eax, [rcx+2Ch]
0x1400025f2  test    al, 1
0x1400025f4  jz      short loc_140002611
0x1400025f6  cmp     byte ptr [rcx+29h], 4
0x1400025fa  jb      short loc_140002611
0x1400025fc  mov     rcx, [rcx+18h]
0x140002600  lea     r8, WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids
0x140002607  mov     edx, 75h ; 'u'
0x14000260c  call    WPP_SF_
0x140002611  mov     ecx, [rbx+90h]
0x140002617  test    ecx, ecx
0x140002619  jz      loc_140002747
0x14000261f  sub     ecx, 1
0x140002622  jz      loc_1400026FC
0x140002628  sub     ecx, 1
0x14000262b  jz      loc_1400026BD
0x140002631  cmp     ecx, 1
0x140002634  jnz     loc_14000270F
0x14000263a  mov     rbx, [rbx+88h]
0x140002641  lea     edx, [rcx+13h]; DataOffsetDelta
0x140002644  mov     r8b, cl; FreeMdl
0x140002647  xor     r9d, r9d; FreeMdlMdlHandler
0x14000264a  mov     rcx, rbx; NetBufferList
0x14000264d  mov     rsi, [rbx+48h]
0x140002651  mov     rdi, [rbx+50h]
0x140002655  call    cs:__imp_NdisAdvanceNetBufferListDataStart
0x14000265c  nop     dword ptr [rax+rax+00h]
0x140002661  mov     edx, 0A0h; ContextSize
0x140002666  mov     rcx, rbx; NetBufferList
0x140002669  call    cs:__imp_NdisFreeNetBufferListContext
0x140002670  nop     dword ptr [rax+rax+00h]
0x140002675  mov     edx, 2; FreeCloneFlags
0x14000267a  mov     rcx, rbx; CloneNetBufferList
0x14000267d  call    cs:__imp_NdisFreeCloneNetBufferList
0x140002684  nop     dword ptr [rax+rax+00h]
0x140002689  mov     rcx, [rsi+0A8h]; NdisVcHandle
0x140002690  xor     r8d, r8d; SendCompleteFlags
0x140002693  mov     rdx, rdi; NetBufferLists
0x140002696  call    cs:__imp_NdisMCoSendNetBufferListsComplete
0x14000269d  nop     dword ptr [rax+rax+00h]
0x1400026a2  lea     rcx, [rsi+28h]
0x1400026a6  or      eax, 0FFFFFFFFh
0x1400026a9  lock xadd [rcx], eax
0x1400026ad  cmp     eax, 1
0x1400026b0  jnz     short loc_14000270F
0x1400026b2  mov     rax, [rcx+8]
0x1400026b6  call    _guard_dispatch_icall
0x1400026bb  jmp     short loc_14000270F
0x1400026bd  mov     rdi, [rbx+88h]
0x1400026c4  mov     eax, [rbx+80h]
0x1400026ca  mov     rcx, rdi; NetBufferList
0x1400026cd  test    al, 2
0x1400026cf  jnz     short loc_140002703
0x1400026d1  mov     rbx, [rbx+98h]
0x1400026d8  xor     r9d, r9d; AllocateMdlHandler
0x1400026db  xor     r8d, r8d; DataBackFill
0x1400026de  mov     [rsp+58h+FreeMdlHandler], 0; FreeMdlHandler
0x1400026e7  lea     edx, [r9+14h]; DataOffsetDelta
0x1400026eb  call    cs:__imp_NdisRetreatNetBufferListDataStart
0x1400026f2  nop     dword ptr [rax+rax+00h]
0x1400026f7  mov     rcx, rdi
0x1400026fa  jmp     short loc_140002762
0x1400026fc  mov     rcx, [rbx+88h]; NetBufferList
0x140002703  call    cs:__imp_NdisFreeNetBufferList
0x14000270a  nop     dword ptr [rax+rax+00h]
0x14000270f  mov     rcx, cs:WPP_GLOBAL_Control
0x140002716  cmp     rcx, rbp
0x140002719  jz      short loc_14000273D
0x14000271b  mov     eax, [rcx+2Ch]
0x14000271e  test    al, 1
0x140002720  jz      short loc_14000273D
0x140002722  cmp     byte ptr [rcx+29h], 4
0x140002726  jb      short loc_14000273D
0x140002728  mov     rcx, [rcx+18h]
0x14000272c  lea     r8, WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids
0x140002733  mov     edx, 76h ; 'v'
0x140002738  call    WPP_SF_
0x14000273d  add     rsp, 38h
0x140002741  pop     rdi
0x140002742  pop     rsi
0x140002743  pop     rbp
0x140002744  pop     rbx
0x140002745  retn
0x140002747  mov     rdi, [rbx+88h]
0x14000274e  mov     eax, [rbx+80h]
0x140002754  mov     rcx, rdi; NetBufferList
0x140002757  test    al, 2
0x140002759  jnz     short loc_140002703
0x14000275b  mov     rbx, [rbx+98h]
0x140002762  mov     edx, 0A0h; ContextSize
0x140002767  call    cs:__imp_NdisFreeNetBufferListContext
0x14000276e  nop     dword ptr [rax+rax+00h]
0x140002773  mov     rcx, [rbx+158h]; NdisBindingHandle
0x14000277a  xor     r8d, r8d; ReturnFlags
0x14000277d  mov     rdx, rdi; NetBufferLists
0x140002780  call    cs:__imp_NdisReturnNetBufferLists
0x140002787  nop     dword ptr [rax+rax+00h]
0x14000278c  jmp     short loc_14000270F
```
