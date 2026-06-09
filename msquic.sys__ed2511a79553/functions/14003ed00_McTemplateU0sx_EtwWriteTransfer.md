# McTemplateU0sx_EtwWriteTransfer

- ea: `0x14003ed00`
- end: `0x14003ed95`
- name: `McTemplateU0sx_EtwWriteTransfer`
- size: `149`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `76`
- callee_count: `3`
- tags: ``

## callers

- `0x1400010b0`
- `0x1400013c4`
- `0x140001510`
- `0x140002840`
- `0x140002e8c`
- `0x1400033e0`
- `0x1400049b0`
- `0x14000524c`
- `0x140005aa4`
- `0x140007b30`
- `0x140008268`
- `0x140008468`
- `0x140008568`
- `0x140008bb0`
- `0x14000a250`
- `0x14000b850`
- `0x14000bad0`
- `0x14000bf30`
- `0x14000db70`
- `0x14000fbc0`
- `0x14000fdb0`
- `0x1400108c0`
- `0x140015b70`
- `0x140016e30`
- `0x14001a050`
- `0x14001c664`
- `0x14001f464`
- `0x1400211bc`
- `0x140021b60`
- `0x140022710`
- `0x140023f20`
- `0x140024810`
- `0x1400258c0`
- `0x14002636c`
- `0x140026600`
- `0x140026770`
- `0x14002697c`
- `0x140026f1c`
- `0x140027444`
- `0x140028728`
- `0x140029810`
- `0x140029a60`
- `0x140029bb0`
- `0x14002a180`
- `0x14002b730`
- `0x14002c014`
- `0x14002f3c4`
- `0x14002f644`
- `0x140030388`
- `0x14003383c`

## callees

- `0x14003c8e0`
- `0x14003e8c4`
- `0x14003ed00`

## pseudocode

```c
NTSTATUS McTemplateU0sx_EtwWriteTransfer(__int64 a1, __int64 a2, const char *a3, ...)
{
  __int64 v3; // rax
  int v4; // eax
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-48h] BYREF
  const char *v7; // [rsp+40h] [rbp-38h]
  int v8; // [rsp+48h] [rbp-30h]
  int v9; // [rsp+4Ch] [rbp-2Ch]
  va_list v10; // [rsp+50h] [rbp-28h]
  __int64 v11; // [rsp+58h] [rbp-20h]
  va_list va; // [rsp+98h] [rbp+20h] BYREF

  va_start(va, a3);
  if ( a3 )
  {
    v3 = -1;
    do
      ++v3;
    while ( a3[v3] );
    v4 = v3 + 1;
  }
  else
  {
    v4 = 5;
  }
  v8 = v4;
  v9 = 0;
  va_copy(v10, va);
  v11 = 8;
  if ( !a3 )
    a3 = "NULL";
  v7 = a3;
  return McGenEventWrite_EtwWriteTransfer(
           (__int64)"NULL",
           (const EVENT_DESCRIPTOR *)QuicAllocFailure,
           (__int64)a3,
           3u,
           &v6);
}

```

## disassembly

```asm
0x14003ed00  mov     [rsp+arg_18], r9
0x14003ed05  sub     rsp, 78h
0x14003ed09  mov     rax, cs:__security_cookie
0x14003ed10  xor     rax, rsp
0x14003ed13  mov     [rsp+78h+var_18], rax
0x14003ed18  xor     edx, edx
0x14003ed1a  test    r8, r8
0x14003ed1d  jz      short loc_14003ED30
0x14003ed1f  or      rax, 0FFFFFFFFFFFFFFFFh
0x14003ed23  inc     rax
0x14003ed26  cmp     [r8+rax], dl
0x14003ed2a  jnz     short loc_14003ED23
0x14003ed2c  inc     eax
0x14003ed2e  jmp     short loc_14003ED35
0x14003ed30  mov     eax, 5
0x14003ed35  mov     [rsp+78h+var_30], eax
0x14003ed39  lea     rcx, aNull; "NULL"
0x14003ed40  lea     rax, [rsp+78h+arg_18]
0x14003ed48  mov     [rsp+78h+var_2C], edx
0x14003ed4c  test    r8, r8
0x14003ed4f  mov     [rsp+78h+var_28], rax
0x14003ed54  lea     rax, [rsp+78h+var_48]
0x14003ed59  mov     [rsp+78h+var_20], 8
0x14003ed62  cmovz   r8, rcx
0x14003ed66  mov     [rsp+78h+var_58], rax
0x14003ed6b  mov     r9d, 3
0x14003ed71  mov     [rsp+78h+var_38], r8
0x14003ed76  lea     rdx, QuicAllocFailure
0x14003ed7d  call    McGenEventWrite_EtwWriteTransfer
0x14003ed82  mov     rcx, [rsp+78h+var_18]
0x14003ed87  xor     rcx, rsp; StackCookie
0x14003ed8a  call    __security_check_cookie
0x14003ed8f  add     rsp, 78h
0x14003ed93  retn
```
