# CheckThreadState

- ea: `0x180005f10`
- end: `0x180005fe5`
- name: `CheckThreadState`
- size: `213`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800407a0`
- `0x1800407e0`
- `0x180040820`
- `0x180040840`
- `0x180040870`

## callees

- `0x180005f10`
- `0x180045030`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x180005f36`
- `KERNEL32!TlsGetValue` at `0x180005f36`
- `KERNEL32!RaiseException` at `0x180005f91`
- `KERNEL32!RaiseException` at `0x180005f91`
- `KERNEL32!TlsSetValue` at `0x180005fb0`
- `KERNEL32!TlsSetValue` at `0x180005fb0`
- `KERNEL32!TlsAlloc` at `0x180005fb8`
- `KERNEL32!TlsAlloc` at `0x180005fb8`
- `KERNEL32!TlsFree` at `0x180005fd3`
- `KERNEL32!TlsFree` at `0x180005fd3`
- `KERNEL32!HeapAlloc` at `0x180005f6c`
- `KERNEL32!HeapAlloc` at `0x180005f6c`
- `KERNEL32!GetProcessHeap` at `0x180005f5b`
- `KERNEL32!GetProcessHeap` at `0x180005f5b`

## pseudocode

```c
void *__fastcall CheckThreadState(int a1, int a2)
{
  void *Value; // rbx
  HANDLE ProcessHeap; // rax
  DWORD v7; // ecx

  if ( dwTlsIndex == -1 )
  {
    v7 = TlsAlloc();
    if ( _InterlockedCompareExchange((volatile signed __int32 *)&dwTlsIndex, v7, -1) != -1 )
      TlsFree(v7);
  }
  Value = TlsGetValue(dwTlsIndex);
  if ( Value || !a2 )
    return Value;
  ProcessHeap = GetProcessHeap();
  Value = HeapAlloc(ProcessHeap, 0, 0xA0u);
  if ( Value )
  {
LABEL_9:
    memset_thunk_772440563353939046(Value, 0, 0xA0u);
    TlsSetValue(dwTlsIndex, Value);
    return Value;
  }
  if ( a1 != 9 && a1 != 6 )
  {
    RaiseException(0xC0000017, 0, 0, 0);
    goto LABEL_9;
  }
  return 0;
}

```

## disassembly

```asm
0x180005f10  mov     [rsp+arg_0], rbx
0x180005f15  mov     [rsp+arg_8], rsi
0x180005f1a  push    rdi
0x180005f1b  sub     rsp, 20h
0x180005f1f  cmp     cs:dwTlsIndex, 0FFFFFFFFh
0x180005f26  mov     edi, edx
0x180005f28  mov     esi, ecx
0x180005f2a  jz      loc_180005FB8
0x180005f30  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180005f36  call    cs:__imp_TlsGetValue
0x180005f3c  mov     rbx, rax
0x180005f3f  test    rax, rax
0x180005f42  jz      short loc_180005F57
0x180005f44  mov     rax, rbx
0x180005f47  mov     rbx, [rsp+28h+arg_0]
0x180005f4c  mov     rsi, [rsp+28h+arg_8]
0x180005f51  add     rsp, 20h
0x180005f55  pop     rdi
0x180005f56  retn
0x180005f57  test    edi, edi
0x180005f59  jz      short loc_180005F44
0x180005f5b  call    cs:__imp_GetProcessHeap
0x180005f61  xor     edx, edx; dwFlags
0x180005f63  mov     r8d, 0A0h; dwBytes
0x180005f69  mov     rcx, rax; hHeap
0x180005f6c  call    cs:__imp_HeapAlloc
0x180005f72  mov     rbx, rax
0x180005f75  test    rax, rax
0x180005f78  jnz     short loc_180005F97
0x180005f7a  cmp     esi, 9
0x180005f7d  jz      short loc_180005FDE
0x180005f7f  cmp     esi, 6
0x180005f82  jz      short loc_180005FDE
0x180005f84  xor     r9d, r9d; lpArguments
0x180005f87  xor     r8d, r8d; nNumberOfArguments
0x180005f8a  xor     edx, edx; dwExceptionFlags
0x180005f8c  mov     ecx, 0C0000017h; dwExceptionCode
0x180005f91  call    cs:__imp_RaiseException
0x180005f97  xor     edx, edx; Val
0x180005f99  mov     r8d, 0A0h; Size
0x180005f9f  mov     rcx, rbx; void *
0x180005fa2  call    memset$thunk$772440563353939046
0x180005fa7  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180005fad  mov     rdx, rbx; lpTlsValue
0x180005fb0  call    cs:__imp_TlsSetValue
0x180005fb6  jmp     short loc_180005F44
0x180005fb8  call    cs:__imp_TlsAlloc
0x180005fbe  mov     ecx, eax; dwTlsIndex
0x180005fc0  mov     eax, 0FFFFFFFFh
0x180005fc5  lock cmpxchg cs:dwTlsIndex, ecx
0x180005fcd  jz      loc_180005F30
0x180005fd3  call    cs:__imp_TlsFree
0x180005fd9  jmp     loc_180005F30
0x180005fde  xor     eax, eax
0x180005fe0  jmp     loc_180005F47
```
