# McTemplateU0zq_EventWriteTransfer

- ea: `0x1800101e0`
- end: `0x180010281`
- name: `McTemplateU0zq_EventWriteTransfer`
- size: `161`
- prototype: `ULONG __fastcall(__int64, __int64, const wchar_t *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180003f00`
- `0x180007330`

## callees

- `0x18000b838`
- `0x1800101e0`
- `0x180011980`

## pseudocode

```c
ULONG __fastcall McTemplateU0zq_EventWriteTransfer(__int64 a1, __int64 a2, const wchar_t *a3, int a4)
{
  __int64 v4; // rax
  int v5; // eax
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-48h] BYREF
  const wchar_t *v8; // [rsp+40h] [rbp-38h]
  int v9; // [rsp+48h] [rbp-30h]
  int v10; // [rsp+4Ch] [rbp-2Ch]
  int *v11; // [rsp+50h] [rbp-28h]
  __int64 v12; // [rsp+58h] [rbp-20h]
  int v13; // [rsp+98h] [rbp+20h] BYREF

  v13 = a4;
  if ( a3 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a3[v4] );
    v5 = 2 * v4 + 2;
  }
  else
  {
    v5 = 10;
  }
  v9 = v5;
  v10 = 0;
  v11 = &v13;
  v12 = 4;
  if ( !a3 )
    a3 = L"NULL";
  v8 = a3;
  return McGenEventWrite_EventWriteTransfer(
           (REGHANDLE *)FH_SERVICE_PROVIDER_GUID_Context,
           (const EVENT_DESCRIPTOR *)BackupCycleStart,
           (__int64)a3,
           3u,
           &v7);
}

```

## disassembly

```asm
0x1800101e0  mov     [rsp+arg_18], r9d
0x1800101e5  sub     rsp, 78h
0x1800101e9  mov     rax, cs:__security_cookie
0x1800101f0  xor     rax, rsp
0x1800101f3  mov     [rsp+78h+var_18], rax
0x1800101f8  xor     edx, edx
0x1800101fa  test    r8, r8
0x1800101fd  jz      short loc_180010216
0x1800101ff  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010203  inc     rax
0x180010206  cmp     [r8+rax*2], dx
0x18001020b  jnz     short loc_180010203
0x18001020d  lea     eax, ds:2[rax*2]
0x180010214  jmp     short loc_18001021B
0x180010216  mov     eax, 0Ah
0x18001021b  mov     [rsp+78h+var_30], eax
0x18001021f  lea     rcx, aNull_0; "NULL"
0x180010226  lea     rax, [rsp+78h+arg_18]
0x18001022e  mov     [rsp+78h+var_2C], edx
0x180010232  test    r8, r8
0x180010235  mov     [rsp+78h+var_28], rax
0x18001023a  lea     rax, [rsp+78h+var_48]
0x18001023f  mov     [rsp+78h+var_20], 4
0x180010248  cmovz   r8, rcx
0x18001024c  mov     [rsp+78h+var_58], rax
0x180010251  mov     r9d, 3
0x180010257  mov     [rsp+78h+var_38], r8
0x18001025c  lea     rdx, BackupCycleStart
0x180010263  lea     rcx, FH_SERVICE_PROVIDER_GUID_Context
0x18001026a  call    McGenEventWrite_EventWriteTransfer
0x18001026f  mov     rcx, [rsp+78h+var_18]
0x180010274  xor     rcx, rsp; StackCookie
0x180010277  call    __security_check_cookie
0x18001027c  add     rsp, 78h
0x180010280  retn
```
