# CipSetFileCache

- ea: `0x18009e068`
- end: `0x18009e3de`
- name: `CipSetFileCache`
- size: `886`
- prototype: `__int64 __usercall@<rax>(PFILE_OBJECT FileObject@<rcx>, int, int, __int64, int, int, int, __int64, __int64, __int16, int, __int64)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180064340`
- `0x180096f80`
- `0x1800c77c0`
- `0x1800e5a50`

## callees

- `0x180060da8`
- `0x18009d394`
- `0x18009dee0`
- `0x18009e068`
- `0x18009f044`
- `0x18009f2fc`
- `0x1800d34fc`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x18009e177`
- `ntoskrnl!PsGetCurrentProcess` at `0x18009e177`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x18009e1e6`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x18009e1e6`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18009e397`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18009e397`
- `ntoskrnl!PsGetProcessProtection` at `0x18009e186`
- `ntoskrnl!PsGetProcessProtection` at `0x18009e186`
- `ntoskrnl!FsRtlKernelFsControlFile` at `0x18009e231`
- `ntoskrnl!FsRtlKernelFsControlFile` at `0x18009e2af`
- `ntoskrnl!FsRtlKernelFsControlFile` at `0x18009e231`
- `ntoskrnl!FsRtlKernelFsControlFile` at `0x18009e2af`
- `ntoskrnl!FsRtlSetKernelEaFile` at `0x18009e377`
- `ntoskrnl!FsRtlSetKernelEaFile` at `0x18009e377`

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
0x18009e068  mov     [rsp-8+arg_18], r9
0x18009e06d  mov     [rsp-8+arg_8], edx
0x18009e071  push    rbp
0x18009e072  push    rbx
0x18009e073  push    rsi
0x18009e074  push    rdi
0x18009e075  push    r12
0x18009e077  push    r13
0x18009e079  push    r14
0x18009e07b  push    r15
0x18009e07d  lea     rbp, [rsp-7]
0x18009e082  sub     rsp, 98h
0x18009e089  xor     ebx, ebx
0x18009e08b  movzx   r13d, r8b
0x18009e08f  mov     rsi, rcx
0x18009e092  mov     [rbp+3Fh+var_88], rbx
0x18009e096  xorps   xmm0, xmm0
0x18009e099  mov     [rbp+3Fh+var_90], ebx
0x18009e09c  add     rcx, 58h ; 'X'
0x18009e0a0  mov     [rbp+3Fh+var_8C], ebx
0x18009e0a3  lea     rdx, CiSetFileCacheStart
0x18009e0aa  mov     [rbp+3Fh+arg_48], ebx
0x18009e0b0  mov     [rbp+3Fh+var_56], bx
0x18009e0b4  movdqa  [rbp+3Fh+var_50], xmm0
0x18009e0b9  mov     [rbp+3Fh+arg_0], ebx
0x18009e0bc  mov     [rbp+3Fh+arg_10], bl
0x18009e0bf  call    CiLogFileEvent
0x18009e0c4  lea     edi, [rbx+2]
0x18009e0c7  cmp     r13b, dil
0x18009e0ca  jnb     short loc_18009E0DB
0x18009e0cc  lea     edi, [rbx+1]
0x18009e0cf  mov     r14d, r13d
0x18009e0d2  mov     r12d, [rbp+3Fh+arg_8]
0x18009e0d6  jmp     loc_18009E3A3
0x18009e0db  lea     r8, [rbp+3Fh+arg_10]
0x18009e0df  mov     rcx, rsi; FileObject
0x18009e0e2  lea     rdx, [rbp+3Fh+arg_0]
0x18009e0e6  mov     r14, rbx
0x18009e0e9  call    CipGetVolumeFlags
0x18009e0ee  mov     r15d, [rbp+3Fh+arg_0]
0x18009e0f2  mov     r12d, eax
0x18009e0f5  mov     rax, [rsi+8]
0x18009e0f9  test    dword ptr [rax+30h], 100h
0x18009e100  jnz     short loc_18009E152
0x18009e102  lea     rdx, [rbp+3Fh+arg_48]
0x18009e109  mov     rcx, rsi
0x18009e10c  call    CipGetFileAttributes
0x18009e111  mov     ebx, eax
0x18009e113  test    eax, eax
0x18009e115  js      short loc_18009E0D2
0x18009e117  xor     ebx, ebx
0x18009e119  test    r12d, r12d
0x18009e11c  jns     short loc_18009E128
0x18009e11e  mov     ebx, r12d
0x18009e121  mov     edi, 3
0x18009e126  jmp     short loc_18009E0D2
0x18009e128  mov     edx, [rbp+3Fh+arg_48]
0x18009e12e  bt      r15d, 11h
0x18009e133  setb    cl
0x18009e136  bt      edx, 0Eh
0x18009e13a  setb    al
0x18009e13d  test    al, cl
0x18009e13f  jz      short loc_18009E152
0x18009e141  mov     r14, r15
0x18009e144  mov     edi, 4
0x18009e149  shl     r14, 20h
0x18009e14d  or      r14, rdx
0x18009e150  jmp     short loc_18009E0D2
0x18009e152  cmp     [rsi+4Eh], bl
0x18009e155  jz      short loc_18009E166
0x18009e157  mov     edi, 5
0x18009e15c  mov     ebx, 0C0000043h
0x18009e161  jmp     loc_18009E0D2
0x18009e166  cmp     [rsi+4Bh], bl
0x18009e169  jz      short loc_18009E1C1
0x18009e16b  mov     rax, [rbp+3Fh+arg_50]
0x18009e172  test    rax, rax
0x18009e175  jnz     short loc_18009E183
0x18009e177  call    cs:__imp_PsGetCurrentProcess
0x18009e17e  nop     dword ptr [rax+rax+00h]
0x18009e183  mov     rcx, rax
0x18009e186  call    cs:__imp_PsGetProcessProtection
0x18009e18d  nop     dword ptr [rax+rax+00h]
0x18009e192  cmp     al, 51h ; 'Q'
0x18009e194  jz      short loc_18009E19A
0x18009e196  cmp     al, 21h ; '!'
0x18009e198  jnz     short loc_18009E1B6
0x18009e19a  mov     rcx, cs:g_CipWhichLevelComparisons
0x18009e1a1  mov     rdx, r13
0x18009e1a4  and     edx, 0Fh
0x18009e1a7  test    dword ptr [rcx+rdx*4], 100h
0x18009e1ae  jz      short loc_18009E1B6
0x18009e1b0  cmp     r13b, 7
0x18009e1b4  jnz     short loc_18009E1C1
0x18009e1b6  mov     edi, 6
0x18009e1bb  movzx   r14d, al
0x18009e1bf  jmp     short loc_18009E15C
0x18009e1c1  test    r12d, r12d
0x18009e1c4  js      short loc_18009E1DF
0x18009e1c6  bt      r15d, 13h
0x18009e1cb  jnb     short loc_18009E1DF
0x18009e1cd  mov     edi, 0Dh
0x18009e1d2  mov     r14, r15
0x18009e1d5  mov     ebx, 0C00000A2h
0x18009e1da  jmp     loc_18009E0D2
0x18009e1df  lea     rcx, g_CiEaCacheLookasideList; Lookaside
0x18009e1e6  call    cs:__imp_ExAllocateFromPagedLookasideList
0x18009e1ed  nop     dword ptr [rax+rax+00h]
0x18009e1f2  mov     r15, rax
0x18009e1f5  mov     edi, 8
0x18009e1fa  test    rax, rax
0x18009e1fd  jnz     short loc_18009E209
0x18009e1ff  mov     ebx, 0C0000017h
0x18009e204  jmp     loc_18009E0D2
0x18009e209  lea     rax, [rbp+3Fh+var_90]
0x18009e20d  mov     r12d, 900EFh
0x18009e213  mov     [rsp+0D0h+EventDescriptor], rax
0x18009e218  xor     r9d, r9d
0x18009e21b  lea     rax, [rbp+3Fh+var_88]
0x18009e21f  mov     dword ptr [rsp+0D0h+var_A8], edi
0x18009e223  xor     r8d, r8d
0x18009e226  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18009e22b  mov     edx, r12d
0x18009e22e  mov     rcx, rsi
0x18009e231  call    cs:__imp_FsRtlKernelFsControlFile
0x18009e238  nop     dword ptr [rax+rax+00h]
0x18009e23d  mov     ebx, eax
0x18009e23f  cmp     eax, 0C00002B8h
0x18009e244  jnz     short loc_18009E2BD
0x18009e246  cmp     cs:g_CiIsWinPE, r14b
0x18009e24d  jz      short loc_18009E256
0x18009e24f  mov     ebx, 0C00000BBh
0x18009e254  jmp     short loc_18009E27F
0x18009e256  bt      cs:g_CiOptions, 8
0x18009e25e  jb      short loc_18009E271
0x18009e260  cmp     [rbp+3Fh+arg_10], r14b
0x18009e264  jnz     short loc_18009E271
0x18009e266  mov     rax, [rsi+8]
0x18009e26a  bt      dword ptr [rax+30h], 8
0x18009e26f  jnb     short loc_18009E24F
0x18009e271  mov     rcx, rsi
0x18009e274  call    CipEnableJournalingAlways
0x18009e279  mov     ebx, eax
0x18009e27b  test    eax, eax
0x18009e27d  jns     short loc_18009E28D
0x18009e27f  mov     edi, 9
0x18009e284  mov     r12d, [rbp+3Fh+arg_8]
0x18009e288  jmp     loc_18009E38D
0x18009e28d  lea     rax, [rbp+3Fh+var_90]
0x18009e291  xor     r9d, r9d
0x18009e294  mov     [rsp+0D0h+EventDescriptor], rax
0x18009e299  xor     r8d, r8d
0x18009e29c  lea     rax, [rbp+3Fh+var_88]
0x18009e2a0  mov     dword ptr [rsp+0D0h+var_A8], edi
0x18009e2a4  mov     edx, r12d
0x18009e2a7  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18009e2ac  mov     rcx, rsi
0x18009e2af  call    cs:__imp_FsRtlKernelFsControlFile
0x18009e2b6  nop     dword ptr [rax+rax+00h]
0x18009e2bb  mov     ebx, eax
0x18009e2bd  test    ebx, ebx
0x18009e2bf  jns     short loc_18009E2C8
0x18009e2c1  mov     edi, 0Ah
0x18009e2c6  jmp     short loc_18009E284
0x18009e2c8  mov     rax, [rbp+3Fh+arg_18]
0x18009e2cc  mov     [rbp+3Fh+var_80], rax
0x18009e2d0  mov     eax, [rbp+3Fh+arg_20]
0x18009e2d3  mov     [rbp+3Fh+var_78], eax
0x18009e2d6  mov     eax, [rbp+3Fh+arg_28]
0x18009e2d9  mov     [rbp+3Fh+var_74], eax
0x18009e2dc  mov     rax, [rbp+3Fh+arg_30]
0x18009e2e0  mov     [rbp+3Fh+var_70], rax
0x18009e2e4  mov     eax, [rbp+3Fh+arg_38]
0x18009e2ea  mov     [rbp+3Fh+var_68], eax
0x18009e2ed  mov     eax, [rbp+3Fh+arg_40]
0x18009e2f3  mov     [rbp+3Fh+var_64], eax
0x18009e2f6  mov     rax, [rbp+3Fh+arg_58]
0x18009e2fd  mov     [rbp+3Fh+var_60], rax
0x18009e301  movzx   eax, [rbp+3Fh+arg_60]
0x18009e308  mov     [rbp+3Fh+var_58], ax
0x18009e30c  mov     eax, [rbp+3Fh+arg_68]
0x18009e312  mov     [rbp+3Fh+var_54], eax
0x18009e315  mov     rax, [rbp+3Fh+arg_70]
0x18009e31c  test    rax, rax
0x18009e31f  jz      short loc_18009E332
0x18009e321  mov     ecx, [rax+4]
0x18009e324  test    ecx, ecx
0x18009e326  jz      short loc_18009E332
0x18009e328  add     rax, rdi
0x18009e32b  mov     dword ptr [rbp+3Fh+var_50+8], ecx
0x18009e32e  mov     qword ptr [rbp+3Fh+var_50], rax
0x18009e332  mov     r12d, [rbp+3Fh+arg_8]
0x18009e336  lea     rax, [rbp+3Fh+var_8C]
0x18009e33a  mov     [rsp+0D0h+EventDescriptor], rax
0x18009e33f  lea     r9, [rbp+3Fh+var_80]
0x18009e343  mov     dword ptr [rsp+0D0h+var_A8], 298h
0x18009e34b  mov     r8, rsi
0x18009e34e  mov     edx, r12d
0x18009e351  mov     qword ptr [rsp+0D0h+var_B0], r15
0x18009e356  mov     cl, r13b
0x18009e359  call    CiBuildEaCacheContents
0x18009e35e  mov     ebx, eax
0x18009e360  test    eax, eax
0x18009e362  jns     short loc_18009E36B
0x18009e364  mov     edi, 0Bh
0x18009e369  jmp     short loc_18009E38D
0x18009e36b  mov     r8d, [rbp+3Fh+var_8C]
0x18009e36f  mov     rdx, r15
0x18009e372  mov     rcx, rsi
0x18009e375  xor     edi, edi
0x18009e377  call    cs:__imp_FsRtlSetKernelEaFile
0x18009e37e  nop     dword ptr [rax+rax+00h]
0x18009e383  mov     ebx, eax
0x18009e385  lea     eax, [rdi+0Ch]
0x18009e388  test    ebx, ebx
0x18009e38a  cmovs   edi, eax
0x18009e38d  mov     rdx, r15; Entry
0x18009e390  lea     rcx, g_CiEaCacheLookasideList; Lookaside
0x18009e397  call    cs:__imp_ExFreeToPagedLookasideList
0x18009e39e  nop     dword ptr [rax+rax+00h]
0x18009e3a3  lea     rax, CiSetFileCacheComplete
0x18009e3aa  mov     r9d, r12d; int
0x18009e3ad  mov     [rsp+0D0h+EventDescriptor], rax; EventDescriptor
0x18009e3b2  mov     r8b, r13b; int
0x18009e3b5  mov     qword ptr [rsp+0D0h+var_A8], r14; char
0x18009e3ba  xor     edx, edx; int
0x18009e3bc  mov     ecx, ebx; int
0x18009e3be  mov     dword ptr [rsp+0D0h+var_B0], edi; char
0x18009e3c2  call    CiLogCacheEvent
0x18009e3c7  mov     eax, ebx
0x18009e3c9  add     rsp, 98h
0x18009e3d0  pop     r15
0x18009e3d2  pop     r14
0x18009e3d4  pop     r13
0x18009e3d6  pop     r12
0x18009e3d8  pop     rdi
0x18009e3d9  pop     rsi
0x18009e3da  pop     rbx
0x18009e3db  pop     rbp
0x18009e3dc  retn
```
