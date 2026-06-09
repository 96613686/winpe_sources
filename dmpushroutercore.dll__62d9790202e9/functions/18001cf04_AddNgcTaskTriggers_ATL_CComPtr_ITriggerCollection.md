# AddNgcTaskTriggers(ATL::CComPtr<ITriggerCollection> &)

- ea: `0x18001cf04`
- end: `0x18001d18b`
- name: `?AddNgcTaskTriggers@@YAJAEAV?$CComPtr@UITriggerCollection@@@ATL@@@Z`
- size: `647`
- prototype: `__int64 __fastcall(struct ITriggerCollection **)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180038390`

## callees

- `0x1800039f0`
- `0x18000604c`
- `0x180013d4c`
- `0x18001ce6c`
- `0x18001cf04`
- `0x18001d194`
- `0x18001d30c`
- `0x1800235ac`
- `0x18003593c`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cfd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cfd1`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d0a2`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d0a2`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18001cf52`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18001cf52`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001d14c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001d14c`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18001cf6c`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18001cf6c`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18001d13f`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18001d13f`
- `SspiCli!GetUserNameExW` at `0x18001cfc7`
- `SspiCli!GetUserNameExW` at `0x18001cfc7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AddNgcTaskTriggers(struct ITriggerCollection **a1)
{
  SAFEARRAY *v2; // rax
  SAFEARRAY *v3; // rbx
  HRESULT v4; // eax
  unsigned int i; // edi
  signed int v6; // edi
  signed int LastError; // eax
  struct ITriggerCollection *v8; // rcx
  int v9; // eax
  SAFEARRAYBOUND v10; // rcx
  SAFEARRAY *v11; // rcx
  SAFEARRAY *v12; // r14
  __int64 v13; // r15
  BSTR *v14; // rdi
  BSTR v15; // rax
  const struct std::nothrow_t *v16; // rdx
  int v17; // eax
  SAFEARRAY *v19; // [rsp+20h] [rbp-E0h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+28h] [rbp-D8h] BYREF
  ULONG nSize; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR NameBuffer[264]; // [rsp+40h] [rbp-C0h] BYREF

  v22 = WNF_NGC_GESTURE_AUTHENTICATED;
  rgsabound = (SAFEARRAYBOUND)8LL;
  v2 = SafeArrayCreate(0x11u, 1u, &rgsabound);
  v19 = v2;
  v3 = v2;
  if ( !v2 )
  {
    v4 = -2147024882;
LABEL_31:
    ATL::AtlThrowImpl(v4);
  }
  v4 = SafeArrayLock(v2);
  if ( v4 < 0 )
    goto LABEL_31;
  for ( i = 0; i < 8; ++i )
    ATL::CComSafeArray<unsigned char,17>::SetAt(&v19, i, (char *)&NameBuffer[-4] + i);
  v6 = AddTaskWNFTrigger(*a1, &v19);
  if ( v6 < 0 )
    goto LABEL_25;
  nSize = 260;
  if ( !GetUserNameExW(NameSamCompatible, NameBuffer, &nSize) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_25;
  }
  v8 = *a1;
  rgsabound = 0;
  v9 = ((__int64 (__fastcall *)(struct ITriggerCollection *, __int64, SAFEARRAYBOUND *))v8->lpVtbl->Create)(
         v8,
         9,
         &rgsabound);
  v10 = rgsabound;
  v6 = v9;
  if ( v9 < 0 )
    goto LABEL_10;
  v19 = 0;
  v6 = (***(__int64 (__fastcall ****)(SAFEARRAYBOUND, GUID *, SAFEARRAY **))&rgsabound)(
         rgsabound,
         &IID_ILogonTrigger,
         &v19);
  if ( v6 < 0 )
  {
    v11 = v19;
LABEL_14:
    if ( v11 )
      (*(void (__fastcall **)(SAFEARRAY *))(*(_QWORD *)&v11->cDims + 16LL))(v11);
    v10 = rgsabound;
LABEL_10:
    if ( v10 )
      (*(void (__fastcall **)(SAFEARRAYBOUND))(**(_QWORD **)&v10 + 16LL))(v10);
    goto LABEL_25;
  }
  v12 = v19;
  v13 = *(_QWORD *)&v19->cDims;
  v14 = (BSTR *)operator new(0x18u);
  v14[1] = 0;
  *((_DWORD *)v14 + 4) = 1;
  v15 = SysAllocString(NameBuffer);
  *v14 = v15;
  if ( !v15 )
    _com_issue_error(-2147024882);
  v22 = (__int64)v14;
  v6 = (*(__int64 (__fastcall **)(SAFEARRAY *, BSTR))(v13 + 184))(v12, v15);
  _bstr_t::~_bstr_t((_bstr_t *)&v22, v16);
  v11 = v19;
  if ( v6 < 0 )
    goto LABEL_14;
  v17 = (*(__int64 (__fastcall **)(SAFEARRAY *, __int64))(*(_QWORD *)&v19->cDims + 152LL))(v19, 0xFFFFFFFFLL);
  v11 = v19;
  v6 = v17;
  if ( v17 < 0 )
    goto LABEL_14;
  if ( v19 )
    (*(void (**)(void))(*(_QWORD *)&v19->cDims + 16LL))();
  if ( rgsabound )
    (*(void (__fastcall **)(SAFEARRAYBOUND))(**(_QWORD **)&rgsabound + 16LL))(rgsabound);
  v6 = AddTaskUnlockTrigger(*a1, NameBuffer);
LABEL_25:
  if ( v3 && SafeArrayUnlock(v3) >= 0 )
    SafeArrayDestroy(v3);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001cf04  push    rbp
0x18001cf06  push    rbx
0x18001cf07  push    rsi
0x18001cf08  push    rdi
0x18001cf09  push    r14
0x18001cf0b  push    r15
0x18001cf0d  lea     rbp, [rsp-168h]
0x18001cf15  sub     rsp, 268h
0x18001cf1c  mov     rax, cs:__security_cookie
0x18001cf23  xor     rax, rsp
0x18001cf26  mov     [rbp+190h+var_40], rax
0x18001cf2d  mov     rax, cs:WNF_NGC_GESTURE_AUTHENTICATED
0x18001cf34  lea     r8, [rsp+290h+rgsabound]; rgsabound
0x18001cf39  mov     rsi, rcx
0x18001cf3c  mov     [rsp+290h+var_258], rax
0x18001cf41  mov     ecx, 11h; vt
0x18001cf46  mov     qword ptr [rsp+290h+rgsabound.cElements], 8
0x18001cf4f  lea     edx, [rcx-10h]; cDims
0x18001cf52  call    cs:__imp_SafeArrayCreate
0x18001cf58  mov     [rsp+290h+var_270], rax
0x18001cf5d  mov     rbx, rax
0x18001cf60  test    rax, rax
0x18001cf63  jz      loc_18001D17E
0x18001cf69  mov     rcx, rbx; psa
0x18001cf6c  call    cs:__imp_SafeArrayLock
0x18001cf72  test    eax, eax
0x18001cf74  js      loc_18001D183
0x18001cf7a  xor     edi, edi
0x18001cf7c  mov     eax, edi
0x18001cf7e  lea     r8, [rsp+290h+var_258]
0x18001cf83  add     r8, rax
0x18001cf86  lea     rcx, [rsp+290h+var_270]
0x18001cf8b  mov     edx, edi
0x18001cf8d  call    ?SetAt@?$CComSafeArray@E$0BB@@ATL@@QEAAJJAEBEH@Z; ATL::CComSafeArray<uchar,17>::SetAt(long,uchar const &,int)
0x18001cf92  inc     edi
0x18001cf94  cmp     edi, 8
0x18001cf97  jb      short loc_18001CF7C
0x18001cf99  mov     rcx, [rsi]
0x18001cf9c  lea     rdx, [rsp+290h+var_270]
0x18001cfa1  call    ?AddTaskWNFTrigger@@YAJPEAUITriggerCollection@@PEAV?$CComSafeArray@E$0BB@@ATL@@@Z; AddTaskWNFTrigger(ITriggerCollection *,ATL::CComSafeArray<uchar,17> *)
0x18001cfa6  mov     edi, eax
0x18001cfa8  test    eax, eax
0x18001cfaa  js      loc_18001D137
0x18001cfb0  lea     r8, [rsp+290h+nSize]; nSize
0x18001cfb5  mov     [rsp+290h+nSize], 104h
0x18001cfbd  lea     rdx, [rsp+290h+NameBuffer]; lpNameBuffer
0x18001cfc2  mov     ecx, 2; NameFormat
0x18001cfc7  call    cs:__imp_GetUserNameExW
0x18001cfcd  test    al, al
0x18001cfcf  jnz     short loc_18001CFEF
0x18001cfd1  call    cs:__imp_GetLastError
0x18001cfd7  mov     edi, eax
0x18001cfd9  test    eax, eax
0x18001cfdb  jle     loc_18001D137
0x18001cfe1  movzx   edi, ax
0x18001cfe4  or      edi, 80070000h
0x18001cfea  jmp     loc_18001D137
0x18001cfef  mov     rcx, [rsi]
0x18001cff2  lea     r8, [rsp+290h+rgsabound]
0x18001cff7  mov     edx, 9
0x18001cffc  mov     qword ptr [rsp+290h+rgsabound.cElements], 0
0x18001d005  mov     rax, [rcx]
0x18001d008  mov     rax, [rax+50h]
0x18001d00c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d011  mov     rcx, qword ptr [rsp+290h+rgsabound.cElements]
0x18001d016  mov     edi, eax
0x18001d018  test    eax, eax
0x18001d01a  jns     short loc_18001D036
0x18001d01c  test    rcx, rcx
0x18001d01f  jz      loc_18001D137
0x18001d025  mov     rax, [rcx]
0x18001d028  mov     rax, [rax+10h]
0x18001d02c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d031  jmp     loc_18001D137
0x18001d036  mov     [rsp+290h+var_270], 0
0x18001d03f  lea     r8, [rsp+290h+var_270]
0x18001d044  mov     rax, [rcx]
0x18001d047  lea     rdx, IID_ILogonTrigger
0x18001d04e  mov     rax, [rax]
0x18001d051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d056  mov     edi, eax
0x18001d058  test    eax, eax
0x18001d05a  jns     short loc_18001D079
0x18001d05c  mov     rcx, [rsp+290h+var_270]
0x18001d061  test    rcx, rcx
0x18001d064  jz      short loc_18001D072
0x18001d066  mov     rax, [rcx]
0x18001d069  mov     rax, [rax+10h]
0x18001d06d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d072  mov     rcx, qword ptr [rsp+290h+rgsabound.cElements]
0x18001d077  jmp     short loc_18001D01C
0x18001d079  mov     r14, [rsp+290h+var_270]
0x18001d07e  mov     ecx, 18h; Size
0x18001d083  mov     r15, [r14]
0x18001d086  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d08b  lea     rcx, [rsp+290h+NameBuffer]; psz
0x18001d090  mov     rdi, rax
0x18001d093  mov     qword ptr [rax+8], 0
0x18001d09b  mov     dword ptr [rax+10h], 1
0x18001d0a2  call    cs:__imp_SysAllocString
0x18001d0a8  mov     [rdi], rax
0x18001d0ab  test    rax, rax
0x18001d0ae  jz      loc_18001D173
0x18001d0b4  mov     rdx, rax
0x18001d0b7  mov     [rsp+290h+var_258], rdi
0x18001d0bc  mov     rax, [r15+0B8h]
0x18001d0c3  mov     rcx, r14
0x18001d0c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0cb  lea     rcx, [rsp+290h+var_258]; this
0x18001d0d0  mov     edi, eax
0x18001d0d2  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18001d0d7  mov     rcx, [rsp+290h+var_270]
0x18001d0dc  test    edi, edi
0x18001d0de  js      short loc_18001D061
0x18001d0e0  mov     rax, [rcx]
0x18001d0e3  or      edx, 0FFFFFFFFh
0x18001d0e6  mov     rax, [rax+98h]
0x18001d0ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0f2  mov     rcx, [rsp+290h+var_270]
0x18001d0f7  mov     edi, eax
0x18001d0f9  test    eax, eax
0x18001d0fb  js      loc_18001D061
0x18001d101  test    rcx, rcx
0x18001d104  jz      short loc_18001D112
0x18001d106  mov     rax, [rcx]
0x18001d109  mov     rax, [rax+10h]
0x18001d10d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d112  mov     rcx, qword ptr [rsp+290h+rgsabound.cElements]
0x18001d117  test    rcx, rcx
0x18001d11a  jz      short loc_18001D128
0x18001d11c  mov     rax, [rcx]
0x18001d11f  mov     rax, [rax+10h]
0x18001d123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d128  mov     rcx, [rsi]; struct ITriggerCollection *
0x18001d12b  lea     rdx, [rsp+290h+NameBuffer]; unsigned __int16 *
0x18001d130  call    ?AddTaskUnlockTrigger@@YAJPEAUITriggerCollection@@PEAG@Z; AddTaskUnlockTrigger(ITriggerCollection *,ushort *)
0x18001d135  mov     edi, eax
0x18001d137  test    rbx, rbx
0x18001d13a  jz      short loc_18001D152
0x18001d13c  mov     rcx, rbx; psa
0x18001d13f  call    cs:__imp_SafeArrayUnlock
0x18001d145  test    eax, eax
0x18001d147  js      short loc_18001D152
0x18001d149  mov     rcx, rbx; psa
0x18001d14c  call    cs:__imp_SafeArrayDestroy
0x18001d152  mov     eax, edi
0x18001d154  mov     rcx, [rbp+190h+var_40]
0x18001d15b  xor     rcx, rsp; StackCookie
0x18001d15e  call    __security_check_cookie
0x18001d163  add     rsp, 268h
0x18001d16a  pop     r15
0x18001d16c  pop     r14
0x18001d16e  pop     rdi
0x18001d16f  pop     rsi
0x18001d170  pop     rbx
0x18001d171  pop     rbp
0x18001d172  retn
0x18001d173  mov     ecx, 8007000Eh; int
0x18001d178  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18001d17e  mov     eax, 8007000Eh
0x18001d183  mov     ecx, eax; int
0x18001d185  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
