# DiagnosePNRPFailure(CRATicket *,ulong,HWND__ *)

- ea: `0x1400300d0`
- end: `0x140030298`
- name: `?DiagnosePNRPFailure@@YAJPEAVCRATicket@@KPEAUHWND__@@@Z`
- size: `456`
- prototype: `__int64 __fastcall(struct CRATicket *this, int, HWND)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400194c8`

## callees

- `0x140002463`
- `0x1400187cc`
- `0x1400300d0`
- `0x140034ce4`
- `0x14003fab8`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140030276`
- `OLEAUT32!__imp_SysFreeString` at `0x140030276`
- `NDFAPI!NdfCloseIncident` at `0x140030244`
- `NDFAPI!NdfCloseIncident` at `0x140030244`
- `NDFAPI!NdfExecuteDiagnosis` at `0x140030215`
- `NDFAPI!NdfExecuteDiagnosis` at `0x140030215`
- `NDFAPI!NdfCreateIncident` at `0x1400301cf`
- `NDFAPI!NdfCreateIncident` at `0x1400301cf`

## pseudocode

```c
__int64 __fastcall DiagnosePNRPFailure(struct CRATicket *this, int a2, HWND a3)
{
  OLECHAR *v5; // rbx
  int PNRPAddress; // eax
  ULONG v7; // edx
  const wchar_t *v8; // rax
  HRESULT v9; // eax
  CEventLogger *v10; // rcx
  unsigned int v11; // edi
  HRESULT v12; // eax
  HRESULT v13; // eax
  int v15; // [rsp+20h] [rbp-E0h]
  HELPER_ATTRIBUTE attributes; // [rsp+30h] [rbp-D0h] BYREF
  const wchar_t *v17; // [rsp+C0h] [rbp-40h]
  int v18; // [rsp+C8h] [rbp-38h]
  BSTR v19; // [rsp+D0h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]
  BSTR bstrString; // [rsp+170h] [rbp+70h] BYREF
  NDFHANDLE handle; // [rsp+180h] [rbp+80h] BYREF

  handle = 0;
  attributes.pwszName = 0;
  memset_0(&attributes.type, 0, 0x118u);
  v5 = 0;
  bstrString = 0;
  if ( !this )
    goto LABEL_9;
  PNRPAddress = CRATicket::get_PNRPAddress(this, &bstrString);
  if ( PNRPAddress < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2FE,
      (unsigned int)"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
      (const char *)(unsigned int)PNRPAddress,
      v15);
  v5 = bstrString;
  if ( bstrString )
  {
    attributes.type = AT_UINT32;
    attributes.pwszName = L"DiagnosisType";
    v7 = 2;
    v18 = 10;
    v19 = bstrString;
    if ( a2 == 6 )
    {
      attributes.Boolean = 6;
      v8 = L"PNRPAddressList";
    }
    else
    {
      attributes.Boolean = 5;
      v8 = L"PNRPAddress";
    }
    v17 = v8;
  }
  else
  {
LABEL_9:
    attributes.type = AT_UINT32;
    attributes.pwszName = L"DiagnosisType";
    v7 = 1;
    attributes.Boolean = 4;
  }
  v9 = NdfCreateIncident(L"RAHelperClass", v7, &attributes, &handle);
  v11 = v9;
  if ( v9 >= 0 )
  {
    v12 = NdfExecuteDiagnosis(handle, 0);
    if ( v12 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x345,
        (unsigned int)"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
        (const char *)(unsigned int)v12,
        v15);
    v13 = NdfCloseIncident(handle);
    v11 = v13;
    if ( v13 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x349,
        (unsigned int)"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
        (const char *)(unsigned int)v13,
        v15);
  }
  else
  {
    CEventLogger::LogError(
      v10,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
      0x33Au,
      L"DiagnosePNRPFailure",
      v9);
  }
  if ( v5 )
    SysFreeString(v5);
  return v11;
}

```

## disassembly

```asm
0x1400300d0  mov     [rsp-8+arg_8], rbx
0x1400300d5  mov     [rsp-8+handle], r8
0x1400300da  push    rbp
0x1400300db  push    rsi
0x1400300dc  push    rdi
0x1400300dd  lea     rbp, [rsp-50h]
0x1400300e2  sub     rsp, 150h
0x1400300e9  mov     esi, edx
0x1400300eb  mov     [rbp+60h+handle], 0
0x1400300f6  mov     rdi, rcx
0x1400300f9  mov     [rsp+160h+attributes.pwszName], 0
0x140030102  xor     edx, edx; Val
0x140030104  lea     rcx, [rsp+160h+attributes.type]; void *
0x140030109  mov     r8d, 118h; Size
0x14003010f  call    memset_0
0x140030114  xor     ebx, ebx
0x140030116  mov     [rbp+60h+bstrString], rbx
0x14003011a  test    rdi, rdi
0x14003011d  jz      short loc_14003019B
0x14003011f  lea     rdx, [rbp+60h+bstrString]; unsigned __int16 **
0x140030123  mov     rcx, rdi; this
0x140030126  call    ?get_PNRPAddress@CRATicket@@QEAAJPEAPEAG@Z; CRATicket::get_PNRPAddress(ushort * *)
0x14003012b  test    eax, eax
0x14003012d  jns     short loc_140030147
0x14003012f  mov     rcx, [rbp+68h]; this
0x140030133  lea     r8, aBaseDiagnosisR_22; "base\\diagnosis\\ra\\ui\\radiagutils.cp"...
0x14003013a  mov     r9d, eax; char *
0x14003013d  mov     edx, 2FEh; void *
0x140030142  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140030147  mov     rbx, [rbp+60h+bstrString]
0x14003014b  test    rbx, rbx
0x14003014e  jz      short loc_14003019B
0x140030150  mov     [rsp+160h+attributes.type], 7
0x140030158  lea     rax, aDiagnosistype; "DiagnosisType"
0x14003015f  mov     [rsp+160h+attributes.pwszName], rax
0x140030164  mov     edx, 2
0x140030169  mov     [rbp+60h+var_98], 0Ah
0x140030170  mov     [rbp+60h+var_90], rbx
0x140030174  cmp     esi, 6
0x140030177  jnz     short loc_140030186
0x140030179  mov     dword ptr [rsp+160h+attributes.10h], esi
0x14003017d  lea     rax, aPnrpaddresslis; "PNRPAddressList"
0x140030184  jmp     short loc_140030195
0x140030186  mov     dword ptr [rsp+160h+attributes.10h], 5
0x14003018e  lea     rax, aPnrpaddress; "PNRPAddress"
0x140030195  mov     [rbp+60h+var_A0], rax
0x140030199  jmp     short loc_1400301BC
0x14003019b  lea     rax, aDiagnosistype; "DiagnosisType"
0x1400301a2  mov     [rsp+160h+attributes.type], 7
0x1400301aa  mov     [rsp+160h+attributes.pwszName], rax
0x1400301af  mov     edx, 1; celt
0x1400301b4  mov     dword ptr [rsp+160h+attributes.10h], 4
0x1400301bc  lea     r9, [rbp+60h+handle]; handle
0x1400301c3  lea     r8, [rsp+160h+attributes]; attributes
0x1400301c8  lea     rcx, helperClassName; "RAHelperClass"
0x1400301cf  call    cs:__imp_NdfCreateIncident
0x1400301d6  nop     dword ptr [rax+rax+00h]
0x1400301db  mov     edi, eax
0x1400301dd  test    eax, eax
0x1400301df  jns     short loc_14003020C
0x1400301e1  mov     [rsp+160h+var_138], eax; unsigned int
0x1400301e5  lea     r8, aBaseDiagnosisR_28; "base\\diagnosis\\ra\\ui\\radiagutils.cp"...
0x1400301ec  lea     rax, aDiagnosepnrpfa; "DiagnosePNRPFailure"
0x1400301f3  mov     r9d, 33Ah; unsigned int
0x1400301f9  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140030200  mov     [rsp+160h+var_140], rax; unsigned __int16 *
0x140030205  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14003020a  jmp     short loc_14003026E
0x14003020c  mov     rcx, [rbp+60h+handle]; handle
0x140030213  xor     edx, edx; hwnd
0x140030215  call    cs:__imp_NdfExecuteDiagnosis
0x14003021c  nop     dword ptr [rax+rax+00h]
0x140030221  test    eax, eax
0x140030223  jns     short loc_14003023D
0x140030225  mov     rcx, [rbp+68h]; this
0x140030229  lea     r8, aBaseDiagnosisR_22; "base\\diagnosis\\ra\\ui\\radiagutils.cp"...
0x140030230  mov     r9d, eax; char *
0x140030233  mov     edx, 345h; void *
0x140030238  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14003023d  mov     rcx, [rbp+60h+handle]; handle
0x140030244  call    cs:__imp_NdfCloseIncident
0x14003024b  nop     dword ptr [rax+rax+00h]
0x140030250  mov     edi, eax
0x140030252  test    eax, eax
0x140030254  jns     short loc_14003026E
0x140030256  mov     rcx, [rbp+68h]; this
0x14003025a  lea     r8, aBaseDiagnosisR_22; "base\\diagnosis\\ra\\ui\\radiagutils.cp"...
0x140030261  mov     r9d, eax; char *
0x140030264  mov     edx, 349h; void *
0x140030269  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14003026e  test    rbx, rbx
0x140030271  jz      short loc_140030282
0x140030273  mov     rcx, rbx; bstrString
0x140030276  call    cs:__imp_SysFreeString
0x14003027d  nop     dword ptr [rax+rax+00h]
0x140030282  mov     rbx, [rsp+160h+arg_8]
0x14003028a  mov     eax, edi
0x14003028c  add     rsp, 150h
0x140030293  pop     rdi
0x140030294  pop     rsi
0x140030295  pop     rbp
0x140030296  retn
```
