# __CxxUnhandledExceptionFilter(_EXCEPTION_POINTERS *)

- ea: `0x140001320`
- end: `0x140001359`
- name: `?__CxxUnhandledExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@@Z`
- size: `57`
- prototype: `LONG __stdcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140001320`

## import_xrefs

- `msvcrt!?terminate@@YAXXZ` at `0x14000134b`
- `msvcrt!?terminate@@YAXXZ` at `0x14000134b`

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
0x140001320  sub     rsp, 28h
0x140001324  mov     rax, [rcx]
0x140001327  cmp     dword ptr [rax], 0E06D7363h
0x14000132d  jnz     short loc_140001352
0x14000132f  cmp     dword ptr [rax+18h], 4
0x140001333  jnz     short loc_140001352
0x140001335  mov     ecx, [rax+20h]
0x140001338  lea     eax, [rcx-19930520h]
0x14000133e  cmp     eax, 2
0x140001341  jbe     short loc_14000134B
0x140001343  cmp     ecx, 1994000h
0x140001349  jnz     short loc_140001352
0x14000134b  call    cs:__imp_?terminate@@YAXXZ; terminate(void)
0x140001352  xor     eax, eax
0x140001354  add     rsp, 28h
0x140001358  retn
```
