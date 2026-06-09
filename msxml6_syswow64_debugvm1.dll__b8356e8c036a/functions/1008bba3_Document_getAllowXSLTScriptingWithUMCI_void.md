# Document::getAllowXSLTScriptingWithUMCI(void)

- ea: `0x1008bba3`
- end: `0x1008bc2d`
- name: `?getAllowXSLTScriptingWithUMCI@Document@@CG_NXZ`
- size: `138`
- prototype: `bool __stdcall()`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1008be8f`

## callees

- `0x1008bba3`

## import_xrefs

- `ntdll!NtQuerySecurityPolicy` at `0x1008bc0a`
- `ntdll!NtQuerySecurityPolicy` at `0x1008bc0a`

## string_xrefs

- `0x1008bbd9`: `MSXML`

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
0x1008bba3  mov     edi, edi
0x1008bba5  push    ebp
0x1008bba6  mov     ebp, esp
0x1008bba8  sub     esp, 24h
0x1008bbab  push    0Ah
0x1008bbad  pop     eax
0x1008bbae  push    0Ch
0x1008bbb0  pop     ecx
0x1008bbb1  push    34h ; '4'
0x1008bbb3  mov     [ebp+szProvider.Length], ax
0x1008bbb7  pop     eax
0x1008bbb8  push    36h ; '6'
0x1008bbba  mov     [ebp+szKey.Length], ax
0x1008bbbe  pop     eax
0x1008bbbf  push    0Eh
0x1008bbc1  mov     [ebp+szKey.MaximumLength], ax
0x1008bbc5  pop     eax
0x1008bbc6  mov     [ebp+szValueName.MaximumLength], ax
0x1008bbca  lea     eax, [ebp+valueSize]
0x1008bbcd  push    eax
0x1008bbce  lea     eax, [ebp+value]
0x1008bbd1  mov     [ebp+szProvider.MaximumLength], cx
0x1008bbd5  push    eax
0x1008bbd6  lea     eax, [ebp+valueType]
0x1008bbd9  mov     [ebp+szProvider.Buffer], offset aMsxml; "MSXML" ...
0x1008bbe0  push    eax
0x1008bbe1  lea     eax, [ebp+szValueName]
0x1008bbe4  mov     [ebp+szKey.Buffer], offset aAllowxsltscrip; "ALLOWXSLTSCRIPTINGWITHUMCI" ...
0x1008bbeb  push    eax
0x1008bbec  lea     eax, [ebp+szKey]
0x1008bbef  mov     [ebp+szValueName.Length], cx
0x1008bbf3  push    eax
0x1008bbf4  lea     eax, [ebp+szProvider]
0x1008bbf7  mov     [ebp+szValueName.Buffer], offset aAlways; "ALWAYS" ...
0x1008bbfe  push    eax
0x1008bbff  mov     [ebp+value], 0
0x1008bc03  mov     [ebp+valueSize], 1
0x1008bc0a  call    ds:__imp__NtQuerySecurityPolicy@24; NtQuerySecurityPolicy(x,x,x,x,x,x)
0x1008bc10  test    eax, eax
0x1008bc12  js      short loc_1008BC29
0x1008bc14  cmp     [ebp+valueType], 0
0x1008bc18  jnz     short loc_1008BC29
0x1008bc1a  cmp     [ebp+valueSize], 1
0x1008bc1e  jnz     short loc_1008BC29
0x1008bc20  cmp     [ebp+value], 0
0x1008bc24  setnz   al
0x1008bc27  leave
0x1008bc28  retn
0x1008bc29  xor     al, al
0x1008bc2b  leave
0x1008bc2c  retn
```
