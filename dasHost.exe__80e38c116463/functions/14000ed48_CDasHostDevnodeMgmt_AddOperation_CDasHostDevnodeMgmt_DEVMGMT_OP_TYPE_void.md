# CDasHostDevnodeMgmt::AddOperation(CDasHostDevnodeMgmt *,DEVMGMT_OP_TYPE,void *)

- ea: `0x14000ed48`
- end: `0x14000ee20`
- name: `?AddOperation@CDasHostDevnodeMgmt@@SAJPEAV1@W4DEVMGMT_OP_TYPE@@PEAX@Z`
- size: `216`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x14000e6a0`
- `0x14000e780`
- `0x14000e9a0`
- `0x14000ea90`
- `0x14000f2c8`
- `0x14000fd20`
- `0x1400104b0`
- `0x140010560`

## callees

- `0x14000ed48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000edbf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000edbf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000ee0d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14000ee0d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000ee03`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000ee03`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000edf9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000edf9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000ed60`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000ed60`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000ed88`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000ed88`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ed79`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ed79`

## pseudocode

```c
__int64 __fastcall CDasHostDevnodeMgmt::AddOperation(__int64 a1, int a2, __int64 a3)
{
  unsigned int v6; // edi
  HANDLE ProcessHeap; // rax
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  int v10; // ecx
  _QWORD *v11; // rcx

  AcquireSRWLockShared((PSRWLOCK)(a1 + 120));
  if ( *(_DWORD *)(a1 + 128) )
  {
    ProcessHeap = GetProcessHeap();
    v8 = HeapAlloc(ProcessHeap, 0, 0x20u);
    v9 = v8;
    if ( v8 )
    {
      *v8 = 0;
      v8[1] = 0;
      *((_DWORD *)v8 + 5) = 0;
      *((_DWORD *)v8 + 4) = a2;
      v8[3] = a3;
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 96));
      v10 = *(_DWORD *)(a1 + 104);
      *(_DWORD *)(a1 + 104) = v10 + 1;
      *((_DWORD *)v9 + 5) = v10;
      v11 = *(_QWORD **)(a1 + 72);
      if ( *v11 != a1 + 64 )
        __fastfail(3u);
      *v9 = a1 + 64;
      v6 = 0;
      v9[1] = v11;
      *v11 = v9;
      *(_QWORD *)(a1 + 72) = v9;
      SetEvent(*(HANDLE *)(a1 + 24));
      ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 96));
    }
    else
    {
      v6 = -2147024882;
    }
  }
  else
  {
    v6 = -2140930029;
  }
  ReleaseSRWLockShared((PSRWLOCK)(a1 + 120));
  return v6;
}

```

## disassembly

```asm
0x14000ed48  push    rbx
0x14000ed4a  push    rbp
0x14000ed4b  push    rsi
0x14000ed4c  push    rdi
0x14000ed4d  push    r14
0x14000ed4f  sub     rsp, 20h
0x14000ed53  mov     rsi, rcx
0x14000ed56  mov     rdi, r8
0x14000ed59  add     rcx, 78h ; 'x'; SRWLock
0x14000ed5d  mov     r14d, edx
0x14000ed60  call    cs:__imp_AcquireSRWLockShared
0x14000ed66  cmp     dword ptr [rsi+80h], 0
0x14000ed6d  jnz     short loc_14000ED79
0x14000ed6f  mov     edi, 80640013h
0x14000ed74  jmp     loc_14000EE09
0x14000ed79  call    cs:__imp_GetProcessHeap
0x14000ed7f  xor     edx, edx; dwFlags
0x14000ed81  mov     rcx, rax; hHeap
0x14000ed84  lea     r8d, [rdx+20h]; dwBytes
0x14000ed88  call    cs:__imp_HeapAlloc
0x14000ed8e  mov     rbx, rax
0x14000ed91  test    rax, rax
0x14000ed94  jnz     short loc_14000ED9D
0x14000ed96  mov     edi, 8007000Eh
0x14000ed9b  jmp     short loc_14000EE09
0x14000ed9d  mov     qword ptr [rax], 0
0x14000eda4  lea     rcx, [rsi+60h]; SRWLock
0x14000eda8  mov     qword ptr [rax+8], 0
0x14000edb0  mov     dword ptr [rax+14h], 0
0x14000edb7  mov     [rax+10h], r14d
0x14000edbb  mov     [rax+18h], rdi
0x14000edbf  call    cs:__imp_AcquireSRWLockExclusive
0x14000edc5  mov     ecx, [rsi+68h]
0x14000edc8  lea     eax, [rcx+1]
0x14000edcb  mov     [rsi+68h], eax
0x14000edce  lea     rax, [rsi+40h]
0x14000edd2  mov     [rbx+14h], ecx
0x14000edd5  mov     rcx, [rax+8]
0x14000edd9  cmp     [rcx], rax
0x14000eddc  jz      short loc_14000EDE5
0x14000edde  mov     ecx, 3
0x14000ede3  int     29h; Win8: RtlFailFast(ecx)
0x14000ede5  mov     [rbx], rax
0x14000ede8  xor     edi, edi
0x14000edea  mov     [rbx+8], rcx
0x14000edee  mov     [rcx], rbx
0x14000edf1  mov     [rax+8], rbx
0x14000edf5  mov     rcx, [rsi+18h]; hEvent
0x14000edf9  call    cs:__imp_SetEvent
0x14000edff  lea     rcx, [rsi+60h]; SRWLock
0x14000ee03  call    cs:__imp_ReleaseSRWLockExclusive
0x14000ee09  lea     rcx, [rsi+78h]; SRWLock
0x14000ee0d  call    cs:__imp_ReleaseSRWLockShared
0x14000ee13  mov     eax, edi
0x14000ee15  add     rsp, 20h
0x14000ee19  pop     r14
0x14000ee1b  pop     rdi
0x14000ee1c  pop     rsi
0x14000ee1d  pop     rbp
0x14000ee1e  pop     rbx
0x14000ee1f  retn
```
