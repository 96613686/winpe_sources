# _anonymous_namespace_::GetLinguisticDataCollectionPolicy

- ea: `0x1800c476c`
- end: `0x1800c4a19`
- name: `_anonymous_namespace_::GetLinguisticDataCollectionPolicy`
- size: `685`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800c45d0`

## callees

- `0x18001daf0`
- `0x18001dcc8`
- `0x1800c476c`
- `0x1800c51f0`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c47ae`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c47ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c47da`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c4802`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c47da`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c4802`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4997`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c49b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c49cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c49e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c49ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4997`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c49b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c49cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c49e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c49ff`

## string_xrefs

- `0x1800c47a7`: `policymanager.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall anonymous_namespace_::GetLinguisticDataCollectionPolicy(_BYTE *a1, bool *a2)
{
  HMODULE Library; // rax
  int v5; // r8d
  FARPROC ProcAddress; // rcx
  FARPROC v7; // rdx
  int Policy; // ebx
  void (*v9)(void); // rax
  void (*v11)(void); // rax
  __int64 v12; // rcx
  void (*v13)(void); // rax
  void (*v14)(void); // rax
  signed int LastError; // eax
  int v16; // edx
  unsigned int v17; // r8d
  signed int v18; // eax
  int v19; // edx
  unsigned int v20; // r8d
  signed int v21; // eax
  int v22; // edx
  unsigned int v23; // r8d
  signed int v24; // eax
  int v25; // edx
  unsigned int v26; // r8d
  signed int v27; // eax
  int v28; // edx
  unsigned int v29; // r8d
  __int128 v30; // [rsp+30h] [rbp-30h] BYREF
  const int *v31; // [rsp+40h] [rbp-20h] BYREF
  HMODULE v32; // [rsp+48h] [rbp-18h]
  INT_PTR (__stdcall *v33)(); // [rsp+50h] [rbp-10h]
  FARPROC v34; // [rsp+58h] [rbp-8h]
  int v35; // [rsp+80h] [rbp+20h] BYREF
  int v36; // [rsp+84h] [rbp+24h]

  if ( !a1 || !a2 )
    return 2147500037LL;
  *a1 = 0;
  *a2 = 0;
  Library = LoadLibraryExW(L"policymanager.dll", 0, 0x800u);
  v31 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  v32 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "PolicyManager_GetPolicy");
    v33 = ProcAddress;
    Library = v32;
  }
  else
  {
    ProcAddress = 0;
    v33 = 0;
  }
  if ( Library )
  {
    v7 = GetProcAddress(Library, "PolicyManager_FreeGetPolicyData");
    v34 = v7;
    ProcAddress = v33;
    Library = v32;
  }
  else
  {
    v7 = 0;
    v34 = 0;
  }
  if ( !ProcAddress || !v7 )
  {
    v31 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
    if ( Library && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v31) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v16, v17);
      __debugbreak();
    }
    return 2147500037LL;
  }
  v35 = 1;
  v36 = 2;
  v30 = 0;
  Policy = anonymous_namespace_::PolicyManagerDelayLoad::PolicyManager_GetPolicy(
             (unsigned int)&v31,
             (_DWORD)v7,
             v5,
             (unsigned int)&v35,
             (__int64)&v30);
  if ( Policy != -2147024769 )
  {
    if ( Policy < 0 )
    {
      if ( *((_QWORD *)&v30 + 1) )
      {
        v11 = *(void (**)(void))(v30 + 24);
        if ( v11 )
          v11();
      }
      v31 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
      if ( v32 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v31) )
      {
        v27 = GetLastError();
        if ( v27 > 0 )
          v27 = (unsigned __int16)v27 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v27, v28, v29);
        JUMPOUT(0x1800C4A18LL);
      }
      return (unsigned int)Policy;
    }
    v12 = *((_QWORD *)&v30 + 1);
    if ( *(_DWORD *)(*((_QWORD *)&v30 + 1) + 8LL) == 1 )
    {
      if ( *(_DWORD *)(*((_QWORD *)&v30 + 1) + 4LL) == 2 )
        *a1 = 1;
      *a2 = *(_DWORD *)(v12 + 16) != 0;
      if ( v12 )
      {
        v14 = *(void (**)(void))(v30 + 24);
        if ( v14 )
          v14();
      }
      v31 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
      if ( v32 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v31) )
      {
        v21 = GetLastError();
        if ( v21 > 0 )
          v21 = (unsigned __int16)v21 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v21, v22, v23);
        __debugbreak();
      }
      return (unsigned int)Policy;
    }
    if ( *((_QWORD *)&v30 + 1) )
    {
      v13 = *(void (**)(void))(v30 + 24);
      if ( v13 )
        v13();
    }
    v31 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
    if ( v32 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v31) )
    {
      v18 = GetLastError();
      if ( v18 > 0 )
        v18 = (unsigned __int16)v18 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v18, v19, v20);
      __debugbreak();
    }
    return 2147500037LL;
  }
  if ( *((_QWORD *)&v30 + 1) )
  {
    v9 = *(void (**)(void))(v30 + 24);
    if ( v9 )
      v9();
  }
  v31 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( v32 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v31) )
  {
    v24 = GetLastError();
    if ( v24 > 0 )
      v24 = (unsigned __int16)v24 | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v24, v25, v26);
    __debugbreak();
  }
  return 0;
}

```

## disassembly

```asm
0x1800c476c  mov     [rsp-18h+arg_8], rbx
0x1800c4771  mov     [rsp-18h+arg_10], rsi
0x1800c4776  push    rbp
0x1800c4777  push    rdi
0x1800c4778  push    r15
0x1800c477a  mov     rbp, rsp
0x1800c477d  sub     rsp, 60h
0x1800c4781  mov     rdi, rdx
0x1800c4784  mov     rsi, rcx
0x1800c4787  test    rcx, rcx
0x1800c478a  jz      loc_1800C497D
0x1800c4790  test    rdx, rdx
0x1800c4793  jz      loc_1800C497D
0x1800c4799  mov     byte ptr [rcx], 0
0x1800c479c  mov     byte ptr [rdx], 0
0x1800c479f  xor     edx, edx; hFile
0x1800c47a1  mov     r8d, 800h; dwFlags
0x1800c47a7  lea     rcx, aPolicymanagerD; "policymanager.dll"
0x1800c47ae  call    cs:__imp_LoadLibraryExW
0x1800c47b4  lea     r15, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x1800c47bb  mov     [rbp+var_20], r15
0x1800c47bf  mov     [rbp+var_18], rax
0x1800c47c3  test    rax, rax
0x1800c47c6  jnz     short loc_1800C47D0
0x1800c47c8  xor     ecx, ecx
0x1800c47ca  mov     [rbp+var_10], rcx
0x1800c47ce  jmp     short loc_1800C47EB
0x1800c47d0  lea     rdx, aPolicymanagerG_1; "PolicyManager_GetPolicy"
0x1800c47d7  mov     rcx, rax; hModule
0x1800c47da  call    cs:__imp_GetProcAddress
0x1800c47e0  mov     rcx, rax
0x1800c47e3  mov     [rbp+var_10], rax
0x1800c47e7  mov     rax, [rbp+var_18]
0x1800c47eb  test    rax, rax
0x1800c47ee  jnz     short loc_1800C47F8
0x1800c47f0  xor     edx, edx
0x1800c47f2  mov     [rbp+var_8], rdx
0x1800c47f6  jmp     short loc_1800C4817
0x1800c47f8  lea     rdx, aPolicymanagerF_0; "PolicyManager_FreeGetPolicyData"
0x1800c47ff  mov     rcx, rax; hModule
0x1800c4802  call    cs:__imp_GetProcAddress
0x1800c4808  mov     rdx, rax
0x1800c480b  mov     [rbp+var_8], rax
0x1800c480f  mov     rcx, [rbp+var_10]
0x1800c4813  mov     rax, [rbp+var_18]
0x1800c4817  test    rcx, rcx
0x1800c481a  jz      loc_1800C4967
0x1800c4820  test    rdx, rdx
0x1800c4823  jz      loc_1800C4967
0x1800c4829  mov     [rbp+arg_0], 1
0x1800c4830  mov     [rbp+arg_4], 2
0x1800c4837  xorps   xmm0, xmm0
0x1800c483a  movdqu  [rbp+var_30], xmm0
0x1800c483f  lea     rax, [rbp+var_30]
0x1800c4843  mov     [rsp+60h+var_40], rax
0x1800c4848  lea     r9, [rbp+arg_0]
0x1800c484c  lea     rcx, [rbp+var_20]
0x1800c4850  call    _anonymous_namespace___PolicyManagerDelayLoad__PolicyManager_GetPolicy
0x1800c4855  mov     ebx, eax
0x1800c4857  cmp     eax, 8007007Fh
0x1800c485c  jnz     short loc_1800C489D
0x1800c485e  mov     rcx, qword ptr [rbp+var_30+8]
0x1800c4862  test    rcx, rcx
0x1800c4865  jz      short loc_1800C487A
0x1800c4867  mov     rax, qword ptr [rbp+var_30]
0x1800c486b  mov     rax, [rax+18h]
0x1800c486f  test    rax, rax
0x1800c4872  jz      short loc_1800C487A
0x1800c4874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4879  nop
0x1800c487a  mov     [rbp+var_20], r15
0x1800c487e  cmp     [rbp+var_18], 0
0x1800c4883  jz      short loc_1800C4896
0x1800c4885  lea     rcx, [rbp+var_20]
0x1800c4889  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800c488e  test    al, al
0x1800c4890  jz      loc_1800C49E5
0x1800c4896  xor     eax, eax
0x1800c4898  jmp     loc_1800C4982
0x1800c489d  test    ebx, ebx
0x1800c489f  jns     short loc_1800C48E0
0x1800c48a1  mov     rcx, qword ptr [rbp+var_30+8]
0x1800c48a5  test    rcx, rcx
0x1800c48a8  jz      short loc_1800C48BD
0x1800c48aa  mov     rax, qword ptr [rbp+var_30]
0x1800c48ae  mov     rax, [rax+18h]
0x1800c48b2  test    rax, rax
0x1800c48b5  jz      short loc_1800C48BD
0x1800c48b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c48bc  nop
0x1800c48bd  mov     [rbp+var_20], r15
0x1800c48c1  cmp     [rbp+var_18], 0
0x1800c48c6  jz      short loc_1800C48D9
0x1800c48c8  lea     rcx, [rbp+var_20]
0x1800c48cc  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800c48d1  test    al, al
0x1800c48d3  jz      loc_1800C49FF
0x1800c48d9  mov     eax, ebx
0x1800c48db  jmp     loc_1800C4982
0x1800c48e0  mov     rcx, qword ptr [rbp+var_30+8]
0x1800c48e4  cmp     dword ptr [rcx+8], 1
0x1800c48e8  jz      short loc_1800C4920
0x1800c48ea  test    rcx, rcx
0x1800c48ed  jz      short loc_1800C4902
0x1800c48ef  mov     rax, qword ptr [rbp+var_30]
0x1800c48f3  mov     rax, [rax+18h]
0x1800c48f7  test    rax, rax
0x1800c48fa  jz      short loc_1800C4902
0x1800c48fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4901  nop
0x1800c4902  mov     [rbp+var_20], r15
0x1800c4906  cmp     [rbp+var_18], 0
0x1800c490b  jz      short loc_1800C497D
0x1800c490d  lea     rcx, [rbp+var_20]
0x1800c4911  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800c4916  test    al, al
0x1800c4918  jz      loc_1800C49B1
0x1800c491e  jmp     short loc_1800C497D
0x1800c4920  cmp     dword ptr [rcx+4], 2
0x1800c4924  jnz     short loc_1800C4929
0x1800c4926  mov     byte ptr [rsi], 1
0x1800c4929  cmp     dword ptr [rcx+10h], 0
0x1800c492d  setnz   al
0x1800c4930  mov     [rdi], al
0x1800c4932  test    rcx, rcx
0x1800c4935  jz      short loc_1800C494A
0x1800c4937  mov     rax, qword ptr [rbp+var_30]
0x1800c493b  mov     rax, [rax+18h]
0x1800c493f  test    rax, rax
0x1800c4942  jz      short loc_1800C494A
0x1800c4944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4949  nop
0x1800c494a  mov     [rbp+var_20], r15
0x1800c494e  cmp     [rbp+var_18], 0
0x1800c4953  jz      short loc_1800C48D9
0x1800c4955  lea     rcx, [rbp+var_20]
0x1800c4959  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800c495e  test    al, al
0x1800c4960  jz      short loc_1800C49CB
0x1800c4962  jmp     loc_1800C48D9
0x1800c4967  mov     [rbp+var_20], r15
0x1800c496b  test    rax, rax
0x1800c496e  jz      short loc_1800C497D
0x1800c4970  lea     rcx, [rbp+var_20]
0x1800c4974  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800c4979  test    al, al
0x1800c497b  jz      short loc_1800C4997
0x1800c497d  mov     eax, 80004005h
0x1800c4982  lea     r11, [rsp+60h+var_s0]
0x1800c4987  mov     rbx, [r11+28h]
0x1800c498b  mov     rsi, [r11+30h]
0x1800c498f  mov     rsp, r11
0x1800c4992  pop     r15
0x1800c4994  pop     rdi
0x1800c4995  pop     rbp
0x1800c4996  retn
0x1800c4997  call    cs:__imp_GetLastError
0x1800c499d  test    eax, eax
0x1800c499f  jle     short loc_1800C49A9
0x1800c49a1  movzx   eax, ax
0x1800c49a4  or      eax, 80070000h
0x1800c49a9  mov     ecx, eax; this
0x1800c49ab  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800c49b0  int     3; Trap to Debugger
0x1800c49b1  call    cs:__imp_GetLastError
0x1800c49b7  test    eax, eax
0x1800c49b9  jle     short loc_1800C49C3
0x1800c49bb  movzx   eax, ax
0x1800c49be  or      eax, 80070000h
0x1800c49c3  mov     ecx, eax; this
0x1800c49c5  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800c49ca  int     3; Trap to Debugger
0x1800c49cb  call    cs:__imp_GetLastError
0x1800c49d1  test    eax, eax
0x1800c49d3  jle     short loc_1800C49DD
0x1800c49d5  movzx   eax, ax
0x1800c49d8  or      eax, 80070000h
0x1800c49dd  mov     ecx, eax; this
0x1800c49df  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800c49e4  int     3; Trap to Debugger
0x1800c49e5  call    cs:__imp_GetLastError
0x1800c49eb  test    eax, eax
0x1800c49ed  jle     short loc_1800C49F7
0x1800c49ef  movzx   eax, ax
0x1800c49f2  or      eax, 80070000h
0x1800c49f7  mov     ecx, eax; this
0x1800c49f9  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800c49fe  int     3; Trap to Debugger
0x1800c49ff  call    cs:__imp_GetLastError
0x1800c4a05  test    eax, eax
0x1800c4a07  jle     short loc_1800C4A11
0x1800c4a09  movzx   eax, ax
0x1800c4a0c  or      eax, 80070000h
0x1800c4a11  mov     ecx, eax; this
0x1800c4a13  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
