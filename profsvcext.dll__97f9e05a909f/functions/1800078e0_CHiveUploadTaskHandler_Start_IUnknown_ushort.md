# CHiveUploadTaskHandler::Start(IUnknown *,ushort *)

- ea: `0x1800078e0`
- end: `0x1800079ea`
- name: `?Start@CHiveUploadTaskHandler@@UEAAJPEAUIUnknown@@PEAG@Z`
- size: `266`
- prototype: `__int64 __fastcall(CHiveUploadTaskHandler *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180005aa0`
- `0x180006a9c`
- `0x1800078e0`
- `0x1800079f0`
- `0x180009cf8`
- `0x18000fca8`
- `0x180017f4c`
- `0x180020010`

## string_xrefs

- `0x180007910`: `clientcore\ds\security\gina\profile\roaming\uploadtask.cpp`
- `0x18000794d`: `clientcore\ds\security\gina\profile\roaming\uploadtask.cpp`
- `0x1800079bb`: `clientcore\ds\security\gina\profile\roaming\uploadtask.cpp`

## pseudocode

```c
__int64 __fastcall CHiveUploadTaskHandler::Start(
        CHiveUploadTaskHandler *this,
        struct IUnknown *a2,
        unsigned __int16 *a3)
{
  int LocalSetting; // eax
  __int64 v6; // rcx
  int v7; // eax
  unsigned int v8; // ebx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  int v10; // eax
  __int64 v11; // rdx
  int v13[6]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  char v15; // [rsp+58h] [rbp+20h] BYREF

  v15 = 0;
  LocalSetting = Profile::GetLocalSetting(6, &v15, a3);
  if ( LocalSetting < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x298,
      (int)"clientcore\\ds\\security\\gina\\profile\\roaming\\uploadtask.cpp",
      (const char *)(unsigned int)LocalSetting);
  if ( v15
    || (wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v15, this),
        v7 = CRupUserList::ForEachUserToken__lambda_aa0b0ee3689b7534866efe16f2ea56da___(v6, &v15),
        v8 = v7,
        v7 >= 0) )
  {
    *(_QWORD *)v13 = 0;
    QueryInterface = a2->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(v13);
    v10 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, int *))QueryInterface)(
            a2,
            &GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a,
            v13);
    v8 = v10;
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)v13 + 32LL))(*(_QWORD *)v13, 0);
      v8 = v10;
      if ( v10 >= 0 )
      {
        v8 = 0;
        goto LABEL_12;
      }
      v11 = 684;
    }
    else
    {
      v11 = 683;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\uploadtask.cpp",
      (const char *)(unsigned int)v10,
      v13[0]);
LABEL_12:
    Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(v13);
    return v8;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2A6,
    (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\uploadtask.cpp",
    (const char *)(unsigned int)v7,
    v13[0]);
  return v8;
}

```

## disassembly

```asm
0x1800078e0  mov     [rsp+arg_0], rbx
0x1800078e5  push    rdi
0x1800078e6  sub     rsp, 30h
0x1800078ea  mov     rdi, rdx
0x1800078ed  mov     rbx, rcx
0x1800078f0  mov     [rsp+38h+arg_18], 0
0x1800078f5  lea     rdx, [rsp+38h+arg_18]
0x1800078fa  mov     ecx, 6
0x1800078ff  call    ?GetLocalSetting@Profile@@YAJW4PROFILE_SETTING_ID@1@AEA_NPEBGW4USERSTATE_SETTING_SOURCES@@@Z; Profile::GetLocalSetting(Profile::PROFILE_SETTING_ID,bool &,ushort const *,USERSTATE_SETTING_SOURCES)
0x180007904  mov     rcx, [rsp+38h]; this
0x180007909  test    eax, eax
0x18000790b  jns     short loc_180007921
0x18000790d  mov     r9d, eax; char *
0x180007910  lea     r8, aClientcoreDsSe_0; "clientcore\\ds\\security\\gina\\profile"...
0x180007917  mov     edx, 298h; void *
0x18000791c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007921  cmp     [rsp+38h+arg_18], 0
0x180007926  jnz     short loc_180007960
0x180007928  mov     rdx, rbx
0x18000792b  lea     rcx, [rsp+38h+arg_18]
0x180007930  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180007935  lea     rdx, [rsp+38h+arg_18]
0x18000793a  call    CRupUserList__ForEachUserToken__lambda_aa0b0ee3689b7534866efe16f2ea56da___
0x18000793f  mov     ebx, eax
0x180007941  test    eax, eax
0x180007943  jns     short loc_180007960
0x180007945  mov     rcx, [rsp+38h]; this
0x18000794a  mov     r9d, eax; char *
0x18000794d  lea     r8, aClientcoreDsSe_0; "clientcore\\ds\\security\\gina\\profile"...
0x180007954  mov     edx, 2A6h; void *
0x180007959  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000795e  jmp     short loc_1800079DD
0x180007960  mov     qword ptr [rsp+38h+var_18], 0; int
0x180007969  mov     rax, [rdi]
0x18000796c  mov     rbx, [rax]
0x18000796f  lea     rcx, [rsp+38h+var_18]
0x180007974  call    ?InternalRelease@?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(void)
0x180007979  lea     r8, [rsp+38h+var_18]
0x18000797e  lea     rdx, _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a
0x180007985  mov     rcx, rdi
0x180007988  mov     rax, rbx
0x18000798b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007990  mov     ebx, eax
0x180007992  test    eax, eax
0x180007994  jns     short loc_18000799D
0x180007996  mov     edx, 2ABh
0x18000799b  jmp     short loc_1800079BB
0x18000799d  mov     rcx, qword ptr [rsp+38h+var_18]
0x1800079a2  mov     rax, [rcx]
0x1800079a5  xor     edx, edx
0x1800079a7  mov     rax, [rax+20h]
0x1800079ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079b0  mov     ebx, eax
0x1800079b2  test    eax, eax
0x1800079b4  jns     short loc_1800079D1
0x1800079b6  mov     edx, 2ACh; void *
0x1800079bb  lea     r8, aClientcoreDsSe_0; "clientcore\\ds\\security\\gina\\profile"...
0x1800079c2  mov     r9d, eax; char *
0x1800079c5  mov     rcx, [rsp+38h]; this
0x1800079ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800079cf  jmp     short loc_1800079D3
0x1800079d1  xor     ebx, ebx
0x1800079d3  lea     rcx, [rsp+38h+var_18]
0x1800079d8  call    ?InternalRelease@?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IRegisteredTask>::InternalRelease(void)
0x1800079dd  mov     eax, ebx
0x1800079df  mov     rbx, [rsp+38h+arg_0]
0x1800079e4  add     rsp, 30h
0x1800079e8  pop     rdi
0x1800079e9  retn
```
