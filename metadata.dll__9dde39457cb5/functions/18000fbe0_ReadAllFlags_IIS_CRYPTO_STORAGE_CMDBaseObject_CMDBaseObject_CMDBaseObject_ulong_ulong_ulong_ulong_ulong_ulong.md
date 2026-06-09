# ReadAllFlags(IIS_CRYPTO_STORAGE *,CMDBaseObject *,CMDBaseObject *,CMDBaseObject *,ulong,ulong,ulong,ulong,ulong,ulong)

- ea: `0x18000fbe0`
- end: `0x18000ff09`
- name: `?ReadAllFlags@@YAJPEAVIIS_CRYPTO_STORAGE@@PEAVCMDBaseObject@@11KKKKKK@Z`
- size: `809`
- prototype: `__int64 __usercall@<rax>(struct IIS_CRYPTO_STORAGE *@<rcx>, struct CMDBaseObject *@<rdx>, struct CMDBaseObject *@<r8>, struct CMDBaseObject *@<r9>, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180010714`

## callees

- `0x18000fbe0`
- `0x180010474`
- `0x18002267c`
- `0x1800309d0`
- `0x180031010`

## import_xrefs

- `IisRTL!PuDbgPrintW` at `0x18000fcd9`
- `IisRTL!PuDbgPrintW` at `0x18000fcd9`

## string_xrefs

- `0x18000fcc0`: `inetsrv\iis\mb\metadata\readschema.cpp`
- `0x18000fcc7`: `[ReadAllFlags] Unable to read flags. GetRowIndexBySearch failed with hr = 0x%x.\n`
- `0x18000fcb5`: `ReadAllFlags`

## pseudocode

```c
__int64 __fastcall ReadAllFlags(
        struct IIS_CRYPTO_STORAGE *a1,
        struct CMDBaseObject *a2,
        struct CMDBaseObject *a3,
        struct CMDBaseObject *a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8,
        unsigned int a9,
        unsigned int a10)
{
  void *v10; // rdi
  __int64 v12; // rcx
  int v13; // eax
  unsigned int FlagTypes; // ebx
  unsigned int v15; // esi
  unsigned int v16; // r15d
  unsigned int v17; // r12d
  unsigned int v18; // r13d
  int v19; // eax
  unsigned int v21[2]; // [rsp+28h] [rbp-D8h]
  unsigned int *v22; // [rsp+40h] [rbp-C0h]
  int v23; // [rsp+50h] [rbp-B0h] BYREF
  int v24; // [rsp+54h] [rbp-ACh] BYREF
  int v25; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v26; // [rsp+5Ch] [rbp-A4h] BYREF
  int v27; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v28[2]; // [rsp+68h] [rbp-98h] BYREF
  void *v29; // [rsp+70h] [rbp-90h] BYREF
  int *v30; // [rsp+78h] [rbp-88h]
  int *v31; // [rsp+80h] [rbp-80h]
  int *v32; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v33; // [rsp+90h] [rbp-70h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  int *v35; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  struct CMDBaseObject *v38; // [rsp+C0h] [rbp-40h]
  struct CMDBaseObject *v39; // [rsp+C8h] [rbp-38h]
  struct CMDBaseObject *v40; // [rsp+D0h] [rbp-30h]
  unsigned int v41[3]; // [rsp+D8h] [rbp-28h] BYREF
  int v42; // [rsp+E4h] [rbp-1Ch]
  _DWORD v43[6]; // [rsp+100h] [rbp+0h] BYREF
  void *v44[2]; // [rsp+118h] [rbp+18h] BYREF
  __int128 v45; // [rsp+128h] [rbp+28h]
  __int128 v46; // [rsp+138h] [rbp+38h]
  _OWORD v47[3]; // [rsp+148h] [rbp+48h] BYREF
  _BYTE v48[8]; // [rsp+178h] [rbp+78h] BYREF
  int v49; // [rsp+180h] [rbp+80h]

  v10 = 0;
  v28[1] = 1;
  v26 = 0;
  memset(v47, 0, sizeof(v47));
  v28[0] = 0;
  v38 = a2;
  *(_QWORD *)&v47[0] = *((_QWORD *)g_pGlobalISTHelper + 29);
  *((_QWORD *)&v47[0] + 1) = &a5;
  v12 = *((_QWORD *)g_pGlobalISTHelper + 2);
  v40 = a4;
  v39 = a3;
  v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _DWORD *, _QWORD, _OWORD *, unsigned int *))(*(_QWORD *)v12 + 56LL))(
          v12,
          0,
          2,
          v28,
          0,
          v47,
          &v26);
  FlagTypes = v13;
  if ( v13 == -2145318890 )
  {
    return 0;
  }
  else if ( v13 >= 0 )
  {
    v15 = v26;
    v16 = a10;
    v17 = a9;
    v18 = a8;
    while ( 1 )
    {
      *(_OWORD *)v44 = 0;
      v43[0] = 0;
      v45 = 0;
      v43[1] = 1;
      v46 = 0;
      v43[2] = 2;
      v43[3] = 4;
      v43[4] = 5;
      v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _DWORD *, _BYTE *, void **))(**((_QWORD **)g_pGlobalISTHelper
                                                                                              + 2)
                                                                                           + 32LL))(
              *((_QWORD *)g_pGlobalISTHelper + 2),
              v15,
              5,
              v43,
              v48,
              v44);
      FlagTypes = v19;
      if ( v19 == -2145318890 )
        break;
      if ( v19 < 0 )
        return FlagTypes;
      if ( !v10 )
        v10 = v44[0];
      if ( v10 != v44[0] )
        return FlagTypes;
      if ( a5 != *(_DWORD *)v44[1] )
        return FlagTypes;
      FlagTypes = ReadFlagTypes(v38, a1, a6, a7, v18, v17, v16, v44, v22);
      if ( (FlagTypes & 0x80000000) != 0 )
        return FlagTypes;
      v36 = 0;
      v37 = 0;
      v23 = 0;
      v33 = L"/Schema/Properties/Names";
      v34 = *((_QWORD *)&v46 + 1);
      v31 = &v23;
      v35 = &v24;
      v30 = &v25;
      v29 = (void *)v45;
      v32 = (int *)v45;
      v42 = v49;
      v25 = 2;
      v24 = 1;
      FlagTypes = ReadDataObject(v39, (unsigned __int16 **)&v29, v41, a1);
      if ( (FlagTypes & 0x80000000) != 0 )
        return FlagTypes;
      v36 = 0;
      v37 = 0;
      v25 = 0;
      v27 = 0;
      v29 = (void *)v45;
      v33 = L"/Schema/Properties/Defaults";
      v34 = *((_QWORD *)&v46 + 1);
      v31 = &v25;
      v35 = &v24;
      v30 = &v23;
      v23 = 1;
      v24 = 1;
      v32 = &v27;
      v42 = 4;
      FlagTypes = ReadDataObject(v40, (unsigned __int16 **)&v29, v41, a1);
      if ( (FlagTypes & 0x80000000) != 0 )
        return FlagTypes;
      ++v15;
    }
    return 0;
  }
  else if ( (g_dwDebugFlags & 3) != 0 )
  {
    v21[0] = v13;
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\readschema.cpp",
      1081,
      "ReadAllFlags",
      L"[ReadAllFlags] Unable to read flags. GetRowIndexBySearch failed with hr = 0x%x.\n",
      *(_QWORD *)v21);
  }
  return FlagTypes;
}

```

## disassembly

```asm
0x18000fbe0  push    rbp
0x18000fbe2  push    rbx
0x18000fbe3  push    rsi
0x18000fbe4  push    rdi
0x18000fbe5  push    r12
0x18000fbe7  push    r13
0x18000fbe9  push    r14
0x18000fbeb  push    r15
0x18000fbed  lea     rbp, [rsp-0A8h]
0x18000fbf5  sub     rsp, 1A8h
0x18000fbfc  mov     rax, cs:__security_cookie
0x18000fc03  xor     rax, rsp
0x18000fc06  mov     [rbp+0E0h+var_50], rax
0x18000fc0d  xor     edi, edi
0x18000fc0f  mov     [rsp+1E0h+var_174], 1
0x18000fc17  xorps   xmm0, xmm0
0x18000fc1a  mov     [rsp+1E0h+var_184], edi
0x18000fc1e  movups  [rbp+0E0h+var_98], xmm0
0x18000fc22  mov     [rsp+1E0h+var_178], edi
0x18000fc26  mov     r14, rcx
0x18000fc29  mov     rcx, cs:?g_pGlobalISTHelper@@3PEAVCWriterGlobalHelper@@EA; CWriterGlobalHelper * g_pGlobalISTHelper
0x18000fc30  movups  [rbp+0E0h+var_88], xmm0
0x18000fc34  mov     [rbp+0E0h+var_120], rdx
0x18000fc38  lea     rdx, [rsp+1E0h+var_184]
0x18000fc3d  mov     qword ptr [rsp+1E0h+var_1B0], rdx
0x18000fc42  lea     rdx, [rbp+0E0h+var_98]
0x18000fc46  movups  [rbp+0E0h+var_78], xmm0
0x18000fc4a  mov     rax, [rcx+0E8h]
0x18000fc51  mov     qword ptr [rbp+0E0h+var_98], rax
0x18000fc55  lea     rax, [rbp+0E0h+arg_20]
0x18000fc5c  mov     qword ptr [rbp+0E0h+var_98+8], rax
0x18000fc60  mov     rcx, [rcx+10h]
0x18000fc64  mov     qword ptr [rsp+1E0h+var_1B8], rdx
0x18000fc69  xor     edx, edx
0x18000fc6b  mov     [rbp+0E0h+var_110], r9
0x18000fc6f  lea     r9, [rsp+1E0h+var_178]
0x18000fc74  mov     [rbp+0E0h+var_118], r8
0x18000fc78  lea     r8d, [rdi+2]
0x18000fc7c  mov     rax, [rcx]
0x18000fc7f  mov     qword ptr [rsp+1E0h+var_1C0], rdi
0x18000fc84  mov     rax, [rax+38h]
0x18000fc88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc8d  mov     ebx, eax
0x18000fc8f  cmp     eax, 80210816h
0x18000fc94  jnz     short loc_18000FC9D
0x18000fc96  mov     ebx, edi
0x18000fc98  jmp     loc_18000FEE4
0x18000fc9d  test    eax, eax
0x18000fc9f  jns     short loc_18000FCE4
0x18000fca1  test    byte ptr cs:g_dwDebugFlags, 3
0x18000fca8  jz      loc_18000FEE4
0x18000fcae  mov     rcx, cs:g_pDebug
0x18000fcb5  lea     r9, aReadallflags; "ReadAllFlags"
0x18000fcbc  mov     [rsp+1E0h+var_1B8], eax
0x18000fcc0  lea     rdx, aInetsrvIisMbMe_0; "inetsrv\\iis\\mb\\metadata\\readschema."...
0x18000fcc7  lea     rax, aReadallflagsUn; "[ReadAllFlags] Unable to read flags. Ge"...
0x18000fcce  mov     r8d, 439h
0x18000fcd4  mov     qword ptr [rsp+1E0h+var_1C0], rax
0x18000fcd9  call    cs:__imp_PuDbgPrintW
0x18000fcdf  jmp     loc_18000FEE4
0x18000fce4  mov     esi, [rsp+1E0h+var_184]
0x18000fce8  mov     r15d, [rbp+0E0h+arg_48]
0x18000fcef  mov     r12d, [rbp+0E0h+arg_40]
0x18000fcf6  mov     r13d, [rbp+0E0h+arg_38]
0x18000fcfd  mov     rax, cs:?g_pGlobalISTHelper@@3PEAVCWriterGlobalHelper@@EA; CWriterGlobalHelper * g_pGlobalISTHelper
0x18000fd04  lea     rdx, [rbp+0E0h+var_C8]
0x18000fd08  xorps   xmm0, xmm0
0x18000fd0b  mov     qword ptr [rsp+1E0h+var_1B8], rdx
0x18000fd10  movups  xmmword ptr [rbp+0E0h+var_C8], xmm0
0x18000fd14  mov     [rbp+0E0h+var_E0], 0
0x18000fd1b  lea     rdx, [rbp+0E0h+var_68]
0x18000fd1f  movups  [rbp+0E0h+var_B8], xmm0
0x18000fd23  mov     [rbp+0E0h+var_DC], 1
0x18000fd2a  lea     r9, [rbp+0E0h+var_E0]
0x18000fd2e  movups  [rbp+0E0h+var_A8], xmm0
0x18000fd32  mov     [rbp+0E0h+var_D8], 2
0x18000fd39  mov     r8d, 5
0x18000fd3f  mov     [rbp+0E0h+var_D4], 4
0x18000fd46  mov     [rbp+0E0h+var_D0], 5
0x18000fd4d  mov     rcx, [rax+10h]
0x18000fd51  mov     qword ptr [rsp+1E0h+var_1C0], rdx
0x18000fd56  mov     edx, esi
0x18000fd58  mov     rax, [rcx]
0x18000fd5b  mov     rax, [rax+20h]
0x18000fd5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd64  mov     ebx, eax
0x18000fd66  cmp     eax, 80210816h
0x18000fd6b  jz      loc_18000FEE2
0x18000fd71  test    eax, eax
0x18000fd73  js      loc_18000FEE4
0x18000fd79  test    rdi, rdi
0x18000fd7c  cmovz   rdi, [rbp+0E0h+var_C8]
0x18000fd81  cmp     rdi, [rbp+0E0h+var_C8]
0x18000fd85  jnz     loc_18000FEE4
0x18000fd8b  mov     rax, [rbp+0E0h+var_C8+8]
0x18000fd8f  mov     ecx, [rax]
0x18000fd91  cmp     [rbp+0E0h+arg_20], ecx
0x18000fd97  jnz     loc_18000FEE4
0x18000fd9d  mov     r9d, [rbp+0E0h+arg_30]; unsigned int
0x18000fda4  lea     rax, [rbp+0E0h+var_C8]
0x18000fda8  mov     r8d, [rbp+0E0h+arg_28]; unsigned int
0x18000fdaf  mov     rdx, r14; struct IIS_CRYPTO_STORAGE *
0x18000fdb2  mov     rcx, [rbp+0E0h+var_120]; this
0x18000fdb6  mov     [rsp+1E0h+var_1A8], rax; void **
0x18000fdbb  mov     [rsp+1E0h+var_1B0], r15d; unsigned int
0x18000fdc0  mov     [rsp+1E0h+var_1B8], r12d; unsigned int
0x18000fdc5  mov     [rsp+1E0h+var_1C0], r13d; int
0x18000fdca  call    ?ReadFlagTypes@@YAJPEAVCMDBaseObject@@PEAVIIS_CRYPTO_STORAGE@@KKKKKPEAPEAXPEAK@Z; ReadFlagTypes(CMDBaseObject *,IIS_CRYPTO_STORAGE *,ulong,ulong,ulong,ulong,ulong,void * *,ulong *)
0x18000fdcf  mov     ebx, eax
0x18000fdd1  xor     eax, eax
0x18000fdd3  test    ebx, ebx
0x18000fdd5  js      loc_18000FEE4
0x18000fddb  mov     rcx, qword ptr [rbp+0E0h+var_B8]
0x18000fddf  lea     r8, [rbp+0E0h+var_108]; unsigned int *
0x18000fde3  mov     [rbp+0E0h+var_138], rax
0x18000fde7  lea     rdx, [rsp+1E0h+var_170]; void **
0x18000fdec  mov     [rbp+0E0h+var_130], rax
0x18000fdf0  mov     r9, r14; struct IIS_CRYPTO_STORAGE *
0x18000fdf3  mov     [rsp+1E0h+var_190], eax
0x18000fdf7  lea     rax, aSchemaProperti_0; "/Schema/Properties/Names"
0x18000fdfe  mov     [rbp+0E0h+var_150], rax
0x18000fe02  mov     rax, qword ptr [rbp+0E0h+var_A8+8]
0x18000fe06  mov     [rbp+0E0h+var_148], rax
0x18000fe0a  lea     rax, [rsp+1E0h+var_190]
0x18000fe0f  mov     [rbp+0E0h+var_160], rax
0x18000fe13  lea     rax, [rsp+1E0h+var_18C]
0x18000fe18  mov     [rbp+0E0h+var_140], rax
0x18000fe1c  lea     rax, [rsp+1E0h+var_188]
0x18000fe21  mov     [rsp+1E0h+var_168], rax
0x18000fe26  mov     eax, [rbp+0E0h+var_60]
0x18000fe2c  mov     [rsp+1E0h+var_170], rcx
0x18000fe31  mov     [rbp+0E0h+var_158], rcx
0x18000fe35  mov     rcx, [rbp+0E0h+var_118]; this
0x18000fe39  mov     [rbp+0E0h+var_FC], eax
0x18000fe3c  mov     [rsp+1E0h+var_188], 2
0x18000fe44  mov     [rsp+1E0h+var_18C], 1
0x18000fe4c  call    ?ReadDataObject@@YAJPEAVCMDBaseObject@@PEAPEAXPEAKPEAVIIS_CRYPTO_STORAGE@@H@Z; ReadDataObject(CMDBaseObject *,void * *,ulong *,IIS_CRYPTO_STORAGE *,int)
0x18000fe51  mov     ebx, eax
0x18000fe53  xor     eax, eax
0x18000fe55  test    ebx, ebx
0x18000fe57  js      loc_18000FEE4
0x18000fe5d  lea     ecx, [rax+1]
0x18000fe60  mov     [rbp+0E0h+var_138], rax
0x18000fe64  mov     [rbp+0E0h+var_130], rax
0x18000fe68  lea     r8, [rbp+0E0h+var_108]; unsigned int *
0x18000fe6c  mov     [rsp+1E0h+var_188], eax
0x18000fe70  lea     rdx, [rsp+1E0h+var_170]; void **
0x18000fe75  mov     [rsp+1E0h+var_180], eax
0x18000fe79  mov     r9, r14; struct IIS_CRYPTO_STORAGE *
0x18000fe7c  mov     rax, qword ptr [rbp+0E0h+var_B8]
0x18000fe80  mov     [rsp+1E0h+var_170], rax
0x18000fe85  lea     rax, aSchemaProperti_2; "/Schema/Properties/Defaults"
0x18000fe8c  mov     [rbp+0E0h+var_150], rax
0x18000fe90  mov     rax, qword ptr [rbp+0E0h+var_A8+8]
0x18000fe94  mov     [rbp+0E0h+var_148], rax
0x18000fe98  lea     rax, [rsp+1E0h+var_188]
0x18000fe9d  mov     [rbp+0E0h+var_160], rax
0x18000fea1  lea     rax, [rsp+1E0h+var_18C]
0x18000fea6  mov     [rbp+0E0h+var_140], rax
0x18000feaa  lea     rax, [rsp+1E0h+var_190]
0x18000feaf  mov     [rsp+1E0h+var_168], rax
0x18000feb4  lea     rax, [rsp+1E0h+var_180]
0x18000feb9  mov     [rsp+1E0h+var_190], ecx
0x18000febd  mov     [rsp+1E0h+var_18C], ecx
0x18000fec1  mov     rcx, [rbp+0E0h+var_110]; this
0x18000fec5  mov     [rbp+0E0h+var_158], rax
0x18000fec9  mov     [rbp+0E0h+var_FC], 4
0x18000fed0  call    ?ReadDataObject@@YAJPEAVCMDBaseObject@@PEAPEAXPEAKPEAVIIS_CRYPTO_STORAGE@@H@Z; ReadDataObject(CMDBaseObject *,void * *,ulong *,IIS_CRYPTO_STORAGE *,int)
0x18000fed5  mov     ebx, eax
0x18000fed7  test    eax, eax
0x18000fed9  js      short loc_18000FEE4
0x18000fedb  inc     esi
0x18000fedd  jmp     loc_18000FCFD
0x18000fee2  xor     ebx, ebx
0x18000fee4  mov     eax, ebx
0x18000fee6  mov     rcx, [rbp+0E0h+var_50]
0x18000feed  xor     rcx, rsp; StackCookie
0x18000fef0  call    __security_check_cookie
0x18000fef5  add     rsp, 1A8h
0x18000fefc  pop     r15
0x18000fefe  pop     r14
0x18000ff00  pop     r13
0x18000ff02  pop     r12
0x18000ff04  pop     rdi
0x18000ff05  pop     rsi
0x18000ff06  pop     rbx
0x18000ff07  pop     rbp
0x18000ff08  retn
```
