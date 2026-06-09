# LuafvQueryDirectoryIfNeeded

- ea: `0x140022354`
- end: `0x14002247d`
- name: `LuafvQueryDirectoryIfNeeded`
- size: `297`
- prototype: `NTSTATUS __fastcall(PFLT_INSTANCE Instance, __int64, BOOLEAN, FILE_INFORMATION_CLASS, PUNICODE_STRING FileName, BOOLEAN RestartScan)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14002205c`

## callees

- `0x140022354`

## import_xrefs

- `ntoskrnl!IoFileObjectType` at `0x140022387`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400223af`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400223af`
- `ntoskrnl!ObfDereferenceObject` at `0x14002240d`
- `ntoskrnl!ObfDereferenceObject` at `0x14002240d`
- `FLTMGR!FltQueryDirectoryFile` at `0x1400223f9`
- `FLTMGR!FltQueryDirectoryFile` at `0x1400223f9`

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
0x140022354  push    rbx
0x140022356  push    rbp
0x140022357  push    rsi
0x140022358  push    rdi
0x140022359  push    r14
0x14002235b  push    r15
0x14002235d  sub     rsp, 68h
0x140022361  mov     sil, [rsp+98h+arg_28]
0x140022369  mov     ebp, r9d
0x14002236c  mov     [rsp+98h+var_48], 0
0x140022375  mov     r14b, r8b
0x140022378  mov     rbx, rdx
0x14002237b  mov     r15, rcx
0x14002237e  test    sil, sil
0x140022381  jz      loc_140022438
0x140022387  mov     r8, cs:__imp_IoFileObjectType
0x14002238e  lea     rax, [rsp+98h+var_48]
0x140022393  mov     rcx, [rbx]; Handle
0x140022396  xor     r9d, r9d; AccessMode
0x140022399  mov     [rsp+98h+HandleInformation], 0; HandleInformation
0x1400223a2  mov     edx, 100001h; DesiredAccess
0x1400223a7  mov     [rsp+98h+Object], rax; Object
0x1400223ac  mov     r8, [r8]; ObjectType
0x1400223af  call    cs:__imp_ObReferenceObjectByHandle
0x1400223b6  nop     dword ptr [rax+rax+00h]
0x1400223bb  mov     edi, eax
0x1400223bd  test    eax, eax
0x1400223bf  js      loc_14002246E
0x1400223c5  mov     rax, [rsp+98h+arg_20]
0x1400223cd  mov     rcx, r15; Instance
0x1400223d0  mov     r9d, [rbx+0Ch]; Length
0x1400223d4  mov     r8, [rbx+10h]; FileInformation
0x1400223d8  mov     rdx, [rsp+98h+var_48]; FileObject
0x1400223dd  mov     [rsp+98h+LengthReturned], 0; LengthReturned
0x1400223e6  mov     [rsp+98h+RestartScan], sil; RestartScan
0x1400223eb  mov     [rsp+98h+FileName], rax; FileName
0x1400223f0  mov     byte ptr [rsp+98h+HandleInformation], r14b; ReturnSingleEntry
0x1400223f5  mov     dword ptr [rsp+98h+Object], ebp; FileInformationClass
0x1400223f9  call    cs:__imp_FltQueryDirectoryFile
0x140022400  nop     dword ptr [rax+rax+00h]
0x140022405  mov     rcx, [rsp+98h+var_48]; Object
0x14002240a  mov     [rbx+8], eax
0x14002240d  call    cs:__imp_ObfDereferenceObject
0x140022414  nop     dword ptr [rax+rax+00h]
0x140022419  mov     eax, [rbx+8]
0x14002241c  test    eax, eax
0x14002241e  js      short loc_14002245E
0x140022420  mov     rax, [rbx+10h]
0x140022424  mov     [rbx+18h], rax
0x140022428  mov     eax, edi
0x14002242a  add     rsp, 68h
0x14002242e  pop     r15
0x140022430  pop     r14
0x140022432  pop     rdi
0x140022433  pop     rsi
0x140022434  pop     rbp
0x140022435  pop     rbx
0x140022436  retn
0x140022438  mov     rdx, [rdx+18h]
0x14002243c  test    rdx, rdx
0x14002243f  jz      loc_140022387
0x140022445  mov     eax, [rbx+0Ch]
0x140022448  xor     edi, edi
0x14002244a  add     rax, [rbx+10h]
0x14002244e  cmp     rdx, rax
0x140022451  jb      short loc_140022428
0x140022453  cmp     [rbx+8], edi
0x140022456  jz      loc_140022387
0x14002245c  jmp     short loc_140022428
0x14002245e  cmp     eax, 80000006h
0x140022463  jnz     short loc_140022473
0x140022465  mov     eax, [rbx+0Ch]
0x140022468  add     rax, [rbx+10h]
0x14002246c  jmp     short loc_140022424
0x14002246e  mov     [rbx+8], edi
0x140022471  jmp     short loc_14002242A
0x140022473  cmp     eax, 0C000000Fh
0x140022478  cmovnz  edi, eax
0x14002247b  jmp     short loc_140022465
```
