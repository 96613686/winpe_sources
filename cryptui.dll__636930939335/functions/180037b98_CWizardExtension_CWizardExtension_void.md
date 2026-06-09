# CWizardExtension::~CWizardExtension(void)

- ea: `0x180037b98`
- end: `0x180037bf1`
- name: `??1CWizardExtension@@QEAA@XZ`
- size: `89`
- prototype: `void __fastcall(CWizardExtension *__hidden this)`
- caller_count: `10`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180037e10`
- `0x180037ec0`
- `0x180037f90`
- `0x180038050`
- `0x1800380f0`
- `0x1800381b0`
- `0x180038270`
- `0x1800408b5`
- `0x1800408d9`
- `0x1800408fd`

## callees

- `0x180037b98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037bb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037bb0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037bc3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037bc3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180037bbb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180037bbb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CWizardExtension::~CWizardExtension(HMODULE *this)
{
  DWORD LastError; // ebx

  if ( *this )
  {
    LastError = GetLastError();
    FreeLibrary(*this);
    SetLastError(LastError);
    this[1] = 0;
    *((_DWORD *)this + 4) = 0;
    *this = 0;
  }
  *this = 0;
}

```

## disassembly

```asm
0x180037b98  mov     [rsp+arg_8], rbx
0x180037b9d  mov     [rsp+arg_0], rcx
0x180037ba2  push    rdi
0x180037ba3  sub     rsp, 20h
0x180037ba7  mov     rdi, rcx
0x180037baa  cmp     qword ptr [rcx], 0
0x180037bae  jz      short loc_180037BDF
0x180037bb0  call    cs:__imp_GetLastError
0x180037bb6  mov     ebx, eax
0x180037bb8  mov     rcx, [rdi]; hLibModule
0x180037bbb  call    cs:__imp_FreeLibrary
0x180037bc1  mov     ecx, ebx; dwErrCode
0x180037bc3  call    cs:__imp_SetLastError
0x180037bc9  mov     qword ptr [rdi+8], 0
0x180037bd1  mov     dword ptr [rdi+10h], 0
0x180037bd8  mov     qword ptr [rdi], 0
0x180037bdf  mov     qword ptr [rdi], 0
0x180037be6  mov     rbx, [rsp+28h+arg_8]
0x180037beb  add     rsp, 20h
0x180037bef  pop     rdi
0x180037bf0  retn
```
