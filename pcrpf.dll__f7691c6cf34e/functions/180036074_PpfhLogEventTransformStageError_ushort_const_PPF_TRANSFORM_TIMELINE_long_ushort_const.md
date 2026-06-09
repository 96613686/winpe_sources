# PpfhLogEventTransformStageError(ushort const *,PPF_TRANSFORM_TIMELINE,long,ushort const *)

- ea: `0x180036074`
- end: `0x18003621c`
- name: `?PpfhLogEventTransformStageError@@YAJPEBGW4PPF_TRANSFORM_TIMELINE@@J0@Z`
- size: `424`
- prototype: `int __fastcall(const unsigned __int16 *, int, int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18001bab0`
- `0x18001bb90`

## callees

- `0x180003270`
- `0x180003cf0`
- `0x180009c64`
- `0x18000dfe0`
- `0x18001aff0`
- `0x18003535c`
- `0x180036074`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18003611b`
- `ntdll!EtwEventWrite` at `0x1800361d0`
- `ntdll!EtwEventWrite` at `0x18003611b`
- `ntdll!EtwEventWrite` at `0x1800361d0`

## pseudocode

```c
int __fastcall PpfhLogEventTransformStageError(const unsigned __int16 *a1, int a2, int a3, const unsigned __int16 *a4)
{
  int v7; // ebx
  __int64 v8; // rdx
  unsigned int v9; // eax
  __int64 v10; // rdx
  int v12[4]; // [rsp+20h] [rbp-60h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+30h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+40h] [rbp-40h] BYREF
  __int128 v15; // [rsp+50h] [rbp-30h]
  int *v16; // [rsp+60h] [rbp-20h]
  __int64 v17; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  int v19; // [rsp+B0h] [rbp+30h] BYREF

  v19 = a3;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl'::`2'::impl) )
  {
    memset_0(&v13, 0, 0x40u);
    if ( !a4 )
      a4 = L"Default";
    v7 = InitializeEventDataDescWithStr(&v13, a4);
    if ( v7 < 0 )
    {
      v8 = 222;
      goto LABEL_10;
    }
    v7 = InitializeEventDataDescWithStr(&v14, a1);
    if ( v7 < 0 )
    {
      v8 = 223;
      goto LABEL_10;
    }
    *(_QWORD *)&v15 = v12;
    v12[0] = a2;
    v16 = &v19;
    *((_QWORD *)&v15 + 1) = 4;
    v17 = 4;
    v9 = EtwEventWrite(g_eventProvider, PCRPF_EVENT_TRANSFORM_STAGE_ERROR_V2, 4, &v13);
    if ( v9 )
    {
      v10 = 228;
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v10,
               (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
               (const char *)v9,
               v12[0]);
    }
  }
  else
  {
    v13 = 0;
    v14 = 0;
    v15 = 0;
    v7 = InitializeEventDataDescWithStr(&v13, a1);
    if ( v7 < 0 )
    {
      v8 = 234;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
        (const char *)(unsigned int)v7,
        v12[0]);
      return v7;
    }
    v14.Ptr = (ULONGLONG)v12;
    v12[0] = a2;
    *(_QWORD *)&v15 = &v19;
    *(_QWORD *)&v14.Size = 4;
    *((_QWORD *)&v15 + 1) = 4;
    v9 = EtwEventWrite(g_eventProvider, PCRPF_EVENT_TRANSFORM_STAGE_ERROR, 3, &v13);
    if ( v9 )
    {
      v10 = 239;
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v10,
               (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
               (const char *)v9,
               v12[0]);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180036074  mov     [rsp-18h+arg_8], rbx
0x180036079  mov     [rsp-18h+arg_10], r8d
0x18003607e  push    rbp
0x18003607f  push    rsi
0x180036080  push    rdi
0x180036081  mov     rbp, rsp
0x180036084  sub     rsp, 80h
0x18003608b  mov     rax, cs:__security_cookie
0x180036092  xor     rax, rsp
0x180036095  mov     [rbp+var_10], rax
0x180036099  mov     rbx, r9
0x18003609c  mov     esi, edx
0x18003609e  mov     rdi, rcx
0x1800360a1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration> `wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl(void)'::`2'::impl
0x1800360a8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled(void)
0x1800360ad  test    al, al
0x1800360af  jnz     loc_180036139
0x1800360b5  xorps   xmm0, xmm0
0x1800360b8  lea     rcx, [rbp+var_50]; struct _EVENT_DATA_DESCRIPTOR *
0x1800360bc  mov     rdx, rdi; unsigned __int16 *
0x1800360bf  movups  xmmword ptr [rbp+var_50.Ptr], xmm0
0x1800360c3  movups  xmmword ptr [rbp+var_40.Ptr], xmm0
0x1800360c7  movups  [rbp+var_30], xmm0
0x1800360cb  call    ?InitializeEventDataDescWithStr@@YAJPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; InitializeEventDataDescWithStr(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x1800360d0  mov     ebx, eax
0x1800360d2  test    eax, eax
0x1800360d4  jns     short loc_1800360E0
0x1800360d6  mov     edx, 0EAh
0x1800360db  jmp     loc_18003616D
0x1800360e0  mov     rcx, cs:?g_eventProvider@@3_KA; unsigned __int64 g_eventProvider
0x1800360e7  lea     rax, [rbp+var_60]
0x1800360eb  mov     [rbp+var_40.Ptr], rax
0x1800360ef  lea     r9, [rbp+var_50]
0x1800360f3  lea     rax, [rbp+arg_10]
0x1800360f7  mov     [rbp+var_60], esi
0x1800360fa  mov     r8d, 3
0x180036100  mov     qword ptr [rbp+var_30], rax
0x180036104  lea     rdx, PCRPF_EVENT_TRANSFORM_STAGE_ERROR
0x18003610b  mov     qword ptr [rbp+var_40.Size], 4
0x180036113  mov     qword ptr [rbp+var_30+8], 4
0x18003611b  call    cs:__imp_EtwEventWrite
0x180036122  nop     dword ptr [rax+rax+00h]
0x180036127  test    eax, eax
0x180036129  jz      loc_1800361FA
0x18003612f  mov     edx, 0EFh
0x180036134  jmp     loc_1800361E5
0x180036139  xor     edx, edx; Val
0x18003613b  lea     rcx, [rbp+var_50]; void *
0x18003613f  lea     r8d, [rdx+40h]; Size
0x180036143  call    memset_0
0x180036148  lea     rax, aDefault; "Default"
0x18003614f  test    rbx, rbx
0x180036152  lea     rcx, [rbp+var_50]; struct _EVENT_DATA_DESCRIPTOR *
0x180036156  cmovz   rbx, rax
0x18003615a  mov     rdx, rbx; unsigned __int16 *
0x18003615d  call    ?InitializeEventDataDescWithStr@@YAJPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; InitializeEventDataDescWithStr(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180036162  mov     ebx, eax
0x180036164  test    eax, eax
0x180036166  jns     short loc_180036184
0x180036168  mov     edx, 0DEh; void *
0x18003616d  mov     rcx, [rbp+18h]; this
0x180036171  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180036178  mov     r9d, ebx; char *
0x18003617b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036180  mov     eax, ebx
0x180036182  jmp     short loc_1800361FC
0x180036184  mov     rdx, rdi; unsigned __int16 *
0x180036187  lea     rcx, [rbp+var_40]; struct _EVENT_DATA_DESCRIPTOR *
0x18003618b  call    ?InitializeEventDataDescWithStr@@YAJPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; InitializeEventDataDescWithStr(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180036190  mov     ebx, eax
0x180036192  test    eax, eax
0x180036194  jns     short loc_18003619D
0x180036196  mov     edx, 0DFh
0x18003619b  jmp     short loc_18003616D
0x18003619d  mov     rcx, cs:?g_eventProvider@@3_KA; unsigned __int64 g_eventProvider
0x1800361a4  lea     rax, [rbp+var_60]
0x1800361a8  mov     r8d, 4
0x1800361ae  mov     qword ptr [rbp+var_30], rax
0x1800361b2  lea     rax, [rbp+arg_10]
0x1800361b6  mov     [rbp+var_60], esi
0x1800361b9  lea     r9, [rbp+var_50]
0x1800361bd  mov     [rbp+var_20], rax
0x1800361c1  lea     rdx, PCRPF_EVENT_TRANSFORM_STAGE_ERROR_V2
0x1800361c8  mov     qword ptr [rbp+var_30+8], r8
0x1800361cc  mov     [rbp+var_18], r8
0x1800361d0  call    cs:__imp_EtwEventWrite
0x1800361d7  nop     dword ptr [rax+rax+00h]
0x1800361dc  test    eax, eax
0x1800361de  jz      short loc_1800361FA
0x1800361e0  mov     edx, 0E4h; void *
0x1800361e5  mov     rcx, [rbp+18h]; this
0x1800361e9  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x1800361f0  mov     r9d, eax; char *
0x1800361f3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800361f8  jmp     short loc_1800361FC
0x1800361fa  xor     eax, eax
0x1800361fc  mov     rcx, [rbp+var_10]
0x180036200  xor     rcx, rsp; StackCookie
0x180036203  call    __security_check_cookie
0x180036208  mov     rbx, [rsp+80h+arg_8]
0x180036210  add     rsp, 80h
0x180036217  pop     rdi
0x180036218  pop     rsi
0x180036219  pop     rbp
0x18003621a  retn
```
