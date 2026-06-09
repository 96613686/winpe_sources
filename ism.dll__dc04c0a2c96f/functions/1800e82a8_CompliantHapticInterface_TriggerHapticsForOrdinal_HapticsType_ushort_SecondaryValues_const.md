# CompliantHapticInterface::TriggerHapticsForOrdinal(HapticsType,ushort,SecondaryValues const &)

- ea: `0x1800e82a8`
- end: `0x1800e858e`
- name: `?TriggerHapticsForOrdinal@CompliantHapticInterface@@QEBAJW4HapticsType@@GAEBUSecondaryValues@@@Z`
- size: `742`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x1800e8010`
- `0x1800e8070`
- `0x1800e80c4`
- `0x1800e8150`

## callees

- `0x18002f9b4`
- `0x18008daac`
- `0x18008ead4`
- `0x1800e4834`
- `0x1800e82a8`
- `0x1800f08d8`
- `0x1800f2478`
- `0x18019ba34`
- `0x18019ceac`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800e8510`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800e8510`
- `HID!HidP_SetUsageValue` at `0x1800e83be`
- `HID!HidP_SetUsageValue` at `0x1800e84bb`
- `HID!HidP_SetUsageValue` at `0x1800e83be`
- `HID!HidP_SetUsageValue` at `0x1800e84bb`

## string_xrefs

- `0x1800e84e2`: `onecoreuap\windows\moderncore\inputv2\inputprocessors\devices\haptic\hid\lib\complianthapticinterface.cpp`
- `0x1800e851e`: `onecoreuap\windows\moderncore\inputv2\inputprocessors\devices\haptic\hid\lib\complianthapticinterface.cpp`
- `0x1800e8565`: `onecoreuap\windows\moderncore\inputv2\inputprocessors\devices\haptic\hid\lib\complianthapticinterface.cpp`

## pseudocode

```c
__int64 __fastcall CompliantHapticInterface::TriggerHapticsForOrdinal(
        __int64 a1,
        ULONG a2,
        unsigned __int16 a3,
        __int64 a4)
{
  ULONG v5; // r12d
  _QWORD *v7; // r10
  __int64 v8; // r14
  unsigned int v9; // ebx
  __int64 v10; // rdx
  ULONG v11; // esi
  CHAR *Report; // rbx
  ULONG ReportLength; // eax
  __int64 v14; // rsi
  NTSTATUS v15; // eax
  __int64 v16; // rdx
  unsigned int LastError; // edi
  __int64 v18; // rdx
  ULONG v19; // r12d
  __int64 v20; // r9
  __int64 v21; // r8
  unsigned int v22; // ecx
  unsigned int v23; // eax
  int v24; // ecx
  int v25; // eax
  unsigned int v26; // eax
  bool v27; // cf
  void *v28; // rcx
  const char *v29; // r9
  int UsageValue; // [rsp+20h] [rbp-40h]
  int UsageValuea; // [rsp+20h] [rbp-40h]
  CHAR *v33; // [rsp+40h] [rbp-20h] BYREF
  _BYTE v34[16]; // [rsp+48h] [rbp-18h] BYREF
  __int64 v35; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  __int64 v37; // [rsp+A0h] [rbp+40h] BYREF
  ULONG nNumberOfBytesToWrite; // [rsp+A8h] [rbp+48h] BYREF
  unsigned __int16 v39; // [rsp+B0h] [rbp+50h] BYREF

  v39 = a3;
  nNumberOfBytesToWrite = a2;
  v5 = a3;
  if ( (unsigned __int64)(*(_QWORD *)a1 - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v9 = -2147483629;
    v10 = 542;
    goto LABEL_45;
  }
  std::_Tree<std::_Tmap_traits<unsigned short,HapticsWaveform,std::less<unsigned short>,std::allocator<std::pair<unsigned short const,HapticsWaveform>>,0>>::_Find_lower_bound<unsigned short>(
    a1 + 232,
    v34,
    &v39);
  v8 = v35;
  if ( *(_BYTE *)(v35 + 25) || (unsigned __int16)v5 < *(_WORD *)(v35 + 28) || v35 == *v7 )
  {
    v9 = -2147024809;
    v10 = 546;
    goto LABEL_45;
  }
  if ( !*(_BYTE *)(a1 + 336) )
  {
    v9 = -2147024809;
    v10 = 551;
LABEL_45:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputprocessors\\devices\\haptic\\hid\\lib\\complianthapticinterface.cpp",
      (const char *)v9,
      UsageValue);
    return v9;
  }
  if ( (*(_BYTE *)(v35 + 40) & 4) != 0 )
  {
    v9 = -2147024809;
    v10 = 557;
    goto LABEL_45;
  }
  v11 = *(unsigned __int16 *)(a1 + 22);
  v37 = std::optional<HapticsTrigger>::value(a1 + 248);
  v33 = (CHAR *)operator new[](v11, (const struct std::nothrow_t *)&std::nothrow);
  Report = v33;
  memset_0(v33, 0, v11);
  ReportLength = v11;
  v14 = v37;
  *v33 = *(_BYTE *)(v37 + 2);
  nNumberOfBytesToWrite = ReportLength;
  v15 = HidP_SetUsageValue(
          HidP_Output,
          0xEu,
          *(_WORD *)(v14 + 6),
          *(_WORD *)(v14 + 56),
          v5,
          *(PHIDP_PREPARSED_DATA *)(a1 + 8),
          Report,
          ReportLength);
  LastError = v15;
  if ( v15 < 0 )
  {
    v18 = 580;
LABEL_38:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputprocessors\\devices\\haptic\\hid\\lib\\complianthapticinterface.cpp",
      (const char *)(unsigned int)v15,
      UsageValuea);
LABEL_41:
    VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(&v33);
    return LastError;
  }
  v19 = nNumberOfBytesToWrite;
  v20 = **(_QWORD **)(v14 + 72);
  v37 = v20;
  while ( !*(_BYTE *)(v20 + 25) )
  {
    LODWORD(v21) = 0;
    if ( (*(_BYTE *)(v8 + 40) & 8) != 0 )
      goto LABEL_35;
    v21 = *(unsigned int *)(v20 + 76);
    switch ( *(_WORD *)(v20 + 28) )
    {
      case '#':
        if ( *(float *)a4 == 0.0 )
        {
LABEL_31:
          LODWORD(v21) = 0;
          goto LABEL_35;
        }
        v26 = 1;
        LODWORD(v21) = (int)(float)((float)(int)v21 * *(float *)a4);
        v27 = (_DWORD)v21 == 0;
        goto LABEL_33;
      case '$':
        v25 = *(_DWORD *)(a4 + 4);
        if ( !v25 )
          goto LABEL_31;
        v26 = v25 - 1;
        v27 = v26 < (unsigned int)v21;
LABEL_33:
        if ( v27 )
          LODWORD(v21) = v26;
        goto LABEL_35;
      case '%':
        v24 = *(_DWORD *)(a4 + 8);
        if ( !v24 )
          goto LABEL_31;
        v22 = *(_DWORD *)(v8 + 36) + v24;
        goto LABEL_25;
    }
    if ( *(_WORD *)(v20 + 28) != 40 )
      goto LABEL_36;
    v22 = *(_DWORD *)(a4 + 12);
    if ( v22 )
    {
      v23 = *(_DWORD *)(v20 + 76);
      if ( v22 < (unsigned int)v21 )
        v23 = *(_DWORD *)(a4 + 12);
      if ( *(_DWORD *)(v20 + 72) > v23 )
      {
        LODWORD(v21) = *(_DWORD *)(v20 + 72);
        goto LABEL_35;
      }
LABEL_25:
      if ( v22 < (unsigned int)v21 )
        LODWORD(v21) = v22;
    }
LABEL_35:
    v15 = HidP_SetUsageValue(
            HidP_Output,
            0xEu,
            *(_WORD *)(v14 + 6),
            *(_WORD *)(v20 + 28),
            v21,
            *(PHIDP_PREPARSED_DATA *)(a1 + 8),
            Report,
            v19);
    LastError = v15;
    if ( v15 < 0 )
    {
      v18 = 633;
      goto LABEL_38;
    }
LABEL_36:
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,MagnifierRecognizer::ContactState>>>,std::_Iterator_base0>::operator++(
      &v37,
      v16,
      v21);
    v20 = v37;
  }
  v28 = *(void **)a1;
  nNumberOfBytesToWrite = 0;
  if ( !WriteFile(v28, Report, v19, &nNumberOfBytesToWrite, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x285,
                  (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputprocessors\\devices\\haptic\\hid\\lib\\co"
                                "mplianthapticinterface.cpp",
                  v29);
    goto LABEL_41;
  }
  VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(&v33);
  return 0;
}

```

## disassembly

```asm
0x1800e82a8  mov     [rsp-38h+arg_18], rbx
0x1800e82ad  mov     [rsp-38h+arg_10], r8w
0x1800e82b3  mov     [rsp-38h+nNumberOfBytesToWrite], edx
0x1800e82b7  push    rbp
0x1800e82b8  push    rsi
0x1800e82b9  push    rdi
0x1800e82ba  push    r12
0x1800e82bc  push    r13
0x1800e82be  push    r14
0x1800e82c0  push    r15
0x1800e82c2  mov     rbp, rsp
0x1800e82c5  sub     rsp, 60h
0x1800e82c9  mov     rax, [rcx]
0x1800e82cc  mov     r13, r9
0x1800e82cf  dec     rax
0x1800e82d2  movzx   r12d, r8w
0x1800e82d6  mov     r15, rcx
0x1800e82d9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800e82dd  ja      loc_1800E8557
0x1800e82e3  lea     r10, [rcx+0E8h]
0x1800e82ea  mov     rcx, r10
0x1800e82ed  lea     r8, [rbp+arg_10]
0x1800e82f1  lea     rdx, [rbp+var_18]
0x1800e82f5  call    ??$_Find_lower_bound@G@?$_Tree@V?$_Tmap_traits@GUHapticsWaveform@@U?$less@G@std@@V?$allocator@U?$pair@$$CBGUHapticsWaveform@@@std@@@3@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBGUHapticsWaveform@@@std@@PEAX@std@@@1@AEBG@Z; std::_Tree<std::_Tmap_traits<ushort,HapticsWaveform,std::less<ushort>,std::allocator<std::pair<ushort const,HapticsWaveform>>,0>>::_Find_lower_bound<ushort>(ushort const &)
0x1800e82fa  mov     r14, [rbp+var_8]
0x1800e82fe  cmp     byte ptr [r14+19h], 0
0x1800e8303  jnz     loc_1800E854B
0x1800e8309  cmp     r12w, [r14+1Ch]
0x1800e830e  jb      loc_1800E854B
0x1800e8314  cmp     r14, [r10]
0x1800e8317  jz      loc_1800E854B
0x1800e831d  cmp     byte ptr [r15+150h], 0
0x1800e8325  jnz     short loc_1800E8336
0x1800e8327  mov     ebx, 80070057h
0x1800e832c  mov     edx, 227h
0x1800e8331  jmp     loc_1800E8561
0x1800e8336  test    byte ptr [r14+28h], 4
0x1800e833b  jz      short loc_1800E834C
0x1800e833d  mov     ebx, 80070057h
0x1800e8342  mov     edx, 22Dh
0x1800e8347  jmp     loc_1800E8561
0x1800e834c  movzx   esi, word ptr [r15+16h]
0x1800e8351  lea     rcx, [r15+0F8h]
0x1800e8358  call    ?value@?$optional@UHapticsTrigger@@@std@@QEGBAAEBUHapticsTrigger@@XZ; std::optional<HapticsTrigger>::value(void)
0x1800e835d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800e8364  mov     [rbp+arg_0], rax
0x1800e8368  mov     ecx, esi; unsigned __int64
0x1800e836a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800e836f  mov     r8d, esi; Size
0x1800e8372  mov     [rbp+var_20], rax
0x1800e8376  xor     edx, edx; Val
0x1800e8378  mov     rcx, rax; void *
0x1800e837b  mov     rbx, rax
0x1800e837e  call    memset_0
0x1800e8383  mov     rax, [rbp+arg_0]
0x1800e8387  mov     edx, 0Eh; UsagePage
0x1800e838c  mov     cl, [rax+2]
0x1800e838f  mov     eax, esi
0x1800e8391  mov     rsi, [rbp+arg_0]
0x1800e8395  mov     [rbx], cl
0x1800e8397  lea     ecx, [rdx-0Dh]; ReportType
0x1800e839a  mov     [rsp+60h+ReportLength], eax; ReportLength
0x1800e839e  mov     [rbp+nNumberOfBytesToWrite], eax
0x1800e83a1  mov     rax, [r15+8]
0x1800e83a5  movzx   r9d, word ptr [rsi+38h]; Usage
0x1800e83aa  movzx   r8d, word ptr [rsi+6]; LinkCollection
0x1800e83af  mov     [rsp+60h+Report], rbx; Report
0x1800e83b4  mov     [rsp+60h+PreparsedData], rax; PreparsedData
0x1800e83b9  mov     [rsp+60h+UsageValue], r12d; UsageValue
0x1800e83be  call    cs:__imp_HidP_SetUsageValue
0x1800e83c4  mov     edi, eax
0x1800e83c6  test    eax, eax
0x1800e83c8  jns     short loc_1800E83D4
0x1800e83ca  mov     edx, 244h
0x1800e83cf  jmp     loc_1800E84DE
0x1800e83d4  mov     r9, [rsi+48h]
0x1800e83d8  mov     r12d, [rbp+nNumberOfBytesToWrite]
0x1800e83dc  mov     r9, [r9]
0x1800e83df  mov     [rbp+arg_0], r9
0x1800e83e3  cmp     byte ptr [r9+19h], 0
0x1800e83e8  jnz     loc_1800E84F3
0x1800e83ee  xor     r8d, r8d
0x1800e83f1  test    byte ptr [r14+28h], 8
0x1800e83f6  jnz     loc_1800E8491
0x1800e83fc  movzx   ecx, word ptr [r9+1Ch]
0x1800e8401  mov     r8d, [r9+4Ch]
0x1800e8405  sub     ecx, 23h ; '#'
0x1800e8408  jz      short loc_1800E845E
0x1800e840a  sub     ecx, 1
0x1800e840d  jz      short loc_1800E844F
0x1800e840f  sub     ecx, 1
0x1800e8412  jz      short loc_1800E843A
0x1800e8414  cmp     ecx, 3
0x1800e8417  jnz     loc_1800E84C7
0x1800e841d  mov     ecx, [r13+0Ch]
0x1800e8421  test    ecx, ecx
0x1800e8423  jz      short loc_1800E8491
0x1800e8425  cmp     ecx, r8d
0x1800e8428  mov     eax, r8d
0x1800e842b  cmovb   eax, ecx
0x1800e842e  cmp     [r9+48h], eax
0x1800e8432  jbe     short loc_1800E8446
0x1800e8434  mov     r8d, [r9+48h]
0x1800e8438  jmp     short loc_1800E8491
0x1800e843a  mov     ecx, [r13+8]
0x1800e843e  test    ecx, ecx
0x1800e8440  jz      short loc_1800E846F
0x1800e8442  add     ecx, [r14+24h]
0x1800e8446  cmp     ecx, r8d
0x1800e8449  cmovb   r8d, ecx
0x1800e844d  jmp     short loc_1800E8491
0x1800e844f  mov     eax, [r13+4]
0x1800e8453  test    eax, eax
0x1800e8455  jz      short loc_1800E846F
0x1800e8457  dec     eax
0x1800e8459  cmp     eax, r8d
0x1800e845c  jmp     short loc_1800E848D
0x1800e845e  movss   xmm1, dword ptr [r13+0]
0x1800e8464  ucomiss xmm1, cs:__real@00000000
0x1800e846b  jp      short loc_1800E8474
0x1800e846d  jnz     short loc_1800E8474
0x1800e846f  xor     r8d, r8d
0x1800e8472  jmp     short loc_1800E8491
0x1800e8474  xorps   xmm0, xmm0
0x1800e8477  mov     eax, 1
0x1800e847c  cvtsi2ss xmm0, r8
0x1800e8481  mulss   xmm0, xmm1
0x1800e8485  cvttss2si r8, xmm0
0x1800e848a  cmp     r8d, eax
0x1800e848d  cmovb   r8d, eax
0x1800e8491  mov     rax, [r15+8]
0x1800e8495  mov     edx, 0Eh; UsagePage
0x1800e849a  movzx   r9d, word ptr [r9+1Ch]; Usage
0x1800e849f  mov     [rsp+60h+ReportLength], r12d; ReportLength
0x1800e84a4  mov     [rsp+60h+Report], rbx; Report
0x1800e84a9  mov     [rsp+60h+PreparsedData], rax; PreparsedData
0x1800e84ae  lea     ecx, [rdx-0Dh]; ReportType
0x1800e84b1  mov     [rsp+60h+UsageValue], r8d; int
0x1800e84b6  movzx   r8d, word ptr [rsi+6]; LinkCollection
0x1800e84bb  call    cs:__imp_HidP_SetUsageValue
0x1800e84c1  mov     edi, eax
0x1800e84c3  test    eax, eax
0x1800e84c5  js      short loc_1800E84D9
0x1800e84c7  lea     rcx, [rbp+arg_0]
0x1800e84cb  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKUContactState@MagnifierRecognizer@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,MagnifierRecognizer::ContactState>>>,std::_Iterator_base0>::operator++(void)
0x1800e84d0  mov     r9, [rbp+arg_0]
0x1800e84d4  jmp     loc_1800E83E3
0x1800e84d9  mov     edx, 279h; void *
0x1800e84de  mov     rcx, [rbp+38h]; this
0x1800e84e2  lea     r8, aOnecoreuapWind_214; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800e84e9  mov     r9d, eax; char *
0x1800e84ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e84f1  jmp     short loc_1800E8531
0x1800e84f3  mov     rcx, [r15]; hFile
0x1800e84f6  lea     r9, [rbp+nNumberOfBytesToWrite]; lpNumberOfBytesWritten
0x1800e84fa  mov     r8d, r12d; nNumberOfBytesToWrite
0x1800e84fd  mov     [rbp+nNumberOfBytesToWrite], 0
0x1800e8504  mov     rdx, rbx; lpBuffer
0x1800e8507  mov     qword ptr [rsp+60h+UsageValue], 0; lpOverlapped
0x1800e8510  call    cs:__imp_WriteFile
0x1800e8516  test    eax, eax
0x1800e8518  jnz     short loc_1800E853E
0x1800e851a  mov     rcx, [rbp+38h]; this
0x1800e851e  lea     r8, aOnecoreuapWind_214; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800e8525  mov     edx, 285h; void *
0x1800e852a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800e852f  mov     edi, eax
0x1800e8531  lea     rcx, [rbp+var_20]
0x1800e8535  call    ??1?$VariableSizedPayloadStorage@UInputInfo@@@@QEAA@XZ; VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(void)
0x1800e853a  mov     eax, edi
0x1800e853c  jmp     short loc_1800E8576
0x1800e853e  lea     rcx, [rbp+var_20]
0x1800e8542  call    ??1?$VariableSizedPayloadStorage@UInputInfo@@@@QEAA@XZ; VariableSizedPayloadStorage<InputInfo>::~VariableSizedPayloadStorage<InputInfo>(void)
0x1800e8547  xor     eax, eax
0x1800e8549  jmp     short loc_1800E8576
0x1800e854b  mov     ebx, 80070057h
0x1800e8550  mov     edx, 222h
0x1800e8555  jmp     short loc_1800E8561
0x1800e8557  mov     ebx, 80000013h
0x1800e855c  mov     edx, 21Eh; void *
0x1800e8561  mov     rcx, [rbp+38h]; this
0x1800e8565  lea     r8, aOnecoreuapWind_214; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800e856c  mov     r9d, ebx; char *
0x1800e856f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e8574  mov     eax, ebx
0x1800e8576  mov     rbx, [rsp+60h+arg_18]
0x1800e857e  add     rsp, 60h
0x1800e8582  pop     r15
0x1800e8584  pop     r14
0x1800e8586  pop     r13
0x1800e8588  pop     r12
0x1800e858a  pop     rdi
0x1800e858b  pop     rsi
0x1800e858c  pop     rbp
0x1800e858d  retn
```
