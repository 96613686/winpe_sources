# OfflineMapsTelemetry::UpdateTaskCompleted_(bool,uint,uint)

- ea: `0x180006ee4`
- end: `0x180006ffc`
- name: `?UpdateTaskCompleted_@OfflineMapsTelemetry@@QEAAX_NII@Z`
- size: `280`
- prototype: `void __fastcall(OfflineMapsTelemetry *this, unsigned __int8, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800065c4`

## callees

- `0x18000163c`
- `0x180001be0`
- `0x1800055b0`
- `0x180006ee4`

## pseudocode

```c
void __fastcall OfflineMapsTelemetry::UpdateTaskCompleted_(
        OfflineMapsTelemetry *this,
        unsigned __int8 a2,
        int a3,
        int a4)
{
  int v5; // esi
  const struct _tlgProvider_t *v8; // rax
  const struct _tlgProvider_t *v9; // r11
  __int64 v10; // rax
  int v11; // [rsp+30h] [rbp-79h] BYREF
  int v12; // [rsp+34h] [rbp-75h] BYREF
  int v13; // [rsp+38h] [rbp-71h] BYREF
  __int64 v14; // [rsp+40h] [rbp-69h] BYREF
  _BYTE v15[32]; // [rsp+50h] [rbp-59h] BYREF
  int *v16; // [rsp+70h] [rbp-39h]
  __int64 v17; // [rsp+78h] [rbp-31h]
  int *v18; // [rsp+80h] [rbp-29h]
  __int64 v19; // [rsp+88h] [rbp-21h]
  int *v20; // [rsp+90h] [rbp-19h]
  __int64 v21; // [rsp+98h] [rbp-11h]
  char *v22; // [rsp+A0h] [rbp-9h]
  __int64 v23; // [rsp+A8h] [rbp-1h]
  char *v24; // [rsp+B0h] [rbp+7h]
  __int64 v25; // [rsp+B8h] [rbp+Fh]
  __int64 *v26; // [rsp+C0h] [rbp+17h]
  __int64 v27; // [rsp+C8h] [rbp+1Fh]

  v5 = a2;
  v8 = OfflineMapsTraceLogging::Provider();
  v9 = v8;
  if ( *(_DWORD *)v8 > 5u )
  {
    v10 = *((_QWORD *)v8 + 3);
    if ( (*((_QWORD *)v9 + 2) & 0x400000000000LL) != 0 && (v10 & 0x400000000000LL) == v10 )
    {
      v14 = 50331648;
      v24 = (char *)this + 24;
      v27 = 8;
      v26 = &v14;
      v22 = (char *)this + 24;
      v20 = &v11;
      v11 = a4;
      v18 = &v12;
      v12 = a3;
      v16 = &v13;
      v13 = v5;
      v25 = 16;
      v23 = 16;
      v21 = 4;
      v19 = 4;
      v17 = 4;
      tlgWriteTransfer_EventWriteTransfer(v9, &byte_18000B627, 0, 0, 8, v15);
    }
  }
}

```

## disassembly

```asm
0x180006ee4  push    rbp
0x180006ee6  push    rbx
0x180006ee7  push    rsi
0x180006ee8  push    rdi
0x180006ee9  push    r14
0x180006eeb  lea     rbp, [rsp-37h]
0x180006ef0  sub     rsp, 0E0h
0x180006ef7  mov     rax, cs:__security_cookie
0x180006efe  xor     rax, rsp
0x180006f01  mov     [rbp+57h+var_30], rax
0x180006f05  mov     ebx, r9d
0x180006f08  movzx   esi, dl
0x180006f0b  mov     edi, r8d
0x180006f0e  mov     r14, rcx
0x180006f11  call    ?Provider@OfflineMapsTraceLogging@@SAPEBU_tlgProvider_t@@XZ; OfflineMapsTraceLogging::Provider(void)
0x180006f16  mov     r11, rax
0x180006f19  mov     r10d, [rax]
0x180006f1c  cmp     r10d, 5
0x180006f20  jbe     loc_180006FE2
0x180006f26  mov     rax, [rax+18h]
0x180006f2a  mov     rdx, 400000000000h
0x180006f34  mov     r10, [r11+10h]
0x180006f38  test    rdx, r10
0x180006f3b  jz      loc_180006FE2
0x180006f41  mov     rcx, rax
0x180006f44  and     rcx, rdx
0x180006f47  cmp     rcx, rax
0x180006f4a  jnz     loc_180006FE2
0x180006f50  lea     rcx, [r14+18h]
0x180006f54  mov     [rbp+57h+var_C0], 3000000h
0x180006f5c  mov     r8d, 8
0x180006f62  mov     [rbp+57h+var_50], rcx
0x180006f66  lea     rax, [rbp+57h+var_C0]
0x180006f6a  mov     [rbp+57h+var_38], r8
0x180006f6e  mov     [rbp+57h+var_40], rax
0x180006f72  lea     rdx, byte_18000B627
0x180006f79  lea     rax, [rbp+57h+var_D0]
0x180006f7d  mov     [rbp+57h+var_60], rcx
0x180006f81  mov     [rbp+57h+var_70], rax
0x180006f85  xor     r9d, r9d
0x180006f88  lea     rax, [rbp+57h+var_CC]
0x180006f8c  mov     [rbp+57h+var_D0], ebx
0x180006f8f  mov     [rbp+57h+var_80], rax
0x180006f93  mov     rcx, r11
0x180006f96  lea     rax, [rbp+57h+var_C8]
0x180006f9a  mov     [rbp+57h+var_CC], edi
0x180006f9d  mov     [rbp+57h+var_90], rax
0x180006fa1  lea     rax, [rbp+57h+var_B0]
0x180006fa5  mov     [rsp+100h+var_D8], rax
0x180006faa  mov     [rsp+100h+var_E0], r8d
0x180006faf  xor     r8d, r8d
0x180006fb2  mov     [rbp+57h+var_C8], esi
0x180006fb5  mov     [rbp+57h+var_48], 10h
0x180006fbd  mov     [rbp+57h+var_58], 10h
0x180006fc5  mov     [rbp+57h+var_68], 4
0x180006fcd  mov     [rbp+57h+var_78], 4
0x180006fd5  mov     [rbp+57h+var_88], 4
0x180006fdd  call    _tlgWriteTransfer_EventWriteTransfer
0x180006fe2  mov     rcx, [rbp+57h+var_30]
0x180006fe6  xor     rcx, rsp; StackCookie
0x180006fe9  call    __security_check_cookie
0x180006fee  add     rsp, 0E0h
0x180006ff5  pop     r14
0x180006ff7  pop     rdi
0x180006ff8  pop     rsi
0x180006ff9  pop     rbx
0x180006ffa  pop     rbp
0x180006ffb  retn
```
