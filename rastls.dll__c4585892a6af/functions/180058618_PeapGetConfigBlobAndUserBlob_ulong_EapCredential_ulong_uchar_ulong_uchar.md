# PeapGetConfigBlobAndUserBlob(ulong,_EapCredential,ulong *,uchar * *,ulong *,uchar * *)

- ea: `0x180058618`
- end: `0x180058924`
- name: `?PeapGetConfigBlobAndUserBlob@@YAKKU_EapCredential@@PEAKPEAPEAE12@Z`
- size: `780`
- prototype: `unsigned int __usercall@<eax>(unsigned int@<ecx>, struct _EapCredential *__struct_ptr@<rdx>, unsigned int *@<r8>, unsigned __int8 **@<r9>, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x18005d140`

## callees

- `0x180004688`
- `0x180005010`
- `0x180006620`
- `0x180020d80`
- `0x180038e4c`
- `0x180058618`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800586d7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800586d7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800586f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180058712`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800586f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180058712`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180058893`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180058893`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005885b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005885b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180058792`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800587f5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180058792`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800587f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800588a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800588b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800588c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800588cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800588a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800588b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800588c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800588cf`

## string_xrefs

- `0x1800586ca`: `raschap.dll`
- `0x1800586ef`: `RasEapGetConfigBlobAndUserBlob`

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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 891, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, UserData);
  return UserData;
}

```

## disassembly

```asm
0x180058618  mov     rax, rsp
0x18005861b  mov     [rax+10h], rbx
0x18005861f  mov     [rax+20h], r9
0x180058623  mov     [rax+18h], r8
0x180058627  push    rbp
0x180058628  push    rsi
0x180058629  push    rdi
0x18005862a  push    r12
0x18005862c  push    r13
0x18005862e  push    r14
0x180058630  push    r15
0x180058632  lea     rbp, [rax-4Fh]
0x180058636  sub     rsp, 0A0h
0x18005863d  mov     r13d, ecx
0x180058640  mov     rbx, rdx
0x180058643  xor     ecx, ecx
0x180058645  mov     [rbp+47h+Src], rcx
0x180058649  mov     esi, ecx
0x18005864b  mov     [rbp+47h+hMem], rcx
0x18005864f  mov     r15d, ecx
0x180058652  mov     dword ptr [rbp+47h+Size], ecx
0x180058655  mov     [rbp+47h+var_80], rcx
0x180058659  mov     dword ptr [rbp+47h+var_90], ecx
0x18005865c  mov     [rbp+47h+var_78], rcx
0x180058660  mov     [rbp+47h+var_68], rcx
0x180058664  test    r13b, 20h
0x180058668  jnz     short loc_18005867B
0x18005866a  mov     eax, [rdx]
0x18005866c  dec     eax
0x18005866e  cmp     eax, 1
0x180058671  jbe     short loc_18005867B
0x180058673  lea     edi, [rcx+57h]
0x180058676  jmp     loc_18005889F
0x18005867b  mov     r14, rcx
0x18005867e  lea     r9, [rbp+47h+Src]; struct _PEAP_CONN_PROPERTIES **
0x180058682  mov     r12, rcx
0x180058685  xor     r8d, r8d; unsigned int
0x180058688  mov     ecx, r13d; unsigned int
0x18005868b  xor     edx, edx; unsigned __int8 *
0x18005868d  call    ?PeapReadConnectionData@@YAKKPEAEKPEAPEAU_PEAP_CONN_PROPERTIES@@@Z; PeapReadConnectionData(ulong,uchar *,ulong,_PEAP_CONN_PROPERTIES * *)
0x180058692  mov     rsi, [rbp+47h+Src]
0x180058696  mov     edi, eax
0x180058698  test    eax, eax
0x18005869a  jnz     loc_180058869
0x1800586a0  and     dword ptr [rsi+18h], 0FFFFFFFBh
0x1800586a4  cmp     dword ptr [rbx], 1
0x1800586a7  jnz     short loc_1800586AE
0x1800586a9  bts     dword ptr [rsi+18h], 9
0x1800586ae  lea     r9, [rbp+47h+hMem]; struct _PEAP_USER_PROPERTIES **
0x1800586b2  xor     r8d, r8d; unsigned int
0x1800586b5  xor     edx, edx; unsigned __int8 *
0x1800586b7  xor     ecx, ecx; int
0x1800586b9  call    ?PeapReadUserData@@YAKHPEAEKPEAPEAU_PEAP_USER_PROPERTIES@@@Z; PeapReadUserData(int,uchar *,ulong,_PEAP_USER_PROPERTIES * *)
0x1800586be  mov     edi, eax
0x1800586c0  test    eax, eax
0x1800586c2  jnz     loc_180058869
0x1800586c8  xor     edx, edx; hFile
0x1800586ca  lea     rcx, aRaschapDll; "raschap.dll"
0x1800586d1  mov     r8d, 800h; dwFlags
0x1800586d7  call    cs:__imp_LoadLibraryExW
0x1800586de  nop     dword ptr [rax+rax+00h]
0x1800586e3  mov     r14, rax
0x1800586e6  test    rax, rax
0x1800586e9  jz      loc_18005885B
0x1800586ef  lea     rdx, aRaseapgetconfi_0; "RasEapGetConfigBlobAndUserBlob"
0x1800586f6  mov     rcx, rax; hModule
0x1800586f9  call    cs:__imp_GetProcAddress
0x180058700  nop     dword ptr [rax+rax+00h]
0x180058705  lea     rdx, ProcName; "RasEapFreeMemory"
0x18005870c  mov     rcx, r14; hModule
0x18005870f  mov     rdi, rax
0x180058712  call    cs:__imp_GetProcAddress
0x180058719  nop     dword ptr [rax+rax+00h]
0x18005871e  mov     r12, rax
0x180058721  test    rdi, rdi
0x180058724  jz      loc_18005885B
0x18005872a  test    rax, rax
0x18005872d  jz      loc_18005885B
0x180058733  movaps  xmm0, xmmword ptr [rbx]
0x180058736  lea     rax, [rbp+47h+var_78]
0x18005873a  movaps  xmm1, xmmword ptr [rbx+10h]
0x18005873e  lea     r9, [rbp+47h+Size]
0x180058742  mov     [rsp+30h], rax
0x180058747  lea     r8, [rbp+47h+var_60]
0x18005874b  lea     rax, [rbp+47h+var_90]
0x18005874f  movaps  [rbp+47h+var_60], xmm0
0x180058753  movsd   xmm0, qword ptr [rbx+20h]
0x180058758  mov     edx, 1Ah
0x18005875d  mov     [rsp+0D0h+var_A8], rax
0x180058762  mov     ecx, r13d
0x180058765  lea     rax, [rbp+47h+var_80]
0x180058769  movaps  [rbp+47h+var_50], xmm1
0x18005876d  mov     [rsp+0D0h+var_B0], rax
0x180058772  mov     rax, rdi
0x180058775  movsd   [rbp+47h+var_40], xmm0
0x18005877a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005877f  mov     edi, eax
0x180058781  test    eax, eax
0x180058783  jnz     loc_180058869
0x180058789  mov     edx, [rsi+4]
0x18005878c  lea     ecx, [rax+40h]; uFlags
0x18005878f  add     edx, dword ptr [rbp+47h+Size]; uBytes
0x180058792  call    cs:__imp_LocalAlloc
0x180058799  nop     dword ptr [rax+rax+00h]
0x18005879e  mov     r15, rax
0x1800587a1  test    rax, rax
0x1800587a4  jz      loc_18005885B
0x1800587aa  mov     r8d, [rsi+4]; Size
0x1800587ae  mov     rdx, rsi; Src
0x1800587b1  mov     rcx, rax; void *
0x1800587b4  call    memcpy_0
0x1800587b9  lea     rdx, [rbp+47h+var_68]; struct _PEAP_ENTRY_CONN_PROPERTIES **
0x1800587bd  mov     rcx, r15; struct _PEAP_CONN_PROPERTIES *
0x1800587c0  call    ?PeapGetFirstEntryConnProp@@YAKPEAU_PEAP_CONN_PROPERTIES@@PEAPEFAU_PEAP_ENTRY_CONN_PROPERTIES@@@Z; PeapGetFirstEntryConnProp(_PEAP_CONN_PROPERTIES *,_PEAP_ENTRY_CONN_PROPERTIES * *)
0x1800587c5  mov     rbx, [rbp+47h+var_68]
0x1800587c9  mov     r8d, dword ptr [rbp+47h+Size]; Size
0x1800587cd  mov     rdx, [rbp+47h+var_80]; Src
0x1800587d1  lea     rcx, [rbx+0Ch]; void *
0x1800587d5  call    memcpy_0
0x1800587da  mov     eax, dword ptr [rbp+47h+Size]
0x1800587dd  lea     ecx, [rdi+40h]; uFlags
0x1800587e0  add     [rbx+4], eax
0x1800587e3  mov     eax, dword ptr [rbp+47h+Size]
0x1800587e6  add     [r15+4], eax
0x1800587ea  mov     r13, [rbp+47h+hMem]
0x1800587ee  mov     edx, [r13+4]
0x1800587f2  add     edx, dword ptr [rbp+47h+var_90]; uBytes
0x1800587f5  call    cs:__imp_LocalAlloc
0x1800587fc  nop     dword ptr [rax+rax+00h]
0x180058801  mov     rbx, rax
0x180058804  test    rax, rax
0x180058807  jz      short loc_18005885B
0x180058809  mov     r8d, [r13+4]; Size
0x18005880d  mov     rdx, r13; Src
0x180058810  mov     rcx, rax; void *
0x180058813  call    memcpy_0
0x180058818  mov     r8d, dword ptr [rbp+47h+var_90]; Size
0x18005881c  lea     rcx, [rbx+38h]; void *
0x180058820  mov     rdx, [rbp+47h+var_78]; Src
0x180058824  call    memcpy_0
0x180058829  mov     eax, dword ptr [rbp+47h+var_90]
0x18005882c  add     [rbx+2Ch], eax
0x18005882f  mov     eax, dword ptr [rbp+47h+var_90]
0x180058832  add     [rbx+4], eax
0x180058835  mov     eax, [r15+4]
0x180058839  mov     rcx, [rbp+47h+arg_10]
0x18005883d  mov     [rcx], eax
0x18005883f  mov     rax, [rbp+47h+arg_18]
0x180058843  mov     [rax], r15
0x180058846  xor     r15d, r15d
0x180058849  mov     rax, [rbp+47h+arg_20]
0x18005884d  mov     ecx, [rbx+4]
0x180058850  mov     [rax], ecx
0x180058852  mov     rax, [rbp+47h+arg_28]
0x180058856  mov     [rax], rbx
0x180058859  jmp     short loc_180058869
0x18005885b  call    cs:__imp_GetLastError
0x180058862  nop     dword ptr [rax+rax+00h]
0x180058867  mov     edi, eax
0x180058869  mov     rcx, [rbp+47h+var_80]
0x18005886d  test    rcx, rcx
0x180058870  jz      short loc_18005887A
0x180058872  mov     rax, r12
0x180058875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005887a  mov     rcx, [rbp+47h+var_78]
0x18005887e  test    rcx, rcx
0x180058881  jz      short loc_18005888B
0x180058883  mov     rax, r12
0x180058886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005888b  test    r14, r14
0x18005888e  jz      short loc_18005889F
0x180058890  mov     rcx, r14; hLibModule
0x180058893  call    cs:__imp_FreeLibrary
0x18005889a  nop     dword ptr [rax+rax+00h]
0x18005889f  mov     rcx, rsi; hMem
0x1800588a2  call    cs:__imp_LocalFree
0x1800588a9  nop     dword ptr [rax+rax+00h]
0x1800588ae  mov     rcx, [rbp+47h+hMem]; hMem
0x1800588b2  call    cs:__imp_LocalFree
0x1800588b9  nop     dword ptr [rax+rax+00h]
0x1800588be  mov     rcx, r15; hMem
0x1800588c1  call    cs:__imp_LocalFree
0x1800588c8  nop     dword ptr [rax+rax+00h]
0x1800588cd  xor     ecx, ecx; hMem
0x1800588cf  call    cs:__imp_LocalFree
0x1800588d6  nop     dword ptr [rax+rax+00h]
0x1800588db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800588e2  lea     rax, WPP_GLOBAL_Control
0x1800588e9  cmp     rcx, rax
0x1800588ec  jz      short loc_180058906
0x1800588ee  mov     rcx, [rcx+10h]
0x1800588f2  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x1800588f9  mov     edx, 37Bh
0x1800588fe  mov     r9d, edi
0x180058901  call    WPP_SF_d
0x180058906  mov     rbx, [rsp+0D0h+arg_8]
0x18005890e  mov     eax, edi
0x180058910  add     rsp, 0A0h
0x180058917  pop     r15
0x180058919  pop     r14
0x18005891b  pop     r13
0x18005891d  pop     r12
0x18005891f  pop     rdi
0x180058920  pop     rsi
0x180058921  pop     rbp
0x180058922  retn
```
