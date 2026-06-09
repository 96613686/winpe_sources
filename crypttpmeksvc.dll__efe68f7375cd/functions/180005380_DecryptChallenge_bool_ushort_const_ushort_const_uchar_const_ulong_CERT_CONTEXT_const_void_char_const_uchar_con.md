# _DecryptChallenge(bool,ushort const *,ushort const *,uchar const *,ulong,_CERT_CONTEXT const *,void *,char const *,uchar const *,ulong,uchar * *,ulong *)

- ea: `0x180005380`
- end: `0x180005600`
- name: `?_DecryptChallenge@@YAK_NPEBG1PEBEKPEBU_CERT_CONTEXT@@PEAXPEBD2KPEAPEAEPEAK@Z`
- size: `640`
- prototype: `__int64 __fastcall(bool, const unsigned __int16 *, const unsigned __int16 *, BYTE *, DWORD cbData, const struct _CERT_CONTEXT *, void *, char *, unsigned __int8 *, DWORD, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180009470`

## callees

- `0x180003750`
- `0x180004230`
- `0x180004440`
- `0x180005380`
- `0x180005910`
- `0x180007d80`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000542d`
- `msvcrt!_wcsicmp` at `0x18000542d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800055c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800055c0`

## pseudocode

```c
__int64 __fastcall _DecryptChallenge(
        bool a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        BYTE *a4,
        DWORD cbData,
        const struct _CERT_CONTEXT *a6,
        void *a7,
        char *a8,
        unsigned __int8 *a9,
        DWORD a10,
        unsigned __int8 **a11,
        unsigned int *a12)
{
  const unsigned __int8 *v14; // rdi
  DWORD v15; // r12d
  unsigned __int8 **v16; // rsi
  unsigned int *v17; // r14
  int v18; // eax
  unsigned int v19; // ebx
  unsigned int v21; // eax
  BYTE *v22; // rdi
  __int64 v23; // r12
  unsigned int v24; // eax
  __int64 v25; // rdx
  BYTE *v26; // rax
  int cbInput; // [rsp+20h] [rbp-68h]
  unsigned int v28; // [rsp+40h] [rbp-48h] BYREF
  unsigned __int8 *v29; // [rsp+48h] [rbp-40h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-38h] BYREF
  DWORD cbToBeEncrypted; // [rsp+98h] [rbp+10h] BYREF
  LPCWSTR pszKeyName; // [rsp+A0h] [rbp+18h]
  PBYTE pbData; // [rsp+A8h] [rbp+20h]

  pbData = a4;
  pszKeyName = a3;
  hMem = 0;
  cbToBeEncrypted = 0;
  v29 = 0;
  v28 = 0;
  if ( !a2 || !a6 || !a8 || (v14 = a9) == 0 || (v15 = a10) == 0 || (v16 = a11) == 0 || (v17 = a12) == 0 )
  {
    ekTraceFmt(0x64C12C2u, 1u, "ERROR: Arguments. Return=%d\n", 160);
    return 160;
  }
  *a11 = 0;
  *v17 = 0;
  if ( _wcsicmp(a2, L"Microsoft Platform Crypto Provider") )
  {
    cbInput = 160;
    ekTraceFmt(0x66612C2u, 1u, "ERROR: Invalid KSP.Ksp=%ws Return=%d\n", a2, cbInput);
    return 160;
  }
  v18 = _ValidateCaExchangeCertificate(a1, a6, a7);
  v19 = v18;
  if ( v18 )
  {
    ekTraceFmt(0x67812C2u, 1u, "ERROR: _ValidateCaExchangeCertificate. Return=%d\n", v18);
    return v19;
  }
  v21 = _TpmActivateAttestationIdentityKey(pszKeyName, pbData, cbData, v14, v15, (DWORD)&hMem, &cbToBeEncrypted);
  v22 = (BYTE *)hMem;
  v19 = v21;
  v23 = cbToBeEncrypted;
  if ( v21 )
  {
    ekTraceFmt(0x68812C2u, 1u, "ERROR: _TpmActivateAttestationIdentityKey. Return=%x\n", v21);
  }
  else
  {
    ekTraceFmt(0x68D12C2u, 2u, "TRACE: Algorithm=%hs\n", a8);
    v24 = _EncryptContent(v22, v23, a8, a6, &v29, &v28);
    v19 = v24;
    if ( v24 )
    {
      ekTraceFmt(0x69A12C2u, 1u, "ERROR: _EncryptContent. Return=%d\n", v24);
      if ( v29 )
        MIDL_user_free(v29);
    }
    else
    {
      v19 = 0;
      *v16 = v29;
      *v17 = v28;
    }
  }
  if ( !v22 )
    return v19;
  v25 = v23;
  v26 = v22;
  if ( (_DWORD)v23 )
  {
    do
    {
      *v26++ = 0;
      --v25;
    }
    while ( v25 );
  }
  LocalFree(v22);
  return v19;
}

```

## disassembly

```asm
0x180005380  mov     r11, rsp
0x180005383  mov     [r11+8], rbx
0x180005387  mov     [r11+20h], r9
0x18000538b  mov     [r11+18h], r8
0x18000538f  push    rsi
0x180005390  push    rdi
0x180005391  push    r12
0x180005393  push    r13
0x180005395  push    r14
0x180005397  sub     rsp, 60h
0x18000539b  xor     eax, eax
0x18000539d  mov     rbx, rdx
0x1800053a0  mov     [r11-38h], rax
0x1800053a4  movzx   r13d, cl
0x1800053a8  mov     [r11+10h], eax
0x1800053ac  mov     [r11-40h], rax
0x1800053b0  mov     [rsp+88h+var_48], eax
0x1800053b4  test    rdx, rdx
0x1800053b7  jz      loc_1800055CA
0x1800053bd  cmp     [rsp+88h+arg_28], rax
0x1800053c5  jz      loc_1800055CA
0x1800053cb  cmp     [rsp+88h+arg_38], rax
0x1800053d3  jz      loc_1800055CA
0x1800053d9  mov     rdi, [rsp+88h+arg_40]
0x1800053e1  test    rdi, rdi
0x1800053e4  jz      loc_1800055CA
0x1800053ea  mov     r12d, [rsp+88h+arg_48]
0x1800053f2  test    r12d, r12d
0x1800053f5  jz      loc_1800055CA
0x1800053fb  mov     rsi, [rsp+88h+arg_50]
0x180005403  test    rsi, rsi
0x180005406  jz      loc_1800055CA
0x18000540c  mov     r14, [rsp+88h+arg_58]
0x180005414  test    r14, r14
0x180005417  jz      loc_1800055CA
0x18000541d  mov     [rsi], rax
0x180005420  lea     rdx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x180005427  mov     rcx, rbx; String1
0x18000542a  mov     [r14], eax
0x18000542d  call    cs:__imp__wcsicmp
0x180005433  test    eax, eax
0x180005435  jz      short loc_18000545D
0x180005437  mov     r9, rbx
0x18000543a  mov     [rsp+88h+cbInput], 0A0h
0x180005442  lea     r8, aErrorInvalidKs; "ERROR: Invalid KSP.Ksp=%ws Return=%d\n"
0x180005449  mov     edx, 1; unsigned int
0x18000544e  mov     ecx, 66612C2h; unsigned int
0x180005453  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180005458  jmp     loc_1800055E6
0x18000545d  mov     r8, [rsp+88h+arg_30]; void *
0x180005465  movzx   ecx, r13b; bool
0x180005469  mov     rdx, [rsp+88h+arg_28]; struct _CERT_CONTEXT *
0x180005471  call    ?_ValidateCaExchangeCertificate@@YAJ_NPEBU_CERT_CONTEXT@@PEAX@Z; _ValidateCaExchangeCertificate(bool,_CERT_CONTEXT const *,void *)
0x180005476  mov     ebx, eax
0x180005478  test    eax, eax
0x18000547a  jz      short loc_18000549C
0x18000547c  mov     r9d, eax
0x18000547f  lea     r8, aErrorValidatec_0; "ERROR: _ValidateCaExchangeCertificate. "...
0x180005486  mov     edx, 1; unsigned int
0x18000548b  mov     ecx, 67812C2h; unsigned int
0x180005490  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180005495  mov     eax, ebx
0x180005497  jmp     loc_1800055EB
0x18000549c  mov     r8d, [rsp+88h+cbData]; cbData
0x1800054a4  lea     rax, [rsp+88h+cbToBeEncrypted]
0x1800054ac  mov     rdx, [rsp+88h+pbData]; pbData
0x1800054b4  mov     r9, rdi; unsigned __int8 *
0x1800054b7  mov     rcx, [rsp+88h+pszKeyName]; pszKeyName
0x1800054bf  mov     [rsp+88h+var_58], rax; unsigned int *
0x1800054c4  lea     rax, [rsp+88h+hMem]
0x1800054c9  mov     qword ptr [rsp+88h+pcbResult], rax; pcbResult
0x1800054ce  mov     [rsp+88h+cbInput], r12d; cbInput
0x1800054d3  call    ?_TpmActivateAttestationIdentityKey@@YAJPEBGPEBEK1KPEAPEAEPEAK@Z; _TpmActivateAttestationIdentityKey(ushort const *,uchar const *,ulong,uchar const *,ulong,uchar * *,ulong *)
0x1800054d8  mov     rdi, [rsp+88h+hMem]
0x1800054dd  mov     ebx, eax
0x1800054df  mov     r12d, [rsp+88h+cbToBeEncrypted]
0x1800054e7  test    eax, eax
0x1800054e9  jz      short loc_180005509
0x1800054eb  mov     r9d, eax
0x1800054ee  lea     r8, aErrorTpmactiva; "ERROR: _TpmActivateAttestationIdentityK"...
0x1800054f5  mov     edx, 1; unsigned int
0x1800054fa  mov     ecx, 68812C2h; unsigned int
0x1800054ff  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180005504  jmp     loc_180005597
0x180005509  mov     r9, [rsp+88h+arg_38]
0x180005511  lea     r8, aTraceAlgorithm; "TRACE: Algorithm=%hs\n"
0x180005518  mov     edx, 2; unsigned int
0x18000551d  mov     ecx, 68D12C2h; unsigned int
0x180005522  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180005527  mov     r9, [rsp+88h+arg_28]; struct _CERT_CONTEXT *
0x18000552f  lea     rax, [rsp+88h+var_48]
0x180005534  mov     r8, [rsp+88h+arg_38]; char *
0x18000553c  mov     edx, r12d; cbToBeEncrypted
0x18000553f  mov     qword ptr [rsp+88h+pcbResult], rax; unsigned int *
0x180005544  mov     rcx, rdi; pbToBeEncrypted
0x180005547  lea     rax, [rsp+88h+var_40]
0x18000554c  mov     qword ptr [rsp+88h+cbInput], rax; unsigned __int8 **
0x180005551  call    ?_EncryptContent@@YAJPEAEKPEBDPEBU_CERT_CONTEXT@@PEAPEAEPEAK@Z; _EncryptContent(uchar *,ulong,char const *,_CERT_CONTEXT const *,uchar * *,ulong *)
0x180005556  mov     ebx, eax
0x180005558  test    eax, eax
0x18000555a  jz      short loc_180005586
0x18000555c  mov     r9d, eax
0x18000555f  lea     r8, aErrorEncryptco; "ERROR: _EncryptContent. Return=%d\n"
0x180005566  mov     edx, 1; unsigned int
0x18000556b  mov     ecx, 69A12C2h; unsigned int
0x180005570  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180005575  mov     rcx, [rsp+88h+var_40]; void *
0x18000557a  test    rcx, rcx
0x18000557d  jz      short loc_180005597
0x18000557f  call    MIDL_user_free
0x180005584  jmp     short loc_180005597
0x180005586  mov     rax, [rsp+88h+var_40]
0x18000558b  xor     ebx, ebx
0x18000558d  mov     [rsi], rax
0x180005590  mov     eax, [rsp+88h+var_48]
0x180005594  mov     [r14], eax
0x180005597  test    rdi, rdi
0x18000559a  jz      loc_180005495
0x1800055a0  mov     rdx, r12
0x1800055a3  mov     rax, rdi
0x1800055a6  test    r12d, r12d
0x1800055a9  jz      short loc_1800055BD
0x1800055ab  nop     dword ptr [rax+rax+00h]
0x1800055b0  mov     byte ptr [rax], 0
0x1800055b3  lea     rax, [rax+1]
0x1800055b7  sub     rdx, 1
0x1800055bb  jnz     short loc_1800055B0
0x1800055bd  mov     rcx, rdi; hMem
0x1800055c0  call    cs:__imp_LocalFree
0x1800055c6  mov     eax, ebx
0x1800055c8  jmp     short loc_1800055EB
0x1800055ca  mov     r9d, 0A0h
0x1800055d0  lea     r8, aErrorArguments; "ERROR: Arguments. Return=%d\n"
0x1800055d7  mov     edx, 1; unsigned int
0x1800055dc  mov     ecx, 64C12C2h; unsigned int
0x1800055e1  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x1800055e6  mov     eax, 0A0h
0x1800055eb  mov     rbx, [rsp+88h+arg_0]
0x1800055f3  add     rsp, 60h
0x1800055f7  pop     r14
0x1800055f9  pop     r13
0x1800055fb  pop     r12
0x1800055fd  pop     rdi
0x1800055fe  pop     rsi
0x1800055ff  retn
```
