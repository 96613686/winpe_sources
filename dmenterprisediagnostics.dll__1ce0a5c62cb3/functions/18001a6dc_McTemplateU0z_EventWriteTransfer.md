# McTemplateU0z_EventWriteTransfer

- ea: `0x18001a6dc`
- end: `0x18001a756`
- name: `McTemplateU0z_EventWriteTransfer`
- size: `122`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001964c`
- `0x180019e30`

## callees

- `0x1800017e0`
- `0x18001a62c`
- `0x18001a6dc`

## pseudocode

```c
ULONG __fastcall McTemplateU0z_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, const wchar_t *a3)
{
  __int64 v3; // rax
  int v4; // eax
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-38h] BYREF
  const wchar_t *v7; // [rsp+40h] [rbp-28h]
  int v8; // [rsp+48h] [rbp-20h]
  int v9; // [rsp+4Ch] [rbp-1Ch]

  if ( a3 )
  {
    v3 = -1;
    do
      ++v3;
    while ( a3[v3] );
    v4 = 2 * v3 + 2;
  }
  else
  {
    v4 = 10;
  }
  v8 = v4;
  v9 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v7 = a3;
  return McGenEventWrite_EventWriteTransfer((__int64)L"NULL", a2, (__int64)a3, 2u, &v6);
}

```

## disassembly

```asm
0x18001a6dc  sub     rsp, 68h
0x18001a6e0  mov     rax, cs:__security_cookie
0x18001a6e7  xor     rax, rsp
0x18001a6ea  mov     [rsp+68h+var_18], rax
0x18001a6ef  xor     r9d, r9d
0x18001a6f2  test    r8, r8
0x18001a6f5  jz      short loc_18001A70E
0x18001a6f7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a6fb  inc     rax
0x18001a6fe  cmp     [r8+rax*2], r9w
0x18001a703  jnz     short loc_18001A6FB
0x18001a705  lea     eax, ds:2[rax*2]
0x18001a70c  jmp     short loc_18001A713
0x18001a70e  mov     eax, 0Ah
0x18001a713  test    r8, r8
0x18001a716  mov     [rsp+68h+var_20], eax
0x18001a71a  lea     rcx, aNull; "NULL"
0x18001a721  mov     [rsp+68h+var_1C], r9d
0x18001a726  cmovz   r8, rcx
0x18001a72a  lea     rax, [rsp+68h+var_38]
0x18001a72f  mov     r9d, 2
0x18001a735  mov     [rsp+68h+var_28], r8
0x18001a73a  mov     [rsp+68h+var_48], rax
0x18001a73f  call    McGenEventWrite_EventWriteTransfer
0x18001a744  mov     rcx, [rsp+68h+var_18]
0x18001a749  xor     rcx, rsp; StackCookie
0x18001a74c  call    __security_check_cookie
0x18001a751  add     rsp, 68h
0x18001a755  retn
```
