# GpFontLink::CacheFontSubstitutionDataW(void)

- ea: `0x1800b765c`
- end: `0x1800b792b`
- name: `?CacheFontSubstitutionDataW@GpFontLink@@AEAAXXZ`
- size: `719`
- prototype: `void __fastcall(GpFontLink *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800e1d70`

## callees

- `0x180034ae0`
- `0x1800b765c`
- `0x1800b7934`
- `0x1800b7aac`
- `0x1800b7bb8`
- `0x1800e7e40`
- `0x1800e9380`
- `0x1800e9898`
- `0x180175010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b786e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b78b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b786e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b78b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b788a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b78d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b788a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b78d0`

## string_xrefs

- `0x1800b78b1`: `RegOpenKeyExW`

## pseudocode

```c
void __fastcall GpFontLink::CacheFontSubstitutionDataW(GpFontLink *this)
{
  FARPROC ProcAddress; // rax
  __int64 v3; // rax
  unsigned int v4; // edi
  FARPROC v5; // rax
  __int64 v6; // rsi
  DWORD v7; // eax
  int v8; // ecx
  __int64 i; // rax
  struct GpFontFamily *Family; // rax
  unsigned int j; // edx
  __int64 v12; // r8
  __int16 v13; // r9
  DWORD LastError; // eax
  int v15; // edx
  int v16; // r8d
  int v17; // r9d
  __int64 *v18; // [rsp+20h] [rbp-E0h]
  unsigned int v19; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v20; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v21; // [rsp+70h] [rbp-90h]
  int v22[3]; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned __int16 v23[264]; // [rsp+80h] [rbp-80h] BYREF
  _WORD v24[264]; // [rsp+290h] [rbp+190h] BYREF

  ProcAddress = (FARPROC)qword_1801B3D60;
  v20 = 0;
  if ( qword_1801B3D60 )
    goto LABEL_27;
  if ( (unsigned int)DLpLoadRegistryDll() )
    return;
  ProcAddress = GetProcAddress(g_hInstRegistryDLL, "RegOpenKeyExW");
  qword_1801B3D60 = (__int64)ProcAddress;
  if ( ProcAddress )
  {
LABEL_27:
    v18 = &v20;
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
    v21 = 0;
    if ( !(unsigned int)DLRegQueryInfoKeyW(v20, v15, v16, v17, (_DWORD)v18) )
    {
      if ( v21 )
      {
        v3 = GpMallocItems<FontSubstitutionEntry>(v21);
        *((_QWORD *)this + 3) = v3;
        if ( v3 )
        {
          v4 = 0;
          while ( 1 )
          {
            v5 = (FARPROC)qword_1801B3D80;
            v6 = v20;
            v19 = 260;
            v22[0] = 260;
            if ( qword_1801B3D80 )
              goto LABEL_10;
            if ( (unsigned int)DLpLoadRegistryDll() )
              break;
            v5 = GetProcAddress(g_hInstRegistryDLL, "RegEnumValueW");
            qword_1801B3D80 = (__int64)v5;
            if ( v5 )
LABEL_10:
              v7 = ((__int64 (__fastcall *)(__int64, _QWORD, _WORD *, unsigned int *, _QWORD, _QWORD, unsigned __int16 *, int *))v5)(
                     v6,
                     v4,
                     v24,
                     &v19,
                     0,
                     0,
                     v23,
                     v22);
            else
              v7 = GetLastError();
            if ( v7 )
              break;
            ++v4;
            v8 = v22[0] - 1;
            for ( i = v22[0] - 1; i >= 0; --i )
            {
              if ( v23[i] == 44 )
              {
                if ( (unsigned __int64)(2LL * v8) >= 0x208 )
                  _report_rangecheckfailure();
                v23[v8] = 0;
                break;
              }
              --v8;
            }
            Family = GpFontFamilyList::GetFamily(
                       *(GpFontFamilyList **)(*((_QWORD *)Globals::FontCollection + 2) + 8LL),
                       v23);
            if ( Family )
            {
              *(_QWORD *)(536LL * *((int *)this + 8) + *((_QWORD *)this + 3) + 528) = Family;
              for ( j = 0; j < v19; *(_WORD *)(*((_QWORD *)this + 3) + 2 * (v12 + 268LL * *((int *)this + 8))) = v13 )
              {
                v12 = j;
                v13 = v24[j];
                if ( v13 == 44 )
                  break;
                ++j;
              }
              *(_WORD *)(*((_QWORD *)this + 3) + 2 * (j + 268LL * *((int *)this + 8))) = 0;
              *(_DWORD *)(536LL * (int)(*((_DWORD *)this + 8))++ + *((_QWORD *)this + 3) + 520) = j;
            }
          }
        }
      }
    }
    DLRegCloseKey(v20);
  }
}

```

## disassembly

```asm
0x1800b765c  mov     [rsp-8+arg_8], rbx
0x1800b7661  mov     [rsp-8+arg_10], rsi
0x1800b7666  push    rbp
0x1800b7667  push    rdi
0x1800b7668  push    r14
0x1800b766a  lea     rbp, [rsp-3B0h]
0x1800b7672  sub     rsp, 4B0h
0x1800b7679  mov     rax, cs:__security_cookie
0x1800b7680  xor     rax, rsp
0x1800b7683  mov     [rbp+3C0h+var_20], rax
0x1800b768a  mov     rax, cs:qword_1801B3D60
0x1800b7691  xor     r14d, r14d
0x1800b7694  mov     [rsp+4C0h+var_458], r14
0x1800b7699  mov     rbx, rcx
0x1800b769c  test    rax, rax
0x1800b769f  jnz     loc_1800B78E1
0x1800b76a5  call    ?DLpLoadRegistryDll@@YAKXZ; DLpLoadRegistryDll(void)
0x1800b76aa  test    eax, eax
0x1800b76ac  jz      loc_1800B78AA
0x1800b76b2  mov     rcx, [rbp+3C0h+var_20]
0x1800b76b9  xor     rcx, rsp; StackCookie
0x1800b76bc  call    __security_check_cookie
0x1800b76c1  lea     r11, [rsp+4C0h+var_10]
0x1800b76c9  mov     rbx, [r11+28h]
0x1800b76cd  mov     rsi, [r11+30h]
0x1800b76d1  mov     rsp, r11
0x1800b76d4  pop     r14
0x1800b76d6  pop     rdi
0x1800b76d7  pop     rbp
0x1800b76d8  retn
0x1800b76da  test    eax, eax
0x1800b76dc  jnz     short loc_1800B76B2
0x1800b76de  mov     rcx, [rsp+4C0h+var_458]
0x1800b76e3  lea     rax, [rsp+4C0h+var_450]
0x1800b76e8  mov     [rsp+4C0h+var_488], rax
0x1800b76ed  mov     [rsp+4C0h+var_450], r14d
0x1800b76f2  call    DLRegQueryInfoKeyW
0x1800b76f7  test    eax, eax
0x1800b76f9  jnz     loc_1800B789B
0x1800b76ff  mov     eax, [rsp+4C0h+var_450]
0x1800b7703  test    eax, eax
0x1800b7705  jz      loc_1800B789B
0x1800b770b  mov     ecx, eax
0x1800b770d  call    ??$GpMallocItems@UFontSubstitutionEntry@@@@YAPEAUFontSubstitutionEntry@@_K@Z; GpMallocItems<FontSubstitutionEntry>(unsigned __int64)
0x1800b7712  mov     [rbx+18h], rax
0x1800b7716  test    rax, rax
0x1800b7719  jz      loc_1800B789B
0x1800b771f  mov     edi, r14d
0x1800b7722  mov     rax, cs:qword_1801B3D80
0x1800b7729  mov     rsi, [rsp+4C0h+var_458]
0x1800b772e  mov     [rsp+4C0h+var_460], 104h
0x1800b7736  mov     [rsp+4C0h+var_44C], 104h
0x1800b773e  test    rax, rax
0x1800b7741  jz      loc_1800B7857
0x1800b7747  lea     rcx, [rsp+4C0h+var_44C]
0x1800b774c  mov     edx, edi
0x1800b774e  mov     [rsp+4C0h+var_488], rcx
0x1800b7753  lea     r9, [rsp+4C0h+var_460]
0x1800b7758  lea     rcx, [rbp+3C0h+var_440]
0x1800b775c  mov     [rsp+4C0h+var_490], rcx
0x1800b7761  lea     r8, [rbp+3C0h+var_230]
0x1800b7768  mov     [rsp+4C0h+var_498], r14
0x1800b776d  mov     rcx, rsi
0x1800b7770  mov     [rsp+4C0h+var_4A0], r14
0x1800b7775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b777a  test    eax, eax
0x1800b777c  jnz     loc_1800B789B
0x1800b7782  mov     ecx, [rsp+4C0h+var_44C]
0x1800b7786  inc     edi
0x1800b7788  dec     ecx
0x1800b778a  movsxd  rax, ecx
0x1800b778d  test    rax, rax
0x1800b7790  jns     loc_1800B7841
0x1800b7796  mov     rax, cs:?FontCollection@Globals@@3PEAVGpInstalledFontCollection@@EA; GpInstalledFontCollection * Globals::FontCollection
0x1800b779d  lea     rdx, [rbp+3C0h+var_440]; unsigned __int16 *
0x1800b77a1  mov     rcx, [rax+10h]
0x1800b77a5  mov     rcx, [rcx+8]; this
0x1800b77a9  call    ?GetFamily@GpFontFamilyList@@QEBAPEAVGpFontFamily@@PEBG@Z; GpFontFamilyList::GetFamily(ushort const *)
0x1800b77ae  test    rax, rax
0x1800b77b1  jz      loc_1800B7722
0x1800b77b7  movsxd  rcx, dword ptr [rbx+20h]
0x1800b77bb  imul    rdx, rcx, 218h
0x1800b77c2  mov     rcx, [rbx+18h]
0x1800b77c6  mov     [rdx+rcx+210h], rax
0x1800b77ce  mov     edx, r14d
0x1800b77d1  cmp     [rsp+4C0h+var_460], r14d
0x1800b77d6  jbe     short loc_1800B780A
0x1800b77d8  mov     r8d, edx
0x1800b77db  movzx   r9d, [rbp+r8*2+3C0h+var_230]
0x1800b77e4  cmp     r9w, 2Ch ; ','
0x1800b77e9  jz      short loc_1800B780A
0x1800b77eb  movsxd  rax, dword ptr [rbx+20h]
0x1800b77ef  inc     edx
0x1800b77f1  imul    rcx, rax, 10Ch
0x1800b77f8  mov     rax, [rbx+18h]
0x1800b77fc  add     rcx, r8
0x1800b77ff  mov     [rax+rcx*2], r9w
0x1800b7804  cmp     edx, [rsp+4C0h+var_460]
0x1800b7808  jb      short loc_1800B77D8
0x1800b780a  movsxd  rax, dword ptr [rbx+20h]
0x1800b780e  imul    rcx, rax, 10Ch
0x1800b7815  mov     eax, edx
0x1800b7817  add     rcx, rax
0x1800b781a  mov     rax, [rbx+18h]
0x1800b781e  mov     [rax+rcx*2], r14w
0x1800b7823  movsxd  rax, dword ptr [rbx+20h]
0x1800b7827  imul    rcx, rax, 218h
0x1800b782e  mov     rax, [rbx+18h]
0x1800b7832  mov     [rcx+rax+208h], edx
0x1800b7839  inc     dword ptr [rbx+20h]
0x1800b783c  jmp     loc_1800B7722
0x1800b7841  cmp     [rbp+rax*2+3C0h+var_440], 2Ch ; ','
0x1800b7847  jz      loc_1800B790C
0x1800b784d  dec     ecx
0x1800b784f  dec     rax
0x1800b7852  jmp     loc_1800B778D
0x1800b7857  call    ?DLpLoadRegistryDll@@YAKXZ; DLpLoadRegistryDll(void)
0x1800b785c  test    eax, eax
0x1800b785e  jnz     short loc_1800B789B
0x1800b7860  mov     rcx, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; hModule
0x1800b7867  lea     rdx, aRegenumvaluew; "RegEnumValueW"
0x1800b786e  call    cs:__imp_GetProcAddress
0x1800b7875  nop     dword ptr [rax+rax+00h]
0x1800b787a  mov     cs:qword_1801B3D80, rax
0x1800b7881  test    rax, rax
0x1800b7884  jnz     loc_1800B7747
0x1800b788a  call    cs:__imp_GetLastError
0x1800b7891  nop     dword ptr [rax+rax+00h]
0x1800b7896  jmp     loc_1800B777A
0x1800b789b  mov     rcx, [rsp+4C0h+var_458]
0x1800b78a0  call    DLRegCloseKey
0x1800b78a5  jmp     loc_1800B76B2
0x1800b78aa  mov     rcx, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; hModule
0x1800b78b1  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x1800b78b8  call    cs:__imp_GetProcAddress
0x1800b78bf  nop     dword ptr [rax+rax+00h]
0x1800b78c4  mov     cs:qword_1801B3D60, rax
0x1800b78cb  test    rax, rax
0x1800b78ce  jnz     short loc_1800B78E1
0x1800b78d0  call    cs:__imp_GetLastError
0x1800b78d7  nop     dword ptr [rax+rax+00h]
0x1800b78dc  jmp     loc_1800B76DA
0x1800b78e1  lea     rcx, [rsp+4C0h+var_458]
0x1800b78e6  mov     r9d, 9
0x1800b78ec  mov     [rsp+4C0h+var_4A0], rcx
0x1800b78f1  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800b78f8  mov     rcx, 0FFFFFFFF80000002h
0x1800b78ff  xor     r8d, r8d
0x1800b7902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7907  jmp     loc_1800B76DA
0x1800b790c  movsxd  rax, ecx
0x1800b790f  add     rax, rax
0x1800b7912  cmp     rax, 208h
0x1800b7918  jnb     short loc_1800B7925
0x1800b791a  mov     [rbp+rax+3C0h+var_440], r14w
0x1800b7920  jmp     loc_1800B7796
0x1800b7925  call    __report_rangecheckfailure
```
