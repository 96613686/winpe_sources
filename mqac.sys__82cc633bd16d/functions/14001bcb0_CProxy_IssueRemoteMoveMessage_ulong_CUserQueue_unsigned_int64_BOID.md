# CProxy::IssueRemoteMoveMessage(ulong,CUserQueue *,unsigned __int64,BOID *)

- ea: `0x14001bcb0`
- end: `0x14001bd44`
- name: `?IssueRemoteMoveMessage@CProxy@@QEBAJKPEAVCUserQueue@@_KPEAUBOID@@@Z`
- size: `148`
- prototype: `__int64 __fastcall(CProxy *__hidden this, unsigned int, struct CUserQueue *, unsigned __int64, struct BOID *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001be10`

## callees

- `0x14001b114`
- `0x14001bcb0`
- `0x140024bf0`

## pseudocode

```c
__int64 __fastcall CProxy::IssueRemoteMoveMessage(
        CProxy *this,
        int a2,
        struct CUserQueue *a3,
        __int64 a4,
        struct BOID *a5)
{
  __int64 v5; // rax
  __int64 v8; // rsi
  _BYTE v10[16]; // [rsp+20h] [rbp-F8h] BYREF
  int v11; // [rsp+30h] [rbp-E8h]
  __int64 v12; // [rsp+38h] [rbp-E0h]
  __int64 v13; // [rsp+40h] [rbp-D8h]
  int v14; // [rsp+48h] [rbp-D0h]
  __int64 v15; // [rsp+50h] [rbp-C8h]
  __int128 v16; // [rsp+58h] [rbp-C0h]

  v5 = *((_QWORD *)this + 8);
  v11 = 14;
  v8 = *(_QWORD *)(v5 + 64);
  v12 = *((_QWORD *)this + 19);
  v13 = (*(__int64 (__fastcall **)(struct CUserQueue *))(*(_QWORD *)a3 + 112LL))(a3);
  v14 = a2;
  v15 = a4;
  if ( a5 )
    v16 = *(_OWORD *)a5;
  else
    v16 = 0;
  return CQMInterface::ProcessRequest((CQMInterface *)(v8 + 72), (const struct CACRequest *)v10);
}

```

## disassembly

```asm
0x14001bcb0  mov     [rsp+arg_0], rbx
0x14001bcb5  mov     [rsp+arg_8], rsi
0x14001bcba  push    rdi
0x14001bcbb  sub     rsp, 110h
0x14001bcc2  mov     rax, [rcx+40h]
0x14001bcc6  mov     rdi, r9
0x14001bcc9  mov     ebx, edx
0x14001bccb  mov     [rsp+118h+var_E8], 0Eh
0x14001bcd3  mov     rsi, [rax+40h]
0x14001bcd7  mov     rax, [rcx+98h]
0x14001bcde  mov     rcx, r8
0x14001bce1  mov     [rsp+118h+var_E0], rax
0x14001bce6  mov     rax, [r8]
0x14001bce9  mov     rax, [rax+70h]
0x14001bced  call    _guard_dispatch_icall
0x14001bcf2  mov     [rsp+118h+var_D8], rax
0x14001bcf7  mov     rax, [rsp+118h+arg_20]
0x14001bcff  mov     [rsp+118h+var_D0], ebx
0x14001bd03  mov     [rsp+118h+var_C8], rdi
0x14001bd08  test    rax, rax
0x14001bd0b  jz      short loc_14001BD18
0x14001bd0d  movups  xmm0, xmmword ptr [rax]
0x14001bd10  movdqu  [rsp+118h+var_C0], xmm0
0x14001bd16  jmp     short loc_14001BD20
0x14001bd18  xorps   xmm0, xmm0
0x14001bd1b  movups  [rsp+118h+var_C0], xmm0
0x14001bd20  lea     rcx, [rsi+48h]; this
0x14001bd24  lea     rdx, [rsp+118h+var_F8]; struct CACRequest *
0x14001bd29  call    ?ProcessRequest@CQMInterface@@QEAAJAEBVCACRequest@@@Z; CQMInterface::ProcessRequest(CACRequest const &)
0x14001bd2e  lea     r11, [rsp+118h+var_8]
0x14001bd36  mov     rbx, [r11+10h]
0x14001bd3a  mov     rsi, [r11+18h]
0x14001bd3e  mov     rsp, r11
0x14001bd41  pop     rdi
0x14001bd42  retn
```
