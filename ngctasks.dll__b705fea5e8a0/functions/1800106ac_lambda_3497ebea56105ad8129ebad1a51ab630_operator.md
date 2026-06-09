# _lambda_3497ebea56105ad8129ebad1a51ab630_::operator()

- ea: `0x1800106ac`
- end: `0x1800108f0`
- name: `_lambda_3497ebea56105ad8129ebad1a51ab630_::operator()`
- size: `580`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000fba0`

## callees

- `0x180007345`
- `0x18000cc34`
- `0x18000ebc0`
- `0x18000fdf0`
- `0x180010248`
- `0x1800106ac`
- `0x180011418`
- `0x180013e14`
- `0x1800189d4`
- `0x18001c1f8`
- `0x18001cff4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180010887`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180010887`
- `ntdll!RtlPublishWnfStateData` at `0x180010854`
- `ntdll!RtlPublishWnfStateData` at `0x180010854`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800107a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010808`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010824`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800107a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010808`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010824`

## string_xrefs

- `0x180010875`: `\Microsoft\Windows\CertificateServicesClient\KeyPreGenTask`
- `0x180010710`: `\Microsoft\Windows\CertificateServicesClient\AIKCertEnrollTask`
- `0x1800106d0`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall lambda_3497ebea56105ad8129ebad1a51ab630_::operator()(__int64 a1, __int64 a2, unsigned int *a3)
{
  unsigned __int64 v4; // rcx
  __int64 v5; // rdx
  unsigned int v6; // ebx
  const unsigned __int16 *v7; // rdi
  const unsigned __int16 *v8; // rsi
  int SrkHash; // esi
  HLOCAL v10; // rcx
  _DWORD *v12; // rax
  __int64 v13; // rdx
  HLOCAL v14; // rcx
  bool v15; // zf
  NgcUtils *v16; // rcx
  int v17; // eax
  int v18; // eax
  int v19; // [rsp+20h] [rbp-40h]
  _BYTE v20[4]; // [rsp+30h] [rbp-30h] BYREF
  int v21; // [rsp+34h] [rbp-2Ch]
  HLOCAL hMem; // [rsp+38h] [rbp-28h] BYREF
  HLOCAL *p_hMem; // [rsp+40h] [rbp-20h] BYREF
  __int64 v24; // [rsp+48h] [rbp-18h] BYREF
  char v25; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  unsigned __int8 *v27; // [rsp+80h] [rbp+20h] BYREF

  v21 = 0;
  v4 = (unsigned int)(**(_DWORD **)a1 - 1);
  if ( (_DWORD)v4 )
  {
    if ( (_DWORD)v4 != 1 )
    {
      v5 = 1782;
LABEL_4:
      v6 = -2147024809;
      goto LABEL_5;
    }
    if ( **(_QWORD **)(a1 + 8) )
    {
      v5 = 1778;
      goto LABEL_4;
    }
    v7 = L"\\Microsoft\\Windows\\CertificateServicesClient\\AIKCertEnrollTask";
    v8 = L"AIKCertEnroll";
LABEL_27:
    v6 = CoInitializeEx(0, 0);
    if ( (v6 & 0x80000000) == 0 )
    {
      wil::ScopeExitIgnore__lambda_0f94373613415aef655645707f91be66___(v20);
      v18 = RunOobeTask(v7, v8);
      v6 = v18;
      if ( v18 >= 0 )
        v6 = 0;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x705,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
          (const char *)(unsigned int)v18,
          v19);
      wil::details::ScopeExitFnGuard__lambda_0f94373613415aef655645707f91be66___::operator()(v20);
      return v6;
    }
    v5 = 1787;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
      (const char *)v6,
      v19);
    return v6;
  }
  if ( !**(_QWORD **)(a1 + 8) )
    goto LABEL_22;
  LODWORD(v27) = 0;
  hMem = 0;
  p_hMem = &hMem;
  v24 = 0;
  v25 = 1;
  SrkHash = NgcUtils::GetSrkHash((NgcUtils *)&v24, &v27, a3);
  v21 = 0;
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)&p_hMem);
  if ( SrkHash >= 0 )
  {
    v12 = *(_DWORD **)(a1 + 16);
    if ( (_DWORD)v27 != *v12 )
    {
      v13 = 1758;
      goto LABEL_18;
    }
    if ( memcmp_0(hMem, **(const void ***)(a1 + 8), (unsigned int)*v12) )
    {
      v13 = 1759;
LABEL_18:
      v6 = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
        (const char *)0x80070057LL,
        v19);
      v14 = hMem;
      v15 = hMem == 0;
      hMem = 0;
      if ( !v15 )
        LocalFree(v14);
      return v6;
    }
    v4 = (unsigned __int64)hMem;
    hMem = 0;
    if ( v4 )
      LocalFree((HLOCAL)v4);
LABEL_22:
    if ( NgcUtils::IsSecureBioEnabled((NgcUtils *)v4) || NgcUtils::IsNgcInVsmEnabled(v16) )
    {
      v19 = 0;
      v17 = RtlPublishWnfStateData(WNF_NGC_PREGEN_NGCISOCTNR_TRIGGER, 0, 0, 0) | 0x10000000;
      if ( v17 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x6E6,
          (int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
          (const char *)(unsigned int)v17);
    }
    v7 = L"\\Microsoft\\Windows\\CertificateServicesClient\\KeyPreGenTask";
    v8 = L"NGCKeyPreGen";
    goto LABEL_27;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x6DC,
    (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
    (const char *)(unsigned int)SrkHash,
    v19);
  v10 = hMem;
  hMem = 0;
  if ( v10 )
    LocalFree(v10);
  return (unsigned int)SrkHash;
}

```

## disassembly

```asm
0x1800106ac  mov     [rsp-18h+arg_8], rbx
0x1800106b1  mov     [rsp-18h+arg_10], rsi
0x1800106b6  push    rbp
0x1800106b7  push    rdi
0x1800106b8  push    r15
0x1800106ba  mov     rbp, rsp
0x1800106bd  sub     rsp, 60h
0x1800106c1  mov     rdi, rcx
0x1800106c4  mov     [rbp+var_2C], 0
0x1800106cb  mov     rdx, [rcx]
0x1800106ce  mov     ecx, [rdx]
0x1800106d0  lea     r15, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x1800106d7  sub     ecx, 1
0x1800106da  jz      short loc_180010723
0x1800106dc  cmp     ecx, 1
0x1800106df  jz      short loc_1800106FF
0x1800106e1  mov     edx, 6F6h; void *
0x1800106e6  mov     ebx, 80070057h
0x1800106eb  mov     rcx, [rbp+18h]; this
0x1800106ef  mov     r9d, ebx; char *
0x1800106f2  mov     r8, r15; unsigned int
0x1800106f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800106fa  jmp     loc_1800108D9
0x1800106ff  mov     rax, [rdi+8]
0x180010703  cmp     qword ptr [rax], 0
0x180010707  jz      short loc_180010710
0x180010709  mov     edx, 6F2h
0x18001070e  jmp     short loc_1800106E6
0x180010710  lea     rdi, aMicrosoftWindo; "\\Microsoft\\Windows\\CertificateServic"...
0x180010717  lea     rsi, aAikcertenroll; "AIKCertEnroll"
0x18001071e  jmp     loc_180010883
0x180010723  mov     rax, [rdi+8]
0x180010727  cmp     qword ptr [rax], 0
0x18001072b  jz      loc_18001082A
0x180010731  mov     dword ptr [rbp+arg_0], 0
0x180010738  mov     [rbp+hMem], 0
0x180010740  lea     rax, [rbp+hMem]
0x180010744  mov     [rbp+var_20], rax
0x180010748  mov     [rbp+var_18], 0
0x180010750  mov     ebx, 1
0x180010755  mov     [rbp+var_10], bl
0x180010758  mov     [rbp+var_2C], ebx
0x18001075b  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18001075f  lea     rcx, [rbp+var_18]; this
0x180010763  call    ?GetSrkHash@NgcUtils@@YAJPEAPEAEPEAK@Z; NgcUtils::GetSrkHash(uchar * *,ulong *)
0x180010768  mov     esi, eax
0x18001076a  and     ebx, 0FFFFFFFEh
0x18001076d  mov     [rbp+var_2C], ebx
0x180010770  lea     rcx, [rbp+var_20]
0x180010774  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180010779  test    esi, esi
0x18001077b  jns     short loc_1800107B0
0x18001077d  mov     rcx, [rbp+18h]; this
0x180010781  mov     r9d, esi; char *
0x180010784  mov     r8, r15; unsigned int
0x180010787  mov     edx, 6DCh; void *
0x18001078c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010791  nop
0x180010792  mov     rcx, [rbp+hMem]; hMem
0x180010796  mov     [rbp+hMem], 0
0x18001079e  test    rcx, rcx
0x1800107a1  jz      short loc_1800107A9
0x1800107a3  call    cs:__imp_LocalFree
0x1800107a9  mov     eax, esi
0x1800107ab  jmp     loc_1800108DB
0x1800107b0  mov     rax, [rdi+10h]
0x1800107b4  mov     ecx, [rax]
0x1800107b6  cmp     dword ptr [rbp+arg_0], ecx
0x1800107b9  jz      short loc_1800107C2
0x1800107bb  mov     edx, 6DEh
0x1800107c0  jmp     short loc_1800107DE
0x1800107c2  mov     r8, rcx; Size
0x1800107c5  mov     rdx, [rdi+8]
0x1800107c9  mov     rdx, [rdx]; Buf2
0x1800107cc  mov     rcx, [rbp+hMem]; Buf1
0x1800107d0  call    memcmp_0
0x1800107d5  test    eax, eax
0x1800107d7  jz      short loc_180010813
0x1800107d9  mov     edx, 6DFh; void *
0x1800107de  mov     ebx, 80070057h
0x1800107e3  mov     r9d, ebx; char *
0x1800107e6  mov     r8, r15; unsigned int
0x1800107e9  mov     rcx, [rbp+18h]; this
0x1800107ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800107f2  nop
0x1800107f3  mov     rcx, [rbp+hMem]; hMem
0x1800107f7  test    rcx, rcx
0x1800107fa  mov     [rbp+hMem], 0
0x180010802  jz      loc_1800108D9
0x180010808  call    cs:__imp_LocalFree
0x18001080e  jmp     loc_1800108D9
0x180010813  mov     rcx, [rbp+hMem]; hMem
0x180010817  mov     [rbp+hMem], 0
0x18001081f  test    rcx, rcx
0x180010822  jz      short loc_18001082A
0x180010824  call    cs:__imp_LocalFree
0x18001082a  call    ?IsSecureBioEnabled@NgcUtils@@YA_NXZ; NgcUtils::IsSecureBioEnabled(void)
0x18001082f  test    al, al
0x180010831  jnz     short loc_18001083C
0x180010833  call    ?IsNgcInVsmEnabled@NgcUtils@@YA_NXZ; NgcUtils::IsNgcInVsmEnabled(void)
0x180010838  test    al, al
0x18001083a  jz      short loc_180010875
0x18001083c  mov     qword ptr [rsp+60h+var_40], 0; int
0x180010845  xor     r9d, r9d
0x180010848  xor     r8d, r8d
0x18001084b  xor     edx, edx
0x18001084d  mov     rcx, cs:WNF_NGC_PREGEN_NGCISOCTNR_TRIGGER
0x180010854  call    cs:__imp_RtlPublishWnfStateData
0x18001085a  or      eax, 10000000h
0x18001085f  mov     rcx, [rbp+18h]; this
0x180010863  jge     short loc_180010875
0x180010865  mov     r9d, eax; char *
0x180010868  mov     r8, r15; unsigned int
0x18001086b  mov     edx, 6E6h; void *
0x180010870  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010875  lea     rdi, aMicrosoftWindo_1; "\\Microsoft\\Windows\\CertificateServic"...
0x18001087c  lea     rsi, aNgckeypregen; "NGCKeyPreGen"
0x180010883  xor     edx, edx; dwCoInit
0x180010885  xor     ecx, ecx; pvReserved
0x180010887  call    cs:__imp_CoInitializeEx
0x18001088d  mov     ebx, eax
0x18001088f  test    eax, eax
0x180010891  jns     short loc_18001089D
0x180010893  mov     edx, 6FBh
0x180010898  jmp     loc_1800106EB
0x18001089d  lea     rcx, [rbp+var_30]
0x1800108a1  call    wil__ScopeExitIgnore__lambda_0f94373613415aef655645707f91be66___
0x1800108a6  nop
0x1800108a7  mov     rdx, rsi; unsigned __int16 *
0x1800108aa  mov     rcx, rdi; unsigned __int16 *
0x1800108ad  call    ?RunOobeTask@@YAJPEBG0@Z; RunOobeTask(ushort const *,ushort const *)
0x1800108b2  mov     ebx, eax
0x1800108b4  test    eax, eax
0x1800108b6  jns     short loc_1800108CE
0x1800108b8  mov     rcx, [rbp+18h]; this
0x1800108bc  mov     r9d, eax; char *
0x1800108bf  mov     r8, r15; unsigned int
0x1800108c2  mov     edx, 705h; void *
0x1800108c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800108cc  jmp     short loc_1800108D0
0x1800108ce  xor     ebx, ebx
0x1800108d0  lea     rcx, [rbp+var_30]
0x1800108d4  call    wil__details__ScopeExitFnGuard__lambda_0f94373613415aef655645707f91be66_____operator__
0x1800108d9  mov     eax, ebx
0x1800108db  lea     r11, [rsp+60h+var_s0]
0x1800108e0  mov     rbx, [r11+28h]
0x1800108e4  mov     rsi, [r11+30h]
0x1800108e8  mov     rsp, r11
0x1800108eb  pop     r15
0x1800108ed  pop     rdi
0x1800108ee  pop     rbp
0x1800108ef  retn
```
