# CflGetScenarioDataNew

- ea: `0x180010bd0`
- end: `0x180010da6`
- name: `CflGetScenarioDataNew`
- size: `470`
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
- `0x180010bd0`
- `0x1800298d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010c1c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010c1c`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180010c34`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180010c34`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180010c3a`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180010c3a`

## string_xrefs

- `0x180010cf3`: `onecore\ds\security\cfl\api\dll\entrypoints.cpp`
- `0x180010cd9`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall CflGetScenarioDataNew(_QWORD *a1, _QWORD *a2, DWORD *a3, _DWORD *a4)
{
  HANDLE CurrentProcess; // rax
  const unsigned __int16 *CommandLineW; // rbx
  unsigned int v10; // ebx
  __int64 v11; // rdx
  int AllScenarioData; // eax
  int v14[2]; // [rsp+20h] [rbp-3D8h]
  DWORD dwSize[4]; // [rsp+40h] [rbp-3B8h] BYREF
  _QWORD v16[42]; // [rsp+50h] [rbp-3A8h] BYREF
  WCHAR ExeName[264]; // [rsp+1A0h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3F8h] [rbp+0h]

  memset_0(ExeName, 0, 0x20Au);
  dwSize[0] = 261;
  CurrentProcess = GetCurrentProcess();
  QueryFullProcessImageNameW(CurrentProcess, 0, ExeName, dwSize);
  CommandLineW = GetCommandLineW();
  wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v16,
    "CflGetScenarioDataActivity");
  v16[0] = &CflApiTraceProvider::CflGetScenarioDataActivity::`vftable';
  CflApiTraceProvider::CflGetScenarioDataActivity::StartActivity(
    (CflApiTraceProvider::CflGetScenarioDataActivity *)v16,
    ExeName,
    CommandLineW);
  if ( !a1 )
  {
    v10 = -2147467261;
    v11 = 230;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
      (const char *)v10,
      v14[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10F,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\dll\\entrypoints.cpp",
      (const char *)v10,
      v14[0]);
    v16[0] = &CflApiTraceProvider::CflGetScenarioDataActivity::`vftable';
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v16);
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v16);
    return v10;
  }
  if ( a2 )
  {
    if ( a3 )
      goto LABEL_5;
LABEL_12:
    v10 = -2147024809;
    v11 = 235;
    goto LABEL_8;
  }
  if ( a3 )
    goto LABEL_12;
LABEL_5:
  AllScenarioData = CflApiNew::GetAllScenarioData(1, 0, 0, 0, a1, a2, a3, a4);
  v10 = AllScenarioData;
  if ( AllScenarioData >= 0 )
  {
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v16);
    v16[0] = &CflApiTraceProvider::CflGetScenarioDataActivity::`vftable';
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v16);
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v16);
    return 0;
  }
  else
  {
    if ( AllScenarioData != -2147024894 )
    {
      v11 = 247;
      goto LABEL_8;
    }
    v16[0] = &CflApiTraceProvider::CflGetScenarioDataActivity::`vftable';
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v16);
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v16);
    return 2147942402LL;
  }
}

```

## disassembly

```asm
0x180010bd0  push    rbx
0x180010bd2  push    rsi
0x180010bd3  push    rdi
0x180010bd4  push    r12
0x180010bd6  push    r14
0x180010bd8  push    r15
0x180010bda  sub     rsp, 3C8h
0x180010be1  mov     rax, cs:__security_cookie
0x180010be8  xor     rax, rsp
0x180010beb  mov     [rsp+3F8h+var_48], rax
0x180010bf3  mov     r15, r9
0x180010bf6  mov     rdi, r8
0x180010bf9  mov     rsi, rdx
0x180010bfc  mov     r14, rcx
0x180010bff  xor     edx, edx; Val
0x180010c01  mov     r8d, 20Ah; Size
0x180010c07  lea     rcx, [rsp+3F8h+ExeName]; void *
0x180010c0f  call    memset_0
0x180010c14  mov     [rsp+3F8h+dwSize], 105h
0x180010c1c  call    cs:__imp_GetCurrentProcess
0x180010c22  mov     rcx, rax; hProcess
0x180010c25  lea     r9, [rsp+3F8h+dwSize]; lpdwSize
0x180010c2a  lea     r8, [rsp+3F8h+ExeName]; lpExeName
0x180010c32  xor     edx, edx; dwFlags
0x180010c34  call    cs:__imp_QueryFullProcessImageNameW
0x180010c3a  call    cs:__imp_GetCommandLineW
0x180010c40  mov     rbx, rax
0x180010c43  lea     rdx, aCflgetscenario_1; "CflGetScenarioDataActivity"
0x180010c4a  lea     rcx, [rsp+3F8h+var_3A8]
0x180010c4f  call    ??0?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180010c54  lea     r12, ??_7CflGetScenarioDataActivity@CflApiTraceProvider@@6B@; const CflApiTraceProvider::CflGetScenarioDataActivity::`vftable'
0x180010c5b  mov     [rsp+3F8h+var_3A8], r12
0x180010c60  mov     r8, rbx; unsigned __int16 *
0x180010c63  lea     rdx, [rsp+3F8h+ExeName]; unsigned __int16 *
0x180010c6b  lea     rcx, [rsp+3F8h+var_3A8]; this
0x180010c70  call    ?StartActivity@CflGetScenarioDataActivity@CflApiTraceProvider@@QEAAXPEBG0@Z; CflApiTraceProvider::CflGetScenarioDataActivity::StartActivity(ushort const *,ushort const *)
0x180010c75  nop
0x180010c76  test    r14, r14
0x180010c79  jnz     short loc_180010C87
0x180010c7b  mov     ebx, 80004003h
0x180010c80  mov     edx, 0E6h
0x180010c85  jmp     short loc_180010CD1
0x180010c87  test    rsi, rsi
0x180010c8a  jz      loc_180010D8C
0x180010c90  test    rdi, rdi
0x180010c93  jz      loc_180010D95
0x180010c99  mov     [rsp+3F8h+var_3C0], r15
0x180010c9e  mov     [rsp+3F8h+var_3C8], rdi
0x180010ca3  mov     [rsp+3F8h+var_3D0], rsi
0x180010ca8  mov     qword ptr [rsp+3F8h+var_3D8], r14; int
0x180010cad  xor     r9d, r9d
0x180010cb0  xor     r8d, r8d
0x180010cb3  xor     edx, edx
0x180010cb5  lea     ecx, [rdx+1]
0x180010cb8  call    CflApiNew__GetAllScenarioData
0x180010cbd  mov     ebx, eax
0x180010cbf  test    eax, eax
0x180010cc1  jns     short loc_180010D3F
0x180010cc3  mov     edi, 80070002h
0x180010cc8  cmp     eax, edi
0x180010cca  jz      short loc_180010D22
0x180010ccc  mov     edx, 0F7h; void *
0x180010cd1  mov     rcx, [rsp+3F8h]; this
0x180010cd9  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x180010ce0  mov     r9d, ebx; char *
0x180010ce3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010ce8  mov     rcx, [rsp+3F8h]; this
0x180010cf0  mov     r9d, ebx; char *
0x180010cf3  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cfl\\api\\dll\\e"...
0x180010cfa  mov     edx, 10Fh; void *
0x180010cff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010d04  nop
0x180010d05  mov     [rsp+3F8h+var_3A8], r12
0x180010d0a  lea     rcx, [rsp+3F8h+var_3A8]
0x180010d0f  call    ?Destroy@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180010d14  lea     rcx, [rsp+3F8h+var_3A8]
0x180010d19  call    ??1?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180010d1e  mov     eax, ebx
0x180010d20  jmp     short loc_180010D6B
0x180010d22  mov     [rsp+3F8h+var_3A8], r12
0x180010d27  lea     rcx, [rsp+3F8h+var_3A8]
0x180010d2c  call    ?Destroy@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180010d31  lea     rcx, [rsp+3F8h+var_3A8]
0x180010d36  call    ??1?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180010d3b  mov     eax, edi
0x180010d3d  jmp     short loc_180010D6B
0x180010d3f  lea     rcx, [rsp+3F8h+var_3A8]
0x180010d44  call    ?Stop@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180010d49  nop
0x180010d4a  mov     [rsp+3F8h+var_3A8], r12
0x180010d4f  lea     rcx, [rsp+3F8h+var_3A8]
0x180010d54  call    ?Destroy@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180010d59  lea     rcx, [rsp+3F8h+var_3A8]
0x180010d5e  call    ??1?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180010d63  xor     eax, eax
0x180010d65  jmp     short loc_180010D6B
0x180010d67  mov     eax, [rsp+3F8h+dwSize]
0x180010d6b  mov     rcx, [rsp+3F8h+var_48]
0x180010d73  xor     rcx, rsp; StackCookie
0x180010d76  call    __security_check_cookie
0x180010d7b  add     rsp, 3C8h
0x180010d82  pop     r15
0x180010d84  pop     r14
0x180010d86  pop     r12
0x180010d88  pop     rdi
0x180010d89  pop     rsi
0x180010d8a  pop     rbx
0x180010d8b  retn
0x180010d8c  test    rdi, rdi
0x180010d8f  jz      loc_180010C99
0x180010d95  mov     ebx, 80070057h
0x180010d9a  mov     edx, 0EBh
0x180010d9f  jmp     loc_180010CD1
```
