# CWapDPUHelper::ConvertVariantToString(ConfigDataType,tagVARIANT,ushort * *)

- ea: `0x180026290`
- end: `0x180026478`
- name: `?ConvertVariantToString@CWapDPUHelper@@UEAAJW4ConfigDataType@@UtagVARIANT@@PEAPEAG@Z`
- size: `488`
- prototype: `__int64 __fastcall(__int64, int, __int64, LONGLONG *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180014330`
- `0x180026290`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180026333`
- `OLEAUT32!__imp_SysAllocString` at `0x180026333`
- `OLEAUT32!__imp_SysFreeString` at `0x1800263c1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800263c1`
- `OLEAUT32!__imp_VariantInit` at `0x1800262eb`
- `OLEAUT32!__imp_VariantInit` at `0x1800262eb`
- `OLEAUT32!__imp_VariantClear` at `0x1800263e1`
- `OLEAUT32!__imp_VariantClear` at `0x1800263e1`
- `OLEAUT32!__imp_VariantChangeType` at `0x18002639e`
- `OLEAUT32!__imp_VariantChangeType` at `0x18002639e`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x180026424`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x180026424`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800263d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800263d1`
- `DMOleAutUtils!SafeArrayToBase64Str` at `0x180026319`
- `DMOleAutUtils!SafeArrayToBase64Str` at `0x180026319`
- `DMOleAutUtils!SafeArrayToMultiString` at `0x18002636f`
- `DMOleAutUtils!SafeArrayToMultiString` at `0x18002636f`
- `dmiso8601utils!SystemTimeToISO8601String` at `0x180026467`
- `dmiso8601utils!SystemTimeToISO8601String` at `0x180026467`

## pseudocode

```c
__int64 __fastcall CWapDPUHelper::ConvertVariantToString(__int64 a1, int a2, __int64 a3, LONGLONG *a4)
{
  IRecordInfo *v4; // xmm1_8
  HRESULT v7; // ebx
  int v8; // eax
  LONGLONG llVal; // rax
  __int64 v11; // rdx
  OLECHAR *psz; // [rsp+20h] [rbp-50h] BYREF
  VARIANTARG pvarSrc; // [rsp+28h] [rbp-48h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-30h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+58h] [rbp-18h] BYREF

  v4 = *(IRecordInfo **)(a3 + 16);
  *(_OWORD *)&pvarSrc.vt = *(_OWORD *)a3;
  psz = 0;
  pvarSrc.pRecInfo = v4;
  SystemTime = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( a2 != 6 )
  {
    if ( a2 == 7 )
    {
      if ( pvarSrc.vt != 8200 )
        goto LABEL_3;
      v8 = SafeArrayToMultiString(pvarSrc.parray, 0xF000u, &psz, 0);
    }
    else
    {
      if ( (unsigned int)(a2 - 3) > 1 )
      {
        v7 = VariantChangeType(&pvarg, &pvarSrc, 0, 8u);
        if ( v7 < 0 )
          goto LABEL_15;
        llVal = pvarg.llVal;
        pvarg.llVal = 0;
        goto LABEL_14;
      }
      if ( pvarSrc.vt != 7 )
        goto LABEL_3;
      v7 = VariantTimeToSystemTime(pvarSrc.dblVal, &SystemTime);
      if ( v7 < 0 )
        goto LABEL_15;
      if ( a2 == 3 )
      {
        v11 = 4;
      }
      else
      {
        v11 = 0;
        if ( SystemTime.wYear == 1753 && SystemTime.wMonth == 1 && SystemTime.wDay == 1 )
          v11 = 8;
      }
      v8 = SystemTimeToISO8601String(&SystemTime, v11, &psz);
    }
LABEL_5:
    v7 = v8;
    if ( v8 < 0 )
      goto LABEL_15;
    llVal = (LONGLONG)SysAllocString(psz);
    if ( !llVal )
    {
      v7 = -2147024882;
      goto LABEL_15;
    }
LABEL_14:
    *a4 = llVal;
    goto LABEL_15;
  }
  if ( pvarSrc.vt == 8209 )
  {
    v8 = SafeArrayToBase64Str(pvarSrc.parray, &psz);
    goto LABEL_5;
  }
LABEL_3:
  v7 = -2147467259;
LABEL_15:
  SysFreeString(0);
  LocalFree(psz);
  VariantClear(&pvarg);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180026290  mov     [rsp-18h+arg_0], rbx
0x180026295  mov     [rsp-18h+arg_8], rsi
0x18002629a  push    rbp
0x18002629b  push    rdi
0x18002629c  push    r14
0x18002629e  mov     rbp, rsp
0x1800262a1  sub     rsp, 70h
0x1800262a5  mov     rax, cs:__security_cookie
0x1800262ac  xor     rax, rsp
0x1800262af  mov     [rbp+var_8], rax
0x1800262b3  movups  xmm0, xmmword ptr [r8]
0x1800262b7  lea     rcx, [rbp+pvarg]; pvarg
0x1800262bb  xor     eax, eax
0x1800262bd  movsd   xmm1, qword ptr [r8+10h]
0x1800262c3  mov     rsi, r9
0x1800262c6  movups  xmmword ptr [rbp+pvarSrc], xmm0
0x1800262ca  mov     edi, edx
0x1800262cc  mov     [rbp+psz], 0
0x1800262d4  movsd   qword ptr [rbp+pvarSrc+10h], xmm1
0x1800262d9  xorps   xmm0, xmm0
0x1800262dc  xorps   xmm1, xmm1
0x1800262df  mov     qword ptr [rbp+pvarg+10h], rax
0x1800262e3  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x1800262e7  movups  xmmword ptr [rbp+pvarg], xmm1
0x1800262eb  call    cs:__imp_VariantInit
0x1800262f2  nop     dword ptr [rax+rax+00h]
0x1800262f7  cmp     edi, 6
0x1800262fa  jnz     short loc_18002634B
0x1800262fc  mov     eax, 2011h
0x180026301  cmp     word ptr [rbp+pvarSrc], ax
0x180026305  jz      short loc_180026311
0x180026307  mov     ebx, 80004005h
0x18002630c  jmp     loc_1800263BF
0x180026311  mov     rcx, qword ptr [rbp+pvarSrc+8]
0x180026315  lea     rdx, [rbp+psz]
0x180026319  call    cs:__imp_?SafeArrayToBase64Str@@YAJPEAUtagSAFEARRAY@@PEAPEAG@Z; SafeArrayToBase64Str(tagSAFEARRAY *,ushort * *)
0x180026320  nop     dword ptr [rax+rax+00h]
0x180026325  mov     ebx, eax
0x180026327  test    eax, eax
0x180026329  js      loc_1800263BF
0x18002632f  mov     rcx, [rbp+psz]; psz
0x180026333  call    cs:__imp_SysAllocString
0x18002633a  nop     dword ptr [rax+rax+00h]
0x18002633f  test    rax, rax
0x180026342  jnz     short loc_1800263BC
0x180026344  mov     ebx, 8007000Eh
0x180026349  jmp     short loc_1800263BF
0x18002634b  mov     ecx, 7
0x180026350  cmp     edi, ecx
0x180026352  jnz     short loc_18002637D
0x180026354  mov     eax, 2008h
0x180026359  cmp     word ptr [rbp+pvarSrc], ax
0x18002635d  jnz     short loc_180026307
0x18002635f  mov     rcx, qword ptr [rbp+pvarSrc+8]
0x180026363  lea     r8, [rbp+psz]
0x180026367  mov     edx, 0F000h
0x18002636c  xor     r9d, r9d
0x18002636f  call    cs:__imp_?SafeArrayToMultiString@@YAJPEAUtagSAFEARRAY@@GPEAPEAGPEA_K@Z; SafeArrayToMultiString(tagSAFEARRAY *,ushort,ushort * *,unsigned __int64 *)
0x180026376  nop     dword ptr [rax+rax+00h]
0x18002637b  jmp     short loc_180026325
0x18002637d  lea     eax, [rdi-3]
0x180026380  mov     r14d, 1
0x180026386  cmp     eax, r14d
0x180026389  jbe     loc_180026411
0x18002638f  lea     r9d, [r14+7]; vt
0x180026393  xor     r8d, r8d; wFlags
0x180026396  lea     rdx, [rbp+pvarSrc]; pvarSrc
0x18002639a  lea     rcx, [rbp+pvarg]; pvargDest
0x18002639e  call    cs:__imp_VariantChangeType
0x1800263a5  nop     dword ptr [rax+rax+00h]
0x1800263aa  mov     ebx, eax
0x1800263ac  test    eax, eax
0x1800263ae  js      short loc_1800263BF
0x1800263b0  mov     rax, qword ptr [rbp+pvarg+8]
0x1800263b4  mov     qword ptr [rbp+pvarg+8], 0
0x1800263bc  mov     [rsi], rax
0x1800263bf  xor     ecx, ecx; bstrString
0x1800263c1  call    cs:__imp_SysFreeString
0x1800263c8  nop     dword ptr [rax+rax+00h]
0x1800263cd  mov     rcx, [rbp+psz]; hMem
0x1800263d1  call    cs:__imp_LocalFree
0x1800263d8  nop     dword ptr [rax+rax+00h]
0x1800263dd  lea     rcx, [rbp+pvarg]; pvarg
0x1800263e1  call    cs:__imp_VariantClear
0x1800263e8  nop     dword ptr [rax+rax+00h]
0x1800263ed  mov     eax, ebx
0x1800263ef  mov     rcx, [rbp+var_8]
0x1800263f3  xor     rcx, rsp; StackCookie
0x1800263f6  call    __security_check_cookie
0x1800263fb  lea     r11, [rsp+70h+var_s0]
0x180026400  mov     rbx, [r11+20h]
0x180026404  mov     rsi, [r11+28h]
0x180026408  mov     rsp, r11
0x18002640b  pop     r14
0x18002640d  pop     rdi
0x18002640e  pop     rbp
0x18002640f  retn
0x180026411  cmp     cx, word ptr [rbp+pvarSrc]
0x180026415  jnz     loc_180026307
0x18002641b  movsd   xmm0, qword ptr [rbp+pvarSrc+8]; vtime
0x180026420  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x180026424  call    cs:__imp_VariantTimeToSystemTime
0x18002642b  nop     dword ptr [rax+rax+00h]
0x180026430  mov     ebx, eax
0x180026432  test    eax, eax
0x180026434  js      short loc_1800263BF
0x180026436  cmp     edi, 3
0x180026439  jnz     short loc_180026440
0x18002643b  lea     edx, [rdi+1]
0x18002643e  jmp     short loc_18002645F
0x180026440  xor     edx, edx
0x180026442  mov     eax, 6D9h
0x180026447  cmp     ax, [rbp+SystemTime.wYear]
0x18002644b  jnz     short loc_18002645F
0x18002644d  cmp     r14w, [rbp+SystemTime.wMonth]
0x180026452  jnz     short loc_18002645F
0x180026454  cmp     r14w, [rbp+SystemTime.wDay]
0x180026459  lea     eax, [rdx+8]
0x18002645c  cmovz   edx, eax
0x18002645f  lea     r8, [rbp+psz]
0x180026463  lea     rcx, [rbp+SystemTime]
0x180026467  call    cs:__imp_SystemTimeToISO8601String
0x18002646e  nop     dword ptr [rax+rax+00h]
0x180026473  jmp     loc_180026325
```
