# CDXGIFactory::Initialize(uint)

- ea: `0x18004f008`
- end: `0x18004f31a`
- name: `?Initialize@CDXGIFactory@@QEAAJI@Z`
- size: `786`
- prototype: `__int64 __fastcall(CDXGIFactory *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004eb18`

## callees

- `0x18001c7a4`
- `0x1800301dc`
- `0x18003ee38`
- `0x18004ef4c`
- `0x18004f008`
- `0x180056428`
- `0x18006651c`
- `0x18006d108`
- `0x180096470`
- `0x1800a732c`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f2dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f2dd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004f2ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004f2ae`

## pseudocode

```c
__int64 __fastcall CDXGIFactory::Initialize(CDXGIFactory *this, int a2)
{
  bool v3; // al
  __int64 v4; // r10
  signed int v5; // r14d
  unsigned int v6; // edi
  int v7; // ecx
  unsigned __int32 v8; // esi
  __m128i v9; // xmm6
  __m128i *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  bool v13; // al
  char *v14; // rdx
  const char *v15; // r8
  const char *v16; // r9
  bool v17; // al
  __int64 result; // rax
  bool phkResult; // [rsp+20h] [rbp-60h]
  void (*v20)(bool, unsigned int, void *); // [rsp+28h] [rbp-58h]
  __int128 v21; // [rsp+50h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+B0h] [rbp+30h] BYREF

  v3 = NtCurrentPeb()->SessionId && NtCurrentPeb()->SessionId != MEMORY[0x7FFE02D8];
  *((_BYTE *)this + 745) = v3;
  *((_DWORD *)this + 103) = a2;
  *((_BYTE *)this + 744) = (a2 & 0x40000000) == 0;
  if ( (a2 & 1) != 0 )
  {
    CheckDxgiDebugDll();
    v4 = *(_QWORD *)g_pDebugPrivate;
    v21 = (__int128)DXGI_DEBUG_DXGI;
    (*(void (__fastcall **)(struct IDXGIDebugPrivate *, __int128 *, unsigned __int64, char *))(v4 + 32))(
      g_pDebugPrivate,
      &v21,
      ((unsigned __int64)this + 224) & -(__int64)(this != 0),
      (char *)this + 392);
  }
  hKey = 0;
  if ( (unsigned int)CompatValueImpl("Hybrid", (unsigned __int64 *)&hKey, 0) )
    *((_DWORD *)this + 105) = (_DWORD)hKey;
  hKey = 0;
  if ( (unsigned int)CompatValueImpl("NoUserSettingCaching", (unsigned __int64 *)&hKey, 0) && hKey )
    *((_BYTE *)this + 428) = 1;
  v5 = CDXGIFactory::SampleAdapters(this);
  if ( v5 >= 0 )
  {
    *((_BYTE *)this + 760) = 1;
    if ( (Microsoft_Windows_DXGIEnableBits & 1) != 0 )
      McTemplateU0pqqZRZRx_EtwEventWriteTransfer(
        qword_180109C48,
        (unsigned int)EventCreateFactory,
        (_DWORD)this,
        *((_BYTE *)this + 744) != 0);
  }
  v21 = 0;
  if ( byte_180109D48 )
  {
    v6 = xmmword_180109D4C;
    v7 = DWORD1(xmmword_180109D4C);
    v8 = DWORD2(xmmword_180109D4C);
    v21 = xmmword_180109D4C;
    v9 = (__m128i)xmmword_180109D4C;
  }
  else
  {
    v10 = (__m128i *)CDXGIFactory::EvaluateDynamicSwitch((__int64)this, (__int64)&v21);
    v9 = *v10;
    v8 = v10->m128i_u32[2];
    v6 = _mm_cvtsi128_si32(*v10);
    if ( (Microsoft_Windows_DXGIEnableBits & 2) != 0 )
      McTemplateU0tq_EtwEventWriteTransfer(v12, v11, v6, v8);
    word_180109D49 = *(_WORD *)((char *)&v21 + 1);
    byte_180109D4B = BYTE3(v21);
    DWORD1(xmmword_180109D4C) = v9.m128i_i32[1];
    v7 = _mm_cvtsi128_si32(_mm_srli_si128(v9, 4));
    byte_180109D48 = 1;
    LODWORD(xmmword_180109D4C) = v6;
    DWORD2(xmmword_180109D4C) = v8;
    HIDWORD(xmmword_180109D4C) = _mm_srli_si128(v9, 8).m128i_i32[1];
  }
  v13 = v6 || v7;
  if ( ((v8 - 5) & 0xFFFFFFFD) != 0 && v13 && !_InterlockedCompareExchange8(&byte_180109DF8, 1, 0) )
  {
    v21 = (__int128)v9;
    CDXGIFactory::ApplyDynamicSwitchPreference(this, &v21);
  }
  *((_BYTE *)this + 436) = *((_BYTE *)xmmword_180109A10 + 160);
  *((_BYTE *)this + 437) = 0;
  if ( (_DWORD)qword_180109A08 )
  {
    hKey = 0;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\AppOnHMD",
            0,
            0x20019u,
            &hKey)
      && hKey )
    {
      v17 = RegDWORDPresentAndNonZero(hKey, v14);
      *((_BYTE *)this + 436) = v17;
      *((_BYTE *)xmmword_180109A10 + 160) = v17;
      RegCloseKey(hKey);
    }
    CRegistryWatcher::SetDWORDWatch((CDXGIFactory *)((char *)this + 440), (HKEY)v14, v15, v16, phkResult, v20, this);
  }
  result = (unsigned int)v5;
  *((_BYTE *)this + 438) = 1;
  return result;
}

```

## disassembly

```asm
0x18004f008  mov     [rsp-28h+arg_10], rbx
0x18004f00d  push    rbp
0x18004f00e  push    rsi
0x18004f00f  push    rdi
0x18004f010  push    r12
0x18004f012  push    r14
0x18004f014  mov     rbp, rsp
0x18004f017  sub     rsp, 80h
0x18004f01e  mov     rax, gs:60h
0x18004f027  mov     rbx, rcx
0x18004f02a  movaps  [rsp+80h+var_10], xmm6
0x18004f02f  mov     r12d, 1
0x18004f035  cmp     dword ptr [rax+2C0h], 0
0x18004f03c  jz      short loc_18004F05F
0x18004f03e  mov     rax, gs:60h
0x18004f047  mov     r8d, [rax+2C0h]
0x18004f04e  mov     eax, ds:7FFE02D8h
0x18004f055  cmp     r8d, eax
0x18004f058  jz      short loc_18004F05F
0x18004f05a  mov     al, r12b
0x18004f05d  jmp     short loc_18004F061
0x18004f05f  xor     al, al
0x18004f061  mov     [rcx+2E9h], al
0x18004f067  mov     eax, edx
0x18004f069  shr     eax, 1Eh
0x18004f06c  not     al
0x18004f06e  mov     [rcx+19Ch], edx
0x18004f074  and     al, r12b
0x18004f077  mov     [rcx+2E8h], al
0x18004f07d  test    r12b, dl
0x18004f080  jz      short loc_18004F0C4
0x18004f082  call    ?CheckDxgiDebugDll@@YAXXZ; CheckDxgiDebugDll(void)
0x18004f087  mov     rcx, cs:?g_pDebugPrivate@@3PEAUIDXGIDebugPrivate@@EA; IDXGIDebugPrivate * g_pDebugPrivate
0x18004f08e  lea     rdx, [rbx+0E0h]
0x18004f095  movups  xmm0, xmmword ptr cs:DXGI_DEBUG_DXGI.Data1
0x18004f09c  mov     rax, rbx
0x18004f09f  lea     r9, [rbx+188h]
0x18004f0a6  neg     rax
0x18004f0a9  mov     r10, [rcx]
0x18004f0ac  sbb     r8, r8
0x18004f0af  and     r8, rdx
0x18004f0b2  lea     rdx, [rbp+var_30]
0x18004f0b6  movdqu  [rbp+var_30], xmm0
0x18004f0bb  mov     rax, [r10+20h]
0x18004f0bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f0c4  xor     r8d, r8d; bool
0x18004f0c7  mov     [rbp+hKey], 0
0x18004f0cf  lea     rdx, [rbp+hKey]; unsigned __int64 *
0x18004f0d3  lea     rcx, aHybrid; "Hybrid"
0x18004f0da  call    ?CompatValueImpl@@YAHPEBDPEA_K_N@Z; CompatValueImpl(char const *,unsigned __int64 *,bool)
0x18004f0df  test    eax, eax
0x18004f0e1  jz      short loc_18004F0EC
0x18004f0e3  mov     eax, dword ptr [rbp+hKey]
0x18004f0e6  mov     [rbx+1A4h], eax
0x18004f0ec  xor     r8d, r8d; bool
0x18004f0ef  mov     [rbp+hKey], 0
0x18004f0f7  lea     rdx, [rbp+hKey]; unsigned __int64 *
0x18004f0fb  lea     rcx, aNousersettingc; "NoUserSettingCaching"
0x18004f102  call    ?CompatValueImpl@@YAHPEBDPEA_K_N@Z; CompatValueImpl(char const *,unsigned __int64 *,bool)
0x18004f107  test    eax, eax
0x18004f109  jz      short loc_18004F119
0x18004f10b  cmp     [rbp+hKey], 0
0x18004f110  jz      short loc_18004F119
0x18004f112  mov     [rbx+1ACh], r12b
0x18004f119  mov     rcx, rbx; this
0x18004f11c  call    ?SampleAdapters@CDXGIFactory@@QEAAJXZ; CDXGIFactory::SampleAdapters(void)
0x18004f121  mov     r14d, eax
0x18004f124  test    eax, eax
0x18004f126  js      short loc_18004F161
0x18004f128  mov     [rbx+2F8h], r12b
0x18004f12f  test    byte ptr cs:Microsoft_Windows_DXGIEnableBits, r12b
0x18004f136  jz      short loc_18004F161
0x18004f138  mov     rcx, cs:qword_180109C48
0x18004f13f  lea     rdx, EventCreateFactory
0x18004f146  xor     r9d, r9d
0x18004f149  mov     [rsp+80h+var_38], rcx
0x18004f14e  cmp     [rbx+2E8h], r9b
0x18004f155  mov     r8, rbx
0x18004f158  setnz   r9b
0x18004f15c  call    McTemplateU0pqqZRZRx_EtwEventWriteTransfer
0x18004f161  cmp     cs:byte_180109D48, 0
0x18004f168  xorps   xmm0, xmm0
0x18004f16b  movups  [rbp+var_30], xmm0
0x18004f16f  jz      short loc_18004F19E
0x18004f171  mov     edi, dword ptr cs:xmmword_180109D4C
0x18004f177  mov     ecx, dword ptr cs:xmmword_180109D4C+4
0x18004f17d  mov     esi, dword ptr cs:xmmword_180109D4C+8
0x18004f183  mov     eax, dword ptr cs:xmmword_180109D4C+0Ch
0x18004f189  mov     dword ptr [rbp+var_30], edi
0x18004f18c  mov     dword ptr [rbp+var_30+4], ecx
0x18004f18f  mov     dword ptr [rbp+var_30+8], esi
0x18004f192  mov     dword ptr [rbp+var_30+0Ch], eax
0x18004f195  movaps  xmm6, [rbp+var_30]
0x18004f199  jmp     loc_18004F223
0x18004f19e  lea     rdx, [rbp+var_30]
0x18004f1a2  mov     rcx, rbx
0x18004f1a5  call    ?EvaluateDynamicSwitch@CDXGIFactory@@AEAA?AU_DYNAMIC_SWITCH_DECISION@@XZ; CDXGIFactory::EvaluateDynamicSwitch(void)
0x18004f1aa  test    byte ptr cs:Microsoft_Windows_DXGIEnableBits, 2
0x18004f1b1  movups  xmm6, xmmword ptr [rax]
0x18004f1b4  mov     esi, [rax+8]
0x18004f1b7  movd    edi, xmm6
0x18004f1bb  jz      short loc_18004F1C8
0x18004f1bd  mov     r9d, esi
0x18004f1c0  mov     r8d, edi
0x18004f1c3  call    McTemplateU0tq_EtwEventWriteTransfer
0x18004f1c8  movzx   eax, word ptr [rbp+var_30+1]
0x18004f1cc  movdqa  xmm0, xmm6
0x18004f1d0  mov     cs:word_180109D49, ax
0x18004f1d7  mov     al, byte ptr [rbp+var_30+3]
0x18004f1da  mov     cs:byte_180109D4B, al
0x18004f1e0  movq    rax, xmm6
0x18004f1e5  shr     rax, 20h
0x18004f1e9  psrldq  xmm0, 8
0x18004f1ee  mov     dword ptr cs:xmmword_180109D4C+4, eax
0x18004f1f4  movq    rax, xmm0
0x18004f1f9  movdqa  xmm0, xmm6
0x18004f1fd  shr     rax, 20h
0x18004f201  psrldq  xmm0, 4
0x18004f206  movd    ecx, xmm0
0x18004f20a  mov     cs:byte_180109D48, r12b
0x18004f211  mov     dword ptr cs:xmmword_180109D4C, edi
0x18004f217  mov     dword ptr cs:xmmword_180109D4C+8, esi
0x18004f21d  mov     dword ptr cs:xmmword_180109D4C+0Ch, eax
0x18004f223  lea     eax, [rsi-5]
0x18004f226  test    eax, 0FFFFFFFDh
0x18004f22b  setnz   dl
0x18004f22e  test    edi, edi
0x18004f230  jnz     short loc_18004F23A
0x18004f232  test    ecx, ecx
0x18004f234  jnz     short loc_18004F23A
0x18004f236  xor     al, al
0x18004f238  jmp     short loc_18004F23D
0x18004f23a  mov     al, r12b
0x18004f23d  test    dl, dl
0x18004f23f  jz      short loc_18004F263
0x18004f241  test    al, al
0x18004f243  jz      short loc_18004F263
0x18004f245  xor     eax, eax
0x18004f247  lock cmpxchg cs:byte_180109DF8, r12b
0x18004f250  jnz     short loc_18004F263
0x18004f252  lea     rdx, [rbp+var_30]
0x18004f256  movdqa  [rbp+var_30], xmm6
0x18004f25b  mov     rcx, rbx
0x18004f25e  call    ?ApplyDynamicSwitchPreference@CDXGIFactory@@AEAAXU_DYNAMIC_SWITCH_DECISION@@@Z; CDXGIFactory::ApplyDynamicSwitchPreference(_DYNAMIC_SWITCH_DECISION)
0x18004f263  mov     rax, qword ptr cs:xmmword_180109A10
0x18004f26a  mov     cl, [rax+0A0h]
0x18004f270  mov     [rbx+1B4h], cl
0x18004f276  mov     byte ptr [rbx+1B5h], 0
0x18004f27d  cmp     dword ptr cs:qword_180109A08, 0
0x18004f284  jz      short loc_18004F2F4
0x18004f286  lea     rax, [rbp+hKey]
0x18004f28a  mov     [rbp+hKey], 0
0x18004f292  mov     r9d, 20019h; samDesired
0x18004f298  mov     [rsp+80h+phkResult], rax; bool
0x18004f29d  xor     r8d, r8d; ulOptions
0x18004f2a0  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18004f2a7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004f2ae  call    cs:__imp_RegOpenKeyExW
0x18004f2b4  test    eax, eax
0x18004f2b6  jnz     short loc_18004F2E3
0x18004f2b8  mov     rcx, [rbp+hKey]; HKEY
0x18004f2bc  test    rcx, rcx
0x18004f2bf  jz      short loc_18004F2E3
0x18004f2c1  call    ?RegDWORDPresentAndNonZero@@YA_NPEAUHKEY__@@PEBD@Z; RegDWORDPresentAndNonZero(HKEY__ *,char const *)
0x18004f2c6  mov     [rbx+1B4h], al
0x18004f2cc  mov     rcx, qword ptr cs:xmmword_180109A10
0x18004f2d3  mov     [rcx+0A0h], al
0x18004f2d9  mov     rcx, [rbp+hKey]; hKey
0x18004f2dd  call    cs:__imp_RegCloseKey
0x18004f2e3  lea     rcx, [rbx+1B8h]; this
0x18004f2ea  mov     [rsp+80h+var_50], rbx; void *
0x18004f2ef  call    ?SetDWORDWatch@CRegistryWatcher@@QEAAJPEAUHKEY__@@PEBD1_NP6AX2KPEAX@Z3@Z; CRegistryWatcher::SetDWORDWatch(HKEY__ *,char const *,char const *,bool,void (*)(bool,ulong,void *),void *)
0x18004f2f4  movaps  xmm6, [rsp+80h+var_10]
0x18004f2f9  mov     eax, r14d
0x18004f2fc  mov     [rbx+1B6h], r12b
0x18004f303  mov     rbx, [rsp+80h+arg_10]
0x18004f30b  add     rsp, 80h
0x18004f312  pop     r14
0x18004f314  pop     r12
0x18004f316  pop     rdi
0x18004f317  pop     rsi
0x18004f318  pop     rbp
0x18004f319  retn
```
