# RDPDYN_HandleGetNextDevMgmtEventIOCTL

- ea: `0x140001f10`
- end: `0x14000215a`
- name: `RDPDYN_HandleGetNextDevMgmtEventIOCTL`
- size: `586`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14002b930`

## callees

- `0x140001660`
- `0x140001f10`
- `0x14000231c`
- `0x1400025ac`
- `0x14000327c`
- `0x140004168`
- `0x140004438`
- `0x140004604`
- `0x14001aac4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140002081`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002081`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001fcc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001fcc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002044`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400020c1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002125`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002044`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400020c1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002125`
- `ntoskrnl!IofCompleteRequest` at `0x140001fa2`
- `ntoskrnl!IofCompleteRequest` at `0x14000210e`
- `ntoskrnl!IofCompleteRequest` at `0x140002144`
- `ntoskrnl!IofCompleteRequest` at `0x140001fa2`
- `ntoskrnl!IofCompleteRequest` at `0x14000210e`
- `ntoskrnl!IofCompleteRequest` at `0x140002144`

## pseudocode

```c
__int64 __fastcall RDPDYN_HandleGetNextDevMgmtEventIOCTL(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  __int64 v4; // rax
  unsigned int *v5; // rdi
  unsigned int v6; // ebp
  unsigned int v8; // r15d
  KIRQL v9; // si
  int v10; // ecx
  __int64 v11; // rcx
  __int64 v12; // rcx
  unsigned int v13; // r14d
  PVOID v14; // rdi
  RefCount *v15; // rsi
  unsigned int v16; // ebx
  unsigned int v17; // eax
  unsigned int v18; // edi
  __int64 v19; // [rsp+70h] [rbp+8h] BYREF
  PVOID P; // [rsp+78h] [rbp+10h] BYREF
  RefCount *v21; // [rsp+80h] [rbp+18h] BYREF

  v19 = a1;
  v2 = *(_QWORD *)(a2 + 184);
  LODWORD(v19) = 0;
  P = 0;
  v21 = 0;
  v4 = *(_QWORD *)(v2 + 48);
  if ( v4 && (v5 = *(unsigned int **)(v4 + 24)) != 0 )
  {
    v6 = *v5;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids, v6);
    if ( WPP_MAIN_CB.DeviceQueue.Lock )
    {
      v8 = *(_DWORD *)(v2 + 8);
      v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)WPP_MAIN_CB.DeviceQueue.Lock);
      if ( (unsigned int)RDPEVNTLIST_PeekNextEvent(v10, v6, (unsigned int)&P, (unsigned int)&v19, (__int64)&v21) )
      {
        v13 = RDPDYN_DevMgmtEventSize(P, (unsigned int)v19);
        if ( v8 < v13 + 8 )
        {
          KeReleaseSpinLock((PKSPIN_LOCK)WPP_MAIN_CB.DeviceQueue.Lock, v9);
          return CompleteIRPWithResizeMsg((PIRP)a2);
        }
        else
        {
          RDPEVNTLIST_DequeueEvent(v12, v6, &v19, &P, 0);
          KeReleaseSpinLock((PKSPIN_LOCK)WPP_MAIN_CB.DeviceQueue.Lock, v9);
          v14 = P;
          v15 = v21;
          v16 = CompleteIRPWithDevMgmtEvent((PIRP)a2, v13, v19, P, (__int64)v21);
          if ( v14 )
            ExFreePoolWithTag(v14, 0);
          if ( v15 )
            RefCount::Release(v15);
          return v16;
        }
      }
      else
      {
        v17 = RDPEVNTLIST_EnqueueRequest(v11, *v5, a2);
        v18 = v17;
        if ( v17 )
        {
          *(_DWORD *)(a2 + 48) = v17;
          IofCompleteRequest((PIRP)a2, 0);
        }
        else
        {
          v18 = 259;
          *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
          _InterlockedExchange64((volatile __int64 *)(a2 + 104), (__int64)DevMgmtEventRequestIRPCancel);
        }
        KeReleaseSpinLock((PKSPIN_LOCK)WPP_MAIN_CB.DeviceQueue.Lock, v9);
        return v18;
      }
    }
    else
    {
      *(_DWORD *)(a2 + 48) = -1073741808;
      IofCompleteRequest((PIRP)a2, 0);
      return 3221225488LL;
    }
  }
  else
  {
    *(_DWORD *)(a2 + 48) = -1073741808;
    IofCompleteRequest((PIRP)a2, 0);
    return 3221225488LL;
  }
}

```

## disassembly

```asm
0x140001f10  mov     r11, rsp
0x140001f13  mov     [r11+8], rcx
0x140001f17  push    rbx
0x140001f18  push    rsi
0x140001f19  push    rdi
0x140001f1a  push    r12
0x140001f1c  sub     rsp, 48h
0x140001f20  mov     rsi, [rdx+0B8h]
0x140001f27  xor     r12d, r12d
0x140001f2a  mov     rbx, rdx
0x140001f2d  mov     [r11+8], r12d
0x140001f31  mov     [r11+10h], r12
0x140001f35  mov     [r11+18h], r12
0x140001f39  mov     rax, [rsi+30h]
0x140001f3d  test    rax, rax
0x140001f40  jz      loc_140002138
0x140001f46  mov     rdi, [rax+18h]
0x140001f4a  test    rdi, rdi
0x140001f4d  jz      loc_140002138
0x140001f53  mov     [r11-28h], rbp
0x140001f57  mov     ebp, [rdi]
0x140001f59  mov     rcx, cs:WPP_GLOBAL_Control
0x140001f60  lea     rax, WPP_GLOBAL_Control
0x140001f67  cmp     rcx, rax
0x140001f6a  jz      short loc_140001F8A
0x140001f6c  cmp     byte ptr [rcx+29h], 4
0x140001f70  jb      short loc_140001F8A
0x140001f72  mov     rcx, [rcx+18h]
0x140001f76  lea     r8, WPP_7cfd4f0a915a35e66f2fc58ee32aeefb_Traceguids
0x140001f7d  mov     edx, 19h
0x140001f82  mov     r9d, ebp
0x140001f85  call    WPP_SF_d
0x140001f8a  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.Lock; SpinLock
0x140001f91  test    rcx, rcx
0x140001f94  jnz     short loc_140001FC3
0x140001f96  xor     edx, edx; PriorityBoost
0x140001f98  mov     dword ptr [rbx+30h], 0C0000010h
0x140001f9f  mov     rcx, rbx; Irp
0x140001fa2  call    cs:__imp_IofCompleteRequest
0x140001fa9  nop     dword ptr [rax+rax+00h]
0x140001fae  mov     rbp, [rsp+68h+var_28]
0x140001fb3  mov     eax, 0C0000010h
0x140001fb8  add     rsp, 48h
0x140001fbc  pop     r12
0x140001fbe  pop     rdi
0x140001fbf  pop     rsi
0x140001fc0  pop     rbx
0x140001fc1  retn
0x140001fc3  mov     [rsp+68h+var_38], r15
0x140001fc8  mov     r15d, [rsi+8]
0x140001fcc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001fd3  nop     dword ptr [rax+rax+00h]
0x140001fd8  lea     r9, [rsp+68h+arg_0]
0x140001fdd  mov     edx, ebp
0x140001fdf  movzx   esi, al
0x140001fe2  lea     r8, [rsp+68h+P]
0x140001fe7  lea     rax, [rsp+68h+arg_10]
0x140001fef  mov     [rsp+68h+var_48], rax
0x140001ff4  call    RDPEVNTLIST_PeekNextEvent
0x140001ff9  test    eax, eax
0x140001ffb  jz      loc_1400020D9
0x140002001  mov     edx, dword ptr [rsp+68h+arg_0]
0x140002005  mov     rcx, [rsp+68h+P]
0x14000200a  mov     [rsp+68h+var_30], r14
0x14000200f  call    RDPDYN_DevMgmtEventSize
0x140002014  mov     r14d, eax
0x140002017  lea     edi, [rax+8]
0x14000201a  cmp     r15d, edi
0x14000201d  jb      loc_1400020B6
0x140002023  lea     r9, [rsp+68h+P]
0x140002028  mov     [rsp+68h+var_48], r12
0x14000202d  lea     r8, [rsp+68h+arg_0]
0x140002032  mov     edx, ebp
0x140002034  call    RDPEVNTLIST_DequeueEvent
0x140002039  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.Lock; SpinLock
0x140002040  movzx   edx, sil; NewIrql
0x140002044  call    cs:__imp_KeReleaseSpinLock
0x14000204b  nop     dword ptr [rax+rax+00h]
0x140002050  mov     rdi, [rsp+68h+P]
0x140002055  mov     edx, r14d; Size
0x140002058  mov     rsi, [rsp+68h+arg_10]
0x140002060  mov     r9, rdi
0x140002063  mov     r8d, dword ptr [rsp+68h+arg_0]
0x140002068  mov     rcx, rbx; Irp
0x14000206b  mov     [rsp+68h+var_48], rsi; __int64
0x140002070  call    CompleteIRPWithDevMgmtEvent
0x140002075  mov     ebx, eax
0x140002077  test    rdi, rdi
0x14000207a  jz      short loc_14000208D
0x14000207c  xor     edx, edx; Tag
0x14000207e  mov     rcx, rdi; P
0x140002081  call    cs:__imp_ExFreePoolWithTag
0x140002088  nop     dword ptr [rax+rax+00h]
0x14000208d  test    rsi, rsi
0x140002090  jz      short loc_14000209A
0x140002092  mov     rcx, rsi; this
0x140002095  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x14000209a  mov     eax, ebx
0x14000209c  mov     r14, [rsp+68h+var_30]
0x1400020a1  mov     r15, [rsp+68h+var_38]
0x1400020a6  mov     rbp, [rsp+68h+var_28]
0x1400020ab  add     rsp, 48h
0x1400020af  pop     r12
0x1400020b1  pop     rdi
0x1400020b2  pop     rsi
0x1400020b3  pop     rbx
0x1400020b4  retn
0x1400020b6  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.Lock; SpinLock
0x1400020bd  movzx   edx, sil; NewIrql
0x1400020c1  call    cs:__imp_KeReleaseSpinLock
0x1400020c8  nop     dword ptr [rax+rax+00h]
0x1400020cd  mov     edx, edi
0x1400020cf  mov     rcx, rbx; Irp
0x1400020d2  call    CompleteIRPWithResizeMsg
0x1400020d7  jmp     short loc_14000209C
0x1400020d9  mov     edx, [rdi]
0x1400020db  mov     r8, rbx
0x1400020de  call    RDPEVNTLIST_EnqueueRequest
0x1400020e3  mov     edi, eax
0x1400020e5  test    eax, eax
0x1400020e7  jnz     short loc_140002106
0x1400020e9  mov     rax, [rbx+0B8h]
0x1400020f0  mov     edi, 103h
0x1400020f5  or      byte ptr [rax+3], 1
0x1400020f9  lea     rax, ?DevMgmtEventRequestIRPCancel@@YAXPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; DevMgmtEventRequestIRPCancel(_DEVICE_OBJECT *,_IRP *)
0x140002100  xchg    rax, [rbx+68h]
0x140002104  jmp     short loc_14000211A
0x140002106  xor     edx, edx; PriorityBoost
0x140002108  mov     [rbx+30h], eax
0x14000210b  mov     rcx, rbx; Irp
0x14000210e  call    cs:__imp_IofCompleteRequest
0x140002115  nop     dword ptr [rax+rax+00h]
0x14000211a  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.Lock; SpinLock
0x140002121  movzx   edx, sil; NewIrql
0x140002125  call    cs:__imp_KeReleaseSpinLock
0x14000212c  nop     dword ptr [rax+rax+00h]
0x140002131  mov     eax, edi
0x140002133  jmp     loc_1400020A1
0x140002138  mov     dword ptr [rdx+30h], 0C0000010h
0x14000213f  mov     rcx, rbx; Irp
0x140002142  xor     edx, edx; PriorityBoost
0x140002144  call    cs:__imp_IofCompleteRequest
0x14000214b  nop     dword ptr [rax+rax+00h]
0x140002150  mov     eax, 0C0000010h
0x140002155  jmp     loc_1400020AB
```
