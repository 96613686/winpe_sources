# CSiteCreator::InternalCreateNewSite(tag_SC_SUPPORTED_SERVICES,ushort const *,ushort const *,ushort const *,IIISApplicationAdmin *,ulong *,ulong *)

- ea: `0x180010638`
- end: `0x180010b3e`
- name: `?InternalCreateNewSite@CSiteCreator@@AEAAJW4tag_SC_SUPPORTED_SERVICES@@PEBG11PEAUIIISApplicationAdmin@@PEAK3@Z`
- size: `1286`
- prototype: `__int64 __fastcall(CSiteCreator *, __int64, unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, __int64, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task`

## callers

- `0x180008c40`

## callees

- `0x180010638`
- `0x180010b44`
- `0x180010e80`
- `0x180010ef4`
- `0x1800111e0`
- `0x180012010`

## import_xrefs

- `msvcrt!_ultow` at `0x18001074b`
- `msvcrt!_ultow` at `0x18001074b`
- `msvcrt!wcscpy_s` at `0x1800108fd`
- `msvcrt!wcscpy_s` at `0x1800109a7`
- `msvcrt!wcscpy_s` at `0x180010a9c`
- `msvcrt!wcscpy_s` at `0x1800108fd`
- `msvcrt!wcscpy_s` at `0x1800109a7`
- `msvcrt!wcscpy_s` at `0x180010a9c`
- `msvcrt!wcscat_s` at `0x180010913`
- `msvcrt!wcscat_s` at `0x1800109bd`
- `msvcrt!wcscat_s` at `0x180010aac`
- `msvcrt!wcscat_s` at `0x180010913`
- `msvcrt!wcscat_s` at `0x1800109bd`
- `msvcrt!wcscat_s` at `0x180010aac`

## pseudocode

```c
__int64 __fastcall CSiteCreator::InternalCreateNewSite(
        CSiteCreator *a1,
        __int64 a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4,
        unsigned __int8 *a5,
        __int64 a6,
        unsigned int *a7,
        unsigned int *a8)
{
  struct TService *v10; // rax
  struct TService **v11; // r13
  char v12; // si
  __int64 result; // rax
  const unsigned __int16 *v14; // r8
  unsigned __int8 *v15; // rdi
  unsigned int v16; // ebx
  wchar_t *v17; // rax
  unsigned int v18; // edi
  int v19; // ebx
  __int64 v20; // r15
  __int64 v21; // rax
  int v22; // eax
  unsigned int v23; // ecx
  __int64 v24; // rax
  unsigned int v25; // eax
  __int64 v26; // rcx
  unsigned __int8 *v27; // r12
  __int64 v28; // r15
  unsigned __int8 *v29; // [rsp+20h] [rbp-E0h]
  unsigned int v30; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int Value; // [rsp+54h] [rbp-ACh] BYREF
  unsigned __int8 v32[8]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int8 *v33; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int8 *v34; // [rsp+68h] [rbp-98h]
  __int64 v35; // [rsp+70h] [rbp-90h]
  unsigned int *v36; // [rsp+78h] [rbp-88h]
  wchar_t Destination[4]; // [rsp+80h] [rbp-80h] BYREF
  int v38; // [rsp+88h] [rbp-78h]
  int v39; // [rsp+8Ch] [rbp-74h]
  __int64 v40; // [rsp+90h] [rbp-70h]
  unsigned int *v41; // [rsp+98h] [rbp-68h]
  unsigned __int8 *v42; // [rsp+A0h] [rbp-60h]
  wchar_t Buffer[8]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v44; // [rsp+D0h] [rbp-30h]
  __int64 v45; // [rsp+E0h] [rbp-20h]
  wchar_t v46[56]; // [rsp+F0h] [rbp-10h] BYREF

  v34 = a5;
  v36 = a7;
  v35 = a6;
  v33 = a4;
  v30 = 0;
  Value = 0;
  v45 = 0;
  *(_OWORD *)Buffer = 0;
  v44 = 0;
  if ( a8 && (int)*a8 <= 0 )
    return 2147942487LL;
  v10 = (struct TService *)TServiceData::apService;
  v11 = (struct TService **)&TServiceData::apService;
  v12 = 1;
  while ( v10 && *(_DWORD *)v10 != 1 )
    v10 = *++v11;
  if ( !*v11 )
    return 2147942487LL;
  v14 = &hMem;
  if ( a3 )
    v14 = (const unsigned __int16 *)a3;
  result = CSiteCreator::InternalCreateNode(a1, *v11, v14, &v30, &Value, a8);
  if ( (int)result >= 0 )
  {
    v15 = (unsigned __int8 *)*((_QWORD *)*v11 + 3);
    v16 = 2 * *((_DWORD *)*v11 + 8) + 2;
    v17 = _ultow(Value, Buffer, 10);
    v29 = v15;
    v18 = v30;
    v19 = CSiteCreator::InternalSetData(a1, v30, v17, 0x3EAu, v29, v16, 0, 2u, 1u);
    if ( v19 < 0 )
      goto LABEL_37;
    v20 = -1;
    if ( a3 )
    {
      v21 = -1;
      do
        ++v21;
      while ( *(_WORD *)&a3[2 * v21] );
      v22 = CSiteCreator::InternalSetData(a1, v18, Buffer, 0x3F7u, a3, 2 * (int)v21 + 2, 1u, 2u, 1u);
      a3 = 0;
      v19 = v22;
      if ( v22 < 0 )
        goto LABEL_37;
    }
    if ( v33 )
    {
      v23 = (unsigned int)a3;
      do
      {
        v24 = -1;
        do
          ++v24;
        while ( *(_WORD *)&v33[2 * v23 + 2 * v24] != (_WORD)a3 );
        v25 = v24 + 1;
        v23 += v25;
      }
      while ( v25 > 1 );
      if ( v23 > 1 )
      {
        v19 = CSiteCreator::InternalSetData(a1, v18, Buffer, 0x3FFu, v33, 2 * v23, (unsigned int)a3, 5u, 1u);
        if ( v19 < 0 )
          goto LABEL_37;
      }
    }
    *(_DWORD *)v32 = (_DWORD)a3;
    v19 = CSiteCreator::InternalSetData(a1, v18, Buffer, 0x1770u, v32, 4u, 1u, 1u, 2u);
    if ( v19 < 0 )
      goto LABEL_37;
    v26 = *((_QWORD *)a1 + 7);
    v30 = (unsigned int)a3;
    v41 = &v30;
    LODWORD(v33) = (_DWORD)a3;
    v40 = 4;
    v42 = a3;
    *(_QWORD *)Destination = 1101;
    v38 = 1;
    v39 = 1;
    (*(void (__fastcall **)(__int64, _QWORD, const wchar_t *, wchar_t *, unsigned __int8 **))(*(_QWORD *)v26 + 80LL))(
      v26,
      v18,
      L"Info",
      Destination,
      &v33);
    if ( v30 >= 6 )
    {
      wcscpy_s(Destination, 0x1Eu, Buffer);
      wcscat_s(Destination, 0x1Eu, L"/filters/");
      v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, wchar_t *))(**((_QWORD **)a1 + 7) + 24LL))(
              *((_QWORD *)a1 + 7),
              v18,
              Destination);
      if ( v19 < 0 )
        goto LABEL_37;
      v19 = CSiteCreator::InternalSetData(
              a1,
              v18,
              Destination,
              0x3EAu,
              (unsigned __int8 *)L"IIsFilters",
              0x16u,
              (unsigned int)a3,
              2u,
              1u);
      if ( v19 < 0 )
        goto LABEL_37;
      v19 = CSiteCreator::SetAdminACL(a1, v18, Destination);
    }
    v27 = v34;
    if ( v34 )
    {
      wcscpy_s(Destination, 0x1Eu, Buffer);
      wcscat_s(Destination, 0x1Eu, L"/root/");
      v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, wchar_t *))(**((_QWORD **)a1 + 7) + 24LL))(
              *((_QWORD *)a1 + 7),
              v18,
              Destination);
      if ( v19 < 0 )
        goto LABEL_37;
      v19 = CSiteCreator::InternalSetData(
              a1,
              v18,
              Destination,
              0x3EAu,
              *((unsigned __int8 **)*v11 + 5),
              2 * *((_DWORD *)*v11 + 12) + 2,
              0,
              2u,
              1u);
      if ( v19 < 0 )
        goto LABEL_37;
      do
        ++v20;
      while ( *(_WORD *)&v27[2 * v20] );
      v19 = CSiteCreator::InternalSetData(a1, v18, Destination, 0xBB9u, v27, 2 * (int)v20 + 2, 1u, 2u, 2u);
      if ( v19 < 0 )
        goto LABEL_37;
      v28 = v35;
      if ( v35 )
      {
        wcscpy_s(v46, 0x32u, *((const wchar_t **)*v11 + 1));
        wcscat_s(v46, 0x32u, Destination);
        (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)a1 + 7) + 144LL))(*((_QWORD *)a1 + 7), v18);
        v12 = 0;
        v19 = (*(__int64 (__fastcall **)(__int64, wchar_t *, __int64, _QWORD, _DWORD))(*(_QWORD *)v28 + 24LL))(
                v28,
                v46,
                2,
                0,
                0);
        if ( v19 < 0 )
          return (unsigned int)v19;
      }
    }
    *v36 = Value;
    if ( !v12 )
      return (unsigned int)v19;
LABEL_37:
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)a1 + 7) + 144LL))(*((_QWORD *)a1 + 7), v18);
    return (unsigned int)v19;
  }
  return result;
}

```

## disassembly

```asm
0x180010638  mov     [rsp-8+arg_8], rbx
0x18001063d  push    rbp
0x18001063e  push    rsi
0x18001063f  push    rdi
0x180010640  push    r12
0x180010642  push    r13
0x180010644  push    r14
0x180010646  push    r15
0x180010648  lea     rbp, [rsp-70h]
0x18001064d  sub     rsp, 170h
0x180010654  mov     rax, cs:__security_cookie
0x18001065b  xor     rax, rsp
0x18001065e  mov     [rbp+0A0h+var_40], rax
0x180010662  mov     rax, [rbp+0A0h+arg_20]
0x180010669  xor     r15d, r15d
0x18001066c  mov     [rsp+1A0h+var_138], rax
0x180010671  mov     r14, rcx
0x180010674  mov     rax, [rbp+0A0h+arg_30]
0x18001067b  xorps   xmm0, xmm0
0x18001067e  mov     rcx, [rbp+0A0h+arg_28]
0x180010685  mov     r12, r8
0x180010688  mov     [rsp+1A0h+var_128], rax
0x18001068d  xor     eax, eax
0x18001068f  mov     [rsp+1A0h+var_130], rcx
0x180010694  mov     rcx, [rbp+0A0h+arg_38]
0x18001069b  mov     [rsp+1A0h+var_140], r9
0x1800106a0  mov     [rsp+1A0h+var_150], r15d
0x1800106a5  mov     [rsp+1A0h+Value], r15d
0x1800106aa  mov     [rbp+0A0h+var_C0], rax
0x1800106ae  movups  xmmword ptr [rbp+0A0h+Buffer], xmm0
0x1800106b2  movups  [rbp+0A0h+var_D0], xmm0
0x1800106b6  test    rcx, rcx
0x1800106b9  jz      short loc_1800106C0
0x1800106bb  cmp     [rcx], r15d
0x1800106be  jle     short loc_1800106EF
0x1800106c0  mov     rax, cs:?apService@TServiceData@@2PAPEAUTService@@A; TService * near * TServiceData::apService
0x1800106c7  lea     r13, ?apService@TServiceData@@2PAPEAUTService@@A; TService * near * TServiceData::apService
0x1800106ce  mov     esi, 1
0x1800106d3  jmp     short loc_1800106E1
0x1800106d5  cmp     [rax], esi
0x1800106d7  jz      short loc_1800106E6
0x1800106d9  add     r13, 8
0x1800106dd  mov     rax, [r13+0]
0x1800106e1  test    rax, rax
0x1800106e4  jnz     short loc_1800106D5
0x1800106e6  mov     rdx, [r13+0]; struct TService *
0x1800106ea  test    rdx, rdx
0x1800106ed  jnz     short loc_1800106F9
0x1800106ef  mov     eax, 80070057h
0x1800106f4  jmp     loc_180010B17
0x1800106f9  mov     [rsp+1A0h+var_178], rcx; unsigned int *
0x1800106fe  lea     rax, [rsp+1A0h+Value]
0x180010703  test    r12, r12
0x180010706  mov     [rsp+1A0h+var_180], rax; unsigned int *
0x18001070b  lea     r8, hMem
0x180010712  mov     rcx, r14; this
0x180010715  cmovnz  r8, r12; unsigned __int16 *
0x180010719  lea     r9, [rsp+1A0h+var_150]; unsigned int *
0x18001071e  call    ?InternalCreateNode@CSiteCreator@@AEAAJPEAUTService@@PEBGPEAK2QEAK@Z; CSiteCreator::InternalCreateNode(TService *,ushort const *,ulong *,ulong *,ulong * const)
0x180010723  test    eax, eax
0x180010725  js      loc_180010B17
0x18001072b  mov     rcx, [r13+0]
0x18001072f  lea     rdx, [rbp+0A0h+Buffer]; Buffer
0x180010733  mov     r8d, 0Ah; Radix
0x180010739  mov     eax, [rcx+20h]
0x18001073c  mov     rdi, [rcx+18h]
0x180010740  mov     ecx, [rsp+1A0h+Value]; Value
0x180010744  lea     ebx, ds:2[rax*2]
0x18001074b  call    cs:__imp__ultow
0x180010751  mov     [rsp+1A0h+var_160], esi; unsigned int
0x180010755  mov     r9d, 3EAh; unsigned int
0x18001075b  mov     [rsp+1A0h+var_168], 2; unsigned int
0x180010763  mov     r8, rax; unsigned __int16 *
0x180010766  mov     [rsp+1A0h+var_170], r15d; unsigned int
0x18001076b  mov     rcx, r14; this
0x18001076e  mov     dword ptr [rsp+1A0h+var_178], ebx; unsigned int
0x180010772  mov     [rsp+1A0h+var_180], rdi; unsigned __int8 *
0x180010777  mov     edi, [rsp+1A0h+var_150]
0x18001077b  mov     edx, edi; unsigned int
0x18001077d  call    ?InternalSetData@CSiteCreator@@AEAAJKPEBGKPEAEKKKK@Z; CSiteCreator::InternalSetData(ulong,ushort const *,ulong,uchar *,ulong,ulong,ulong,ulong)
0x180010782  mov     ebx, eax
0x180010784  test    eax, eax
0x180010786  js      loc_180010B00
0x18001078c  or      r15, 0FFFFFFFFFFFFFFFFh
0x180010790  xor     ecx, ecx
0x180010792  test    r12, r12
0x180010795  jz      short loc_1800107E5
0x180010797  mov     rax, r15
0x18001079a  inc     rax
0x18001079d  cmp     [r12+rax*2], cx
0x1800107a2  jnz     short loc_18001079A
0x1800107a4  mov     [rsp+1A0h+var_160], esi; unsigned int
0x1800107a8  lea     eax, ds:2[rax*2]
0x1800107af  mov     [rsp+1A0h+var_168], 2; unsigned int
0x1800107b7  lea     r8, [rbp+0A0h+Buffer]; unsigned __int16 *
0x1800107bb  mov     [rsp+1A0h+var_170], esi; unsigned int
0x1800107bf  mov     r9d, 3F7h; unsigned int
0x1800107c5  mov     dword ptr [rsp+1A0h+var_178], eax; unsigned int
0x1800107c9  mov     edx, edi; unsigned int
0x1800107cb  mov     rcx, r14; this
0x1800107ce  mov     [rsp+1A0h+var_180], r12; unsigned __int8 *
0x1800107d3  call    ?InternalSetData@CSiteCreator@@AEAAJKPEBGKPEAEKKKK@Z; CSiteCreator::InternalSetData(ulong,ushort const *,ulong,uchar *,ulong,ulong,ulong,ulong)
0x1800107d8  xor     r12d, r12d
0x1800107db  mov     ebx, eax
0x1800107dd  test    eax, eax
0x1800107df  js      loc_180010B00
0x1800107e5  mov     r8, [rsp+1A0h+var_140]
0x1800107ea  test    r8, r8
0x1800107ed  jz      short loc_18001084C
0x1800107ef  mov     ecx, r12d
0x1800107f2  mov     eax, ecx
0x1800107f4  lea     rdx, [r8+rax*2]
0x1800107f8  mov     rax, r15
0x1800107fb  inc     rax
0x1800107fe  cmp     [rdx+rax*2], r12w
0x180010803  jnz     short loc_1800107FB
0x180010805  inc     eax
0x180010807  add     ecx, eax
0x180010809  cmp     eax, esi
0x18001080b  ja      short loc_1800107F2
0x18001080d  cmp     ecx, esi
0x18001080f  jbe     short loc_18001084C
0x180010811  mov     [rsp+1A0h+var_160], esi; unsigned int
0x180010815  lea     eax, [rcx+rcx]
0x180010818  mov     [rsp+1A0h+var_168], 5; unsigned int
0x180010820  mov     r9d, 3FFh; unsigned int
0x180010826  mov     [rsp+1A0h+var_170], r12d; unsigned int
0x18001082b  mov     edx, edi; unsigned int
0x18001082d  mov     dword ptr [rsp+1A0h+var_178], eax; unsigned int
0x180010831  mov     rcx, r14; this
0x180010834  mov     [rsp+1A0h+var_180], r8; unsigned __int8 *
0x180010839  lea     r8, [rbp+0A0h+Buffer]; unsigned __int16 *
0x18001083d  call    ?InternalSetData@CSiteCreator@@AEAAJKPEBGKPEAEKKKK@Z; CSiteCreator::InternalSetData(ulong,ushort const *,ulong,uchar *,ulong,ulong,ulong,ulong)
0x180010842  mov     ebx, eax
0x180010844  test    eax, eax
0x180010846  js      loc_180010B00
0x18001084c  mov     [rsp+1A0h+var_160], 2; unsigned int
0x180010854  lea     rax, [rsp+1A0h+var_148]
0x180010859  mov     [rsp+1A0h+var_168], esi; unsigned int
0x18001085d  lea     r8, [rbp+0A0h+Buffer]; unsigned __int16 *
0x180010861  mov     [rsp+1A0h+var_170], esi; unsigned int
0x180010865  mov     r9d, 1770h; unsigned int
0x18001086b  mov     dword ptr [rsp+1A0h+var_178], 4; unsigned int
0x180010873  mov     edx, edi; unsigned int
0x180010875  mov     rcx, r14; this
0x180010878  mov     [rsp+1A0h+var_180], rax; unsigned __int8 *
0x18001087d  mov     dword ptr [rsp+1A0h+var_148], r12d
0x180010882  call    ?InternalSetData@CSiteCreator@@AEAAJKPEBGKPEAEKKKK@Z; CSiteCreator::InternalSetData(ulong,ushort const *,ulong,uchar *,ulong,ulong,ulong,ulong)
0x180010887  mov     ebx, eax
0x180010889  test    eax, eax
0x18001088b  js      loc_180010B00
0x180010891  mov     rcx, [r14+38h]
0x180010895  lea     rdx, [rsp+1A0h+var_140]
0x18001089a  lea     rax, [rsp+1A0h+var_150]
0x18001089f  mov     [rsp+1A0h+var_150], r12d
0x1800108a4  mov     [rbp+0A0h+var_108], rax
0x1800108a8  lea     r9, [rbp+0A0h+Destination]
0x1800108ac  mov     dword ptr [rsp+1A0h+var_140], r12d
0x1800108b1  lea     r8, aInfo; "Info"
0x1800108b8  mov     [rbp+0A0h+var_110], 4
0x1800108c0  mov     [rbp+0A0h+var_100], r12
0x1800108c4  mov     qword ptr [rbp+0A0h+Destination], 44Dh
0x1800108cc  mov     [rbp+0A0h+var_118], esi
0x1800108cf  mov     [rbp+0A0h+var_114], esi
0x1800108d2  mov     rax, [rcx]
0x1800108d5  mov     [rsp+1A0h+var_180], rdx
0x1800108da  mov     edx, edi
0x1800108dc  mov     rax, [rax+50h]
0x1800108e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108e5  cmp     [rsp+1A0h+var_150], 6
0x1800108ea  jb      loc_18001098C
0x1800108f0  lea     r8, [rbp+0A0h+Buffer]; Source
0x1800108f4  mov     edx, 1Eh; SizeInWords
0x1800108f9  lea     rcx, [rbp+0A0h+Destination]; Destination
0x1800108fd  call    cs:__imp_wcscpy_s
0x180010903  lea     r8, aFilters; "/filters/"
0x18001090a  mov     edx, 1Eh; SizeInWords
0x18001090f  lea     rcx, [rbp+0A0h+Destination]; Destination
0x180010913  call    cs:__imp_wcscat_s
0x180010919  mov     rcx, [r14+38h]
0x18001091d  lea     r8, [rbp+0A0h+Destination]
0x180010921  mov     edx, edi
0x180010923  mov     rax, [rcx]
0x180010926  mov     rax, [rax+18h]
0x18001092a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001092f  mov     ebx, eax
0x180010931  test    eax, eax
0x180010933  js      loc_180010B00
0x180010939  mov     [rsp+1A0h+var_160], esi; unsigned int
0x18001093d  lea     rax, aIisfilters; "IIsFilters"
0x180010944  mov     [rsp+1A0h+var_168], 2; unsigned int
0x18001094c  lea     r8, [rbp+0A0h+Destination]; unsigned __int16 *
0x180010950  mov     [rsp+1A0h+var_170], r12d; unsigned int
0x180010955  mov     r9d, 3EAh; unsigned int
0x18001095b  mov     dword ptr [rsp+1A0h+var_178], 16h; unsigned int
0x180010963  mov     edx, edi; unsigned int
0x180010965  mov     rcx, r14; this
0x180010968  mov     [rsp+1A0h+var_180], rax; unsigned __int8 *
0x18001096d  call    ?InternalSetData@CSiteCreator@@AEAAJKPEBGKPEAEKKKK@Z; CSiteCreator::InternalSetData(ulong,ushort const *,ulong,uchar *,ulong,ulong,ulong,ulong)
0x180010972  mov     ebx, eax
0x180010974  test    eax, eax
0x180010976  js      loc_180010B00
0x18001097c  lea     r8, [rbp+0A0h+Destination]; unsigned __int16 *
0x180010980  mov     edx, edi; unsigned int
0x180010982  mov     rcx, r14; this
0x180010985  call    ?SetAdminACL@CSiteCreator@@AEAAJKPEBG@Z; CSiteCreator::SetAdminACL(ulong,ushort const *)
0x18001098a  mov     ebx, eax
0x18001098c  mov     r12, [rsp+1A0h+var_138]
0x180010991  test    r12, r12
0x180010994  jz      loc_180010AF0
0x18001099a  lea     r8, [rbp+0A0h+Buffer]; Source
0x18001099e  mov     edx, 1Eh; SizeInWords
0x1800109a3  lea     rcx, [rbp+0A0h+Destination]; Destination
0x1800109a7  call    cs:__imp_wcscpy_s
0x1800109ad  lea     r8, aRoot; "/root/"
0x1800109b4  mov     edx, 1Eh; SizeInWords
0x1800109b9  lea     rcx, [rbp+0A0h+Destination]; Destination
0x1800109bd  call    cs:__imp_wcscat_s
0x1800109c3  mov     rcx, [r14+38h]
0x1800109c7  lea     r8, [rbp+0A0h+Destination]
0x1800109cb  mov     edx, edi
0x1800109cd  mov     rax, [rcx]
0x1800109d0  mov     rax, [rax+18h]
0x1800109d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109d9  mov     ebx, eax
0x1800109db  test    eax, eax
0x1800109dd  js      loc_180010B00
0x1800109e3  mov     rcx, [r13+0]
0x1800109e7  lea     r8, [rbp+0A0h+Destination]; unsigned __int16 *
0x1800109eb  mov     [rsp+1A0h+var_160], esi; unsigned int
0x1800109ef  mov     r9d, 3EAh; unsigned int
0x1800109f5  mov     [rsp+1A0h+var_168], 2; unsigned int
0x1800109fd  mov     edx, edi; unsigned int
0x1800109ff  mov     [rsp+1A0h+var_170], 0; unsigned int
0x180010a07  mov     eax, [rcx+30h]
0x180010a0a  lea     eax, ds:2[rax*2]
0x180010a11  mov     dword ptr [rsp+1A0h+var_178], eax; unsigned int
0x180010a15  mov     rax, [rcx+28h]
0x180010a19  mov     rcx, r14; this
0x180010a1c  mov     [rsp+1A0h+var_180], rax; unsigned __int8 *
0x180010a21  call    ?InternalSetData@CSiteCreator@@AEAAJKPEBGKPEAEKKKK@Z; CSiteCreator::InternalSetData(ulong,ushort const *,ulong,uchar *,ulong,ulong,ulong,ulong)
0x180010a26  mov     ebx, eax
0x180010a28  xor     eax, eax
0x180010a2a  test    ebx, ebx
0x180010a2c  js      loc_180010B00
0x180010a32  inc     r15
0x180010a35  cmp     [r12+r15*2], ax
0x180010a3a  jnz     short loc_180010A32
0x180010a3c  mov     ecx, 2
0x180010a41  lea     eax, ds:2[r15*2]
0x180010a49  mov     [rsp+1A0h+var_160], ecx; unsigned int
0x180010a4d  lea     r8, [rbp+0A0h+Destination]; unsigned __int16 *
0x180010a51  mov     [rsp+1A0h+var_168], ecx; unsigned int
0x180010a55  mov     r9d, 0BB9h; unsigned int
0x180010a5b  mov     [rsp+1A0h+var_170], esi; unsigned int
0x180010a5f  mov     edx, edi; unsigned int
0x180010a61  mov     dword ptr [rsp+1A0h+var_178], eax; unsigned int
0x180010a65  mov     rcx, r14; this
0x180010a68  mov     [rsp+1A0h+var_180], r12; unsigned __int8 *
0x180010a6d  call    ?InternalSetData@CSiteCreator@@AEAAJKPEBGKPEAEKKKK@Z; CSiteCreator::InternalSetData(ulong,ushort const *,ulong,uchar *,ulong,ulong,ulong,ulong)
0x180010a72  xor     r12d, r12d
0x180010a75  mov     ebx, eax
0x180010a77  test    eax, eax
0x180010a79  js      loc_180010B00
0x180010a7f  mov     r15, [rsp+1A0h+var_130]
0x180010a84  test    r15, r15
0x180010a87  jz      short loc_180010AF0
0x180010a89  mov     r8, [r13+0]
0x180010a8d  lea     ebx, [r12+32h]
0x180010a92  mov     edx, ebx; SizeInWords
0x180010a94  lea     rcx, [rbp+0A0h+var_B0]; Destination
0x180010a98  mov     r8, [r8+8]; Source
0x180010a9c  call    cs:__imp_wcscpy_s
0x180010aa2  lea     r8, [rbp+0A0h+Destination]; Source
0x180010aa6  mov     edx, ebx; SizeInWords
0x180010aa8  lea     rcx, [rbp+0A0h+var_B0]; Destination
0x180010aac  call    cs:__imp_wcscat_s
0x180010ab2  mov     rcx, [r14+38h]
0x180010ab6  mov     edx, edi
0x180010ab8  mov     rax, [rcx]
0x180010abb  mov     rax, [rax+90h]
0x180010ac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ac7  mov     rax, [r15]
0x180010aca  lea     r8d, [r12+2]
0x180010acf  xor     r9d, r9d
0x180010ad2  mov     dword ptr [rsp+1A0h+var_180], r12d
0x180010ad7  lea     rdx, [rbp+0A0h+var_B0]
0x180010adb  mov     rcx, r15
0x180010ade  mov     sil, r12b
0x180010ae1  mov     rax, [rax+18h]
0x180010ae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010aea  mov     ebx, eax
0x180010aec  test    eax, eax
0x180010aee  js      short loc_180010B15
0x180010af0  mov     rcx, [rsp+1A0h+var_128]
0x180010af5  mov     eax, [rsp+1A0h+Value]
0x180010af9  mov     [rcx], eax
0x180010afb  test    sil, sil
0x180010afe  jz      short loc_180010B15
0x180010b00  mov     rcx, [r14+38h]
  ... truncated ...
```
