# _ApiTracingDataCollector::put_ExcludeApis(tagSAFEARRAY *)

- ea: `0x180065830`
- end: `0x180065b7a`
- name: `?put_ExcludeApis@_ApiTracingDataCollector@@UEAAJPEAUtagSAFEARRAY@@@Z`
- size: `842`
- prototype: `int(_ApiTracingDataCollector *__hidden this, struct tagSAFEARRAY *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x180065830`
- `0x18006e574`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180065b47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180065b47`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800658fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800658fe`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180065aaf`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180065ac4`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180065aaf`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180065ac4`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800659fb`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800659fb`

## pseudocode

```c
__int64 __fastcall _ApiTracingDataCollector::put_ExcludeApis(_ApiTracingDataCollector *this, struct tagSAFEARRAY *a2)
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
    EventingWriteEvent(
      (__int64)&g_Eventing,
      (__int64)&PLA_EVENT_METHOD,
      3,
      (__int64)"_ApiTracingDataCollector::put_ExcludeApis");
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
      EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENT_ERROR, 5, (__int64)v7);
      goto LABEL_34;
    }
  }
  v10 = (SAFEARRAY *)*((_QWORD *)this + 22);
  if ( !v10 || (v4 = SafeArrayDestroy(v10), v4 >= 0) )
  {
    *((_QWORD *)this + 22) = ppsaOut;
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
0x180065830  mov     [rsp-8+arg_10], rbx
0x180065835  mov     [rsp-8+arg_18], rsi
0x18006583a  push    rbp
0x18006583b  push    rdi
0x18006583c  push    r12
0x18006583e  push    r14
0x180065840  push    r15
0x180065842  lea     rbp, [rsp-120h]
0x18006584a  sub     rsp, 220h
0x180065851  mov     rax, cs:__security_cookie
0x180065858  xor     rax, rsp
0x18006585b  mov     [rbp+140h+var_30], rax
0x180065862  mov     eax, [rcx+38h]
0x180065865  xor     r14d, r14d
0x180065868  cmp     dword ptr cs:xmmword_180169738, r14d
0x18006586f  mov     rsi, rdx
0x180065872  mov     rdi, rcx
0x180065875  mov     [rsp+240h+var_1D0], eax
0x180065879  mov     ebx, r14d
0x18006587c  mov     [rbp+140h+ppsaOut], rcx
0x180065880  lea     r15d, [r14+4]
0x180065884  lea     r12d, [r14+2Ah]
0x180065888  jz      short loc_1800658F4
0x18006588a  mov     rdx, 4000000000000400h
0x180065894  test    qword ptr cs:xmmword_180169738+8, rdx
0x18006589b  jz      short loc_1800658F4
0x18006589d  mov     rax, cs:qword_180169748
0x1800658a4  and     rax, rdx
0x1800658a7  cmp     cs:qword_180169748, rax
0x1800658ae  jnz     short loc_1800658F4
0x1800658b0  mov     [rsp+240h+var_200], r15
0x1800658b5  lea     rax, [rsp+240h+var_1D0]
0x1800658ba  mov     [rsp+240h+var_208], rax
0x1800658bf  lea     r9, aApitracingdata_13; "_ApiTracingDataCollector::put_ExcludeAp"...
0x1800658c6  lea     rax, [rbp+140h+ppsaOut]
0x1800658ca  mov     [rsp+240h+var_210], 8
0x1800658d3  mov     [rsp+240h+var_218], rax
0x1800658d8  lea     r8d, [r14+3]
0x1800658dc  lea     rdx, PLA_EVENT_METHOD
0x1800658e3  mov     [rsp+240h+var_220], r12
0x1800658e8  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800658ef  call    EventingWriteEvent
0x1800658f4  cmp     [rdi+8], r14d
0x1800658f8  jz      short loc_180065904
0x1800658fa  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800658fe  call    cs:__imp_EnterCriticalSection
0x180065904  mov     [rbp+140h+ppsaOut], r14
0x180065908  test    rsi, rsi
0x18006590b  jz      loc_180065A9F
0x180065911  mov     rcx, rsi; psa
0x180065914  call    ?PlaiValidateSafeArray@@YAJPEAUtagSAFEARRAY@@@Z; PlaiValidateSafeArray(tagSAFEARRAY *)
0x180065919  mov     ebx, eax
0x18006591b  test    eax, eax
0x18006591d  jns     loc_1800659F4
0x180065923  cmp     dword ptr cs:xmmword_180169738, r14d
0x18006592a  mov     [rsp+240h+var_1D0], r14d
0x18006592f  mov     [rsp+240h+var_1C8], eax
0x180065933  jz      loc_180065B3D
0x180065939  mov     rdx, 4000000000000800h; unsigned __int64
0x180065943  test    qword ptr cs:xmmword_180169738+8, rdx
0x18006594a  jz      loc_180065B3D
0x180065950  mov     rax, cs:qword_180169748
0x180065957  and     rax, rdx
0x18006595a  cmp     cs:qword_180169748, rax
0x180065961  jnz     loc_180065B3D
0x180065967  lea     rcx, [rbp+140h+var_1B0]; unsigned __int16 *
0x18006596b  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180065970  lea     rcx, [rbp+140h+var_1B0]
0x180065974  or      rax, 0FFFFFFFFFFFFFFFFh
0x180065978  inc     rax
0x18006597b  cmp     [rcx+rax*2], r14w
0x180065980  jnz     short loc_180065978
0x180065982  lea     ecx, [rax+rax]
0x180065985  lea     rax, [rbp+140h+var_1B0]
0x180065989  add     rcx, 2
0x18006598d  mov     [rsp+240h+var_1E0], rcx
0x180065992  lea     r9, [rsp+240h+var_1C8]
0x180065997  mov     [rsp+240h+var_1E8], rax
0x18006599c  lea     rax, aApitracingdata_13; "_ApiTracingDataCollector::put_ExcludeAp"...
0x1800659a3  mov     [rsp+240h+var_1F0], r12
0x1800659a8  mov     [rsp+240h+var_1F8], rax
0x1800659ad  lea     rax, [rsp+240h+var_1D0]
0x1800659b2  mov     [rsp+240h+var_200], r15
0x1800659b7  lea     rdx, PLA_EVENT_ERROR
0x1800659be  mov     [rsp+240h+var_208], rax
0x1800659c3  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800659ca  lea     rax, byte_180147320
0x1800659d1  mov     [rsp+240h+var_210], 1
0x1800659da  mov     [rsp+240h+var_218], rax
0x1800659df  mov     r8d, 5
0x1800659e5  mov     [rsp+240h+var_220], r15
0x1800659ea  call    EventingWriteEvent
0x1800659ef  jmp     loc_180065B3D
0x1800659f4  lea     rdx, [rbp+140h+ppsaOut]; ppsaOut
0x1800659f8  mov     rcx, rsi; psa
0x1800659fb  call    cs:__imp_SafeArrayCopy
0x180065a01  mov     ebx, eax
0x180065a03  test    eax, eax
0x180065a05  jns     loc_180065A9F
0x180065a0b  cmp     dword ptr cs:xmmword_180169738, r14d
0x180065a12  mov     [rsp+240h+var_1C8], r14d
0x180065a17  mov     [rsp+240h+var_1D0], eax
0x180065a1b  jz      loc_180065B3D
0x180065a21  mov     rdx, 4000000000000800h; unsigned __int64
0x180065a2b  test    qword ptr cs:xmmword_180169738+8, rdx
0x180065a32  jz      loc_180065B3D
0x180065a38  mov     rax, cs:qword_180169748
0x180065a3f  and     rax, rdx
0x180065a42  cmp     cs:qword_180169748, rax
0x180065a49  jnz     loc_180065B3D
0x180065a4f  lea     rcx, [rbp+140h+var_130]; unsigned __int16 *
0x180065a53  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180065a58  lea     rcx, [rbp+140h+var_130]
0x180065a5c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180065a60  inc     rax
0x180065a63  cmp     [rcx+rax*2], r14w
0x180065a68  jnz     short loc_180065A60
0x180065a6a  lea     ecx, [rax+rax]
0x180065a6d  lea     rax, [rbp+140h+var_130]
0x180065a71  add     rcx, 2
0x180065a75  lea     r9, [rsp+240h+var_1D0]
0x180065a7a  mov     [rsp+240h+var_1E0], rcx
0x180065a7f  mov     [rsp+240h+var_1E8], rax
0x180065a84  lea     rax, aApitracingdata_13; "_ApiTracingDataCollector::put_ExcludeAp"...
0x180065a8b  mov     [rsp+240h+var_1F0], r12
0x180065a90  mov     [rsp+240h+var_1F8], rax
0x180065a95  lea     rax, [rsp+240h+var_1C8]
0x180065a9a  jmp     loc_1800659B2
0x180065a9f  mov     rcx, [rdi+0B0h]; psa
0x180065aa6  test    rcx, rcx
0x180065aa9  jz      loc_180065B32
0x180065aaf  call    cs:__imp_SafeArrayDestroy
0x180065ab5  mov     ebx, eax
0x180065ab7  test    eax, eax
0x180065ab9  jns     short loc_180065B32
0x180065abb  mov     rcx, [rbp+140h+ppsaOut]; psa
0x180065abf  test    rcx, rcx
0x180065ac2  jz      short loc_180065ACA
0x180065ac4  call    cs:__imp_SafeArrayDestroy
0x180065aca  cmp     dword ptr cs:xmmword_180169738, r14d
0x180065ad1  mov     [rsp+240h+var_1C8], r14d
0x180065ad6  mov     [rsp+240h+var_1D0], ebx
0x180065ada  jz      short loc_180065B3D
0x180065adc  mov     rdx, 4000000000000800h; unsigned __int64
0x180065ae6  test    qword ptr cs:xmmword_180169738+8, rdx
0x180065aed  jz      short loc_180065B3D
0x180065aef  mov     rax, cs:qword_180169748
0x180065af6  and     rax, rdx
0x180065af9  cmp     cs:qword_180169748, rax
0x180065b00  jnz     short loc_180065B3D
0x180065b02  lea     rcx, [rbp+140h+var_B0]; unsigned __int16 *
0x180065b09  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180065b0e  lea     rcx, [rbp+140h+var_B0]
0x180065b15  or      rax, 0FFFFFFFFFFFFFFFFh
0x180065b19  inc     rax
0x180065b1c  cmp     [rcx+rax*2], r14w
0x180065b21  jnz     short loc_180065B19
0x180065b23  lea     ecx, [rax+rax]
0x180065b26  lea     rax, [rbp+140h+var_B0]
0x180065b2d  jmp     loc_180065A71
0x180065b32  mov     rax, [rbp+140h+ppsaOut]
0x180065b36  mov     [rdi+0B0h], rax
0x180065b3d  cmp     [rdi+8], r14d
0x180065b41  jz      short loc_180065B4D
0x180065b43  lea     rcx, [rdi+10h]; lpCriticalSection
0x180065b47  call    cs:__imp_LeaveCriticalSection
0x180065b4d  mov     eax, ebx
0x180065b4f  mov     rcx, [rbp+140h+var_30]
0x180065b56  xor     rcx, rsp; StackCookie
0x180065b59  call    __security_check_cookie
0x180065b5e  lea     r11, [rsp+240h+var_20]
0x180065b66  mov     rbx, [r11+40h]
0x180065b6a  mov     rsi, [r11+48h]
0x180065b6e  mov     rsp, r11
0x180065b71  pop     r15
0x180065b73  pop     r14
0x180065b75  pop     r12
0x180065b77  pop     rdi
0x180065b78  pop     rbp
0x180065b79  retn
```
