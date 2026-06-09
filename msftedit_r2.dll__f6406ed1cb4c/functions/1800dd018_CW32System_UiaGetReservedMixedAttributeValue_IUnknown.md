# CW32System::UiaGetReservedMixedAttributeValue(IUnknown * *)

- ea: `0x1800dd018`
- end: `0x1800dd0c8`
- name: `?UiaGetReservedMixedAttributeValue@CW32System@@SAJPEAPEAUIUnknown@@@Z`
- size: `176`
- prototype: `__int64 __fastcall(struct IUnknown **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800dca6c`

## callees

- `0x18000f358`
- `0x18005921c`
- `0x1800dd018`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800dd084`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800dd084`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800dd062`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800dd062`

## string_xrefs

- `0x1800dd055`: `uiautomationcore.dll`

## pseudocode

```c
__int64 __fastcall CW32System::UiaGetReservedMixedAttributeValue(struct IUnknown **a1)
{
  __int64 (__fastcall *v1)(__int64 *); // rax
  HMODULE Library; // rax
  struct IUnknown **v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = a1;
  v1 = (__int64 (__fastcall *)(__int64 *))pUiaGetReservedMixedAttributeValue;
  if ( pUiaGetReservedMixedAttributeValue )
    return v1(&qword_1802E4168);
  CWriteLock::CWriteLock((unsigned int *)&v4, 0);
  if ( !pUiaGetReservedMixedAttributeValue )
  {
    Library = qword_1802E4220;
    if ( qword_1802E4220
      || (Library = LoadLibraryExW(L"uiautomationcore.dll", 0, 0x800u), (qword_1802E4220 = Library) != 0) )
    {
      pUiaGetReservedMixedAttributeValue = GetProcAddress(Library, "UiaGetReservedMixedAttributeValue");
    }
  }
  CWriteLock::~CWriteLock((CWriteLock *)&v4);
  v1 = (__int64 (__fastcall *)(__int64 *))pUiaGetReservedMixedAttributeValue;
  if ( pUiaGetReservedMixedAttributeValue )
    return v1(&qword_1802E4168);
  else
    return 2147500034LL;
}

```

## disassembly

```asm
0x1800dd018  mov     [rsp+arg_0], rcx
0x1800dd01d  sub     rsp, 28h
0x1800dd021  mov     rax, cs:?pUiaGetReservedMixedAttributeValue@@3PEAXEA; void * pUiaGetReservedMixedAttributeValue
0x1800dd028  test    rax, rax
0x1800dd02b  jnz     loc_1800DD0B8
0x1800dd031  xor     edx, edx
0x1800dd033  lea     rcx, [rsp+28h+arg_0]
0x1800dd038  call    ??0CWriteLock@@QEAA@W4LOCK_TYPE@@@Z; CWriteLock::CWriteLock(LOCK_TYPE)
0x1800dd03d  cmp     cs:?pUiaGetReservedMixedAttributeValue@@3PEAXEA, 0; void * pUiaGetReservedMixedAttributeValue
0x1800dd045  jnz     short loc_1800DD097
0x1800dd047  mov     rax, cs:qword_1802E4220
0x1800dd04e  test    rax, rax
0x1800dd051  jnz     short loc_1800DD07A
0x1800dd053  xor     edx, edx; hFile
0x1800dd055  lea     rcx, aUiautomationco; "uiautomationcore.dll"
0x1800dd05c  mov     r8d, 800h; dwFlags
0x1800dd062  call    cs:__imp_LoadLibraryExW
0x1800dd069  nop     dword ptr [rax+rax+00h]
0x1800dd06e  mov     cs:qword_1802E4220, rax
0x1800dd075  test    rax, rax
0x1800dd078  jz      short loc_1800DD097
0x1800dd07a  lea     rdx, aUiagetreserved; "UiaGetReservedMixedAttributeValue"
0x1800dd081  mov     rcx, rax; hModule
0x1800dd084  call    cs:__imp_GetProcAddress
0x1800dd08b  nop     dword ptr [rax+rax+00h]
0x1800dd090  mov     cs:?pUiaGetReservedMixedAttributeValue@@3PEAXEA, rax; void * pUiaGetReservedMixedAttributeValue
0x1800dd097  lea     rcx, [rsp+28h+arg_0]; this
0x1800dd09c  call    ??1CWriteLock@@QEAA@XZ; CWriteLock::~CWriteLock(void)
0x1800dd0a1  mov     rax, cs:?pUiaGetReservedMixedAttributeValue@@3PEAXEA; void * pUiaGetReservedMixedAttributeValue
0x1800dd0a8  test    rax, rax
0x1800dd0ab  jnz     short loc_1800DD0B8
0x1800dd0ad  mov     eax, 80004002h
0x1800dd0b2  add     rsp, 28h
0x1800dd0b6  retn
0x1800dd0b8  lea     rcx, qword_1802E4168
0x1800dd0bf  add     rsp, 28h
0x1800dd0c3  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
