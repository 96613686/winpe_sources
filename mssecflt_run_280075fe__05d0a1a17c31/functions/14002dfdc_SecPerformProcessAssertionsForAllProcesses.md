# SecPerformProcessAssertionsForAllProcesses

- ea: `0x14002dfdc`
- end: `0x14002e0ef`
- name: `SecPerformProcessAssertionsForAllProcesses`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x140043ff0`

## callees

- `0x14000ac04`
- `0x14001042b`
- `0x1400104eb`
- `0x140011650`
- `0x14002d080`
- `0x14002dfdc`

## import_xrefs

- `ntoskrnl!PsLookupProcessByProcessId` at `0x14002e066`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14002e066`
- `ntoskrnl!ObfDereferenceObject` at `0x14002e08b`
- `ntoskrnl!ObfDereferenceObject` at `0x14002e08b`

## pseudocode

```c
__int64 __fastcall SecPerformProcessAssertionsForAllProcesses(__int64 a1)
{
  __int64 v2; // rdi
  __int64 v3; // rbp
  __int64 v4; // rbx
  char *v5; // rdx
  __int64 v6; // rax
  _QWORD *v7; // rsi
  _QWORD *v8; // r14
  PEPROCESS Process; // [rsp+20h] [rbp-18h] BYREF

  Process = 0;
  if ( (BYTE8(xmmword_14001B740) & 1) == 0 )
    return SecEnumerateProcessContexts(a1, 0);
  FltAcquirePushLockSharedEx_0((char *)SecProcessTable + 8, 0);
  v2 = 0;
  v3 = 128;
  v4 = 0;
  do
  {
    v5 = (char *)SecProcessTable;
    v6 = *((_QWORD *)SecProcessTable + 40);
    v7 = *(_QWORD **)(v2 + v6);
    if ( v7 != (_QWORD *)(v4 + v6) )
    {
      do
      {
        v8 = v7 - 2;
        v7 = (_QWORD *)*v7;
        if ( PsLookupProcessByProcessId((HANDLE)v8[4], &Process) >= 0 )
        {
          SecDetPerformProcessAssertionsWithContext(Process, v8, 0);
          ObfDereferenceObject(Process);
        }
        v5 = (char *)SecProcessTable;
      }
      while ( v7 != (_QWORD *)(v4 + *((_QWORD *)SecProcessTable + 40)) );
    }
    v4 += 16;
    v2 += 16;
    --v3;
  }
  while ( v3 );
  return FltReleasePushLockEx_0(v5 + 8, 0);
}

```

## disassembly

```asm
0x14002dfdc  mov     r11, rsp
0x14002dfdf  mov     [r11+8], rbx
0x14002dfe3  mov     [r11+10h], rbp
0x14002dfe7  mov     [r11+18h], rsi
0x14002dfeb  mov     [r11+20h], rdi
0x14002dfef  push    r14
0x14002dff1  sub     rsp, 30h
0x14002dff5  mov     rax, cs:__security_cookie
0x14002dffc  xor     rax, rsp
0x14002dfff  mov     [rsp+38h+var_10], rax
0x14002e004  test    byte ptr cs:xmmword_14001B740+8, 1
0x14002e00b  mov     qword ptr [r11-18h], 0
0x14002e013  jnz     short loc_14002E021
0x14002e015  xor     edx, edx
0x14002e017  call    SecEnumerateProcessContexts
0x14002e01c  jmp     loc_14002E0C6
0x14002e021  mov     rcx, cs:SecProcessTable
0x14002e028  xor     edx, edx
0x14002e02a  add     rcx, 8
0x14002e02e  call    FltAcquirePushLockSharedEx_0
0x14002e033  xor     edi, edi
0x14002e035  mov     ebp, 80h
0x14002e03a  xor     ebx, ebx
0x14002e03c  mov     rdx, cs:SecProcessTable
0x14002e043  mov     rax, [rdx+140h]
0x14002e04a  mov     rsi, [rdi+rax]
0x14002e04e  add     rax, rbx
0x14002e051  cmp     rsi, rax
0x14002e054  jz      short loc_14002E0AD
0x14002e056  lea     r14, [rsi-10h]
0x14002e05a  mov     rsi, [rsi]
0x14002e05d  mov     rcx, [r14+20h]; ProcessId
0x14002e061  lea     rdx, [rsp+38h+Process]; Process
0x14002e066  call    cs:__imp_PsLookupProcessByProcessId
0x14002e06d  nop     dword ptr [rax+rax+00h]
0x14002e072  test    eax, eax
0x14002e074  js      short loc_14002E097
0x14002e076  mov     rcx, [rsp+38h+Process]
0x14002e07b  xor     r8d, r8d
0x14002e07e  mov     rdx, r14
0x14002e081  call    SecDetPerformProcessAssertionsWithContext
0x14002e086  mov     rcx, [rsp+38h+Process]; Object
0x14002e08b  call    cs:__imp_ObfDereferenceObject
0x14002e092  nop     dword ptr [rax+rax+00h]
0x14002e097  mov     rdx, cs:SecProcessTable
0x14002e09e  mov     rcx, [rdx+140h]
0x14002e0a5  add     rcx, rbx
0x14002e0a8  cmp     rsi, rcx
0x14002e0ab  jnz     short loc_14002E056
0x14002e0ad  add     rbx, 10h
0x14002e0b1  add     rdi, 10h
0x14002e0b5  sub     rbp, 1
0x14002e0b9  jnz     short loc_14002E03C
0x14002e0bb  lea     rcx, [rdx+8]
0x14002e0bf  xor     edx, edx
0x14002e0c1  call    FltReleasePushLockEx_0
0x14002e0c6  mov     rcx, [rsp+38h+var_10]
0x14002e0cb  xor     rcx, rsp; StackCookie
0x14002e0ce  call    __security_check_cookie
0x14002e0d3  mov     rbx, [rsp+38h+arg_0]
0x14002e0d8  mov     rbp, [rsp+38h+arg_8]
0x14002e0dd  mov     rsi, [rsp+38h+arg_10]
0x14002e0e2  mov     rdi, [rsp+38h+arg_18]
0x14002e0e7  add     rsp, 30h
0x14002e0eb  pop     r14
0x14002e0ed  retn
```
