# CLocationWriter::WriteCustomProperty(void * *,ulong *)

- ea: `0x18002ec50`
- end: `0x18002f1a9`
- name: `?WriteCustomProperty@CLocationWriter@@AEAAJPEAPEAXPEAK@Z`
- size: `1369`
- prototype: `__int64 __fastcall(CLocationWriter *__hidden this, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180006204`

## callees

- `0x18000674c`
- `0x180006d08`
- `0x180008a08`
- `0x18002bdb4`
- `0x18002c76c`
- `0x18002ec50`
- `0x1800309d0`
- `0x180031010`

## import_xrefs

- `msvcrt!_ultow` at `0x18002ed1f`
- `msvcrt!_ultow` at `0x18002ed1f`

## pseudocode

```c
__int64 __fastcall CLocationWriter::WriteCustomProperty(CLocationWriter *this, void **a2, unsigned int *a3)
{
  unsigned int v6; // r8d
  unsigned int *v7; // rax
  unsigned __int16 *v8; // r15
  unsigned __int16 *v9; // r14
  unsigned int v10; // ebx
  __int64 v11; // rax
  unsigned int *v12; // rcx
  int UserType; // eax
  _WORD *v14; // r12
  int v15; // ebx
  int v16; // eax
  __int64 v17; // rax
  int v18; // eax
  _WORD *v19; // rdx
  __int64 v20; // rsi
  __int64 v21; // r8
  __int64 v22; // r8
  __int64 v23; // r8
  __int64 v24; // r8
  __int64 v25; // r8
  CWriterGlobalHelper *v27; // [rsp+20h] [rbp-E0h]
  int v28; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v29; // [rsp+44h] [rbp-BCh] BYREF
  CWriterGlobalHelper *v30; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v31; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v32; // [rsp+58h] [rbp-A8h] BYREF
  void *v33; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v34; // [rsp+68h] [rbp-98h] BYREF
  void *Block; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v36[4]; // [rsp+78h] [rbp-88h] BYREF
  _OWORD v37[2]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v38; // [rsp+A8h] [rbp-58h]
  wchar_t Buffer[40]; // [rsp+C0h] [rbp-40h] BYREF

  v6 = *(_DWORD *)a2[1];
  v33 = L"Unknown_Type";
  v7 = (unsigned int *)a2[6];
  v30 = (CWriterGlobalHelper *)v6;
  v8 = 0;
  v32 = 0;
  v9 = 0;
  v10 = *v7;
  memset(v37, 0, sizeof(v37));
  v36[0] = 0;
  Block = L"UNKNOWN_UserType";
  v36[1] = 1;
  v28 = 1;
  v11 = *((_QWORD *)this + 4);
  v38 = 0;
  v36[2] = 4;
  *(_QWORD *)&v37[0] = *(_QWORD *)(v11 + 224);
  v12 = (unsigned int *)a2[5];
  *((_QWORD *)&v37[0] + 1) = &v28;
  v29 = 0;
  v34 = 0;
  v31 = 0;
  *(_QWORD *)&v38 = &v30;
  _ultow(*v12, Buffer, 10);
  UserType = CWriterGlobalHelper::GetUserType(
               *(CWriterGlobalHelper **)(*((_QWORD *)this + 3) + 65600LL),
               v10,
               (unsigned __int16 **)&Block,
               &v32,
               (int *)&v30 + 1);
  v14 = Block;
  v15 = UserType;
  if ( UserType < 0 )
    goto LABEL_46;
  v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _DWORD *, _QWORD, _OWORD *, unsigned int *))(**(_QWORD **)(*((_QWORD *)this + 4) + 8LL) + 56LL))(
          *(_QWORD *)(*((_QWORD *)this + 4) + 8LL),
          0,
          3,
          v36,
          0,
          v37,
          &v29);
  v15 = v16;
  if ( v16 == -2145318890 )
    goto LABEL_7;
  if ( v16 < 0 )
    goto LABEL_46;
  v17 = *((_QWORD *)this + 4);
  v28 = 2;
  v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, int *, _QWORD, void **))(**(_QWORD **)(v17 + 8) + 32LL))(
          *(_QWORD *)(v17 + 8),
          v29,
          1,
          &v28,
          0,
          &v33);
  v15 = v18;
  if ( v18 == -2145318890 )
  {
LABEL_7:
    v33 = L"Unknown_Type";
  }
  else if ( v18 < 0 )
  {
    goto LABEL_46;
  }
  v15 = CWriterGlobalHelper::FlagToString(
          *((__int64 ***)this + 4),
          *(_DWORD *)a2[2],
          &v31,
          *(unsigned __int16 **)(*((_QWORD *)this + 4) + 224LL),
          2u);
  if ( v15 < 0 )
  {
    v9 = v31;
    goto LABEL_46;
  }
  LODWORD(v27) = (_DWORD)v30;
  v15 = CWriterGlobalHelper::ToString(
          *((CWriterGlobalHelper **)this + 4),
          (const unsigned __int16 *)a2[3],
          a3[3],
          *(_DWORD *)a2[5],
          v27,
          *(_DWORD *)a2[2],
          &v34);
  if ( v15 < 0 )
    goto LABEL_43;
  v15 = CWriter::WriteToFile(*((CWriter **)this + 3), L"\t<Custom\r\n", g_cchBeginCustomProperty, 0);
  if ( v15 < 0 )
    goto LABEL_43;
  v15 = CWriter::WriteToFile(*((CWriter **)this + 3), L"\t\tName=\"", g_cchNameEq, 0);
  if ( v15 < 0 )
    goto LABEL_43;
  v19 = *a2;
  v20 = -1;
  v21 = -1;
  do
    ++v21;
  while ( v19[v21] );
  v15 = CWriter::WriteToFile(*((CWriter **)this + 3), v19, v21, 0);
  if ( v15 < 0 )
    goto LABEL_43;
  v15 = CWriter::WriteToFile(*((CWriter **)this + 3), L"\"\r\n", g_cchQuoteRtn, 0);
  if ( v15 < 0 )
    goto LABEL_43;
  v15 = CWriter::WriteToFile(*((CWriter **)this + 3), L"\t\tID=\"", g_cchIDEq, 0);
  if ( v15 < 0 )
    goto LABEL_43;
  v22 = -1;
  do
    ++v22;
  while ( Buffer[v22] );
  v15 = CWriter::WriteToFile(*((CWriter **)this + 3), Buffer, v22, 0);
  if ( v15 < 0
    || (v15 = CWriter::WriteToFile(*((CWriter **)this + 3), L"\"\r\n", g_cchQuoteRtn, 0), v15 < 0)
    || (v15 = CWriter::WriteToFile(*((CWriter **)this + 3), L"\t\tValue=\"", g_cchValueEq, 0), v15 < 0) )
  {
LABEL_43:
    v8 = v34;
LABEL_44:
    v9 = v31;
    goto LABEL_46;
  }
  v8 = v34;
  if ( v34 )
  {
    v23 = -1;
    do
      ++v23;
    while ( v34[v23] );
    v15 = CWriter::WriteToFile(*((CWriter **)this + 3), v34, v23, 0);
    if ( v15 < 0 )
      goto LABEL_44;
  }
  v15 = CWriter::WriteToFile(*((CWriter **)this + 3), L"\"\r\n", g_cchQuoteRtn, 0);
  if ( v15 < 0 )
    goto LABEL_44;
  v15 = CWriter::WriteToFile(*((CWriter **)this + 3), L"\t\tType=\"", g_cchTypeEq, 0);
  if ( v15 < 0 )
    goto LABEL_44;
  v24 = -1;
  do
    ++v24;
  while ( *((_WORD *)v33 + v24) );
  v15 = CWriter::WriteToFile(*((CWriter **)this + 3), v33, v24, 0);
  if ( v15 < 0 )
    goto LABEL_44;
  v15 = CWriter::WriteToFile(*((CWriter **)this + 3), L"\"\r\n", g_cchQuoteRtn, 0);
  if ( v15 < 0 )
    goto LABEL_44;
  v15 = CWriter::WriteToFile(*((CWriter **)this + 3), L"\t\tUserType=\"", g_cchUserTypeEq, 0);
  if ( v15 < 0 )
    goto LABEL_44;
  v25 = -1;
  do
    ++v25;
  while ( v14[v25] );
  v15 = CWriter::WriteToFile(*((CWriter **)this + 3), v14, v25, 0);
  if ( v15 < 0 )
    goto LABEL_44;
  v15 = CWriter::WriteToFile(*((CWriter **)this + 3), L"\"\r\n", g_cchQuoteRtn, 0);
  if ( v15 < 0 )
    goto LABEL_44;
  v15 = CWriter::WriteToFile(*((CWriter **)this + 3), L"\t\tAttributes=\"", g_cchAttributesEq, 0);
  if ( v15 < 0 )
    goto LABEL_44;
  v9 = v31;
  do
    ++v20;
  while ( v31[v20] );
  v15 = CWriter::WriteToFile(*((CWriter **)this + 3), v31, v20, 0);
  if ( v15 >= 0 )
  {
    v15 = CWriter::WriteToFile(*((CWriter **)this + 3), L"\"\r\n", g_cchQuoteRtn, 0);
    if ( v15 >= 0 )
      v15 = CWriter::WriteToFile(*((CWriter **)this + 3), L"\t/>\r\n", g_cchEndCustomProperty, 0);
  }
LABEL_46:
  if ( v14 && HIDWORD(v30) )
    operator delete(v14);
  if ( v8 )
    operator delete(v8);
  if ( v9 )
    operator delete(v9);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18002ec50  mov     [rsp-8+arg_18], rbx
0x18002ec55  push    rbp
0x18002ec56  push    rsi
0x18002ec57  push    rdi
0x18002ec58  push    r12
0x18002ec5a  push    r13
0x18002ec5c  push    r14
0x18002ec5e  push    r15
0x18002ec60  lea     rbp, [rsp-20h]
0x18002ec65  sub     rsp, 120h
0x18002ec6c  mov     rax, cs:__security_cookie
0x18002ec73  xor     rax, rsp
0x18002ec76  mov     [rbp+50h+var_40], rax
0x18002ec7a  mov     rax, [rdx+8]
0x18002ec7e  mov     rsi, rdx
0x18002ec81  xorps   xmm0, xmm0
0x18002ec84  mov     rdi, rcx
0x18002ec87  mov     r13, r8
0x18002ec8a  mov     r8d, [rax]
0x18002ec8d  lea     rax, aUnknownType; "Unknown_Type"
0x18002ec94  mov     [rsp+150h+var_F0], rax
0x18002ec99  mov     rax, [rdx+30h]
0x18002ec9d  xor     edx, edx
0x18002ec9f  mov     dword ptr [rsp+150h+var_108], r8d
0x18002eca4  mov     r15d, edx
0x18002eca7  mov     [rsp+150h+var_F8], edx
0x18002ecab  mov     r14d, edx
0x18002ecae  mov     dword ptr [rsp+150h+var_108+4], edx
0x18002ecb2  mov     ebx, [rax]
0x18002ecb4  lea     r8d, [rdx+0Ah]; Radix
0x18002ecb8  movups  [rbp+50h+var_C8], xmm0
0x18002ecbc  mov     [rsp+150h+var_D8], edx
0x18002ecc0  lea     rax, aUnknownUsertyp; "UNKNOWN_UserType"
0x18002ecc7  mov     [rsp+150h+Block], rax
0x18002eccc  lea     eax, [rdx+1]
0x18002eccf  mov     [rsp+150h+var_D4], eax
0x18002ecd3  mov     [rsp+150h+var_110], eax
0x18002ecd7  mov     rax, [rcx+20h]
0x18002ecdb  movups  [rbp+50h+var_A8], xmm0
0x18002ecdf  mov     [rbp+50h+var_D0], 4
0x18002ece6  movups  [rbp+50h+var_B8], xmm0
0x18002ecea  mov     rcx, [rax+0E0h]
0x18002ecf1  lea     rax, [rsp+150h+var_110]
0x18002ecf6  mov     qword ptr [rbp+50h+var_C8], rcx
0x18002ecfa  mov     rcx, [rsi+28h]
0x18002ecfe  mov     qword ptr [rbp+50h+var_C8+8], rax
0x18002ed02  lea     rax, [rsp+150h+var_108]
0x18002ed07  mov     [rsp+150h+var_10C], edx
0x18002ed0b  mov     [rsp+150h+var_E8], rdx
0x18002ed10  mov     [rsp+150h+var_100], rdx
0x18002ed15  lea     rdx, [rbp+50h+Buffer]; Buffer
0x18002ed19  mov     qword ptr [rbp+50h+var_A8], rax
0x18002ed1d  mov     ecx, [rcx]; Value
0x18002ed1f  call    cs:__imp__ultow
0x18002ed25  mov     rcx, [rdi+18h]
0x18002ed29  lea     rax, [rsp+150h+var_108+4]
0x18002ed2e  lea     r9, [rsp+150h+var_F8]; unsigned int *
0x18002ed33  mov     [rsp+150h+var_130], rax; int *
0x18002ed38  lea     r8, [rsp+150h+Block]; unsigned __int16 **
0x18002ed3d  mov     edx, ebx; unsigned int
0x18002ed3f  mov     rcx, [rcx+10040h]; this
0x18002ed46  call    ?GetUserType@CWriterGlobalHelper@@QEAAJKPEAPEAGPEAKPEAH@Z; CWriterGlobalHelper::GetUserType(ulong,ushort * *,ulong *,int *)
0x18002ed4b  mov     r12, [rsp+150h+Block]
0x18002ed50  mov     ebx, eax
0x18002ed52  test    eax, eax
0x18002ed54  js      loc_18002F14F
0x18002ed5a  mov     rax, [rdi+20h]
0x18002ed5e  lea     rdx, [rsp+150h+var_10C]
0x18002ed63  mov     [rsp+150h+var_120], rdx
0x18002ed68  lea     r9, [rsp+150h+var_D8]
0x18002ed6d  lea     rdx, [rbp+50h+var_C8]
0x18002ed71  mov     qword ptr [rsp+150h+var_128], rdx
0x18002ed76  lea     r8d, [r14+3]
0x18002ed7a  mov     rcx, [rax+8]
0x18002ed7e  xor     edx, edx
0x18002ed80  mov     [rsp+150h+var_130], r14
0x18002ed85  mov     rax, [rcx]
0x18002ed88  mov     rax, [rax+38h]
0x18002ed8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed91  mov     ebx, eax
0x18002ed93  cmp     eax, 80210816h
0x18002ed98  jz      short loc_18002EDED
0x18002ed9a  test    eax, eax
0x18002ed9c  js      loc_18002F14F
0x18002eda2  mov     rax, [rdi+20h]
0x18002eda6  lea     rdx, [rsp+150h+var_F0]
0x18002edab  mov     [rsp+150h+var_110], 2
0x18002edb3  lea     r9, [rsp+150h+var_110]
0x18002edb8  mov     qword ptr [rsp+150h+var_128], rdx
0x18002edbd  lea     r8d, [r14+1]
0x18002edc1  mov     edx, [rsp+150h+var_10C]
0x18002edc5  mov     rcx, [rax+8]
0x18002edc9  mov     [rsp+150h+var_130], r14
0x18002edce  mov     rax, [rcx]
0x18002edd1  mov     rax, [rax+20h]
0x18002edd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002edda  mov     ebx, eax
0x18002eddc  cmp     eax, 80210816h
0x18002ede1  jz      short loc_18002EDED
0x18002ede3  test    eax, eax
0x18002ede5  js      loc_18002F14F
0x18002edeb  jmp     short loc_18002EDF9
0x18002eded  lea     rax, aUnknownType; "Unknown_Type"
0x18002edf4  mov     [rsp+150h+var_F0], rax
0x18002edf9  mov     rcx, [rdi+20h]; this
0x18002edfd  lea     r8, [rsp+150h+var_100]; unsigned __int16 **
0x18002ee02  mov     rdx, [rsi+10h]
0x18002ee06  mov     dword ptr [rsp+150h+var_130], 2; unsigned int
0x18002ee0e  mov     r9, [rcx+0E0h]; unsigned __int16 *
0x18002ee15  mov     edx, [rdx]; unsigned int
0x18002ee17  call    ?FlagToString@CWriterGlobalHelper@@QEAAJKPEAPEAGPEAGK@Z; CWriterGlobalHelper::FlagToString(ulong,ushort * *,ushort *,ulong)
0x18002ee1c  mov     ebx, eax
0x18002ee1e  test    eax, eax
0x18002ee20  js      loc_18002F14A
0x18002ee26  mov     rax, [rsi+10h]
0x18002ee2a  lea     rcx, [rsp+150h+var_E8]
0x18002ee2f  mov     r9, [rsi+28h]
0x18002ee33  mov     r8d, [r13+0Ch]; unsigned int
0x18002ee37  mov     rdx, [rsi+18h]; unsigned __int8 *
0x18002ee3b  mov     eax, [rax]
0x18002ee3d  mov     r9d, [r9]; unsigned int
0x18002ee40  mov     [rsp+150h+var_120], rcx; unsigned __int16 **
0x18002ee45  mov     rcx, [rdi+20h]; this
0x18002ee49  mov     [rsp+150h+var_128], eax; unsigned int
0x18002ee4d  mov     eax, dword ptr [rsp+150h+var_108]
0x18002ee51  mov     dword ptr [rsp+150h+var_130], eax; CWriterGlobalHelper *
0x18002ee55  call    ?ToString@CWriterGlobalHelper@@QEAAJPEAEKKKKPEAPEAG@Z; CWriterGlobalHelper::ToString(uchar *,ulong,ulong,ulong,ulong,ushort * *)
0x18002ee5a  xor     r13d, r13d
0x18002ee5d  mov     ebx, eax
0x18002ee5f  test    eax, eax
0x18002ee61  js      loc_18002F13E
0x18002ee67  mov     r8d, cs:?g_cchBeginCustomProperty@@3KA; unsigned int
0x18002ee6e  lea     rdx, aCustom; "\t<Custom\r\n"
0x18002ee75  mov     rcx, [rdi+18h]; this
0x18002ee79  xor     r9d, r9d; int
0x18002ee7c  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002ee81  mov     ebx, eax
0x18002ee83  test    eax, eax
0x18002ee85  js      loc_18002F13E
0x18002ee8b  mov     r8d, cs:?g_cchNameEq@@3KA; unsigned int
0x18002ee92  lea     rdx, aName; "\t\tName=\""
0x18002ee99  mov     rcx, [rdi+18h]; this
0x18002ee9d  xor     r9d, r9d; int
0x18002eea0  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002eea5  mov     ebx, eax
0x18002eea7  test    eax, eax
0x18002eea9  js      loc_18002F13E
0x18002eeaf  mov     rdx, [rsi]; void *
0x18002eeb2  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002eeb6  mov     r8, rsi
0x18002eeb9  inc     r8; unsigned int
0x18002eebc  cmp     [rdx+r8*2], r13w
0x18002eec1  jnz     short loc_18002EEB9
0x18002eec3  mov     rcx, [rdi+18h]; this
0x18002eec7  xor     r9d, r9d; int
0x18002eeca  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002eecf  mov     ebx, eax
0x18002eed1  test    eax, eax
0x18002eed3  js      loc_18002F13E
0x18002eed9  mov     r8d, cs:?g_cchQuoteRtn@@3KA; unsigned int
0x18002eee0  lea     r14, asc_180033CC0; "\"\r\n"
0x18002eee7  mov     rcx, [rdi+18h]; this
0x18002eeeb  mov     rdx, r14; void *
0x18002eeee  xor     r9d, r9d; int
0x18002eef1  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002eef6  mov     ebx, eax
0x18002eef8  test    eax, eax
0x18002eefa  js      loc_18002F13E
0x18002ef00  mov     r8d, cs:?g_cchIDEq@@3KA; unsigned int
0x18002ef07  lea     rdx, aId_1; "\t\tID=\""
0x18002ef0e  mov     rcx, [rdi+18h]; this
0x18002ef12  xor     r9d, r9d; int
0x18002ef15  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002ef1a  mov     ebx, eax
0x18002ef1c  test    eax, eax
0x18002ef1e  js      loc_18002F13E
0x18002ef24  lea     rax, [rbp+50h+Buffer]
0x18002ef28  mov     r8, rsi
0x18002ef2b  inc     r8; unsigned int
0x18002ef2e  cmp     [rax+r8*2], r13w
0x18002ef33  jnz     short loc_18002EF2B
0x18002ef35  mov     rcx, [rdi+18h]; this
0x18002ef39  lea     rdx, [rbp+50h+Buffer]; void *
0x18002ef3d  xor     r9d, r9d; int
0x18002ef40  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002ef45  mov     ebx, eax
0x18002ef47  test    eax, eax
0x18002ef49  js      loc_18002F13E
0x18002ef4f  mov     r8d, cs:?g_cchQuoteRtn@@3KA; unsigned int
0x18002ef56  xor     r9d, r9d; int
0x18002ef59  mov     rcx, [rdi+18h]; this
0x18002ef5d  mov     rdx, r14; void *
0x18002ef60  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002ef65  mov     ebx, eax
0x18002ef67  test    eax, eax
0x18002ef69  js      loc_18002F13E
0x18002ef6f  mov     r8d, cs:?g_cchValueEq@@3KA; unsigned int
0x18002ef76  lea     rdx, aValue_0; "\t\tValue=\""
0x18002ef7d  mov     rcx, [rdi+18h]; this
0x18002ef81  xor     r9d, r9d; int
0x18002ef84  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002ef89  mov     ebx, eax
0x18002ef8b  test    eax, eax
0x18002ef8d  js      loc_18002F13E
0x18002ef93  mov     r15, [rsp+150h+var_E8]
0x18002ef98  test    r15, r15
0x18002ef9b  jz      short loc_18002EFC3
0x18002ef9d  mov     r8, rsi
0x18002efa0  inc     r8; unsigned int
0x18002efa3  cmp     [r15+r8*2], r13w
0x18002efa8  jnz     short loc_18002EFA0
0x18002efaa  mov     rcx, [rdi+18h]; this
0x18002efae  xor     r9d, r9d; int
0x18002efb1  mov     rdx, r15; void *
0x18002efb4  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002efb9  mov     ebx, eax
0x18002efbb  test    eax, eax
0x18002efbd  js      loc_18002F143
0x18002efc3  mov     r8d, cs:?g_cchQuoteRtn@@3KA; unsigned int
0x18002efca  xor     r9d, r9d; int
0x18002efcd  mov     rcx, [rdi+18h]; this
0x18002efd1  mov     rdx, r14; void *
0x18002efd4  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002efd9  mov     ebx, eax
0x18002efdb  test    eax, eax
0x18002efdd  js      loc_18002F143
0x18002efe3  mov     r8d, cs:?g_cchTypeEq@@3KA; unsigned int
0x18002efea  lea     rdx, aType; "\t\tType=\""
0x18002eff1  mov     rcx, [rdi+18h]; this
0x18002eff5  xor     r9d, r9d; int
0x18002eff8  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002effd  mov     ebx, eax
0x18002efff  test    eax, eax
0x18002f001  js      loc_18002F143
0x18002f007  mov     rdx, [rsp+150h+var_F0]; void *
0x18002f00c  mov     r8, rsi
0x18002f00f  inc     r8; unsigned int
0x18002f012  cmp     [rdx+r8*2], r13w
0x18002f017  jnz     short loc_18002F00F
0x18002f019  mov     rcx, [rdi+18h]; this
0x18002f01d  xor     r9d, r9d; int
0x18002f020  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002f025  mov     ebx, eax
0x18002f027  test    eax, eax
0x18002f029  js      loc_18002F143
0x18002f02f  mov     r8d, cs:?g_cchQuoteRtn@@3KA; unsigned int
0x18002f036  xor     r9d, r9d; int
0x18002f039  mov     rcx, [rdi+18h]; this
0x18002f03d  mov     rdx, r14; void *
0x18002f040  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002f045  mov     ebx, eax
0x18002f047  test    eax, eax
0x18002f049  js      loc_18002F143
0x18002f04f  mov     r8d, cs:?g_cchUserTypeEq@@3KA; unsigned int
0x18002f056  lea     rdx, aUsertype_0; "\t\tUserType=\""
0x18002f05d  mov     rcx, [rdi+18h]; this
0x18002f061  xor     r9d, r9d; int
0x18002f064  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002f069  mov     ebx, eax
0x18002f06b  test    eax, eax
0x18002f06d  js      loc_18002F143
0x18002f073  mov     r8, rsi
0x18002f076  inc     r8; unsigned int
0x18002f079  cmp     [r12+r8*2], r13w
0x18002f07e  jnz     short loc_18002F076
0x18002f080  mov     rcx, [rdi+18h]; this
0x18002f084  xor     r9d, r9d; int
0x18002f087  mov     rdx, r12; void *
0x18002f08a  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002f08f  mov     ebx, eax
0x18002f091  test    eax, eax
0x18002f093  js      loc_18002F143
0x18002f099  mov     r8d, cs:?g_cchQuoteRtn@@3KA; unsigned int
0x18002f0a0  xor     r9d, r9d; int
0x18002f0a3  mov     rcx, [rdi+18h]; this
0x18002f0a7  mov     rdx, r14; void *
0x18002f0aa  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002f0af  mov     ebx, eax
0x18002f0b1  test    eax, eax
0x18002f0b3  js      loc_18002F143
0x18002f0b9  mov     r8d, cs:?g_cchAttributesEq@@3KA; unsigned int
0x18002f0c0  lea     rdx, aAttributes; "\t\tAttributes=\""
0x18002f0c7  mov     rcx, [rdi+18h]; this
0x18002f0cb  xor     r9d, r9d; int
0x18002f0ce  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002f0d3  mov     ebx, eax
0x18002f0d5  test    eax, eax
0x18002f0d7  js      short loc_18002F143
0x18002f0d9  mov     r14, [rsp+150h+var_100]
0x18002f0de  inc     rsi
0x18002f0e1  cmp     [r14+rsi*2], r13w
0x18002f0e6  jnz     short loc_18002F0DE
0x18002f0e8  mov     rcx, [rdi+18h]; this
0x18002f0ec  xor     r9d, r9d; int
0x18002f0ef  mov     r8d, esi; unsigned int
0x18002f0f2  mov     rdx, r14; void *
0x18002f0f5  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002f0fa  mov     ebx, eax
0x18002f0fc  test    eax, eax
0x18002f0fe  js      short loc_18002F152
  ... truncated ...
```
