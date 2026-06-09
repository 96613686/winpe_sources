# McTemplateK0hzr0hzr2q_EtwWriteTransfer

- ea: `0x1400041b8`
- end: `0x140004265`
- name: `McTemplateK0hzr0hzr2q_EtwWriteTransfer`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140015980`

## callees

- `0x140004158`
- `0x1400054a0`

## string_xrefs

- `0x1400041f2`: `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\NetworkProvider\HardenedPaths`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0hzr0hzr2q_EtwWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        unsigned __int16 a6,
        __int64 a7,
        char a8)
{
  __int16 v9; // [rsp+30h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+40h] [rbp-39h] BYREF
  __int16 *v11; // [rsp+50h] [rbp-29h]
  __int64 v12; // [rsp+58h] [rbp-21h]
  const wchar_t *v13; // [rsp+60h] [rbp-19h]
  __int64 v14; // [rsp+68h] [rbp-11h]
  unsigned __int16 *v15; // [rsp+70h] [rbp-9h]
  __int64 v16; // [rsp+78h] [rbp-1h]
  __int64 v17; // [rsp+80h] [rbp+7h]
  int v18; // [rsp+88h] [rbp+Fh]
  int v19; // [rsp+8Ch] [rbp+13h]
  char *v20; // [rsp+90h] [rbp+17h]
  __int64 v21; // [rsp+98h] [rbp+1Fh]

  v12 = 2;
  v19 = 0;
  v9 = 84;
  v11 = &v9;
  v13 = L"HKEY_LOCAL_MACHINE\\Software\\Policies\\Microsoft\\Windows\\NetworkProvider\\HardenedPaths";
  v14 = 168;
  v15 = &a6;
  v17 = a7;
  v16 = 2;
  v18 = 2 * a6;
  v20 = &a8;
  v21 = 4;
  return McGenEventWrite_EtwWriteTransfer(
           a1,
           (const EVENT_DESCRIPTOR *)UncHardening_UnsupportedRegistryValueType,
           a3,
           6u,
           &v10);
}

```

## disassembly

```asm
0x1400041b8  push    rbp
0x1400041ba  lea     rbp, [rsp-37h]
0x1400041bf  sub     rsp, 0B0h
0x1400041c6  mov     rax, cs:__security_cookie
0x1400041cd  xor     rax, rsp
0x1400041d0  mov     [rbp+37h+var_10], rax
0x1400041d4  xor     edx, edx
0x1400041d6  mov     [rbp+37h+var_58], 2
0x1400041de  mov     eax, 54h ; 'T'
0x1400041e3  mov     [rbp+37h+var_24], edx
0x1400041e6  mov     [rbp+37h+var_80], ax
0x1400041ea  lea     rax, [rbp+37h+var_80]
0x1400041ee  mov     [rbp+37h+var_60], rax
0x1400041f2  lea     rax, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\Software\\Policies"...
0x1400041f9  mov     [rbp+37h+var_50], rax
0x1400041fd  lea     r9d, [rdx+6]
0x140004201  lea     rax, [rbp+37h+arg_28]
0x140004205  mov     [rbp+37h+var_48], 0A8h
0x14000420d  mov     [rbp+37h+var_40], rax
0x140004211  lea     rdx, UncHardening_UnsupportedRegistryValueType
0x140004218  mov     rax, [rbp+37h+arg_30]
0x14000421c  mov     [rbp+37h+var_30], rax
0x140004220  movzx   eax, [rbp+37h+arg_28]
0x140004224  add     eax, eax
0x140004226  mov     [rbp+37h+var_38], 2
0x14000422e  mov     [rbp+37h+var_28], eax
0x140004231  lea     rax, [rbp+37h+arg_38]
0x140004235  mov     [rbp+37h+var_20], rax
0x140004239  lea     rax, [rbp+37h+var_70]
0x14000423d  mov     [rsp+0B0h+var_90], rax
0x140004242  mov     [rbp+37h+var_18], 4
0x14000424a  call    McGenEventWrite_EtwWriteTransfer
0x14000424f  mov     rcx, [rbp+37h+var_10]
0x140004253  xor     rcx, rsp; StackCookie
0x140004256  call    __security_check_cookie
0x14000425b  add     rsp, 0B0h
0x140004262  pop     rbp
0x140004263  retn
```
