# DpspGetSystemSessionHost

- ea: `0x180006d08`
- end: `0x180006e03`
- name: `DpspGetSystemSessionHost`
- size: `251`
- prototype: `signed __int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x18000ed8c`

## callees

- `0x180006c5c`
- `0x180006d08`
- `0x180009090`
- `0x18000f534`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006db1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006df1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006db1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006df1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006d71`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006d71`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180006d15`
- `KERNELBASE!WTSGetServiceSessionId` at `0x180006d15`

## pseudocode

```c
signed __int64 __fastcall DpspGetSystemSessionHost(unsigned int a1)
{
  signed __int64 v2; // rbx
  int v3; // ebp
  PSID v4; // rsi
  int v5; // eax
  char Args; // bl
  signed __int64 SessionHostFromSid; // [rsp+68h] [rbp+10h] BYREF

  v2 = 0;
  v3 = WTSGetServiceSessionId();
  if ( a1 < 2 )
  {
    v4 = g_pLocalServSid;
LABEL_6:
    EnterCriticalSection(&g_csHostList);
    SessionHostFromSid = DpspGetSessionHostFromSid(v4, v3, a1);
    v2 = SessionHostFromSid;
    if ( !SessionHostFromSid )
    {
      v5 = DpspCreateSpecificSessionHost(&SessionHostFromSid, v4, v3, a1);
      Args = v5;
      if ( v5 < 0 )
      {
        LeaveCriticalSection(&g_csHostList);
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
          (int)L"DpspGetSystemSessionHost",
          439,
          (int)L"Error = %d",
          Args);
        return SessionHostFromSid;
      }
      v2 = SessionHostFromSid;
    }
    LeaveCriticalSection(&g_csHostList);
    return v2;
  }
  if ( a1 == 2 )
  {
    v4 = g_pLocalSysSid;
    goto LABEL_6;
  }
  WdipTraceError(
    (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
    (int)L"DpspGetSystemSessionHost",
    422,
    (int)L"Error = %d",
    5);
  return v2;
}

```

## disassembly

```asm
0x180006d08  push    rbx
0x180006d0a  push    rbp
0x180006d0b  push    rsi
0x180006d0c  push    rdi
0x180006d0d  sub     rsp, 38h
0x180006d11  mov     edi, ecx
0x180006d13  xor     ebx, ebx
0x180006d15  call    cs:__imp_WTSGetServiceSessionId
0x180006d1b  mov     edx, edi
0x180006d1d  mov     ebp, eax
0x180006d1f  test    edi, edi
0x180006d21  jz      short loc_180006D63
0x180006d23  sub     edx, 1
0x180006d26  jz      short loc_180006D63
0x180006d28  cmp     edx, 1
0x180006d2b  jz      short loc_180006D5A
0x180006d2d  lea     r9, aErrorD; "Error = %d"
0x180006d34  mov     dword ptr [rsp+58h+Args], 4005h; Args
0x180006d3c  mov     r8d, 1A6h; int
0x180006d42  lea     rdx, aDpspgetsystems; "DpspGetSystemSessionHost"
0x180006d49  lea     rcx, aClientcoreBase_11; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180006d50  call    WdipTraceError
0x180006d55  jmp     loc_180006DF7
0x180006d5a  mov     rsi, cs:g_pLocalSysSid
0x180006d61  jmp     short loc_180006D6A
0x180006d63  mov     rsi, cs:g_pLocalServSid
0x180006d6a  lea     rcx, g_csHostList; lpCriticalSection
0x180006d71  call    cs:__imp_EnterCriticalSection
0x180006d77  mov     r8d, edi
0x180006d7a  mov     edx, ebp
0x180006d7c  mov     rcx, rsi; pSid1
0x180006d7f  call    DpspGetSessionHostFromSid
0x180006d84  mov     [rsp+58h+arg_8], rax
0x180006d89  mov     rbx, rax
0x180006d8c  test    rax, rax
0x180006d8f  jnz     short loc_180006DEA
0x180006d91  mov     r9d, edi
0x180006d94  lea     rcx, [rsp+58h+arg_8]
0x180006d99  mov     r8d, ebp
0x180006d9c  mov     rdx, rsi
0x180006d9f  call    DpspCreateSpecificSessionHost
0x180006da4  mov     ebx, eax
0x180006da6  test    eax, eax
0x180006da8  jns     short loc_180006DE5
0x180006daa  lea     rcx, g_csHostList; lpCriticalSection
0x180006db1  call    cs:__imp_LeaveCriticalSection
0x180006db7  movzx   eax, bx
0x180006dba  lea     r9, aErrorD; "Error = %d"
0x180006dc1  mov     r8d, 1B7h; int
0x180006dc7  mov     dword ptr [rsp+58h+Args], eax; Args
0x180006dcb  lea     rdx, aDpspgetsystems; "DpspGetSystemSessionHost"
0x180006dd2  lea     rcx, aClientcoreBase_11; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180006dd9  call    WdipTraceError
0x180006dde  mov     rbx, [rsp+58h+arg_8]
0x180006de3  jmp     short loc_180006DF7
0x180006de5  mov     rbx, [rsp+58h+arg_8]
0x180006dea  lea     rcx, g_csHostList; lpCriticalSection
0x180006df1  call    cs:__imp_LeaveCriticalSection
0x180006df7  mov     rax, rbx
0x180006dfa  add     rsp, 38h
0x180006dfe  pop     rdi
0x180006dff  pop     rsi
0x180006e00  pop     rbp
0x180006e01  pop     rbx
0x180006e02  retn
```
