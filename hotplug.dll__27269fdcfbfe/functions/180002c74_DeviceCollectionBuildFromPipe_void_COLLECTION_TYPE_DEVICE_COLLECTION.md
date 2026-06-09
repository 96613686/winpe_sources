# DeviceCollectionBuildFromPipe(void *,_COLLECTION_TYPE,DEVICE_COLLECTION *)

- ea: `0x180002c74`
- end: `0x180002d6a`
- name: `?DeviceCollectionBuildFromPipe@@YAHPEAXW4_COLLECTION_TYPE@@PEAUDEVICE_COLLECTION@@@Z`
- size: `246`
- prototype: `__int64 __fastcall(void *, int, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180004aec`
- `0x180004c20`
- `0x180004e60`
- `0x180005430`

## callees

- `0x180002824`
- `0x180002c74`

## import_xrefs

- `KERNEL32!ReadFile` at `0x180002cb0`
- `KERNEL32!ReadFile` at `0x180002d06`
- `KERNEL32!ReadFile` at `0x180002cb0`
- `KERNEL32!ReadFile` at `0x180002d06`
- `KERNEL32!LocalFree` at `0x180002d54`
- `KERNEL32!LocalFree` at `0x180002d54`
- `KERNEL32!LocalAlloc` at `0x180002cdb`
- `KERNEL32!LocalAlloc` at `0x180002cdb`

## pseudocode

```c
__int64 __fastcall DeviceCollectionBuildFromPipe(void *a1, int a2, __int64 a3)
{
  unsigned int v6; // esi
  WCHAR *v7; // rdi
  WCHAR *v8; // rax
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v11; // [rsp+34h] [rbp-44h]
  WCHAR *v12; // [rsp+38h] [rbp-40h]
  DWORD nNumberOfBytesToRead; // [rsp+98h] [rbp+20h] BYREF

  NumberOfBytesRead = 0;
  v6 = 0;
  v11 = 0;
  v7 = 0;
  v12 = 0;
  nNumberOfBytesToRead = 0;
  if ( ReadFile(a1, &nNumberOfBytesToRead, 4u, &NumberOfBytesRead, 0) )
  {
    if ( nNumberOfBytesToRead - 1 <= 0xFFFFFFF9 && NumberOfBytesRead == 4 )
    {
      v8 = (WCHAR *)LocalAlloc(0x40u, nNumberOfBytesToRead + 4LL);
      v7 = v8;
      v12 = v8;
      if ( v8 )
      {
        if ( ReadFile(a1, v8, nNumberOfBytesToRead, &NumberOfBytesRead, 0) )
        {
          v7[(unsigned __int64)nNumberOfBytesToRead >> 1] = 0;
          v7[((unsigned __int64)nNumberOfBytesToRead >> 1) + 1] = 0;
          v6 = DeviceCollectionBuildFromMultiSz(v7, a2, a3);
          v11 = v6;
        }
      }
    }
  }
  if ( v7 )
    LocalFree(v7);
  return v6;
}

```

## disassembly

```asm
0x180002c74  mov     rax, rsp
0x180002c77  push    rbx
0x180002c78  push    rsi
0x180002c79  push    rdi
0x180002c7a  push    r12
0x180002c7c  push    r14
0x180002c7e  push    r15
0x180002c80  sub     rsp, 48h
0x180002c84  mov     r15, r8
0x180002c87  mov     r12d, edx
0x180002c8a  mov     r14, rcx
0x180002c8d  xor     ebx, ebx
0x180002c8f  mov     [rax-48h], ebx
0x180002c92  mov     esi, ebx
0x180002c94  mov     [rax-44h], ebx
0x180002c97  mov     edi, ebx
0x180002c99  mov     [rax-40h], rbx
0x180002c9d  mov     [rax+20h], ebx
0x180002ca0  mov     [rax-58h], rbx
0x180002ca4  lea     r9, [rax-48h]; lpNumberOfBytesRead
0x180002ca8  lea     r8d, [rbx+4]; nNumberOfBytesToRead
0x180002cac  lea     rdx, [rax+20h]; lpBuffer
0x180002cb0  call    cs:__imp_ReadFile
0x180002cb6  test    eax, eax
0x180002cb8  jz      loc_180002D41
0x180002cbe  mov     ecx, [rsp+78h+nNumberOfBytesToRead]
0x180002cc5  lea     eax, [rcx-1]
0x180002cc8  cmp     eax, 0FFFFFFF9h
0x180002ccb  ja      short loc_180002D41
0x180002ccd  cmp     [rsp+78h+NumberOfBytesRead], 4
0x180002cd2  jnz     short loc_180002D41
0x180002cd4  lea     rdx, [rcx+4]; uBytes
0x180002cd8  lea     ecx, [rbx+40h]; uFlags
0x180002cdb  call    cs:__imp_LocalAlloc
0x180002ce1  mov     rdi, rax
0x180002ce4  mov     [rsp+78h+var_40], rax
0x180002ce9  test    rax, rax
0x180002cec  jz      short loc_180002D41
0x180002cee  mov     [rsp+78h+lpOverlapped], rbx; lpOverlapped
0x180002cf3  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180002cf8  mov     r8d, [rsp+78h+nNumberOfBytesToRead]; nNumberOfBytesToRead
0x180002d00  mov     rdx, rax; lpBuffer
0x180002d03  mov     rcx, r14; hFile
0x180002d06  call    cs:__imp_ReadFile
0x180002d0c  test    eax, eax
0x180002d0e  jz      short loc_180002D41
0x180002d10  mov     eax, [rsp+78h+nNumberOfBytesToRead]
0x180002d17  shr     rax, 1
0x180002d1a  mov     [rdi+rax*2], bx
0x180002d1e  mov     eax, [rsp+78h+nNumberOfBytesToRead]
0x180002d25  shr     rax, 1
0x180002d28  mov     [rdi+rax*2+2], bx
0x180002d2d  mov     r8, r15
0x180002d30  mov     edx, r12d
0x180002d33  mov     rcx, rdi
0x180002d36  call    ?DeviceCollectionBuildFromMultiSz@@YAHQEAGW4_COLLECTION_TYPE@@PEAUDEVICE_COLLECTION@@@Z; DeviceCollectionBuildFromMultiSz(ushort * const,_COLLECTION_TYPE,DEVICE_COLLECTION *)
0x180002d3b  mov     esi, eax
0x180002d3d  mov     [rsp+78h+var_44], eax
0x180002d41  jmp     short loc_180002D4C
0x180002d43  mov     rdi, [rsp+78h+var_40]
0x180002d48  mov     esi, [rsp+78h+var_44]
0x180002d4c  test    rdi, rdi
0x180002d4f  jz      short loc_180002D5A
0x180002d51  mov     rcx, rdi; hMem
0x180002d54  call    cs:__imp_LocalFree
0x180002d5a  mov     eax, esi
0x180002d5c  add     rsp, 48h
0x180002d60  pop     r15
0x180002d62  pop     r14
0x180002d64  pop     r12
0x180002d66  pop     rdi
0x180002d67  pop     rsi
0x180002d68  pop     rbx
0x180002d69  retn
```
