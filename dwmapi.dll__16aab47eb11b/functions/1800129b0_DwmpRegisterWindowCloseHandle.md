# DwmpRegisterWindowCloseHandle

- ea: `0x1800129b0`
- end: `0x180012a91`
- name: `DwmpRegisterWindowCloseHandle`
- size: `225`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004d20`
- `0x18000b92c`
- `0x18001244c`
- `0x1800129b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800129f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800129f4`

## string_xrefs

- `0x180012a5a`: `clientcore\windows\dwm\dwmapi\composition.cpp`

## pseudocode

```c
__int64 __fastcall DwmpRegisterWindowCloseHandle(__int64 a1, __int64 a2, unsigned __int64 *a3)
{
  DWORD CurrentProcessId; // eax
  unsigned __int64 v8; // rbx
  CApiPortClient *v9; // rcx
  int v10; // edi
  __int64 v11; // rdx
  int v12[5]; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int64 v13; // [rsp+34h] [rbp-14h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned __int64 v15; // [rsp+68h] [rbp+20h] BYREF

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::GetImpl'::`2'::impl) )
    return 2147500033LL;
  *a3 = 0;
  CurrentProcessId = GetCurrentProcessId();
  *(_QWORD *)&v12[3] = a2;
  v15 = __PAIR64__(CurrentProcessId, _InterlockedIncrement(&dword_18001F858));
  v8 = v15;
  v13 = v15;
  v12[0] = 1073741972;
  *(_QWORD *)&v12[1] = a1;
  LODWORD(v15) = 0;
  v10 = CApiPortClient::SendRequestValidate(v9, v12, 0x1Cu, (int *)&v15);
  if ( v10 < 0 )
  {
    v11 = 577;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"clientcore\\windows\\dwm\\dwmapi\\composition.cpp",
      (const char *)(unsigned int)v10,
      v12[0]);
    return (unsigned int)v10;
  }
  v10 = v15;
  if ( (v15 & 0x80000000) != 0LL )
  {
    v11 = 578;
    goto LABEL_5;
  }
  *a3 = v8;
  return 0;
}

```

## disassembly

```asm
0x1800129b0  mov     [rsp+arg_0], rbx
0x1800129b5  mov     [rsp+arg_8], rsi
0x1800129ba  push    rdi
0x1800129bb  sub     rsp, 40h
0x1800129bf  mov     rsi, r8
0x1800129c2  mov     rbx, rdx
0x1800129c5  mov     rdi, rcx
0x1800129c8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows> `wil::Feature<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::GetImpl(void)'::`2'::impl
0x1800129cf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::__private_IsEnabled(void)
0x1800129d4  test    al, al
0x1800129d6  jnz     short loc_1800129E2
0x1800129d8  mov     eax, 80004001h
0x1800129dd  jmp     loc_180012A81
0x1800129e2  xorps   xmm0, xmm0
0x1800129e5  xor     eax, eax
0x1800129e7  movups  xmmword ptr [rsp+48h+var_28], xmm0
0x1800129ec  mov     [rsi], rax
0x1800129ef  movups  xmmword ptr [rsp+48h+var_28+0Ch], xmm0
0x1800129f4  call    cs:__imp_GetCurrentProcessId
0x1800129fa  mov     dword ptr [rsp+48h+arg_18+4], eax
0x1800129fe  mov     eax, 1
0x180012a03  lock xadd cs:dword_18001F858, eax
0x180012a0b  inc     eax
0x180012a0d  mov     qword ptr [rsp+48h+var_28+0Ch], rbx
0x180012a12  mov     dword ptr [rsp+48h+arg_18], eax
0x180012a16  lea     r9, [rsp+48h+arg_18]; int *
0x180012a1b  mov     rbx, [rsp+48h+arg_18]
0x180012a20  lea     rdx, [rsp+48h+var_28]; void *
0x180012a25  mov     r8d, 1Ch; unsigned __int64
0x180012a2b  mov     [rsp+48h+var_14], rbx
0x180012a30  mov     dword ptr [rsp+48h+var_28], 40000094h; int
0x180012a38  mov     qword ptr [rsp+48h+var_28+4], rdi
0x180012a3d  mov     dword ptr [rsp+48h+arg_18], 0
0x180012a45  call    ?SendRequestValidate@CApiPortClient@@QEAAJPEAX_KPEAJ@Z; CApiPortClient::SendRequestValidate(void *,unsigned __int64,long *)
0x180012a4a  mov     edi, eax
0x180012a4c  test    eax, eax
0x180012a4e  jns     short loc_180012A6D
0x180012a50  mov     edx, 241h; void *
0x180012a55  mov     rcx, [rsp+48h]; this
0x180012a5a  lea     r8, aClientcoreWind_0; "clientcore\\windows\\dwm\\dwmapi\\compo"...
0x180012a61  mov     r9d, edi; char *
0x180012a64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012a69  mov     eax, edi
0x180012a6b  jmp     short loc_180012A81
0x180012a6d  mov     edi, dword ptr [rsp+48h+arg_18]
0x180012a71  test    edi, edi
0x180012a73  jns     short loc_180012A7C
0x180012a75  mov     edx, 242h
0x180012a7a  jmp     short loc_180012A55
0x180012a7c  mov     [rsi], rbx
0x180012a7f  xor     eax, eax
0x180012a81  mov     rbx, [rsp+48h+arg_0]
0x180012a86  mov     rsi, [rsp+48h+arg_8]
0x180012a8b  add     rsp, 40h
0x180012a8f  pop     rdi
0x180012a90  retn
```
