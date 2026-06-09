# McTemplateU0qzggd_EventWriteTransfer

- ea: `0x1400166a4`
- end: `0x140016772`
- name: `McTemplateU0qzggd_EventWriteTransfer`
- size: `206`
- prototype: `ULONG __fastcall(__int64, __int64, __int64, const wchar_t *, char, char, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14001097c`

## callees

- `0x1400029a0`
- `0x140016058`
- `0x1400166a4`

## pseudocode

```c
ULONG __fastcall McTemplateU0qzggd_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4,
        char a5,
        char a6,
        char a7)
{
  __int64 v7; // rax
  int v8; // eax
  int v10; // [rsp+30h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+40h] [rbp-31h] BYREF
  int *v12; // [rsp+50h] [rbp-21h]
  __int64 v13; // [rsp+58h] [rbp-19h]
  const wchar_t *v14; // [rsp+60h] [rbp-11h]
  int v15; // [rsp+68h] [rbp-9h]
  int v16; // [rsp+6Ch] [rbp-5h]
  char *v17; // [rsp+70h] [rbp-1h]
  __int64 v18; // [rsp+78h] [rbp+7h]
  char *v19; // [rsp+80h] [rbp+Fh]
  __int64 v20; // [rsp+88h] [rbp+17h]
  char *v21; // [rsp+90h] [rbp+1Fh]
  __int64 v22; // [rsp+98h] [rbp+27h]

  v10 = 2;
  v13 = 4;
  v12 = &v10;
  if ( a4 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a4[v7] );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v8 = 10;
  }
  v15 = v8;
  v16 = 0;
  v18 = 8;
  v17 = &a5;
  if ( !a4 )
    a4 = L"NULL";
  v20 = 8;
  v14 = a4;
  v19 = &a6;
  v22 = 4;
  v21 = &a7;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)L"NULL",
           (const EVENT_DESCRIPTOR *)CleanmgrPluginInstantiateStop,
           a3,
           6u,
           &v11);
}

```

## disassembly

```asm
0x1400166a4  push    rbp
0x1400166a6  lea     rbp, [rsp-3Fh]
0x1400166ab  sub     rsp, 0B0h
0x1400166b2  mov     rax, cs:__security_cookie
0x1400166b9  xor     rax, rsp
0x1400166bc  mov     [rbp+3Fh+var_10], rax
0x1400166c0  xor     edx, edx
0x1400166c2  mov     [rbp+3Fh+var_80], 2
0x1400166c9  mov     [rbp+3Fh+var_58], 4
0x1400166d1  lea     rax, [rbp+3Fh+var_80]
0x1400166d5  mov     [rbp+3Fh+var_60], rax
0x1400166d9  test    r9, r9
0x1400166dc  jz      short loc_1400166F5
0x1400166de  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400166e2  inc     rax
0x1400166e5  cmp     [r9+rax*2], dx
0x1400166ea  jnz     short loc_1400166E2
0x1400166ec  lea     eax, ds:2[rax*2]
0x1400166f3  jmp     short loc_1400166FA
0x1400166f5  mov     eax, 0Ah
0x1400166fa  mov     [rbp+3Fh+var_48], eax
0x1400166fd  lea     rcx, aNull_0; "NULL"
0x140016704  test    r9, r9
0x140016707  mov     [rbp+3Fh+var_44], edx
0x14001670a  lea     rax, [rbp+3Fh+arg_20]
0x14001670e  mov     [rbp+3Fh+var_38], 8
0x140016716  mov     [rbp+3Fh+var_40], rax
0x14001671a  lea     rdx, CleanmgrPluginInstantiateStop
0x140016721  cmovz   r9, rcx
0x140016725  mov     [rbp+3Fh+var_28], 8
0x14001672d  lea     rax, [rbp+3Fh+arg_28]
0x140016731  mov     [rbp+3Fh+var_50], r9
0x140016735  mov     [rbp+3Fh+var_30], rax
0x140016739  mov     r9d, 6
0x14001673f  lea     rax, [rbp+3Fh+arg_30]
0x140016743  mov     [rbp+3Fh+var_18], 4
0x14001674b  mov     [rbp+3Fh+var_20], rax
0x14001674f  lea     rax, [rbp+3Fh+var_70]
0x140016753  mov     [rsp+0B0h+var_90], rax
0x140016758  call    McGenEventWrite_EventWriteTransfer
0x14001675d  mov     rcx, [rbp+3Fh+var_10]
0x140016761  xor     rcx, rsp; StackCookie
0x140016764  call    __security_check_cookie
0x140016769  add     rsp, 0B0h
0x140016770  pop     rbp
0x140016771  retn
```
