# CsDllMain

- ea: `0x18003cf0c`
- end: `0x18003cf9f`
- name: `CsDllMain`
- size: `147`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180042c88`

## callees

- `0x18003cf0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003cf54`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003cf54`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003cf6b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003cf6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cf47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cf47`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cf28`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cf28`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003cf8c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003cf8c`

## pseudocode

```c
__int64 __fastcall CsDllMain(int a1)
{
  if ( a1 == 1 )
  {
    InitializeCriticalSection(&CriticalSection);
    byte_1800FDF94 = 1;
  }
  else if ( !a1 && byte_1800FDF94 )
  {
    EnterCriticalSection(&CriticalSection);
    if ( byte_1800FDFA0 && hLibModule )
    {
      FreeLibrary(hLibModule);
      hLibModule = 0;
    }
    LeaveCriticalSection(&CriticalSection);
    DeleteCriticalSection(&CriticalSection);
  }
  return 1;
}

```

## disassembly

```asm
0x18003cf0c  sub     rsp, 28h
0x18003cf10  cmp     ecx, 1
0x18003cf13  jz      short loc_18003CF64
0x18003cf15  test    ecx, ecx
0x18003cf17  jnz     short loc_18003CF5A
0x18003cf19  cmp     cs:byte_1800FDF94, cl
0x18003cf1f  jz      short loc_18003CF5A
0x18003cf21  lea     rcx, CriticalSection; lpCriticalSection
0x18003cf28  call    cs:__imp_EnterCriticalSection
0x18003cf2e  jmp     short loc_18003CF37
0x18003cf30  mov     eax, 1
0x18003cf35  jmp     short loc_18003CF5F
0x18003cf37  cmp     cs:byte_1800FDFA0, 0
0x18003cf3e  jnz     short loc_18003CF80
0x18003cf40  lea     rcx, CriticalSection; lpCriticalSection
0x18003cf47  call    cs:__imp_LeaveCriticalSection
0x18003cf4d  lea     rcx, CriticalSection; lpCriticalSection
0x18003cf54  call    cs:__imp_DeleteCriticalSection
0x18003cf5a  mov     eax, 1
0x18003cf5f  add     rsp, 28h
0x18003cf63  retn
0x18003cf64  lea     rcx, CriticalSection; lpCriticalSection
0x18003cf6b  call    cs:__imp_InitializeCriticalSection
0x18003cf71  jmp     short loc_18003CF77
0x18003cf73  xor     eax, eax
0x18003cf75  jmp     short loc_18003CF5F
0x18003cf77  mov     cs:byte_1800FDF94, 1
0x18003cf7e  jmp     short loc_18003CF5A
0x18003cf80  mov     rcx, cs:hLibModule; hLibModule
0x18003cf87  test    rcx, rcx
0x18003cf8a  jz      short loc_18003CF40
0x18003cf8c  call    cs:__imp_FreeLibrary
0x18003cf92  mov     cs:hLibModule, 0
0x18003cf9d  jmp     short loc_18003CF40
```
