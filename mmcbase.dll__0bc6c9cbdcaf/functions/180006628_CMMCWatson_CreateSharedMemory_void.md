# CMMCWatson::CreateSharedMemory(void)

- ea: `0x180006628`
- end: `0x1800066dc`
- name: `?CreateSharedMemory@CMMCWatson@@AEAA_NXZ`
- size: `180`
- prototype: `bool __fastcall(CMMCWatson *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180012834`

## callees

- `0x180006628`
- `0x18001b522`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180006681`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180006681`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800066a9`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800066a9`

## pseudocode

```c
char __fastcall CMMCWatson::CreateSharedMemory(CMMCWatson *this)
{
  char v1; // di
  HANDLE FileMappingW; // rax
  void *v4; // rax

  v1 = 0;
  if ( !*((_QWORD *)this + 71) )
  {
    *((_OWORD *)this + 36) = 0;
    *((_QWORD *)this + 74) = 0;
    *((_DWORD *)this + 148) = 1;
    *((_DWORD *)this + 144) = 24;
    FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, (LPSECURITY_ATTRIBUTES)this + 24, 4u, 0, 0x1C6Cu, 0);
    *((_QWORD *)this + 70) = FileMappingW;
    if ( FileMappingW )
    {
      v4 = MapViewOfFile(FileMappingW, 6u, 0, 0, 0);
      *((_QWORD *)this + 71) = v4;
      if ( v4 )
      {
        memset_0(v4, 0, 0x1C6Cu);
        return 1;
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180006628  mov     [rsp+arg_0], rbx
0x18000662d  push    rdi
0x18000662e  sub     rsp, 30h
0x180006632  xor     dil, dil
0x180006635  mov     rbx, rcx
0x180006638  cmp     qword ptr [rcx+238h], 0
0x180006640  jnz     loc_1800066CE
0x180006646  lea     rdx, [rcx+240h]; lpFileMappingAttributes
0x18000664d  xor     eax, eax
0x18000664f  xorps   xmm0, xmm0
0x180006652  mov     [rsp+38h+lpName], rax; lpName
0x180006657  movups  xmmword ptr [rdx], xmm0
0x18000665a  mov     [rdx+10h], rax
0x18000665e  xor     r9d, r9d; dwMaximumSizeHigh
0x180006661  mov     dword ptr [rcx+250h], 1
0x18000666b  lea     r8d, [rax+4]; flProtect
0x18000666f  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x180006673  mov     dword ptr [rdx], 18h
0x180006679  mov     [rsp+38h+dwMaximumSizeLow], 1C6Ch; dwMaximumSizeLow
0x180006681  call    cs:__imp_CreateFileMappingW
0x180006687  mov     [rbx+230h], rax
0x18000668e  test    rax, rax
0x180006691  jz      short loc_1800066CE
0x180006693  xor     r9d, r9d; dwFileOffsetLow
0x180006696  mov     qword ptr [rsp+38h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x18000669f  xor     r8d, r8d; dwFileOffsetHigh
0x1800066a2  mov     rcx, rax; hFileMappingObject
0x1800066a5  lea     edx, [r9+6]; dwDesiredAccess
0x1800066a9  call    cs:__imp_MapViewOfFile
0x1800066af  mov     [rbx+238h], rax
0x1800066b6  test    rax, rax
0x1800066b9  jz      short loc_1800066CE
0x1800066bb  xor     edx, edx; Val
0x1800066bd  mov     r8d, 1C6Ch; Size
0x1800066c3  mov     rcx, rax; void *
0x1800066c6  call    memset_0
0x1800066cb  mov     dil, 1
0x1800066ce  mov     rbx, [rsp+38h+arg_0]
0x1800066d3  mov     al, dil
0x1800066d6  add     rsp, 30h
0x1800066da  pop     rdi
0x1800066db  retn
```
