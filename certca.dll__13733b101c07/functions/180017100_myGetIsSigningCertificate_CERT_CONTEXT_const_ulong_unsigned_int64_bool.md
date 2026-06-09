# myGetIsSigningCertificate(_CERT_CONTEXT const *,ulong,unsigned __int64,bool *)

- ea: `0x180017100`
- end: `0x180017269`
- name: `?myGetIsSigningCertificate@@YAJPEBU_CERT_CONTEXT@@K_KPEA_N@Z`
- size: `361`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT *, enum X509KeySpec, NCRYPT_KEY_HANDLE, bool *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180008400`
- `0x180012450`
- `0x180013a86`
- `0x180017100`
- `0x180017270`
- `0x18001737c`
- `0x18001e080`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001724e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001724e`
- `CRYPT32!CertFindExtension` at `0x18001719f`
- `CRYPT32!CertFindExtension` at `0x18001719f`
- `ncrypt!NCryptIsKeyHandle` at `0x180017140`
- `ncrypt!NCryptIsKeyHandle` at `0x180017140`

## pseudocode

```c
__int64 __fastcall myGetIsSigningCertificate(
        const struct _CERT_CONTEXT *a1,
        enum X509KeySpec a2,
        NCRYPT_KEY_HANDLE a3,
        bool *a4)
{
  bool IsSigningKeySpec; // di
  int KeyUsageFlagFromNCryptKey; // eax
  unsigned int v9; // ebx
  unsigned int v10; // ecx
  PCERT_EXTENSION Extension; // rax
  DWORD cbData; // r9d
  const BYTE *pbData; // r8
  size_t v14; // r8
  HLOCAL v15; // rcx
  __int64 v17; // [rsp+28h] [rbp-28h]
  int v18; // [rsp+40h] [rbp-10h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-8h] BYREF
  unsigned int v20; // [rsp+88h] [rbp+38h] BYREF

  hMem = 0;
  IsSigningKeySpec = myIsSigningKeySpec(a2);
  if ( IsSigningKeySpec )
    goto LABEL_19;
  if ( !a3 || !NCryptIsKeyHandle(a3) )
    goto LABEL_9;
  v20 = 0;
  KeyUsageFlagFromNCryptKey = myGetKeyUsageFlagFromNCryptKey(a3, &v20);
  v9 = KeyUsageFlagFromNCryptKey;
  if ( !KeyUsageFlagFromNCryptKey )
  {
    if ( (v20 & 7) == 2 )
    {
      IsSigningKeySpec = 1;
      goto LABEL_19;
    }
LABEL_9:
    Extension = CertFindExtension("2.5.29.15", a1->pCertInfo->cExtension, a1->pCertInfo->rgExtension);
    if ( Extension )
    {
      cbData = Extension->Value.cbData;
      pbData = Extension->Value.pbData;
      v18 = 0;
      v20 = 0;
      if ( !myDecodeObjectEx(1u, (const CHAR *)0xE, pbData, cbData, 0, v17, &hMem, &v20) )
      {
        KeyUsageFlagFromNCryptKey = myHLastError();
        v9 = KeyUsageFlagFromNCryptKey;
        v10 = 272630180;
        goto LABEL_6;
      }
      if ( v20 && hMem && *(_DWORD *)hMem )
      {
        v14 = 4;
        if ( *(_DWORD *)hMem <= 4u )
          v14 = *(unsigned int *)hMem;
        memcpy_0(&v18, *((const void **)hMem + 1), v14);
        if ( (v18 & 0x80B9) == 0x80 )
          IsSigningKeySpec = 1;
      }
    }
LABEL_19:
    v9 = 0;
    goto LABEL_20;
  }
  v10 = 270598564;
LABEL_6:
  CSPrintErrorLineFile(v10, KeyUsageFlagFromNCryptKey);
LABEL_20:
  v15 = hMem;
  *a4 = IsSigningKeySpec;
  LocalFree(v15);
  return v9;
}

```

## disassembly

```asm
0x180017100  mov     [rsp-18h+arg_0], rbx
0x180017105  mov     [rsp-18h+arg_8], rsi
0x18001710a  push    rbp
0x18001710b  push    rdi
0x18001710c  push    r14
0x18001710e  mov     rbp, rsp
0x180017111  sub     rsp, 50h
0x180017115  mov     rsi, rcx
0x180017118  mov     [rbp+hMem], 0
0x180017120  mov     ecx, edx; enum X509KeySpec
0x180017122  mov     r14, r9
0x180017125  mov     rbx, r8
0x180017128  call    ?myIsSigningKeySpec@@YA_NW4X509KeySpec@@@Z; myIsSigningKeySpec(X509KeySpec)
0x18001712d  movzx   edi, al
0x180017130  test    al, al
0x180017132  jnz     loc_180017245
0x180017138  test    rbx, rbx
0x18001713b  jz      short loc_180017187
0x18001713d  mov     rcx, rbx; hKey
0x180017140  call    cs:__imp_NCryptIsKeyHandle
0x180017146  test    eax, eax
0x180017148  jz      short loc_180017187
0x18001714a  lea     rdx, [rbp+arg_18]; unsigned int *
0x18001714e  mov     [rbp+arg_18], 0
0x180017155  mov     rcx, rbx; unsigned __int64
0x180017158  call    ?myGetKeyUsageFlagFromNCryptKey@@YAJ_KPEAK@Z; myGetKeyUsageFlagFromNCryptKey(unsigned __int64,ulong *)
0x18001715d  mov     ebx, eax
0x18001715f  test    eax, eax
0x180017161  jz      short loc_180017174
0x180017163  mov     ecx, 102101A4h; unsigned int
0x180017168  mov     edx, eax; int
0x18001716a  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001716f  jmp     loc_180017247
0x180017174  mov     eax, [rbp+arg_18]
0x180017177  and     al, 7
0x180017179  cmp     al, 2
0x18001717b  jnz     short loc_180017187
0x18001717d  mov     edi, 1
0x180017182  jmp     loc_180017245
0x180017187  mov     rdx, [rsi+18h]
0x18001718b  lea     rcx, pszObjId; "2.5.29.15"
0x180017192  mov     r8, [rdx+0C8h]; rgExtensions
0x180017199  mov     edx, [rdx+0C0h]; cExtensions
0x18001719f  call    cs:__imp_CertFindExtension
0x1800171a5  test    rax, rax
0x1800171a8  jz      loc_180017245
0x1800171ae  mov     r9d, [rax+10h]
0x1800171b2  lea     rcx, [rbp+arg_18]
0x1800171b6  mov     r8, [rax+18h]
0x1800171ba  mov     edx, 0Eh
0x1800171bf  mov     [rsp+50h+var_18], rcx
0x1800171c4  lea     rcx, [rbp+hMem]
0x1800171c8  mov     [rsp+50h+var_20], rcx
0x1800171cd  mov     [rbp+var_10], 0
0x1800171d4  lea     ebx, [rdx-0Dh]
0x1800171d7  mov     [rbp+arg_18], 0
0x1800171de  mov     ecx, ebx
0x1800171e0  mov     [rsp+50h+var_30], 0
0x1800171e8  call    ?myDecodeObjectEx@@YAHKPEBDPEBEKKW4CERTLIB_ALLOCATOR@@PEAPEAXPEAK@Z; myDecodeObjectEx(ulong,char const *,uchar const *,ulong,ulong,CERTLIB_ALLOCATOR,void * *,ulong *)
0x1800171ed  test    eax, eax
0x1800171ef  jnz     short loc_180017202
0x1800171f1  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x1800171f6  mov     ebx, eax
0x1800171f8  mov     ecx, 104001A4h
0x1800171fd  jmp     loc_180017168
0x180017202  cmp     [rbp+arg_18], 0
0x180017206  jz      short loc_180017245
0x180017208  mov     rax, [rbp+hMem]
0x18001720c  test    rax, rax
0x18001720f  jz      short loc_180017245
0x180017211  cmp     dword ptr [rax], 0
0x180017214  jz      short loc_180017245
0x180017216  mov     r8d, 4
0x18001721c  cmp     [rax], r8d
0x18001721f  ja      short loc_180017224
0x180017221  mov     r8d, [rax]; Size
0x180017224  mov     rdx, [rbp+hMem]
0x180017228  lea     rcx, [rbp+var_10]; void *
0x18001722c  mov     rdx, [rdx+8]; Src
0x180017230  call    memcpy_0
0x180017235  mov     eax, [rbp+var_10]
0x180017238  and     eax, 80B9h
0x18001723d  cmp     eax, 80h
0x180017242  cmovz   edi, ebx
0x180017245  xor     ebx, ebx
0x180017247  mov     rcx, [rbp+hMem]; hMem
0x18001724b  mov     [r14], dil
0x18001724e  call    cs:__imp_LocalFree
0x180017254  mov     rsi, [rsp+50h+arg_8]
0x180017259  mov     eax, ebx
0x18001725b  mov     rbx, [rsp+50h+arg_0]
0x180017260  add     rsp, 50h
0x180017264  pop     r14
0x180017266  pop     rdi
0x180017267  pop     rbp
0x180017268  retn
```
