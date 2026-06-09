# DavSelectCertificateFromStore

- ea: `0x18000e2b0`
- end: `0x18000e48c`
- name: `DavSelectCertificateFromStore`
- size: `476`
- prototype: `__int64 __fastcall(LPCWSTR UncPath, __int64, PCCERT_CONTEXT *, __int64 *, HCERTSTORE hCertStore, int, __int64, unsigned int, __int64, void (**)(void))`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180007ad0`

## callees

- `0x18000b494`
- `0x18000da5c`
- `0x18000e2b0`
- `0x180010a14`
- `0x180010d00`
- `0x180011e82`
- `0x180013010`

## import_xrefs

- `CRYPT32!CertEnumCertificatesInStore` at `0x18000e425`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18000e425`
- `CRYPTUI!CryptUIDlgSelectCertificateW` at `0x18000e465`
- `CRYPTUI!CryptUIDlgSelectCertificateW` at `0x18000e465`

## pseudocode

```c
__int64 __fastcall DavSelectCertificateFromStore(
        LPCWSTR UncPath,
        __int64 a2,
        PCCERT_CONTEXT *a3,
        __int64 *a4,
        HCERTSTORE hCertStore,
        int a6,
        __int64 a7,
        unsigned int a8,
        __int64 a9,
        void (**a10)(void))
{
  __int64 v14; // rcx
  void (**v15)(void); // rdi
  __int64 result; // rax
  unsigned int v17; // edx
  PCCERT_CONTEXT v18; // rax
  __int64 v19; // [rsp+60h] [rbp-89h] BYREF
  _DWORD v20[2]; // [rsp+70h] [rbp-79h] BYREF
  __int64 v21; // [rsp+78h] [rbp-71h]
  int v22; // [rsp+B8h] [rbp-31h]
  HCERTSTORE *p_hCertStore; // [rsp+C0h] [rbp-29h]
  int v24; // [rsp+C8h] [rbp-21h]
  HCERTSTORE *v25; // [rsp+D0h] [rbp-19h]
  __int64 v26; // [rsp+138h] [rbp+4Fh] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      307,
      (unsigned int)WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids,
      (_DWORD)UncPath,
      a2);
  *a4 = 0;
  if ( !CallBackRegistered() )
  {
LABEL_15:
    v20[1] = 0;
    if ( a6 )
    {
      if ( a6 == 1 )
      {
        v18 = CertEnumCertificatesInStore(hCertStore, 0);
      }
      else
      {
        memset_0(v20, 0, 0x80u);
        v21 = a7;
        p_hCertStore = &hCertStore;
        v25 = &hCertStore;
        v20[0] = 128;
        v22 = 1;
        v24 = 1;
        v18 = (PCCERT_CONTEXT)CryptUIDlgSelectCertificateW(v20);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 308, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids);
      v18 = 0;
    }
    *a3 = v18;
    return 0;
  }
  v14 = *a4;
  v15 = a10;
  LODWORD(a9) = 0;
  LODWORD(v19) = 0;
  LODWORD(v26) = 0;
  if ( v14 && *a10 )
  {
    (*a10)();
    *a4 = 0;
    *v15 = 0;
  }
  result = DavPromptForCredentialsUsingCallback(UncPath, a2, a4, 0, 0, &v19, a8, 0x10000u, &v26, &a9, v15);
  v17 = result;
  if ( !(_DWORD)result )
  {
    if ( (_DWORD)a9 != 1 )
    {
      if ( (_DWORD)a9 == 2 )
        return 1223;
      goto LABEL_15;
    }
    if ( !(_DWORD)v26 )
      return 13;
    return v17;
  }
  return result;
}

```

## disassembly

```asm
0x18000e2b0  mov     [rsp-8+arg_0], rbx
0x18000e2b5  mov     [rsp-8+arg_8], rsi
0x18000e2ba  push    rbp
0x18000e2bb  push    rdi
0x18000e2bc  push    r13
0x18000e2be  push    r14
0x18000e2c0  push    r15
0x18000e2c2  lea     rbp, [rsp-7]
0x18000e2c7  sub     rsp, 0F0h
0x18000e2ce  mov     rbx, r9
0x18000e2d1  mov     r15, r8
0x18000e2d4  mov     rsi, rdx
0x18000e2d7  mov     r14, rcx
0x18000e2da  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e2e1  lea     r13, WPP_GLOBAL_Control
0x18000e2e8  cmp     rcx, r13
0x18000e2eb  jz      short loc_18000E310
0x18000e2ed  test    byte ptr [rcx+1Ch], 2
0x18000e2f1  jz      short loc_18000E310
0x18000e2f3  mov     rcx, [rcx+10h]
0x18000e2f7  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000e2fe  mov     edx, 133h
0x18000e303  mov     [rsp+110h+var_F0], rsi
0x18000e308  mov     r9, r14
0x18000e30b  call    WPP_SF_SS
0x18000e310  mov     qword ptr [rbx], 0
0x18000e317  call    CallBackRegistered
0x18000e31c  test    eax, eax
0x18000e31e  jz      loc_18000E3DF
0x18000e324  mov     rcx, [rbx]
0x18000e327  mov     rdi, [rbp+27h+arg_48]
0x18000e32b  mov     dword ptr [rbp+27h+arg_40], 0
0x18000e332  mov     dword ptr [rsp+110h+var_B0], 0
0x18000e33a  mov     dword ptr [rbp+27h+arg_18], 0
0x18000e341  test    rcx, rcx
0x18000e344  jz      short loc_18000E361
0x18000e346  mov     rax, [rdi]
0x18000e349  test    rax, rax
0x18000e34c  jz      short loc_18000E361
0x18000e34e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e353  mov     qword ptr [rbx], 0
0x18000e35a  mov     qword ptr [rdi], 0
0x18000e361  mov     [rsp+110h+var_C0], rdi; __int64
0x18000e366  lea     rax, [rbp+27h+arg_40]
0x18000e36a  mov     [rsp+110h+var_C8], rax; __int64
0x18000e36f  xor     r9d, r9d
0x18000e372  lea     rax, [rbp+27h+arg_18]
0x18000e376  mov     r8, rbx
0x18000e379  mov     [rsp+110h+var_D0], rax; __int64
0x18000e37e  mov     rdx, rsi
0x18000e381  mov     eax, [rbp+27h+arg_38]
0x18000e384  mov     rcx, r14; UncPath
0x18000e387  mov     [rsp+110h+var_D8], 10000h; int
0x18000e38f  mov     [rsp+110h+var_E0], eax; int
0x18000e393  lea     rax, [rsp+110h+var_B0]
0x18000e398  mov     [rsp+110h+var_E8], rax; __int64
0x18000e39d  mov     [rsp+110h+var_F0], 0; __int64
0x18000e3a6  call    DavPromptForCredentialsUsingCallback
0x18000e3ab  mov     edx, eax
0x18000e3ad  test    eax, eax
0x18000e3af  jnz     loc_18000E470
0x18000e3b5  mov     ecx, dword ptr [rbp+27h+arg_40]
0x18000e3b8  sub     ecx, 1
0x18000e3bb  jz      short loc_18000E3CC
0x18000e3bd  cmp     ecx, 1
0x18000e3c0  jnz     short loc_18000E3DF
0x18000e3c2  mov     eax, 4C7h
0x18000e3c7  jmp     loc_18000E470
0x18000e3cc  cmp     dword ptr [rbp+27h+arg_18], 0
0x18000e3d0  mov     eax, 0Dh
0x18000e3d5  cmovz   edx, eax
0x18000e3d8  mov     eax, edx
0x18000e3da  jmp     loc_18000E470
0x18000e3df  xor     eax, eax
0x18000e3e1  mov     [rbp+27h+var_9C], eax
0x18000e3e4  mov     eax, [rbp+27h+arg_28]
0x18000e3e7  test    eax, eax
0x18000e3e9  jnz     short loc_18000E416
0x18000e3eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e3f2  cmp     rcx, r13
0x18000e3f5  jz      short loc_18000E412
0x18000e3f7  test    byte ptr [rcx+1Ch], 2
0x18000e3fb  jz      short loc_18000E412
0x18000e3fd  mov     rcx, [rcx+10h]
0x18000e401  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000e408  mov     edx, 134h
0x18000e40d  call    WPP_SF_
0x18000e412  xor     eax, eax
0x18000e414  jmp     short loc_18000E46B
0x18000e416  mov     edi, 1
0x18000e41b  cmp     eax, edi
0x18000e41d  jnz     short loc_18000E42D
0x18000e41f  mov     rcx, [rbp+27h+hCertStore]; hCertStore
0x18000e423  xor     edx, edx; pPrevCertContext
0x18000e425  call    cs:__imp_CertEnumCertificatesInStore
0x18000e42b  jmp     short loc_18000E46B
0x18000e42d  mov     ebx, 80h
0x18000e432  lea     rcx, [rbp+27h+var_A0]; void *
0x18000e436  mov     r8d, ebx; Size
0x18000e439  xor     edx, edx; Val
0x18000e43b  call    memset_0
0x18000e440  mov     rax, [rbp+27h+arg_30]
0x18000e444  lea     rcx, [rbp+27h+var_A0]
0x18000e448  mov     [rbp+27h+var_98], rax
0x18000e44c  lea     rax, [rbp+27h+hCertStore]
0x18000e450  mov     [rbp+27h+var_50], rax
0x18000e454  lea     rax, [rbp+27h+hCertStore]
0x18000e458  mov     [rbp+27h+var_40], rax
0x18000e45c  mov     [rbp+27h+var_A0], ebx
0x18000e45f  mov     [rbp+27h+var_58], edi
0x18000e462  mov     [rbp+27h+var_48], edi
0x18000e465  call    cs:__imp_CryptUIDlgSelectCertificateW
0x18000e46b  mov     [r15], rax
0x18000e46e  xor     eax, eax
0x18000e470  lea     r11, [rsp+110h+var_20]
0x18000e478  mov     rbx, [r11+30h]
0x18000e47c  mov     rsi, [r11+38h]
0x18000e480  mov     rsp, r11
0x18000e483  pop     r15
0x18000e485  pop     r14
0x18000e487  pop     r13
0x18000e489  pop     rdi
0x18000e48a  pop     rbp
0x18000e48b  retn
```
