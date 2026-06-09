# FILE_LISTENER::OpenFile(void * *)

- ea: `0x1800045e0`
- end: `0x1800046b9`
- name: `?OpenFile@FILE_LISTENER@@QEAAJPEAPEAX@Z`
- size: `217`
- prototype: `__int64 __fastcall(FILE_LISTENER *__hidden this, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000401c`
- `0x180007b00`

## callees

- `0x1800045e0`
- `0x18000ee10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004664`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004664`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180004686`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180004686`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004651`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004651`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180004620`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180004620`

## pseudocode

```c
signed int __fastcall FILE_LISTENER::OpenFile(LPCWSTR *this, void **a2)
{
  int v4; // ebx
  DWORD v5; // esi
  HANDLE FileW; // rax
  signed int result; // eax
  __int128 FileInformation; // [rsp+40h] [rbp-48h] BYREF
  __int128 v9; // [rsp+50h] [rbp-38h]
  int v10; // [rsp+60h] [rbp-28h]

  v10 = 0;
  v4 = 0;
  FileInformation = 0;
  v5 = 50;
  v9 = 0;
  while ( 1 )
  {
    if ( v4 )
    {
      Sleep(v5);
      v5 *= 2;
    }
    FileW = CreateFileW(this[6], 0x80000000, 1u, 0, 3u, 0x80u, 0);
    if ( FileW != (HANDLE)-1LL )
      break;
    if ( (unsigned int)++v4 >= 5 )
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
  }
  *a2 = FileW;
  if ( GetFileAttributesExW(this[6], GetFileExInfoStandard, &FileInformation) )
    this[9] = *(LPCWSTR *)((char *)&v9 + 4);
  return 0;
}

```

## disassembly

```asm
0x1800045e0  mov     [rsp+arg_10], rbx
0x1800045e5  push    rsi
0x1800045e6  push    rdi
0x1800045e7  push    r14
0x1800045e9  sub     rsp, 70h
0x1800045ed  mov     rax, cs:__security_cookie
0x1800045f4  xor     rax, rsp
0x1800045f7  mov     [rsp+88h+var_20], rax
0x1800045fc  xor     eax, eax
0x1800045fe  xorps   xmm0, xmm0
0x180004601  mov     r14, rdx
0x180004604  mov     [rsp+88h+var_28], eax
0x180004608  mov     rdi, rcx
0x18000460b  xor     ebx, ebx
0x18000460d  movups  [rsp+88h+FileInformation], xmm0
0x180004612  lea     esi, [rax+32h]
0x180004615  movups  [rsp+88h+var_38], xmm0
0x18000461a  test    ebx, ebx
0x18000461c  jz      short loc_180004628
0x18000461e  mov     ecx, esi; dwMilliseconds
0x180004620  call    cs:__imp_Sleep
0x180004626  add     esi, esi
0x180004628  mov     rcx, [rdi+30h]; lpFileName
0x18000462c  xor     r9d, r9d; lpSecurityAttributes
0x18000462f  mov     [rsp+88h+hTemplateFile], 0; hTemplateFile
0x180004638  mov     edx, 80000000h; dwDesiredAccess
0x18000463d  mov     [rsp+88h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180004645  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x18000464d  lea     r8d, [r9+1]; dwShareMode
0x180004651  call    cs:__imp_CreateFileW
0x180004657  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000465b  jnz     short loc_180004678
0x18000465d  inc     ebx
0x18000465f  cmp     ebx, 5
0x180004662  jb      short loc_18000461A
0x180004664  call    cs:__imp_GetLastError
0x18000466a  test    eax, eax
0x18000466c  jle     short loc_18000469B
0x18000466e  movzx   eax, ax
0x180004671  or      eax, 80070000h
0x180004676  jmp     short loc_18000469B
0x180004678  mov     [r14], rax
0x18000467b  lea     r8, [rsp+88h+FileInformation]; lpFileInformation
0x180004680  mov     rcx, [rdi+30h]; lpFileName
0x180004684  xor     edx, edx; fInfoLevelId
0x180004686  call    cs:__imp_GetFileAttributesExW
0x18000468c  test    eax, eax
0x18000468e  jz      short loc_180004699
0x180004690  mov     rax, qword ptr [rsp+88h+var_38+4]
0x180004695  mov     [rdi+48h], rax
0x180004699  xor     eax, eax
0x18000469b  mov     rcx, [rsp+88h+var_20]
0x1800046a0  xor     rcx, rsp; StackCookie
0x1800046a3  call    __security_check_cookie
0x1800046a8  mov     rbx, [rsp+88h+arg_10]
0x1800046b0  add     rsp, 70h
0x1800046b4  pop     r14
0x1800046b6  pop     rdi
0x1800046b7  pop     rsi
0x1800046b8  retn
```
