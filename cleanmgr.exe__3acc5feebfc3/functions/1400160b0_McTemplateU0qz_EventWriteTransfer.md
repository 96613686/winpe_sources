# McTemplateU0qz_EventWriteTransfer

- ea: `0x1400160b0`
- end: `0x140016145`
- name: `McTemplateU0qz_EventWriteTransfer`
- size: `149`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, const wchar_t *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000f154`
- `0x14000f1b4`

## callees

- `0x1400029a0`
- `0x140016058`
- `0x1400160b0`

## pseudocode

```c
ULONG __fastcall McTemplateU0qz_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        const wchar_t *a4)
{
  __int64 v4; // rax
  int v5; // eax
  int v7; // [rsp+30h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+38h] [rbp-40h] BYREF
  int *v9; // [rsp+48h] [rbp-30h]
  __int64 v10; // [rsp+50h] [rbp-28h]
  const wchar_t *v11; // [rsp+58h] [rbp-20h]
  int v12; // [rsp+60h] [rbp-18h]
  int v13; // [rsp+64h] [rbp-14h]

  v7 = 2;
  v10 = 4;
  v9 = &v7;
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
  v12 = v5;
  v13 = 0;
  if ( !a4 )
    a4 = L"NULL";
  v11 = a4;
  return McGenEventWrite_EventWriteTransfer((__int64)L"NULL", a2, 0, 3u, &v8);
}

```

## disassembly

```asm
0x1400160b0  sub     rsp, 78h
0x1400160b4  mov     rax, cs:__security_cookie
0x1400160bb  xor     rax, rsp
0x1400160be  mov     [rsp+78h+var_10], rax
0x1400160c3  xor     r8d, r8d
0x1400160c6  mov     [rsp+78h+var_48], 2
0x1400160ce  mov     [rsp+78h+var_28], 4
0x1400160d7  lea     rax, [rsp+78h+var_48]
0x1400160dc  mov     [rsp+78h+var_30], rax
0x1400160e1  test    r9, r9
0x1400160e4  jz      short loc_1400160FD
0x1400160e6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400160ea  inc     rax
0x1400160ed  cmp     [r9+rax*2], r8w
0x1400160f2  jnz     short loc_1400160EA
0x1400160f4  lea     eax, ds:2[rax*2]
0x1400160fb  jmp     short loc_140016102
0x1400160fd  mov     eax, 0Ah
0x140016102  test    r9, r9
0x140016105  mov     [rsp+78h+var_18], eax
0x140016109  lea     rcx, aNull_0; "NULL"
0x140016110  mov     [rsp+78h+var_14], r8d
0x140016115  cmovz   r9, rcx
0x140016119  lea     rax, [rsp+78h+var_40]
0x14001611e  mov     [rsp+78h+var_20], r9
0x140016123  mov     r9d, 3
0x140016129  mov     [rsp+78h+var_58], rax
0x14001612e  call    McGenEventWrite_EventWriteTransfer
0x140016133  mov     rcx, [rsp+78h+var_10]
0x140016138  xor     rcx, rsp; StackCookie
0x14001613b  call    __security_check_cookie
0x140016140  add     rsp, 78h
0x140016144  retn
```
