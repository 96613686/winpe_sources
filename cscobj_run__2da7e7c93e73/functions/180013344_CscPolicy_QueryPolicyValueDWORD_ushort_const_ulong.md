# CscPolicy_QueryPolicyValueDWORD(ushort const *,ulong *)

- ea: `0x180013344`
- end: `0x18001357b`
- name: `?CscPolicy_QueryPolicyValueDWORD@@YAJPEBGPEAK@Z`
- size: `567`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180012fc4`

## callees

- `0x18000f5cc`
- `0x180013344`
- `0x180014068`
- `0x1800140c8`
- `0x180014418`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013387`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013387`
- `OLEAUT32!__imp_VariantInit` at `0x1800133e2`
- `OLEAUT32!__imp_VariantInit` at `0x1800133e2`
- `OLEAUT32!__imp_VariantClear` at `0x1800134d8`
- `OLEAUT32!__imp_VariantClear` at `0x1800134d8`

## string_xrefs

- `0x18001339b`: `EncryptCache`

## pseudocode

```c
__int64 __fastcall CscPolicy_QueryPolicyValueDWORD(const unsigned __int16 *a1, unsigned int *a2)
{
  HRESULT v3; // ebx
  VARIANTARG pvarg; // [rsp+30h] [rbp-20h] BYREF
  const unsigned __int16 *v6; // [rsp+70h] [rbp+20h] BYREF
  __int64 v7; // [rsp+78h] [rbp+28h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp+30h] BYREF

  v6 = a1;
  *a2 = 0;
  ppv = 0;
  v3 = CoCreateInstance(&CLSID_OfflineFilesCache, 0, 1u, &IID_IOfflineFilesCache, &ppv);
  if ( v3 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        16,
        WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids,
        (unsigned int)v3);
  }
  else
  {
    v7 = 0;
    v3 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)ppv + 136LL))(
           ppv,
           L"EncryptCache",
           &v7);
    if ( v3 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        WPP_SF_SD(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          15,
          (unsigned int)WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids,
          (unsigned int)L"EncryptCache",
          v3);
    }
    else
    {
      LODWORD(v6) = 0;
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      v3 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *, const unsigned __int16 **))(*(_QWORD *)v7 + 88LL))(
             v7,
             &pvarg,
             &v6);
      if ( v3 < 0 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
          WPP_SF_SD(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            14,
            (unsigned int)WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids,
            (unsigned int)L"EncryptCache",
            v3);
      }
      else if ( (_DWORD)v6 )
      {
        if ( pvarg.vt == 19 )
        {
          v3 = 0;
          *a2 = pvarg.cyVal.Lo;
        }
        else
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
            WPP_SF_Sdd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, 19, (unsigned int)L"EncryptCache", 19, pvarg.vt);
          v3 = -2147352571;
        }
      }
      else
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(char *)(WPP_GLOBAL_Control + 28LL) < 0 )
          WPP_SF_S(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            12,
            WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids,
            L"EncryptCache");
        v3 = -2147024894;
      }
      VariantClear(&pvarg);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180013344  mov     [rsp-18h+arg_18], rbx
0x180013349  mov     [rsp-18h+arg_0], rcx
0x18001334e  push    rbp
0x18001334f  push    rdi
0x180013350  push    r14
0x180013352  mov     rbp, rsp
0x180013355  sub     rsp, 50h
0x180013359  mov     rdi, rdx
0x18001335c  mov     dword ptr [rdx], 0
0x180013362  xor     edx, edx; pUnkOuter
0x180013364  mov     [rbp+arg_10], 0
0x18001336c  lea     rax, [rbp+arg_10]
0x180013370  lea     r9, IID_IOfflineFilesCache; riid
0x180013377  mov     [rsp+50h+ppv], rax; ppv
0x18001337c  lea     rcx, CLSID_OfflineFilesCache; rclsid
0x180013383  lea     r8d, [rdx+1]; dwClsContext
0x180013387  call    cs:__imp_CoCreateInstance
0x18001338d  mov     ebx, eax
0x18001338f  test    eax, eax
0x180013391  js      loc_180013537
0x180013397  mov     rcx, [rbp+arg_10]
0x18001339b  lea     r14, aEncryptcache; "EncryptCache"
0x1800133a2  mov     [rbp+arg_8], 0
0x1800133aa  lea     r8, [rbp+arg_8]
0x1800133ae  mov     rdx, r14
0x1800133b1  mov     rax, [rcx]
0x1800133b4  mov     rax, [rax+88h]
0x1800133bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133c0  mov     ebx, eax
0x1800133c2  test    eax, eax
0x1800133c4  js      loc_1800134F0
0x1800133ca  xorps   xmm0, xmm0
0x1800133cd  mov     dword ptr [rbp+arg_0], 0
0x1800133d4  xor     eax, eax
0x1800133d6  lea     rcx, [rbp+pvarg]; pvarg
0x1800133da  movups  xmmword ptr [rbp+pvarg], xmm0
0x1800133de  mov     qword ptr [rbp+pvarg+10h], rax
0x1800133e2  call    cs:__imp_VariantInit
0x1800133e8  mov     rcx, [rbp+arg_8]
0x1800133ec  lea     r8, [rbp+arg_0]
0x1800133f0  lea     rdx, [rbp+pvarg]
0x1800133f4  mov     rax, [rcx]
0x1800133f7  mov     rax, [rax+58h]
0x1800133fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013400  mov     ebx, eax
0x180013402  test    eax, eax
0x180013404  js      loc_18001349F
0x18001340a  cmp     dword ptr [rbp+arg_0], 0
0x18001340e  jnz     short loc_18001344B
0x180013410  mov     rcx, cs:WPP_GLOBAL_Control
0x180013417  lea     rax, WPP_GLOBAL_Control
0x18001341e  cmp     rcx, rax
0x180013421  jz      short loc_180013441
0x180013423  test    byte ptr [rcx+1Ch], 80h
0x180013427  jz      short loc_180013441
0x180013429  mov     rcx, [rcx+10h]
0x18001342d  lea     r8, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids
0x180013434  mov     edx, 0Ch
0x180013439  mov     r9, r14
0x18001343c  call    WPP_SF_S
0x180013441  mov     ebx, 80070002h
0x180013446  jmp     loc_1800134D4
0x18001344b  mov     r8d, 13h
0x180013451  cmp     r8w, word ptr [rbp+pvarg]
0x180013456  jnz     short loc_180013461
0x180013458  mov     eax, dword ptr [rbp+pvarg+8]
0x18001345b  xor     ebx, ebx
0x18001345d  mov     [rdi], eax
0x18001345f  jmp     short loc_1800134D4
0x180013461  mov     rcx, cs:WPP_GLOBAL_Control
0x180013468  lea     rax, WPP_GLOBAL_Control
0x18001346f  cmp     rcx, rax
0x180013472  jz      short loc_180013498
0x180013474  test    byte ptr [rcx+1Ch], 2
0x180013478  jz      short loc_180013498
0x18001347a  movzx   eax, word ptr [rbp+pvarg]
0x18001347e  mov     edx, 0Dh
0x180013483  mov     rcx, [rcx+10h]
0x180013487  mov     r9, r14
0x18001348a  mov     [rsp+50h+var_28], eax
0x18001348e  mov     dword ptr [rsp+50h+ppv], r8d
0x180013493  call    WPP_SF_Sdd
0x180013498  mov     ebx, 80020005h
0x18001349d  jmp     short loc_1800134D4
0x18001349f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800134a6  lea     rax, WPP_GLOBAL_Control
0x1800134ad  cmp     rcx, rax
0x1800134b0  jz      short loc_1800134D4
0x1800134b2  test    byte ptr [rcx+1Ch], 2
0x1800134b6  jz      short loc_1800134D4
0x1800134b8  mov     rcx, [rcx+10h]
0x1800134bc  lea     r8, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids
0x1800134c3  mov     edx, 0Eh
0x1800134c8  mov     dword ptr [rsp+50h+ppv], ebx
0x1800134cc  mov     r9, r14
0x1800134cf  call    WPP_SF_SD
0x1800134d4  lea     rcx, [rbp+pvarg]; pvarg
0x1800134d8  call    cs:__imp_VariantClear
0x1800134de  mov     rcx, [rbp+arg_8]
0x1800134e2  mov     rax, [rcx]
0x1800134e5  mov     rax, [rax+10h]
0x1800134e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134ee  jmp     short loc_180013525
0x1800134f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800134f7  lea     rax, WPP_GLOBAL_Control
0x1800134fe  cmp     rcx, rax
0x180013501  jz      short loc_180013525
0x180013503  test    byte ptr [rcx+1Ch], 2
0x180013507  jz      short loc_180013525
0x180013509  mov     rcx, [rcx+10h]
0x18001350d  lea     r8, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids
0x180013514  mov     edx, 0Fh
0x180013519  mov     dword ptr [rsp+50h+ppv], ebx
0x18001351d  mov     r9, r14
0x180013520  call    WPP_SF_SD
0x180013525  mov     rcx, [rbp+arg_10]
0x180013529  mov     rax, [rcx]
0x18001352c  mov     rax, [rax+10h]
0x180013530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013535  jmp     short loc_180013568
0x180013537  mov     rcx, cs:WPP_GLOBAL_Control
0x18001353e  lea     rax, WPP_GLOBAL_Control
0x180013545  cmp     rcx, rax
0x180013548  jz      short loc_180013568
0x18001354a  test    byte ptr [rcx+1Ch], 2
0x18001354e  jz      short loc_180013568
0x180013550  mov     rcx, [rcx+10h]
0x180013554  lea     r8, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids
0x18001355b  mov     edx, 10h
0x180013560  mov     r9d, ebx
0x180013563  call    WPP_SF_d
0x180013568  mov     eax, ebx
0x18001356a  mov     rbx, [rsp+50h+arg_18]
0x180013572  add     rsp, 50h
0x180013576  pop     r14
0x180013578  pop     rdi
0x180013579  pop     rbp
0x18001357a  retn
```
