# McTemplateU0z_EventWriteTransfer

- ea: `0x180006544`
- end: `0x1800065bf`
- name: `McTemplateU0z_EventWriteTransfer`
- size: `123`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, const wchar_t *)`
- caller_count: `61`
- callee_count: `3`
- tags: ``

## callers

- `0x180005180`
- `0x180005c20`
- `0x180006190`
- `0x1800067e0`
- `0x180006940`
- `0x180006b10`
- `0x180006c60`
- `0x180007560`
- `0x180007780`
- `0x180007954`
- `0x180007b58`
- `0x180007f10`
- `0x180008138`
- `0x18000833c`
- `0x180008560`
- `0x180008774`
- `0x180008a4c`
- `0x180008be4`
- `0x18000ce40`
- `0x18000cfa0`
- `0x18000d720`
- `0x18000db90`
- `0x18000e250`
- `0x18000e5d0`
- `0x18000ebf0`
- `0x18000edc0`
- `0x18000f1b0`
- `0x18000f430`
- `0x18000f8d0`
- `0x18000fcf0`
- `0x18000fe20`
- `0x1800100f0`
- `0x180010270`
- `0x180010430`
- `0x180010600`
- `0x180010820`
- `0x1800109b0`
- `0x180010c70`
- `0x180010de0`
- `0x180012950`
- `0x180012c20`
- `0x1800136e0`
- `0x180013990`
- `0x180013c10`
- `0x180013dd0`
- `0x180014330`
- `0x180014520`
- `0x180014900`
- `0x180014aa0`
- `0x180014b80`

## callees

- `0x180004c2c`
- `0x180006544`
- `0x18001cc70`

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
0x180006544  sub     rsp, 68h
0x180006548  mov     rax, cs:__security_cookie
0x18000654f  xor     rax, rsp
0x180006552  mov     [rsp+68h+var_18], rax
0x180006557  xor     r9d, r9d
0x18000655a  test    r8, r8
0x18000655d  jz      short loc_180006576
0x18000655f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006563  inc     rax
0x180006566  cmp     [r8+rax*2], r9w
0x18000656b  jnz     short loc_180006563
0x18000656d  lea     eax, ds:2[rax*2]
0x180006574  jmp     short loc_18000657B
0x180006576  mov     eax, 0Ah
0x18000657b  test    r8, r8
0x18000657e  mov     [rsp+68h+var_20], eax
0x180006582  lea     rcx, aNull_0; "NULL"
0x180006589  mov     [rsp+68h+var_1C], r9d
0x18000658e  cmovz   r8, rcx
0x180006592  lea     rax, [rsp+68h+var_38]
0x180006597  mov     r9d, 2
0x18000659d  mov     [rsp+68h+var_28], r8
0x1800065a2  mov     [rsp+68h+var_48], rax
0x1800065a7  call    McGenEventWrite_EventWriteTransfer
0x1800065ac  mov     rcx, [rsp+68h+var_18]
0x1800065b1  xor     rcx, rsp; StackCookie
0x1800065b4  call    __security_check_cookie
0x1800065b9  add     rsp, 68h
0x1800065bd  retn
```
