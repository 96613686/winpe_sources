# CITETranslateColors

- ea: `0x180051f50`
- end: `0x18005221a`
- name: `CITETranslateColors`
- size: `714`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18000e850`

## callees

- `0x180018eb0`
- `0x18001b074`
- `0x1800286cc`
- `0x18002e5f0`
- `0x18002e670`
- `0x180051f50`
- `0x180054e68`
- `0x180084010`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800521da`
- `ntdll!EtwEventWrite` at `0x1800521da`

## pseudocode

```c
__int64 __fastcall CITETranslateColors(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5,
        enum COLORTYPE a6)
{
  __int64 *v9; // r15
  __int64 v10; // rcx
  int v11; // ebx
  unsigned int v12; // ecx
  struct ICITEPixelConverter *v13; // rdi
  int v14; // eax
  struct ICITEPixelConverter *v15; // r14
  unsigned int v16; // eax
  unsigned int v17; // ecx
  int v18; // eax
  unsigned int v19; // ebx
  void *v20; // rax
  void *v21; // rax
  struct ICITEPixelConverter *v22; // r15
  struct ICITEPixelConverter *v24; // [rsp+40h] [rbp-39h] BYREF
  struct ICITEPixelConverter *v25; // [rsp+48h] [rbp-31h] BYREF
  unsigned int v26; // [rsp+50h] [rbp-29h]
  int v27; // [rsp+54h] [rbp-25h] BYREF
  unsigned int v28; // [rsp+58h] [rbp-21h]
  _QWORD v29[2]; // [rsp+60h] [rbp-19h] BYREF

  if ( a2 && a5 && a3 )
  {
    v9 = *(__int64 **)((a1 ^ 0x49434D20) + 0x18);
    v10 = *v9;
    v27 = 1;
    v29[0] = v10;
    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, __int64, __int64))(*(_QWORD *)v10 + 24LL))(
            v10,
            a3,
            a4,
            (unsigned int)a6,
            a2,
            a5);
    if ( v11 == -2147467263 )
    {
      v27 = 0;
      v12 = *((_DWORD *)v9 + 5);
      v13 = 0;
      v25 = 0;
      v24 = 0;
      v14 = CreateCITEPixelConverter(v12, a4, a3, &v24);
      v15 = v24;
      v11 = v14;
      if ( v14 >= 0 )
      {
        v16 = (*(__int64 (__fastcall **)(struct ICITEPixelConverter *))(*(_QWORD *)v24 + 16LL))(v24);
        v17 = *((_DWORD *)v9 + 6);
        v26 = v16;
        v18 = CreateCITEPixelConverter(v17, a6, a3, &v25);
        v13 = v25;
        v11 = v18;
        if ( v18 >= 0 )
        {
          v19 = (*(__int64 (__fastcall **)(struct ICITEPixelConverter *))(*(_QWORD *)v25 + 16LL))(v25);
          v28 = v19;
          v24 = 0;
          v25 = 0;
          if ( a3 > 0x3FFFFFFF / v26 || a3 > 0x3FFFFFFF / v19 )
          {
            v11 = -2147024809;
          }
          else
          {
            v20 = operator new(saturated_mul(a3 * v26, 4u));
            NCoreLibrary::TAutoPtrArray<enum CHuePlane::ECacheStatus>::operator=(&v24, (__int64)v20);
            v21 = operator new(saturated_mul(v19 * a3, 4u));
            NCoreLibrary::TAutoPtrArray<enum CHuePlane::ECacheStatus>::operator=(&v25, (__int64)v21);
            if ( v24 && (v22 = v25) != 0 )
            {
              v11 = (*(__int64 (__fastcall **)(struct ICITEPixelConverter *, __int64, struct ICITEPixelConverter *, _QWORD))(*(_QWORD *)v15 + 48LL))(
                      v15,
                      a2,
                      v24,
                      0);
              if ( v11 >= 0 )
              {
                v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, struct ICITEPixelConverter *, struct ICITEPixelConverter *))(*(_QWORD *)v29[0] + 32LL))(
                        v29[0],
                        a3,
                        v26,
                        v28,
                        v24,
                        v22);
                if ( v11 >= 0 )
                  v11 = (*(__int64 (__fastcall **)(struct ICITEPixelConverter *, struct ICITEPixelConverter *, _QWORD, __int64))(*(_QWORD *)v13 + 40LL))(
                          v13,
                          v22,
                          0,
                          a5);
              }
            }
            else
            {
              v11 = -2147024882;
            }
          }
          NCoreLibrary::TGenericSP<LuvColorF,NCoreLibrary::TAutoPtrArray<LuvColorF>,LuvColorF *,0,LuvColorF const *>::Reset(&v25);
          NCoreLibrary::TGenericSP<LuvColorF,NCoreLibrary::TAutoPtrArray<LuvColorF>,LuvColorF *,0,LuvColorF const *>::Reset(&v24);
        }
      }
      if ( v15 )
        (**(void (__fastcall ***)(struct ICITEPixelConverter *, __int64))v15)(v15, 1);
      if ( v13 )
        (**(void (__fastcall ***)(struct ICITEPixelConverter *, __int64))v13)(v13, 1);
    }
    if ( v11 >= 0 )
    {
      v29[1] = 4;
      v29[0] = &v27;
      EtwEventWrite(g_etwHandle, FLOATING_POINT_OR_INTEGER_LUT, 1, v29);
      return 1;
    }
  }
  else
  {
    v11 = -2147024809;
  }
  SetLastErrorFromHRESULT((unsigned int)v11, 2020);
  return 0;
}

```

## disassembly

```asm
0x180051f50  push    rbp
0x180051f52  push    rbx
0x180051f53  push    rsi
0x180051f54  push    rdi
0x180051f55  push    r12
0x180051f57  push    r13
0x180051f59  push    r14
0x180051f5b  push    r15
0x180051f5d  lea     rbp, [rsp-0Fh]
0x180051f62  sub     rsp, 88h
0x180051f69  mov     rax, cs:__security_cookie
0x180051f70  xor     rax, rsp
0x180051f73  mov     [rbp+47h+var_50], rax
0x180051f77  mov     r12, [rbp+47h+arg_20]
0x180051f7b  mov     r14d, r9d
0x180051f7e  mov     esi, r8d
0x180051f81  mov     r13, rdx
0x180051f84  test    rdx, rdx
0x180051f87  jz      loc_1800521E7
0x180051f8d  test    r12, r12
0x180051f90  jz      loc_1800521E7
0x180051f96  test    r8d, r8d
0x180051f99  jz      loc_1800521E7
0x180051f9f  mov     r9d, [rbp+47h+arg_28]
0x180051fa3  xor     rcx, 49434D20h
0x180051faa  mov     [rsp+0C0h+var_98], r12
0x180051faf  mov     r8d, r14d
0x180051fb2  mov     [rsp+0C0h+var_A0], rdx
0x180051fb7  mov     edx, esi
0x180051fb9  mov     r15, [rcx+18h]
0x180051fbd  mov     rcx, [r15]
0x180051fc0  mov     [rbp+47h+var_6C], 1
0x180051fc7  mov     [rbp+47h+var_60], rcx
0x180051fcb  mov     rax, [rcx]
0x180051fce  mov     rax, [rax+18h]
0x180051fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051fd7  mov     ebx, eax
0x180051fd9  cmp     eax, 80004001h
0x180051fde  jnz     loc_1800521AE
0x180051fe4  mov     [rbp+47h+var_6C], 0
0x180051feb  lea     r9, [rbp+47h+var_80]; struct ICITEPixelConverter **
0x180051fef  mov     ecx, [r15+14h]; int
0x180051ff3  xor     edi, edi
0x180051ff5  mov     r8d, esi; unsigned int
0x180051ff8  mov     [rbp+47h+var_78], rdi
0x180051ffc  mov     edx, r14d; enum COLORTYPE
0x180051fff  mov     [rbp+47h+var_80], 0
0x180052007  call    ?CreateCITEPixelConverter@@YAJHW4COLORTYPE@@IPEAPEAVICITEPixelConverter@@@Z; CreateCITEPixelConverter(int,COLORTYPE,uint,ICITEPixelConverter * *)
0x18005200c  mov     r14, [rbp+47h+var_80]
0x180052010  mov     ebx, eax
0x180052012  test    eax, eax
0x180052014  js      loc_18005217E
0x18005201a  mov     rax, [r14]
0x18005201d  mov     rcx, r14
0x180052020  mov     rax, [rax+10h]
0x180052024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052029  mov     edx, [rbp+47h+arg_28]; enum COLORTYPE
0x18005202c  lea     r9, [rbp+47h+var_78]; struct ICITEPixelConverter **
0x180052030  mov     ecx, [r15+18h]; int
0x180052034  mov     r8d, esi; unsigned int
0x180052037  mov     [rbp+47h+var_70], eax
0x18005203a  call    ?CreateCITEPixelConverter@@YAJHW4COLORTYPE@@IPEAPEAVICITEPixelConverter@@@Z; CreateCITEPixelConverter(int,COLORTYPE,uint,ICITEPixelConverter * *)
0x18005203f  mov     rdi, [rbp+47h+var_78]
0x180052043  mov     ebx, eax
0x180052045  test    eax, eax
0x180052047  js      loc_18005217E
0x18005204d  mov     rax, [rdi]
0x180052050  mov     rcx, rdi
0x180052053  mov     rax, [rax+10h]
0x180052057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005205c  mov     ecx, [rbp+47h+var_70]
0x18005205f  mov     ebx, eax
0x180052061  mov     [rbp+47h+var_68], eax
0x180052064  xor     edx, edx
0x180052066  mov     r8d, 3FFFFFFFh
0x18005206c  mov     [rbp+47h+var_80], 0
0x180052074  mov     eax, r8d
0x180052077  mov     [rbp+47h+var_78], 0
0x18005207f  div     ecx
0x180052081  cmp     esi, eax
0x180052083  ja      loc_180052167
0x180052089  xor     edx, edx
0x18005208b  mov     eax, r8d
0x18005208e  div     ebx
0x180052090  cmp     esi, eax
0x180052092  ja      loc_180052167
0x180052098  imul    ecx, esi
0x18005209b  mov     eax, 4
0x1800520a0  mov     r15, 0FFFFFFFFFFFFFFFFh
0x1800520a7  mul     rcx
0x1800520aa  cmovb   rax, r15
0x1800520ae  mov     rcx, rax; Size
0x1800520b1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800520b6  mov     rdx, rax
0x1800520b9  lea     rcx, [rbp+47h+var_80]
0x1800520bd  call    ??4?$TAutoPtrArray@W4ECacheStatus@CHuePlane@@@NCoreLibrary@@QEAAPEAW4ECacheStatus@CHuePlane@@PEAW423@@Z; NCoreLibrary::TAutoPtrArray<CHuePlane::ECacheStatus>::operator=(CHuePlane::ECacheStatus *)
0x1800520c2  mov     ecx, esi
0x1800520c4  lea     eax, [r15+5]
0x1800520c8  imul    ecx, ebx
0x1800520cb  mul     rcx
0x1800520ce  cmovb   rax, r15
0x1800520d2  mov     rcx, rax; Size
0x1800520d5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800520da  mov     rdx, rax
0x1800520dd  lea     rcx, [rbp+47h+var_78]
0x1800520e1  call    ??4?$TAutoPtrArray@W4ECacheStatus@CHuePlane@@@NCoreLibrary@@QEAAPEAW4ECacheStatus@CHuePlane@@PEAW423@@Z; NCoreLibrary::TAutoPtrArray<CHuePlane::ECacheStatus>::operator=(CHuePlane::ECacheStatus *)
0x1800520e6  mov     rcx, [rbp+47h+var_80]
0x1800520ea  test    rcx, rcx
0x1800520ed  jz      short loc_180052160
0x1800520ef  mov     r15, [rbp+47h+var_78]
0x1800520f3  test    r15, r15
0x1800520f6  jz      short loc_180052160
0x1800520f8  mov     rax, [r14]
0x1800520fb  mov     r8, rcx
0x1800520fe  xor     r9d, r9d
0x180052101  mov     rdx, r13
0x180052104  mov     rcx, r14
0x180052107  mov     rax, [rax+30h]
0x18005210b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052110  mov     ebx, eax
0x180052112  test    eax, eax
0x180052114  js      short loc_18005216C
0x180052116  mov     rdx, [rbp+47h+var_80]
0x18005211a  mov     rcx, [rbp+47h+var_60]
0x18005211e  mov     r9d, [rbp+47h+var_68]
0x180052122  mov     r8d, [rbp+47h+var_70]
0x180052126  mov     [rsp+0C0h+var_98], r15
0x18005212b  mov     rax, [rcx]
0x18005212e  mov     [rsp+0C0h+var_A0], rdx
0x180052133  mov     edx, esi
0x180052135  mov     rax, [rax+20h]
0x180052139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005213e  mov     ebx, eax
0x180052140  test    eax, eax
0x180052142  js      short loc_18005216C
0x180052144  mov     rax, [rdi]
0x180052147  mov     r9, r12
0x18005214a  xor     r8d, r8d
0x18005214d  mov     rdx, r15
0x180052150  mov     rcx, rdi
0x180052153  mov     rax, [rax+28h]
0x180052157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005215c  mov     ebx, eax
0x18005215e  jmp     short loc_18005216C
0x180052160  mov     ebx, 8007000Eh
0x180052165  jmp     short loc_18005216C
0x180052167  mov     ebx, 80070057h
0x18005216c  lea     rcx, [rbp+47h+var_78]
0x180052170  call    ?Reset@?$TGenericSP@ULuvColorF@@V?$TAutoPtrArray@ULuvColorF@@@NCoreLibrary@@PEAU1@$0A@PEBU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<LuvColorF,NCoreLibrary::TAutoPtrArray<LuvColorF>,LuvColorF *,0,LuvColorF const *>::Reset(void)
0x180052175  lea     rcx, [rbp+47h+var_80]
0x180052179  call    ?Reset@?$TGenericSP@ULuvColorF@@V?$TAutoPtrArray@ULuvColorF@@@NCoreLibrary@@PEAU1@$0A@PEBU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<LuvColorF,NCoreLibrary::TAutoPtrArray<LuvColorF>,LuvColorF *,0,LuvColorF const *>::Reset(void)
0x18005217e  test    r14, r14
0x180052181  jz      short loc_180052196
0x180052183  mov     rax, [r14]
0x180052186  mov     edx, 1
0x18005218b  mov     rcx, r14
0x18005218e  mov     rax, [rax]
0x180052191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052196  test    rdi, rdi
0x180052199  jz      short loc_1800521AE
0x18005219b  mov     rax, [rdi]
0x18005219e  mov     edx, 1
0x1800521a3  mov     rcx, rdi
0x1800521a6  mov     rax, [rax]
0x1800521a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800521ae  test    ebx, ebx
0x1800521b0  js      short loc_1800521EC
0x1800521b2  lea     rcx, [rbp+47h+var_6C]
0x1800521b6  mov     [rbp+47h+var_58], 4
0x1800521be  mov     [rbp+47h+var_60], rcx
0x1800521c2  lea     r9, [rbp+47h+var_60]
0x1800521c6  mov     rcx, cs:g_etwHandle
0x1800521cd  lea     rdx, FLOATING_POINT_OR_INTEGER_LUT
0x1800521d4  mov     r8d, 1
0x1800521da  call    cs:__imp_EtwEventWrite
0x1800521e0  mov     eax, 1
0x1800521e5  jmp     short loc_1800521FA
0x1800521e7  mov     ebx, 80070057h
0x1800521ec  mov     edx, 7E4h
0x1800521f1  mov     ecx, ebx
0x1800521f3  call    SetLastErrorFromHRESULT
0x1800521f8  xor     eax, eax
0x1800521fa  mov     rcx, [rbp+47h+var_50]
0x1800521fe  xor     rcx, rsp; StackCookie
0x180052201  call    __security_check_cookie
0x180052206  add     rsp, 88h
0x18005220d  pop     r15
0x18005220f  pop     r14
0x180052211  pop     r13
0x180052213  pop     r12
0x180052215  pop     rdi
0x180052216  pop     rsi
0x180052217  pop     rbx
0x180052218  pop     rbp
0x180052219  retn
```
