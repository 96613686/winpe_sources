# GpFontLink::GetFontLinkingDataFromRegistryW(void)

- ea: `0x1800346a4`
- end: `0x180034ad7`
- name: `?GetFontLinkingDataFromRegistryW@GpFontLink@@AEAAXXZ`
- size: `1075`
- prototype: `void __fastcall(GpFontLink *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800e1d70`

## callees

- `0x180009cf4`
- `0x18001f950`
- `0x1800346a4`
- `0x180034ae0`
- `0x180035a1c`
- `0x1800b79e8`
- `0x1800b7aac`
- `0x1800b7bb8`
- `0x1800e5044`
- `0x1800e9380`
- `0x1800e9898`
- `0x180175010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800349bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180034a0d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800349bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180034a0d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800347dc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800348bb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800347dc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800348bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800349d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034a25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800349d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034a25`

## string_xrefs

- `0x180034a46`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\FontLink\SystemLink`
- `0x180034a06`: `RegOpenKeyExW`

## pseudocode

```c
void __fastcall GpFontLink::GetFontLinkingDataFromRegistryW(GpFontLink *this)
{
  FARPROC ProcAddress; // rax
  unsigned int v2; // esi
  unsigned int v3; // r13d
  __int64 v4; // rdi
  FARPROC v5; // rax
  __int64 v6; // rbx
  int RegistryDll; // eax
  _QWORD *v8; // rbx
  struct GpFontFamily *Family; // rax
  unsigned int v10; // esi
  unsigned int v11; // r12d
  int v12; // r15d
  WCHAR v13; // cx
  __int64 v14; // rax
  struct GpFontFamily *v15; // r14
  _QWORD *v16; // rax
  _QWORD *v17; // rcx
  GpFontLink *v18; // r14
  WCHAR *v19; // rcx
  unsigned int v20; // r8d
  WCHAR v21; // dx
  DWORD LastError; // eax
  __int64 *v23; // [rsp+28h] [rbp-E0h]
  int v24; // [rsp+30h] [rbp-D8h]
  __int64 v25; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v26; // [rsp+60h] [rbp-A8h] BYREF
  int v27; // [rsp+68h] [rbp-A0h]
  _QWORD *v28; // [rsp+70h] [rbp-98h]
  GpFontLink *v29; // [rsp+78h] [rbp-90h]
  WCHAR FileName[264]; // [rsp+88h] [rbp-80h] BYREF
  unsigned __int16 v31[264]; // [rsp+298h] [rbp+190h] BYREF
  WCHAR Buffer[264]; // [rsp+4A8h] [rbp+3A0h] BYREF

  ProcAddress = (FARPROC)qword_1801B3D60;
  v29 = this;
  v26 = 0;
  v2 = 0;
  v3 = 520;
  v25 = 0;
  if ( qword_1801B3D60 )
    goto LABEL_45;
  if ( (unsigned int)DLpLoadRegistryDll() )
    return;
  ProcAddress = GetProcAddress(g_hInstRegistryDLL, "RegOpenKeyExW");
  qword_1801B3D60 = (__int64)ProcAddress;
  if ( ProcAddress )
  {
LABEL_45:
    v23 = &v26;
    LastError = ((__int64 (__fastcall *)(__int64, const wchar_t *, _QWORD, __int64))ProcAddress)(
                  -2147483646,
                  L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\FontLink\\SystemLink",
                  0,
                  9);
  }
  else
  {
    LastError = GetLastError();
  }
  if ( !LastError )
  {
    v4 = GpMallocEx(520, 0);
    if ( !v4 )
      goto LABEL_42;
    while ( 1 )
    {
      v5 = (FARPROC)qword_1801B3D80;
      v6 = v26;
      v25 = v3 | 0x10400000000LL;
      if ( qword_1801B3D80 )
        break;
      RegistryDll = DLpLoadRegistryDll();
      if ( !RegistryDll )
      {
        v5 = GetProcAddress(g_hInstRegistryDLL, "RegEnumValueW");
        qword_1801B3D80 = (__int64)v5;
        if ( v5 )
          break;
        RegistryDll = GetLastError();
      }
LABEL_8:
      if ( RegistryDll == 234 )
      {
        HIDWORD(v25) = 260;
        v3 *= 2;
        GpFree(v4);
        v4 = GpMallocEx(v3, 0);
        if ( !v4 )
          goto LABEL_42;
        LODWORD(v25) = v3;
        RegistryDll = DLRegEnumValueW(
                        v26,
                        v2,
                        (unsigned int)v31,
                        (unsigned int)&v25 + 4,
                        (_DWORD)v23,
                        v24,
                        v4,
                        (__int64)&v25);
      }
      if ( RegistryDll )
      {
        GpFree(v4);
LABEL_42:
        DLRegCloseKey(v26);
        return;
      }
      v27 = ++v2;
      v8 = HeapAlloc(GpRuntime::GpMemHeap, 0, 0x18u);
      if ( v8 )
      {
        v28 = 0;
        Family = GpFontFamilyList::GetFamily(
                   *(GpFontFamilyList **)(*((_QWORD *)Globals::FontCollection + 2) + 8LL),
                   v31);
        *v8 = Family;
        if ( Family )
        {
          v8[1] = 0;
          v10 = 0;
          v8[2] = 0;
          v11 = 0;
          LODWORD(v25) = (unsigned int)v25 >> 1;
          v12 = 0;
          while ( v11 < (unsigned int)v25 )
          {
            v13 = *(_WORD *)(v4 + 2LL * v11);
            if ( v13 == 44 )
            {
              v10 = 0;
              v12 = 1;
            }
            else if ( v13 )
            {
              v14 = v10++;
              FileName[v14] = v13;
            }
            else if ( v10 )
            {
              if ( 2 * (unsigned __int64)v10 >= 0x208 )
                _report_rangecheckfailure();
              FileName[v10] = 0;
              v10 = 0;
              if ( v12 )
              {
                v12 = 0;
                v15 = GpFontFamilyList::GetFamily(
                        *(GpFontFamilyList **)(*((_QWORD *)Globals::FontCollection + 2) + 8LL),
                        FileName);
                if ( v15 )
                {
                  v16 = HeapAlloc(GpRuntime::GpMemHeap, 0, 0x10u);
                  if ( v16 )
                  {
                    v17 = v28;
                    *v16 = v15;
                    if ( v17 )
                    {
                      v16[1] = 0;
                      v17[1] = v16;
                    }
                    else
                    {
                      v16[1] = v8[1];
                      v8[1] = v16;
                    }
                    v28 = v16;
                  }
                }
              }
              else if ( (unsigned int)MakePathName(Buffer, FileName) )
              {
                v19 = Buffer;
                v20 = 0;
                while ( 1 )
                {
                  v21 = *v19;
                  if ( !*v19 )
                    break;
                  if ( (unsigned __int16)(v21 - 97) <= 0x19u )
                    v21 -= 32;
                  *v19 = v21;
                  ++v20;
                  ++v19;
                  if ( v20 >= 0x104 )
                    goto LABEL_36;
                }
                *v19 = 0;
LABEL_36:
                GpFontTable::GetFirstFontFamilyFromFile(*((GpFontTable **)Globals::FontCollection + 2), Buffer);
              }
            }
            ++v11;
          }
          v18 = v29;
          v2 = v27;
          v8[2] = *(_QWORD *)v29;
          *(_QWORD *)v18 = v8;
        }
        else
        {
          GpFree(v8);
        }
      }
    }
    v24 = 0;
    LODWORD(v23) = 0;
    RegistryDll = ((__int64 (__fastcall *)(__int64, _QWORD, unsigned __int16 *, char *))v5)(
                    v6,
                    v2,
                    v31,
                    (char *)&v25 + 4);
    goto LABEL_8;
  }
}

```

## disassembly

```asm
0x1800346a4  mov     rax, rsp
0x1800346a7  mov     [rax+10h], rbx
0x1800346ab  mov     [rax+18h], rsi
0x1800346af  mov     [rax+20h], rdi
0x1800346b3  push    rbp
0x1800346b4  push    r12
0x1800346b6  push    r13
0x1800346b8  push    r14
0x1800346ba  push    r15
0x1800346bc  lea     rbp, [rax-5E8h]
0x1800346c3  sub     rsp, 6C0h
0x1800346ca  mov     rax, cs:__security_cookie
0x1800346d1  xor     rax, rsp
0x1800346d4  mov     [rbp+5E0h+var_30], rax
0x1800346db  mov     rax, cs:qword_1801B3D60
0x1800346e2  xor     r14d, r14d
0x1800346e5  mov     [rsp+6E0h+var_670], rcx
0x1800346ea  mov     ebx, 208h
0x1800346ef  mov     [rsp+6E0h+var_688], r14
0x1800346f4  mov     esi, r14d
0x1800346f7  mov     dword ptr [rsp+6E0h+var_690+4], r14d
0x1800346fc  mov     r13d, ebx
0x1800346ff  mov     dword ptr [rsp+6E0h+var_690], r14d
0x180034704  test    rax, rax
0x180034707  jnz     loc_180034A36
0x18003470d  call    ?DLpLoadRegistryDll@@YAKXZ; DLpLoadRegistryDll(void)
0x180034712  test    eax, eax
0x180034714  jz      loc_1800349FF
0x18003471a  mov     rcx, [rbp+5E0h+var_30]
0x180034721  xor     rcx, rsp; StackCookie
0x180034724  call    __security_check_cookie
0x180034729  lea     r11, [rsp+6E0h+var_20]
0x180034731  mov     rbx, [r11+38h]
0x180034735  mov     rsi, [r11+40h]
0x180034739  mov     rdi, [r11+48h]
0x18003473d  mov     rsp, r11
0x180034740  pop     r15
0x180034742  pop     r14
0x180034744  pop     r13
0x180034746  pop     r12
0x180034748  pop     rbp
0x180034749  retn
0x18003474b  test    eax, eax
0x18003474d  jnz     short loc_18003471A
0x18003474f  xor     edx, edx
0x180034751  mov     rcx, rbx
0x180034754  call    GpMallocEx
0x180034759  mov     rdi, rax
0x18003475c  test    rax, rax
0x18003475f  jz      loc_1800349F0
0x180034765  mov     rax, cs:qword_1801B3D80
0x18003476c  mov     rbx, [rsp+6E0h+var_688]
0x180034771  mov     dword ptr [rsp+6E0h+var_690+4], 104h
0x180034779  mov     dword ptr [rsp+6E0h+var_690], r13d
0x18003477e  test    rax, rax
0x180034781  jz      loc_1800349A0
0x180034787  lea     rcx, [rsp+6E0h+var_690]
0x18003478c  mov     edx, esi
0x18003478e  mov     [rsp+6E0h+var_6A8], rcx
0x180034793  lea     r9, [rsp+6E0h+var_690+4]
0x180034798  mov     [rsp+6E0h+var_6B0], rdi
0x18003479d  lea     r8, [rbp+5E0h+var_450]
0x1800347a4  mov     [rsp+6E0h+var_6B8], r14
0x1800347a9  mov     rcx, rbx
0x1800347ac  mov     [rsp+6E0h+var_6C0], r14
0x1800347b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800347b6  cmp     eax, 0EAh
0x1800347bb  jz      loc_180034A61
0x1800347c1  test    eax, eax
0x1800347c3  jnz     loc_1800349E8
0x1800347c9  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x1800347d0  lea     r8d, [rax+18h]; dwBytes
0x1800347d4  inc     esi
0x1800347d6  xor     edx, edx; dwFlags
0x1800347d8  mov     [rsp+6E0h+var_680], esi
0x1800347dc  call    cs:__imp_HeapAlloc
0x1800347e3  nop     dword ptr [rax+rax+00h]
0x1800347e8  mov     rbx, rax
0x1800347eb  test    rax, rax
0x1800347ee  jz      loc_180034765
0x1800347f4  mov     rcx, cs:?FontCollection@Globals@@3PEAVGpInstalledFontCollection@@EA; GpInstalledFontCollection * Globals::FontCollection
0x1800347fb  lea     rdx, [rbp+5E0h+var_450]; unsigned __int16 *
0x180034802  mov     [rsp+6E0h+var_678], r14
0x180034807  mov     rcx, [rcx+10h]
0x18003480b  mov     rcx, [rcx+8]; this
0x18003480f  call    ?GetFamily@GpFontFamilyList@@QEBAPEAVGpFontFamily@@PEBG@Z; GpFontFamilyList::GetFamily(ushort const *)
0x180034814  mov     [rbx], rax
0x180034817  test    rax, rax
0x18003481a  jz      loc_180034993
0x180034820  mov     [rbx+8], r14
0x180034824  mov     esi, r14d
0x180034827  mov     [rbx+10h], r14
0x18003482b  mov     r12d, r14d
0x18003482e  shr     dword ptr [rsp+6E0h+var_690], 1
0x180034832  mov     r15d, r14d
0x180034835  cmp     r12d, dword ptr [rsp+6E0h+var_690]
0x18003483a  jnb     loc_180034904
0x180034840  mov     eax, r12d
0x180034843  movzx   ecx, word ptr [rdi+rax*2]
0x180034847  cmp     cx, 2Ch ; ','
0x18003484b  jz      loc_1800348EE
0x180034851  test    cx, cx
0x180034854  jz      short loc_180034864
0x180034856  mov     eax, esi
0x180034858  inc     esi
0x18003485a  mov     [rbp+rax*2+5E0h+FileName], cx
0x18003485f  inc     r12d
0x180034862  jmp     short loc_180034835
0x180034864  test    esi, esi
0x180034866  jz      short loc_18003485F
0x180034868  mov     eax, esi
0x18003486a  add     rax, rax
0x18003486d  cmp     rax, 208h
0x180034873  jnb     loc_180034AD1
0x180034879  mov     [rbp+rax+5E0h+FileName], r14w
0x18003487f  mov     esi, r14d
0x180034882  lea     rdx, [rbp+5E0h+FileName]; lpFileName
0x180034886  test    r15d, r15d
0x180034889  jz      loc_18003492D
0x18003488f  mov     rax, cs:?FontCollection@Globals@@3PEAVGpInstalledFontCollection@@EA; GpInstalledFontCollection * Globals::FontCollection
0x180034896  mov     rcx, [rax+10h]
0x18003489a  mov     rcx, [rcx+8]; this
0x18003489e  call    ?GetFamily@GpFontFamilyList@@QEBAPEAVGpFontFamily@@PEBG@Z; GpFontFamilyList::GetFamily(ushort const *)
0x1800348a3  xor     r15d, r15d
0x1800348a6  mov     r14, rax
0x1800348a9  test    rax, rax
0x1800348ac  jz      short loc_1800348FC
0x1800348ae  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x1800348b5  lea     r8d, [r15+10h]; dwBytes
0x1800348b9  xor     edx, edx; dwFlags
0x1800348bb  call    cs:__imp_HeapAlloc
0x1800348c2  nop     dword ptr [rax+rax+00h]
0x1800348c7  test    rax, rax
0x1800348ca  jz      short loc_1800348FC
0x1800348cc  mov     rcx, [rsp+6E0h+var_678]
0x1800348d1  mov     [rax], r14
0x1800348d4  xor     r14d, r14d
0x1800348d7  test    rcx, rcx
0x1800348da  jz      short loc_18003491F
0x1800348dc  mov     [rax+8], r14
0x1800348e0  mov     [rcx+8], rax
0x1800348e4  mov     [rsp+6E0h+var_678], rax
0x1800348e9  jmp     loc_18003485F
0x1800348ee  mov     esi, r14d
0x1800348f1  mov     r15d, 1
0x1800348f7  jmp     loc_18003485F
0x1800348fc  xor     r14d, r14d
0x1800348ff  jmp     loc_18003485F
0x180034904  mov     r14, [rsp+6E0h+var_670]
0x180034909  mov     esi, [rsp+6E0h+var_680]
0x18003490d  mov     rax, [r14]
0x180034910  mov     [rbx+10h], rax
0x180034914  mov     [r14], rbx
0x180034917  xor     r14d, r14d
0x18003491a  jmp     loc_180034765
0x18003491f  mov     rcx, [rbx+8]
0x180034923  mov     [rax+8], rcx
0x180034927  mov     [rbx+8], rax
0x18003492b  jmp     short loc_1800348E4
0x18003492d  lea     rcx, [rbp+5E0h+Buffer]; lpBuffer
0x180034934  call    ?MakePathName@@YAHPEAGPEBG@Z; MakePathName(ushort *,ushort const *)
0x180034939  test    eax, eax
0x18003493b  jz      loc_18003485F
0x180034941  lea     rcx, [rbp+5E0h+Buffer]
0x180034948  mov     r8d, r14d
0x18003494b  movzx   edx, word ptr [rcx]
0x18003494e  test    dx, dx
0x180034951  jz      loc_180034AC8
0x180034957  lea     eax, [rdx-61h]
0x18003495a  cmp     ax, 19h
0x18003495e  jbe     loc_180034ABB
0x180034964  mov     [rcx], dx
0x180034967  inc     r8d
0x18003496a  add     rcx, 2
0x18003496e  cmp     r8d, 104h
0x180034975  jb      short loc_18003494B
0x180034977  mov     rcx, cs:?FontCollection@Globals@@3PEAVGpInstalledFontCollection@@EA; GpInstalledFontCollection * Globals::FontCollection
0x18003497e  lea     rdx, [rbp+5E0h+Buffer]; unsigned __int16 *
0x180034985  mov     rcx, [rcx+10h]; this
0x180034989  call    ?GetFirstFontFamilyFromFile@GpFontTable@@QEBAPEAVGpFontFamily@@PEBG@Z; GpFontTable::GetFirstFontFamilyFromFile(ushort const *)
0x18003498e  jmp     loc_18003485F
0x180034993  mov     rcx, rbx
0x180034996  call    GpFree
0x18003499b  jmp     loc_180034765
0x1800349a0  call    ?DLpLoadRegistryDll@@YAKXZ; DLpLoadRegistryDll(void)
0x1800349a5  test    eax, eax
0x1800349a7  jnz     loc_1800347B6
0x1800349ad  mov     rcx, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; hModule
0x1800349b4  lea     rdx, aRegenumvaluew; "RegEnumValueW"
0x1800349bb  call    cs:__imp_GetProcAddress
0x1800349c2  nop     dword ptr [rax+rax+00h]
0x1800349c7  mov     cs:qword_1801B3D80, rax
0x1800349ce  test    rax, rax
0x1800349d1  jnz     loc_180034787
0x1800349d7  call    cs:__imp_GetLastError
0x1800349de  nop     dword ptr [rax+rax+00h]
0x1800349e3  jmp     loc_1800347B6
0x1800349e8  mov     rcx, rdi
0x1800349eb  call    GpFree
0x1800349f0  mov     rcx, [rsp+6E0h+var_688]
0x1800349f5  call    DLRegCloseKey
0x1800349fa  jmp     loc_18003471A
0x1800349ff  mov     rcx, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180034a06  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x180034a0d  call    cs:__imp_GetProcAddress
0x180034a14  nop     dword ptr [rax+rax+00h]
0x180034a19  mov     cs:qword_1801B3D60, rax
0x180034a20  test    rax, rax
0x180034a23  jnz     short loc_180034A36
0x180034a25  call    cs:__imp_GetLastError
0x180034a2c  nop     dword ptr [rax+rax+00h]
0x180034a31  jmp     loc_18003474B
0x180034a36  lea     rcx, [rsp+6E0h+var_688]
0x180034a3b  mov     r9d, 9
0x180034a41  mov     [rsp+6E0h+var_6C0], rcx
0x180034a46  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180034a4d  mov     rcx, 0FFFFFFFF80000002h
0x180034a54  xor     r8d, r8d
0x180034a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034a5c  jmp     loc_18003474B
0x180034a61  mov     rcx, rdi
0x180034a64  mov     dword ptr [rsp+6E0h+var_690+4], 104h
0x180034a6c  add     r13d, r13d
0x180034a6f  call    GpFree
0x180034a74  mov     ecx, r13d
0x180034a77  xor     edx, edx
0x180034a79  call    GpMallocEx
0x180034a7e  mov     rdi, rax
0x180034a81  test    rax, rax
0x180034a84  jz      loc_1800349F0
0x180034a8a  mov     rcx, [rsp+6E0h+var_688]
0x180034a8f  lea     rax, [rsp+6E0h+var_690]
0x180034a94  mov     [rsp+6E0h+var_6A8], rax
0x180034a99  lea     r9, [rsp+6E0h+var_690+4]
0x180034a9e  lea     r8, [rbp+5E0h+var_450]
0x180034aa5  mov     [rsp+6E0h+var_6B0], rdi
0x180034aaa  mov     edx, esi
0x180034aac  mov     dword ptr [rsp+6E0h+var_690], r13d
0x180034ab1  call    DLRegEnumValueW
0x180034ab6  jmp     loc_1800347C1
0x180034abb  mov     eax, 0FFE0h
0x180034ac0  add     dx, ax
0x180034ac3  jmp     loc_180034964
0x180034ac8  mov     [rcx], r14w
0x180034acc  jmp     loc_180034977
0x180034ad1  call    __report_rangecheckfailure
```
