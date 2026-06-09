# CFveApi::CreateNkp(_CERT_CONTEXT const *)

- ea: `0x1800d0ff0`
- end: `0x1800d1252`
- name: `?CreateNkp@CFveApi@@AEAAJPEBU_CERT_CONTEXT@@@Z`
- size: `610`
- prototype: `__int64 __fastcall(CFveApi *__hidden this, const struct _CERT_CONTEXT *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180019b60`

## callees

- `0x1800b1450`
- `0x1800d0ff0`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d121e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801285b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d121e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801285b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d1208`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18012859e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d1208`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18012859e`
- `bcrypt!BCryptDestroyKey` at `0x1800d11cc`
- `bcrypt!BCryptDestroyKey` at `0x180128566`
- `bcrypt!BCryptDestroyKey` at `0x1800d11cc`
- `bcrypt!BCryptDestroyKey` at `0x180128566`
- `FVECERTS!FveCertGetPublicKeyHandle` at `0x1800d10f3`
- `FVECERTS!FveCertGetPublicKeyHandle` at `0x1800d10f3`
- `FVECERTS!FveCertFreeCertInfo` at `0x1800d11eb`
- `FVECERTS!FveCertFreeCertInfo` at `0x180128583`
- `FVECERTS!FveCertFreeCertInfo` at `0x1800d11eb`
- `FVECERTS!FveCertFreeCertInfo` at `0x180128583`
- `FVECERTS!FveCertCreateCertInfo` at `0x1800d1116`
- `FVECERTS!FveCertCreateCertInfo` at `0x1800d1116`

## pseudocode

```c
__int64 __fastcall CFveApi::CreateNkp(CFveApi *this, const struct _CERT_CONTEXT *a2)
{
  int PublicKeyHandle; // ebx
  HANDLE ProcessHeap; // rax
  BCRYPT_KEY_HANDLE hKey; // [rsp+30h] [rbp-528h] BYREF
  __int64 v8; // [rsp+38h] [rbp-520h] BYREF
  __int128 v9; // [rsp+40h] [rbp-518h] BYREF
  LPVOID lpMem[2]; // [rsp+50h] [rbp-508h]
  __int128 v11; // [rsp+60h] [rbp-4F8h]
  __int64 v12; // [rsp+70h] [rbp-4E8h]
  _DWORD v13[4]; // [rsp+80h] [rbp-4D8h] BYREF
  BCRYPT_KEY_HANDLE v14; // [rsp+90h] [rbp-4C8h]
  int v15; // [rsp+98h] [rbp-4C0h]
  __int64 v16; // [rsp+A0h] [rbp-4B8h]
  struct _GUID v17; // [rsp+2D0h] [rbp-288h] BYREF
  int v18; // [rsp+2E0h] [rbp-278h] BYREF
  __int64 v19; // [rsp+2E4h] [rbp-274h]
  int v20; // [rsp+2ECh] [rbp-26Ch]
  __int128 v21; // [rsp+530h] [rbp-28h] BYREF

  memset_0(v13, 0, 0x248u);
  memset_0(&v18, 0, 0x248u);
  hKey = 0;
  v8 = 0;
  v21 = 0;
  v17 = 0;
  v9 = 0;
  *(_OWORD *)lpMem = 0;
  v11 = 0;
  v12 = 0;
  if ( a2 )
  {
    v18 = 36;
    v19 = 1;
    v20 = 3;
    *(_QWORD *)&v21 = &v18;
    v13[0] = 40;
    v13[1] = 1;
    v13[3] = 5;
    v13[2] = 5;
    PublicKeyHandle = FveCertGetPublicKeyHandle(a2, &hKey);
    if ( PublicKeyHandle >= 0 )
    {
      PublicKeyHandle = FveCertCreateCertInfo(a2, 4, &v8);
      if ( PublicKeyHandle >= 0 )
      {
        v14 = hKey;
        v16 = v8;
        v15 = *(_DWORD *)(v8 + 4);
        *((_QWORD *)&v21 + 1) = v13;
        *(_QWORD *)&v9 = 0x100000038LL;
        *((_QWORD *)&v9 + 1) = 0x200220000LL;
        lpMem[0] = &v21;
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
0x1800d0ff0  mov     [rsp+arg_10], rbx
0x1800d0ff5  mov     [rsp+arg_18], rsi
0x1800d0ffa  push    rdi
0x1800d0ffb  sub     rsp, 550h
0x1800d1002  mov     rax, cs:__security_cookie
0x1800d1009  xor     rax, rsp
0x1800d100c  mov     [rsp+558h+var_18], rax
0x1800d1014  mov     rdi, rdx
0x1800d1017  mov     rsi, rcx
0x1800d101a  mov     ebx, 248h
0x1800d101f  mov     r8d, ebx; Size
0x1800d1022  xor     edx, edx; Val
0x1800d1024  lea     rcx, [rsp+558h+var_4D8]; void *
0x1800d102c  call    memset_0
0x1800d1031  mov     r8d, ebx; Size
0x1800d1034  xor     edx, edx; Val
0x1800d1036  lea     rcx, [rsp+558h+var_278]; void *
0x1800d103e  call    memset_0
0x1800d1043  mov     [rsp+558h+hKey], 0
0x1800d104c  mov     [rsp+558h+var_520], 0
0x1800d1055  xorps   xmm0, xmm0
0x1800d1058  movups  [rsp+558h+var_28], xmm0
0x1800d1060  xorps   xmm1, xmm1
0x1800d1063  movups  xmmword ptr [rsp+558h+var_288.Data1], xmm1
0x1800d106b  xor     eax, eax
0x1800d106d  movups  [rsp+558h+var_518], xmm0
0x1800d1072  movups  xmmword ptr [rsp+558h+lpMem], xmm0
0x1800d1077  movups  [rsp+558h+var_4F8], xmm0
0x1800d107c  mov     [rsp+558h+var_4E8], rax
0x1800d1081  test    rdi, rdi
0x1800d1084  jnz     short loc_1800D1090
0x1800d1086  mov     ebx, 80070057h
0x1800d108b  jmp     loc_1800D11C2
0x1800d1090  mov     [rsp+558h+var_278], 24h ; '$'
0x1800d109b  mov     [rsp+558h+var_274], 1
0x1800d10a7  mov     [rsp+558h+var_26C], 3
0x1800d10b2  lea     rax, [rsp+558h+var_278]
0x1800d10ba  mov     qword ptr [rsp+558h+var_28], rax
0x1800d10c2  mov     [rsp+558h+var_4D8], 28h ; '('
0x1800d10cd  mov     [rsp+558h+var_4D4], 1
0x1800d10d8  mov     eax, 5
0x1800d10dd  mov     [rsp+558h+var_4CC], eax
0x1800d10e4  mov     [rsp+558h+var_4D0], eax
0x1800d10eb  lea     rdx, [rsp+558h+hKey]
0x1800d10f0  mov     rcx, rdi
0x1800d10f3  call    cs:__imp_FveCertGetPublicKeyHandle
0x1800d10fa  nop     dword ptr [rax+rax+00h]
0x1800d10ff  mov     ebx, eax
0x1800d1101  test    eax, eax
0x1800d1103  js      loc_1800D11C2
0x1800d1109  lea     r8, [rsp+558h+var_520]
0x1800d110e  mov     edx, 4
0x1800d1113  mov     rcx, rdi
0x1800d1116  call    cs:__imp_FveCertCreateCertInfo
0x1800d111d  nop     dword ptr [rax+rax+00h]
0x1800d1122  mov     ebx, eax
0x1800d1124  test    eax, eax
0x1800d1126  js      loc_1800D11C2
0x1800d112c  mov     rax, [rsp+558h+hKey]
0x1800d1131  mov     [rsp+558h+var_4C8], rax
0x1800d1139  mov     rax, [rsp+558h+var_520]
0x1800d113e  mov     [rsp+558h+var_4B8], rax
0x1800d1146  mov     eax, [rax+4]
0x1800d1149  mov     [rsp+558h+var_4C0], eax
0x1800d1150  lea     rax, [rsp+558h+var_4D8]
0x1800d1158  mov     qword ptr [rsp+558h+var_28+8], rax
0x1800d1160  mov     dword ptr [rsp+558h+var_518], 38h ; '8'
0x1800d1168  mov     dword ptr [rsp+558h+var_518+4], 1
0x1800d1170  mov     dword ptr [rsp+558h+var_518+8], 220000h
0x1800d1178  mov     dword ptr [rsp+558h+var_518+0Ch], 2
0x1800d1180  lea     rax, [rsp+558h+var_28]
0x1800d1188  mov     [rsp+558h+lpMem], rax
0x1800d118d  mov     [rsp+558h+lpMem+8], 0
0x1800d1196  mov     [rsp+558h+var_530], 0; struct _FVE_TPM_API_SURFACE *
0x1800d119f  mov     [rsp+558h+var_538], 0; struct _GUID *
0x1800d11a8  mov     r9b, 1; bool
0x1800d11ab  lea     r8, [rsp+558h+var_288]; struct _GUID *
0x1800d11b3  lea     rdx, [rsp+558h+var_518]; struct _FVE_AUTH_INFORMATION *
0x1800d11b8  mov     rcx, rsi; this
0x1800d11bb  call    ?AddAuthMethodInformation@CFveApi@@QEAAJPEBU_FVE_AUTH_INFORMATION@@PEAU_GUID@@_NPEBU3@PEAU_FVE_TPM_API_SURFACE@@@Z; CFveApi::AddAuthMethodInformation(_FVE_AUTH_INFORMATION const *,_GUID *,bool,_GUID const *,_FVE_TPM_API_SURFACE *)
0x1800d11c0  mov     ebx, eax
0x1800d11c2  mov     rcx, [rsp+558h+hKey]; hKey
0x1800d11c7  test    rcx, rcx
0x1800d11ca  jz      short loc_1800D11E1
0x1800d11cc  call    cs:__imp_BCryptDestroyKey
0x1800d11d3  nop     dword ptr [rax+rax+00h]
0x1800d11d8  mov     [rsp+558h+hKey], 0
0x1800d11e1  mov     rcx, [rsp+558h+var_520]
0x1800d11e6  test    rcx, rcx
0x1800d11e9  jz      short loc_1800D1200
0x1800d11eb  call    cs:__imp_FveCertFreeCertInfo
0x1800d11f2  nop     dword ptr [rax+rax+00h]
0x1800d11f7  mov     [rsp+558h+var_520], 0
0x1800d1200  cmp     [rsp+558h+lpMem+8], 0
0x1800d1206  jz      short loc_1800D122A
0x1800d1208  call    cs:__imp_GetProcessHeap
0x1800d120f  nop     dword ptr [rax+rax+00h]
0x1800d1214  mov     rcx, rax; hHeap
0x1800d1217  mov     r8, [rsp+558h+lpMem+8]; lpMem
0x1800d121c  xor     edx, edx; dwFlags
0x1800d121e  call    cs:__imp_HeapFree
0x1800d1225  nop     dword ptr [rax+rax+00h]
0x1800d122a  mov     eax, ebx
0x1800d122c  mov     rcx, [rsp+558h+var_18]
0x1800d1234  xor     rcx, rsp; StackCookie
0x1800d1237  call    __security_check_cookie
0x1800d123c  lea     r11, [rsp+558h+var_8]
0x1800d1244  mov     rbx, [r11+20h]
0x1800d1248  mov     rsi, [r11+28h]
0x1800d124c  mov     rsp, r11
0x1800d124f  pop     rdi
0x1800d1250  retn
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
