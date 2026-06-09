# CFveApi::CreateNbp(_CERT_CONTEXT const *)

- ea: `0x1800d0dc8`
- end: `0x1800d0fe8`
- name: `?CreateNbp@CFveApi@@AEAAJPEBU_CERT_CONTEXT@@@Z`
- size: `544`
- prototype: `__int64 __fastcall(CFveApi *__hidden this, const struct _CERT_CONTEXT *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180058a40`

## callees

- `0x1800b1450`
- `0x1800d0dc8`
- `0x1800d0ff0`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d0fb4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d0fb4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d0f9e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d0f9e`
- `bcrypt!BCryptDestroyKey` at `0x1800d0f62`
- `bcrypt!BCryptDestroyKey` at `0x1800d0f62`
- `FVECERTS!FveCertGetPublicKeyHandle` at `0x1800d0e89`
- `FVECERTS!FveCertGetPublicKeyHandle` at `0x1800d0e89`
- `FVECERTS!FveCertFreeCertInfo` at `0x1800d0f81`
- `FVECERTS!FveCertFreeCertInfo` at `0x1800d0f81`
- `FVECERTS!FveCertCreateCertInfo` at `0x1800d0eac`
- `FVECERTS!FveCertCreateCertInfo` at `0x1800d0eac`

## pseudocode

```c
__int64 __fastcall CFveApi::CreateNbp(CFveApi *this, const struct _CERT_CONTEXT *a2)
{
  int PublicKeyHandle; // ebx
  HANDLE ProcessHeap; // rax
  BCRYPT_KEY_HANDLE hKey; // [rsp+30h] [rbp-2C8h] BYREF
  __int64 v8; // [rsp+38h] [rbp-2C0h] BYREF
  __int128 v9; // [rsp+40h] [rbp-2B8h] BYREF
  LPVOID lpMem[2]; // [rsp+50h] [rbp-2A8h]
  __int128 v11; // [rsp+60h] [rbp-298h]
  __int64 v12; // [rsp+70h] [rbp-288h]
  _DWORD v13[4]; // [rsp+80h] [rbp-278h] BYREF
  BCRYPT_KEY_HANDLE v14; // [rsp+90h] [rbp-268h]
  int v15; // [rsp+98h] [rbp-260h]
  __int64 v16; // [rsp+A0h] [rbp-258h]
  struct _GUID v17; // [rsp+2D0h] [rbp-28h] BYREF
  _DWORD *v18; // [rsp+2E0h] [rbp-18h] BYREF

  memset_0(v13, 0, 0x248u);
  hKey = 0;
  v8 = 0;
  v18 = 0;
  v9 = 0;
  *(_OWORD *)lpMem = 0;
  v11 = 0;
  v12 = 0;
  v17 = 0;
  if ( a2 )
  {
    v13[0] = 40;
    v13[1] = 1;
    v13[3] = 5;
    v13[2] = 33;
    PublicKeyHandle = FveCertGetPublicKeyHandle(a2, &hKey);
    if ( PublicKeyHandle >= 0 )
    {
      PublicKeyHandle = FveCertCreateCertInfo(a2, 8, &v8);
      if ( PublicKeyHandle >= 0 )
      {
        v14 = hKey;
        v16 = v8;
        v15 = *(_DWORD *)(v8 + 4);
        v18 = v13;
        *(_QWORD *)&v9 = 0x100000038LL;
        *((_QWORD *)&v9 + 1) = 0x100200000LL;
        lpMem[0] = &v18;
        lpMem[1] = 0;
        PublicKeyHandle = CFveApi::AddAuthMethodInformation(
                            this,
                            (const struct _FVE_AUTH_INFORMATION *)&v9,
                            &v17,
                            1,
                            0,
                            0);
      }
    }
  }
  else
  {
    PublicKeyHandle = -2147024809;
  }
  if ( hKey )
  {
    BCryptDestroyKey(hKey);
    hKey = 0;
  }
  if ( v8 )
  {
    FveCertFreeCertInfo(v8);
    v8 = 0;
  }
  if ( lpMem[1] )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem[1]);
  }
  return (unsigned int)PublicKeyHandle;
}

```

## disassembly

```asm
0x1800d0dc8  mov     [rsp+arg_10], rbx
0x1800d0dcd  mov     [rsp+arg_18], rsi
0x1800d0dd2  push    rdi
0x1800d0dd3  sub     rsp, 2F0h
0x1800d0dda  mov     rax, cs:__security_cookie
0x1800d0de1  xor     rax, rsp
0x1800d0de4  mov     [rsp+2F8h+var_10], rax
0x1800d0dec  mov     rdi, rdx
0x1800d0def  mov     rsi, rcx
0x1800d0df2  xor     edx, edx; Val
0x1800d0df4  mov     r8d, 248h; Size
0x1800d0dfa  lea     rcx, [rsp+2F8h+var_278]; void *
0x1800d0e02  call    memset_0
0x1800d0e07  mov     [rsp+2F8h+hKey], 0
0x1800d0e10  mov     [rsp+2F8h+var_2C0], 0
0x1800d0e19  mov     [rsp+2F8h+var_18], 0
0x1800d0e25  xorps   xmm0, xmm0
0x1800d0e28  xor     eax, eax
0x1800d0e2a  movups  [rsp+2F8h+var_2B8], xmm0
0x1800d0e2f  movups  xmmword ptr [rsp+2F8h+lpMem], xmm0
0x1800d0e34  movups  [rsp+2F8h+var_298], xmm0
0x1800d0e39  mov     [rsp+2F8h+var_288], rax
0x1800d0e3e  movups  xmmword ptr [rsp+2F8h+var_28.Data1], xmm0
0x1800d0e46  test    rdi, rdi
0x1800d0e49  jnz     short loc_1800D0E55
0x1800d0e4b  mov     ebx, 80070057h
0x1800d0e50  jmp     loc_1800D0F58
0x1800d0e55  mov     [rsp+2F8h+var_278], 28h ; '('
0x1800d0e60  mov     [rsp+2F8h+var_274], 1
0x1800d0e6b  mov     [rsp+2F8h+var_26C], 5
0x1800d0e76  mov     [rsp+2F8h+var_270], 21h ; '!'
0x1800d0e81  lea     rdx, [rsp+2F8h+hKey]
0x1800d0e86  mov     rcx, rdi
0x1800d0e89  call    cs:__imp_FveCertGetPublicKeyHandle
0x1800d0e90  nop     dword ptr [rax+rax+00h]
0x1800d0e95  mov     ebx, eax
0x1800d0e97  test    eax, eax
0x1800d0e99  js      loc_1800D0F58
0x1800d0e9f  lea     r8, [rsp+2F8h+var_2C0]
0x1800d0ea4  mov     edx, 8
0x1800d0ea9  mov     rcx, rdi
0x1800d0eac  call    cs:__imp_FveCertCreateCertInfo
0x1800d0eb3  nop     dword ptr [rax+rax+00h]
0x1800d0eb8  mov     ebx, eax
0x1800d0eba  test    eax, eax
0x1800d0ebc  js      loc_1800D0F58
0x1800d0ec2  mov     rax, [rsp+2F8h+hKey]
0x1800d0ec7  mov     [rsp+2F8h+var_268], rax
0x1800d0ecf  mov     rax, [rsp+2F8h+var_2C0]
0x1800d0ed4  mov     [rsp+2F8h+var_258], rax
0x1800d0edc  mov     eax, [rax+4]
0x1800d0edf  mov     [rsp+2F8h+var_260], eax
0x1800d0ee6  lea     rax, [rsp+2F8h+var_278]
0x1800d0eee  mov     [rsp+2F8h+var_18], rax
0x1800d0ef6  mov     dword ptr [rsp+2F8h+var_2B8], 38h ; '8'
0x1800d0efe  mov     dword ptr [rsp+2F8h+var_2B8+4], 1
0x1800d0f06  mov     dword ptr [rsp+2F8h+var_2B8+8], 200000h
0x1800d0f0e  mov     dword ptr [rsp+2F8h+var_2B8+0Ch], 1
0x1800d0f16  lea     rax, [rsp+2F8h+var_18]
0x1800d0f1e  mov     [rsp+2F8h+lpMem], rax
0x1800d0f23  mov     [rsp+2F8h+lpMem+8], 0
0x1800d0f2c  mov     [rsp+2F8h+var_2D0], 0; struct _FVE_TPM_API_SURFACE *
0x1800d0f35  mov     [rsp+2F8h+var_2D8], 0; struct _GUID *
0x1800d0f3e  mov     r9b, 1; bool
0x1800d0f41  lea     r8, [rsp+2F8h+var_28]; struct _GUID *
0x1800d0f49  lea     rdx, [rsp+2F8h+var_2B8]; struct _FVE_AUTH_INFORMATION *
0x1800d0f4e  mov     rcx, rsi; this
0x1800d0f51  call    ?AddAuthMethodInformation@CFveApi@@QEAAJPEBU_FVE_AUTH_INFORMATION@@PEAU_GUID@@_NPEBU3@PEAU_FVE_TPM_API_SURFACE@@@Z; CFveApi::AddAuthMethodInformation(_FVE_AUTH_INFORMATION const *,_GUID *,bool,_GUID const *,_FVE_TPM_API_SURFACE *)
0x1800d0f56  mov     ebx, eax
0x1800d0f58  mov     rcx, [rsp+2F8h+hKey]; hKey
0x1800d0f5d  test    rcx, rcx
0x1800d0f60  jz      short loc_1800D0F77
0x1800d0f62  call    cs:__imp_BCryptDestroyKey
0x1800d0f69  nop     dword ptr [rax+rax+00h]
0x1800d0f6e  mov     [rsp+2F8h+hKey], 0
0x1800d0f77  mov     rcx, [rsp+2F8h+var_2C0]
0x1800d0f7c  test    rcx, rcx
0x1800d0f7f  jz      short loc_1800D0F96
0x1800d0f81  call    cs:__imp_FveCertFreeCertInfo
0x1800d0f88  nop     dword ptr [rax+rax+00h]
0x1800d0f8d  mov     [rsp+2F8h+var_2C0], 0
0x1800d0f96  cmp     [rsp+2F8h+lpMem+8], 0
0x1800d0f9c  jz      short loc_1800D0FC0
0x1800d0f9e  call    cs:__imp_GetProcessHeap
0x1800d0fa5  nop     dword ptr [rax+rax+00h]
0x1800d0faa  mov     rcx, rax; hHeap
0x1800d0fad  mov     r8, [rsp+2F8h+lpMem+8]; lpMem
0x1800d0fb2  xor     edx, edx; dwFlags
0x1800d0fb4  call    cs:__imp_HeapFree
0x1800d0fbb  nop     dword ptr [rax+rax+00h]
0x1800d0fc0  mov     eax, ebx
0x1800d0fc2  mov     rcx, [rsp+2F8h+var_10]
0x1800d0fca  xor     rcx, rsp; StackCookie
0x1800d0fcd  call    __security_check_cookie
0x1800d0fd2  lea     r11, [rsp+2F8h+var_8]
0x1800d0fda  mov     rbx, [r11+20h]
0x1800d0fde  mov     rsi, [r11+28h]
0x1800d0fe2  mov     rsp, r11
0x1800d0fe5  pop     rdi
0x1800d0fe6  retn
0x180128554  push    rbp
0x180128556  sub     rsp, 30h
0x18012855a  mov     rbp, rdx
0x18012855d  mov     rcx, [rbp+30h]; hKey
0x180128561  test    rcx, rcx
0x180128564  jz      short loc_18012857A
0x180128566  call    cs:__imp_BCryptDestroyKey
0x18012856d  nop     dword ptr [rax+rax+00h]
0x180128572  mov     qword ptr [rbp+30h], 0
0x18012857a  mov     rcx, [rbp+38h]
0x18012857e  test    rcx, rcx
0x180128581  jz      short loc_180128597
0x180128583  call    cs:__imp_FveCertFreeCertInfo
0x18012858a  nop     dword ptr [rax+rax+00h]
0x18012858f  mov     qword ptr [rbp+38h], 0
0x180128597  cmp     qword ptr [rbp+58h], 0
0x18012859c  jz      short loc_1801285C0
0x18012859e  call    cs:__imp_GetProcessHeap
0x1801285a5  nop     dword ptr [rax+rax+00h]
0x1801285aa  mov     rcx, rax; hHeap
0x1801285ad  mov     r8, [rbp+58h]; lpMem
0x1801285b1  xor     edx, edx; dwFlags
0x1801285b3  call    cs:__imp_HeapFree
0x1801285ba  nop     dword ptr [rax+rax+00h]
0x1801285bf  nop
0x1801285c0  add     rsp, 30h
0x1801285c4  pop     rbp
0x1801285c5  retn
```
