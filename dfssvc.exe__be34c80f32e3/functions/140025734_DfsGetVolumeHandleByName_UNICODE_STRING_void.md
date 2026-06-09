# DfsGetVolumeHandleByName(_UNICODE_STRING *,void * *)

- ea: `0x140025734`
- end: `0x1400257de`
- name: `?DfsGetVolumeHandleByName@@YAKPEAU_UNICODE_STRING@@PEAPEAX@Z`
- size: `170`
- prototype: `unsigned int __fastcall(struct _UNICODE_STRING *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path`

## callers

- `0x140026018`

## callees

- `0x1400011c4`
- `0x1400011d0`
- `0x140025734`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400257b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400257b5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400257a6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400257a6`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x140025771`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x140025771`

## pseudocode

```c
__int64 __fastcall DfsGetVolumeHandleByName(struct _UNICODE_STRING *a1, void **a2)
{
  WCHAR *v4; // rax
  WCHAR *v5; // rdi
  DWORD LastError; // ebx

  *a2 = (void *)-1LL;
  v4 = (WCHAR *)operator new(0x208u);
  v5 = v4;
  if ( !v4 )
    return 8;
  if ( GetVolumeNameForVolumeMountPointW(a1->Buffer, v4, 0x104u) )
    *a2 = CreateFileW(v5, 0x80000000, 1u, 0, 3u, 0x2020000u, 0);
  LastError = GetLastError();
  operator delete(v5);
  return LastError;
}

```

## disassembly

```asm
0x140025734  mov     [rsp+arg_0], rbx
0x140025739  mov     [rsp+arg_8], rsi
0x14002573e  push    rdi
0x14002573f  sub     rsp, 40h
0x140025743  or      qword ptr [rdx], 0FFFFFFFFFFFFFFFFh
0x140025747  mov     rsi, rcx
0x14002574a  mov     ecx, 208h; Size
0x14002574f  mov     rbx, rdx
0x140025752  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140025757  mov     rdi, rax
0x14002575a  test    rax, rax
0x14002575d  jnz     short loc_140025764
0x14002575f  lea     eax, [rdi+8]
0x140025762  jmp     short loc_1400257CD
0x140025764  mov     rcx, [rsi+8]; lpszVolumeMountPoint
0x140025768  mov     r8d, 104h; cchBufferLength
0x14002576e  mov     rdx, rdi; lpszVolumeName
0x140025771  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x140025778  nop     dword ptr [rax+rax+00h]
0x14002577d  test    eax, eax
0x14002577f  jz      short loc_1400257B5
0x140025781  and     [rsp+48h+var_18], 0
0x140025787  xor     r9d, r9d; lpSecurityAttributes
0x14002578a  mov     [rsp+48h+dwFlagsAndAttributes], 2020000h; dwFlagsAndAttributes
0x140025792  mov     edx, 80000000h; dwDesiredAccess
0x140025797  mov     rcx, rdi; lpFileName
0x14002579a  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x1400257a2  lea     r8d, [r9+1]; dwShareMode
0x1400257a6  call    cs:__imp_CreateFileW
0x1400257ad  nop     dword ptr [rax+rax+00h]
0x1400257b2  mov     [rbx], rax
0x1400257b5  call    cs:__imp_GetLastError
0x1400257bc  nop     dword ptr [rax+rax+00h]
0x1400257c1  mov     rcx, rdi; Block
0x1400257c4  mov     ebx, eax
0x1400257c6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400257cb  mov     eax, ebx
0x1400257cd  mov     rbx, [rsp+48h+arg_0]
0x1400257d2  mov     rsi, [rsp+48h+arg_8]
0x1400257d7  add     rsp, 40h
0x1400257db  pop     rdi
0x1400257dc  retn
```
