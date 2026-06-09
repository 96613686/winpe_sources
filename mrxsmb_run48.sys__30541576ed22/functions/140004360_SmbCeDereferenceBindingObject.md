# SmbCeDereferenceBindingObject

- ea: `0x140004360`
- end: `0x14000447a`
- name: `SmbCeDereferenceBindingObject`
- size: `282`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x140001630`
- `0x1400017f0`
- `0x140002750`
- `0x140003550`
- `0x140005540`
- `0x140005740`
- `0x140006680`
- `0x1400093a0`
- `0x14000a030`
- `0x140012840`
- `0x140022950`
- `0x140037d60`
- `0x14003fbb0`
- `0x1400434d0`
- `0x140045c60`

## callees

- `0x140004360`
- `0x140037fa4`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x140004447`
- `ntoskrnl!KeBugCheckEx` at `0x14000446d`
- `ntoskrnl!KeBugCheckEx` at `0x140004447`
- `ntoskrnl!KeBugCheckEx` at `0x14000446d`
- `rdbss!RxPostToWorkerThread` at `0x1400043e8`
- `rdbss!RxPostToWorkerThread` at `0x1400043e8`

## pseudocode

```c
int __fastcall SmbCeDereferenceBindingObject(ULONG_PTR BugCheckParameter2)
{
  signed __int32 v2; // ebx
  PDEVICE_OBJECT *v3; // rax
  __int64 v4; // rcx
  signed __int32 v5; // edx
  char v6; // cc
  signed __int32 v7; // edx
  signed __int32 v8; // eax
  signed __int32 v9; // eax

  v2 = _InterlockedDecrement((volatile signed __int32 *)(BugCheckParameter2 + 8));
  v3 = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    LODWORD(v3) = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( ((unsigned __int8)v3 & 0x40) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      LODWORD(v3) = WPP_SF_qDD(
                      WPP_GLOBAL_Control->AttachedDevice,
                      15,
                      &WPP_1342ee1acfa830e98f791bdb08bd815d_Traceguids,
                      BugCheckParameter2,
                      v2 + 1,
                      v2);
  }
  if ( !v2 )
  {
    v4 = *(_QWORD *)(BugCheckParameter2 + 24);
    *(_DWORD *)(BugCheckParameter2 + 12) = 10;
    *(_QWORD *)(BugCheckParameter2 + 208) = BugCheckParameter2 + 200;
    *(_QWORD *)(BugCheckParameter2 + 200) = BugCheckParameter2 + 200;
    _InterlockedIncrement((volatile signed __int32 *)(v4 + 2668));
    v5 = _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 2656), 1u);
    v6 = (v5 + 1 < 0) ^ __OFADD__(1, v5) | (v5 == -1);
    v7 = v5 + 1;
    if ( v6 )
      KeBugCheckEx(0x27u, 0xA0001u, BugCheckParameter2, v7, 6u);
    v8 = _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 2664), 1u);
    v6 = (v8 + 1 < 0) ^ __OFADD__(1, v8) | (v8 == -1);
    v9 = v8 + 1;
    if ( v6 )
      KeBugCheckEx(0x27u, 0xA0001u, BugCheckParameter2, v9, 8u);
    LODWORD(v3) = RxPostToWorkerThread(
                    (PRDBSS_DEVICE_OBJECT)v4,
                    NormalWorkQueue,
                    (PRX_WORK_QUEUE_ITEM)(BugCheckParameter2 + 200),
                    (PRX_WORKERTHREAD_ROUTINE)SmbCeTearDownBindingObject,
                    (PVOID)BugCheckParameter2);
  }
  return (int)v3;
}

```

## disassembly

```asm
0x140004360  mov     [rsp+arg_0], rbx
0x140004365  push    rdi
0x140004366  sub     rsp, 30h
0x14000436a  mov     rdi, rcx
0x14000436d  mov     ebx, 0FFFFFFFFh
0x140004372  lock xadd [rcx+8], ebx
0x140004377  dec     ebx
0x140004379  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140004380  lea     rax, WPP_GLOBAL_Control
0x140004387  cmp     rcx, rax
0x14000438a  jz      short loc_140004393
0x14000438c  mov     eax, [rcx+2Ch]
0x14000438f  test    al, 40h
0x140004391  jnz     short loc_140004400
0x140004393  test    ebx, ebx
0x140004395  jnz     short loc_1400043F4
0x140004397  mov     rcx, [rdi+18h]; pMRxDeviceObject
0x14000439b  lea     r8, [rdi+0C8h]; pWorkQueueItem
0x1400043a2  mov     dword ptr [rdi+0Ch], 0Ah
0x1400043a9  mov     [r8+8], r8
0x1400043ad  mov     [r8], r8
0x1400043b0  lock inc dword ptr [rcx+0A6Ch]
0x1400043b7  mov     eax, 1
0x1400043bc  mov     edx, eax
0x1400043be  lock xadd [rcx+0A60h], edx
0x1400043c6  add     edx, eax
0x1400043c8  jle     short loc_14000442E
0x1400043ca  lock xadd [rcx+0A68h], eax
0x1400043d2  add     eax, 1
0x1400043d5  jle     short loc_140004454
0x1400043d7  lea     r9, SmbCeTearDownBindingObject; Routine
0x1400043de  mov     [rsp+38h+pContext], rdi; pContext
0x1400043e3  mov     edx, 3; WorkQueueType
0x1400043e8  call    cs:__imp_RxPostToWorkerThread
0x1400043ef  nop     dword ptr [rax+rax+00h]
0x1400043f4  mov     rbx, [rsp+38h+arg_0]
0x1400043f9  add     rsp, 30h
0x1400043fd  pop     rdi
0x1400043fe  retn
0x140004400  cmp     byte ptr [rcx+29h], 4
0x140004404  jb      short loc_140004393
0x140004406  mov     rcx, [rcx+18h]
0x14000440a  lea     eax, [rbx+1]
0x14000440d  mov     edx, 0Fh
0x140004412  mov     [rsp+38h+var_10], ebx
0x140004416  mov     r9, rdi
0x140004419  mov     dword ptr [rsp+38h+pContext], eax
0x14000441d  lea     r8, WPP_1342ee1acfa830e98f791bdb08bd815d_Traceguids
0x140004424  call    WPP_SF_qDD
0x140004429  jmp     loc_140004393
0x14000442e  movsxd  r9, edx; BugCheckParameter3
0x140004431  mov     r8, rdi; BugCheckParameter2
0x140004434  mov     edx, 0A0001h; BugCheckParameter1
0x140004439  mov     [rsp+38h+pContext], 6; BugCheckParameter4
0x140004442  mov     ecx, 27h ; '''; BugCheckCode
0x140004447  call    cs:__imp_KeBugCheckEx
0x140004454  movsxd  r9, eax; BugCheckParameter3
0x140004457  mov     r8, rdi; BugCheckParameter2
0x14000445a  mov     edx, 0A0001h; BugCheckParameter1
0x14000445f  mov     [rsp+38h+pContext], 8; BugCheckParameter4
0x140004468  mov     ecx, 27h ; '''; BugCheckCode
0x14000446d  call    cs:__imp_KeBugCheckEx
```
