# CCompRC::Init(ushort *,int)

- ea: `0x140012450`
- end: `0x1400124f7`
- name: `?Init@CCompRC@@QEAAJPEAGH@Z`
- size: `167`
- prototype: `__int64 __fastcall(CCompRC *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001181c`

## callees

- `0x14000a148`
- `0x140012450`
- `0x140013f30`

## string_xrefs

- `0x140012468`: `mscorrc.dll`

## pseudocode

```c
__int64 __fastcall CCompRC::Init(CCompRC *this, unsigned __int16 *a2)
{
  struct IExecutionEngine *ExecutionEngine; // rax
  signed __int64 v3; // rax
  struct IExecutionEngine *v4; // rax

  dword_140027A08 = 1;
  if ( !qword_1400279F0 )
  {
    _InterlockedCompareExchange64(&qword_1400279F0, (signed __int64)L"mscorrc.dll", 0);
    if ( !qword_1400279F0 )
      return 2147942414LL;
  }
  if ( qword_1400279E8 )
    return 0;
  ExecutionEngine = GetExecutionEngine();
  v3 = (*(__int64 (__fastcall **)(struct IExecutionEngine *, _QWORD, __int64, __int64))(*(_QWORD *)ExecutionEngine + 72LL))(
         ExecutionEngine,
         0,
         12,
         152);
  if ( v3 )
  {
    if ( _InterlockedCompareExchange64(&qword_1400279E8, v3, 0) )
    {
      v4 = GetExecutionEngine();
      (*(void (__fastcall **)(struct IExecutionEngine *))(*(_QWORD *)v4 + 80LL))(v4);
    }
  }
  if ( qword_1400279E8 )
    return 0;
  else
    return 2147942414LL;
}

```

## disassembly

```asm
0x140012450  sub     rsp, 38h
0x140012454  cmp     cs:qword_1400279F0, 0
0x14001245c  mov     cs:dword_140027A08, 1
0x140012466  jnz     short loc_140012484
0x140012468  lea     rcx, aMscorrcDll; "mscorrc.dll"
0x14001246f  xor     eax, eax
0x140012471  lock cmpxchg cs:qword_1400279F0, rcx
0x14001247a  cmp     cs:qword_1400279F0, 0
0x140012482  jz      short loc_1400124E9
0x140012484  cmp     cs:qword_1400279E8, 0
0x14001248c  jnz     short loc_1400124F0
0x14001248e  call    ?GetExecutionEngine@@YAPEAUIExecutionEngine@@XZ; GetExecutionEngine(void)
0x140012493  mov     r10, rax
0x140012496  xor     edx, edx
0x140012498  mov     r9d, 98h
0x14001249e  mov     rcx, [rax]
0x1400124a1  lea     r8d, [rdx+0Ch]
0x1400124a5  mov     rax, [rcx+48h]
0x1400124a9  mov     rcx, r10
0x1400124ac  call    cs:__guard_dispatch_icall_fptr
0x1400124b2  mov     rdx, rax
0x1400124b5  test    rax, rax
0x1400124b8  jz      short loc_1400124DF
0x1400124ba  xor     eax, eax
0x1400124bc  lock cmpxchg cs:qword_1400279E8, rdx
0x1400124c5  jz      short loc_1400124DF
0x1400124c7  call    ?GetExecutionEngine@@YAPEAUIExecutionEngine@@XZ; GetExecutionEngine(void)
0x1400124cc  mov     r8, rax
0x1400124cf  mov     rcx, [rax]
0x1400124d2  mov     rax, [rcx+50h]
0x1400124d6  mov     rcx, r8
0x1400124d9  call    cs:__guard_dispatch_icall_fptr
0x1400124df  cmp     cs:qword_1400279E8, 0
0x1400124e7  jnz     short loc_1400124F0
0x1400124e9  mov     eax, 8007000Eh
0x1400124ee  jmp     short loc_1400124F2
0x1400124f0  xor     eax, eax
0x1400124f2  add     rsp, 38h
0x1400124f6  retn
```
