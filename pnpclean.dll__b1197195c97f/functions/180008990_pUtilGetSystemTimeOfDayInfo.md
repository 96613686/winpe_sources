# pUtilGetSystemTimeOfDayInfo

- ea: `0x180008990`
- end: `0x180008a2a`
- name: `pUtilGetSystemTimeOfDayInfo`
- size: `154`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004e74`
- `0x180007680`

## callees

- `0x180008990`
- `0x180008e30`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x1800089d1`
- `ntdll!NtQuerySystemInformation` at `0x1800089d1`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800089dd`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800089dd`

## pseudocode

```c
__int64 __fastcall pUtilGetSystemTimeOfDayInfo(_QWORD *a1, _QWORD *a2)
{
  int v4; // eax
  unsigned int v5; // ecx
  _OWORD SystemInformation[3]; // [rsp+20h] [rbp-48h] BYREF

  memset(SystemInformation, 0, sizeof(SystemInformation));
  v4 = NtQuerySystemInformation(SystemTimeOfDayInformation, SystemInformation, 0x30u, 0);
  if ( v4 >= 0 )
  {
    v5 = 0;
    if ( a1 )
      *a1 = *((_QWORD *)&SystemInformation[0] + 1);
    if ( a2 )
      *a2 = *(_QWORD *)&SystemInformation[0];
  }
  else
  {
    return RtlNtStatusToDosErrorNoTeb(v4);
  }
  return v5;
}

```

## disassembly

```asm
0x180008990  mov     [rsp+arg_10], rbx
0x180008995  push    rdi
0x180008996  sub     rsp, 60h
0x18000899a  mov     rax, cs:__security_cookie
0x1800089a1  xor     rax, rsp
0x1800089a4  mov     [rsp+68h+var_18], rax
0x1800089a9  xorps   xmm0, xmm0
0x1800089ac  xor     r9d, r9d; ReturnLength
0x1800089af  mov     rbx, rdx
0x1800089b2  mov     rdi, rcx
0x1800089b5  lea     rdx, [rsp+68h+SystemInformation]; SystemInformation
0x1800089ba  movups  [rsp+68h+SystemInformation], xmm0
0x1800089bf  lea     r8d, [r9+30h]; SystemInformationLength
0x1800089c3  lea     ecx, [r9+3]; SystemInformationClass
0x1800089c7  movups  [rsp+68h+var_38], xmm0
0x1800089cc  movups  [rsp+68h+var_28], xmm0
0x1800089d1  call    cs:__imp_NtQuerySystemInformation
0x1800089d7  test    eax, eax
0x1800089d9  jns     short loc_1800089E7
0x1800089db  mov     ecx, eax; Status
0x1800089dd  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800089e3  mov     ecx, eax
0x1800089e5  jmp     short loc_180008A0D
0x1800089e7  xor     ecx, ecx
0x1800089e9  test    rdi, rdi
0x1800089ec  jz      short loc_1800089FB
0x1800089ee  mov     eax, dword ptr [rsp+68h+SystemInformation+8]
0x1800089f2  mov     [rdi], eax
0x1800089f4  mov     eax, dword ptr [rsp+68h+SystemInformation+0Ch]
0x1800089f8  mov     [rdi+4], eax
0x1800089fb  test    rbx, rbx
0x1800089fe  jz      short loc_180008A0D
0x180008a00  mov     eax, dword ptr [rsp+68h+SystemInformation]
0x180008a04  mov     [rbx], eax
0x180008a06  mov     eax, dword ptr [rsp+68h+SystemInformation+4]
0x180008a0a  mov     [rbx+4], eax
0x180008a0d  mov     eax, ecx
0x180008a0f  mov     rcx, [rsp+68h+var_18]
0x180008a14  xor     rcx, rsp; StackCookie
0x180008a17  call    __security_check_cookie
0x180008a1c  mov     rbx, [rsp+68h+arg_10]
0x180008a24  add     rsp, 60h
0x180008a28  pop     rdi
0x180008a29  retn
```
