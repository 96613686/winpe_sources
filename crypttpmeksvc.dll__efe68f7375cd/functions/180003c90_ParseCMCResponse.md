# ParseCMCResponse

- ea: `0x180003c90`
- end: `0x180003e6b`
- name: `ParseCMCResponse`
- size: `475`
- prototype: `__int64 __fastcall(BYTE *, DWORD, unsigned __int8 *, struct _XCMCRESPONSE **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180009470`

## callees

- `0x180003750`
- `0x180003c90`
- `0x180003e80`
- `0x180007098`
- `0x18000a7da`
- `0x18000a800`

## import_xrefs

- `CRYPT32!CertCloseStore` at `0x180003e42`
- `CRYPT32!CertCloseStore` at `0x180003e42`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003e1f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003e2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003e1f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003e2d`

## pseudocode

```c
__int64 __fastcall ParseCMCResponse(
        BYTE *a1,
        DWORD a2,
        unsigned __int8 *a3,
        struct _XCMCRESPONSE **a4,
        unsigned int *a5)
{
  unsigned int v7; // eax
  char *v8; // rdi
  unsigned int v9; // ebx
  unsigned int v10; // r9d
  unsigned int v11; // eax
  void *v13; // [rsp+48h] [rbp-290h]
  unsigned int pvData; // [rsp+60h] [rbp-278h] BYREF
  DWORD cbEncoded; // [rsp+64h] [rbp-274h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-270h] BYREF
  HCERTSTORE hCertStore; // [rsp+70h] [rbp-268h] BYREF
  char *Str1; // [rsp+78h] [rbp-260h] BYREF
  unsigned __int16 v19[264]; // [rsp+80h] [rbp-258h] BYREF

  pvData = 0;
  Str1 = 0;
  hMem = 0;
  cbEncoded = 0;
  hCertStore = 0;
  if ( a3 )
    *(_QWORD *)a3 = 0;
  *a4 = 0;
  *a5 = 0;
  v7 = _DecodePkcs7(
         a1,
         a2,
         a3,
         (unsigned int)a4,
         (unsigned __int8 **)&hMem,
         &cbEncoded,
         &pvData,
         &Str1,
         0,
         v13,
         &hCertStore,
         0);
  v8 = Str1;
  v9 = v7;
  if ( v7 )
  {
    ekTraceFmt(0x46D12C0u, 1u, "ERROR: _DecodePkcs7 Hr=%x\n", v7);
  }
  else
  {
    v9 = -2147024883;
    if ( pvData == 2 )
    {
      if ( Str1 && !strcmp_0(Str1, "1.3.6.1.5.5.7.12.3") )
      {
        v19[0] = 0;
        v11 = _DecodeCMCResponse((BYTE *)hMem, cbEncoded, v19, v10, a4, a5);
        v9 = v11;
        if ( v11 )
        {
          ekTraceFmt(0x48712C0u, 1u, "ERROR: _DecodeCMCResponse Hr=%x\n", v11);
        }
        else
        {
          if ( a3 )
          {
            *(_QWORD *)a3 = hCertStore;
            hCertStore = 0;
          }
          v9 = 0;
        }
      }
      else
      {
        ekTraceFmt(0x47A12C0u, 1u, "ERROR: InnerContentOid pszInnerContentObjId=%s\n", v8);
      }
    }
    else
    {
      ekTraceFmt(0x47412C0u, 1u, "ERROR: MessageType MsgType=%d\n", pvData);
    }
  }
  if ( hMem )
    LocalFree(hMem);
  if ( v8 )
    LocalFree(v8);
  if ( hCertStore )
    CertCloseStore(hCertStore, 2u);
  return v9;
}

```

## disassembly

```asm
0x180003c90  push    rbx
0x180003c92  push    rbp
0x180003c93  push    rdi
0x180003c94  push    r12
0x180003c96  push    r14
0x180003c98  push    r15
0x180003c9a  sub     rsp, 2A8h
0x180003ca1  mov     rax, cs:__security_cookie
0x180003ca8  xor     rax, rsp
0x180003cab  mov     [rsp+2D8h+var_48], rax
0x180003cb3  mov     rbp, [rsp+2D8h+arg_20]
0x180003cbb  xor     r12d, r12d
0x180003cbe  mov     [rsp+2D8h+var_278], r12d
0x180003cc3  mov     r15, r9
0x180003cc6  mov     [rsp+2D8h+Str1], r12
0x180003ccb  mov     r14, r8
0x180003cce  mov     [rsp+2D8h+hMem], r12
0x180003cd3  mov     [rsp+2D8h+cbEncoded], r12d
0x180003cd8  mov     [rsp+2D8h+hCertStore], r12
0x180003cdd  test    r8, r8
0x180003ce0  jz      short loc_180003CE5
0x180003ce2  mov     [r8], r12
0x180003ce5  mov     [rsp+2D8h+var_280], r12; void **
0x180003cea  lea     rax, [rsp+2D8h+hCertStore]
0x180003cef  mov     [rsp+2D8h+var_288], rax; void **
0x180003cf4  lea     rax, [rsp+2D8h+Str1]
0x180003cf9  mov     [rsp+2D8h+var_298], r12; unsigned int *
0x180003cfe  mov     [rsp+2D8h+var_2A0], rax; char **
0x180003d03  lea     rax, [rsp+2D8h+var_278]
0x180003d08  mov     [rsp+2D8h+pvData], rax; pvData
0x180003d0d  lea     rax, [rsp+2D8h+cbEncoded]
0x180003d12  mov     [rsp+2D8h+var_2B0], rax; unsigned int *
0x180003d17  lea     rax, [rsp+2D8h+hMem]
0x180003d1c  mov     [r9], r12
0x180003d1f  mov     [rsp+2D8h+var_2B8], rax; unsigned __int8 **
0x180003d24  mov     [rbp+0], r12d
0x180003d28  call    ?_DecodePkcs7@@YAJPEBEK0KPEAPEAEPEAK2PEAPEAD22PEAPEAX4@Z; _DecodePkcs7(uchar const *,ulong,uchar const *,ulong,uchar * *,ulong *,ulong *,char * *,ulong *,ulong *,void * *,void * *)
0x180003d2d  mov     rdi, [rsp+2D8h+Str1]
0x180003d32  mov     ebx, eax
0x180003d34  test    eax, eax
0x180003d36  jz      short loc_180003D56
0x180003d38  mov     r9d, eax
0x180003d3b  lea     r8, aErrorDecodepkc; "ERROR: _DecodePkcs7 Hr=%x\n"
0x180003d42  mov     edx, 1; unsigned int
0x180003d47  mov     ecx, 46D12C0h; unsigned int
0x180003d4c  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180003d51  jmp     loc_180003E13
0x180003d56  mov     r9d, [rsp+2D8h+var_278]
0x180003d5b  mov     ebx, 8007000Dh
0x180003d60  cmp     r9d, 2
0x180003d64  jz      short loc_180003D81
0x180003d66  lea     r8, aErrorMessagety; "ERROR: MessageType MsgType=%d\n"
0x180003d6d  mov     edx, 1; unsigned int
0x180003d72  mov     ecx, 47412C0h; unsigned int
0x180003d77  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180003d7c  jmp     loc_180003E13
0x180003d81  test    rdi, rdi
0x180003d84  jz      short loc_180003DFA
0x180003d86  lea     rdx, Str2; "1.3.6.1.5.5.7.12.3"
0x180003d8d  mov     rcx, rdi; Str1
0x180003d90  call    strcmp_0
0x180003d95  test    eax, eax
0x180003d97  jnz     short loc_180003DFA
0x180003d99  mov     edx, [rsp+2D8h+cbEncoded]; cbEncoded
0x180003d9d  lea     r8, [rsp+2D8h+var_258]; unsigned __int16 *
0x180003da5  mov     rcx, [rsp+2D8h+hMem]; pbEncoded
0x180003daa  mov     [rsp+2D8h+var_2B0], rbp; unsigned int *
0x180003daf  mov     [rsp+2D8h+var_2B8], r15; struct _XCMCRESPONSE **
0x180003db4  mov     [rsp+2D8h+var_258], r12w
0x180003dbd  call    ?_DecodeCMCResponse@@YAJPEAEKPEAGKPEAPEAU_XCMCRESPONSE@@PEAK@Z; _DecodeCMCResponse(uchar *,ulong,ushort *,ulong,_XCMCRESPONSE * *,ulong *)
0x180003dc2  mov     ebx, eax
0x180003dc4  test    eax, eax
0x180003dc6  jz      short loc_180003DE3
0x180003dc8  mov     r9d, eax
0x180003dcb  lea     r8, aErrorDecodecmc; "ERROR: _DecodeCMCResponse Hr=%x\n"
0x180003dd2  mov     edx, 1; unsigned int
0x180003dd7  mov     ecx, 48712C0h; unsigned int
0x180003ddc  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180003de1  jmp     short loc_180003E13
0x180003de3  test    r14, r14
0x180003de6  jz      short loc_180003DF5
0x180003de8  mov     rax, [rsp+2D8h+hCertStore]
0x180003ded  mov     [r14], rax
0x180003df0  mov     [rsp+2D8h+hCertStore], r12
0x180003df5  mov     ebx, r12d
0x180003df8  jmp     short loc_180003E13
0x180003dfa  mov     r9, rdi
0x180003dfd  lea     r8, aErrorInnercont; "ERROR: InnerContentOid pszInnerContentO"...
0x180003e04  mov     edx, 1; unsigned int
0x180003e09  mov     ecx, 47A12C0h; unsigned int
0x180003e0e  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180003e13  cmp     [rsp+2D8h+hMem], r12
0x180003e18  jz      short loc_180003E25
0x180003e1a  mov     rcx, [rsp+2D8h+hMem]; hMem
0x180003e1f  call    cs:__imp_LocalFree
0x180003e25  test    rdi, rdi
0x180003e28  jz      short loc_180003E33
0x180003e2a  mov     rcx, rdi; hMem
0x180003e2d  call    cs:__imp_LocalFree
0x180003e33  mov     rcx, [rsp+2D8h+hCertStore]; hCertStore
0x180003e38  test    rcx, rcx
0x180003e3b  jz      short loc_180003E48
0x180003e3d  mov     edx, 2; dwFlags
0x180003e42  call    cs:__imp_CertCloseStore
0x180003e48  mov     eax, ebx
0x180003e4a  mov     rcx, [rsp+2D8h+var_48]
0x180003e52  xor     rcx, rsp; StackCookie
0x180003e55  call    __security_check_cookie
0x180003e5a  add     rsp, 2A8h
0x180003e61  pop     r15
0x180003e63  pop     r14
0x180003e65  pop     r12
0x180003e67  pop     rdi
0x180003e68  pop     rbp
0x180003e69  pop     rbx
0x180003e6a  retn
```
