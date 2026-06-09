# GdiConvertMetaFilePict

- ea: `0x180093910`
- end: `0x1800939b3`
- name: `GdiConvertMetaFilePict`
- size: `163`
- prototype: `__int64 __fastcall(HGLOBAL hMem)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18002e040`
- `0x180093910`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180093994`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180093994`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180093926`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180093926`
- `GDI32!GdiSetLastError` at `0x180093955`
- `GDI32!GdiSetLastError` at `0x180093955`
- `win32u!NtGdiCreateServerMetaFile` at `0x180093982`
- `win32u!NtGdiCreateServerMetaFile` at `0x180093982`

## pseudocode

```c
__int64 __fastcall GdiConvertMetaFilePict(HGLOBAL hMem)
{
  unsigned int *v2; // rax
  unsigned int *v3; // rbx
  __int64 v4; // rax
  __int64 ServerMetaFile; // rbx

  if ( gbDisableMetaFiles )
    return 0;
  v2 = (unsigned int *)GlobalLock(hMem);
  v3 = v2;
  if ( !v2 )
    return 0;
  v4 = pvClientObjGet(*((_QWORD *)v2 + 2), 2490368);
  if ( v4 )
  {
    ServerMetaFile = NtGdiCreateServerMetaFile(
                       1599096397,
                       (unsigned int)(2 * *(_DWORD *)(v4 + 10)),
                       *(_QWORD *)(v4 + 40),
                       *v3,
                       v3[1],
                       v3[2]);
  }
  else
  {
    ServerMetaFile = 0;
    GdiSetLastError(6);
  }
  GlobalUnlock(hMem);
  return ServerMetaFile;
}

```

## disassembly

```asm
0x180093910  mov     [rsp+arg_0], rbx
0x180093915  push    rdi
0x180093916  sub     rsp, 30h
0x18009391a  cmp     cs:gbDisableMetaFiles, 0
0x180093921  mov     rdi, rcx
0x180093924  jnz     short loc_1800939A5
0x180093926  call    cs:__imp_GlobalLock
0x18009392d  nop     dword ptr [rax+rax+00h]
0x180093932  mov     rbx, rax
0x180093935  test    rax, rax
0x180093938  jz      short loc_1800939A5
0x18009393a  mov     rcx, [rax+10h]
0x18009393e  mov     edx, 260000h
0x180093943  call    pvClientObjGet
0x180093948  mov     r8, rax
0x18009394b  test    rax, rax
0x18009394e  jnz     short loc_180093963
0x180093950  xor     ebx, ebx
0x180093952  lea     ecx, [rax+6]
0x180093955  call    cs:__imp_GdiSetLastError
0x18009395c  nop     dword ptr [rax+rax+00h]
0x180093961  jmp     short loc_180093991
0x180093963  mov     edx, [rax+0Ah]
0x180093966  mov     ecx, 5F50464Dh
0x18009396b  mov     eax, [rbx+8]
0x18009396e  add     edx, edx
0x180093970  mov     r9d, [rbx]
0x180093973  mov     r8, [r8+28h]
0x180093977  mov     [rsp+38h+var_10], eax
0x18009397b  mov     eax, [rbx+4]
0x18009397e  mov     [rsp+38h+var_18], eax
0x180093982  call    cs:__imp_NtGdiCreateServerMetaFile
0x180093989  nop     dword ptr [rax+rax+00h]
0x18009398e  mov     rbx, rax
0x180093991  mov     rcx, rdi; hMem
0x180093994  call    cs:__imp_GlobalUnlock
0x18009399b  nop     dword ptr [rax+rax+00h]
0x1800939a0  mov     rax, rbx
0x1800939a3  jmp     short loc_1800939A7
0x1800939a5  xor     eax, eax
0x1800939a7  mov     rbx, [rsp+38h+arg_0]
0x1800939ac  add     rsp, 30h
0x1800939b0  pop     rdi
0x1800939b1  retn
```
