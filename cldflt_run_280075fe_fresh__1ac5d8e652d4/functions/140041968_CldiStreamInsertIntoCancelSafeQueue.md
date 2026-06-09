# CldiStreamInsertIntoCancelSafeQueue

- ea: `0x140041968`
- end: `0x140041b87`
- name: `CldiStreamInsertIntoCancelSafeQueue`
- size: `543`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14003fc70`
- `0x140040090`
- `0x1400829e0`

## callees

- `0x140003c50`
- `0x14000abb8`
- `0x14000d868`
- `0x140041968`
- `0x140081134`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400419a3`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400419a3`
- `FLTMGR!FltCbdqInsertIo` at `0x140041a42`
- `FLTMGR!FltCbdqInsertIo` at `0x140041a42`

## pseudocode

```c
__int64 __fastcall CldiStreamInsertIntoCancelSafeQueue(void *a1, struct _FLT_CALLBACK_DATA *a2, __int64 a3, _QWORD *a4)
{
  unsigned int v4; // ebp
  volatile signed __int32 *v8; // rax
  _OWORD *v9; // rax
  volatile signed __int32 *v10; // rax
  PDEVICE_OBJECT p_QueueLinks; // rcx

  v4 = 0;
  if ( !a2 || (a2->Flags & 1) == 0 )
  {
    p_QueueLinks = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids, a2, a1, a4);
    }
    if ( a2 && !a2->QueueContext[1] )
    {
      p_QueueLinks = (PDEVICE_OBJECT)&a2->QueueLinks;
      a2->QueueContext[1] = a1;
      a2->QueueLinks.Blink = &a2->QueueLinks;
      a2->QueueLinks.Flink = &a2->QueueLinks;
    }
    goto LABEL_25;
  }
  v8 = (volatile signed __int32 *)a2->QueueContext[1];
  if ( v8 )
  {
    a4[12] = v8;
    _InterlockedIncrement(v8 + 8);
    p_QueueLinks = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids, a2, a1, a4);
    }
LABEL_25:
    CldiStreamCdqINSERT_IO(p_QueueLinks, a2, a4);
    return v4;
  }
  v9 = ExAllocateFromPagedLookasideList(&stru_140028880);
  if ( v9 )
  {
    *v9 = 0;
    v9[1] = 0;
    v9[2] = 0;
    a2->QueueContext[1] = v9;
    *(_QWORD *)v9 = a2;
    a2->QueueLinks.Blink = &a2->QueueLinks;
    a2->QueueLinks.Flink = &a2->QueueLinks;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids, a2, a1, a4);
    }
    v10 = (volatile signed __int32 *)a2->QueueContext[1];
    a4[12] = v10;
    _InterlockedIncrement(v10 + 8);
    FltCbdqInsertIo(
      (PFLT_CALLBACK_DATA_QUEUE)(*(_QWORD *)(*(_QWORD *)a1 + 8LL) + 144LL),
      a2,
      (PFLT_CALLBACK_DATA_QUEUE_IO_CONTEXT)(a4[12] + 8LL),
      a4);
  }
  else
  {
    v4 = -1073741670;
    HsmDbgBreakOnStatus(3221225626LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqqd(
        WPP_GLOBAL_Control->AttachedDevice,
        13,
        WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids,
        a2,
        a1,
        a4,
        -1073741670);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x140041968  push    rbx
0x14004196a  push    rbp
0x14004196b  push    rsi
0x14004196c  push    rdi
0x14004196d  sub     rsp, 48h
0x140041971  xor     ebp, ebp
0x140041973  mov     rdi, r9
0x140041976  mov     rbx, rdx
0x140041979  mov     rsi, rcx
0x14004197c  test    rdx, rdx
0x14004197f  jz      loc_140041B12
0x140041985  mov     eax, [rdx]
0x140041987  test    al, 1
0x140041989  jz      loc_140041B12
0x14004198f  mov     rax, [rdx+48h]
0x140041993  test    rax, rax
0x140041996  jnz     loc_140041AB8
0x14004199c  lea     rcx, stru_140028880; Lookaside
0x1400419a3  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1400419aa  nop     dword ptr [rax+rax+00h]
0x1400419af  test    rax, rax
0x1400419b2  jz      loc_140041A53
0x1400419b8  xorps   xmm0, xmm0
0x1400419bb  movups  xmmword ptr [rax], xmm0
0x1400419be  movups  xmmword ptr [rax+10h], xmm0
0x1400419c2  movups  xmmword ptr [rax+20h], xmm0
0x1400419c6  mov     [rbx+48h], rax
0x1400419ca  mov     [rax], rbx
0x1400419cd  lea     rax, [rbx+30h]
0x1400419d1  mov     [rax+8], rax
0x1400419d5  mov     [rax], rax
0x1400419d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400419df  lea     rax, WPP_GLOBAL_Control
0x1400419e6  cmp     rcx, rax
0x1400419e9  jz      short loc_140041A1A
0x1400419eb  test    dword ptr [rcx+2Ch], 100h
0x1400419f2  jz      short loc_140041A1A
0x1400419f4  cmp     byte ptr [rcx+29h], 4
0x1400419f8  jb      short loc_140041A1A
0x1400419fa  mov     rcx, [rcx+18h]
0x1400419fe  lea     edx, [rbp+0Eh]
0x140041a01  mov     [rsp+68h+var_40], rdi
0x140041a06  lea     r8, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids
0x140041a0d  mov     r9, rbx
0x140041a10  mov     [rsp+68h+var_48], rsi
0x140041a15  call    WPP_SF_qqq
0x140041a1a  mov     rax, [rbx+48h]
0x140041a1e  mov     [rdi+60h], rax
0x140041a22  lock inc dword ptr [rax+20h]
0x140041a26  mov     rax, [rsi]
0x140041a29  mov     r9, rdi; InsertContext
0x140041a2c  mov     r8, [rdi+60h]
0x140041a30  mov     rdx, rbx; Cbd
0x140041a33  add     r8, 8; Context
0x140041a37  mov     rcx, [rax+8]
0x140041a3b  add     rcx, 90h; Cbdq
0x140041a42  call    cs:__imp_FltCbdqInsertIo
0x140041a49  nop     dword ptr [rax+rax+00h]
0x140041a4e  jmp     loc_140041B7B
0x140041a53  mov     ebp, 0C000009Ah
0x140041a58  mov     ecx, ebp
0x140041a5a  call    HsmDbgBreakOnStatus
0x140041a5f  mov     rcx, cs:WPP_GLOBAL_Control
0x140041a66  lea     rax, WPP_GLOBAL_Control
0x140041a6d  cmp     rcx, rax
0x140041a70  jz      loc_140041B7B
0x140041a76  test    dword ptr [rcx+2Ch], 100h
0x140041a7d  jz      loc_140041B7B
0x140041a83  cmp     byte ptr [rcx+29h], 2
0x140041a87  jb      loc_140041B7B
0x140041a8d  mov     rcx, [rcx+18h]
0x140041a91  lea     r8, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids
0x140041a98  mov     [rsp+68h+var_38], ebp
0x140041a9c  mov     edx, 0Dh
0x140041aa1  mov     [rsp+68h+var_40], rdi
0x140041aa6  mov     r9, rbx
0x140041aa9  mov     [rsp+68h+var_48], rsi
0x140041aae  call    WPP_SF_qqqd
0x140041ab3  jmp     loc_140041B7B
0x140041ab8  mov     [r9+60h], rax
0x140041abc  lock inc dword ptr [rax+20h]
0x140041ac0  mov     rcx, cs:WPP_GLOBAL_Control
0x140041ac7  lea     rax, WPP_GLOBAL_Control
0x140041ace  cmp     rcx, rax
0x140041ad1  jz      loc_140041B70
0x140041ad7  test    dword ptr [rcx+2Ch], 100h
0x140041ade  jz      loc_140041B70
0x140041ae4  cmp     byte ptr [rcx+29h], 4
0x140041ae8  jb      loc_140041B70
0x140041aee  mov     rcx, [rcx+18h]
0x140041af2  lea     r8, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids
0x140041af9  mov     edx, 10h
0x140041afe  mov     [rsp+68h+var_40], rdi
0x140041b03  mov     r9, rbx
0x140041b06  mov     [rsp+68h+var_48], rsi
0x140041b0b  call    WPP_SF_qqq
0x140041b10  jmp     short loc_140041B70
0x140041b12  mov     rcx, cs:WPP_GLOBAL_Control
0x140041b19  lea     rax, WPP_GLOBAL_Control
0x140041b20  cmp     rcx, rax
0x140041b23  jz      short loc_140041B56
0x140041b25  test    dword ptr [rcx+2Ch], 100h
0x140041b2c  jz      short loc_140041B56
0x140041b2e  cmp     byte ptr [rcx+29h], 4
0x140041b32  jb      short loc_140041B56
0x140041b34  mov     rcx, [rcx+18h]
0x140041b38  lea     r8, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids
0x140041b3f  mov     edx, 11h
0x140041b44  mov     [rsp+68h+var_40], rdi
0x140041b49  mov     r9, rbx
0x140041b4c  mov     [rsp+68h+var_48], rsi
0x140041b51  call    WPP_SF_qqq
0x140041b56  test    rbx, rbx
0x140041b59  jz      short loc_140041B70
0x140041b5b  cmp     [rbx+48h], rbp
0x140041b5f  jnz     short loc_140041B70
0x140041b61  lea     rcx, [rbx+30h]
0x140041b65  mov     [rbx+48h], rsi
0x140041b69  mov     [rcx+8], rcx
0x140041b6d  mov     [rcx], rcx
0x140041b70  mov     r8, rdi
0x140041b73  mov     rdx, rbx
0x140041b76  call    CldiStreamCdqINSERT_IO
0x140041b7b  mov     eax, ebp
0x140041b7d  add     rsp, 48h
0x140041b81  pop     rdi
0x140041b82  pop     rsi
0x140041b83  pop     rbp
0x140041b84  pop     rbx
0x140041b85  retn
```
