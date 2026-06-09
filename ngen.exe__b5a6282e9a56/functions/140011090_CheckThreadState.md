# CheckThreadState

- ea: `0x140011090`
- end: `0x140011160`
- name: `CheckThreadState`
- size: `208`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140011210`
- `0x140011270`
- `0x140011290`
- `0x1400112d0`
- `0x140011300`

## callees

- `0x140011090`
- `0x140013ce8`

## import_xrefs

- `KERNEL32!TlsFree` at `0x1400110c3`
- `KERNEL32!TlsFree` at `0x1400110c3`
- `KERNEL32!TlsGetValue` at `0x1400110dd`
- `KERNEL32!TlsGetValue` at `0x1400110dd`
- `KERNEL32!TlsAlloc` at `0x1400110ae`
- `KERNEL32!TlsAlloc` at `0x1400110ae`
- `KERNEL32!TlsSetValue` at `0x140011143`
- `KERNEL32!TlsSetValue` at `0x140011143`
- `KERNEL32!RaiseException` at `0x140011127`
- `KERNEL32!RaiseException` at `0x140011127`
- `KERNEL32!HeapAlloc` at `0x140011102`
- `KERNEL32!HeapAlloc` at `0x140011102`
- `KERNEL32!GetProcessHeap` at `0x1400110ef`
- `KERNEL32!GetProcessHeap` at `0x1400110ef`

## pseudocode

```c
void *__fastcall CheckThreadState(int a1, int a2)
{
  DWORD v4; // ecx
  DWORD v5; // ecx
  void *Value; // rbx
  HANDLE ProcessHeap; // rax

  v4 = dwTlsIndex;
  if ( dwTlsIndex == -1 )
  {
    v5 = TlsAlloc();
    if ( _InterlockedCompareExchange((volatile signed __int32 *)&dwTlsIndex, v5, -1) != -1 )
      TlsFree(v5);
    v4 = dwTlsIndex;
    __ClrFlsGetBlock = ClrFlsGetBlockDirect;
  }
  Value = TlsGetValue(v4);
  if ( Value || !a2 )
    return Value;
  ProcessHeap = GetProcessHeap();
  Value = HeapAlloc(ProcessHeap, 0, 0xB0u);
  if ( Value )
  {
LABEL_11:
    memset_0(Value, 0, 0xB0u);
    TlsSetValue(dwTlsIndex, Value);
    return Value;
  }
  if ( a1 != 9 && a1 != 6 )
  {
    RaiseException(0xC0000017, 0, 0, 0);
    goto LABEL_11;
  }
  return 0;
}

```

## disassembly

```asm
0x140011090  mov     [rsp+arg_0], rbx
0x140011095  mov     [rsp+arg_8], rsi
0x14001109a  push    rdi
0x14001109b  sub     rsp, 20h
0x14001109f  mov     edi, ecx
0x1400110a1  mov     esi, edx
0x1400110a3  mov     ecx, cs:dwTlsIndex
0x1400110a9  cmp     ecx, 0FFFFFFFFh
0x1400110ac  jnz     short loc_1400110DD
0x1400110ae  call    cs:__imp_TlsAlloc
0x1400110b4  mov     ecx, eax; dwTlsIndex
0x1400110b6  or      eax, 0FFFFFFFFh
0x1400110b9  lock cmpxchg cs:dwTlsIndex, ecx
0x1400110c1  jz      short loc_1400110C9
0x1400110c3  call    cs:__imp_TlsFree
0x1400110c9  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1400110cf  lea     rax, ?ClrFlsGetBlockDirect@@YAPEAXXZ; ClrFlsGetBlockDirect(void)
0x1400110d6  mov     cs:?__ClrFlsGetBlock@@3P6APEAXXZEA, rax; void * (*__ClrFlsGetBlock)(void)
0x1400110dd  call    cs:__imp_TlsGetValue
0x1400110e3  mov     rbx, rax
0x1400110e6  test    rax, rax
0x1400110e9  jnz     short loc_140011149
0x1400110eb  test    esi, esi
0x1400110ed  jz      short loc_140011149
0x1400110ef  call    cs:__imp_GetProcessHeap
0x1400110f5  mov     esi, 0B0h
0x1400110fa  xor     edx, edx; dwFlags
0x1400110fc  mov     rcx, rax; hHeap
0x1400110ff  mov     r8d, esi; dwBytes
0x140011102  call    cs:__imp_HeapAlloc
0x140011108  mov     rbx, rax
0x14001110b  test    rax, rax
0x14001110e  jnz     short loc_14001112D
0x140011110  cmp     edi, 9
0x140011113  jz      short loc_14001115C
0x140011115  cmp     edi, 6
0x140011118  jz      short loc_14001115C
0x14001111a  xor     r9d, r9d; lpArguments
0x14001111d  xor     r8d, r8d; nNumberOfArguments
0x140011120  xor     edx, edx; dwExceptionFlags
0x140011122  mov     ecx, 0C0000017h; dwExceptionCode
0x140011127  call    cs:__imp_RaiseException
0x14001112d  mov     r8, rsi; Size
0x140011130  xor     edx, edx; Val
0x140011132  mov     rcx, rbx; void *
0x140011135  call    memset_0
0x14001113a  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x140011140  mov     rdx, rbx; lpTlsValue
0x140011143  call    cs:__imp_TlsSetValue
0x140011149  mov     rax, rbx
0x14001114c  mov     rbx, [rsp+28h+arg_0]
0x140011151  mov     rsi, [rsp+28h+arg_8]
0x140011156  add     rsp, 20h
0x14001115a  pop     rdi
0x14001115b  retn
0x14001115c  xor     eax, eax
0x14001115e  jmp     short loc_14001114C
```
