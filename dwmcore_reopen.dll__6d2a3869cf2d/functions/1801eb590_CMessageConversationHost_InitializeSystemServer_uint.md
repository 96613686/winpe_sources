# CMessageConversationHost::InitializeSystemServer(uint *)

- ea: `0x1801eb590`
- end: `0x1801eb737`
- name: `?InitializeSystemServer@CMessageConversationHost@@AEAAJPEAI@Z`
- size: `423`
- prototype: `__int64 __fastcall(CMessageConversationHost *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801eb4d0`

## callees

- `0x180050270`
- `0x1801d8a14`
- `0x1801d8a78`
- `0x1801eb590`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801eb5bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801eb5bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801eb60e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801eb60e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801eb5d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801eb71a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801eb5d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801eb71a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1801eb604`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1801eb604`

## string_xrefs

- `0x1801eb67c`: `System\CompositionEngine`

## pseudocode

```c
__int64 __fastcall CMessageConversationHost::InitializeSystemServer(CMessageConversationHost *this, unsigned int *a2)
{
  HLOCAL v4; // rbx
  signed int LastError; // eax
  signed int v6; // ebx
  int v7; // r9d
  int v8; // eax
  __int64 v9; // rcx
  __int64 (__fastcall *v10)(__int64, const wchar_t *, __int64, __int64 *, int, int, int, CMessageConversationHost *, unsigned int *, char *); // rax
  __int64 v11; // rcx
  unsigned int v13; // [rsp+20h] [rbp-50h]
  __int64 v14; // [rsp+60h] [rbp-10h] BYREF
  int v15; // [rsp+68h] [rbp-8h]
  HLOCAL hMem; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v17; // [rsp+A8h] [rbp+38h] BYREF

  hMem = 0;
  v17 = 0;
  SetLastError(0);
  v4 = hMem;
  if ( hMem )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v14);
    LocalFree(v4);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v14);
  }
  hMem = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;;0x01;;;WD)(A;;0x01;;;AC)(A;;0x01;;;S-1-15-3-1024-1502825166-1963708345-2616377461-2562897074-4192028372-3"
          "968301570-1997628692-1435953622)",
         1u,
         &hMem,
         0) )
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD, HLOCAL, __int64 *))(**((_QWORD **)this + 2) + 64LL))(
           *((_QWORD *)this + 2),
           hMem,
           &v17);
    v6 = v8;
    if ( v8 < 0 )
    {
      v13 = 131;
    }
    else
    {
      v9 = *((_QWORD *)this + 2);
      v10 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64 *, int, int, int, CMessageConversationHost *, unsigned int *, char *))(*(_QWORD *)v9 + 304LL);
      v14 = 0;
      v15 = 1;
      v8 = v10(v9, L"System\\CompositionEngine", v17, &v14, 1, 1, 1, this, a2, (char *)this + 24);
      v6 = v8;
      if ( v8 >= 0 )
        goto LABEL_15;
      v13 = 142;
    }
    v7 = v8;
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    v13 = 127;
    if ( v6 >= 0 )
      v6 = -2003304445;
    v7 = v6;
  }
  MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v7, v13, 0);
LABEL_15:
  v11 = v17;
  if ( v17 )
  {
    v17 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  if ( hMem )
    LocalFree(hMem);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1801eb590  mov     [rsp-18h+arg_0], rbx
0x1801eb595  mov     [rsp-18h+arg_8], rsi
0x1801eb59a  push    rbp
0x1801eb59b  push    rdi
0x1801eb59c  push    r15
0x1801eb59e  mov     rbp, rsp
0x1801eb5a1  sub     rsp, 70h
0x1801eb5a5  mov     rdi, rcx
0x1801eb5a8  mov     [rbp+hMem], 0
0x1801eb5b0  xor     ecx, ecx; dwErrCode
0x1801eb5b2  mov     [rbp+arg_18], 0
0x1801eb5ba  mov     rsi, rdx
0x1801eb5bd  call    cs:__imp_SetLastError
0x1801eb5c3  mov     rbx, [rbp+hMem]
0x1801eb5c7  test    rbx, rbx
0x1801eb5ca  jz      short loc_1801EB5E7
0x1801eb5cc  lea     rcx, [rbp+var_10]; this
0x1801eb5d0  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1801eb5d5  mov     rcx, rbx; hMem
0x1801eb5d8  call    cs:__imp_LocalFree
0x1801eb5de  lea     rcx, [rbp+var_10]; this
0x1801eb5e2  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1801eb5e7  xor     r9d, r9d; SecurityDescriptorSize
0x1801eb5ea  mov     [rbp+hMem], 0
0x1801eb5f2  lea     r8, [rbp+hMem]; SecurityDescriptor
0x1801eb5f6  lea     rcx, StringSecurityDescriptor; "D:(A;;0x01;;;WD)(A;;0x01;;;AC)(A;;0x01;"...
0x1801eb5fd  lea     r15d, [r9+1]
0x1801eb601  mov     edx, r15d; StringSDRevision
0x1801eb604  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1801eb60a  test    eax, eax
0x1801eb60c  jnz     short loc_1801EB646
0x1801eb60e  call    cs:__imp_GetLastError
0x1801eb614  mov     ebx, eax
0x1801eb616  test    eax, eax
0x1801eb618  jle     short loc_1801EB623
0x1801eb61a  movzx   ebx, ax
0x1801eb61d  or      ebx, 80070000h
0x1801eb623  test    ebx, ebx
0x1801eb625  mov     [rsp+70h+var_48], 0
0x1801eb62e  mov     eax, 88980003h
0x1801eb633  mov     [rsp+70h+var_50], 7Fh
0x1801eb63b  cmovns  ebx, eax
0x1801eb63e  mov     r9d, ebx
0x1801eb641  jmp     loc_1801EB6E7
0x1801eb646  mov     rcx, [rdi+10h]
0x1801eb64a  lea     r8, [rbp+arg_18]
0x1801eb64e  mov     rdx, [rbp+hMem]
0x1801eb652  mov     rax, [rcx]
0x1801eb655  mov     rax, [rax+40h]
0x1801eb659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eb65e  mov     ebx, eax
0x1801eb660  test    eax, eax
0x1801eb662  js      short loc_1801EB6D3
0x1801eb664  mov     eax, [rbp+var_4]
0x1801eb667  lea     rdx, [rdi+18h]
0x1801eb66b  mov     rcx, [rdi+10h]
0x1801eb66f  lea     r9, [rbp+var_10]
0x1801eb673  mov     r8, [rbp+arg_18]
0x1801eb677  mov     [rsp+70h+var_28], rdx
0x1801eb67c  lea     rdx, aSystemComposit_0; "System\\CompositionEngine"
0x1801eb683  mov     [rsp+70h+var_30], rsi
0x1801eb688  mov     [rbp+var_4], eax
0x1801eb68b  mov     rax, [rcx]
0x1801eb68e  mov     [rsp+70h+var_38], rdi
0x1801eb693  mov     [rsp+70h+var_40], r15d
0x1801eb698  mov     dword ptr [rsp+70h+var_48], r15d
0x1801eb69d  mov     rax, [rax+130h]
0x1801eb6a4  mov     [rbp+var_10], 0
0x1801eb6ac  mov     [rbp+var_8], r15d
0x1801eb6b0  mov     [rsp+70h+var_50], r15d
0x1801eb6b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eb6ba  mov     ebx, eax
0x1801eb6bc  test    eax, eax
0x1801eb6be  jns     short loc_1801EB6F4
0x1801eb6c0  mov     [rsp+70h+var_48], 0
0x1801eb6c9  mov     [rsp+70h+var_50], 8Eh
0x1801eb6d1  jmp     short loc_1801EB6E4
0x1801eb6d3  mov     [rsp+70h+var_48], 0; void *
0x1801eb6dc  mov     [rsp+70h+var_50], 83h; unsigned int
0x1801eb6e4  mov     r9d, eax; int
0x1801eb6e7  xor     edx, edx; int *
0x1801eb6e9  xor     r8d, r8d; unsigned int
0x1801eb6ec  lea     ecx, [rdx+14h]; unsigned int
0x1801eb6ef  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1801eb6f4  mov     rcx, [rbp+arg_18]
0x1801eb6f8  test    rcx, rcx
0x1801eb6fb  jz      short loc_1801EB711
0x1801eb6fd  mov     [rbp+arg_18], 0
0x1801eb705  mov     rax, [rcx]
0x1801eb708  mov     rax, [rax+10h]
0x1801eb70c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801eb711  mov     rcx, [rbp+hMem]; hMem
0x1801eb715  test    rcx, rcx
0x1801eb718  jz      short loc_1801EB720
0x1801eb71a  call    cs:__imp_LocalFree
0x1801eb720  lea     r11, [rsp+70h+var_s0]
0x1801eb725  mov     eax, ebx
0x1801eb727  mov     rbx, [r11+20h]
0x1801eb72b  mov     rsi, [r11+28h]
0x1801eb72f  mov     rsp, r11
0x1801eb732  pop     r15
0x1801eb734  pop     rdi
0x1801eb735  pop     rbp
0x1801eb736  retn
```
