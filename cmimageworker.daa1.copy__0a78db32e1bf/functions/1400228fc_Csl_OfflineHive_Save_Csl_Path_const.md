# Csl::OfflineHive::Save(Csl::Path const &)

- ea: `0x1400228fc`
- end: `0x1400229c2`
- name: `?Save@OfflineHive@Csl@@QEBAJAEBVPath@2@@Z`
- size: `198`
- prototype: `__int64 __fastcall(Csl::OfflineHive *__hidden this, const struct Path *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x140019e40`
- `0x14001b938`
- `0x14001d310`

## callees

- `0x140006fc4`
- `0x14000d7bc`
- `0x1400228fc`
- `0x140023a10`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400229a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400229a8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140022932`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140022932`

## string_xrefs

- `0x14002294c`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x140022989`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Csl::OfflineHive::Save(Csl::OfflineHive *this, LPCWSTR *a2)
{
  HANDLE FileW; // rbx
  const char *v4; // r9
  unsigned int v6; // eax
  unsigned int v7; // edi
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  FileW = CreateFileW(*a2, 2u, 0, 0, 1u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xD7,
             (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
             v4);
  v6 = ORSaveHiveToHandle(*((_QWORD *)this + 1), (_DWORD)FileW, 10, 0, *(_BYTE *)this != 0);
  if ( v6 )
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xFE,
           (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
           (const char *)v6,
           dwCreationDisposition);
  else
    v7 = 0;
  if ( FileW )
    CloseHandle(FileW);
  return v7;
}

```

## disassembly

```asm
0x1400228fc  mov     [rsp+arg_0], rbx
0x140022901  push    rdi
0x140022902  sub     rsp, 40h
0x140022906  mov     rax, rdx
0x140022909  mov     rdi, rcx
0x14002290c  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x140022915  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14002291d  mov     [rsp+48h+dwCreationDisposition], 1; dwCreationDisposition
0x140022925  xor     r9d, r9d; lpSecurityAttributes
0x140022928  xor     r8d, r8d; dwShareMode
0x14002292b  lea     edx, [r9+2]; dwDesiredAccess
0x14002292f  mov     rcx, [rax]; lpFileName
0x140022932  call    cs:__imp_CreateFileW
0x140022939  nop     dword ptr [rax+rax+00h]
0x14002293e  mov     rbx, rax
0x140022941  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140022945  jnz     short loc_14002295F
0x140022947  mov     rcx, [rsp+48h]; this
0x14002294c  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x140022953  mov     edx, 0D7h; void *
0x140022958  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14002295d  jmp     short loc_1400229B6
0x14002295f  xor     eax, eax
0x140022961  cmp     [rdi], al
0x140022963  setnz   al
0x140022966  mov     [rsp+48h+dwCreationDisposition], eax; unsigned int
0x14002296a  xor     r9d, r9d
0x14002296d  lea     r8d, [r9+0Ah]
0x140022971  mov     rdx, rbx
0x140022974  mov     rcx, [rdi+8]
0x140022978  call    ORSaveHiveToHandle
0x14002297d  test    eax, eax
0x14002297f  jz      short loc_14002299E
0x140022981  mov     rcx, [rsp+48h]; this
0x140022986  mov     r9d, eax; char *
0x140022989  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x140022990  mov     edx, 0FEh; void *
0x140022995  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14002299a  mov     edi, eax
0x14002299c  jmp     short loc_1400229A0
0x14002299e  xor     edi, edi
0x1400229a0  test    rbx, rbx
0x1400229a3  jz      short loc_1400229B4
0x1400229a5  mov     rcx, rbx; hObject
0x1400229a8  call    cs:__imp_CloseHandle
0x1400229af  nop     dword ptr [rax+rax+00h]
0x1400229b4  mov     eax, edi
0x1400229b6  mov     rbx, [rsp+48h+arg_0]
0x1400229bb  add     rsp, 40h
0x1400229bf  pop     rdi
0x1400229c0  retn
```
