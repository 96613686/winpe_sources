# CWizardExtension::CryptUIWizBuildCTL(ulong,HWND__ *,ushort const *,_CRYPTUI_WIZ_BUILDCTL_SRC_INFO const *,_CRYPTUI_WIZ_BUILDCTL_DEST_INFO const *,_CTL_CONTEXT const * *)

- ea: `0x180037bf8`
- end: `0x180037c9d`
- name: `?CryptUIWizBuildCTL@CWizardExtension@@QEAAHKPEAUHWND__@@PEBGPEBU_CRYPTUI_WIZ_BUILDCTL_SRC_INFO@@PEBU_CRYPTUI_WIZ_BUILDCTL_DEST_INFO@@PEAPEBU_CTL_CONTEXT@@@Z`
- size: `165`
- prototype: `__int64 __fastcall(CWizardExtension *__hidden this, unsigned int, HWND, const unsigned __int16 *, const struct _CRYPTUI_WIZ_BUILDCTL_SRC_INFO *, const struct _CRYPTUI_WIZ_BUILDCTL_DEST_INFO *, const struct _CTL_CONTEXT **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180037e10`

## callees

- `0x18000a248`
- `0x180037bf8`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037c57`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037c57`

## pseudocode

```c
__int64 __fastcall CWizardExtension::CryptUIWizBuildCTL(
        CWizardExtension *this,
        unsigned int a2,
        HWND a3,
        const unsigned __int16 *a4,
        const struct _CRYPTUI_WIZ_BUILDCTL_SRC_INFO *a5,
        const struct _CRYPTUI_WIZ_BUILDCTL_DEST_INFO *a6,
        const struct _CTL_CONTEXT **a7)
{
  int FunctionPointer; // eax
  __int64 v11; // r11
  DWORD v12; // ecx
  __int64 (*v14)(void); // [rsp+40h] [rbp-18h] BYREF

  v14 = 0;
  if ( a7 )
    *a7 = 0;
  FunctionPointer = CCryptUiExtension::GetFunctionPointer(this, 1, &v14);
  if ( FunctionPointer >= 0 )
    return ((__int64 (__fastcall *)(_QWORD, HWND, const unsigned __int16 *, const struct _CRYPTUI_WIZ_BUILDCTL_SRC_INFO *, const struct _CRYPTUI_WIZ_BUILDCTL_DEST_INFO *, __int64))v14)(
             a2,
             a3,
             a4,
             a5,
             a6,
             v11);
  v12 = (unsigned __int16)FunctionPointer;
  if ( (FunctionPointer & 0xFFFF0000) != 0x80070000 )
    v12 = 1;
  SetLastError(v12);
  return 0;
}

```

## disassembly

```asm
0x180037bf8  mov     [rsp+arg_0], rbx
0x180037bfd  mov     [rsp+arg_8], rsi
0x180037c02  push    rdi
0x180037c03  sub     rsp, 50h
0x180037c07  mov     r11, [rsp+58h+arg_30]
0x180037c0f  mov     rbx, r9
0x180037c12  mov     [rsp+58h+var_18], 0
0x180037c1b  mov     rdi, r8
0x180037c1e  mov     esi, edx
0x180037c20  test    r11, r11
0x180037c23  jz      short loc_180037C2C
0x180037c25  mov     qword ptr [r11], 0
0x180037c2c  lea     r8, [rsp+58h+var_18]; __int64 (**)(void)
0x180037c31  mov     edx, 1; unsigned int
0x180037c36  call    ?GetFunctionPointer@CCryptUiExtension@@IEAAJKPEAP6A_JXZ@Z; CCryptUiExtension::GetFunctionPointer(ulong,__int64 (**)(void))
0x180037c3b  test    eax, eax
0x180037c3d  jns     short loc_180037C61
0x180037c3f  mov     ecx, eax
0x180037c41  and     ecx, 0FFFF0000h
0x180037c47  cmp     ecx, 80070000h
0x180037c4d  movzx   ecx, ax
0x180037c50  jz      short loc_180037C57
0x180037c52  mov     ecx, 1; dwErrCode
0x180037c57  call    cs:__imp_SetLastError
0x180037c5d  xor     eax, eax
0x180037c5f  jmp     short loc_180037C8D
0x180037c61  mov     rcx, [rsp+58h+arg_28]
0x180037c69  mov     r8, rbx
0x180037c6c  mov     r9, [rsp+58h+arg_20]
0x180037c74  mov     rdx, rdi
0x180037c77  mov     rax, [rsp+58h+var_18]
0x180037c7c  mov     [rsp+58h+var_30], r11
0x180037c81  mov     [rsp+58h+var_38], rcx
0x180037c86  mov     ecx, esi
0x180037c88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037c8d  mov     rbx, [rsp+58h+arg_0]
0x180037c92  mov     rsi, [rsp+58h+arg_8]
0x180037c97  add     rsp, 50h
0x180037c9b  pop     rdi
0x180037c9c  retn
```
