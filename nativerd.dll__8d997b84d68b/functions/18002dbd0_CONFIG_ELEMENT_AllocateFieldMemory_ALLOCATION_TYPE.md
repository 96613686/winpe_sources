# CONFIG_ELEMENT::AllocateFieldMemory(ALLOCATION_TYPE)

- ea: `0x18002dbd0`
- end: `0x18002dd30`
- name: `?AllocateFieldMemory@CONFIG_ELEMENT@@QEAAJW4ALLOCATION_TYPE@@@Z`
- size: `352`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `18`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180014098`
- `0x18001b1b8`
- `0x18001f4c8`
- `0x18002dd38`
- `0x18002f8a0`
- `0x180030044`
- `0x180030078`
- `0x180031df8`
- `0x180031fa4`
- `0x180032828`
- `0x180033d44`
- `0x180033de0`
- `0x18003424c`
- `0x180034410`
- `0x180035114`
- `0x180038ac8`
- `0x180040358`
- `0x180042d6c`

## callees

- `0x18001c250`
- `0x18002dbd0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002dc09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002dc4f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002dcf1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002dc09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002dc4f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002dcf1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002dc1a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002dc61`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002dd03`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002dc1a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002dc61`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002dd03`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002dd1d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002dd1d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002dbf9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002dc3f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002dc86`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002dce2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002dbf9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002dc3f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002dc86`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002dce2`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x18002dcab`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x18002dcab`

## pseudocode

```c
__int64 __fastcall CONFIG_ELEMENT::AllocateFieldMemory(RTL_SRWLOCK *a1, int a2)
{
  unsigned int v3; // esi
  RTL_SRWLOCK *v4; // rbx
  HANDLE v5; // rax
  LPVOID v6; // rax
  HANDLE ProcessHeap; // rax
  CReaderWriterLock3 *v8; // rax
  CReaderWriterLock3 *v9; // rbp
  HANDLE v10; // rax

  v3 = 0;
  if ( a2 )
  {
    if ( a2 == 1 )
    {
      if ( a1[14].Ptr )
        return v3;
      v4 = a1 + 12;
      AcquireSRWLockExclusive(a1 + 12);
      if ( a1[14].Ptr )
        goto LABEL_21;
      ProcessHeap = GetProcessHeap();
      v6 = HeapAlloc(ProcessHeap, 8u, 0x10u);
      a1[14].Ptr = v6;
    }
    else
    {
      if ( a2 == 2 )
      {
        if ( !a1[15].Ptr )
        {
          v4 = a1 + 12;
          AcquireSRWLockExclusive(a1 + 12);
          if ( !a1[15].Ptr )
          {
            v8 = (CReaderWriterLock3 *)operator new(0x28u);
            v9 = v8;
            if ( !v8 )
            {
              a1[15].Ptr = 0;
LABEL_20:
              v3 = -2147024888;
              goto LABEL_21;
            }
            CReaderWriterLock3::CReaderWriterLock3(v8);
            *((_DWORD *)v9 + 2) = 0;
            *((_QWORD *)v9 + 2) = 0;
            *((_QWORD *)v9 + 3) = 0;
            *((_QWORD *)v9 + 4) = 0;
            a1[15].Ptr = v9;
          }
LABEL_21:
          ReleaseSRWLockExclusive(v4);
          return v3;
        }
        return v3;
      }
      if ( a2 != 3 || a1[16].Ptr )
        return v3;
      v4 = a1 + 12;
      AcquireSRWLockExclusive(a1 + 12);
      if ( a1[16].Ptr )
        goto LABEL_21;
      v10 = GetProcessHeap();
      v6 = HeapAlloc(v10, 8u, 0x20u);
      a1[16].Ptr = v6;
    }
LABEL_19:
    if ( !v6 )
      goto LABEL_20;
    goto LABEL_21;
  }
  if ( !a1[13].Ptr )
  {
    v4 = a1 + 12;
    AcquireSRWLockExclusive(a1 + 12);
    if ( a1[13].Ptr )
      goto LABEL_21;
    v5 = GetProcessHeap();
    v6 = HeapAlloc(v5, 8u, 0x18u);
    a1[13].Ptr = v6;
    goto LABEL_19;
  }
  return v3;
}

```

## disassembly

```asm
0x18002dbd0  push    rbx
0x18002dbd2  push    rbp
0x18002dbd3  push    rsi
0x18002dbd4  push    rdi
0x18002dbd5  push    r14
0x18002dbd7  sub     rsp, 20h
0x18002dbdb  xor     r14d, r14d
0x18002dbde  mov     rdi, rcx
0x18002dbe1  mov     esi, r14d
0x18002dbe4  test    edx, edx
0x18002dbe6  jnz     short loc_18002DC29
0x18002dbe8  cmp     [rcx+68h], r14
0x18002dbec  jnz     loc_18002DD23
0x18002dbf2  lea     rbx, [rcx+60h]
0x18002dbf6  mov     rcx, rbx; SRWLock
0x18002dbf9  call    cs:__imp_AcquireSRWLockExclusive
0x18002dbff  cmp     [rdi+68h], r14
0x18002dc03  jnz     loc_18002DD1A
0x18002dc09  call    cs:__imp_GetProcessHeap
0x18002dc0f  mov     rcx, rax; hHeap
0x18002dc12  lea     edx, [r14+8]; dwFlags
0x18002dc16  lea     r8d, [r14+18h]; dwBytes
0x18002dc1a  call    cs:__imp_HeapAlloc
0x18002dc20  mov     [rdi+68h], rax
0x18002dc24  jmp     loc_18002DD10
0x18002dc29  cmp     edx, 1
0x18002dc2c  jnz     short loc_18002DC70
0x18002dc2e  cmp     [rcx+70h], r14
0x18002dc32  jnz     loc_18002DD23
0x18002dc38  lea     rbx, [rcx+60h]
0x18002dc3c  mov     rcx, rbx; SRWLock
0x18002dc3f  call    cs:__imp_AcquireSRWLockExclusive
0x18002dc45  cmp     [rdi+70h], r14
0x18002dc49  jnz     loc_18002DD1A
0x18002dc4f  call    cs:__imp_GetProcessHeap
0x18002dc55  mov     edx, 8; dwFlags
0x18002dc5a  mov     rcx, rax; hHeap
0x18002dc5d  lea     r8d, [rdx+8]; dwBytes
0x18002dc61  call    cs:__imp_HeapAlloc
0x18002dc67  mov     [rdi+70h], rax
0x18002dc6b  jmp     loc_18002DD10
0x18002dc70  cmp     edx, 2
0x18002dc73  jnz     short loc_18002DCCD
0x18002dc75  cmp     [rcx+78h], r14
0x18002dc79  jnz     loc_18002DD23
0x18002dc7f  lea     rbx, [rcx+60h]
0x18002dc83  mov     rcx, rbx; SRWLock
0x18002dc86  call    cs:__imp_AcquireSRWLockExclusive
0x18002dc8c  cmp     [rdi+78h], r14
0x18002dc90  jnz     loc_18002DD1A
0x18002dc96  mov     ecx, 28h ; '('; Size
0x18002dc9b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002dca0  mov     rbp, rax
0x18002dca3  test    rax, rax
0x18002dca6  jz      short loc_18002DCC7
0x18002dca8  mov     rcx, rax
0x18002dcab  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x18002dcb1  mov     [rbp+8], r14d
0x18002dcb5  mov     [rbp+10h], r14
0x18002dcb9  mov     [rbp+18h], r14
0x18002dcbd  mov     [rbp+20h], r14
0x18002dcc1  mov     [rdi+78h], rbp
0x18002dcc5  jmp     short loc_18002DD1A
0x18002dcc7  mov     [rdi+78h], r14
0x18002dccb  jmp     short loc_18002DD15
0x18002dccd  cmp     edx, 3
0x18002dcd0  jnz     short loc_18002DD23
0x18002dcd2  cmp     [rcx+80h], r14
0x18002dcd9  jnz     short loc_18002DD23
0x18002dcdb  lea     rbx, [rcx+60h]
0x18002dcdf  mov     rcx, rbx; SRWLock
0x18002dce2  call    cs:__imp_AcquireSRWLockExclusive
0x18002dce8  cmp     [rdi+80h], r14
0x18002dcef  jnz     short loc_18002DD1A
0x18002dcf1  call    cs:__imp_GetProcessHeap
0x18002dcf7  mov     edx, 8; dwFlags
0x18002dcfc  mov     rcx, rax; hHeap
0x18002dcff  lea     r8d, [rdx+18h]; dwBytes
0x18002dd03  call    cs:__imp_HeapAlloc
0x18002dd09  mov     [rdi+80h], rax
0x18002dd10  test    rax, rax
0x18002dd13  jnz     short loc_18002DD1A
0x18002dd15  mov     esi, 80070008h
0x18002dd1a  mov     rcx, rbx; SRWLock
0x18002dd1d  call    cs:__imp_ReleaseSRWLockExclusive
0x18002dd23  mov     eax, esi
0x18002dd25  add     rsp, 20h
0x18002dd29  pop     r14
0x18002dd2b  pop     rdi
0x18002dd2c  pop     rsi
0x18002dd2d  pop     rbp
0x18002dd2e  pop     rbx
0x18002dd2f  retn
```
