# CipSetFileCache

- ea: `0x18009ca38`
- end: `0x18009cdae`
- name: `CipSetFileCache`
- size: `886`
- prototype: `__int64 __usercall@<rax>(PFILE_OBJECT FileObject@<rcx>, int, int, __int64, int, int, int, __int64, __int64, __int16, int, __int64)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180063a10`
- `0x180095950`
- `0x1800c6340`
- `0x1800e55e0`

## callees

- `0x1800605f4`
- `0x18009bd64`
- `0x18009c8b0`
- `0x18009ca38`
- `0x18009da14`
- `0x18009dccc`
- `0x1800d203c`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x18009cb47`
- `ntoskrnl!PsGetCurrentProcess` at `0x18009cb47`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x18009cbb6`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x18009cbb6`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18009cd67`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18009cd67`
- `ntoskrnl!PsGetProcessProtection` at `0x18009cb56`
- `ntoskrnl!PsGetProcessProtection` at `0x18009cb56`
- `ntoskrnl!FsRtlKernelFsControlFile` at `0x18009cc01`
- `ntoskrnl!FsRtlKernelFsControlFile` at `0x18009cc7f`
- `ntoskrnl!FsRtlKernelFsControlFile` at `0x18009cc01`
- `ntoskrnl!FsRtlKernelFsControlFile` at `0x18009cc7f`
- `ntoskrnl!FsRtlSetKernelEaFile` at `0x18009cd47`
- `ntoskrnl!FsRtlSetKernelEaFile` at `0x18009cd47`

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
        unsigned int a10,
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
  __int64 v22; // rdx
  int VolumeFlags; // r12d
  __int64 CurrentProcess; // rax
  char ProcessProtection; // al
  PVOID v26; // r15
  int v27; // ecx
  int v29; // [rsp+40h] [rbp-51h] BYREF
  unsigned int v30; // [rsp+44h] [rbp-4Dh] BYREF
  __int64 v31; // [rsp+48h] [rbp-49h] BYREF
  __int64 v32; // [rsp+50h] [rbp-41h] BYREF
  int v33; // [rsp+58h] [rbp-39h]
  int v34; // [rsp+5Ch] [rbp-35h]
  __int64 v35; // [rsp+60h] [rbp-31h]
  int v36; // [rsp+68h] [rbp-29h]
  int v37; // [rsp+6Ch] [rbp-25h]
  __int64 v38; // [rsp+70h] [rbp-21h]
  __int16 v39; // [rsp+78h] [rbp-19h]
  __int16 v40; // [rsp+7Ah] [rbp-17h]
  int v41; // [rsp+7Ch] [rbp-15h]
  __int128 v42; // [rsp+80h] [rbp-11h]

  FileAttributes = 0;
  v31 = 0;
  v29 = 0;
  v30 = 0;
  a10 = 0;
  v40 = 0;
  v42 = 0;
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
      v22 = a10;
    }
    if ( FileObject->SharedWrite )
    {
      v19 = 5;
LABEL_11:
      FileAttributes = -1073741757;
      goto LABEL_3;
    }
    if ( FileObject->WriteAccess )
    {
      CurrentProcess = a11;
      if ( !a11 )
        CurrentProcess = PsGetCurrentProcess();
      if ( (ProcessProtection = PsGetProcessProtection(CurrentProcess, v22), ProcessProtection != 81)
        && ProcessProtection != 33
        || (*((_DWORD *)g_CipWhichLevelComparisons + (a3 & 0xF)) & 0x100) == 0
        || a3 == 7 )
      {
        v19 = 6;
        v20 = ProcessProtection;
        goto LABEL_11;
      }
    }
    v26 = ExAllocateFromPagedLookasideList(&g_CiEaCacheLookasideList);
    v19 = 8;
    if ( !v26 )
    {
      FileAttributes = -1073741801;
      goto LABEL_3;
    }
    FileAttributes = FsRtlKernelFsControlFile(FileObject, 590063, 0, 0, &v31, 8, &v29);
    if ( FileAttributes == -1073741128 )
    {
      if ( g_CiIsWinPE
        || !_bittest(&g_CiOptions, 8u) && !_bittest((const signed __int32 *)&FileObject->DeviceObject->Flags, 8u) )
      {
        FileAttributes = -1073741637;
LABEL_28:
        v19 = 9;
        goto LABEL_29;
      }
      FileAttributes = CipEnableJournalingAlways(FileObject);
      if ( FileAttributes < 0 )
        goto LABEL_28;
      FileAttributes = FsRtlKernelFsControlFile(FileObject, 590063, 0, 0, &v31, 8, &v29);
    }
    if ( FileAttributes >= 0 )
    {
      v32 = a4;
      v33 = a5;
      v34 = a6;
      v35 = a7;
      v36 = a8;
      v37 = a9;
      v38 = a12;
      v39 = a13;
      v41 = a14;
      if ( a15 )
      {
        v27 = *(_DWORD *)(a15 + 4);
        if ( v27 )
        {
          DWORD2(v42) = *(_DWORD *)(a15 + 4);
          *(_QWORD *)&v42 = a15 + 8;
        }
      }
      v21 = a2;
      LOBYTE(v27) = a3;
      FileAttributes = CiBuildEaCacheContents(
                         v27,
                         a2,
                         (_DWORD)FileObject,
                         (unsigned int)&v32,
                         (__int64)v26,
                         664,
                         (__int64)&v30);
      if ( FileAttributes >= 0 )
      {
        v19 = 0;
        FileAttributes = FsRtlSetKernelEaFile(FileObject, v26, v30);
        if ( FileAttributes < 0 )
          v19 = 12;
      }
      else
      {
        v19 = 11;
      }
      goto LABEL_40;
    }
    v19 = 10;
LABEL_29:
    v21 = a2;
LABEL_40:
    ExFreeToPagedLookasideList(&g_CiEaCacheLookasideList, v26);
    goto LABEL_41;
  }
  v19 = 1;
  v20 = a3;
LABEL_3:
  v21 = a2;
LABEL_41:
  LOBYTE(v18) = a3;
  CiLogCacheEvent(FileAttributes, 0, v18, v21, v19, v20, &CiSetFileCacheComplete);
  return (unsigned int)FileAttributes;
}

```

## disassembly

```asm
0x18009ca38  mov     [rsp-8+arg_18], r9
0x18009ca3d  mov     [rsp-8+arg_8], edx
0x18009ca41  push    rbp
0x18009ca42  push    rbx
0x18009ca43  push    rsi
0x18009ca44  push    rdi
0x18009ca45  push    r12
0x18009ca47  push    r13
0x18009ca49  push    r14
0x18009ca4b  push    r15
0x18009ca4d  lea     rbp, [rsp-7]
0x18009ca52  sub     rsp, 98h
0x18009ca59  xor     ebx, ebx
0x18009ca5b  movzx   r13d, r8b
0x18009ca5f  mov     rsi, rcx
0x18009ca62  mov     [rbp+3Fh+var_88], rbx
0x18009ca66  xorps   xmm0, xmm0
0x18009ca69  mov     [rbp+3Fh+var_90], ebx
0x18009ca6c  add     rcx, 58h ; 'X'
0x18009ca70  mov     [rbp+3Fh+var_8C], ebx
0x18009ca73  lea     rdx, CiSetFileCacheStart
0x18009ca7a  mov     [rbp+3Fh+arg_48], ebx
0x18009ca80  mov     [rbp+3Fh+var_56], bx
0x18009ca84  movdqa  [rbp+3Fh+var_50], xmm0
0x18009ca89  mov     [rbp+3Fh+arg_0], ebx
0x18009ca8c  mov     [rbp+3Fh+arg_10], bl
0x18009ca8f  call    CiLogFileEvent
0x18009ca94  lea     edi, [rbx+2]
0x18009ca97  cmp     r13b, dil
0x18009ca9a  jnb     short loc_18009CAAB
0x18009ca9c  lea     edi, [rbx+1]
0x18009ca9f  mov     r14d, r13d
0x18009caa2  mov     r12d, [rbp+3Fh+arg_8]
0x18009caa6  jmp     loc_18009CD73
0x18009caab  lea     r8, [rbp+3Fh+arg_10]
0x18009caaf  mov     rcx, rsi; FileObject
0x18009cab2  lea     rdx, [rbp+3Fh+arg_0]
0x18009cab6  mov     r14, rbx
0x18009cab9  call    CipGetVolumeFlags
0x18009cabe  mov     r15d, [rbp+3Fh+arg_0]
0x18009cac2  mov     r12d, eax
0x18009cac5  mov     rax, [rsi+8]
0x18009cac9  test    dword ptr [rax+30h], 100h
0x18009cad0  jnz     short loc_18009CB22
0x18009cad2  lea     rdx, [rbp+3Fh+arg_48]
0x18009cad9  mov     rcx, rsi
0x18009cadc  call    CipGetFileAttributes
0x18009cae1  mov     ebx, eax
0x18009cae3  test    eax, eax
0x18009cae5  js      short loc_18009CAA2
0x18009cae7  xor     ebx, ebx
0x18009cae9  test    r12d, r12d
0x18009caec  jns     short loc_18009CAF8
0x18009caee  mov     ebx, r12d
0x18009caf1  mov     edi, 3
0x18009caf6  jmp     short loc_18009CAA2
0x18009caf8  mov     edx, [rbp+3Fh+arg_48]
0x18009cafe  bt      r15d, 11h
0x18009cb03  setb    cl
0x18009cb06  bt      edx, 0Eh
0x18009cb0a  setb    al
0x18009cb0d  test    al, cl
0x18009cb0f  jz      short loc_18009CB22
0x18009cb11  mov     r14, r15
0x18009cb14  mov     edi, 4
0x18009cb19  shl     r14, 20h
0x18009cb1d  or      r14, rdx
0x18009cb20  jmp     short loc_18009CAA2
0x18009cb22  cmp     [rsi+4Eh], bl
0x18009cb25  jz      short loc_18009CB36
0x18009cb27  mov     edi, 5
0x18009cb2c  mov     ebx, 0C0000043h
0x18009cb31  jmp     loc_18009CAA2
0x18009cb36  cmp     [rsi+4Bh], bl
0x18009cb39  jz      short loc_18009CB91
0x18009cb3b  mov     rax, [rbp+3Fh+arg_50]
0x18009cb42  test    rax, rax
0x18009cb45  jnz     short loc_18009CB53
0x18009cb47  call    cs:__imp_PsGetCurrentProcess
0x18009cb4e  nop     dword ptr [rax+rax+00h]
0x18009cb53  mov     rcx, rax
0x18009cb56  call    cs:__imp_PsGetProcessProtection
0x18009cb5d  nop     dword ptr [rax+rax+00h]
0x18009cb62  cmp     al, 51h ; 'Q'
0x18009cb64  jz      short loc_18009CB6A
0x18009cb66  cmp     al, 21h ; '!'
0x18009cb68  jnz     short loc_18009CB86
0x18009cb6a  mov     rcx, cs:g_CipWhichLevelComparisons
0x18009cb71  mov     rdx, r13
0x18009cb74  and     edx, 0Fh
0x18009cb77  test    dword ptr [rcx+rdx*4], 100h
0x18009cb7e  jz      short loc_18009CB86
0x18009cb80  cmp     r13b, 7
0x18009cb84  jnz     short loc_18009CB91
0x18009cb86  mov     edi, 6
0x18009cb8b  movzx   r14d, al
0x18009cb8f  jmp     short loc_18009CB2C
0x18009cb91  test    r12d, r12d
0x18009cb94  js      short loc_18009CBAF
0x18009cb96  bt      r15d, 13h
0x18009cb9b  jnb     short loc_18009CBAF
0x18009cb9d  mov     edi, 0Dh
0x18009cba2  mov     r14, r15
0x18009cba5  mov     ebx, 0C00000A2h
0x18009cbaa  jmp     loc_18009CAA2
0x18009cbaf  lea     rcx, g_CiEaCacheLookasideList; Lookaside
0x18009cbb6  call    cs:__imp_ExAllocateFromPagedLookasideList
0x18009cbbd  nop     dword ptr [rax+rax+00h]
0x18009cbc2  mov     r15, rax
0x18009cbc5  mov     edi, 8
0x18009cbca  test    rax, rax
0x18009cbcd  jnz     short loc_18009CBD9
0x18009cbcf  mov     ebx, 0C0000017h
0x18009cbd4  jmp     loc_18009CAA2
0x18009cbd9  lea     rax, [rbp+3Fh+var_90]
0x18009cbdd  mov     r12d, 900EFh
0x18009cbe3  mov     [rsp+0D0h+EventDescriptor], rax
0x18009cbe8  xor     r9d, r9d
0x18009cbeb  lea     rax, [rbp+3Fh+var_88]
0x18009cbef  mov     dword ptr [rsp+0D0h+var_A8], edi
0x18009cbf3  xor     r8d, r8d
0x18009cbf6  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18009cbfb  mov     edx, r12d
0x18009cbfe  mov     rcx, rsi
0x18009cc01  call    cs:__imp_FsRtlKernelFsControlFile
0x18009cc08  nop     dword ptr [rax+rax+00h]
0x18009cc0d  mov     ebx, eax
0x18009cc0f  cmp     eax, 0C00002B8h
0x18009cc14  jnz     short loc_18009CC8D
0x18009cc16  cmp     cs:g_CiIsWinPE, r14b
0x18009cc1d  jz      short loc_18009CC26
0x18009cc1f  mov     ebx, 0C00000BBh
0x18009cc24  jmp     short loc_18009CC4F
0x18009cc26  bt      cs:g_CiOptions, 8
0x18009cc2e  jb      short loc_18009CC41
0x18009cc30  cmp     [rbp+3Fh+arg_10], r14b
0x18009cc34  jnz     short loc_18009CC41
0x18009cc36  mov     rax, [rsi+8]
0x18009cc3a  bt      dword ptr [rax+30h], 8
0x18009cc3f  jnb     short loc_18009CC1F
0x18009cc41  mov     rcx, rsi
0x18009cc44  call    CipEnableJournalingAlways
0x18009cc49  mov     ebx, eax
0x18009cc4b  test    eax, eax
0x18009cc4d  jns     short loc_18009CC5D
0x18009cc4f  mov     edi, 9
0x18009cc54  mov     r12d, [rbp+3Fh+arg_8]
0x18009cc58  jmp     loc_18009CD5D
0x18009cc5d  lea     rax, [rbp+3Fh+var_90]
0x18009cc61  xor     r9d, r9d
0x18009cc64  mov     [rsp+0D0h+EventDescriptor], rax
0x18009cc69  xor     r8d, r8d
0x18009cc6c  lea     rax, [rbp+3Fh+var_88]
0x18009cc70  mov     dword ptr [rsp+0D0h+var_A8], edi
0x18009cc74  mov     edx, r12d
0x18009cc77  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18009cc7c  mov     rcx, rsi
0x18009cc7f  call    cs:__imp_FsRtlKernelFsControlFile
0x18009cc86  nop     dword ptr [rax+rax+00h]
0x18009cc8b  mov     ebx, eax
0x18009cc8d  test    ebx, ebx
0x18009cc8f  jns     short loc_18009CC98
0x18009cc91  mov     edi, 0Ah
0x18009cc96  jmp     short loc_18009CC54
0x18009cc98  mov     rax, [rbp+3Fh+arg_18]
0x18009cc9c  mov     [rbp+3Fh+var_80], rax
0x18009cca0  mov     eax, [rbp+3Fh+arg_20]
0x18009cca3  mov     [rbp+3Fh+var_78], eax
0x18009cca6  mov     eax, [rbp+3Fh+arg_28]
0x18009cca9  mov     [rbp+3Fh+var_74], eax
0x18009ccac  mov     rax, [rbp+3Fh+arg_30]
0x18009ccb0  mov     [rbp+3Fh+var_70], rax
0x18009ccb4  mov     eax, [rbp+3Fh+arg_38]
0x18009ccba  mov     [rbp+3Fh+var_68], eax
0x18009ccbd  mov     eax, [rbp+3Fh+arg_40]
0x18009ccc3  mov     [rbp+3Fh+var_64], eax
0x18009ccc6  mov     rax, [rbp+3Fh+arg_58]
0x18009cccd  mov     [rbp+3Fh+var_60], rax
0x18009ccd1  movzx   eax, [rbp+3Fh+arg_60]
0x18009ccd8  mov     [rbp+3Fh+var_58], ax
0x18009ccdc  mov     eax, [rbp+3Fh+arg_68]
0x18009cce2  mov     [rbp+3Fh+var_54], eax
0x18009cce5  mov     rax, [rbp+3Fh+arg_70]
0x18009ccec  test    rax, rax
0x18009ccef  jz      short loc_18009CD02
0x18009ccf1  mov     ecx, [rax+4]
0x18009ccf4  test    ecx, ecx
0x18009ccf6  jz      short loc_18009CD02
0x18009ccf8  add     rax, rdi
0x18009ccfb  mov     dword ptr [rbp+3Fh+var_50+8], ecx
0x18009ccfe  mov     qword ptr [rbp+3Fh+var_50], rax
0x18009cd02  mov     r12d, [rbp+3Fh+arg_8]
0x18009cd06  lea     rax, [rbp+3Fh+var_8C]
0x18009cd0a  mov     [rsp+0D0h+EventDescriptor], rax
0x18009cd0f  lea     r9, [rbp+3Fh+var_80]
0x18009cd13  mov     dword ptr [rsp+0D0h+var_A8], 298h
0x18009cd1b  mov     r8, rsi
0x18009cd1e  mov     edx, r12d
0x18009cd21  mov     qword ptr [rsp+0D0h+var_B0], r15
0x18009cd26  mov     cl, r13b
0x18009cd29  call    CiBuildEaCacheContents
0x18009cd2e  mov     ebx, eax
0x18009cd30  test    eax, eax
0x18009cd32  jns     short loc_18009CD3B
0x18009cd34  mov     edi, 0Bh
0x18009cd39  jmp     short loc_18009CD5D
0x18009cd3b  mov     r8d, [rbp+3Fh+var_8C]
0x18009cd3f  mov     rdx, r15
0x18009cd42  mov     rcx, rsi
0x18009cd45  xor     edi, edi
0x18009cd47  call    cs:__imp_FsRtlSetKernelEaFile
0x18009cd4e  nop     dword ptr [rax+rax+00h]
0x18009cd53  mov     ebx, eax
0x18009cd55  lea     eax, [rdi+0Ch]
0x18009cd58  test    ebx, ebx
0x18009cd5a  cmovs   edi, eax
0x18009cd5d  mov     rdx, r15; Entry
0x18009cd60  lea     rcx, g_CiEaCacheLookasideList; Lookaside
0x18009cd67  call    cs:__imp_ExFreeToPagedLookasideList
0x18009cd6e  nop     dword ptr [rax+rax+00h]
0x18009cd73  lea     rax, CiSetFileCacheComplete
0x18009cd7a  mov     r9d, r12d; int
0x18009cd7d  mov     [rsp+0D0h+EventDescriptor], rax; EventDescriptor
0x18009cd82  mov     r8b, r13b; int
0x18009cd85  mov     qword ptr [rsp+0D0h+var_A8], r14; char
0x18009cd8a  xor     edx, edx; int
0x18009cd8c  mov     ecx, ebx; int
0x18009cd8e  mov     dword ptr [rsp+0D0h+var_B0], edi; char
0x18009cd92  call    CiLogCacheEvent
0x18009cd97  mov     eax, ebx
0x18009cd99  add     rsp, 98h
0x18009cda0  pop     r15
0x18009cda2  pop     r14
0x18009cda4  pop     r13
0x18009cda6  pop     r12
0x18009cda8  pop     rdi
0x18009cda9  pop     rsi
0x18009cdaa  pop     rbx
0x18009cdab  pop     rbp
0x18009cdac  retn
```
