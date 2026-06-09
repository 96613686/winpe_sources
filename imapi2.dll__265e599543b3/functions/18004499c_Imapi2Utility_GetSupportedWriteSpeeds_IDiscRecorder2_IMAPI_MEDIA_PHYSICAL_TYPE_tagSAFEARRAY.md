# Imapi2Utility::GetSupportedWriteSpeeds(IDiscRecorder2 *,_IMAPI_MEDIA_PHYSICAL_TYPE,tagSAFEARRAY * *)

- ea: `0x18004499c`
- end: `0x180044af0`
- name: `?GetSupportedWriteSpeeds@Imapi2Utility@@YAJPEAUIDiscRecorder2@@W4_IMAPI_MEDIA_PHYSICAL_TYPE@@PEAPEAUtagSAFEARRAY@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(Imapi2Utility *__hidden this, struct IDiscRecorder2 *, enum _IMAPI_MEDIA_PHYSICAL_TYPE, struct tagSAFEARRAY **)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x180022360`
- `0x180031da0`
- `0x18003b3f0`

## callees

- `0x1800140f4`
- `0x180042ae0`
- `0x1800431a8`
- `0x1800436f8`
- `0x18004499c`
- `0x180047f88`
- `0x18004a010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180044a76`
- `KERNEL32!LocalFree` at `0x180044a85`
- `KERNEL32!LocalFree` at `0x180044adb`
- `KERNEL32!LocalFree` at `0x180044a76`
- `KERNEL32!LocalFree` at `0x180044a85`
- `KERNEL32!LocalFree` at `0x180044adb`

## pseudocode

```c
__int64 __fastcall Imapi2Utility::GetSupportedWriteSpeeds(
        void (__fastcall ***this)(Imapi2Utility *, GUID *, __int64 *),
        struct IDiscRecorder2 *a2,
        _QWORD *a3,
        struct tagSAFEARRAY **a4)
{
  LONG *v4; // rbx
  int VariantSafeArrayFromV1Enums; // edi
  unsigned int **v8; // r9
  int v9; // eax
  unsigned int v10; // r8d
  struct tagSAFEARRAY **v11; // r9
  _QWORD *v12; // rcx
  unsigned int v13; // eax
  __int64 i; // rbx
  __int64 v15; // rdx
  HLOCAL hMem; // [rsp+30h] [rbp-20h] BYREF
  HLOCAL v17; // [rsp+38h] [rbp-18h] BYREF
  unsigned int v18[2]; // [rsp+40h] [rbp-10h] BYREF
  struct IWriteSpeedDescriptor **v19; // [rsp+80h] [rbp+30h] BYREF
  HLOCAL v20; // [rsp+88h] [rbp+38h] BYREF

  v4 = 0;
  v17 = 0;
  hMem = 0;
  v20 = 0;
  LODWORD(v19) = 0;
  *(_QWORD *)v18 = 0;
  if ( !a3 )
    return 2147500035LL;
  VariantSafeArrayFromV1Enums = Imapi2Utility::BuildSupportedDescriptorArray(
                                  this,
                                  a2,
                                  &v20,
                                  (struct IWriteSpeedDescriptor ***)&v17,
                                  (unsigned int **)&v19);
  if ( VariantSafeArrayFromV1Enums < 0
    || (v9 = Imapi2Utility::ConvertDescriptorArrayToULONGArray(
               (Imapi2Utility *)v20,
               (struct IWriteSpeedDescriptor **)(unsigned int)v19,
               (unsigned int)&hMem,
               v8),
        v4 = (LONG *)hMem,
        VariantSafeArrayFromV1Enums = v9,
        v9 < 0)
    || (LODWORD(v19) = Imapi2Utility::SortAndEliminateDuplicates(
                         (Imapi2Utility *)hMem,
                         (unsigned int *)(unsigned int)v19,
                         v10),
        VariantSafeArrayFromV1Enums = Imapi2Utility::CreateVariantSafeArrayFromV1Enums(
                                        v4,
                                        (const int *)(unsigned int)v19,
                                        (SAFEARRAY **)v18,
                                        v11),
        VariantSafeArrayFromV1Enums < 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        119,
        &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
        (unsigned int)VariantSafeArrayFromV1Enums);
    }
  }
  else
  {
    *a3 = *(_QWORD *)v18;
  }
  if ( v4 )
    LocalFree(v4);
  if ( v17 )
  {
    LocalFree(v17);
    v17 = 0;
  }
  v12 = v20;
  if ( v20 )
  {
    v13 = (unsigned int)v19;
    for ( i = 0; (unsigned int)i < v13; i = (unsigned int)(i + 1) )
    {
      v15 = v12[i];
      if ( v15 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v15 + 16LL))(v12[i]);
        *((_QWORD *)v20 + i) = 0;
        v12 = v20;
        v13 = (unsigned int)v19;
      }
    }
    if ( v12 )
      LocalFree(v12);
  }
  return (unsigned int)VariantSafeArrayFromV1Enums;
}

```

## disassembly

```asm
0x18004499c  mov     [rsp-18h+arg_0], rbx
0x1800449a1  push    rbp
0x1800449a2  push    rsi
0x1800449a3  push    rdi
0x1800449a4  mov     rbp, rsp
0x1800449a7  sub     rsp, 50h
0x1800449ab  xor     ebx, ebx
0x1800449ad  mov     [rbp+var_18], 0
0x1800449b5  mov     [rbp+hMem], rbx
0x1800449b9  mov     rsi, r8
0x1800449bc  mov     [rbp+arg_18], rbx
0x1800449c0  mov     dword ptr [rbp+arg_10], ebx
0x1800449c3  mov     qword ptr [rbp+var_10], rbx
0x1800449c7  test    r8, r8
0x1800449ca  jnz     short loc_1800449D6
0x1800449cc  mov     eax, 80004003h
0x1800449d1  jmp     loc_180044AE3
0x1800449d6  lea     rax, [rbp+arg_10]
0x1800449da  lea     r9, [rbp+var_18]; struct IWriteSpeedDescriptor ***
0x1800449de  mov     [rsp+50h+var_30], rax; unsigned int **
0x1800449e3  lea     r8, [rbp+arg_18]; enum _IMAPI_MEDIA_PHYSICAL_TYPE
0x1800449e7  call    ?BuildSupportedDescriptorArray@Imapi2Utility@@YAJPEAUIDiscRecorder2@@W4_IMAPI_MEDIA_PHYSICAL_TYPE@@PEAPEAPEAUIWriteSpeedDescriptor@@PEAPEAKPEAK@Z; Imapi2Utility::BuildSupportedDescriptorArray(IDiscRecorder2 *,_IMAPI_MEDIA_PHYSICAL_TYPE,IWriteSpeedDescriptor * * *,ulong * *,ulong *)
0x1800449ec  mov     edi, eax
0x1800449ee  test    eax, eax
0x1800449f0  js      short loc_180044A37
0x1800449f2  mov     edx, dword ptr [rbp+arg_10]; struct IWriteSpeedDescriptor **
0x1800449f5  lea     r8, [rbp+hMem]; unsigned int
0x1800449f9  mov     rcx, [rbp+arg_18]; this
0x1800449fd  call    ?ConvertDescriptorArrayToULONGArray@Imapi2Utility@@YAJPEAPEAUIWriteSpeedDescriptor@@KPEAPEAK@Z; Imapi2Utility::ConvertDescriptorArrayToULONGArray(IWriteSpeedDescriptor * *,ulong,ulong * *)
0x180044a02  mov     rbx, [rbp+hMem]
0x180044a06  mov     edi, eax
0x180044a08  test    eax, eax
0x180044a0a  js      short loc_180044A37
0x180044a0c  mov     edx, dword ptr [rbp+arg_10]; unsigned int *
0x180044a0f  mov     rcx, rbx; this
0x180044a12  call    ?SortAndEliminateDuplicates@Imapi2Utility@@YAKPEAKK@Z; Imapi2Utility::SortAndEliminateDuplicates(ulong *,ulong)
0x180044a17  lea     r8, [rbp+var_10]; unsigned int
0x180044a1b  mov     dword ptr [rbp+arg_10], eax
0x180044a1e  mov     edx, eax; int *
0x180044a20  mov     rcx, rbx; this
0x180044a23  call    ?CreateVariantSafeArrayFromV1Enums@Imapi2Utility@@YA?BJPEBJKPEAPEAUtagSAFEARRAY@@@Z; Imapi2Utility::CreateVariantSafeArrayFromV1Enums(long const *,ulong,tagSAFEARRAY * *)
0x180044a28  mov     edi, eax
0x180044a2a  test    eax, eax
0x180044a2c  js      short loc_180044A37
0x180044a2e  mov     rax, qword ptr [rbp+var_10]
0x180044a32  mov     [rsi], rax
0x180044a35  jmp     short loc_180044A6E
0x180044a37  mov     rcx, cs:WPP_GLOBAL_Control
0x180044a3e  lea     rax, WPP_GLOBAL_Control
0x180044a45  cmp     rcx, rax
0x180044a48  jz      short loc_180044A6E
0x180044a4a  test    byte ptr [rcx+1Ch], 4
0x180044a4e  jz      short loc_180044A6E
0x180044a50  cmp     byte ptr [rcx+19h], 4
0x180044a54  jb      short loc_180044A6E
0x180044a56  mov     rcx, [rcx+10h]
0x180044a5a  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180044a61  mov     edx, 77h ; 'w'
0x180044a66  mov     r9d, edi
0x180044a69  call    WPP_SF_d
0x180044a6e  test    rbx, rbx
0x180044a71  jz      short loc_180044A7C
0x180044a73  mov     rcx, rbx; hMem
0x180044a76  call    cs:__imp_LocalFree
0x180044a7c  mov     rcx, [rbp+var_18]; hMem
0x180044a80  test    rcx, rcx
0x180044a83  jz      short loc_180044A93
0x180044a85  call    cs:__imp_LocalFree
0x180044a8b  mov     [rbp+var_18], 0
0x180044a93  mov     rcx, [rbp+arg_18]
0x180044a97  test    rcx, rcx
0x180044a9a  jz      short loc_180044AE1
0x180044a9c  mov     eax, dword ptr [rbp+arg_10]
0x180044a9f  xor     ebx, ebx
0x180044aa1  test    eax, eax
0x180044aa3  jz      short loc_180044AD6
0x180044aa5  mov     rdx, [rcx+rbx*8]
0x180044aa9  test    rdx, rdx
0x180044aac  jz      short loc_180044AD0
0x180044aae  mov     rax, [rdx]
0x180044ab1  mov     rcx, rdx
0x180044ab4  mov     rax, [rax+10h]
0x180044ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044abd  mov     rax, [rbp+arg_18]
0x180044ac1  mov     qword ptr [rax+rbx*8], 0
0x180044ac9  mov     rcx, [rbp+arg_18]; hMem
0x180044acd  mov     eax, dword ptr [rbp+arg_10]
0x180044ad0  inc     ebx
0x180044ad2  cmp     ebx, eax
0x180044ad4  jb      short loc_180044AA5
0x180044ad6  test    rcx, rcx
0x180044ad9  jz      short loc_180044AE1
0x180044adb  call    cs:__imp_LocalFree
0x180044ae1  mov     eax, edi
0x180044ae3  mov     rbx, [rsp+50h+arg_0]
0x180044ae8  add     rsp, 50h
0x180044aec  pop     rdi
0x180044aed  pop     rsi
0x180044aee  pop     rbp
0x180044aef  retn
```
