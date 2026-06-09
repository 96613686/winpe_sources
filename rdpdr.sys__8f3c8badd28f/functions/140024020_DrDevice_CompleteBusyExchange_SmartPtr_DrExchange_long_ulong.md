# DrDevice::CompleteBusyExchange(SmartPtr<DrExchange> &,long,ulong)

- ea: `0x140024020`
- end: `0x140024173`
- name: `?CompleteBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@JK@Z`
- size: `339`
- prototype: `__int64 __fastcall(__int64, __int64, int, unsigned int)`
- caller_count: `17`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400010fc`
- `0x1400127a0`
- `0x140012f40`
- `0x140012ff0`
- `0x1400131e0`
- `0x1400137c0`
- `0x140013e70`
- `0x140014360`
- `0x140014b40`
- `0x140014bf0`
- `0x140014ca0`
- `0x14001f5fc`
- `0x14001fbd8`
- `0x14001fd20`
- `0x140022ab0`
- `0x140023030`
- `0x140023500`

## callees

- `0x140001660`
- `0x14000324c`
- `0x140006560`
- `0x140024020`
- `0x140024180`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x140024049`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400240af`
- `ntoskrnl!ExAcquireFastMutex` at `0x140024049`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400240af`
- `ntoskrnl!ExReleaseFastMutex` at `0x140024085`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400240e1`
- `ntoskrnl!ExReleaseFastMutex` at `0x140024142`
- `ntoskrnl!ExReleaseFastMutex` at `0x140024085`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400240e1`
- `ntoskrnl!ExReleaseFastMutex` at `0x140024142`
- `rdbss!RxMapAndDissociateMidFromContext` at `0x140024125`
- `rdbss!RxMapAndDissociateMidFromContext` at `0x140024125`

## pseudocode

```c
__int64 __fastcall DrDevice::CompleteBusyExchange(__int64 a1, __int64 a2, int a3, unsigned int a4)
{
  _QWORD *v8; // rbx
  struct _RX_CONTEXT *v9; // rdi
  __int64 v10; // rdi
  struct _RX_MID_ATLAS *v11; // rcx
  PVOID ContextPointer; // [rsp+50h] [rbp+8h] BYREF

  ExAcquireFastMutex(&DrMutex);
  v8 = *(_QWORD **)(*(_QWORD *)a2 + 32LL);
  v9 = (struct _RX_CONTEXT *)v8[6];
  v8[6] = 0;
  *(_QWORD *)(*(_QWORD *)a2 + 32LL) = 0;
  if ( v9 )
  {
    v9->MRxContext[2] = 0;
    ExReleaseFastMutex(&DrMutex);
    DrDevice::CompleteRxContext(v9, a3, a4);
  }
  else
  {
    ExReleaseFastMutex(&DrMutex);
  }
  v10 = *(_QWORD *)(a1 + 32);
  ContextPointer = 0;
  ExAcquireFastMutex(&DrMutex);
  v11 = *(struct _RX_MID_ATLAS **)(v10 + 720);
  if ( v11 )
  {
    RxMapAndDissociateMidFromContext(v11, *(_WORD *)(*(_QWORD *)a2 + 48LL), &ContextPointer);
    if ( ContextPointer )
      RefCount::Release((RefCount *)ContextPointer);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_e59448592ec538b831cf1e49bf008190_Traceguids);
  }
  ExReleaseFastMutex(&DrMutex);
  return (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v8 + 16LL))(v8, 1);
}

```

## disassembly

```asm
0x140024020  mov     [rsp+arg_8], rbx
0x140024025  mov     [rsp+arg_10], rbp
0x14002402a  push    rsi
0x14002402b  push    rdi
0x14002402c  push    r12
0x14002402e  push    r14
0x140024030  push    r15
0x140024032  sub     rsp, 20h
0x140024036  mov     rsi, rcx
0x140024039  mov     ebp, r9d
0x14002403c  lea     rcx, ?DrMutex@@3U_FAST_MUTEX@@A; FastMutex
0x140024043  mov     r15d, r8d
0x140024046  mov     r14, rdx
0x140024049  call    cs:__imp_ExAcquireFastMutex
0x140024050  nop     dword ptr [rax+rax+00h]
0x140024055  mov     rbx, [r14]
0x140024058  lea     rcx, ?DrMutex@@3U_FAST_MUTEX@@A; FastMutex
0x14002405f  xor     r12d, r12d
0x140024062  mov     rbx, [rbx+20h]
0x140024066  mov     rdi, [rbx+30h]
0x14002406a  mov     [rbx+30h], r12
0x14002406e  mov     rax, [r14]
0x140024071  mov     [rax+20h], r12
0x140024075  test    rdi, rdi
0x140024078  jz      loc_140024142
0x14002407e  mov     [rdi+0D0h], r12
0x140024085  call    cs:__imp_ExReleaseFastMutex
0x14002408c  nop     dword ptr [rax+rax+00h]
0x140024091  mov     r8d, ebp; unsigned int
0x140024094  mov     edx, r15d; int
0x140024097  mov     rcx, rdi; RxContext
0x14002409a  call    ?CompleteRxContext@DrDevice@@KAXPEAU_RX_CONTEXT@@JK@Z; DrDevice::CompleteRxContext(_RX_CONTEXT *,long,ulong)
0x14002409f  mov     rdi, [rsi+20h]
0x1400240a3  lea     rcx, ?DrMutex@@3U_FAST_MUTEX@@A; FastMutex
0x1400240aa  mov     [rsp+48h+ContextPointer], r12
0x1400240af  call    cs:__imp_ExAcquireFastMutex
0x1400240b6  nop     dword ptr [rax+rax+00h]
0x1400240bb  mov     rcx, [rdi+2D0h]; MidAtlas
0x1400240c2  test    rcx, rcx
0x1400240c5  jnz     short loc_140024119
0x1400240c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400240ce  lea     rax, WPP_GLOBAL_Control
0x1400240d5  cmp     rcx, rax
0x1400240d8  jnz     short loc_140024153
0x1400240da  lea     rcx, ?DrMutex@@3U_FAST_MUTEX@@A; FastMutex
0x1400240e1  call    cs:__imp_ExReleaseFastMutex
0x1400240e8  nop     dword ptr [rax+rax+00h]
0x1400240ed  mov     rax, [rbx]
0x1400240f0  mov     edx, 1
0x1400240f5  mov     rcx, rbx
0x1400240f8  mov     rax, [rax+10h]
0x1400240fc  call    _guard_dispatch_icall
0x140024101  mov     rbx, [rsp+48h+arg_8]
0x140024106  mov     rbp, [rsp+48h+arg_10]
0x14002410b  add     rsp, 20h
0x14002410f  pop     r15
0x140024111  pop     r14
0x140024113  pop     r12
0x140024115  pop     rdi
0x140024116  pop     rsi
0x140024117  retn
0x140024119  mov     rdx, [r14]
0x14002411c  lea     r8, [rsp+48h+ContextPointer]; ContextPointer
0x140024121  movzx   edx, word ptr [rdx+30h]; Mid
0x140024125  call    cs:__imp_RxMapAndDissociateMidFromContext
0x14002412c  nop     dword ptr [rax+rax+00h]
0x140024131  mov     rcx, [rsp+48h+ContextPointer]; this
0x140024136  test    rcx, rcx
0x140024139  jz      short loc_1400240DA
0x14002413b  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x140024140  jmp     short loc_1400240DA
0x140024142  call    cs:__imp_ExReleaseFastMutex
0x140024149  nop     dword ptr [rax+rax+00h]
0x14002414e  jmp     loc_14002409F
0x140024153  cmp     byte ptr [rcx+29h], 5
0x140024157  jb      short loc_1400240DA
0x140024159  mov     rcx, [rcx+18h]
0x14002415d  lea     r8, WPP_e59448592ec538b831cf1e49bf008190_Traceguids
0x140024164  mov     edx, 0Fh
0x140024169  call    WPP_SF_
0x14002416e  jmp     loc_1400240DA
```
