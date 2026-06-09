# BookKeeping::GetRecord(int)

- ea: `0x1800013a0`
- end: `0x180001411`
- name: `?GetRecord@BookKeeping@@CAAEAVSnapinRecord@@H@Z`
- size: `113`
- prototype: `struct SnapinRecord *__fastcall(int)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001420`
- `0x18000d370`
- `0x18000d6f0`
- `0x18000d870`
- `0x18000dde0`

## callees

- `0x1800013a0`
- `0x18001984c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800013b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800013b9`

## pseudocode

```c
struct SnapinRecord *__fastcall BookKeeping::GetRecord(int a1)
{
  __int64 v1; // rbx
  __int64 v2; // rdi
  struct SnapinRecord *result; // rax

  v1 = 0;
  v2 = a1;
  if ( dword_18002F688
    || _InterlockedCompareExchange((volatile signed __int32 *)&dword_18002F688, GetCurrentThreadId(), 0) )
  {
    CSmallSpinLock::_LockSpin((CSmallSpinLock *)&dword_18002F688);
  }
  if ( (int)v2 >= 0 && (int)v2 < SHIDWORD(qword_18002F680) )
    v1 = *((_QWORD *)Src + v2);
  _InterlockedExchange((volatile __int32 *)&dword_18002F688, 0);
  result = (struct SnapinRecord *)&BookKeeping::s_unknownSnapin;
  if ( v1 )
    return (struct SnapinRecord *)v1;
  return result;
}

```

## disassembly

```asm
0x1800013a0  mov     [rsp+arg_8], rbx
0x1800013a5  push    rdi
0x1800013a6  sub     rsp, 20h
0x1800013aa  mov     eax, cs:dword_18002F688
0x1800013b0  xor     ebx, ebx
0x1800013b2  movsxd  rdi, ecx
0x1800013b5  test    eax, eax
0x1800013b7  jnz     short loc_1800013CD
0x1800013b9  call    cs:__imp_GetCurrentThreadId
0x1800013bf  mov     edx, eax
0x1800013c1  xor     eax, eax
0x1800013c3  lock cmpxchg cs:dword_18002F688, edx
0x1800013cb  jz      short loc_1800013D9
0x1800013cd  lea     rcx, dword_18002F688; this
0x1800013d4  call    ?_LockSpin@CSmallSpinLock@@AEAAXXZ; CSmallSpinLock::_LockSpin(void)
0x1800013d9  test    edi, edi
0x1800013db  js      short loc_1800013F0
0x1800013dd  cmp     edi, dword ptr cs:qword_18002F680+4
0x1800013e3  jge     short loc_1800013F0
0x1800013e5  mov     rbx, cs:Src
0x1800013ec  mov     rbx, [rbx+rdi*8]
0x1800013f0  xor     eax, eax
0x1800013f2  xchg    eax, cs:dword_18002F688
0x1800013f8  test    rbx, rbx
0x1800013fb  lea     rax, ?s_unknownSnapin@BookKeeping@@0VSnapinRecord@@A; SnapinRecord BookKeeping::s_unknownSnapin
0x180001402  cmovnz  rax, rbx
0x180001406  mov     rbx, [rsp+28h+arg_8]
0x18000140b  add     rsp, 20h
0x18000140f  pop     rdi
0x180001410  retn
```
