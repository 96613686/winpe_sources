# CUIElementSink::UpdateCandidateListUIElement(IMCLock &,ITfCandidateListUIElement *)

- ea: `0x18001ff6c`
- end: `0x180020533`
- name: `?UpdateCandidateListUIElement@CUIElementSink@@AEAAJAEAVIMCLock@@PEAUITfCandidateListUIElement@@@Z`
- size: `1479`
- prototype: `int(CUIElementSink *__hidden this, struct IMCLock *, struct ITfCandidateListUIElement *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18001fcf0`

## callees

- `0x1800185f0`
- `0x18001cc80`
- `0x18001ff6c`
- `0x180065660`
- `0x18009eaea`
- `0x18010a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002032f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020451`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002047a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002032f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020451`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002047a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002005b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800200b2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002005b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800200b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002011b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020124`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002011b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020124`
- `OLEAUT32!__imp_SysFreeString` at `0x18002010b`
- `OLEAUT32!__imp_SysFreeString` at `0x18002010b`
- `OLEAUT32!__imp_SysStringLen` at `0x180020174`
- `OLEAUT32!__imp_SysStringLen` at `0x1800203c4`
- `OLEAUT32!__imp_SysStringLen` at `0x180020174`
- `OLEAUT32!__imp_SysStringLen` at `0x1800203c4`
- `IMM32!ImmGetIMCCSize` at `0x1800203da`
- `IMM32!ImmGetIMCCSize` at `0x1800203da`
- `IMM32!ImmLockIMCC` at `0x1800201f4`
- `IMM32!ImmLockIMCC` at `0x18002028f`
- `IMM32!ImmLockIMCC` at `0x1800201f4`
- `IMM32!ImmLockIMCC` at `0x18002028f`
- `IMM32!ImmUnlockIMCC` at `0x180020322`
- `IMM32!ImmUnlockIMCC` at `0x180020444`
- `IMM32!ImmUnlockIMCC` at `0x18002046d`
- `IMM32!ImmUnlockIMCC` at `0x180020322`
- `IMM32!ImmUnlockIMCC` at `0x180020444`
- `IMM32!ImmUnlockIMCC` at `0x18002046d`
- `IMM32!ImmCreateIMCC` at `0x1800201a7`
- `IMM32!ImmCreateIMCC` at `0x1800201a7`
- `IMM32!ImmReSizeIMCC` at `0x1800203f7`
- `IMM32!ImmReSizeIMCC` at `0x1800203f7`
- `IMM32!ImmDestroyIMCC` at `0x1800204ae`
- `IMM32!ImmDestroyIMCC` at `0x1800204ae`

## string_xrefs

- `0x1800204b9`: `CUIElementSink::UpdateCandidateList. no candidate list in imc.`

## pseudocode

```c
__int64 __fastcall CUIElementSink::UpdateCandidateListUIElement(
        CUIElementSink *this,
        struct IMCLock *a2,
        struct ITfCandidateListUIElement *a3)
{
  struct ITfCandidateListUIElementVtbl *lpVtbl; // rax
  __int64 result; // rax
  struct ITfCandidateListUIElementVtbl *v7; // rax
  struct ITfCandidateListUIElementVtbl *v8; // rax
  struct ITfCandidateListUIElementVtbl *v9; // rax
  struct ITfCandidateListUIElementVtbl *v10; // rax
  unsigned int v11; // eax
  unsigned int *v12; // rax
  unsigned int *v13; // r15
  CUIElementSink *v14; // rcx
  int updated; // ebx
  unsigned int v16; // eax
  _QWORD *v17; // r12
  unsigned int i; // r14d
  unsigned int j; // edi
  unsigned int v20; // edi
  int v21; // r14d
  unsigned int v22; // ebx
  UINT v23; // eax
  DWORD v24; // r14d
  HIMCC v25; // rcx
  __int64 v26; // rax
  _DWORD *v27; // r12
  DWORD *v28; // r15
  HIMCC v29; // r13
  signed int v30; // eax
  LPVOID v31; // r9
  _DWORD *v32; // r15
  _DWORD *v33; // rdx
  HIMCC v34; // rsi
  signed int v35; // eax
  __int64 v36; // r8
  unsigned int v37; // ecx
  unsigned int *v38; // r11
  unsigned int v39; // eax
  __int64 v40; // rcx
  unsigned int v41; // r10d
  unsigned int v42; // eax
  unsigned int v43; // esi
  _WORD *v44; // rbx
  _QWORD *v45; // r15
  DWORD v46; // ecx
  bool v47; // zf
  unsigned __int64 v48; // rcx
  _WORD *v49; // r8
  __int64 v50; // rdx
  _WORD *v51; // rax
  _WORD *v52; // rdx
  UINT v53; // eax
  HIMCC v54; // rax
  __int64 v55; // rcx
  unsigned int v56; // [rsp+40h] [rbp-49h] BYREF
  unsigned int v57; // [rsp+44h] [rbp-45h] BYREF
  _QWORD *v58; // [rsp+48h] [rbp-41h]
  unsigned int *v59; // [rsp+50h] [rbp-39h]
  unsigned int v60; // [rsp+58h] [rbp-31h]
  unsigned int v61; // [rsp+5Ch] [rbp-2Dh]
  unsigned int v62; // [rsp+60h] [rbp-29h]
  _DWORD *v63; // [rsp+68h] [rbp-21h]
  void **v64; // [rsp+70h] [rbp-19h] BYREF
  LPVOID v65; // [rsp+78h] [rbp-11h]
  HIMCC v66; // [rsp+80h] [rbp-9h]
  signed int v67; // [rsp+88h] [rbp-1h]
  void **v68; // [rsp+90h] [rbp+7h] BYREF
  _DWORD *v69; // [rsp+98h] [rbp+Fh]
  HIMCC v70; // [rsp+A0h] [rbp+17h]
  signed int v71; // [rsp+A8h] [rbp+1Fh]
  CUIElementSink *v72; // [rsp+F0h] [rbp+67h] BYREF
  unsigned int v73; // [rsp+100h] [rbp+77h] BYREF
  int v74; // [rsp+108h] [rbp+7Fh] BYREF

  v72 = this;
  lpVtbl = a3->lpVtbl;
  v74 = 0;
  result = ((__int64 (__fastcall *)(struct ITfCandidateListUIElement *, int *))lpVtbl->GetUpdatedFlags)(a3, &v74);
  if ( (int)result >= 0 )
  {
    v7 = a3->lpVtbl;
    LODWORD(v72) = 0;
    result = ((__int64 (__fastcall *)(struct ITfCandidateListUIElement *, CUIElementSink **))v7->GetCount)(a3, &v72);
    if ( (int)result >= 0 )
    {
      if ( (_DWORD)v72 )
      {
        v8 = a3->lpVtbl;
        v73 = 0;
        result = ((__int64 (__fastcall *)(struct ITfCandidateListUIElement *, _QWORD, _QWORD, unsigned int *))v8->GetPageIndex)(
                   a3,
                   0,
                   0,
                   &v73);
        if ( (int)result >= 0 )
        {
          v9 = a3->lpVtbl;
          v57 = 0;
          result = ((__int64 (__fastcall *)(struct ITfCandidateListUIElement *, unsigned int *))v9->GetSelection)(
                     a3,
                     &v57);
          if ( (int)result >= 0 )
          {
            v10 = a3->lpVtbl;
            v56 = 0;
            result = ((__int64 (__fastcall *)(struct ITfCandidateListUIElement *, unsigned int *))v10->GetCurrentPage)(
                       a3,
                       &v56);
            if ( (int)result >= 0 )
            {
              v11 = 4 * v73;
              if ( !is_mul_ok(v73, 4u) )
                v11 = -1;
              v12 = (unsigned int *)LocalAlloc(0x40u, v11);
              v59 = v12;
              v13 = v12;
              if ( !v12 )
                return 2147942414LL;
              updated = ((__int64 (__fastcall *)(struct ITfCandidateListUIElement *, unsigned int *, _QWORD, unsigned int *))a3->lpVtbl->GetPageIndex)(
                          a3,
                          v12,
                          v73,
                          &v73);
              if ( updated < 0 )
                goto LABEL_23;
              if ( (v74 & 0xA) == 0 )
              {
                if ( (v74 & 0x34) != 0 )
                  updated = CUIElementSink::UpdateCandidateList(v14, a2, (unsigned int)v72, v57, v56, v73, v13);
                goto LABEL_23;
              }
              v16 = 8 * (_DWORD)v72;
              if ( !is_mul_ok((unsigned int)v72, 8u) )
                v16 = -1;
              v58 = LocalAlloc(0x40u, v16);
              v17 = v58;
              if ( !v58 )
              {
                updated = -2147024882;
LABEL_23:
                LocalFree(v13);
                return (unsigned int)updated;
              }
              for ( i = 0; i < (unsigned int)v72; ++i )
              {
                ((void (__fastcall *)(struct ITfCandidateListUIElement *, _QWORD, _QWORD *))a3->lpVtbl->GetString)(
                  a3,
                  i,
                  &v17[i]);
                if ( !v17[i] )
                  goto LABEL_19;
              }
              v20 = (unsigned int)v72;
              if ( !(_DWORD)v72 )
              {
                updated = -2147467259;
                goto LABEL_20;
              }
              v21 = 0;
              v62 = v73;
              v22 = 0;
              v61 = v56;
              v60 = v57;
              do
              {
                v23 = SysStringLen((BSTR)v17[v22++]);
                v21 += v23 + 1;
              }
              while ( v22 < v20 );
              v24 = 2 * (v21 + 2 * v20 + 84);
              v25 = *(HIMCC *)(*((_QWORD *)a2 + 1) + 296LL);
              if ( v25 )
              {
                if ( ImmGetIMCCSize(v25) == v24 )
                  goto LABEL_30;
                v54 = ImmReSizeIMCC(*(HIMCC *)(*((_QWORD *)a2 + 1) + 296LL), v24);
                v55 = *((_QWORD *)a2 + 1);
                if ( v54 )
                {
                  *(_QWORD *)(v55 + 296) = v54;
                  goto LABEL_30;
                }
                ImmDestroyIMCC(*(HIMCC *)(v55 + 296));
              }
              *(_QWORD *)(*((_QWORD *)a2 + 1) + 296LL) = ImmCreateIMCC(v24);
              if ( !*(_QWORD *)(*((_QWORD *)a2 + 1) + 296LL) )
              {
LABEL_19:
                updated = -2147024882;
                goto LABEL_20;
              }
LABEL_30:
              v26 = *((_QWORD *)a2 + 1);
              v27 = 0;
              v28 = 0;
              v69 = 0;
              updated = -2147467259;
              v29 = *(HIMCC *)(v26 + 296);
              v30 = 0;
              v70 = v29;
              v71 = 0;
              if ( v29 )
              {
                v69 = ImmLockIMCC(v29);
                v27 = v69;
                v28 = v69;
                v30 = v69 == 0 ? 0x80004005 : 0;
                v71 = v30;
              }
              v68 = &IMCCLock<tagCANDIDATEINFO>::`vftable';
              if ( v28 )
              {
                if ( v30 < 0 )
                {
                  updated = v30;
                }
                else
                {
                  memset_0(v28, 0, v24);
                  *v28 = v24;
                  v28[1] = 1;
                  v28[2] = 144;
                  v31 = 0;
                  v32 = v28 + 36;
                  v65 = 0;
                  v63 = v32;
                  v33 = 0;
                  v67 = 0;
                  *v32 = v24 - 144;
                  v32[1] = 0;
                  v34 = *(HIMCC *)(*((_QWORD *)a2 + 1) + 296LL);
                  v35 = 0;
                  v66 = v34;
                  if ( v34 )
                  {
                    v65 = ImmLockIMCC(v34);
                    v31 = v65;
                    v33 = v65;
                    v35 = v65 == 0 ? 0x80004005 : 0;
                    v67 = v35;
                  }
                  v64 = &IMCCLock<tagCANDIDATEINFO>::`vftable';
                  if ( v33 )
                  {
                    updated = v35;
                    if ( v35 >= 0 )
                    {
                      if ( v33[1] )
                      {
                        v36 = (unsigned int)v33[2];
                        v37 = v60;
                        v38 = v59;
                        if ( v60 == -1 )
                          v37 = 0;
                        v39 = v62;
                        *(_DWORD *)((char *)v33 + v36 + 12) = v37;
                        v40 = v61;
                        *(_DWORD *)((char *)v33 + v36 + 8) = v20;
                        v41 = v38[v40];
                        if ( (unsigned int)v40 < v39 - 1 )
                        {
                          v42 = v38[(unsigned int)(v40 + 1)];
                          if ( v42 > v20 )
                            v42 = v20;
                        }
                        else
                        {
                          v42 = v20;
                        }
                        *(_DWORD *)((char *)v33 + v36 + 16) = v41;
                        *(_DWORD *)((char *)v33 + v36 + 20) = v42 - v41;
                        if ( v31 && !ImmUnlockIMCC(v34) )
                          GetLastError();
                      }
                      else
                      {
                        CicTrace(
                          2u,
                          "CUIElementSink::UpdateCandidateList. no candidate list in imc.",
                          &IMCCLock<tagCANDIDATEINFO>::`vftable',
                          v31);
                        InternalIMCCLock::~InternalIMCCLock((InternalIMCCLock *)&v64);
                      }
                      v43 = 0;
                      v44 = &v32[v20 + 6];
                      v45 = v58;
                      while ( v43 < v20 )
                      {
                        v46 = (_DWORD)v44 - (_DWORD)v63;
                        v63[v43 + 6] = (_DWORD)v44 - (_DWORD)v63;
                        if ( v46 > v24 )
                        {
                          if ( v27 && !ImmUnlockIMCC(v29) )
                            GetLastError();
                          updated = -2147024882;
                          goto LABEL_69;
                        }
                        v47 = v24 == v46;
                        v48 = v24 - v46;
                        if ( !v47 )
                        {
                          if ( v48 > 0x7FFFFFFF )
                          {
                            *v44 = 0;
                          }
                          else
                          {
                            v49 = (_WORD *)v45[v43];
                            v50 = 2147483646;
                            v51 = v44;
                            do
                            {
                              if ( !v50 )
                                break;
                              if ( !*v49 )
                                break;
                              *v51++ = *v49++;
                              --v50;
                              --v48;
                            }
                            while ( v48 );
                            v52 = v51 - 1;
                            if ( v48 )
                              v52 = v51;
                            *v52 = 0;
                          }
                        }
                        v53 = SysStringLen((BSTR)v45[v43++]);
                        v44 += v53 + 1;
                      }
                      if ( v27 && !ImmUnlockIMCC(v29) )
                        GetLastError();
                      updated = 0;
LABEL_69:
                      v17 = v45;
                      goto LABEL_64;
                    }
                  }
                  InternalIMCCLock::~InternalIMCCLock((InternalIMCCLock *)&v64);
                }
              }
              InternalIMCCLock::~InternalIMCCLock((InternalIMCCLock *)&v68);
              v17 = v58;
LABEL_64:
              v13 = v59;
LABEL_20:
              for ( j = 0; j < (unsigned int)v72; ++j )
                SysFreeString((BSTR)v17[j]);
              LocalFree(v17);
              goto LABEL_23;
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001ff6c  mov     [rsp-8+arg_8], rbx
0x18001ff71  mov     [rsp-8+arg_0], rcx
0x18001ff76  push    rbp
0x18001ff77  push    rsi
0x18001ff78  push    rdi
0x18001ff79  push    r12
0x18001ff7b  push    r13
0x18001ff7d  push    r14
0x18001ff7f  push    r15
0x18001ff81  lea     rbp, [rsp-27h]
0x18001ff86  sub     rsp, 0B0h
0x18001ff8d  mov     rax, [r8]
0x18001ff90  mov     rsi, rdx
0x18001ff93  xor     r13d, r13d
0x18001ff96  lea     rdx, [rbp+57h+arg_18]
0x18001ff9a  mov     rcx, r8
0x18001ff9d  mov     [rbp+57h+arg_18], r13d
0x18001ffa1  mov     rdi, r8
0x18001ffa4  mov     rax, [rax+38h]
0x18001ffa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffad  test    eax, eax
0x18001ffaf  js      loc_18002012C
0x18001ffb5  mov     rax, [rdi]
0x18001ffb8  lea     rdx, [rbp+57h+arg_0]
0x18001ffbc  mov     rcx, rdi
0x18001ffbf  mov     dword ptr [rbp+57h+arg_0], r13d
0x18001ffc3  mov     rax, [rax+48h]
0x18001ffc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffcc  test    eax, eax
0x18001ffce  js      loc_18002012C
0x18001ffd4  cmp     dword ptr [rbp+57h+arg_0], r13d
0x18001ffd8  jz      loc_18002012C
0x18001ffde  mov     rax, [rdi]
0x18001ffe1  lea     r9, [rbp+57h+arg_10]
0x18001ffe5  xor     r8d, r8d
0x18001ffe8  mov     [rbp+57h+arg_10], r13d
0x18001ffec  xor     edx, edx
0x18001ffee  mov     rcx, rdi
0x18001fff1  mov     rax, [rax+60h]
0x18001fff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fffa  test    eax, eax
0x18001fffc  js      loc_18002012C
0x180020002  mov     rax, [rdi]
0x180020005  lea     rdx, [rbp+57h+var_9C]
0x180020009  mov     rcx, rdi
0x18002000c  mov     [rbp+57h+var_9C], r13d
0x180020010  mov     rax, [rax+50h]
0x180020014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020019  test    eax, eax
0x18002001b  js      loc_18002012C
0x180020021  mov     rax, [rdi]
0x180020024  lea     rdx, [rbp+57h+var_A0]
0x180020028  mov     rcx, rdi
0x18002002b  mov     [rbp+57h+var_A0], r13d
0x18002002f  mov     rax, [rax+70h]
0x180020033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020038  test    eax, eax
0x18002003a  js      loc_18002012C
0x180020040  mov     ecx, [rbp+57h+arg_10]
0x180020043  lea     eax, [r13+4]
0x180020047  mul     rcx
0x18002004a  lea     r12, [r13-1]
0x18002004e  lea     r14d, [r13+40h]
0x180020052  cmovb   rax, r12
0x180020056  mov     ecx, r14d; uFlags
0x180020059  mov     edx, eax; uBytes
0x18002005b  call    cs:__imp_LocalAlloc
0x180020061  mov     [rbp+57h+var_90], rax
0x180020065  mov     r15, rax
0x180020068  test    rax, rax
0x18002006b  jz      loc_180020493
0x180020071  mov     rax, [rdi]
0x180020074  lea     r9, [rbp+57h+arg_10]
0x180020078  mov     r8d, [rbp+57h+arg_10]
0x18002007c  mov     rdx, r15
0x18002007f  mov     rcx, rdi
0x180020082  mov     rax, [rax+60h]
0x180020086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002008b  mov     ebx, eax
0x18002008d  test    eax, eax
0x18002008f  js      loc_180020121
0x180020095  test    byte ptr [rbp+57h+arg_18], 0Ah
0x180020099  jz      loc_1800204FF
0x18002009f  mov     edx, dword ptr [rbp+57h+arg_0]
0x1800200a2  lea     eax, [r13+8]
0x1800200a6  mul     rdx
0x1800200a9  mov     ecx, r14d; uFlags
0x1800200ac  cmovb   rax, r12
0x1800200b0  mov     edx, eax; uBytes
0x1800200b2  call    cs:__imp_LocalAlloc
0x1800200b8  mov     [rbp+57h+var_98], rax
0x1800200bc  mov     r12, rax
0x1800200bf  test    rax, rax
0x1800200c2  jz      loc_180020489
0x1800200c8  mov     r14d, r13d
0x1800200cb  cmp     r14d, dword ptr [rbp+57h+arg_0]
0x1800200cf  jnb     short loc_180020147
0x1800200d1  mov     eax, r14d
0x1800200d4  mov     edx, r14d
0x1800200d7  mov     rcx, rdi
0x1800200da  lea     rbx, [r12+rax*8]
0x1800200de  mov     rax, [rdi]
0x1800200e1  mov     r8, rbx
0x1800200e4  mov     rax, [rax+58h]
0x1800200e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800200ed  cmp     [rbx], r13
0x1800200f0  jz      short loc_1800200F7
0x1800200f2  inc     r14d
0x1800200f5  jmp     short loc_1800200CB
0x1800200f7  mov     ebx, 8007000Eh
0x1800200fc  mov     edi, r13d
0x1800200ff  cmp     dword ptr [rbp+57h+arg_0], r13d
0x180020103  jbe     short loc_180020118
0x180020105  mov     ecx, edi
0x180020107  mov     rcx, [r12+rcx*8]; bstrString
0x18002010b  call    cs:__imp_SysFreeString
0x180020111  inc     edi
0x180020113  cmp     edi, dword ptr [rbp+57h+arg_0]
0x180020116  jb      short loc_180020105
0x180020118  mov     rcx, r12; hMem
0x18002011b  call    cs:__imp_LocalFree
0x180020121  mov     rcx, r15; hMem
0x180020124  call    cs:__imp_LocalFree
0x18002012a  mov     eax, ebx
0x18002012c  mov     rbx, [rsp+0E0h+arg_8]
0x180020134  add     rsp, 0B0h
0x18002013b  pop     r15
0x18002013d  pop     r14
0x18002013f  pop     r13
0x180020141  pop     r12
0x180020143  pop     rdi
0x180020144  pop     rsi
0x180020145  pop     rbp
0x180020146  retn
0x180020147  mov     edi, dword ptr [rbp+57h+arg_0]
0x18002014a  test    edi, edi
0x18002014c  jz      loc_18002049D
0x180020152  mov     eax, [rbp+57h+arg_10]
0x180020155  mov     r14d, r13d
0x180020158  mov     [rbp+57h+var_80], eax
0x18002015b  mov     ebx, r13d
0x18002015e  mov     eax, [rbp+57h+var_A0]
0x180020161  mov     [rbp+57h+var_84], eax
0x180020164  mov     eax, [rbp+57h+var_9C]
0x180020167  mov     [rbp+57h+var_88], eax
0x18002016a  test    edi, edi
0x18002016c  jz      short loc_180020185
0x18002016e  mov     ecx, ebx
0x180020170  mov     rcx, [r12+rcx*8]; pbstr
0x180020174  call    cs:__imp_SysStringLen
0x18002017a  inc     eax
0x18002017c  inc     ebx
0x18002017e  add     r14d, eax
0x180020181  cmp     ebx, edi
0x180020183  jb      short loc_18002016E
0x180020185  mov     rax, [rsi+8]
0x180020189  lea     r14d, [r14+rdi*2]
0x18002018d  add     r14d, 54h ; 'T'
0x180020191  add     r14d, r14d
0x180020194  mov     rcx, [rax+128h]; HIMCC
0x18002019b  test    rcx, rcx
0x18002019e  jnz     loc_1800203DA
0x1800201a4  mov     ecx, r14d; DWORD
0x1800201a7  call    cs:__imp_ImmCreateIMCC
0x1800201ad  mov     rcx, [rsi+8]
0x1800201b1  mov     [rcx+128h], rax
0x1800201b8  mov     rax, [rsi+8]
0x1800201bc  cmp     [rax+128h], r13
0x1800201c3  jz      loc_1800200F7
0x1800201c9  mov     rax, [rsi+8]
0x1800201cd  xor     r12d, r12d
0x1800201d0  xor     r15d, r15d
0x1800201d3  mov     [rbp+57h+var_48], r12
0x1800201d7  mov     ebx, 80004005h
0x1800201dc  mov     r13, [rax+128h]
0x1800201e3  xor     eax, eax
0x1800201e5  mov     [rbp+57h+var_40], r13
0x1800201e9  mov     [rbp+57h+var_38], eax
0x1800201ec  test    r13, r13
0x1800201ef  jz      short loc_180020213
0x1800201f1  mov     rcx, r13; HIMCC
0x1800201f4  call    cs:__imp_ImmLockIMCC
0x1800201fa  mov     rcx, rax
0x1800201fd  mov     [rbp+57h+var_48], rax
0x180020201  mov     r12, rax
0x180020204  mov     r15, rax
0x180020207  neg     rcx
0x18002020a  sbb     eax, eax
0x18002020c  not     eax
0x18002020e  and     eax, ebx
0x180020210  mov     [rbp+57h+var_38], eax
0x180020213  lea     rcx, ??_7?$IMCCLock@UtagCANDIDATEINFO@@@@6B@; const IMCCLock<tagCANDIDATEINFO>::`vftable'
0x18002021a  mov     [rbp+57h+var_50], rcx
0x18002021e  test    r15, r15
0x180020221  jz      loc_18002041F
0x180020227  test    eax, eax
0x180020229  js      loc_180020485
0x18002022f  mov     r8d, r14d; Size
0x180020232  xor     edx, edx; Val
0x180020234  mov     rcx, r15; void *
0x180020237  call    memset_0
0x18002023c  xor     ecx, ecx
0x18002023e  mov     [r15], r14d
0x180020241  mov     dword ptr [r15+4], 1
0x180020249  lea     eax, [r14-90h]
0x180020250  mov     dword ptr [r15+8], 90h
0x180020258  mov     r9d, ecx
0x18002025b  add     r15, 90h
0x180020262  mov     [rbp+57h+var_68], rcx
0x180020266  mov     [rbp+57h+var_78], r15
0x18002026a  mov     edx, ecx
0x18002026c  mov     [rbp+57h+var_58], ecx
0x18002026f  mov     [r15], eax
0x180020272  mov     [r15+4], ecx
0x180020276  mov     rax, [rsi+8]
0x18002027a  mov     rsi, [rax+128h]
0x180020281  mov     eax, ecx
0x180020283  mov     [rbp+57h+var_60], rsi
0x180020287  test    rsi, rsi
0x18002028a  jz      short loc_1800202B0
0x18002028c  mov     rcx, rsi; HIMCC
0x18002028f  call    cs:__imp_ImmLockIMCC
0x180020295  mov     rcx, rax
0x180020298  mov     [rbp+57h+var_68], rax
0x18002029c  mov     r9, rax
0x18002029f  mov     rdx, rax
0x1800202a2  neg     rcx
0x1800202a5  sbb     eax, eax
0x1800202a7  not     eax
0x1800202a9  and     eax, ebx
0x1800202ab  mov     [rbp+57h+var_58], eax
0x1800202ae  xor     ecx, ecx
0x1800202b0  lea     r8, ??_7?$IMCCLock@UtagCANDIDATEINFO@@@@6B@; const IMCCLock<tagCANDIDATEINFO>::`vftable'
0x1800202b7  mov     [rbp+57h+var_70], r8
0x1800202bb  test    rdx, rdx
0x1800202be  jz      loc_180020416
0x1800202c4  mov     ebx, eax
0x1800202c6  test    eax, eax
0x1800202c8  js      loc_180020416
0x1800202ce  cmp     [rdx+4], ecx
0x1800202d1  jz      loc_1800204B9
0x1800202d7  mov     r8d, [rdx+8]
0x1800202db  mov     eax, ecx
0x1800202dd  mov     ecx, [rbp+57h+var_88]
0x1800202e0  cmp     ecx, 0FFFFFFFFh
0x1800202e3  mov     r11, [rbp+57h+var_90]
0x1800202e7  cmovz   ecx, eax
0x1800202ea  mov     eax, [rbp+57h+var_80]
0x1800202ed  mov     [r8+rdx+0Ch], ecx
0x1800202f2  dec     eax
0x1800202f4  mov     ecx, [rbp+57h+var_84]
0x1800202f7  mov     [r8+rdx+8], edi
0x1800202fc  mov     r10d, [r11+rcx*4]
0x180020300  cmp     ecx, eax
0x180020302  jb      loc_1800204D8
0x180020308  mov     eax, edi
0x18002030a  sub     eax, r10d
0x18002030d  mov     [r8+rdx+10h], r10d
0x180020312  xor     r11d, r11d
0x180020315  mov     [r8+rdx+14h], eax
0x18002031a  test    r9, r9
0x18002031d  jz      short loc_180020338
0x18002031f  mov     rcx, rsi; HIMCC
0x180020322  call    cs:__imp_ImmUnlockIMCC
0x180020328  xor     r11d, r11d
0x18002032b  test    eax, eax
0x18002032d  jnz     short loc_180020338
0x18002032f  call    cs:__imp_GetLastError
0x180020335  xor     r11d, r11d
0x180020338  lea     ebx, [rdi-1]
0x18002033b  mov     esi, r11d
0x18002033e  lea     rbx, [rbx+7]
0x180020342  lea     rbx, [r15+rbx*4]
0x180020346  mov     r15, [rbp+57h+var_98]
0x18002034a  cmp     esi, edi
0x18002034c  jnb     loc_180020461
0x180020352  mov     rax, [rbp+57h+var_78]
0x180020356  mov     ecx, ebx
0x180020358  sub     ecx, eax
0x18002035a  mov     r10d, esi
0x18002035d  mov     [rax+r10*4+18h], ecx
0x180020362  cmp     ecx, r14d
0x180020365  ja      loc_180020438
0x18002036b  mov     eax, r14d
0x18002036e  sub     eax, ecx
0x180020370  mov     ecx, eax
0x180020372  jz      short loc_1800203C0
0x180020374  cmp     rcx, 7FFFFFFFh
0x18002037b  ja      loc_1800204E9
0x180020381  mov     r8, [r15+r10*8]
0x180020385  mov     edx, 7FFFFFFEh
0x18002038a  mov     rax, rbx
0x18002038d  test    rdx, rdx
0x180020390  jz      short loc_1800203B1
0x180020392  movzx   r9d, word ptr [r8]
0x180020396  test    r9w, r9w
0x18002039a  jz      short loc_1800203B1
0x18002039c  mov     [rax], r9w
0x1800203a0  add     r8, 2
0x1800203a4  add     rax, 2
  ... truncated ...
```
