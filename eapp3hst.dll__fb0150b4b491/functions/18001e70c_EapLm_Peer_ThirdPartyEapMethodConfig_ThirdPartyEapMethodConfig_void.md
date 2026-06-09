# EapLm::Peer::ThirdPartyEapMethodConfig::~ThirdPartyEapMethodConfig(void)

- ea: `0x18001e70c`
- end: `0x18001e833`
- name: `??1ThirdPartyEapMethodConfig@Peer@EapLm@@UEAA@XZ`
- size: `295`
- prototype: `void __fastcall(EapLm::Peer::ThirdPartyEapMethodConfig *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001e870`

## callees

- `0x1800017a0`
- `0x180004ec0`
- `0x180016400`
- `0x18001b154`
- `0x18001e70c`
- `0x18001fca0`
- `0x180020280`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18001e7b4`
- `ntdll!EtwEventEnabled` at `0x18001e7b4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001e779`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001e779`

## string_xrefs

- `0x18001e7be`: `ThirdPartyEapMethodConfig : CoUninitialize called`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall EapLm::Peer::ThirdPartyEapMethodConfig::~ThirdPartyEapMethodConfig(
        EapLm::Peer::ThirdPartyEapMethodConfig *this)
{
  EapLm::Peer::ThirdPartyEapMethodConfig *v1; // rbx
  char v4[2048]; // [rsp+30h] [rbp-818h] BYREF

  v1 = this;
  *(_QWORD *)this = &EapLm::Peer::ThirdPartyEapMethodConfig::`vftable';
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_f8de5c7b8ba83db1c680dda639d42263_Traceguids);
  if ( *((_DWORD *)v1 + 322) == 1 )
  {
    CoUninitialize();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_f8de5c7b8ba83db1c680dda639d42263_Traceguids);
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent) )
    {
      try
      {
        if ( (int)StringCchPrintfA(v4, 0x800u, "ThirdPartyEapMethodConfig : CoUninitialize called") >= 0
          && Microsoft_Windows_EapHostEnableBits < 0 )
        {
          McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v4);
        }
      }
      catch ( Exception )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_f8de5c7b8ba83db1c680dda639d42263_Traceguids);
        v1 = this;
        goto LABEL_14;
      }
    }
  }
  EapLm::Peer::ThirdPartyEapMethodConfig::Shutdown(v1);
LABEL_14:
  EapLm::Peer::BaseEapMethodConfig::~BaseEapMethodConfig((EapLm::DelayLoadModule **)v1);
}

```

## disassembly

```asm
0x18001e70c  mov     [rsp+arg_8], rbx
0x18001e711  push    rdi
0x18001e712  sub     rsp, 840h
0x18001e719  mov     rax, cs:__security_cookie
0x18001e720  xor     rax, rsp
0x18001e723  mov     [rsp+848h+var_18], rax
0x18001e72b  mov     rbx, rcx
0x18001e72e  mov     [rsp+848h+var_828], rcx
0x18001e733  lea     rax, ??_7ThirdPartyEapMethodConfig@Peer@EapLm@@6B@; const EapLm::Peer::ThirdPartyEapMethodConfig::`vftable'
0x18001e73a  mov     [rcx], rax
0x18001e73d  lea     rdi, WPP_GLOBAL_Control
0x18001e744  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e74b  cmp     rcx, rdi
0x18001e74e  jz      short loc_18001E76C
0x18001e750  test    byte ptr [rcx+1Ch], 4
0x18001e754  jz      short loc_18001E76C
0x18001e756  mov     edx, 0Dh
0x18001e75b  lea     r8, WPP_f8de5c7b8ba83db1c680dda639d42263_Traceguids
0x18001e762  mov     rcx, [rcx+10h]
0x18001e766  call    WPP_SF_
0x18001e76b  nop
0x18001e76c  cmp     dword ptr [rbx+508h], 1
0x18001e773  jnz     loc_18001E7F9
0x18001e779  call    cs:__imp_CoUninitialize
0x18001e77f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e786  cmp     rcx, rdi
0x18001e789  jz      short loc_18001E7A6
0x18001e78b  test    byte ptr [rcx+1Ch], 4
0x18001e78f  jz      short loc_18001E7A6
0x18001e791  mov     edx, 0Eh
0x18001e796  lea     r8, WPP_f8de5c7b8ba83db1c680dda639d42263_Traceguids
0x18001e79d  mov     rcx, [rcx+10h]
0x18001e7a1  call    WPP_SF_
0x18001e7a6  lea     rdx, DebugInfoEvent
0x18001e7ad  mov     rcx, cs:eaphost_Context
0x18001e7b4  call    cs:__imp_EtwEventEnabled
0x18001e7ba  test    al, al
0x18001e7bc  jz      short loc_18001E7F9
0x18001e7be  lea     r8, aThirdpartyeapm; "ThirdPartyEapMethodConfig : CoUninitial"...
0x18001e7c5  mov     edx, 800h; unsigned __int64
0x18001e7ca  lea     rcx, [rsp+848h+var_818]; char *
0x18001e7cf  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001e7d4  test    eax, eax
0x18001e7d6  js      short loc_18001E7F9
0x18001e7d8  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x18001e7df  jge     short loc_18001E7F9
0x18001e7e1  lea     r8, [rsp+848h+var_818]
0x18001e7e6  lea     rdx, DebugInfoEvent
0x18001e7ed  lea     rcx, eaphost_Context
0x18001e7f4  call    McTemplateU0s_EtwEventWriteTransfer
0x18001e7f9  mov     rcx, rbx; this
0x18001e7fc  call    ?Shutdown@ThirdPartyEapMethodConfig@Peer@EapLm@@UEAAXXZ; EapLm::Peer::ThirdPartyEapMethodConfig::Shutdown(void)
0x18001e801  nop
0x18001e802  jmp     short loc_18001E809
0x18001e804  mov     rbx, [rsp+848h+var_828]
0x18001e809  mov     rcx, rbx; this
0x18001e80c  call    ??1BaseEapMethodConfig@Peer@EapLm@@UEAA@XZ; EapLm::Peer::BaseEapMethodConfig::~BaseEapMethodConfig(void)
0x18001e811  nop
0x18001e812  mov     rcx, [rsp+848h+var_18]
0x18001e81a  xor     rcx, rsp; StackCookie
0x18001e81d  call    __security_check_cookie
0x18001e822  mov     rbx, [rsp+848h+arg_8]
0x18001e82a  add     rsp, 840h
0x18001e831  pop     rdi
0x18001e832  retn
```
