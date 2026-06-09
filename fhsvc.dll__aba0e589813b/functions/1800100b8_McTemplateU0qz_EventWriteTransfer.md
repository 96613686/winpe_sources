# McTemplateU0qz_EventWriteTransfer

- ea: `0x1800100b8`
- end: `0x180010150`
- name: `McTemplateU0qz_EventWriteTransfer`
- size: `152`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, int, const wchar_t *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180006dd0`
- `0x18000c210`

## callees

- `0x18000b838`
- `0x1800100b8`
- `0x180011980`

## pseudocode

```c
ULONG __fastcall McTemplateU0qz_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, int a3, const wchar_t *a4)
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
  return McGenEventWrite_EventWriteTransfer((REGHANDLE *)FH_CORE_PROVIDER_GUID_Context, a2, 0, 3u, &v7);
}

```

## disassembly

```asm
0x1800100b8  mov     r11, rsp
0x1800100bb  mov     [r11+18h], r8d
0x1800100bf  sub     rsp, 78h
0x1800100c3  mov     rax, cs:__security_cookie
0x1800100ca  xor     rax, rsp
0x1800100cd  mov     [rsp+78h+var_18], rax
0x1800100d2  xor     r8d, r8d
0x1800100d5  mov     qword ptr [r11-30h], 4
0x1800100dd  lea     rax, [r11+18h]
0x1800100e1  mov     [r11-38h], rax
0x1800100e5  test    r9, r9
0x1800100e8  jz      short loc_180010101
0x1800100ea  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800100ee  inc     rax
0x1800100f1  cmp     [r9+rax*2], r8w
0x1800100f6  jnz     short loc_1800100EE
0x1800100f8  lea     eax, ds:2[rax*2]
0x1800100ff  jmp     short loc_180010106
0x180010101  mov     eax, 0Ah
0x180010106  test    r9, r9
0x180010109  mov     [rsp+78h+var_20], eax
0x18001010d  lea     rcx, aNull_0; "NULL"
0x180010114  mov     [rsp+78h+var_1C], r8d
0x180010119  cmovz   r9, rcx
0x18001011d  lea     rax, [rsp+78h+var_48]
0x180010122  mov     [rsp+78h+var_28], r9
0x180010127  lea     rcx, FH_CORE_PROVIDER_GUID_Context
0x18001012e  mov     r9d, 3
0x180010134  mov     [rsp+78h+var_58], rax
0x180010139  call    McGenEventWrite_EventWriteTransfer
0x18001013e  mov     rcx, [rsp+78h+var_18]
0x180010143  xor     rcx, rsp; StackCookie
0x180010146  call    __security_check_cookie
0x18001014b  add     rsp, 78h
0x18001014f  retn
```
