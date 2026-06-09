# CSafeSem::Take(void)

- ea: `0x180015f30`
- end: `0x18001612f`
- name: `?Take@CSafeSem@@QEAAJXZ`
- size: `511`
- prototype: `__int64 __fastcall(CSafeSem *__hidden this)`
- caller_count: `34`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180006d80`
- `0x180007310`
- `0x18000a780`
- `0x18000aef0`
- `0x18000b680`
- `0x180015280`
- `0x180015420`
- `0x180015880`
- `0x180015b70`
- `0x1800162a0`
- `0x18001c99c`
- `0x18001f0b0`
- `0x18001f1c4`
- `0x1800205e0`
- `0x1800216a0`
- `0x180021cf0`
- `0x180024020`
- `0x180032890`
- `0x180035890`
- `0x180037fa0`
- `0x180038970`
- `0x180039ca0`
- `0x18003abf0`
- `0x18003d780`
- `0x180041890`
- `0x18004b010`
- `0x18004b8d0`
- `0x18004bd30`
- `0x18004bfa0`
- `0x18004c130`
- `0x18004c5a0`
- `0x18004d610`
- `0x18004e400`
- `0x18004e480`

## callees

- `0x180015f30`
- `0x18001b840`
- `0x18002ea90`
- `0x180032aac`

## import_xrefs

- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x180016053`
- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x180016053`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016094`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016094`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800160c5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800160c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015f40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015f40`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180016074`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180016074`

## pseudocode

```c
__int64 __fastcall CSafeSem::Take(CSafeSem *this)
{
  __int64 v1; // rbp
  DWORD CurrentThreadId; // eax
  DWORD v4; // ebx
  signed __int32 v5; // r8d
  __int64 v6; // rcx
  signed int v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // r9
  int v13; // r11d
  int v14; // edx
  int v16; // edx
  DWORD v17; // eax
  signed int LastError; // eax
  CSmAllocator *v19; // rax
  CSmAllocator *v20; // rax
  _QWORD *ReservedForOle; // [rsp+50h] [rbp+8h] BYREF

  v1 = *((_QWORD *)this + 1);
  CurrentThreadId = GetCurrentThreadId();
  v4 = CurrentThreadId;
  v5 = _InterlockedExchangeAdd(*(volatile signed __int32 **)(v1 + 112), 1u);
  v6 = *(_QWORD *)(v1 + 112);
  if ( v5 == -1 )
  {
    *(_DWORD *)(v6 + 4) = 1;
    *(_DWORD *)(*(_QWORD *)(v1 + 112) + 8LL) = CurrentThreadId;
LABEL_3:
    v7 = 0;
LABEL_4:
    v8 = *(_QWORD *)(v1 + 88);
    if ( v8 )
    {
      v16 = **(_DWORD **)(v8 + 8);
      if ( v16 != *(_DWORD *)(v8 + 16) )
      {
        v7 = CSharedMemoryBlock::Commit((CSharedMemoryBlock *)v8, v16 - 24);
        if ( v7 < 0 )
          CDfMutex::Release((CDfMutex *)(v1 + 112));
      }
    }
    goto LABEL_5;
  }
  if ( *(_DWORD *)(v6 + 8) == CurrentThreadId )
  {
    ++*(_DWORD *)(v6 + 4);
    goto LABEL_3;
  }
  v17 = WaitForSingleObject(*(HANDLE *)(v1 + 120), 0x124F80u);
  if ( !v17 || v17 == 128 )
  {
    *(_DWORD *)(*(_QWORD *)(v1 + 112) + 4LL) = 1;
    *(_DWORD *)(*(_QWORD *)(v1 + 112) + 8LL) = v4;
    goto LABEL_3;
  }
  if ( v17 == 258 )
  {
    v7 = -2147286784;
    goto LABEL_5;
  }
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  if ( v7 >= 0 )
    goto LABEL_4;
LABEL_5:
  *(_DWORD *)this = v7;
  ReservedForOle = NtCurrentTeb()->ReservedForOle;
  if ( !ReservedForOle )
    InternalTlsAllocData(&ReservedForOle);
  if ( !ReservedForOle[1] )
  {
    v19 = (CSmAllocator *)HeapAlloc(g_hHeap, 0, 0x30u);
    if ( v19 )
    {
      v20 = CSmAllocator::CSmAllocator(v19);
      ReservedForOle[1] = v20;
      if ( v20 )
        goto LABEL_8;
    }
    else
    {
      ReservedForOle[1] = 0;
    }
    ReservedForOle[1] = &g_ErrorSmAllocator;
  }
LABEL_8:
  v9 = *((_QWORD *)this + 1);
  v10 = ReservedForOle[1];
  *((_QWORD *)this + 3) = v10;
  v11 = *(_QWORD *)(v9 + 88);
  v12 = *(_QWORD *)(v9 + 96);
  v13 = *(_DWORD *)(v9 + 104);
  *(_QWORD *)(v10 + 8) = v11;
  *(_QWORD *)(v10 + 16) = v12;
  if ( v11 )
    v14 = *(_DWORD *)(v11 + 16) - 24;
  else
    v14 = 0;
  *(_DWORD *)(v10 + 32) = v14;
  *(_DWORD *)(v10 + 36) = v13;
  *(_QWORD *)NtCurrentTeb()->ReservedForOle = v12;
  if ( this != (CSafeSem *)-16LL )
    *((_QWORD *)this + 2) = *(_QWORD *)(v10 + 24);
  *(_QWORD *)(v10 + 24) = v9;
  return *(unsigned int *)this;
}

```

## disassembly

```asm
0x180015f30  push    rbx
0x180015f32  push    rbp
0x180015f33  push    rsi
0x180015f34  push    rdi
0x180015f35  sub     rsp, 28h
0x180015f39  mov     rbp, [rcx+8]
0x180015f3d  mov     rdi, rcx
0x180015f40  call    cs:__imp_GetCurrentThreadId
0x180015f46  mov     rdx, [rbp+70h]
0x180015f4a  mov     r8d, 1
0x180015f50  mov     ebx, eax
0x180015f52  lock xadd [rdx], r8d
0x180015f57  mov     rcx, [rbp+70h]
0x180015f5b  add     r8d, 1
0x180015f5f  jnz     loc_18001605E
0x180015f65  mov     dword ptr [rcx+4], 1
0x180015f6c  mov     rcx, [rbp+70h]
0x180015f70  mov     [rcx+8], eax
0x180015f73  xor     ebx, ebx
0x180015f75  mov     rcx, [rbp+58h]; this
0x180015f79  test    rcx, rcx
0x180015f7c  jnz     loc_18001601F
0x180015f82  mov     [rdi], ebx
0x180015f84  mov     rax, gs:30h
0x180015f8d  mov     rcx, [rax+1758h]
0x180015f94  mov     [rsp+48h+arg_0], rcx
0x180015f99  test    rcx, rcx
0x180015f9c  jz      loc_18001604E
0x180015fa2  mov     rax, [rsp+48h+arg_0]
0x180015fa7  cmp     qword ptr [rax+8], 0
0x180015fac  jz      loc_1800160B6
0x180015fb2  mov     r8, [rdi+8]
0x180015fb6  lea     r10, [rdi+10h]
0x180015fba  mov     rax, [rsp+48h+arg_0]
0x180015fbf  mov     rax, [rax+8]
0x180015fc3  mov     [rdi+18h], rax
0x180015fc7  mov     rcx, [r8+58h]
0x180015fcb  mov     r9, [r8+60h]
0x180015fcf  mov     r11d, [r8+68h]
0x180015fd3  mov     [rax+8], rcx
0x180015fd7  mov     [rax+10h], r9
0x180015fdb  test    rcx, rcx
0x180015fde  jz      short loc_18001601B
0x180015fe0  mov     edx, [rcx+10h]
0x180015fe3  sub     edx, 18h
0x180015fe6  mov     [rax+20h], edx
0x180015fe9  mov     [rax+24h], r11d
0x180015fed  mov     rcx, gs:30h
0x180015ff6  mov     rdx, [rcx+1758h]
0x180015ffd  mov     [rdx], r9
0x180016000  test    r10, r10
0x180016003  jz      short loc_18001600C
0x180016005  mov     rcx, [rax+18h]
0x180016009  mov     [r10], rcx
0x18001600c  mov     [rax+18h], r8
0x180016010  mov     eax, [rdi]
0x180016012  add     rsp, 28h
0x180016016  pop     rdi
0x180016017  pop     rsi
0x180016018  pop     rbp
0x180016019  pop     rbx
0x18001601a  retn
0x18001601b  xor     edx, edx
0x18001601d  jmp     short loc_180015FE6
0x18001601f  mov     rax, [rcx+8]
0x180016023  mov     edx, [rax]
0x180016025  cmp     edx, [rcx+10h]
0x180016028  jz      loc_180015F82
0x18001602e  add     edx, 0FFFFFFE8h; unsigned int
0x180016031  call    ?Commit@CSharedMemoryBlock@@QEAAJK@Z; CSharedMemoryBlock::Commit(ulong)
0x180016036  mov     ebx, eax
0x180016038  test    eax, eax
0x18001603a  jns     loc_180015F82
0x180016040  lea     rcx, [rbp+70h]; this
0x180016044  call    ?Release@CDfMutex@@QEAAXXZ; CDfMutex::Release(void)
0x180016049  jmp     loc_180015F82
0x18001604e  lea     rcx, [rsp+48h+arg_0]
0x180016053  call    cs:__imp_InternalTlsAllocData
0x180016059  jmp     loc_180015FA2
0x18001605e  cmp     [rcx+8], ebx
0x180016061  jnz     short loc_18001606B
0x180016063  inc     dword ptr [rcx+4]
0x180016066  jmp     loc_180015F73
0x18001606b  mov     rcx, [rbp+78h]; hHandle
0x18001606f  mov     edx, 124F80h; dwMilliseconds
0x180016074  call    cs:__imp_WaitForSingleObject
0x18001607a  test    eax, eax
0x18001607c  jz      loc_180016118
0x180016082  cmp     eax, 80h
0x180016087  jz      loc_180016118
0x18001608d  cmp     eax, 102h
0x180016092  jz      short loc_18001610E
0x180016094  call    cs:__imp_GetLastError
0x18001609a  mov     ebx, eax
0x18001609c  test    eax, eax
0x18001609e  jle     short loc_1800160A9
0x1800160a0  movzx   ebx, ax
0x1800160a3  or      ebx, 80070000h
0x1800160a9  test    ebx, ebx
0x1800160ab  jns     loc_180015F75
0x1800160b1  jmp     loc_180015F82
0x1800160b6  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800160bd  xor     edx, edx; dwFlags
0x1800160bf  mov     r8d, 30h ; '0'; dwBytes
0x1800160c5  call    cs:__imp_HeapAlloc
0x1800160cb  test    rax, rax
0x1800160ce  jnz     short loc_1800160DF
0x1800160d0  mov     rax, [rsp+48h+arg_0]
0x1800160d5  mov     qword ptr [rax+8], 0
0x1800160dd  jmp     short loc_1800160F9
0x1800160df  mov     rcx, rax; this
0x1800160e2  call    ??0CSmAllocator@@QEAA@XZ; CSmAllocator::CSmAllocator(void)
0x1800160e7  mov     rcx, [rsp+48h+arg_0]
0x1800160ec  mov     [rcx+8], rax
0x1800160f0  test    rax, rax
0x1800160f3  jnz     loc_180015FB2
0x1800160f9  mov     rax, [rsp+48h+arg_0]
0x1800160fe  lea     rcx, ?g_ErrorSmAllocator@@3VCErrorSmAllocator@@A; CErrorSmAllocator g_ErrorSmAllocator
0x180016105  mov     [rax+8], rcx
0x180016109  jmp     loc_180015FB2
0x18001610e  mov     ebx, 80030100h
0x180016113  jmp     loc_180015F82
0x180016118  mov     rax, [rbp+70h]
0x18001611c  mov     dword ptr [rax+4], 1
0x180016123  mov     rax, [rbp+70h]
0x180016127  mov     [rax+8], ebx
0x18001612a  jmp     loc_180015F73
```
