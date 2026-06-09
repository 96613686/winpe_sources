# CSimpStorage::Init(ushort const *,void *)

- ea: `0x18004e8c0`
- end: `0x18004e969`
- name: `?Init@CSimpStorage@@QEAAJPEBGPEAX@Z`
- size: `169`
- prototype: `int(CSimpStorage *__hidden this, const unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18004e6e0`

## callees

- `0x180026bc4`
- `0x18004e8c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e922`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e922`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004e912`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004e912`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18004e937`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18004e937`

## pseudocode

```c
__int64 __fastcall CSimpStorage::Init(CSimpStorage *this, const unsigned __int16 *a2, void *a3)
{
  HANDLE FileW; // rax
  DWORD LastError; // eax
  __int64 result; // rax
  _QWORD v7[5]; // [rsp+40h] [rbp-28h] BYREF

  v7[1] = a3;
  v7[0] = 24;
  v7[2] = 0;
  FileW = CreateFileW(
            a2,
            0xC0000000,
            0,
            (LPSECURITY_ATTRIBUTES)((unsigned __int64)v7 & -(__int64)(a3 != 0)),
            4u,
            0x80u,
            0);
  *((_QWORD *)this + 8) = FileW;
  if ( FileW == (HANDLE)-1LL || !SetEndOfFile(FileW) )
  {
    LastError = GetLastError();
    return Win32ErrorToScode(LastError);
  }
  else
  {
    *((_DWORD *)this + 150) = 0;
    result = 0;
    *((_DWORD *)this + 18) = 1;
    *(GUID *)((char *)this + 604) = GUID_NULL;
  }
  return result;
}

```

## disassembly

```asm
0x18004e8c0  mov     r11, rsp
0x18004e8c3  push    rbx
0x18004e8c4  sub     rsp, 60h
0x18004e8c8  mov     [r11-20h], r8
0x18004e8cc  mov     rbx, rcx
0x18004e8cf  neg     r8
0x18004e8d2  mov     qword ptr [r11-38h], 0
0x18004e8da  lea     rcx, [r11-28h]
0x18004e8de  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18004e8e6  sbb     r9, r9
0x18004e8e9  mov     qword ptr [r11-28h], 18h
0x18004e8f1  mov     rax, rdx
0x18004e8f4  mov     qword ptr [r11-18h], 0
0x18004e8fc  and     r9, rcx; lpSecurityAttributes
0x18004e8ff  mov     [rsp+68h+dwCreationDisposition], 4; dwCreationDisposition
0x18004e907  mov     rcx, rax; lpFileName
0x18004e90a  xor     r8d, r8d; dwShareMode
0x18004e90d  mov     edx, 0C0000000h; dwDesiredAccess
0x18004e912  call    cs:__imp_CreateFileW
0x18004e918  mov     [rbx+40h], rax
0x18004e91c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004e920  jnz     short loc_18004E934
0x18004e922  call    cs:__imp_GetLastError
0x18004e928  mov     ecx, eax; unsigned int
0x18004e92a  add     rsp, 60h
0x18004e92e  pop     rbx
0x18004e92f  jmp     ?Win32ErrorToScode@@YAJK@Z; Win32ErrorToScode(ulong)
0x18004e934  mov     rcx, rax; hFile
0x18004e937  call    cs:__imp_SetEndOfFile
0x18004e93d  test    eax, eax
0x18004e93f  jz      short loc_18004E922
0x18004e941  mov     dword ptr [rbx+258h], 0
0x18004e94b  xor     eax, eax
0x18004e94d  mov     dword ptr [rbx+48h], 1
0x18004e954  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004e95b  movdqu  xmmword ptr [rbx+25Ch], xmm0
0x18004e963  add     rsp, 60h
0x18004e967  pop     rbx
0x18004e968  retn
```
