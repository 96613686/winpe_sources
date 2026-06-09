# PoWdiPass1_ServiceVeto

- ea: `0x180004240`
- end: `0x1800042e9`
- name: `PoWdiPass1_ServiceVeto`
- size: `169`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x1800018a8`
- `0x1800022dc`
- `0x1800039b0`
- `0x180004240`
- `0x180004930`

## string_xrefs

- `0x180004282`: `ServiceName`

## pseudocode

```c
TDHSTATUS __fastcall PoWdiPass1_ServiceVeto(struct _EVENT_RECORD *a1, __int64 a2, __int64 a3)
{
  bool v3; // zf
  TDHSTATUS result; // eax
  unsigned __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // [rsp+30h] [rbp-A8h] BYREF
  BYTE v9[128]; // [rsp+40h] [rbp-98h] BYREF

  v3 = *(_DWORD *)(a2 + 8) == 0;
  LODWORD(v8) = 0;
  if ( v3 )
    *(_DWORD *)(a2 + 8) = 3;
  result = PoWdiGetProperty(a1, (ULONGLONG)L"ServiceName", a3, v9, 0x7Eu, (ULONG *)&v8);
  if ( !result && (unsigned int)v8 <= 0x7E )
  {
    v6 = (unsigned int)v8 & 0xFFFFFFFE;
    if ( v6 >= 0x80 )
      _report_rangecheckfailure();
    v7 = *(unsigned int *)(a2 + 4);
    *(_WORD *)&v9[v6] = 0;
    return PoWdiLogVetoTelemetry(0, v7, 2, v9);
  }
  return result;
}

```

## disassembly

```asm
0x180004240  push    rbx
0x180004242  sub     rsp, 0D0h
0x180004249  mov     rax, cs:__security_cookie
0x180004250  xor     rax, rsp
0x180004253  mov     [rsp+0D8h+var_18], rax
0x18000425b  cmp     dword ptr [rdx+8], 0
0x18000425f  mov     rbx, rdx
0x180004262  mov     dword ptr [rsp+0D8h+var_A8], 0
0x18000426a  jnz     short loc_180004273
0x18000426c  mov     dword ptr [rdx+8], 3
0x180004273  lea     rax, [rsp+0D8h+var_A8]
0x180004278  mov     [rsp+0D8h+var_B0], rax; __int64
0x18000427d  lea     r9, [rsp+0D8h+var_98]
0x180004282  lea     rdx, aServicename; "ServiceName"
0x180004289  mov     [rsp+0D8h+var_B8], 7Eh ; '~'; int
0x180004291  call    PoWdiGetProperty
0x180004296  test    eax, eax
0x180004298  jnz     short loc_1800042CA
0x18000429a  cmp     dword ptr [rsp+0D8h+var_A8], 7Eh ; '~'
0x18000429f  ja      short loc_1800042CA
0x1800042a1  mov     ecx, dword ptr [rsp+0D8h+var_A8]
0x1800042a5  and     rcx, 0FFFFFFFFFFFFFFFEh
0x1800042a9  cmp     rcx, 80h
0x1800042b0  jnb     short loc_1800042E3
0x1800042b2  mov     edx, [rbx+4]
0x1800042b5  lea     r9, [rsp+0D8h+var_98]
0x1800042ba  mov     word ptr [rsp+rcx+0D8h+var_98], ax
0x1800042bf  lea     r8d, [rax+2]
0x1800042c3  xor     ecx, ecx
0x1800042c5  call    PoWdiLogVetoTelemetry
0x1800042ca  mov     rcx, [rsp+0D8h+var_18]
0x1800042d2  xor     rcx, rsp; StackCookie
0x1800042d5  call    __security_check_cookie
0x1800042da  add     rsp, 0D0h
0x1800042e1  pop     rbx
0x1800042e2  retn
0x1800042e3  call    __report_rangecheckfailure
```
