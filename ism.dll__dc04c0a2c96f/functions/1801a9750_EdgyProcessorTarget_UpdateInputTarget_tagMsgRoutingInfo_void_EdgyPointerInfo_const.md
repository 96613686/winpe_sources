# EdgyProcessorTarget::UpdateInputTarget(tagMsgRoutingInfo,void *,EdgyPointerInfo const &)

- ea: `0x1801a9750`
- end: `0x1801a99bd`
- name: `?UpdateInputTarget@EdgyProcessorTarget@@QEAAJUtagMsgRoutingInfo@@PEAXAEBUEdgyPointerInfo@@@Z`
- size: `621`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1801a6fd0`
- `0x1801a897c`

## callees

- `0x18000dcd4`
- `0x180012b74`
- `0x180013e14`
- `0x180018804`
- `0x18002009c`
- `0x180024d08`
- `0x18004fdbc`
- `0x18008ead4`
- `0x1801a9750`
- `0x1801ce010`

## import_xrefs

- `win32u!NtCloseCompositionInputSink` at `0x1801a9834`
- `win32u!NtCloseCompositionInputSink` at `0x1801a995d`
- `win32u!NtCloseCompositionInputSink` at `0x1801a9834`
- `win32u!NtCloseCompositionInputSink` at `0x1801a995d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall EdgyProcessorTarget::UpdateInputTarget(__int64 a1, __int64 a2, __int64 a3, _OWORD *a4)
{
  _OWORD *v4; // r15
  __int64 v5; // rdi
  __int64 v6; // rsi
  __int64 v7; // r14
  __int64 v8; // r12
  int (__fastcall ***v9)(_QWORD, GUID *, int *); // rax
  char v10; // r13
  int (__fastcall *v11)(_QWORD, GUID *, int *); // rbx
  int (__fastcall ***v13)(_QWORD, _QWORD, _QWORD); // rbx
  struct InputSiteManager *InputSiteManager; // rax
  __int64 InputSiteFromInputSinkHandle; // rax
  __int64 v16; // rcx
  unsigned int v17; // esi
  int v18; // eax
  const char *v19; // r9
  int v20; // [rsp+20h] [rbp-88h]
  int v21[2]; // [rsp+20h] [rbp-88h] BYREF
  int (__fastcall ***v22)(_QWORD, _QWORD, _QWORD); // [rsp+28h] [rbp-80h] BYREF
  __int64 v23; // [rsp+30h] [rbp-78h] BYREF
  __int64 v24; // [rsp+38h] [rbp-70h]
  __int64 v25; // [rsp+40h] [rbp-68h]
  __int64 v26; // [rsp+48h] [rbp-60h]
  wil::ResultException *v27; // [rsp+50h] [rbp-58h] BYREF
  __int64 v28; // [rsp+60h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v4 = a4;
  v5 = a3;
  v6 = a2;
  v7 = a1;
  v25 = a1;
  v28 = a2;
  v26 = a3;
  v8 = a1 + 128;
  v24 = a1 + 128;
  v9 = *(int (__fastcall ****)(_QWORD, GUID *, int *))(a1 + 128);
  v22 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v9;
  if ( !v9 )
    goto LABEL_9;
  v10 = 0;
  *(_QWORD *)v21 = 0;
  v11 = **v9;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v21);
  if ( v11(v22, &GUID_05b38163_1229_4e7b_a0fc_5b47c4e7b631, v21) >= 0 )
  {
    if ( !*(_QWORD *)v21 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x74,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\contextualprocessors\\processors\\edgylegacy\\processor\\edgytarget.cpp",
        (const char *)0x8000FFFFLL,
        0);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v21);
      return 2147549183LL;
    }
    v10 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)v21 + 24LL))(*(_QWORD *)v21, v6, v5);
    if ( v10 && v5 )
      NtCloseCompositionInputSink(v5);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v21);
  if ( !v10 )
  {
LABEL_9:
    v23 = 0;
    v13 = 0;
    v22 = 0;
    if ( v5 )
    {
      try
      {
        InputSiteManager = ISMStatics::GetInputSiteManager();
        InputSiteFromInputSinkHandle = InputSiteManager::GetInputSiteFromInputSinkHandle(InputSiteManager, v21, v5);
        Microsoft::WRL::ComPtr<InputSite>::operator=(&v22, InputSiteFromInputSinkHandle);
        v16 = *(_QWORD *)v21;
        if ( *(_QWORD *)v21 )
        {
          *(_QWORD *)v21 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        }
      }
      catch ( wil::ResultException *v27 )
      {
        v19 = (const char *)*((unsigned int *)v27 + 8);
        v21[0] = (int)v19;
        if ( (int)v19 >= 0 )
        {
          v4 = a4;
          v7 = v25;
          v6 = v28;
          v5 = v26;
          v8 = v24;
          goto LABEL_16;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9F,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\contextualprocessors\\processors\\edgylegacy\\processo"
                        "r\\edgytarget.cpp",
          v19,
          v20);
        if ( v22 )
          ((void (__fastcall *)(int (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v22)[2])(v22);
        v17 = v21[0];
LABEL_20:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
        return v17;
      }
LABEL_16:
      v13 = v22;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
    v22 = v13;
    wil::com_ptr_t<AsyncHRESULTPrincipal,wil::err_exception_policy>::~com_ptr_t<AsyncHRESULTPrincipal,wil::err_exception_policy>(&v22);
    v18 = DWMInputTarget::Create(v6, &v22, &v23);
    v17 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA6,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\contextualprocessors\\processors\\edgylegacy\\processor\\edgytarget.cpp",
        (const char *)(unsigned int)v18,
        v21[0]);
      if ( v13 )
        ((void (__fastcall *)(int (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v13)[2])(v13);
      goto LABEL_20;
    }
    NtCloseCompositionInputSink(v5);
    Microsoft::WRL::ComPtr<IMPCFocusTarget>::operator=(v8, &v23);
    if ( v13 )
      ((void (__fastcall *)(int (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v13)[2])(v13);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
  }
  *(_DWORD *)(v7 + 32) = 0;
  *(_OWORD *)(v7 + 48) = *v4;
  *(_OWORD *)(v7 + 64) = v4[1];
  return 0;
}

```

## disassembly

```asm
0x1801a9750  mov     [rsp+arg_18], r9
0x1801a9755  push    rbx
0x1801a9756  push    rsi
0x1801a9757  push    rdi
0x1801a9758  push    r12
0x1801a975a  push    r13
0x1801a975c  push    r14
0x1801a975e  push    r15
0x1801a9760  sub     rsp, 70h
0x1801a9764  mov     r15, r9
0x1801a9767  mov     rdi, r8
0x1801a976a  mov     rsi, rdx
0x1801a976d  mov     r14, rcx
0x1801a9770  mov     [rsp+0A8h+var_68], rcx
0x1801a9775  mov     [rsp+0A8h+var_48], rdx
0x1801a977a  mov     [rsp+0A8h+var_60], r8
0x1801a977f  lea     r12, [rcx+80h]
0x1801a9786  mov     [rsp+0A8h+var_70], r12
0x1801a978b  mov     rax, [r12]
0x1801a978f  mov     [rsp+0A8h+var_80], rax
0x1801a9794  test    rax, rax
0x1801a9797  jz      loc_1801A984E
0x1801a979d  xor     r13b, r13b
0x1801a97a0  mov     qword ptr [rsp+0A8h+var_88], 0; int
0x1801a97a9  mov     rax, [rax]
0x1801a97ac  mov     rbx, [rax]
0x1801a97af  lea     rcx, [rsp+0A8h+var_88]
0x1801a97b4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801a97b9  lea     r8, [rsp+0A8h+var_88]
0x1801a97be  lea     rdx, _GUID_05b38163_1229_4e7b_a0fc_5b47c4e7b631
0x1801a97c5  mov     rcx, [rsp+0A8h+var_80]
0x1801a97ca  mov     rax, rbx
0x1801a97cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a97d2  test    eax, eax
0x1801a97d4  js      short loc_1801A983B
0x1801a97d6  mov     rcx, qword ptr [rsp+0A8h+var_88]
0x1801a97db  test    rcx, rcx
0x1801a97de  jnz     short loc_1801A9813
0x1801a97e0  mov     rcx, [rsp+0A8h]; this
0x1801a97e8  mov     ebx, 8000FFFFh
0x1801a97ed  mov     r9d, ebx; char *
0x1801a97f0  lea     r8, aOnecoreuapWind_230; "onecoreuap\\windows\\moderncore\\inputv"...
0x1801a97f7  mov     edx, 74h ; 't'; void *
0x1801a97fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a9801  nop
0x1801a9802  lea     rcx, [rsp+0A8h+var_88]
0x1801a9807  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801a980c  mov     eax, ebx
0x1801a980e  jmp     loc_1801A99AD
0x1801a9813  mov     rax, [rcx]
0x1801a9816  mov     r8, rdi
0x1801a9819  mov     rdx, rsi
0x1801a981c  mov     rax, [rax+18h]
0x1801a9820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a9825  mov     r13b, al
0x1801a9828  test    al, al
0x1801a982a  jz      short loc_1801A983B
0x1801a982c  test    rdi, rdi
0x1801a982f  jz      short loc_1801A983B
0x1801a9831  mov     rcx, rdi
0x1801a9834  call    cs:__imp_NtCloseCompositionInputSink
0x1801a983a  nop
0x1801a983b  lea     rcx, [rsp+0A8h+var_88]
0x1801a9840  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801a9845  test    r13b, r13b
0x1801a9848  jnz     loc_1801A9990
0x1801a984e  mov     [rsp+0A8h+var_78], 0
0x1801a9857  xor     ebx, ebx
0x1801a9859  mov     [rsp+0A8h+var_80], rbx
0x1801a985e  test    rdi, rdi
0x1801a9861  jz      loc_1801A98E9
0x1801a9867  call    ?GetInputSiteManager@ISMStatics@@SAPEAVInputSiteManager@@XZ; ISMStatics::GetInputSiteManager(void)
0x1801a986c  mov     r8, rdi
0x1801a986f  lea     rdx, [rsp+0A8h+var_88]
0x1801a9874  mov     rcx, rax
0x1801a9877  call    ?GetInputSiteFromInputSinkHandle@InputSiteManager@@QEAA?AV?$ComPtr@VInputSite@@@WRL@Microsoft@@PEAX@Z; InputSiteManager::GetInputSiteFromInputSinkHandle(void *)
0x1801a987c  mov     rdx, rax
0x1801a987f  lea     rcx, [rsp+0A8h+var_80]
0x1801a9884  call    ??4?$ComPtr@VInputSite@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<InputSite>::operator=(Microsoft::WRL::ComPtr<InputSite> &&)
0x1801a9889  nop
0x1801a988a  mov     rcx, qword ptr [rsp+0A8h+var_88]
0x1801a988f  test    rcx, rcx
0x1801a9892  jz      short loc_1801A98A6
0x1801a9894  mov     qword ptr [rsp+0A8h+var_88], rbx
0x1801a9899  mov     rax, [rcx]
0x1801a989c  mov     rax, [rax+10h]
0x1801a98a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a98a5  nop
0x1801a98a6  jmp     short loc_1801A98E4
0x1801a98a8  mov     rcx, [rsp+0A8h+var_80]
0x1801a98ad  test    rcx, rcx
0x1801a98b0  jz      short loc_1801A98BF
0x1801a98b2  mov     rax, [rcx]
0x1801a98b5  mov     rax, [rax+10h]
0x1801a98b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a98be  nop
0x1801a98bf  mov     esi, [rsp+0A8h+var_88]
0x1801a98c3  jmp     loc_1801A994C
0x1801a98c8  mov     r15, [rsp+0A8h+arg_18]
0x1801a98d0  mov     r14, [rsp+0A8h+var_68]
0x1801a98d5  mov     rsi, [rsp+0A8h+var_48]
0x1801a98da  mov     rdi, [rsp+0A8h+var_60]
0x1801a98df  mov     r12, [rsp+0A8h+var_70]
0x1801a98e4  mov     rbx, [rsp+0A8h+var_80]
0x1801a98e9  lea     rcx, [rsp+0A8h+var_78]
0x1801a98ee  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801a98f3  mov     [rsp+0A8h+var_80], rbx
0x1801a98f8  lea     rcx, [rsp+0A8h+var_80]
0x1801a98fd  call    ??1?$com_ptr_t@VAsyncHRESULTPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<AsyncHRESULTPrincipal,wil::err_exception_policy>::~com_ptr_t<AsyncHRESULTPrincipal,wil::err_exception_policy>(void)
0x1801a9902  lea     r8, [rsp+0A8h+var_78]
0x1801a9907  lea     rdx, [rsp+0A8h+var_80]
0x1801a990c  mov     rcx, rsi
0x1801a990f  call    ?Create@DWMInputTarget@@SAJAEBUtagMsgRoutingInfo@@V?$ComPtr@VInputSite@@@WRL@Microsoft@@PEAPEAUIInputTarget@@@Z; DWMInputTarget::Create(tagMsgRoutingInfo const &,Microsoft::WRL::ComPtr<InputSite>,IInputTarget * *)
0x1801a9914  mov     esi, eax
0x1801a9916  test    eax, eax
0x1801a9918  jns     short loc_1801A995A
0x1801a991a  mov     rcx, [rsp+0A8h]; this
0x1801a9922  mov     r9d, eax; char *
0x1801a9925  lea     r8, aOnecoreuapWind_230; "onecoreuap\\windows\\moderncore\\inputv"...
0x1801a992c  mov     edx, 0A6h; void *
0x1801a9931  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a9936  nop
0x1801a9937  test    rbx, rbx
0x1801a993a  jz      short loc_1801A994C
0x1801a993c  mov     rax, [rbx]
0x1801a993f  mov     rcx, rbx
0x1801a9942  mov     rax, [rax+10h]
0x1801a9946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a994b  nop
0x1801a994c  lea     rcx, [rsp+0A8h+var_78]
0x1801a9951  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801a9956  mov     eax, esi
0x1801a9958  jmp     short loc_1801A99AD
0x1801a995a  mov     rcx, rdi
0x1801a995d  call    cs:__imp_NtCloseCompositionInputSink
0x1801a9963  lea     rdx, [rsp+0A8h+var_78]
0x1801a9968  mov     rcx, r12
0x1801a996b  call    ??4?$ComPtr@UIMPCFocusTarget@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<IMPCFocusTarget>::operator=(Microsoft::WRL::ComPtr<IMPCFocusTarget> const &)
0x1801a9970  nop
0x1801a9971  test    rbx, rbx
0x1801a9974  jz      short loc_1801A9986
0x1801a9976  mov     rax, [rbx]
0x1801a9979  mov     rcx, rbx
0x1801a997c  mov     rax, [rax+10h]
0x1801a9980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a9985  nop
0x1801a9986  lea     rcx, [rsp+0A8h+var_78]
0x1801a998b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801a9990  mov     dword ptr [r14+20h], 0
0x1801a9998  movups  xmm0, xmmword ptr [r15]
0x1801a999c  movups  xmmword ptr [r14+30h], xmm0
0x1801a99a1  movups  xmm1, xmmword ptr [r15+10h]
0x1801a99a6  movups  xmmword ptr [r14+40h], xmm1
0x1801a99ab  xor     eax, eax
0x1801a99ad  add     rsp, 70h
0x1801a99b1  pop     r15
0x1801a99b3  pop     r14
0x1801a99b5  pop     r13
0x1801a99b7  pop     r12
0x1801a99b9  pop     rdi
0x1801a99ba  pop     rsi
0x1801a99bb  pop     rbx
0x1801a99bc  retn
```
