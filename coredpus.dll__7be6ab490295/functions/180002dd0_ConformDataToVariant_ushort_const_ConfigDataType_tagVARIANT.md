# ConformDataToVariant(ushort const *,ConfigDataType,tagVARIANT *)

- ea: `0x180002dd0`
- end: `0x180003254`
- name: `?ConformDataToVariant@@YAJPEBGW4ConfigDataType@@PEAUtagVARIANT@@@Z`
- size: `1156`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, VARIANTARG *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180009380`

## callees

- `0x180002dd0`
- `0x180014330`
- `0x180016398`
- `0x180016700`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x180002faa`
- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x180002faa`
- `OLEAUT32!__imp_SysAllocString` at `0x180002f93`
- `OLEAUT32!__imp_SysAllocString` at `0x180003180`
- `OLEAUT32!__imp_SysAllocString` at `0x180002f93`
- `OLEAUT32!__imp_SysAllocString` at `0x180003180`
- `OLEAUT32!__imp_VariantClear` at `0x1800030f1`
- `OLEAUT32!__imp_VariantClear` at `0x1800030f1`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800031ce`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800031ce`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x1800031b9`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x1800031b9`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x180003160`
- `OLEAUT32!__imp_SystemTimeToVariantTime` at `0x180003160`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800031f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800031f3`
- `DMOleAutUtils!MultiStringToSafeArray` at `0x18000301b`
- `DMOleAutUtils!MultiStringToSafeArray` at `0x18000301b`
- `DMOleAutUtils!Base64StrToSafeArray` at `0x180002fef`
- `DMOleAutUtils!Base64StrToSafeArray` at `0x180002fef`
- `DMCmnUtils!InvStrCmpIW` at `0x180002f0c`
- `DMCmnUtils!InvStrCmpIW` at `0x180002f2d`
- `DMCmnUtils!InvStrCmpIW` at `0x180003052`
- `DMCmnUtils!InvStrCmpIW` at `0x18000307e`
- `DMCmnUtils!InvStrCmpIW` at `0x1800030aa`
- `DMCmnUtils!InvStrCmpIW` at `0x180002f0c`
- `DMCmnUtils!InvStrCmpIW` at `0x180002f2d`
- `DMCmnUtils!InvStrCmpIW` at `0x180003052`
- `DMCmnUtils!InvStrCmpIW` at `0x18000307e`
- `DMCmnUtils!InvStrCmpIW` at `0x1800030aa`
- `DMCmnUtils!CopyString` at `0x180002e68`
- `DMCmnUtils!CopyString` at `0x180002e68`
- `dmiso8601utils!ISO8601StringToSystemTime` at `0x180003119`
- `dmiso8601utils!ISO8601StringToSystemTime` at `0x180003119`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ConformDataToVariant(const unsigned __int16 *a1, int a2, VARIANTARG *a3)
{
  OLECHAR *v5; // r14
  INT v6; // ebx
  int v7; // ebp
  int v8; // r12d
  __int64 v9; // rdx
  __int16 v10; // ax
  const OLECHAR *v11; // rcx
  VARTYPE vt; // di
  HRESULT v13; // eax
  int v15; // [rsp+34h] [rbp-64h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-60h] BYREF
  OLECHAR *psz; // [rsp+40h] [rbp-58h]
  _SYSTEMTIME SystemTime; // [rsp+48h] [rbp-50h] BYREF

  v15 = 0;
  psz = 0;
  hMem = 0;
  v5 = 0;
  SystemTime = 0;
  if ( (a1 != 0) != (a2 != 9) )
  {
    v6 = -2147024809;
    goto LABEL_60;
  }
  v6 = 0;
  if ( a2 == 1 || a2 == 7 )
  {
    v5 = (OLECHAR *)a1;
    goto LABEL_10;
  }
  if ( a2 == 9 )
  {
LABEL_10:
    v7 = 0;
    if ( a2 != 1 )
      goto LABEL_11;
LABEL_52:
    vt = 8;
LABEL_53:
    a3->llVal = (LONGLONG)SysAllocString(v5);
LABEL_54:
    if ( a3->llVal )
    {
      a3->vt = 8;
      if ( v7 )
        v13 = VariantChangeTypeEx(a3, a3, 0x7Fu, 0, vt);
      else
        v13 = VariantChangeType(a3, a3, 0, vt);
      v6 = v13;
    }
    else
    {
      v6 = -2147024882;
    }
    goto LABEL_60;
  }
  v6 = CopyString(a1, 0xFFFFFFFF, (unsigned __int16 **)&hMem);
  if ( v6 >= 0 )
  {
    v6 = TrimString((unsigned __int16 *)hMem);
    if ( v6 >= 0 )
    {
      v7 = 0;
      v5 = psz;
      *((_WORD *)hMem + (((char *)psz - (_BYTE *)hMem) >> 1)) = 0;
LABEL_11:
      v8 = 0;
      v9 = 32;
      switch ( a2 )
      {
        case 0:
          v7 = 1;
          if ( ((*v5 - 78) & 0xFFDF) == 0 )
          {
            if ( v5[1] )
              goto LABEL_24;
            v11 = L"0";
            goto LABEL_23;
          }
          if ( ((*v5 - 89) & 0xFFDF) == 0 && !v5[1] )
          {
            v11 = L"1";
LABEL_23:
            a3->llVal = (LONGLONG)SysAllocString(v11);
            v8 = 1;
          }
LABEL_24:
          if ( !(unsigned int)_o_iswdigit(*v5) && ((*v5 - 43) & 0xFFFD) != 0 && !v8 )
          {
LABEL_48:
            v6 = -2147024809;
            break;
          }
          vt = 3;
          if ( v8 )
            goto LABEL_54;
          goto LABEL_53;
        case 2:
          a3->vt = 4;
          vt = 0;
          if ( InvStrCmpIW(L"NaN", v5) )
          {
            if ( InvStrCmpIW(L"INF", v5) )
            {
              if ( InvStrCmpIW(L"-INF", v5) )
              {
                vt = 4;
                a3->vt = 0;
                v7 = 1;
              }
              else
              {
                v6 = SetSpecialFloatValue(4u, &a3->fltVal);
              }
            }
            else
            {
              v6 = SetSpecialFloatValue(0x200u, &a3->fltVal);
            }
          }
          else
          {
            v6 = SetSpecialFloatValue(2u, &a3->fltVal);
          }
          if ( v6 >= 0 && vt )
            goto LABEL_53;
          break;
        case 3:
          v9 = 16;
          goto LABEL_45;
        case 4:
LABEL_45:
          v6 = ISO8601StringToSystemTime(v5, v9, &SystemTime, &v15);
          if ( v6 < 0 )
            break;
          if ( (v15 & 0x80u) == 0 )
            goto LABEL_50;
          if ( a2 == 3 )
            goto LABEL_48;
          *(_DWORD *)&SystemTime.wYear = 67289;
          SystemTime.wDay = 1;
LABEL_50:
          v6 = SystemTimeToVariantTime(&SystemTime, &a3->dblVal);
          if ( v6 >= 0 )
            a3->vt = 7;
          break;
        case 5:
          if ( InvStrCmpIW(L"true", v5) )
          {
            if ( InvStrCmpIW(L"false", v5) )
              goto LABEL_48;
            v10 = 0;
          }
          else
          {
            v10 = -1;
          }
          a3->iVal = v10;
          a3->vt = 11;
          break;
        case 6:
          v6 = Base64StrToSafeArray(v5, &a3->parray);
          if ( v6 >= 0 )
            a3->vt = 8209;
          break;
        case 7:
          v6 = MultiStringToSafeArray(v5, 0xF000u, &a3->parray);
          if ( v6 >= 0 )
            a3->vt = 8200;
          break;
        case 9:
          VariantClear(a3);
          a3->vt = 1;
          break;
        case 13:
          goto LABEL_52;
        default:
          break;
      }
    }
  }
LABEL_60:
  LocalFree(hMem);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180002dd0  push    rbx
0x180002dd2  push    rsi
0x180002dd3  push    rdi
0x180002dd4  push    r13
0x180002dd6  push    r14
0x180002dd8  sub     rsp, 70h
0x180002ddc  mov     rax, cs:__security_cookie
0x180002de3  xor     rax, rsp
0x180002de6  mov     [rsp+98h+var_40], rax
0x180002deb  xor     r13d, r13d
0x180002dee  movsxd  rdi, edx
0x180002df1  mov     r9, rcx
0x180002df4  mov     [rsp+98h+var_64], r13d
0x180002df9  test    r9, r9
0x180002dfc  mov     [rsp+98h+psz], r13
0x180002e01  mov     ecx, r13d
0x180002e04  mov     [rsp+98h+hMem], r13
0x180002e09  setnz   cl
0x180002e0c  mov     eax, r13d
0x180002e0f  cmp     edi, 9
0x180002e12  xorps   xmm0, xmm0
0x180002e15  mov     rsi, r8
0x180002e18  mov     r14d, r13d
0x180002e1b  setnz   al
0x180002e1e  movups  xmmword ptr [rsp+98h+SystemTime.wYear], xmm0
0x180002e23  cmp     ecx, eax
0x180002e25  jz      short loc_180002E31
0x180002e27  mov     ebx, 80070057h
0x180002e2c  jmp     loc_1800031EE
0x180002e31  mov     [rsp+98h+arg_8], rbp
0x180002e39  mov     ebx, r13d
0x180002e3c  mov     [rsp+98h+var_30], r12
0x180002e41  mov     [rsp+98h+var_38], r15
0x180002e46  mov     r15d, 8
0x180002e4c  cmp     edi, 1
0x180002e4f  jz      short loc_180002ECA
0x180002e51  cmp     edi, 7
0x180002e54  jz      short loc_180002ECA
0x180002e56  cmp     edi, 9
0x180002e59  jz      short loc_180002ECD
0x180002e5b  lea     r8, [rsp+98h+hMem]
0x180002e60  mov     edx, 0FFFFFFFFh
0x180002e65  mov     rcx, r9
0x180002e68  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180002e6f  nop     dword ptr [rax+rax+00h]
0x180002e74  mov     ebx, eax
0x180002e76  test    eax, eax
0x180002e78  js      def_180002EFC; jumptable 0000000180002EFC default case, cases 1,8,10-12
0x180002e7e  mov     rcx, [rsp+98h+hMem]; unsigned __int16 *
0x180002e83  lea     r9, [rsp+98h+var_68]
0x180002e88  lea     r8, [rsp+98h+psz]
0x180002e8d  mov     [rsp+98h+var_68], r13d
0x180002e92  mov     edx, 0FFFFFFFFh
0x180002e97  call    TrimString
0x180002e9c  mov     ebx, eax
0x180002e9e  test    eax, eax
0x180002ea0  js      def_180002EFC; jumptable 0000000180002EFC default case, cases 1,8,10-12
0x180002ea6  mov     rcx, [rsp+98h+hMem]
0x180002eab  mov     ebp, r13d
0x180002eae  mov     r14, [rsp+98h+psz]
0x180002eb3  mov     eax, [rsp+98h+var_68]
0x180002eb7  mov     rdx, r14
0x180002eba  sub     rdx, rcx
0x180002ebd  sar     rdx, 1
0x180002ec0  add     rdx, rax
0x180002ec3  mov     [rcx+rdx*2], r13w
0x180002ec8  jmp     short loc_180002ED9
0x180002eca  mov     r14, r9
0x180002ecd  mov     ebp, r13d
0x180002ed0  cmp     edi, 1
0x180002ed3  jz      loc_180003179; jumptable 0000000180002EFC case 13
0x180002ed9  mov     r12d, r13d
0x180002edc  cmp     edi, 0Dh; switch 14 cases
0x180002edf  ja      def_180002EFC; jumptable 0000000180002EFC default case, cases 1,8,10-12
0x180002ee5  lea     r8, __ImageBase
0x180002eec  mov     edx, 20h ; ' '
0x180002ef1  mov     ecx, ds:(jpt_180002EFC - 180000000h)[r8+rdi*4]
0x180002ef9  add     rcx, r8
0x180002efc  jmp     rcx; switch jump
0x180002f02  mov     rdx, r14; jumptable 0000000180002EFC case 5
0x180002f05  lea     rcx, ?gc_szTrueVal@@3QBGB; "true"
0x180002f0c  call    cs:__imp_?InvStrCmpIW@@YAHPEBG0@Z; InvStrCmpIW(ushort const *,ushort const *)
0x180002f13  nop     dword ptr [rax+rax+00h]
0x180002f18  test    eax, eax
0x180002f1a  jnz     short loc_180002F23
0x180002f1c  mov     eax, 0FFFFFFFFh
0x180002f21  jmp     short loc_180002F44
0x180002f23  mov     rdx, r14
0x180002f26  lea     rcx, ?gc_szFalseVal@@3QBGB; "false"
0x180002f2d  call    cs:__imp_?InvStrCmpIW@@YAHPEBG0@Z; InvStrCmpIW(ushort const *,ushort const *)
0x180002f34  nop     dword ptr [rax+rax+00h]
0x180002f39  test    eax, eax
0x180002f3b  jnz     loc_18000313B
0x180002f41  mov     eax, r13d
0x180002f44  mov     rcx, rsi
0x180002f47  mov     [r15+rcx], ax
0x180002f4c  mov     word ptr [rsi], 0Bh
0x180002f51  jmp     def_180002EFC; jumptable 0000000180002EFC default case, cases 1,8,10-12
0x180002f56  movzx   ecx, word ptr [r14]; jumptable 0000000180002EFC case 0
0x180002f5a  mov     edx, 0FFDFh
0x180002f5f  mov     ebp, 1
0x180002f64  lea     eax, [rcx-4Eh]
0x180002f67  test    dx, ax
0x180002f6a  jz      short loc_180002F85
0x180002f6c  sub     cx, 59h ; 'Y'
0x180002f70  test    dx, cx
0x180002f73  jnz     short loc_180002FA6
0x180002f75  cmp     [r14+2], r13w
0x180002f7a  jnz     short loc_180002FA6
0x180002f7c  lea     rcx, a1; "1"
0x180002f83  jmp     short loc_180002F93
0x180002f85  cmp     [r14+2], r13w
0x180002f8a  jnz     short loc_180002FA6
0x180002f8c  lea     rcx, a0; "0"
0x180002f93  call    cs:__imp_SysAllocString
0x180002f9a  nop     dword ptr [rax+rax+00h]
0x180002f9f  mov     [rsi+8], rax
0x180002fa3  mov     r12d, ebp
0x180002fa6  movzx   ecx, word ptr [r14]
0x180002faa  call    cs:__imp__o_iswdigit
0x180002fb1  nop     dword ptr [rax+rax+00h]
0x180002fb6  test    eax, eax
0x180002fb8  jnz     short loc_180002FD5
0x180002fba  movzx   eax, word ptr [r14]
0x180002fbe  mov     ecx, 0FFFDh
0x180002fc3  sub     ax, 2Bh ; '+'
0x180002fc7  test    cx, ax
0x180002fca  jz      short loc_180002FD5
0x180002fcc  test    r12d, r12d
0x180002fcf  jz      loc_18000313B
0x180002fd5  mov     edi, 3
0x180002fda  test    r12d, r12d
0x180002fdd  jz      loc_18000317D
0x180002fe3  jmp     loc_180003190
0x180002fe8  lea     rdx, [rsi+8]; jumptable 0000000180002EFC case 6
0x180002fec  mov     rcx, r14
0x180002fef  call    cs:__imp_?Base64StrToSafeArray@@YAJPEBGPEAPEAUtagSAFEARRAY@@@Z; Base64StrToSafeArray(ushort const *,tagSAFEARRAY * *)
0x180002ff6  nop     dword ptr [rax+rax+00h]
0x180002ffb  mov     ebx, eax
0x180002ffd  test    eax, eax
0x180002fff  js      def_180002EFC; jumptable 0000000180002EFC default case, cases 1,8,10-12
0x180003005  mov     word ptr [rsi], 2011h
0x18000300a  jmp     def_180002EFC; jumptable 0000000180002EFC default case, cases 1,8,10-12
0x18000300f  lea     r8, [rsi+8]; jumptable 0000000180002EFC case 7
0x180003013  mov     edx, 0F000h
0x180003018  mov     rcx, r14
0x18000301b  call    cs:__imp_?MultiStringToSafeArray@@YAJPEBGGPEAPEAUtagSAFEARRAY@@@Z; MultiStringToSafeArray(ushort const *,ushort,tagSAFEARRAY * *)
0x180003022  nop     dword ptr [rax+rax+00h]
0x180003027  mov     ebx, eax
0x180003029  test    eax, eax
0x18000302b  js      def_180002EFC; jumptable 0000000180002EFC default case, cases 1,8,10-12
0x180003031  mov     word ptr [rsi], 2008h
0x180003036  jmp     def_180002EFC; jumptable 0000000180002EFC default case, cases 1,8,10-12
0x18000303b  mov     r12d, 4; jumptable 0000000180002EFC case 2
0x180003041  lea     rcx, ?gc_szNaN@@3QBGB; "NaN"
0x180003048  mov     rdx, r14
0x18000304b  mov     [rsi], r12w
0x18000304f  mov     edi, r13d
0x180003052  call    cs:__imp_?InvStrCmpIW@@YAHPEBG0@Z; InvStrCmpIW(ushort const *,ushort const *)
0x180003059  nop     dword ptr [rax+rax+00h]
0x18000305e  test    eax, eax
0x180003060  jnz     short loc_180003074
0x180003062  lea     rdx, [rsi+8]; float *
0x180003066  mov     ecx, 2; unsigned int
0x18000306b  call    ?SetSpecialFloatValue@@YAJKPEAM@Z; SetSpecialFloatValue(ulong,float *)
0x180003070  mov     ebx, eax
0x180003072  jmp     short loc_1800030D7
0x180003074  mov     rdx, r14
0x180003077  lea     rcx, ?gc_szPosInf@@3QBGB; "INF"
0x18000307e  call    cs:__imp_?InvStrCmpIW@@YAHPEBG0@Z; InvStrCmpIW(ushort const *,ushort const *)
0x180003085  nop     dword ptr [rax+rax+00h]
0x18000308a  test    eax, eax
0x18000308c  jnz     short loc_1800030A0
0x18000308e  lea     rdx, [rsi+8]; float *
0x180003092  mov     ecx, 200h; unsigned int
0x180003097  call    ?SetSpecialFloatValue@@YAJKPEAM@Z; SetSpecialFloatValue(ulong,float *)
0x18000309c  mov     ebx, eax
0x18000309e  jmp     short loc_1800030D7
0x1800030a0  mov     rdx, r14
0x1800030a3  lea     rcx, ?gc_szNegInf@@3QBGB; "-INF"
0x1800030aa  call    cs:__imp_?InvStrCmpIW@@YAHPEBG0@Z; InvStrCmpIW(ushort const *,ushort const *)
0x1800030b1  nop     dword ptr [rax+rax+00h]
0x1800030b6  test    eax, eax
0x1800030b8  jnz     short loc_1800030CA
0x1800030ba  lea     rdx, [rsi+8]; float *
0x1800030be  mov     ecx, r12d; unsigned int
0x1800030c1  call    ?SetSpecialFloatValue@@YAJKPEAM@Z; SetSpecialFloatValue(ulong,float *)
0x1800030c6  mov     ebx, eax
0x1800030c8  jmp     short loc_1800030D7
0x1800030ca  movzx   edi, r12w
0x1800030ce  mov     [rsi], r13w
0x1800030d2  mov     ebp, 1
0x1800030d7  test    ebx, ebx
0x1800030d9  js      def_180002EFC; jumptable 0000000180002EFC default case, cases 1,8,10-12
0x1800030df  cmp     r13w, di
0x1800030e3  jnz     loc_18000317D
0x1800030e9  jmp     def_180002EFC; jumptable 0000000180002EFC default case, cases 1,8,10-12
0x1800030ee  mov     rcx, rsi; jumptable 0000000180002EFC case 9
0x1800030f1  call    cs:__imp_VariantClear
0x1800030f8  nop     dword ptr [rax+rax+00h]
0x1800030fd  mov     word ptr [rsi], 1
0x180003102  jmp     def_180002EFC; jumptable 0000000180002EFC default case, cases 1,8,10-12
0x180003107  mov     edx, 10h; jumptable 0000000180002EFC case 3
0x18000310c  lea     r9, [rsp+98h+var_64]; jumptable 0000000180002EFC case 4
0x180003111  mov     rcx, r14
0x180003114  lea     r8, [rsp+98h+SystemTime]
0x180003119  call    cs:__imp_ISO8601StringToSystemTime
0x180003120  nop     dword ptr [rax+rax+00h]
0x180003125  mov     ebx, eax
0x180003127  test    eax, eax
0x180003129  js      def_180002EFC; jumptable 0000000180002EFC default case, cases 1,8,10-12
0x18000312f  test    byte ptr [rsp+98h+var_64], 80h
0x180003134  jz      short loc_180003157
0x180003136  cmp     edi, 3
0x180003139  jnz     short loc_180003145
0x18000313b  mov     ebx, 80070057h
0x180003140  jmp     def_180002EFC; jumptable 0000000180002EFC default case, cases 1,8,10-12
0x180003145  mov     ebp, 1
0x18000314a  mov     dword ptr [rsp+98h+SystemTime.wYear], 106D9h
0x180003152  mov     [rsp+98h+SystemTime.wDay], bp
0x180003157  lea     rdx, [rsi+8]; pvtime
0x18000315b  lea     rcx, [rsp+98h+SystemTime]; lpSystemTime
0x180003160  call    cs:__imp_SystemTimeToVariantTime
0x180003167  nop     dword ptr [rax+rax+00h]
0x18000316c  mov     ebx, eax
0x18000316e  test    eax, eax
0x180003170  js      short def_180002EFC; jumptable 0000000180002EFC default case, cases 1,8,10-12
0x180003172  mov     word ptr [rsi], 7
0x180003177  jmp     short def_180002EFC; jumptable 0000000180002EFC default case, cases 1,8,10-12
0x180003179  movzx   edi, r15w; jumptable 0000000180002EFC case 13
0x18000317d  mov     rcx, r14; psz
0x180003180  call    cs:__imp_SysAllocString
0x180003187  nop     dword ptr [rax+rax+00h]
0x18000318c  mov     [rsi+8], rax
0x180003190  cmp     [rsi+8], r13
0x180003194  jnz     short loc_18000319D
0x180003196  mov     ebx, 8007000Eh
0x18000319b  jmp     short def_180002EFC; jumptable 0000000180002EFC default case, cases 1,8,10-12
0x18000319d  mov     [rsi], r15w
0x1800031a1  mov     rdx, rsi; pvarSrc
0x1800031a4  mov     rcx, rsi; pvargDest
0x1800031a7  test    ebp, ebp
0x1800031a9  jz      short loc_1800031C7
0x1800031ab  xor     r9d, r9d; wFlags
0x1800031ae  mov     [rsp+98h+vt], di; vt
0x1800031b3  mov     r8d, 7Fh; lcid
0x1800031b9  call    cs:__imp_VariantChangeTypeEx
0x1800031c0  nop     dword ptr [rax+rax+00h]
0x1800031c5  jmp     short loc_1800031DA
0x1800031c7  xor     r8d, r8d; wFlags
0x1800031ca  movzx   r9d, di; vt
0x1800031ce  call    cs:__imp_VariantChangeType
0x1800031d5  nop     dword ptr [rax+rax+00h]
0x1800031da  mov     ebx, eax
0x1800031dc  mov     r12, [rsp+98h+var_30]; jumptable 0000000180002EFC default case, cases 1,8,10-12
0x1800031e1  mov     rbp, [rsp+98h+arg_8]
0x1800031e9  mov     r15, [rsp+98h+var_38]
0x1800031ee  mov     rcx, [rsp+98h+hMem]; hMem
0x1800031f3  call    cs:__imp_LocalFree
0x1800031fa  nop     dword ptr [rax+rax+00h]
0x1800031ff  mov     eax, ebx
0x180003201  mov     rcx, [rsp+98h+var_40]
0x180003206  xor     rcx, rsp; StackCookie
0x180003209  call    __security_check_cookie
0x18000320e  add     rsp, 70h
0x180003212  pop     r14
0x180003214  pop     r13
0x180003216  pop     rdi
0x180003217  pop     rsi
0x180003218  pop     rbx
0x180003219  retn
```
