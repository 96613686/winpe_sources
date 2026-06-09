# Enumerator::GetIndex<ITraceDataProvider>(tagVARIANT,long (ITraceDataProvider::*)(ushort * *),ulong *)

- ea: `0x180006170`
- end: `0x1800067a6`
- name: `??$GetIndex@UITraceDataProvider@@@Enumerator@@IEAAJUtagVARIANT@@P8ITraceDataProvider@@EAAJPEAPEAG@ZPEAK@Z`
- size: `1590`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180005200`
- `0x180005d70`
- `0x18011bab8`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x180006170`
- `0x1800198b0`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000672f`
- `msvcrt!_wcsicmp` at `0x18000672f`
- `OLEAUT32!__imp_SysFreeString` at `0x180006321`
- `OLEAUT32!__imp_SysFreeString` at `0x180006321`
- `OLEAUT32!__imp_VariantChangeType` at `0x180006224`
- `OLEAUT32!__imp_VariantChangeType` at `0x180006224`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800061f9`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800061f9`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000625c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000625c`

## pseudocode

```c
__int64 __fastcall Enumerator::GetIndex<ITraceDataProvider>(
        __int64 a1,
        VARIANTARG *a2,
        __int64 (__fastcall *a3)(__int64, BSTR *),
        unsigned int *a4)
{
  int vt; // eax
  __int64 v8; // rdx
  SAFEARRAY *v10; // rcx
  unsigned int i; // r14d
  HRESULT v12; // eax
  unsigned __int64 v13; // rdx
  int v14; // edi
  HRESULT v15; // eax
  unsigned __int64 v16; // rdx
  OLECHAR *v17; // rbx
  __int64 v19; // rax
  bool v20; // zf
  __int64 v21; // rax
  __int64 v22; // rax
  unsigned int v23; // edx
  __int64 v24; // [rsp+78h] [rbp-90h] BYREF
  BSTR v25; // [rsp+80h] [rbp-88h] BYREF
  __int64 v26; // [rsp+88h] [rbp-80h] BYREF
  void *ppvData; // [rsp+90h] [rbp-78h] BYREF
  BSTR bstrString[2]; // [rsp+98h] [rbp-70h] BYREF
  unsigned __int16 v29[64]; // [rsp+A8h] [rbp-60h] BYREF
  unsigned __int16 v30[64]; // [rsp+128h] [rbp+20h] BYREF
  unsigned __int16 v31[64]; // [rsp+1A8h] [rbp+A0h] BYREF

  vt = a2->vt;
  v8 = 0;
  bstrString[0] = 0;
  ppvData = 0;
  v26 = 0;
  if ( vt == 9 )
  {
LABEL_2:
    v10 = *(SAFEARRAY **)(a1 + 64);
    if ( !v10 )
    {
      v14 = -2147023728;
      goto LABEL_12;
    }
    i = *(_DWORD *)(a1 + 76);
    v12 = SafeArrayAccessData(v10, &ppvData);
    v14 = v12;
    if ( v12 < 0 )
    {
      LODWORD(v24) = 0;
      LODWORD(v25) = v12;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_9;
      }
      PlaiWhoAmI(v30, v13);
      v22 = -1;
      do
        v20 = v30[++v22] == 0;
      while ( !v20 );
    }
    else
    {
      if ( a2->vt != 17 )
      {
        switch ( a2->vt )
        {
          case 2u:
          case 3u:
          case 0x10u:
          case 0x12u:
          case 0x13u:
            break;
          case 8u:
            for ( i = 0; i < *(_DWORD *)(a1 + 76); ++i )
            {
              v24 = 24LL * i;
              if ( *(_WORD *)((char *)ppvData + v24) == 9 )
              {
                if ( v26 )
                {
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
                  v26 = 0;
                }
                v14 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))((char *)ppvData + v24 + 8))(
                        *(_QWORD *)((char *)ppvData + v24 + 8),
                        &GUID_03837512_098b_11d8_9414_505054503030,
                        &v26);
                if ( v14 >= 0 )
                {
                  PlaiFreeString(bstrString[0]);
                  bstrString[0] = 0;
                  v14 = a3(v26, bstrString);
                  if ( v14 >= 0 && bstrString[0] && *bstrString[0] && !_wcsicmp(bstrString[0], a2->bstrVal) )
                    break;
                }
              }
            }
            goto LABEL_7;
          case 9u:
            v23 = *(_DWORD *)(a1 + 76);
            for ( i = 0; i < v23; ++i )
            {
              if ( *((_WORD *)ppvData + 12 * i) == 9 && a2->llVal == *((_QWORD *)ppvData + 3 * i + 1) )
                break;
            }
            goto LABEL_7;
          default:
            goto LABEL_7;
        }
      }
      v15 = VariantChangeType(a2, a2, 0, 0x13u);
      v14 = v15;
      if ( v15 >= 0 )
      {
        i = a2->cyVal.Lo;
LABEL_7:
        if ( i >= *(_DWORD *)(a1 + 76) )
          v14 = -2147023728;
        else
          *a4 = i;
        goto LABEL_9;
      }
      LODWORD(v24) = 0;
      LODWORD(v25) = v15;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
LABEL_9:
        if ( ppvData )
        {
          SafeArrayUnaccessData(*(SAFEARRAY **)(a1 + 64));
          ppvData = 0;
        }
        v8 = v26;
        goto LABEL_12;
      }
      PlaiWhoAmI(v31, v16);
      v21 = -1;
      do
        v20 = v31[++v21] == 0;
      while ( !v20 );
    }
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v25, 4, byte_180147320, 1, &v24, 4);
    goto LABEL_9;
  }
  switch ( vt )
  {
    case 2:
    case 3:
    case 16:
    case 17:
    case 18:
    case 19:
      goto LABEL_2;
    case 8:
      if ( a3 )
        goto LABEL_2;
      break;
    default:
      break;
  }
  v14 = -2147024809;
  LODWORD(v24) = -2147024809;
  LODWORD(v25) = 0;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v29, 0);
    v19 = -1;
    do
      v20 = v29[++v19] == 0;
    while ( !v20 );
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v24, 4, byte_180147320, 1, &v25, 4);
    goto LABEL_9;
  }
LABEL_12:
  v17 = bstrString[0];
  if ( bstrString[0] )
  {
    v25 = bstrString[0];
    LODWORD(v24) = 0;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000200LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000200LL) )
    {
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_FREE_STRING, 3, byte_180147320, 1, &v24, 4, &v25, 8);
    }
    SysFreeString(v17);
    v8 = v26;
  }
  bstrString[0] = 0;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180006170  mov     r11, rsp
0x180006173  push    rbp
0x180006174  push    rdi
0x180006175  lea     rbp, [r11-178h]
0x18000617c  sub     rsp, 268h
0x180006183  mov     rax, cs:__security_cookie
0x18000618a  xor     rax, rsp
0x18000618d  mov     [rbp+170h+var_50], rax
0x180006194  mov     [r11-18h], rbx
0x180006198  mov     rbx, rcx
0x18000619b  mov     [r11-20h], rsi
0x18000619f  mov     rsi, rdx
0x1800061a2  mov     [r11-28h], r12
0x1800061a6  mov     r12, r8
0x1800061a9  mov     [r11-30h], r13
0x1800061ad  lea     r8, __ImageBase
0x1800061b4  xor     r13d, r13d
0x1800061b7  mov     [r11-38h], r14
0x1800061bb  movzx   eax, word ptr [rsi]
0x1800061be  lea     r14, byte_180147320
0x1800061c5  mov     [r11-40h], r15
0x1800061c9  mov     edx, r13d; unsigned __int64
0x1800061cc  mov     [rbp+170h+bstrString], r13
0x1800061d0  mov     r15, r9
0x1800061d3  mov     [rbp+170h+ppvData], r13
0x1800061d7  mov     [rbp+170h+var_1F0], rdx
0x1800061db  cmp     eax, 9
0x1800061de  jnz     loc_180006330
0x1800061e4  mov     rcx, [rbx+40h]; jumptable 000000018000661E cases 2,3,16-19
0x1800061e8  test    rcx, rcx
0x1800061eb  jz      loc_18000662E
0x1800061f1  mov     r14d, [rbx+4Ch]
0x1800061f5  lea     rdx, [rbp+170h+ppvData]; ppvData
0x1800061f9  call    cs:__imp_SafeArrayAccessData
0x1800061ff  mov     edi, eax
0x180006201  test    eax, eax
0x180006203  js      loc_1800065CB
0x180006209  movzx   eax, word ptr [rsi]
0x18000620c  cmp     eax, 11h
0x18000620f  jnz     loc_1800062CB
0x180006215  mov     r9d, 13h; jumptable 00000001800062F2 cases 2,3,16,18,19
0x18000621b  xor     r8d, r8d; wFlags
0x18000621e  mov     rdx, rsi; pvarSrc
0x180006221  mov     rcx, rsi; pvargDest
0x180006224  call    cs:__imp_VariantChangeType
0x18000622a  mov     edi, eax
0x18000622c  test    eax, eax
0x18000622e  js      loc_180006423
0x180006234  mov     r14d, [rsi+8]
0x180006238  cmp     r14d, [rbx+4Ch]; jumptable 00000001800062F2 default case, cases 4-7,10-15,17
0x18000623c  jnb     loc_180006745
0x180006242  mov     [r15], r14d
0x180006245  lea     r14, byte_180147320
0x18000624c  mov     ecx, 40h ; '@'
0x180006251  cmp     [rbp+170h+ppvData], 0
0x180006256  jz      short loc_180006266
0x180006258  mov     rcx, [rbx+rcx]; psa
0x18000625c  call    cs:__imp_SafeArrayUnaccessData
0x180006262  mov     [rbp+170h+ppvData], r13
0x180006266  mov     rdx, [rbp+170h+var_1F0]
0x18000626a  mov     rbx, [rbp+170h+bstrString]
0x18000626e  mov     r15, [rsp+270h+var_38]
0x180006276  mov     r12, [rsp+270h+var_20]
0x18000627e  mov     rsi, [rsp+270h+var_18]
0x180006286  test    rbx, rbx
0x180006289  jnz     short loc_1800062F4
0x18000628b  mov     r14, [rsp+270h+var_30]
0x180006293  mov     rbx, [rsp+260h]
0x18000629b  mov     [rbp+170h+bstrString], r13
0x18000629f  mov     r13, [rsp+270h+var_28]
0x1800062a7  test    rdx, rdx
0x1800062aa  jnz     loc_18000674F
0x1800062b0  mov     eax, edi
0x1800062b2  mov     rcx, [rbp+170h+var_50]
0x1800062b9  xor     rcx, rsp; StackCookie
0x1800062bc  call    __security_check_cookie
0x1800062c1  add     rsp, 268h
0x1800062c8  pop     rdi
0x1800062c9  pop     rbp
0x1800062ca  retn
0x1800062cb  add     eax, 0FFFFFFFEh; switch 18 cases
0x1800062ce  cmp     eax, 11h
0x1800062d1  ja      def_1800062F2; jumptable 00000001800062F2 default case, cases 4-7,10-15,17
0x1800062d7  lea     rdx, __ImageBase
0x1800062de  cdqe
0x1800062e0  movzx   eax, ds:(byte_180006774 - 180000000h)[rdx+rax]
0x1800062e8  mov     ecx, ds:(jpt_1800062F2 - 180000000h)[rdx+rax*4]
0x1800062ef  add     rcx, rdx
0x1800062f2  jmp     rcx; switch jump
0x1800062f4  cmp     dword ptr cs:xmmword_180169738, 0
0x1800062fb  mov     [rsp+270h+var_1F8], rbx
0x180006300  mov     dword ptr [rsp+270h+var_200], r13d
0x180006305  jz      short loc_18000631E
0x180006307  mov     rcx, 4000000000000200h
0x180006311  test    qword ptr cs:xmmword_180169738+8, rcx
0x180006318  jnz     loc_18000650E
0x18000631e  mov     rcx, rbx; bstrString
0x180006321  call    cs:__imp_SysFreeString
0x180006327  mov     rdx, [rbp+170h+var_1F0]
0x18000632b  jmp     loc_18000628B
0x180006330  add     eax, 0FFFFFFFEh; switch 18 cases
0x180006333  cmp     eax, 11h
0x180006336  jbe     loc_180006608
0x18000633c  cmp     dword ptr cs:xmmword_180169738, edx; jumptable 000000018000661E default case, cases 4-7,9-15
0x180006342  mov     edi, 80070057h
0x180006347  mov     dword ptr [rsp+270h+var_200], edi
0x18000634b  mov     dword ptr [rsp+270h+var_1F8], r13d
0x180006350  jz      loc_18000626A
0x180006356  mov     rcx, 4000000000000800h
0x180006360  test    qword ptr cs:xmmword_180169738+8, rcx
0x180006367  jz      loc_18000626A
0x18000636d  mov     rax, cs:qword_180169748
0x180006374  and     rax, rcx
0x180006377  cmp     cs:qword_180169748, rax
0x18000637e  jnz     loc_18000626A
0x180006384  lea     rcx, [rbp+170h+var_1D0]; unsigned __int16 *
0x180006388  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18000638d  lea     rcx, [rbp+170h+var_1D0]
0x180006391  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180006398  nop     dword ptr [rax+rax+00000000h]
0x1800063a0  cmp     [rcx+rax*2+2], r13w
0x1800063a6  lea     rax, [rax+1]
0x1800063aa  jnz     short loc_1800063A0
0x1800063ac  lea     ecx, [rax+rax]
0x1800063af  mov     r8d, 5
0x1800063b5  add     rcx, 2
0x1800063b9  lea     rax, [rbp+170h+var_1D0]
0x1800063bd  mov     [rsp+60h], rcx
0x1800063c2  lea     r9, [rsp+270h+var_200]
0x1800063c7  mov     [rsp+270h+var_218], rax
0x1800063cc  lea     rdx, PLA_EVENT_ERROR
0x1800063d3  mov     [rsp+270h+var_220], 15h
0x1800063dc  lea     rax, aEnumeratorGeti_0; "Enumerator::GetIndex"
0x1800063e3  mov     [rsp+270h+var_228], rax
0x1800063e8  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800063ef  mov     [rsp+270h+var_230], 4
0x1800063f8  lea     rax, [rsp+270h+var_1F8]
0x1800063fd  mov     [rsp+270h+var_238], rax
0x180006402  mov     [rsp+270h+var_240], 1
0x18000640b  mov     [rsp+270h+var_248], r14
0x180006410  mov     [rsp+270h+var_250], 4
0x180006419  call    EventingWriteEvent
0x18000641e  jmp     loc_18000624C
0x180006423  cmp     dword ptr cs:xmmword_180169738, r13d
0x18000642a  mov     dword ptr [rsp+270h+var_200], r13d
0x18000642f  mov     dword ptr [rsp+270h+var_1F8], eax
0x180006433  jz      loc_180006245
0x180006439  mov     rcx, 4000000000000800h
0x180006443  test    qword ptr cs:xmmword_180169738+8, rcx
0x18000644a  jz      loc_180006245
0x180006450  mov     rax, cs:qword_180169748
0x180006457  and     rax, rcx
0x18000645a  cmp     cs:qword_180169748, rax
0x180006461  jnz     loc_180006245
0x180006467  lea     rcx, [rbp+170h+var_D0]; unsigned __int16 *
0x18000646e  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180006473  lea     rcx, [rbp+170h+var_D0]
0x18000647a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180006481  cmp     [rcx+rax*2+2], r13w
0x180006487  lea     rax, [rax+1]
0x18000648b  jnz     short loc_180006481
0x18000648d  lea     ecx, [rax+rax]
0x180006490  lea     rax, [rbp+170h+var_D0]
0x180006497  add     rcx, 2
0x18000649b  lea     r14, byte_180147320
0x1800064a2  mov     [rsp+60h], rcx
0x1800064a7  lea     r9, [rsp+270h+var_1F8]
0x1800064ac  mov     [rsp+270h+var_218], rax
0x1800064b1  lea     rdx, PLA_EVENT_ERROR
0x1800064b8  mov     [rsp+270h+var_220], 15h
0x1800064c1  lea     rax, aEnumeratorGeti_0; "Enumerator::GetIndex"
0x1800064c8  mov     [rsp+270h+var_228], rax
0x1800064cd  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800064d4  mov     [rsp+270h+var_230], 4
0x1800064dd  lea     rax, [rsp+270h+var_200]
0x1800064e2  mov     [rsp+270h+var_238], rax
0x1800064e7  mov     r8d, 5
0x1800064ed  mov     [rsp+270h+var_240], 1
0x1800064f6  mov     [rsp+270h+var_248], r14
0x1800064fb  mov     [rsp+270h+var_250], 4
0x180006504  call    EventingWriteEvent
0x180006509  jmp     loc_18000624C
0x18000650e  mov     rax, cs:qword_180169748
0x180006515  and     rax, rcx
0x180006518  cmp     cs:qword_180169748, rax
0x18000651f  jnz     loc_18000631E
0x180006525  mov     [rsp+270h+var_230], 8
0x18000652e  lea     rax, [rsp+270h+var_1F8]
0x180006533  mov     [rsp+270h+var_238], rax
0x180006538  lea     rdx, PLA_EVENT_FREE_STRING
0x18000653f  lea     rax, [rsp+270h+var_200]
0x180006544  mov     [rsp+270h+var_240], 4
0x18000654d  mov     [rsp+270h+var_248], rax
0x180006552  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180006559  mov     r9, r14
0x18000655c  mov     [rsp+270h+var_250], 1
0x180006565  mov     r8d, 3
0x18000656b  call    EventingWriteEvent
0x180006570  jmp     loc_18000631E
0x180006575  mov     rax, cs:qword_180169748
0x18000657c  and     rax, rcx
0x18000657f  cmp     cs:qword_180169748, rax
0x180006586  jnz     loc_180006245
0x18000658c  lea     rcx, [rbp+170h+var_150]; unsigned __int16 *
0x180006590  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180006595  lea     rcx, [rbp+170h+var_150]
0x180006599  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800065a0  cmp     [rcx+rax*2+2], r13w
0x1800065a6  lea     rax, [rax+1]
0x1800065aa  jnz     short loc_1800065A0
0x1800065ac  lea     ecx, [rax+rax]
0x1800065af  lea     rax, [rbp+170h+var_150]
0x1800065b3  jmp     loc_180006497
0x1800065b8  xor     eax, eax
0x1800065ba  cmp     ax, [rcx]
0x1800065bd  jnz     loc_18000672B
0x1800065c3  inc     r14d
0x1800065c6  jmp     loc_180006683
0x1800065cb  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800065d2  mov     dword ptr [rsp+270h+var_200], r13d
0x1800065d7  mov     dword ptr [rsp+270h+var_1F8], eax
0x1800065db  jz      loc_180006245
0x1800065e1  mov     rcx, 4000000000000800h
0x1800065eb  test    qword ptr cs:xmmword_180169738+8, rcx
0x1800065f2  jz      loc_180006245
0x1800065f8  jmp     loc_180006575
0x1800065fd  mov     rcx, [rbp+170h+bstrString]; String1
0x180006601  test    rcx, rcx
0x180006604  jz      short loc_1800065C3
0x180006606  jmp     short loc_1800065B8
0x180006608  cdqe
0x18000660a  movzx   eax, ds:(byte_180006794 - 180000000h)[r8+rax]
0x180006613  mov     ecx, ds:(jpt_18000661E - 180000000h)[r8+rax*4]
0x18000661b  add     rcx, r8
0x18000661e  jmp     rcx; switch jump
0x180006620  test    r12, r12; jumptable 000000018000661E case 8
0x180006623  jnz     loc_1800061E4; jumptable 000000018000661E cases 2,3,16-19
0x180006629  jmp     def_18000661E; jumptable 000000018000661E default case, cases 4-7,9-15
0x18000662e  mov     edi, 80070490h
0x180006633  jmp     loc_18000626A
0x180006638  mov     edx, [rbx+4Ch]; jumptable 00000001800062F2 case 9
0x18000663b  mov     r14d, r13d
0x18000663e  test    edx, edx
0x180006640  jz      def_1800062F2; jumptable 00000001800062F2 default case, cases 4-7,10-15,17
0x180006646  mov     r13d, 9
0x18000664c  mov     eax, r14d
0x18000664f  lea     rcx, [rax+rax*2]
0x180006653  mov     rax, [rbp+170h+ppvData]
0x180006657  cmp     r13w, [rax+rcx*8]
0x18000665c  jnz     short loc_18000666D
0x18000665e  mov     rax, [rax+rcx*8+8]
0x180006663  cmp     [rsi+8], rax
0x180006667  jz      loc_18000673D
0x18000666d  inc     r14d
0x180006670  cmp     r14d, edx
0x180006673  jb      short loc_18000664C
0x180006675  jmp     loc_18000673D
0x18000667a  mov     r14d, r13d; jumptable 00000001800062F2 case 8
0x18000667d  mov     r13d, 9
0x180006683  cmp     r14d, [rbx+4Ch]
0x180006687  jnb     loc_18000673D
0x18000668d  mov     eax, r14d
0x180006690  lea     rcx, [rax+rax*2]
0x180006694  mov     rax, [rbp+170h+ppvData]
0x180006698  lea     rcx, ds:0[rcx*8]
0x1800066a0  mov     [rsp+270h+var_200], rcx
0x1800066a5  cmp     r13w, [rcx+rax]
0x1800066aa  jnz     loc_1800065C3
0x1800066b0  mov     rcx, [rbp+170h+var_1F0]
0x1800066b4  test    rcx, rcx
0x1800066b7  jz      short loc_1800066CD
0x1800066b9  mov     rax, [rcx]
0x1800066bc  mov     rax, [rax+10h]
0x1800066c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066c5  mov     [rbp+170h+var_1F0], 0
0x1800066cd  mov     rax, [rbp+170h+ppvData]
0x1800066d1  lea     r8, [rbp+170h+var_1F0]
0x1800066d5  mov     rcx, [rsp+270h+var_200]
0x1800066da  lea     rdx, _GUID_03837512_098b_11d8_9414_505054503030
0x1800066e1  mov     rcx, [rcx+rax+8]
0x1800066e6  mov     rax, [rcx]
0x1800066e9  mov     rax, [rax]
0x1800066ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066f1  mov     edi, eax
0x1800066f3  test    eax, eax
0x1800066f5  js      loc_1800065C3
0x1800066fb  mov     rcx, [rbp+170h+bstrString]; bstrString
0x1800066ff  call    ?PlaiFreeString@@YAJPEAG@Z; PlaiFreeString(ushort *)
0x180006704  mov     rcx, [rbp+170h+var_1F0]
0x180006708  lea     rdx, [rbp+170h+bstrString]
0x18000670c  mov     rax, r12
0x18000670f  mov     [rbp+170h+bstrString], 0
0x180006717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000671c  mov     edi, eax
0x18000671e  test    eax, eax
0x180006720  js      loc_1800065C3
0x180006726  jmp     loc_1800065FD
0x18000672b  mov     rdx, [rsi+8]; String2
0x18000672f  call    cs:__imp__wcsicmp
0x180006735  test    eax, eax
  ... truncated ...
```
