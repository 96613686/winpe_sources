# QuicPacketValidateInitialToken

- ea: `0x14002a048`
- end: `0x14002a12a`
- name: `QuicPacketValidateInitialToken`
- size: `226`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140015b70`
- `0x140022e94`

## callees

- `0x140004840`
- `0x140026a88`
- `0x14002a048`
- `0x14003c8e0`
- `0x14003ce00`
- `0x1400424d4`

## string_xrefs

- `0x14002a07e`: `New Token not supported`
- `0x14002a09c`: `Invalid Token Length`
- `0x14002a0c8`: `Retry Token Decryption Failure`
- `0x14002a0de`: `Invalid Retry Token OrigConnId Length`
- `0x14002a0fd`: `Retry Token Addr Mismatch`

## pseudocode

```c
char __fastcall QuicPacketValidateInitialToken(__int64 a1, __int64 a2, __int16 a3, _BYTE *a4, _BYTE *a5)
{
  __int64 v6; // rbx
  __int64 v7; // rdi
  const char *v8; // r8
  char result; // al
  _BYTE v10[80]; // [rsp+20h] [rbp-78h] BYREF

  v6 = a2;
  v7 = a1;
  if ( (*a4 & 1) != 0 )
  {
    v8 = "New Token not supported";
LABEL_3:
    QuicPacketLogDrop(a1, a2, v8);
    result = 0;
    *a5 = 1;
    return result;
  }
  if ( a3 != 80 )
  {
    v8 = "Invalid Token Length";
    goto LABEL_3;
  }
  memset(v10, 0, sizeof(v10));
  if ( !(unsigned __int8)QuicRetryTokenDecrypt(v6, a4, v10) )
  {
    v8 = "Retry Token Decryption Failure";
LABEL_8:
    a2 = v6;
    a1 = v7;
    goto LABEL_3;
  }
  if ( v10[56] > 0x14u )
  {
    v8 = "Invalid Retry Token OrigConnId Length";
    goto LABEL_8;
  }
  if ( !(unsigned __int8)QuicAddrCompare(&v10[8], *(_QWORD *)(v6 + 8) + 8LL) )
  {
    v8 = "Retry Token Addr Mismatch";
    goto LABEL_8;
  }
  return 1;
}

```

## disassembly

```asm
0x14002a048  mov     [rsp+arg_10], rbx
0x14002a04d  push    rsi
0x14002a04e  push    rdi
0x14002a04f  push    r14
0x14002a051  sub     rsp, 80h
0x14002a058  mov     rax, cs:__security_cookie
0x14002a05f  xor     rax, rsp
0x14002a062  mov     [rsp+98h+var_28], rax
0x14002a067  test    byte ptr [r9], 1
0x14002a06b  mov     r14, r9
0x14002a06e  mov     rsi, [rsp+98h+arg_20]
0x14002a076  mov     rbx, rdx
0x14002a079  mov     rdi, rcx
0x14002a07c  jz      short loc_14002A091
0x14002a07e  lea     r8, aNewTokenNotSup; "New Token not supported"
0x14002a085  call    QuicPacketLogDrop
0x14002a08a  xor     al, al
0x14002a08c  mov     byte ptr [rsi], 1
0x14002a08f  jmp     short loc_14002A108
0x14002a091  mov     eax, 50h ; 'P'
0x14002a096  cmp     r8w, ax
0x14002a09a  jz      short loc_14002A0A5
0x14002a09c  lea     r8, aInvalidTokenLe; "Invalid Token Length"
0x14002a0a3  jmp     short loc_14002A085
0x14002a0a5  mov     r8, rax; Size
0x14002a0a8  lea     rcx, [rsp+98h+var_78]; void *
0x14002a0ad  xor     edx, edx; Val
0x14002a0af  call    memset
0x14002a0b4  lea     r8, [rsp+98h+var_78]
0x14002a0b9  mov     rdx, r14
0x14002a0bc  mov     rcx, rbx
0x14002a0bf  call    QuicRetryTokenDecrypt
0x14002a0c4  test    al, al
0x14002a0c6  jnz     short loc_14002A0D7
0x14002a0c8  lea     r8, aRetryTokenDecr; "Retry Token Decryption Failure"
0x14002a0cf  mov     rdx, rbx
0x14002a0d2  mov     rcx, rdi
0x14002a0d5  jmp     short loc_14002A085
0x14002a0d7  cmp     [rsp+98h+var_40], 14h
0x14002a0dc  jbe     short loc_14002A0E7
0x14002a0de  lea     r8, aInvalidRetryTo; "Invalid Retry Token OrigConnId Length"
0x14002a0e5  jmp     short loc_14002A0CF
0x14002a0e7  mov     rdx, [rbx+8]
0x14002a0eb  lea     rcx, [rsp+98h+var_70]
0x14002a0f0  add     rdx, 8
0x14002a0f4  call    QuicAddrCompare
0x14002a0f9  test    al, al
0x14002a0fb  jnz     short loc_14002A106
0x14002a0fd  lea     r8, aRetryTokenAddr; "Retry Token Addr Mismatch"
0x14002a104  jmp     short loc_14002A0CF
0x14002a106  mov     al, 1
0x14002a108  mov     rcx, [rsp+98h+var_28]
0x14002a10d  xor     rcx, rsp; StackCookie
0x14002a110  call    __security_check_cookie
0x14002a115  mov     rbx, [rsp+98h+arg_10]
0x14002a11d  add     rsp, 80h
0x14002a124  pop     r14
0x14002a126  pop     rdi
0x14002a127  pop     rsi
0x14002a128  retn
```
