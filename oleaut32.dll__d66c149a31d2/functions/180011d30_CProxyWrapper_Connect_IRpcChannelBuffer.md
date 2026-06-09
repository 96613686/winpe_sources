# CProxyWrapper::Connect(IRpcChannelBuffer *)

- ea: `0x180011d30`
- end: `0x180011f7c`
- name: `?Connect@CProxyWrapper@@UEAAJPEAUIRpcChannelBuffer@@@Z`
- size: `588`
- prototype: `__int64 __fastcall(CProxyWrapper *__hidden this, struct IRpcChannelBuffer *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, installer_update`

## callees

- `0x180011d30`
- `0x180011f84`
- `0x180011fb4`
- `0x180012020`
- `0x18004a530`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011e98`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011e98`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011d5b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011d5b`
- `RPCRT4!CreateProxyFromTypeInfo` at `0x180011f26`
- `RPCRT4!CreateProxyFromTypeInfo` at `0x180011f26`
- `RPCRT4!NdrDllGetClassObject` at `0x180011df5`
- `RPCRT4!NdrDllGetClassObject` at `0x180011df5`

## pseudocode

```c
__int64 __fastcall CProxyWrapper::Connect(CProxyWrapper *this, struct IRpcChannelBuffer *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // r12
  struct IRpcChannelBuffer *v4; // r13
  _QWORD *v5; // r15
  int v6; // r14d
  int v7; // esi
  signed int TypeInfoOfIIDFwd; // ebx
  HRESULT ClassObject; // eax
  struct IPSFactoryBuffer *v10; // rcx
  GUID *v11; // r8
  __int64 v13; // [rsp+30h] [rbp-28h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-20h] BYREF
  HANDLE Token; // [rsp+40h] [rbp-18h] BYREF
  void *ppv; // [rsp+A0h] [rbp+48h] BYREF
  struct IRpcChannelBuffer *v17; // [rsp+A8h] [rbp+50h]
  struct ITypeInfo *v18; // [rsp+B0h] [rbp+58h] BYREF
  __int64 v19; // [rsp+B8h] [rbp+60h]

  v17 = a2;
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 56);
  v4 = a2;
  v13 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  v5 = (_QWORD *)((char *)this + 48);
  if ( *((_QWORD *)this + 6) )
    goto LABEL_17;
  v6 = 1;
  if ( ((__int64 (__fastcall *)(struct IRpcChannelBuffer *, __int64 *, __int64 *))v4->lpVtbl->QueryInterface)(
         v4,
         qword_1800AC978,
         &v13) >= 0 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    *((_DWORD *)this + 7) |= 1u;
  }
  else
  {
    *((_DWORD *)this + 7) &= ~1u;
  }
  v7 = *((_DWORD *)this + 7);
  v19 = *((_QWORD *)this + 4);
  Token = 0;
  TypeInfoOfIIDFwd = SuspendImpersonate(&Token);
  if ( TypeInfoOfIIDFwd >= 0 )
  {
    ppv = 0;
    if ( (v7 & 1) != 0 )
    {
      v6 = 0;
      v10 = COleAutomationPSFactory::Create();
      ppv = v10;
      TypeInfoOfIIDFwd = v10 == 0 ? 0x8007000E : 0;
    }
    else
    {
      ClassObject = NdrDllGetClassObject(
                      &IID_IProvideClassInfo,
                      &IID_IPSFactoryBuffer,
                      &ppv,
                      (const ProxyFileInfo **)&aProxyFileList,
                      &IID_IProvideClassInfo,
                      &gPFactory);
      v10 = (struct IPSFactoryBuffer *)ppv;
      TypeInfoOfIIDFwd = ClassObject;
    }
    if ( !v10 )
    {
LABEL_15:
      ResumeImpersonate(Token);
      if ( TypeInfoOfIIDFwd >= 0 )
      {
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 16LL))(*((_QWORD *)this + 5));
LABEL_17:
        TypeInfoOfIIDFwd = (*(__int64 (__fastcall **)(_QWORD, struct IRpcChannelBuffer *))(*(_QWORD *)*v5 + 24LL))(
                             *v5,
                             v4);
        goto LABEL_18;
      }
      goto LABEL_18;
    }
    if ( v6 )
    {
      if ( (v7 & 4) != 0 )
      {
        v11 = &IID_IDispatch;
        goto LABEL_12;
      }
      if ( (v7 & 2) != 0 )
      {
        v18 = 0;
        TokenHandle = 0;
        TypeInfoOfIIDFwd = SuspendImpersonate(&TokenHandle);
        if ( TypeInfoOfIIDFwd >= 0 )
        {
          TypeInfoOfIIDFwd = GetTypeInfoOfIIDFwd((const struct _GUID *)((char *)this + 12), &v18, 0);
          ResumeImpersonate(TokenHandle);
          if ( TypeInfoOfIIDFwd < 0 )
            goto LABEL_23;
          TypeInfoOfIIDFwd = CreateProxyFromTypeInfo(v18, v19, (char *)this + 12, (char *)this + 48, (char *)this + 40);
          ((void (__fastcall *)(struct ITypeInfo *))v18->lpVtbl->Release)(v18);
        }
LABEL_13:
        if ( TypeInfoOfIIDFwd >= 0 )
        {
LABEL_14:
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
          v4 = v17;
          v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 56);
          goto LABEL_15;
        }
LABEL_23:
        *v5 = 0;
        *((_QWORD *)this + 5) = 0;
        goto LABEL_14;
      }
    }
    v11 = (GUID *)((char *)this + 12);
LABEL_12:
    TypeInfoOfIIDFwd = ((__int64 (__fastcall *)(struct IPSFactoryBuffer *, __int64, GUID *, char *, char *))v10->lpVtbl->CreateProxy)(
                         v10,
                         v19,
                         v11,
                         (char *)this + 48,
                         (char *)this + 40);
    goto LABEL_13;
  }
LABEL_18:
  LeaveCriticalSection(v2);
  return (unsigned int)TypeInfoOfIIDFwd;
}

```

## disassembly

```asm
0x180011d30  mov     [rsp-40h+arg_8], rdx
0x180011d35  push    rbp
0x180011d36  push    rbx
0x180011d37  push    rsi
0x180011d38  push    rdi
0x180011d39  push    r12
0x180011d3b  push    r13
0x180011d3d  push    r14
0x180011d3f  push    r15
0x180011d41  mov     rbp, rsp
0x180011d44  sub     rsp, 58h
0x180011d48  lea     r12, [rcx+38h]
0x180011d4c  mov     rdi, rcx
0x180011d4f  xor     ebx, ebx
0x180011d51  mov     rcx, r12; lpCriticalSection
0x180011d54  mov     r13, rdx
0x180011d57  mov     [rbp+var_28], rbx
0x180011d5b  call    cs:__imp_EnterCriticalSection
0x180011d61  lea     r15, [rdi+30h]
0x180011d65  cmp     [r15], rbx
0x180011d68  jnz     loc_180011E81
0x180011d6e  mov     rax, [r13+0]
0x180011d72  lea     r8, [rbp+var_28]
0x180011d76  lea     rdx, qword_1800AC978
0x180011d7d  mov     rcx, r13
0x180011d80  mov     rax, [rax]
0x180011d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d88  lea     r14d, [rbx+1]
0x180011d8c  test    eax, eax
0x180011d8e  jns     loc_180011F63
0x180011d94  and     dword ptr [rdi+1Ch], 0FFFFFFFEh
0x180011d98  mov     rax, [rdi+20h]
0x180011d9c  lea     rcx, [rbp+Token]; TokenHandle
0x180011da0  mov     esi, [rdi+1Ch]
0x180011da3  mov     [rbp+arg_18], rax
0x180011da7  mov     [rbp+Token], rbx
0x180011dab  call    ?SuspendImpersonate@@YAJPEAPEAX@Z; SuspendImpersonate(void * *)
0x180011db0  mov     ebx, eax
0x180011db2  test    eax, eax
0x180011db4  js      loc_180011E95
0x180011dba  mov     [rbp+ppv], 0
0x180011dc2  test    r14b, sil
0x180011dc5  jnz     loc_180011EB1
0x180011dcb  lea     rax, gPFactory
0x180011dd2  lea     rcx, IID_IProvideClassInfo; rclsid
0x180011dd9  mov     [rsp+58h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x180011dde  lea     r9, aProxyFileList; pProxyFileList
0x180011de5  mov     [rsp+58h+pclsid], rcx; pclsid
0x180011dea  lea     r8, [rbp+ppv]; ppv
0x180011dee  lea     rdx, IID_IPSFactoryBuffer; riid
0x180011df5  call    cs:__imp_NdrDllGetClassObject
0x180011dfb  mov     rcx, [rbp+ppv]
0x180011dff  mov     ebx, eax
0x180011e01  test    rcx, rcx
0x180011e04  jz      short loc_180011E64
0x180011e06  lea     r12, [rdi+28h]
0x180011e0a  lea     r13, [rdi+0Ch]
0x180011e0e  test    r14d, r14d
0x180011e11  jz      short loc_180011E27
0x180011e13  test    sil, 4
0x180011e17  jnz     loc_180011F57
0x180011e1d  test    sil, 2
0x180011e21  jnz     loc_180011ED2
0x180011e27  mov     r8, r13
0x180011e2a  mov     rax, [rcx]
0x180011e2d  mov     r9, r15
0x180011e30  mov     rdx, [rbp+arg_18]
0x180011e34  mov     [rsp+58h+pclsid], r12
0x180011e39  mov     rax, [rax+18h]
0x180011e3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e42  mov     ebx, eax
0x180011e44  test    ebx, ebx
0x180011e46  js      loc_180011F43
0x180011e4c  mov     rcx, [rbp+ppv]
0x180011e50  mov     rax, [rcx]
0x180011e53  mov     rax, [rax+10h]
0x180011e57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e5c  mov     r13, [rbp+arg_8]
0x180011e60  lea     r12, [rdi+38h]
0x180011e64  mov     rcx, [rbp+Token]; Token
0x180011e68  call    ?ResumeImpersonate@@YAXPEAX@Z; ResumeImpersonate(void *)
0x180011e6d  test    ebx, ebx
0x180011e6f  js      short loc_180011E95
0x180011e71  mov     rcx, [rdi+28h]
0x180011e75  mov     rax, [rcx]
0x180011e78  mov     rax, [rax+10h]
0x180011e7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e81  mov     rcx, [r15]
0x180011e84  mov     rdx, r13
0x180011e87  mov     rax, [rcx]
0x180011e8a  mov     rax, [rax+18h]
0x180011e8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e93  mov     ebx, eax
0x180011e95  mov     rcx, r12; lpCriticalSection
0x180011e98  call    cs:__imp_LeaveCriticalSection
0x180011e9e  mov     eax, ebx
0x180011ea0  add     rsp, 58h
0x180011ea4  pop     r15
0x180011ea6  pop     r14
0x180011ea8  pop     r13
0x180011eaa  pop     r12
0x180011eac  pop     rdi
0x180011ead  pop     rsi
0x180011eae  pop     rbx
0x180011eaf  pop     rbp
0x180011eb0  retn
0x180011eb1  xor     r14d, r14d
0x180011eb4  call    ?Create@COleAutomationPSFactory@@SAPEAUIPSFactoryBuffer@@XZ; COleAutomationPSFactory::Create(void)
0x180011eb9  mov     rcx, rax
0x180011ebc  mov     [rbp+ppv], rax
0x180011ec0  neg     rax
0x180011ec3  sbb     ebx, ebx
0x180011ec5  not     ebx
0x180011ec7  and     ebx, 8007000Eh
0x180011ecd  jmp     loc_180011E01
0x180011ed2  lea     rcx, [rbp+TokenHandle]; TokenHandle
0x180011ed6  mov     [rbp+arg_10], 0
0x180011ede  mov     [rbp+TokenHandle], 0
0x180011ee6  call    ?SuspendImpersonate@@YAJPEAPEAX@Z; SuspendImpersonate(void * *)
0x180011eeb  mov     ebx, eax
0x180011eed  test    eax, eax
0x180011eef  js      loc_180011E44
0x180011ef5  xor     r8d, r8d; int
0x180011ef8  lea     rdx, [rbp+arg_10]; struct ITypeInfo **
0x180011efc  mov     rcx, r13; struct _GUID *
0x180011eff  call    ?GetTypeInfoOfIIDFwd@@YAJAEBU_GUID@@PEAPEAUITypeInfo@@H@Z; GetTypeInfoOfIIDFwd(_GUID const &,ITypeInfo * *,int)
0x180011f04  mov     rcx, [rbp+TokenHandle]; Token
0x180011f08  mov     ebx, eax
0x180011f0a  call    ?ResumeImpersonate@@YAXPEAX@Z; ResumeImpersonate(void *)
0x180011f0f  test    ebx, ebx
0x180011f11  js      short loc_180011F43
0x180011f13  mov     rdx, [rbp+arg_18]
0x180011f17  mov     r9, r15
0x180011f1a  mov     rcx, [rbp+arg_10]
0x180011f1e  mov     r8, r13
0x180011f21  mov     [rsp+58h+pclsid], r12
0x180011f26  call    cs:__imp_CreateProxyFromTypeInfo
0x180011f2c  mov     rcx, [rbp+arg_10]
0x180011f30  mov     ebx, eax
0x180011f32  mov     rax, [rcx]
0x180011f35  mov     rax, [rax+10h]
0x180011f39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f3e  jmp     loc_180011E44
0x180011f43  mov     qword ptr [r15], 0
0x180011f4a  mov     qword ptr [r12], 0
0x180011f52  jmp     loc_180011E4C
0x180011f57  lea     r8, IID_IDispatch
0x180011f5e  jmp     loc_180011E2A
0x180011f63  mov     rcx, [rbp+var_28]
0x180011f67  mov     rax, [rcx]
0x180011f6a  mov     rax, [rax+10h]
0x180011f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f73  or      [rdi+1Ch], r14d
0x180011f77  jmp     loc_180011D98
```
