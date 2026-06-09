# addRequestToPriorityQueue

- ea: `0x1400039d4`
- end: `0x140003aa0`
- name: `addRequestToPriorityQueue`
- size: `204`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140003268`
- `0x140003520`
- `0x1400037ec`

## callees

- `0x140003970`
- `0x1400039d4`

## import_xrefs

- `ntoskrnl!KeBugCheck` at `0x1400039eb`
- `ntoskrnl!KeBugCheck` at `0x1400039eb`

## pseudocode

```c
PDEVICE_OBJECT *__fastcall addRequestToPriorityQueue(__int64 a1)
{
  __int64 v1; // rdx
  char *v2; // r8
  bool v3; // zf
  __int64 v4; // r9
  _QWORD *v5; // r10
  unsigned int v6; // eax
  int v7; // r9d
  PDEVICE_OBJECT *result; // rax

  v1 = *(unsigned int *)(a1 + 128);
  if ( (unsigned int)(v1 - 1) > 0x1E )
    KeBugCheck(0x6C746166u);
  v2 = g_priorityQueueSw;
  v3 = (*(_DWORD *)(a1 + 92) & 1) == 0;
  *(_DWORD *)(a1 + 152) = 6;
  if ( v3 )
    v2 = g_priorityQueueHw;
  v4 = (__int64)&v2[16 * v1 + 8];
  v5 = *(_QWORD **)(v4 + 8);
  if ( *v5 != v4 )
    __fastfail(3u);
  *(_QWORD *)(a1 + 136) = v4;
  *(_QWORD *)(a1 + 144) = v5;
  *v5 = a1 + 136;
  *(_QWORD *)(v4 + 8) = a1 + 136;
  v6 = *((_DWORD *)v2 + 1);
  if ( v6 <= (unsigned int)v1 )
    v6 = v1;
  v7 = ++*(_DWORD *)v2;
  *((_DWORD *)v2 + 1) = v6;
  g_nBytesInQueues += *(unsigned int *)(a1 + 32);
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = (PDEVICE_OBJECT *)HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( ((unsigned __int8)result & 4) != 0 )
      return (PDEVICE_OBJECT *)WPP_SF_dDD(
                                 WPP_GLOBAL_Control->AttachedDevice,
                                 v1,
                                 WPP_GLOBAL_Control,
                                 *(unsigned int *)(a1 + 92),
                                 v1,
                                 v7);
  }
  return result;
}

```

## disassembly

```asm
0x1400039d4  sub     rsp, 38h
0x1400039d8  mov     edx, [rcx+80h]
0x1400039de  lea     eax, [rdx-1]
0x1400039e1  cmp     eax, 1Eh
0x1400039e4  jbe     short loc_1400039F8
0x1400039e6  mov     ecx, 6C746166h; BugCheckCode
0x1400039eb  call    cs:__imp_KeBugCheck
0x1400039f8  mov     eax, [rcx+5Ch]
0x1400039fb  lea     r8, g_priorityQueueSw
0x140003a02  test    al, 1
0x140003a04  mov     dword ptr [rcx+98h], 6
0x140003a0e  lea     rax, g_priorityQueueHw
0x140003a15  cmovz   r8, rax
0x140003a19  mov     rax, rdx
0x140003a1c  shl     rax, 4
0x140003a20  lea     r9, [r8+8]
0x140003a24  add     r9, rax
0x140003a27  mov     r10, [r9+8]
0x140003a2b  cmp     [r10], r9
0x140003a2e  jz      short loc_140003A37
0x140003a30  mov     ecx, 3
0x140003a35  int     29h; Win8: RtlFailFast(ecx)
0x140003a37  lea     rax, [rcx+88h]
0x140003a3e  mov     [rax], r9
0x140003a41  mov     [rax+8], r10
0x140003a45  mov     [r10], rax
0x140003a48  mov     [r9+8], rax
0x140003a4c  mov     eax, [r8+4]
0x140003a50  cmp     eax, edx
0x140003a52  cmovbe  eax, edx
0x140003a55  inc     dword ptr [r8]
0x140003a58  mov     r9d, [r8]
0x140003a5b  mov     [r8+4], eax
0x140003a5f  mov     eax, [rcx+20h]
0x140003a62  add     cs:g_nBytesInQueues, rax
0x140003a69  mov     r8, cs:WPP_GLOBAL_Control
0x140003a70  lea     rax, WPP_GLOBAL_Control
0x140003a77  cmp     r8, rax
0x140003a7a  jz      short loc_140003A9A
0x140003a7c  mov     eax, [r8+2Ch]
0x140003a80  test    al, 4
0x140003a82  jz      short loc_140003A9A
0x140003a84  mov     [rsp+38h+var_10], r9d
0x140003a89  mov     r9d, [rcx+5Ch]
0x140003a8d  mov     rcx, [r8+18h]
0x140003a91  mov     [rsp+38h+var_18], edx
0x140003a95  call    WPP_SF_dDD
0x140003a9a  add     rsp, 38h
0x140003a9e  retn
```
