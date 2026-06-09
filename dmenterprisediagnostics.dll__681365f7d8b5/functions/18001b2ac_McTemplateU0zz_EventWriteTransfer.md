# McTemplateU0zz_EventWriteTransfer

- ea: `0x18001b2ac`
- end: `0x18001b35e`
- name: `McTemplateU0zz_EventWriteTransfer`
- size: `178`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180019bb0`

## callees

- `0x180001800`
- `0x18001b0cc`
- `0x18001b2ac`

## pseudocode

```c
ULONG __fastcall McTemplateU0zz_EventWriteTransfer(__int64 a1, __int64 a2, const wchar_t *a3, const wchar_t *a4)
{
  __int64 v4; // rax
  int v5; // edx
  __int64 v6; // rcx
  __int64 v7; // rcx
  bool v8; // zf
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+30h] [rbp-48h] BYREF
  const wchar_t *v11; // [rsp+40h] [rbp-38h]
  int v12; // [rsp+48h] [rbp-30h]
  int v13; // [rsp+4Ch] [rbp-2Ch]
  const wchar_t *v14; // [rsp+50h] [rbp-28h]
  int v15; // [rsp+58h] [rbp-20h]
  int v16; // [rsp+5Ch] [rbp-1Ch]

  v4 = -1;
  v5 = 10;
  if ( a3 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a3[v6] );
    v7 = (unsigned int)(2 * v6 + 2);
  }
  else
  {
    v7 = 10;
  }
  v12 = v7;
  v13 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v11 = a3;
  v8 = a4 == 0;
  if ( a4 )
  {
    do
      ++v4;
    while ( a4[v4] );
    v5 = 2 * v4 + 2;
    v8 = a4 == 0;
  }
  if ( v8 )
    a4 = L"NULL";
  v15 = v5;
  v14 = a4;
  v16 = 0;
  return McGenEventWrite_EventWriteTransfer(
           v7,
           (const EVENT_DESCRIPTOR *)TraceMerge_NGEN_CopyingPDB_Start,
           (__int64)a3,
           3u,
           &v10);
}

```

## disassembly

```asm
0x18001b2ac  sub     rsp, 78h
0x18001b2b0  mov     rax, cs:__security_cookie
0x18001b2b7  xor     rax, rsp
0x18001b2ba  mov     [rsp+78h+var_18], rax
0x18001b2bf  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b2c3  xor     r10d, r10d
0x18001b2c6  mov     edx, 0Ah
0x18001b2cb  test    r8, r8
0x18001b2ce  jz      short loc_18001B2E6
0x18001b2d0  mov     rcx, rax
0x18001b2d3  inc     rcx
0x18001b2d6  cmp     [r8+rcx*2], r10w
0x18001b2db  jnz     short loc_18001B2D3
0x18001b2dd  lea     ecx, ds:2[rcx*2]
0x18001b2e4  jmp     short loc_18001B2E8
0x18001b2e6  mov     ecx, edx
0x18001b2e8  test    r8, r8
0x18001b2eb  mov     [rsp+78h+var_30], ecx
0x18001b2ef  lea     r11, aNull; "NULL"
0x18001b2f6  mov     [rsp+78h+var_2C], r10d
0x18001b2fb  cmovz   r8, r11
0x18001b2ff  mov     [rsp+78h+var_38], r8
0x18001b304  test    r9, r9
0x18001b307  jz      short loc_18001B31D
0x18001b309  inc     rax
0x18001b30c  cmp     [r9+rax*2], r10w
0x18001b311  jnz     short loc_18001B309
0x18001b313  lea     edx, ds:2[rax*2]
0x18001b31a  test    r9, r9
0x18001b31d  cmovz   r9, r11
0x18001b321  mov     [rsp+78h+var_20], edx
0x18001b325  mov     [rsp+78h+var_28], r9
0x18001b32a  lea     rax, [rsp+78h+var_48]
0x18001b32f  mov     r9d, 3
0x18001b335  mov     [rsp+78h+var_1C], r10d
0x18001b33a  lea     rdx, TraceMerge_NGEN_CopyingPDB_Start
0x18001b341  mov     [rsp+78h+var_58], rax
0x18001b346  call    McGenEventWrite_EventWriteTransfer
0x18001b34b  mov     rcx, [rsp+78h+var_18]
0x18001b350  xor     rcx, rsp; StackCookie
0x18001b353  call    __security_check_cookie
0x18001b358  add     rsp, 78h
0x18001b35c  retn
```
