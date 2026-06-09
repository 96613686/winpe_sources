# RtlpEtcIsValidFeatureId

- ea: `0x180148478`
- end: `0x180148562`
- name: `RtlpEtcIsValidFeatureId`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180148180`

## callees

- `0x180037038`
- `0x1801483f4`
- `0x180148478`
- `0x180162810`
- `0x18016f030`

## string_xrefs

- `0x1801484cd`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\FeatureManagement\EnterpriseTempControls`

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
0x180148478  mov     [rsp+arg_10], rbx
0x18014847d  mov     [rsp+arg_18], rsi
0x180148482  push    rdi
0x180148483  sub     rsp, 1C0h
0x18014848a  mov     rax, cs:__security_cookie
0x180148491  xor     rax, rsp
0x180148494  mov     [rsp+1C8h+var_18], rax
0x18014849c  mov     ebx, edx
0x18014849e  mov     [rsp+1C8h+var_198], 0
0x1801484a6  mov     esi, ecx
0x1801484a8  xor     edx, edx; Val
0x1801484aa  lea     rcx, [rsp+1C8h+var_148]; void *
0x1801484b2  mov     r8d, 12Ch; Size
0x1801484b8  call    memset$thunk$772440563353939046
0x1801484bd  xor     edx, edx; Val
0x1801484bf  lea     rcx, [rsp+1C8h+var_188]; void *
0x1801484c4  lea     r8d, [rdx+40h]; Size
0x1801484c8  call    memset$thunk$772440563353939046
0x1801484cd  lea     r9, aRegistryMachin_28; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x1801484d4  mov     [rsp+1C8h+var_1A8], ebx
0x1801484d8  lea     r8, aSLu; "%s\\%lu"
0x1801484df  mov     edx, 96h
0x1801484e4  lea     rcx, [rsp+1C8h+var_148]
0x1801484ec  xor     dil, dil
0x1801484ef  call    RtlStringCchPrintfW
0x1801484f4  test    eax, eax
0x1801484f6  js      short loc_180148539
0x1801484f8  mov     r9d, esi
0x1801484fb  lea     r8, aLu; "%lu"
0x180148502  mov     edx, 20h ; ' '
0x180148507  lea     rcx, [rsp+1C8h+var_188]
0x18014850c  call    RtlStringCchPrintfW
0x180148511  test    eax, eax
0x180148513  js      short loc_180148539
0x180148515  lea     r8, [rsp+1C8h+var_198]
0x18014851a  lea     rdx, [rsp+1C8h+var_188]
0x18014851f  lea     rcx, [rsp+1C8h+var_148]
0x180148527  call    RtlpEtcGetDwordFromRegistry
0x18014852c  test    eax, eax
0x18014852e  js      short loc_180148539
0x180148530  cmp     [rsp+1C8h+var_198], 0
0x180148535  setnz   dil
0x180148539  mov     al, dil
0x18014853c  mov     rcx, [rsp+1C8h+var_18]
0x180148544  xor     rcx, rsp; StackCookie
0x180148547  call    __security_check_cookie
0x18014854c  lea     r11, [rsp+1C8h+var_8]
0x180148554  mov     rbx, [r11+20h]
0x180148558  mov     rsi, [r11+28h]
0x18014855c  mov     rsp, r11
0x18014855f  pop     rdi
0x180148560  retn
```
