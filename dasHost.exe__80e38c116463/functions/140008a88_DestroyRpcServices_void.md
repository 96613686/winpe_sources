# DestroyRpcServices(void)

- ea: `0x140008a88`
- end: `0x140008b53`
- name: `?DestroyRpcServices@@YAJXZ`
- size: `203`
- prototype: `__int64 __fastcall(__int64, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x140010928`

## callees

- `0x140008a88`
- `0x140008eec`
- `0x140008f88`

## import_xrefs

- `RPCRT4!I_RpcMapWin32Status` at `0x140008aea`
- `RPCRT4!I_RpcMapWin32Status` at `0x140008aea`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x140008ade`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x140008ade`

## pseudocode

```c
__int64 __fastcall DestroyRpcServices(__int64 a1, int a2, int a3)
{
  int v3; // ebx
  RPC_STATUS v4; // eax
  int v6; // [rsp+28h] [rbp-20h]

  v3 = 0;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 5), a2, a3, 14, &WPP_e4f7ba077fe53c4e47029ecf7e1b99ca_Traceguids);
  if ( g_bDasHostCommandAndControlRegistered )
  {
    v4 = RpcServerUnregisterIfEx(qword_14001E9B0, 0, 1);
    if ( v4 )
      v3 = I_RpcMapWin32Status(v4);
    g_bDasHostCommandAndControlRegistered = 0;
  }
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      a2,
      a3,
      15,
      &WPP_e4f7ba077fe53c4e47029ecf7e1b99ca_Traceguids,
      v6,
      v3);
  if ( v3 > 0 )
    return (unsigned __int16)v3 | 0x80070000;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140008a88  mov     [rsp+arg_0], rbx
0x140008a8d  mov     [rsp+arg_8], rbp
0x140008a92  push    rdi
0x140008a93  sub     rsp, 40h
0x140008a97  xor     ebx, ebx
0x140008a99  lea     rdi, WPP_RECORDER_INITIALIZED
0x140008aa0  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140008aa7  lea     rbp, WPP_e4f7ba077fe53c4e47029ecf7e1b99ca_Traceguids
0x140008aae  jz      short loc_140008AC9
0x140008ab0  mov     rcx, cs:WPP_GLOBAL_Control
0x140008ab7  lea     r9d, [rbx+0Eh]; int
0x140008abb  mov     [rsp+48h+MessageGuid], rbp; MessageGuid
0x140008ac0  mov     rcx, [rcx+28h]; int
0x140008ac4  call    WPP_RECORDER_SF_s
0x140008ac9  cmp     cs:?g_bDasHostCommandAndControlRegistered@@3HA, ebx; int g_bDasHostCommandAndControlRegistered
0x140008acf  jz      short loc_140008AFC
0x140008ad1  xor     edx, edx; MgrTypeUuid
0x140008ad3  lea     rcx, qword_14001E9B0; IfSpec
0x140008ada  lea     r8d, [rdx+1]; RundownContextHandles
0x140008ade  call    cs:__imp_RpcServerUnregisterIfEx
0x140008ae4  test    eax, eax
0x140008ae6  jz      short loc_140008AF2
0x140008ae8  mov     ecx, eax; Status
0x140008aea  call    cs:__imp_I_RpcMapWin32Status
0x140008af0  mov     ebx, eax
0x140008af2  mov     cs:?g_bDasHostCommandAndControlRegistered@@3HA, 0; int g_bDasHostCommandAndControlRegistered
0x140008afc  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140008b03  jz      short loc_140008B34
0x140008b05  test    ebx, ebx
0x140008b07  jg      short loc_140008B0D
0x140008b09  mov     eax, ebx
0x140008b0b  jmp     short loc_140008B15
0x140008b0d  movzx   eax, bx
0x140008b10  or      eax, 80070000h
0x140008b15  mov     rcx, cs:WPP_GLOBAL_Control
0x140008b1c  mov     r9d, 0Fh; int
0x140008b22  mov     dword ptr [rsp+48h+var_18], eax; char
0x140008b26  mov     [rsp+48h+MessageGuid], rbp; MessageGuid
0x140008b2b  mov     rcx, [rcx+28h]; int
0x140008b2f  call    WPP_RECORDER_SF_sd
0x140008b34  test    ebx, ebx
0x140008b36  jle     short loc_140008B41
0x140008b38  movzx   ebx, bx
0x140008b3b  or      ebx, 80070000h
0x140008b41  mov     rbp, [rsp+48h+arg_8]
0x140008b46  mov     eax, ebx
0x140008b48  mov     rbx, [rsp+48h+arg_0]
0x140008b4d  add     rsp, 40h
0x140008b51  pop     rdi
0x140008b52  retn
```
