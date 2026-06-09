# McTemplateU0z_EventWriteTransfer

- ea: `0x180003110`
- end: `0x18000318a`
- name: `McTemplateU0z_EventWriteTransfer`
- size: `122`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `90`
- callee_count: `3`
- tags: ``

## callers

- `0x180001e00`
- `0x1800023a8`
- `0x180003308`
- `0x1800034d4`
- `0x180003660`
- `0x180003770`
- `0x18000419c`
- `0x180004388`
- `0x1800048e8`
- `0x180004eac`
- `0x1800051a0`
- `0x1800053c0`
- `0x1800054a8`
- `0x180005704`
- `0x180006118`
- `0x1800066d0`
- `0x180007060`
- `0x1800078e0`
- `0x180008320`
- `0x180008910`
- `0x1800089b0`
- `0x180009330`
- `0x180009400`
- `0x180009560`
- `0x1800096e8`
- `0x180009900`
- `0x180009c00`
- `0x180009eb0`
- `0x18000a0f0`
- `0x18000a310`
- `0x18000a3c0`
- `0x18000a4f0`
- `0x18000a610`
- `0x18000aed4`
- `0x18000b170`
- `0x18000b310`
- `0x18000b800`
- `0x18000b834`
- `0x18000ba40`
- `0x18000bc28`
- `0x18000be0c`
- `0x18000bfc0`
- `0x18000c4ac`
- `0x18000c854`
- `0x18000c9a0`
- `0x18000cb10`
- `0x18000d020`
- `0x18000d284`
- `0x18000d480`
- `0x18000d8e4`

## callees

- `0x180001460`
- `0x1800030b4`
- `0x180003110`

## pseudocode

```c
ULONG __fastcall McTemplateU0z_EventWriteTransfer(REGHANDLE *a1, const EVENT_DESCRIPTOR *a2, const wchar_t *a3)
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
  return McGenEventWrite_EventWriteTransfer(a1, a2, (__int64)a3, 2u, &v6);
}

```

## disassembly

```asm
0x180003110  sub     rsp, 68h
0x180003114  mov     rax, cs:__security_cookie
0x18000311b  xor     rax, rsp
0x18000311e  mov     [rsp+68h+var_18], rax
0x180003123  xor     r10d, r10d
0x180003126  test    r8, r8
0x180003129  jz      short loc_180003142
0x18000312b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000312f  inc     rax
0x180003132  cmp     [r8+rax*2], r10w
0x180003137  jnz     short loc_18000312F
0x180003139  lea     eax, ds:2[rax*2]
0x180003140  jmp     short loc_180003147
0x180003142  mov     eax, 0Ah
0x180003147  lea     r9, aNull; "NULL"
0x18000314e  mov     [rsp+68h+var_20], eax
0x180003152  test    r8, r8
0x180003155  mov     [rsp+68h+var_1C], r10d
0x18000315a  lea     rax, [rsp+68h+var_38]
0x18000315f  cmovz   r8, r9
0x180003163  mov     [rsp+68h+var_48], rax
0x180003168  mov     r9d, 2
0x18000316e  mov     [rsp+68h+var_28], r8
0x180003173  call    McGenEventWrite_EventWriteTransfer
0x180003178  mov     rcx, [rsp+68h+var_18]
0x18000317d  xor     rcx, rsp; StackCookie
0x180003180  call    __security_check_cookie
0x180003185  add     rsp, 68h
0x180003189  retn
```
