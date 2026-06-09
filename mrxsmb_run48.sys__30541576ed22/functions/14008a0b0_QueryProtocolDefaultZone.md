# QueryProtocolDefaultZone

- ea: `0x14008a0b0`
- end: `0x14008a1e3`
- name: `QueryProtocolDefaultZone`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14008a85c`

## callees

- `0x1400882c0`
- `0x14008a0b0`
- `0x140092510`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14008a1ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008a1c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008a1ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008a1c3`

## string_xrefs

- `0x14008a0e9`: `\Registry\Machine\Software\Policies\Microsoft\Windows\CurrentVersion\Internet Settings\ZoneMap`
- `0x14008a0fb`: `ProtocolDefaults`
- `0x14008a137`: `ProtocolDefaults`
- `0x14008a126`: `\Registry\Machine\Software\Microsoft\Windows\CurrentVersion\Internet Settings\ZoneMap`
- `0x14008a155`: `\Registry\Machine\Software\Microsoft\Windows\CurrentVersion\Internet Settings\ZoneMap`

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
0x14008a0b0  mov     r11, rsp
0x14008a0b3  mov     [r11+8], rbx
0x14008a0b7  push    rbp
0x14008a0b8  push    rsi
0x14008a0b9  push    rdi
0x14008a0ba  push    r14
0x14008a0bc  push    r15
0x14008a0be  sub     rsp, 30h
0x14008a0c2  xor     esi, esi
0x14008a0c4  xor     edi, edi
0x14008a0c6  mov     rax, r8
0x14008a0c9  mov     [r11-38h], rsi
0x14008a0cd  xor     r14b, r14b
0x14008a0d0  mov     [r11+20h], rdi
0x14008a0d4  xor     bpl, bpl
0x14008a0d7  mov     r15, r9
0x14008a0da  lea     r8d, [rsi+3]
0x14008a0de  mov     [r11+10h], r8d
0x14008a0e2  mov     [r9], r8d
0x14008a0e5  test    dl, dl
0x14008a0e7  jz      short loc_14008A122
0x14008a0e9  lea     rbx, aRegistryMachin_3; "\\Registry\\Machine\\Software\\Policies"...
0x14008a0f0  test    cl, cl
0x14008a0f2  jnz     short loc_14008A15F
0x14008a0f4  lea     r9, [r11+20h]
0x14008a0f8  mov     rcx, rax
0x14008a0fb  lea     r8, aProtocoldefaul; "ProtocolDefaults"
0x14008a102  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Windows"...
0x14008a109  call    BuildUserZoneMapPath
0x14008a10e  mov     esi, eax
0x14008a110  test    eax, eax
0x14008a112  js      loc_14008A1CF
0x14008a118  mov     rdi, [rsp+58h+arg_18]
0x14008a11d  mov     bpl, 1
0x14008a120  jmp     short loc_14008A15F
0x14008a122  test    cl, cl
0x14008a124  jz      short loc_14008A12F
0x14008a126  lea     rbx, aRegistryMachin_1; "\\Registry\\Machine\\Software\\Microsof"...
0x14008a12d  jmp     short loc_14008A15F
0x14008a12f  lea     r9, [rsp+58h+var_38]
0x14008a134  mov     rcx, rax
0x14008a137  lea     r8, aProtocoldefaul; "ProtocolDefaults"
0x14008a13e  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14008a145  call    BuildUserZoneMapPath
0x14008a14a  mov     esi, eax
0x14008a14c  test    eax, eax
0x14008a14e  js      short loc_14008A1CF
0x14008a150  mov     rbx, [rsp+58h+var_38]
0x14008a155  lea     rdi, aRegistryMachin_1; "\\Registry\\Machine\\Software\\Microsof"...
0x14008a15c  mov     r14b, 1
0x14008a15f  lea     r8, [rsp+58h+arg_8]
0x14008a164  mov     rcx, rbx; SourceString
0x14008a167  lea     rdx, aFile; "file"
0x14008a16e  call    RfsRegGetDWord
0x14008a173  test    eax, eax
0x14008a175  jns     short loc_14008A194
0x14008a177  test    rdi, rdi
0x14008a17a  jz      short loc_14008A19B
0x14008a17c  lea     r8, [rsp+58h+arg_8]
0x14008a181  mov     rcx, rdi; SourceString
0x14008a184  lea     rdx, aFile; "file"
0x14008a18b  call    RfsRegGetDWord
0x14008a190  test    eax, eax
0x14008a192  js      short loc_14008A19B
0x14008a194  mov     eax, [rsp+58h+arg_8]
0x14008a198  mov     [r15], eax
0x14008a19b  mov     r15d, 7A4D6D53h
0x14008a1a1  test    r14b, r14b
0x14008a1a4  jz      short loc_14008A1B8
0x14008a1a6  mov     edx, r15d; Tag
0x14008a1a9  mov     rcx, rbx; P
0x14008a1ac  call    cs:__imp_ExFreePoolWithTag
0x14008a1b3  nop     dword ptr [rax+rax+00h]
0x14008a1b8  test    bpl, bpl
0x14008a1bb  jz      short loc_14008A1CF
0x14008a1bd  mov     edx, r15d; Tag
0x14008a1c0  mov     rcx, rdi; P
0x14008a1c3  call    cs:__imp_ExFreePoolWithTag
0x14008a1ca  nop     dword ptr [rax+rax+00h]
0x14008a1cf  mov     rbx, [rsp+58h+arg_0]
0x14008a1d4  mov     eax, esi
0x14008a1d6  add     rsp, 30h
0x14008a1da  pop     r15
0x14008a1dc  pop     r14
0x14008a1de  pop     rdi
0x14008a1df  pop     rsi
0x14008a1e0  pop     rbp
0x14008a1e1  retn
```
