# MRxDAVHandleGeneralCancellation

- ea: `0x140004f50`
- end: `0x140005029`
- name: `MRxDAVHandleGeneralCancellation`
- size: `217`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400044b0`

## callees

- `0x140001b64`
- `0x140004f50`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140004f82`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140004f82`
- `ntoskrnl!KeSetEvent` at `0x140005011`
- `ntoskrnl!KeSetEvent` at `0x140005011`
- `rdbss!RxCompleteRequestEx` at `0x140004ff7`
- `rdbss!RxCompleteRequestEx` at `0x140004ff7`

## pseudocode

```c
__int64 __fastcall MRxDAVHandleGeneralCancellation(__int64 a1, int a2)
{
  __int64 v2; // rsi
  __int64 v5; // rbx
  HANDLE CurrentThreadId; // rax
  int v7; // edx
  bool v8; // zf

  v2 = *(_QWORD *)(a1 + 80);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v5 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    CurrentThreadId = PsGetCurrentThreadId();
    WPP_SF_qqq(v5, 24, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids, CurrentThreadId, a1, v2);
  }
  v7 = a2 != 0 ? -1073741536 : -1073741643;
  *(_DWORD *)(a1 + 128) = v7;
  v8 = *(_DWORD *)(a1 + 52) == 0;
  *(_QWORD *)(a1 + 136) = 0;
  if ( v8 )
  {
    KeSetEvent((PRKEVENT)(a1 + 448), 0, 0);
  }
  else
  {
    *(_DWORD *)(*(_QWORD *)(v2 + 40) + 48LL) = v7;
    *(_QWORD *)(*(_QWORD *)(v2 + 40) + 56LL) = *(_QWORD *)(a1 + 136);
    RxCompleteRequestEx(v2, *(_QWORD *)(v2 + 40), *(unsigned int *)(a1 + 128));
  }
  return 0;
}

```

## disassembly

```asm
0x140004f50  push    rbx
0x140004f52  push    rbp
0x140004f53  push    rsi
0x140004f54  push    rdi
0x140004f55  sub     rsp, 38h
0x140004f59  mov     rsi, [rcx+50h]
0x140004f5d  mov     ebp, edx
0x140004f5f  mov     rdi, rcx
0x140004f62  mov     rbx, cs:WPP_GLOBAL_Control
0x140004f69  lea     rax, WPP_GLOBAL_Control
0x140004f70  cmp     rbx, rax
0x140004f73  jz      short loc_140004FAF
0x140004f75  test    dword ptr [rbx+2Ch], 4000h
0x140004f7c  jz      short loc_140004FAF
0x140004f7e  mov     rbx, [rbx+18h]
0x140004f82  call    cs:__imp_PsGetCurrentThreadId
0x140004f89  nop     dword ptr [rax+rax+00h]
0x140004f8e  mov     edx, 18h
0x140004f93  mov     [rsp+58h+var_30], rsi
0x140004f98  mov     r9, rax
0x140004f9b  mov     [rsp+58h+var_38], rdi
0x140004fa0  lea     r8, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids
0x140004fa7  mov     rcx, rbx
0x140004faa  call    WPP_SF_qqq
0x140004faf  neg     ebp
0x140004fb1  sbb     edx, edx
0x140004fb3  and     edx, 6Bh
0x140004fb6  add     edx, 0C00000B5h
0x140004fbc  mov     [rdi+80h], edx
0x140004fc2  cmp     dword ptr [rdi+34h], 0
0x140004fc6  mov     qword ptr [rdi+88h], 0
0x140004fd1  jz      short loc_140005005
0x140004fd3  mov     rax, [rsi+28h]
0x140004fd7  mov     rcx, rsi
0x140004fda  mov     [rax+30h], edx
0x140004fdd  mov     rdx, [rsi+28h]
0x140004fe1  mov     rax, [rdi+88h]
0x140004fe8  mov     [rdx+38h], rax
0x140004fec  mov     r8d, [rdi+80h]
0x140004ff3  mov     rdx, [rsi+28h]
0x140004ff7  call    cs:__imp_RxCompleteRequestEx
0x140004ffe  nop     dword ptr [rax+rax+00h]
0x140005003  jmp     short loc_14000501D
0x140005005  lea     rcx, [rdi+1C0h]; Event
0x14000500c  xor     r8d, r8d; Wait
0x14000500f  xor     edx, edx; Increment
0x140005011  call    cs:__imp_KeSetEvent
0x140005018  nop     dword ptr [rax+rax+00h]
0x14000501d  xor     eax, eax
0x14000501f  add     rsp, 38h
0x140005023  pop     rdi
0x140005024  pop     rsi
0x140005025  pop     rbp
0x140005026  pop     rbx
0x140005027  retn
```
