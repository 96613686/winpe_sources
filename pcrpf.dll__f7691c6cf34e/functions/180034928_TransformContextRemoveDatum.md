# TransformContextRemoveDatum

- ea: `0x180034928`
- end: `0x1800349b1`
- name: `TransformContextRemoveDatum`
- size: `137`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180033e04`
- `0x1800341e0`

## callees

- `0x18002d5ec`
- `0x1800348d0`
- `0x180034928`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034983`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034983`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034997`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034997`

## string_xrefs

- `0x180034957`: `TransformContextRemoveDatum`

## pseudocode

```c
int TransformContextRemoveDatum()
{
  __int64 Datum; // rax
  _QWORD *v1; // rbx
  __int64 v2; // rdx
  _QWORD *v3; // rax
  HANDLE ProcessHeap; // rax

  Datum = TransformContextFindDatum();
  v1 = (_QWORD *)Datum;
  if ( Datum )
  {
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
      0x976u,
      "TransformContextRemoveDatum",
      "Removing existing datum: '%ws'",
      Datum + 4);
    v2 = v1[17];
    if ( *(_QWORD **)(v2 + 8) != v1 + 17 || (v3 = (_QWORD *)v1[18], (_QWORD *)*v3 != v1 + 17) )
      __fastfail(3u);
    *v3 = v2;
    *(_QWORD *)(v2 + 8) = v3;
    ProcessHeap = GetProcessHeap();
    LODWORD(Datum) = HeapFree(ProcessHeap, 0, v1);
  }
  return Datum;
}

```

## disassembly

```asm
0x180034928  push    rbx
0x18003492a  sub     rsp, 30h
0x18003492e  call    TransformContextFindDatum
0x180034933  mov     rbx, rax
0x180034936  test    rax, rax
0x180034939  jz      short loc_1800349A3
0x18003493b  lea     rcx, [rax+4]
0x18003493f  mov     edx, 976h; unsigned int
0x180034944  mov     [rsp+38h+var_18], rcx
0x180034949  lea     r9, aRemovingExisti; "Removing existing datum: '%ws'"
0x180034950  lea     rcx, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180034957  lea     r8, aTransformconte; "TransformContextRemoveDatum"
0x18003495e  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180034963  lea     rcx, [rbx+88h]
0x18003496a  mov     rdx, [rcx]
0x18003496d  cmp     [rdx+8], rcx
0x180034971  jnz     short loc_1800349AA
0x180034973  mov     rax, [rcx+8]
0x180034977  cmp     [rax], rcx
0x18003497a  jnz     short loc_1800349AA
0x18003497c  mov     [rax], rdx
0x18003497f  mov     [rdx+8], rax
0x180034983  call    cs:__imp_GetProcessHeap
0x18003498a  nop     dword ptr [rax+rax+00h]
0x18003498f  mov     r8, rbx; lpMem
0x180034992  xor     edx, edx; dwFlags
0x180034994  mov     rcx, rax; hHeap
0x180034997  call    cs:__imp_HeapFree
0x18003499e  nop     dword ptr [rax+rax+00h]
0x1800349a3  add     rsp, 30h
0x1800349a7  pop     rbx
0x1800349a8  retn
0x1800349aa  mov     ecx, 3
0x1800349af  int     29h; Win8: RtlFailFast(ecx)
```
