# CreatePropertySheetPageW

- ea: `0x180017eb8`
- end: `0x180017f4d`
- name: `CreatePropertySheetPageW`
- size: `149`
- prototype: `HPROPSHEETPAGE __stdcall(LPCPROPSHEETPAGEW constPropSheetPagePointer)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000c018`
- `0x180016530`

## callees

- `0x180017c70`
- `0x180017eb8`
- `0x1800183e4`
- `0x180019010`

## import_xrefs

- `KERNEL32!DeactivateActCtx` at `0x180017f39`
- `KERNEL32!DeactivateActCtx` at `0x180017f39`

## string_xrefs

- `0x180017ee7`: `CreatePropertySheetPageW`

## pseudocode

```c
HPROPSHEETPAGE __stdcall CreatePropertySheetPageW(LPCPROPSHEETPAGEW constPropSheetPagePointer)
{
  struct _PSP *v2; // rdi
  __int64 (__fastcall *v3)(LPCPROPSHEETPAGEW); // rax
  ULONG_PTR ulCookie; // [rsp+38h] [rbp+10h] BYREF

  ulCookie = 0;
  v2 = 0;
  SHActivateContext(&ulCookie);
  v3 = (__int64 (__fastcall *)(LPCPROPSHEETPAGEW))qword_1800213E8;
  if ( qword_1800213E8 == -1 )
  {
    GetProcFromComCtl32((FARPROC *)&qword_1800213E8, "CreatePropertySheetPageW");
    v3 = (__int64 (__fastcall *)(LPCPROPSHEETPAGEW))qword_1800213E8;
  }
  if ( v3 )
  {
    if ( constPropSheetPagePointer->dwSize > 0x58 )
    {
      constPropSheetPagePointer->dwFlags |= 0x4000u;
      constPropSheetPagePointer->hActCtx = (HANDLE)g_hActCtx;
      v3 = (__int64 (__fastcall *)(LPCPROPSHEETPAGEW))qword_1800213E8;
    }
    v2 = (struct _PSP *)v3(constPropSheetPagePointer);
  }
  if ( ulCookie )
    DeactivateActCtx(0, ulCookie);
  return v2;
}

```

## disassembly

```asm
0x180017eb8  mov     [rsp+arg_0], rbx
0x180017ebd  push    rdi
0x180017ebe  sub     rsp, 20h
0x180017ec2  mov     rbx, rcx
0x180017ec5  mov     [rsp+28h+ulCookie], 0
0x180017ece  lea     rcx, [rsp+28h+ulCookie]
0x180017ed3  xor     edi, edi
0x180017ed5  call    SHActivateContext
0x180017eda  mov     rax, cs:qword_1800213E8
0x180017ee1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180017ee5  jnz     short loc_180017F01
0x180017ee7  lea     rdx, aCreateproperty; "CreatePropertySheetPageW"
0x180017eee  lea     rcx, qword_1800213E8
0x180017ef5  call    _GetProcFromComCtl32
0x180017efa  mov     rax, cs:qword_1800213E8
0x180017f01  test    rax, rax
0x180017f04  jz      short loc_180017F2D
0x180017f06  cmp     dword ptr [rbx], 58h ; 'X'
0x180017f09  jbe     short loc_180017F22
0x180017f0b  bts     dword ptr [rbx+4], 0Eh
0x180017f10  mov     rax, cs:g_hActCtx
0x180017f17  mov     [rbx+58h], rax
0x180017f1b  mov     rax, cs:qword_1800213E8
0x180017f22  mov     rcx, rbx
0x180017f25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f2a  mov     rdi, rax
0x180017f2d  mov     rdx, [rsp+28h+ulCookie]; ulCookie
0x180017f32  test    rdx, rdx
0x180017f35  jz      short loc_180017F3F
0x180017f37  xor     ecx, ecx; dwFlags
0x180017f39  call    cs:__imp_DeactivateActCtx
0x180017f3f  mov     rbx, [rsp+28h+arg_0]
0x180017f44  mov     rax, rdi
0x180017f47  add     rsp, 20h
0x180017f4b  pop     rdi
0x180017f4c  retn
```
