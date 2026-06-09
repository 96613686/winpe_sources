# FDResPub_InitializeHost(void)

- ea: `0x1800047f8`
- end: `0x180004a23`
- name: `?FDResPub_InitializeHost@@YAJXZ`
- size: `555`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180004a30`
- `0x180004cd4`

## callees

- `0x180001014`
- `0x180001020`
- `0x18000102c`
- `0x180004770`
- `0x1800047f8`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000485b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000485b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000496f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000496f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004891`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000494b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004891`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000494b`

## pseudocode

```c
__int64 FDResPub_InitializeHost(void)
{
  void *v0; // rdi
  LSTATUS v1; // eax
  unsigned int v2; // ebx
  bool v3; // cc
  unsigned __int64 v4; // rax
  __int64 v5; // rcx
  const wchar_t *v6; // rdx
  _WORD *v7; // r8
  _WORD *v8; // rcx
  LSTATUS v9; // eax
  CResourcePublisher *v10; // rcx
  CResourcePublisher *v11; // rax
  DWORD cbData; // [rsp+50h] [rbp+20h] BYREF
  DWORD Type; // [rsp+58h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+30h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_db7cc9e2c33f3bbb1ab807d3dbe66b7d_Traceguids);
  hKey = 0;
  v0 = 0;
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Cryptography", 0, 1u, &hKey);
  v2 = v1;
  v3 = v1 <= 0;
  if ( v1
    || (cbData = 0,
        Type = 0,
        v1 = RegQueryValueExW(hKey, L"MachineGuid", 0, &Type, 0, &cbData),
        v2 = v1,
        v3 = v1 <= 0,
        v1) )
  {
    if ( !v3 )
      v2 = (unsigned __int16)v1 | 0x80070000;
  }
  else
  {
    v0 = operator new[](saturated_mul(((unsigned __int64)cbData >> 1) + 10, 2u));
    if ( v0 )
    {
      v2 = 0;
      v4 = ((unsigned __int64)cbData >> 1) + 10;
      if ( v4 <= 0x7FFFFFFF )
      {
        v5 = 2147483646;
        v6 = L"urn:uuid:";
        v7 = v0;
        do
        {
          if ( !v5 )
            break;
          if ( !*v6 )
            break;
          *v7++ = *v6++;
          --v5;
          --v4;
        }
        while ( v4 );
        v8 = v7 - 1;
        if ( v4 )
          v8 = v7;
        *v8 = 0;
      }
      else
      {
        *(_WORD *)v0 = 0;
      }
      v9 = RegQueryValueExW(hKey, L"MachineGuid", 0, &Type, (LPBYTE)v0 + 18, &cbData);
      if ( v9 )
      {
        if ( v9 > 0 )
          v2 = (unsigned __int16)v9 | 0x80070000;
        else
          v2 = v9;
      }
    }
    else
    {
      v2 = -2147024882;
    }
    RegCloseKey(hKey);
    hKey = 0;
  }
  v10 = g_pPublisher;
  if ( v2 || g_pPublisher )
  {
LABEL_31:
    if ( !v0 )
      goto LABEL_33;
    goto LABEL_32;
  }
  v11 = (CResourcePublisher *)operator new(0x10u);
  v10 = v11;
  if ( !v11 )
  {
    v10 = 0;
    g_pPublisher = 0;
    goto LABEL_30;
  }
  *((_QWORD *)v11 + 1) = 0;
  *(_QWORD *)v11 = &CResourcePublisher::`vftable';
  g_pPublisher = v11;
  if ( !v0 )
  {
LABEL_30:
    v2 = -2147024882;
    goto LABEL_31;
  }
  v2 = ((__int64 (__fastcall *)(CResourcePublisher *, void *, const wchar_t *, const wchar_t *))CResourcePublisher::`vftable')(
         v11,
         v0,
         L"Provider\\Microsoft.Base.Publication",
         L"Publication");
LABEL_32:
  operator delete[](v0);
  v10 = g_pPublisher;
LABEL_33:
  if ( !v2 )
    return (*(unsigned int (__fastcall **)(CResourcePublisher *, _QWORD))(*(_QWORD *)v10 + 8LL))(v10, 0);
  return v2;
}

```

## disassembly

```asm
0x1800047f8  mov     [rsp-18h+arg_18], rbx
0x1800047fd  push    rbp
0x1800047fe  push    rsi
0x1800047ff  push    rdi
0x180004800  mov     rbp, rsp
0x180004803  sub     rsp, 30h
0x180004807  mov     rcx, cs:WPP_GLOBAL_Control
0x18000480e  lea     rax, WPP_GLOBAL_Control
0x180004815  cmp     rcx, rax
0x180004818  jz      short loc_180004835
0x18000481a  cmp     byte ptr [rcx+19h], 4
0x18000481e  jb      short loc_180004835
0x180004820  mov     rcx, [rcx+10h]
0x180004824  lea     r8, WPP_db7cc9e2c33f3bbb1ab807d3dbe66b7d_Traceguids
0x18000482b  mov     edx, 12h
0x180004830  call    WPP_SF_s
0x180004835  xor     esi, esi
0x180004837  lea     rax, [rbp+hKey]
0x18000483b  xor     r8d, r8d; ulOptions
0x18000483e  mov     [rbp+hKey], rsi
0x180004842  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Cryptography"
0x180004849  mov     [rsp+30h+phkResult], rax; phkResult
0x18000484e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004855  mov     edi, esi
0x180004857  lea     r9d, [rsi+1]; samDesired
0x18000485b  call    cs:__imp_RegOpenKeyExW
0x180004861  mov     ebx, eax
0x180004863  test    eax, eax
0x180004865  jnz     loc_18000497B
0x18000486b  mov     rcx, [rbp+hKey]; hKey
0x18000486f  lea     rax, [rbp+cbData]
0x180004873  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180004878  lea     r9, [rbp+Type]; lpType
0x18000487c  xor     r8d, r8d; lpReserved
0x18000487f  mov     [rsp+30h+phkResult], rsi; lpData
0x180004884  lea     rdx, aMachineguid; "MachineGuid"
0x18000488b  mov     [rbp+cbData], esi
0x18000488e  mov     [rbp+Type], esi
0x180004891  call    cs:__imp_RegQueryValueExW
0x180004897  mov     ebx, eax
0x180004899  test    eax, eax
0x18000489b  jnz     loc_18000497B
0x1800048a1  mov     ecx, [rbp+cbData]
0x1800048a4  lea     eax, [rsi+2]
0x1800048a7  shr     rcx, 1
0x1800048aa  add     rcx, 0Ah
0x1800048ae  mul     rcx
0x1800048b1  lea     rcx, [rsi-1]
0x1800048b5  cmovb   rax, rcx
0x1800048b9  mov     rcx, rax; unsigned __int64
0x1800048bc  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800048c1  mov     rdi, rax
0x1800048c4  test    rax, rax
0x1800048c7  jz      loc_180004966
0x1800048cd  mov     eax, [rbp+cbData]
0x1800048d0  mov     ebx, esi
0x1800048d2  shr     rax, 1
0x1800048d5  add     rax, 0Ah
0x1800048d9  cmp     rax, 7FFFFFFFh
0x1800048df  jbe     short loc_1800048E6
0x1800048e1  mov     [rdi], si
0x1800048e4  jmp     short loc_180004927
0x1800048e6  mov     ecx, 7FFFFFFEh
0x1800048eb  lea     rdx, aUrnUuid; "urn:uuid:"
0x1800048f2  mov     r8, rdi
0x1800048f5  test    rcx, rcx
0x1800048f8  jz      short loc_180004919
0x1800048fa  movzx   r9d, word ptr [rdx]
0x1800048fe  test    r9w, r9w
0x180004902  jz      short loc_180004919
0x180004904  mov     [r8], r9w
0x180004908  add     rdx, 2
0x18000490c  add     r8, 2
0x180004910  dec     rcx
0x180004913  sub     rax, 1
0x180004917  jnz     short loc_1800048F5
0x180004919  test    rax, rax
0x18000491c  lea     rcx, [r8-2]
0x180004920  cmovnz  rcx, r8
0x180004924  mov     [rcx], si
0x180004927  lea     rcx, [rbp+cbData]
0x18000492b  xor     r8d, r8d; lpReserved
0x18000492e  mov     [rsp+30h+lpcbData], rcx; lpcbData
0x180004933  lea     rax, [rdi+12h]
0x180004937  mov     rcx, [rbp+hKey]; hKey
0x18000493b  lea     r9, [rbp+Type]; lpType
0x18000493f  lea     rdx, aMachineguid; "MachineGuid"
0x180004946  mov     [rsp+30h+phkResult], rax; lpData
0x18000494b  call    cs:__imp_RegQueryValueExW
0x180004951  test    eax, eax
0x180004953  jz      short loc_18000496B
0x180004955  jg      short loc_18000495B
0x180004957  mov     ebx, eax
0x180004959  jmp     short loc_18000496B
0x18000495b  movzx   ebx, ax
0x18000495e  or      ebx, 80070000h
0x180004964  jmp     short loc_18000496B
0x180004966  mov     ebx, 8007000Eh
0x18000496b  mov     rcx, [rbp+hKey]; hKey
0x18000496f  call    cs:__imp_RegCloseKey
0x180004975  mov     [rbp+hKey], rsi
0x180004979  jmp     short loc_180004986
0x18000497b  jle     short loc_180004986
0x18000497d  movzx   ebx, ax
0x180004980  or      ebx, 80070000h
0x180004986  mov     rcx, cs:?g_pPublisher@@3PEAVCResourcePublisher@@EA; CResourcePublisher * g_pPublisher
0x18000498d  test    ebx, ebx
0x18000498f  jnz     short loc_1800049EC
0x180004991  test    rcx, rcx
0x180004994  jnz     short loc_1800049EC
0x180004996  lea     ecx, [rbx+10h]; Size
0x180004999  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000499e  mov     rcx, rax
0x1800049a1  test    rax, rax
0x1800049a4  jz      short loc_1800049DD
0x1800049a6  mov     [rcx+8], rsi
0x1800049aa  lea     rax, ??_7CResourcePublisher@@6B@; const CResourcePublisher::`vftable'
0x1800049b1  mov     [rcx], rax
0x1800049b4  mov     cs:?g_pPublisher@@3PEAVCResourcePublisher@@EA, rcx; CResourcePublisher * g_pPublisher
0x1800049bb  test    rdi, rdi
0x1800049be  jz      short loc_1800049E7
0x1800049c0  mov     rax, [rax]
0x1800049c3  lea     r9, aPublication; "Publication"
0x1800049ca  lea     r8, aProviderMicros; "Provider\\Microsoft.Base.Publication"
0x1800049d1  mov     rdx, rdi
0x1800049d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049d9  mov     ebx, eax
0x1800049db  jmp     short loc_1800049F1
0x1800049dd  mov     rcx, rsi
0x1800049e0  mov     cs:?g_pPublisher@@3PEAVCResourcePublisher@@EA, rcx; CResourcePublisher * g_pPublisher
0x1800049e7  mov     ebx, 8007000Eh
0x1800049ec  test    rdi, rdi
0x1800049ef  jz      short loc_180004A00
0x1800049f1  mov     rcx, rdi; Block
0x1800049f4  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800049f9  mov     rcx, cs:?g_pPublisher@@3PEAVCResourcePublisher@@EA; CResourcePublisher * g_pPublisher
0x180004a00  test    ebx, ebx
0x180004a02  jnz     short loc_180004A14
0x180004a04  mov     rax, [rcx]
0x180004a07  xor     edx, edx
0x180004a09  mov     rax, [rax+8]
0x180004a0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a12  mov     ebx, eax
0x180004a14  mov     eax, ebx
0x180004a16  mov     rbx, [rsp+30h+arg_18]
0x180004a1b  add     rsp, 30h
0x180004a1f  pop     rdi
0x180004a20  pop     rsi
0x180004a21  pop     rbp
0x180004a22  retn
```
