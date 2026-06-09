# FwIsIntegrityEnforced(ushort const *,int *)

- ea: `0x1800ab580`
- end: `0x1800ab7ac`
- name: `?FwIsIntegrityEnforced@@YAJPEBGPEAH@Z`
- size: `556`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800ab7b4`

## callees

- `0x18000a710`
- `0x1800ab580`
- `0x1800abc44`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab5ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab654`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab6c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab717`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab5ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab654`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab6c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab717`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ab5b3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ab5b3`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800ab640`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800ab640`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800ab6b0`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800ab6b0`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800ab774`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800ab774`
- `fwbase!FwCloseHandle` at `0x1800ab783`
- `fwbase!FwCloseHandle` at `0x1800ab792`
- `fwbase!FwCloseHandle` at `0x1800ab783`
- `fwbase!FwCloseHandle` at `0x1800ab792`

## pseudocode

```c
__int64 __fastcall FwIsIntegrityEnforced(const unsigned __int16 *a1, int *a2)
{
  HANDLE FileW; // rax
  HANDLE v4; // rbp
  HANDLE v5; // rsi
  signed int LastError; // eax
  unsigned int v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // rdx
  HANDLE FileMappingW; // rax
  signed int v11; // eax
  const void *v12; // rax
  const void *v13; // rdi
  signed int v14; // eax
  __int64 v15; // rax
  signed int v16; // eax

  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
  v4 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v5 = 0;
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    v8 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v9 = 31;
LABEL_7:
      WPP_SF_d(*(_QWORD *)(v8 + 16), v9, WPP_8b2bb7d61c06371ab4f9e7ad4a862a27_Traceguids, v7);
    }
  }
  else
  {
    FileMappingW = CreateFileMappingW(FileW, 0, 2u, 0, 0, 0);
    v5 = FileMappingW;
    if ( FileMappingW )
    {
      v12 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
      v13 = v12;
      if ( v12 )
      {
        v15 = RtlpImageNtHeader(v12);
        if ( v15 )
        {
          v7 = 0;
          *a2 = *(unsigned __int8 *)(v15 + 94) >> 7;
        }
        else
        {
          v16 = GetLastError();
          v7 = v16;
          if ( v16 > 0 )
            v7 = (unsigned __int16)v16 | 0x80070000;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 34, WPP_8b2bb7d61c06371ab4f9e7ad4a862a27_Traceguids, v7);
        }
        UnmapViewOfFile(v13);
      }
      else
      {
        v14 = GetLastError();
        v7 = v14;
        if ( v14 > 0 )
          v7 = (unsigned __int16)v14 | 0x80070000;
        v8 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v9 = 33;
          goto LABEL_7;
        }
      }
    }
    else
    {
      v11 = GetLastError();
      v7 = v11;
      if ( v11 > 0 )
        v7 = (unsigned __int16)v11 | 0x80070000;
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v9 = 32;
        goto LABEL_7;
      }
    }
  }
  FwCloseHandle(v5);
  FwCloseHandle(v4);
  return v7;
}

```

## disassembly

```asm
0x1800ab580  push    rbx
0x1800ab582  push    rbp
0x1800ab583  push    rsi
0x1800ab584  push    rdi
0x1800ab585  push    r14
0x1800ab587  sub     rsp, 40h
0x1800ab58b  xor     r9d, r9d; lpSecurityAttributes
0x1800ab58e  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x1800ab597  mov     r14, rdx
0x1800ab59a  mov     [rsp+68h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x1800ab5a2  mov     edx, 80000000h; dwDesiredAccess
0x1800ab5a7  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x1800ab5af  lea     r8d, [r9+1]; dwShareMode
0x1800ab5b3  call    cs:__imp_CreateFileW
0x1800ab5ba  nop     dword ptr [rax+rax+00h]
0x1800ab5bf  mov     rbp, rax
0x1800ab5c2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800ab5c6  jnz     short loc_1800AB623
0x1800ab5c8  xor     esi, esi
0x1800ab5ca  call    cs:__imp_GetLastError
0x1800ab5d1  nop     dword ptr [rax+rax+00h]
0x1800ab5d6  mov     ebx, eax
0x1800ab5d8  test    eax, eax
0x1800ab5da  jle     short loc_1800AB5E5
0x1800ab5dc  movzx   ebx, ax
0x1800ab5df  or      ebx, 80070000h
0x1800ab5e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab5ec  lea     rax, WPP_GLOBAL_Control
0x1800ab5f3  cmp     rcx, rax
0x1800ab5f6  jz      loc_1800AB780
0x1800ab5fc  test    byte ptr [rcx+1Ch], 1
0x1800ab600  jz      loc_1800AB780
0x1800ab606  mov     edx, 1Fh
0x1800ab60b  mov     rcx, [rcx+10h]
0x1800ab60f  lea     r8, WPP_8b2bb7d61c06371ab4f9e7ad4a862a27_Traceguids
0x1800ab616  mov     r9d, ebx
0x1800ab619  call    WPP_SF_d
0x1800ab61e  jmp     loc_1800AB780
0x1800ab623  xor     r9d, r9d; dwMaximumSizeHigh
0x1800ab626  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], 0; lpName
0x1800ab62f  xor     edx, edx; lpFileMappingAttributes
0x1800ab631  mov     [rsp+68h+dwCreationDisposition], 0; dwMaximumSizeLow
0x1800ab639  mov     rcx, rbp; hFile
0x1800ab63c  lea     r8d, [r9+2]; flProtect
0x1800ab640  call    cs:__imp_CreateFileMappingW
0x1800ab647  nop     dword ptr [rax+rax+00h]
0x1800ab64c  mov     rsi, rax
0x1800ab64f  test    rax, rax
0x1800ab652  jnz     short loc_1800AB69A
0x1800ab654  call    cs:__imp_GetLastError
0x1800ab65b  nop     dword ptr [rax+rax+00h]
0x1800ab660  mov     ebx, eax
0x1800ab662  test    eax, eax
0x1800ab664  jle     short loc_1800AB66F
0x1800ab666  movzx   ebx, ax
0x1800ab669  or      ebx, 80070000h
0x1800ab66f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab676  lea     rax, WPP_GLOBAL_Control
0x1800ab67d  cmp     rcx, rax
0x1800ab680  jz      loc_1800AB780
0x1800ab686  test    byte ptr [rcx+1Ch], 1
0x1800ab68a  jz      loc_1800AB780
0x1800ab690  mov     edx, 20h ; ' '
0x1800ab695  jmp     loc_1800AB60B
0x1800ab69a  xor     r9d, r9d; dwFileOffsetLow
0x1800ab69d  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x1800ab6a6  xor     r8d, r8d; dwFileOffsetHigh
0x1800ab6a9  mov     rcx, rax; hFileMappingObject
0x1800ab6ac  lea     edx, [r9+4]; dwDesiredAccess
0x1800ab6b0  call    cs:__imp_MapViewOfFile
0x1800ab6b7  nop     dword ptr [rax+rax+00h]
0x1800ab6bc  mov     rdi, rax
0x1800ab6bf  test    rax, rax
0x1800ab6c2  jnz     short loc_1800AB70A
0x1800ab6c4  call    cs:__imp_GetLastError
0x1800ab6cb  nop     dword ptr [rax+rax+00h]
0x1800ab6d0  mov     ebx, eax
0x1800ab6d2  test    eax, eax
0x1800ab6d4  jle     short loc_1800AB6DF
0x1800ab6d6  movzx   ebx, ax
0x1800ab6d9  or      ebx, 80070000h
0x1800ab6df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab6e6  lea     rax, WPP_GLOBAL_Control
0x1800ab6ed  cmp     rcx, rax
0x1800ab6f0  jz      loc_1800AB780
0x1800ab6f6  test    byte ptr [rcx+1Ch], 1
0x1800ab6fa  jz      loc_1800AB780
0x1800ab700  mov     edx, 21h ; '!'
0x1800ab705  jmp     loc_1800AB60B
0x1800ab70a  mov     rcx, rdi
0x1800ab70d  call    RtlpImageNtHeader
0x1800ab712  test    rax, rax
0x1800ab715  jnz     short loc_1800AB765
0x1800ab717  call    cs:__imp_GetLastError
0x1800ab71e  nop     dword ptr [rax+rax+00h]
0x1800ab723  mov     ebx, eax
0x1800ab725  test    eax, eax
0x1800ab727  jle     short loc_1800AB732
0x1800ab729  movzx   ebx, ax
0x1800ab72c  or      ebx, 80070000h
0x1800ab732  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ab739  lea     rax, WPP_GLOBAL_Control
0x1800ab740  cmp     rcx, rax
0x1800ab743  jz      short loc_1800AB771
0x1800ab745  test    byte ptr [rcx+1Ch], 1
0x1800ab749  jz      short loc_1800AB771
0x1800ab74b  mov     rcx, [rcx+10h]
0x1800ab74f  lea     r8, WPP_8b2bb7d61c06371ab4f9e7ad4a862a27_Traceguids
0x1800ab756  mov     edx, 22h ; '"'
0x1800ab75b  mov     r9d, ebx
0x1800ab75e  call    WPP_SF_d
0x1800ab763  jmp     short loc_1800AB771
0x1800ab765  movzx   ecx, byte ptr [rax+5Eh]
0x1800ab769  xor     ebx, ebx
0x1800ab76b  shr     ecx, 7
0x1800ab76e  mov     [r14], ecx
0x1800ab771  mov     rcx, rdi; lpBaseAddress
0x1800ab774  call    cs:__imp_UnmapViewOfFile
0x1800ab77b  nop     dword ptr [rax+rax+00h]
0x1800ab780  mov     rcx, rsi
0x1800ab783  call    cs:__imp_FwCloseHandle
0x1800ab78a  nop     dword ptr [rax+rax+00h]
0x1800ab78f  mov     rcx, rbp
0x1800ab792  call    cs:__imp_FwCloseHandle
0x1800ab799  nop     dword ptr [rax+rax+00h]
0x1800ab79e  mov     eax, ebx
0x1800ab7a0  add     rsp, 40h
0x1800ab7a4  pop     r14
0x1800ab7a6  pop     rdi
0x1800ab7a7  pop     rsi
0x1800ab7a8  pop     rbp
0x1800ab7a9  pop     rbx
0x1800ab7aa  retn
```
