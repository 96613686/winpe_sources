# McTemplateU0z_EventWriteTransfer

- ea: `0x180003170`
- end: `0x1800031eb`
- name: `McTemplateU0z_EventWriteTransfer`
- size: `123`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `90`
- callee_count: `3`
- tags: ``

## callers

- `0x180001e0c`
- `0x1800023c0`
- `0x18000339c`
- `0x180003568`
- `0x1800036f8`
- `0x18000380c`
- `0x18000423c`
- `0x18000442c`
- `0x1800049e4`
- `0x180005054`
- `0x180005380`
- `0x1800055b0`
- `0x180005698`
- `0x180005908`
- `0x18000638c`
- `0x180006970`
- `0x180007310`
- `0x180007bd0`
- `0x180008630`
- `0x180008c70`
- `0x180008d10`
- `0x1800096b0`
- `0x1800097a0`
- `0x180009920`
- `0x180009aac`
- `0x180009cd0`
- `0x180009fd0`
- `0x18000a280`
- `0x18000a4c0`
- `0x18000a6e0`
- `0x18000a790`
- `0x18000a8c0`
- `0x18000a9f0`
- `0x18000b2e8`
- `0x18000b580`
- `0x18000b720`
- `0x18000bc20`
- `0x18000bc54`
- `0x18000be68`
- `0x18000c050`
- `0x18000c234`
- `0x18000c3e8`
- `0x18000c8d4`
- `0x18000cc7c`
- `0x18000cdc8`
- `0x18000cf3c`
- `0x18000d450`
- `0x18000d6b4`
- `0x18000d8b4`
- `0x18000dd20`

## callees

- `0x180001460`
- `0x18000310c`
- `0x180003170`

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
0x180003170  sub     rsp, 68h
0x180003174  mov     rax, cs:__security_cookie
0x18000317b  xor     rax, rsp
0x18000317e  mov     [rsp+68h+var_18], rax
0x180003183  xor     r10d, r10d
0x180003186  test    r8, r8
0x180003189  jz      short loc_1800031A2
0x18000318b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000318f  inc     rax
0x180003192  cmp     [r8+rax*2], r10w
0x180003197  jnz     short loc_18000318F
0x180003199  lea     eax, ds:2[rax*2]
0x1800031a0  jmp     short loc_1800031A7
0x1800031a2  mov     eax, 0Ah
0x1800031a7  lea     r9, aNull; "NULL"
0x1800031ae  mov     [rsp+68h+var_20], eax
0x1800031b2  test    r8, r8
0x1800031b5  mov     [rsp+68h+var_1C], r10d
0x1800031ba  lea     rax, [rsp+68h+var_38]
0x1800031bf  cmovz   r8, r9
0x1800031c3  mov     [rsp+68h+var_48], rax
0x1800031c8  mov     r9d, 2
0x1800031ce  mov     [rsp+68h+var_28], r8
0x1800031d3  call    McGenEventWrite_EventWriteTransfer
0x1800031d8  mov     rcx, [rsp+68h+var_18]
0x1800031dd  xor     rcx, rsp; StackCookie
0x1800031e0  call    __security_check_cookie
0x1800031e5  add     rsp, 68h
0x1800031e9  retn
```
