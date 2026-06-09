# TraceDataProvider::put_FilterData(tagSAFEARRAY *)

- ea: `0x180100440`
- end: `0x18010078a`
- name: `?put_FilterData@TraceDataProvider@@UEAAJPEAUtagSAFEARRAY@@@Z`
- size: `842`
- prototype: `int(TraceDataProvider *__hidden this, struct tagSAFEARRAY *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18006e574`
- `0x180100440`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180100757`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180100757`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18010050e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18010050e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1801006bf`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1801006d4`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1801006bf`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1801006d4`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18010060b`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18010060b`

## pseudocode

```c
__int64 __fastcall TraceDataProvider::put_FilterData(TraceDataProvider *this, struct tagSAFEARRAY *a2)
{
  HRESULT v4; // ebx
  int v5; // eax
  __int64 v6; // rax
  int *v7; // r9
  HRESULT v8; // eax
  __int64 v9; // rax
  SAFEARRAY *v10; // rcx
  __int64 v11; // rax
  HRESULT v13; // [rsp+70h] [rbp-90h] BYREF
  int v14; // [rsp+78h] [rbp-88h] BYREF
  SAFEARRAY *ppsaOut; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v16[64]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v17[64]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v18[64]; // [rsp+190h] [rbp+90h] BYREF

  v13 = *((_DWORD *)this + 14);
  v4 = 0;
  ppsaOut = (SAFEARRAY *)this;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent((__int64)&g_Eventing, (__int64)PLA_EVENT_METHOD, 3, (__int64)"TraceDataProvider::put_FilterData");
  }
  if ( *((_DWORD *)this + 2) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  ppsaOut = 0;
  if ( a2 )
  {
    v5 = PlaiValidateSafeArray(a2);
    v4 = v5;
    if ( v5 < 0 )
    {
      v13 = 0;
      v14 = v5;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v16, 0x4000000000000800uLL);
        v6 = -1;
        do
          ++v6;
        while ( v16[v6] );
        v7 = &v14;
        goto LABEL_15;
      }
      goto LABEL_34;
    }
    v8 = SafeArrayCopy(a2, &ppsaOut);
    v4 = v8;
    if ( v8 < 0 )
    {
      v14 = 0;
      v13 = v8;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_34;
      }
      PlaiWhoAmI(v17, 0x4000000000000800uLL);
      v9 = -1;
      do
        ++v9;
      while ( v17[v9] );
LABEL_22:
      v7 = &v13;
LABEL_15:
      EventingWriteEvent((__int64)&g_Eventing, (__int64)PLA_EVENT_ERROR, 5, (__int64)v7);
      goto LABEL_34;
    }
  }
  v10 = (SAFEARRAY *)*((_QWORD *)this + 16);
  if ( !v10 || (v4 = SafeArrayDestroy(v10), v4 >= 0) )
  {
    *((_QWORD *)this + 16) = ppsaOut;
    goto LABEL_34;
  }
  if ( ppsaOut )
    SafeArrayDestroy(ppsaOut);
  v14 = 0;
  v13 = v4;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v18, 0x4000000000000800uLL);
    v11 = -1;
    do
      ++v11;
    while ( v18[v11] );
    goto LABEL_22;
  }
LABEL_34:
  if ( *((_DWORD *)this + 2) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180100440  mov     [rsp-8+arg_10], rbx
0x180100445  mov     [rsp-8+arg_18], rsi
0x18010044a  push    rbp
0x18010044b  push    rdi
0x18010044c  push    r12
0x18010044e  push    r14
0x180100450  push    r15
0x180100452  lea     rbp, [rsp-120h]
0x18010045a  sub     rsp, 220h
0x180100461  mov     rax, cs:__security_cookie
0x180100468  xor     rax, rsp
0x18010046b  mov     [rbp+140h+var_30], rax
0x180100472  mov     eax, [rcx+38h]
0x180100475  xor     r14d, r14d
0x180100478  cmp     dword ptr cs:xmmword_180169738, r14d
0x18010047f  mov     rsi, rdx
0x180100482  mov     rdi, rcx
0x180100485  mov     [rsp+240h+var_1D0], eax
0x180100489  mov     ebx, r14d
0x18010048c  mov     [rbp+140h+ppsaOut], rcx
0x180100490  lea     r15d, [r14+4]
0x180100494  lea     r12d, [r14+22h]
0x180100498  jz      short loc_180100504
0x18010049a  mov     rdx, 4000000000000400h
0x1801004a4  test    qword ptr cs:xmmword_180169738+8, rdx
0x1801004ab  jz      short loc_180100504
0x1801004ad  mov     rax, cs:qword_180169748
0x1801004b4  and     rax, rdx
0x1801004b7  cmp     cs:qword_180169748, rax
0x1801004be  jnz     short loc_180100504
0x1801004c0  mov     [rsp+240h+var_200], r15
0x1801004c5  lea     rax, [rsp+240h+var_1D0]
0x1801004ca  mov     [rsp+240h+var_208], rax
0x1801004cf  lea     r9, aTracedataprovi_10; "TraceDataProvider::put_FilterData"
0x1801004d6  lea     rax, [rbp+140h+ppsaOut]
0x1801004da  mov     [rsp+240h+var_210], 8
0x1801004e3  mov     [rsp+240h+var_218], rax
0x1801004e8  lea     r8d, [r14+3]
0x1801004ec  lea     rdx, PLA_EVENT_METHOD
0x1801004f3  mov     [rsp+240h+var_220], r12
0x1801004f8  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1801004ff  call    EventingWriteEvent
0x180100504  cmp     [rdi+8], r14d
0x180100508  jz      short loc_180100514
0x18010050a  lea     rcx, [rdi+10h]; lpCriticalSection
0x18010050e  call    cs:__imp_EnterCriticalSection
0x180100514  mov     [rbp+140h+ppsaOut], r14
0x180100518  test    rsi, rsi
0x18010051b  jz      loc_1801006AF
0x180100521  mov     rcx, rsi; psa
0x180100524  call    ?PlaiValidateSafeArray@@YAJPEAUtagSAFEARRAY@@@Z; PlaiValidateSafeArray(tagSAFEARRAY *)
0x180100529  mov     ebx, eax
0x18010052b  test    eax, eax
0x18010052d  jns     loc_180100604
0x180100533  cmp     dword ptr cs:xmmword_180169738, r14d
0x18010053a  mov     [rsp+240h+var_1D0], r14d
0x18010053f  mov     [rsp+240h+var_1C8], eax
0x180100543  jz      loc_18010074D
0x180100549  mov     rdx, 4000000000000800h; unsigned __int64
0x180100553  test    qword ptr cs:xmmword_180169738+8, rdx
0x18010055a  jz      loc_18010074D
0x180100560  mov     rax, cs:qword_180169748
0x180100567  and     rax, rdx
0x18010056a  cmp     cs:qword_180169748, rax
0x180100571  jnz     loc_18010074D
0x180100577  lea     rcx, [rbp+140h+var_1B0]; unsigned __int16 *
0x18010057b  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180100580  lea     rcx, [rbp+140h+var_1B0]
0x180100584  or      rax, 0FFFFFFFFFFFFFFFFh
0x180100588  inc     rax
0x18010058b  cmp     [rcx+rax*2], r14w
0x180100590  jnz     short loc_180100588
0x180100592  lea     ecx, [rax+rax]
0x180100595  lea     rax, [rbp+140h+var_1B0]
0x180100599  add     rcx, 2
0x18010059d  mov     [rsp+240h+var_1E0], rcx
0x1801005a2  lea     r9, [rsp+240h+var_1C8]
0x1801005a7  mov     [rsp+240h+var_1E8], rax
0x1801005ac  lea     rax, aTracedataprovi_10; "TraceDataProvider::put_FilterData"
0x1801005b3  mov     [rsp+240h+var_1F0], r12
0x1801005b8  mov     [rsp+240h+var_1F8], rax
0x1801005bd  lea     rax, [rsp+240h+var_1D0]
0x1801005c2  mov     [rsp+240h+var_200], r15
0x1801005c7  lea     rdx, PLA_EVENT_ERROR
0x1801005ce  mov     [rsp+240h+var_208], rax
0x1801005d3  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1801005da  lea     rax, qword_180147320
0x1801005e1  mov     [rsp+240h+var_210], 1
0x1801005ea  mov     [rsp+240h+var_218], rax
0x1801005ef  mov     r8d, 5
0x1801005f5  mov     [rsp+240h+var_220], r15
0x1801005fa  call    EventingWriteEvent
0x1801005ff  jmp     loc_18010074D
0x180100604  lea     rdx, [rbp+140h+ppsaOut]; ppsaOut
0x180100608  mov     rcx, rsi; psa
0x18010060b  call    cs:__imp_SafeArrayCopy
0x180100611  mov     ebx, eax
0x180100613  test    eax, eax
0x180100615  jns     loc_1801006AF
0x18010061b  cmp     dword ptr cs:xmmword_180169738, r14d
0x180100622  mov     [rsp+240h+var_1C8], r14d
0x180100627  mov     [rsp+240h+var_1D0], eax
0x18010062b  jz      loc_18010074D
0x180100631  mov     rdx, 4000000000000800h; unsigned __int64
0x18010063b  test    qword ptr cs:xmmword_180169738+8, rdx
0x180100642  jz      loc_18010074D
0x180100648  mov     rax, cs:qword_180169748
0x18010064f  and     rax, rdx
0x180100652  cmp     cs:qword_180169748, rax
0x180100659  jnz     loc_18010074D
0x18010065f  lea     rcx, [rbp+140h+var_130]; unsigned __int16 *
0x180100663  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180100668  lea     rcx, [rbp+140h+var_130]
0x18010066c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180100670  inc     rax
0x180100673  cmp     [rcx+rax*2], r14w
0x180100678  jnz     short loc_180100670
0x18010067a  lea     ecx, [rax+rax]
0x18010067d  lea     rax, [rbp+140h+var_130]
0x180100681  add     rcx, 2
0x180100685  lea     r9, [rsp+240h+var_1D0]
0x18010068a  mov     [rsp+240h+var_1E0], rcx
0x18010068f  mov     [rsp+240h+var_1E8], rax
0x180100694  lea     rax, aTracedataprovi_10; "TraceDataProvider::put_FilterData"
0x18010069b  mov     [rsp+240h+var_1F0], r12
0x1801006a0  mov     [rsp+240h+var_1F8], rax
0x1801006a5  lea     rax, [rsp+240h+var_1C8]
0x1801006aa  jmp     loc_1801005C2
0x1801006af  mov     rcx, [rdi+80h]; psa
0x1801006b6  test    rcx, rcx
0x1801006b9  jz      loc_180100742
0x1801006bf  call    cs:__imp_SafeArrayDestroy
0x1801006c5  mov     ebx, eax
0x1801006c7  test    eax, eax
0x1801006c9  jns     short loc_180100742
0x1801006cb  mov     rcx, [rbp+140h+ppsaOut]; psa
0x1801006cf  test    rcx, rcx
0x1801006d2  jz      short loc_1801006DA
0x1801006d4  call    cs:__imp_SafeArrayDestroy
0x1801006da  cmp     dword ptr cs:xmmword_180169738, r14d
0x1801006e1  mov     [rsp+240h+var_1C8], r14d
0x1801006e6  mov     [rsp+240h+var_1D0], ebx
0x1801006ea  jz      short loc_18010074D
0x1801006ec  mov     rdx, 4000000000000800h; unsigned __int64
0x1801006f6  test    qword ptr cs:xmmword_180169738+8, rdx
0x1801006fd  jz      short loc_18010074D
0x1801006ff  mov     rax, cs:qword_180169748
0x180100706  and     rax, rdx
0x180100709  cmp     cs:qword_180169748, rax
0x180100710  jnz     short loc_18010074D
0x180100712  lea     rcx, [rbp+140h+var_B0]; unsigned __int16 *
0x180100719  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18010071e  lea     rcx, [rbp+140h+var_B0]
0x180100725  or      rax, 0FFFFFFFFFFFFFFFFh
0x180100729  inc     rax
0x18010072c  cmp     [rcx+rax*2], r14w
0x180100731  jnz     short loc_180100729
0x180100733  lea     ecx, [rax+rax]
0x180100736  lea     rax, [rbp+140h+var_B0]
0x18010073d  jmp     loc_180100681
0x180100742  mov     rax, [rbp+140h+ppsaOut]
0x180100746  mov     [rdi+80h], rax
0x18010074d  cmp     [rdi+8], r14d
0x180100751  jz      short loc_18010075D
0x180100753  lea     rcx, [rdi+10h]; lpCriticalSection
0x180100757  call    cs:__imp_LeaveCriticalSection
0x18010075d  mov     eax, ebx
0x18010075f  mov     rcx, [rbp+140h+var_30]
0x180100766  xor     rcx, rsp; StackCookie
0x180100769  call    __security_check_cookie
0x18010076e  lea     r11, [rsp+240h+var_20]
0x180100776  mov     rbx, [r11+40h]
0x18010077a  mov     rsi, [r11+48h]
0x18010077e  mov     rsp, r11
0x180100781  pop     r15
0x180100783  pop     r14
0x180100785  pop     r12
0x180100787  pop     rdi
0x180100788  pop     rbp
0x180100789  retn
```
