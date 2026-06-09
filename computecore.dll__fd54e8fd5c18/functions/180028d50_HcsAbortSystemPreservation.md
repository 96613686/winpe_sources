# HcsAbortSystemPreservation

- ea: `0x180028d50`
- end: `0x180028e91`
- name: `HcsAbortSystemPreservation`
- size: `321`
- prototype: `__int64 __fastcall(RPC_WSTR StringUuid)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800067c0`
- `0x180007438`
- `0x180013de8`
- `0x1800144a4`
- `0x180014f14`
- `0x180015150`
- `0x18001587c`
- `0x180028d50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028dd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028dd5`
- `RPCRT4!UuidFromStringW` at `0x180028e17`
- `RPCRT4!UuidFromStringW` at `0x180028e17`
- `vid!VidCloseStatisticsHandle` at `0x180028e2e`
- `vid!VidCloseStatisticsHandle` at `0x180028e2e`
- `vid!VidOpenStatisticsHandle` at `0x180028dc6`
- `vid!VidOpenStatisticsHandle` at `0x180028dc6`
- `vid!VidPhuFreePersistedData` at `0x180028e25`
- `vid!VidPhuFreePersistedData` at `0x180028e25`

## string_xrefs

- `0x180028e7e`: `onecore\vm\compute\dll\core\src\utilities.cpp`
- `0x180028da3`: `HcsAbortSystemPreservation`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall HcsAbortSystemPreservation(RPC_WSTR StringUuid)
{
  __int64 v2; // rdi
  signed int LastError; // eax
  unsigned int v4; // ebx
  const char *v5; // r9
  __int64 result; // rax
  unsigned int v7; // eax
  int v8; // edx
  int v9; // [rsp+20h] [rbp-188h]
  UUID Uuid; // [rsp+28h] [rbp-180h] BYREF
  _QWORD v11[42]; // [rsp+40h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  memset_0(v11, 0, sizeof(v11));
  wil::ActivityBase<ComputeCore::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeCore::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>(v11);
  v11[0] = &ComputeCore::Diagnostics::TraceProvider::HcsClientApi::`vftable';
  try
  {
    ComputeCore::Diagnostics::TraceProvider::HcsClientApi::StartActivity(
      (ComputeCore::Diagnostics::TraceProvider::HcsClientApi *)v11,
      "HcsAbortSystemPreservation",
      0);
    if ( !StringUuid )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD5,
        (unsigned int)"onecore\\vm\\compute\\dll\\core\\src\\utilities.cpp",
        (const char *)0x80070057LL,
        v9);
    v2 = VidOpenStatisticsHandle(retaddr);
    if ( v2 == -1 )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( (LastError & 0x1FFF0000) != 0 )
      {
        if ( LastError > 0 )
          v4 = LastError & 0xFFFFFFF | 0x80000000;
      }
      else if ( LastError > 0 )
      {
        v4 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    else
    {
      v4 = 0;
      Uuid = 0;
      UuidFromStringW(StringUuid, &Uuid);
      VidPhuFreePersistedData(v2, &Uuid);
      VidCloseStatisticsHandle(v2);
    }
    wil::ActivityBase<ComputeCore::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
      v11,
      v4);
    ComputeCore::Diagnostics::TraceProvider::HcsClientApi::~HcsClientApi((ComputeCore::Diagnostics::TraceProvider::HcsClientApi *)v11);
    result = v4;
  }
  catch ( ... )
  {
    v7 = wil::details::in1diag3::Log_CaughtException(
           retaddr,
           (void *)0xDA,
           (unsigned int)"onecore\\vm\\compute\\dll\\core\\src\\utilities.cpp",
           v5);
    return (unsigned int)ClientError::ToV2Result((ClientError *)v7, v8);
  }
  return result;
}

```

## disassembly

```asm
0x180028d50  mov     [rsp+arg_8], rbx
0x180028d55  mov     [rsp+arg_10], rsi
0x180028d5a  push    rdi
0x180028d5b  sub     rsp, 1A0h
0x180028d62  mov     rax, cs:__security_cookie
0x180028d69  xor     rax, rsp
0x180028d6c  mov     [rsp+1A8h+var_18], rax
0x180028d74  mov     rsi, rcx
0x180028d77  xor     edx, edx; Val
0x180028d79  mov     r8d, 150h; Size
0x180028d7f  lea     rcx, [rsp+1A8h+var_168]; void *
0x180028d84  call    memset_0
0x180028d89  nop
0x180028d8a  lea     rcx, [rsp+1A8h+var_168]
0x180028d8f  call    ??0?$ActivityBase@VTraceProvider@Diagnostics@ComputeCore@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ComputeCore::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ComputeCore::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180028d94  lea     rax, ??_7HcsClientApi@TraceProvider@Diagnostics@ComputeCore@@6B@; const ComputeCore::Diagnostics::TraceProvider::HcsClientApi::`vftable'
0x180028d9b  mov     [rsp+1A8h+var_168], rax
0x180028da0  xor     r8d, r8d; void *
0x180028da3  lea     rdx, aHcsabortsystem_0; "HcsAbortSystemPreservation"
0x180028daa  lea     rcx, [rsp+1A8h+var_168]; this
0x180028daf  call    ?StartActivity@HcsClientApi@TraceProvider@Diagnostics@ComputeCore@@QEAAXPEBDPEAX@Z; ComputeCore::Diagnostics::TraceProvider::HcsClientApi::StartActivity(char const *,void *)
0x180028db4  nop
0x180028db5  mov     rcx, [rsp+1A8h]; this
0x180028dbd  test    rsi, rsi
0x180028dc0  jz      loc_180028E78
0x180028dc6  call    cs:__imp_VidOpenStatisticsHandle
0x180028dcc  mov     rdi, rax
0x180028dcf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180028dd3  jnz     short loc_180028E05
0x180028dd5  call    cs:__imp_GetLastError
0x180028ddb  mov     ebx, eax
0x180028ddd  test    eax, 1FFF0000h
0x180028de2  jnz     short loc_180028DF3
0x180028de4  test    eax, eax
0x180028de6  jle     short loc_180028E34
0x180028de8  movzx   ebx, bx
0x180028deb  or      ebx, 80070000h
0x180028df1  jmp     short loc_180028E34
0x180028df3  test    ebx, ebx
0x180028df5  jle     short loc_180028E34
0x180028df7  and     ebx, 0FFFFFFFh
0x180028dfd  or      ebx, 80000000h
0x180028e03  jmp     short loc_180028E34
0x180028e05  xor     ebx, ebx
0x180028e07  xorps   xmm0, xmm0
0x180028e0a  movups  xmmword ptr [rsp+1A8h+Uuid.Data1], xmm0
0x180028e0f  lea     rdx, [rsp+1A8h+Uuid]; Uuid
0x180028e14  mov     rcx, rsi; StringUuid
0x180028e17  call    cs:__imp_UuidFromStringW
0x180028e1d  lea     rdx, [rsp+1A8h+Uuid]
0x180028e22  mov     rcx, rdi
0x180028e25  call    cs:__imp_VidPhuFreePersistedData
0x180028e2b  mov     rcx, rdi
0x180028e2e  call    cs:__imp_VidCloseStatisticsHandle
0x180028e34  mov     edx, ebx
0x180028e36  lea     rcx, [rsp+1A8h+var_168]
0x180028e3b  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeCore@@$0A@$0CAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeCore::Diagnostics::TraceProvider,0,131072,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180028e40  nop
0x180028e41  lea     rcx, [rsp+1A8h+var_168]; this
0x180028e46  call    ??1HcsClientApi@TraceProvider@Diagnostics@ComputeCore@@QEAA@XZ; ComputeCore::Diagnostics::TraceProvider::HcsClientApi::~HcsClientApi(void)
0x180028e4b  mov     eax, ebx
0x180028e4d  jmp     short loc_180028E53
0x180028e4f  mov     eax, [rsp+1A8h+var_188]
0x180028e53  mov     rcx, [rsp+1A8h+var_18]
0x180028e5b  xor     rcx, rsp; StackCookie
0x180028e5e  call    __security_check_cookie
0x180028e63  lea     r11, [rsp+1A8h+var_8]
0x180028e6b  mov     rbx, [r11+18h]
0x180028e6f  mov     rsi, [r11+20h]
0x180028e73  mov     rsp, r11
0x180028e76  pop     rdi
0x180028e77  retn
0x180028e78  mov     r9d, 80070057h; char *
0x180028e7e  lea     r8, aOnecoreVmCompu_20; "onecore\\vm\\compute\\dll\\core\\src\\u"...
0x180028e85  mov     edx, 0D5h; void *
0x180028e8a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
