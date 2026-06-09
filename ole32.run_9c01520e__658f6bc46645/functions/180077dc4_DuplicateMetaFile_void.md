# DuplicateMetaFile(void *)

- ea: `0x180077dc4`
- end: `0x180077ec0`
- name: `?DuplicateMetaFile@@YAPEAXPEAX@Z`
- size: `252`
- prototype: `void *__fastcall(void *hSrcData)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800783a0`

## callees

- `0x180077dc4`
- `0x1800aca50`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x180077e3c`
- `KERNELBASE!GlobalAlloc` at `0x180077e3c`
- `KERNELBASE!GlobalFree` at `0x180077e9c`
- `KERNELBASE!GlobalFree` at `0x180077e9c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180077e0e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180077e6a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180077e0e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180077e6a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180077df3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180077e53`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180077df3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180077e53`
- `GDI32!DeleteMetaFile` at `0x180077e88`
- `GDI32!DeleteMetaFile` at `0x180077e88`
- `GDI32!CopyMetaFileW` at `0x180077e20`
- `GDI32!CopyMetaFileW` at `0x180077e20`

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
0x180077dc4  mov     [rsp+arg_0], rbx
0x180077dc9  mov     [rsp+arg_8], rbp
0x180077dce  mov     [rsp+arg_10], rsi
0x180077dd3  push    rdi
0x180077dd4  sub     rsp, 20h
0x180077dd8  mov     rbx, hSrcData
0x180077ddb  mov     ecx, 3; cfFormat
0x180077de0  mov     rdx, rbx; hGlobal
0x180077de3  call    ?VerifyStructFromHGlobal@@YAJGPEAX@Z; VerifyStructFromHGlobal(ushort,void *)
0x180077de8  test    eax, eax
0x180077dea  js      loc_180077EA8
0x180077df0  mov     hSrcData, rbx; hMem
0x180077df3  call    cs:__imp_GlobalLock
0x180077dfa  nop     dword ptr [rax+rax+00h]
0x180077dff  mov     rdi, rax
0x180077e02  test    rax, rax
0x180077e05  jz      loc_180077EA8
0x180077e0b  mov     hSrcData, rbx; hMem
0x180077e0e  call    cs:__imp_GlobalUnlock
0x180077e15  nop     dword ptr [rax+rax+00h]
0x180077e1a  mov     hSrcData, [rdi+10h]; HMETAFILE
0x180077e1e  xor     edx, edx; LPCWSTR
0x180077e20  call    cs:__imp_CopyMetaFileW
0x180077e27  nop     dword ptr [rax+rax+00h]
0x180077e2c  mov     rbp, rax
0x180077e2f  test    rax, rax
0x180077e32  jz      short loc_180077EA8
0x180077e34  mov     edx, 18h; dwBytes
0x180077e39  lea     ecx, [rdx-16h]; uFlags
0x180077e3c  call    cs:__imp_GlobalAlloc
0x180077e43  nop     dword ptr [rax+rax+00h]
0x180077e48  mov     rbx, rax
0x180077e4b  test    rax, rax
0x180077e4e  jz      short $errMfp
0x180077e50  mov     hSrcData, rax; hMem
0x180077e53  call    cs:__imp_GlobalLock
0x180077e5a  nop     dword ptr [rax+rax+00h]
0x180077e5f  mov     rsi, rax
0x180077e62  test    rax, rax
0x180077e65  jz      short $errMfp
0x180077e67  mov     hSrcData, rbx; hMem
0x180077e6a  call    cs:__imp_GlobalUnlock
0x180077e71  nop     dword ptr [rax+rax+00h]
0x180077e76  movups  xmm0, xmmword ptr [rdi]
0x180077e79  mov     rax, rbx
0x180077e7c  movups  xmmword ptr [rsi], xmm0
0x180077e7f  mov     [rsi+10h], rbp
0x180077e83  jmp     short loc_180077EAA
0x180077e85  mov     hSrcData, rbp; hmf
0x180077e88  call    cs:__imp_DeleteMetaFile
0x180077e8f  nop     dword ptr [rax+rax+00h]
0x180077e94  test    rbx, rbx
0x180077e97  jz      short loc_180077EA8
0x180077e99  mov     hSrcData, rbx; hMem
0x180077e9c  call    cs:__imp_GlobalFree
0x180077ea3  nop     dword ptr [rax+rax+00h]
0x180077ea8  xor     eax, eax
0x180077eaa  mov     rbx, [rsp+28h+arg_0]
0x180077eaf  mov     rbp, [rsp+28h+arg_8]
0x180077eb4  mov     rsi, [rsp+28h+arg_10]
0x180077eb9  add     rsp, 20h
0x180077ebd  pop     rdi
0x180077ebe  retn
```
