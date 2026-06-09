# MRxDAVHandleCreateVNetRootCancellation

- ea: `0x140004e98`
- end: `0x140004f47`
- name: `MRxDAVHandleCreateVNetRootCancellation`
- size: `175`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400044b0`

## callees

- `0x140001b64`
- `0x140004e98`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140004ece`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140004ece`
- `ntoskrnl!KeSetEvent` at `0x140004f28`
- `ntoskrnl!KeSetEvent` at `0x140004f28`

## pseudocode

```c
__int64 __fastcall MRxDAVHandleCreateVNetRootCancellation(__int64 a1)
{
  __int64 v1; // rsi
  __int64 v3; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v5; // rax

  v1 = *(_QWORD *)(a1 + 80);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v3 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    CurrentThreadId = PsGetCurrentThreadId();
    WPP_SF_qqq(v3, 31, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids, CurrentThreadId, a1, v1);
  }
  v5 = *(_QWORD *)(v1 + 216);
  if ( v5 )
    v5 = *(_QWORD *)(v5 + 40);
  *(_DWORD *)(v5 + 100) = 1;
  *(_DWORD *)(a1 + 128) = -1073741643;
  KeSetEvent((PRKEVENT)(a1 + 448), 0, 0);
  return 0;
}

```

## disassembly

```asm
0x140004e98  mov     [rsp+arg_0], rbx
0x140004e9d  mov     [rsp+arg_8], rsi
0x140004ea2  push    rdi
0x140004ea3  sub     rsp, 30h
0x140004ea7  mov     rsi, [rcx+50h]
0x140004eab  mov     rdi, rcx
0x140004eae  mov     rbx, cs:WPP_GLOBAL_Control
0x140004eb5  lea     rax, WPP_GLOBAL_Control
0x140004ebc  cmp     rbx, rax
0x140004ebf  jz      short loc_140004EFB
0x140004ec1  test    dword ptr [rbx+2Ch], 2000h
0x140004ec8  jz      short loc_140004EFB
0x140004eca  mov     rbx, [rbx+18h]
0x140004ece  call    cs:__imp_PsGetCurrentThreadId
0x140004ed5  nop     dword ptr [rax+rax+00h]
0x140004eda  mov     edx, 1Fh
0x140004edf  mov     [rsp+38h+var_10], rsi
0x140004ee4  mov     r9, rax
0x140004ee7  mov     [rsp+38h+var_18], rdi
0x140004eec  lea     r8, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids
0x140004ef3  mov     rcx, rbx
0x140004ef6  call    WPP_SF_qqq
0x140004efb  mov     rax, [rsi+0D8h]
0x140004f02  test    rax, rax
0x140004f05  jz      short loc_140004F0B
0x140004f07  mov     rax, [rax+28h]
0x140004f0b  mov     dword ptr [rax+64h], 1
0x140004f12  lea     rcx, [rdi+1C0h]; Event
0x140004f19  xor     r8d, r8d; Wait
0x140004f1c  mov     dword ptr [rdi+80h], 0C00000B5h
0x140004f26  xor     edx, edx; Increment
0x140004f28  call    cs:__imp_KeSetEvent
0x140004f2f  nop     dword ptr [rax+rax+00h]
0x140004f34  mov     rbx, [rsp+38h+arg_0]
0x140004f39  xor     eax, eax
0x140004f3b  mov     rsi, [rsp+38h+arg_8]
0x140004f40  add     rsp, 30h
0x140004f44  pop     rdi
0x140004f45  retn
```
