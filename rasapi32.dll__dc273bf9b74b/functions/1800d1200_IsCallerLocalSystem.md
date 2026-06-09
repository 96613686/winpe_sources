# IsCallerLocalSystem

- ea: `0x1800d1200`
- end: `0x1800d127b`
- name: `IsCallerLocalSystem`
- size: `123`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000642c`

## callees

- `0x1800d1200`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800d123d`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800d123d`
- `rtutils!TracePrintfExA` at `0x1800d125c`
- `rtutils!TracePrintfExA` at `0x1800d125c`

## string_xrefs

- `0x1800d1252`: `CheckTokenMemberShip for local system failed.`

## pseudocode

```c
__int64 IsCallerLocalSystem()
{
  WINBOOL IsMember; // [rsp+20h] [rbp-20h] BYREF
  _DWORD SidToCheck[4]; // [rsp+28h] [rbp-18h] BYREF

  IsMember = 0;
  SidToCheck[0] = 257;
  SidToCheck[1] = 83886080;
  SidToCheck[2] = 18;
  if ( CheckTokenMembership(0, SidToCheck, &IsMember) )
    return (unsigned int)IsMember;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "CheckTokenMemberShip for local system failed.");
  return 0;
}

```

## disassembly

```asm
0x1800d1200  push    rbp
0x1800d1202  mov     rbp, rsp
0x1800d1205  sub     rsp, 40h
0x1800d1209  mov     rax, cs:__security_cookie
0x1800d1210  xor     rax, rsp
0x1800d1213  mov     [rbp+var_8], rax
0x1800d1217  lea     r8, [rbp+IsMember]; IsMember
0x1800d121b  mov     [rbp+IsMember], 0
0x1800d1222  lea     rdx, [rbp+SidToCheck]; SidToCheck
0x1800d1226  mov     [rbp+SidToCheck], 101h
0x1800d122d  xor     ecx, ecx; TokenHandle
0x1800d122f  mov     [rbp+var_14], 5000000h
0x1800d1236  mov     [rbp+var_10], 12h
0x1800d123d  call    cs:__imp_CheckTokenMembership
0x1800d1243  test    eax, eax
0x1800d1245  jnz     short loc_1800D1266
0x1800d1247  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800d124d  cmp     ecx, 0FFFFFFFFh
0x1800d1250  jz      short loc_1800D1262
0x1800d1252  lea     r8, aChecktokenmemb; "CheckTokenMemberShip for local system f"...
0x1800d1259  lea     edx, [rax+0Ch]; dwFlags
0x1800d125c  call    cs:__imp_TracePrintfExA
0x1800d1262  xor     eax, eax
0x1800d1264  jmp     short loc_1800D1269
0x1800d1266  mov     eax, [rbp+IsMember]
0x1800d1269  mov     rcx, [rbp+var_8]
0x1800d126d  xor     rcx, rsp; StackCookie
0x1800d1270  call    __security_check_cookie
0x1800d1275  add     rsp, 40h
0x1800d1279  pop     rbp
0x1800d127a  retn
```
