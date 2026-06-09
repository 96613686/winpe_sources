# CDpSearchProtocol::Init(_TIMEOUT_INFO *,IProtocolHandlerSite *,_PROXY_INFO *)

- ea: `0x180004a00`
- end: `0x180004a56`
- name: `?Init@CDpSearchProtocol@@UEAAJPEAU_TIMEOUT_INFO@@PEAUIProtocolHandlerSite@@PEAU_PROXY_INFO@@@Z`
- size: `86`
- prototype: `__int64 __fastcall(CDpSearchProtocol *__hidden this, struct _TIMEOUT_INFO *, struct IProtocolHandlerSite *, struct _PROXY_INFO *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004a00`
- `0x180007a40`
- `0x180007cc4`
- `0x1800099e4`
- `0x18000ab60`

## pseudocode

```c
__int64 __fastcall CDpSearchProtocol::Init(
        CDpSearchProtocol *this,
        struct _TIMEOUT_INFO *a2,
        struct IProtocolHandlerSite *a3,
        struct _PROXY_INFO *a4)
{
  ATL::CAtlException *v5; // [rsp+20h] [rbp-78h] BYREF
  LPVOID ppv[10]; // [rsp+30h] [rbp-68h] BYREF

  try
  {
    DpSearch::DpSearch(ppv);
    DpSearch::PruneIndex((DpSearch *)ppv);
    DpSearch::~DpSearch((DpSearch *)ppv);
  }
  catch ( exception )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_67d934e699f83311671b1011635d052f_Traceguids);
    return 0;
  }
  catch ( ATL::CAtlException *v5 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_67d934e699f83311671b1011635d052f_Traceguids,
        *(unsigned int *)v5);
  }
  DpSearch::DpSearch(ppv);
}

```

## disassembly

```asm
0x180004a00  sub     rsp, 98h
0x180004a07  mov     rax, cs:__security_cookie
0x180004a0e  xor     rax, rsp
0x180004a11  mov     [rsp+98h+var_18], rax
0x180004a19  lea     rcx, [rsp+98h+ppv]; ppv
0x180004a1e  call    ??0DpSearch@@QEAA@XZ; DpSearch::DpSearch(void)
0x180004a23  nop
0x180004a24  lea     rcx, [rsp+98h+ppv]; this
0x180004a29  call    ?PruneIndex@DpSearch@@QEAAXXZ; DpSearch::PruneIndex(void)
0x180004a2e  nop
0x180004a2f  lea     rcx, [rsp+98h+ppv]; this
0x180004a34  call    ??1DpSearch@@QEAA@XZ; DpSearch::~DpSearch(void)
0x180004a39  nop
0x180004a3a  xor     eax, eax
0x180004a3c  mov     rcx, [rsp+98h+var_18]
0x180004a44  xor     rcx, rsp; StackCookie
0x180004a47  call    __security_check_cookie
0x180004a4c  add     rsp, 98h
0x180004a53  retn
0x180004a54  jmp     short loc_180004A3A
```
