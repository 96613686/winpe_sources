# GetDxDbFODState(_DismPackageFeatureState &)

- ea: `0x1400090c4`
- end: `0x140009349`
- name: `?GetDxDbFODState@@YAJAEAW4_DismPackageFeatureState@@@Z`
- size: `645`
- prototype: `int __fastcall(enum _DismPackageFeatureState *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x14000eafc`

## callees

- `0x1400090c4`
- `0x14000c8d4`
- `0x14000c91c`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009115`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009128`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000913b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000914f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009163`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009115`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009128`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000913b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000914f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009163`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400092d8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000932d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400092d8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000932d`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1400090e1`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1400090e1`

## string_xrefs

- `0x1400091c1`: `onecoreuap\windows\directx\dxg\dxgi\adaptercache\exe\main.cpp`
- `0x140009218`: `onecoreuap\windows\directx\dxg\dxgi\adaptercache\exe\main.cpp`
- `0x140009274`: `onecoreuap\windows\directx\dxg\dxgi\adaptercache\exe\main.cpp`
- `0x1400090da`: `dismapi.dll`
- `0x14000911e`: `DismOpenSession`
- `0x140009255`: `DirectX.Configuration.Database~~~~0.0.1.0`

## pseudocode

```c
int __fastcall GetDxDbFODState(enum _DismPackageFeatureState *a1)
{
  HMODULE LibraryW; // rax
  unsigned int v3; // r8d
  HMODULE v4; // rbx
  FARPROC ProcAddress; // rdi
  FARPROC v7; // r14
  FARPROC v8; // rax
  unsigned int v9; // r8d
  __int64 (__fastcall *v10)(_QWORD, _QWORD, _QWORD); // rsi
  int v11; // eax
  int v12; // edi
  int v13; // eax
  int v14; // eax
  unsigned int v15; // r8d
  unsigned int v16; // [rsp+20h] [rbp-40h]
  _QWORD v17[5]; // [rsp+30h] [rbp-30h] BYREF
  char v18; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  unsigned int v20; // [rsp+98h] [rbp+38h] BYREF
  void (*v21)(void); // [rsp+A0h] [rbp+40h] BYREF
  void (*v22)(void); // [rsp+A8h] [rbp+48h] BYREF

  LibraryW = LoadLibraryW(L"dismapi.dll");
  v4 = LibraryW;
  v17[1] = LibraryW;
  if ( !LibraryW )
    return wil::details::in1diag3::Return_Win32(retaddr, (void *)0xA1, v3, (const char *)0x32, v16);
  ProcAddress = GetProcAddress(LibraryW, "DismInitialize");
  v7 = GetProcAddress(v4, "DismOpenSession");
  v21 = (void (*)(void))GetProcAddress(v4, "DismCloseSession");
  v22 = (void (*)(void))GetProcAddress(v4, "DismShutdown");
  v8 = GetProcAddress(v4, "DismGetCapabilityInfo");
  v10 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))v8;
  if ( !ProcAddress || !v7 || !v21 || !v22 || !v8 )
  {
    v12 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0xBC, v9, (const char *)0x32, v16);
    goto LABEL_27;
  }
  v20 = 0;
  v11 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD))ProcAddress)(2, 0, 0);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC1,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\adaptercache\\exe\\main.cpp",
      (const char *)(unsigned int)v11,
      v16);
LABEL_27:
    FreeLibrary(v4);
    return v12;
  }
  v17[2] = &v20;
  v17[3] = &v21;
  v17[4] = &v22;
  v18 = 1;
  v13 = ((__int64 (__fastcall *)(const wchar_t *, _QWORD, _QWORD, unsigned int *))v7)(
          L"DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF845}",
          0,
          0,
          &v20);
  v12 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCC,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\adaptercache\\exe\\main.cpp",
      (const char *)(unsigned int)v13,
      v16);
    if ( v20 )
      v21();
    v22();
    goto LABEL_27;
  }
  v17[0] = 0;
  v14 = v10(v20, L"DirectX.Configuration.Database~~~~0.0.1.0", v17);
  v12 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCF,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\adaptercache\\exe\\main.cpp",
      (const char *)(unsigned int)v14,
      v16);
    if ( v20 )
      v21();
LABEL_17:
    v22();
    goto LABEL_27;
  }
  if ( !*(_QWORD *)v17[0] || !*(_DWORD *)(v17[0] + 32LL) )
  {
    v12 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0xD3, v15, (const char *)2, v16);
    if ( v20 )
      v21();
    goto LABEL_17;
  }
  *(_DWORD *)a1 = *(_DWORD *)(v17[0] + 8LL);
  if ( v20 )
    v21();
  v22();
  FreeLibrary(v4);
  return 0;
}

```

## disassembly

```asm
0x1400090c4  mov     [rsp-28h+arg_0], rbx
0x1400090c9  push    rbp
0x1400090ca  push    rsi
0x1400090cb  push    rdi
0x1400090cc  push    r14
0x1400090ce  push    r15
0x1400090d0  mov     rbp, rsp
0x1400090d3  sub     rsp, 60h
0x1400090d7  mov     r15, rcx
0x1400090da  lea     rcx, LibFileName; "dismapi.dll"
0x1400090e1  call    cs:__imp_LoadLibraryW
0x1400090e7  mov     rbx, rax
0x1400090ea  mov     [rbp+var_28], rax
0x1400090ee  test    rax, rax
0x1400090f1  jnz     short loc_14000910B
0x1400090f3  mov     rcx, [rbp+28h]; this
0x1400090f7  mov     edx, 0A1h; void *
0x1400090fc  lea     r9d, [rax+32h]; char *
0x140009100  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140009105  nop
0x140009106  jmp     loc_140009335
0x14000910b  lea     rdx, aDisminitialize; "DismInitialize"
0x140009112  mov     rcx, rbx; hModule
0x140009115  call    cs:__imp_GetProcAddress
0x14000911b  mov     rdi, rax
0x14000911e  lea     rdx, aDismopensessio; "DismOpenSession"
0x140009125  mov     rcx, rbx; hModule
0x140009128  call    cs:__imp_GetProcAddress
0x14000912e  mov     r14, rax
0x140009131  lea     rdx, aDismclosesessi; "DismCloseSession"
0x140009138  mov     rcx, rbx; hModule
0x14000913b  call    cs:__imp_GetProcAddress
0x140009141  mov     [rbp+arg_10], rax
0x140009145  lea     rdx, aDismshutdown; "DismShutdown"
0x14000914c  mov     rcx, rbx; hModule
0x14000914f  call    cs:__imp_GetProcAddress
0x140009155  mov     [rbp+arg_18], rax
0x140009159  lea     rdx, aDismgetcapabil; "DismGetCapabilityInfo"
0x140009160  mov     rcx, rbx; hModule
0x140009163  call    cs:__imp_GetProcAddress
0x140009169  mov     rsi, rax
0x14000916c  test    rdi, rdi
0x14000916f  jz      loc_140009314
0x140009175  test    r14, r14
0x140009178  jz      loc_140009314
0x14000917e  cmp     [rbp+arg_10], 0
0x140009183  jz      loc_140009314
0x140009189  cmp     [rbp+arg_18], 0
0x14000918e  jz      loc_140009314
0x140009194  test    rax, rax
0x140009197  jz      loc_140009314
0x14000919d  mov     [rbp+arg_8], 0
0x1400091a4  xor     r8d, r8d
0x1400091a7  xor     edx, edx
0x1400091a9  lea     ecx, [rdx+2]
0x1400091ac  mov     rax, rdi
0x1400091af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400091b4  mov     edi, eax
0x1400091b6  test    eax, eax
0x1400091b8  jns     short loc_1400091D7
0x1400091ba  mov     rcx, [rbp+28h]; this
0x1400091be  mov     r9d, eax; char *
0x1400091c1  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x1400091c8  mov     edx, 0C1h; void *
0x1400091cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400091d2  jmp     loc_14000932A
0x1400091d7  lea     rax, [rbp+arg_8]
0x1400091db  mov     [rbp+var_20], rax
0x1400091df  lea     rax, [rbp+arg_10]
0x1400091e3  mov     [rbp+var_18], rax
0x1400091e7  lea     rax, [rbp+arg_18]
0x1400091eb  mov     [rbp+var_10], rax
0x1400091ef  mov     [rbp+var_8], 1
0x1400091f3  lea     r9, [rbp+arg_8]
0x1400091f7  xor     r8d, r8d
0x1400091fa  xor     edx, edx
0x1400091fc  lea     rcx, aDism53bfae52B1; "DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF"...
0x140009203  mov     rax, r14
0x140009206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000920b  mov     edi, eax
0x14000920d  test    eax, eax
0x14000920f  jns     short loc_140009249
0x140009211  mov     rcx, [rbp+28h]; this
0x140009215  mov     r9d, eax; char *
0x140009218  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x14000921f  mov     edx, 0CCh; void *
0x140009224  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009229  nop
0x14000922a  mov     ecx, [rbp+arg_8]
0x14000922d  test    ecx, ecx
0x14000922f  jz      short loc_14000923A
0x140009231  mov     rax, [rbp+arg_10]
0x140009235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000923a  mov     rax, [rbp+arg_18]
0x14000923e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009243  nop
0x140009244  jmp     loc_14000932A
0x140009249  mov     [rbp+var_30], 0
0x140009251  lea     r8, [rbp+var_30]
0x140009255  lea     rdx, aDirectxConfigu; "DirectX.Configuration.Database~~~~0.0.1"...
0x14000925c  mov     ecx, [rbp+arg_8]
0x14000925f  mov     rax, rsi
0x140009262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009267  mov     edi, eax
0x140009269  test    eax, eax
0x14000926b  jns     short loc_1400092A5
0x14000926d  mov     rcx, [rbp+28h]; this
0x140009271  mov     r9d, eax; char *
0x140009274  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x14000927b  mov     edx, 0CFh; void *
0x140009280  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009285  nop
0x140009286  mov     ecx, [rbp+arg_8]
0x140009289  test    ecx, ecx
0x14000928b  jz      short loc_140009296
0x14000928d  mov     rax, [rbp+arg_10]
0x140009291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009296  mov     rax, [rbp+arg_18]
0x14000929a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000929f  nop
0x1400092a0  jmp     loc_14000932A
0x1400092a5  mov     rax, [rbp+var_30]
0x1400092a9  cmp     qword ptr [rax], 0
0x1400092ad  jz      short loc_1400092E2
0x1400092af  cmp     dword ptr [rax+20h], 0
0x1400092b3  jz      short loc_1400092E2
0x1400092b5  mov     eax, [rax+8]
0x1400092b8  mov     [r15], eax
0x1400092bb  mov     ecx, [rbp+arg_8]
0x1400092be  test    ecx, ecx
0x1400092c0  jz      short loc_1400092CB
0x1400092c2  mov     rax, [rbp+arg_10]
0x1400092c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400092cb  mov     rax, [rbp+arg_18]
0x1400092cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400092d4  nop
0x1400092d5  mov     rcx, rbx; hLibModule
0x1400092d8  call    cs:__imp_FreeLibrary
0x1400092de  xor     eax, eax
0x1400092e0  jmp     short loc_140009335
0x1400092e2  mov     rcx, [rbp+28h]; this
0x1400092e6  mov     edx, 0D3h; void *
0x1400092eb  mov     r9d, 2; char *
0x1400092f1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1400092f6  mov     edi, eax
0x1400092f8  mov     ecx, [rbp+arg_8]
0x1400092fb  test    ecx, ecx
0x1400092fd  jz      short loc_140009308
0x1400092ff  mov     rax, [rbp+arg_10]
0x140009303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009308  mov     rax, [rbp+arg_18]
0x14000930c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009311  nop
0x140009312  jmp     short loc_14000932A
0x140009314  mov     rcx, [rbp+28h]; this
0x140009318  mov     edx, 0BCh; void *
0x14000931d  mov     r9d, 32h ; '2'; char *
0x140009323  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140009328  mov     edi, eax
0x14000932a  mov     rcx, rbx; hLibModule
0x14000932d  call    cs:__imp_FreeLibrary
0x140009333  mov     eax, edi
0x140009335  mov     rbx, [rsp+60h+arg_0]
0x14000933d  add     rsp, 60h
0x140009341  pop     r15
0x140009343  pop     r14
0x140009345  pop     rdi
0x140009346  pop     rsi
0x140009347  pop     rbp
0x140009348  retn
```
