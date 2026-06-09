# NdisWanFreeBundleCB

- ea: `0x140005568`
- end: `0x140005720`
- name: `NdisWanFreeBundleCB`
- size: `440`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140005494`

## callees

- `0x140005568`
- `0x140005728`
- `0x140005750`
- `0x140008b48`
- `0x14000a648`
- `0x140024d68`
- `0x140024e48`
- `0x1400353d0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140005648`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005648`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140005703`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140005703`

## pseudocode

```c
void __fastcall NdisWanFreeBundleCB(_QWORD *Entry)
{
  __int64 i; // rdi
  ULONGLONG Alignment; // rax
  struct _NET_BUFFER_LIST *v4; // r8
  void *v5; // rcx
  int v6; // eax
  __int64 v7; // rcx

  FlushAssemblyLists();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids, Entry[29]);
  }
  NdisWanFreeRecvDesc(Entry[29]);
  Entry[29] = 0;
  for ( i = Entry[38]; ; CompleteNetBufferList(*(_QWORD *)(i + 56), i, v4, 0) )
  {
    v4 = *(struct _NET_BUFFER_LIST **)(i + 160);
    if ( !v4 )
      break;
    Alignment = v4->Link.Alignment;
    if ( !v4->Link.Alignment )
      *(_QWORD *)(i + 168) = 0;
    v4->Link.Alignment = 0;
    *(_QWORD *)(i + 160) = Alignment;
    *(_DWORD *)(i + 176) -= *(_DWORD *)&v4->Context->ContextData[v4->Context->Offset + 100];
    --*(_DWORD *)(i + 184);
    _InterlockedDecrement((volatile signed __int32 *)&v4->Context->ContextData[v4->Context->Offset + 24]);
  }
  v5 = (void *)Entry[50];
  if ( v5 )
  {
    ExFreePoolWithTag(v5, 0);
    Entry[50] = 0;
  }
  v6 = *((_DWORD *)Entry + 4);
  if ( (v6 & 0x4000) != 0 )
  {
    LOBYTE(v4) = 1;
    WanDeallocateCCP(Entry, Entry + 51, v4);
    *((_DWORD *)Entry + 4) &= ~0x4000u;
    v6 = *((_DWORD *)Entry + 4);
  }
  if ( (v6 & 0x8000) != 0 )
  {
    WanDeallocateCCP(Entry, Entry + 98, 0);
    *((_DWORD *)Entry + 4) &= ~0x8000u;
    v6 = *((_DWORD *)Entry + 4);
  }
  if ( (v6 & 0x10000) != 0 )
  {
    WanDeallocateECP((__int64)v5, (__int64)(Entry + 51), Entry + 145);
    *((_DWORD *)Entry + 4) &= ~0x10000u;
    v6 = *((_DWORD *)Entry + 4);
  }
  if ( (v6 & 0x20000) != 0 )
  {
    WanDeallocateECP((__int64)v5, (__int64)(Entry + 98), Entry + 155);
    *((_DWORD *)Entry + 4) &= ~0x20000u;
  }
  v7 = Entry[38] + 272LL;
  *((_DWORD *)Entry + 5) = 0;
  NdisWanFreeNdisString(v7);
  ExFreeToNPagedLookasideList(&BundleCBList, Entry);
}

```

## disassembly

```asm
0x140005568  mov     [rsp+arg_0], rbx
0x14000556d  mov     [rsp+arg_8], rsi
0x140005572  push    rdi
0x140005573  sub     rsp, 20h
0x140005577  mov     rbx, rcx
0x14000557a  call    FlushAssemblyLists
0x14000557f  mov     rcx, cs:WPP_GLOBAL_Control
0x140005586  lea     rax, WPP_GLOBAL_Control
0x14000558d  cmp     rcx, rax
0x140005590  jz      short loc_1400055BD
0x140005592  test    dword ptr [rcx+2Ch], 8000h
0x140005599  jz      short loc_1400055BD
0x14000559b  cmp     byte ptr [rcx+29h], 5
0x14000559f  jb      short loc_1400055BD
0x1400055a1  mov     r9, [rbx+0E8h]
0x1400055a8  lea     r8, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids
0x1400055af  mov     rcx, [rcx+18h]
0x1400055b3  mov     edx, 21h ; '!'
0x1400055b8  call    WPP_SF_q
0x1400055bd  mov     rcx, [rbx+0E8h]
0x1400055c4  call    NdisWanFreeRecvDesc
0x1400055c9  mov     qword ptr [rbx+0E8h], 0
0x1400055d4  mov     rdi, [rbx+130h]
0x1400055db  jmp     short loc_14000562E
0x1400055dd  mov     rax, [r8]
0x1400055e0  test    rax, rax
0x1400055e3  jnz     short loc_1400055EC
0x1400055e5  mov     [rdi+0A8h], rax
0x1400055ec  mov     qword ptr [r8], 0
0x1400055f3  xor     r9d, r9d
0x1400055f6  mov     [rdi+0A0h], rax
0x1400055fd  mov     rcx, [r8+10h]
0x140005601  movzx   eax, word ptr [rcx+0Ah]
0x140005605  mov     edx, [rax+rcx+74h]
0x140005609  sub     [rdi+0B0h], edx
0x14000560f  mov     rdx, rdi
0x140005612  dec     dword ptr [rdi+0B8h]
0x140005618  mov     rcx, [r8+10h]
0x14000561c  movzx   eax, word ptr [rcx+0Ah]
0x140005620  lock dec dword ptr [rax+rcx+28h]
0x140005625  mov     rcx, [rdi+38h]
0x140005629  call    CompleteNetBufferList
0x14000562e  mov     r8, [rdi+0A0h]
0x140005635  test    r8, r8
0x140005638  jnz     short loc_1400055DD
0x14000563a  mov     rcx, [rbx+190h]; P
0x140005641  test    rcx, rcx
0x140005644  jz      short loc_14000565F
0x140005646  xor     edx, edx; Tag
0x140005648  call    cs:__imp_ExFreePoolWithTag
0x14000564f  nop     dword ptr [rax+rax+00h]
0x140005654  mov     qword ptr [rbx+190h], 0
0x14000565f  mov     eax, [rbx+10h]
0x140005662  lea     rsi, [rbx+198h]
0x140005669  bt      eax, 0Eh
0x14000566d  jnb     short loc_140005685
0x14000566f  mov     r8b, 1
0x140005672  mov     rdx, rsi
0x140005675  mov     rcx, rbx
0x140005678  call    WanDeallocateCCP
0x14000567d  btr     dword ptr [rbx+10h], 0Eh
0x140005682  mov     eax, [rbx+10h]
0x140005685  lea     rdi, [rbx+310h]
0x14000568c  bt      eax, 0Fh
0x140005690  jnb     short loc_1400056A8
0x140005692  xor     r8d, r8d
0x140005695  mov     rdx, rdi
0x140005698  mov     rcx, rbx
0x14000569b  call    WanDeallocateCCP
0x1400056a0  btr     dword ptr [rbx+10h], 0Fh
0x1400056a5  mov     eax, [rbx+10h]
0x1400056a8  bt      eax, 10h
0x1400056ac  jnb     short loc_1400056C5
0x1400056ae  lea     r8, [rbx+488h]
0x1400056b5  mov     rdx, rsi
0x1400056b8  call    WanDeallocateECP
0x1400056bd  btr     dword ptr [rbx+10h], 10h
0x1400056c2  mov     eax, [rbx+10h]
0x1400056c5  bt      eax, 11h
0x1400056c9  jnb     short loc_1400056DF
0x1400056cb  lea     r8, [rbx+4D8h]
0x1400056d2  mov     rdx, rdi
0x1400056d5  call    WanDeallocateECP
0x1400056da  btr     dword ptr [rbx+10h], 11h
0x1400056df  mov     rcx, [rbx+130h]
0x1400056e6  add     rcx, 110h
0x1400056ed  mov     dword ptr [rbx+14h], 0
0x1400056f4  call    NdisWanFreeNdisString
0x1400056f9  mov     rdx, rbx; Entry
0x1400056fc  lea     rcx, BundleCBList; Lookaside
0x140005703  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000570a  nop     dword ptr [rax+rax+00h]
0x14000570f  mov     rbx, [rsp+28h+arg_0]
0x140005714  mov     rsi, [rsp+28h+arg_8]
0x140005719  add     rsp, 20h
0x14000571d  pop     rdi
0x14000571e  retn
```
