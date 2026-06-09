# PeapGetConfigBlobAndUserBlob(ulong,_EapCredential,ulong *,uchar * *,ulong *,uchar * *)

- ea: `0x1800555d0`
- end: `0x180055899`
- name: `?PeapGetConfigBlobAndUserBlob@@YAKKU_EapCredential@@PEAKPEAPEAE12@Z`
- size: `713`
- prototype: `unsigned int __usercall@<eax>(unsigned int@<ecx>, struct _EapCredential *__struct_ptr@<rdx>, unsigned int *@<r8>, unsigned __int8 **@<r9>, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180059db0`

## callees

- `0x1800042dc`
- `0x180004bd0`
- `0x1800060f0`
- `0x18001f020`
- `0x18003623c`
- `0x1800555d0`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005568f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005568f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800556ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800556be`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800556ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800556be`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180055827`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180055827`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800557f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800557f5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180055738`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180055795`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180055738`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180055795`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055830`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005583a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055843`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005584b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055830`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005583a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055843`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005584b`

## string_xrefs

- `0x180055682`: `raschap.dll`
- `0x1800556a1`: `RasEapGetConfigBlobAndUserBlob`

## pseudocode

```c
__int64 __fastcall PeapGetConfigBlobAndUserBlob(
        unsigned int a1,
        struct _EapCredential *a2,
        unsigned int *a3,
        unsigned __int8 **a4,
        unsigned int *a5,
        unsigned __int8 **a6)
{
  _DWORD *v8; // rsi
  HLOCAL v9; // r15
  DWORD UserData; // edi
  HMODULE v11; // r14
  void (*v12)(void); // r12
  unsigned int ConnectionData; // eax
  HMODULE Library; // rax
  FARPROC ProcAddress; // rdi
  FARPROC v16; // rax
  __int128 v17; // xmm1
  LPWSTR password; // xmm0_8
  HLOCAL v19; // rax
  struct _PEAP_ENTRY_CONN_PROPERTIES *v20; // rbx
  unsigned int *v21; // r13
  unsigned __int8 *v22; // rax
  unsigned __int8 *v23; // rbx
  size_t v25; // [rsp+48h] [rbp-49h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-41h] BYREF
  void *v27; // [rsp+58h] [rbp-39h] BYREF
  void *v28; // [rsp+60h] [rbp-31h] BYREF
  void *Src; // [rsp+68h] [rbp-29h] BYREF
  struct _PEAP_ENTRY_CONN_PROPERTIES *v30; // [rsp+70h] [rbp-21h] BYREF
  _OWORD v31[2]; // [rsp+78h] [rbp-19h] BYREF
  LPWSTR v32; // [rsp+98h] [rbp+7h]
  size_t Size; // [rsp+E8h] [rbp+57h] BYREF
  unsigned int *v34; // [rsp+F8h] [rbp+67h]
  unsigned __int8 **v35; // [rsp+100h] [rbp+6Fh]

  v35 = a4;
  v34 = a3;
  Src = 0;
  v8 = 0;
  hMem = 0;
  v9 = 0;
  LODWORD(Size) = 0;
  v27 = 0;
  LODWORD(v25) = 0;
  v28 = 0;
  v30 = 0;
  if ( (a1 & 0x20) == 0 && (unsigned int)(a2->credType - 1) > 1 )
  {
    UserData = 87;
    goto LABEL_22;
  }
  v11 = 0;
  v12 = 0;
  ConnectionData = PeapReadConnectionData(a1, 0, 0, (struct _PEAP_CONN_PROPERTIES **)&Src);
  v8 = Src;
  UserData = ConnectionData;
  if ( !ConnectionData )
  {
    *((_DWORD *)Src + 6) &= ~4u;
    if ( a2->credType == EAP_USERNAME_PASSWORD_CREDENTIAL )
      v8[6] |= 0x200u;
    UserData = PeapReadUserData(0, 0, 0, (struct _PEAP_USER_PROPERTIES **)&hMem);
    if ( !UserData )
    {
      Library = LoadLibraryExW(L"raschap.dll", 0, 0x800u);
      v11 = Library;
      if ( !Library )
        goto LABEL_15;
      ProcAddress = GetProcAddress(Library, "RasEapGetConfigBlobAndUserBlob");
      v16 = GetProcAddress(v11, "RasEapFreeMemory");
      v12 = (void (*)(void))v16;
      if ( !ProcAddress || !v16 )
        goto LABEL_15;
      v17 = *(_OWORD *)(&a2->credData.sim + 1);
      v31[0] = *(_OWORD *)&a2->credType;
      password = a2->credData.certificate.password;
      v31[1] = v17;
      v32 = password;
      UserData = ((__int64 (__fastcall *)(_QWORD, __int64, _OWORD *, size_t *, void **, size_t *, void **))ProcAddress)(
                   a1,
                   26,
                   v31,
                   &Size,
                   &v27,
                   &v25,
                   &v28);
      if ( !UserData )
      {
        v19 = LocalAlloc(0x40u, (unsigned int)(Size + v8[1]));
        v9 = v19;
        if ( v19 )
        {
          memcpy_0(v19, v8, (unsigned int)v8[1]);
          PeapGetFirstEntryConnProp((struct _PEAP_CONN_PROPERTIES *)v9, &v30);
          v20 = v30;
          memcpy_0((char *)v30 + 12, v27, (unsigned int)Size);
          *((_DWORD *)v20 + 1) += Size;
          *((_DWORD *)v9 + 1) += Size;
          v21 = (unsigned int *)hMem;
          v22 = (unsigned __int8 *)LocalAlloc(UserData + 64, (unsigned int)(v25 + *((_DWORD *)hMem + 1)));
          v23 = v22;
          if ( v22 )
          {
            memcpy_0(v22, v21, v21[1]);
            memcpy_0(v23 + 56, v28, (unsigned int)v25);
            *((_DWORD *)v23 + 11) += v25;
            *((_DWORD *)v23 + 1) += v25;
            *v34 = *((_DWORD *)v9 + 1);
            *v35 = (unsigned __int8 *)v9;
            v9 = 0;
            *a5 = *((_DWORD *)v23 + 1);
            *a6 = v23;
            goto LABEL_16;
          }
        }
LABEL_15:
        UserData = GetLastError();
      }
    }
  }
LABEL_16:
  if ( v27 )
    v12();
  if ( v28 )
    v12();
  if ( v11 )
    FreeLibrary(v11);
LABEL_22:
  LocalFree(v8);
  LocalFree(hMem);
  LocalFree(v9);
  LocalFree(0);
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 891, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, UserData);
  return UserData;
}

```

## disassembly

```asm
0x1800555d0  mov     rax, rsp
0x1800555d3  mov     [rax+10h], rbx
0x1800555d7  mov     [rax+20h], r9
0x1800555db  mov     [rax+18h], r8
0x1800555df  push    rbp
0x1800555e0  push    rsi
0x1800555e1  push    rdi
0x1800555e2  push    r12
0x1800555e4  push    r13
0x1800555e6  push    r14
0x1800555e8  push    r15
0x1800555ea  lea     rbp, [rax-4Fh]
0x1800555ee  sub     rsp, 0A0h
0x1800555f5  mov     r13d, ecx
0x1800555f8  mov     rbx, rdx
0x1800555fb  xor     ecx, ecx
0x1800555fd  mov     [rbp+47h+Src], rcx
0x180055601  mov     esi, ecx
0x180055603  mov     [rbp+47h+hMem], rcx
0x180055607  mov     r15d, ecx
0x18005560a  mov     dword ptr [rbp+47h+Size], ecx
0x18005560d  mov     [rbp+47h+var_80], rcx
0x180055611  mov     dword ptr [rbp+47h+var_90], ecx
0x180055614  mov     [rbp+47h+var_78], rcx
0x180055618  mov     [rbp+47h+var_68], rcx
0x18005561c  test    r13b, 20h
0x180055620  jnz     short loc_180055633
0x180055622  mov     eax, [rdx]
0x180055624  dec     eax
0x180055626  cmp     eax, 1
0x180055629  jbe     short loc_180055633
0x18005562b  lea     edi, [rcx+57h]
0x18005562e  jmp     loc_18005582D
0x180055633  mov     r14, rcx
0x180055636  lea     r9, [rbp+47h+Src]; struct _PEAP_CONN_PROPERTIES **
0x18005563a  mov     r12, rcx
0x18005563d  xor     r8d, r8d; unsigned int
0x180055640  mov     ecx, r13d; unsigned int
0x180055643  xor     edx, edx; unsigned __int8 *
0x180055645  call    ?PeapReadConnectionData@@YAKKPEAEKPEAPEAU_PEAP_CONN_PROPERTIES@@@Z; PeapReadConnectionData(ulong,uchar *,ulong,_PEAP_CONN_PROPERTIES * *)
0x18005564a  mov     rsi, [rbp+47h+Src]
0x18005564e  mov     edi, eax
0x180055650  test    eax, eax
0x180055652  jnz     loc_1800557FD
0x180055658  and     dword ptr [rsi+18h], 0FFFFFFFBh
0x18005565c  cmp     dword ptr [rbx], 1
0x18005565f  jnz     short loc_180055666
0x180055661  bts     dword ptr [rsi+18h], 9
0x180055666  lea     r9, [rbp+47h+hMem]; struct _PEAP_USER_PROPERTIES **
0x18005566a  xor     r8d, r8d; unsigned int
0x18005566d  xor     edx, edx; unsigned __int8 *
0x18005566f  xor     ecx, ecx; int
0x180055671  call    ?PeapReadUserData@@YAKHPEAEKPEAPEAU_PEAP_USER_PROPERTIES@@@Z; PeapReadUserData(int,uchar *,ulong,_PEAP_USER_PROPERTIES * *)
0x180055676  mov     edi, eax
0x180055678  test    eax, eax
0x18005567a  jnz     loc_1800557FD
0x180055680  xor     edx, edx; hFile
0x180055682  lea     rcx, aRaschapDll; "raschap.dll"
0x180055689  mov     r8d, 800h; dwFlags
0x18005568f  call    cs:__imp_LoadLibraryExW
0x180055695  mov     r14, rax
0x180055698  test    rax, rax
0x18005569b  jz      loc_1800557F5
0x1800556a1  lea     rdx, aRaseapgetconfi_0; "RasEapGetConfigBlobAndUserBlob"
0x1800556a8  mov     rcx, rax; hModule
0x1800556ab  call    cs:__imp_GetProcAddress
0x1800556b1  lea     rdx, ProcName; "RasEapFreeMemory"
0x1800556b8  mov     rcx, r14; hModule
0x1800556bb  mov     rdi, rax
0x1800556be  call    cs:__imp_GetProcAddress
0x1800556c4  mov     r12, rax
0x1800556c7  test    rdi, rdi
0x1800556ca  jz      loc_1800557F5
0x1800556d0  test    rax, rax
0x1800556d3  jz      loc_1800557F5
0x1800556d9  movaps  xmm0, xmmword ptr [rbx]
0x1800556dc  lea     rax, [rbp+47h+var_78]
0x1800556e0  movaps  xmm1, xmmword ptr [rbx+10h]
0x1800556e4  lea     r9, [rbp+47h+Size]
0x1800556e8  mov     [rsp+30h], rax
0x1800556ed  lea     r8, [rbp+47h+var_60]
0x1800556f1  lea     rax, [rbp+47h+var_90]
0x1800556f5  movaps  [rbp+47h+var_60], xmm0
0x1800556f9  movsd   xmm0, qword ptr [rbx+20h]
0x1800556fe  mov     edx, 1Ah
0x180055703  mov     [rsp+0D0h+var_A8], rax
0x180055708  mov     ecx, r13d
0x18005570b  lea     rax, [rbp+47h+var_80]
0x18005570f  movaps  [rbp+47h+var_50], xmm1
0x180055713  mov     [rsp+0D0h+var_B0], rax
0x180055718  mov     rax, rdi
0x18005571b  movsd   [rbp+47h+var_40], xmm0
0x180055720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055725  mov     edi, eax
0x180055727  test    eax, eax
0x180055729  jnz     loc_1800557FD
0x18005572f  mov     edx, [rsi+4]
0x180055732  lea     ecx, [rax+40h]; uFlags
0x180055735  add     edx, dword ptr [rbp+47h+Size]; uBytes
0x180055738  call    cs:__imp_LocalAlloc
0x18005573e  mov     r15, rax
0x180055741  test    rax, rax
0x180055744  jz      loc_1800557F5
0x18005574a  mov     r8d, [rsi+4]; Size
0x18005574e  mov     rdx, rsi; Src
0x180055751  mov     rcx, rax; void *
0x180055754  call    memcpy_0
0x180055759  lea     rdx, [rbp+47h+var_68]; struct _PEAP_ENTRY_CONN_PROPERTIES **
0x18005575d  mov     rcx, r15; struct _PEAP_CONN_PROPERTIES *
0x180055760  call    ?PeapGetFirstEntryConnProp@@YAKPEAU_PEAP_CONN_PROPERTIES@@PEAPEFAU_PEAP_ENTRY_CONN_PROPERTIES@@@Z; PeapGetFirstEntryConnProp(_PEAP_CONN_PROPERTIES *,_PEAP_ENTRY_CONN_PROPERTIES * *)
0x180055765  mov     rbx, [rbp+47h+var_68]
0x180055769  mov     r8d, dword ptr [rbp+47h+Size]; Size
0x18005576d  mov     rdx, [rbp+47h+var_80]; Src
0x180055771  lea     rcx, [rbx+0Ch]; void *
0x180055775  call    memcpy_0
0x18005577a  mov     eax, dword ptr [rbp+47h+Size]
0x18005577d  lea     ecx, [rdi+40h]; uFlags
0x180055780  add     [rbx+4], eax
0x180055783  mov     eax, dword ptr [rbp+47h+Size]
0x180055786  add     [r15+4], eax
0x18005578a  mov     r13, [rbp+47h+hMem]
0x18005578e  mov     edx, [r13+4]
0x180055792  add     edx, dword ptr [rbp+47h+var_90]; uBytes
0x180055795  call    cs:__imp_LocalAlloc
0x18005579b  mov     rbx, rax
0x18005579e  test    rax, rax
0x1800557a1  jz      short loc_1800557F5
0x1800557a3  mov     r8d, [r13+4]; Size
0x1800557a7  mov     rdx, r13; Src
0x1800557aa  mov     rcx, rax; void *
0x1800557ad  call    memcpy_0
0x1800557b2  mov     r8d, dword ptr [rbp+47h+var_90]; Size
0x1800557b6  lea     rcx, [rbx+38h]; void *
0x1800557ba  mov     rdx, [rbp+47h+var_78]; Src
0x1800557be  call    memcpy_0
0x1800557c3  mov     eax, dword ptr [rbp+47h+var_90]
0x1800557c6  add     [rbx+2Ch], eax
0x1800557c9  mov     eax, dword ptr [rbp+47h+var_90]
0x1800557cc  add     [rbx+4], eax
0x1800557cf  mov     eax, [r15+4]
0x1800557d3  mov     rcx, [rbp+47h+arg_10]
0x1800557d7  mov     [rcx], eax
0x1800557d9  mov     rax, [rbp+47h+arg_18]
0x1800557dd  mov     [rax], r15
0x1800557e0  xor     r15d, r15d
0x1800557e3  mov     rax, [rbp+47h+arg_20]
0x1800557e7  mov     ecx, [rbx+4]
0x1800557ea  mov     [rax], ecx
0x1800557ec  mov     rax, [rbp+47h+arg_28]
0x1800557f0  mov     [rax], rbx
0x1800557f3  jmp     short loc_1800557FD
0x1800557f5  call    cs:__imp_GetLastError
0x1800557fb  mov     edi, eax
0x1800557fd  mov     rcx, [rbp+47h+var_80]
0x180055801  test    rcx, rcx
0x180055804  jz      short loc_18005580E
0x180055806  mov     rax, r12
0x180055809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005580e  mov     rcx, [rbp+47h+var_78]
0x180055812  test    rcx, rcx
0x180055815  jz      short loc_18005581F
0x180055817  mov     rax, r12
0x18005581a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005581f  test    r14, r14
0x180055822  jz      short loc_18005582D
0x180055824  mov     rcx, r14; hLibModule
0x180055827  call    cs:__imp_FreeLibrary
0x18005582d  mov     rcx, rsi; hMem
0x180055830  call    cs:__imp_LocalFree
0x180055836  mov     rcx, [rbp+47h+hMem]; hMem
0x18005583a  call    cs:__imp_LocalFree
0x180055840  mov     rcx, r15; hMem
0x180055843  call    cs:__imp_LocalFree
0x180055849  xor     ecx, ecx; hMem
0x18005584b  call    cs:__imp_LocalFree
0x180055851  mov     rcx, cs:WPP_GLOBAL_Control
0x180055858  lea     rax, WPP_GLOBAL_Control
0x18005585f  cmp     rcx, rax
0x180055862  jz      short loc_18005587C
0x180055864  mov     rcx, [rcx+10h]
0x180055868  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18005586f  mov     edx, 37Bh
0x180055874  mov     r9d, edi
0x180055877  call    WPP_SF_d
0x18005587c  mov     rbx, [rsp+0D0h+arg_8]
0x180055884  mov     eax, edi
0x180055886  add     rsp, 0A0h
0x18005588d  pop     r15
0x18005588f  pop     r14
0x180055891  pop     r13
0x180055893  pop     r12
0x180055895  pop     rdi
0x180055896  pop     rsi
0x180055897  pop     rbp
0x180055898  retn
```
