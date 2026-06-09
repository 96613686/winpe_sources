# Document::getAllowXSLTScriptingWithUMCI(void)

- ea: `0x1008bbe3`
- end: `0x1008bc6d`
- name: `?getAllowXSLTScriptingWithUMCI@Document@@CG_NXZ`
- size: `138`
- prototype: `bool __stdcall()`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1008becf`

## callees

- `0x1008bbe3`

## import_xrefs

- `ntdll!NtQuerySecurityPolicy` at `0x1008bc4a`
- `ntdll!NtQuerySecurityPolicy` at `0x1008bc4a`

## string_xrefs

- `0x1008bc19`: `MSXML`

## pseudocode

```c
bool __stdcall Document::getAllowXSLTScriptingWithUMCI()
{
  _UNICODE_STRING szProvider; // [esp+0h] [ebp-24h] BYREF
  _UNICODE_STRING szKey; // [esp+8h] [ebp-1Ch] BYREF
  _UNICODE_STRING szValueName; // [esp+10h] [ebp-14h] BYREF
  _SECURE_SETTING_VALUE_TYPE valueType; // [esp+18h] [ebp-Ch] BYREF
  unsigned int valueSize; // [esp+1Ch] [ebp-8h] BYREF
  unsigned __int8 value; // [esp+23h] [ebp-1h] BYREF

  szProvider.Length = 10;
  szKey.Length = 52;
  szKey.MaximumLength = 54;
  szValueName.MaximumLength = 14;
  szProvider.MaximumLength = 12;
  szProvider.Buffer = L"MSXML";
  szKey.Buffer = L"ALLOWXSLTSCRIPTINGWITHUMCI";
  szValueName.Length = 12;
  szValueName.Buffer = L"ALWAYS";
  value = 0;
  valueSize = 1;
  return (int)NtQuerySecurityPolicy(&szProvider, &szKey, &szValueName, &valueType, &value, &valueSize) >= 0
      && valueType == SecureSettingValueTypeBoolean
      && valueSize == 1
      && value != 0;
}

```

## disassembly

```asm
0x1008bbe3  mov     edi, edi
0x1008bbe5  push    ebp
0x1008bbe6  mov     ebp, esp
0x1008bbe8  sub     esp, 24h
0x1008bbeb  push    0Ah
0x1008bbed  pop     eax
0x1008bbee  push    0Ch
0x1008bbf0  pop     ecx
0x1008bbf1  push    34h ; '4'
0x1008bbf3  mov     [ebp+szProvider.Length], ax
0x1008bbf7  pop     eax
0x1008bbf8  push    36h ; '6'
0x1008bbfa  mov     [ebp+szKey.Length], ax
0x1008bbfe  pop     eax
0x1008bbff  push    0Eh
0x1008bc01  mov     [ebp+szKey.MaximumLength], ax
0x1008bc05  pop     eax
0x1008bc06  mov     [ebp+szValueName.MaximumLength], ax
0x1008bc0a  lea     eax, [ebp+valueSize]
0x1008bc0d  push    eax
0x1008bc0e  lea     eax, [ebp+value]
0x1008bc11  mov     [ebp+szProvider.MaximumLength], cx
0x1008bc15  push    eax
0x1008bc16  lea     eax, [ebp+valueType]
0x1008bc19  mov     [ebp+szProvider.Buffer], offset aMsxml; "MSXML" ...
0x1008bc20  push    eax
0x1008bc21  lea     eax, [ebp+szValueName]
0x1008bc24  mov     [ebp+szKey.Buffer], offset aAllowxsltscrip; "ALLOWXSLTSCRIPTINGWITHUMCI" ...
0x1008bc2b  push    eax
0x1008bc2c  lea     eax, [ebp+szKey]
0x1008bc2f  mov     [ebp+szValueName.Length], cx
0x1008bc33  push    eax
0x1008bc34  lea     eax, [ebp+szProvider]
0x1008bc37  mov     [ebp+szValueName.Buffer], offset aAlways; "ALWAYS" ...
0x1008bc3e  push    eax
0x1008bc3f  mov     [ebp+value], 0
0x1008bc43  mov     [ebp+valueSize], 1
0x1008bc4a  call    ds:__imp__NtQuerySecurityPolicy@24; NtQuerySecurityPolicy(x,x,x,x,x,x)
0x1008bc50  test    eax, eax
0x1008bc52  js      short loc_1008BC69
0x1008bc54  cmp     [ebp+valueType], 0
0x1008bc58  jnz     short loc_1008BC69
0x1008bc5a  cmp     [ebp+valueSize], 1
0x1008bc5e  jnz     short loc_1008BC69
0x1008bc60  cmp     [ebp+value], 0
0x1008bc64  setnz   al
0x1008bc67  leave
0x1008bc68  retn
0x1008bc69  xor     al, al
0x1008bc6b  leave
0x1008bc6c  retn
```
