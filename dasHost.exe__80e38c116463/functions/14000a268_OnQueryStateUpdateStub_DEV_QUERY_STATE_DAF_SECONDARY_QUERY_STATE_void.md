# OnQueryStateUpdateStub(_DEV_QUERY_STATE,_DAF_SECONDARY_QUERY_STATE,void *)

- ea: `0x14000a268`
- end: `0x14000a36c`
- name: `?OnQueryStateUpdateStub@@YAJW4_DEV_QUERY_STATE@@W4_DAF_SECONDARY_QUERY_STATE@@PEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(int, int, struct _PROVIDER_QUERY_ENTRY *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1400173a0`

## callees

- `0x140008eec`
- `0x140008f88`
- `0x140009be0`
- `0x14000a268`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000a2b9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000a2e9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000a2b9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000a2e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a331`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a331`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a2aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a2da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a323`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a2aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a2da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a323`

## pseudocode

```c
__int64 __fastcall OnQueryStateUpdateStub(int a1, int a2, struct _PROVIDER_QUERY_ENTRY *a3)
{
  HANDLE ProcessHeap; // rax
  int v6; // edx
  struct _DAS_HOST_QUERY_RESULT *v7; // rdi
  int v8; // r8d
  unsigned int v9; // ebx
  HANDLE v10; // rax
  _OWORD *v11; // rax
  HANDLE v12; // rax
  int v14; // [rsp+28h] [rbp-40h]

  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      a2,
      (int)a3,
      35,
      &WPP_92038ab37ee4317b05ca4ff2fd992641_Traceguids);
  ProcessHeap = GetProcessHeap();
  v7 = (struct _DAS_HOST_QUERY_RESULT *)HeapAlloc(ProcessHeap, 0, 0x18u);
  if ( !v7 )
  {
    v9 = -2147024882;
    goto LABEL_9;
  }
  *(_OWORD *)v7 = 0;
  *((_QWORD *)v7 + 2) = 0;
  v10 = GetProcessHeap();
  v11 = HeapAlloc(v10, 0, 0x28u);
  if ( v11 )
  {
    *v11 = 0;
    v11[1] = 0;
    *((_QWORD *)v11 + 4) = 0;
    *((_DWORD *)v11 + 2) = a1;
    *((_QWORD *)v7 + 2) = v11;
    v9 = AddToResultList(v7, a3);
    if ( !v9 )
      goto LABEL_9;
  }
  else
  {
    v9 = -2147024882;
  }
  v12 = GetProcessHeap();
  HeapFree(v12, 0, v7);
LABEL_9:
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v6,
      v8,
      36,
      &WPP_92038ab37ee4317b05ca4ff2fd992641_Traceguids,
      v14,
      v9);
  return v9;
}

```

## disassembly

```asm
0x14000a268  push    rbx
0x14000a26a  push    rbp
0x14000a26b  push    rsi
0x14000a26c  push    rdi
0x14000a26d  push    r14
0x14000a26f  sub     rsp, 40h
0x14000a273  mov     rbx, r8
0x14000a276  mov     esi, ecx
0x14000a278  lea     rbp, WPP_RECORDER_INITIALIZED
0x14000a27f  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000a286  lea     r14, WPP_92038ab37ee4317b05ca4ff2fd992641_Traceguids
0x14000a28d  jz      short loc_14000A2AA
0x14000a28f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a296  mov     r9d, 23h ; '#'; int
0x14000a29c  mov     [rsp+68h+MessageGuid], r14; MessageGuid
0x14000a2a1  mov     rcx, [rcx+28h]; int
0x14000a2a5  call    WPP_RECORDER_SF_s
0x14000a2aa  call    cs:__imp_GetProcessHeap
0x14000a2b0  xor     edx, edx; dwFlags
0x14000a2b2  mov     rcx, rax; hHeap
0x14000a2b5  lea     r8d, [rdx+18h]; dwBytes
0x14000a2b9  call    cs:__imp_HeapAlloc
0x14000a2bf  mov     rdi, rax
0x14000a2c2  test    rax, rax
0x14000a2c5  jnz     short loc_14000A2CE
0x14000a2c7  mov     ebx, 8007000Eh
0x14000a2cc  jmp     short loc_14000A337
0x14000a2ce  xorps   xmm0, xmm0
0x14000a2d1  xor     eax, eax
0x14000a2d3  movups  xmmword ptr [rdi], xmm0
0x14000a2d6  mov     [rdi+10h], rax
0x14000a2da  call    cs:__imp_GetProcessHeap
0x14000a2e0  xor     edx, edx; dwFlags
0x14000a2e2  mov     rcx, rax; hHeap
0x14000a2e5  lea     r8d, [rdx+28h]; dwBytes
0x14000a2e9  call    cs:__imp_HeapAlloc
0x14000a2ef  test    rax, rax
0x14000a2f2  jnz     short loc_14000A2FB
0x14000a2f4  mov     ebx, 8007000Eh
0x14000a2f9  jmp     short loc_14000A323
0x14000a2fb  xorps   xmm0, xmm0
0x14000a2fe  xor     ecx, ecx
0x14000a300  movups  xmmword ptr [rax], xmm0
0x14000a303  mov     rdx, rbx; struct _PROVIDER_QUERY_ENTRY *
0x14000a306  movups  xmmword ptr [rax+10h], xmm0
0x14000a30a  mov     [rax+20h], rcx
0x14000a30e  mov     rcx, rdi; struct _DAS_HOST_QUERY_RESULT *
0x14000a311  mov     [rax+8], esi
0x14000a314  mov     [rdi+10h], rax
0x14000a318  call    ?AddToResultList@@YAJPEAU_DAS_HOST_QUERY_RESULT@@PEAU_PROVIDER_QUERY_ENTRY@@@Z; AddToResultList(_DAS_HOST_QUERY_RESULT *,_PROVIDER_QUERY_ENTRY *)
0x14000a31d  mov     ebx, eax
0x14000a31f  test    eax, eax
0x14000a321  jz      short loc_14000A337
0x14000a323  call    cs:__imp_GetProcessHeap
0x14000a329  mov     r8, rdi; lpMem
0x14000a32c  xor     edx, edx; dwFlags
0x14000a32e  mov     rcx, rax; hHeap
0x14000a331  call    cs:__imp_HeapFree
0x14000a337  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000a33e  jz      short loc_14000A35F
0x14000a340  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a347  mov     r9d, 24h ; '$'; int
0x14000a34d  mov     dword ptr [rsp+68h+var_38], ebx; char
0x14000a351  mov     [rsp+68h+MessageGuid], r14; MessageGuid
0x14000a356  mov     rcx, [rcx+28h]; int
0x14000a35a  call    WPP_RECORDER_SF_sd
0x14000a35f  mov     eax, ebx
0x14000a361  add     rsp, 40h
0x14000a365  pop     r14
0x14000a367  pop     rdi
0x14000a368  pop     rsi
0x14000a369  pop     rbp
0x14000a36a  pop     rbx
0x14000a36b  retn
```
