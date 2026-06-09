# ConformVariantToData(tagVARIANT *,ConfigDataType,ulong,ushort * *)

- ea: `0x180003f70`
- end: `0x180004218`
- name: `?ConformVariantToData@@YAJPEAUtagVARIANT@@W4ConfigDataType@@KPEAPEAG@Z`
- size: `680`
- prototype: `__int64 __fastcall(VARIANTARG *, int, unsigned int, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000c600`
- `0x18000e020`

## callees

- `0x180003f70`
- `0x180014330`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__fpclass` at `0x180004129`
- `api-ms-win-crt-private-l1-1-0!_o__fpclass` at `0x180004129`
- `OLEAUT32!__imp_VariantChangeType` at `0x180003fe6`
- `OLEAUT32!__imp_VariantChangeType` at `0x180003fe6`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x180004166`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x180004166`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x1800040a5`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x1800040a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800041f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800041f1`
- `DMOleAutUtils!SafeArrayToBase64Str` at `0x18000406d`
- `DMOleAutUtils!SafeArrayToBase64Str` at `0x18000406d`
- `DMOleAutUtils!SafeArrayToMultiString` at `0x18000402d`
- `DMOleAutUtils!SafeArrayToMultiString` at `0x18000402d`
- `DMCmnUtils!CopyString` at `0x1800041d7`
- `DMCmnUtils!CopyString` at `0x1800041d7`
- `dmiso8601utils!SystemTimeToISO8601String` at `0x1800040f3`
- `dmiso8601utils!SystemTimeToISO8601String` at `0x1800040f3`

## pseudocode

```c
__int64 __fastcall ConformVariantToData(VARIANTARG *a1, int a2, unsigned int a3, unsigned __int16 **a4)
{
  HRESULT v8; // ebx
  const unsigned __int16 *bstrVal; // rcx
  struct tagSAFEARRAY *v10; // rcx
  struct tagSAFEARRAY *parray; // rcx
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  SHORT iVal; // cx
  HLOCAL hMem; // [rsp+30h] [rbp-48h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+38h] [rbp-40h] BYREF

  hMem = 0;
  *a4 = 0;
  SystemTime = 0;
  switch ( a2 )
  {
    case 5:
      if ( a1->vt == 11 )
      {
        iVal = a1->iVal;
        if ( iVal == -1 )
        {
          bstrVal = L"true";
          goto LABEL_44;
        }
        if ( !iVal )
        {
          bstrVal = L"false";
          goto LABEL_44;
        }
      }
      goto LABEL_45;
    case 2:
      if ( a1->vt == 4 )
      {
        v12 = _fpclass(a1->fltVal) - 1;
        if ( !v12 || (v13 = v12 - 1) == 0 )
        {
          bstrVal = L"NaN";
          goto LABEL_44;
        }
        v14 = v13 - 2;
        if ( !v14 )
        {
          bstrVal = L"-INF";
          goto LABEL_44;
        }
        v15 = v14 - 28;
        if ( !v15 )
        {
          bstrVal = L"-0";
          goto LABEL_44;
        }
        if ( v15 == 480 )
        {
          bstrVal = L"INF";
          goto LABEL_44;
        }
        v8 = VariantChangeTypeEx(a1, a1, 0x7Fu, 0, 8u);
        if ( v8 >= 0 )
        {
          bstrVal = a1->bstrVal;
          goto LABEL_44;
        }
        goto LABEL_46;
      }
      goto LABEL_45;
    case 3:
    case 4:
      if ( a1->vt == 7 )
      {
        v8 = VariantTimeToSystemTime(a1->dblVal, &SystemTime);
        if ( v8 >= 0 )
        {
          if ( a2 == 3 )
          {
            a3 |= 4u;
          }
          else if ( SystemTime.wYear == 1753 && SystemTime.wMonth == 1 && SystemTime.wDay == 1 )
          {
            a3 |= 8u;
          }
          v8 = SystemTimeToISO8601String(&SystemTime, a3, &hMem);
          if ( v8 >= 0 )
          {
            bstrVal = (const unsigned __int16 *)hMem;
            goto LABEL_44;
          }
        }
        goto LABEL_46;
      }
      goto LABEL_45;
    case 6:
      if ( a1->vt == 8209 )
      {
        parray = a1->parray;
        if ( parray )
        {
          v8 = SafeArrayToBase64Str(parray, (unsigned __int16 **)&hMem);
          if ( v8 >= 0 )
          {
            bstrVal = (const unsigned __int16 *)hMem;
            goto LABEL_44;
          }
          goto LABEL_46;
        }
      }
      goto LABEL_45;
  }
  if ( a2 != 7 )
  {
    v8 = VariantChangeType(a1, a1, 0, 8u);
    if ( v8 >= 0 )
    {
      bstrVal = a1->bstrVal;
LABEL_44:
      v8 = CopyString(bstrVal, 0xFFFFFFFF, a4);
      goto LABEL_46;
    }
    goto LABEL_46;
  }
  if ( a1->vt != 8200 || (v10 = a1->parray) == 0 )
  {
LABEL_45:
    v8 = -2147418113;
    goto LABEL_46;
  }
  v8 = SafeArrayToMultiString(v10, 0xF000u, (unsigned __int16 **)&hMem, 0);
  if ( v8 >= 0 )
  {
    bstrVal = (const unsigned __int16 *)hMem;
    goto LABEL_44;
  }
LABEL_46:
  LocalFree(hMem);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180003f70  push    rbx
0x180003f72  push    rbp
0x180003f73  push    rsi
0x180003f74  push    rdi
0x180003f75  push    r14
0x180003f77  sub     rsp, 50h
0x180003f7b  mov     rax, cs:__security_cookie
0x180003f82  xor     rax, rsp
0x180003f85  mov     [rsp+78h+var_30], rax
0x180003f8a  mov     esi, edx
0x180003f8c  xorps   xmm0, xmm0
0x180003f8f  xor     edx, edx
0x180003f91  mov     r14, r9
0x180003f94  mov     [rsp+78h+hMem], rdx
0x180003f99  mov     ebp, r8d
0x180003f9c  mov     [r9], rdx
0x180003f9f  mov     rdi, rcx
0x180003fa2  movups  xmmword ptr [rsp+78h+SystemTime.wYear], xmm0
0x180003fa7  cmp     esi, 5
0x180003faa  jz      loc_1800041A2
0x180003fb0  mov     ecx, esi
0x180003fb2  sub     ecx, 2
0x180003fb5  jz      loc_180004113
0x180003fbb  sub     ecx, 1
0x180003fbe  jz      loc_18000408D
0x180003fc4  sub     ecx, 1
0x180003fc7  jz      loc_18000408D
0x180003fcd  sub     ecx, 2
0x180003fd0  jz      short loc_18000404D
0x180003fd2  cmp     ecx, 1
0x180003fd5  jz      short loc_180004005
0x180003fd7  mov     r9d, 8; vt
0x180003fdd  xor     r8d, r8d; wFlags
0x180003fe0  mov     rdx, rdi; pvarSrc
0x180003fe3  mov     rcx, rdi; pvargDest
0x180003fe6  call    cs:__imp_VariantChangeType
0x180003fed  nop     dword ptr [rax+rax+00h]
0x180003ff2  mov     ebx, eax
0x180003ff4  test    eax, eax
0x180003ff6  js      loc_1800041EC
0x180003ffc  mov     rcx, [rdi+8]
0x180004000  jmp     loc_1800041CF
0x180004005  mov     eax, 2008h
0x18000400a  cmp     ax, [rdi]
0x18000400d  jnz     loc_1800041E7
0x180004013  mov     rcx, [rdi+8]
0x180004017  test    rcx, rcx
0x18000401a  jz      loc_1800041E7
0x180004020  mov     edx, 0F000h
0x180004025  lea     r8, [rsp+78h+hMem]
0x18000402a  xor     r9d, r9d
0x18000402d  call    cs:__imp_?SafeArrayToMultiString@@YAJPEAUtagSAFEARRAY@@GPEAPEAGPEA_K@Z; SafeArrayToMultiString(tagSAFEARRAY *,ushort,ushort * *,unsigned __int64 *)
0x180004034  nop     dword ptr [rax+rax+00h]
0x180004039  mov     ebx, eax
0x18000403b  test    eax, eax
0x18000403d  js      loc_1800041EC
0x180004043  mov     rcx, [rsp+78h+hMem]
0x180004048  jmp     loc_1800041CF
0x18000404d  mov     eax, 2011h
0x180004052  cmp     ax, [rdi]
0x180004055  jnz     loc_1800041E7
0x18000405b  mov     rcx, [rdi+8]
0x18000405f  test    rcx, rcx
0x180004062  jz      loc_1800041E7
0x180004068  lea     rdx, [rsp+78h+hMem]
0x18000406d  call    cs:__imp_?SafeArrayToBase64Str@@YAJPEAUtagSAFEARRAY@@PEAPEAG@Z; SafeArrayToBase64Str(tagSAFEARRAY *,ushort * *)
0x180004074  nop     dword ptr [rax+rax+00h]
0x180004079  mov     ebx, eax
0x18000407b  test    eax, eax
0x18000407d  js      loc_1800041EC
0x180004083  mov     rcx, [rsp+78h+hMem]
0x180004088  jmp     loc_1800041CF
0x18000408d  mov     eax, 7
0x180004092  cmp     ax, [rdi]
0x180004095  jnz     loc_1800041E7
0x18000409b  movsd   xmm0, qword ptr [rdi+8]; vtime
0x1800040a0  lea     rdx, [rsp+78h+SystemTime]; lpSystemTime
0x1800040a5  call    cs:__imp_VariantTimeToSystemTime
0x1800040ac  nop     dword ptr [rax+rax+00h]
0x1800040b1  mov     ebx, eax
0x1800040b3  test    eax, eax
0x1800040b5  js      loc_1800041EC
0x1800040bb  cmp     esi, 3
0x1800040be  jnz     short loc_1800040C5
0x1800040c0  or      ebp, 4
0x1800040c3  jmp     short loc_1800040E7
0x1800040c5  mov     eax, 6D9h
0x1800040ca  cmp     ax, [rsp+78h+SystemTime.wYear]
0x1800040cf  jnz     short loc_1800040E7
0x1800040d1  mov     eax, 1
0x1800040d6  cmp     ax, [rsp+78h+SystemTime.wMonth]
0x1800040db  jnz     short loc_1800040E7
0x1800040dd  cmp     ax, [rsp+78h+SystemTime.wDay]
0x1800040e2  jnz     short loc_1800040E7
0x1800040e4  or      ebp, 8
0x1800040e7  lea     r8, [rsp+78h+hMem]
0x1800040ec  mov     edx, ebp
0x1800040ee  lea     rcx, [rsp+78h+SystemTime]
0x1800040f3  call    cs:__imp_SystemTimeToISO8601String
0x1800040fa  nop     dword ptr [rax+rax+00h]
0x1800040ff  mov     ebx, eax
0x180004101  test    eax, eax
0x180004103  js      loc_1800041EC
0x180004109  mov     rcx, [rsp+78h+hMem]
0x18000410e  jmp     loc_1800041CF
0x180004113  mov     eax, 4
0x180004118  cmp     ax, [rdi]
0x18000411b  jnz     loc_1800041E7
0x180004121  movss   xmm0, dword ptr [rdi+8]
0x180004126  cvtps2pd xmm0, xmm0; X
0x180004129  call    cs:__imp__fpclass
0x180004130  nop     dword ptr [rax+rax+00h]
0x180004135  sub     eax, 1
0x180004138  jz      short loc_180004199
0x18000413a  sub     eax, 1
0x18000413d  jz      short loc_180004199
0x18000413f  sub     eax, 2
0x180004142  jz      short loc_180004190
0x180004144  sub     eax, 1Ch
0x180004147  jz      short loc_180004187
0x180004149  cmp     eax, 1E0h
0x18000414e  jz      short loc_18000417E
0x180004150  xor     r9d, r9d; wFlags
0x180004153  mov     [rsp+78h+vt], 8; vt
0x18000415a  mov     r8d, 7Fh; lcid
0x180004160  mov     rdx, rdi; pvarSrc
0x180004163  mov     rcx, rdi; pvargDest
0x180004166  call    cs:__imp_VariantChangeTypeEx
0x18000416d  nop     dword ptr [rax+rax+00h]
0x180004172  mov     ebx, eax
0x180004174  test    eax, eax
0x180004176  js      short loc_1800041EC
0x180004178  mov     rcx, [rdi+8]
0x18000417c  jmp     short loc_1800041CF
0x18000417e  lea     rcx, ?gc_szPosInf@@3QBGB; "INF"
0x180004185  jmp     short loc_1800041CF
0x180004187  lea     rcx, ?gc_szNegZero@@3QBGB; "-0"
0x18000418e  jmp     short loc_1800041CF
0x180004190  lea     rcx, ?gc_szNegInf@@3QBGB; "-INF"
0x180004197  jmp     short loc_1800041CF
0x180004199  lea     rcx, ?gc_szNaN@@3QBGB; "NaN"
0x1800041a0  jmp     short loc_1800041CF
0x1800041a2  mov     eax, 0Bh
0x1800041a7  cmp     ax, [rcx]
0x1800041aa  jnz     short loc_1800041E7
0x1800041ac  movzx   ecx, word ptr [rcx+8]
0x1800041b0  mov     eax, 0FFFFFFFFh
0x1800041b5  cmp     ax, cx
0x1800041b8  jnz     short loc_1800041C3
0x1800041ba  lea     rcx, ?gc_szTrueVal@@3QBGB; "true"
0x1800041c1  jmp     short loc_1800041CF
0x1800041c3  cmp     dx, cx
0x1800041c6  jnz     short loc_1800041E7
0x1800041c8  lea     rcx, ?gc_szFalseVal@@3QBGB; "false"
0x1800041cf  mov     r8, r14
0x1800041d2  mov     edx, 0FFFFFFFFh
0x1800041d7  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x1800041de  nop     dword ptr [rax+rax+00h]
0x1800041e3  mov     ebx, eax
0x1800041e5  jmp     short loc_1800041EC
0x1800041e7  mov     ebx, 8000FFFFh
0x1800041ec  mov     rcx, [rsp+78h+hMem]; hMem
0x1800041f1  call    cs:__imp_LocalFree
0x1800041f8  nop     dword ptr [rax+rax+00h]
0x1800041fd  mov     eax, ebx
0x1800041ff  mov     rcx, [rsp+78h+var_30]
0x180004204  xor     rcx, rsp; StackCookie
0x180004207  call    __security_check_cookie
0x18000420c  add     rsp, 50h
0x180004210  pop     r14
0x180004212  pop     rdi
0x180004213  pop     rsi
0x180004214  pop     rbp
0x180004215  pop     rbx
0x180004216  retn
```
