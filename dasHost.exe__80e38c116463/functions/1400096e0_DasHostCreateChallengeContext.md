# DasHostCreateChallengeContext

- ea: `0x1400096e0`
- end: `0x14000983e`
- name: `DasHostCreateChallengeContext`
- size: `350`
- prototype: `__int64 __fastcall(__int64, _OWORD *, _WORD *, RTL_SRWLOCK **)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1400020d0`
- `0x140008eec`
- `0x140008f88`
- `0x1400096e0`
- `0x14001a83c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1400097ec`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1400097ec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000973f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400097c7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000973f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400097c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000972c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400097a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000972c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400097a6`

## pseudocode

```c
__int64 __fastcall DasHostCreateChallengeContext(__int64 a1, _OWORD *a2, _WORD *a3, RTL_SRWLOCK **a4)
{
  HANDLE ProcessHeap; // rax
  RTL_SRWLOCK *v8; // rax
  int v9; // edx
  int v10; // r8d
  RTL_SRWLOCK *v11; // rsi
  unsigned int v12; // ebx
  _WORD *v13; // rax
  __int64 v14; // rdi
  HANDLE v15; // rax
  SIZE_T v16; // rdi
  void *v17; // rax
  int v19; // [rsp+28h] [rbp-60h]

  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (int)a2,
      (int)a3,
      10,
      &WPP_e7bcb4884d5632717339d31cbd6bbd09_Traceguids);
  ProcessHeap = GetProcessHeap();
  v8 = (RTL_SRWLOCK *)HeapAlloc(ProcessHeap, 0, 0x40u);
  v11 = v8;
  if ( !v8 )
  {
LABEL_4:
    v12 = -2147024882;
    goto LABEL_13;
  }
  memset_0(v8, 0, 0x40u);
  *(_OWORD *)&v11->Ptr = *a2;
  if ( a3 )
  {
    v13 = a3;
    v14 = 768;
    do
    {
      if ( !*v13 )
        break;
      ++v13;
      --v14;
    }
    while ( v14 );
    v12 = v14 == 0 ? 0x80070057 : 0;
    if ( !v14 )
      goto LABEL_13;
    v15 = GetProcessHeap();
    v16 = ((2 * (768 - v14)) & -(__int64)(v14 != 0)) + 2;
    v17 = HeapAlloc(v15, 0, v16);
    v11[2].Ptr = v17;
    if ( !v17 )
      goto LABEL_4;
    memcpy_0(v17, a3, v16);
    InitializeSRWLock(v11 + 4);
    *a4 = v11;
  }
  else
  {
    v12 = -2147024809;
  }
LABEL_13:
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v9,
      v10,
      11,
      &WPP_e7bcb4884d5632717339d31cbd6bbd09_Traceguids,
      v19,
      v12);
  return v12;
}

```

## disassembly

```asm
0x1400096e0  push    rbx
0x1400096e2  push    rbp
0x1400096e3  push    rsi
0x1400096e4  push    rdi
0x1400096e5  push    r12
0x1400096e7  push    r13
0x1400096e9  push    r14
0x1400096eb  push    r15
0x1400096ed  sub     rsp, 48h
0x1400096f1  mov     r15, r9
0x1400096f4  mov     r14, r8
0x1400096f7  mov     rbx, rdx
0x1400096fa  lea     r13, WPP_RECORDER_INITIALIZED
0x140009701  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140009708  lea     rax, WPP_e7bcb4884d5632717339d31cbd6bbd09_Traceguids
0x14000970f  jz      short loc_14000972C
0x140009711  mov     rcx, cs:WPP_GLOBAL_Control
0x140009718  mov     r9d, 0Ah; int
0x14000971e  mov     [rsp+88h+MessageGuid], rax; MessageGuid
0x140009723  mov     rcx, [rcx+28h]; int
0x140009727  call    WPP_RECORDER_SF_s
0x14000972c  call    cs:__imp_GetProcessHeap
0x140009732  mov     edi, 40h ; '@'
0x140009737  xor     edx, edx; dwFlags
0x140009739  mov     rcx, rax; hHeap
0x14000973c  mov     r8d, edi; dwBytes
0x14000973f  call    cs:__imp_HeapAlloc
0x140009745  xor     r12d, r12d
0x140009748  mov     rsi, rax
0x14000974b  test    rax, rax
0x14000974e  jnz     short loc_14000975A
0x140009750  mov     ebx, 8007000Eh
0x140009755  jmp     loc_1400097FC
0x14000975a  mov     r8, rdi; Size
0x14000975d  xor     edx, edx; Val
0x14000975f  mov     rcx, rsi; void *
0x140009762  call    memset_0
0x140009767  movups  xmm0, xmmword ptr [rbx]
0x14000976a  movdqu  xmmword ptr [rsi], xmm0
0x14000976e  test    r14, r14
0x140009771  jz      loc_1400097F7
0x140009777  mov     ebp, 300h
0x14000977c  mov     rax, r14
0x14000977f  mov     edi, ebp
0x140009781  cmp     [rax], r12w
0x140009785  jz      short loc_140009791
0x140009787  add     rax, 2
0x14000978b  sub     rdi, 1
0x14000978f  jnz     short loc_140009781
0x140009791  mov     rax, rdi
0x140009794  neg     rax
0x140009797  sbb     ebx, ebx
0x140009799  not     ebx
0x14000979b  and     ebx, 80070057h
0x1400097a1  test    rdi, rdi
0x1400097a4  jz      short loc_1400097FC
0x1400097a6  call    cs:__imp_GetProcessHeap
0x1400097ac  sub     rbp, rdi
0x1400097af  add     rbp, rbp
0x1400097b2  neg     rdi
0x1400097b5  sbb     rcx, rcx
0x1400097b8  xor     edx, edx; dwFlags
0x1400097ba  and     rcx, rbp
0x1400097bd  lea     rdi, [rcx+2]
0x1400097c1  mov     rcx, rax; hHeap
0x1400097c4  mov     r8, rdi; dwBytes
0x1400097c7  call    cs:__imp_HeapAlloc
0x1400097cd  mov     [rsi+10h], rax
0x1400097d1  test    rax, rax
0x1400097d4  jz      loc_140009750
0x1400097da  mov     r8, rdi; Size
0x1400097dd  mov     rdx, r14; Src
0x1400097e0  mov     rcx, rax; void *
0x1400097e3  call    memcpy_0
0x1400097e8  lea     rcx, [rsi+20h]; SRWLock
0x1400097ec  call    cs:__imp_InitializeSRWLock
0x1400097f2  mov     [r15], rsi
0x1400097f5  jmp     short loc_1400097FC
0x1400097f7  mov     ebx, 80070057h
0x1400097fc  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140009803  jz      short loc_14000982B
0x140009805  mov     rcx, cs:WPP_GLOBAL_Control
0x14000980c  lea     rax, WPP_e7bcb4884d5632717339d31cbd6bbd09_Traceguids
0x140009813  mov     r9d, 0Bh; int
0x140009819  mov     dword ptr [rsp+88h+var_58], ebx; char
0x14000981d  mov     [rsp+88h+MessageGuid], rax; MessageGuid
0x140009822  mov     rcx, [rcx+28h]; int
0x140009826  call    WPP_RECORDER_SF_sd
0x14000982b  mov     eax, ebx
0x14000982d  add     rsp, 48h
0x140009831  pop     r15
0x140009833  pop     r14
0x140009835  pop     r13
0x140009837  pop     r12
0x140009839  pop     rdi
0x14000983a  pop     rsi
0x14000983b  pop     rbp
0x14000983c  pop     rbx
0x14000983d  retn
```
