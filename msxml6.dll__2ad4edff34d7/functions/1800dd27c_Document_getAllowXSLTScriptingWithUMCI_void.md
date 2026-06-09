# Document::getAllowXSLTScriptingWithUMCI(void)

- ea: `0x1800dd27c`
- end: `0x1800dd319`
- name: `?getAllowXSLTScriptingWithUMCI@Document@@CA_NXZ`
- size: `157`
- prototype: `bool __fastcall()`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800e5f50`

## callees

- `0x1800dd27c`

## import_xrefs

- `ntdll!NtQuerySecurityPolicy` at `0x1800dd2f2`
- `ntdll!NtQuerySecurityPolicy` at `0x1800dd2f2`

## string_xrefs

- `0x1800dd285`: `MSXML`

## pseudocode

```c
bool __fastcall Document::getAllowXSLTScriptingWithUMCI()
{
  _UNICODE_STRING szValueName; // [rsp+30h] [rbp-30h] BYREF
  _UNICODE_STRING szKey; // [rsp+40h] [rbp-20h] BYREF
  _UNICODE_STRING szProvider; // [rsp+50h] [rbp-10h] BYREF
  unsigned __int8 value; // [rsp+70h] [rbp+10h] BYREF
  _SECURE_SETTING_VALUE_TYPE valueType; // [rsp+78h] [rbp+18h] BYREF
  unsigned int valueSize; // [rsp+80h] [rbp+20h] BYREF

  *(_QWORD *)&szProvider.Length = 786442;
  szProvider.Buffer = L"MSXML";
  *(_QWORD *)&szKey.Length = 3538996;
  szKey.Buffer = L"ALLOWXSLTSCRIPTINGWITHUMCI";
  *(_QWORD *)&szValueName.Length = 917516;
  szValueName.Buffer = L"ALWAYS";
  value = 0;
  valueSize = 1;
  valueType = SecureSettingValueTypeBoolean;
  return (int)((__int64 (__fastcall *)(_UNICODE_STRING *, _UNICODE_STRING *, _UNICODE_STRING *, _SECURE_SETTING_VALUE_TYPE *, unsigned __int8 *, unsigned int *))NtQuerySecurityPolicy)(
                &szProvider,
                &szKey,
                &szValueName,
                &valueType,
                &value,
                &valueSize) >= 0
      && valueType == SecureSettingValueTypeBoolean
      && valueSize == 1
      && value != 0;
}

```

## disassembly

```asm
0x1800dd27c  push    rbp
0x1800dd27e  mov     rbp, rsp
0x1800dd281  sub     rsp, 60h
0x1800dd285  lea     rax, aMsxml; "MSXML"
0x1800dd28c  mov     qword ptr [rbp+szProvider.Length], 0C000Ah
0x1800dd294  mov     [rbp+szProvider.Buffer], rax
0x1800dd298  lea     r9, [rbp+valueType]
0x1800dd29c  lea     rax, aAllowxsltscrip; "ALLOWXSLTSCRIPTINGWITHUMCI"
0x1800dd2a3  mov     qword ptr [rbp+szKey.Length], 360034h
0x1800dd2ab  mov     [rbp+szKey.Buffer], rax
0x1800dd2af  lea     r8, [rbp+szValueName]
0x1800dd2b3  lea     rax, aAlways; "ALWAYS"
0x1800dd2ba  mov     qword ptr [rbp+szValueName.Length], 0E000Ch
0x1800dd2c2  mov     [rbp+szValueName.Buffer], rax
0x1800dd2c6  lea     rdx, [rbp+szKey]
0x1800dd2ca  lea     rax, [rbp+valueSize]
0x1800dd2ce  mov     [rbp+value], 0
0x1800dd2d2  mov     [rsp+60h+var_38], rax
0x1800dd2d7  lea     rcx, [rbp+szProvider]
0x1800dd2db  lea     rax, [rbp+value]
0x1800dd2df  mov     [rbp+valueSize], 1
0x1800dd2e6  mov     [rsp+60h+var_40], rax
0x1800dd2eb  mov     [rbp+valueType], 0
0x1800dd2f2  call    cs:__imp_NtQuerySecurityPolicy
0x1800dd2f8  test    eax, eax
0x1800dd2fa  js      short loc_1800DD311
0x1800dd2fc  cmp     [rbp+valueType], 0
0x1800dd300  jnz     short loc_1800DD311
0x1800dd302  cmp     [rbp+valueSize], 1
0x1800dd306  jnz     short loc_1800DD311
0x1800dd308  cmp     [rbp+value], 0
0x1800dd30c  setnz   al
0x1800dd30f  jmp     short loc_1800DD313
0x1800dd311  xor     al, al
0x1800dd313  add     rsp, 60h
0x1800dd317  pop     rbp
0x1800dd318  retn
```
