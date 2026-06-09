# McTemplateU0qs_EtwWriteTransfer

- ea: `0x14003e928`
- end: `0x14003e9b9`
- name: `McTemplateU0qs_EtwWriteTransfer`
- size: `145`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `26`
- callee_count: `3`
- tags: ``

## callers

- `0x140027f2c`
- `0x14002d33c`
- `0x14002db50`
- `0x14002de24`
- `0x14003383c`
- `0x140033a6c`
- `0x140033bfc`
- `0x140033e30`
- `0x1400340c8`
- `0x1400346f8`
- `0x140034788`
- `0x14003495c`
- `0x140034b30`
- `0x140034c90`
- `0x1400356ac`
- `0x140036138`
- `0x14003695c`
- `0x140036a90`
- `0x140036b90`
- `0x140036db8`
- `0x1400392d0`
- `0x140039e18`
- `0x14003aea0`
- `0x140063008`
- `0x14006503c`
- `0x14006514c`

## callees

- `0x14003c8e0`
- `0x14003e8c4`
- `0x14003e928`

## pseudocode

```c
NTSTATUS __fastcall McTemplateU0qs_EtwWriteTransfer(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  __int64 v4; // rax
  int v5; // eax
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-48h] BYREF
  int *v8; // [rsp+40h] [rbp-38h]
  __int64 v9; // [rsp+48h] [rbp-30h]
  const char *v10; // [rsp+50h] [rbp-28h]
  int v11; // [rsp+58h] [rbp-20h]
  int v12; // [rsp+5Ch] [rbp-1Ch]
  int v13; // [rsp+90h] [rbp+18h] BYREF

  v13 = a3;
  v9 = 4;
  v8 = &v13;
  if ( a4 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a4[v4] );
    v5 = v4 + 1;
  }
  else
  {
    v5 = 5;
  }
  v11 = v5;
  v12 = 0;
  if ( !a4 )
    a4 = "NULL";
  v10 = a4;
  return McGenEventWrite_EtwWriteTransfer(
           (__int64)"NULL",
           (const EVENT_DESCRIPTOR *)QuicLibraryErrorStatus,
           a3,
           3u,
           &v7);
}

```

## disassembly

```asm
0x14003e928  mov     r11, rsp
0x14003e92b  mov     [r11+18h], r8d
0x14003e92f  sub     rsp, 78h
0x14003e933  mov     rax, cs:__security_cookie
0x14003e93a  xor     rax, rsp
0x14003e93d  mov     [rsp+78h+var_18], rax
0x14003e942  xor     edx, edx
0x14003e944  mov     qword ptr [r11-30h], 4
0x14003e94c  lea     rax, [r11+18h]
0x14003e950  mov     [r11-38h], rax
0x14003e954  test    r9, r9
0x14003e957  jz      short loc_14003E96A
0x14003e959  or      rax, 0FFFFFFFFFFFFFFFFh
0x14003e95d  inc     rax
0x14003e960  cmp     [r9+rax], dl
0x14003e964  jnz     short loc_14003E95D
0x14003e966  inc     eax
0x14003e968  jmp     short loc_14003E96F
0x14003e96a  mov     eax, 5
0x14003e96f  test    r9, r9
0x14003e972  mov     [rsp+78h+var_20], eax
0x14003e976  lea     rcx, aNull; "NULL"
0x14003e97d  mov     [rsp+78h+var_1C], edx
0x14003e981  cmovz   r9, rcx
0x14003e985  lea     rax, [rsp+78h+var_48]
0x14003e98a  mov     [rsp+78h+var_28], r9
0x14003e98f  lea     rdx, QuicLibraryErrorStatus
0x14003e996  mov     r9d, 3
0x14003e99c  mov     [rsp+78h+var_58], rax
0x14003e9a1  call    McGenEventWrite_EtwWriteTransfer
0x14003e9a6  mov     rcx, [rsp+78h+var_18]
0x14003e9ab  xor     rcx, rsp; StackCookie
0x14003e9ae  call    __security_check_cookie
0x14003e9b3  add     rsp, 78h
0x14003e9b7  retn
```
