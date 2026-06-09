# SmSessionComplete

- ea: `0x180003ea0`
- end: `0x180003f15`
- name: `SmSessionComplete`
- size: `117`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003de0`

## callees

- `0x18000ab61`
- `0x18000ab80`

## import_xrefs

- `ntdll!RtlSendMsgToSm` at `0x180003eef`
- `ntdll!RtlSendMsgToSm` at `0x180003eef`

## pseudocode

```c
__int64 __fastcall SmSessionComplete(__int64 a1, int a2)
{
  _BYTE v4[40]; // [rsp+20h] [rbp-168h] BYREF
  int v5; // [rsp+48h] [rbp-140h]
  int v6; // [rsp+50h] [rbp-138h]
  int v7; // [rsp+54h] [rbp-134h]

  memset_0(v4, 0, 0x148u);
  v6 = a2;
  v7 = 0;
  v5 = 1;
  return RtlSendMsgToSm(CsrSmApiPort, v4);
}

```

## disassembly

```asm
0x180003ea0  push    rbx
0x180003ea2  sub     rsp, 180h
0x180003ea9  mov     rax, cs:__security_cookie
0x180003eb0  xor     rax, rsp
0x180003eb3  mov     [rsp+188h+var_18], rax
0x180003ebb  mov     ebx, edx
0x180003ebd  lea     rcx, [rsp+188h+var_168]; void *
0x180003ec2  xor     edx, edx; Val
0x180003ec4  mov     r8d, 148h; Size
0x180003eca  call    memset_0
0x180003ecf  mov     rcx, cs:CsrSmApiPort
0x180003ed6  lea     rdx, [rsp+188h+var_168]
0x180003edb  mov     [rsp+188h+var_138], ebx
0x180003edf  mov     [rsp+188h+var_134], 0
0x180003ee7  mov     [rsp+188h+var_140], 1
0x180003eef  call    cs:__imp_RtlSendMsgToSm
0x180003ef6  nop     dword ptr [rax+rax+00h]
0x180003efb  mov     rcx, [rsp+188h+var_18]
0x180003f03  xor     rcx, rsp; StackCookie
0x180003f06  call    __security_check_cookie
0x180003f0b  add     rsp, 180h
0x180003f12  pop     rbx
0x180003f13  retn
```
