# LuafvQueryDirectoryIfNeeded

- ea: `0x1400223a4`
- end: `0x1400224cd`
- name: `LuafvQueryDirectoryIfNeeded`
- size: `297`
- prototype: `NTSTATUS __fastcall(PFLT_INSTANCE Instance, __int64, BOOLEAN, FILE_INFORMATION_CLASS, PUNICODE_STRING FileName, BOOLEAN RestartScan)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400220ac`

## callees

- `0x1400223a4`

## import_xrefs

- `ntoskrnl!IoFileObjectType` at `0x1400223d7`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400223ff`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400223ff`
- `ntoskrnl!ObfDereferenceObject` at `0x14002245d`
- `ntoskrnl!ObfDereferenceObject` at `0x14002245d`
- `FLTMGR!FltQueryDirectoryFile` at `0x140022449`
- `FLTMGR!FltQueryDirectoryFile` at `0x140022449`

## pseudocode

```c
NTSTATUS __fastcall LuafvQueryDirectoryIfNeeded(
        PFLT_INSTANCE Instance,
        __int64 a2,
        BOOLEAN a3,
        FILE_INFORMATION_CLASS a4,
        PUNICODE_STRING FileName,
        BOOLEAN RestartScan)
{
  NTSTATUS result; // eax
  NTSTATUS v11; // edi
  NTSTATUS DirectoryFile; // eax
  PVOID v13; // rcx
  int v14; // eax
  __int64 v15; // rax
  unsigned __int64 v16; // rdx
  PVOID Object; // [rsp+50h] [rbp-48h] BYREF

  Object = 0;
  if ( !RestartScan )
  {
    v16 = *(_QWORD *)(a2 + 24);
    if ( v16 )
    {
      v11 = 0;
      if ( v16 < *(_QWORD *)(a2 + 16) + (unsigned __int64)*(unsigned int *)(a2 + 12) || *(_DWORD *)(a2 + 8) )
        return v11;
    }
  }
  result = ObReferenceObjectByHandle(*(HANDLE *)a2, 0x100001u, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
  v11 = result;
  if ( result >= 0 )
  {
    DirectoryFile = FltQueryDirectoryFile(
                      Instance,
                      (PFILE_OBJECT)Object,
                      *(PVOID *)(a2 + 16),
                      *(_DWORD *)(a2 + 12),
                      a4,
                      a3,
                      FileName,
                      RestartScan,
                      0);
    v13 = Object;
    *(_DWORD *)(a2 + 8) = DirectoryFile;
    ObfDereferenceObject(v13);
    v14 = *(_DWORD *)(a2 + 8);
    if ( v14 < 0 )
    {
      if ( v14 != -2147483642 && v14 != -1073741809 )
        v11 = *(_DWORD *)(a2 + 8);
      v15 = *(_QWORD *)(a2 + 16) + *(unsigned int *)(a2 + 12);
    }
    else
    {
      v15 = *(_QWORD *)(a2 + 16);
    }
    *(_QWORD *)(a2 + 24) = v15;
    return v11;
  }
  *(_DWORD *)(a2 + 8) = result;
  return result;
}

```

## disassembly

```asm
0x1400223a4  push    rbx
0x1400223a6  push    rbp
0x1400223a7  push    rsi
0x1400223a8  push    rdi
0x1400223a9  push    r14
0x1400223ab  push    r15
0x1400223ad  sub     rsp, 68h
0x1400223b1  mov     sil, [rsp+98h+arg_28]
0x1400223b9  mov     ebp, r9d
0x1400223bc  mov     [rsp+98h+var_48], 0
0x1400223c5  mov     r14b, r8b
0x1400223c8  mov     rbx, rdx
0x1400223cb  mov     r15, rcx
0x1400223ce  test    sil, sil
0x1400223d1  jz      loc_140022488
0x1400223d7  mov     r8, cs:__imp_IoFileObjectType
0x1400223de  lea     rax, [rsp+98h+var_48]
0x1400223e3  mov     rcx, [rbx]; Handle
0x1400223e6  xor     r9d, r9d; AccessMode
0x1400223e9  mov     [rsp+98h+HandleInformation], 0; HandleInformation
0x1400223f2  mov     edx, 100001h; DesiredAccess
0x1400223f7  mov     [rsp+98h+Object], rax; Object
0x1400223fc  mov     r8, [r8]; ObjectType
0x1400223ff  call    cs:__imp_ObReferenceObjectByHandle
0x140022406  nop     dword ptr [rax+rax+00h]
0x14002240b  mov     edi, eax
0x14002240d  test    eax, eax
0x14002240f  js      loc_1400224BE
0x140022415  mov     rax, [rsp+98h+arg_20]
0x14002241d  mov     rcx, r15; Instance
0x140022420  mov     r9d, [rbx+0Ch]; Length
0x140022424  mov     r8, [rbx+10h]; FileInformation
0x140022428  mov     rdx, [rsp+98h+var_48]; FileObject
0x14002242d  mov     [rsp+98h+LengthReturned], 0; LengthReturned
0x140022436  mov     [rsp+98h+RestartScan], sil; RestartScan
0x14002243b  mov     [rsp+98h+FileName], rax; FileName
0x140022440  mov     byte ptr [rsp+98h+HandleInformation], r14b; ReturnSingleEntry
0x140022445  mov     dword ptr [rsp+98h+Object], ebp; FileInformationClass
0x140022449  call    cs:__imp_FltQueryDirectoryFile
0x140022450  nop     dword ptr [rax+rax+00h]
0x140022455  mov     rcx, [rsp+98h+var_48]; Object
0x14002245a  mov     [rbx+8], eax
0x14002245d  call    cs:__imp_ObfDereferenceObject
0x140022464  nop     dword ptr [rax+rax+00h]
0x140022469  mov     eax, [rbx+8]
0x14002246c  test    eax, eax
0x14002246e  js      short loc_1400224AE
0x140022470  mov     rax, [rbx+10h]
0x140022474  mov     [rbx+18h], rax
0x140022478  mov     eax, edi
0x14002247a  add     rsp, 68h
0x14002247e  pop     r15
0x140022480  pop     r14
0x140022482  pop     rdi
0x140022483  pop     rsi
0x140022484  pop     rbp
0x140022485  pop     rbx
0x140022486  retn
0x140022488  mov     rdx, [rdx+18h]
0x14002248c  test    rdx, rdx
0x14002248f  jz      loc_1400223D7
0x140022495  mov     eax, [rbx+0Ch]
0x140022498  xor     edi, edi
0x14002249a  add     rax, [rbx+10h]
0x14002249e  cmp     rdx, rax
0x1400224a1  jb      short loc_140022478
0x1400224a3  cmp     [rbx+8], edi
0x1400224a6  jz      loc_1400223D7
0x1400224ac  jmp     short loc_140022478
0x1400224ae  cmp     eax, 80000006h
0x1400224b3  jnz     short loc_1400224C3
0x1400224b5  mov     eax, [rbx+0Ch]
0x1400224b8  add     rax, [rbx+10h]
0x1400224bc  jmp     short loc_140022474
0x1400224be  mov     [rbx+8], edi
0x1400224c1  jmp     short loc_14002247A
0x1400224c3  cmp     eax, 0C000000Fh
0x1400224c8  cmovnz  edi, eax
0x1400224cb  jmp     short loc_1400224B5
```
