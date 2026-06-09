# McTemplateU0qz_EventWriteTransfer

- ea: `0x1800126a0`
- end: `0x180012737`
- name: `McTemplateU0qz_EventWriteTransfer`
- size: `151`
- prototype: `ULONG __fastcall(__int64, __int64, __int64, const wchar_t *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180001400`
- `0x180001ee0`
- `0x180011f80`

## callees

- `0x180004c2c`
- `0x1800126a0`
- `0x18001cc70`

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
  return McGenEventWrite_EventWriteTransfer((__int64)L"NULL", (const EVENT_DESCRIPTOR *)ProbeStart, a3, 3u, &v7);
}

```

## disassembly

```asm
0x1800126a0  mov     r11, rsp
0x1800126a3  mov     [r11+18h], r8d
0x1800126a7  sub     rsp, 78h
0x1800126ab  mov     rax, cs:__security_cookie
0x1800126b2  xor     rax, rsp
0x1800126b5  mov     [rsp+78h+var_18], rax
0x1800126ba  xor     edx, edx
0x1800126bc  mov     qword ptr [r11-30h], 4
0x1800126c4  lea     rax, [r11+18h]
0x1800126c8  mov     [r11-38h], rax
0x1800126cc  test    r9, r9
0x1800126cf  jz      short loc_1800126E8
0x1800126d1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800126d5  inc     rax
0x1800126d8  cmp     [r9+rax*2], dx
0x1800126dd  jnz     short loc_1800126D5
0x1800126df  lea     eax, ds:2[rax*2]
0x1800126e6  jmp     short loc_1800126ED
0x1800126e8  mov     eax, 0Ah
0x1800126ed  test    r9, r9
0x1800126f0  mov     [rsp+78h+var_20], eax
0x1800126f4  lea     rcx, aNull_0; "NULL"
0x1800126fb  mov     [rsp+78h+var_1C], edx
0x1800126ff  cmovz   r9, rcx
0x180012703  lea     rax, [rsp+78h+var_48]
0x180012708  mov     [rsp+78h+var_28], r9
0x18001270d  lea     rdx, ProbeStart
0x180012714  mov     r9d, 3
0x18001271a  mov     [rsp+78h+var_58], rax
0x18001271f  call    McGenEventWrite_EventWriteTransfer
0x180012724  mov     rcx, [rsp+78h+var_18]
0x180012729  xor     rcx, rsp; StackCookie
0x18001272c  call    __security_check_cookie
0x180012731  add     rsp, 78h
0x180012735  retn
```
