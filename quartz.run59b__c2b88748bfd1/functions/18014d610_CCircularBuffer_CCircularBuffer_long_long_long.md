# CCircularBuffer::CCircularBuffer(long,long,long &)

- ea: `0x18014d610`
- end: `0x18014d7a0`
- name: `??0CCircularBuffer@@QEAA@JJAEAJ@Z`
- size: `400`
- prototype: `CCircularBuffer *__fastcall(CCircularBuffer *__hidden this, int, int, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800e9c60`
- `0x18014dcf0`

## callees

- `0x18002e740`
- `0x18014d610`
- `0x18014d884`

## import_xrefs

- `KERNEL32!CreateFileMappingW` at `0x18014d735`
- `KERNEL32!CreateFileMappingW` at `0x18014d735`
- `KERNEL32!CloseHandle` at `0x18014d77b`
- `KERNEL32!CloseHandle` at `0x18014d77b`
- `KERNEL32!GetLastError` at `0x18014d749`
- `KERNEL32!GetLastError` at `0x18014d749`
- `KERNEL32!CreateFileW` at `0x18014d69a`
- `KERNEL32!CreateFileW` at `0x18014d69a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18014d701`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18014d701`

## pseudocode

```c
CCircularBuffer *__fastcall CCircularBuffer::CCircularBuffer(CCircularBuffer *this, int a2, int a3, DWORD *a4)
{
  HANDLE FileW; // rcx
  HANDLE FileMappingW; // rbp
  int i; // esi
  int Mappings; // eax
  DWORD BytesReturned; // [rsp+68h] [rbp+10h] BYREF
  int InBuffer; // [rsp+70h] [rbp+18h] BYREF

  *(_QWORD *)this = 0;
  *((_DWORD *)this + 2) = a2;
  *((_DWORD *)this + 3) = a3;
  if ( a2 && a3 && a3 <= a2 && (((unsigned int)CCircularBuffer::AlignmentRequired() - 1) & a2) == 0 )
  {
    FileW = hVxD;
    if ( hVxD == (HANDLE)-1LL )
      goto LABEL_11;
    if ( !hVxD )
    {
      FileW = CreateFileW(L"\\\\.\\QUARTZ.VXD", 0x40000000u, 2u, 0, 4u, 0x80u, 0);
      hVxD = FileW;
    }
    if ( FileW == (HANDLE)-1LL )
    {
LABEL_11:
      FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, *((_DWORD *)this + 2), 0);
      if ( FileMappingW )
      {
        for ( i = 0; i < 20; ++i )
        {
          Mappings = CCircularBuffer::CreateMappings(this, FileMappingW);
          *a4 = Mappings;
          if ( Mappings >= 0 )
            break;
        }
        CloseHandle(FileMappingW);
      }
      else
      {
        *a4 = GetLastError() | 0x80070000;
      }
    }
    else
    {
      ++crefVxD;
      BytesReturned = 0;
      InBuffer = a2 / 4096;
      if ( !DeviceIoControl(FileW, 1u, &InBuffer, 4u, this, 8u, &BytesReturned, 0) )
        *a4 = -2147024882;
    }
  }
  else
  {
    *a4 = -2147418113;
  }
  return this;
}

```

## disassembly

```asm
0x18014d610  mov     [rsp+arg_0], rbx
0x18014d615  push    rbp
0x18014d616  push    rsi
0x18014d617  push    rdi
0x18014d618  sub     rsp, 40h
0x18014d61c  mov     qword ptr [rcx], 0
0x18014d623  mov     rdi, r9
0x18014d626  mov     [rcx+8], edx
0x18014d629  mov     esi, edx
0x18014d62b  mov     [rcx+0Ch], r8d
0x18014d62f  mov     rbx, rcx
0x18014d632  test    edx, edx
0x18014d634  jz      loc_18014D789
0x18014d63a  test    r8d, r8d
0x18014d63d  jz      loc_18014D789
0x18014d643  cmp     r8d, edx
0x18014d646  jg      loc_18014D789
0x18014d64c  call    ?AlignmentRequired@CCircularBuffer@@CAJXZ; CCircularBuffer::AlignmentRequired(void)
0x18014d651  dec     eax
0x18014d653  test    esi, eax
0x18014d655  jnz     loc_18014D789
0x18014d65b  mov     rcx, cs:?hVxD@@3PEAXEA; void * hVxD
0x18014d662  mov     ebp, 4
0x18014d667  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18014d66b  jz      loc_18014D719
0x18014d671  test    rcx, rcx
0x18014d674  jnz     short loc_18014D6B0
0x18014d676  mov     [rsp+58h+hTemplateFile], rcx; hTemplateFile
0x18014d67b  lea     r8d, [rbp-2]; dwShareMode
0x18014d67f  mov     [rsp+58h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18014d687  lea     rcx, FileName; "\\\\.\\QUARTZ.VXD"
0x18014d68e  xor     r9d, r9d; lpSecurityAttributes
0x18014d691  mov     [rsp+58h+dwCreationDisposition], ebp; dwCreationDisposition
0x18014d695  mov     edx, 40000000h; dwDesiredAccess
0x18014d69a  call    cs:__imp_CreateFileW
0x18014d6a1  nop     dword ptr [rax+rax+00h]
0x18014d6a6  mov     rcx, rax; hDevice
0x18014d6a9  mov     cs:?hVxD@@3PEAXEA, rax; void * hVxD
0x18014d6b0  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18014d6b4  jz      short loc_18014D719
0x18014d6b6  inc     cs:?crefVxD@@3HA; int crefVxD
0x18014d6bc  mov     eax, esi
0x18014d6be  cdq
0x18014d6bf  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x18014d6c8  mov     r8d, 1000h
0x18014d6ce  mov     [rsp+58h+BytesReturned], 0
0x18014d6d6  idiv    r8d
0x18014d6d9  mov     r9d, ebp; nInBufferSize
0x18014d6dc  lea     r8, [rsp+58h+InBuffer]; lpInBuffer
0x18014d6e1  mov     [rsp+58h+InBuffer], eax
0x18014d6e5  mov     edx, 1; dwIoControlCode
0x18014d6ea  lea     rax, [rsp+58h+BytesReturned]
0x18014d6ef  mov     [rsp+58h+hTemplateFile], rax; lpBytesReturned
0x18014d6f4  mov     [rsp+58h+dwFlagsAndAttributes], 8; nOutBufferSize
0x18014d6fc  mov     qword ptr [rsp+58h+dwCreationDisposition], rbx; lpOutBuffer
0x18014d701  call    cs:__imp_DeviceIoControl
0x18014d708  nop     dword ptr [rax+rax+00h]
0x18014d70d  test    eax, eax
0x18014d70f  jnz     short loc_18014D78F
0x18014d711  mov     dword ptr [rdi], 8007000Eh
0x18014d717  jmp     short loc_18014D78F
0x18014d719  mov     eax, [rbx+8]
0x18014d71c  xor     r9d, r9d; dwMaximumSizeHigh
0x18014d71f  mov     qword ptr [rsp+58h+dwFlagsAndAttributes], 0; lpName
0x18014d728  mov     r8d, ebp; flProtect
0x18014d72b  xor     edx, edx; lpFileMappingAttributes
0x18014d72d  mov     [rsp+58h+dwCreationDisposition], eax; dwMaximumSizeLow
0x18014d731  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18014d735  call    cs:__imp_CreateFileMappingW
0x18014d73c  nop     dword ptr [rax+rax+00h]
0x18014d741  mov     rbp, rax
0x18014d744  test    rax, rax
0x18014d747  jnz     short loc_18014D75E
0x18014d749  call    cs:__imp_GetLastError
0x18014d750  nop     dword ptr [rax+rax+00h]
0x18014d755  or      eax, 80070000h
0x18014d75a  mov     [rdi], eax
0x18014d75c  jmp     short loc_18014D78F
0x18014d75e  xor     esi, esi
0x18014d760  mov     rdx, rbp; void *
0x18014d763  mov     rcx, rbx; this
0x18014d766  call    ?CreateMappings@CCircularBuffer@@AEAAJPEAX@Z; CCircularBuffer::CreateMappings(void *)
0x18014d76b  mov     [rdi], eax
0x18014d76d  test    eax, eax
0x18014d76f  jns     short loc_18014D778
0x18014d771  inc     esi
0x18014d773  cmp     esi, 14h
0x18014d776  jl      short loc_18014D760
0x18014d778  mov     rcx, rbp; hObject
0x18014d77b  call    cs:__imp_CloseHandle
0x18014d782  nop     dword ptr [rax+rax+00h]
0x18014d787  jmp     short loc_18014D78F
0x18014d789  mov     dword ptr [rdi], 8000FFFFh
0x18014d78f  mov     rax, rbx
0x18014d792  mov     rbx, [rsp+58h+arg_0]
0x18014d797  add     rsp, 40h
0x18014d79b  pop     rdi
0x18014d79c  pop     rsi
0x18014d79d  pop     rbp
0x18014d79e  retn
```
