# GpFontLink::CacheFontSubstitutionDataW(void)

- ea: `0x180088c38`
- end: `0x180088ef1`
- name: `?CacheFontSubstitutionDataW@GpFontLink@@AEAAXXZ`
- size: `697`
- prototype: `void __fastcall(GpFontLink *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800f4614`

## callees

- `0x180088c38`
- `0x18008a940`
- `0x1800a9480`
- `0x1800a95f8`
- `0x1800a9704`
- `0x1800f37cc`
- `0x180105d40`
- `0x180106130`
- `0x180172010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180088e50`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180088e88`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180088e50`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180088e88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088e6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088ea0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088e6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088ea0`

## string_xrefs

- `0x180088e81`: `RegOpenKeyExW`

## pseudocode

```c
void __fastcall GpFontLink::CacheFontSubstitutionDataW(GpFontLink *this)
{
  FARPROC ProcAddress; // rax
  unsigned int i; // edi
  struct GpFontFamily *Family; // rax
  __int64 v5; // r8
  __int16 v6; // r9
  __int64 v7; // rdx
  __int64 v8; // rax
  FARPROC v9; // rax
  __int64 v10; // rsi
  DWORD v11; // eax
  int v12; // ecx
  DWORD LastError; // eax
  int v14; // edx
  int v15; // r8d
  int v16; // r9d
  __int64 *v17; // [rsp+20h] [rbp-E0h]
  unsigned int v18; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v19; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v20; // [rsp+70h] [rbp-90h]
  int v21[3]; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned __int16 v22[264]; // [rsp+80h] [rbp-80h] BYREF
  _WORD v23[264]; // [rsp+290h] [rbp+190h] BYREF

  ProcAddress = (FARPROC)qword_1801AE7C0;
  v19 = 0;
  if ( qword_1801AE7C0 )
    goto LABEL_28;
  if ( (unsigned int)DLpLoadRegistryDll() )
    return;
  ProcAddress = GetProcAddress(g_hInstRegistryDLL, "RegOpenKeyExW");
  qword_1801AE7C0 = (__int64)ProcAddress;
  if ( ProcAddress )
  {
LABEL_28:
    v17 = &v19;
    LastError = ((__int64 (__fastcall *)(__int64, const wchar_t *, _QWORD, __int64))ProcAddress)(
                  -2147483646,
                  L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\FontSubstitutes",
                  0,
                  9);
  }
  else
  {
    LastError = GetLastError();
  }
  if ( !LastError )
  {
    v20 = 0;
    if ( !(unsigned int)DLRegQueryInfoKeyW(v19, v14, v15, v16, (_DWORD)v17) )
    {
      if ( v20 )
      {
        v8 = GpMallocItems<FontSubstitutionEntry>(v20);
        *((_QWORD *)this + 3) = v8;
        if ( v8 )
        {
          for ( i = 0; ; ++i )
          {
            v9 = (FARPROC)qword_1801AE7D8;
            v10 = v19;
            v18 = 260;
            v21[0] = 260;
            if ( qword_1801AE7D8 )
              goto LABEL_17;
            if ( (unsigned int)DLpLoadRegistryDll() )
              break;
            v9 = GetProcAddress(g_hInstRegistryDLL, "RegEnumValueW");
            qword_1801AE7D8 = (__int64)v9;
            if ( v9 )
LABEL_17:
              v11 = ((__int64 (__fastcall *)(__int64, _QWORD, _WORD *, unsigned int *, _QWORD, _QWORD, unsigned __int16 *, int *))v9)(
                      v10,
                      i,
                      v23,
                      &v18,
                      0,
                      0,
                      v22,
                      v21);
            else
              v11 = GetLastError();
            if ( v11 )
              break;
            v12 = v21[0];
            while ( --v12 >= 0 )
            {
              if ( v22[v12] == 44 )
              {
                if ( (unsigned __int64)(2LL * v12) >= 0x208 )
                  _report_rangecheckfailure();
                v22[v12] = 0;
                break;
              }
            }
            Family = GpFontFamilyList::GetFamily(
                       *(GpFontFamilyList **)(*((_QWORD *)Globals::FontCollection + 2) + 8LL),
                       v22);
            if ( Family )
            {
              v5 = 0;
              for ( *(_QWORD *)(536LL * *((int *)this + 8) + *((_QWORD *)this + 3) + 528) = Family;
                    (unsigned int)v5 < v18;
                    *(_WORD *)(*((_QWORD *)this + 3) + 2 * (v7 + 268LL * *((int *)this + 8))) = v6 )
              {
                v6 = v23[v5];
                v7 = (unsigned int)v5;
                if ( v6 == 44 )
                  break;
                v5 = (unsigned int)(v5 + 1);
              }
              *(_WORD *)(*((_QWORD *)this + 3) + 2 * ((unsigned int)v5 + 268LL * *((int *)this + 8))) = 0;
              *(_DWORD *)(536LL * (int)(*((_DWORD *)this + 8))++ + *((_QWORD *)this + 3) + 520) = v5;
            }
          }
        }
      }
    }
    DLRegCloseKey(v19);
  }
}

```

## disassembly

```asm
0x180088c38  push    rbp
0x180088c3a  push    rbx
0x180088c3b  push    rsi
0x180088c3c  push    rdi
0x180088c3d  lea     rbp, [rsp-3B8h]
0x180088c45  sub     rsp, 4B8h
0x180088c4c  mov     rax, cs:__security_cookie
0x180088c53  xor     rax, rsp
0x180088c56  mov     [rbp+3D0h+var_30], rax
0x180088c5d  mov     rax, cs:qword_1801AE7C0
0x180088c64  mov     rbx, rcx
0x180088c67  mov     [rsp+4D0h+var_468], 0
0x180088c70  test    rax, rax
0x180088c73  jnz     loc_180088EB1
0x180088c79  call    ?DLpLoadRegistryDll@@YAKXZ; DLpLoadRegistryDll(void)
0x180088c7e  test    eax, eax
0x180088c80  jz      loc_180088E7A
0x180088c86  mov     rcx, [rbp+3D0h+var_30]
0x180088c8d  xor     rcx, rsp; StackCookie
0x180088c90  call    __security_check_cookie
0x180088c95  add     rsp, 4B8h
0x180088c9c  pop     rdi
0x180088c9d  pop     rsi
0x180088c9e  pop     rbx
0x180088c9f  pop     rbp
0x180088ca0  retn
0x180088ca2  cmp     rdx, 208h
0x180088ca9  jnb     loc_180088EDC
0x180088caf  xor     eax, eax
0x180088cb1  mov     [rbp+rdx+3D0h+var_450], ax
0x180088cb6  mov     rax, cs:?FontCollection@Globals@@3PEAVGpInstalledFontCollection@@EA; GpInstalledFontCollection * Globals::FontCollection
0x180088cbd  lea     rdx, [rbp+3D0h+var_450]; unsigned __int16 *
0x180088cc1  inc     edi
0x180088cc3  mov     rcx, [rax+10h]
0x180088cc7  mov     rcx, [rcx+8]; this
0x180088ccb  call    ?GetFamily@GpFontFamilyList@@QEBAPEAVGpFontFamily@@PEBG@Z; GpFontFamilyList::GetFamily(ushort const *)
0x180088cd0  test    rax, rax
0x180088cd3  jz      loc_180088DAF
0x180088cd9  movsxd  rcx, dword ptr [rbx+20h]
0x180088cdd  xor     r8d, r8d
0x180088ce0  imul    rdx, rcx, 218h
0x180088ce7  mov     rcx, [rbx+18h]
0x180088ceb  mov     [rdx+rcx+210h], rax
0x180088cf3  cmp     [rsp+4D0h+var_470], r8d
0x180088cf8  jbe     short loc_180088D2E
0x180088cfa  movzx   r9d, [rbp+r8*2+3D0h+var_240]
0x180088d03  mov     edx, r8d
0x180088d06  cmp     r9w, 2Ch ; ','
0x180088d0b  jz      short loc_180088D2E
0x180088d0d  movsxd  rax, dword ptr [rbx+20h]
0x180088d11  inc     r8d
0x180088d14  imul    rcx, rax, 10Ch
0x180088d1b  mov     rax, [rbx+18h]
0x180088d1f  add     rcx, rdx
0x180088d22  mov     [rax+rcx*2], r9w
0x180088d27  cmp     r8d, [rsp+4D0h+var_470]
0x180088d2c  jb      short loc_180088CFA
0x180088d2e  movsxd  rax, dword ptr [rbx+20h]
0x180088d32  mov     rcx, [rbx+18h]
0x180088d36  imul    rdx, rax, 10Ch
0x180088d3d  mov     eax, r8d
0x180088d40  add     rdx, rax
0x180088d43  xor     eax, eax
0x180088d45  mov     [rcx+rdx*2], ax
0x180088d49  movsxd  rax, dword ptr [rbx+20h]
0x180088d4d  imul    rcx, rax, 218h
0x180088d54  mov     rax, [rbx+18h]
0x180088d58  mov     [rcx+rax+208h], r8d
0x180088d60  inc     dword ptr [rbx+20h]
0x180088d63  jmp     short loc_180088DAF
0x180088d65  test    eax, eax
0x180088d67  jnz     loc_180088C86
0x180088d6d  mov     rcx, [rsp+4D0h+var_468]
0x180088d72  mov     [rsp+4D0h+var_460], eax
0x180088d76  lea     rax, [rsp+4D0h+var_460]
0x180088d7b  mov     [rsp+4D0h+var_498], rax
0x180088d80  call    DLRegQueryInfoKeyW
0x180088d85  test    eax, eax
0x180088d87  jnz     loc_180088EE2
0x180088d8d  mov     eax, [rsp+4D0h+var_460]
0x180088d91  test    eax, eax
0x180088d93  jz      loc_180088EE2
0x180088d99  mov     ecx, eax
0x180088d9b  call    ??$GpMallocItems@UFontSubstitutionEntry@@@@YAPEAUFontSubstitutionEntry@@_K@Z; GpMallocItems<FontSubstitutionEntry>(unsigned __int64)
0x180088da0  mov     [rbx+18h], rax
0x180088da4  test    rax, rax
0x180088da7  jz      loc_180088EE2
0x180088dad  xor     edi, edi
0x180088daf  mov     rax, cs:qword_1801AE7D8
0x180088db6  mov     rsi, [rsp+4D0h+var_468]
0x180088dbb  mov     [rsp+4D0h+var_470], 104h
0x180088dc3  mov     [rsp+4D0h+var_45C], 104h
0x180088dcb  test    rax, rax
0x180088dce  jz      short loc_180088E35
0x180088dd0  lea     rcx, [rsp+4D0h+var_45C]
0x180088dd5  mov     edx, edi
0x180088dd7  mov     [rsp+4D0h+var_498], rcx
0x180088ddc  lea     r9, [rsp+4D0h+var_470]
0x180088de1  lea     rcx, [rbp+3D0h+var_450]
0x180088de5  mov     [rsp+4D0h+var_4A0], rcx
0x180088dea  lea     r8, [rbp+3D0h+var_240]
0x180088df1  mov     [rsp+4D0h+var_4A8], 0
0x180088dfa  mov     rcx, rsi
0x180088dfd  mov     [rsp+4D0h+var_4B0], 0
0x180088e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088e0b  test    eax, eax
0x180088e0d  jnz     loc_180088EE2
0x180088e13  mov     ecx, [rsp+4D0h+var_45C]
0x180088e17  dec     ecx
0x180088e19  test    ecx, ecx
0x180088e1b  js      loc_180088CB6
0x180088e21  movsxd  rax, ecx
0x180088e24  lea     rdx, [rax+rax]
0x180088e28  cmp     [rbp+rdx+3D0h+var_450], 2Ch ; ','
0x180088e2e  jnz     short loc_180088E17
0x180088e30  jmp     loc_180088CA2
0x180088e35  call    ?DLpLoadRegistryDll@@YAKXZ; DLpLoadRegistryDll(void)
0x180088e3a  test    eax, eax
0x180088e3c  jnz     loc_180088EE2
0x180088e42  mov     rcx, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180088e49  lea     rdx, aRegenumvaluew; "RegEnumValueW"
0x180088e50  call    cs:__imp_GetProcAddress
0x180088e57  nop     dword ptr [rax+rax+00h]
0x180088e5c  mov     cs:qword_1801AE7D8, rax
0x180088e63  test    rax, rax
0x180088e66  jnz     loc_180088DD0
0x180088e6c  call    cs:__imp_GetLastError
0x180088e73  nop     dword ptr [rax+rax+00h]
0x180088e78  jmp     short loc_180088E0B
0x180088e7a  mov     rcx, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180088e81  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x180088e88  call    cs:__imp_GetProcAddress
0x180088e8f  nop     dword ptr [rax+rax+00h]
0x180088e94  mov     cs:qword_1801AE7C0, rax
0x180088e9b  test    rax, rax
0x180088e9e  jnz     short loc_180088EB1
0x180088ea0  call    cs:__imp_GetLastError
0x180088ea7  nop     dword ptr [rax+rax+00h]
0x180088eac  jmp     loc_180088D65
0x180088eb1  lea     rcx, [rsp+4D0h+var_468]
0x180088eb6  mov     r9d, 9
0x180088ebc  mov     [rsp+4D0h+var_4B0], rcx
0x180088ec1  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180088ec8  mov     rcx, 0FFFFFFFF80000002h
0x180088ecf  xor     r8d, r8d
0x180088ed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180088ed7  jmp     loc_180088D65
0x180088edc  call    __report_rangecheckfailure
0x180088ee2  mov     rcx, [rsp+4D0h+var_468]
0x180088ee7  call    DLRegCloseKey
0x180088eec  jmp     loc_180088C86
```
