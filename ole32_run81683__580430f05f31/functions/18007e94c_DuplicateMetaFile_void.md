# DuplicateMetaFile(void *)

- ea: `0x18007e94c`
- end: `0x18007e9fc`
- name: `?DuplicateMetaFile@@YAPEAXPEAX@Z`
- size: `176`
- prototype: `void *__fastcall(void *hSrcData)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18007ee34`

## callees

- `0x18007e94c`
- `0x1800a5b68`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x18007e9a3`
- `KERNELBASE!GlobalAlloc` at `0x18007e9a3`
- `KERNELBASE!GlobalFree` at `0x18007e9eb`
- `KERNELBASE!GlobalFree` at `0x18007e9eb`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18007e981`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18007e9c5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18007e981`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18007e9c5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18007e970`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18007e9b4`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18007e970`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18007e9b4`
- `GDI32!DeleteMetaFile` at `0x18007e9dd`
- `GDI32!DeleteMetaFile` at `0x18007e9dd`
- `GDI32!CopyMetaFileW` at `0x18007e98d`
- `GDI32!CopyMetaFileW` at `0x18007e98d`

## pseudocode

```c
void *__fastcall DuplicateMetaFile(void *hSrcData)
{
  HMETAFILE *v2; // rdi
  HMETAFILE v3; // rbp
  HGLOBAL v4; // rax
  void *v5; // rbx
  _QWORD *v6; // rsi
  void *result; // rax

  if ( VerifyStructFromHGlobal(3u, hSrcData) >= 0 )
  {
    v2 = (HMETAFILE *)GlobalLock(hSrcData);
    if ( v2 )
    {
      GlobalUnlock(hSrcData);
      v3 = CopyMetaFileW(v2[2], 0);
      if ( v3 )
      {
        v4 = GlobalAlloc(2u, 0x18u);
        v5 = v4;
        if ( v4 )
        {
          v6 = GlobalLock(v4);
          if ( v6 )
          {
            GlobalUnlock(v5);
            result = v5;
            *(_OWORD *)v6 = *(_OWORD *)v2;
            v6[2] = v3;
            return result;
          }
        }
        DeleteMetaFile(v3);
        if ( v5 )
          GlobalFree(v5);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18007e94c  push    rbx
0x18007e94e  push    rbp
0x18007e94f  push    rsi
0x18007e950  push    rdi
0x18007e951  sub     rsp, 28h
0x18007e955  mov     rbx, hSrcData
0x18007e958  mov     ecx, 3; cfFormat
0x18007e95d  mov     rdx, rbx; hGlobal
0x18007e960  call    ?VerifyStructFromHGlobal@@YAJGPEAX@Z; VerifyStructFromHGlobal(ushort,void *)
0x18007e965  test    eax, eax
0x18007e967  js      loc_18007E9F1
0x18007e96d  mov     hSrcData, rbx; hMem
0x18007e970  call    cs:__imp_GlobalLock
0x18007e976  mov     rdi, rax
0x18007e979  test    rax, rax
0x18007e97c  jz      short loc_18007E9F1
0x18007e97e  mov     hSrcData, rbx; hMem
0x18007e981  call    cs:__imp_GlobalUnlock
0x18007e987  mov     hSrcData, [rdi+10h]; HMETAFILE
0x18007e98b  xor     edx, edx; LPCWSTR
0x18007e98d  call    cs:__imp_CopyMetaFileW
0x18007e993  mov     rbp, rax
0x18007e996  test    rax, rax
0x18007e999  jz      short loc_18007E9F1
0x18007e99b  mov     edx, 18h; dwBytes
0x18007e9a0  lea     ecx, [rdx-16h]; uFlags
0x18007e9a3  call    cs:__imp_GlobalAlloc
0x18007e9a9  mov     rbx, rax
0x18007e9ac  test    rax, rax
0x18007e9af  jz      short $errMfp
0x18007e9b1  mov     hSrcData, rax; hMem
0x18007e9b4  call    cs:__imp_GlobalLock
0x18007e9ba  mov     rsi, rax
0x18007e9bd  test    rax, rax
0x18007e9c0  jz      short $errMfp
0x18007e9c2  mov     hSrcData, rbx; hMem
0x18007e9c5  call    cs:__imp_GlobalUnlock
0x18007e9cb  movups  xmm0, xmmword ptr [rdi]
0x18007e9ce  mov     rax, rbx
0x18007e9d1  movups  xmmword ptr [rsi], xmm0
0x18007e9d4  mov     [rsi+10h], rbp
0x18007e9d8  jmp     short loc_18007E9F3
0x18007e9da  mov     hSrcData, rbp; hmf
0x18007e9dd  call    cs:__imp_DeleteMetaFile
0x18007e9e3  test    rbx, rbx
0x18007e9e6  jz      short loc_18007E9F1
0x18007e9e8  mov     hSrcData, rbx; hMem
0x18007e9eb  call    cs:__imp_GlobalFree
0x18007e9f1  xor     eax, eax
0x18007e9f3  add     rsp, 28h
0x18007e9f7  pop     rdi
0x18007e9f8  pop     rsi
0x18007e9f9  pop     rbp
0x18007e9fa  pop     rbx
0x18007e9fb  retn
```
