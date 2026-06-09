# MRxDAVFinalizeNetRoot

- ea: `0x1400194f0`
- end: `0x1400195a5`
- name: `MRxDAVFinalizeNetRoot`
- size: `181`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1400017e4`
- `0x140001b64`
- `0x1400192b8`
- `0x1400194f0`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14001951d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140019562`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001951d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140019562`

## pseudocode

```c
__int64 __fastcall MRxDAVFinalizeNetRoot(__int64 a1)
{
  __int64 v2; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v4; // rbx
  __int64 v5; // rdi
  HANDLE v6; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v2 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_qq(v2, 64, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, CurrentThreadId, a1);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v4 = *(_QWORD *)(a1 + 40);
      v5 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v6 = PsGetCurrentThreadId();
      WPP_SF_qqq(v5, 65, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v6, v4, a1);
    }
  }
  MRxDAVDereferenceNetRootContext(*(char **)(a1 + 40));
  return 0;
}

```

## disassembly

```asm
0x1400194f0  push    rbx
0x1400194f2  push    rsi
0x1400194f3  push    rdi
0x1400194f4  push    r14
0x1400194f6  sub     rsp, 38h
0x1400194fa  mov     rsi, rcx
0x1400194fd  mov     rbx, cs:WPP_GLOBAL_Control
0x140019504  lea     r14, WPP_GLOBAL_Control
0x14001950b  cmp     rbx, r14
0x14001950e  jz      short loc_14001958F
0x140019510  test    dword ptr [rbx+2Ch], 2000h
0x140019517  jz      short loc_140019545
0x140019519  mov     rbx, [rbx+18h]
0x14001951d  call    cs:__imp_PsGetCurrentThreadId
0x140019524  nop     dword ptr [rax+rax+00h]
0x140019529  mov     edx, 40h ; '@'
0x14001952e  mov     [rsp+58h+var_38], rsi
0x140019533  mov     r9, rax
0x140019536  lea     r8, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x14001953d  mov     rcx, rbx
0x140019540  call    WPP_SF_qq
0x140019545  mov     rdi, cs:WPP_GLOBAL_Control
0x14001954c  cmp     rdi, r14
0x14001954f  jz      short loc_14001958F
0x140019551  test    dword ptr [rdi+2Ch], 2000h
0x140019558  jz      short loc_14001958F
0x14001955a  mov     rbx, [rsi+28h]
0x14001955e  mov     rdi, [rdi+18h]
0x140019562  call    cs:__imp_PsGetCurrentThreadId
0x140019569  nop     dword ptr [rax+rax+00h]
0x14001956e  mov     edx, 41h ; 'A'
0x140019573  mov     [rsp+58h+var_30], rsi
0x140019578  mov     r9, rax
0x14001957b  mov     [rsp+58h+var_38], rbx
0x140019580  lea     r8, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x140019587  mov     rcx, rdi
0x14001958a  call    WPP_SF_qqq
0x14001958f  mov     rcx, [rsi+28h]; P
0x140019593  call    MRxDAVDereferenceNetRootContext
0x140019598  xor     eax, eax
0x14001959a  add     rsp, 38h
0x14001959e  pop     r14
0x1400195a0  pop     rdi
0x1400195a1  pop     rsi
0x1400195a2  pop     rbx
0x1400195a3  retn
```
