# OfflineMapsTelemetry::UpdateTaskFailed_(bool,uint,uint,long)

- ea: `0x180007004`
- end: `0x18000713d`
- name: `?UpdateTaskFailed_@OfflineMapsTelemetry@@QEAAX_NIIJ@Z`
- size: `313`
- prototype: `void __fastcall(OfflineMapsTelemetry *this, unsigned __int8, int, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x1800065c4`

## callees

- `0x18000163c`
- `0x180001be0`
- `0x1800055b0`
- `0x180007004`

## pseudocode

```c
void __fastcall OfflineMapsTelemetry::UpdateTaskFailed_(
        OfflineMapsTelemetry *this,
        unsigned __int8 a2,
        int a3,
        int a4,
        int a5)
{
  int v6; // esi
  const struct _tlgProvider_t *v9; // rax
  const struct _tlgProvider_t *v10; // r11
  __int64 v11; // rax
  int v12; // [rsp+30h] [rbp-91h] BYREF
  int v13; // [rsp+34h] [rbp-8Dh] BYREF
  int v14; // [rsp+38h] [rbp-89h] BYREF
  int v15; // [rsp+3Ch] [rbp-85h] BYREF
  __int64 v16; // [rsp+40h] [rbp-81h] BYREF
  _BYTE v17[32]; // [rsp+50h] [rbp-71h] BYREF
  int *v18; // [rsp+70h] [rbp-51h]
  __int64 v19; // [rsp+78h] [rbp-49h]
  int *v20; // [rsp+80h] [rbp-41h]
  __int64 v21; // [rsp+88h] [rbp-39h]
  int *v22; // [rsp+90h] [rbp-31h]
  __int64 v23; // [rsp+98h] [rbp-29h]
  char *v24; // [rsp+A0h] [rbp-21h]
  __int64 v25; // [rsp+A8h] [rbp-19h]
  int *v26; // [rsp+B0h] [rbp-11h]
  __int64 v27; // [rsp+B8h] [rbp-9h]
  char *v28; // [rsp+C0h] [rbp-1h]
  __int64 v29; // [rsp+C8h] [rbp+7h]
  __int64 *v30; // [rsp+D0h] [rbp+Fh]
  __int64 v31; // [rsp+D8h] [rbp+17h]

  v6 = a2;
  v9 = OfflineMapsTraceLogging::Provider();
  v10 = v9;
  if ( *(_DWORD *)v9 > 5u )
  {
    v11 = *((_QWORD *)v9 + 3);
    if ( (*((_QWORD *)v10 + 2) & 0x400000000000LL) != 0 && (v11 & 0x400000000000LL) == v11 )
    {
      v12 = a5;
      v28 = (char *)this + 24;
      v30 = &v16;
      v24 = (char *)this + 24;
      v26 = &v12;
      v16 = 0x2000000;
      v22 = &v13;
      v13 = a4;
      v20 = &v14;
      v18 = &v15;
      v14 = a3;
      v15 = v6;
      v31 = 8;
      v29 = 16;
      v27 = 4;
      v25 = 16;
      v23 = 4;
      v21 = 4;
      v19 = 4;
      tlgWriteTransfer_EventWriteTransfer(v10, word_18000B58A, 0, 0, 9, v17);
    }
  }
}

```

## disassembly

```asm
0x180007004  push    rbp
0x180007006  push    rbx
0x180007007  push    rsi
0x180007008  push    rdi
0x180007009  push    r14
0x18000700b  lea     rbp, [rsp-2Fh]
0x180007010  sub     rsp, 0F0h
0x180007017  mov     rax, cs:__security_cookie
0x18000701e  xor     rax, rsp
0x180007021  mov     [rbp+4Fh+var_30], rax
0x180007025  mov     ebx, r9d
0x180007028  movzx   esi, dl
0x18000702b  mov     edi, r8d
0x18000702e  mov     r14, rcx
0x180007031  call    ?Provider@OfflineMapsTraceLogging@@SAPEBU_tlgProvider_t@@XZ; OfflineMapsTraceLogging::Provider(void)
0x180007036  mov     r11, rax
0x180007039  mov     r10d, [rax]
0x18000703c  cmp     r10d, 5
0x180007040  jbe     loc_180007123
0x180007046  mov     rax, [rax+18h]
0x18000704a  mov     rdx, 400000000000h
0x180007054  mov     r10, [r11+10h]
0x180007058  test    rdx, r10
0x18000705b  jz      loc_180007123
0x180007061  mov     rcx, rax
0x180007064  and     rcx, rdx
0x180007067  cmp     rcx, rax
0x18000706a  jnz     loc_180007123
0x180007070  mov     eax, [rbp+4Fh+arg_20]
0x180007073  lea     rcx, [r14+18h]
0x180007077  mov     [rsp+110h+var_E0], eax
0x18000707b  lea     rdx, word_18000B58A
0x180007082  lea     rax, [rsp+110h+var_D0]
0x180007087  mov     [rbp+4Fh+var_50], rcx
0x18000708b  mov     [rbp+4Fh+var_40], rax
0x18000708f  xor     r9d, r9d
0x180007092  lea     rax, [rsp+110h+var_E0]
0x180007097  mov     [rbp+4Fh+var_70], rcx
0x18000709b  mov     [rbp+4Fh+var_60], rax
0x18000709f  xor     r8d, r8d
0x1800070a2  lea     rax, [rsp+110h+var_DC]
0x1800070a7  mov     [rsp+110h+var_D0], 2000000h
0x1800070b0  mov     [rbp+4Fh+var_80], rax
0x1800070b4  mov     rcx, r11
0x1800070b7  lea     rax, [rsp+110h+var_D8]
0x1800070bc  mov     [rsp+110h+var_DC], ebx
0x1800070c0  mov     [rbp+4Fh+var_90], rax
0x1800070c4  lea     rax, [rsp+110h+var_D4]
0x1800070c9  mov     [rbp+4Fh+var_A0], rax
0x1800070cd  lea     rax, [rbp+4Fh+var_C0]
0x1800070d1  mov     [rsp+110h+var_E8], rax
0x1800070d6  mov     [rsp+110h+var_F0], 9
0x1800070de  mov     [rsp+110h+var_D8], edi
0x1800070e2  mov     [rsp+110h+var_D4], esi
0x1800070e6  mov     [rbp+4Fh+var_38], 8
0x1800070ee  mov     [rbp+4Fh+var_48], 10h
0x1800070f6  mov     [rbp+4Fh+var_58], 4
0x1800070fe  mov     [rbp+4Fh+var_68], 10h
0x180007106  mov     [rbp+4Fh+var_78], 4
0x18000710e  mov     [rbp+4Fh+var_88], 4
0x180007116  mov     [rbp+4Fh+var_98], 4
0x18000711e  call    _tlgWriteTransfer_EventWriteTransfer
0x180007123  mov     rcx, [rbp+4Fh+var_30]
0x180007127  xor     rcx, rsp; StackCookie
0x18000712a  call    __security_check_cookie
0x18000712f  add     rsp, 0F0h
0x180007136  pop     r14
0x180007138  pop     rdi
0x180007139  pop     rsi
0x18000713a  pop     rbx
0x18000713b  pop     rbp
0x18000713c  retn
```
