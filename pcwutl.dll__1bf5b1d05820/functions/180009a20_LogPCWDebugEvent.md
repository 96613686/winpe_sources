# LogPCWDebugEvent

- ea: `0x180009a20`
- end: `0x180009ae1`
- name: `LogPCWDebugEvent`
- size: `193`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180009a20`
- `0x18000e240`
- `0x1800191f0`

## import_xrefs

- `ntdll!EtwEventWriteNoRegistration` at `0x180009ac2`
- `ntdll!EtwEventWriteNoRegistration` at `0x180009ac2`

## pseudocode

```c
__int64 __fastcall LogPCWDebugEvent(__int64 a1, __int64 a2)
{
  __int64 v3; // rax
  int v4; // eax
  __int64 v6; // [rsp+30h] [rbp-A8h] BYREF
  int v7; // [rsp+38h] [rbp-A0h]
  int v8; // [rsp+3Ch] [rbp-9Ch]
  __int64 *v9; // [rsp+40h] [rbp-98h]
  __int64 v10; // [rsp+48h] [rbp-90h]
  __int64 v11; // [rsp+E8h] [rbp+10h] BYREF

  v11 = a2;
  AslLogCallPrintf(3, "LogPCWDebugEvent", 1104, "DebugString: %ws", a1);
  if ( a1 )
  {
    v3 = -1;
    do
      ++v3;
    while ( *(_WORD *)(a1 + 2 * v3) );
    v4 = 2 * v3 + 2;
  }
  else
  {
    v4 = 0;
  }
  v7 = v4;
  v8 = 0;
  v9 = &v11;
  v6 = a1;
  v10 = 8;
  return EtwEventWriteNoRegistration(AE_LOG, AE_PCW_DEBUG_INFO_EVENT, 2, &v6);
}

```

## disassembly

```asm
0x180009a20  mov     [rsp+arg_8], rdx
0x180009a25  push    rbx
0x180009a26  sub     rsp, 0D0h
0x180009a2d  mov     rax, cs:__security_cookie
0x180009a34  xor     rax, rsp
0x180009a37  mov     [rsp+0D8h+var_18], rax
0x180009a3f  mov     rbx, rcx
0x180009a42  mov     [rsp+0D8h+var_B8], rcx
0x180009a47  mov     ecx, 3
0x180009a4c  lea     r9, aDebugstringWs; "DebugString: %ws"
0x180009a53  mov     r8d, 450h
0x180009a59  lea     rdx, aLogpcwdebugeve_0; "LogPCWDebugEvent"
0x180009a60  call    AslLogCallPrintf
0x180009a65  xor     ecx, ecx
0x180009a67  test    rbx, rbx
0x180009a6a  jz      short loc_180009A83
0x180009a6c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009a70  inc     rax
0x180009a73  cmp     [rbx+rax*2], cx
0x180009a77  jnz     short loc_180009A70
0x180009a79  lea     rax, ds:2[rax*2]
0x180009a81  jmp     short loc_180009A86
0x180009a83  mov     rax, rcx
0x180009a86  mov     [rsp+0D8h+var_A0], eax
0x180009a8a  lea     r9, [rsp+0D8h+var_A8]
0x180009a8f  lea     rax, [rsp+0D8h+arg_8]
0x180009a97  mov     [rsp+0D8h+var_9C], ecx
0x180009a9b  mov     r8d, 2
0x180009aa1  mov     [rsp+0D8h+var_98], rax
0x180009aa6  lea     rdx, AE_PCW_DEBUG_INFO_EVENT
0x180009aad  mov     [rsp+0D8h+var_A8], rbx
0x180009ab2  lea     rcx, AE_LOG
0x180009ab9  mov     [rsp+0D8h+var_90], 8
0x180009ac2  call    cs:__imp_EtwEventWriteNoRegistration
0x180009ac8  mov     rcx, [rsp+0D8h+var_18]
0x180009ad0  xor     rcx, rsp; StackCookie
0x180009ad3  call    __security_check_cookie
0x180009ad8  add     rsp, 0D0h
0x180009adf  pop     rbx
0x180009ae0  retn
```
