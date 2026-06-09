# OfflineMapsTelemetry::MapsBrokerServiceStop_(void)

- ea: `0x180006750`
- end: `0x18000680d`
- name: `?MapsBrokerServiceStop_@OfflineMapsTelemetry@@QEAAXXZ`
- size: `189`
- prototype: `void __fastcall(OfflineMapsTelemetry *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006c24`

## callees

- `0x18000163c`
- `0x180001d00`
- `0x180006750`
- `0x18000689c`

## pseudocode

```c
void __fastcall OfflineMapsTelemetry::MapsBrokerServiceStop_(OfflineMapsTelemetry *this)
{
  const struct _tlgProvider_t *v2; // rax
  const struct _tlgProvider_t *v3; // r10
  __int64 v4; // rax
  __int64 v5; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v6[32]; // [rsp+40h] [rbp-58h] BYREF
  char *v7; // [rsp+60h] [rbp-38h]
  __int64 v8; // [rsp+68h] [rbp-30h]
  __int64 *v9; // [rsp+70h] [rbp-28h]
  __int64 v10; // [rsp+78h] [rbp-20h]

  v2 = OfflineMapsTraceLogging::Provider();
  v3 = v2;
  if ( *(_DWORD *)v2 > 5u )
  {
    v4 = *((_QWORD *)v2 + 3);
    if ( (*((_QWORD *)v3 + 2) & 0x400000000000LL) != 0 && (v4 & 0x400000000000LL) == v4 )
    {
      v5 = 50331648;
      v7 = (char *)this + 24;
      v9 = &v5;
      v10 = 8;
      v8 = 16;
      tlgWriteTransfer_EventWriteTransfer(v3, byte_180013F49, 0, 0, 4, v6);
    }
  }
}

```

## disassembly

```asm
0x180006750  push    rbx
0x180006752  sub     rsp, 90h
0x180006759  mov     rax, cs:__security_cookie
0x180006760  xor     rax, rsp
0x180006763  mov     [rsp+98h+var_18], rax
0x18000676b  mov     rbx, rcx
0x18000676e  call    ?Provider@OfflineMapsTraceLogging@@SAPEBU_tlgProvider_t@@XZ; OfflineMapsTraceLogging::Provider(void)
0x180006773  mov     r10, rax
0x180006776  mov     edx, [rax]
0x180006778  cmp     edx, 5
0x18000677b  jbe     short loc_1800067F4
0x18000677d  mov     rax, [rax+18h]
0x180006781  mov     r8, 400000000000h
0x18000678b  mov     rdx, [r10+10h]
0x18000678f  test    r8, rdx
0x180006792  jz      short loc_1800067F4
0x180006794  mov     rcx, rax
0x180006797  and     rcx, r8
0x18000679a  cmp     rcx, rax
0x18000679d  jnz     short loc_1800067F4
0x18000679f  lea     rax, [rbx+18h]
0x1800067a3  mov     [rsp+98h+var_68], 3000000h
0x1800067ac  mov     [rsp+98h+var_38], rax
0x1800067b1  lea     rcx, [rsp+98h+var_68]
0x1800067b6  lea     rax, [rsp+98h+var_58]
0x1800067bb  mov     [rsp+98h+var_28], rcx
0x1800067c0  mov     [rsp+98h+var_70], rax
0x1800067c5  lea     rdx, byte_180013F49
0x1800067cc  xor     r9d, r9d
0x1800067cf  mov     [rsp+98h+var_78], 4
0x1800067d7  xor     r8d, r8d
0x1800067da  mov     [rsp+98h+var_20], 8
0x1800067e3  mov     rcx, r10
0x1800067e6  mov     [rsp+98h+var_30], 10h
0x1800067ef  call    _tlgWriteTransfer_EventWriteTransfer
0x1800067f4  mov     rcx, [rsp+98h+var_18]
0x1800067fc  xor     rcx, rsp; StackCookie
0x1800067ff  call    __security_check_cookie
0x180006804  add     rsp, 90h
0x18000680b  pop     rbx
0x18000680c  retn
```
