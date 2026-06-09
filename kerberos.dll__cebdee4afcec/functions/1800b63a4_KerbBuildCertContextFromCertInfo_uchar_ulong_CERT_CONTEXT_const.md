# KerbBuildCertContextFromCertInfo(uchar *,ulong,_CERT_CONTEXT const * *)

- ea: `0x1800b63a4`
- end: `0x1800b65f9`
- name: `?KerbBuildCertContextFromCertInfo@@YAJPEAEKPEAPEBU_CERT_CONTEXT@@@Z`
- size: `597`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, const struct _CERT_CONTEXT **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1800b7a24`

## callees

- `0x18001018c`
- `0x1800107f8`
- `0x18008b70c`
- `0x1800b63a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b64f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b6552`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b64f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b6552`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b65a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b65a3`
- `CRYPT32!CertFindCertificateInStore` at `0x1800b6540`
- `CRYPT32!CertFindCertificateInStore` at `0x1800b6540`
- `CRYPT32!CertCloseStore` at `0x1800b6585`
- `CRYPT32!CertCloseStore` at `0x1800b6585`
- `CRYPT32!CertOpenStore` at `0x1800b64e1`
- `CRYPT32!CertOpenStore` at `0x1800b64e1`

## string_xrefs

- `0x1800b6500`: `Failed to open the cert store: %#x, LastError %#x\n`

## pseudocode

```c
__int64 __fastcall KerbBuildCertContextFromCertInfo(
        unsigned __int8 *a1,
        unsigned int a2,
        const struct _CERT_CONTEXT **a3)
{
  int v5; // eax
  int v6; // ecx
  unsigned int v7; // edi
  const char *v8; // r9
  __int64 v9; // r8
  unsigned int v10; // edx
  unsigned __int8 *v11; // rcx
  unsigned __int8 *v12; // rsi
  const wchar_t *pvPara; // rcx
  HCERTSTORE v14; // rbp
  DWORD v15; // eax
  const struct _CERT_CONTEXT *CertificateInStore; // rax
  DWORD LastError; // eax
  HANDLE v18; // rbx
  _DWORD pvFindPara[2]; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int8 *v21; // [rsp+38h] [rbp-30h]
  HANDLE hObject; // [rsp+88h] [rbp+20h] BYREF

  hObject = 0;
  pvFindPara[1] = 0;
  if ( !a1 || a2 < 8 || (v5 = *(_DWORD *)a1, *(_DWORD *)a1 != a2) )
  {
    v8 = "Invalid cert info: %#x\n";
    v9 = 3950;
    goto LABEL_28;
  }
  v6 = *((_DWORD *)a1 + 1);
  if ( v6 != 1 )
  {
    v7 = -1073741811;
    KerbTracerT::Log(
      1,
      "KerbBuildCertContextFromCertInfo",
      3957,
      "Invalid info type (%#x) in cert info: %#x\n",
      v6,
      -1073741811);
    return v7;
  }
  if ( (unsigned int)(v5 - 8) < 4 )
  {
    v8 = "hash info size in cert info is too small: %#x\n";
    v9 = 3970;
LABEL_28:
    v7 = -1073741811;
    KerbTracerT::Log(1, "KerbBuildCertContextFromCertInfo", v9, v8, -1073741811);
    return v7;
  }
  v10 = *((_DWORD *)a1 + 2);
  if ( (unsigned int)(v5 - 8) < ((unsigned __int64)v10 >> 16) + (unsigned __int16)v10 + 4LL || (v10 & 1) != 0 )
  {
    v8 = "Invalid hash info in cert info: %#x\n";
    v9 = 3980;
    goto LABEL_28;
  }
  v11 = a1 + 12;
  if ( (_WORD)v10 )
  {
    if ( *(_WORD *)&v11[2 * ((unsigned __int64)(unsigned __int16)v10 >> 1) - 2] )
    {
      v8 = "store name in cert info is not null terminated: %#x\n";
      v9 = 3992;
      goto LABEL_28;
    }
    v12 = a1 + 12;
    v11 += (unsigned __int16)v10;
  }
  else
  {
    v12 = 0;
  }
  v21 = v11;
  pvFindPara[0] = HIWORD(v10);
  v7 = KerbImpersonateClient(0, &hObject);
  if ( (v7 & 0x80000000) == 0 )
  {
    pvPara = L"MY";
    if ( v12 )
      pvPara = (const wchar_t *)v12;
    v14 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x20000u, pvPara);
    if ( v14 )
    {
      CertificateInStore = CertFindCertificateInStore(v14, 0x10001u, 0, 0x10000u, pvFindPara, 0);
      if ( CertificateInStore )
      {
        *a3 = CertificateInStore;
      }
      else
      {
        v7 = -2146893042;
        LastError = GetLastError();
        KerbTracerT::Log(
          1,
          "KerbBuildCertContextFromCertInfo",
          4045,
          "Failed to find cert in cert store : %#x, LastError %#x\n",
          -2146893042,
          LastError);
      }
      CertCloseStore(v14, 0);
    }
    else
    {
      v7 = -2146893042;
      v15 = GetLastError();
      KerbTracerT::Log(
        1,
        "KerbBuildCertContextFromCertInfo",
        4029,
        "Failed to open the cert store: %#x, LastError %#x\n",
        -2146893042,
        v15);
    }
    v18 = hObject;
    KerbRevertImpersonation(hObject);
    if ( v18 )
      CloseHandle(v18);
  }
  return v7;
}

```

## disassembly

```asm
0x1800b63a4  mov     rax, rsp
0x1800b63a7  mov     [rax+10h], rbx
0x1800b63ab  push    rbp
0x1800b63ac  push    rsi
0x1800b63ad  push    rdi
0x1800b63ae  push    r14
0x1800b63b0  push    r15
0x1800b63b2  sub     rsp, 40h
0x1800b63b6  xor     r15d, r15d
0x1800b63b9  mov     r14, r8
0x1800b63bc  mov     [rax+20h], r15
0x1800b63c0  mov     r9, rcx
0x1800b63c3  mov     [rax-34h], r15d
0x1800b63c7  test    rcx, rcx
0x1800b63ca  jz      loc_1800B65BD
0x1800b63d0  cmp     edx, 8
0x1800b63d3  jb      loc_1800B65BD
0x1800b63d9  mov     eax, [rcx]
0x1800b63db  cmp     eax, edx
0x1800b63dd  jnz     loc_1800B65BD
0x1800b63e3  mov     ecx, [rcx+4]
0x1800b63e6  lea     ebx, [r15+1]
0x1800b63ea  cmp     ecx, ebx
0x1800b63ec  jz      short loc_1800B641D
0x1800b63ee  mov     eax, 0C000000Dh
0x1800b63f3  lea     r9, aInvalidInfoTyp; "Invalid info type (%#x) in cert info: %"...
0x1800b63fa  mov     dword ptr [rsp+68h+pPrevCertContext], eax
0x1800b63fe  lea     rdx, aKerbbuildcertc; "KerbBuildCertContextFromCertInfo"
0x1800b6405  mov     dword ptr [rsp+68h+pvPara], ecx
0x1800b6409  mov     r8d, 0F75h
0x1800b640f  mov     ecx, ebx
0x1800b6411  mov     edi, eax
0x1800b6413  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b6418  jmp     loc_1800B65E6
0x1800b641d  lea     r10d, [rax-8]
0x1800b6421  cmp     r10d, 4
0x1800b6425  jnb     short loc_1800B643B
0x1800b6427  lea     r9, aHashInfoSizeIn; "hash info size in cert info is too smal"...
0x1800b642e  mov     r8d, 0F82h
0x1800b6434  mov     ecx, ebx
0x1800b6436  jmp     loc_1800B65CF
0x1800b643b  mov     edx, [r9+8]
0x1800b643f  movzx   r8d, dx
0x1800b6443  mov     eax, edx
0x1800b6445  shr     rax, 10h
0x1800b6449  mov     [rsp+68h+arg_0], edx
0x1800b644d  lea     rcx, [r8+4]
0x1800b6451  add     rcx, rax
0x1800b6454  mov     eax, r10d
0x1800b6457  cmp     rax, rcx
0x1800b645a  jb      loc_1800B65AB
0x1800b6460  test    bl, dl
0x1800b6462  jnz     loc_1800B65AB
0x1800b6468  lea     rcx, [r9+0Ch]
0x1800b646c  test    dx, dx
0x1800b646f  jz      short loc_1800B6496
0x1800b6471  mov     eax, r8d
0x1800b6474  shr     rax, 1
0x1800b6477  cmp     [rcx+rax*2-2], r15w
0x1800b647d  jz      short loc_1800B648E
0x1800b647f  lea     r9, aStoreNameInCer; "store name in cert info is not null ter"...
0x1800b6486  mov     r8d, 0F98h
0x1800b648c  jmp     short loc_1800B6434
0x1800b648e  mov     rsi, rcx
0x1800b6491  add     rcx, r8
0x1800b6494  jmp     short loc_1800B6499
0x1800b6496  mov     rsi, r15
0x1800b6499  movzx   eax, word ptr [rsp+68h+arg_0+2]
0x1800b649e  lea     rdx, [rsp+68h+hObject]; void **
0x1800b64a6  mov     [rsp+68h+var_30], rcx
0x1800b64ab  xor     ecx, ecx; struct _LUID *
0x1800b64ad  mov     [rsp+68h+pvFindPara], eax
0x1800b64b1  call    ?KerbImpersonateClient@@YAJPEAU_LUID@@PEAPEAX@Z; KerbImpersonateClient(_LUID *,void * *)
0x1800b64b6  mov     edi, eax
0x1800b64b8  test    eax, eax
0x1800b64ba  js      loc_1800B65E6
0x1800b64c0  test    rsi, rsi
0x1800b64c3  lea     rcx, aMy_0; "MY"
0x1800b64ca  mov     r9d, 20000h; dwFlags
0x1800b64d0  cmovnz  rcx, rsi
0x1800b64d4  xor     edx, edx; dwEncodingType
0x1800b64d6  mov     [rsp+68h+pvPara], rcx; pvPara
0x1800b64db  xor     r8d, r8d; hCryptProv
0x1800b64de  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x1800b64e1  call    cs:__imp_CertOpenStore
0x1800b64e7  mov     rbp, rax
0x1800b64ea  test    rax, rax
0x1800b64ed  jnz     short loc_1800B6521
0x1800b64ef  mov     esi, 8009030Eh
0x1800b64f4  mov     edi, esi
0x1800b64f6  call    cs:__imp_GetLastError
0x1800b64fc  mov     dword ptr [rsp+68h+pPrevCertContext], eax
0x1800b6500  lea     r9, aFailedToOpenTh_0; "Failed to open the cert store: %#x, Las"...
0x1800b6507  mov     r8d, 0FBDh
0x1800b650d  mov     dword ptr [rsp+68h+pvPara], esi
0x1800b6511  lea     rdx, aKerbbuildcertc; "KerbBuildCertContextFromCertInfo"
0x1800b6518  mov     ecx, ebx
0x1800b651a  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b651f  jmp     short loc_1800B658B
0x1800b6521  mov     r9d, 10000h; dwFindType
0x1800b6527  mov     [rsp+68h+pPrevCertContext], r15; pPrevCertContext
0x1800b652c  lea     rax, [rsp+68h+pvFindPara]
0x1800b6531  xor     r8d, r8d; dwFindFlags
0x1800b6534  mov     rcx, rbp; hCertStore
0x1800b6537  mov     [rsp+68h+pvPara], rax; pvFindPara
0x1800b653c  lea     edx, [r9+1]; dwCertEncodingType
0x1800b6540  call    cs:__imp_CertFindCertificateInStore
0x1800b6546  test    rax, rax
0x1800b6549  jnz     short loc_1800B657D
0x1800b654b  mov     esi, 8009030Eh
0x1800b6550  mov     edi, esi
0x1800b6552  call    cs:__imp_GetLastError
0x1800b6558  mov     dword ptr [rsp+68h+pPrevCertContext], eax
0x1800b655c  lea     r9, aFailedToFindCe_0; "Failed to find cert in cert store : %#x"...
0x1800b6563  mov     r8d, 0FCDh
0x1800b6569  mov     dword ptr [rsp+68h+pvPara], esi
0x1800b656d  lea     rdx, aKerbbuildcertc; "KerbBuildCertContextFromCertInfo"
0x1800b6574  mov     ecx, ebx
0x1800b6576  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b657b  jmp     short loc_1800B6580
0x1800b657d  mov     [r14], rax
0x1800b6580  xor     edx, edx; dwFlags
0x1800b6582  mov     rcx, rbp; hCertStore
0x1800b6585  call    cs:__imp_CertCloseStore
0x1800b658b  mov     rbx, [rsp+68h+hObject]
0x1800b6593  mov     rcx, rbx; Token
0x1800b6596  call    ?KerbRevertImpersonation@@YAXPEAX@Z; KerbRevertImpersonation(void *)
0x1800b659b  test    rbx, rbx
0x1800b659e  jz      short loc_1800B65E6
0x1800b65a0  mov     rcx, rbx; hObject
0x1800b65a3  call    cs:__imp_CloseHandle
0x1800b65a9  jmp     short loc_1800B65E6
0x1800b65ab  lea     r9, aInvalidHashInf; "Invalid hash info in cert info: %#x\n"
0x1800b65b2  mov     r8d, 0F8Ch
0x1800b65b8  jmp     loc_1800B6434
0x1800b65bd  lea     r9, aInvalidCertInf; "Invalid cert info: %#x\n"
0x1800b65c4  mov     r8d, 0F6Eh
0x1800b65ca  mov     ecx, 1
0x1800b65cf  mov     eax, 0C000000Dh
0x1800b65d4  lea     rdx, aKerbbuildcertc; "KerbBuildCertContextFromCertInfo"
0x1800b65db  mov     edi, eax
0x1800b65dd  mov     dword ptr [rsp+68h+pvPara], eax
0x1800b65e1  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b65e6  mov     rbx, [rsp+68h+arg_8]
0x1800b65eb  mov     eax, edi
0x1800b65ed  add     rsp, 40h
0x1800b65f1  pop     r15
0x1800b65f3  pop     r14
0x1800b65f5  pop     rdi
0x1800b65f6  pop     rsi
0x1800b65f7  pop     rbp
0x1800b65f8  retn
```
