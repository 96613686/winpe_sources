# Is64bitDll(wchar_t const *)

- ea: `0x180028bdc`
- end: `0x180028cc0`
- name: `?Is64bitDll@@YAHPEB_W@Z`
- size: `228`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x180020864`

## callees

- `0x180006dcc`
- `0x180028bdc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028c9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028ca7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028c9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028ca7`
- `ntdll!NtQuerySection` at `0x180028c80`
- `ntdll!NtQuerySection` at `0x180028c80`
- `ntdll!NtCreateSection` at `0x180028c5d`
- `ntdll!NtCreateSection` at `0x180028c5d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180028c0b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180028c0b`

## pseudocode

```c
__int64 __fastcall Is64bitDll(const wchar_t *a1)
{
  unsigned int v1; // ebx
  HANDLE FileHandle; // rdi
  _BYTE SectionInformation[48]; // [rsp+40h] [rbp-48h] BYREF
  __int16 v5; // [rsp+70h] [rbp-18h]
  void *SectionHandle; // [rsp+98h] [rbp+10h] BYREF

  v1 = 0;
  FileHandle = CreateFileW(a1, 0x100020u, 5u, 0, 3u, 0x8000000u, 0);
  if ( FileHandle )
  {
    SectionHandle = 0;
    memset_0(SectionInformation, 0, 0x40u);
    if ( NtCreateSection(&SectionHandle, 0xF001Fu, 0, 0, 0x10u, 0x1000000u, FileHandle) >= 0 )
    {
      NtQuerySection(SectionHandle, SectionImageInformation, SectionInformation, 0x40u, 0);
      if ( v5 == -31132 )
        v1 = 6;
      CloseHandle(SectionHandle);
    }
    CloseHandle(FileHandle);
  }
  return v1;
}

```

## disassembly

```asm
0x180028bdc  mov     rax, rsp
0x180028bdf  mov     [rax+8], rbx
0x180028be3  push    rdi
0x180028be4  sub     rsp, 80h
0x180028beb  xor     ebx, ebx
0x180028bed  xor     r9d, r9d; lpSecurityAttributes
0x180028bf0  mov     [rax-58h], rbx
0x180028bf4  mov     edx, 100020h; dwDesiredAccess
0x180028bf9  mov     dword ptr [rax-60h], 8000000h
0x180028c00  mov     dword ptr [rax-68h], 3
0x180028c07  lea     r8d, [rbx+5]; dwShareMode
0x180028c0b  call    cs:__imp_CreateFileW
0x180028c11  mov     rdi, rax
0x180028c14  test    rax, rax
0x180028c17  jz      loc_180028CAD
0x180028c1d  xor     edx, edx; Val
0x180028c1f  mov     [rsp+88h+SectionHandle], rbx
0x180028c27  lea     r8d, [rbx+40h]; Size
0x180028c2b  lea     rcx, [rsp+88h+SectionInformation]; void *
0x180028c30  call    memset_0
0x180028c35  mov     [rsp+88h+FileHandle], rdi; FileHandle
0x180028c3a  lea     rcx, [rsp+88h+SectionHandle]; SectionHandle
0x180028c42  mov     [rsp+88h+AllocationAttributes], 1000000h; AllocationAttributes
0x180028c4a  xor     r9d, r9d; MaximumSize
0x180028c4d  xor     r8d, r8d; ObjectAttributes
0x180028c50  mov     [rsp+88h+SectionPageProtection], 10h; SectionPageProtection
0x180028c58  mov     edx, 0F001Fh; DesiredAccess
0x180028c5d  call    cs:__imp_NtCreateSection
0x180028c63  test    eax, eax
0x180028c65  js      short loc_180028CA4
0x180028c67  mov     rcx, [rsp+88h+SectionHandle]; SectionHandle
0x180028c6f  lea     r9d, [rbx+40h]; Length
0x180028c73  lea     r8, [rsp+88h+SectionInformation]; SectionInformation
0x180028c78  mov     qword ptr [rsp+88h+SectionPageProtection], rbx; ResultLength
0x180028c7d  lea     edx, [rbx+1]; SectionInformationClass
0x180028c80  call    cs:__imp_NtQuerySection
0x180028c86  mov     eax, 8664h
0x180028c8b  lea     ecx, [rbx+6]
0x180028c8e  cmp     [rsp+88h+var_18], ax
0x180028c93  cmovz   ebx, ecx
0x180028c96  mov     rcx, [rsp+88h+SectionHandle]; hObject
0x180028c9e  call    cs:__imp_CloseHandle
0x180028ca4  mov     rcx, rdi; hObject
0x180028ca7  call    cs:__imp_CloseHandle
0x180028cad  mov     eax, ebx
0x180028caf  mov     rbx, [rsp+88h+arg_0]
0x180028cb7  add     rsp, 80h
0x180028cbe  pop     rdi
0x180028cbf  retn
```
