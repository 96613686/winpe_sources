# __CxxUnhandledExceptionFilter(_EXCEPTION_POINTERS *)

- ea: `0x1400013b0`
- end: `0x1400013e9`
- name: `?__CxxUnhandledExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@@Z`
- size: `57`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400013b0`

## import_xrefs

- `msvcrt!?terminate@@YAXXZ` at `0x1400013db`
- `msvcrt!?terminate@@YAXXZ` at `0x1400013db`

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
0x1400013b0  sub     rsp, 28h
0x1400013b4  mov     rax, [rcx]
0x1400013b7  cmp     dword ptr [rax], 0E06D7363h
0x1400013bd  jnz     short loc_1400013E2
0x1400013bf  cmp     dword ptr [rax+18h], 4
0x1400013c3  jnz     short loc_1400013E2
0x1400013c5  mov     ecx, [rax+20h]
0x1400013c8  lea     eax, [rcx-19930520h]
0x1400013ce  cmp     eax, 2
0x1400013d1  jbe     short loc_1400013DB
0x1400013d3  cmp     ecx, 1994000h
0x1400013d9  jnz     short loc_1400013E2
0x1400013db  call    cs:__imp_?terminate@@YAXXZ; terminate(void)
0x1400013e2  xor     eax, eax
0x1400013e4  add     rsp, 28h
0x1400013e8  retn
```
