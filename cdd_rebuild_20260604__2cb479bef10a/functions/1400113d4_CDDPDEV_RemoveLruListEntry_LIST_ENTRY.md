# CDDPDEV::RemoveLruListEntry(_LIST_ENTRY *)

- ea: `0x1400113d4`
- end: `0x1400114fd`
- name: `?RemoveLruListEntry@CDDPDEV@@QEAAEPEAU_LIST_ENTRY@@@Z`
- size: `297`
- prototype: `unsigned __int8 __fastcall(CDDPDEV *__hidden this, struct _LIST_ENTRY *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140010c2c`
- `0x140015764`
- `0x1400218e4`

## callees

- `0x1400113d4`

## import_xrefs

- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140011422`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x1400114bf`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140011422`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x1400114bf`
- `watchdog!WdLogSingleEntry0` at `0x14001140c`
- `watchdog!WdLogSingleEntry0` at `0x1400114a8`
- `watchdog!WdLogSingleEntry0` at `0x14001140c`
- `watchdog!WdLogSingleEntry0` at `0x1400114a8`

## pseudocode

```c
char __fastcall CDDPDEV::RemoveLruListEntry(CDDPDEV *this, struct _LIST_ENTRY *a2)
{
  char v2; // di
  __int64 v4; // rdx
  __int64 v5; // rcx
  _QWORD *v6; // rcx
  struct _LIST_ENTRY *Flink; // rax
  struct _LIST_ENTRY *Blink; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  _QWORD *v12; // rax

  v2 = 0;
  if ( *((_BYTE *)this + 12716) )
  {
    if ( *(struct _KTHREAD **)(*((_QWORD *)this + 1600) + 8LL) != KeGetCurrentThread() )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 603;
      v6 = (_QWORD *)WdLogNewEntry5_WdAssertion(v5, v4);
      v6[3] = gCddImageInfo;
      v6[4] = (unsigned int)dword_14003E570;
      v6[5] = 215857758;
      WdLogGlobalForLineNumber = 603;
    }
    if ( a2->Flink )
    {
      if ( !a2->Blink )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 607;
        v12 = (_QWORD *)WdLogNewEntry5_WdAssertion(v11, v10);
        v12[3] = gCddImageInfo;
        v12[4] = (unsigned int)dword_14003E570;
        v12[5] = 215857758;
        WdLogGlobalForLineNumber = 607;
      }
      Flink = a2->Flink;
      if ( a2->Flink->Blink != a2 || (Blink = a2->Blink, Blink->Flink != a2) )
        __fastfail(3u);
      Blink->Flink = Flink;
      v2 = 1;
      Flink->Blink = Blink;
      a2->Flink = 0;
      a2->Blink = 0;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1400113d4  mov     [rsp+arg_0], rbx
0x1400113d9  push    rdi
0x1400113da  sub     rsp, 20h
0x1400113de  xor     dil, dil
0x1400113e1  mov     rbx, rdx
0x1400113e4  cmp     [rcx+31ACh], dil
0x1400113eb  jz      loc_140011494
0x1400113f1  mov     r8, gs:188h
0x1400113fa  mov     rax, [rcx+3200h]
0x140011401  cmp     [rax+8], r8
0x140011405  jz      short loc_140011458
0x140011407  mov     ecx, 1
0x14001140c  call    cs:__imp_WdLogSingleEntry0
0x140011413  nop     dword ptr [rax+rax+00h]
0x140011418  mov     cs:WdLogGlobalForLineNumber, 25Bh
0x140011422  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x140011429  nop     dword ptr [rax+rax+00h]
0x14001142e  mov     rcx, rax
0x140011431  mov     rax, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140011438  mov     [rcx+18h], rax
0x14001143c  mov     eax, cs:dword_14003E570
0x140011442  mov     [rcx+20h], rax
0x140011446  mov     qword ptr [rcx+28h], 0CDDBA5Eh
0x14001144e  mov     cs:WdLogGlobalForLineNumber, 25Bh
0x140011458  cmp     qword ptr [rbx], 0
0x14001145c  jz      short loc_140011494
0x14001145e  cmp     qword ptr [rbx+8], 0
0x140011463  jz      short loc_1400114A3
0x140011465  mov     rax, [rbx]
0x140011468  cmp     [rax+8], rbx
0x14001146c  jnz     loc_1400114F6
0x140011472  mov     rcx, [rbx+8]
0x140011476  cmp     [rcx], rbx
0x140011479  jnz     short loc_1400114F6
0x14001147b  mov     [rcx], rax
0x14001147e  mov     dil, 1
0x140011481  mov     [rax+8], rcx
0x140011485  mov     qword ptr [rbx], 0
0x14001148c  mov     qword ptr [rbx+8], 0
0x140011494  mov     rbx, [rsp+28h+arg_0]
0x140011499  mov     al, dil
0x14001149c  add     rsp, 20h
0x1400114a0  pop     rdi
0x1400114a1  retn
0x1400114a3  mov     ecx, 1
0x1400114a8  call    cs:__imp_WdLogSingleEntry0
0x1400114af  nop     dword ptr [rax+rax+00h]
0x1400114b4  mov     edi, 25Fh
0x1400114b9  mov     cs:WdLogGlobalForLineNumber, edi
0x1400114bf  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x1400114c6  nop     dword ptr [rax+rax+00h]
0x1400114cb  mov     rcx, rax
0x1400114ce  mov     rax, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x1400114d5  mov     [rcx+18h], rax
0x1400114d9  mov     eax, cs:dword_14003E570
0x1400114df  mov     [rcx+20h], rax
0x1400114e3  mov     qword ptr [rcx+28h], 0CDDBA5Eh
0x1400114eb  mov     cs:WdLogGlobalForLineNumber, edi
0x1400114f1  jmp     loc_140011465
0x1400114f6  mov     ecx, 3
0x1400114fb  int     29h; Win8: RtlFailFast(ecx)
```
