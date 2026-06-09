# InfMultiSzCat

- ea: `0x18001f3d8`
- end: `0x18001f5b8`
- name: `InfMultiSzCat`
- size: `480`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18001f5c0`

## callees

- `0x18000d57c`
- `0x18000d624`
- `0x18001f3d8`
- `0x180039044`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f53f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f53f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f4e5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f4e5`

## string_xrefs

- `0x18001f478`: `The target already contains a double-null terminator.`
- `0x18001f4ab`: `The string to append already has a double-null terminator.`

## pseudocode

```c
__int64 __fastcall InfMultiSzCat(const void **a1, int *a2, _WORD *a3, unsigned int a4)
{
  __int64 v4; // rbx
  int v8; // r13d
  int v9; // ebp
  _WORD *v10; // r8
  int v11; // edx
  int v12; // r14d
  char *v13; // rax
  char *v14; // r13
  unsigned int v15; // ebp
  __int64 v16; // rax
  int v18; // [rsp+60h] [rbp+8h]

  v4 = a4;
  if ( !a1 || !a2 || !a3 || a4 - 1 > 0xFFFFFFFD || *a2 > -2 - a4 )
  {
    ClassInstallerTelemetry::WriteDbgTraceError(
      "InfMultiSzCat",
      L"Invalid Argument: ppszzTarget=%p, pcchTarget=%p, pszzToAppend=%ws, cchToAppend=%d",
      a1,
      a2,
      a3,
      a4);
    v15 = -2147024809;
    goto LABEL_28;
  }
  v8 = 0;
  v18 = 0;
  v9 = 0;
  ClassInstallerTelemetry::WriteDbgTraceInfo(
    "InfMultiSzCat",
    L"Adding a multi-string beginning with %ws to the target multi-string");
  v10 = *a1;
  if ( *a1 )
  {
    v11 = *a2;
    if ( (unsigned int)*a2 > 1 && !v10[v11 - 1] && !v10[v11 - 2] )
    {
      v8 = 1;
      v18 = 1;
      ClassInstallerTelemetry::WriteDbgTraceInfo(
        "InfMultiSzCat",
        L"The target already contains a double-null terminator.");
    }
  }
  if ( (unsigned int)v4 > 1 && !a3[(unsigned int)(v4 - 1)] && !a3[(unsigned int)(v4 - 2)] )
  {
    v9 = 1;
    ClassInstallerTelemetry::WriteDbgTraceInfo(
      "InfMultiSzCat",
      L"The string to append already has a double-null terminator.");
  }
  v12 = v4 + *a2;
  if ( v8 )
  {
    if ( v9 )
      --v12;
  }
  else if ( !v9 )
  {
    ++v12;
  }
  v13 = (char *)LocalAlloc(0x40u, (unsigned int)(2 * v12));
  v14 = v13;
  if ( !v13 )
  {
    v15 = -2147024882;
LABEL_28:
    ClassInstallerTelemetry::WriteDbgTraceError(
      "InfMultiSzCat",
      L"Error appending the multi-string to the target: hr: 0x%x",
      v15);
    return v15;
  }
  v15 = 0;
  memcpy_0(v13, *a1, 2LL * (unsigned int)*a2);
  v16 = (unsigned int)(*a2 - 1);
  if ( !v18 )
    v16 = (unsigned int)*a2;
  memcpy_0(&v14[2 * v16], a3, 2 * v4);
  if ( *a1 )
    LocalFree((HLOCAL)*a1);
  *a1 = v14;
  *a2 = v12;
  ClassInstallerTelemetry::WriteDbgTraceInfo("InfMultiSzCat", L"Successfully appended the multi-string to the target.");
  return v15;
}

```

## disassembly

```asm
0x18001f3d8  mov     [rsp+arg_8], rbx
0x18001f3dd  mov     [rsp+arg_10], rbp
0x18001f3e2  push    rdi
0x18001f3e3  push    r12
0x18001f3e5  push    r13
0x18001f3e7  push    r14
0x18001f3e9  push    r15
0x18001f3eb  sub     rsp, 30h
0x18001f3ef  mov     ebx, r9d
0x18001f3f2  mov     r15, r8
0x18001f3f5  mov     rdi, rdx
0x18001f3f8  mov     r12, rcx
0x18001f3fb  test    rcx, rcx
0x18001f3fe  jz      loc_18001F561
0x18001f404  test    rdx, rdx
0x18001f407  jz      loc_18001F561
0x18001f40d  test    r8, r8
0x18001f410  jz      loc_18001F561
0x18001f416  lea     eax, [rbx-1]
0x18001f419  cmp     eax, 0FFFFFFFDh
0x18001f41c  ja      loc_18001F561
0x18001f422  mov     eax, 0FFFFFFFEh
0x18001f427  sub     eax, ebx
0x18001f429  cmp     [rdx], eax
0x18001f42b  ja      loc_18001F561
0x18001f431  xor     r13d, r13d
0x18001f434  lea     rdx, aAddingAMultiSt; "Adding a multi-string beginning with %w"...
0x18001f43b  lea     rcx, aInfmultiszcat; "InfMultiSzCat"
0x18001f442  mov     [rsp+58h+arg_0], r13d
0x18001f447  xor     ebp, ebp
0x18001f449  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001f44e  mov     r8, [r12]
0x18001f452  test    r8, r8
0x18001f455  jz      short loc_18001F490
0x18001f457  mov     edx, [rdi]
0x18001f459  cmp     edx, 1
0x18001f45c  jbe     short loc_18001F490
0x18001f45e  lea     ecx, [rdx-1]
0x18001f461  xor     eax, eax
0x18001f463  cmp     ax, [r8+rcx*2]
0x18001f468  jnz     short loc_18001F490
0x18001f46a  lea     ecx, [rdx-2]
0x18001f46d  cmp     ax, [r8+rcx*2]
0x18001f472  jnz     short loc_18001F490
0x18001f474  lea     r13d, [rbp+1]
0x18001f478  lea     rdx, aTheTargetAlrea; "The target already contains a double-nu"...
0x18001f47f  mov     [rsp+58h+arg_0], r13d
0x18001f484  lea     rcx, aInfmultiszcat; "InfMultiSzCat"
0x18001f48b  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001f490  cmp     ebx, 1
0x18001f493  jbe     short loc_18001F4C1
0x18001f495  lea     ecx, [rbx-1]
0x18001f498  xor     eax, eax
0x18001f49a  cmp     ax, [r15+rcx*2]
0x18001f49f  jnz     short loc_18001F4C1
0x18001f4a1  lea     ecx, [rbx-2]
0x18001f4a4  cmp     ax, [r15+rcx*2]
0x18001f4a9  jnz     short loc_18001F4C1
0x18001f4ab  lea     rdx, aTheStringToApp; "The string to append already has a doub"...
0x18001f4b2  lea     rcx, aInfmultiszcat; "InfMultiSzCat"
0x18001f4b9  lea     ebp, [rax+1]
0x18001f4bc  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001f4c1  mov     r14d, [rdi]
0x18001f4c4  add     r14d, ebx
0x18001f4c7  test    r13d, r13d
0x18001f4ca  jz      short loc_18001F4D5
0x18001f4cc  test    ebp, ebp
0x18001f4ce  jz      short loc_18001F4DC
0x18001f4d0  dec     r14d
0x18001f4d3  jmp     short loc_18001F4DC
0x18001f4d5  test    ebp, ebp
0x18001f4d7  jnz     short loc_18001F4DC
0x18001f4d9  inc     r14d
0x18001f4dc  lea     edx, [r14+r14]; uBytes
0x18001f4e0  mov     ecx, 40h ; '@'; uFlags
0x18001f4e5  call    cs:__imp_LocalAlloc
0x18001f4eb  mov     r13, rax
0x18001f4ee  test    rax, rax
0x18001f4f1  jnz     short loc_18001F4FD
0x18001f4f3  mov     ebp, 8007000Eh
0x18001f4f8  jmp     loc_18001F588
0x18001f4fd  mov     r8d, [rdi]
0x18001f500  mov     rcx, r13; void *
0x18001f503  mov     rdx, [r12]; Src
0x18001f507  add     r8, r8; Size
0x18001f50a  xor     ebp, ebp
0x18001f50c  call    memcpy_0
0x18001f511  mov     ecx, [rdi]
0x18001f513  mov     r8, rbx
0x18001f516  add     r8, r8; Size
0x18001f519  mov     rdx, r15; Src
0x18001f51c  cmp     [rsp+58h+arg_0], ebp
0x18001f520  lea     eax, [rcx-1]
0x18001f523  cmovz   eax, ecx
0x18001f526  lea     rcx, ds:0[rax*2]
0x18001f52e  add     rcx, r13; void *
0x18001f531  call    memcpy_0
0x18001f536  mov     rcx, [r12]; hMem
0x18001f53a  test    rcx, rcx
0x18001f53d  jz      short loc_18001F545
0x18001f53f  call    cs:__imp_LocalFree
0x18001f545  mov     [r12], r13
0x18001f549  lea     rdx, aSuccessfullyAp; "Successfully appended the multi-string "...
0x18001f550  lea     rcx, aInfmultiszcat; "InfMultiSzCat"
0x18001f557  mov     [rdi], r14d
0x18001f55a  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001f55f  jmp     short loc_18001F59E
0x18001f561  mov     [rsp+58h+var_30], ebx
0x18001f565  lea     rdx, aInvalidArgumen_5; "Invalid Argument: ppszzTarget=%p, pcchT"...
0x18001f56c  mov     r9, rdi
0x18001f56f  mov     [rsp+58h+var_38], r15
0x18001f574  mov     r8, r12
0x18001f577  lea     rcx, aInfmultiszcat; "InfMultiSzCat"
0x18001f57e  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18001f583  mov     ebp, 80070057h
0x18001f588  mov     r8d, ebp
0x18001f58b  lea     rdx, aErrorAppending; "Error appending the multi-string to the"...
0x18001f592  lea     rcx, aInfmultiszcat; "InfMultiSzCat"
0x18001f599  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18001f59e  mov     rbx, [rsp+58h+arg_8]
0x18001f5a3  mov     eax, ebp
0x18001f5a5  mov     rbp, [rsp+58h+arg_10]
0x18001f5aa  add     rsp, 30h
0x18001f5ae  pop     r15
0x18001f5b0  pop     r14
0x18001f5b2  pop     r13
0x18001f5b4  pop     r12
0x18001f5b6  pop     rdi
0x18001f5b7  retn
```
