# CW32System::GetLocaleCodePage(void)

- ea: `0x1800905ec`
- end: `0x180090607`
- name: `?GetLocaleCodePage@CW32System@@SAIXZ`
- size: `27`
- prototype: `unsigned int(void)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18006f638`
- `0x18008dffc`

## callees

- `0x18002c900`

## import_xrefs

- `KERNEL32!GetThreadLocale` at `0x1800905f0`
- `KERNEL32!GetThreadLocale` at `0x1800905f0`

## pseudocode

```c
unsigned int CW32System::GetLocaleCodePage(void)
{
  unsigned __int16 ThreadLocale; // ax

  ThreadLocale = GetThreadLocale();
  return CW32System::ConvertLanguageIDtoCodePage(ThreadLocale);
}

```

## disassembly

```asm
0x1800905ec  sub     rsp, 28h
0x1800905f0  call    cs:__imp_GetThreadLocale
0x1800905f7  nop     dword ptr [rax+rax+00h]
0x1800905fc  mov     ecx, eax; unsigned __int16
0x1800905fe  add     rsp, 28h
0x180090602  jmp     ?ConvertLanguageIDtoCodePage@CW32System@@SAIG@Z; CW32System::ConvertLanguageIDtoCodePage(ushort)
```
