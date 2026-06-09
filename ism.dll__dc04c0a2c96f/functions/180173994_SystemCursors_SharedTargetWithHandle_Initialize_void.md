# SystemCursors::SharedTargetWithHandle::Initialize(void)

- ea: `0x180173994`
- end: `0x180173b9d`
- name: `?Initialize@SharedTargetWithHandle@SystemCursors@@QEAAJXZ`
- size: `521`
- prototype: `__int64 __fastcall(SystemCursors::SharedTargetWithHandle *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800902cc`

## callees

- `0x180037940`
- `0x180069f90`
- `0x180082780`
- `0x18008ead4`
- `0x18009fd10`
- `0x1800ae370`
- `0x1800af9b8`
- `0x180173994`
- `0x1801ce010`

## import_xrefs

- `win32u!NtDCompositionDuplicateHandleToProcess` at `0x180173b3a`
- `win32u!NtDCompositionDuplicateHandleToProcess` at `0x180173b3a`

## string_xrefs

- `0x1801739e2`: `onecoreuap\windows\moderncore\inputv2\inputhost\components\cursor\systemcursorservice\lib\cursorwc.cpp`
- `0x180173a29`: `onecoreuap\windows\moderncore\inputv2\inputhost\components\cursor\systemcursorservice\lib\cursorwc.cpp`
- `0x180173a78`: `onecoreuap\windows\moderncore\inputv2\inputhost\components\cursor\systemcursorservice\lib\cursorwc.cpp`
- `0x180173ad3`: `onecoreuap\windows\moderncore\inputv2\inputhost\components\cursor\systemcursorservice\lib\cursorwc.cpp`
- `0x180173b4b`: `onecoreuap\windows\moderncore\inputv2\inputhost\components\cursor\systemcursorservice\lib\cursorwc.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall SystemCursors::SharedTargetWithHandle::Initialize(SystemCursors::SharedTargetWithHandle *this)
{
  int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rax
  int v5; // eax
  int v6; // eax
  __int64 *v7; // rdi
  __int64 (__fastcall *v8)(__int64 *, __int64, __int64 *); // rbx
  int v9; // eax
  __int64 (__fastcall ***v10)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v11; // rbx
  int v12; // eax
  int v14[6]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+20h]
  __int64 (__fastcall ***v16)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp+28h] BYREF
  __int64 v17; // [rsp+68h] [rbp+30h] BYREF
  __int64 v18; // [rsp+70h] [rbp+38h] BYREF
  __int64 *v19; // [rsp+78h] [rbp+40h] BYREF

  wil::com_ptr_t<InputSite,wil::err_exception_policy>::com_ptr_t<InputSite,wil::err_exception_policy>(
    v14,
    **(_QWORD **)this);
  v19 = 0;
  v2 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 **))v14)(
         *(_QWORD *)v14,
         &GUID_9cbd9312_070d_4588_9bf3_bbf528cf3e84,
         &v19);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v16 = 0;
    v4 = *v19;
    v16 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64 *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(v4 + 32))(
           v19,
           &v16);
    v3 = v5;
    if ( v5 >= 0 )
    {
      v18 = 0;
      v6 = (**v16)(v16, &GUID_bcb4ad45_7609_4550_934f_16002a68fded, &v18);
      v3 = v6;
      if ( v6 >= 0 )
      {
        v17 = 0;
        v7 = v19;
        v8 = *(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(*v19 + 64);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &v17,
          0);
        v9 = v8(v7, v18, &v17);
        v3 = v9;
        if ( v9 >= 0 )
        {
          wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
            (char *)this + 16,
            &v17);
          v10 = v16;
          v11 = *((_QWORD *)this + 1);
          *((_QWORD *)this + 1) = v16;
          if ( v10 )
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v10)[1])(v10);
          if ( v11 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
          v12 = NtDCompositionDuplicateHandleToProcess(
                  *((_QWORD *)this + 2),
                  *((unsigned int *)this + 8),
                  (char *)this + 24);
          if ( v12 >= 0 )
          {
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
            wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(&v18);
            wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(&v16);
            v3 = 0;
            goto LABEL_19;
          }
          v3 = wil::details::in1diag3::Return_NtStatus(
                 retaddr,
                 (void *)0x135,
                 (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputhost\\components\\cursor\\systemcursorserv"
                               "ice\\lib\\cursorwc.cpp",
                 (const char *)(unsigned int)v12,
                 v14[0]);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x129,
            (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputhost\\components\\cursor\\systemcursorservice\\"
                          "lib\\cursorwc.cpp",
            (const char *)(unsigned int)v9,
            v14[0]);
        }
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x124,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputhost\\components\\cursor\\systemcursorservice\\lib\\cursorwc.cpp",
          (const char *)(unsigned int)v6,
          v14[0]);
      }
      wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(&v18);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x121,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputhost\\components\\cursor\\systemcursorservice\\lib\\cursorwc.cpp",
        (const char *)(unsigned int)v5,
        v14[0]);
    }
    wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(&v16);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11C,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputhost\\components\\cursor\\systemcursorservice\\lib\\cursorwc.cpp",
      (const char *)(unsigned int)v2,
      v14[0]);
  }
LABEL_19:
  wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(&v19);
  wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(v14);
  return v3;
}

```

## disassembly

```asm
0x180173994  push    rbp
0x180173996  push    rbx
0x180173997  push    rsi
0x180173998  push    rdi
0x180173999  mov     rbp, rsp
0x18017399c  sub     rsp, 38h
0x1801739a0  mov     rsi, rcx
0x1801739a3  mov     rdx, [rcx]
0x1801739a6  mov     rdx, [rdx]
0x1801739a9  lea     rcx, [rbp+var_18]
0x1801739ad  call    ??0?$com_ptr_t@VInputSite@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVInputSite@@@Z; wil::com_ptr_t<InputSite,wil::err_exception_policy>::com_ptr_t<InputSite,wil::err_exception_policy>(InputSite *)
0x1801739b2  nop
0x1801739b3  mov     [rbp+arg_18], 0
0x1801739bb  mov     rcx, qword ptr [rbp+var_18]
0x1801739bf  mov     rax, [rcx]
0x1801739c2  lea     r8, [rbp+arg_18]
0x1801739c6  lea     rdx, _GUID_9cbd9312_070d_4588_9bf3_bbf528cf3e84
0x1801739cd  mov     rax, [rax]
0x1801739d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801739d5  mov     ebx, eax
0x1801739d7  test    eax, eax
0x1801739d9  jns     short loc_1801739F8
0x1801739db  mov     rcx, [rbp+20h]; this
0x1801739df  mov     r9d, eax; char *
0x1801739e2  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\moderncore\\inputv"...
0x1801739e9  mov     edx, 11Ch; void *
0x1801739ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801739f3  jmp     loc_180173B7F
0x1801739f8  mov     [rbp+arg_0], 0
0x180173a00  mov     rcx, [rbp+arg_18]
0x180173a04  mov     rax, [rcx]
0x180173a07  mov     [rbp+arg_0], 0
0x180173a0f  lea     rdx, [rbp+arg_0]
0x180173a13  mov     rax, [rax+20h]
0x180173a17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180173a1c  mov     ebx, eax
0x180173a1e  test    eax, eax
0x180173a20  jns     short loc_180173A49
0x180173a22  mov     rcx, [rbp+20h]; this
0x180173a26  mov     r9d, eax; char *
0x180173a29  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\moderncore\\inputv"...
0x180173a30  mov     edx, 121h; void *
0x180173a35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180173a3a  nop
0x180173a3b  lea     rcx, [rbp+arg_0]
0x180173a3f  call    ??1?$com_ptr_t@UIMPCInputProviderBase@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(void)
0x180173a44  jmp     loc_180173B7F
0x180173a49  mov     [rbp+arg_10], 0
0x180173a51  mov     rcx, [rbp+arg_0]
0x180173a55  mov     rax, [rcx]
0x180173a58  lea     r8, [rbp+arg_10]
0x180173a5c  lea     rdx, _GUID_bcb4ad45_7609_4550_934f_16002a68fded
0x180173a63  mov     rax, [rax]
0x180173a66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180173a6b  mov     ebx, eax
0x180173a6d  test    eax, eax
0x180173a6f  jns     short loc_180173A95
0x180173a71  mov     rcx, [rbp+20h]; this
0x180173a75  mov     r9d, eax; char *
0x180173a78  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\moderncore\\inputv"...
0x180173a7f  mov     edx, 124h; void *
0x180173a84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180173a89  nop
0x180173a8a  lea     rcx, [rbp+arg_10]
0x180173a8e  call    ??1?$com_ptr_t@UIMPCInputProviderBase@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(void)
0x180173a93  jmp     short loc_180173A3B
0x180173a95  mov     [rbp+arg_8], 0
0x180173a9d  mov     rdi, [rbp+arg_18]
0x180173aa1  mov     rax, [rdi]
0x180173aa4  mov     rbx, [rax+40h]
0x180173aa8  xor     edx, edx
0x180173aaa  lea     rcx, [rbp+arg_8]
0x180173aae  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180173ab3  lea     r8, [rbp+arg_8]
0x180173ab7  mov     rdx, [rbp+arg_10]
0x180173abb  mov     rcx, rdi
0x180173abe  mov     rax, rbx
0x180173ac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180173ac6  mov     ebx, eax
0x180173ac8  test    eax, eax
0x180173aca  jns     short loc_180173AF0
0x180173acc  mov     rcx, [rbp+20h]; this
0x180173ad0  mov     r9d, eax; char *
0x180173ad3  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\moderncore\\inputv"...
0x180173ada  mov     edx, 129h; void *
0x180173adf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180173ae4  nop
0x180173ae5  lea     rcx, [rbp+arg_8]
0x180173ae9  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180173aee  jmp     short loc_180173A8A
0x180173af0  lea     rdx, [rbp+arg_8]
0x180173af4  lea     rcx, [rsi+10h]
0x180173af8  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180173afd  mov     rcx, [rbp+arg_0]
0x180173b01  mov     rbx, [rsi+8]
0x180173b05  mov     [rsi+8], rcx
0x180173b09  test    rcx, rcx
0x180173b0c  jz      short loc_180173B1A
0x180173b0e  mov     rax, [rcx]
0x180173b11  mov     rax, [rax+8]
0x180173b15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180173b1a  test    rbx, rbx
0x180173b1d  jz      short loc_180173B2F
0x180173b1f  mov     rax, [rbx]
0x180173b22  mov     rcx, rbx
0x180173b25  mov     rax, [rax+10h]
0x180173b29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180173b2e  nop
0x180173b2f  lea     r8, [rsi+18h]
0x180173b33  mov     edx, [rsi+20h]
0x180173b36  mov     rcx, [rsi+10h]
0x180173b3a  call    cs:__imp_NtDCompositionDuplicateHandleToProcess
0x180173b40  test    eax, eax
0x180173b42  jns     short loc_180173B60
0x180173b44  mov     rcx, [rbp+20h]; this
0x180173b48  mov     r9d, eax; char *
0x180173b4b  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\moderncore\\inputv"...
0x180173b52  mov     edx, 135h; void *
0x180173b57  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180173b5c  mov     ebx, eax
0x180173b5e  jmp     short loc_180173AE5
0x180173b60  lea     rcx, [rbp+arg_8]
0x180173b64  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180173b69  nop
0x180173b6a  lea     rcx, [rbp+arg_10]
0x180173b6e  call    ??1?$com_ptr_t@UIMPCInputProviderBase@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(void)
0x180173b73  nop
0x180173b74  lea     rcx, [rbp+arg_0]
0x180173b78  call    ??1?$com_ptr_t@UIMPCInputProviderBase@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(void)
0x180173b7d  xor     ebx, ebx
0x180173b7f  lea     rcx, [rbp+arg_18]
0x180173b83  call    ??1?$com_ptr_t@UIMPCInputProviderBase@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(void)
0x180173b88  nop
0x180173b89  lea     rcx, [rbp+var_18]
0x180173b8d  call    ??1?$com_ptr_t@UIMPCInputProviderBase@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(void)
0x180173b92  mov     eax, ebx
0x180173b94  add     rsp, 38h
0x180173b98  pop     rdi
0x180173b99  pop     rsi
0x180173b9a  pop     rbx
0x180173b9b  pop     rbp
0x180173b9c  retn
```
