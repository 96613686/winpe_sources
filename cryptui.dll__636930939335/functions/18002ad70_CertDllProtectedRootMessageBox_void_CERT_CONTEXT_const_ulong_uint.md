# CertDllProtectedRootMessageBox(void *,_CERT_CONTEXT const *,ulong,uint)

- ea: `0x18002ad70`
- end: `0x18002af34`
- name: `?CertDllProtectedRootMessageBox@@YAHPEAXPEBU_CERT_CONTEXT@@KI@Z`
- size: `452`
- prototype: `int(void *, const struct _CERT_CONTEXT *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180001f66`
- `0x18002ad70`
- `0x18002af3c`
- `0x18002b074`
- `0x18002b1ac`
- `0x18003a054`
- `0x18003a090`
- `0x18003e5c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aeed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aeed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002adba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002adba`
- `USER32!MessageBoxW` at `0x18002aec1`
- `USER32!MessageBoxW` at `0x18002aec1`
- `RPCRT4!RpcRevertToSelf` at `0x18002af01`
- `RPCRT4!RpcRevertToSelf` at `0x18002af01`
- `RPCRT4!RpcImpersonateClient` at `0x18002addd`
- `RPCRT4!RpcImpersonateClient` at `0x18002addd`

## pseudocode

```c
__int64 __fastcall CertDllProtectedRootMessageBox(void *a1, const struct _CERT_CONTEXT *a2, int a3, int a4)
{
  int v6; // r8d
  int v8; // ebp
  RPC_STATUS v9; // r13d
  int v10; // ebx
  unsigned int v11; // eax
  unsigned int v12; // ecx
  unsigned int i; // edi
  __int64 v14; // rax
  WCHAR *v15; // r15
  unsigned int v16; // esi
  _WORD *j; // r14
  unsigned int v18; // eax
  size_t v19; // rbx
  int v20; // eax
  unsigned int v21; // ebx
  void *v22; // rcx
  void *Src[20]; // [rsp+30h] [rbp-E8h] BYREF

  v6 = a3 - 1;
  if ( v6 )
  {
    if ( v6 != 1 )
    {
      SetLastError(0x80070057);
      return 2;
    }
    v8 = 3509;
  }
  else
  {
    v8 = 3508;
  }
  v9 = 0;
  v10 = 0;
  if ( a1 )
    v9 = RpcImpersonateClient(a1);
  if ( v8 == 3508 )
    v11 = I_FormatAddRootBoxItems(a2, (LPWSTR)Src);
  else
    v11 = I_FormatRootBoxItems(a2);
  v12 = 0;
  for ( i = v11; v12 < v11; ++v12 )
  {
    if ( Src[2 * v12] )
      v10 += LODWORD(Src[2 * v12 + 1]);
    else
      LODWORD(Src[2 * v12 + 1]) = 0;
  }
  v14 = PkiNonzeroAlloc(2LL * (unsigned int)(v10 + 1));
  v15 = (WCHAR *)v14;
  if ( v14 )
  {
    v16 = 0;
    for ( j = (_WORD *)v14; v16 < i; ++v16 )
    {
      v18 = (unsigned int)Src[2 * v16 + 1];
      if ( v18 )
      {
        v19 = 2LL * v18;
        memcpy_0(j, Src[2 * v16], v19);
        j = (_WORD *)((char *)j + v19);
      }
    }
    *j = 0;
    FormatMsgBoxItem((LPWSTR)&Src[2 * i]);
    v20 = MessageBoxW(0, v15, (LPCWSTR)Src[2 * i++], a4 | 0x40134);
    v21 = v20;
    PkiFree(v15);
  }
  else
  {
    v21 = 7;
  }
  while ( i )
  {
    v22 = Src[2 * --i];
    if ( v22 )
      LocalFree(v22);
  }
  if ( a1 )
  {
    if ( !v9 )
      RpcRevertToSelf();
  }
  return v21;
}

```

## disassembly

```asm
0x18002ad70  mov     [rsp+arg_10], rbx
0x18002ad75  push    rbp
0x18002ad76  push    rsi
0x18002ad77  push    rdi
0x18002ad78  push    r12
0x18002ad7a  push    r13
0x18002ad7c  push    r14
0x18002ad7e  push    r15
0x18002ad80  sub     rsp, 0E0h
0x18002ad87  mov     rax, cs:__security_cookie
0x18002ad8e  xor     rax, rsp
0x18002ad91  mov     [rsp+118h+var_48], rax
0x18002ad99  mov     [rsp+118h+var_F8], r9d
0x18002ad9e  mov     rdi, rdx
0x18002ada1  mov     r12, rcx
0x18002ada4  mov     esi, 0DB4h
0x18002ada9  sub     r8d, 1
0x18002adad  jz      short loc_18002ADD1
0x18002adaf  cmp     r8d, 1
0x18002adb3  jz      short loc_18002ADCA
0x18002adb5  mov     ecx, 80070057h; dwErrCode
0x18002adba  call    cs:__imp_SetLastError
0x18002adc0  mov     eax, 2
0x18002adc5  jmp     loc_18002AF09
0x18002adca  mov     ebp, 0DB5h
0x18002adcf  jmp     short loc_18002ADD3
0x18002add1  mov     ebp, esi
0x18002add3  xor     r13d, r13d
0x18002add6  xor     ebx, ebx
0x18002add8  test    r12, r12
0x18002addb  jz      short loc_18002ADE6
0x18002addd  call    cs:__imp_RpcImpersonateClient
0x18002ade3  mov     r13d, eax
0x18002ade6  mov     rcx, rdi; pCertContext
0x18002ade9  cmp     ebp, esi
0x18002adeb  jnz     short loc_18002ADF9
0x18002aded  lea     rdx, [rsp+118h+Src]; lpBuffer
0x18002adf2  call    I_FormatAddRootBoxItems
0x18002adf7  jmp     short loc_18002AE05
0x18002adf9  lea     r8, [rsp+118h+Src]
0x18002adfe  mov     edx, ebp
0x18002ae00  call    I_FormatRootBoxItems
0x18002ae05  xor     ecx, ecx
0x18002ae07  mov     edi, eax
0x18002ae09  test    eax, eax
0x18002ae0b  jz      short loc_18002AE2F
0x18002ae0d  mov     eax, ecx
0x18002ae0f  shl     rax, 4
0x18002ae13  cmp     [rsp+rax+118h+Src], 0
0x18002ae19  jz      short loc_18002AE21
0x18002ae1b  add     ebx, [rsp+rax+118h+var_E0]
0x18002ae1f  jmp     short loc_18002AE29
0x18002ae21  mov     [rsp+rax+118h+var_E0], 0
0x18002ae29  inc     ecx
0x18002ae2b  cmp     ecx, edi
0x18002ae2d  jb      short loc_18002AE0D
0x18002ae2f  lea     ecx, [rbx+1]
0x18002ae32  add     rcx, rcx; uBytes
0x18002ae35  call    PkiNonzeroAlloc
0x18002ae3a  mov     r15, rax
0x18002ae3d  test    rax, rax
0x18002ae40  jz      loc_18002AED5
0x18002ae46  xor     esi, esi
0x18002ae48  mov     r14, rax
0x18002ae4b  test    edi, edi
0x18002ae4d  jz      short loc_18002AE7A
0x18002ae4f  mov     edx, esi
0x18002ae51  add     rdx, rdx
0x18002ae54  mov     eax, [rsp+rdx*8+118h+var_E0]
0x18002ae58  test    eax, eax
0x18002ae5a  jz      short loc_18002AE74
0x18002ae5c  mov     rdx, [rsp+rdx*8+118h+Src]; Src
0x18002ae61  mov     ebx, eax
0x18002ae63  add     rbx, rbx
0x18002ae66  mov     rcx, r14; void *
0x18002ae69  mov     r8, rbx; Size
0x18002ae6c  call    memcpy_0
0x18002ae71  add     r14, rbx
0x18002ae74  inc     esi
0x18002ae76  cmp     esi, edi
0x18002ae78  jb      short loc_18002AE4F
0x18002ae7a  xor     eax, eax
0x18002ae7c  lea     rbx, [rsp+118h+Src]
0x18002ae81  mov     [r14], ax
0x18002ae85  mov     eax, edi
0x18002ae87  shl     rax, 4
0x18002ae8b  add     rbx, rax
0x18002ae8e  mov     eax, 0DACh
0x18002ae93  cmp     ebp, 0DB4h
0x18002ae99  mov     rcx, rbx; lpBuffer
0x18002ae9c  lea     r8d, [rax+14h]
0x18002aea0  cmovnz  r8d, eax
0x18002aea4  lea     rdx, [rbx+8]
0x18002aea8  call    FormatMsgBoxItem
0x18002aead  mov     r9d, [rsp+118h+var_F8]
0x18002aeb2  mov     rdx, r15; lpText
0x18002aeb5  mov     r8, [rbx]; lpCaption
0x18002aeb8  or      r9d, 40134h; uType
0x18002aebf  xor     ecx, ecx; hWnd
0x18002aec1  call    cs:__imp_MessageBoxW
0x18002aec7  mov     rcx, r15; hMem
0x18002aeca  inc     edi
0x18002aecc  mov     ebx, eax
0x18002aece  call    PkiFree
0x18002aed3  jmp     short loc_18002AEF3
0x18002aed5  mov     ebx, 7
0x18002aeda  jmp     short loc_18002AEF3
0x18002aedc  dec     edi
0x18002aede  mov     eax, edi
0x18002aee0  add     rax, rax
0x18002aee3  mov     rcx, [rsp+rax*8+118h+Src]; hMem
0x18002aee8  test    rcx, rcx
0x18002aeeb  jz      short loc_18002AEF3
0x18002aeed  call    cs:__imp_LocalFree
0x18002aef3  test    edi, edi
0x18002aef5  jnz     short loc_18002AEDC
0x18002aef7  test    r12, r12
0x18002aefa  jz      short loc_18002AF07
0x18002aefc  test    r13d, r13d
0x18002aeff  jnz     short loc_18002AF07
0x18002af01  call    cs:__imp_RpcRevertToSelf
0x18002af07  mov     eax, ebx
0x18002af09  mov     rcx, [rsp+118h+var_48]
0x18002af11  xor     rcx, rsp; StackCookie
0x18002af14  call    __security_check_cookie
0x18002af19  mov     rbx, [rsp+118h+arg_10]
0x18002af21  add     rsp, 0E0h
0x18002af28  pop     r15
0x18002af2a  pop     r14
0x18002af2c  pop     r13
0x18002af2e  pop     r12
0x18002af30  pop     rdi
0x18002af31  pop     rsi
0x18002af32  pop     rbp
0x18002af33  retn
```
