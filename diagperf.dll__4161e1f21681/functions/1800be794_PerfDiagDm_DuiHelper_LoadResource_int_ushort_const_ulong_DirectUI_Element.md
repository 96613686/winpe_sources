# PerfDiagDm::DuiHelper::LoadResource(int,ushort const *,ulong *,DirectUI::Element * *)

- ea: `0x1800be794`
- end: `0x1800be855`
- name: `?LoadResource@DuiHelper@PerfDiagDm@@AEAAJHPEBGPEAKPEAPEAVElement@DirectUI@@@Z`
- size: `193`
- prototype: `__int64 __fastcall(PerfDiagDm::DuiHelper *__hidden this, int, const unsigned __int16 *, unsigned int *, struct DirectUI::Element **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800bdb2c`

## callees

- `0x1800be794`

## import_xrefs

- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x1800be7eb`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x1800be7eb`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x1800be81c`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x1800be81c`
- `DUI70!InitThread` at `0x1800be7b7`
- `DUI70!InitThread` at `0x1800be7b7`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x1800be842`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x1800be842`

## pseudocode

```c
__int64 __fastcall PerfDiagDm::DuiHelper::LoadResource(
        PerfDiagDm::DuiHelper *this,
        __int64 a2,
        const unsigned __int16 *a3,
        unsigned int *a4,
        struct DirectUI::Element **a5)
{
  struct DirectUI::DUIXmlParser **v5; // rsi
  int v8; // ebx

  v5 = (struct DirectUI::DUIXmlParser **)((char *)this + 8);
  v8 = -2147467259;
  if ( !*((_QWORD *)this + 1) )
  {
    if ( (int)InitThread(2, a2, a3) < 0 )
    {
      *a5 = 0;
      return (unsigned int)v8;
    }
    v8 = DirectUI::DUIXmlParser::Create(
           v5,
           (struct DirectUI::Value *(*)(const unsigned __int16 *, void *))XPerfCore::CEventSinkRootEx<0,XPerfAddIn::CReadyBootInfoSource,ATL::CComSingleThreadModel>::IsInductive,
           this,
           (void (*)(const unsigned __int16 *, const unsigned __int16 *, int, void *))wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
           this);
  }
  *a5 = 0;
  if ( v8 >= 0 )
  {
    v8 = DirectUI::DUIXmlParser::SetXMLFromResource(*v5, 0xC8u, hInstance, (HINSTANCE)&_ImageBase);
    if ( v8 >= 0 )
      return (unsigned int)DirectUI::DUIXmlParser::CreateElement(*v5, L"main", 0, 0, a4, a5);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800be794  push    rbx
0x1800be796  push    rbp
0x1800be797  push    rsi
0x1800be798  push    rdi
0x1800be799  sub     rsp, 38h
0x1800be79d  lea     rsi, [rcx+8]
0x1800be7a1  mov     rbp, r9
0x1800be7a4  cmp     qword ptr [rsi], 0
0x1800be7a8  mov     rdi, rcx
0x1800be7ab  mov     ebx, 80004005h
0x1800be7b0  jnz     short loc_1800BE7F3
0x1800be7b2  mov     ecx, 2
0x1800be7b7  call    cs:__imp_InitThread
0x1800be7bd  test    eax, eax
0x1800be7bf  jns     short loc_1800BE7D2
0x1800be7c1  mov     rax, [rsp+58h+arg_20]
0x1800be7c9  mov     qword ptr [rax], 0
0x1800be7d0  jmp     short loc_1800BE84A
0x1800be7d2  lea     r9, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x1800be7d9  mov     [rsp+58h+var_38], rdi
0x1800be7de  mov     r8, rdi
0x1800be7e1  lea     rdx, ?IsInductive@?$CEventSinkRootEx@$0A@VCReadyBootInfoSource@XPerfAddIn@@VCComSingleThreadModel@ATL@@@XPerfCore@@EEAAHXZ; XPerfCore::CEventSinkRootEx<0,XPerfAddIn::CReadyBootInfoSource,ATL::CComSingleThreadModel>::IsInductive(void)
0x1800be7e8  mov     rcx, rsi
0x1800be7eb  call    cs:__imp_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z; DirectUI::DUIXmlParser::Create(DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *,void (*)(ushort const *,ushort const *,int,void *),void *)
0x1800be7f1  mov     ebx, eax
0x1800be7f3  mov     rdi, [rsp+58h+arg_20]
0x1800be7fb  mov     qword ptr [rdi], 0
0x1800be802  test    ebx, ebx
0x1800be804  js      short loc_1800BE84A
0x1800be806  mov     r8, cs:hInstance
0x1800be80d  lea     r9, __ImageBase
0x1800be814  mov     rcx, [rsi]
0x1800be817  mov     edx, 0C8h
0x1800be81c  call    cs:__imp_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z; DirectUI::DUIXmlParser::SetXMLFromResource(uint,HINSTANCE__ *,HINSTANCE__ *)
0x1800be822  mov     ebx, eax
0x1800be824  test    eax, eax
0x1800be826  js      short loc_1800BE84A
0x1800be828  mov     rcx, [rsi]
0x1800be82b  lea     rdx, aMain; "main"
0x1800be832  mov     [rsp+58h+var_30], rdi
0x1800be837  xor     r9d, r9d
0x1800be83a  xor     r8d, r8d
0x1800be83d  mov     [rsp+58h+var_38], rbp
0x1800be842  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x1800be848  mov     ebx, eax
0x1800be84a  mov     eax, ebx
0x1800be84c  add     rsp, 38h
0x1800be850  pop     rdi
0x1800be851  pop     rsi
0x1800be852  pop     rbp
0x1800be853  pop     rbx
0x1800be854  retn
```
