# wil::details_abi::WriteWnfUsageBuffer(__WIL__WNF_STATE_NAME const *,ulong,wil::details_abi::RawUsageIndex &)

- ea: `0x18000436c`
- end: `0x1800043e2`
- name: `?WriteWnfUsageBuffer@details_abi@wil@@YA_NPEBU__WIL__WNF_STATE_NAME@@KAEAVRawUsageIndex@12@@Z`
- size: `118`
- prototype: `bool __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned int, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800035c4`

## callees

- `0x18000436c`
- `0x18000a228`

## pseudocode

```c
char __fastcall wil::details_abi::WriteWnfUsageBuffer(
        wil::details_abi *this,
        const struct __WIL__WNF_STATE_NAME *a2,
        __int64 a3,
        struct wil::details_abi::RawUsageIndex *a4)
{
  int updated; // eax
  __int64 v7; // r9
  int v9; // [rsp+20h] [rbp-28h]
  int v10; // [rsp+20h] [rbp-28h]

  if ( !*(_BYTE *)(a3 + 56) )
    return 1;
  updated = wil_details_NtUpdateWnfStateData(
              (__int64)this,
              *(_QWORD *)(a3 + 24),
              *(_DWORD *)(a3 + 32) - (unsigned int)*(_QWORD *)(a3 + 24),
              (__int64)a4,
              v9,
              (int)a2,
              1);
  if ( updated != -1073741823 )
  {
    if ( updated )
      wil_details_NtUpdateWnfStateData(
        (__int64)this,
        *(_QWORD *)(a3 + 24),
        *(_DWORD *)(a3 + 32) - *(_QWORD *)(a3 + 24),
        v7,
        v10,
        0,
        0);
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18000436c  mov     [rsp+arg_0], rbx
0x180004371  push    rdi
0x180004372  sub     rsp, 40h
0x180004376  cmp     byte ptr [r8+38h], 0
0x18000437b  mov     rbx, r8
0x18000437e  mov     eax, edx
0x180004380  mov     rdi, rcx
0x180004383  jz      short loc_1800043AC
0x180004385  mov     rdx, [r8+18h]
0x180004389  mov     r8d, [r8+20h]
0x18000438d  sub     r8d, edx
0x180004390  mov     [rsp+48h+var_18], 1
0x180004398  mov     [rsp+48h+var_20], eax
0x18000439c  call    wil_details_NtUpdateWnfStateData
0x1800043a1  cmp     eax, 0C0000001h
0x1800043a6  jz      short loc_1800043B9
0x1800043a8  test    eax, eax
0x1800043aa  jnz     short loc_1800043BD
0x1800043ac  mov     al, 1
0x1800043ae  mov     rbx, [rsp+48h+arg_0]
0x1800043b3  add     rsp, 40h
0x1800043b7  pop     rdi
0x1800043b8  retn
0x1800043b9  xor     al, al
0x1800043bb  jmp     short loc_1800043AE
0x1800043bd  mov     rdx, [rbx+18h]
0x1800043c1  mov     rcx, rdi
0x1800043c4  mov     r8d, [rbx+20h]
0x1800043c8  sub     r8d, edx
0x1800043cb  mov     [rsp+48h+var_18], 0
0x1800043d3  mov     [rsp+48h+var_20], 0
0x1800043db  call    wil_details_NtUpdateWnfStateData
0x1800043e0  jmp     short loc_1800043AC
```
