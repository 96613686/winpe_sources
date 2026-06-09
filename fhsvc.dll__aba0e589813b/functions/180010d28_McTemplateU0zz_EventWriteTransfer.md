# McTemplateU0zz_EventWriteTransfer

- ea: `0x180010d28`
- end: `0x180010de0`
- name: `McTemplateU0zz_EventWriteTransfer`
- size: `184`
- prototype: `ULONG __fastcall(__int64, __int64, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180004e80`

## callees

- `0x18000b838`
- `0x180010d28`
- `0x180011980`

## pseudocode

```c
ULONG __fastcall McTemplateU0zz_EventWriteTransfer(__int64 a1, __int64 a2, const wchar_t *a3, const wchar_t *a4)
{
  __int64 v4; // rax
  int v5; // edx
  __int64 v6; // rcx
  int v7; // ecx
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
    v7 = 2 * v6 + 2;
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
           (REGHANDLE *)FH_SERVICE_PROVIDER_GUID_Context,
           (const EVENT_DESCRIPTOR *)CatalogLoadStart,
           (__int64)a3,
           3u,
           &v10);
}

```

## disassembly

```asm
0x180010d28  sub     rsp, 78h
0x180010d2c  mov     rax, cs:__security_cookie
0x180010d33  xor     rax, rsp
0x180010d36  mov     [rsp+78h+var_18], rax
0x180010d3b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010d3f  xor     r10d, r10d
0x180010d42  mov     edx, 0Ah
0x180010d47  test    r8, r8
0x180010d4a  jz      short loc_180010D62
0x180010d4c  mov     rcx, rax
0x180010d4f  inc     rcx
0x180010d52  cmp     [r8+rcx*2], r10w
0x180010d57  jnz     short loc_180010D4F
0x180010d59  lea     ecx, ds:2[rcx*2]
0x180010d60  jmp     short loc_180010D64
0x180010d62  mov     ecx, edx
0x180010d64  test    r8, r8
0x180010d67  mov     [rsp+78h+var_30], ecx
0x180010d6b  lea     r11, aNull_0; "NULL"
0x180010d72  mov     [rsp+78h+var_2C], r10d
0x180010d77  cmovz   r8, r11
0x180010d7b  mov     [rsp+78h+var_38], r8
0x180010d80  test    r9, r9
0x180010d83  jz      short loc_180010D99
0x180010d85  inc     rax
0x180010d88  cmp     [r9+rax*2], r10w
0x180010d8d  jnz     short loc_180010D85
0x180010d8f  lea     edx, ds:2[rax*2]
0x180010d96  test    r9, r9
0x180010d99  cmovz   r9, r11
0x180010d9d  mov     [rsp+78h+var_20], edx
0x180010da1  mov     [rsp+78h+var_28], r9
0x180010da6  lea     rax, [rsp+78h+var_48]
0x180010dab  mov     r9d, 3
0x180010db1  mov     [rsp+78h+var_1C], r10d
0x180010db6  lea     rdx, CatalogLoadStart
0x180010dbd  mov     [rsp+78h+var_58], rax
0x180010dc2  lea     rcx, FH_SERVICE_PROVIDER_GUID_Context
0x180010dc9  call    McGenEventWrite_EventWriteTransfer
0x180010dce  mov     rcx, [rsp+78h+var_18]
0x180010dd3  xor     rcx, rsp; StackCookie
0x180010dd6  call    __security_check_cookie
0x180010ddb  add     rsp, 78h
0x180010ddf  retn
```
