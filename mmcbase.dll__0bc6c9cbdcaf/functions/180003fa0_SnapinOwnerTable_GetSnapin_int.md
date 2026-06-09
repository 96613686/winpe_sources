# SnapinOwnerTable::GetSnapin(int)

- ea: `0x180003fa0`
- end: `0x180004006`
- name: `?GetSnapin@SnapinOwnerTable@@QEAAPEAVSnapinRecord@@H@Z`
- size: `102`
- prototype: `struct SnapinRecord *__fastcall(SnapinOwnerTable *__hidden this, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f2fc`

## callees

- `0x180003fa0`
- `0x18001984c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003fb9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003fb9`

## pseudocode

```c
struct SnapinRecord *__fastcall SnapinOwnerTable::GetSnapin(SnapinOwnerTable *this, int a2)
{
  __int64 v2; // rdi
  __int64 v3; // rbx

  v2 = 0;
  v3 = a2;
  if ( dword_18002F688
    || _InterlockedCompareExchange((volatile signed __int32 *)&dword_18002F688, GetCurrentThreadId(), 0) )
  {
    CSmallSpinLock::_LockSpin((CSmallSpinLock *)&dword_18002F688);
  }
  if ( (int)v3 >= 0 && (int)v3 < SHIDWORD(qword_18002F680) )
    v2 = *((_QWORD *)Src + v3);
  _InterlockedExchange((volatile __int32 *)&dword_18002F688, 0);
  return (struct SnapinRecord *)v2;
}

```

## disassembly

```asm
0x180003fa0  mov     [rsp+arg_0], rbx
0x180003fa5  push    rdi
0x180003fa6  sub     rsp, 20h
0x180003faa  mov     eax, cs:dword_18002F688
0x180003fb0  xor     edi, edi
0x180003fb2  movsxd  rbx, edx
0x180003fb5  test    eax, eax
0x180003fb7  jnz     short loc_180003FCD
0x180003fb9  call    cs:__imp_GetCurrentThreadId
0x180003fbf  mov     ecx, eax
0x180003fc1  xor     eax, eax
0x180003fc3  lock cmpxchg cs:dword_18002F688, ecx
0x180003fcb  jz      short loc_180003FD9
0x180003fcd  lea     rcx, dword_18002F688; this
0x180003fd4  call    ?_LockSpin@CSmallSpinLock@@AEAAXXZ; CSmallSpinLock::_LockSpin(void)
0x180003fd9  test    ebx, ebx
0x180003fdb  js      short loc_180003FF0
0x180003fdd  cmp     ebx, dword ptr cs:qword_18002F680+4
0x180003fe3  jge     short loc_180003FF0
0x180003fe5  mov     rax, cs:Src
0x180003fec  mov     rdi, [rax+rbx*8]
0x180003ff0  mov     rbx, [rsp+28h+arg_0]
0x180003ff5  xor     ecx, ecx
0x180003ff7  xchg    ecx, cs:dword_18002F688
0x180003ffd  mov     rax, rdi
0x180004000  add     rsp, 20h
0x180004004  pop     rdi
0x180004005  retn
```
