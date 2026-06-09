# KsControlWnfNotify::Initialize(ushort const *)

- ea: `0x1800111fc`
- end: `0x1800113ce`
- name: `?Initialize@KsControlWnfNotify@@QEAAJPEBG@Z`
- size: `466`
- prototype: `__int64 __fastcall(KsControlWnfNotify *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800196f0`

## callees

- `0x180007b14`
- `0x1800081e4`
- `0x1800111fc`
- `0x180045010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18001127a`
- `ole32!CoCreateInstance` at `0x18001127a`
- `MFPlat!MFStartup` at `0x18001122e`
- `MFPlat!MFStartup` at `0x18001122e`

## pseudocode

```c
__int64 __fastcall KsControlWnfNotify::Initialize(KsControlWnfNotify *this, const unsigned __int16 *a2)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  LPVOID v6; // rcx
  __int64 v7; // rcx
  LPVOID v8; // rbx
  __int64 v9; // rax
  __int64 (__fastcall *v10)(LPVOID, _QWORD, GUID *, __int64 *); // rsi
  __int64 v11; // rcx
  __int64 v12; // rbx
  __int64 v14; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  __int64 v16; // [rsp+60h] [rbp+30h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp+38h] BYREF

  ppv = 0;
  v16 = 0;
  v4 = MFStartup(0x20070u, 0);
  v5 = v4;
  if ( v4 < 0 )
  {
    v14 = 30;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (int)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\kscontrolwnfnotify.cpp",
      (const char *)(unsigned int)v4);
    wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(&v16);
    wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>((__int64 *)&ppv);
    return v5;
  }
  v6 = ppv;
  *((_BYTE *)this + 48) = 1;
  ppv = 0;
  if ( v6 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
  v4 = CoCreateInstance(&CLSID_FrameServerMonitorObjectFactory, 0, 1u, &GUID_473ae402_5e85_4176_ba86_285b5ce2cb94, &ppv);
  v5 = v4;
  if ( v4 < 0 )
  {
    v14 = 33;
    goto LABEL_22;
  }
  v7 = v16;
  v8 = ppv;
  v9 = *(_QWORD *)ppv;
  v16 = 0;
  v10 = *(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, __int64 *))(v9 + 24);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  v4 = v10(v8, 0, &GUID_746ea290_a034_4497_8afd_952a87bdd3d5, &v16);
  v5 = v4;
  if ( v4 < 0 )
  {
    v14 = 34;
    goto LABEL_22;
  }
  v4 = (*(__int64 (__fastcall **)(__int64, __int64, const unsigned __int16 *))(*(_QWORD *)v16 + 24LL))(v16, 6, a2);
  v5 = v4;
  if ( v4 < 0 )
  {
    v14 = 35;
    goto LABEL_22;
  }
  v11 = v16;
  v12 = *(_QWORD *)this;
  *(_QWORD *)this = v16;
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
    v11 = v16;
  }
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v11 = v16;
  }
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return 0;
}

```

## disassembly

```asm
0x1800111fc  mov     [rsp-18h+arg_0], rbx
0x180011201  mov     [rsp-18h+arg_8], rsi
0x180011206  push    rbp
0x180011207  push    rdi
0x180011208  push    r14
0x18001120a  mov     rbp, rsp
0x18001120d  sub     rsp, 30h
0x180011211  mov     r14, rdx
0x180011214  mov     [rbp+arg_18], 0
0x18001121c  mov     rdi, rcx
0x18001121f  mov     [rbp+arg_10], 0
0x180011227  xor     edx, edx; dwFlags
0x180011229  mov     ecx, 20070h; Version
0x18001122e  call    cs:__imp_MFStartup
0x180011235  nop     dword ptr [rax+rax+00h]
0x18001123a  mov     ebx, eax
0x18001123c  test    eax, eax
0x18001123e  js      loc_180011362
0x180011244  mov     rcx, [rbp+arg_18]
0x180011248  mov     byte ptr [rdi+30h], 1
0x18001124c  mov     [rbp+arg_18], 0
0x180011254  test    rcx, rcx
0x180011257  jnz     loc_180011369
0x18001125d  xor     edx, edx; pUnkOuter
0x18001125f  lea     rax, [rbp+arg_18]
0x180011263  lea     r9, _GUID_473ae402_5e85_4176_ba86_285b5ce2cb94; riid
0x18001126a  mov     [rsp+30h+ppv], rax; int
0x18001126f  lea     rcx, CLSID_FrameServerMonitorObjectFactory; rclsid
0x180011276  lea     r8d, [rdx+1]; dwClsContext
0x18001127a  call    cs:__imp_CoCreateInstance
0x180011281  nop     dword ptr [rax+rax+00h]
0x180011286  mov     ebx, eax
0x180011288  test    eax, eax
0x18001128a  js      loc_18001137A
0x180011290  mov     rcx, [rbp+arg_10]
0x180011294  mov     rbx, [rbp+arg_18]
0x180011298  mov     rax, [rbx]
0x18001129b  mov     [rbp+arg_10], 0
0x1800112a3  mov     rsi, [rax+18h]
0x1800112a7  test    rcx, rcx
0x1800112aa  jz      short loc_1800112B8
0x1800112ac  mov     rdx, [rcx]
0x1800112af  mov     rax, [rdx+10h]
0x1800112b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112b8  lea     r9, [rbp+arg_10]
0x1800112bc  xor     edx, edx
0x1800112be  lea     r8, _GUID_746ea290_a034_4497_8afd_952a87bdd3d5
0x1800112c5  mov     rcx, rbx
0x1800112c8  mov     rax, rsi
0x1800112cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112d0  mov     ebx, eax
0x1800112d2  test    eax, eax
0x1800112d4  js      loc_180011381
0x1800112da  mov     rcx, [rbp+arg_10]
0x1800112de  xor     r9d, r9d
0x1800112e1  mov     r8, r14
0x1800112e4  mov     rax, [rcx]
0x1800112e7  lea     edx, [r9+6]
0x1800112eb  mov     rax, [rax+18h]
0x1800112ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112f4  mov     ebx, eax
0x1800112f6  test    eax, eax
0x1800112f8  js      loc_180011388
0x1800112fe  mov     rcx, [rbp+arg_10]
0x180011302  mov     rbx, [rdi]
0x180011305  mov     [rdi], rcx
0x180011308  test    rcx, rcx
0x18001130b  jz      short loc_18001131D
0x18001130d  mov     rax, [rcx]
0x180011310  mov     rax, [rax+8]
0x180011314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011319  mov     rcx, [rbp+arg_10]
0x18001131d  test    rbx, rbx
0x180011320  jnz     loc_1800113B6
0x180011326  test    rcx, rcx
0x180011329  jz      short loc_180011337
0x18001132b  mov     rax, [rcx]
0x18001132e  mov     rax, [rax+10h]
0x180011332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011337  mov     rcx, [rbp+arg_18]
0x18001133b  test    rcx, rcx
0x18001133e  jz      short loc_18001134C
0x180011340  mov     rax, [rcx]
0x180011343  mov     rax, [rax+10h]
0x180011347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001134c  xor     eax, eax
0x18001134e  mov     rbx, [rsp+30h+arg_0]
0x180011353  mov     rsi, [rsp+30h+arg_8]
0x180011358  add     rsp, 30h
0x18001135c  pop     r14
0x18001135e  pop     rdi
0x18001135f  pop     rbp
0x180011360  retn
0x180011362  mov     edx, 1Eh
0x180011367  jmp     short loc_18001138D
0x180011369  mov     rax, [rcx]
0x18001136c  mov     rax, [rax+10h]
0x180011370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011375  jmp     loc_18001125D
0x18001137a  mov     edx, 21h ; '!'
0x18001137f  jmp     short loc_18001138D
0x180011381  mov     edx, 22h ; '"'
0x180011386  jmp     short loc_18001138D
0x180011388  mov     edx, 23h ; '#'; void *
0x18001138d  mov     rcx, [rbp+18h]; this
0x180011391  lea     r8, aMultimediaDsho_1; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x180011398  mov     r9d, eax; char *
0x18001139b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800113a0  lea     rcx, [rbp+arg_10]
0x1800113a4  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x1800113a9  lea     rcx, [rbp+arg_18]
0x1800113ad  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x1800113b2  mov     eax, ebx
0x1800113b4  jmp     short loc_18001134E
0x1800113b6  mov     rax, [rbx]
0x1800113b9  mov     rcx, rbx
0x1800113bc  mov     rax, [rax+10h]
0x1800113c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113c5  mov     rcx, [rbp+arg_10]
0x1800113c9  jmp     loc_180011326
```
