# GpFontLink::GetEudcDataFromTheRegistryW(void)

- ea: `0x1800a8f1c`
- end: `0x1800a926f`
- name: `?GetEudcDataFromTheRegistryW@GpFontLink@@AEAAXXZ`
- size: `851`
- prototype: `void __fastcall(GpFontLink *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x1800f4614`

## callees

- `0x180063cd8`
- `0x18008a940`
- `0x1800a8f1c`
- `0x1800a9278`
- `0x1800a95f8`
- `0x1800a9704`
- `0x180105d40`
- `0x180106130`
- `0x180172010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a9041`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a90da`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a9041`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a90da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9059`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a90f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a9059`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a90f2`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x1800a8f9b`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x1800a8f9b`

## string_xrefs

- `0x1800a903a`: `RegOpenKeyExW`

## pseudocode

```c
void __fastcall GpFontLink::GetEudcDataFromTheRegistryW(GpFontLink *this)
{
  _QWORD *v2; // rax
  int v3; // edi
  __int64 v4; // rcx
  int v5; // ebx
  UINT ACP; // r9d
  __int64 v7; // rax
  __int64 v8; // rcx
  FARPROC ProcAddress; // rax
  unsigned int v10; // ebx
  int RegistryDll; // eax
  int v12; // r12d
  FARPROC v13; // rax
  __int64 v14; // r14
  int v15; // edi
  DWORD LastError; // eax
  const wchar_t *v17; // r8
  unsigned __int16 *i; // r9
  unsigned __int16 v19; // dx
  wchar_t v20; // cx
  struct GpFontFamily *v21; // rax
  struct GpFontFamily *Family; // r15
  struct GpFontFamily *v23; // r14
  struct GpFontFamily **v24; // rax
  struct GpFontFamily **v25; // rcx
  __int64 v26; // rax
  struct GpFontFamily *v27; // rdx
  int v28; // [rsp+50h] [rbp-B0h] BYREF
  int v29; // [rsp+54h] [rbp-ACh] BYREF
  _QWORD v30[3]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v31[264]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v32[264]; // [rsp+280h] [rbp+180h] BYREF

  v2 = (_QWORD *)GpMallocEx(16, 0);
  *((_QWORD *)this + 1) = v2;
  if ( !v2 )
    return;
  *v2 = 0;
  v3 = 0;
  *(_QWORD *)(*((_QWORD *)this + 1) + 8LL) = 0;
  do
  {
    v4 = v3++;
    v31[v4] = aEudc[v4];
  }
  while ( aEudc[v3] );
  v5 = 0;
  ACP = GetACP();
  do
  {
    if ( !ACP )
      break;
    v7 = (unsigned int)v5++;
    *((_WORD *)&v30[1] + v7) = ACP % 0xA + 48;
    ACP /= 0xAu;
  }
  while ( v5 < 5 );
  while ( --v5 >= 0 )
  {
    v8 = v3++;
    v31[v8] = *((_WORD *)&v30[1] + (unsigned int)v5);
  }
  if ( (unsigned __int64)(2LL * v3) >= 0x208 )
    _report_rangecheckfailure();
  ProcAddress = (FARPROC)qword_1801AE7C0;
  v10 = 0;
  v31[v3] = 0;
  v30[0] = 0;
  if ( ProcAddress )
    goto LABEL_15;
  RegistryDll = DLpLoadRegistryDll();
  if ( !RegistryDll )
  {
    ProcAddress = GetProcAddress(g_hInstRegistryDLL, "RegOpenKeyExW");
    qword_1801AE7C0 = (__int64)ProcAddress;
    if ( !ProcAddress )
    {
      RegistryDll = GetLastError();
      goto LABEL_16;
    }
LABEL_15:
    RegistryDll = ((__int64 (__fastcall *)(__int64, unsigned __int16 *, _QWORD, __int64, _QWORD *))ProcAddress)(
                    -2147483647,
                    v31,
                    0,
                    9,
                    v30);
  }
LABEL_16:
  v29 = 0;
  v12 = 1;
  v28 = 0;
  if ( !RegistryDll )
  {
    while ( 1 )
    {
      v13 = (FARPROC)qword_1801AE7D8;
      v14 = v30[0];
      v29 = 260;
      v28 = 260;
      if ( qword_1801AE7D8 )
        goto LABEL_21;
      v15 = DLpLoadRegistryDll();
      if ( v15 )
        goto LABEL_23;
      v13 = GetProcAddress(g_hInstRegistryDLL, "RegEnumValueW");
      qword_1801AE7D8 = (__int64)v13;
      if ( v13 )
LABEL_21:
        LastError = ((__int64 (__fastcall *)(__int64, _QWORD, unsigned __int16 *, int *, _QWORD, _QWORD, unsigned __int16 *, int *))v13)(
                      v14,
                      v10,
                      v32,
                      &v29,
                      0,
                      0,
                      v31,
                      &v28);
      else
        LastError = GetLastError();
      v15 = LastError;
LABEL_23:
      if ( v15 )
        goto LABEL_45;
      if ( !v12 )
        goto LABEL_38;
      v17 = L"SystemDefaultEUDCFont";
      for ( i = v32; ; ++i )
      {
        v19 = *i;
        v20 = *v17;
        if ( !*i )
          break;
        if ( !v20 )
          goto LABEL_38;
        if ( (unsigned __int16)(v19 - 97) <= 0x19u )
          v19 -= 32;
        if ( (unsigned __int16)(v20 - 97) <= 0x19u )
          v20 -= 32;
        if ( v19 < v20 || v19 > v20 )
          goto LABEL_38;
        ++v17;
      }
      if ( v20 )
      {
LABEL_38:
        Family = GpFontFamilyList::GetFamily(
                   *(GpFontFamilyList **)(*((_QWORD *)Globals::FontCollection + 2) + 8LL),
                   v32);
        if ( Family )
        {
          v23 = GpFontLink::CheckAndLoadTheFile(this, v31);
          if ( v23 )
          {
            v24 = (struct GpFontFamily **)GpMallocEx(24, 0);
            v25 = v24;
            if ( v24 )
            {
              *v24 = Family;
              v24[1] = v23;
              v26 = *((_QWORD *)this + 1);
              v27 = *(struct GpFontFamily **)(v26 + 8);
              if ( v27 )
              {
                v25[2] = v27;
                *(_QWORD *)(*((_QWORD *)this + 1) + 8LL) = v25;
              }
              else
              {
                *(_QWORD *)(v26 + 8) = v25;
                v25[2] = 0;
              }
              goto LABEL_43;
            }
          }
        }
LABEL_45:
        ++v10;
        if ( v15 )
          break;
      }
      else
      {
        v12 = 0;
        v21 = GpFontLink::CheckAndLoadTheFile(this, v31);
        if ( v21 )
          **((_QWORD **)this + 1) = v21;
LABEL_43:
        ++v10;
      }
    }
  }
  if ( v30[0] )
    DLRegCloseKey(v30[0]);
}

```

## disassembly

```asm
0x1800a8f1c  push    rbp
0x1800a8f1e  push    rbx
0x1800a8f1f  push    rsi
0x1800a8f20  push    rdi
0x1800a8f21  push    r12
0x1800a8f23  push    r13
0x1800a8f25  push    r14
0x1800a8f27  push    r15
0x1800a8f29  lea     rbp, [rsp-3A8h]
0x1800a8f31  sub     rsp, 4A8h
0x1800a8f38  mov     rax, cs:__security_cookie
0x1800a8f3f  xor     rax, rsp
0x1800a8f42  mov     [rbp+3E0h+var_50], rax
0x1800a8f49  xor     edx, edx
0x1800a8f4b  mov     rsi, rcx
0x1800a8f4e  lea     ecx, [rdx+10h]
0x1800a8f51  call    GpMallocEx
0x1800a8f56  xor     r13d, r13d
0x1800a8f59  mov     [rsi+8], rax
0x1800a8f5d  test    rax, rax
0x1800a8f60  jz      loc_1800A9245
0x1800a8f66  mov     [rax], r13
0x1800a8f69  lea     rdx, aEudc; "EUDC\\"
0x1800a8f70  mov     rax, [rsi+8]
0x1800a8f74  lea     r14d, [r13+1]
0x1800a8f78  mov     edi, r13d
0x1800a8f7b  mov     [rax+8], r13
0x1800a8f7f  movsxd  rcx, edi
0x1800a8f82  add     edi, r14d
0x1800a8f85  movzx   eax, word ptr [rdx+rcx*2]
0x1800a8f89  mov     [rsp+rcx*2+4E0h+var_470], ax
0x1800a8f8e  movsxd  rax, edi
0x1800a8f91  cmp     [rdx+rax*2], r13w
0x1800a8f96  jnz     short loc_1800A8F7F
0x1800a8f98  mov     ebx, r13d
0x1800a8f9b  call    cs:__imp_GetACP
0x1800a8fa2  nop     dword ptr [rax+rax+00h]
0x1800a8fa7  mov     r9d, eax
0x1800a8faa  test    r9d, r9d
0x1800a8fad  jz      short loc_1800A8FF7
0x1800a8faf  mov     eax, 0CCCCCCCDh
0x1800a8fb4  mul     r9d
0x1800a8fb7  mov     eax, ebx
0x1800a8fb9  add     ebx, r14d
0x1800a8fbc  shr     edx, 3
0x1800a8fbf  movzx   ecx, dx
0x1800a8fc2  shl     cx, 2
0x1800a8fc6  lea     r8d, [rcx+rdx]
0x1800a8fca  add     r8w, r8w
0x1800a8fce  sub     r9w, r8w
0x1800a8fd2  add     r9w, 30h ; '0'
0x1800a8fd7  mov     [rsp+rax*2+4E0h+var_480], r9w
0x1800a8fdd  mov     r9d, edx
0x1800a8fe0  cmp     ebx, 5
0x1800a8fe3  jl      short loc_1800A8FAA
0x1800a8fe5  jmp     short loc_1800A8FF7
0x1800a8fe7  movzx   eax, [rsp+rbx*2+4E0h+var_480]
0x1800a8fec  movsxd  rcx, edi
0x1800a8fef  add     edi, r14d
0x1800a8ff2  mov     [rsp+rcx*2+4E0h+var_470], ax
0x1800a8ff7  sub     ebx, r14d
0x1800a8ffa  jns     short loc_1800A8FE7
0x1800a8ffc  movsxd  rax, edi
0x1800a8fff  lea     rcx, [rax+rax]
0x1800a9003  cmp     rcx, 208h
0x1800a900a  jnb     loc_1800A9269
0x1800a9010  mov     rax, cs:qword_1801AE7C0
0x1800a9017  mov     ebx, r13d
0x1800a901a  mov     [rsp+rcx+4E0h+var_470], r13w
0x1800a9020  mov     [rsp+4E0h+var_488], r13
0x1800a9025  test    rax, rax
0x1800a9028  jnz     short loc_1800A9067
0x1800a902a  call    ?DLpLoadRegistryDll@@YAKXZ; DLpLoadRegistryDll(void)
0x1800a902f  test    eax, eax
0x1800a9031  jnz     short loc_1800A908B
0x1800a9033  mov     rcx, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; hModule
0x1800a903a  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x1800a9041  call    cs:__imp_GetProcAddress
0x1800a9048  nop     dword ptr [rax+rax+00h]
0x1800a904d  mov     cs:qword_1801AE7C0, rax
0x1800a9054  test    rax, rax
0x1800a9057  jnz     short loc_1800A9067
0x1800a9059  call    cs:__imp_GetLastError
0x1800a9060  nop     dword ptr [rax+rax+00h]
0x1800a9065  jmp     short loc_1800A908B
0x1800a9067  lea     rcx, [rsp+4E0h+var_488]
0x1800a906c  mov     r9d, 9
0x1800a9072  mov     [rsp+4E0h+var_4C0], rcx
0x1800a9077  lea     rdx, [rsp+4E0h+var_470]
0x1800a907c  mov     rcx, 0FFFFFFFF80000001h
0x1800a9083  xor     r8d, r8d
0x1800a9086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a908b  mov     [rsp+4E0h+var_48C], r13d
0x1800a9090  mov     r12d, r14d
0x1800a9093  mov     [rsp+4E0h+var_490], r13d
0x1800a9098  test    eax, eax
0x1800a909a  jnz     loc_1800A9236
0x1800a90a0  mov     rax, cs:qword_1801AE7D8
0x1800a90a7  mov     r14, [rsp+4E0h+var_488]
0x1800a90ac  mov     [rsp+4E0h+var_48C], 104h
0x1800a90b4  mov     [rsp+4E0h+var_490], 104h
0x1800a90bc  test    rax, rax
0x1800a90bf  jnz     short loc_1800A9100
0x1800a90c1  call    ?DLpLoadRegistryDll@@YAKXZ; DLpLoadRegistryDll(void)
0x1800a90c6  mov     edi, eax
0x1800a90c8  test    eax, eax
0x1800a90ca  jnz     short loc_1800A9136
0x1800a90cc  mov     rcx, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; hModule
0x1800a90d3  lea     rdx, aRegenumvaluew; "RegEnumValueW"
0x1800a90da  call    cs:__imp_GetProcAddress
0x1800a90e1  nop     dword ptr [rax+rax+00h]
0x1800a90e6  mov     cs:qword_1801AE7D8, rax
0x1800a90ed  test    rax, rax
0x1800a90f0  jnz     short loc_1800A9100
0x1800a90f2  call    cs:__imp_GetLastError
0x1800a90f9  nop     dword ptr [rax+rax+00h]
0x1800a90fe  jmp     short loc_1800A9134
0x1800a9100  lea     rcx, [rsp+4E0h+var_490]
0x1800a9105  mov     edx, ebx
0x1800a9107  mov     [rsp+4E0h+var_4A8], rcx
0x1800a910c  lea     r9, [rsp+4E0h+var_48C]
0x1800a9111  lea     rcx, [rsp+4E0h+var_470]
0x1800a9116  mov     [rsp+4E0h+var_4B0], rcx
0x1800a911b  lea     r8, [rbp+3E0h+var_260]
0x1800a9122  mov     [rsp+4E0h+var_4B8], r13
0x1800a9127  mov     rcx, r14
0x1800a912a  mov     [rsp+4E0h+var_4C0], r13
0x1800a912f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9134  mov     edi, eax
0x1800a9136  test    edi, edi
0x1800a9138  jnz     loc_1800A922C
0x1800a913e  test    r12d, r12d
0x1800a9141  jz      short loc_1800A91B1
0x1800a9143  lea     r8, aSystemdefaulte; "SystemDefaultEUDCFont"
0x1800a914a  lea     r9, [rbp+3E0h+var_260]
0x1800a9151  movzx   edx, word ptr [r9]
0x1800a9155  movzx   ecx, word ptr [r8]
0x1800a9159  test    dx, dx
0x1800a915c  jz      short loc_1800A918E
0x1800a915e  test    cx, cx
0x1800a9161  jz      short loc_1800A91B1
0x1800a9163  lea     eax, [rdx-61h]
0x1800a9166  cmp     ax, 19h
0x1800a916a  ja      short loc_1800A9170
0x1800a916c  sub     dx, 20h ; ' '
0x1800a9170  lea     eax, [rcx-61h]
0x1800a9173  cmp     ax, 19h
0x1800a9177  ja      short loc_1800A917D
0x1800a9179  sub     cx, 20h ; ' '
0x1800a917d  cmp     dx, cx
0x1800a9180  jb      short loc_1800A91B1
0x1800a9182  ja      short loc_1800A91B1
0x1800a9184  add     r9, 2
0x1800a9188  add     r8, 2
0x1800a918c  jmp     short loc_1800A9151
0x1800a918e  test    cx, cx
0x1800a9191  jnz     short loc_1800A91B1
0x1800a9193  lea     rdx, [rsp+4E0h+var_470]; unsigned __int16 *
0x1800a9198  mov     rcx, rsi; this
0x1800a919b  mov     r12d, r13d
0x1800a919e  call    ?CheckAndLoadTheFile@GpFontLink@@AEAAPEAVGpFontFamily@@PEBG@Z; GpFontLink::CheckAndLoadTheFile(ushort const *)
0x1800a91a3  test    rax, rax
0x1800a91a6  jz      short loc_1800A9217
0x1800a91a8  mov     rcx, [rsi+8]
0x1800a91ac  mov     [rcx], rax
0x1800a91af  jmp     short loc_1800A9217
0x1800a91b1  mov     rax, cs:?FontCollection@Globals@@3PEAVGpInstalledFontCollection@@EA; GpInstalledFontCollection * Globals::FontCollection
0x1800a91b8  lea     rdx, [rbp+3E0h+var_260]; unsigned __int16 *
0x1800a91bf  mov     rcx, [rax+10h]
0x1800a91c3  mov     rcx, [rcx+8]; this
0x1800a91c7  call    ?GetFamily@GpFontFamilyList@@QEBAPEAVGpFontFamily@@PEBG@Z; GpFontFamilyList::GetFamily(ushort const *)
0x1800a91cc  mov     r15, rax
0x1800a91cf  test    rax, rax
0x1800a91d2  jz      short loc_1800A922C
0x1800a91d4  lea     rdx, [rsp+4E0h+var_470]; unsigned __int16 *
0x1800a91d9  mov     rcx, rsi; this
0x1800a91dc  call    ?CheckAndLoadTheFile@GpFontLink@@AEAAPEAVGpFontFamily@@PEBG@Z; GpFontLink::CheckAndLoadTheFile(ushort const *)
0x1800a91e1  mov     r14, rax
0x1800a91e4  test    rax, rax
0x1800a91e7  jz      short loc_1800A922C
0x1800a91e9  xor     edx, edx
0x1800a91eb  lea     ecx, [rdx+18h]
0x1800a91ee  call    GpMallocEx
0x1800a91f3  mov     rcx, rax
0x1800a91f6  test    rax, rax
0x1800a91f9  jz      short loc_1800A922C
0x1800a91fb  mov     [rax], r15
0x1800a91fe  mov     [rax+8], r14
0x1800a9202  mov     rax, [rsi+8]
0x1800a9206  mov     rdx, [rax+8]
0x1800a920a  test    rdx, rdx
0x1800a920d  jnz     short loc_1800A921E
0x1800a920f  mov     [rax+8], rcx
0x1800a9213  mov     [rcx+10h], r13
0x1800a9217  inc     ebx
0x1800a9219  jmp     loc_1800A90A0
0x1800a921e  mov     [rcx+10h], rdx
0x1800a9222  mov     rax, [rsi+8]
0x1800a9226  mov     [rax+8], rcx
0x1800a922a  jmp     short loc_1800A9217
0x1800a922c  inc     ebx
0x1800a922e  test    edi, edi
0x1800a9230  jz      loc_1800A90A0
0x1800a9236  mov     rcx, [rsp+4E0h+var_488]
0x1800a923b  test    rcx, rcx
0x1800a923e  jz      short loc_1800A9245
0x1800a9240  call    DLRegCloseKey
0x1800a9245  mov     rcx, [rbp+3E0h+var_50]
0x1800a924c  xor     rcx, rsp; StackCookie
0x1800a924f  call    __security_check_cookie
0x1800a9254  add     rsp, 4A8h
0x1800a925b  pop     r15
0x1800a925d  pop     r14
0x1800a925f  pop     r13
0x1800a9261  pop     r12
0x1800a9263  pop     rdi
0x1800a9264  pop     rsi
0x1800a9265  pop     rbx
0x1800a9266  pop     rbp
0x1800a9267  retn
0x1800a9269  call    __report_rangecheckfailure
```
