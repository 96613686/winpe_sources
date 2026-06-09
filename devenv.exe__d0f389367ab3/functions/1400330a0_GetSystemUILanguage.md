# GetSystemUILanguage

- ea: `0x1400330a0`
- end: `0x14003327c`
- name: `GetSystemUILanguage`
- size: `476`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140032bb0`

## callees

- `0x140001020`
- `0x140002c10`
- `0x140002dd0`
- `0x140032d80`
- `0x140032de0`
- `0x1400330a0`
- `0x140033280`
- `0x140033ab0`

## import_xrefs

- `KERNEL32!GetSystemDefaultUILanguage` at `0x1400330c5`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x1400330c5`
- `KERNEL32!GetSystemPreferredUILanguages` at `0x1400330ea`
- `KERNEL32!GetSystemPreferredUILanguages` at `0x140033173`
- `KERNEL32!GetSystemPreferredUILanguages` at `0x1400330ea`
- `KERNEL32!GetSystemPreferredUILanguages` at `0x140033173`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 GetSystemUILanguage()
{
  LANGID SystemDefaultUILanguage; // bx
  struct ATL::IAtlStringMgr *Instance; // rax
  __int64 v2; // rax
  WCHAR *v3; // r8
  const wchar_t *const *v4; // rax
  int v5; // edi
  _QWORD *v6; // rdx
  PZZWSTR v7; // rax
  int v8; // ecx
  PZZWSTR v9; // rdx
  _QWORD v11[2]; // [rsp+20h] [rbp-40h] BYREF
  WCHAR *v12; // [rsp+30h] [rbp-30h]
  __int64 v13; // [rsp+38h] [rbp-28h]
  ULONG pcchLanguagesBuffer; // [rsp+40h] [rbp-20h] BYREF
  LANGID v15; // [rsp+44h] [rbp-1Ch] BYREF
  PZZWSTR pwszLanguagesBuffer; // [rsp+48h] [rbp-18h] BYREF
  ULONG pulNumLanguages; // [rsp+50h] [rbp-10h] BYREF

  SystemDefaultUILanguage = GetSystemDefaultUILanguage();
  v15 = SystemDefaultUILanguage;
  pulNumLanguages = 0;
  pcchLanguagesBuffer = 0;
  if ( !GetSystemPreferredUILanguages(4u, &pulNumLanguages, 0, &pcchLanguagesBuffer) )
    return v15;
  pwszLanguagesBuffer = 0;
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  v2 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance);
  v3 = (WCHAR *)(v2 + 24);
  pwszLanguagesBuffer = (PZZWSTR)(v2 + 24);
  v11[1] = &pwszLanguagesBuffer;
  v12 = 0;
  v13 = 0xFFFFFFFFLL;
  if ( (pcchLanguagesBuffer & 0x80000000) != 0 )
    ATL::AtlThrowImpl(-2147024809);
  if ( (((1 - *(_DWORD *)(v2 + 16)) | (*(_DWORD *)(v2 + 12) - pcchLanguagesBuffer)) & 0x80000000) != 0 )
  {
    _mm_lfence();
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&pwszLanguagesBuffer, pcchLanguagesBuffer);
    v3 = pwszLanguagesBuffer;
  }
  v12 = v3;
  if ( GetSystemPreferredUILanguages(4u, &pulNumLanguages, v3, &pcchLanguagesBuffer) && pulNumLanguages )
  {
    v4 = (const wchar_t *const *)ATL::operator+(v11, L"0x", &pwszLanguagesBuffer);
    v5 = swscanf_s(*v4, L"%hx", &v15);
    v6 = (_QWORD *)(v11[0] - 24LL);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v11[0] - 24LL + 16), 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 8LL))(*v6);
    }
    if ( v5 != 1 )
      v15 = SystemDefaultUILanguage;
  }
  v7 = pwszLanguagesBuffer;
  if ( pwszLanguagesBuffer )
  {
    v8 = wcsnlen_0(pwszLanguagesBuffer, *((int *)pwszLanguagesBuffer - 3));
    if ( v8 < 0 )
      goto LABEL_21;
    v7 = pwszLanguagesBuffer;
  }
  else
  {
    v8 = 0;
  }
  if ( v8 > *((_DWORD *)v7 - 3) )
LABEL_21:
    ATL::AtlThrowImpl(-2147024809);
  *((_DWORD *)v7 - 4) = v8;
  pwszLanguagesBuffer[v8] = 0;
  v9 = pwszLanguagesBuffer - 12;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)pwszLanguagesBuffer - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v9 + 8LL))(*(_QWORD *)v9);
  }
  return v15;
}

```

## disassembly

```asm
0x1400330a0  mov     [rsp-8+arg_0], rbx
0x1400330a5  mov     [rsp-8+arg_8], rsi
0x1400330aa  mov     [rsp-8+arg_10], rdi
0x1400330af  push    rbp
0x1400330b0  mov     rbp, rsp
0x1400330b3  sub     rsp, 60h
0x1400330b7  mov     rax, cs:__security_cookie
0x1400330be  xor     rax, rsp
0x1400330c1  mov     [rbp+var_8], rax
0x1400330c5  call    cs:__imp_GetSystemDefaultUILanguage
0x1400330cb  movzx   ebx, ax
0x1400330ce  mov     [rbp+var_1C], ax
0x1400330d2  xor     esi, esi
0x1400330d4  mov     [rbp+pulNumLanguages], esi
0x1400330d7  mov     [rbp+pcchLanguagesBuffer], esi
0x1400330da  lea     r9, [rbp+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x1400330de  xor     r8d, r8d; pwszLanguagesBuffer
0x1400330e1  lea     rdx, [rbp+pulNumLanguages]; pulNumLanguages
0x1400330e5  lea     edi, [rsi+4]
0x1400330e8  mov     ecx, edi; dwFlags
0x1400330ea  call    cs:__imp_GetSystemPreferredUILanguages
0x1400330f0  test    eax, eax
0x1400330f2  jz      loc_14003322D
0x1400330f8  mov     [rbp+pwszLanguagesBuffer], rsi
0x1400330fc  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x140033101  mov     rcx, rax
0x140033104  test    rax, rax
0x140033107  jz      loc_140033271
0x14003310d  mov     rax, [rax]
0x140033110  call    qword ptr [rax+18h]
0x140033113  lea     r8, [rax+18h]
0x140033117  mov     [rbp+pwszLanguagesBuffer], r8
0x14003311b  xorps   xmm0, xmm0
0x14003311e  xor     ecx, ecx
0x140033120  movups  [rbp+var_38], xmm0
0x140033124  mov     [rbp+var_28], rcx
0x140033128  lea     rcx, [rbp+pwszLanguagesBuffer]
0x14003312c  mov     qword ptr [rbp+var_38], rcx
0x140033130  mov     qword ptr [rbp+var_38+8], rsi
0x140033134  or      dword ptr [rbp+var_28], 0FFFFFFFFh
0x140033138  mov     edx, [rbp+pcchLanguagesBuffer]
0x14003313b  test    edx, edx
0x14003313d  js      loc_140033253
0x140033143  lea     ecx, [rsi+1]
0x140033146  sub     ecx, [rax+10h]
0x140033149  mov     eax, [rax+0Ch]
0x14003314c  sub     eax, edx
0x14003314e  or      eax, ecx
0x140033150  jge     short loc_140033165
0x140033152  lfence
0x140033155  mov     edx, [rbp+pcchLanguagesBuffer]
0x140033158  lea     rcx, [rbp+pwszLanguagesBuffer]
0x14003315c  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x140033161  mov     r8, [rbp+pwszLanguagesBuffer]; pwszLanguagesBuffer
0x140033165  mov     qword ptr [rbp+var_38+8], r8
0x140033169  lea     r9, [rbp+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x14003316d  lea     rdx, [rbp+pulNumLanguages]; pulNumLanguages
0x140033171  mov     ecx, edi; dwFlags
0x140033173  call    cs:__imp_GetSystemPreferredUILanguages
0x140033179  test    eax, eax
0x14003317b  jz      short loc_1400331D6
0x14003317d  cmp     [rbp+pulNumLanguages], esi
0x140033180  jbe     short loc_1400331D6
0x140033182  lea     r8, [rbp+pwszLanguagesBuffer]
0x140033186  lea     rdx, a0x; "0x"
0x14003318d  lea     rcx, [rbp+var_40]
0x140033191  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@PEBGAEBV10@@Z; ATL::operator+(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140033196  lea     r8, [rbp+var_1C]
0x14003319a  lea     rdx, aHx; "%hx"
0x1400331a1  mov     rcx, [rax]; Buffer
0x1400331a4  call    swscanf_s
0x1400331a9  mov     edi, eax
0x1400331ab  mov     rdx, [rbp+var_40]
0x1400331af  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400331b3  or      ecx, 0FFFFFFFFh
0x1400331b6  lock xadd [rdx+10h], ecx
0x1400331bb  sub     ecx, 1
0x1400331be  jg      short loc_1400331CD
0x1400331c0  lfence
0x1400331c3  mov     rcx, [rdx]
0x1400331c6  mov     r8, [rcx]
0x1400331c9  call    qword ptr [r8+8]
0x1400331cd  cmp     edi, 1
0x1400331d0  jz      short loc_1400331D6
0x1400331d2  mov     [rbp+var_1C], bx
0x1400331d6  mov     rax, [rbp+pwszLanguagesBuffer]
0x1400331da  test    rax, rax
0x1400331dd  jnz     short loc_1400331E3
0x1400331df  mov     ecx, esi
0x1400331e1  jmp     short loc_1400331FA
0x1400331e3  movsxd  rdx, dword ptr [rax-0Ch]; MaxCount
0x1400331e7  mov     rcx, rax; Source
0x1400331ea  call    wcsnlen_0
0x1400331ef  mov     rcx, rax
0x1400331f2  test    eax, eax
0x1400331f4  js      short loc_140033261
0x1400331f6  mov     rax, [rbp+pwszLanguagesBuffer]
0x1400331fa  cmp     ecx, [rax-0Ch]
0x1400331fd  jg      short loc_140033261
0x1400331ff  mov     [rax-10h], ecx
0x140033202  mov     ecx, ecx
0x140033204  mov     rax, [rbp+pwszLanguagesBuffer]
0x140033208  mov     [rax+rcx*2], si
0x14003320c  mov     rdx, [rbp+pwszLanguagesBuffer]
0x140033210  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140033214  or      eax, 0FFFFFFFFh
0x140033217  lock xadd [rdx+10h], eax
0x14003321c  sub     eax, 1
0x14003321f  jg      short loc_14003322D
0x140033221  lfence
0x140033224  mov     rcx, [rdx]
0x140033227  mov     rax, [rcx]
0x14003322a  call    qword ptr [rax+8]
0x14003322d  movzx   eax, [rbp+var_1C]
0x140033231  mov     rcx, [rbp+var_8]
0x140033235  xor     rcx, rsp; StackCookie
0x140033238  call    __security_check_cookie
0x14003323d  lea     r11, [rsp+60h+var_s0]
0x140033242  mov     rbx, [r11+10h]
0x140033246  mov     rsi, [r11+18h]
0x14003324a  mov     rdi, [r11+20h]
0x14003324e  mov     rsp, r11
0x140033251  pop     rbp
0x140033252  retn
0x140033253  mov     ecx, 80070057h; int
0x140033258  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14003325e  jmp     short $+2
0x140033260  nop
0x140033261  mov     ecx, 80070057h; int
0x140033266  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140033271  mov     ecx, 80004005h; int
0x140033276  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
