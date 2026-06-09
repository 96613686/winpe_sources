# MRxDAVCleanupFobx

- ea: `0x1400234b0`
- end: `0x14002351b`
- name: `MRxDAVCleanupFobx`
- size: `107`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140002ac4`
- `0x1400234b0`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x1400234e5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400234e5`

## pseudocode

```c
__int64 __fastcall MRxDAVCleanupFobx(__int64 a1)
{
  __int64 v1; // rdi
  __int64 v2; // rbx
  unsigned int CurrentThreadId; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v1 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v2 = *(_QWORD *)(a1 + 56) + 360LL;
    CurrentThreadId = (unsigned int)PsGetCurrentThreadId();
    WPP_SF_qZ(v1, 27, (unsigned int)WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids, CurrentThreadId, v2);
  }
  return 0;
}

```

## disassembly

```asm
0x1400234b0  mov     [rsp+arg_0], rbx
0x1400234b5  push    rdi
0x1400234b6  sub     rsp, 30h
0x1400234ba  mov     rdi, cs:WPP_GLOBAL_Control
0x1400234c1  lea     rax, WPP_GLOBAL_Control
0x1400234c8  cmp     rdi, rax
0x1400234cb  jz      short loc_14002350D
0x1400234cd  test    dword ptr [rdi+2Ch], 4000h
0x1400234d4  jz      short loc_14002350D
0x1400234d6  mov     rbx, [rcx+38h]
0x1400234da  mov     rdi, [rdi+18h]
0x1400234de  add     rbx, 168h
0x1400234e5  call    cs:__imp_PsGetCurrentThreadId
0x1400234ec  nop     dword ptr [rax+rax+00h]
0x1400234f1  mov     edx, 1Bh
0x1400234f6  mov     [rsp+38h+var_18], rbx
0x1400234fb  mov     r9, rax
0x1400234fe  lea     r8, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids
0x140023505  mov     rcx, rdi
0x140023508  call    WPP_SF_qZ
0x14002350d  mov     rbx, [rsp+38h+arg_0]
0x140023512  xor     eax, eax
0x140023514  add     rsp, 30h
0x140023518  pop     rdi
0x140023519  retn
```
