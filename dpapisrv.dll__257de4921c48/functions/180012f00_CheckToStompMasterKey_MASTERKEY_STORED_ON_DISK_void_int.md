# CheckToStompMasterKey(MASTERKEY_STORED_ON_DISK *,void *,int *)

- ea: `0x180012f00`
- end: `0x180013085`
- name: `?CheckToStompMasterKey@@YAHPEAUMASTERKEY_STORED_ON_DISK@@PEAXPEAH@Z`
- size: `389`
- prototype: `__int64 __fastcall(struct MASTERKEY_STORED_ON_DISK *, void *, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003908`

## callees

- `0x180012f00`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013058`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013058`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180012fbe`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180012fbe`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x180012fe5`
- `api-ms-win-core-memory-l1-1-0!VirtualQuery` at `0x180012fe5`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180012f8b`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180012f8b`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180013044`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180013044`

## pseudocode

```c
__int64 __fastcall CheckToStompMasterKey(struct MASTERKEY_STORED_ON_DISK *a1, void *a2, int *a3)
{
  _DWORD *v5; // rdi
  unsigned int v6; // esi
  HANDLE FileMappingW; // rax
  void *v8; // r14
  _DWORD *v9; // rax
  _MEMORY_BASIC_INFORMATION Buffer; // [rsp+40h] [rbp-48h] BYREF

  memset(&Buffer, 0, sizeof(Buffer));
  *a3 = 1;
  if ( (*((_BYTE *)a1 + 92) & 2) != 0 || (*((_BYTE *)a1 + 92) & 1) != 0 && *((_DWORD *)a1 + 28) )
    return 1;
  v5 = 0;
  v6 = 0;
  if ( *((_DWORD *)a1 + 30) )
    return 1;
  FileMappingW = CreateFileMappingW(a2, 0, 2u, 0, 0x80u, 0);
  v8 = FileMappingW;
  if ( FileMappingW )
  {
    v9 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0x80u);
    v5 = v9;
    if ( v9 )
    {
      if ( VirtualQuery(v9, &Buffer, 0x30u) >= 0x30 && Buffer.RegionSize >= 0x80 && *v5 <= 2u )
      {
        if ( !*((_DWORD *)a1 + 28) && (v5[28] || v5[30]) )
          *a3 = 0;
        v6 = 1;
      }
    }
  }
  if ( v5 )
    UnmapViewOfFile(v5);
  if ( v8 )
    CloseHandle(v8);
  return v6;
}

```

## disassembly

```asm
0x180012f00  mov     [rsp+arg_8], rsi
0x180012f05  mov     [rsp+arg_10], rdi
0x180012f0a  push    r12
0x180012f0c  push    r14
0x180012f0e  push    r15
0x180012f10  sub     rsp, 70h
0x180012f14  mov     r12, r8
0x180012f17  mov     rax, rdx
0x180012f1a  mov     r15, rcx
0x180012f1d  xorps   xmm0, xmm0
0x180012f20  movups  xmmword ptr [rsp+88h+Buffer.BaseAddress], xmm0
0x180012f25  movups  xmmword ptr [rsp+88h+Buffer.AllocationProtect], xmm0
0x180012f2a  movups  xmmword ptr [rsp+88h+Buffer.State], xmm0
0x180012f2f  mov     dword ptr [r8], 1
0x180012f36  test    byte ptr [rcx+5Ch], 2
0x180012f3a  jnz     loc_180013068
0x180012f40  test    byte ptr [rcx+5Ch], 1
0x180012f44  jz      short loc_180012F50
0x180012f46  cmp     dword ptr [rcx+70h], 0
0x180012f4a  jnz     loc_180013068
0x180012f50  mov     [rsp+88h+var_58], 0
0x180012f59  xor     edi, edi
0x180012f5b  mov     [rsp+88h+var_50], rdi
0x180012f60  xor     esi, esi
0x180012f62  mov     [rsp+88h+arg_0], esi
0x180012f69  cmp     [rcx+78h], esi
0x180012f6c  jnz     loc_180013068
0x180012f72  mov     [rsp+88h+lpName], rsi; lpName
0x180012f77  mov     [rsp+88h+dwMaximumSizeLow], 80h; dwMaximumSizeLow
0x180012f7f  xor     r9d, r9d; dwMaximumSizeHigh
0x180012f82  xor     edx, edx; lpFileMappingAttributes
0x180012f84  lea     r8d, [rdi+2]; flProtect
0x180012f88  mov     rcx, rax; hFile
0x180012f8b  call    cs:__imp_CreateFileMappingW
0x180012f92  nop     dword ptr [rax+rax+00h]
0x180012f97  mov     r14, rax
0x180012f9a  mov     [rsp+88h+var_58], rax
0x180012f9f  test    rax, rax
0x180012fa2  jz      loc_18001303C
0x180012fa8  mov     qword ptr [rsp+88h+dwMaximumSizeLow], 80h; dwNumberOfBytesToMap
0x180012fb1  xor     r9d, r9d; dwFileOffsetLow
0x180012fb4  xor     r8d, r8d; dwFileOffsetHigh
0x180012fb7  lea     edx, [r9+4]; dwDesiredAccess
0x180012fbb  mov     rcx, rax; hFileMappingObject
0x180012fbe  call    cs:__imp_MapViewOfFile
0x180012fc5  nop     dword ptr [rax+rax+00h]
0x180012fca  mov     rdi, rax
0x180012fcd  mov     [rsp+88h+var_50], rax
0x180012fd2  test    rax, rax
0x180012fd5  jz      short loc_18001303C
0x180012fd7  mov     r8d, 30h ; '0'; dwLength
0x180012fdd  lea     rdx, [rsp+88h+Buffer]; lpBuffer
0x180012fe2  mov     rcx, rdi; lpAddress
0x180012fe5  call    cs:__imp_VirtualQuery
0x180012fec  nop     dword ptr [rax+rax+00h]
0x180012ff1  cmp     rax, 30h ; '0'
0x180012ff5  jb      short loc_180013029
0x180012ff7  cmp     [rsp+88h+Buffer.RegionSize], 80h
0x180013000  jb      short loc_180013029
0x180013002  cmp     dword ptr [rdi], 2
0x180013005  ja      short loc_18001303C
0x180013007  cmp     dword ptr [r15+70h], 0
0x18001300c  jnz     short loc_180013022
0x18001300e  cmp     dword ptr [rdi+70h], 0
0x180013012  jnz     short loc_18001301A
0x180013014  cmp     dword ptr [rdi+78h], 0
0x180013018  jz      short loc_180013022
0x18001301a  mov     dword ptr [r12], 0
0x180013022  mov     esi, 1
0x180013027  jmp     short loc_18001303C
0x180013029  jmp     short loc_18001303C
0x18001302b  mov     r14, [rsp+88h+var_58]
0x180013030  mov     rdi, [rsp+88h+var_50]
0x180013035  mov     esi, [rsp+88h+arg_0]
0x18001303c  test    rdi, rdi
0x18001303f  jz      short loc_180013050
0x180013041  mov     rcx, rdi; lpBaseAddress
0x180013044  call    cs:__imp_UnmapViewOfFile
0x18001304b  nop     dword ptr [rax+rax+00h]
0x180013050  test    r14, r14
0x180013053  jz      short loc_180013064
0x180013055  mov     rcx, r14; hObject
0x180013058  call    cs:__imp_CloseHandle
0x18001305f  nop     dword ptr [rax+rax+00h]
0x180013064  mov     eax, esi
0x180013066  jmp     short loc_18001306D
0x180013068  mov     eax, 1
0x18001306d  lea     r11, [rsp+88h+var_18]
0x180013072  mov     rsi, [r11+28h]
0x180013076  mov     rdi, [r11+30h]
0x18001307a  mov     rsp, r11
0x18001307d  pop     r15
0x18001307f  pop     r14
0x180013081  pop     r12
0x180013083  retn
```
