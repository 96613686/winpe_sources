# CAMCMultiDocTemplate::CloseAllDocuments(int)

- ea: `0x140069bd0`
- end: `0x140069d23`
- name: `?CloseAllDocuments@CAMCMultiDocTemplate@@UEAAXH@Z`
- size: `339`
- prototype: `void __fastcall(CAMCMultiDocTemplate *__hidden this, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000c1d0`
- `0x140066f14`
- `0x140069bd0`
- `0x1400730b8`

## import_xrefs

- `MFC42u!__imp_?CloseAllDocuments@CDocTemplate@@UEAAXH@Z` at `0x140069c37`
- `MFC42u!__imp_?CloseAllDocuments@CDocTemplate@@UEAAXH@Z` at `0x140069c37`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140069c66`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140069ca1`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140069ce4`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140069d0d`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140069c66`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140069ca1`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140069ce4`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x140069d0d`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140069c70`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140069cab`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140069cee`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140069c70`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140069cab`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140069cee`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x140069bed`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x140069bed`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x140069c5b`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x140069c96`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x140069cd9`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x140069c5b`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x140069c96`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x140069cd9`
- `mmcbase!GetComObjectEventSource` at `0x140069cbf`
- `mmcbase!GetComObjectEventSource` at `0x140069cbf`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x140069bff`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x140069bff`
- `mmcbase!?TraceAndClear@SC@mmcerror@@QEAAXXZ` at `0x140069cb9`
- `mmcbase!?TraceAndClear@SC@mmcerror@@QEAAXXZ` at `0x140069cfc`
- `mmcbase!?TraceAndClear@SC@mmcerror@@QEAAXXZ` at `0x140069cb9`
- `mmcbase!?TraceAndClear@SC@mmcerror@@QEAAXXZ` at `0x140069cfc`

## string_xrefs

- `0x140069bf4`: `CAMCMultiDocTemplate::CloseAllDocuments`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CAMCMultiDocTemplate::CloseAllDocuments(CAMCMultiDocTemplate *this, int a2)
{
  int v4; // r8d
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 ComObjectEventSource; // rax
  __int64 v8; // r8
  mmcerror::SC *v9; // rax
  _BYTE v10[24]; // [rsp+20h] [rbp-30h] BYREF
  _BYTE v11[24]; // [rsp+38h] [rbp-18h] BYREF

  mmcerror::SC::SC((mmcerror::SC *)v10, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v10, L"CAMCMultiDocTemplate::CloseAllDocuments");
  v4 = `CAMCMultiDocTemplate::CloseAllDocuments'::`2'::cInvocations++;
  if ( (unsigned int)`CAMCMultiDocTemplate::CloseAllDocuments'::`2'::cInvocations <= 1 )
  {
    CDocTemplate::CloseAllDocuments(this, a2);
    v5 = ScCheckPointers(v11, &theApp, 2147549183LL);
    mmcerror::SC::operator=(v10, v5);
    mmcerror::SC::~SC((mmcerror::SC *)v11);
    if ( !(unsigned __int8)mmcerror::SC::operator bool(v10) )
    {
      v6 = CAMCApp::ScOnQuitApp(&theApp, v11);
      mmcerror::SC::operator=(v10, v6);
      mmcerror::SC::~SC((mmcerror::SC *)v11);
      if ( (unsigned __int8)mmcerror::SC::operator bool(v10) )
        mmcerror::SC::TraceAndClear((mmcerror::SC *)v10);
      ComObjectEventSource = GetComObjectEventSource();
      v9 = CEventSource<CComObjectObserver,CVoid,CVoid,CVoid,CVoid>::ScFireEvent<CComObjectObserver>(
             ComObjectEventSource,
             (mmcerror::SC *)v11,
             v8);
      mmcerror::SC::operator=(v10, v9);
      mmcerror::SC::~SC((mmcerror::SC *)v11);
      if ( (unsigned __int8)mmcerror::SC::operator bool(v10) )
        mmcerror::SC::TraceAndClear((mmcerror::SC *)v10);
    }
    --`CAMCMultiDocTemplate::CloseAllDocuments'::`2'::cInvocations;
  }
  else
  {
    `CAMCMultiDocTemplate::CloseAllDocuments'::`2'::cInvocations = v4;
  }
  mmcerror::SC::~SC((mmcerror::SC *)v10);
}

```

## disassembly

```asm
0x140069bd0  mov     [rsp-8+arg_0], rbx
0x140069bd5  mov     [rsp-8+arg_8], rdi
0x140069bda  push    rbp
0x140069bdb  mov     rbp, rsp
0x140069bde  sub     rsp, 50h
0x140069be2  mov     ebx, edx
0x140069be4  mov     rdi, rcx
0x140069be7  xor     edx, edx
0x140069be9  lea     rcx, [rbp+var_30]
0x140069bed  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x140069bf3  nop
0x140069bf4  lea     rdx, aCamcmultidocte_0; "CAMCMultiDocTemplate::CloseAllDocuments"
0x140069bfb  lea     rcx, [rbp+var_30]
0x140069bff  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x140069c05  lea     rax, ?cInvocations@?1??CloseAllDocuments@CAMCMultiDocTemplate@@UEAAXH@Z@4IA; uint `CAMCMultiDocTemplate::CloseAllDocuments(int)'::`2'::cInvocations
0x140069c0c  mov     [rbp+arg_10], rax
0x140069c10  mov     r8d, cs:?cInvocations@?1??CloseAllDocuments@CAMCMultiDocTemplate@@UEAAXH@Z@4IA; uint `CAMCMultiDocTemplate::CloseAllDocuments(int)'::`2'::cInvocations
0x140069c17  lea     eax, [r8+1]
0x140069c1b  mov     cs:?cInvocations@?1??CloseAllDocuments@CAMCMultiDocTemplate@@UEAAXH@Z@4IA, eax; uint `CAMCMultiDocTemplate::CloseAllDocuments(int)'::`2'::cInvocations
0x140069c21  cmp     eax, 1
0x140069c24  jbe     short loc_140069C32
0x140069c26  mov     cs:?cInvocations@?1??CloseAllDocuments@CAMCMultiDocTemplate@@UEAAXH@Z@4IA, r8d; uint `CAMCMultiDocTemplate::CloseAllDocuments(int)'::`2'::cInvocations
0x140069c2d  jmp     loc_140069D09
0x140069c32  mov     edx, ebx
0x140069c34  mov     rcx, rdi
0x140069c37  call    cs:__imp_?CloseAllDocuments@CDocTemplate@@UEAAXH@Z; CDocTemplate::CloseAllDocuments(int)
0x140069c3d  mov     r8d, 8000FFFFh
0x140069c43  lea     rdx, ?theApp@@3VCAMCApp@@A; CAMCApp theApp
0x140069c4a  lea     rcx, [rbp+var_18]
0x140069c4e  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBXJ@Z; ScCheckPointers(void const *,long)
0x140069c53  nop
0x140069c54  mov     rdx, rax
0x140069c57  lea     rcx, [rbp+var_30]
0x140069c5b  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x140069c61  nop
0x140069c62  lea     rcx, [rbp+var_18]
0x140069c66  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x140069c6c  lea     rcx, [rbp+var_30]
0x140069c70  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x140069c76  test    al, al
0x140069c78  jnz     loc_140069D03
0x140069c7e  lea     rdx, [rbp+var_18]
0x140069c82  lea     rcx, ?theApp@@3VCAMCApp@@A; CAMCApp theApp
0x140069c89  call    ?ScOnQuitApp@CAMCApp@@QEAA?AVSC@mmcerror@@XZ; CAMCApp::ScOnQuitApp(void)
0x140069c8e  nop
0x140069c8f  mov     rdx, rax
0x140069c92  lea     rcx, [rbp+var_30]
0x140069c96  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x140069c9c  nop
0x140069c9d  lea     rcx, [rbp+var_18]
0x140069ca1  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x140069ca7  lea     rcx, [rbp+var_30]
0x140069cab  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x140069cb1  test    al, al
0x140069cb3  jz      short loc_140069CBF
0x140069cb5  lea     rcx, [rbp+var_30]
0x140069cb9  call    cs:__imp_?TraceAndClear@SC@mmcerror@@QEAAXXZ; mmcerror::SC::TraceAndClear(void)
0x140069cbf  call    cs:__imp_?GetComObjectEventSource@@YAAEAV?$CEventSource@VCComObjectObserver@@VCVoid@@V2@V2@V2@@@XZ; GetComObjectEventSource(void)
0x140069cc5  lea     rdx, [rbp+var_18]
0x140069cc9  mov     rcx, rax
0x140069ccc  call    ??$ScFireEvent@VCComObjectObserver@@@?$CEventSource@VCComObjectObserver@@VCVoid@@V2@V2@V2@@@QEAA?AVSC@mmcerror@@P8CComObjectObserver@@EAA?AV12@XZ@Z; CEventSource<CComObjectObserver,CVoid,CVoid,CVoid,CVoid>::ScFireEvent<CComObjectObserver>(mmcerror::SC (CComObjectObserver::*)(void))
0x140069cd1  nop
0x140069cd2  mov     rdx, rax
0x140069cd5  lea     rcx, [rbp+var_30]
0x140069cd9  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x140069cdf  nop
0x140069ce0  lea     rcx, [rbp+var_18]
0x140069ce4  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x140069cea  lea     rcx, [rbp+var_30]
0x140069cee  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x140069cf4  test    al, al
0x140069cf6  jz      short loc_140069D03
0x140069cf8  lea     rcx, [rbp+var_30]
0x140069cfc  call    cs:__imp_?TraceAndClear@SC@mmcerror@@QEAAXXZ; mmcerror::SC::TraceAndClear(void)
0x140069d02  nop
0x140069d03  dec     cs:?cInvocations@?1??CloseAllDocuments@CAMCMultiDocTemplate@@UEAAXH@Z@4IA; uint `CAMCMultiDocTemplate::CloseAllDocuments(int)'::`2'::cInvocations
0x140069d09  lea     rcx, [rbp+var_30]
0x140069d0d  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x140069d13  mov     rbx, [rsp+50h+arg_0]
0x140069d18  mov     rdi, [rsp+50h+arg_8]
0x140069d1d  add     rsp, 50h
0x140069d21  pop     rbp
0x140069d22  retn
```
