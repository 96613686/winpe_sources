# _IsValidCASignatureForMachine(_CERT_CONTEXT const *,void *)

- ea: `0x180006080`
- end: `0x1800061ee`
- name: `?_IsValidCASignatureForMachine@@YAJPEBU_CERT_CONTEXT@@PEAX@Z`
- size: `366`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT *, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800062f8`

## callees

- `0x180001140`
- `0x180003750`
- `0x180006080`

## import_xrefs

- `CRYPT32!CertFindExtension` at `0x1800060fb`
- `CRYPT32!CertFindExtension` at `0x1800060fb`
- `CRYPT32!CryptDecodeObjectEx` at `0x18000613d`
- `CRYPT32!CryptDecodeObjectEx` at `0x18000613d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800061a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800061a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006147`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006147`

## pseudocode

```c
__int64 __fastcall _IsValidCASignatureForMachine(const struct _CERT_CONTEXT *a1, void *a2)
{
  unsigned int v3; // eax
  unsigned int v4; // ebx
  bool v5; // si
  PCERT_EXTENSION Extension; // rax
  signed int LastError; // eax
  const char *v8; // r8
  unsigned int v9; // ecx
  void *dwFlags; // [rsp+20h] [rbp-28h]
  DWORD pcbStructInfo; // [rsp+60h] [rbp+18h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp+20h] BYREF

  v3 = _VerifyCertContext(0, a1, 0, 0, dwFlags, a2);
  v4 = v3;
  if ( !v3 )
  {
    v5 = 0;
    hMem = 0;
    pcbStructInfo = 0;
    if ( a1 )
    {
      Extension = CertFindExtension("2.5.29.19", a1->pCertInfo->cExtension, a1->pCertInfo->rgExtension);
      if ( Extension )
      {
        if ( !CryptDecodeObjectEx(
                1u,
                (LPCSTR)0xF,
                Extension->Value.pbData,
                Extension->Value.cbData,
                0x8000u,
                0,
                &hMem,
                &pcbStructInfo) )
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError > 0 )
            v4 = (unsigned __int16)LastError | 0x80070000;
          ekTraceFmt(0x16D12C3u, 1u, "ERROR: CryptDecodeObjectEx Hr=%x\n", v4);
LABEL_12:
          if ( hMem )
            LocalFree(hMem);
          if ( v4 )
          {
            v8 = "ERROR: IsCaCert Hr=%x\n";
            v9 = 26612419;
          }
          else
          {
            if ( v5 )
              return v4;
            v4 = -2146885589;
            v8 = "ERROR: BasicConstraintsNotCa Hr=%x\n";
            v9 = 27071171;
          }
          ekTraceFmt(v9, 1u, v8, v4);
          return v4;
        }
        v5 = *(_DWORD *)hMem != 0;
      }
      v4 = 0;
      goto LABEL_12;
    }
    v4 = -2147467261;
    ekTraceFmt(0x15612C3u, 1u, "ERROR: InvalidParameter Hr=%x\n", 2147500035LL);
    goto LABEL_12;
  }
  ekTraceFmt(0x18F12C3u, 1u, "ERROR: _VerifyCertContext Hr=%x\n", v3);
  return v4;
}

```

## disassembly

```asm
0x180006080  mov     [rsp+arg_0], rbx
0x180006085  mov     [rsp+arg_8], rsi
0x18000608a  push    rdi
0x18000608b  sub     rsp, 40h
0x18000608f  mov     [rsp+48h+pDecodePara], rdx; void *
0x180006094  mov     rdi, rcx
0x180006097  mov     rdx, rcx; struct _CERT_CONTEXT *
0x18000609a  xor     r9d, r9d; char **
0x18000609d  xor     ecx, ecx; bool
0x18000609f  xor     r8d, r8d; unsigned int
0x1800060a2  call    ?_VerifyCertContext@@YAJ_NPEBU_CERT_CONTEXT@@KPEBQEBDPEAX3@Z; _VerifyCertContext(bool,_CERT_CONTEXT const *,ulong,char const * const *,void *,void *)
0x1800060a7  mov     ebx, eax
0x1800060a9  test    eax, eax
0x1800060ab  jz      short loc_1800060C6
0x1800060ad  mov     r9d, eax
0x1800060b0  lea     r8, aErrorVerifycer_0; "ERROR: _VerifyCertContext Hr=%x\n"
0x1800060b7  mov     edx, 1
0x1800060bc  mov     ecx, 18F12C3h
0x1800060c1  jmp     loc_1800061D7
0x1800060c6  xor     sil, sil
0x1800060c9  mov     [rsp+48h+hMem], 0
0x1800060d2  mov     [rsp+48h+arg_10], 0
0x1800060da  test    rdi, rdi
0x1800060dd  jz      loc_18000617A
0x1800060e3  mov     rdx, [rdi+18h]
0x1800060e7  lea     rcx, a252919; "2.5.29.19"
0x1800060ee  mov     r8, [rdx+0C8h]; rgExtensions
0x1800060f5  mov     edx, [rdx+0C0h]; cExtensions
0x1800060fb  call    cs:__imp_CertFindExtension
0x180006101  mov     edi, 1
0x180006106  test    rax, rax
0x180006109  jz      short loc_180006176
0x18000610b  mov     r9d, [rax+10h]; cbEncoded
0x18000610f  lea     rcx, [rsp+48h+arg_10]
0x180006114  mov     r8, [rax+18h]; pbEncoded
0x180006118  lea     edx, [rdi+0Eh]; lpszStructType
0x18000611b  mov     [rsp+48h+pcbStructInfo], rcx; pcbStructInfo
0x180006120  lea     rcx, [rsp+48h+hMem]
0x180006125  mov     [rsp+48h+pvStructInfo], rcx; pvStructInfo
0x18000612a  mov     ecx, edi; dwCertEncodingType
0x18000612c  mov     [rsp+48h+pDecodePara], 0; pDecodePara
0x180006135  mov     dword ptr [rsp+48h+dwFlags], 8000h; dwFlags
0x18000613d  call    cs:__imp_CryptDecodeObjectEx
0x180006143  test    eax, eax
0x180006145  jnz     short loc_18000616A
0x180006147  call    cs:__imp_GetLastError
0x18000614d  mov     ebx, eax
0x18000614f  test    eax, eax
0x180006151  jle     short loc_18000615C
0x180006153  movzx   ebx, ax
0x180006156  or      ebx, 80070000h
0x18000615c  lea     r8, aErrorCryptdeco; "ERROR: CryptDecodeObjectEx Hr=%x\n"
0x180006163  mov     ecx, 16D12C3h
0x180006168  jmp     short loc_180006190
0x18000616a  mov     rax, [rsp+48h+hMem]
0x18000616f  cmp     dword ptr [rax], 0
0x180006172  setnz   sil
0x180006176  xor     ebx, ebx
0x180006178  jmp     short loc_18000619A
0x18000617a  mov     ebx, 80004003h
0x18000617f  lea     r8, aErrorInvalidpa; "ERROR: InvalidParameter Hr=%x\n"
0x180006186  mov     edi, 1
0x18000618b  mov     ecx, 15612C3h; unsigned int
0x180006190  mov     r9d, ebx
0x180006193  mov     edx, edi; unsigned int
0x180006195  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x18000619a  mov     rcx, [rsp+48h+hMem]; hMem
0x18000619f  test    rcx, rcx
0x1800061a2  jz      short loc_1800061AA
0x1800061a4  call    cs:__imp_LocalFree
0x1800061aa  test    ebx, ebx
0x1800061ac  jz      short loc_1800061BC
0x1800061ae  lea     r8, aErrorIscacertH; "ERROR: IsCaCert Hr=%x\n"
0x1800061b5  mov     ecx, 19612C3h
0x1800061ba  jmp     short loc_1800061D2
0x1800061bc  test    sil, sil
0x1800061bf  jnz     short loc_1800061DC
0x1800061c1  mov     ebx, 8009202Bh
0x1800061c6  lea     r8, aErrorBasiccons; "ERROR: BasicConstraintsNotCa Hr=%x\n"
0x1800061cd  mov     ecx, 19D12C3h; unsigned int
0x1800061d2  mov     edx, edi; unsigned int
0x1800061d4  mov     r9d, ebx
0x1800061d7  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x1800061dc  mov     rsi, [rsp+48h+arg_8]
0x1800061e1  mov     eax, ebx
0x1800061e3  mov     rbx, [rsp+48h+arg_0]
0x1800061e8  add     rsp, 40h
0x1800061ec  pop     rdi
0x1800061ed  retn
```
