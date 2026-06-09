# CPropertyStorage::_WriteMultiple(ulong,tagPROPSPEC const * const,tagPROPVARIANT const * const,ulong)

- ea: `0x180035e8c`
- end: `0x18003629b`
- name: `?_WriteMultiple@CPropertyStorage@@AEAAJKQEBUtagPROPSPEC@@QEBUtagPROPVARIANT@@K@Z`
- size: `1039`
- prototype: `int(CPropertyStorage *__hidden this, unsigned int, const struct tagPROPSPEC *const, const struct tagPROPVARIANT *const, unsigned int)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180027840`
- `0x180057590`

## callees

- `0x180027128`
- `0x180035e8c`
- `0x18003a6b0`
- `0x18003e690`
- `0x18003f834`
- `0x180042800`
- `0x1800504d8`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003622b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036254`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036270`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003622b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036254`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036270`

## pseudocode

```c
__int64 __fastcall CPropertyStorage::_WriteMultiple(
        CPropertyStorage *this,
        unsigned int a2,
        const struct tagPROPSPEC *const a3,
        const struct tagPROPVARIANT *const a4,
        unsigned int a5)
{
  int v9; // eax
  unsigned int *v10; // rcx
  unsigned int v11; // ebx
  struct _INDIRECTPROPERTY **p_pv; // rax
  int v13; // eax
  int v14; // eax
  unsigned int v15; // edx
  int v16; // eax
  _DWORD *v17; // rcx
  int i; // esi
  unsigned __int16 *v19; // r12
  __int64 v20; // rdi
  __int64 v21; // r15
  BSTR *pbstrVal; // rsi
  int v23; // edi
  unsigned int v24; // eax
  int j; // edi
  unsigned int v26; // eax
  LARGE_INTEGER hVal; // rcx
  int v29; // edi
  unsigned __int16 *v30; // [rsp+20h] [rbp-E0h]
  __int64 v31; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v33; // [rsp+50h] [rbp-B0h] BYREF
  const struct tagPROPVARIANT *v34; // [rsp+58h] [rbp-A8h]
  struct _INDIRECTPROPERTY *v35[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int *v36; // [rsp+70h] [rbp-90h] BYREF
  int v37; // [rsp+78h] [rbp-88h]
  unsigned int *v38; // [rsp+80h] [rbp-80h]
  int v39; // [rsp+88h] [rbp-78h]
  _BYTE v40[256]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v41[32]; // [rsp+190h] [rbp+90h] BYREF

  v34 = a4;
  v37 = 64;
  v36 = (unsigned int *)v40;
  v39 = 4;
  v38 = (unsigned int *)v40;
  pv = 0;
  v35[0] = 0;
  v35[1] = 0;
  v9 = CStackBuffer::Init((CStackBuffer *)&v36, a2);
  v10 = v36;
  v11 = v9;
  if ( v9 )
    goto LABEL_63;
  p_pv = (struct _INDIRECTPROPERTY **)&pv;
  if ( a2 == 1 )
    p_pv = v35;
  v13 = PrSetProperties(
          *((struct CPropertySetStream **)this + 4),
          a2,
          a5,
          a3,
          (unsigned __int16 *)this + 50,
          v36,
          p_pv,
          a4);
  if ( v13 < 0 )
  {
    v11 = DfpNtStatusToHResult(v13);
  }
  else
  {
    v14 = *((_DWORD *)this + 27);
    v15 = v14 & 0xFFFFFFFD;
    v16 = v14 | 2;
    if ( *((_WORD *)this + 50) != 1200 )
      v15 = v16;
    *((_DWORD *)this + 27) = v15;
    if ( a2 == 1 )
    {
      if ( LODWORD(v35[0]) != -1 )
      {
        v17 = v35;
        pv = v35;
LABEL_13:
        if ( (v15 & 1) != 0 )
        {
          for ( i = 0; ; ++i )
          {
            LODWORD(v31) = i;
            if ( v11 || v17[4 * i] == -1 )
              goto LABEL_53;
            if ( v17[4 * i] >= a2 )
            {
              CStackBuffer::~CStackBuffer((CStackBuffer *)&v36);
              return 2147549183LL;
            }
            v19 = *(unsigned __int16 **)&v17[4 * i + 2];
            v20 = (unsigned int)v17[4 * i];
            if ( !v19 )
            {
              StringCbPrintfW(v41, 0x20u, L"prop%lu", v36[v20]);
              v19 = v41;
            }
            if ( !v34 )
            {
LABEL_50:
              v11 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(**((_QWORD **)this + 2) + 96LL))(
                      *((_QWORD *)this + 2),
                      v19);
              goto LABEL_48;
            }
            v21 = v20;
            if ( v34[v20].vt == 66 )
              goto LABEL_26;
            if ( v34[v20].vt != 67 )
            {
              if ( v34[v20].vt == 68 )
                goto LABEL_26;
              if ( v34[v20].vt != 69 )
                break;
            }
            v31 = 0;
            for ( j = 0; j <= 1; ++j )
            {
              LODWORD(v30) = 0;
              v26 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, _QWORD, _QWORD, unsigned __int16 *, __int64 *))(**((_QWORD **)this + 2) + 40LL))(
                      *((_QWORD *)this + 2),
                      v19,
                      *((_DWORD *)this + 28) & 0xFFFEEF8F | 0x1010,
                      0,
                      v30,
                      &v31);
              v11 = v26;
              if ( !v26 )
              {
                hVal = v34[v21].hVal;
                if ( hVal.QuadPart )
                  v11 = (*(__int64 (__fastcall **)(LARGE_INTEGER, _QWORD, _QWORD, _QWORD, __int64))(*(_QWORD *)hVal.QuadPart
                                                                                                  + 56LL))(
                          hVal,
                          0,
                          0,
                          0,
                          v31);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
                break;
              }
              if ( v26 != -2147286960 )
                break;
              if ( !j )
                (*(void (__fastcall **)(_QWORD, unsigned __int16 *))(**((_QWORD **)this + 2) + 96LL))(
                  *((_QWORD *)this + 2),
                  v19);
            }
LABEL_48:
            v17 = pv;
            if ( a2 == 1 )
              goto LABEL_53;
          }
          if ( v34[v20].vt != 73 )
            goto LABEL_50;
LABEL_26:
          pbstrVal = v34[v20].pbstrVal;
          v23 = 0;
          v33 = 0;
          if ( v34[v21].vt == 73 )
            pbstrVal = (BSTR *)pbstrVal[2];
          while ( v23 <= 1 )
          {
            LODWORD(v30) = 0;
            v24 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *, _QWORD, _QWORD, unsigned __int16 *, __int64 *))(**((_QWORD **)this + 2) + 24LL))(
                    *((_QWORD *)this + 2),
                    v19,
                    *((_DWORD *)this + 28) & 0xFFFEEF8F | 0x1010,
                    0,
                    v30,
                    &v33);
            v11 = v24;
            if ( !v24 )
            {
              if ( pbstrVal )
                v11 = (*((__int64 (__fastcall **)(BSTR *, __int64, __int64, _QWORD, _QWORD))*pbstrVal + 7))(
                        pbstrVal,
                        v33,
                        -1,
                        0,
                        0);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
              break;
            }
            if ( v24 != -2147286960 )
              break;
            if ( !v23 )
              (*(void (__fastcall **)(_QWORD, unsigned __int16 *))(**((_QWORD **)this + 2) + 96LL))(
                *((_QWORD *)this + 2),
                v19);
            ++v23;
          }
          i = v31;
          goto LABEL_48;
        }
        v11 = -2147286800;
LABEL_53:
        v29 = 0;
        if ( *v17 == -1 )
        {
LABEL_58:
          if ( a2 != 1 && v17 )
            CoTaskMemFree(v17);
        }
        else
        {
          while ( 1 )
          {
            if ( *(_QWORD *)&v17[4 * v29 + 2] )
            {
              CoTaskMemFree(*(LPVOID *)&v17[4 * v29 + 2]);
              v17 = pv;
            }
            if ( a2 == 1 )
              break;
            if ( v17[4 * ++v29] == -1 )
              goto LABEL_58;
          }
        }
        goto LABEL_62;
      }
      v17 = 0;
      pv = 0;
    }
    else
    {
      v17 = pv;
    }
    if ( v17 )
      goto LABEL_13;
  }
LABEL_62:
  v10 = v36;
LABEL_63:
  if ( v10 != v38 )
    CoTaskMemFree(v10);
  return v11;
}

```

## disassembly

```asm
0x180035e8c  push    rbp
0x180035e8e  push    rbx
0x180035e8f  push    rsi
0x180035e90  push    rdi
0x180035e91  push    r12
0x180035e93  push    r13
0x180035e95  push    r14
0x180035e97  push    r15
0x180035e99  lea     rbp, [rsp-0E8h]
0x180035ea1  sub     rsp, 1E8h
0x180035ea8  mov     rax, cs:__security_cookie
0x180035eaf  xor     rax, rsp
0x180035eb2  mov     [rbp+120h+var_50], rax
0x180035eb9  xor     edi, edi
0x180035ebb  mov     [rsp+220h+var_1C8], r9
0x180035ec0  lea     rax, [rbp+120h+var_190]
0x180035ec4  mov     [rsp+220h+var_1A8], 40h ; '@'
0x180035ecc  mov     [rsp+220h+var_1B0], rax
0x180035ed1  mov     r13, rcx
0x180035ed4  lea     rax, [rbp+120h+var_190]
0x180035ed8  mov     [rbp+120h+var_198], 4
0x180035edf  lea     rcx, [rsp+220h+var_1B0]; this
0x180035ee4  mov     [rbp+120h+var_1A0], rax
0x180035ee8  mov     r12, r9
0x180035eeb  mov     [rsp+220h+pv], rdi
0x180035ef0  mov     rsi, r8
0x180035ef3  mov     [rsp+220h+var_1C0], rdi
0x180035ef8  mov     r14d, edx
0x180035efb  mov     [rsp+220h+var_1B8], rdi
0x180035f00  call    ?Init@CStackBuffer@@QEAAJK@Z; CStackBuffer::Init(ulong)
0x180035f05  mov     rcx, [rsp+220h+var_1B0]
0x180035f0a  mov     ebx, eax
0x180035f0c  test    eax, eax
0x180035f0e  jnz     loc_18003626A
0x180035f14  mov     r8d, [rbp+120h+arg_20]; unsigned int
0x180035f1b  lea     rdx, [rsp+220h+var_1C0]
0x180035f20  mov     [rsp+220h+var_1E8], r12; struct tagPROPVARIANT *
0x180035f25  lea     rax, [rsp+220h+pv]
0x180035f2a  cmp     r14d, 1
0x180035f2e  lea     rdi, [r13+64h]
0x180035f32  mov     r9, rsi; struct tagPROPSPEC *
0x180035f35  cmovz   rax, rdx
0x180035f39  mov     edx, r14d; unsigned int
0x180035f3c  mov     [rsp+220h+var_1F0], rax; struct _INDIRECTPROPERTY **
0x180035f41  mov     [rsp+220h+var_1F8], rcx; unsigned int *
0x180035f46  mov     rcx, [r13+20h]; this
0x180035f4a  mov     [rsp+220h+var_200], rdi; unsigned __int16 *
0x180035f4f  call    ?PrSetProperties@@YAJPEAVCPropertySetStream@@KKQEBUtagPROPSPEC@@PEAGQEAKPEAPEAU_INDIRECTPROPERTY@@QEBUtagPROPVARIANT@@@Z; PrSetProperties(CPropertySetStream *,ulong,ulong,tagPROPSPEC const * const,ushort *,ulong * const,_INDIRECTPROPERTY * *,tagPROPVARIANT const * const)
0x180035f54  test    eax, eax
0x180035f56  js      loc_18003625C
0x180035f5c  mov     edx, [r13+6Ch]
0x180035f60  mov     ecx, 4B0h
0x180035f65  mov     eax, edx
0x180035f67  and     edx, 0FFFFFFFDh
0x180035f6a  or      eax, 2
0x180035f6d  cmp     cx, [rdi]
0x180035f70  cmovnz  edx, eax
0x180035f73  mov     [r13+6Ch], edx
0x180035f77  cmp     r14d, 1
0x180035f7b  jnz     short loc_180035F99
0x180035f7d  cmp     dword ptr [rsp+220h+var_1C0], 0FFFFFFFFh
0x180035f82  jz      short loc_180035F90
0x180035f84  lea     rcx, [rsp+220h+var_1C0]
0x180035f89  mov     [rsp+220h+pv], rcx
0x180035f8e  jmp     short loc_180035FA7
0x180035f90  xor     ecx, ecx
0x180035f92  mov     [rsp+220h+pv], rcx
0x180035f97  jmp     short loc_180035F9E
0x180035f99  mov     rcx, [rsp+220h+pv]
0x180035f9e  test    rcx, rcx
0x180035fa1  jz      loc_180036265
0x180035fa7  test    dl, 1
0x180035faa  jz      loc_18003620D
0x180035fb0  xor     esi, esi
0x180035fb2  mov     dword ptr [rsp+220h+var_1E0], esi
0x180035fb6  test    ebx, ebx
0x180035fb8  jnz     loc_180036212
0x180035fbe  mov     eax, esi
0x180035fc0  add     rax, rax
0x180035fc3  cmp     dword ptr [rcx+rax*8], 0FFFFFFFFh
0x180035fc7  jz      loc_180036212
0x180035fcd  cmp     [rcx+rax*8], r14d
0x180035fd1  jnb     loc_1800361FC
0x180035fd7  mov     r12, [rcx+rax*8+8]
0x180035fdc  mov     edi, [rcx+rax*8]
0x180035fdf  test    r12, r12
0x180035fe2  jnz     short loc_18003600A
0x180035fe4  mov     r9, [rsp+220h+var_1B0]
0x180035fe9  lea     r8, aPropLu; "prop%lu"
0x180035ff0  lea     edx, [rbx+20h]; unsigned __int64
0x180035ff3  lea     rcx, [rbp+120h+var_90]; unsigned __int16 *
0x180035ffa  mov     r9d, [r9+rdi*4]
0x180035ffe  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180036003  lea     r12, [rbp+120h+var_90]
0x18003600a  mov     rdx, [rsp+220h+var_1C8]
0x18003600f  test    rdx, rdx
0x180036012  jz      loc_1800361E5
0x180036018  lea     r15, [rdi+rdi*2]
0x18003601c  movzx   ecx, word ptr [rdx+r15*8]
0x180036021  sub     ecx, 42h ; 'B'
0x180036024  jz      short loc_180036046
0x180036026  sub     ecx, 1
0x180036029  jz      loc_1800360D7
0x18003602f  sub     ecx, 1
0x180036032  jz      short loc_180036046
0x180036034  sub     ecx, 1
0x180036037  jz      loc_1800360D7
0x18003603d  cmp     ecx, 4
0x180036040  jnz     loc_1800361E5
0x180036046  mov     rsi, [rdx+r15*8+8]
0x18003604b  xor     edi, edi
0x18003604d  mov     [rsp+220h+var_1D0], 0
0x180036056  lea     eax, [rdi+49h]
0x180036059  cmp     ax, [rdx+r15*8]
0x18003605e  jnz     short loc_180036064
0x180036060  mov     rsi, [rsi+10h]
0x180036064  cmp     edi, 1
0x180036067  jg      loc_1800361CF
0x18003606d  mov     rcx, [r13+10h]
0x180036071  lea     rdx, [rsp+220h+var_1D0]
0x180036076  mov     r8d, [r13+70h]
0x18003607a  xor     r9d, r9d
0x18003607d  mov     [rsp+220h+var_1F8], rdx
0x180036082  and     r8d, 0FFFEFF9Fh
0x180036089  or      r8d, 1010h
0x180036090  mov     dword ptr [rsp+220h+var_200], 0
0x180036098  mov     rax, [rcx]
0x18003609b  mov     rdx, r12
0x18003609e  mov     rax, [rax+18h]
0x1800360a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800360a7  mov     ebx, eax
0x1800360a9  test    eax, eax
0x1800360ab  jz      loc_180036193
0x1800360b1  cmp     eax, 80030050h
0x1800360b6  jnz     loc_1800361CF
0x1800360bc  test    edi, edi
0x1800360be  jnz     short loc_1800360D3
0x1800360c0  mov     rcx, [r13+10h]
0x1800360c4  mov     rdx, r12
0x1800360c7  mov     rax, [rcx]
0x1800360ca  mov     rax, [rax+60h]
0x1800360ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800360d3  inc     edi
0x1800360d5  jmp     short loc_180036064
0x1800360d7  mov     [rsp+220h+var_1E0], 0
0x1800360e0  xor     edi, edi
0x1800360e2  cmp     edi, 1
0x1800360e5  jg      loc_1800361D3
0x1800360eb  mov     rcx, [r13+10h]
0x1800360ef  lea     rdx, [rsp+220h+var_1E0]
0x1800360f4  mov     r8d, [r13+70h]
0x1800360f8  xor     r9d, r9d
0x1800360fb  mov     [rsp+220h+var_1F8], rdx
0x180036100  and     r8d, 0FFFEFF9Fh
0x180036107  or      r8d, 1010h
0x18003610e  mov     dword ptr [rsp+220h+var_200], 0
0x180036116  mov     rax, [rcx]
0x180036119  mov     rdx, r12
0x18003611c  mov     rax, [rax+28h]
0x180036120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036125  mov     ebx, eax
0x180036127  test    eax, eax
0x180036129  jz      short loc_180036151
0x18003612b  cmp     eax, 80030050h
0x180036130  jnz     loc_1800361D3
0x180036136  test    edi, edi
0x180036138  jnz     short loc_18003614D
0x18003613a  mov     rcx, [r13+10h]
0x18003613e  mov     rdx, r12
0x180036141  mov     rax, [rcx]
0x180036144  mov     rax, [rax+60h]
0x180036148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003614d  inc     edi
0x18003614f  jmp     short loc_1800360E2
0x180036151  mov     r12, [rsp+220h+var_1C8]
0x180036156  mov     rcx, [r12+r15*8+8]
0x18003615b  test    rcx, rcx
0x18003615e  jz      short loc_180036180
0x180036160  mov     rdx, [rsp+220h+var_1E0]
0x180036165  xor     r9d, r9d
0x180036168  mov     rax, [rcx]
0x18003616b  xor     r8d, r8d
0x18003616e  mov     [rsp+220h+var_200], rdx
0x180036173  xor     edx, edx
0x180036175  mov     rax, [rax+38h]
0x180036179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003617e  mov     ebx, eax
0x180036180  mov     rcx, [rsp+220h+var_1E0]
0x180036185  mov     rax, [rcx]
0x180036188  mov     rax, [rax+10h]
0x18003618c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036191  jmp     short loc_1800361D3
0x180036193  test    rsi, rsi
0x180036196  jz      short loc_1800361BE
0x180036198  mov     rax, [rsi]
0x18003619b  xor     r9d, r9d
0x18003619e  mov     rdx, [rsp+220h+var_1D0]
0x1800361a3  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800361a7  mov     rcx, rsi
0x1800361aa  mov     [rsp+220h+var_200], 0
0x1800361b3  mov     rax, [rax+38h]
0x1800361b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800361bc  mov     ebx, eax
0x1800361be  mov     rcx, [rsp+220h+var_1D0]
0x1800361c3  mov     rax, [rcx]
0x1800361c6  mov     rax, [rax+10h]
0x1800361ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800361cf  mov     esi, dword ptr [rsp+220h+var_1E0]
0x1800361d3  mov     rcx, [rsp+220h+pv]
0x1800361d8  cmp     r14d, 1
0x1800361dc  jz      short loc_180036212
0x1800361de  inc     esi
0x1800361e0  jmp     loc_180035FB2
0x1800361e5  mov     rcx, [r13+10h]
0x1800361e9  mov     rdx, r12
0x1800361ec  mov     rax, [rcx]
0x1800361ef  mov     rax, [rax+60h]
0x1800361f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800361f8  mov     ebx, eax
0x1800361fa  jmp     short loc_1800361D3
0x1800361fc  lea     rcx, [rsp+220h+var_1B0]; this
0x180036201  call    ??1CStackBuffer@@QEAA@XZ; CStackBuffer::~CStackBuffer(void)
0x180036206  mov     eax, 8000FFFFh
0x18003620b  jmp     short loc_180036278
0x18003620d  mov     ebx, 800300F0h
0x180036212  xor     edi, edi
0x180036214  cmp     dword ptr [rcx], 0FFFFFFFFh
0x180036217  jz      short loc_180036249
0x180036219  mov     eax, edi
0x18003621b  add     rax, rax
0x18003621e  mov     rdx, [rcx+rax*8+8]
0x180036223  test    rdx, rdx
0x180036226  jz      short loc_180036236
0x180036228  mov     rcx, rdx; pv
0x18003622b  call    cs:__imp_CoTaskMemFree
0x180036231  mov     rcx, [rsp+220h+pv]; pv
0x180036236  cmp     r14d, 1
0x18003623a  jz      short loc_180036265
0x18003623c  inc     edi
0x18003623e  mov     eax, edi
0x180036240  add     rax, rax
0x180036243  cmp     dword ptr [rcx+rax*8], 0FFFFFFFFh
0x180036247  jnz     short loc_180036219
0x180036249  cmp     r14d, 1
0x18003624d  jz      short loc_180036265
0x18003624f  test    rcx, rcx
0x180036252  jz      short loc_180036265
0x180036254  call    cs:__imp_CoTaskMemFree
0x18003625a  jmp     short loc_180036265
0x18003625c  mov     ecx, eax; int
0x18003625e  call    ?DfpNtStatusToHResult@@YAJJ@Z; DfpNtStatusToHResult(long)
0x180036263  mov     ebx, eax
0x180036265  mov     rcx, [rsp+220h+var_1B0]; pv
0x18003626a  cmp     rcx, [rbp+120h+var_1A0]
0x18003626e  jz      short loc_180036276
0x180036270  call    cs:__imp_CoTaskMemFree
0x180036276  mov     eax, ebx
0x180036278  mov     rcx, [rbp+120h+var_50]
0x18003627f  xor     rcx, rsp; StackCookie
0x180036282  call    __security_check_cookie
0x180036287  add     rsp, 1E8h
0x18003628e  pop     r15
0x180036290  pop     r14
0x180036292  pop     r13
0x180036294  pop     r12
0x180036296  pop     rdi
0x180036297  pop     rsi
0x180036298  pop     rbx
0x180036299  pop     rbp
0x18003629a  retn
```
