# HsmpDbgInitialize

- ea: `0x140012238`
- end: `0x140012322`
- name: `HsmpDbgInitialize`
- size: `234`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140087490`

## callees

- `0x14000ddc8`
- `0x140012238`
- `0x140042f50`

## import_xrefs

- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x1400122aa`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x1400122aa`

## string_xrefs

- `0x14001224f`: `\Registry\Machine\System\CurrentControlSet\Services\%s\Debug`
- `0x1400122c1`: `\Registry\Machine\OSDATA\Software\Microsoft\%s\Debug`
- `0x14001229e`: `BreakOnOpen`
- `0x14001230f`: `BreakOnOpen`

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
0x140012238  push    rbx
0x14001223a  sub     rsp, 20h
0x14001223e  mov     r9, cs:__BE.Buffer
0x140012245  lea     rbx, __DEBUG
0x14001224c  mov     rcx, rbx; pszDest
0x14001224f  lea     r8, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x140012256  mov     edx, 80h; cchDest
0x14001225b  call    RtlStringCchPrintfW
0x140012260  test    eax, eax
0x140012262  js      loc_14001231B
0x140012268  lea     r8, dword_140028E50
0x14001226f  mov     rcx, rbx; SourceString
0x140012272  lea     rdx, aFlags; "Flags"
0x140012279  call    HsmpGetRegDword
0x14001227e  lea     r8, dword_140029084
0x140012285  mov     rcx, rbx; SourceString
0x140012288  lea     rdx, aBreakonhydrati; "BreakOnHydration"
0x14001228f  call    HsmpGetRegDword
0x140012294  lea     r8, dword_140029088
0x14001229b  mov     rcx, rbx; SourceString
0x14001229e  lea     rdx, aBreakonopen; "BreakOnOpen"
0x1400122a5  call    HsmpGetRegDword
0x1400122aa  call    cs:__imp_RtlIsStateSeparationEnabled
0x1400122b1  nop     dword ptr [rax+rax+00h]
0x1400122b6  test    al, al
0x1400122b8  jz      short loc_14001231B
0x1400122ba  mov     r9, cs:__BE.Buffer
0x1400122c1  lea     r8, aRegistryMachin_3; "\\Registry\\Machine\\OSDATA\\Software\\"...
0x1400122c8  mov     edx, 80h; cchDest
0x1400122cd  mov     rcx, rbx; pszDest
0x1400122d0  call    RtlStringCchPrintfW
0x1400122d5  test    eax, eax
0x1400122d7  js      short loc_14001231B
0x1400122d9  lea     r8, dword_140028E50
0x1400122e0  mov     rcx, rbx; SourceString
0x1400122e3  lea     rdx, aFlags; "Flags"
0x1400122ea  call    HsmpGetRegDword
0x1400122ef  lea     r8, dword_140029084
0x1400122f6  mov     rcx, rbx; SourceString
0x1400122f9  lea     rdx, aBreakonhydrati; "BreakOnHydration"
0x140012300  call    HsmpGetRegDword
0x140012305  lea     r8, dword_140029088
0x14001230c  mov     rcx, rbx; SourceString
0x14001230f  lea     rdx, aBreakonopen; "BreakOnOpen"
0x140012316  call    HsmpGetRegDword
0x14001231b  add     rsp, 20h
0x14001231f  pop     rbx
0x140012320  retn
```
