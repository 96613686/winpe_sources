# HsmpDbgInitialize

- ea: `0x1400121b8`
- end: `0x1400122a2`
- name: `HsmpDbgInitialize`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140087490`

## callees

- `0x14000ddc8`
- `0x1400121b8`
- `0x140042e60`

## import_xrefs

- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x14001222a`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x14001222a`

## string_xrefs

- `0x1400121cf`: `\Registry\Machine\System\CurrentControlSet\Services\%s\Debug`
- `0x14001221e`: `BreakOnOpen`
- `0x14001228f`: `BreakOnOpen`
- `0x140012241`: `\Registry\Machine\OSDATA\Software\Microsoft\%s\Debug`

## pseudocode

```c
NTSTATUS HsmpDbgInitialize()
{
  NTSTATUS result; // eax

  result = RtlStringCchPrintfW(
             &_DEBUG,
             0x80u,
             L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\%s\\Debug",
             _BE.Buffer);
  if ( result >= 0 )
  {
    HsmpGetRegDword(&_DEBUG, L"Flags", &dword_140028E50);
    HsmpGetRegDword(&_DEBUG, L"BreakOnHydration", &dword_140029084);
    HsmpGetRegDword(&_DEBUG, L"BreakOnOpen", &dword_140029088);
    result = RtlIsStateSeparationEnabled();
    if ( (_BYTE)result )
    {
      result = RtlStringCchPrintfW(
                 &_DEBUG,
                 0x80u,
                 L"\\Registry\\Machine\\OSDATA\\Software\\Microsoft\\%s\\Debug",
                 _BE.Buffer);
      if ( result >= 0 )
      {
        HsmpGetRegDword(&_DEBUG, L"Flags", &dword_140028E50);
        HsmpGetRegDword(&_DEBUG, L"BreakOnHydration", &dword_140029084);
        return HsmpGetRegDword(&_DEBUG, L"BreakOnOpen", &dword_140029088);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400121b8  push    rbx
0x1400121ba  sub     rsp, 20h
0x1400121be  mov     r9, cs:__BE.Buffer
0x1400121c5  lea     rbx, __DEBUG
0x1400121cc  mov     rcx, rbx; pszDest
0x1400121cf  lea     r8, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400121d6  mov     edx, 80h; cchDest
0x1400121db  call    RtlStringCchPrintfW
0x1400121e0  test    eax, eax
0x1400121e2  js      loc_14001229B
0x1400121e8  lea     r8, dword_140028E50
0x1400121ef  mov     rcx, rbx; SourceString
0x1400121f2  lea     rdx, aFlags; "Flags"
0x1400121f9  call    HsmpGetRegDword
0x1400121fe  lea     r8, dword_140029084
0x140012205  mov     rcx, rbx; SourceString
0x140012208  lea     rdx, aBreakonhydrati; "BreakOnHydration"
0x14001220f  call    HsmpGetRegDword
0x140012214  lea     r8, dword_140029088
0x14001221b  mov     rcx, rbx; SourceString
0x14001221e  lea     rdx, aBreakonopen; "BreakOnOpen"
0x140012225  call    HsmpGetRegDword
0x14001222a  call    cs:__imp_RtlIsStateSeparationEnabled
0x140012231  nop     dword ptr [rax+rax+00h]
0x140012236  test    al, al
0x140012238  jz      short loc_14001229B
0x14001223a  mov     r9, cs:__BE.Buffer
0x140012241  lea     r8, aRegistryMachin_3; "\\Registry\\Machine\\OSDATA\\Software\\"...
0x140012248  mov     edx, 80h; cchDest
0x14001224d  mov     rcx, rbx; pszDest
0x140012250  call    RtlStringCchPrintfW
0x140012255  test    eax, eax
0x140012257  js      short loc_14001229B
0x140012259  lea     r8, dword_140028E50
0x140012260  mov     rcx, rbx; SourceString
0x140012263  lea     rdx, aFlags; "Flags"
0x14001226a  call    HsmpGetRegDword
0x14001226f  lea     r8, dword_140029084
0x140012276  mov     rcx, rbx; SourceString
0x140012279  lea     rdx, aBreakonhydrati; "BreakOnHydration"
0x140012280  call    HsmpGetRegDword
0x140012285  lea     r8, dword_140029088
0x14001228c  mov     rcx, rbx; SourceString
0x14001228f  lea     rdx, aBreakonopen; "BreakOnOpen"
0x140012296  call    HsmpGetRegDword
0x14001229b  add     rsp, 20h
0x14001229f  pop     rbx
0x1400122a0  retn
```
