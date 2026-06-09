# CITETranslateBitmapBits

- ea: `0x180051aa0`
- end: `0x180051f48`
- name: `CITETranslateBitmapBits`
- size: `1192`
- prototype: `__int64 __fastcall(__int64, __int64, enum BMFORMAT, unsigned int, unsigned int, unsigned int, __int64, enum BMFORMAT, unsigned int, unsigned int (__fastcall *)(_QWORD, _QWORD, __int64), __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18000ea20`

## callees

- `0x180018eb0`
- `0x18001b074`
- `0x1800286cc`
- `0x18002e5f0`
- `0x18002e670`
- `0x180051aa0`
- `0x180054b08`
- `0x180084010`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180051f08`
- `ntdll!EtwEventWrite` at `0x180051f08`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180051da4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180051e38`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180051e61`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180051da4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180051e38`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180051e61`

## pseudocode

```c
__int64 __fastcall CITETranslateBitmapBits(
        __int64 a1,
        __int64 a2,
        enum BMFORMAT a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        __int64 a7,
        enum BMFORMAT a8,
        unsigned int a9,
        unsigned int (__fastcall *a10)(_QWORD, _QWORD, __int64),
        __int64 a11)
{
  __int64 *v13; // r15
  __int64 v14; // r10
  __int64 (__fastcall *v15)(__int64, _QWORD, __int64); // rax
  unsigned __int64 v16; // rdi
  int v17; // ebx
  int v18; // ecx
  struct ICITEPixelConverter *v19; // rsi
  int v20; // eax
  struct ICITEPixelConverter *v21; // r14
  unsigned int v22; // eax
  unsigned int v23; // r15d
  unsigned int v24; // r12d
  unsigned int v25; // eax
  unsigned int v26; // ecx
  unsigned int v27; // r15d
  struct ICITEPixelConverter *v28; // r12
  struct ICITEPixelConverter *v29; // r15
  unsigned int v30; // r15d
  __int64 v31; // rax
  void *v32; // rax
  DWORD TickCount; // r12d
  __int64 v35; // [rsp+68h] [rbp-69h] BYREF
  struct ICITEPixelConverter *v36; // [rsp+70h] [rbp-61h] BYREF
  struct ICITEPixelConverter *v37; // [rsp+78h] [rbp-59h] BYREF
  unsigned int v38; // [rsp+80h] [rbp-51h]
  int v39; // [rsp+84h] [rbp-4Dh] BYREF
  unsigned int v40; // [rsp+88h] [rbp-49h]
  __int64 v41; // [rsp+90h] [rbp-41h]
  struct ICITEPixelConverter *v42; // [rsp+98h] [rbp-39h]
  struct ICITEPixelConverter *v43; // [rsp+A0h] [rbp-31h]
  unsigned int (__fastcall *v44)(_QWORD, _QWORD, __int64); // [rsp+A8h] [rbp-29h]
  _QWORD v45[2]; // [rsp+B0h] [rbp-21h] BYREF

  v13 = *(__int64 **)((a1 ^ 0x49434D20) + 0x18);
  v14 = *v13;
  v39 = 1;
  v15 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v14 + 40LL);
  v16 = a4;
  v41 = a7;
  v44 = a10;
  v45[0] = v14;
  v17 = v15(v14, a10, a11);
  if ( v17 == -2147467263 )
  {
    v39 = 0;
    if ( !a2 || !(_DWORD)v16 || !a5 || !a7 )
    {
      v17 = -2147024809;
      goto LABEL_43;
    }
    v18 = *((_DWORD *)v13 + 5);
    v19 = 0;
    v36 = 0;
    v37 = 0;
    v20 = CreateCITEPixelConverter(v18, a3, v16, a6, &v37);
    v21 = v37;
    v17 = v20;
    if ( v20 >= 0 )
    {
      v17 = CreateCITEPixelConverter(*((_DWORD *)v13 + 5), a8, v16, a9, &v36);
      if ( v17 < 0 )
      {
        v19 = v36;
      }
      else
      {
        v22 = (*(__int64 (__fastcall **)(struct ICITEPixelConverter *))(*(_QWORD *)v21 + 32LL))(v21);
        v19 = v36;
        v23 = v22;
        v24 = (*(__int64 (__fastcall **)(struct ICITEPixelConverter *))(*(_QWORD *)v36 + 32LL))(v36);
        v38 = (*(__int64 (__fastcall **)(struct ICITEPixelConverter *))(*(_QWORD *)v21 + 16LL))(v21);
        v25 = (*(__int64 (__fastcall **)(struct ICITEPixelConverter *))(*(_QWORD *)v19 + 16LL))(v19);
        v40 = v25;
        if ( (unsigned int)v16 <= 0x3FFFFFFF / v38
          && (unsigned int)v16 <= 0x3FFFFFFF / v25
          && (unsigned int)v16 <= 0x3FFFFFFF / v23
          && (unsigned int)v16 <= 0x3FFFFFFF / v24
          && (v26 = v23 * v16) != 0
          && v24 * (_DWORD)v16
          && v38 * (_DWORD)v16
          && (v27 = v25 * v16) != 0
          && v26 <= a6
          && v24 * (unsigned int)v16 <= a9 )
        {
          v42 = (struct ICITEPixelConverter *)operator new(saturated_mul(v38 * (unsigned int)v16, 4u));
          v28 = v42;
          v36 = 0;
          NCoreLibrary::TGenericSP<LuvColorF,NCoreLibrary::TAutoPtrArray<LuvColorF>,LuvColorF *,0,LuvColorF const *>::Reset(&v36);
          v36 = v28;
          v43 = (struct ICITEPixelConverter *)operator new(saturated_mul(v27, 4u));
          v29 = v43;
          v37 = 0;
          NCoreLibrary::TGenericSP<LuvColorF,NCoreLibrary::TAutoPtrArray<LuvColorF>,LuvColorF *,0,LuvColorF const *>::Reset(&v37);
          v37 = v29;
          v30 = 0;
          v35 = 0;
          NCoreLibrary::TGenericSP<LuvColorF,NCoreLibrary::TAutoPtrArray<LuvColorF>,LuvColorF *,0,LuvColorF const *>::Reset(&v35);
          v31 = *(_QWORD *)v21;
          v35 = 0;
          if ( (*(unsigned int (__fastcall **)(struct ICITEPixelConverter *))(v31 + 24))(v21)
            && (*(unsigned int (__fastcall **)(struct ICITEPixelConverter *))(*(_QWORD *)v19 + 24LL))(v19)
            && (v32 = operator new(saturated_mul(v16, 4u)),
                NCoreLibrary::TAutoPtrArray<enum CHuePlane::ECacheStatus>::operator=(&v35, v32),
                !v35) )
          {
            v17 = -2147024882;
          }
          else
          {
            TickCount = GetTickCount();
            while ( v30 < a5 )
            {
              v17 = (*(__int64 (__fastcall **)(struct ICITEPixelConverter *, __int64, struct ICITEPixelConverter *, __int64))(*(_QWORD *)v21 + 48LL))(
                      v21,
                      a2,
                      v42,
                      v35);
              if ( v17 < 0 )
                break;
              v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, struct ICITEPixelConverter *, struct ICITEPixelConverter *))(*(_QWORD *)v45[0] + 32LL))(
                      v45[0],
                      (unsigned int)v16,
                      v38,
                      v40,
                      v42,
                      v43);
              if ( v17 < 0 )
                break;
              v17 = (*(__int64 (__fastcall **)(struct ICITEPixelConverter *, struct ICITEPixelConverter *, __int64, __int64))(*(_QWORD *)v19 + 40LL))(
                      v19,
                      v43,
                      v35,
                      v41);
              if ( v17 < 0 )
                break;
              if ( v44 && GetTickCount() - TickCount > 0x64 )
              {
                if ( !v44(a5, v30 + 1, a11) )
                {
                  v17 = -2147023673;
                  break;
                }
                TickCount = GetTickCount();
              }
              a2 += a6;
              v41 += a9;
              ++v30;
            }
          }
          NCoreLibrary::TGenericSP<LuvColorF,NCoreLibrary::TAutoPtrArray<LuvColorF>,LuvColorF *,0,LuvColorF const *>::Reset(&v35);
          NCoreLibrary::TGenericSP<LuvColorF,NCoreLibrary::TAutoPtrArray<LuvColorF>,LuvColorF *,0,LuvColorF const *>::Reset(&v37);
          NCoreLibrary::TGenericSP<LuvColorF,NCoreLibrary::TAutoPtrArray<LuvColorF>,LuvColorF *,0,LuvColorF const *>::Reset(&v36);
        }
        else
        {
          v17 = -2147024809;
        }
      }
    }
    if ( v21 )
      (**(void (__fastcall ***)(struct ICITEPixelConverter *, __int64))v21)(v21, 1);
    if ( v19 )
      (**(void (__fastcall ***)(struct ICITEPixelConverter *, __int64))v19)(v19, 1);
  }
  if ( v17 >= 0 )
  {
    v45[1] = 4;
    v45[0] = &v39;
    EtwEventWrite(g_etwHandle, FLOATING_POINT_OR_INTEGER_LUT, 1, v45);
    return 1;
  }
LABEL_43:
  SetLastErrorFromHRESULT((unsigned int)v17, 2020);
  return 0;
}

```

## disassembly

```asm
0x180051aa0  push    rbp
0x180051aa2  push    rbx
0x180051aa3  push    rsi
0x180051aa4  push    rdi
0x180051aa5  push    r12
0x180051aa7  push    r13
0x180051aa9  push    r14
0x180051aab  push    r15
0x180051aad  lea     rbp, [rsp-7]
0x180051ab2  sub     rsp, 0D8h
0x180051ab9  mov     rax, cs:__security_cookie
0x180051ac0  xor     rax, rsp
0x180051ac3  mov     [rbp+3Fh+var_50], rax
0x180051ac7  mov     r11, [rbp+3Fh+arg_48]
0x180051ace  xor     rcx, 49434D20h
0x180051ad5  mov     rsi, [rbp+3Fh+arg_30]
0x180051ad9  mov     r13, rdx
0x180051adc  mov     edx, [rbp+3Fh+arg_40]
0x180051ae2  mov     r14d, r8d
0x180051ae5  mov     r8d, [rbp+3Fh+arg_28]
0x180051ae9  mov     r15, [rcx+18h]
0x180051aed  mov     ecx, [rbp+3Fh+arg_20]
0x180051af0  mov     r12d, [rbp+3Fh+arg_38]
0x180051af7  mov     [rsp+110h+var_C0], rsi
0x180051afc  mov     r10, [r15]
0x180051aff  mov     [rsp+110h+var_C8], edx
0x180051b03  mov     [rsp+110h+var_D0], r12d
0x180051b08  mov     [rsp+110h+var_D8], r13
0x180051b0d  mov     [rsp+110h+var_E0], r8d
0x180051b12  mov     [rbp+3Fh+var_8C], 1
0x180051b19  mov     rax, [r10]
0x180051b1c  mov     [rbp+3Fh+var_B0], r8d
0x180051b20  mov     r8, [rbp+3Fh+arg_50]
0x180051b27  mov     [rbp+3Fh+var_AC], edx
0x180051b2a  mov     rdx, r11
0x180051b2d  mov     rax, [rax+28h]
0x180051b31  mov     dword ptr [rsp+110h+var_E8], r14d
0x180051b36  mov     dword ptr [rsp+110h+var_F0], ecx
0x180051b3a  mov     rcx, r10
0x180051b3d  mov     edi, r9d
0x180051b40  mov     [rbp+3Fh+var_80], rsi
0x180051b44  mov     [rbp+3Fh+var_68], r11
0x180051b48  mov     [rbp+3Fh+var_60], r10
0x180051b4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051b51  mov     ebx, eax
0x180051b53  cmp     eax, 80004001h
0x180051b58  jnz     loc_180051EDC
0x180051b5e  mov     [rbp+3Fh+var_8C], 0
0x180051b65  test    r13, r13
0x180051b68  jz      loc_180051F15
0x180051b6e  test    edi, edi
0x180051b70  jz      loc_180051F15
0x180051b76  cmp     [rbp+3Fh+arg_20], 0
0x180051b7a  jz      loc_180051F15
0x180051b80  test    rsi, rsi
0x180051b83  jz      loc_180051F15
0x180051b89  mov     r9d, [rbp+3Fh+var_B0]; unsigned int
0x180051b8d  lea     rax, [rbp+3Fh+var_98]
0x180051b91  mov     ecx, [r15+14h]; int
0x180051b95  xor     esi, esi
0x180051b97  mov     r8d, edi; unsigned int
0x180051b9a  mov     [rbp+3Fh+var_A0], rsi
0x180051b9e  mov     edx, r14d; enum BMFORMAT
0x180051ba1  mov     [rsp+110h+var_F0], rax; struct ICITEPixelConverter **
0x180051ba6  mov     [rbp+3Fh+var_98], 0
0x180051bae  call    ?CreateCITEPixelConverter@@YAJHW4BMFORMAT@@IIPEAPEAVICITEPixelConverter@@@Z; CreateCITEPixelConverter(int,BMFORMAT,uint,uint,ICITEPixelConverter * *)
0x180051bb3  mov     r14, [rbp+3Fh+var_98]
0x180051bb7  mov     ebx, eax
0x180051bb9  test    eax, eax
0x180051bbb  js      loc_180051EAC
0x180051bc1  mov     r9d, [rbp+3Fh+var_AC]; unsigned int
0x180051bc5  lea     rax, [rbp+3Fh+var_A0]
0x180051bc9  mov     ecx, [r15+14h]; int
0x180051bcd  mov     r8d, edi; unsigned int
0x180051bd0  mov     edx, r12d; enum BMFORMAT
0x180051bd3  mov     [rsp+110h+var_F0], rax; struct ICITEPixelConverter **
0x180051bd8  call    ?CreateCITEPixelConverter@@YAJHW4BMFORMAT@@IIPEAPEAVICITEPixelConverter@@@Z; CreateCITEPixelConverter(int,BMFORMAT,uint,uint,ICITEPixelConverter * *)
0x180051bdd  mov     ebx, eax
0x180051bdf  test    eax, eax
0x180051be1  js      loc_180051EA8
0x180051be7  mov     rax, [r14]
0x180051bea  mov     rcx, r14
0x180051bed  mov     rax, [rax+20h]
0x180051bf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051bf6  mov     rsi, [rbp+3Fh+var_A0]
0x180051bfa  mov     r15d, eax
0x180051bfd  mov     rcx, rsi
0x180051c00  mov     rax, [rsi]
0x180051c03  mov     rax, [rax+20h]
0x180051c07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051c0c  mov     r12d, eax
0x180051c0f  mov     rcx, r14
0x180051c12  mov     rax, [r14]
0x180051c15  mov     rax, [rax+10h]
0x180051c19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051c1e  mov     [rbp+3Fh+var_90], eax
0x180051c21  mov     rcx, rsi
0x180051c24  mov     rax, [rsi]
0x180051c27  mov     rax, [rax+10h]
0x180051c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051c30  mov     r9d, [rbp+3Fh+var_90]
0x180051c34  mov     r8d, eax
0x180051c37  mov     [rbp+3Fh+var_88], eax
0x180051c3a  xor     edx, edx
0x180051c3c  mov     ecx, 3FFFFFFFh
0x180051c41  mov     eax, ecx
0x180051c43  div     r9d
0x180051c46  cmp     edi, eax
0x180051c48  ja      loc_180051EA1
0x180051c4e  xor     edx, edx
0x180051c50  mov     eax, ecx
0x180051c52  div     r8d
0x180051c55  cmp     edi, eax
0x180051c57  ja      loc_180051EA1
0x180051c5d  xor     edx, edx
0x180051c5f  mov     eax, ecx
0x180051c61  div     r15d
0x180051c64  cmp     edi, eax
0x180051c66  ja      loc_180051EA1
0x180051c6c  xor     edx, edx
0x180051c6e  mov     eax, ecx
0x180051c70  div     r12d
0x180051c73  cmp     edi, eax
0x180051c75  ja      loc_180051EA1
0x180051c7b  mov     ecx, edi
0x180051c7d  imul    ecx, r15d
0x180051c81  test    ecx, ecx
0x180051c83  jz      loc_180051EA1
0x180051c89  mov     eax, edi
0x180051c8b  imul    eax, r12d
0x180051c8f  test    eax, eax
0x180051c91  jz      loc_180051EA1
0x180051c97  mov     edx, edi
0x180051c99  imul    edx, r9d
0x180051c9d  test    edx, edx
0x180051c9f  jz      loc_180051EA1
0x180051ca5  mov     r15d, edi
0x180051ca8  imul    r15d, r8d
0x180051cac  test    r15d, r15d
0x180051caf  jz      loc_180051EA1
0x180051cb5  cmp     ecx, [rbp+3Fh+var_B0]
0x180051cb8  ja      loc_180051EA1
0x180051cbe  cmp     eax, [rbp+3Fh+var_AC]
0x180051cc1  ja      loc_180051EA1
0x180051cc7  mov     ecx, edx
0x180051cc9  mov     eax, 4
0x180051cce  mul     rcx
0x180051cd1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180051cd8  cmovb   rax, rcx
0x180051cdc  mov     rcx, rax; Size
0x180051cdf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180051ce4  lea     rcx, [rbp+3Fh+var_A0]
0x180051ce8  mov     [rbp+3Fh+var_78], rax
0x180051cec  mov     r12, rax
0x180051cef  mov     [rbp+3Fh+var_A0], 0
0x180051cf7  call    ?Reset@?$TGenericSP@ULuvColorF@@V?$TAutoPtrArray@ULuvColorF@@@NCoreLibrary@@PEAU1@$0A@PEBU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<LuvColorF,NCoreLibrary::TAutoPtrArray<LuvColorF>,LuvColorF *,0,LuvColorF const *>::Reset(void)
0x180051cfc  mov     ecx, r15d
0x180051cff  mov     eax, 4
0x180051d04  mul     rcx
0x180051d07  mov     [rbp+3Fh+var_A0], r12
0x180051d0b  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180051d12  cmovb   rax, r12
0x180051d16  mov     rcx, rax; Size
0x180051d19  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180051d1e  lea     rcx, [rbp+3Fh+var_98]
0x180051d22  mov     [rbp+3Fh+var_70], rax
0x180051d26  mov     r15, rax
0x180051d29  mov     [rbp+3Fh+var_98], 0
0x180051d31  call    ?Reset@?$TGenericSP@ULuvColorF@@V?$TAutoPtrArray@ULuvColorF@@@NCoreLibrary@@PEAU1@$0A@PEBU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<LuvColorF,NCoreLibrary::TAutoPtrArray<LuvColorF>,LuvColorF *,0,LuvColorF const *>::Reset(void)
0x180051d36  mov     [rbp+3Fh+var_98], r15
0x180051d3a  lea     rcx, [rbp+3Fh+var_A8]
0x180051d3e  xor     r15d, r15d
0x180051d41  mov     [rbp+3Fh+var_A8], r15
0x180051d45  call    ?Reset@?$TGenericSP@ULuvColorF@@V?$TAutoPtrArray@ULuvColorF@@@NCoreLibrary@@PEAU1@$0A@PEBU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<LuvColorF,NCoreLibrary::TAutoPtrArray<LuvColorF>,LuvColorF *,0,LuvColorF const *>::Reset(void)
0x180051d4a  mov     rax, [r14]
0x180051d4d  mov     rcx, r14
0x180051d50  mov     [rbp+3Fh+var_A8], r15
0x180051d54  mov     rax, [rax+18h]
0x180051d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051d5d  test    eax, eax
0x180051d5f  jz      short loc_180051DA4
0x180051d61  mov     rax, [rsi]
0x180051d64  mov     rcx, rsi
0x180051d67  mov     rax, [rax+18h]
0x180051d6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051d70  test    eax, eax
0x180051d72  jz      short loc_180051DA4
0x180051d74  lea     eax, [r12+5]
0x180051d79  mul     rdi
0x180051d7c  cmovb   rax, r12
0x180051d80  mov     rcx, rax; Size
0x180051d83  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180051d88  mov     rdx, rax
0x180051d8b  lea     rcx, [rbp+3Fh+var_A8]
0x180051d8f  call    ??4?$TAutoPtrArray@W4ECacheStatus@CHuePlane@@@NCoreLibrary@@QEAAPEAW4ECacheStatus@CHuePlane@@PEAW423@@Z; NCoreLibrary::TAutoPtrArray<CHuePlane::ECacheStatus>::operator=(CHuePlane::ECacheStatus *)
0x180051d94  cmp     [rbp+3Fh+var_A8], r15
0x180051d98  jnz     short loc_180051DA4
0x180051d9a  mov     ebx, 8007000Eh
0x180051d9f  jmp     loc_180051E84
0x180051da4  call    cs:__imp_GetTickCount
0x180051daa  mov     r12d, eax
0x180051dad  cmp     r15d, [rbp+3Fh+arg_20]
0x180051db1  jnb     loc_180051E84
0x180051db7  mov     rax, [r14]
0x180051dba  mov     rdx, r13
0x180051dbd  mov     r9, [rbp+3Fh+var_A8]
0x180051dc1  mov     rcx, r14
0x180051dc4  mov     r8, [rbp+3Fh+var_78]
0x180051dc8  mov     rax, [rax+30h]
0x180051dcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051dd1  mov     ebx, eax
0x180051dd3  test    eax, eax
0x180051dd5  js      loc_180051E84
0x180051ddb  mov     r10, [rbp+3Fh+var_60]
0x180051ddf  mov     edx, edi
0x180051de1  mov     rcx, [rbp+3Fh+var_70]
0x180051de5  mov     r9d, [rbp+3Fh+var_88]
0x180051de9  mov     r8d, [rbp+3Fh+var_90]
0x180051ded  mov     rax, [r10]
0x180051df0  mov     [rsp+110h+var_E8], rcx
0x180051df5  mov     rcx, [rbp+3Fh+var_78]
0x180051df9  mov     [rsp+110h+var_F0], rcx
0x180051dfe  mov     rcx, r10
0x180051e01  mov     rax, [rax+20h]
0x180051e05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051e0a  mov     ebx, eax
0x180051e0c  test    eax, eax
0x180051e0e  js      short loc_180051E84
0x180051e10  mov     rax, [rsi]
0x180051e13  mov     rcx, rsi
0x180051e16  mov     r9, [rbp+3Fh+var_80]
0x180051e1a  mov     r8, [rbp+3Fh+var_A8]
0x180051e1e  mov     rdx, [rbp+3Fh+var_70]
0x180051e22  mov     rax, [rax+28h]
0x180051e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051e2b  mov     ebx, eax
0x180051e2d  test    eax, eax
0x180051e2f  js      short loc_180051E84
0x180051e31  cmp     [rbp+3Fh+var_68], 0
0x180051e36  jz      short loc_180051E6A
0x180051e38  call    cs:__imp_GetTickCount
0x180051e3e  sub     eax, r12d
0x180051e41  cmp     eax, 64h ; 'd'
0x180051e44  jbe     short loc_180051E6A
0x180051e46  mov     r8, [rbp+3Fh+arg_50]
0x180051e4d  lea     edx, [r15+1]
0x180051e51  mov     ecx, [rbp+3Fh+arg_20]
0x180051e54  mov     rax, [rbp+3Fh+var_68]
0x180051e58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051e5d  test    eax, eax
0x180051e5f  jz      short loc_180051E7F
0x180051e61  call    cs:__imp_GetTickCount
0x180051e67  mov     r12d, eax
0x180051e6a  mov     eax, [rbp+3Fh+var_B0]
0x180051e6d  add     r13, rax
0x180051e70  mov     eax, [rbp+3Fh+var_AC]
0x180051e73  add     [rbp+3Fh+var_80], rax
0x180051e77  inc     r15d
0x180051e7a  jmp     loc_180051DAD
0x180051e7f  mov     ebx, 800704C7h
0x180051e84  lea     rcx, [rbp+3Fh+var_A8]
0x180051e88  call    ?Reset@?$TGenericSP@ULuvColorF@@V?$TAutoPtrArray@ULuvColorF@@@NCoreLibrary@@PEAU1@$0A@PEBU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<LuvColorF,NCoreLibrary::TAutoPtrArray<LuvColorF>,LuvColorF *,0,LuvColorF const *>::Reset(void)
0x180051e8d  lea     rcx, [rbp+3Fh+var_98]
0x180051e91  call    ?Reset@?$TGenericSP@ULuvColorF@@V?$TAutoPtrArray@ULuvColorF@@@NCoreLibrary@@PEAU1@$0A@PEBU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<LuvColorF,NCoreLibrary::TAutoPtrArray<LuvColorF>,LuvColorF *,0,LuvColorF const *>::Reset(void)
0x180051e96  lea     rcx, [rbp+3Fh+var_A0]
0x180051e9a  call    ?Reset@?$TGenericSP@ULuvColorF@@V?$TAutoPtrArray@ULuvColorF@@@NCoreLibrary@@PEAU1@$0A@PEBU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<LuvColorF,NCoreLibrary::TAutoPtrArray<LuvColorF>,LuvColorF *,0,LuvColorF const *>::Reset(void)
0x180051e9f  jmp     short loc_180051EAC
0x180051ea1  mov     ebx, 80070057h
0x180051ea6  jmp     short loc_180051EAC
0x180051ea8  mov     rsi, [rbp+3Fh+var_A0]
0x180051eac  test    r14, r14
0x180051eaf  jz      short loc_180051EC4
0x180051eb1  mov     rax, [r14]
0x180051eb4  mov     edx, 1
0x180051eb9  mov     rcx, r14
0x180051ebc  mov     rax, [rax]
0x180051ebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051ec4  test    rsi, rsi
0x180051ec7  jz      short loc_180051EDC
0x180051ec9  mov     rax, [rsi]
0x180051ecc  mov     edx, 1
0x180051ed1  mov     rcx, rsi
0x180051ed4  mov     rax, [rax]
0x180051ed7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051edc  test    ebx, ebx
0x180051ede  js      short loc_180051F1A
0x180051ee0  lea     rcx, [rbp+3Fh+var_8C]
0x180051ee4  mov     [rbp+3Fh+var_58], 4
0x180051eec  mov     [rbp+3Fh+var_60], rcx
0x180051ef0  lea     r9, [rbp+3Fh+var_60]
0x180051ef4  mov     rcx, cs:g_etwHandle
0x180051efb  lea     rdx, FLOATING_POINT_OR_INTEGER_LUT
0x180051f02  mov     r8d, 1
0x180051f08  call    cs:__imp_EtwEventWrite
0x180051f0e  mov     eax, 1
0x180051f13  jmp     short loc_180051F28
0x180051f15  mov     ebx, 80070057h
0x180051f1a  mov     edx, 7E4h
0x180051f1f  mov     ecx, ebx
0x180051f21  call    SetLastErrorFromHRESULT
  ... truncated ...
```
