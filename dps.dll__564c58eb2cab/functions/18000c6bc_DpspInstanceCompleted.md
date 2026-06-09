# DpspInstanceCompleted

- ea: `0x18000c6bc`
- end: `0x18000c77d`
- name: `DpspInstanceCompleted`
- size: `193`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800104f4`

## callees

- `0x1800013d0`
- `0x180002dc0`
- `0x180002f10`
- `0x180009090`
- `0x18000c6bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c75f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c75f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c735`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c735`

## string_xrefs

- `0x18000c715`: `DpspInstanceCompleted`

## pseudocode

```c
__int64 __fastcall DpspInstanceCompleted(__int64 a1)
{
  unsigned int v2; // esi
  struct INSTANCEINFO *v4[2]; // [rsp+30h] [rbp-38h] BYREF
  _QWORD *v5[2]; // [rsp+40h] [rbp-28h] BYREF
  _QWORD *v6[3]; // [rsp+50h] [rbp-18h] BYREF

  v4[1] = (struct INSTANCEINFO *)v4;
  v4[0] = (struct INSTANCEINFO *)v4;
  v6[1] = v6;
  v6[0] = v6;
  v5[1] = v5;
  v5[0] = v5;
  if ( a1 )
  {
    v2 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
    --*(_DWORD *)(a1 + 28);
    DpspGetDMDispatchInstanceList(a1, (__int64)v4);
    DpspDispatchInstanceList(v4, (__int64)v6, (__int64)v5);
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
  }
  else
  {
    v2 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
      (int)L"DpspInstanceCompleted",
      2821,
      (int)L"Error = %d",
      87);
  }
  DpspCloseInstanceList(v6, v5);
  return v2;
}

```

## disassembly

```asm
0x18000c6bc  push    rbp
0x18000c6be  push    rbx
0x18000c6bf  push    rsi
0x18000c6c0  push    rdi
0x18000c6c1  mov     rbp, rsp
0x18000c6c4  sub     rsp, 68h
0x18000c6c8  lea     rax, [rbp+var_38]
0x18000c6cc  mov     rdi, rcx
0x18000c6cf  mov     [rbp+var_30], rax
0x18000c6d3  lea     rax, [rbp+var_38]
0x18000c6d7  mov     [rbp+var_38], rax
0x18000c6db  lea     rax, [rbp+var_18]
0x18000c6df  mov     [rbp+var_10], rax
0x18000c6e3  lea     rax, [rbp+var_18]
0x18000c6e7  mov     [rbp+var_18], rax
0x18000c6eb  lea     rax, [rbp+var_28]
0x18000c6ef  mov     [rbp+var_20], rax
0x18000c6f3  lea     rax, [rbp+var_28]
0x18000c6f7  mov     [rbp+var_28], rax
0x18000c6fb  test    rcx, rcx
0x18000c6fe  jnz     short loc_18000C72F
0x18000c700  lea     r9, aErrorD; "Error = %d"
0x18000c707  mov     dword ptr [rsp+68h+Args], 57h ; 'W'; Args
0x18000c70f  mov     r8d, 0B05h; int
0x18000c715  lea     rdx, aDpspinstanceco_0; "DpspInstanceCompleted"
0x18000c71c  lea     rcx, aClientcoreBase_7; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000c723  mov     esi, 80070057h
0x18000c728  call    WdipTraceError
0x18000c72d  jmp     short loc_18000C765
0x18000c72f  add     rcx, 40h ; '@'; lpCriticalSection
0x18000c733  xor     esi, esi
0x18000c735  call    cs:__imp_EnterCriticalSection
0x18000c73b  dec     dword ptr [rdi+1Ch]
0x18000c73e  lea     rdx, [rbp+var_38]
0x18000c742  mov     rcx, rdi
0x18000c745  call    DpspGetDMDispatchInstanceList
0x18000c74a  lea     r8, [rbp+var_28]
0x18000c74e  lea     rdx, [rbp+var_18]
0x18000c752  lea     rcx, [rbp+var_38]
0x18000c756  call    DpspDispatchInstanceList
0x18000c75b  lea     rcx, [rdi+40h]; lpCriticalSection
0x18000c75f  call    cs:__imp_LeaveCriticalSection
0x18000c765  lea     rdx, [rbp+var_28]
0x18000c769  lea     rcx, [rbp+var_18]
0x18000c76d  call    DpspCloseInstanceList
0x18000c772  mov     eax, esi
0x18000c774  add     rsp, 68h
0x18000c778  pop     rdi
0x18000c779  pop     rsi
0x18000c77a  pop     rbx
0x18000c77b  pop     rbp
0x18000c77c  retn
```
