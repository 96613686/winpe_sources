# Document::getAllowXSLTScriptingWithUMCI(void)

- ea: `0x1800df1f0`
- end: `0x1800df294`
- name: `?getAllowXSLTScriptingWithUMCI@Document@@CA_NXZ`
- size: `164`
- prototype: `bool __fastcall()`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800df414`

## callees

- `0x1800df1f0`

## import_xrefs

- `ntdll!NtQuerySecurityPolicy` at `0x1800df266`
- `ntdll!NtQuerySecurityPolicy` at `0x1800df266`

## string_xrefs

- `0x1800df1f9`: `MSXML`

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
0x1800df1f0  push    rbp
0x1800df1f2  mov     rbp, rsp
0x1800df1f5  sub     rsp, 60h
0x1800df1f9  lea     rax, aMsxml; "MSXML"
0x1800df200  mov     qword ptr [rbp+szProvider.Length], 0C000Ah
0x1800df208  mov     [rbp+szProvider.Buffer], rax
0x1800df20c  lea     r9, [rbp+valueType]
0x1800df210  lea     rax, aAllowxsltscrip; "ALLOWXSLTSCRIPTINGWITHUMCI"
0x1800df217  mov     qword ptr [rbp+szKey.Length], 360034h
0x1800df21f  mov     [rbp+szKey.Buffer], rax
0x1800df223  lea     r8, [rbp+szValueName]
0x1800df227  lea     rax, aAlways; "ALWAYS"
0x1800df22e  mov     qword ptr [rbp+szValueName.Length], 0E000Ch
0x1800df236  mov     [rbp+szValueName.Buffer], rax
0x1800df23a  lea     rdx, [rbp+szKey]
0x1800df23e  lea     rax, [rbp+valueSize]
0x1800df242  mov     [rbp+value], 0
0x1800df246  mov     [rsp+60h+var_38], rax
0x1800df24b  lea     rcx, [rbp+szProvider]
0x1800df24f  lea     rax, [rbp+value]
0x1800df253  mov     [rbp+valueSize], 1
0x1800df25a  mov     [rsp+60h+var_40], rax
0x1800df25f  mov     [rbp+valueType], 0
0x1800df266  call    cs:__imp_NtQuerySecurityPolicy
0x1800df26d  nop     dword ptr [rax+rax+00h]
0x1800df272  test    eax, eax
0x1800df274  js      short loc_1800DF28B
0x1800df276  cmp     [rbp+valueType], 0
0x1800df27a  jnz     short loc_1800DF28B
0x1800df27c  cmp     [rbp+valueSize], 1
0x1800df280  jnz     short loc_1800DF28B
0x1800df282  cmp     [rbp+value], 0
0x1800df286  setnz   al
0x1800df289  jmp     short loc_1800DF28D
0x1800df28b  xor     al, al
0x1800df28d  add     rsp, 60h
0x1800df291  pop     rbp
0x1800df292  retn
```
