# RtlpEtcIsValidFeatureId

- ea: `0x180147b18`
- end: `0x180147c02`
- name: `RtlpEtcIsValidFeatureId`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180147820`

## callees

- `0x18002ae28`
- `0x180147a94`
- `0x180147b18`
- `0x180162000`
- `0x18016f030`

## string_xrefs

- `0x180147b6d`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\FeatureManagement\EnterpriseTempControls`

## pseudocode

```c
bool __fastcall RtlpEtcIsValidFeatureId(unsigned int a1, int a2)
{
  char v4; // di
  int v6; // [rsp+20h] [rbp-1A8h]
  _DWORD v7[4]; // [rsp+30h] [rbp-198h] BYREF
  _BYTE v8[64]; // [rsp+40h] [rbp-188h] BYREF
  _BYTE v9[304]; // [rsp+80h] [rbp-148h] BYREF

  v7[0] = 0;
  memset_thunk_772440563353939046(v9, 0, 0x12Cu);
  memset_thunk_772440563353939046(v8, 0, 0x40u);
  v6 = a2;
  v4 = 0;
  if ( (int)RtlStringCchPrintfW(
              v9,
              150,
              L"%s\\%lu",
              L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control\\FeatureManagement\\EnterpriseTempControls",
              v6) >= 0
    && (int)RtlStringCchPrintfW(v8, 32, L"%lu", a1) >= 0
    && (int)RtlpEtcGetDwordFromRegistry(v9, v8, v7) >= 0 )
  {
    return v7[0] != 0;
  }
  return v4;
}

```

## disassembly

```asm
0x180147b18  mov     [rsp+arg_10], rbx
0x180147b1d  mov     [rsp+arg_18], rsi
0x180147b22  push    rdi
0x180147b23  sub     rsp, 1C0h
0x180147b2a  mov     rax, cs:__security_cookie
0x180147b31  xor     rax, rsp
0x180147b34  mov     [rsp+1C8h+var_18], rax
0x180147b3c  mov     ebx, edx
0x180147b3e  mov     [rsp+1C8h+var_198], 0
0x180147b46  mov     esi, ecx
0x180147b48  xor     edx, edx; Val
0x180147b4a  lea     rcx, [rsp+1C8h+var_148]; void *
0x180147b52  mov     r8d, 12Ch; Size
0x180147b58  call    memset$thunk$772440563353939046
0x180147b5d  xor     edx, edx; Val
0x180147b5f  lea     rcx, [rsp+1C8h+var_188]; void *
0x180147b64  lea     r8d, [rdx+40h]; Size
0x180147b68  call    memset$thunk$772440563353939046
0x180147b6d  lea     r9, aRegistryMachin_28; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x180147b74  mov     [rsp+1C8h+var_1A8], ebx
0x180147b78  lea     r8, aSLu; "%s\\%lu"
0x180147b7f  mov     edx, 96h
0x180147b84  lea     rcx, [rsp+1C8h+var_148]
0x180147b8c  xor     dil, dil
0x180147b8f  call    RtlStringCchPrintfW
0x180147b94  test    eax, eax
0x180147b96  js      short loc_180147BD9
0x180147b98  mov     r9d, esi
0x180147b9b  lea     r8, aLu; "%lu"
0x180147ba2  mov     edx, 20h ; ' '
0x180147ba7  lea     rcx, [rsp+1C8h+var_188]
0x180147bac  call    RtlStringCchPrintfW
0x180147bb1  test    eax, eax
0x180147bb3  js      short loc_180147BD9
0x180147bb5  lea     r8, [rsp+1C8h+var_198]
0x180147bba  lea     rdx, [rsp+1C8h+var_188]
0x180147bbf  lea     rcx, [rsp+1C8h+var_148]
0x180147bc7  call    RtlpEtcGetDwordFromRegistry
0x180147bcc  test    eax, eax
0x180147bce  js      short loc_180147BD9
0x180147bd0  cmp     [rsp+1C8h+var_198], 0
0x180147bd5  setnz   dil
0x180147bd9  mov     al, dil
0x180147bdc  mov     rcx, [rsp+1C8h+var_18]
0x180147be4  xor     rcx, rsp; StackCookie
0x180147be7  call    __security_check_cookie
0x180147bec  lea     r11, [rsp+1C8h+var_8]
0x180147bf4  mov     rbx, [r11+20h]
0x180147bf8  mov     rsi, [r11+28h]
0x180147bfc  mov     rsp, r11
0x180147bff  pop     rdi
0x180147c00  retn
```
