# Enumerator::GetIndex<IDataCollector>(tagVARIANT,long (IDataCollector::*)(ushort * *),ulong *)

- ea: `0x1800281c0`
- end: `0x1800287ce`
- name: `??$GetIndex@UIDataCollector@@@Enumerator@@IEAAJUtagVARIANT@@P8IDataCollector@@EAAJPEAPEAG@ZPEAK@Z`
- size: `1550`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180027b80`
- `0x1801222bc`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800198b0`
- `0x1800281c0`
- `0x180122624`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002863c`
- `msvcrt!_wcsicmp` at `0x18002863c`
- `OLEAUT32!__imp_SysFreeString` at `0x18002844a`
- `OLEAUT32!__imp_SysFreeString` at `0x18002844a`
- `OLEAUT32!__imp_VariantChangeType` at `0x180028271`
- `OLEAUT32!__imp_VariantChangeType` at `0x180028271`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180028246`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180028246`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800282a9`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800282a9`

## pseudocode

```c
__int64 __fastcall Enumerator::GetIndex<IDataCollector>(__int64 a1, VARIANTARG *a2, __int64 a3, unsigned int *a4)
{
  int vt; // eax
  __int64 v7; // r8
  SAFEARRAY *v9; // rcx
  unsigned int i; // r14d
  HRESULT v11; // eax
  unsigned __int64 v12; // rdx
  int v13; // ebx
  HRESULT v14; // eax
  unsigned __int64 v15; // rdx
  OLECHAR *v16; // rdi
  __int64 v18; // rax
  bool v19; // zf
  __int64 v20; // rax
  __int64 v21; // rax
  unsigned int v22; // edx
  __int64 v23; // r12
  __int64 v24; // [rsp+78h] [rbp-90h] BYREF
  BSTR v25; // [rsp+80h] [rbp-88h] BYREF
  __int64 v26; // [rsp+88h] [rbp-80h] BYREF
  void *ppvData; // [rsp+90h] [rbp-78h] BYREF
  BSTR bstrString[2]; // [rsp+98h] [rbp-70h] BYREF
  unsigned __int16 v29[64]; // [rsp+A8h] [rbp-60h] BYREF
  unsigned __int16 v30[64]; // [rsp+128h] [rbp+20h] BYREF
  unsigned __int16 v31[64]; // [rsp+1A8h] [rbp+A0h] BYREF

  vt = a2->vt;
  v7 = 0;
  bstrString[0] = 0;
  ppvData = 0;
  v26 = 0;
  if ( vt != 9 )
  {
    switch ( vt )
    {
      case 2:
      case 3:
      case 8:
      case 16:
      case 17:
      case 18:
      case 19:
        goto LABEL_2;
      default:
        v13 = -2147024809;
        LODWORD(v24) = -2147024809;
        LODWORD(v25) = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_12;
        }
        PlaiWhoAmI(v29, (unsigned __int64)a2);
        v18 = -1;
        do
          v19 = v29[++v18] == 0;
        while ( !v19 );
        EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v24, 4, byte_180147320, 1, &v25, 4);
        break;
    }
    goto LABEL_9;
  }
LABEL_2:
  v9 = *(SAFEARRAY **)(a1 + 64);
  if ( !v9 )
  {
    v13 = -2147023728;
    goto LABEL_12;
  }
  i = *(_DWORD *)(a1 + 76);
  v11 = SafeArrayAccessData(v9, &ppvData);
  v13 = v11;
  if ( v11 < 0 )
  {
    LODWORD(v24) = 0;
    LODWORD(v25) = v11;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_9;
    }
    PlaiWhoAmI(v30, v12);
    v21 = -1;
    do
      v19 = v30[++v21] == 0;
    while ( !v19 );
LABEL_38:
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v25, 4, byte_180147320, 1, &v24, 4);
    goto LABEL_9;
  }
  if ( a2->vt != 17 )
  {
    switch ( a2->vt )
    {
      case 2u:
      case 3u:
      case 0x10u:
      case 0x12u:
      case 0x13u:
        goto LABEL_5;
      case 8u:
        i = 0;
        break;
      case 9u:
        v22 = *(_DWORD *)(a1 + 76);
        for ( i = 0; i < v22; ++i )
        {
          if ( *((_WORD *)ppvData + 12 * i) == 9 && a2->llVal == *((_QWORD *)ppvData + 3 * i + 1) )
            break;
        }
        goto LABEL_7;
      default:
        goto LABEL_7;
    }
    while ( i < *(_DWORD *)(a1 + 76) )
    {
      v23 = 24LL * i;
      if ( *(_WORD *)((char *)ppvData + v23) == 9 )
      {
        if ( v26 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
          v26 = 0;
        }
        if ( (***(int (__fastcall ****)(_QWORD, GUID *, __int64 *))((char *)ppvData + v23 + 8))(
               *(_QWORD *)((char *)ppvData + v23 + 8),
               &GUID_038374ff_098b_11d8_9414_505054503030,
               &v26) >= 0 )
        {
          PlaiFreeString(bstrString[0]);
          bstrString[0] = 0;
          v13 =  IDataCollector::`vcall'{192,{flat}}(v26, bstrString);
          if ( v13 >= 0 && bstrString[0] && *bstrString[0] && !_wcsicmp(bstrString[0], a2->bstrVal) )
            goto LABEL_7;
        }
      }
      ++i;
    }
    goto LABEL_60;
  }
LABEL_5:
  v14 = VariantChangeType(a2, a2, 0, 0x13u);
  v13 = v14;
  if ( v14 < 0 )
  {
    LODWORD(v24) = 0;
    LODWORD(v25) = v14;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_9;
    }
    PlaiWhoAmI(v31, v15);
    v20 = -1;
    do
      v19 = v31[++v20] == 0;
    while ( !v19 );
    goto LABEL_38;
  }
  i = a2->cyVal.Lo;
LABEL_7:
  if ( i >= *(_DWORD *)(a1 + 76) )
  {
LABEL_60:
    v13 = -2147023728;
    goto LABEL_9;
  }
  *a4 = i;
LABEL_9:
  if ( ppvData )
  {
    SafeArrayUnaccessData(*(SAFEARRAY **)(a1 + 64));
    ppvData = 0;
  }
  v7 = v26;
LABEL_12:
  v16 = bstrString[0];
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
    SysFreeString(v16);
    v7 = v26;
  }
  bstrString[0] = 0;
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800281c0  mov     r11, rsp
0x1800281c3  push    rbp
0x1800281c4  push    rbx
0x1800281c5  lea     rbp, [r11-168h]
0x1800281cc  sub     rsp, 258h
0x1800281d3  mov     rax, cs:__security_cookie
0x1800281da  xor     rax, rsp
0x1800281dd  mov     [rbp+160h+var_40], rax
0x1800281e4  movzx   eax, word ptr [rdx]
0x1800281e7  mov     [r11+18h], rsi
0x1800281eb  mov     rsi, rcx
0x1800281ee  mov     [r11-18h], rdi
0x1800281f2  mov     rdi, rdx
0x1800281f5  mov     [r11-20h], r12
0x1800281f9  xor     r12d, r12d
0x1800281fc  mov     [r11-28h], r13
0x180028200  mov     r8d, r12d
0x180028203  mov     [r11-30h], r14
0x180028207  lea     r14, byte_180147320
0x18002820e  mov     [r11-38h], r15
0x180028212  mov     r15, r9
0x180028215  mov     [rbp+160h+bstrString], r12
0x180028219  lea     r13, __ImageBase
0x180028220  mov     [rbp+160h+ppvData], r12
0x180028224  mov     [rbp+160h+var_1E0], r12
0x180028228  cmp     eax, 9
0x18002822b  jnz     loc_18002831C
0x180028231  mov     rcx, [rsi+40h]; jumptable 0000000180028665 cases 2,3,8,16-19
0x180028235  test    rcx, rcx
0x180028238  jz      loc_180028413
0x18002823e  mov     r14d, [rsi+4Ch]
0x180028242  lea     rdx, [rbp+160h+ppvData]; ppvData
0x180028246  call    cs:__imp_SafeArrayAccessData
0x18002824c  mov     ebx, eax
0x18002824e  test    eax, eax
0x180028250  js      loc_1800284D8
0x180028256  movzx   eax, word ptr [rdi]
0x180028259  cmp     eax, 11h
0x18002825c  jnz     loc_180028667
0x180028262  mov     r9d, 13h; jumptable 0000000180028689 cases 2,3,16,18,19
0x180028268  xor     r8d, r8d; wFlags
0x18002826b  mov     rdx, rdi; pvarSrc
0x18002826e  mov     rcx, rdi; pvargDest
0x180028271  call    cs:__imp_VariantChangeType
0x180028277  mov     ebx, eax
0x180028279  test    eax, eax
0x18002827b  js      loc_180028459
0x180028281  mov     r14d, [rdi+8]
0x180028285  cmp     r14d, [rsi+4Ch]; jumptable 0000000180028689 default case, cases 4-7,10-15,17
0x180028289  jnb     loc_18002876F
0x18002828f  mov     [r15], r14d
0x180028292  lea     r14, byte_180147320
0x180028299  mov     ecx, 40h ; '@'
0x18002829e  cmp     [rbp+160h+ppvData], 0
0x1800282a3  jz      short loc_1800282B3
0x1800282a5  mov     rcx, [rsi+rcx]; psa
0x1800282a9  call    cs:__imp_SafeArrayUnaccessData
0x1800282af  mov     [rbp+160h+ppvData], r12
0x1800282b3  mov     r8, [rbp+160h+var_1E0]
0x1800282b7  mov     rdi, [rbp+160h+bstrString]
0x1800282bb  mov     r15, [rsp+260h+var_30]
0x1800282c3  mov     r13, [rsp+260h+var_20]
0x1800282cb  mov     rsi, [rsp+260h+arg_10]
0x1800282d3  test    rdi, rdi
0x1800282d6  jnz     loc_18002841D
0x1800282dc  mov     r14, [rsp+260h+var_28]
0x1800282e4  mov     rdi, [rsp+250h]
0x1800282ec  mov     [rbp+160h+bstrString], r12
0x1800282f0  mov     r12, [rsp+260h+var_18]
0x1800282f8  test    r8, r8
0x1800282fb  jnz     loc_180028779
0x180028301  mov     eax, ebx
0x180028303  mov     rcx, [rbp+160h+var_40]
0x18002830a  xor     rcx, rsp; StackCookie
0x18002830d  call    __security_check_cookie
0x180028312  add     rsp, 258h
0x180028319  pop     rbx
0x18002831a  pop     rbp
0x18002831b  retn
0x18002831c  add     eax, 0FFFFFFFEh; switch 18 cases
0x18002831f  cmp     eax, 11h
0x180028322  jbe     loc_18002864F
0x180028328  cmp     dword ptr cs:xmmword_180169738, r8d; jumptable 0000000180028665 default case, cases 4-7,9-15
0x18002832f  mov     ebx, 80070057h
0x180028334  mov     dword ptr [rsp+260h+var_1F0], ebx
0x180028338  mov     dword ptr [rsp+260h+var_1E8], r12d
0x18002833d  jz      loc_1800282B7
0x180028343  mov     rcx, 4000000000000800h
0x18002834d  test    qword ptr cs:xmmword_180169738+8, rcx
0x180028354  jz      loc_1800282B7
0x18002835a  mov     rax, cs:qword_180169748
0x180028361  and     rax, rcx
0x180028364  cmp     cs:qword_180169748, rax
0x18002836b  jnz     loc_1800282B7
0x180028371  lea     rcx, [rbp+160h+var_1C0]; unsigned __int16 *
0x180028375  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002837a  lea     rcx, [rbp+160h+var_1C0]
0x18002837e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180028385  nop     word ptr [rax+rax+00000000h]
0x180028390  cmp     [rcx+rax*2+2], r12w
0x180028396  lea     rax, [rax+1]
0x18002839a  jnz     short loc_180028390
0x18002839c  lea     ecx, [rax+rax]
0x18002839f  mov     r8d, 5
0x1800283a5  add     rcx, 2
0x1800283a9  lea     rax, [rbp+160h+var_1C0]
0x1800283ad  mov     [rsp+60h], rcx
0x1800283b2  lea     r9, [rsp+260h+var_1F0]
0x1800283b7  mov     [rsp+260h+var_208], rax
0x1800283bc  lea     rdx, PLA_EVENT_ERROR
0x1800283c3  mov     [rsp+260h+var_210], 15h
0x1800283cc  lea     rax, aEnumeratorGeti_0; "Enumerator::GetIndex"
0x1800283d3  mov     [rsp+260h+var_218], rax
0x1800283d8  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800283df  mov     [rsp+260h+var_220], 4
0x1800283e8  lea     rax, [rsp+260h+var_1E8]
0x1800283ed  mov     [rsp+260h+var_228], rax
0x1800283f2  mov     [rsp+260h+var_230], 1
0x1800283fb  mov     [rsp+260h+var_238], r14
0x180028400  mov     [rsp+260h+var_240], 4
0x180028409  call    EventingWriteEvent
0x18002840e  jmp     loc_180028299
0x180028413  mov     ebx, 80070490h
0x180028418  jmp     loc_1800282B7
0x18002841d  cmp     dword ptr cs:xmmword_180169738, 0
0x180028424  mov     [rsp+260h+var_1E8], rdi
0x180028429  mov     dword ptr [rsp+260h+var_1F0], r12d
0x18002842e  jz      short loc_180028447
0x180028430  mov     rcx, 4000000000000200h
0x18002843a  test    qword ptr cs:xmmword_180169738+8, rcx
0x180028441  jnz     loc_1800285BA
0x180028447  mov     rcx, rdi; bstrString
0x18002844a  call    cs:__imp_SysFreeString
0x180028450  mov     r8, [rbp+160h+var_1E0]
0x180028454  jmp     loc_1800282DC
0x180028459  cmp     dword ptr cs:xmmword_180169738, r12d
0x180028460  mov     dword ptr [rsp+260h+var_1F0], r12d
0x180028465  mov     dword ptr [rsp+260h+var_1E8], eax
0x180028469  jz      loc_180028292
0x18002846f  mov     rcx, 4000000000000800h
0x180028479  test    qword ptr cs:xmmword_180169738+8, rcx
0x180028480  jz      loc_180028292
0x180028486  mov     rax, cs:qword_180169748
0x18002848d  and     rax, rcx
0x180028490  cmp     cs:qword_180169748, rax
0x180028497  jnz     loc_180028292
0x18002849d  lea     rcx, [rbp+160h+var_C0]; unsigned __int16 *
0x1800284a4  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800284a9  lea     rcx, [rbp+160h+var_C0]
0x1800284b0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800284b7  nop     word ptr [rax+rax+00000000h]
0x1800284c0  cmp     [rcx+rax*2+2], r12w
0x1800284c6  lea     rax, [rax+1]
0x1800284ca  jnz     short loc_1800284C0
0x1800284cc  lea     ecx, [rax+rax]
0x1800284cf  lea     rax, [rbp+160h+var_C0]
0x1800284d6  jmp     short loc_180028543
0x1800284d8  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800284df  mov     dword ptr [rsp+260h+var_1F0], r12d
0x1800284e4  mov     dword ptr [rsp+260h+var_1E8], eax
0x1800284e8  jz      loc_180028292
0x1800284ee  mov     rcx, 4000000000000800h
0x1800284f8  test    qword ptr cs:xmmword_180169738+8, rcx
0x1800284ff  jz      loc_180028292
0x180028505  mov     rax, cs:qword_180169748
0x18002850c  and     rax, rcx
0x18002850f  cmp     cs:qword_180169748, rax
0x180028516  jnz     loc_180028292
0x18002851c  lea     rcx, [rbp+160h+var_140]; unsigned __int16 *
0x180028520  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180028525  lea     rcx, [rbp+160h+var_140]
0x180028529  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180028530  cmp     [rcx+rax*2+2], r12w
0x180028536  lea     rax, [rax+1]
0x18002853a  jnz     short loc_180028530
0x18002853c  lea     ecx, [rax+rax]
0x18002853f  lea     rax, [rbp+160h+var_140]
0x180028543  add     rcx, 2
0x180028547  lea     r14, byte_180147320
0x18002854e  mov     [rsp+60h], rcx
0x180028553  lea     r9, [rsp+260h+var_1E8]
0x180028558  mov     [rsp+260h+var_208], rax
0x18002855d  lea     rdx, PLA_EVENT_ERROR
0x180028564  mov     [rsp+260h+var_210], 15h
0x18002856d  lea     rax, aEnumeratorGeti_0; "Enumerator::GetIndex"
0x180028574  mov     [rsp+260h+var_218], rax
0x180028579  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180028580  mov     [rsp+260h+var_220], 4
0x180028589  lea     rax, [rsp+260h+var_1F0]
0x18002858e  mov     [rsp+260h+var_228], rax
0x180028593  mov     r8d, 5
0x180028599  mov     [rsp+260h+var_230], 1
0x1800285a2  mov     [rsp+260h+var_238], r14
0x1800285a7  mov     [rsp+260h+var_240], 4
0x1800285b0  call    EventingWriteEvent
0x1800285b5  jmp     loc_180028299
0x1800285ba  mov     rax, cs:qword_180169748
0x1800285c1  and     rax, rcx
0x1800285c4  cmp     cs:qword_180169748, rax
0x1800285cb  jnz     loc_180028447
0x1800285d1  mov     [rsp+260h+var_220], 8
0x1800285da  lea     rax, [rsp+260h+var_1E8]
0x1800285df  mov     [rsp+260h+var_228], rax
0x1800285e4  lea     rdx, PLA_EVENT_FREE_STRING
0x1800285eb  lea     rax, [rsp+260h+var_1F0]
0x1800285f0  mov     [rsp+260h+var_230], 4
0x1800285f9  mov     [rsp+260h+var_238], rax
0x1800285fe  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180028605  mov     r9, r14
0x180028608  mov     [rsp+260h+var_240], 1
0x180028611  mov     r8d, 3
0x180028617  call    EventingWriteEvent
0x18002861c  jmp     loc_180028447
0x180028621  mov     rcx, [rbp+160h+bstrString]; String1
0x180028625  test    rcx, rcx
0x180028628  jz      loc_180028767
0x18002862e  cmp     r12w, [rcx]
0x180028632  jz      loc_180028767
0x180028638  mov     rdx, [rdi+8]; String2
0x18002863c  call    cs:__imp__wcsicmp
0x180028642  test    eax, eax
0x180028644  jz      def_180028689; jumptable 0000000180028689 default case, cases 4-7,10-15,17
0x18002864a  jmp     loc_180028767
0x18002864f  cdqe
0x180028651  movzx   eax, ds:(byte_180028798 - 180000000h)[rax+r13]
0x18002865a  mov     ecx, ds:(jpt_180028665 - 180000000h)[r13+rax*4]
0x180028662  add     rcx, r13
0x180028665  jmp     rcx; switch jump
0x180028667  add     eax, 0FFFFFFFEh; switch 18 cases
0x18002866a  cmp     eax, 11h
0x18002866d  ja      def_180028689; jumptable 0000000180028689 default case, cases 4-7,10-15,17
0x180028673  cdqe
0x180028675  movzx   eax, ds:(byte_1800287BC - 180000000h)[rax+r13]
0x18002867e  mov     ecx, ds:(jpt_180028689 - 180000000h)[r13+rax*4]
0x180028686  add     rcx, r13
0x180028689  jmp     rcx; switch jump
0x18002868b  mov     edx, [rsi+4Ch]; jumptable 0000000180028689 case 9
0x18002868e  mov     r14d, r12d
0x180028691  test    edx, edx
0x180028693  jz      def_180028689; jumptable 0000000180028689 default case, cases 4-7,10-15,17
0x180028699  mov     r13d, 9
0x18002869f  mov     eax, r14d
0x1800286a2  lea     rcx, [rax+rax*2]
0x1800286a6  mov     rax, [rbp+160h+ppvData]
0x1800286aa  cmp     r13w, [rax+rcx*8]
0x1800286af  jnz     short loc_1800286C0
0x1800286b1  mov     rax, [rax+rcx*8+8]
0x1800286b6  cmp     [rdi+8], rax
0x1800286ba  jz      def_180028689; jumptable 0000000180028689 default case, cases 4-7,10-15,17
0x1800286c0  inc     r14d
0x1800286c3  cmp     r14d, edx
0x1800286c6  jb      short loc_18002869F
0x1800286c8  jmp     def_180028689; jumptable 0000000180028689 default case, cases 4-7,10-15,17
0x1800286cd  mov     r14d, r12d; jumptable 0000000180028689 case 8
0x1800286d0  mov     r13d, 9
0x1800286d6  cmp     r14d, [rsi+4Ch]
0x1800286da  jnb     loc_18002876F
0x1800286e0  mov     eax, r14d
0x1800286e3  lea     rcx, [rax+rax*2]
0x1800286e7  mov     rax, [rbp+160h+ppvData]
0x1800286eb  lea     r12, ds:0[rcx*8]
0x1800286f3  cmp     r13w, [r12+rax]
0x1800286f8  jnz     short loc_180028764
0x1800286fa  mov     rcx, [rbp+160h+var_1E0]
0x1800286fe  test    rcx, rcx
0x180028701  jz      short loc_180028717
0x180028703  mov     rax, [rcx]
0x180028706  mov     rax, [rax+10h]
0x18002870a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002870f  mov     [rbp+160h+var_1E0], 0
0x180028717  mov     rax, [rbp+160h+ppvData]
0x18002871b  lea     r8, [rbp+160h+var_1E0]
0x18002871f  lea     rdx, _GUID_038374ff_098b_11d8_9414_505054503030
0x180028726  mov     rcx, [r12+rax+8]
0x18002872b  mov     rax, [rcx]
0x18002872e  mov     rax, [rax]
0x180028731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028736  mov     ebx, eax
0x180028738  test    eax, eax
0x18002873a  js      short loc_180028764
0x18002873c  mov     rcx, [rbp+160h+bstrString]; bstrString
0x180028740  call    ?PlaiFreeString@@YAJPEAG@Z; PlaiFreeString(ushort *)
0x180028745  mov     rcx, [rbp+160h+var_1E0]
0x180028749  lea     rdx, [rbp+160h+bstrString]
0x18002874d  xor     r12d, r12d
0x180028750  mov     [rbp+160h+bstrString], r12
0x180028754  call    ??_9IDataCollector@@$BMA@AA; [thunk]: IDataCollector::`vcall'{192,{flat}}
0x180028759  mov     ebx, eax
0x18002875b  test    eax, eax
0x18002875d  js      short loc_180028767
0x18002875f  jmp     loc_180028621
0x180028764  xor     r12d, r12d
0x180028767  inc     r14d
0x18002876a  jmp     loc_1800286D6
0x18002876f  mov     ebx, 80070490h
0x180028774  jmp     loc_180028292
0x180028779  mov     rax, [r8]
0x18002877c  mov     rcx, r8
0x18002877f  mov     rax, [rax+10h]
0x180028783  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
