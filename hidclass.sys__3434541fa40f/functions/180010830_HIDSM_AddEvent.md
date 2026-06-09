# HIDSM_AddEvent

- ea: `0x180010830`
- end: `0x1800109a6`
- name: `HIDSM_AddEvent`
- size: `374`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x180003900`
- `0x18000ef30`
- `0x18000fda0`
- `0x18000fe00`
- `0x180010010`
- `0x1800101a0`
- `0x180010200`
- `0x180010454`
- `0x180010814`

## callees

- `0x18000ddc8`
- `0x180010830`
- `0x1800109ac`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x180010909`
- `ntoskrnl!KeReleaseSpinLock` at `0x180010909`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180010848`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180010848`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1800108d8`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1800108d8`

## pseudocode

```c
void __fastcall HIDSM_AddEvent(KSPIN_LOCK *Context, int a2)
{
  KSPIN_LOCK *v2; // rbp
  char v5; // si
  KIRQL v6; // cl
  KSPIN_LOCK v7; // rbx
  NTSTATUS v8; // eax
  int v9; // edx
  int v10; // r8d
  KIRQL v11; // [rsp+88h] [rbp+10h]

  v2 = Context + 105;
  v5 = 1;
  v6 = KeAcquireSpinLockRaiseToDpc(Context + 105);
  v11 = v6;
  *((_DWORD *)Context + *((unsigned __int8 *)Context + 833) + 192) = a2;
  *((_BYTE *)Context + 833) = (*((_BYTE *)Context + 833) + 1) & 0xF;
  *((_DWORD *)Context + *((unsigned __int8 *)Context + 949) + 221) = a2;
  *((_BYTE *)Context + 949) = (*((_BYTE *)Context + 949) + 1) & 0xF;
  if ( !*((_BYTE *)Context + 848) )
  {
    v7 = Context[120];
    *((_BYTE *)Context + 848) = 1;
    v8 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v7 + 640), "State Machine Tag", File, 1u, 0x20u);
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        v5 = 0;
      }
      if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v9) = v5;
        LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_qL(
          WPP_GLOBAL_Control->AttachedDevice,
          v9,
          v10,
          *(_QWORD *)(v7 + 672),
          2,
          9,
          11,
          (__int64)WPP_f42040bb991b3e95d6c62b961b09000a_Traceguids,
          *(_QWORD *)v7,
          v8);
      }
    }
    HIDSM_RunStateMachine(Context);
    v6 = v11;
  }
  KeReleaseSpinLock(v2, v6);
}

```

## disassembly

```asm
0x180010830  push    rbx
0x180010832  push    rbp
0x180010833  push    rsi
0x180010834  push    rdi
0x180010835  sub     rsp, 58h
0x180010839  lea     rbp, [rcx+348h]
0x180010840  mov     rdi, rcx
0x180010843  mov     rcx, rbp; SpinLock
0x180010846  mov     ebx, edx
0x180010848  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x18001084f  nop     dword ptr [rax+rax+00h]
0x180010854  movzx   edx, byte ptr [rdi+341h]
0x18001085b  mov     esi, 1
0x180010860  mov     cl, al
0x180010862  mov     [rsp+78h+arg_8], al
0x180010869  mov     [rdi+rdx*4+300h], ebx
0x180010870  mov     dl, [rdi+341h]
0x180010876  add     dl, sil
0x180010879  and     dl, 0Fh
0x18001087c  mov     [rdi+341h], dl
0x180010882  movzx   eax, byte ptr [rdi+3B5h]
0x180010889  mov     [rdi+rax*4+374h], ebx
0x180010890  mov     al, [rdi+3B5h]
0x180010896  add     al, sil
0x180010899  and     al, 0Fh
0x18001089b  mov     [rdi+3B5h], al
0x1800108a1  cmp     byte ptr [rdi+350h], 0
0x1800108a8  jnz     short loc_180010904
0x1800108aa  mov     rbx, [rdi+3C0h]
0x1800108b1  lea     r8, File; File
0x1800108b8  mov     r9d, esi; Line
0x1800108bb  mov     [rdi+350h], sil
0x1800108c2  lea     rdx, StateMachineTag; "State Machine Tag"
0x1800108c9  mov     [rsp+78h+RemlockSize], 20h ; ' '; RemlockSize
0x1800108d1  lea     rcx, [rbx+280h]; RemoveLock
0x1800108d8  call    cs:__imp_IoAcquireRemoveLockEx
0x1800108df  nop     dword ptr [rax+rax+00h]
0x1800108e4  test    eax, eax
0x1800108e6  js      short loc_18001091F
0x1800108e8  lea     r8, [rsp+78h+arg_8]
0x1800108f0  mov     edx, 3E8h
0x1800108f5  mov     rcx, rdi; Context
0x1800108f8  call    HIDSM_RunStateMachine
0x1800108fd  mov     cl, [rsp+78h+arg_8]
0x180010904  mov     dl, cl; NewIrql
0x180010906  mov     rcx, rbp; SpinLock
0x180010909  call    cs:__imp_KeReleaseSpinLock
0x180010910  nop     dword ptr [rax+rax+00h]
0x180010915  add     rsp, 58h
0x180010919  pop     rdi
0x18001091a  pop     rsi
0x18001091b  pop     rbp
0x18001091c  pop     rbx
0x18001091d  retn
0x18001091f  mov     r10, cs:WPP_GLOBAL_Control
0x180010926  lea     rcx, WPP_GLOBAL_Control
0x18001092d  cmp     r10, rcx
0x180010930  jz      short loc_180010943
0x180010932  test    dword ptr [r10+2Ch], 100h
0x18001093a  jz      short loc_180010943
0x18001093c  cmp     byte ptr [r10+29h], 2
0x180010941  jnb     short loc_180010946
0x180010943  xor     sil, sil
0x180010946  lea     rcx, WPP_RECORDER_INITIALIZED
0x18001094d  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x180010954  setnz   r8b
0x180010958  test    sil, sil
0x18001095b  jnz     short loc_180010962
0x18001095d  test    r8b, r8b
0x180010960  jz      short loc_1800108E8
0x180010962  mov     r9, [rbx+2A0h]
0x180010969  mov     dl, sil
0x18001096c  mov     rcx, [r10+18h]
0x180010970  mov     [rsp+78h+var_30], eax
0x180010974  mov     rax, [rbx]
0x180010977  mov     [rsp+78h+var_38], rax
0x18001097c  lea     rax, WPP_f42040bb991b3e95d6c62b961b09000a_Traceguids
0x180010983  mov     [rsp+78h+var_40], rax
0x180010988  mov     [rsp+78h+var_48], 0Bh
0x18001098f  mov     [rsp+78h+var_50], 9
0x180010997  mov     byte ptr [rsp+78h+RemlockSize], 2
0x18001099c  call    WPP_RECORDER_AND_TRACE_SF_qL
0x1800109a1  jmp     loc_1800108E8
```
