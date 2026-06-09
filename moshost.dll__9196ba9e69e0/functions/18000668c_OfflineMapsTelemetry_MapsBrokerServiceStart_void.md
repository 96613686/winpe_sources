# OfflineMapsTelemetry::MapsBrokerServiceStart_(void)

- ea: `0x18000668c`
- end: `0x180006749`
- name: `?MapsBrokerServiceStart_@OfflineMapsTelemetry@@QEAAXXZ`
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
- `0x18000668c`
- `0x18000689c`

## pseudocode

```c
void __fastcall OfflineMapsTelemetry::MapsBrokerServiceStart_(OfflineMapsTelemetry *this)
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
      tlgWriteTransfer_EventWriteTransfer(v3, &dword_180013F8C, 0, 0, 4, v6);
    }
  }
}

```

## disassembly

```asm
0x18000668c  push    rbx
0x18000668e  sub     rsp, 90h
0x180006695  mov     rax, cs:__security_cookie
0x18000669c  xor     rax, rsp
0x18000669f  mov     [rsp+98h+var_18], rax
0x1800066a7  mov     rbx, rcx
0x1800066aa  call    ?Provider@OfflineMapsTraceLogging@@SAPEBU_tlgProvider_t@@XZ; OfflineMapsTraceLogging::Provider(void)
0x1800066af  mov     r10, rax
0x1800066b2  mov     edx, [rax]
0x1800066b4  cmp     edx, 5
0x1800066b7  jbe     short loc_180006730
0x1800066b9  mov     rax, [rax+18h]
0x1800066bd  mov     r8, 400000000000h
0x1800066c7  mov     rdx, [r10+10h]
0x1800066cb  test    r8, rdx
0x1800066ce  jz      short loc_180006730
0x1800066d0  mov     rcx, rax
0x1800066d3  and     rcx, r8
0x1800066d6  cmp     rcx, rax
0x1800066d9  jnz     short loc_180006730
0x1800066db  lea     rax, [rbx+18h]
0x1800066df  mov     [rsp+98h+var_68], 3000000h
0x1800066e8  mov     [rsp+98h+var_38], rax
0x1800066ed  lea     rcx, [rsp+98h+var_68]
0x1800066f2  lea     rax, [rsp+98h+var_58]
0x1800066f7  mov     [rsp+98h+var_28], rcx
0x1800066fc  mov     [rsp+98h+var_70], rax
0x180006701  lea     rdx, dword_180013F8C
0x180006708  xor     r9d, r9d
0x18000670b  mov     [rsp+98h+var_78], 4
0x180006713  xor     r8d, r8d
0x180006716  mov     [rsp+98h+var_20], 8
0x18000671f  mov     rcx, r10
0x180006722  mov     [rsp+98h+var_30], 10h
0x18000672b  call    _tlgWriteTransfer_EventWriteTransfer
0x180006730  mov     rcx, [rsp+98h+var_18]
0x180006738  xor     rcx, rsp; StackCookie
0x18000673b  call    __security_check_cookie
0x180006740  add     rsp, 90h
0x180006747  pop     rbx
0x180006748  retn
```
