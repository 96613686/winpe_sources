# __CxxUnhandledExceptionFilter(_EXCEPTION_POINTERS *)

- ea: `0x140001340`
- end: `0x140001379`
- name: `?__CxxUnhandledExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@@Z`
- size: `57`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140001340`

## import_xrefs

- `msvcrt!?terminate@@YAXXZ` at `0x14000136b`
- `msvcrt!?terminate@@YAXXZ` at `0x14000136b`

## pseudocode

```c
__int64 __fastcall __CxxUnhandledExceptionFilter(struct _EXCEPTION_POINTERS *ExceptionInfo)
{
  PEXCEPTION_RECORD ExceptionRecord; // rax
  int v2; // ecx

  ExceptionRecord = ExceptionInfo->ExceptionRecord;
  if ( ExceptionInfo->ExceptionRecord->ExceptionCode == -529697949 && ExceptionRecord->NumberParameters == 4 )
  {
    v2 = ExceptionRecord->ExceptionInformation[0];
    if ( (unsigned int)(v2 - 429065504) <= 2 || v2 == 26820608 )
      terminate();
  }
  return 0;
}

```

## disassembly

```asm
0x140001340  sub     rsp, 28h
0x140001344  mov     rax, [rcx]
0x140001347  cmp     dword ptr [rax], 0E06D7363h
0x14000134d  jnz     short loc_140001372
0x14000134f  cmp     dword ptr [rax+18h], 4
0x140001353  jnz     short loc_140001372
0x140001355  mov     ecx, [rax+20h]
0x140001358  lea     eax, [rcx-19930520h]
0x14000135e  cmp     eax, 2
0x140001361  jbe     short loc_14000136B
0x140001363  cmp     ecx, 1994000h
0x140001369  jnz     short loc_140001372
0x14000136b  call    cs:__imp_?terminate@@YAXXZ; terminate(void)
0x140001372  xor     eax, eax
0x140001374  add     rsp, 28h
0x140001378  retn
```
