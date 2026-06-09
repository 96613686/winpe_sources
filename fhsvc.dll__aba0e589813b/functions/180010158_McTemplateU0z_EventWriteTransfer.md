# McTemplateU0z_EventWriteTransfer

- ea: `0x180010158`
- end: `0x1800101d9`
- name: `McTemplateU0z_EventWriteTransfer`
- size: `129`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, const wchar_t *)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180003f00`
- `0x180004e80`
- `0x180007330`

## callees

- `0x18000b838`
- `0x180010158`
- `0x180011980`

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
  return McGenEventWrite_EventWriteTransfer((REGHANDLE *)FH_SERVICE_PROVIDER_GUID_Context, a2, (__int64)a3, 2u, &v6);
}

```

## disassembly

```asm
0x180010158  sub     rsp, 68h
0x18001015c  mov     rax, cs:__security_cookie
0x180010163  xor     rax, rsp
0x180010166  mov     [rsp+68h+var_18], rax
0x18001016b  xor     r9d, r9d
0x18001016e  test    r8, r8
0x180010171  jz      short loc_18001018A
0x180010173  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010177  inc     rax
0x18001017a  cmp     [r8+rax*2], r9w
0x18001017f  jnz     short loc_180010177
0x180010181  lea     eax, ds:2[rax*2]
0x180010188  jmp     short loc_18001018F
0x18001018a  mov     eax, 0Ah
0x18001018f  test    r8, r8
0x180010192  mov     [rsp+68h+var_20], eax
0x180010196  lea     rcx, aNull_0; "NULL"
0x18001019d  mov     [rsp+68h+var_1C], r9d
0x1800101a2  cmovz   r8, rcx
0x1800101a6  lea     rax, [rsp+68h+var_38]
0x1800101ab  lea     rcx, FH_SERVICE_PROVIDER_GUID_Context
0x1800101b2  mov     [rsp+68h+var_28], r8
0x1800101b7  mov     r9d, 2
0x1800101bd  mov     [rsp+68h+var_48], rax
0x1800101c2  call    McGenEventWrite_EventWriteTransfer
0x1800101c7  mov     rcx, [rsp+68h+var_18]
0x1800101cc  xor     rcx, rsp; StackCookie
0x1800101cf  call    __security_check_cookie
0x1800101d4  add     rsp, 68h
0x1800101d8  retn
```
