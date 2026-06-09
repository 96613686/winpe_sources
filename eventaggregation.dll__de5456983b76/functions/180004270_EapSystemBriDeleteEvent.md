# EapSystemBriDeleteEvent

- ea: `0x180004270`
- end: `0x1800042e5`
- name: `EapSystemBriDeleteEvent`
- size: `117`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800022b0`
- `0x180008d98`

## callees

- `0x180004270`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800042c1`
- `RPCRT4!NdrClientCall3` at `0x1800042c1`
- `RPCRT4!UuidEqual` at `0x18000429c`
- `RPCRT4!UuidEqual` at `0x18000429c`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall EapSystemBriDeleteEvent(UUID *a1, __int64 a2, int a3, __int64 a4)
{
  unsigned int v6; // edx
  MIDL_STUBLESS_PROXY_INFO *v7; // rcx
  RPC_STATUS Status[6]; // [rsp+30h] [rbp-18h] BYREF

  Status[0] = 0;
  if ( UuidEqual(a1, (UUID *)&g_SmsRouterBrokerId, Status) )
  {
    v6 = 1;
    v7 = (MIDL_STUBLESS_PROXY_INFO *)&stru_18000D0F0;
  }
  else
  {
    v6 = 2;
    v7 = (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo;
  }
  return NdrClientCall3(v7, v6, 0, a2, a3, a4);
}

```

## disassembly

```asm
0x180004270  mov     [rsp+arg_0], rbx
0x180004275  mov     [rsp+arg_8], rsi
0x18000427a  push    rdi
0x18000427b  sub     rsp, 40h
0x18000427f  mov     esi, r8d
0x180004282  mov     [rsp+48h+Status], 0
0x18000428a  mov     rbx, rdx
0x18000428d  lea     r8, [rsp+48h+Status]; Status
0x180004292  lea     rdx, g_SmsRouterBrokerId; Uuid2
0x180004299  mov     rdi, r9
0x18000429c  call    cs:__imp_UuidEqual
0x1800042a2  xor     r8d, r8d; pReturnValue
0x1800042a5  mov     [rsp+48h+var_20], rdi
0x1800042aa  mov     [rsp+48h+var_28], esi
0x1800042ae  mov     r9, rbx
0x1800042b1  test    eax, eax
0x1800042b3  jnz     short loc_1800042D7
0x1800042b5  mov     edx, 2; nProcNum
0x1800042ba  lea     rcx, pProxyInfo; pProxyInfo
0x1800042c1  call    cs:__imp_NdrClientCall3
0x1800042c7  mov     rbx, [rsp+48h+arg_0]
0x1800042cc  mov     rsi, [rsp+48h+arg_8]
0x1800042d1  add     rsp, 40h
0x1800042d5  pop     rdi
0x1800042d6  retn
0x1800042d7  mov     edx, 1
0x1800042dc  lea     rcx, stru_18000D0F0
0x1800042e3  jmp     short loc_1800042C1
```
