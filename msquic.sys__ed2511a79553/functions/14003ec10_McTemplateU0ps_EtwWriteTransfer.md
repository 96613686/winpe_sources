# McTemplateU0ps_EtwWriteTransfer

- ea: `0x14003ec10`
- end: `0x14003ec9c`
- name: `McTemplateU0ps_EtwWriteTransfer`
- size: `140`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `137`
- callee_count: `3`
- tags: ``

## callers

- `0x140001d6c`
- `0x1400033e0`
- `0x140003738`
- `0x140003fac`
- `0x140004460`
- `0x1400049b0`
- `0x1400051c0`
- `0x14000524c`
- `0x140005aa4`
- `0x1400078c8`
- `0x1400079e4`
- `0x140008944`
- `0x140009438`
- `0x140009534`
- `0x1400098e8`
- `0x1400099b4`
- `0x14000a120`
- `0x14000a2b0`
- `0x14000a6f0`
- `0x14000acfc`
- `0x14000b098`
- `0x14000b1f8`
- `0x14000b27c`
- `0x14000b32c`
- `0x14000b60c`
- `0x14000bad0`
- `0x14000bf30`
- `0x14000ca70`
- `0x14000d230`
- `0x14000d428`
- `0x14000d490`
- `0x14000db70`
- `0x14000edc0`
- `0x14000fdb0`
- `0x140010440`
- `0x1400108c0`
- `0x140012630`
- `0x140012c80`
- `0x140012f10`
- `0x140013200`
- `0x140013550`
- `0x140013b30`
- `0x140014630`
- `0x140015480`
- `0x140015b70`
- `0x140016210`
- `0x140016e30`
- `0x140017580`
- `0x1400183d0`
- `0x1400188f0`

## callees

- `0x14003c8e0`
- `0x14003e8c4`
- `0x14003ec10`

## pseudocode

```c
NTSTATUS __fastcall McTemplateU0ps_EtwWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, __int64 a3, const char *a4)
{
  __int64 v4; // rax
  int v5; // eax
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-48h] BYREF
  __int64 *v8; // [rsp+40h] [rbp-38h]
  __int64 v9; // [rsp+48h] [rbp-30h]
  const char *v10; // [rsp+50h] [rbp-28h]
  int v11; // [rsp+58h] [rbp-20h]
  int v12; // [rsp+5Ch] [rbp-1Ch]
  __int64 v13; // [rsp+90h] [rbp+18h] BYREF

  v13 = a3;
  v9 = 8;
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
  return McGenEventWrite_EtwWriteTransfer((__int64)"NULL", a2, 0, 3u, &v7);
}

```

## disassembly

```asm
0x14003ec10  mov     r11, rsp
0x14003ec13  mov     [r11+18h], r8
0x14003ec17  sub     rsp, 78h
0x14003ec1b  mov     rax, cs:__security_cookie
0x14003ec22  xor     rax, rsp
0x14003ec25  mov     [rsp+78h+var_18], rax
0x14003ec2a  xor     r8d, r8d
0x14003ec2d  mov     qword ptr [r11-30h], 8
0x14003ec35  lea     rax, [r11+18h]
0x14003ec39  mov     [r11-38h], rax
0x14003ec3d  test    r9, r9
0x14003ec40  jz      short loc_14003EC53
0x14003ec42  or      rax, 0FFFFFFFFFFFFFFFFh
0x14003ec46  inc     rax
0x14003ec49  cmp     [r9+rax], r8b
0x14003ec4d  jnz     short loc_14003EC46
0x14003ec4f  inc     eax
0x14003ec51  jmp     short loc_14003EC58
0x14003ec53  mov     eax, 5
0x14003ec58  test    r9, r9
0x14003ec5b  mov     [rsp+78h+var_20], eax
0x14003ec5f  lea     rcx, aNull; "NULL"
0x14003ec66  mov     [rsp+78h+var_1C], r8d
0x14003ec6b  cmovz   r9, rcx
0x14003ec6f  lea     rax, [rsp+78h+var_48]
0x14003ec74  mov     [rsp+78h+var_28], r9
0x14003ec79  mov     r9d, 3
0x14003ec7f  mov     [rsp+78h+var_58], rax
0x14003ec84  call    McGenEventWrite_EtwWriteTransfer
0x14003ec89  mov     rcx, [rsp+78h+var_18]
0x14003ec8e  xor     rcx, rsp; StackCookie
0x14003ec91  call    __security_check_cookie
0x14003ec96  add     rsp, 78h
0x14003ec9a  retn
```
