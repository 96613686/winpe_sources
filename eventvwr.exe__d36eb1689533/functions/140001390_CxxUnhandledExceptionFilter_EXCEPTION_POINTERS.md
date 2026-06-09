# __CxxUnhandledExceptionFilter(_EXCEPTION_POINTERS *)

- ea: `0x140001390`
- end: `0x1400013c9`
- name: `?__CxxUnhandledExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@@Z`
- size: `57`
- prototype: `LONG __stdcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140001390`

## import_xrefs

- `msvcrt!?terminate@@YAXXZ` at `0x1400013bb`
- `msvcrt!?terminate@@YAXXZ` at `0x1400013bb`

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
0x140001390  sub     rsp, 28h
0x140001394  mov     rax, [rcx]
0x140001397  cmp     dword ptr [rax], 0E06D7363h
0x14000139d  jnz     short loc_1400013C2
0x14000139f  cmp     dword ptr [rax+18h], 4
0x1400013a3  jnz     short loc_1400013C2
0x1400013a5  mov     ecx, [rax+20h]
0x1400013a8  lea     eax, [rcx-19930520h]
0x1400013ae  cmp     eax, 2
0x1400013b1  jbe     short loc_1400013BB
0x1400013b3  cmp     ecx, 1994000h
0x1400013b9  jnz     short loc_1400013C2
0x1400013bb  call    cs:__imp_?terminate@@YAXXZ; terminate(void)
0x1400013c2  xor     eax, eax
0x1400013c4  add     rsp, 28h
0x1400013c8  retn
```
