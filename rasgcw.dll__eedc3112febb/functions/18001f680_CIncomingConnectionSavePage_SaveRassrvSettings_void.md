# CIncomingConnectionSavePage::SaveRassrvSettings(void)

- ea: `0x18001f680`
- end: `0x18001f769`
- name: `?SaveRassrvSettings@CIncomingConnectionSavePage@@AEAAHXZ`
- size: `233`
- prototype: `__int64 __fastcall(CIncomingConnectionSavePage *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001f2c0`

## callees

- `0x1800114d8`
- `0x18001f680`
- `0x180020c48`
- `0x180030010`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x18001f74f`
- `rtutils!TracePrintfExA` at `0x18001f74f`

## string_xrefs

- `0x18001f745`: `RassrvCommitSettings failed: %u:`

## pseudocode

```c
__int64 __fastcall CIncomingConnectionSavePage::SaveRassrvSettings(CIncomingConnectionSavePage *this)
{
  _QWORD *v1; // rdi
  __int64 v3; // rcx
  __int64 v5; // [rsp+40h] [rbp+8h] BYREF

  v1 = (_QWORD *)((char *)this + 144);
  if ( (int)HrEnsureTearOffInterfaceLoaded(*((_QWORD *)this + 16), &IID_IXWizardTransaction, (char *)this + 144) < 0 )
    return 0;
  if ( (*(int (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v1 + 24LL))(*v1, 0) < 0 )
    return 0;
  if ( (int)HrEnsureTearOffInterfaceLoaded(*((_QWORD *)this + 16), &IID_IXWizardPropertyBag, (char *)this + 136) < 0 )
    return 0;
  v3 = *((_QWORD *)this + 17);
  v5 = 0;
  if ( (*(int (__fastcall **)(__int64, GUID *, const wchar_t *, __int64 *, _QWORD))(*(_QWORD *)v3 + 48LL))(
         v3,
         &CLSID_IncomingConnectionHookPage,
         L"ICCPageHandle",
         &v5,
         0) < 0
    || (unsigned int)RassrvCommitSettings(v5, 3) )
  {
    return 0;
  }
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "RassrvCommitSettings failed: %u:", 0);
  return 1;
}

```

## disassembly

```asm
0x18001f680  mov     [rsp+arg_8], rbx
0x18001f685  push    rdi
0x18001f686  sub     rsp, 30h
0x18001f68a  lea     rdi, [rcx+90h]
0x18001f691  mov     rbx, rcx
0x18001f694  mov     rcx, [rcx+80h]
0x18001f69b  lea     rdx, IID_IXWizardTransaction
0x18001f6a2  mov     r8, rdi
0x18001f6a5  call    HrEnsureTearOffInterfaceLoaded
0x18001f6aa  test    eax, eax
0x18001f6ac  js      loc_18001F75C
0x18001f6b2  mov     rcx, [rdi]
0x18001f6b5  xor     edx, edx
0x18001f6b7  mov     rax, [rcx]
0x18001f6ba  mov     rax, [rax+18h]
0x18001f6be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f6c3  test    eax, eax
0x18001f6c5  js      loc_18001F75C
0x18001f6cb  mov     rcx, [rbx+80h]
0x18001f6d2  lea     rdi, [rbx+88h]
0x18001f6d9  mov     r8, rdi
0x18001f6dc  lea     rdx, IID_IXWizardPropertyBag
0x18001f6e3  call    HrEnsureTearOffInterfaceLoaded
0x18001f6e8  test    eax, eax
0x18001f6ea  js      short loc_18001F75C
0x18001f6ec  mov     rcx, [rdi]
0x18001f6ef  lea     r9, [rsp+38h+arg_0]
0x18001f6f4  mov     [rsp+38h+arg_0], 0
0x18001f6fd  lea     r8, aIccpagehandle_3; "ICCPageHandle"
0x18001f704  lea     rdx, CLSID_IncomingConnectionHookPage
0x18001f70b  mov     [rsp+38h+var_18], 0
0x18001f714  mov     rax, [rcx]
0x18001f717  mov     rax, [rax+30h]
0x18001f71b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f720  test    eax, eax
0x18001f722  js      short loc_18001F75C
0x18001f724  mov     rcx, [rsp+38h+arg_0]
0x18001f729  mov     edx, 3
0x18001f72e  call    RassrvCommitSettings
0x18001f733  test    eax, eax
0x18001f735  jnz     short loc_18001F75C
0x18001f737  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001f73d  cmp     ecx, 0FFFFFFFFh
0x18001f740  jz      short loc_18001F755
0x18001f742  xor     r9d, r9d
0x18001f745  lea     r8, aRassrvcommitse_2; "RassrvCommitSettings failed: %u:"
0x18001f74c  lea     edx, [rax+0Ch]; dwFlags
0x18001f74f  call    cs:__imp_TracePrintfExA
0x18001f755  mov     eax, 1
0x18001f75a  jmp     short loc_18001F75E
0x18001f75c  xor     eax, eax
0x18001f75e  mov     rbx, [rsp+38h+arg_8]
0x18001f763  add     rsp, 30h
0x18001f767  pop     rdi
0x18001f768  retn
```
