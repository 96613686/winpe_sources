# CTouchHandlerImpl::InitICM(void)

- ea: `0x1800089d0`
- end: `0x180008d72`
- name: `?InitICM@CTouchHandlerImpl@@UEAAJXZ`
- size: `930`
- prototype: `__int64 __fastcall(CTouchHandlerImpl *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180008134`
- `0x180008820`
- `0x1800089d0`
- `0x180008d78`
- `0x180009514`
- `0x18000958c`
- `0x18013ce80`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008abd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008b07`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008b51`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008abd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008b07`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008b51`
- `NInput!CreateInteractionContext` at `0x180008ca7`
- `NInput!CreateInteractionContext` at `0x180008ca7`
- `NInput!RegisterOutputCallbackInteractionContext` at `0x180008cca`
- `NInput!RegisterOutputCallbackInteractionContext` at `0x180008cca`
- `NInput!SetInteractionConfigurationInteractionContext` at `0x180008d04`
- `NInput!SetInteractionConfigurationInteractionContext` at `0x180008d04`
- `NInput!SetPropertyInteractionContext` at `0x180008c16`
- `NInput!SetPropertyInteractionContext` at `0x180008d1f`
- `NInput!SetPropertyInteractionContext` at `0x180008d3b`
- `NInput!SetPropertyInteractionContext` at `0x180008c16`
- `NInput!SetPropertyInteractionContext` at `0x180008d1f`
- `NInput!SetPropertyInteractionContext` at `0x180008d3b`

## pseudocode

```c
__int64 __fastcall CTouchHandlerImpl::InitICM(CTouchHandlerImpl *this)
{
  __int64 v2; // rax
  void ***v3; // rbx
  _QWORD *v4; // r14
  struct CTlsGrippers *v5; // rsi
  struct IHandleInputProcessor *Instance; // rax
  int InteractionContext; // ebx
  __int64 v9; // rcx
  __int64 v10; // rdx
  _QWORD *v11; // rsi
  __int64 v12; // rcx
  __int64 v13; // rcx
  int pvData; // [rsp+40h] [rbp-30h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-2Ch] BYREF
  int v16; // [rsp+48h] [rbp-28h] BYREF
  int v17; // [rsp+4Ch] [rbp-24h] BYREF
  __m128i si128; // [rsp+50h] [rbp-20h] BYREF
  int v19; // [rsp+60h] [rbp-10h]
  int v20; // [rsp+64h] [rbp-Ch]

  pcbData = 4;
  pvData = 0;
  CTouchHandlerImpl::UpdateGripperScalingMode(this);
  v2 = *((_QWORD *)this + 6);
  v3 = &CITextHost2Ref::s_dummyHost;
  v4 = (_QWORD *)((char *)this + 40);
  if ( *(_QWORD *)(v2 + 112) )
    v3 = *(void ****)(v2 + 112);
  if ( !*v4 )
    ((void (__fastcall *)(void ***, GUID *, char *))**v3)(v3, &IID_IGripperHost2, (char *)this + 40);
  v5 = CTlsGrippers::Instance();
  if ( *v4 )
  {
    if ( !*((_QWORD *)v5 + 40) )
    {
      *((_QWORD *)v5 + 40) = *v4;
      *((_QWORD *)v5 + 41) = v3;
      v9 = *v4;
      v16 = 0;
      v17 = 0;
      if ( (*(int (__fastcall **)(__int64, int *, int *))(*(_QWORD *)v9 + 56LL))(v9, &v17, &v16) < 0 )
        MEMORY[0] = 1;
      v10 = *((unsigned int *)this + 17);
      v16 -= v17;
      CGripperMetrics::UpdateMetrics((char *)v5 + 272, v10);
    }
  }
  else if ( (unsigned __int8)CGripperMetrics::UpdateMetrics((char *)v5 + 272, *((unsigned int *)this + 17)) )
  {
    *((_BYTE *)v5 + 100) = 1;
    *((_BYTE *)v5 + 236) = 1;
  }
  if ( *((_QWORD *)this + 14) )
  {
    InteractionContext = -2147418113;
LABEL_31:
    v13 = *((_QWORD *)this + 14);
    if ( v13 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 40LL))(v13, 1);
    *((_QWORD *)this + 14) = 0;
    return (unsigned int)InteractionContext;
  }
  Instance = IHandleInputProcessor::s_CreateInstance();
  *((_QWORD *)this + 14) = Instance;
  if ( !Instance )
  {
    InteractionContext = -2147024882;
    goto LABEL_31;
  }
  InteractionContext = 0;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Input\\Settings",
          L"AutoScrollThreshold",
          0x10u,
          0,
          &pvData,
          &pcbData) )
    *((_DWORD *)this + 55) = pvData;
  pcbData = 4;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Input\\Settings",
          L"AutoScrollTopZone",
          0x10u,
          0,
          &pvData,
          &pcbData) )
    *((_DWORD *)this + 56) = pvData;
  pcbData = 4;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Input\\Settings",
          L"AutoScrollBottomZone",
          0x10u,
          0,
          &pvData,
          &pcbData) )
    *((_DWORD *)this + 57) = pvData;
  (***((void (__fastcall ****)(_QWORD))this + 14))(*((_QWORD *)this + 14));
  if ( !*((_QWORD *)v5 + 40) )
  {
    v11 = (_QWORD *)((char *)this + 8);
    InteractionContext = CreateInteractionContext((char *)this + 8);
    if ( InteractionContext < 0 )
      goto LABEL_31;
    InteractionContext = RegisterOutputCallbackInteractionContext(*v11, CTouchTracker::OutputCallback, this);
    if ( InteractionContext < 0 )
      goto LABEL_31;
    v12 = *v11;
    v19 = 4;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v20 = 1;
    InteractionContext = SetInteractionConfigurationInteractionContext(v12, 3, &si128);
    if ( InteractionContext < 0 )
      goto LABEL_31;
    InteractionContext = SetPropertyInteractionContext(*v11, 1, 1);
    if ( InteractionContext < 0 )
      goto LABEL_31;
    InteractionContext = SetPropertyInteractionContext(*v11, 2, 1);
    if ( InteractionContext < 0 )
      goto LABEL_31;
    InteractionContext = SetPropertyInteractionContext(*v11, 3, 0);
    if ( InteractionContext < 0 )
      goto LABEL_31;
  }
  return (unsigned int)InteractionContext;
}

```

## disassembly

```asm
0x1800089d0  mov     [rsp-28h+arg_8], rbx
0x1800089d5  mov     [rsp-28h+arg_10], rsi
0x1800089da  push    rbp
0x1800089db  push    rdi
0x1800089dc  push    r12
0x1800089de  push    r14
0x1800089e0  push    r15
0x1800089e2  mov     rbp, rsp
0x1800089e5  sub     rsp, 70h
0x1800089e9  mov     rax, cs:__security_cookie
0x1800089f0  xor     rax, rsp
0x1800089f3  mov     [rbp+var_8], rax
0x1800089f7  xor     r15d, r15d
0x1800089fa  mov     [rbp+var_2C], 4
0x180008a01  mov     [rbp+var_30], r15d
0x180008a05  mov     rdi, rcx
0x180008a08  call    ?UpdateGripperScalingMode@CTouchHandlerImpl@@IEAAXXZ; CTouchHandlerImpl::UpdateGripperScalingMode(void)
0x180008a0d  mov     rax, [rdi+30h]
0x180008a11  lea     rbx, ?s_dummyHost@CITextHost2Ref@@0VCDummyHost@@A; CDummyHost CITextHost2Ref::s_dummyHost
0x180008a18  lea     r14, [rdi+28h]
0x180008a1c  cmp     [rax+70h], r15
0x180008a20  cmovnz  rbx, [rax+70h]
0x180008a25  cmp     [r14], r15
0x180008a28  jnz     short loc_180008A42
0x180008a2a  mov     rax, [rbx]
0x180008a2d  lea     rdx, IID_IGripperHost2
0x180008a34  mov     r8, r14
0x180008a37  mov     rcx, rbx
0x180008a3a  mov     rax, [rax]
0x180008a3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a42  call    ?Instance@CTlsGrippers@@SAPEAV1@XZ; CTlsGrippers::Instance(void)
0x180008a47  mov     rsi, rax
0x180008a4a  mov     r12d, 1
0x180008a50  mov     rax, [r14]
0x180008a53  test    rax, rax
0x180008a56  jz      loc_180008C3B
0x180008a5c  cmp     [rsi+140h], r15
0x180008a63  jz      loc_180008BB9
0x180008a69  cmp     [rdi+70h], r15
0x180008a6d  jnz     loc_180008C62
0x180008a73  call    ?s_CreateInstance@IHandleInputProcessor@@SAPEAV1@XZ; IHandleInputProcessor::s_CreateInstance(void)
0x180008a78  mov     [rdi+70h], rax
0x180008a7c  test    rax, rax
0x180008a7f  jz      loc_180008C6C
0x180008a85  lea     rax, [rbp+var_2C]
0x180008a89  mov     r14d, 10h
0x180008a8f  mov     [rsp+70h+pcbData], rax; pcbData
0x180008a94  lea     r8, aAutoscrollthre; "AutoScrollThreshold"
0x180008a9b  lea     rax, [rbp+var_30]
0x180008a9f  mov     r9d, r14d; dwFlags
0x180008aa2  mov     [rsp+70h+pvData], rax; pvData
0x180008aa7  lea     rdx, SubKey; "Software\\Microsoft\\Input\\Settings"
0x180008aae  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180008ab5  mov     [rsp+70h+pdwType], r15; pdwType
0x180008aba  mov     ebx, r15d
0x180008abd  call    cs:__imp_RegGetValueW
0x180008ac4  nop     dword ptr [rax+rax+00h]
0x180008ac9  test    eax, eax
0x180008acb  jz      loc_180008C76
0x180008ad1  lea     rax, [rbp+var_2C]
0x180008ad5  mov     [rbp+var_2C], 4
0x180008adc  mov     [rsp+70h+pcbData], rax; pcbData
0x180008ae1  lea     r8, aAutoscrolltopz; "AutoScrollTopZone"
0x180008ae8  lea     rax, [rbp+var_30]
0x180008aec  mov     r9d, r14d; dwFlags
0x180008aef  mov     [rsp+70h+pvData], rax; pvData
0x180008af4  lea     rdx, SubKey; "Software\\Microsoft\\Input\\Settings"
0x180008afb  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180008b02  mov     [rsp+70h+pdwType], r15; pdwType
0x180008b07  call    cs:__imp_RegGetValueW
0x180008b0e  nop     dword ptr [rax+rax+00h]
0x180008b13  test    eax, eax
0x180008b15  jz      loc_180008C84
0x180008b1b  lea     rax, [rbp+var_2C]
0x180008b1f  mov     [rbp+var_2C], 4
0x180008b26  mov     [rsp+70h+pcbData], rax; pcbData
0x180008b2b  lea     r8, aAutoscrollbott; "AutoScrollBottomZone"
0x180008b32  lea     rax, [rbp+var_30]
0x180008b36  mov     r9d, r14d; dwFlags
0x180008b39  mov     [rsp+70h+pvData], rax; pvData
0x180008b3e  lea     rdx, SubKey; "Software\\Microsoft\\Input\\Settings"
0x180008b45  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180008b4c  mov     [rsp+70h+pdwType], r15; pdwType
0x180008b51  call    cs:__imp_RegGetValueW
0x180008b58  nop     dword ptr [rax+rax+00h]
0x180008b5d  test    eax, eax
0x180008b5f  jz      loc_180008C92
0x180008b65  movss   xmm1, cs:__real@451ec000
0x180008b6d  mov     rcx, [rdi+70h]
0x180008b71  divss   xmm1, dword ptr [rsi+114h]
0x180008b79  mov     rax, [rcx]
0x180008b7c  mov     rax, [rax]
0x180008b7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b84  cmp     [rsi+140h], r15
0x180008b8b  jz      loc_180008CA0
0x180008b91  mov     eax, ebx
0x180008b93  mov     rcx, [rbp+var_8]
0x180008b97  xor     rcx, rsp; StackCookie
0x180008b9a  call    __security_check_cookie
0x180008b9f  lea     r11, [rsp+70h+var_s0]
0x180008ba4  mov     rbx, [r11+38h]
0x180008ba8  mov     rsi, [r11+40h]
0x180008bac  mov     rsp, r11
0x180008baf  pop     r15
0x180008bb1  pop     r14
0x180008bb3  pop     r12
0x180008bb5  pop     rdi
0x180008bb6  pop     rbp
0x180008bb7  retn
0x180008bb9  mov     [rsi+140h], rax
0x180008bc0  lea     r8, [rbp+var_28]
0x180008bc4  mov     [rsi+148h], rbx
0x180008bcb  lea     rdx, [rbp+var_24]
0x180008bcf  mov     rcx, [r14]
0x180008bd2  mov     [rbp+var_28], r15d
0x180008bd6  mov     [rbp+var_24], r15d
0x180008bda  mov     rax, [rcx]
0x180008bdd  mov     rax, [rax+38h]
0x180008be1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008be6  test    eax, eax
0x180008be8  js      short loc_180008C31
0x180008bea  mov     r9d, [rbp+var_28]
0x180008bee  lea     rcx, [rsi+110h]
0x180008bf5  mov     r8d, [rbp+var_24]
0x180008bf9  sub     r9d, r8d
0x180008bfc  mov     edx, [rdi+44h]
0x180008bff  mov     [rbp+var_28], r9d
0x180008c03  call    ?UpdateMetrics@CGripperMetrics@@QEAA_NW4TOUCH_HANDLE_SCALING_MODE@@HH@Z; CGripperMetrics::UpdateMetrics(TOUCH_HANDLE_SCALING_MODE,int,int)
0x180008c08  jmp     loc_180008A69
0x180008c0d  mov     rcx, [rsi]
0x180008c10  xor     r8d, r8d
0x180008c13  mov     edx, r14d
0x180008c16  call    cs:__imp_SetPropertyInteractionContext
0x180008c1d  nop     dword ptr [rax+rax+00h]
0x180008c22  mov     ebx, eax
0x180008c24  test    eax, eax
0x180008c26  jns     loc_180008B91
0x180008c2c  jmp     loc_180008D51
0x180008c31  mov     ds:0, r12d
0x180008c39  jmp     short loc_180008BEA
0x180008c3b  mov     edx, [rdi+44h]
0x180008c3e  lea     rcx, [rsi+110h]
0x180008c45  call    ?UpdateMetrics@CGripperMetrics@@QEAA_NW4TOUCH_HANDLE_SCALING_MODE@@@Z; CGripperMetrics::UpdateMetrics(TOUCH_HANDLE_SCALING_MODE)
0x180008c4a  test    al, al
0x180008c4c  jz      loc_180008A69
0x180008c52  mov     [rsi+64h], r12b
0x180008c56  mov     [rsi+0ECh], r12b
0x180008c5d  jmp     loc_180008A69
0x180008c62  mov     ebx, 8000FFFFh
0x180008c67  jmp     loc_180008D51
0x180008c6c  mov     ebx, 8007000Eh
0x180008c71  jmp     loc_180008D51
0x180008c76  mov     eax, [rbp+var_30]
0x180008c79  mov     [rdi+0DCh], eax
0x180008c7f  jmp     loc_180008AD1
0x180008c84  mov     eax, [rbp+var_30]
0x180008c87  mov     [rdi+0E0h], eax
0x180008c8d  jmp     loc_180008B1B
0x180008c92  mov     eax, [rbp+var_30]
0x180008c95  mov     [rdi+0E4h], eax
0x180008c9b  jmp     loc_180008B65
0x180008ca0  lea     rsi, [rdi+8]
0x180008ca4  mov     rcx, rsi
0x180008ca7  call    cs:__imp_CreateInteractionContext
0x180008cae  nop     dword ptr [rax+rax+00h]
0x180008cb3  mov     ebx, eax
0x180008cb5  test    eax, eax
0x180008cb7  js      loc_180008D51
0x180008cbd  mov     rcx, [rsi]
0x180008cc0  lea     rdx, ?OutputCallback@CTouchTracker@@KAXPEAXPEBUINTERACTION_CONTEXT_OUTPUT@@@Z; CTouchTracker::OutputCallback(void *,INTERACTION_CONTEXT_OUTPUT const *)
0x180008cc7  mov     r8, rdi
0x180008cca  call    cs:__imp_RegisterOutputCallbackInteractionContext
0x180008cd1  nop     dword ptr [rax+rax+00h]
0x180008cd6  mov     ebx, eax
0x180008cd8  test    eax, eax
0x180008cda  js      short loc_180008D51
0x180008cdc  movdqa  xmm0, cs:__xmm@00000001000000030000000300000002
0x180008ce4  lea     r8, [rbp+var_20]
0x180008ce8  mov     rcx, [rsi]
0x180008ceb  mov     r14d, 3
0x180008cf1  mov     edx, r14d
0x180008cf4  mov     [rbp+var_10], 4
0x180008cfb  movdqu  [rbp+var_20], xmm0
0x180008d00  mov     [rbp+var_C], r12d
0x180008d04  call    cs:__imp_SetInteractionConfigurationInteractionContext
0x180008d0b  nop     dword ptr [rax+rax+00h]
0x180008d10  mov     ebx, eax
0x180008d12  test    eax, eax
0x180008d14  js      short loc_180008D51
0x180008d16  mov     rcx, [rsi]
0x180008d19  mov     r8d, r12d
0x180008d1c  mov     edx, r12d
0x180008d1f  call    cs:__imp_SetPropertyInteractionContext
0x180008d26  nop     dword ptr [rax+rax+00h]
0x180008d2b  mov     ebx, eax
0x180008d2d  test    eax, eax
0x180008d2f  js      short loc_180008D51
0x180008d31  mov     rcx, [rsi]
0x180008d34  lea     edx, [r14-1]
0x180008d38  mov     r8d, r12d
0x180008d3b  call    cs:__imp_SetPropertyInteractionContext
0x180008d42  nop     dword ptr [rax+rax+00h]
0x180008d47  mov     ebx, eax
0x180008d49  test    eax, eax
0x180008d4b  jns     loc_180008C0D
0x180008d51  mov     rcx, [rdi+70h]
0x180008d55  test    rcx, rcx
0x180008d58  jz      short loc_180008D69
0x180008d5a  mov     rax, [rcx]
0x180008d5d  mov     edx, r12d
0x180008d60  mov     rax, [rax+28h]
0x180008d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d69  mov     [rdi+70h], r15
0x180008d6d  jmp     loc_180008B91
```
