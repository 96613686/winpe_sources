# UpdateGlobalCallStats

- ea: `0x140018b24`
- end: `0x140018c82`
- name: `UpdateGlobalCallStats`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x14000f2ec`

## callees

- `0x140018b24`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140018c6f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018c6f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018b41`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018b41`

## pseudocode

```c
void __fastcall UpdateGlobalCallStats(_DWORD *a1)
{
  char v2; // al

  if ( a1[88] )
  {
    v2 = KeAcquireSpinLockRaiseToDpc(&g_lockStats);
    *(_QWORD *)&g_stats = g_stats + 1;
    byte_14000A2A8 = v2;
    DWORD2(g_stats) += a1[88];
    HIDWORD(g_stats) += a1[89];
    LODWORD(xmmword_14000A2D0) = a1[90] + xmmword_14000A2D0;
    DWORD1(xmmword_14000A2D0) += a1[91];
    DWORD2(xmmword_14000A2D0) += a1[92];
    HIDWORD(xmmword_14000A2D0) += a1[93];
    LODWORD(xmmword_14000A2E0) = a1[94] + xmmword_14000A2E0;
    DWORD1(xmmword_14000A2E0) += a1[95];
    DWORD2(xmmword_14000A2E0) += a1[96];
    HIDWORD(xmmword_14000A2E0) += a1[97];
    LODWORD(xmmword_14000A2F0) = a1[98] + xmmword_14000A2F0;
    DWORD1(xmmword_14000A2F0) += a1[99];
    DWORD2(xmmword_14000A2F0) += a1[100];
    HIDWORD(xmmword_14000A2F0) += a1[101];
    LODWORD(xmmword_14000A300) = a1[102] + xmmword_14000A300;
    DWORD1(xmmword_14000A300) += a1[103];
    DWORD2(xmmword_14000A300) += a1[104];
    HIDWORD(xmmword_14000A300) += a1[105];
    LODWORD(xmmword_14000A310) = a1[106] + xmmword_14000A310;
    DWORD1(xmmword_14000A310) += a1[107];
    DWORD2(xmmword_14000A310) += a1[108];
    HIDWORD(xmmword_14000A310) += a1[109];
    KeReleaseSpinLock(&g_lockStats, v2);
  }
}

```

## disassembly

```asm
0x140018b24  push    rbx
0x140018b26  sub     rsp, 20h
0x140018b2a  cmp     dword ptr [rcx+160h], 0
0x140018b31  mov     rbx, rcx
0x140018b34  jz      loc_140018C7B
0x140018b3a  lea     rcx, g_lockStats; SpinLock
0x140018b41  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140018b48  nop     dword ptr [rax+rax+00h]
0x140018b4d  inc     qword ptr cs:g_stats
0x140018b54  mov     r8b, al
0x140018b57  mov     cs:byte_14000A2A8, al
0x140018b5d  mov     edx, [rbx+160h]
0x140018b63  add     dword ptr cs:g_stats+8, edx
0x140018b69  mov     edx, [rbx+164h]
0x140018b6f  add     dword ptr cs:g_stats+0Ch, edx
0x140018b75  mov     dl, r8b; NewIrql
0x140018b78  mov     ecx, [rbx+168h]
0x140018b7e  add     dword ptr cs:xmmword_14000A2D0, ecx
0x140018b84  mov     ecx, [rbx+16Ch]
0x140018b8a  add     dword ptr cs:xmmword_14000A2D0+4, ecx
0x140018b90  mov     ecx, [rbx+170h]
0x140018b96  add     dword ptr cs:xmmword_14000A2D0+8, ecx
0x140018b9c  mov     ecx, [rbx+174h]
0x140018ba2  add     dword ptr cs:xmmword_14000A2D0+0Ch, ecx
0x140018ba8  lea     rcx, g_lockStats; SpinLock
0x140018baf  mov     eax, [rbx+178h]
0x140018bb5  add     dword ptr cs:xmmword_14000A2E0, eax
0x140018bbb  mov     eax, [rbx+17Ch]
0x140018bc1  add     dword ptr cs:xmmword_14000A2E0+4, eax
0x140018bc7  mov     eax, [rbx+180h]
0x140018bcd  add     dword ptr cs:xmmword_14000A2E0+8, eax
0x140018bd3  mov     eax, [rbx+184h]
0x140018bd9  add     dword ptr cs:xmmword_14000A2E0+0Ch, eax
0x140018bdf  mov     eax, [rbx+188h]
0x140018be5  add     dword ptr cs:xmmword_14000A2F0, eax
0x140018beb  mov     eax, [rbx+18Ch]
0x140018bf1  add     dword ptr cs:xmmword_14000A2F0+4, eax
0x140018bf7  mov     eax, [rbx+190h]
0x140018bfd  add     dword ptr cs:xmmword_14000A2F0+8, eax
0x140018c03  mov     eax, [rbx+194h]
0x140018c09  add     dword ptr cs:xmmword_14000A2F0+0Ch, eax
0x140018c0f  mov     eax, [rbx+198h]
0x140018c15  add     dword ptr cs:xmmword_14000A300, eax
0x140018c1b  mov     eax, [rbx+19Ch]
0x140018c21  add     dword ptr cs:xmmword_14000A300+4, eax
0x140018c27  mov     eax, [rbx+1A0h]
0x140018c2d  add     dword ptr cs:xmmword_14000A300+8, eax
0x140018c33  mov     eax, [rbx+1A4h]
0x140018c39  add     dword ptr cs:xmmword_14000A300+0Ch, eax
0x140018c3f  mov     eax, [rbx+1A8h]
0x140018c45  add     dword ptr cs:xmmword_14000A310, eax
0x140018c4b  mov     eax, [rbx+1ACh]
0x140018c51  add     dword ptr cs:xmmword_14000A310+4, eax
0x140018c57  mov     eax, [rbx+1B0h]
0x140018c5d  add     dword ptr cs:xmmword_14000A310+8, eax
0x140018c63  mov     eax, [rbx+1B4h]
0x140018c69  add     dword ptr cs:xmmword_14000A310+0Ch, eax
0x140018c6f  call    cs:__imp_KeReleaseSpinLock
0x140018c76  nop     dword ptr [rax+rax+00h]
0x140018c7b  add     rsp, 20h
0x140018c7f  pop     rbx
0x140018c80  retn
```
