# QueryProtocolDefaultZone

- ea: `0x14008a060`
- end: `0x14008a193`
- name: `QueryProtocolDefaultZone`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14008a80c`

## callees

- `0x140088270`
- `0x14008a060`
- `0x1400924c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14008a15c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008a173`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008a15c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008a173`

## string_xrefs

- `0x14008a0d6`: `\Registry\Machine\Software\Microsoft\Windows\CurrentVersion\Internet Settings\ZoneMap`
- `0x14008a105`: `\Registry\Machine\Software\Microsoft\Windows\CurrentVersion\Internet Settings\ZoneMap`
- `0x14008a099`: `\Registry\Machine\Software\Policies\Microsoft\Windows\CurrentVersion\Internet Settings\ZoneMap`
- `0x14008a0ab`: `ProtocolDefaults`
- `0x14008a0e7`: `ProtocolDefaults`

## pseudocode

```c
__int64 __fastcall QueryProtocolDefaultZone(char a1, char a2, __int64 a3, _DWORD *a4)
{
  int v4; // esi
  WCHAR *v5; // rdi
  char v6; // r14
  char v7; // bp
  WCHAR *v9; // rbx
  WCHAR *v11; // [rsp+20h] [rbp-38h] BYREF
  WCHAR *v12; // [rsp+78h] [rbp+20h] BYREF

  v4 = 0;
  v5 = 0;
  v11 = 0;
  v6 = 0;
  v12 = 0;
  v7 = 0;
  *a4 = 3;
  if ( a2 )
  {
    v9 = (WCHAR *)L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\ZoneMap";
    if ( !a1 )
    {
      v4 = BuildUserZoneMapPath(
             a3,
             L"Software\\Policies\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\ZoneMap",
             L"ProtocolDefaults",
             &v12);
      if ( v4 < 0 )
        return (unsigned int)v4;
      v5 = v12;
      v7 = 1;
    }
  }
  else if ( a1 )
  {
    v9 = (WCHAR *)L"\\Registry\\Machine\\Software\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\ZoneMap";
  }
  else
  {
    v4 = BuildUserZoneMapPath(
           a3,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\ZoneMap",
           L"ProtocolDefaults",
           &v11);
    if ( v4 < 0 )
      return (unsigned int)v4;
    v9 = v11;
    v5 = (WCHAR *)L"\\Registry\\Machine\\Software\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\ZoneMap";
    v6 = 1;
  }
  if ( (int)RfsRegGetDWord(v9, L"file") >= 0 || v5 && (int)RfsRegGetDWord(v5, L"file") >= 0 )
    *a4 = 3;
  if ( v6 )
    ExFreePoolWithTag(v9, 0x7A4D6D53u);
  if ( v7 )
    ExFreePoolWithTag(v5, 0x7A4D6D53u);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14008a060  mov     r11, rsp
0x14008a063  mov     [r11+8], rbx
0x14008a067  push    rbp
0x14008a068  push    rsi
0x14008a069  push    rdi
0x14008a06a  push    r14
0x14008a06c  push    r15
0x14008a06e  sub     rsp, 30h
0x14008a072  xor     esi, esi
0x14008a074  xor     edi, edi
0x14008a076  mov     rax, r8
0x14008a079  mov     [r11-38h], rsi
0x14008a07d  xor     r14b, r14b
0x14008a080  mov     [r11+20h], rdi
0x14008a084  xor     bpl, bpl
0x14008a087  mov     r15, r9
0x14008a08a  lea     r8d, [rsi+3]
0x14008a08e  mov     [r11+10h], r8d
0x14008a092  mov     [r9], r8d
0x14008a095  test    dl, dl
0x14008a097  jz      short loc_14008A0D2
0x14008a099  lea     rbx, aRegistryMachin_3; "\\Registry\\Machine\\Software\\Policies"...
0x14008a0a0  test    cl, cl
0x14008a0a2  jnz     short loc_14008A10F
0x14008a0a4  lea     r9, [r11+20h]
0x14008a0a8  mov     rcx, rax
0x14008a0ab  lea     r8, aProtocoldefaul; "ProtocolDefaults"
0x14008a0b2  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Windows"...
0x14008a0b9  call    BuildUserZoneMapPath
0x14008a0be  mov     esi, eax
0x14008a0c0  test    eax, eax
0x14008a0c2  js      loc_14008A17F
0x14008a0c8  mov     rdi, [rsp+58h+arg_18]
0x14008a0cd  mov     bpl, 1
0x14008a0d0  jmp     short loc_14008A10F
0x14008a0d2  test    cl, cl
0x14008a0d4  jz      short loc_14008A0DF
0x14008a0d6  lea     rbx, aRegistryMachin_1; "\\Registry\\Machine\\Software\\Microsof"...
0x14008a0dd  jmp     short loc_14008A10F
0x14008a0df  lea     r9, [rsp+58h+var_38]
0x14008a0e4  mov     rcx, rax
0x14008a0e7  lea     r8, aProtocoldefaul; "ProtocolDefaults"
0x14008a0ee  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14008a0f5  call    BuildUserZoneMapPath
0x14008a0fa  mov     esi, eax
0x14008a0fc  test    eax, eax
0x14008a0fe  js      short loc_14008A17F
0x14008a100  mov     rbx, [rsp+58h+var_38]
0x14008a105  lea     rdi, aRegistryMachin_1; "\\Registry\\Machine\\Software\\Microsof"...
0x14008a10c  mov     r14b, 1
0x14008a10f  lea     r8, [rsp+58h+arg_8]
0x14008a114  mov     rcx, rbx; SourceString
0x14008a117  lea     rdx, aFile; "file"
0x14008a11e  call    RfsRegGetDWord
0x14008a123  test    eax, eax
0x14008a125  jns     short loc_14008A144
0x14008a127  test    rdi, rdi
0x14008a12a  jz      short loc_14008A14B
0x14008a12c  lea     r8, [rsp+58h+arg_8]
0x14008a131  mov     rcx, rdi; SourceString
0x14008a134  lea     rdx, aFile; "file"
0x14008a13b  call    RfsRegGetDWord
0x14008a140  test    eax, eax
0x14008a142  js      short loc_14008A14B
0x14008a144  mov     eax, [rsp+58h+arg_8]
0x14008a148  mov     [r15], eax
0x14008a14b  mov     r15d, 7A4D6D53h
0x14008a151  test    r14b, r14b
0x14008a154  jz      short loc_14008A168
0x14008a156  mov     edx, r15d; Tag
0x14008a159  mov     rcx, rbx; P
0x14008a15c  call    cs:__imp_ExFreePoolWithTag
0x14008a163  nop     dword ptr [rax+rax+00h]
0x14008a168  test    bpl, bpl
0x14008a16b  jz      short loc_14008A17F
0x14008a16d  mov     edx, r15d; Tag
0x14008a170  mov     rcx, rdi; P
0x14008a173  call    cs:__imp_ExFreePoolWithTag
0x14008a17a  nop     dword ptr [rax+rax+00h]
0x14008a17f  mov     rbx, [rsp+58h+arg_0]
0x14008a184  mov     eax, esi
0x14008a186  add     rsp, 30h
0x14008a18a  pop     r15
0x14008a18c  pop     r14
0x14008a18e  pop     rdi
0x14008a18f  pop     rsi
0x14008a190  pop     rbp
0x14008a191  retn
```
