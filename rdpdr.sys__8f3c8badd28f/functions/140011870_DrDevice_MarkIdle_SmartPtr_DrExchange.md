# DrDevice::MarkIdle(SmartPtr<DrExchange> &)

- ea: `0x140011870`
- end: `0x140011953`
- name: `?MarkIdle@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@@Z`
- size: `227`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140012ff0`
- `0x1400131e0`
- `0x1400137c0`
- `0x140013e70`
- `0x140014360`

## callees

- `0x14000324c`
- `0x140006560`
- `0x140011870`
- `0x140024180`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x14001188b`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001188b`
- `ntoskrnl!ExReleaseFastMutex` at `0x140011907`
- `ntoskrnl!ExReleaseFastMutex` at `0x140011907`

## pseudocode

```c
void __fastcall DrDevice::MarkIdle(__int64 a1, __int64 a2)
{
  struct _RX_CONTEXT *v3; // rdi
  __int64 v4; // rbx

  v3 = 0;
  ExAcquireFastMutex(&DrMutex);
  v4 = *(_QWORD *)(*(_QWORD *)a2 + 32LL);
  *(_DWORD *)(v4 + 24) = 0;
  if ( *(_DWORD *)(v4 + 28) && *(_QWORD *)(v4 + 48) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x41u,
        (__int64)WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids);
    v3 = *(struct _RX_CONTEXT **)(v4 + 48);
    *(_QWORD *)(v4 + 48) = 0;
    v3->MRxContext[2] = 0;
  }
  if ( *(_DWORD *)(v4 + 32) )
    *(_QWORD *)(*(_QWORD *)a2 + 32LL) = 0;
  ExReleaseFastMutex(&DrMutex);
  if ( v3 )
  {
    DrDevice::CompleteRxContext(v3, -1073741536, 0);
    if ( *(_DWORD *)(v4 + 32) )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 16LL))(v4, 1);
  }
}

```

## disassembly

```asm
0x140011870  mov     [rsp+arg_0], rbx
0x140011875  mov     [rsp+arg_8], rsi
0x14001187a  push    rdi
0x14001187b  sub     rsp, 20h
0x14001187f  lea     rcx, ?DrMutex@@3U_FAST_MUTEX@@A; FastMutex
0x140011886  mov     rsi, rdx
0x140011889  xor     edi, edi
0x14001188b  call    cs:__imp_ExAcquireFastMutex
0x140011892  nop     dword ptr [rax+rax+00h]
0x140011897  mov     rax, [rsi]
0x14001189a  mov     rbx, [rax+20h]
0x14001189e  mov     [rbx+18h], edi
0x1400118a1  cmp     [rbx+1Ch], edi
0x1400118a4  jz      short loc_1400118EF
0x1400118a6  cmp     [rbx+30h], rdi
0x1400118aa  jz      short loc_1400118EF
0x1400118ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400118b3  lea     rax, WPP_GLOBAL_Control
0x1400118ba  cmp     rcx, rax
0x1400118bd  jz      short loc_1400118D8
0x1400118bf  cmp     byte ptr [rcx+29h], 5
0x1400118c3  jb      short loc_1400118D8
0x1400118c5  mov     rcx, [rcx+18h]
0x1400118c9  lea     edx, [rdi+41h]
0x1400118cc  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x1400118d3  call    WPP_SF_
0x1400118d8  mov     rdi, [rbx+30h]
0x1400118dc  mov     qword ptr [rbx+30h], 0
0x1400118e4  mov     qword ptr [rdi+0D0h], 0
0x1400118ef  cmp     dword ptr [rbx+20h], 0
0x1400118f3  jz      short loc_140011900
0x1400118f5  mov     rax, [rsi]
0x1400118f8  mov     qword ptr [rax+20h], 0
0x140011900  lea     rcx, ?DrMutex@@3U_FAST_MUTEX@@A; FastMutex
0x140011907  call    cs:__imp_ExReleaseFastMutex
0x14001190e  nop     dword ptr [rax+rax+00h]
0x140011913  test    rdi, rdi
0x140011916  jz      short loc_140011942
0x140011918  xor     r8d, r8d; unsigned int
0x14001191b  mov     edx, 0C0000120h; int
0x140011920  mov     rcx, rdi; RxContext
0x140011923  call    ?CompleteRxContext@DrDevice@@KAXPEAU_RX_CONTEXT@@JK@Z; DrDevice::CompleteRxContext(_RX_CONTEXT *,long,ulong)
0x140011928  cmp     dword ptr [rbx+20h], 0
0x14001192c  jz      short loc_140011942
0x14001192e  mov     rax, [rbx]
0x140011931  mov     edx, 1
0x140011936  mov     rcx, rbx
0x140011939  mov     rax, [rax+10h]
0x14001193d  call    _guard_dispatch_icall
0x140011942  mov     rbx, [rsp+28h+arg_0]
0x140011947  mov     rsi, [rsp+28h+arg_8]
0x14001194c  add     rsp, 20h
0x140011950  pop     rdi
0x140011951  retn
```
