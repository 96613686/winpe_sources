# McTemplateU0qqqq_EventWriteTransfer

- ea: `0x180018ab0`
- end: `0x180018b51`
- name: `McTemplateU0qqqq_EventWriteTransfer`
- size: `161`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, __int64, int, char)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180018588`
- `0x180018670`

## callees

- `0x180004c2c`
- `0x18001cc70`

## pseudocode

```c
ULONG __fastcall McTemplateU0qqqq_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        char a6)
{
  unsigned int v7; // [rsp+30h] [rbp-39h] BYREF
  unsigned int v8; // [rsp+38h] [rbp-31h] BYREF
  unsigned int v9; // [rsp+40h] [rbp-29h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+50h] [rbp-19h] BYREF
  unsigned int *v11; // [rsp+60h] [rbp-9h]
  __int64 v12; // [rsp+68h] [rbp-1h]
  unsigned int *v13; // [rsp+70h] [rbp+7h]
  __int64 v14; // [rsp+78h] [rbp+Fh]
  unsigned int *v15; // [rsp+80h] [rbp+17h]
  __int64 v16; // [rsp+88h] [rbp+1Fh]
  char *v17; // [rsp+90h] [rbp+27h]
  __int64 v18; // [rsp+98h] [rbp+2Fh]

  v9 = gNcaEtwPerfTrackDeploymentID;
  v8 = gNcaEtwPerfTrackSessionID;
  v7 = gNcaEtwPerfTrackMachineID;
  v11 = &v7;
  v13 = &v8;
  v15 = &v9;
  v17 = &a6;
  v12 = 4;
  v14 = 4;
  v16 = 4;
  v18 = 4;
  return McGenEventWrite_EventWriteTransfer(a1, a2, a3, 5u, &v10);
}

```

## disassembly

```asm
0x180018ab0  push    rbp
0x180018ab2  lea     rbp, [rsp-47h]
0x180018ab7  sub     rsp, 0B0h
0x180018abe  mov     rax, cs:__security_cookie
0x180018ac5  xor     rax, rsp
0x180018ac8  mov     [rbp+47h+var_10], rax
0x180018acc  mov     eax, cs:?gNcaEtwPerfTrackDeploymentID@@3KA; ulong gNcaEtwPerfTrackDeploymentID
0x180018ad2  mov     r9d, 5
0x180018ad8  mov     [rbp+47h+var_70], eax
0x180018adb  mov     eax, cs:?gNcaEtwPerfTrackSessionID@@3KA; ulong gNcaEtwPerfTrackSessionID
0x180018ae1  mov     [rbp+47h+var_78], eax
0x180018ae4  mov     eax, cs:?gNcaEtwPerfTrackMachineID@@3KA; ulong gNcaEtwPerfTrackMachineID
0x180018aea  mov     [rbp+47h+var_80], eax
0x180018aed  lea     rax, [rbp+47h+var_80]
0x180018af1  mov     [rbp+47h+var_50], rax
0x180018af5  lea     rax, [rbp+47h+var_78]
0x180018af9  mov     [rbp+47h+var_40], rax
0x180018afd  lea     rax, [rbp+47h+var_70]
0x180018b01  mov     [rbp+47h+var_30], rax
0x180018b05  lea     rax, [rbp+47h+arg_28]
0x180018b09  mov     [rbp+47h+var_20], rax
0x180018b0d  lea     rax, [rbp+47h+var_60]
0x180018b11  mov     [rsp+0B0h+var_90], rax
0x180018b16  mov     [rbp+47h+var_48], 4
0x180018b1e  mov     [rbp+47h+var_38], 4
0x180018b26  mov     [rbp+47h+var_28], 4
0x180018b2e  mov     [rbp+47h+var_18], 4
0x180018b36  call    McGenEventWrite_EventWriteTransfer
0x180018b3b  mov     rcx, [rbp+47h+var_10]
0x180018b3f  xor     rcx, rsp; StackCookie
0x180018b42  call    __security_check_cookie
0x180018b47  add     rsp, 0B0h
0x180018b4e  pop     rbp
0x180018b4f  retn
```
