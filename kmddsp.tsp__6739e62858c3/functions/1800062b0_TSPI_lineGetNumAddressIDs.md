# TSPI_lineGetNumAddressIDs

- ea: `0x1800062b0`
- end: `0x1800063a5`
- name: `TSPI_lineGetNumAddressIDs`
- size: `245`
- prototype: `LONG __stdcall(HDRVLINE hdLine, LPDWORD lpdwNumAddressIDs)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x180002494`
- `0x180002ad0`
- `0x180003488`
- `0x1800037a8`
- `0x1800062b0`
- `0x180007df8`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180006334`
- `KERNEL32!LeaveCriticalSection` at `0x180006370`
- `KERNEL32!LeaveCriticalSection` at `0x180006334`
- `KERNEL32!LeaveCriticalSection` at `0x180006370`
- `KERNEL32!EnterCriticalSection` at `0x180006312`
- `KERNEL32!EnterCriticalSection` at `0x180006312`

## string_xrefs

- `0x1800062dd`: `lineGetNumAddressIDs(%d): line(%p)`
- `0x18000637f`: `lineGetNumAddressIDs: numAddressIDs(%x)`

## pseudocode

```c
LONG __stdcall TSPI_lineGetNumAddressIDs(HDRVLINE hdLine, LPDWORD lpdwNumAddressIDs)
{
  LONG result; // eax
  unsigned int v5; // edi
  __int64 LineDevNode; // rax
  __int64 v7; // rbx
  LONG v8; // ebx
  __int64 LineDevCaps; // rax
  __int64 v10; // [rsp+60h] [rbp+18h] BYREF

  v10 = 0;
  TspLog(8, "lineGetNumAddressIDs(%d): line(%p)", ++dword_18000E264, hdLine);
  result = GetLineObjWithReadLock(hdLine, &v10);
  if ( !result )
  {
    v5 = *(_DWORD *)(v10 + 4);
    EnterCriticalSection(&stru_18000E3B0);
    LineDevNode = GetLineDevNode(v5);
    v7 = LineDevNode;
    if ( LineDevNode
      && ((LineDevCaps = *(_QWORD *)(LineDevNode + 8)) != 0
       || (LineDevCaps = GetLineDevCaps(v5, *(unsigned int *)(v7 + 32)), (*(_QWORD *)(v7 + 8) = LineDevCaps) != 0)) )
    {
      *lpdwNumAddressIDs = *(_DWORD *)(LineDevCaps + 48);
      LeaveCriticalSection(&stru_18000E3B0);
      v8 = 0;
      TspLog(4, "lineGetNumAddressIDs: numAddressIDs(%x)", *lpdwNumAddressIDs);
    }
    else
    {
      LeaveCriticalSection(&stru_18000E3B0);
      v8 = -2147483580;
    }
    ReleaseObjReadLock(hdLine);
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x1800062b0  push    rbx
0x1800062b2  push    rsi
0x1800062b3  push    rdi
0x1800062b4  push    r14
0x1800062b6  sub     rsp, 28h
0x1800062ba  mov     r8d, cs:dword_18000E264
0x1800062c1  mov     r14, rdx
0x1800062c4  inc     r8d
0x1800062c7  mov     [rsp+48h+arg_10], 0
0x1800062d0  mov     rsi, rcx
0x1800062d3  mov     cs:dword_18000E264, r8d
0x1800062da  mov     r9, rcx
0x1800062dd  lea     rdx, aLinegetnumaddr_0; "lineGetNumAddressIDs(%d): line(%p)"
0x1800062e4  mov     ecx, 8
0x1800062e9  call    TspLog
0x1800062ee  lea     rdx, [rsp+48h+arg_10]
0x1800062f3  mov     rcx, rsi
0x1800062f6  call    GetLineObjWithReadLock
0x1800062fb  test    eax, eax
0x1800062fd  jnz     loc_18000639A
0x180006303  mov     rax, [rsp+48h+arg_10]
0x180006308  lea     rcx, stru_18000E3B0; lpCriticalSection
0x18000630f  mov     edi, [rax+4]
0x180006312  call    cs:__imp_EnterCriticalSection
0x180006319  nop     dword ptr [rax+rax+00h]
0x18000631e  mov     ecx, edi
0x180006320  call    GetLineDevNode
0x180006325  mov     rbx, rax
0x180006328  test    rax, rax
0x18000632b  jnz     short loc_180006347
0x18000632d  lea     rcx, stru_18000E3B0; lpCriticalSection
0x180006334  call    cs:__imp_LeaveCriticalSection
0x18000633b  nop     dword ptr [rax+rax+00h]
0x180006340  mov     ebx, 80000044h
0x180006345  jmp     short loc_180006390
0x180006347  mov     rax, [rax+8]
0x18000634b  test    rax, rax
0x18000634e  jnz     short loc_180006363
0x180006350  mov     edx, [rbx+20h]
0x180006353  mov     ecx, edi
0x180006355  call    GetLineDevCaps
0x18000635a  mov     [rbx+8], rax
0x18000635e  test    rax, rax
0x180006361  jz      short loc_18000632D
0x180006363  mov     eax, [rax+30h]
0x180006366  lea     rcx, stru_18000E3B0; lpCriticalSection
0x18000636d  mov     [r14], eax
0x180006370  call    cs:__imp_LeaveCriticalSection
0x180006377  nop     dword ptr [rax+rax+00h]
0x18000637c  mov     r8d, [r14]
0x18000637f  lea     rdx, aLinegetnumaddr; "lineGetNumAddressIDs: numAddressIDs(%x)"
0x180006386  xor     ebx, ebx
0x180006388  lea     ecx, [rbx+4]
0x18000638b  call    TspLog
0x180006390  mov     rcx, rsi
0x180006393  call    ReleaseObjReadLock
0x180006398  mov     eax, ebx
0x18000639a  add     rsp, 28h
0x18000639e  pop     r14
0x1800063a0  pop     rdi
0x1800063a1  pop     rsi
0x1800063a2  pop     rbx
0x1800063a3  retn
```
