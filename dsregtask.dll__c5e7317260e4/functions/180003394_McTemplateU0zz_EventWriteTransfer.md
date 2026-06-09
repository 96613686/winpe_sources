# McTemplateU0zz_EventWriteTransfer

- ea: `0x180003394`
- end: `0x18000344c`
- name: `McTemplateU0zz_EventWriteTransfer`
- size: `184`
- prototype: `ULONG __fastcall(__int64, __int64, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800030ec`

## callees

- `0x180001460`
- `0x1800032c0`
- `0x180003394`

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
           &UserDeviceRegistrationEventProvider_Context,
           (const EVENT_DESCRIPTOR *)NullOrEmptyParameterFailureEvent,
           (__int64)a3,
           3u,
           &v10);
}

```

## disassembly

```asm
0x180003394  sub     rsp, 78h
0x180003398  mov     rax, cs:__security_cookie
0x18000339f  xor     rax, rsp
0x1800033a2  mov     [rsp+78h+var_18], rax
0x1800033a7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800033ab  xor     r10d, r10d
0x1800033ae  mov     edx, 0Ah
0x1800033b3  test    r8, r8
0x1800033b6  jz      short loc_1800033CE
0x1800033b8  mov     rcx, rax
0x1800033bb  inc     rcx
0x1800033be  cmp     [r8+rcx*2], r10w
0x1800033c3  jnz     short loc_1800033BB
0x1800033c5  lea     ecx, ds:2[rcx*2]
0x1800033cc  jmp     short loc_1800033D0
0x1800033ce  mov     ecx, edx
0x1800033d0  test    r8, r8
0x1800033d3  mov     [rsp+78h+var_30], ecx
0x1800033d7  lea     r11, aNull; "NULL"
0x1800033de  mov     [rsp+78h+var_2C], r10d
0x1800033e3  cmovz   r8, r11
0x1800033e7  mov     [rsp+78h+var_38], r8
0x1800033ec  test    r9, r9
0x1800033ef  jz      short loc_180003405
0x1800033f1  inc     rax
0x1800033f4  cmp     [r9+rax*2], r10w
0x1800033f9  jnz     short loc_1800033F1
0x1800033fb  lea     edx, ds:2[rax*2]
0x180003402  test    r9, r9
0x180003405  cmovz   r9, r11
0x180003409  mov     [rsp+78h+var_20], edx
0x18000340d  mov     [rsp+78h+var_28], r9
0x180003412  lea     rax, [rsp+78h+var_48]
0x180003417  mov     r9d, 3
0x18000341d  mov     [rsp+78h+var_1C], r10d
0x180003422  lea     rdx, NullOrEmptyParameterFailureEvent
0x180003429  mov     [rsp+78h+var_58], rax
0x18000342e  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x180003435  call    McGenEventWrite_EventWriteTransfer
0x18000343a  mov     rcx, [rsp+78h+var_18]
0x18000343f  xor     rcx, rsp; StackCookie
0x180003442  call    __security_check_cookie
0x180003447  add     rsp, 78h
0x18000344b  retn
```
