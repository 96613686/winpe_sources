# CFtpFolder::CreateViewObject(HWND__ *,_GUID const &,void * *)

- ea: `0x1800162d0`
- end: `0x180016441`
- name: `?CreateViewObject@CFtpFolder@@UEAAJPEAUHWND__@@AEBU_GUID@@PEAPEAX@Z`
- size: `369`
- prototype: `__int64 __fastcall(CFtpFolder *__hidden this, HWND, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task`

## callees

- `0x1800162d0`
- `0x180018038`
- `0x18001862c`
- `0x180018dc0`
- `0x180024068`
- `0x180028010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180016392`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180016392`

## pseudocode

```c
__int64 __fastcall CFtpFolder::CreateViewObject(IUnknown **this, HWND a2, const struct _GUID *a3, void **a4)
{
  IUnknown *v8; // rcx
  unsigned int v9; // ebp
  struct IShellFolder *LegacyShellFolder; // rsi
  void *ppvOut; // [rsp+30h] [rbp-48h] BYREF
  int v13; // [rsp+98h] [rbp+20h] BYREF

  *a4 = 0;
  v13 = 1;
  if ( *(_OWORD *)a3 == *(_OWORD *)&IID_IResolveShellLink
    || *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IShellDetails.Data1
    && *(_QWORD *)a3->Data4 == *(_QWORD *)IID_IShellDetails.Data4
    || *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IFrameLayoutDefinition.Data1
    && *(_QWORD *)a3->Data4 == *(_QWORD *)IID_IFrameLayoutDefinition.Data4
    || !(unsigned int)CFtpFolder::_NeedToFallBack(
                        (CFtpFolder *)this,
                        (const struct _ITEMIDLIST *)((char *)this[6] + *((int *)this + 16)),
                        &v13) )
  {
    return (unsigned int)CFtpFolder::_CreateViewObject((CFtpFolder *)this, a2, a3, a4);
  }
  else
  {
    v8 = this[4];
    ppvOut = 0;
    v9 = -2147467259;
    if ( IUnknown_QueryService(
           v8,
           (const GUID *const)&SID_STopLevelBrowser,
           &GUID_000214f1_0000_0000_c000_000000000046,
           &ppvOut) < 0 )
    {
      LegacyShellFolder = CFtpFolder::_GetLegacyShellFolder((CFtpFolder *)this);
    }
    else
    {
      LegacyShellFolder = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
    }
    if ( v13
      && *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IShellView.Data1
      && *(_QWORD *)a3->Data4 == *(_QWORD *)IID_IShellView.Data4 )
    {
      DisplayBlockingProxyDialog((const struct _ITEMIDLIST *)((char *)this[6] + *((int *)this + 16)), a2);
    }
    if ( LegacyShellFolder )
    {
      v9 = ((__int64 (__fastcall *)(struct IShellFolder *, HWND, const struct _GUID *, void **))LegacyShellFolder->lpVtbl->CreateViewObject)(
             LegacyShellFolder,
             a2,
             a3,
             a4);
      ((void (__fastcall *)(struct IShellFolder *))LegacyShellFolder->lpVtbl->Release)(LegacyShellFolder);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x1800162d0  mov     rax, rsp
0x1800162d3  push    rbx
0x1800162d4  push    rbp
0x1800162d5  push    rsi
0x1800162d6  push    rdi
0x1800162d7  push    r14
0x1800162d9  push    r15
0x1800162db  sub     rsp, 48h
0x1800162df  mov     qword ptr [r9], 0
0x1800162e6  mov     r15, r9
0x1800162e9  mov     dword ptr [rax+20h], 1
0x1800162f0  mov     rbx, r8
0x1800162f3  mov     rax, [r8]
0x1800162f6  mov     r14, rdx
0x1800162f9  cmp     rax, qword ptr cs:IID_IResolveShellLink.Data1
0x180016300  mov     rdi, rcx
0x180016303  jnz     short loc_180016316
0x180016305  mov     rax, [r8+8]
0x180016309  cmp     rax, qword ptr cs:IID_IResolveShellLink.Data4
0x180016310  jz      loc_18001641F
0x180016316  mov     rax, [r8]
0x180016319  cmp     rax, qword ptr cs:IID_IShellDetails.Data1
0x180016320  jnz     short loc_180016333
0x180016322  mov     rax, [r8+8]
0x180016326  cmp     rax, qword ptr cs:IID_IShellDetails.Data4
0x18001632d  jz      loc_18001641F
0x180016333  mov     rax, [r8]
0x180016336  cmp     rax, qword ptr cs:IID_IFrameLayoutDefinition.Data1
0x18001633d  jnz     short loc_180016350
0x18001633f  mov     rax, [r8+8]
0x180016343  cmp     rax, qword ptr cs:IID_IFrameLayoutDefinition.Data4
0x18001634a  jz      loc_18001641F
0x180016350  movsxd  rdx, dword ptr [rcx+40h]
0x180016354  lea     r8, [rsp+78h+arg_18]; int *
0x18001635c  add     rdx, [rcx+30h]; struct _ITEMIDLIST *
0x180016360  call    ?_NeedToFallBack@CFtpFolder@@IEAAHPEFBU_ITEMIDLIST@@PEAH@Z; CFtpFolder::_NeedToFallBack(_ITEMIDLIST const *,int *)
0x180016365  test    eax, eax
0x180016367  jz      loc_18001641F
0x18001636d  mov     rcx, [rdi+20h]; punk
0x180016371  lea     r9, [rsp+78h+ppvOut]; ppvOut
0x180016376  lea     r8, _GUID_000214f1_0000_0000_c000_000000000046; riid
0x18001637d  mov     [rsp+78h+ppvOut], 0
0x180016386  lea     rdx, SID_STopLevelBrowser; guidService
0x18001638d  mov     ebp, 80004005h
0x180016392  call    cs:__imp_IUnknown_QueryService
0x180016398  test    eax, eax
0x18001639a  js      short loc_1800163B1
0x18001639c  mov     rcx, [rsp+78h+ppvOut]
0x1800163a1  xor     esi, esi
0x1800163a3  mov     rax, [rcx]
0x1800163a6  mov     rax, [rax+10h]
0x1800163aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163af  jmp     short loc_1800163BC
0x1800163b1  mov     rcx, rdi; this
0x1800163b4  call    ?_GetLegacyShellFolder@CFtpFolder@@IEAAPEAUIShellFolder@@XZ; CFtpFolder::_GetLegacyShellFolder(void)
0x1800163b9  mov     rsi, rax
0x1800163bc  cmp     [rsp+78h+arg_18], 0
0x1800163c4  jz      short loc_1800163EF
0x1800163c6  mov     rcx, [rbx]
0x1800163c9  cmp     rcx, qword ptr cs:IID_IShellView.Data1
0x1800163d0  jnz     short loc_1800163EF
0x1800163d2  mov     rcx, [rbx+8]
0x1800163d6  cmp     rcx, qword ptr cs:IID_IShellView.Data4
0x1800163dd  jnz     short loc_1800163EF
0x1800163df  movsxd  rcx, dword ptr [rdi+40h]
0x1800163e3  mov     rdx, r14; hWnd
0x1800163e6  add     rcx, [rdi+30h]; struct _ITEMIDLIST *
0x1800163ea  call    ?DisplayBlockingProxyDialog@@YAJPEFBU_ITEMIDLIST@@PEAUHWND__@@@Z; DisplayBlockingProxyDialog(_ITEMIDLIST const *,HWND__ *)
0x1800163ef  test    rsi, rsi
0x1800163f2  jz      short loc_180016432
0x1800163f4  mov     rax, [rsi]
0x1800163f7  mov     r9, r15
0x1800163fa  mov     r8, rbx
0x1800163fd  mov     rdx, r14
0x180016400  mov     rcx, rsi
0x180016403  mov     rax, [rax+40h]
0x180016407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001640c  mov     rcx, [rsi]
0x18001640f  mov     ebp, eax
0x180016411  mov     rax, [rcx+10h]
0x180016415  mov     rcx, rsi
0x180016418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001641d  jmp     short loc_180016432
0x18001641f  mov     r9, r15; void **
0x180016422  mov     r8, rbx; struct _GUID *
0x180016425  mov     rdx, r14; HWND
0x180016428  mov     rcx, rdi; this
0x18001642b  call    ?_CreateViewObject@CFtpFolder@@IEAAJPEAUHWND__@@AEBU_GUID@@PEAPEAX@Z; CFtpFolder::_CreateViewObject(HWND__ *,_GUID const &,void * *)
0x180016430  mov     ebp, eax
0x180016432  mov     eax, ebp
0x180016434  add     rsp, 48h
0x180016438  pop     r15
0x18001643a  pop     r14
0x18001643c  pop     rdi
0x18001643d  pop     rsi
0x18001643e  pop     rbp
0x18001643f  pop     rbx
0x180016440  retn
```
