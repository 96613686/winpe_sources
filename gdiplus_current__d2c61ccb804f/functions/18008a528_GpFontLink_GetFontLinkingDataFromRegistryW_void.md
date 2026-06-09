# GpFontLink::GetFontLinkingDataFromRegistryW(void)

- ea: `0x18008a528`
- end: `0x18008a92b`
- name: `?GetFontLinkingDataFromRegistryW@GpFontLink@@AEAAXXZ`
- size: `1027`
- prototype: `void __fastcall(GpFontLink *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800f4614`

## callees

- `0x180010bd0`
- `0x180063cd8`
- `0x18008a528`
- `0x18008a940`
- `0x1800a93c8`
- `0x1800a9548`
- `0x1800a95f8`
- `0x1800a9704`
- `0x1800a9a54`
- `0x180105d40`
- `0x180106130`
- `0x180172010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008a597`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008a86a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008a597`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008a86a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008a65e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008a74c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008a65e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008a74c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a5b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a886`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a5b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a886`

## string_xrefs

- `0x18008a8b0`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\FontLink\SystemLink`
- `0x18008a590`: `RegOpenKeyExW`

## pseudocode

```c
void __fastcall GpFontLink::GetFontLinkingDataFromRegistryW(GpFontLink *this)
{
  FARPROC ProcAddress; // rax
  unsigned int v2; // r12d
  DWORD LastError; // eax
  unsigned int v4; // esi
  unsigned int v5; // r15d
  __int64 v6; // rdi
  FARPROC v7; // rax
  __int64 v8; // rbx
  int RegistryDll; // eax
  _QWORD *v10; // rbx
  struct GpFontFamily *Family; // rax
  int v12; // esi
  _QWORD *v13; // r13
  unsigned int v14; // r14d
  WCHAR v15; // cx
  __int64 v16; // rax
  struct GpFontFamily *v17; // rsi
  _QWORD *v18; // rax
  GpFontLink *v19; // r14
  WCHAR *v20; // rdx
  unsigned int v21; // r8d
  WCHAR v22; // cx
  __int64 *v23; // [rsp+20h] [rbp-E0h]
  int v24; // [rsp+28h] [rbp-D8h]
  unsigned int v25; // [rsp+50h] [rbp-B0h] BYREF
  int v26; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v27; // [rsp+58h] [rbp-A8h] BYREF
  int v28; // [rsp+60h] [rbp-A0h]
  GpFontLink *v29; // [rsp+68h] [rbp-98h]
  WCHAR FileName[264]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v31[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR Buffer[264]; // [rsp+490h] [rbp+390h] BYREF

  ProcAddress = (FARPROC)qword_1801AE7C0;
  v2 = 0;
  v29 = this;
  v27 = 0;
  v26 = 0;
  v25 = 0;
  if ( qword_1801AE7C0 )
    goto LABEL_46;
  if ( (unsigned int)DLpLoadRegistryDll() )
    return;
  ProcAddress = GetProcAddress(g_hInstRegistryDLL, "RegOpenKeyExW");
  qword_1801AE7C0 = (__int64)ProcAddress;
  if ( ProcAddress )
  {
LABEL_46:
    v23 = &v27;
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
    v4 = 0;
    v5 = 520;
    v6 = GpMallocEx(520, 0);
    if ( !v6 )
      goto LABEL_40;
    while ( 1 )
    {
      v7 = (FARPROC)qword_1801AE7D8;
      v8 = v27;
      v26 = 260;
      v25 = v5;
      if ( qword_1801AE7D8 )
        break;
      RegistryDll = DLpLoadRegistryDll();
      if ( !RegistryDll )
      {
        v7 = GetProcAddress(g_hInstRegistryDLL, "RegEnumValueW");
        qword_1801AE7D8 = (__int64)v7;
        if ( v7 )
          break;
        RegistryDll = GetLastError();
      }
LABEL_9:
      if ( RegistryDll == 234 )
      {
        v26 = 260;
        v5 *= 2;
        GpFree(v6);
        v6 = GpMallocEx(v5, 0);
        if ( !v6 )
          goto LABEL_40;
        v25 = v5;
        RegistryDll = DLRegEnumValueW(
                        v27,
                        v4,
                        (unsigned int)v31,
                        (unsigned int)&v26,
                        (_DWORD)v23,
                        v24,
                        v6,
                        (__int64)&v25);
      }
      if ( RegistryDll )
      {
        GpFree(v6);
LABEL_40:
        DLRegCloseKey(v27);
        return;
      }
      v28 = ++v4;
      v10 = HeapAlloc(GpRuntime::GpMemHeap, 0, 0x18u);
      if ( v10 )
      {
        Family = GpFontFamilyList::GetFamily(
                   *(GpFontFamilyList **)(*((_QWORD *)Globals::FontCollection + 2) + 8LL),
                   v31);
        *v10 = Family;
        if ( Family )
        {
          v10[1] = 0;
          v10[2] = 0;
          v12 = 0;
          v25 >>= 1;
          v13 = 0;
          v14 = 0;
          while ( v2 < v25 )
          {
            v15 = *(_WORD *)(v6 + 2LL * v2);
            if ( v15 == 44 )
            {
              v14 = 0;
              v12 = 1;
            }
            else if ( v15 )
            {
              v16 = v14++;
              FileName[v16] = v15;
            }
            else if ( v14 )
            {
              if ( 2 * (unsigned __int64)v14 >= 0x208 )
                _report_rangecheckfailure();
              FileName[v14] = 0;
              v14 = 0;
              if ( v12 )
              {
                v17 = GpFontFamilyList::GetFamily(
                        *(GpFontFamilyList **)(*((_QWORD *)Globals::FontCollection + 2) + 8LL),
                        FileName);
                if ( v17 )
                {
                  v18 = HeapAlloc(GpRuntime::GpMemHeap, 0, 0x10u);
                  if ( v18 )
                  {
                    *v18 = v17;
                    if ( v13 )
                    {
                      v18[1] = 0;
                      v13[1] = v18;
                    }
                    else
                    {
                      v18[1] = v10[1];
                      v10[1] = v18;
                    }
                    v13 = v18;
                  }
                }
                v12 = 0;
              }
              else if ( MakePathName(Buffer, FileName) )
              {
                v20 = Buffer;
                v21 = 0;
                while ( 1 )
                {
                  v22 = *v20;
                  if ( !*v20 )
                    break;
                  if ( (unsigned __int16)(v22 - 97) <= 0x19u )
                    v22 -= 32;
                  *v20 = v22;
                  ++v21;
                  ++v20;
                  if ( v21 >= 0x104 )
                    goto LABEL_37;
                }
                *v20 = 0;
LABEL_37:
                GpFontTable::GetFirstFontFamilyFromFile(*((GpFontTable **)Globals::FontCollection + 2), Buffer);
              }
            }
            ++v2;
          }
          v19 = v29;
          v2 = 0;
          v4 = v28;
          v10[2] = *(_QWORD *)v29;
          *(_QWORD *)v19 = v10;
        }
        else
        {
          GpFree(v10);
        }
      }
    }
    v24 = 0;
    LODWORD(v23) = 0;
    RegistryDll = ((__int64 (__fastcall *)(__int64, _QWORD, unsigned __int16 *, int *))v7)(v8, v4, v31, &v26);
    goto LABEL_9;
  }
}

```

## disassembly

```asm
0x18008a528  push    rbp
0x18008a52a  push    rbx
0x18008a52b  push    rsi
0x18008a52c  push    rdi
0x18008a52d  push    r12
0x18008a52f  push    r13
0x18008a531  push    r14
0x18008a533  push    r15
0x18008a535  lea     rbp, [rsp-5B8h]
0x18008a53d  sub     rsp, 6B8h
0x18008a544  mov     rax, cs:__security_cookie
0x18008a54b  xor     rax, rsp
0x18008a54e  mov     [rbp+5F0h+var_50], rax
0x18008a555  mov     rax, cs:qword_1801AE7C0
0x18008a55c  xor     r12d, r12d
0x18008a55f  mov     [rsp+6F0h+var_688], rcx
0x18008a564  mov     [rsp+6F0h+var_698], r12
0x18008a569  mov     [rsp+6F0h+var_69C], r12d
0x18008a56e  mov     [rsp+6F0h+var_6A0], r12d
0x18008a573  test    rax, rax
0x18008a576  jnz     loc_18008A8A0
0x18008a57c  call    ?DLpLoadRegistryDll@@YAKXZ; DLpLoadRegistryDll(void)
0x18008a581  test    eax, eax
0x18008a583  jnz     loc_18008A82B
0x18008a589  mov     rcx, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18008a590  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x18008a597  call    cs:__imp_GetProcAddress
0x18008a59e  nop     dword ptr [rax+rax+00h]
0x18008a5a3  mov     cs:qword_1801AE7C0, rax
0x18008a5aa  test    rax, rax
0x18008a5ad  jnz     loc_18008A8A0
0x18008a5b3  call    cs:__imp_GetLastError
0x18008a5ba  nop     dword ptr [rax+rax+00h]
0x18008a5bf  test    eax, eax
0x18008a5c1  jnz     loc_18008A82B
0x18008a5c7  mov     eax, 208h
0x18008a5cc  xor     edx, edx
0x18008a5ce  mov     ecx, eax
0x18008a5d0  mov     esi, r12d
0x18008a5d3  mov     r15d, eax
0x18008a5d6  call    GpMallocEx
0x18008a5db  mov     rdi, rax
0x18008a5de  test    rax, rax
0x18008a5e1  jz      loc_18008A821
0x18008a5e7  mov     rax, cs:qword_1801AE7D8
0x18008a5ee  mov     rbx, [rsp+6F0h+var_698]
0x18008a5f3  mov     [rsp+6F0h+var_69C], 104h
0x18008a5fb  mov     [rsp+6F0h+var_6A0], r15d
0x18008a600  test    rax, rax
0x18008a603  jz      loc_18008A84F
0x18008a609  lea     rcx, [rsp+6F0h+var_6A0]
0x18008a60e  mov     edx, esi
0x18008a610  mov     [rsp+6F0h+var_6B8], rcx
0x18008a615  lea     r9, [rsp+6F0h+var_69C]
0x18008a61a  mov     [rsp+6F0h+var_6C0], rdi
0x18008a61f  lea     r8, [rbp+5F0h+var_470]
0x18008a626  mov     [rsp+6F0h+var_6C8], r12
0x18008a62b  mov     rcx, rbx
0x18008a62e  mov     [rsp+6F0h+var_6D0], r12
0x18008a633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a638  cmp     eax, 0EAh
0x18008a63d  jz      loc_18008A8CB
0x18008a643  test    eax, eax
0x18008a645  jnz     loc_18008A819
0x18008a64b  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x18008a652  lea     r8d, [rax+18h]; dwBytes
0x18008a656  inc     esi
0x18008a658  xor     edx, edx; dwFlags
0x18008a65a  mov     [rsp+6F0h+var_690], esi
0x18008a65e  call    cs:__imp_HeapAlloc
0x18008a665  nop     dword ptr [rax+rax+00h]
0x18008a66a  mov     rbx, rax
0x18008a66d  test    rax, rax
0x18008a670  jz      loc_18008A5E7
0x18008a676  mov     rcx, cs:?FontCollection@Globals@@3PEAVGpInstalledFontCollection@@EA; GpInstalledFontCollection * Globals::FontCollection
0x18008a67d  lea     rdx, [rbp+5F0h+var_470]; unsigned __int16 *
0x18008a684  mov     rcx, [rcx+10h]
0x18008a688  mov     rcx, [rcx+8]; this
0x18008a68c  call    ?GetFamily@GpFontFamilyList@@QEBAPEAVGpFontFamily@@PEBG@Z; GpFontFamilyList::GetFamily(ushort const *)
0x18008a691  mov     [rbx], rax
0x18008a694  test    rax, rax
0x18008a697  jz      loc_18008A80C
0x18008a69d  xor     r9d, r9d
0x18008a6a0  mov     [rbx+8], r12
0x18008a6a4  mov     [rbx+10h], r12
0x18008a6a8  mov     esi, r9d
0x18008a6ab  shr     [rsp+6F0h+var_6A0], 1
0x18008a6af  mov     r13, r12
0x18008a6b2  mov     r14d, r12d
0x18008a6b5  cmp     r12d, [rsp+6F0h+var_6A0]
0x18008a6ba  jnb     loc_18008A775
0x18008a6c0  mov     eax, r12d
0x18008a6c3  movzx   ecx, word ptr [rdi+rax*2]
0x18008a6c7  cmp     cx, 2Ch ; ','
0x18008a6cb  jz      short loc_18008A735
0x18008a6cd  test    cx, cx
0x18008a6d0  jz      short loc_18008A6E2
0x18008a6d2  mov     eax, r14d
0x18008a6d5  inc     r14d
0x18008a6d8  mov     [rsp+rax*2+6F0h+FileName], cx
0x18008a6dd  inc     r12d
0x18008a6e0  jmp     short loc_18008A6B5
0x18008a6e2  test    r14d, r14d
0x18008a6e5  jz      short loc_18008A6DD
0x18008a6e7  mov     eax, r14d
0x18008a6ea  lea     rcx, [rax+rax]
0x18008a6ee  cmp     rcx, 208h
0x18008a6f5  jnb     loc_18008A925
0x18008a6fb  mov     [rsp+rcx+6F0h+FileName], r9w
0x18008a701  mov     r14d, r9d
0x18008a704  lea     rdx, [rsp+6F0h+FileName]; lpFileName
0x18008a709  test    esi, esi
0x18008a70b  jz      loc_18008A79E
0x18008a711  mov     rax, cs:?FontCollection@Globals@@3PEAVGpInstalledFontCollection@@EA; GpInstalledFontCollection * Globals::FontCollection
0x18008a718  mov     rcx, [rax+10h]
0x18008a71c  mov     rcx, [rcx+8]; this
0x18008a720  call    ?GetFamily@GpFontFamilyList@@QEBAPEAVGpFontFamily@@PEBG@Z; GpFontFamilyList::GetFamily(ushort const *)
0x18008a725  xor     r9d, r9d
0x18008a728  mov     rsi, rax
0x18008a72b  test    rax, rax
0x18008a72e  jnz     short loc_18008A73F
0x18008a730  mov     esi, r9d
0x18008a733  jmp     short loc_18008A6DD
0x18008a735  mov     r14d, r9d
0x18008a738  mov     esi, 1
0x18008a73d  jmp     short loc_18008A6DD
0x18008a73f  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x18008a746  xor     edx, edx; dwFlags
0x18008a748  lea     r8d, [rdx+10h]; dwBytes
0x18008a74c  call    cs:__imp_HeapAlloc
0x18008a753  nop     dword ptr [rax+rax+00h]
0x18008a758  xor     r9d, r9d
0x18008a75b  test    rax, rax
0x18008a75e  jz      short loc_18008A730
0x18008a760  mov     [rax], rsi
0x18008a763  test    r13, r13
0x18008a766  jz      short loc_18008A790
0x18008a768  mov     [rax+8], r9
0x18008a76c  mov     [r13+8], rax
0x18008a770  mov     r13, rax
0x18008a773  jmp     short loc_18008A730
0x18008a775  mov     r14, [rsp+6F0h+var_688]
0x18008a77a  xor     r12d, r12d
0x18008a77d  mov     esi, [rsp+6F0h+var_690]
0x18008a781  mov     rax, [r14]
0x18008a784  mov     [rbx+10h], rax
0x18008a788  mov     [r14], rbx
0x18008a78b  jmp     loc_18008A5E7
0x18008a790  mov     rcx, [rbx+8]
0x18008a794  mov     [rax+8], rcx
0x18008a798  mov     [rbx+8], rax
0x18008a79c  jmp     short loc_18008A770
0x18008a79e  lea     rcx, [rbp+5F0h+Buffer]; lpBuffer
0x18008a7a5  call    ?MakePathName@@YAHPEAGPEBG@Z; MakePathName(ushort *,ushort const *)
0x18008a7aa  xor     r9d, r9d
0x18008a7ad  test    eax, eax
0x18008a7af  jz      loc_18008A6DD
0x18008a7b5  lea     rdx, [rbp+5F0h+Buffer]
0x18008a7bc  mov     r8d, r9d
0x18008a7bf  movzx   ecx, word ptr [rdx]
0x18008a7c2  test    cx, cx
0x18008a7c5  jz      loc_18008A897
0x18008a7cb  lea     eax, [rcx-61h]
0x18008a7ce  cmp     ax, 19h
0x18008a7d2  jbe     short loc_18008A806
0x18008a7d4  mov     [rdx], cx
0x18008a7d7  inc     r8d
0x18008a7da  add     rdx, 2
0x18008a7de  cmp     r8d, 104h
0x18008a7e5  jb      short loc_18008A7BF
0x18008a7e7  mov     rcx, cs:?FontCollection@Globals@@3PEAVGpInstalledFontCollection@@EA; GpInstalledFontCollection * Globals::FontCollection
0x18008a7ee  lea     rdx, [rbp+5F0h+Buffer]; unsigned __int16 *
0x18008a7f5  mov     rcx, [rcx+10h]; this
0x18008a7f9  call    ?GetFirstFontFamilyFromFile@GpFontTable@@QEBAPEAVGpFontFamily@@PEBG@Z; GpFontTable::GetFirstFontFamilyFromFile(ushort const *)
0x18008a7fe  xor     r9d, r9d
0x18008a801  jmp     loc_18008A6DD
0x18008a806  sub     cx, 20h ; ' '
0x18008a80a  jmp     short loc_18008A7D4
0x18008a80c  mov     rcx, rbx
0x18008a80f  call    GpFree
0x18008a814  jmp     loc_18008A5E7
0x18008a819  mov     rcx, rdi
0x18008a81c  call    GpFree
0x18008a821  mov     rcx, [rsp+6F0h+var_698]
0x18008a826  call    DLRegCloseKey
0x18008a82b  mov     rcx, [rbp+5F0h+var_50]
0x18008a832  xor     rcx, rsp; StackCookie
0x18008a835  call    __security_check_cookie
0x18008a83a  add     rsp, 6B8h
0x18008a841  pop     r15
0x18008a843  pop     r14
0x18008a845  pop     r13
0x18008a847  pop     r12
0x18008a849  pop     rdi
0x18008a84a  pop     rsi
0x18008a84b  pop     rbx
0x18008a84c  pop     rbp
0x18008a84d  retn
0x18008a84f  call    ?DLpLoadRegistryDll@@YAKXZ; DLpLoadRegistryDll(void)
0x18008a854  test    eax, eax
0x18008a856  jnz     loc_18008A638
0x18008a85c  mov     rcx, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18008a863  lea     rdx, aRegenumvaluew; "RegEnumValueW"
0x18008a86a  call    cs:__imp_GetProcAddress
0x18008a871  nop     dword ptr [rax+rax+00h]
0x18008a876  mov     cs:qword_1801AE7D8, rax
0x18008a87d  test    rax, rax
0x18008a880  jnz     loc_18008A609
0x18008a886  call    cs:__imp_GetLastError
0x18008a88d  nop     dword ptr [rax+rax+00h]
0x18008a892  jmp     loc_18008A638
0x18008a897  mov     [rdx], r9w
0x18008a89b  jmp     loc_18008A7E7
0x18008a8a0  lea     rcx, [rsp+6F0h+var_698]
0x18008a8a5  mov     r9d, 9
0x18008a8ab  mov     [rsp+6F0h+var_6D0], rcx
0x18008a8b0  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18008a8b7  mov     rcx, 0FFFFFFFF80000002h
0x18008a8be  xor     r8d, r8d
0x18008a8c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a8c6  jmp     loc_18008A5BF
0x18008a8cb  mov     rcx, rdi
0x18008a8ce  mov     [rsp+6F0h+var_69C], 104h
0x18008a8d6  add     r15d, r15d
0x18008a8d9  call    GpFree
0x18008a8de  mov     ecx, r15d
0x18008a8e1  xor     edx, edx
0x18008a8e3  call    GpMallocEx
0x18008a8e8  mov     rdi, rax
0x18008a8eb  test    rax, rax
0x18008a8ee  jz      loc_18008A821
0x18008a8f4  mov     rcx, [rsp+6F0h+var_698]
0x18008a8f9  lea     rax, [rsp+6F0h+var_6A0]
0x18008a8fe  mov     [rsp+6F0h+var_6B8], rax
0x18008a903  lea     r9, [rsp+6F0h+var_69C]
0x18008a908  lea     r8, [rbp+5F0h+var_470]
0x18008a90f  mov     [rsp+6F0h+var_6C0], rdi
0x18008a914  mov     edx, esi
0x18008a916  mov     [rsp+6F0h+var_6A0], r15d
0x18008a91b  call    DLRegEnumValueW
0x18008a920  jmp     loc_18008A643
0x18008a925  call    __report_rangecheckfailure
```
