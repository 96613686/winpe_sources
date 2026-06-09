# _StrictElementCoerceType(ushort,void const *,ushort,void *,int)

- ea: `0x180009db0`
- end: `0x18000a216`
- name: `?_StrictElementCoerceType@@YAJGPEBXGPEAXH@Z`
- size: `1126`
- prototype: `int(unsigned __int16, const void *, unsigned __int16, void *, int)`
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180009590`
- `0x18008d58c`
- `0x18008d620`

## callees

- `0x180009240`
- `0x180009db0`
- `0x18000a220`
- `0x180023684`
- `0x180024418`
- `0x1800272f8`
- `0x18002ab10`
- `0x18003feb0`
- `0x180048760`
- `0x18006133c`
- `0x18006ed20`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000a116`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000a195`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000a116`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000a195`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009ee3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009ee3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009ece`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009ed8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a1b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009ece`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009ed8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a1b9`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupA` at `0x18000a02c`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupA` at `0x18000a02c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _StrictElementCoerceType(
        __int64 vt,
        const PROPVARIANT *a2,
        VARTYPE a3,
        unsigned __int16 **a4,
        PROPVAR_CHANGE_FLAGS flags)
{
  unsigned int v6; // ebx
  LPCSTR *p_ppwsz; // r10
  HRESULT ElemPtr; // edi
  __int64 v9; // rdx
  LPCSTR v10; // rcx
  unsigned __int16 v11; // r8
  double *p_FileTime; // r9
  int v13; // esi
  unsigned int v15; // eax
  unsigned __int64 cbMultiByte; // rbx
  void *v17; // rcx
  unsigned __int64 v18; // [rsp+40h] [rbp-61h] BYREF
  LPWSTR ppwsz; // [rsp+48h] [rbp-59h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-51h] BYREF
  LPCSTR v21; // [rsp+58h] [rbp-49h] BYREF
  double v22; // [rsp+60h] [rbp-41h] BYREF
  __int64 v23; // [rsp+68h] [rbp-39h] BYREF
  FILETIME FileTime; // [rsp+70h] [rbp-31h] BYREF
  double v25; // [rsp+78h] [rbp-29h] BYREF
  struct tagPROPVARIANT pvar; // [rsp+80h] [rbp-21h] BYREF

  v6 = a3;
  p_ppwsz = (LPCSTR *)a2;
  ElemPtr = 0;
  memset(&pvar, 0, sizeof(pvar));
  if ( (_WORD)vt != 12 )
    goto LABEL_2;
  ElemPtr = PropVariantChangeType((PROPVARIANT *)&pvar, a2, flags, a3);
  if ( ElemPtr >= 0 )
  {
    ppwsz = 0;
    ElemPtr = PropVariantGetElemPtr(&pvar, 0, (void **)&ppwsz);
    if ( ElemPtr >= 0 )
    {
      p_ppwsz = (LPCSTR *)ppwsz;
      vt = pvar.vt;
LABEL_2:
      v22 = 0.0;
      v21 = 0;
      ppwsz = 0;
      v23 = 0;
      if ( (_WORD)vt )
      {
        if ( (unsigned __int16)(vt - 2) > 0x3Eu || (v9 = 0x40000000200FC20BLL, !_bittest64(&v9, (unsigned int)(vt - 2))) )
        {
          if ( (_WORD)vt != 72 )
          {
            if ( (unsigned __int16)vt != 8 )
            {
              switch ( (__int16)vt )
              {
                case 1:
                  LOWORD(vt) = 0;
                  goto LABEL_11;
                case 4:
                  v22 = *(float *)p_ppwsz;
                  p_ppwsz = (LPCSTR *)&v22;
                  LOWORD(vt) = 5;
                  goto LABEL_11;
                case 7:
                  ElemPtr = VariantTimeToFileTime(vt, &v23, 3, 19);
                  p_ppwsz = (LPCSTR *)&v23;
                  LOWORD(vt) = 64;
                  goto LABEL_11;
                case 22:
                  LOWORD(vt) = 3;
                  goto LABEL_11;
                case 23:
                  LOWORD(vt) = 19;
                  goto LABEL_11;
                case 30:
                  ElemPtr = SHStrDupA(*p_ppwsz, &ppwsz);
                  p_ppwsz = (LPCSTR *)&ppwsz;
                  goto LABEL_10;
                default:
                  ElemPtr = -2147316576;
                  break;
              }
              goto LABEL_16;
            }
            v10 = (LPCSTR)&Src;
            if ( *p_ppwsz )
              v10 = *p_ppwsz;
            v21 = v10;
            p_ppwsz = &v21;
LABEL_10:
            LOWORD(vt) = 31;
          }
        }
LABEL_11:
        if ( ElemPtr < 0 )
        {
LABEL_16:
          CoTaskMemFree(ppwsz);
          goto LABEL_17;
        }
      }
      v11 = v6;
      p_FileTime = (double *)a4;
      v25 = 0.0;
      pv = 0;
      FileTime = 0;
      v13 = -2143352787;
      if ( v6 <= 0x1F && _bittest(&v13, v6) || v6 == 64 || v6 == 72 )
        goto LABEL_14;
      switch ( v6 )
      {
        case 4u:
          p_FileTime = &v25;
          v11 = 5;
          break;
        case 7u:
          p_FileTime = (double *)&FileTime;
          v11 = 64;
          break;
        case 8u:
LABEL_32:
          p_FileTime = (double *)&pv;
          v11 = 31;
          break;
        case 0x16u:
          v11 = 3;
          break;
        case 0x17u:
          v11 = 19;
          break;
        case 0x1Eu:
          goto LABEL_32;
        default:
          ElemPtr = -2147316576;
LABEL_15:
          CoTaskMemFree(pv);
          goto LABEL_16;
      }
LABEL_14:
      ElemPtr = _StrictElementCoercePrimaryType(vt, p_ppwsz, v11, p_FileTime, flags);
      if ( ElemPtr >= 0 && (v6 > 0x1F || !_bittest(&v13, v6)) && v6 != 64 && v6 != 72 )
      {
        switch ( v6 )
        {
          case 4u:
            *(float *)a4 = v25;
            break;
          case 7u:
            ElemPtr = FileTimeToVariantTime(&FileTime);
            break;
          case 8u:
            ElemPtr = SHSysAllocString((const unsigned __int16 *)pv, a4);
            break;
          default:
            if ( v6 != 22 && v6 != 23 )
            {
              if ( v6 == 30 )
              {
                v15 = WideCharToMultiByte(0, 0x400u, (LPCWCH)pv, -1, 0, 0, 0, 0);
                cbMultiByte = v15;
                if ( v15 || (ElemPtr = ResultFromKnownLastError(), ElemPtr >= 0) )
                {
                  *a4 = 0;
                  v18 = 0;
                  ElemPtr = ULongLongMult(cbMultiByte, 1u, &v18);
                  if ( ElemPtr >= 0 )
                  {
                    ElemPtr = CTCoAllocPolicy::Alloc(v17, 1u, v18, (void **)a4);
                    if ( ElemPtr >= 0 )
                    {
                      if ( WideCharToMultiByte(0, 0x400u, (LPCWCH)pv, -1, (LPSTR)*a4, cbMultiByte, 0, 0) )
                      {
                        ElemPtr = 0;
                      }
                      else
                      {
                        ElemPtr = ResultFromKnownLastError();
                        if ( ElemPtr < 0 )
                        {
                          CoTaskMemFree(*a4);
                          *a4 = 0;
                        }
                      }
                    }
                  }
                }
              }
              else
              {
                ElemPtr = -2147418113;
              }
            }
            break;
        }
      }
      goto LABEL_15;
    }
  }
LABEL_17:
  PropVariantClear((PROPVARIANT *)&pvar);
  return (unsigned int)ElemPtr;
}

```

## disassembly

```asm
0x180009db0  push    rbp
0x180009db2  push    rbx
0x180009db3  push    rsi
0x180009db4  push    rdi
0x180009db5  push    r12
0x180009db7  push    r13
0x180009db9  push    r14
0x180009dbb  push    r15
0x180009dbd  lea     rbp, [rsp-17h]
0x180009dc2  sub     rsp, 0B8h
0x180009dc9  movaps  [rsp+0F0h+var_50], xmm6
0x180009dd1  mov     rax, cs:__security_cookie
0x180009dd8  xor     rax, rsp
0x180009ddb  mov     [rbp+4Fh+var_58], rax
0x180009ddf  mov     r14, r9
0x180009de2  movzx   ebx, r8w
0x180009de6  mov     r10, rdx
0x180009de9  xor     r12d, r12d
0x180009dec  mov     edi, r12d
0x180009def  xorps   xmm0, xmm0
0x180009df2  xor     eax, eax
0x180009df4  movups  xmmword ptr [rbp+4Fh+pvar], xmm0
0x180009df8  mov     [rbp+4Fh+var_60], rax
0x180009dfc  mov     r15d, [rbp+4Fh+flags]
0x180009e00  cmp     cx, 0Ch
0x180009e04  jz      loc_18000A08C
0x180009e0a  xorps   xmm6, xmm6
0x180009e0d  movsd   [rbp+4Fh+var_90], xmm6
0x180009e12  mov     [rbp+4Fh+var_98], r12
0x180009e16  mov     [rbp+4Fh+ppwsz], r12
0x180009e1a  mov     [rbp+4Fh+var_88], r12
0x180009e1e  mov     esi, 40h ; '@'
0x180009e23  mov     r11d, 5
0x180009e29  mov     r8d, 3
0x180009e2f  mov     r9d, 13h
0x180009e35  mov     r13d, 1Fh
0x180009e3b  test    cx, cx
0x180009e3e  jz      short loc_180009E8C
0x180009e40  lea     eax, [rcx-2]
0x180009e43  cmp     ax, 3Eh ; '>'
0x180009e47  ja      short loc_180009E59
0x180009e49  mov     rdx, 40000000200FC20Bh
0x180009e53  bt      rdx, rax
0x180009e57  jb      short loc_180009E88
0x180009e59  cmp     cx, 48h ; 'H'
0x180009e5d  jz      short loc_180009E88
0x180009e5f  movzx   eax, cx
0x180009e62  cmp     eax, 8
0x180009e65  jnz     loc_180009F42
0x180009e6b  mov     rax, [r10]
0x180009e6e  lea     rcx, Src
0x180009e75  test    rax, rax
0x180009e78  cmovnz  rcx, rax
0x180009e7c  mov     [rbp+4Fh+var_98], rcx
0x180009e80  lea     r10, [rbp+4Fh+var_98]
0x180009e84  movzx   ecx, r13w; unsigned __int16
0x180009e88  test    edi, edi
0x180009e8a  js      short loc_180009ED4
0x180009e8c  movzx   r8d, bx; unsigned __int16
0x180009e90  mov     r9, r14; void *
0x180009e93  movsd   [rbp+4Fh+var_78], xmm6
0x180009e98  mov     [rbp+4Fh+pv], r12
0x180009e9c  mov     qword ptr [rbp+4Fh+FileTime.dwLowDateTime], r12
0x180009ea0  mov     esi, 803F082Dh
0x180009ea5  cmp     ebx, r13d
0x180009ea8  ja      loc_180009F84
0x180009eae  bt      esi, ebx
0x180009eb1  jnb     loc_180009F84
0x180009eb7  mov     dword ptr [rsp+0F0h+lpMultiByteStr], r15d; int
0x180009ebc  mov     rdx, r10; void *
0x180009ebf  call    ?_StrictElementCoercePrimaryType@@YAJGPEBXGPEAXH@Z; _StrictElementCoercePrimaryType(ushort,void const *,ushort,void *,int)
0x180009ec4  mov     edi, eax
0x180009ec6  test    eax, eax
0x180009ec8  jns     short loc_180009F13
0x180009eca  mov     rcx, [rbp+4Fh+pv]; pv
0x180009ece  call    cs:__imp_CoTaskMemFree
0x180009ed4  mov     rcx, [rbp+4Fh+ppwsz]; pv
0x180009ed8  call    cs:__imp_CoTaskMemFree
0x180009ede  nop
0x180009edf  lea     rcx, [rbp+4Fh+pvar]; pvar
0x180009ee3  call    cs:__imp_PropVariantClear
0x180009ee9  mov     eax, edi
0x180009eeb  mov     rcx, [rbp+4Fh+var_58]
0x180009eef  xor     rcx, rsp; StackCookie
0x180009ef2  call    __security_check_cookie
0x180009ef7  movaps  xmm6, [rsp+0F0h+var_50]
0x180009eff  add     rsp, 0B8h
0x180009f06  pop     r15
0x180009f08  pop     r14
0x180009f0a  pop     r13
0x180009f0c  pop     r12
0x180009f0e  pop     rdi
0x180009f0f  pop     rsi
0x180009f10  pop     rbx
0x180009f11  pop     rbp
0x180009f12  retn
0x180009f13  cmp     ebx, r13d
0x180009f16  ja      short loc_180009F1D
0x180009f18  bt      esi, ebx
0x180009f1b  jb      short loc_180009ECA
0x180009f1d  cmp     ebx, 40h ; '@'
0x180009f20  jz      short loc_180009ECA
0x180009f22  cmp     ebx, 48h ; 'H'
0x180009f25  jz      short loc_180009ECA
0x180009f27  mov     ecx, ebx
0x180009f29  cmp     ebx, 4
0x180009f2c  jnz     loc_180009FC5
0x180009f32  movsd   xmm0, [rbp+4Fh+var_78]
0x180009f37  cvtpd2ps xmm0, xmm0
0x180009f3b  movss   dword ptr [r14], xmm0
0x180009f40  jmp     short loc_180009ECA
0x180009f42  dec     eax; switch 30 cases
0x180009f44  cmp     eax, 1Dh
0x180009f47  ja      def_180009F68; jumptable 0000000180009F68 default case, cases 2,3,5,6,8-21,24-29
0x180009f4d  cdqe
0x180009f4f  lea     rdx, __ImageBase
0x180009f56  movzx   eax, ds:(byte_18000A1F8 - 180000000h)[rdx+rax]
0x180009f5e  mov     ecx, ds:(jpt_180009F68 - 180000000h)[rdx+rax*4]
0x180009f65  add     rcx, rdx
0x180009f68  jmp     rcx; switch jump
0x180009f6a  movss   xmm0, dword ptr [r10]; jumptable 0000000180009F68 case 4
0x180009f6f  cvtps2pd xmm0, xmm0
0x180009f72  movsd   [rbp+4Fh+var_90], xmm0
0x180009f77  lea     r10, [rbp+4Fh+var_90]
0x180009f7b  movzx   ecx, r11w
0x180009f7f  jmp     loc_180009E88
0x180009f84  cmp     ebx, 40h ; '@'
0x180009f87  jz      loc_180009EB7
0x180009f8d  cmp     ebx, 48h ; 'H'
0x180009f90  jz      loc_180009EB7
0x180009f96  mov     edx, ebx
0x180009f98  cmp     ebx, 4
0x180009f9b  jnz     short loc_180009FAA
0x180009f9d  lea     r9, [rbp+4Fh+var_78]
0x180009fa1  movzx   r8d, r11w
0x180009fa5  jmp     loc_180009EB7
0x180009faa  sub     edx, 7
0x180009fad  jz      loc_18000A07D
0x180009fb3  sub     edx, 1
0x180009fb6  jnz     short loc_18000A00C
0x180009fb8  lea     r9, [rbp+4Fh+pv]
0x180009fbc  movzx   r8d, r13w
0x180009fc0  jmp     loc_180009EB7
0x180009fc5  sub     ecx, 7
0x180009fc8  jz      loc_18000A1C7
0x180009fce  sub     ecx, 1
0x180009fd1  jnz     loc_18000A0D0
0x180009fd7  mov     rdx, r14; unsigned __int16 **
0x180009fda  mov     rcx, [rbp+4Fh+pv]; unsigned __int16 *
0x180009fde  call    ?SHSysAllocString@@YAJPEBGPEAPEAG@Z; SHSysAllocString(ushort const *,ushort * *)
0x180009fe3  mov     edi, eax
0x180009fe5  jmp     loc_180009ECA
0x180009fea  lea     rdx, [rbp+4Fh+var_88]; jumptable 0000000180009F68 case 7
0x180009fee  movsd   xmm0, qword ptr [r10]
0x180009ff3  call    VariantTimeToFileTime
0x180009ff8  mov     edi, eax
0x180009ffa  lea     r10, [rbp+4Fh+var_88]
0x180009ffe  movzx   ecx, si
0x18000a001  mov     r11d, 5
0x18000a007  jmp     loc_180009E88
0x18000a00c  sub     edx, 0Eh
0x18000a00f  jz      short loc_18000A072
0x18000a011  sub     edx, 1
0x18000a014  jz      short loc_18000A067
0x18000a016  cmp     edx, 7
0x18000a019  jz      short loc_180009FB8
0x18000a01b  mov     edi, 80028CA0h
0x18000a020  jmp     loc_180009ECA
0x18000a025  lea     rdx, [rbp+4Fh+ppwsz]; jumptable 0000000180009F68 case 30
0x18000a029  mov     rcx, [r10]; psz
0x18000a02c  call    cs:__imp_SHStrDupA
0x18000a032  mov     edi, eax
0x18000a034  lea     r10, [rbp+4Fh+ppwsz]
0x18000a038  mov     r11d, 5
0x18000a03e  jmp     loc_180009E84
0x18000a043  mov     ecx, r12d; jumptable 0000000180009F68 case 1
0x18000a046  jmp     loc_180009E88
0x18000a04b  movzx   ecx, r8w; jumptable 0000000180009F68 case 22
0x18000a04f  jmp     loc_180009E88
0x18000a054  movzx   ecx, r9w; jumptable 0000000180009F68 case 23
0x18000a058  jmp     loc_180009E88
0x18000a05d  mov     edi, 80028CA0h; jumptable 0000000180009F68 default case, cases 2,3,5,6,8-21,24-29
0x18000a062  jmp     loc_180009ED4
0x18000a067  mov     r8d, 13h
0x18000a06d  jmp     loc_180009EB7
0x18000a072  mov     r8d, 3
0x18000a078  jmp     loc_180009EB7
0x18000a07d  lea     r9, [rbp+4Fh+FileTime]
0x18000a081  mov     r8d, 40h ; '@'
0x18000a087  jmp     loc_180009EB7
0x18000a08c  movzx   r9d, bx; vt
0x18000a090  mov     r8d, r15d; flags
0x18000a093  lea     rcx, [rbp+4Fh+pvar]; ppropvarDest
0x18000a097  call    PropVariantChangeType
0x18000a09c  mov     edi, eax
0x18000a09e  test    eax, eax
0x18000a0a0  js      loc_180009EDF
0x18000a0a6  mov     [rbp+4Fh+ppwsz], r12
0x18000a0aa  lea     r8, [rbp+4Fh+ppwsz]; void **
0x18000a0ae  xor     edx, edx; unsigned int
0x18000a0b0  lea     rcx, [rbp+4Fh+pvar]; struct tagPROPVARIANT *
0x18000a0b4  call    ?PropVariantGetElemPtr@@YAJAEBUtagPROPVARIANT@@KPEAPEAX@Z; PropVariantGetElemPtr(tagPROPVARIANT const &,ulong,void * *)
0x18000a0b9  mov     edi, eax
0x18000a0bb  test    eax, eax
0x18000a0bd  js      loc_180009EDF
0x18000a0c3  mov     r10, [rbp+4Fh+ppwsz]
0x18000a0c7  movzx   ecx, word ptr [rbp+4Fh+pvar]
0x18000a0cb  jmp     loc_180009E0A
0x18000a0d0  sub     ecx, 0Eh
0x18000a0d3  jz      loc_180009ECA
0x18000a0d9  sub     ecx, 1
0x18000a0dc  jz      loc_180009ECA
0x18000a0e2  cmp     ecx, 7
0x18000a0e5  jz      short loc_18000A0F1
0x18000a0e7  mov     edi, 8000FFFFh
0x18000a0ec  jmp     loc_180009ECA
0x18000a0f1  mov     [rsp+0F0h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x18000a0f6  mov     [rsp+0F0h+lpDefaultChar], r12; lpDefaultChar
0x18000a0fb  mov     [rsp+0F0h+cbMultiByte], r12d; cbMultiByte
0x18000a100  mov     [rsp+0F0h+lpMultiByteStr], r12; lpMultiByteStr
0x18000a105  mov     r9d, 0FFFFFFFFh; cchWideChar
0x18000a10b  mov     r8, [rbp+4Fh+pv]; lpWideCharStr
0x18000a10f  mov     edx, 400h; dwFlags
0x18000a114  xor     ecx, ecx; CodePage
0x18000a116  call    cs:__imp_WideCharToMultiByte
0x18000a11c  mov     ebx, eax
0x18000a11e  test    eax, eax
0x18000a120  jnz     short loc_18000A131
0x18000a122  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000a127  mov     edi, eax
0x18000a129  test    eax, eax
0x18000a12b  js      loc_180009ECA
0x18000a131  mov     [r14], r12
0x18000a134  mov     [rbp+4Fh+var_B0], r12
0x18000a138  mov     rcx, rbx; unsigned __int64
0x18000a13b  lea     r8, [rbp+4Fh+var_B0]; unsigned __int64 *
0x18000a13f  mov     edx, 1; unsigned __int64
0x18000a144  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18000a149  mov     edi, eax
0x18000a14b  test    eax, eax
0x18000a14d  js      loc_180009ECA
0x18000a153  mov     r9, r14; void **
0x18000a156  mov     r8, [rbp+4Fh+var_B0]; unsigned __int64
0x18000a15a  mov     edx, 1; unsigned int
0x18000a15f  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18000a164  mov     edi, eax
0x18000a166  test    eax, eax
0x18000a168  js      loc_180009ECA
0x18000a16e  mov     [rsp+0F0h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x18000a173  mov     [rsp+0F0h+lpDefaultChar], r12; lpDefaultChar
0x18000a178  mov     [rsp+0F0h+cbMultiByte], ebx; cbMultiByte
0x18000a17c  mov     rax, [r14]
0x18000a17f  mov     [rsp+0F0h+lpMultiByteStr], rax; lpMultiByteStr
0x18000a184  mov     r9d, 0FFFFFFFFh; cchWideChar
0x18000a18a  mov     r8, [rbp+4Fh+pv]; lpWideCharStr
0x18000a18e  mov     edx, 400h; dwFlags
0x18000a193  xor     ecx, ecx; CodePage
0x18000a195  call    cs:__imp_WideCharToMultiByte
0x18000a19b  test    eax, eax
0x18000a19d  jz      short loc_18000A1A7
0x18000a19f  mov     edi, r12d
0x18000a1a2  jmp     loc_180009ECA
0x18000a1a7  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000a1ac  mov     edi, eax
0x18000a1ae  test    eax, eax
0x18000a1b0  jns     loc_180009ECA
0x18000a1b6  mov     rcx, [r14]; pv
0x18000a1b9  call    cs:__imp_CoTaskMemFree
0x18000a1bf  mov     [r14], r12
0x18000a1c2  jmp     loc_180009ECA
0x18000a1c7  mov     rdx, r14
0x18000a1ca  lea     rcx, [rbp+4Fh+FileTime]; lpFileTime
0x18000a1ce  call    FileTimeToVariantTime
0x18000a1d3  mov     edi, eax
0x18000a1d5  jmp     loc_180009ECA
```
