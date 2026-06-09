# Microsoft::Resources::WindowsClientProfileBaseHelpers::ReadRegistryStringFromPackage(ushort const *,ushort const *,ushort const *,Microsoft::Resources::StringResult *)

- ea: `0x18005abd0`
- end: `0x18005ae05`
- name: `?ReadRegistryStringFromPackage@WindowsClientProfileBaseHelpers@Resources@Microsoft@@UEAAJPEBG00PEAVStringResult@23@@Z`
- size: `565`
- prototype: `int(Microsoft::Resources::WindowsClientProfileBaseHelpers *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct Microsoft::Resources::StringResult *)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18005aa30`
- `0x18005aad0`
- `0x18005ab50`

## callees

- `0x180028510`
- `0x18002c8d0`
- `0x18005abd0`
- `0x180083978`
- `0x1800862f0`
- `0x180086800`
- `0x18008680c`

## import_xrefs

- `KERNELBASE!PackageFamilyNameFromFullName` at `0x18005ac34`
- `KERNELBASE!PackageFamilyNameFromFullName` at `0x18005ac34`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005ad25`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005ad8d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005ad25`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005ad8d`
- `profapi!__imp_GetAppContainerRegistryHandleFromName` at `0x18005ac58`
- `profapi!__imp_GetAppContainerRegistryHandleFromName` at `0x18005ac58`

## pseudocode

```c
LSTATUS __fastcall Microsoft::Resources::WindowsClientProfileBaseHelpers::ReadRegistryStringFromPackage(
        Microsoft::Resources::WindowsClientProfileBaseHelpers *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct Microsoft::Resources::StringResult *a5)
{
  HKEY *v5; // rsi
  unsigned int v8; // eax
  int AppContainerRegistryHandleFromName; // eax
  signed int v10; // ebx
  LSTATUS result; // eax
  HKEY v12; // rcx
  unsigned __int64 v13; // rax
  void *pvData; // rdi
  LSTATUS ValueW; // eax
  int v16; // eax
  unsigned __int64 v17; // r9
  __int64 v18; // rdx
  unsigned int pdwType; // [rsp+20h] [rbp-108h]
  int pdwTypea; // [rsp+20h] [rbp-108h]
  int pdwTypeb; // [rsp+20h] [rbp-108h]
  DWORD pcbData; // [rsp+40h] [rbp-E8h] BYREF
  UINT32 packageFamilyNameLength[3]; // [rsp+44h] [rbp-E4h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+50h] [rbp-D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v5 = (HKEY *)((char *)this + 8);
  if ( !*((_QWORD *)this + 1) )
  {
    *v5 = 0;
    packageFamilyNameLength[0] = 65;
    v8 = PackageFamilyNameFromFullName(a2, packageFamilyNameLength, packageFamilyName);
    if ( v8 )
    {
      v10 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x96B,
              (unsigned int)"onecoreuap\\base\\mrt\\mrm\\src\\clientprofiles.cpp",
              (const char *)v8,
              pdwType);
      if ( v10 < 0 )
        goto LABEL_9;
    }
    else
    {
      AppContainerRegistryHandleFromName = GetAppContainerRegistryHandleFromName(packageFamilyName, 0, a3, 131097, v5);
      v10 = AppContainerRegistryHandleFromName;
      if ( AppContainerRegistryHandleFromName < 0 )
      {
        if ( AppContainerRegistryHandleFromName != -2147024894 && AppContainerRegistryHandleFromName != -2147024891 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x970,
            (unsigned int)"onecoreuap\\base\\mrt\\mrm\\src\\clientprofiles.cpp",
            (const char *)(unsigned int)AppContainerRegistryHandleFromName,
            pdwTypea);
LABEL_7:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x982,
            (unsigned int)"onecoreuap\\base\\mrt\\mrm\\src\\clientprofiles.cpp",
            (const char *)(unsigned int)v10,
            pdwTypea);
          return v10;
        }
LABEL_9:
        if ( v10 == -2147024894 || v10 == -2147024891 )
          return v10;
        goto LABEL_7;
      }
    }
  }
  v12 = *v5;
  pcbData = 0;
  result = RegGetValueW(v12, 0, a4, 2u, 0, 0, &pcbData);
  if ( !result )
  {
    v13 = 2 * ((unsigned __int64)pcbData >> 1);
    if ( !is_mul_ok((unsigned __int64)pcbData >> 1, 2u) )
      v13 = -1;
    pvData = operator new[](v13, (const struct std::nothrow_t *)&qword_1800DFCD8);
    if ( pvData )
    {
      ValueW = RegGetValueW(*v5, 0, a4, 2u, 0, pvData, &pcbData);
      v10 = ValueW;
      if ( !ValueW )
      {
        v16 = DefStringResult_SetCopy(*(_QWORD *)a5, pvData);
        v10 = v16;
        if ( v16 >= 0 )
        {
          v10 = 0;
LABEL_21:
          operator delete(pvData);
          return v10;
        }
        v17 = (unsigned int)v16;
        v18 = 2449;
LABEL_23:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"onecoreuap\\base\\mrt\\mrm\\src\\clientprofiles.cpp",
          (const char *)v17,
          pdwTypeb);
        goto LABEL_21;
      }
      if ( ValueW > 0 )
        v10 = (unsigned __int16)ValueW | 0x80070000;
      if ( v10 >= 0 )
        goto LABEL_21;
      v18 = 2447;
    }
    else
    {
      v10 = -2147024882;
      v18 = 2444;
    }
    v17 = (unsigned int)v10;
    goto LABEL_23;
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18005abd0  push    rbx
0x18005abd2  push    rbp
0x18005abd3  push    rsi
0x18005abd4  push    rdi
0x18005abd5  push    r12
0x18005abd7  push    r14
0x18005abd9  sub     rsp, 0F8h
0x18005abe0  mov     rax, cs:__security_cookie
0x18005abe7  xor     rax, rsp
0x18005abea  mov     [rsp+128h+var_48], rax
0x18005abf2  mov     r14, [rsp+128h+arg_20]
0x18005abfa  lea     rsi, [rcx+8]
0x18005abfe  cmp     qword ptr [rsi], 0
0x18005ac02  lea     r12, aOnecoreuapBase_7; "onecoreuap\\base\\mrt\\mrm\\src\\client"...
0x18005ac09  mov     rbp, r9
0x18005ac0c  mov     rbx, r8
0x18005ac0f  mov     rax, rdx
0x18005ac12  jnz     loc_18005ACF1
0x18005ac18  lea     r8, [rsp+128h+packageFamilyName]; packageFamilyName
0x18005ac1d  mov     qword ptr [rsi], 0
0x18005ac24  lea     rdx, [rsp+128h+packageFamilyNameLength]; packageFamilyNameLength
0x18005ac29  mov     [rsp+128h+packageFamilyNameLength], 41h ; 'A'
0x18005ac31  mov     rcx, rax; packageFullName
0x18005ac34  call    cs:__imp_PackageFamilyNameFromFullName
0x18005ac3a  mov     edi, 80070005h
0x18005ac3f  test    eax, eax
0x18005ac41  jnz     short loc_18005ACA5
0x18005ac43  mov     r9d, 20019h
0x18005ac49  mov     [rsp+128h+pdwType], rsi; int
0x18005ac4e  mov     r8, rbx
0x18005ac51  lea     rcx, [rsp+128h+packageFamilyName]
0x18005ac56  xor     edx, edx
0x18005ac58  call    cs:__imp_GetAppContainerRegistryHandleFromName
0x18005ac5e  mov     ebx, eax
0x18005ac60  test    eax, eax
0x18005ac62  jns     loc_18005ACF1
0x18005ac68  cmp     eax, 80070002h
0x18005ac6d  jz      short loc_18005ACC3
0x18005ac6f  cmp     eax, edi
0x18005ac71  jz      short loc_18005ACC3
0x18005ac73  mov     rcx, [rsp+128h]; this
0x18005ac7b  mov     r9d, eax; char *
0x18005ac7e  mov     r8, r12; unsigned int
0x18005ac81  mov     edx, 970h; void *
0x18005ac86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ac8b  mov     rcx, [rsp+128h]; this
0x18005ac93  mov     r9d, ebx; char *
0x18005ac96  mov     r8, r12; unsigned int
0x18005ac99  mov     edx, 982h; void *
0x18005ac9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005aca3  jmp     short loc_18005ACCF
0x18005aca5  mov     rcx, [rsp+128h]; this
0x18005acad  mov     r9d, eax; char *
0x18005acb0  mov     r8, r12; unsigned int
0x18005acb3  mov     edx, 96Bh; void *
0x18005acb8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005acbd  mov     ebx, eax
0x18005acbf  test    eax, eax
0x18005acc1  jns     short loc_18005ACF1
0x18005acc3  cmp     ebx, 80070002h
0x18005acc9  jnz     loc_18005ADF8
0x18005accf  mov     eax, ebx
0x18005acd1  mov     rcx, [rsp+128h+var_48]
0x18005acd9  xor     rcx, rsp; StackCookie
0x18005acdc  call    __security_check_cookie
0x18005ace1  add     rsp, 0F8h
0x18005ace8  pop     r14
0x18005acea  pop     r12
0x18005acec  pop     rdi
0x18005aced  pop     rsi
0x18005acee  pop     rbp
0x18005acef  pop     rbx
0x18005acf0  retn
0x18005acf1  mov     rcx, [rsi]; hkey
0x18005acf4  lea     rax, [rsp+128h+var_E8]
0x18005acf9  mov     [rsp+128h+pcbData], rax; pcbData
0x18005acfe  mov     ebx, 2
0x18005ad03  mov     [rsp+128h+pvData], 0; pvData
0x18005ad0c  mov     r9d, ebx; dwFlags
0x18005ad0f  mov     r8, rbp; lpValue
0x18005ad12  mov     [rsp+128h+pdwType], 0; pdwType
0x18005ad1b  xor     edx, edx; lpSubKey
0x18005ad1d  mov     [rsp+128h+var_E8], 0
0x18005ad25  call    cs:__imp_RegGetValueW
0x18005ad2b  test    eax, eax
0x18005ad2d  jz      short loc_18005AD3B
0x18005ad2f  jle     short loc_18005ACD1
0x18005ad31  movzx   eax, ax
0x18005ad34  or      eax, 80070000h
0x18005ad39  jmp     short loc_18005ACD1
0x18005ad3b  mov     ecx, [rsp+128h+var_E8]
0x18005ad3f  mov     rax, rbx
0x18005ad42  shr     rcx, 1
0x18005ad45  mul     rcx
0x18005ad48  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18005ad4f  lea     rdx, qword_1800DFCD8; struct std::nothrow_t *
0x18005ad56  cmovb   rax, rcx
0x18005ad5a  mov     rcx, rax; unsigned __int64
0x18005ad5d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18005ad62  mov     rdi, rax
0x18005ad65  test    rax, rax
0x18005ad68  jz      short loc_18005ADD3
0x18005ad6a  mov     rcx, [rsi]; hkey
0x18005ad6d  lea     rax, [rsp+128h+var_E8]
0x18005ad72  mov     [rsp+128h+pcbData], rax; pcbData
0x18005ad77  mov     r9d, ebx; dwFlags
0x18005ad7a  mov     [rsp+128h+pvData], rdi; pvData
0x18005ad7f  mov     r8, rbp; lpValue
0x18005ad82  xor     edx, edx; lpSubKey
0x18005ad84  mov     [rsp+128h+pdwType], 0; int
0x18005ad8d  call    cs:__imp_RegGetValueW
0x18005ad93  mov     ebx, eax
0x18005ad95  test    eax, eax
0x18005ad97  jnz     short loc_18005ADE2
0x18005ad99  mov     rcx, [r14]
0x18005ad9c  mov     rdx, rdi
0x18005ad9f  call    DefStringResult_SetCopy
0x18005ada4  mov     ebx, eax
0x18005ada6  test    eax, eax
0x18005ada8  js      short loc_18005ADB9
0x18005adaa  xor     ebx, ebx
0x18005adac  mov     rcx, rdi; Block
0x18005adaf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005adb4  jmp     loc_18005ACCF
0x18005adb9  mov     r9d, eax; char *
0x18005adbc  mov     edx, 991h; void *
0x18005adc1  mov     rcx, [rsp+128h]; this
0x18005adc9  mov     r8, r12; unsigned int
0x18005adcc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005add1  jmp     short loc_18005ADAC
0x18005add3  mov     ebx, 8007000Eh
0x18005add8  mov     edx, 98Ch
0x18005addd  mov     r9d, ebx
0x18005ade0  jmp     short loc_18005ADC1
0x18005ade2  jle     short loc_18005ADED
0x18005ade4  movzx   ebx, ax
0x18005ade7  or      ebx, 80070000h
0x18005aded  test    ebx, ebx
0x18005adef  jns     short loc_18005ADAC
0x18005adf1  mov     edx, 98Fh
0x18005adf6  jmp     short loc_18005ADDD
0x18005adf8  cmp     ebx, edi
0x18005adfa  jz      loc_18005ACCF
0x18005ae00  jmp     loc_18005AC8B
```
