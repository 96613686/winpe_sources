# McTemplateU0qz_EventWriteTransfer

- ea: `0x1800093c8`
- end: `0x18000945e`
- name: `McTemplateU0qz_EventWriteTransfer`
- size: `150`
- prototype: `ULONG __fastcall(__int64, __int64, __int64, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007ba0`

## callees

- `0x180009370`
- `0x1800093c8`
- `0x180009a00`

## pseudocode

```c
ULONG __fastcall McTemplateU0qz_EventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, const wchar_t *a4)
{
  __int64 v4; // rax
  int v5; // eax
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-48h] BYREF
  int *v8; // [rsp+40h] [rbp-38h]
  __int64 v9; // [rsp+48h] [rbp-30h]
  const wchar_t *v10; // [rsp+50h] [rbp-28h]
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
    v5 = 2 * v4 + 2;
  }
  else
  {
    v5 = 10;
  }
  v11 = v5;
  v12 = 0;
  if ( !a4 )
    a4 = L"NULL";
  v10 = a4;
  return McGenEventWrite_EventWriteTransfer((__int64)L"NULL", (const EVENT_DESCRIPTOR *)FhStateChanged, a3, 3u, &v7);
}

```

## disassembly

```asm
0x1800093c8  mov     r11, rsp
0x1800093cb  mov     [r11+18h], r8d
0x1800093cf  sub     rsp, 78h
0x1800093d3  mov     rax, cs:__security_cookie
0x1800093da  xor     rax, rsp
0x1800093dd  mov     [rsp+78h+var_18], rax
0x1800093e2  xor     edx, edx
0x1800093e4  mov     qword ptr [r11-30h], 4
0x1800093ec  lea     rax, [r11+18h]
0x1800093f0  mov     [r11-38h], rax
0x1800093f4  test    r9, r9
0x1800093f7  jz      short loc_180009410
0x1800093f9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800093fd  inc     rax
0x180009400  cmp     [r9+rax*2], dx
0x180009405  jnz     short loc_1800093FD
0x180009407  lea     eax, ds:2[rax*2]
0x18000940e  jmp     short loc_180009415
0x180009410  mov     eax, 0Ah
0x180009415  test    r9, r9
0x180009418  mov     [rsp+78h+var_20], eax
0x18000941c  lea     rcx, aNull; "NULL"
0x180009423  mov     [rsp+78h+var_1C], edx
0x180009427  cmovz   r9, rcx
0x18000942b  lea     rax, [rsp+78h+var_48]
0x180009430  mov     [rsp+78h+var_28], r9
0x180009435  lea     rdx, FhStateChanged
0x18000943c  mov     r9d, 3
0x180009442  mov     [rsp+78h+var_58], rax
0x180009447  call    McGenEventWrite_EventWriteTransfer
0x18000944c  mov     rcx, [rsp+78h+var_18]
0x180009451  xor     rcx, rsp; StackCookie
0x180009454  call    __security_check_cookie
0x180009459  add     rsp, 78h
0x18000945d  retn
```
