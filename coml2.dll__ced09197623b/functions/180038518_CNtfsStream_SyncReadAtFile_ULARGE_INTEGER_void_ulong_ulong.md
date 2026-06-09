# CNtfsStream::SyncReadAtFile(_ULARGE_INTEGER,void *,ulong,ulong *)

- ea: `0x180038518`
- end: `0x180038580`
- name: `?SyncReadAtFile@CNtfsStream@@AEAAJT_ULARGE_INTEGER@@PEAXKPEAK@Z`
- size: `104`
- prototype: `int(CNtfsStream *__hidden this, union _ULARGE_INTEGER, void *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180038380`
- `0x1800582a0`

## callees

- `0x180038518`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038558`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038558`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003854e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003854e`

## pseudocode

```c
__int64 __fastcall CNtfsStream::SyncReadAtFile(
        CNtfsStream *this,
        union _ULARGE_INTEGER a2,
        void *a3,
        DWORD a4,
        unsigned int *lpNumberOfBytesRead)
{
  unsigned int v5; // ebx
  signed int LastError; // eax

  *((union _ULARGE_INTEGER *)this + 21) = a2;
  v5 = 0;
  if ( !ReadFile(*((HANDLE *)this + 12), a3, a4, lpNumberOfBytesRead, (LPOVERLAPPED)((char *)this + 152)) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError != 38 )
      {
        if ( LastError > 0 )
          return (unsigned __int16)LastError | 0x80070000;
        else
          return (unsigned int)LastError;
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180038518  push    rbx
0x18003851a  sub     rsp, 30h
0x18003851e  lea     rax, [rcx+98h]
0x180038525  mov     r10d, r9d
0x180038528  mov     r9, [rsp+38h+lpNumberOfBytesRead]; lpNumberOfBytesRead
0x18003852d  mov     r11, r8
0x180038530  mov     [rax+10h], edx
0x180038533  mov     r8d, r10d; nNumberOfBytesToRead
0x180038536  shr     rdx, 20h
0x18003853a  xor     ebx, ebx
0x18003853c  mov     [rcx+0ACh], edx
0x180038542  mov     rdx, r11; lpBuffer
0x180038545  mov     rcx, [rcx+60h]; hFile
0x180038549  mov     [rsp+38h+lpOverlapped], rax; lpOverlapped
0x18003854e  call    cs:__imp_ReadFile
0x180038554  test    eax, eax
0x180038556  jnz     short loc_180038578
0x180038558  call    cs:__imp_GetLastError
0x18003855e  test    eax, eax
0x180038560  jz      short loc_180038578
0x180038562  cmp     eax, 26h ; '&'
0x180038565  jz      short loc_180038578
0x180038567  test    eax, eax
0x180038569  jg      short loc_18003856F
0x18003856b  mov     ebx, eax
0x18003856d  jmp     short loc_180038578
0x18003856f  movzx   ebx, ax
0x180038572  or      ebx, 80070000h
0x180038578  mov     eax, ebx
0x18003857a  add     rsp, 30h
0x18003857e  pop     rbx
0x18003857f  retn
```
