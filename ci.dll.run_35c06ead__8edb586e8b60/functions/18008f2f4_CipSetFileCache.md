# CipSetFileCache

- ea: `0x18008f2f4`
- end: `0x18008f66a`
- name: `CipSetFileCache`
- size: `886`
- prototype: `__int64 __usercall@<rax>(PFILE_OBJECT FileObject@<rcx>, int, int, __int64, int, int, int, __int64, __int64, __int16, int, __int64)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800644b0`
- `0x18008d750`
- `0x1800c77d0`
- `0x1800e5fd0`

## callees

- `0x180060d48`
- `0x18008f2f4`
- `0x1800902d0`
- `0x180090588`
- `0x1800912c0`
- `0x180091eb8`
- `0x1800d350c`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x18008f403`
- `ntoskrnl!PsGetCurrentProcess` at `0x18008f403`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x18008f472`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x18008f472`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18008f623`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18008f623`
- `ntoskrnl!PsGetProcessProtection` at `0x18008f412`
- `ntoskrnl!PsGetProcessProtection` at `0x18008f412`
- `ntoskrnl!FsRtlKernelFsControlFile` at `0x18008f4bd`
- `ntoskrnl!FsRtlKernelFsControlFile` at `0x18008f53b`
- `ntoskrnl!FsRtlKernelFsControlFile` at `0x18008f4bd`
- `ntoskrnl!FsRtlKernelFsControlFile` at `0x18008f53b`
- `ntoskrnl!FsRtlSetKernelEaFile` at `0x18008f603`
- `ntoskrnl!FsRtlSetKernelEaFile` at `0x18008f603`

## pseudocode

```c
__int64 __fastcall CipSetFileCache(
        PFILE_OBJECT FileObject,
        int a2,
        char a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7,
        int a8,
        int a9,
        int a10,
        __int64 a11,
        __int64 a12,
        __int16 a13,
        int a14,
        __int64 a15)
{
  int FileAttributes; // ebx
  int v18; // r8d
  char v19; // di
  char v20; // r14
  int v21; // r12d
  int VolumeFlags; // r12d
  __int64 CurrentProcess; // rax
  char ProcessProtection; // al
  PVOID v25; // r15
  int v26; // ecx
  int v28; // [rsp+40h] [rbp-51h] BYREF
  unsigned int v29; // [rsp+44h] [rbp-4Dh] BYREF
  __int64 v30; // [rsp+48h] [rbp-49h] BYREF
  __int64 v31; // [rsp+50h] [rbp-41h] BYREF
  int v32; // [rsp+58h] [rbp-39h]
  int v33; // [rsp+5Ch] [rbp-35h]
  __int64 v34; // [rsp+60h] [rbp-31h]
  int v35; // [rsp+68h] [rbp-29h]
  int v36; // [rsp+6Ch] [rbp-25h]
  __int64 v37; // [rsp+70h] [rbp-21h]
  __int16 v38; // [rsp+78h] [rbp-19h]
  __int16 v39; // [rsp+7Ah] [rbp-17h]
  int v40; // [rsp+7Ch] [rbp-15h]
  __int128 v41; // [rsp+80h] [rbp-11h]

  FileAttributes = 0;
  v30 = 0;
  v28 = 0;
  v29 = 0;
  a10 = 0;
  v39 = 0;
  v41 = 0;
  CiLogFileEvent(&FileObject->FileName, CiSetFileCacheStart);
  v19 = 2;
  if ( (unsigned __int8)a3 >= 2u )
  {
    v20 = 0;
    VolumeFlags = CipGetVolumeFlags(FileObject);
    if ( (FileObject->DeviceObject->Flags & 0x100) == 0 )
    {
      FileAttributes = CipGetFileAttributes(FileObject, &a10);
      if ( FileAttributes < 0 )
        goto LABEL_3;
      if ( VolumeFlags < 0 )
      {
        FileAttributes = VolumeFlags;
        v19 = 3;
        goto LABEL_3;
      }
    }
    if ( FileObject->SharedWrite )
    {
      v19 = 5;
LABEL_10:
      FileAttributes = -1073741757;
      goto LABEL_3;
    }
    if ( FileObject->WriteAccess )
    {
      CurrentProcess = a11;
      if ( !a11 )
        CurrentProcess = PsGetCurrentProcess();
      if ( (ProcessProtection = PsGetProcessProtection(CurrentProcess), ProcessProtection != 81)
        && ProcessProtection != 33
        || (*((_DWORD *)g_CipWhichLevelComparisons + (a3 & 0xF)) & 0x100) == 0
        || a3 == 7 )
      {
        v19 = 6;
        v20 = ProcessProtection;
        goto LABEL_10;
      }
    }
    v25 = ExAllocateFromPagedLookasideList(&g_CiEaCacheLookasideList);
    v19 = 8;
    if ( !v25 )
    {
      FileAttributes = -1073741801;
      goto LABEL_3;
    }
    FileAttributes = FsRtlKernelFsControlFile(FileObject, 590063, 0, 0, &v30, 8, &v28);
    if ( FileAttributes == -1073741128 )
    {
      if ( g_CiIsWinPE
        || !_bittest(&g_CiOptions, 8u) && !_bittest((const signed __int32 *)&FileObject->DeviceObject->Flags, 8u) )
      {
        FileAttributes = -1073741637;
LABEL_27:
        v19 = 9;
        goto LABEL_28;
      }
      FileAttributes = CipEnableJournalingAlways(FileObject);
      if ( FileAttributes < 0 )
        goto LABEL_27;
      FileAttributes = FsRtlKernelFsControlFile(FileObject, 590063, 0, 0, &v30, 8, &v28);
    }
    if ( FileAttributes >= 0 )
    {
      v31 = a4;
      v32 = a5;
      v33 = a6;
      v34 = a7;
      v35 = a8;
      v36 = a9;
      v37 = a12;
      v38 = a13;
      v40 = a14;
      if ( a15 )
      {
        v26 = *(_DWORD *)(a15 + 4);
        if ( v26 )
        {
          DWORD2(v41) = *(_DWORD *)(a15 + 4);
          *(_QWORD *)&v41 = a15 + 8;
        }
      }
      v21 = a2;
      LOBYTE(v26) = a3;
      FileAttributes = CiBuildEaCacheContents(
                         v26,
                         a2,
                         (_DWORD)FileObject,
                         (unsigned int)&v31,
                         (__int64)v25,
                         664,
                         (__int64)&v29);
      if ( FileAttributes >= 0 )
      {
        v19 = 0;
        FileAttributes = FsRtlSetKernelEaFile(FileObject, v25, v29);
        if ( FileAttributes < 0 )
          v19 = 12;
      }
      else
      {
        v19 = 11;
      }
      goto LABEL_39;
    }
    v19 = 10;
LABEL_28:
    v21 = a2;
LABEL_39:
    ExFreeToPagedLookasideList(&g_CiEaCacheLookasideList, v25);
    goto LABEL_40;
  }
  v19 = 1;
  v20 = a3;
LABEL_3:
  v21 = a2;
LABEL_40:
  LOBYTE(v18) = a3;
  CiLogCacheEvent(FileAttributes, 0, v18, v21, v19, v20, &CiSetFileCacheComplete);
  return (unsigned int)FileAttributes;
}

```

## disassembly

```asm
0x18008f2f4  mov     [rsp-8+arg_18], r9
0x18008f2f9  mov     [rsp-8+arg_8], edx
0x18008f2fd  push    rbp
0x18008f2fe  push    rbx
0x18008f2ff  push    rsi
0x18008f300  push    rdi
0x18008f301  push    r12
0x18008f303  push    r13
0x18008f305  push    r14
0x18008f307  push    r15
0x18008f309  lea     rbp, [rsp-7]
0x18008f30e  sub     rsp, 98h
0x18008f315  xor     ebx, ebx
0x18008f317  movzx   r13d, r8b
0x18008f31b  mov     rsi, rcx
0x18008f31e  mov     [rbp+3Fh+var_88], rbx
0x18008f322  xorps   xmm0, xmm0
0x18008f325  mov     [rbp+3Fh+var_90], ebx
0x18008f328  add     rcx, 58h ; 'X'
0x18008f32c  mov     [rbp+3Fh+var_8C], ebx
0x18008f32f  lea     rdx, CiSetFileCacheStart
0x18008f336  mov     [rbp+3Fh+arg_48], ebx
0x18008f33c  mov     [rbp+3Fh+var_56], bx
0x18008f340  movdqa  [rbp+3Fh+var_50], xmm0
0x18008f345  mov     [rbp+3Fh+arg_0], ebx
0x18008f348  mov     [rbp+3Fh+arg_10], bl
0x18008f34b  call    CiLogFileEvent
0x18008f350  lea     edi, [rbx+2]
0x18008f353  cmp     r13b, dil
0x18008f356  jnb     short loc_18008F367
0x18008f358  lea     edi, [rbx+1]
0x18008f35b  mov     r14d, r13d
0x18008f35e  mov     r12d, [rbp+3Fh+arg_8]
0x18008f362  jmp     loc_18008F62F
0x18008f367  lea     r8, [rbp+3Fh+arg_10]
0x18008f36b  mov     rcx, rsi; FileObject
0x18008f36e  lea     rdx, [rbp+3Fh+arg_0]
0x18008f372  mov     r14, rbx
0x18008f375  call    CipGetVolumeFlags
0x18008f37a  mov     r15d, [rbp+3Fh+arg_0]
0x18008f37e  mov     r12d, eax
0x18008f381  mov     rax, [rsi+8]
0x18008f385  test    dword ptr [rax+30h], 100h
0x18008f38c  jnz     short loc_18008F3DE
0x18008f38e  lea     rdx, [rbp+3Fh+arg_48]
0x18008f395  mov     rcx, rsi
0x18008f398  call    CipGetFileAttributes
0x18008f39d  mov     ebx, eax
0x18008f39f  test    eax, eax
0x18008f3a1  js      short loc_18008F35E
0x18008f3a3  xor     ebx, ebx
0x18008f3a5  test    r12d, r12d
0x18008f3a8  jns     short loc_18008F3B4
0x18008f3aa  mov     ebx, r12d
0x18008f3ad  mov     edi, 3
0x18008f3b2  jmp     short loc_18008F35E
0x18008f3b4  mov     edx, [rbp+3Fh+arg_48]
0x18008f3ba  bt      r15d, 11h
0x18008f3bf  setb    cl
0x18008f3c2  bt      edx, 0Eh
0x18008f3c6  setb    al
0x18008f3c9  test    al, cl
0x18008f3cb  jz      short loc_18008F3DE
0x18008f3cd  mov     r14, r15
0x18008f3d0  mov     edi, 4
0x18008f3d5  shl     r14, 20h
0x18008f3d9  or      r14, rdx
0x18008f3dc  jmp     short loc_18008F35E
0x18008f3de  cmp     [rsi+4Eh], bl
0x18008f3e1  jz      short loc_18008F3F2
0x18008f3e3  mov     edi, 5
0x18008f3e8  mov     ebx, 0C0000043h
0x18008f3ed  jmp     loc_18008F35E
0x18008f3f2  cmp     [rsi+4Bh], bl
0x18008f3f5  jz      short loc_18008F44D
0x18008f3f7  mov     rax, [rbp+3Fh+arg_50]
0x18008f3fe  test    rax, rax
0x18008f401  jnz     short loc_18008F40F
0x18008f403  call    cs:__imp_PsGetCurrentProcess
0x18008f40a  nop     dword ptr [rax+rax+00h]
0x18008f40f  mov     rcx, rax
0x18008f412  call    cs:__imp_PsGetProcessProtection
0x18008f419  nop     dword ptr [rax+rax+00h]
0x18008f41e  cmp     al, 51h ; 'Q'
0x18008f420  jz      short loc_18008F426
0x18008f422  cmp     al, 21h ; '!'
0x18008f424  jnz     short loc_18008F442
0x18008f426  mov     rcx, cs:g_CipWhichLevelComparisons
0x18008f42d  mov     rdx, r13
0x18008f430  and     edx, 0Fh
0x18008f433  test    dword ptr [rcx+rdx*4], 100h
0x18008f43a  jz      short loc_18008F442
0x18008f43c  cmp     r13b, 7
0x18008f440  jnz     short loc_18008F44D
0x18008f442  mov     edi, 6
0x18008f447  movzx   r14d, al
0x18008f44b  jmp     short loc_18008F3E8
0x18008f44d  test    r12d, r12d
0x18008f450  js      short loc_18008F46B
0x18008f452  bt      r15d, 13h
0x18008f457  jnb     short loc_18008F46B
0x18008f459  mov     edi, 0Dh
0x18008f45e  mov     r14, r15
0x18008f461  mov     ebx, 0C00000A2h
0x18008f466  jmp     loc_18008F35E
0x18008f46b  lea     rcx, g_CiEaCacheLookasideList; Lookaside
0x18008f472  call    cs:__imp_ExAllocateFromPagedLookasideList
0x18008f479  nop     dword ptr [rax+rax+00h]
0x18008f47e  mov     r15, rax
0x18008f481  mov     edi, 8
0x18008f486  test    rax, rax
0x18008f489  jnz     short loc_18008F495
0x18008f48b  mov     ebx, 0C0000017h
0x18008f490  jmp     loc_18008F35E
0x18008f495  lea     rax, [rbp+3Fh+var_90]
0x18008f499  mov     r12d, 900EFh
0x18008f49f  mov     [rsp+0D0h+EventDescriptor], rax
0x18008f4a4  xor     r9d, r9d
0x18008f4a7  lea     rax, [rbp+3Fh+var_88]
0x18008f4ab  mov     dword ptr [rsp+0D0h+var_A8], edi
0x18008f4af  xor     r8d, r8d
0x18008f4b2  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18008f4b7  mov     edx, r12d
0x18008f4ba  mov     rcx, rsi
0x18008f4bd  call    cs:__imp_FsRtlKernelFsControlFile
0x18008f4c4  nop     dword ptr [rax+rax+00h]
0x18008f4c9  mov     ebx, eax
0x18008f4cb  cmp     eax, 0C00002B8h
0x18008f4d0  jnz     short loc_18008F549
0x18008f4d2  cmp     cs:g_CiIsWinPE, r14b
0x18008f4d9  jz      short loc_18008F4E2
0x18008f4db  mov     ebx, 0C00000BBh
0x18008f4e0  jmp     short loc_18008F50B
0x18008f4e2  bt      cs:g_CiOptions, 8
0x18008f4ea  jb      short loc_18008F4FD
0x18008f4ec  cmp     [rbp+3Fh+arg_10], r14b
0x18008f4f0  jnz     short loc_18008F4FD
0x18008f4f2  mov     rax, [rsi+8]
0x18008f4f6  bt      dword ptr [rax+30h], 8
0x18008f4fb  jnb     short loc_18008F4DB
0x18008f4fd  mov     rcx, rsi
0x18008f500  call    CipEnableJournalingAlways
0x18008f505  mov     ebx, eax
0x18008f507  test    eax, eax
0x18008f509  jns     short loc_18008F519
0x18008f50b  mov     edi, 9
0x18008f510  mov     r12d, [rbp+3Fh+arg_8]
0x18008f514  jmp     loc_18008F619
0x18008f519  lea     rax, [rbp+3Fh+var_90]
0x18008f51d  xor     r9d, r9d
0x18008f520  mov     [rsp+0D0h+EventDescriptor], rax
0x18008f525  xor     r8d, r8d
0x18008f528  lea     rax, [rbp+3Fh+var_88]
0x18008f52c  mov     dword ptr [rsp+0D0h+var_A8], edi
0x18008f530  mov     edx, r12d
0x18008f533  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18008f538  mov     rcx, rsi
0x18008f53b  call    cs:__imp_FsRtlKernelFsControlFile
0x18008f542  nop     dword ptr [rax+rax+00h]
0x18008f547  mov     ebx, eax
0x18008f549  test    ebx, ebx
0x18008f54b  jns     short loc_18008F554
0x18008f54d  mov     edi, 0Ah
0x18008f552  jmp     short loc_18008F510
0x18008f554  mov     rax, [rbp+3Fh+arg_18]
0x18008f558  mov     [rbp+3Fh+var_80], rax
0x18008f55c  mov     eax, [rbp+3Fh+arg_20]
0x18008f55f  mov     [rbp+3Fh+var_78], eax
0x18008f562  mov     eax, [rbp+3Fh+arg_28]
0x18008f565  mov     [rbp+3Fh+var_74], eax
0x18008f568  mov     rax, [rbp+3Fh+arg_30]
0x18008f56c  mov     [rbp+3Fh+var_70], rax
0x18008f570  mov     eax, [rbp+3Fh+arg_38]
0x18008f576  mov     [rbp+3Fh+var_68], eax
0x18008f579  mov     eax, [rbp+3Fh+arg_40]
0x18008f57f  mov     [rbp+3Fh+var_64], eax
0x18008f582  mov     rax, [rbp+3Fh+arg_58]
0x18008f589  mov     [rbp+3Fh+var_60], rax
0x18008f58d  movzx   eax, [rbp+3Fh+arg_60]
0x18008f594  mov     [rbp+3Fh+var_58], ax
0x18008f598  mov     eax, [rbp+3Fh+arg_68]
0x18008f59e  mov     [rbp+3Fh+var_54], eax
0x18008f5a1  mov     rax, [rbp+3Fh+arg_70]
0x18008f5a8  test    rax, rax
0x18008f5ab  jz      short loc_18008F5BE
0x18008f5ad  mov     ecx, [rax+4]
0x18008f5b0  test    ecx, ecx
0x18008f5b2  jz      short loc_18008F5BE
0x18008f5b4  add     rax, rdi
0x18008f5b7  mov     dword ptr [rbp+3Fh+var_50+8], ecx
0x18008f5ba  mov     qword ptr [rbp+3Fh+var_50], rax
0x18008f5be  mov     r12d, [rbp+3Fh+arg_8]
0x18008f5c2  lea     rax, [rbp+3Fh+var_8C]
0x18008f5c6  mov     [rsp+0D0h+EventDescriptor], rax
0x18008f5cb  lea     r9, [rbp+3Fh+var_80]
0x18008f5cf  mov     dword ptr [rsp+0D0h+var_A8], 298h
0x18008f5d7  mov     r8, rsi
0x18008f5da  mov     edx, r12d
0x18008f5dd  mov     qword ptr [rsp+0D0h+var_B0], r15
0x18008f5e2  mov     cl, r13b
0x18008f5e5  call    CiBuildEaCacheContents
0x18008f5ea  mov     ebx, eax
0x18008f5ec  test    eax, eax
0x18008f5ee  jns     short loc_18008F5F7
0x18008f5f0  mov     edi, 0Bh
0x18008f5f5  jmp     short loc_18008F619
0x18008f5f7  mov     r8d, [rbp+3Fh+var_8C]
0x18008f5fb  mov     rdx, r15
0x18008f5fe  mov     rcx, rsi
0x18008f601  xor     edi, edi
0x18008f603  call    cs:__imp_FsRtlSetKernelEaFile
0x18008f60a  nop     dword ptr [rax+rax+00h]
0x18008f60f  mov     ebx, eax
0x18008f611  lea     eax, [rdi+0Ch]
0x18008f614  test    ebx, ebx
0x18008f616  cmovs   edi, eax
0x18008f619  mov     rdx, r15; Entry
0x18008f61c  lea     rcx, g_CiEaCacheLookasideList; Lookaside
0x18008f623  call    cs:__imp_ExFreeToPagedLookasideList
0x18008f62a  nop     dword ptr [rax+rax+00h]
0x18008f62f  lea     rax, CiSetFileCacheComplete
0x18008f636  mov     r9d, r12d; int
0x18008f639  mov     [rsp+0D0h+EventDescriptor], rax; EventDescriptor
0x18008f63e  mov     r8b, r13b; int
0x18008f641  mov     qword ptr [rsp+0D0h+var_A8], r14; char
0x18008f646  xor     edx, edx; int
0x18008f648  mov     ecx, ebx; int
0x18008f64a  mov     dword ptr [rsp+0D0h+var_B0], edi; char
0x18008f64e  call    CiLogCacheEvent
0x18008f653  mov     eax, ebx
0x18008f655  add     rsp, 98h
0x18008f65c  pop     r15
0x18008f65e  pop     r14
0x18008f660  pop     r13
0x18008f662  pop     r12
0x18008f664  pop     rdi
0x18008f665  pop     rsi
0x18008f666  pop     rbx
0x18008f667  pop     rbp
0x18008f668  retn
```
