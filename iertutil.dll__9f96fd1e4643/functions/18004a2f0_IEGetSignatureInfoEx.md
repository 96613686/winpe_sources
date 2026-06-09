# IEGetSignatureInfoEx

- ea: `0x18004a2f0`
- end: `0x18004a48c`
- name: `IEGetSignatureInfoEx`
- size: `412`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpwstrFilename@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18004a1e0`

## callees

- `0x18004a230`
- `0x18004a2f0`
- `0x1800528c0`
- `0x180053f78`
- `0x180070edc`
- `0x180071058`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a43f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a43f`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x18004a384`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x18004a384`
- `CRYPT32!CertFreeCertificateContext` at `0x18004a3e0`
- `CRYPT32!CertFreeCertificateContext` at `0x18004a458`
- `CRYPT32!CertFreeCertificateContext` at `0x18004a3e0`
- `CRYPT32!CertFreeCertificateContext` at `0x18004a458`

## pseudocode

```c
__int64 __fastcall IEGetSignatureInfoEx(
        LPCWSTR lpwstrFilename,
        void *a2,
        unsigned int a3,
        __int64 a4,
        PCCERT_CONTEXT *a5,
        void **a6)
{
  void *File2; // r12
  int AuthenticodeSignatureInfo; // esi
  __int64 v11; // r13
  int Error; // eax

  File2 = a2;
  if ( a5 )
    *a5 = 0;
  *a6 = 0;
  if ( !lpwstrFilename || !a4 || *(_DWORD *)a4 < 0x68u || (a3 & 7) == 0 )
  {
    AuthenticodeSignatureInfo = -2147024809;
LABEL_27:
    if ( a5 )
    {
      CertFreeCertificateContext(*a5);
      *a5 = 0;
    }
    if ( *a6 )
    {
      FreeWVTStateData(*a6);
      *a6 = 0;
    }
    return (unsigned int)AuthenticodeSignatureInfo;
  }
  AuthenticodeSignatureInfo = 0;
  v11 = -1;
  *(_QWORD *)(a4 + 4) = 0;
  *(_QWORD *)(a4 + 12) = 0;
  if ( (a3 & 3) != 0 )
  {
    if ( a2 == (void *)-1LL )
    {
      File2 = (void *)CreateFile2(lpwstrFilename, 0x80000000LL, 5);
      v11 = (__int64)File2;
      if ( File2 == (void *)-1LL )
      {
        Error = ResultFromKnownLastError();
LABEL_18:
        AuthenticodeSignatureInfo = Error;
        goto LABEL_19;
      }
    }
    if ( (a3 & 1) == 0
      || (AuthenticodeSignatureInfo = GetAuthenticodeSignatureInfo(
                                        lpwstrFilename,
                                        File2,
                                        a3,
                                        (struct tagIE_SIGNATURE_INFO *)a4,
                                        a5,
                                        a6),
          AuthenticodeSignatureInfo >= 0) )
    {
      if ( (a3 & 2) != 0 && *(_DWORD *)(a4 + 4) <= 1u )
      {
        *(_QWORD *)(a4 + 4) = 0;
        if ( a5 )
        {
          CertFreeCertificateContext(*a5);
          *a5 = 0;
        }
        FreeWVTStateData(*a6);
        *a6 = 0;
        Error = GetCatalogSignatureInfo(lpwstrFilename, File2, a3, (struct tagIE_SIGNATURE_INFO *)a4, a5, a6);
        goto LABEL_18;
      }
    }
  }
LABEL_19:
  *(_DWORD *)(a4 + 16) = *(_DWORD *)(a4 + 12);
  if ( AuthenticodeSignatureInfo >= 0 && (a3 & 4) != 0 )
    AuthenticodeSignatureInfo = FillVersionInformation(lpwstrFilename, (struct tagIE_SIGNATURE_INFO *)a4);
  if ( v11 != -1 )
    CloseHandle((HANDLE)v11);
  if ( AuthenticodeSignatureInfo < 0 )
    goto LABEL_27;
  return (unsigned int)AuthenticodeSignatureInfo;
}

```

## disassembly

```asm
0x18004a2f0  push    rbx
0x18004a2f2  push    rbp
0x18004a2f3  push    rsi
0x18004a2f4  push    rdi
0x18004a2f5  push    r12
0x18004a2f7  push    r13
0x18004a2f9  push    r14
0x18004a2fb  push    r15
0x18004a2fd  sub     rsp, 38h
0x18004a301  mov     rdi, [rsp+78h+arg_20]
0x18004a309  mov     rbx, r9
0x18004a30c  mov     ebp, r8d
0x18004a30f  mov     r12, rdx
0x18004a312  mov     r15, rcx
0x18004a315  test    rdi, rdi
0x18004a318  jz      short loc_18004A321
0x18004a31a  mov     qword ptr [rdi], 0
0x18004a321  mov     r14, [rsp+78h+arg_28]
0x18004a329  mov     qword ptr [r14], 0
0x18004a330  test    r15, r15
0x18004a333  jz      loc_18004A44B
0x18004a339  test    rbx, rbx
0x18004a33c  jz      loc_18004A44B
0x18004a342  cmp     dword ptr [r9], 68h ; 'h'
0x18004a346  jb      loc_18004A44B
0x18004a34c  test    bpl, 7
0x18004a350  jz      loc_18004A44B
0x18004a356  xor     esi, esi
0x18004a358  or      r13, 0FFFFFFFFFFFFFFFFh
0x18004a35c  mov     [r9+4], rsi
0x18004a360  mov     [r9+0Ch], rsi
0x18004a364  lea     r9d, [rsi+3]
0x18004a368  test    r9b, bpl
0x18004a36b  jz      loc_18004A419
0x18004a371  cmp     rdx, r13
0x18004a374  jnz     short loc_18004A39D
0x18004a376  mov     edx, 80000000h
0x18004a37b  mov     [rsp+78h+var_58], rsi
0x18004a380  lea     r8d, [rsi+5]
0x18004a384  call    cs:__imp_CreateFile2
0x18004a38a  mov     r12, rax
0x18004a38d  mov     r13, rax
0x18004a390  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004a394  jnz     short loc_18004A39D
0x18004a396  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18004a39b  jmp     short loc_18004A417
0x18004a39d  test    bpl, 1
0x18004a3a1  jz      short loc_18004A3C4
0x18004a3a3  mov     [rsp+78h+var_50], r14; void **
0x18004a3a8  mov     r9, rbx; struct tagIE_SIGNATURE_INFO *
0x18004a3ab  mov     r8d, ebp; unsigned int
0x18004a3ae  mov     [rsp+78h+var_58], rdi; struct _CERT_CONTEXT **
0x18004a3b3  mov     rdx, r12; void *
0x18004a3b6  mov     rcx, r15; unsigned __int16 *
0x18004a3b9  call    ?GetAuthenticodeSignatureInfo@@YAJPEBGPEAXKPEAUtagIE_SIGNATURE_INFO@@PEAPEBU_CERT_CONTEXT@@PEAPEAX@Z; GetAuthenticodeSignatureInfo(ushort const *,void *,ulong,tagIE_SIGNATURE_INFO *,_CERT_CONTEXT const * *,void * *)
0x18004a3be  mov     esi, eax
0x18004a3c0  test    eax, eax
0x18004a3c2  js      short loc_18004A419
0x18004a3c4  test    bpl, 2
0x18004a3c8  jz      short loc_18004A419
0x18004a3ca  cmp     dword ptr [rbx+4], 1
0x18004a3ce  ja      short loc_18004A419
0x18004a3d0  mov     qword ptr [rbx+4], 0
0x18004a3d8  test    rdi, rdi
0x18004a3db  jz      short loc_18004A3ED
0x18004a3dd  mov     rcx, [rdi]; pCertContext
0x18004a3e0  call    cs:__imp_CertFreeCertificateContext
0x18004a3e6  mov     qword ptr [rdi], 0
0x18004a3ed  mov     rcx, [r14]; void *
0x18004a3f0  call    ?FreeWVTStateData@@YAXPEAX@Z; FreeWVTStateData(void *)
0x18004a3f5  mov     r9, rbx; struct tagIE_SIGNATURE_INFO *
0x18004a3f8  mov     [rsp+78h+var_50], r14; void **
0x18004a3fd  mov     r8d, ebp; unsigned int
0x18004a400  mov     qword ptr [r14], 0
0x18004a407  mov     rdx, r12; void *
0x18004a40a  mov     [rsp+78h+var_58], rdi; struct _CERT_CONTEXT **
0x18004a40f  mov     rcx, r15; unsigned __int16 *
0x18004a412  call    ?GetCatalogSignatureInfo@@YAJPEBGPEAXKPEAUtagIE_SIGNATURE_INFO@@PEAPEBU_CERT_CONTEXT@@PEAPEAX@Z; GetCatalogSignatureInfo(ushort const *,void *,ulong,tagIE_SIGNATURE_INFO *,_CERT_CONTEXT const * *,void * *)
0x18004a417  mov     esi, eax
0x18004a419  mov     eax, [rbx+0Ch]
0x18004a41c  mov     [rbx+10h], eax
0x18004a41f  test    esi, esi
0x18004a421  js      short loc_18004A436
0x18004a423  test    bpl, 4
0x18004a427  jz      short loc_18004A436
0x18004a429  mov     rdx, rbx; struct tagIE_SIGNATURE_INFO *
0x18004a42c  mov     rcx, r15; lpwstrFilename
0x18004a42f  call    ?FillVersionInformation@@YAJPEBGPEAUtagIE_SIGNATURE_INFO@@@Z; FillVersionInformation(ushort const *,tagIE_SIGNATURE_INFO *)
0x18004a434  mov     esi, eax
0x18004a436  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x18004a43a  jz      short loc_18004A445
0x18004a43c  mov     rcx, r13; hObject
0x18004a43f  call    cs:__imp_CloseHandle
0x18004a445  test    esi, esi
0x18004a447  js      short loc_18004A450
0x18004a449  jmp     short loc_18004A479
0x18004a44b  mov     esi, 80070057h
0x18004a450  test    rdi, rdi
0x18004a453  jz      short loc_18004A465
0x18004a455  mov     rcx, [rdi]; pCertContext
0x18004a458  call    cs:__imp_CertFreeCertificateContext
0x18004a45e  mov     qword ptr [rdi], 0
0x18004a465  mov     rcx, [r14]; void *
0x18004a468  test    rcx, rcx
0x18004a46b  jz      short loc_18004A479
0x18004a46d  call    ?FreeWVTStateData@@YAXPEAX@Z; FreeWVTStateData(void *)
0x18004a472  mov     qword ptr [r14], 0
0x18004a479  mov     eax, esi
0x18004a47b  add     rsp, 38h
0x18004a47f  pop     r15
0x18004a481  pop     r14
0x18004a483  pop     r13
0x18004a485  pop     r12
0x18004a487  pop     rdi
0x18004a488  pop     rsi
0x18004a489  pop     rbp
0x18004a48a  pop     rbx
0x18004a48b  retn
```
