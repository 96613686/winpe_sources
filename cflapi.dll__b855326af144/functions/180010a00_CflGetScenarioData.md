# CflGetScenarioData

- ea: `0x180010a00`
- end: `0x180010bca`
- name: `CflGetScenarioData`
- size: `458`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002490`
- `0x180002ef8`
- `0x1800067c4`
- `0x1800084d4`
- `0x180008868`
- `0x180009adc`
- `0x18000cc7c`
- `0x18000d8d8`
- `0x180010a00`
- `0x18001dae0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010a47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010a47`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180010a5f`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180010a5f`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180010a65`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180010a65`

## string_xrefs

- `0x180010b19`: `onecore\ds\security\cfl\api\dll\entrypoints.cpp`
- `0x180010aff`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall CflGetScenarioData(OLECHAR **a1, _QWORD *a2, DWORD *a3)
{
  HANDLE CurrentProcess; // rax
  const unsigned __int16 *CommandLineW; // rbx
  unsigned int v8; // ebx
  __int64 v9; // rdx
  int AllScenarioData; // eax
  int v12[2]; // [rsp+20h] [rbp-3C8h]
  DWORD dwSize[4]; // [rsp+40h] [rbp-3A8h] BYREF
  _QWORD v14[42]; // [rsp+50h] [rbp-398h] BYREF
  WCHAR ExeName[264]; // [rsp+1A0h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3E8h] [rbp+0h]

  memset_0(ExeName, 0, 0x20Au);
  dwSize[0] = 261;
  CurrentProcess = GetCurrentProcess();
  QueryFullProcessImageNameW(CurrentProcess, 0, ExeName, dwSize);
  CommandLineW = GetCommandLineW();
  wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v14,
    "CflGetScenarioDataActivity");
  v14[0] = &CflApiTraceProvider::CflGetScenarioDataActivity::`vftable';
  CflApiTraceProvider::CflGetScenarioDataActivity::StartActivity(
    (CflApiTraceProvider::CflGetScenarioDataActivity *)v14,
    ExeName,
    CommandLineW);
  if ( !a1 )
  {
    v8 = -2147467261;
    v9 = 520;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)v8,
      v12[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF5,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\dll\\entrypoints.cpp",
      (const char *)v8,
      v12[0]);
    v14[0] = &CflApiTraceProvider::CflGetScenarioDataActivity::`vftable';
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v14);
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v14);
    return v8;
  }
  if ( a2 )
  {
    if ( a3 )
      goto LABEL_5;
LABEL_12:
    v8 = -2147024809;
    v9 = 525;
    goto LABEL_8;
  }
  if ( a3 )
    goto LABEL_12;
LABEL_5:
  AllScenarioData = CflApi::GetAllScenarioData(1, 0, 0, 0, a1, a2, a3);
  v8 = AllScenarioData;
  if ( AllScenarioData >= 0 )
  {
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v14);
    v14[0] = &CflApiTraceProvider::CflGetScenarioDataActivity::`vftable';
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v14);
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v14);
    return 0;
  }
  else
  {
    if ( AllScenarioData != -2147024894 )
    {
      v9 = 536;
      goto LABEL_8;
    }
    v14[0] = &CflApiTraceProvider::CflGetScenarioDataActivity::`vftable';
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v14);
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v14);
    return 2147942402LL;
  }
}

```

## disassembly

```asm
0x180010a00  push    rbx
0x180010a02  push    rsi
0x180010a03  push    rdi
0x180010a04  push    r14
0x180010a06  push    r15
0x180010a08  sub     rsp, 3C0h
0x180010a0f  mov     rax, cs:__security_cookie
0x180010a16  xor     rax, rsp
0x180010a19  mov     [rsp+3E8h+var_38], rax
0x180010a21  mov     rdi, r8
0x180010a24  mov     rsi, rdx
0x180010a27  mov     r14, rcx
0x180010a2a  xor     edx, edx; Val
0x180010a2c  mov     r8d, 20Ah; Size
0x180010a32  lea     rcx, [rsp+3E8h+ExeName]; void *
0x180010a3a  call    memset_0
0x180010a3f  mov     [rsp+3E8h+dwSize], 105h
0x180010a47  call    cs:__imp_GetCurrentProcess
0x180010a4d  mov     rcx, rax; hProcess
0x180010a50  lea     r9, [rsp+3E8h+dwSize]; lpdwSize
0x180010a55  lea     r8, [rsp+3E8h+ExeName]; lpExeName
0x180010a5d  xor     edx, edx; dwFlags
0x180010a5f  call    cs:__imp_QueryFullProcessImageNameW
0x180010a65  call    cs:__imp_GetCommandLineW
0x180010a6b  mov     rbx, rax
0x180010a6e  lea     rdx, aCflgetscenario_1; "CflGetScenarioDataActivity"
0x180010a75  lea     rcx, [rsp+3E8h+var_398]
0x180010a7a  call    ??0?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180010a7f  lea     r15, ??_7CflGetScenarioDataActivity@CflApiTraceProvider@@6B@; const CflApiTraceProvider::CflGetScenarioDataActivity::`vftable'
0x180010a86  mov     [rsp+3E8h+var_398], r15
0x180010a8b  mov     r8, rbx; unsigned __int16 *
0x180010a8e  lea     rdx, [rsp+3E8h+ExeName]; unsigned __int16 *
0x180010a96  lea     rcx, [rsp+3E8h+var_398]; this
0x180010a9b  call    ?StartActivity@CflGetScenarioDataActivity@CflApiTraceProvider@@QEAAXPEBG0@Z; CflApiTraceProvider::CflGetScenarioDataActivity::StartActivity(ushort const *,ushort const *)
0x180010aa0  nop
0x180010aa1  test    r14, r14
0x180010aa4  jnz     short loc_180010AB2
0x180010aa6  mov     ebx, 80004003h
0x180010aab  mov     edx, 208h
0x180010ab0  jmp     short loc_180010AF7
0x180010ab2  test    rsi, rsi
0x180010ab5  jz      loc_180010BB0
0x180010abb  test    rdi, rdi
0x180010abe  jz      loc_180010BB9
0x180010ac4  mov     [rsp+3E8h+var_3B8], rdi
0x180010ac9  mov     [rsp+3E8h+var_3C0], rsi
0x180010ace  mov     qword ptr [rsp+3E8h+var_3C8], r14; int
0x180010ad3  xor     r9d, r9d
0x180010ad6  xor     r8d, r8d
0x180010ad9  xor     edx, edx
0x180010adb  lea     ecx, [rdx+1]
0x180010ade  call    CflApi__GetAllScenarioData
0x180010ae3  mov     ebx, eax
0x180010ae5  test    eax, eax
0x180010ae7  jns     short loc_180010B65
0x180010ae9  mov     edi, 80070002h
0x180010aee  cmp     eax, edi
0x180010af0  jz      short loc_180010B48
0x180010af2  mov     edx, 218h; void *
0x180010af7  mov     rcx, [rsp+3E8h]; this
0x180010aff  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x180010b06  mov     r9d, ebx; char *
0x180010b09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010b0e  mov     rcx, [rsp+3E8h]; this
0x180010b16  mov     r9d, ebx; char *
0x180010b19  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cfl\\api\\dll\\e"...
0x180010b20  mov     edx, 0F5h; void *
0x180010b25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010b2a  nop
0x180010b2b  mov     [rsp+3E8h+var_398], r15
0x180010b30  lea     rcx, [rsp+3E8h+var_398]
0x180010b35  call    ?Destroy@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180010b3a  lea     rcx, [rsp+3E8h+var_398]
0x180010b3f  call    ??1?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180010b44  mov     eax, ebx
0x180010b46  jmp     short loc_180010B91
0x180010b48  mov     [rsp+3E8h+var_398], r15
0x180010b4d  lea     rcx, [rsp+3E8h+var_398]
0x180010b52  call    ?Destroy@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180010b57  lea     rcx, [rsp+3E8h+var_398]
0x180010b5c  call    ??1?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180010b61  mov     eax, edi
0x180010b63  jmp     short loc_180010B91
0x180010b65  lea     rcx, [rsp+3E8h+var_398]
0x180010b6a  call    ?Stop@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180010b6f  nop
0x180010b70  mov     [rsp+3E8h+var_398], r15
0x180010b75  lea     rcx, [rsp+3E8h+var_398]
0x180010b7a  call    ?Destroy@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180010b7f  lea     rcx, [rsp+3E8h+var_398]
0x180010b84  call    ??1?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180010b89  xor     eax, eax
0x180010b8b  jmp     short loc_180010B91
0x180010b8d  mov     eax, [rsp+3E8h+dwSize]
0x180010b91  mov     rcx, [rsp+3E8h+var_38]
0x180010b99  xor     rcx, rsp; StackCookie
0x180010b9c  call    __security_check_cookie
0x180010ba1  add     rsp, 3C0h
0x180010ba8  pop     r15
0x180010baa  pop     r14
0x180010bac  pop     rdi
0x180010bad  pop     rsi
0x180010bae  pop     rbx
0x180010baf  retn
0x180010bb0  test    rdi, rdi
0x180010bb3  jz      loc_180010AC4
0x180010bb9  mov     ebx, 80070057h
0x180010bbe  mov     edx, 20Dh
0x180010bc3  jmp     loc_180010AF7
```
