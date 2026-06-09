# PcpLineCreate

- ea: `0x140001884`
- end: `0x140001a81`
- name: `PcpLineCreate`
- size: `509`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x1400010e0`
- `0x14000d8b8`
- `0x14000ee88`

## callees

- `0x140001884`
- `0x140002c1c`
- `0x140003770`
- `0x1400039d8`
- `0x140010f10`
- `0x140013600`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400018d6`
- `ntoskrnl!ExAllocatePool2` at `0x1400018d6`
- `NDIS!NdisAllocateRWLock` at `0x1400019be`
- `NDIS!NdisAllocateRWLock` at `0x1400019be`
- `NDIS!NdisReleaseRWLock` at `0x140001a3f`
- `NDIS!NdisReleaseRWLock` at `0x140001a3f`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400019f9`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400019f9`

## pseudocode

```c
__int64 __fastcall PcpLineCreate(
        _QWORD *a1,
        __int64 a2,
        char a3,
        unsigned __int16 a4,
        unsigned __int16 a5,
        __int64 a6,
        __int64 a7,
        int a8,
        int a9)
{
  int v9; // ebp
  __int64 v10; // rsi
  size_t v14; // r14
  _QWORD *Pool2; // rax
  _QWORD *v16; // rbx
  __int64 v18; // rdx
  __int64 v19; // r9
  __int64 v20; // rax
  struct _LIST_ENTRY *Flink; // rcx
  PNDIS_RW_LOCK_EX RWLock; // rax
  _QWORD *v23; // rax
  struct _NDIS_RW_LOCK_EX *v24; // rcx
  int v25; // edi
  struct _LOCK_STATE_EX LockState; // [rsp+98h] [rbp+20h] BYREF

  v9 = a5;
  v10 = a4;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  *a1 = 0;
  v14 = (unsigned int)a4 + v9 + 344;
  Pool2 = (_QWORD *)ExAllocatePool2(64, v14, 1701602128);
  v16 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  memset(Pool2, 0, v14);
  if ( (_WORD)v10 )
  {
    *((_WORD *)v16 + 133) = v10;
    v16[34] = v16 + 43;
  }
  if ( (_WORD)v9 )
  {
    *((_WORD *)v16 + 141) = v9;
    v16[36] = (char *)v16 + v10 + 344;
  }
  v18 = a6;
  *((_DWORD *)v16 + 76) = a8;
  *((_DWORD *)v16 + 77) = a9;
  *((_DWORD *)v16 + 62) = 1;
  v16[37] = v18;
  if ( a2 )
  {
    v19 = *(_QWORD *)(a2 + 40);
    v20 = *(_QWORD *)(a2 + 48);
  }
  else
  {
    LODWORD(v19) = WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink;
    v20 = 0;
  }
  QosLineCreate((_DWORD)v16 + 24, v18, a7, v19, v20);
  *((_DWORD *)v16 + 61) = 1;
  if ( a2 )
  {
    Flink = *(struct _LIST_ENTRY **)(a2 + 40);
    _InterlockedAdd((volatile signed __int32 *)(a2 + 100), 1u);
    v16[32] = a2;
  }
  else
  {
    Flink = WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink;
  }
  RWLock = NdisAllocateRWLock(Flink);
  v16[2] = RWLock;
  if ( !RWLock )
  {
    PcpLineDereference(v16);
    return 3221225626LL;
  }
  _InterlockedAdd((volatile signed __int32 *)v16 + 62, 1u);
  NdisAcquireRWLockWrite(PcgLineListLock, &LockState, 0);
  v23 = (_QWORD *)qword_140018628;
  if ( *(PVOID **)qword_140018628 != &PcgLineList )
    __fastfail(3u);
  *v16 = &PcgLineList;
  v24 = PcgLineListLock;
  v16[1] = v23;
  *v23 = v16;
  qword_140018628 = (__int64)v16;
  NdisReleaseRWLock(v24, &LockState);
  if ( a3 || (v25 = PcpLineAllocId(v16), v25 >= 0) )
  {
    *a1 = v16;
    return 0;
  }
  else
  {
    PcpLineDestroy(v16);
    return (unsigned int)v25;
  }
}

```

## disassembly

```asm
0x140001884  mov     r11, rsp
0x140001887  push    rbx
0x140001888  push    rbp
0x140001889  push    rsi
0x14000188a  push    rdi
0x14000188b  push    r12
0x14000188d  push    r13
0x14000188f  push    r14
0x140001891  push    r15
0x140001893  sub     rsp, 38h
0x140001897  movzx   ebp, [rsp+78h+arg_20]
0x14000189f  xor     eax, eax
0x1400018a1  movzx   esi, r9w
0x1400018a5  mov     r12b, r8b
0x1400018a8  mov     rdi, rdx
0x1400018ab  mov     [r11+20h], ax
0x1400018b0  mov     r15, rcx
0x1400018b3  mov     [r11+22h], al
0x1400018b7  lea     r10d, [rbp+158h]
0x1400018be  xor     r13d, r13d
0x1400018c1  add     r10d, esi
0x1400018c4  mov     [rcx], r13
0x1400018c7  mov     edx, r10d
0x1400018ca  lea     ecx, [rax+40h]
0x1400018cd  mov     r8d, 656C6350h
0x1400018d3  mov     r14d, r10d
0x1400018d6  call    cs:__imp_ExAllocatePool2
0x1400018dd  nop     dword ptr [rax+rax+00h]
0x1400018e2  mov     rbx, rax
0x1400018e5  test    rax, rax
0x1400018e8  jnz     short loc_1400018F4
0x1400018ea  mov     eax, 0C000009Ah
0x1400018ef  jmp     loc_140001A6F
0x1400018f4  mov     r8, r14; Size
0x1400018f7  xor     edx, edx; Val
0x1400018f9  mov     rcx, rbx; void *
0x1400018fc  call    memset
0x140001901  test    si, si
0x140001904  jz      short loc_14000191B
0x140001906  lea     rax, [rbx+158h]
0x14000190d  mov     [rbx+10Ah], si
0x140001914  mov     [rbx+110h], rax
0x14000191b  test    bp, bp
0x14000191e  jz      short loc_140001938
0x140001920  lea     rcx, [rsi+158h]
0x140001927  mov     [rbx+11Ah], bp
0x14000192e  add     rcx, rbx
0x140001931  mov     [rbx+120h], rcx
0x140001938  mov     eax, [rsp+78h+arg_38]
0x14000193f  mov     esi, 1
0x140001944  mov     rdx, [rsp+78h+arg_28]
0x14000194c  mov     [rbx+130h], eax
0x140001952  mov     eax, [rsp+78h+arg_40]
0x140001959  mov     [rbx+134h], eax
0x14000195f  mov     [rbx+0F8h], esi
0x140001965  mov     [rbx+128h], rdx
0x14000196c  test    rdi, rdi
0x14000196f  jz      short loc_14000197B
0x140001971  mov     r9, [rdi+28h]
0x140001975  mov     rax, [rdi+30h]
0x140001979  jmp     short loc_140001985
0x14000197b  mov     r9, cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink
0x140001982  mov     rax, r13
0x140001985  mov     r8, [rsp+78h+arg_30]
0x14000198d  lea     rcx, [rbx+18h]
0x140001991  mov     [rsp+78h+var_58], rax
0x140001996  call    QosLineCreate
0x14000199b  mov     [rbx+0F4h], esi
0x1400019a1  test    rdi, rdi
0x1400019a4  jz      short loc_1400019B7
0x1400019a6  mov     rcx, [rdi+28h]
0x1400019aa  lock add [rdi+64h], esi
0x1400019ae  mov     [rbx+100h], rdi
0x1400019b5  jmp     short loc_1400019BE
0x1400019b7  mov     rcx, cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink; NdisHandle
0x1400019be  call    cs:__imp_NdisAllocateRWLock
0x1400019c5  nop     dword ptr [rax+rax+00h]
0x1400019ca  mov     [rbx+10h], rax
0x1400019ce  test    rax, rax
0x1400019d1  jnz     short loc_1400019E0
0x1400019d3  mov     rcx, rbx; P
0x1400019d6  call    PcpLineDereference
0x1400019db  jmp     loc_1400018EA
0x1400019e0  lock add [rbx+0F8h], esi
0x1400019e7  mov     rcx, cs:PcgLineListLock; Lock
0x1400019ee  lea     rdx, [rsp+78h+LockState]; LockState
0x1400019f6  xor     r8d, r8d; Flags
0x1400019f9  call    cs:__imp_NdisAcquireRWLockWrite
0x140001a00  nop     dword ptr [rax+rax+00h]
0x140001a05  mov     rax, cs:qword_140018628
0x140001a0c  lea     rcx, PcgLineList
0x140001a13  cmp     [rax], rcx
0x140001a16  jz      short loc_140001A1F
0x140001a18  mov     ecx, 3
0x140001a1d  int     29h; Win8: RtlFailFast(ecx)
0x140001a1f  mov     [rbx], rcx
0x140001a22  lea     rdx, [rsp+78h+LockState]; LockState
0x140001a2a  mov     rcx, cs:PcgLineListLock; Lock
0x140001a31  mov     [rbx+8], rax
0x140001a35  mov     [rax], rbx
0x140001a38  mov     cs:qword_140018628, rbx
0x140001a3f  call    cs:__imp_NdisReleaseRWLock
0x140001a46  nop     dword ptr [rax+rax+00h]
0x140001a4b  test    r12b, r12b
0x140001a4e  jnz     short loc_140001A6A
0x140001a50  mov     rcx, rbx
0x140001a53  call    PcpLineAllocId
0x140001a58  mov     edi, eax
0x140001a5a  test    eax, eax
0x140001a5c  jns     short loc_140001A6A
0x140001a5e  mov     rcx, rbx; P
0x140001a61  call    PcpLineDestroy
0x140001a66  mov     eax, edi
0x140001a68  jmp     short loc_140001A6F
0x140001a6a  mov     [r15], rbx
0x140001a6d  xor     eax, eax
0x140001a6f  add     rsp, 38h
0x140001a73  pop     r15
0x140001a75  pop     r14
0x140001a77  pop     r13
0x140001a79  pop     r12
0x140001a7b  pop     rdi
0x140001a7c  pop     rsi
0x140001a7d  pop     rbp
0x140001a7e  pop     rbx
0x140001a7f  retn
```
