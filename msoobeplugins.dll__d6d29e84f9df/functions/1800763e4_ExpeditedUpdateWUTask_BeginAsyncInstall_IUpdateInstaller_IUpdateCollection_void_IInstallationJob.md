# ExpeditedUpdateWUTask::_BeginAsyncInstall(IUpdateInstaller *,IUpdateCollection *,void *,IInstallationJob * *)

- ea: `0x1800763e4`
- end: `0x1800765c1`
- name: `?_BeginAsyncInstall@ExpeditedUpdateWUTask@@AEAAJPEAUIUpdateInstaller@@PEAUIUpdateCollection@@PEAXPEAPEAUIInstallationJob@@@Z`
- size: `477`
- prototype: `__int64 __fastcall(ExpeditedUpdateWUTask *__hidden this, struct IUpdateInstaller *, struct IUpdateCollection *, void *, struct IInstallationJob **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180073754`

## callees

- `0x180008544`
- `0x18001ad08`
- `0x180072944`
- `0x180072be4`
- `0x1800763e4`
- `0x1800b8834`
- `0x1800c4010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800764fe`
- `OLEAUT32!__imp_VariantInit` at `0x180076509`
- `OLEAUT32!__imp_VariantInit` at `0x1800764fe`
- `OLEAUT32!__imp_VariantInit` at `0x180076509`
- `OLEAUT32!__imp_VariantClear` at `0x180076567`
- `OLEAUT32!__imp_VariantClear` at `0x180076584`
- `OLEAUT32!__imp_VariantClear` at `0x18007658f`
- `OLEAUT32!__imp_VariantClear` at `0x180076567`
- `OLEAUT32!__imp_VariantClear` at `0x180076584`
- `OLEAUT32!__imp_VariantClear` at `0x18007658f`

## string_xrefs

- `0x180076442`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`
- `0x180076489`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`
- `0x1800764cc`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`
- `0x180076551`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`
- `0x180076572`: `ExpeditedUpdateWUTask _BeginAsyncInstall started.`
- `0x180076407`: `ExpeditedUpdateWUTask _BeginAsyncInstall.`
- `0x1800764ec`: `ExpeditedUpdateWUTask install started.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ExpeditedUpdateWUTask::_BeginAsyncInstall(
        ExpeditedUpdateWUTask *this,
        struct IUpdateInstaller *a2,
        struct IUpdateCollection *a3,
        void *a4,
        struct IInstallationJob **a5)
{
  int v8; // r14d
  int v9; // eax
  unsigned int v10; // ebx
  int updated; // eax
  int v12; // eax
  int v13; // eax
  int v15; // [rsp+20h] [rbp-50h]
  __int64 v16; // [rsp+30h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-38h] BYREF
  VARIANTARG v18; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  __int64 v20; // [rsp+98h] [rbp+28h] BYREF
  void *v21; // [rsp+A8h] [rbp+38h] BYREF

  v21 = a4;
  UnattendLogW(0, L"ExpeditedUpdateWUTask _BeginAsyncInstall.");
  v8 = (int)a5;
  *a5 = 0;
  v9 = ((__int64 (__fastcall *)(struct IUpdateInstaller *, struct IUpdateCollection *))a2->lpVtbl->put_Updates)(a2, a3);
  v10 = v9;
  if ( v9 >= 0 )
  {
    a5 = (struct IInstallationJob **)*((_QWORD *)this + 74);
    v16 = 0;
    updated = Microsoft::WRL::Details::MakeAndInitialize<COOBEExpeditedUpdateWUCompletionCallback,IInstallationCompletedCallback,void * &,INamedPropertyStore *>(
                &v16,
                &v21,
                (struct INamedPropertyStore **)&a5);
    v10 = updated;
    if ( updated >= 0 )
    {
      a5 = (struct IInstallationJob **)*((_QWORD *)this + 74);
      v20 = 0;
      v12 = Microsoft::WRL::Details::MakeAndInitialize<COOBEExpeditedUpdateWUProgressCallback,IInstallationProgressChangedCallback,INamedPropertyStore *>(
              &v20,
              &a5);
      v10 = v12;
      if ( v12 >= 0 )
      {
        UnattendLogW(0, L"ExpeditedUpdateWUTask install started.");
        VariantInit(&pvarg);
        VariantInit(&pvarg);
        v18 = pvarg;
        v13 = ((__int64 (__fastcall *)(struct IUpdateInstaller *, __int64, __int64, VARIANTARG *))a2->lpVtbl->BeginInstall)(
                a2,
                v20,
                v16,
                &v18);
        v10 = v13;
        if ( v13 >= 0 )
        {
          UnattendLogW(0, L"ExpeditedUpdateWUTask _BeginAsyncInstall started.");
          VariantClear(&pvarg);
          VariantClear(&pvarg);
          wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v20);
          v10 = 0;
          goto LABEL_11;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x33B,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
          (const char *)(unsigned int)v13,
          v8);
        VariantClear(&pvarg);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x335,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
          (const char *)(unsigned int)v12,
          v15);
      }
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v20);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x333,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
        (const char *)(unsigned int)updated,
        v15);
    }
LABEL_11:
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v16);
    return v10;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x330,
    (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
    (const char *)(unsigned int)v9,
    v15);
  return v10;
}

```

## disassembly

```asm
0x1800763e4  mov     [rsp-18h+arg_0], rbx
0x1800763e9  mov     [rsp-18h+arg_10], rsi
0x1800763ee  mov     [rsp-18h+arg_18], r9
0x1800763f3  push    rbp
0x1800763f4  push    rdi
0x1800763f5  push    r14
0x1800763f7  mov     rbp, rsp
0x1800763fa  sub     rsp, 70h
0x1800763fe  mov     rbx, r8
0x180076401  mov     rsi, rdx
0x180076404  mov     rdi, rcx
0x180076407  lea     rdx, aExpeditedupdat_19; "ExpeditedUpdateWUTask _BeginAsyncInstal"...
0x18007640e  xor     ecx, ecx
0x180076410  call    UnattendLogW
0x180076415  mov     r14, [rbp+arg_20]
0x180076419  mov     qword ptr [r14], 0
0x180076420  mov     rax, [rsi]
0x180076423  mov     rdx, rbx
0x180076426  mov     rcx, rsi
0x180076429  mov     rax, [rax+80h]
0x180076430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076435  mov     ebx, eax
0x180076437  test    eax, eax
0x180076439  jns     short loc_180076458
0x18007643b  mov     rcx, [rbp+18h]; this
0x18007643f  mov     r9d, eax; char *
0x180076442  lea     r8, aShellOobeMachi_0; "shell\\oobe\\machine\\plugins\\adapters"...
0x180076449  mov     edx, 330h; void *
0x18007644e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076453  jmp     loc_1800765AA
0x180076458  mov     rax, [rdi+250h]
0x18007645f  mov     [rbp+arg_20], rax
0x180076463  mov     [rbp+var_40], 0
0x18007646b  lea     r8, [rbp+arg_20]
0x18007646f  lea     rdx, [rbp+arg_18]
0x180076473  lea     rcx, [rbp+var_40]
0x180076477  call    ??$MakeAndInitialize@VCOOBEExpeditedUpdateWUCompletionCallback@@UIInstallationCompletedCallback@@AEAPEAXPEAUINamedPropertyStore@@@Details@WRL@Microsoft@@YAJPEAPEAUIInstallationCompletedCallback@@AEAPEAX$$QEAPEAUINamedPropertyStore@@@Z; Microsoft::WRL::Details::MakeAndInitialize<COOBEExpeditedUpdateWUCompletionCallback,IInstallationCompletedCallback,void * &,INamedPropertyStore *>(IInstallationCompletedCallback * *,void * &,INamedPropertyStore * &&)
0x18007647c  mov     ebx, eax
0x18007647e  test    eax, eax
0x180076480  jns     short loc_18007649F
0x180076482  mov     rcx, [rbp+18h]; this
0x180076486  mov     r9d, eax; char *
0x180076489  lea     r8, aShellOobeMachi_0; "shell\\oobe\\machine\\plugins\\adapters"...
0x180076490  mov     edx, 333h; void *
0x180076495  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007649a  jmp     loc_1800765A1
0x18007649f  mov     rax, [rdi+250h]
0x1800764a6  mov     [rbp+arg_20], rax
0x1800764aa  mov     [rbp+arg_8], 0
0x1800764b2  lea     rdx, [rbp+arg_20]
0x1800764b6  lea     rcx, [rbp+arg_8]
0x1800764ba  call    ??$MakeAndInitialize@VCOOBEExpeditedUpdateWUProgressCallback@@UIInstallationProgressChangedCallback@@PEAUINamedPropertyStore@@@Details@WRL@Microsoft@@YAJPEAPEAUIInstallationProgressChangedCallback@@$$QEAPEAUINamedPropertyStore@@@Z; Microsoft::WRL::Details::MakeAndInitialize<COOBEExpeditedUpdateWUProgressCallback,IInstallationProgressChangedCallback,INamedPropertyStore *>(IInstallationProgressChangedCallback * *,INamedPropertyStore * &&)
0x1800764bf  mov     ebx, eax
0x1800764c1  test    eax, eax
0x1800764c3  jns     short loc_1800764EC
0x1800764c5  mov     rcx, [rbp+18h]; this
0x1800764c9  mov     r9d, eax; char *
0x1800764cc  lea     r8, aShellOobeMachi_0; "shell\\oobe\\machine\\plugins\\adapters"...
0x1800764d3  mov     edx, 335h; void *
0x1800764d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800764dd  nop
0x1800764de  lea     rcx, [rbp+arg_8]
0x1800764e2  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x1800764e7  jmp     loc_1800765A1
0x1800764ec  lea     rdx, aExpeditedupdat_32; "ExpeditedUpdateWUTask install started."
0x1800764f3  xor     ecx, ecx
0x1800764f5  call    UnattendLogW
0x1800764fa  lea     rcx, [rbp+pvarg]; pvarg
0x1800764fe  call    cs:__imp_VariantInit
0x180076504  nop
0x180076505  lea     rcx, [rbp+pvarg]; pvarg
0x180076509  call    cs:__imp_VariantInit
0x18007650f  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180076513  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180076518  movaps  [rbp+var_20], xmm0
0x18007651c  movsd   [rbp+var_10], xmm1
0x180076521  mov     rax, [rsi]
0x180076524  mov     qword ptr [rsp+70h+var_50], r14; int
0x180076529  lea     r9, [rbp+var_20]
0x18007652d  mov     r8, [rbp+var_40]
0x180076531  mov     rdx, [rbp+arg_8]
0x180076535  mov     rcx, rsi
0x180076538  mov     rax, [rax+88h]
0x18007653f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076544  mov     ebx, eax
0x180076546  test    eax, eax
0x180076548  jns     short loc_180076572
0x18007654a  mov     rcx, [rbp+18h]; this
0x18007654e  mov     r9d, eax; char *
0x180076551  lea     r8, aShellOobeMachi_0; "shell\\oobe\\machine\\plugins\\adapters"...
0x180076558  mov     edx, 33Bh; void *
0x18007655d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076562  nop
0x180076563  lea     rcx, [rbp+pvarg]; pvarg
0x180076567  call    cs:__imp_VariantClear
0x18007656d  jmp     loc_1800764DE
0x180076572  lea     rdx, aExpeditedupdat_50; "ExpeditedUpdateWUTask _BeginAsyncInstal"...
0x180076579  xor     ecx, ecx
0x18007657b  call    UnattendLogW
0x180076580  lea     rcx, [rbp+pvarg]; pvarg
0x180076584  call    cs:__imp_VariantClear
0x18007658a  nop
0x18007658b  lea     rcx, [rbp+pvarg]; pvarg
0x18007658f  call    cs:__imp_VariantClear
0x180076595  nop
0x180076596  lea     rcx, [rbp+arg_8]
0x18007659a  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18007659f  xor     ebx, ebx
0x1800765a1  lea     rcx, [rbp+var_40]
0x1800765a5  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x1800765aa  mov     eax, ebx
0x1800765ac  lea     r11, [rsp+70h+var_s0]
0x1800765b1  mov     rbx, [r11+20h]
0x1800765b5  mov     rsi, [r11+30h]
0x1800765b9  mov     rsp, r11
0x1800765bc  pop     r14
0x1800765be  pop     rdi
0x1800765bf  pop     rbp
0x1800765c0  retn
```
