# McTemplateU0z_EventWriteTransfer

- ea: `0x18000384c`
- end: `0x1800038cd`
- name: `McTemplateU0z_EventWriteTransfer`
- size: `129`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, const wchar_t *)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800015a0`
- `0x180001810`
- `0x180001e50`
- `0x180001ed0`
- `0x180002060`

## callees

- `0x1800037f8`
- `0x18000384c`
- `0x180009950`

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
  return McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWSPHONE_DATASHARING_Context, a2, (__int64)a3, 2u, &v6);
}

```

## disassembly

```asm
0x18000384c  sub     rsp, 68h
0x180003850  mov     rax, cs:__security_cookie
0x180003857  xor     rax, rsp
0x18000385a  mov     [rsp+68h+var_18], rax
0x18000385f  xor     r9d, r9d
0x180003862  test    r8, r8
0x180003865  jz      short loc_18000387E
0x180003867  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000386b  inc     rax
0x18000386e  cmp     [r8+rax*2], r9w
0x180003873  jnz     short loc_18000386B
0x180003875  lea     eax, ds:2[rax*2]
0x18000387c  jmp     short loc_180003883
0x18000387e  mov     eax, 0Ah
0x180003883  test    r8, r8
0x180003886  mov     [rsp+68h+var_20], eax
0x18000388a  lea     rcx, aNull; "NULL"
0x180003891  mov     [rsp+68h+var_1C], r9d
0x180003896  cmovz   r8, rcx
0x18000389a  lea     rax, [rsp+68h+var_38]
0x18000389f  lea     rcx, MICROSOFT_WINDOWSPHONE_DATASHARING_Context
0x1800038a6  mov     [rsp+68h+var_28], r8
0x1800038ab  mov     r9d, 2
0x1800038b1  mov     [rsp+68h+var_48], rax
0x1800038b6  call    McGenEventWrite_EventWriteTransfer
0x1800038bb  mov     rcx, [rsp+68h+var_18]
0x1800038c0  xor     rcx, rsp; StackCookie
0x1800038c3  call    __security_check_cookie
0x1800038c8  add     rsp, 68h
0x1800038cc  retn
```
