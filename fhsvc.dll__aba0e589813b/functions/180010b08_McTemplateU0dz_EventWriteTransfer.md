# McTemplateU0dz_EventWriteTransfer

- ea: `0x180010b08`
- end: `0x180010ba5`
- name: `McTemplateU0dz_EventWriteTransfer`
- size: `157`
- prototype: `ULONG __fastcall(__int64, __int64, __int64, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180004e80`

## callees

- `0x18000b838`
- `0x180010b08`
- `0x180011980`

## pseudocode

```c
ULONG __fastcall McTemplateU0dz_EventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, const wchar_t *a4)
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
  return McGenEventWrite_EventWriteTransfer(
           (REGHANDLE *)FH_SERVICE_PROVIDER_GUID_Context,
           (const EVENT_DESCRIPTOR *)ConfigurationLoadStop,
           a3,
           3u,
           &v7);
}

```

## disassembly

```asm
0x180010b08  mov     r11, rsp
0x180010b0b  mov     [r11+18h], r8d
0x180010b0f  sub     rsp, 78h
0x180010b13  mov     rax, cs:__security_cookie
0x180010b1a  xor     rax, rsp
0x180010b1d  mov     [rsp+78h+var_18], rax
0x180010b22  xor     edx, edx
0x180010b24  mov     qword ptr [r11-30h], 4
0x180010b2c  lea     rax, [r11+18h]
0x180010b30  mov     [r11-38h], rax
0x180010b34  test    r9, r9
0x180010b37  jz      short loc_180010B50
0x180010b39  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010b3d  inc     rax
0x180010b40  cmp     [r9+rax*2], dx
0x180010b45  jnz     short loc_180010B3D
0x180010b47  lea     eax, ds:2[rax*2]
0x180010b4e  jmp     short loc_180010B55
0x180010b50  mov     eax, 0Ah
0x180010b55  test    r9, r9
0x180010b58  mov     [rsp+78h+var_20], eax
0x180010b5c  lea     rcx, aNull_0; "NULL"
0x180010b63  mov     [rsp+78h+var_1C], edx
0x180010b67  cmovz   r9, rcx
0x180010b6b  lea     rax, [rsp+78h+var_48]
0x180010b70  mov     [rsp+78h+var_28], r9
0x180010b75  lea     rdx, ConfigurationLoadStop
0x180010b7c  mov     r9d, 3
0x180010b82  mov     [rsp+78h+var_58], rax
0x180010b87  lea     rcx, FH_SERVICE_PROVIDER_GUID_Context
0x180010b8e  call    McGenEventWrite_EventWriteTransfer
0x180010b93  mov     rcx, [rsp+78h+var_18]
0x180010b98  xor     rcx, rsp; StackCookie
0x180010b9b  call    __security_check_cookie
0x180010ba0  add     rsp, 78h
0x180010ba4  retn
```
