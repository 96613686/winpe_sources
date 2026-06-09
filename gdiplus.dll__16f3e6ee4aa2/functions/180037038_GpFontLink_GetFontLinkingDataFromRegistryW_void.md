# GpFontLink::GetFontLinkingDataFromRegistryW(void)

- ea: `0x180037038`
- end: `0x180037416`
- name: `?GetFontLinkingDataFromRegistryW@GpFontLink@@AEAAXXZ`
- size: `990`
- prototype: `void __fastcall(GpFontLink *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800ed284`

## callees

- `0x1800067bc`
- `0x18001ec80`
- `0x180032bac`
- `0x180032c50`
- `0x180032d40`
- `0x18003542c`
- `0x180035b24`
- `0x180037038`
- `0x180037420`
- `0x1800fe680`
- `0x1800fea70`
- `0x180169010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800370a7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180037361`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800370a7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180037361`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180037162`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003724a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180037162`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003724a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800370bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037377`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800370bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037377`

## string_xrefs

- `0x18003739b`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\FontLink\SystemLink`
- `0x1800370a0`: `RegOpenKeyExW`

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

  ProcAddress = (FARPROC)qword_1801A56C8;
  v2 = 0;
  v29 = this;
  v27 = 0;
  v26 = 0;
  v25 = 0;
  if ( qword_1801A56C8 )
    goto LABEL_46;
  if ( (unsigned int)DLpLoadRegistryDll() )
    return;
  ProcAddress = GetProcAddress(g_hInstRegistryDLL, "RegOpenKeyExW");
  qword_1801A56C8 = (__int64)ProcAddress;
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
      v7 = (FARPROC)qword_1801A56E0;
      v8 = v27;
      v26 = 260;
      v25 = v5;
      if ( qword_1801A56E0 )
        break;
      RegistryDll = DLpLoadRegistryDll();
      if ( !RegistryDll )
      {
        v7 = GetProcAddress(g_hInstRegistryDLL, "RegEnumValueW");
        qword_1801A56E0 = (__int64)v7;
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
0x180037038  push    rbp
0x18003703a  push    rbx
0x18003703b  push    rsi
0x18003703c  push    rdi
0x18003703d  push    r12
0x18003703f  push    r13
0x180037041  push    r14
0x180037043  push    r15
0x180037045  lea     rbp, [rsp-5B8h]
0x18003704d  sub     rsp, 6B8h
0x180037054  mov     rax, cs:__security_cookie
0x18003705b  xor     rax, rsp
0x18003705e  mov     [rbp+5F0h+var_50], rax
0x180037065  mov     rax, cs:qword_1801A56C8
0x18003706c  xor     r12d, r12d
0x18003706f  mov     [rsp+6F0h+var_688], rcx
0x180037074  mov     [rsp+6F0h+var_698], r12
0x180037079  mov     [rsp+6F0h+var_69C], r12d
0x18003707e  mov     [rsp+6F0h+var_6A0], r12d
0x180037083  test    rax, rax
0x180037086  jnz     loc_18003738B
0x18003708c  call    ?DLpLoadRegistryDll@@YAKXZ; DLpLoadRegistryDll(void)
0x180037091  test    eax, eax
0x180037093  jnz     loc_180037323
0x180037099  mov     rcx, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; hModule
0x1800370a0  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x1800370a7  call    cs:__imp_GetProcAddress
0x1800370ad  mov     cs:qword_1801A56C8, rax
0x1800370b4  test    rax, rax
0x1800370b7  jnz     loc_18003738B
0x1800370bd  call    cs:__imp_GetLastError
0x1800370c3  test    eax, eax
0x1800370c5  jnz     loc_180037323
0x1800370cb  mov     eax, 208h
0x1800370d0  xor     edx, edx
0x1800370d2  mov     ecx, eax
0x1800370d4  mov     esi, r12d
0x1800370d7  mov     r15d, eax
0x1800370da  call    GpMallocEx
0x1800370df  mov     rdi, rax
0x1800370e2  test    rax, rax
0x1800370e5  jz      loc_180037319
0x1800370eb  mov     rax, cs:qword_1801A56E0
0x1800370f2  mov     rbx, [rsp+6F0h+var_698]
0x1800370f7  mov     [rsp+6F0h+var_69C], 104h
0x1800370ff  mov     [rsp+6F0h+var_6A0], r15d
0x180037104  test    rax, rax
0x180037107  jz      loc_180037346
0x18003710d  lea     rcx, [rsp+6F0h+var_6A0]
0x180037112  mov     edx, esi
0x180037114  mov     [rsp+6F0h+var_6B8], rcx
0x180037119  lea     r9, [rsp+6F0h+var_69C]
0x18003711e  mov     [rsp+6F0h+var_6C0], rdi
0x180037123  lea     r8, [rbp+5F0h+var_470]
0x18003712a  mov     [rsp+6F0h+var_6C8], r12
0x18003712f  mov     rcx, rbx
0x180037132  mov     [rsp+6F0h+var_6D0], r12
0x180037137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003713c  cmp     eax, 0EAh
0x180037141  jz      loc_1800373B6
0x180037147  test    eax, eax
0x180037149  jnz     loc_180037311
0x18003714f  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x180037156  lea     r8d, [rax+18h]; dwBytes
0x18003715a  inc     esi
0x18003715c  xor     edx, edx; dwFlags
0x18003715e  mov     [rsp+6F0h+var_690], esi
0x180037162  call    cs:__imp_HeapAlloc
0x180037168  mov     rbx, rax
0x18003716b  test    rax, rax
0x18003716e  jz      loc_1800370EB
0x180037174  mov     rcx, cs:?FontCollection@Globals@@3PEAVGpInstalledFontCollection@@EA; GpInstalledFontCollection * Globals::FontCollection
0x18003717b  lea     rdx, [rbp+5F0h+var_470]; unsigned __int16 *
0x180037182  mov     rcx, [rcx+10h]
0x180037186  mov     rcx, [rcx+8]; this
0x18003718a  call    ?GetFamily@GpFontFamilyList@@QEBAPEAVGpFontFamily@@PEBG@Z; GpFontFamilyList::GetFamily(ushort const *)
0x18003718f  mov     [rbx], rax
0x180037192  test    rax, rax
0x180037195  jz      loc_180037304
0x18003719b  xor     r9d, r9d
0x18003719e  mov     [rbx+8], r12
0x1800371a2  mov     [rbx+10h], r12
0x1800371a6  mov     esi, r9d
0x1800371a9  shr     [rsp+6F0h+var_6A0], 1
0x1800371ad  mov     r13, r12
0x1800371b0  mov     r14d, r12d
0x1800371b3  cmp     r12d, [rsp+6F0h+var_6A0]
0x1800371b8  jnb     loc_18003726D
0x1800371be  mov     eax, r12d
0x1800371c1  movzx   ecx, word ptr [rdi+rax*2]
0x1800371c5  cmp     cx, 2Ch ; ','
0x1800371c9  jz      short loc_180037233
0x1800371cb  test    cx, cx
0x1800371ce  jz      short loc_1800371E0
0x1800371d0  mov     eax, r14d
0x1800371d3  inc     r14d
0x1800371d6  mov     [rsp+rax*2+6F0h+FileName], cx
0x1800371db  inc     r12d
0x1800371de  jmp     short loc_1800371B3
0x1800371e0  test    r14d, r14d
0x1800371e3  jz      short loc_1800371DB
0x1800371e5  mov     eax, r14d
0x1800371e8  lea     rcx, [rax+rax]
0x1800371ec  cmp     rcx, 208h
0x1800371f3  jnb     loc_180037410
0x1800371f9  mov     [rsp+rcx+6F0h+FileName], r9w
0x1800371ff  mov     r14d, r9d
0x180037202  lea     rdx, [rsp+6F0h+FileName]; lpFileName
0x180037207  test    esi, esi
0x180037209  jz      loc_180037296
0x18003720f  mov     rax, cs:?FontCollection@Globals@@3PEAVGpInstalledFontCollection@@EA; GpInstalledFontCollection * Globals::FontCollection
0x180037216  mov     rcx, [rax+10h]
0x18003721a  mov     rcx, [rcx+8]; this
0x18003721e  call    ?GetFamily@GpFontFamilyList@@QEBAPEAVGpFontFamily@@PEBG@Z; GpFontFamilyList::GetFamily(ushort const *)
0x180037223  xor     r9d, r9d
0x180037226  mov     rsi, rax
0x180037229  test    rax, rax
0x18003722c  jnz     short loc_18003723D
0x18003722e  mov     esi, r9d
0x180037231  jmp     short loc_1800371DB
0x180037233  mov     r14d, r9d
0x180037236  mov     esi, 1
0x18003723b  jmp     short loc_1800371DB
0x18003723d  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x180037244  xor     edx, edx; dwFlags
0x180037246  lea     r8d, [rdx+10h]; dwBytes
0x18003724a  call    cs:__imp_HeapAlloc
0x180037250  xor     r9d, r9d
0x180037253  test    rax, rax
0x180037256  jz      short loc_18003722E
0x180037258  mov     [rax], rsi
0x18003725b  test    r13, r13
0x18003725e  jz      short loc_180037288
0x180037260  mov     [rax+8], r9
0x180037264  mov     [r13+8], rax
0x180037268  mov     r13, rax
0x18003726b  jmp     short loc_18003722E
0x18003726d  mov     r14, [rsp+6F0h+var_688]
0x180037272  xor     r12d, r12d
0x180037275  mov     esi, [rsp+6F0h+var_690]
0x180037279  mov     rax, [r14]
0x18003727c  mov     [rbx+10h], rax
0x180037280  mov     [r14], rbx
0x180037283  jmp     loc_1800370EB
0x180037288  mov     rcx, [rbx+8]
0x18003728c  mov     [rax+8], rcx
0x180037290  mov     [rbx+8], rax
0x180037294  jmp     short loc_180037268
0x180037296  lea     rcx, [rbp+5F0h+Buffer]; lpBuffer
0x18003729d  call    ?MakePathName@@YAHPEAGPEBG@Z; MakePathName(ushort *,ushort const *)
0x1800372a2  xor     r9d, r9d
0x1800372a5  test    eax, eax
0x1800372a7  jz      loc_1800371DB
0x1800372ad  lea     rdx, [rbp+5F0h+Buffer]
0x1800372b4  mov     r8d, r9d
0x1800372b7  movzx   ecx, word ptr [rdx]
0x1800372ba  test    cx, cx
0x1800372bd  jz      loc_180037382
0x1800372c3  lea     eax, [rcx-61h]
0x1800372c6  cmp     ax, 19h
0x1800372ca  jbe     short loc_1800372FE
0x1800372cc  mov     [rdx], cx
0x1800372cf  inc     r8d
0x1800372d2  add     rdx, 2
0x1800372d6  cmp     r8d, 104h
0x1800372dd  jb      short loc_1800372B7
0x1800372df  mov     rcx, cs:?FontCollection@Globals@@3PEAVGpInstalledFontCollection@@EA; GpInstalledFontCollection * Globals::FontCollection
0x1800372e6  lea     rdx, [rbp+5F0h+Buffer]; unsigned __int16 *
0x1800372ed  mov     rcx, [rcx+10h]; this
0x1800372f1  call    ?GetFirstFontFamilyFromFile@GpFontTable@@QEBAPEAVGpFontFamily@@PEBG@Z; GpFontTable::GetFirstFontFamilyFromFile(ushort const *)
0x1800372f6  xor     r9d, r9d
0x1800372f9  jmp     loc_1800371DB
0x1800372fe  sub     cx, 20h ; ' '
0x180037302  jmp     short loc_1800372CC
0x180037304  mov     rcx, rbx
0x180037307  call    GpFree
0x18003730c  jmp     loc_1800370EB
0x180037311  mov     rcx, rdi
0x180037314  call    GpFree
0x180037319  mov     rcx, [rsp+6F0h+var_698]
0x18003731e  call    DLRegCloseKey
0x180037323  mov     rcx, [rbp+5F0h+var_50]
0x18003732a  xor     rcx, rsp; StackCookie
0x18003732d  call    __security_check_cookie
0x180037332  add     rsp, 6B8h
0x180037339  pop     r15
0x18003733b  pop     r14
0x18003733d  pop     r13
0x18003733f  pop     r12
0x180037341  pop     rdi
0x180037342  pop     rsi
0x180037343  pop     rbx
0x180037344  pop     rbp
0x180037345  retn
0x180037346  call    ?DLpLoadRegistryDll@@YAKXZ; DLpLoadRegistryDll(void)
0x18003734b  test    eax, eax
0x18003734d  jnz     loc_18003713C
0x180037353  mov     rcx, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18003735a  lea     rdx, aRegenumvaluew; "RegEnumValueW"
0x180037361  call    cs:__imp_GetProcAddress
0x180037367  mov     cs:qword_1801A56E0, rax
0x18003736e  test    rax, rax
0x180037371  jnz     loc_18003710D
0x180037377  call    cs:__imp_GetLastError
0x18003737d  jmp     loc_18003713C
0x180037382  mov     [rdx], r9w
0x180037386  jmp     loc_1800372DF
0x18003738b  lea     rcx, [rsp+6F0h+var_698]
0x180037390  mov     r9d, 9
0x180037396  mov     [rsp+6F0h+var_6D0], rcx
0x18003739b  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800373a2  mov     rcx, 0FFFFFFFF80000002h
0x1800373a9  xor     r8d, r8d
0x1800373ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800373b1  jmp     loc_1800370C3
0x1800373b6  mov     rcx, rdi
0x1800373b9  mov     [rsp+6F0h+var_69C], 104h
0x1800373c1  add     r15d, r15d
0x1800373c4  call    GpFree
0x1800373c9  mov     ecx, r15d
0x1800373cc  xor     edx, edx
0x1800373ce  call    GpMallocEx
0x1800373d3  mov     rdi, rax
0x1800373d6  test    rax, rax
0x1800373d9  jz      loc_180037319
0x1800373df  mov     rcx, [rsp+6F0h+var_698]
0x1800373e4  lea     rax, [rsp+6F0h+var_6A0]
0x1800373e9  mov     [rsp+6F0h+var_6B8], rax
0x1800373ee  lea     r9, [rsp+6F0h+var_69C]
0x1800373f3  lea     r8, [rbp+5F0h+var_470]
0x1800373fa  mov     [rsp+6F0h+var_6C0], rdi
0x1800373ff  mov     edx, esi
0x180037401  mov     [rsp+6F0h+var_6A0], r15d
0x180037406  call    DLRegEnumValueW
0x18003740b  jmp     loc_180037147
0x180037410  call    __report_rangecheckfailure
```
