# ReadImageIndexInfo(ushort const *,SYMSRV_INDEX_INFOW *)

- ea: `0x1800193fc`
- end: `0x180019478`
- name: `?ReadImageIndexInfo@@YAHPEBGPEAUSYMSRV_INDEX_INFOW@@@Z`
- size: `124`
- prototype: `int(const unsigned __int16 *, struct SYMSRV_INDEX_INFOW *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180019280`
- `0x1801addb0`

## callees

- `0x1800193fc`
- `0x180019480`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001942d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001942d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001945e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001945e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001944f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001944f`

## pseudocode

```c
__int64 __fastcall ReadImageIndexInfo(const unsigned __int16 *a1, struct SYMSRV_INDEX_INFOW *a2)
{
  char *FileW; // rdi
  int ImageDebugInfo; // ebx

  FileW = (char *)CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0, 0);
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    return 0;
  ImageDebugInfo = GetImageDebugInfo(FileW, a2);
  CloseHandle(FileW);
  if ( !ImageDebugInfo )
  {
    SetLastError(0xC1u);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1800193fc  mov     rax, rsp
0x1800193ff  mov     [rax+8], rbx
0x180019403  push    rdi
0x180019404  sub     rsp, 40h
0x180019408  mov     qword ptr [rax-18h], 0
0x180019410  xor     r9d, r9d; lpSecurityAttributes
0x180019413  mov     rbx, rdx
0x180019416  mov     dword ptr [rax-20h], 0
0x18001941d  mov     edx, 80000000h; dwDesiredAccess
0x180019422  mov     dword ptr [rax-28h], 3
0x180019429  lea     r8d, [r9+1]; dwShareMode
0x18001942d  call    cs:__imp_CreateFileW
0x180019433  mov     rdi, rax
0x180019436  dec     rax
0x180019439  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001943d  ja      short loc_180019464
0x18001943f  mov     rdx, rbx; struct SYMSRV_INDEX_INFOW *
0x180019442  mov     rcx, rdi; void *
0x180019445  call    ?GetImageDebugInfo@@YAHPEAXPEAUSYMSRV_INDEX_INFOW@@@Z; GetImageDebugInfo(void *,SYMSRV_INDEX_INFOW *)
0x18001944a  mov     rcx, rdi; hObject
0x18001944d  mov     ebx, eax
0x18001944f  call    cs:__imp_CloseHandle
0x180019455  test    ebx, ebx
0x180019457  jnz     short loc_180019471
0x180019459  mov     ecx, 0C1h; dwErrCode
0x18001945e  call    cs:__imp_SetLastError
0x180019464  xor     eax, eax
0x180019466  mov     rbx, [rsp+48h+arg_0]
0x18001946b  add     rsp, 40h
0x18001946f  pop     rdi
0x180019470  retn
0x180019471  mov     eax, 1
0x180019476  jmp     short loc_180019466
```
