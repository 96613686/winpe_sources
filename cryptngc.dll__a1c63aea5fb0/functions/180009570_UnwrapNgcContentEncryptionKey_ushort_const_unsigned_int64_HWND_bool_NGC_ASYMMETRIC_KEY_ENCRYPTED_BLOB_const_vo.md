# UnwrapNgcContentEncryptionKey(ushort const *,unsigned __int64,HWND__ *,bool,_NGC_ASYMMETRIC_KEY_ENCRYPTED_BLOB const *,void * *)

- ea: `0x180009570`
- end: `0x180009917`
- name: `?UnwrapNgcContentEncryptionKey@@YAJPEBG_KPEAUHWND__@@_NPEBU_NGC_ASYMMETRIC_KEY_ENCRYPTED_BLOB@@PEAPEAX@Z`
- size: `935`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int64, HWND, bool, const struct _NGC_ASYMMETRIC_KEY_ENCRYPTED_BLOB *, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004e40`

## callees

- `0x180006538`
- `0x180008538`
- `0x180009570`
- `0x180009920`
- `0x180028380`
- `0x18003c6f0`
- `0x180046ce0`

## import_xrefs

- `ncrypt!NCryptSetProperty` at `0x180009645`
- `ncrypt!NCryptSetProperty` at `0x1800096ba`
- `ncrypt!NCryptSetProperty` at `0x180009645`
- `ncrypt!NCryptSetProperty` at `0x1800096ba`
- `ncrypt!NCryptFreeObject` at `0x180009615`
- `ncrypt!NCryptFreeObject` at `0x18000968a`
- `ncrypt!NCryptFreeObject` at `0x1800097cb`
- `ncrypt!NCryptFreeObject` at `0x1800098e8`
- `ncrypt!NCryptFreeObject` at `0x180009615`
- `ncrypt!NCryptFreeObject` at `0x18000968a`
- `ncrypt!NCryptFreeObject` at `0x1800097cb`
- `ncrypt!NCryptFreeObject` at `0x1800098e8`
- `ncrypt!NCryptGetProperty` at `0x180009716`
- `ncrypt!NCryptGetProperty` at `0x180009716`
- `ncrypt!NCryptDecrypt` at `0x18000983a`
- `ncrypt!NCryptDecrypt` at `0x18000983a`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18000987c`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18000987c`
- `bcrypt!BCryptDestroyKey` at `0x1800098af`
- `bcrypt!BCryptDestroyKey` at `0x1800098af`

## string_xrefs

- `0x1800095f8`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkeyencrypt.cpp`
- `0x180009672`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkeyencrypt.cpp`
- `0x180009771`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkeyencrypt.cpp`
- `0x1800097ab`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkeyencrypt.cpp`
- `0x1800095e0`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x180009655`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x1800096ca`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x180009726`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x180009846`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x18000988a`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

## pseudocode

```c
__int64 __fastcall UnwrapNgcContentEncryptionKey(
        const unsigned __int16 *a1,
        __int64 a2,
        HWND a3,
        char a4,
        const struct _NGC_ASYMMETRIC_KEY_ENCRYPTED_BLOB *a5,
        void **a6)
{
  const struct _NGC_ASYMMETRIC_KEY_ENCRYPTED_BLOB *v6; // r14
  int v10; // eax
  unsigned int v11; // esi
  SECURITY_STATUS v13; // eax
  SECURITY_STATUS NCryptDwordProperty; // edi
  __int64 v15; // rdx
  SECURITY_STATUS v16; // eax
  NgcUtils *v17; // rsi
  SECURITY_STATUS Property; // eax
  unsigned int *v19; // r9
  __int64 v20; // rdx
  DWORD v21; // r8d
  DWORD v22; // eax
  __int64 v23; // rdx
  NTSTATUS SymmetricKey; // eax
  BCRYPT_KEY_HANDLE v25; // rbx
  NCRYPT_HANDLE v26; // rcx
  int dwFlags; // [rsp+20h] [rbp-60h]
  int dwFlagsg; // [rsp+20h] [rbp-60h]
  int dwFlagsa; // [rsp+20h] [rbp-60h]
  int dwFlagsb; // [rsp+20h] [rbp-60h]
  int dwFlagsc; // [rsp+20h] [rbp-60h]
  int dwFlagsd; // [rsp+20h] [rbp-60h]
  int dwFlagse; // [rsp+20h] [rbp-60h]
  int dwFlagsf; // [rsp+20h] [rbp-60h]
  NCRYPT_HANDLE hObject; // [rsp+40h] [rbp-40h] BYREF
  BYTE pbInput[8]; // [rsp+48h] [rbp-38h] BYREF
  BYTE pbOutput[8]; // [rsp+50h] [rbp-30h] BYREF
  BYTE pbSecret[8]; // [rsp+58h] [rbp-28h] BYREF
  BYTE *v39; // [rsp+60h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v6 = a5;
  *(_QWORD *)pbOutput = &hObject;
  *(_QWORD *)pbInput = a1;
  *(_QWORD *)pbSecret = pbInput;
  hObject = 0;
  v39 = pbOutput;
  v10 = HResultErrorContract__lambda_9209c3bff2fe15152f61109abc0c1cf2_(pbSecret);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4C7,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
      (const char *)(unsigned int)v10,
      dwFlags);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9E,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkeyencrypt.cpp",
      (const char *)v11,
      dwFlagsg);
    if ( hObject )
      NCryptFreeObject(hObject);
    return v11;
  }
  *(_QWORD *)pbInput = a3;
  if ( a3 )
  {
    v13 = NCryptSetProperty(hObject, L"HWND Handle", pbInput, 8u, 0);
    NCryptDwordProperty = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x114,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
        (const char *)(unsigned int)v13,
        dwFlagsa);
      v15 = 162;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkeyencrypt.cpp",
        (const char *)(unsigned int)NCryptDwordProperty,
        dwFlagsb);
      if ( hObject )
        NCryptFreeObject(hObject);
      return (unsigned int)NCryptDwordProperty;
    }
  }
  *(_QWORD *)pbInput = a2;
  if ( a2 )
  {
    v16 = NCryptSetProperty(hObject, L"NgcAuthTicket", pbInput, 8u, 0);
    NCryptDwordProperty = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14E,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
        (const char *)(unsigned int)v16,
        dwFlagsc);
      v15 = 166;
      goto LABEL_8;
    }
  }
  v17 = (NgcUtils *)hObject;
  *(_DWORD *)pbInput = 4;
  *(_DWORD *)pbOutput = 0;
  Property = NCryptGetProperty(hObject, L"NgcKeyImplType", pbOutput, 4u, (DWORD *)pbInput, 0);
  NCryptDwordProperty = Property;
  if ( Property < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE8,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
      (const char *)(unsigned int)Property,
      dwFlagsd);
    v20 = 93;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkeyencrypt.cpp",
      (const char *)(unsigned int)NCryptDwordProperty,
      dwFlagsd);
    v15 = 171;
    goto LABEL_8;
  }
  if ( *(_DWORD *)pbOutput != 1 )
    goto LABEL_27;
  *(_DWORD *)pbOutput = 0;
  NCryptDwordProperty = NgcUtils::GetNCryptDwordProperty(
                          v17,
                          (unsigned __int64)L"Key Usage",
                          (const unsigned __int16 *)pbOutput,
                          v19);
  if ( NCryptDwordProperty < 0 )
  {
    v20 = 105;
    goto LABEL_19;
  }
  if ( *(_DWORD *)pbOutput == 1 && IsTpm12() )
  {
    v21 = *((_DWORD *)a5 + 4);
    if ( !v21 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB1,
        (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkeyencrypt.cpp",
        (const char *)0x80090005LL,
        dwFlagsd);
      if ( hObject )
        NCryptFreeObject(hObject);
      return 2148073477LL;
    }
    v6 = (const struct _NGC_ASYMMETRIC_KEY_ENCRYPTED_BLOB *)((char *)a5
                                                           + *((unsigned int *)a5 + 2)
                                                           + *((unsigned int *)a5 + 3)
                                                           + *((unsigned int *)a5 + 1));
  }
  else
  {
LABEL_27:
    v21 = *((_DWORD *)a5 + 1);
  }
  if ( a4 || (v22 = 2, !a2) )
    v22 = 66;
  *(_DWORD *)pbOutput = 32;
  NCryptDwordProperty = NCryptDecrypt(hObject, (PBYTE)v6 + 20, v21, 0, pbSecret, 0x20u, (DWORD *)pbOutput, v22);
  if ( NCryptDwordProperty < 0 )
  {
    v23 = 657;
LABEL_38:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
      (const char *)(unsigned int)NCryptDwordProperty,
      dwFlagse);
    v15 = 205;
    goto LABEL_8;
  }
  *(_QWORD *)pbInput = 0;
  SymmetricKey = BCryptGenerateSymmetricKey(
                   (BCRYPT_ALG_HANDLE)0x1A1,
                   (BCRYPT_KEY_HANDLE *)pbInput,
                   0,
                   0,
                   pbSecret,
                   *(ULONG *)pbOutput,
                   0);
  if ( SymmetricKey >= 0 )
  {
    v25 = *(BCRYPT_KEY_HANDLE *)pbInput;
  }
  else
  {
    v25 = 0;
    NCryptDwordProperty = wil::details::in1diag3::Return_NtStatus(
                            retaddr,
                            (void *)0x1B5,
                            (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
                            (const char *)(unsigned int)SymmetricKey,
                            dwFlagsf);
    if ( *(_QWORD *)pbInput )
      BCryptDestroyKey(*(BCRYPT_KEY_HANDLE *)pbInput);
    if ( NCryptDwordProperty < 0 )
    {
      v23 = 665;
      goto LABEL_38;
    }
  }
  v26 = hObject;
  *a6 = v25;
  if ( v26 )
    NCryptFreeObject(v26);
  return 0;
}

```

## disassembly

```asm
0x180009570  mov     [rsp-38h+arg_0], rbx
0x180009575  push    rbp
0x180009576  push    rsi
0x180009577  push    rdi
0x180009578  push    r12
0x18000957a  push    r13
0x18000957c  push    r14
0x18000957e  push    r15
0x180009580  mov     rbp, rsp
0x180009583  sub     rsp, 80h
0x18000958a  mov     rax, cs:__security_cookie
0x180009591  xor     rax, rsp
0x180009594  mov     [rbp+var_8], rax
0x180009598  mov     r14, [rbp+arg_20]
0x18000959c  lea     rax, [rbp+hObject]
0x1800095a0  mov     r12, [rbp+arg_28]
0x1800095a4  xor     r13d, r13d
0x1800095a7  mov     qword ptr [rbp+pbOutput], rax
0x1800095ab  movzx   r15d, r9b
0x1800095af  lea     rax, [rbp+pbInput]
0x1800095b3  mov     qword ptr [rbp+pbInput], rcx
0x1800095b7  mov     qword ptr [rbp+pbSecret], rax
0x1800095bb  lea     rcx, [rbp+pbSecret]
0x1800095bf  lea     rax, [rbp+pbOutput]
0x1800095c3  mov     [rbp+hObject], r13
0x1800095c7  mov     [rbp+var_20], rax
0x1800095cb  mov     rdi, r8
0x1800095ce  mov     rbx, rdx
0x1800095d1  call    HResultErrorContract__lambda_9209c3bff2fe15152f61109abc0c1cf2___; HResultErrorContract__lambda_9209c3bff2fe15152f61109abc0c1cf2_
0x1800095d6  mov     esi, eax
0x1800095d8  test    eax, eax
0x1800095da  jns     short loc_180009622
0x1800095dc  mov     rcx, [rbp+38h]; this
0x1800095e0  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x1800095e7  mov     r9d, eax; char *
0x1800095ea  mov     edx, 4C7h; void *
0x1800095ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800095f4  mov     rcx, [rbp+38h]; this
0x1800095f8  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x1800095ff  mov     r9d, esi; char *
0x180009602  mov     edx, 9Eh; void *
0x180009607  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000960c  mov     rcx, [rbp+hObject]; hObject
0x180009610  test    rcx, rcx
0x180009613  jz      short loc_18000961B
0x180009615  call    cs:__imp_NCryptFreeObject
0x18000961b  mov     eax, esi
0x18000961d  jmp     loc_1800098F0
0x180009622  mov     qword ptr [rbp+pbInput], rdi
0x180009626  test    rdi, rdi
0x180009629  jz      short loc_180009697
0x18000962b  mov     rcx, [rbp+hObject]; hObject
0x18000962f  lea     r8, [rbp+pbInput]; pbInput
0x180009633  mov     r9d, 8; cbInput
0x180009639  mov     [rsp+80h+dwFlags], r13d; int
0x18000963e  lea     rdx, aHwndHandle; "HWND Handle"
0x180009645  call    cs:__imp_NCryptSetProperty
0x18000964b  mov     edi, eax
0x18000964d  test    eax, eax
0x18000964f  jns     short loc_180009697
0x180009651  mov     rcx, [rbp+38h]; this
0x180009655  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18000965c  mov     r9d, eax; char *
0x18000965f  mov     edx, 114h; void *
0x180009664  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009669  mov     edx, 0A2h; void *
0x18000966e  mov     rcx, [rbp+38h]; this
0x180009672  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180009679  mov     r9d, edi; char *
0x18000967c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009681  mov     rcx, [rbp+hObject]; hObject
0x180009685  test    rcx, rcx
0x180009688  jz      short loc_180009690
0x18000968a  call    cs:__imp_NCryptFreeObject
0x180009690  mov     eax, edi
0x180009692  jmp     loc_1800098F0
0x180009697  mov     qword ptr [rbp+pbInput], rbx
0x18000969b  test    rbx, rbx
0x18000969e  jz      short loc_1800096E5
0x1800096a0  mov     rcx, [rbp+hObject]; hObject
0x1800096a4  lea     r8, [rbp+pbInput]; pbInput
0x1800096a8  mov     r9d, 8; cbInput
0x1800096ae  mov     [rsp+80h+dwFlags], r13d; int
0x1800096b3  lea     rdx, aNgcauthticket; "NgcAuthTicket"
0x1800096ba  call    cs:__imp_NCryptSetProperty
0x1800096c0  mov     edi, eax
0x1800096c2  test    eax, eax
0x1800096c4  jns     short loc_1800096E5
0x1800096c6  mov     rcx, [rbp+38h]; this
0x1800096ca  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800096d1  mov     r9d, eax; char *
0x1800096d4  mov     edx, 14Eh; void *
0x1800096d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800096de  mov     edx, 0A6h
0x1800096e3  jmp     short loc_18000966E
0x1800096e5  mov     rsi, [rbp+hObject]
0x1800096e9  lea     rax, [rbp+pbInput]
0x1800096ed  mov     rcx, rsi; hObject
0x1800096f0  mov     [rsp+80h+cbOutput], r13d; dwFlags
0x1800096f5  mov     r9d, 4; cbOutput
0x1800096fb  mov     dword ptr [rbp+pbInput], 4
0x180009702  lea     r8, [rbp+pbOutput]; pbOutput
0x180009706  mov     dword ptr [rbp+pbOutput], r13d
0x18000970a  lea     rdx, aNgckeyimpltype; "NgcKeyImplType"
0x180009711  mov     qword ptr [rsp+80h+dwFlags], rax; int
0x180009716  call    cs:__imp_NCryptGetProperty
0x18000971c  mov     edi, eax
0x18000971e  test    eax, eax
0x180009720  jns     short loc_180009741
0x180009722  mov     rcx, [rbp+38h]; this
0x180009726  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18000972d  mov     r9d, eax; char *
0x180009730  mov     edx, 0E8h; void *
0x180009735  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000973a  mov     edx, 5Dh ; ']'
0x18000973f  jmp     short loc_18000976D
0x180009741  cmp     dword ptr [rbp+pbOutput], 1
0x180009745  jnz     loc_1800097F2
0x18000974b  lea     r8, [rbp+pbOutput]; unsigned __int16 *
0x18000974f  mov     dword ptr [rbp+pbOutput], r13d
0x180009753  lea     rdx, aKeyUsage; "Key Usage"
0x18000975a  mov     rcx, rsi; this
0x18000975d  call    ?GetNCryptDwordProperty@NgcUtils@@YAJ_KPEBGPEAK@Z; NgcUtils::GetNCryptDwordProperty(unsigned __int64,ushort const *,ulong *)
0x180009762  mov     edi, eax
0x180009764  test    eax, eax
0x180009766  jns     short loc_18000978A
0x180009768  mov     edx, 69h ; 'i'; void *
0x18000976d  mov     rcx, [rbp+38h]; this
0x180009771  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180009778  mov     r9d, edi; char *
0x18000977b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009780  mov     edx, 0ABh
0x180009785  jmp     loc_18000966E
0x18000978a  cmp     dword ptr [rbp+pbOutput], 1
0x18000978e  setz    al
0x180009791  test    al, al
0x180009793  jz      short loc_1800097F2
0x180009795  call    ?IsTpm12@@YA_NXZ; IsTpm12(void)
0x18000979a  test    al, al
0x18000979c  jz      short loc_1800097F2
0x18000979e  mov     r8d, [r14+10h]
0x1800097a2  test    r8d, r8d
0x1800097a5  jnz     short loc_1800097DB
0x1800097a7  mov     rcx, [rbp+38h]; this
0x1800097ab  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x1800097b2  mov     r9d, 80090005h; char *
0x1800097b8  mov     edx, 0B1h; void *
0x1800097bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800097c2  mov     rcx, [rbp+hObject]; hObject
0x1800097c6  test    rcx, rcx
0x1800097c9  jz      short loc_1800097D1
0x1800097cb  call    cs:__imp_NCryptFreeObject
0x1800097d1  mov     eax, 80090005h
0x1800097d6  jmp     loc_1800098F0
0x1800097db  mov     ecx, [r14+8]
0x1800097df  mov     eax, [r14+0Ch]
0x1800097e3  add     rcx, r14
0x1800097e6  mov     r14d, [r14+4]
0x1800097ea  add     rcx, rax
0x1800097ed  add     r14, rcx
0x1800097f0  jmp     short loc_1800097F6
0x1800097f2  mov     r8d, [r14+4]; cbInput
0x1800097f6  lea     rdx, [r14+14h]; pbInput
0x1800097fa  test    r15b, r15b
0x1800097fd  jnz     short loc_180009809
0x1800097ff  mov     eax, 2
0x180009804  test    rbx, rbx
0x180009807  jnz     short loc_18000980E
0x180009809  mov     eax, 42h ; 'B'
0x18000980e  mov     rcx, [rbp+hObject]; hKey
0x180009812  xor     r9d, r9d; pPaddingInfo
0x180009815  mov     [rsp+80h+var_48], eax; dwFlags
0x180009819  lea     rax, [rbp+pbOutput]
0x18000981d  mov     [rsp+80h+pcbResult], rax; pcbResult
0x180009822  lea     rax, [rbp+pbSecret]
0x180009826  mov     [rsp+80h+cbOutput], 20h ; ' '; cbOutput
0x18000982e  mov     qword ptr [rsp+80h+dwFlags], rax; pbOutput
0x180009833  mov     dword ptr [rbp+pbOutput], 20h ; ' '
0x18000983a  call    cs:__imp_NCryptDecrypt
0x180009840  mov     edi, eax
0x180009842  test    eax, eax
0x180009844  jns     short loc_180009854
0x180009846  lea     rsi, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18000984d  mov     edx, 291h
0x180009852  jmp     short loc_1800098BE
0x180009854  mov     eax, dword ptr [rbp+pbOutput]
0x180009857  lea     rdx, [rbp+pbInput]; phKey
0x18000985b  mov     dword ptr [rsp+80h+pcbResult], r13d; dwFlags
0x180009860  xor     r9d, r9d; cbKeyObject
0x180009863  mov     [rsp+80h+cbOutput], eax; cbSecret
0x180009867  xor     r8d, r8d; pbKeyObject
0x18000986a  lea     rax, [rbp+pbSecret]
0x18000986e  mov     qword ptr [rbp+pbInput], r13
0x180009872  mov     ecx, 1A1h; hAlgorithm
0x180009877  mov     qword ptr [rsp+80h+dwFlags], rax; int
0x18000987c  call    cs:__imp_BCryptGenerateSymmetricKey
0x180009882  test    eax, eax
0x180009884  jns     short loc_1800098D7
0x180009886  mov     rcx, [rbp+38h]; this
0x18000988a  lea     rsi, aOnecoreDsSecur_15; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180009891  mov     r8, rsi; unsigned int
0x180009894  mov     r9d, eax; char *
0x180009897  mov     edx, 1B5h; void *
0x18000989c  mov     rbx, r13
0x18000989f  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800098a4  mov     rcx, qword ptr [rbp+pbInput]; hKey
0x1800098a8  mov     edi, eax
0x1800098aa  test    rcx, rcx
0x1800098ad  jz      short loc_1800098B5
0x1800098af  call    cs:__imp_BCryptDestroyKey
0x1800098b5  test    edi, edi
0x1800098b7  jns     short loc_1800098DB
0x1800098b9  mov     edx, 299h; void *
0x1800098be  mov     rcx, [rbp+38h]; this
0x1800098c2  mov     r9d, edi; char *
0x1800098c5  mov     r8, rsi; unsigned int
0x1800098c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800098cd  mov     edx, 0CDh
0x1800098d2  jmp     loc_18000966E
0x1800098d7  mov     rbx, qword ptr [rbp+pbInput]
0x1800098db  mov     rcx, [rbp+hObject]; hObject
0x1800098df  mov     [r12], rbx
0x1800098e3  test    rcx, rcx
0x1800098e6  jz      short loc_1800098EE
0x1800098e8  call    cs:__imp_NCryptFreeObject
0x1800098ee  xor     eax, eax
0x1800098f0  mov     rcx, [rbp+var_8]
0x1800098f4  xor     rcx, rsp; StackCookie
0x1800098f7  call    __security_check_cookie
0x1800098fc  mov     rbx, [rsp+80h+arg_0]
0x180009904  add     rsp, 80h
0x18000990b  pop     r15
0x18000990d  pop     r14
0x18000990f  pop     r13
0x180009911  pop     r12
0x180009913  pop     rdi
0x180009914  pop     rsi
0x180009915  pop     rbp
0x180009916  retn
```
