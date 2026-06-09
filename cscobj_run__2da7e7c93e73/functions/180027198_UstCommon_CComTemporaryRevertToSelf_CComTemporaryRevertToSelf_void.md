# UstCommon::CComTemporaryRevertToSelf::~CComTemporaryRevertToSelf(void)

- ea: `0x180027198`
- end: `0x1800271d1`
- name: `??1CComTemporaryRevertToSelf@UstCommon@@QEAA@XZ`
- size: `57`
- prototype: `void __fastcall(UstCommon::CComTemporaryRevertToSelf *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002af08`

## callees

- `0x180027198`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800271ab`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800271ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800271b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800271b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800271be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800271be`

## pseudocode

```c
void __fastcall UstCommon::CComTemporaryRevertToSelf::~CComTemporaryRevertToSelf(HANDLE *this)
{
  if ( *this )
  {
    if ( !SetThreadToken(0, *this) )
      GetLastError();
    CloseHandle(*this);
    *this = 0;
  }
}

```

## disassembly

```asm
0x180027198  push    rbx
0x18002719a  sub     rsp, 20h
0x18002719e  mov     rbx, rcx
0x1800271a1  mov     rdx, [rcx]; Token
0x1800271a4  test    rdx, rdx
0x1800271a7  jz      short loc_1800271CB
0x1800271a9  xor     ecx, ecx; Thread
0x1800271ab  call    cs:__imp_SetThreadToken
0x1800271b1  test    eax, eax
0x1800271b3  jnz     short loc_1800271BB
0x1800271b5  call    cs:__imp_GetLastError
0x1800271bb  mov     rcx, [rbx]; hObject
0x1800271be  call    cs:__imp_CloseHandle
0x1800271c4  mov     qword ptr [rbx], 0
0x1800271cb  add     rsp, 20h
0x1800271cf  pop     rbx
0x1800271d0  retn
```
