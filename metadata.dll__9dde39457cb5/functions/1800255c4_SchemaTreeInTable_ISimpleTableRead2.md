# SchemaTreeInTable(ISimpleTableRead2 *)

- ea: `0x1800255c4`
- end: `0x1800256b1`
- name: `?SchemaTreeInTable@@YAHPEAUISimpleTableRead2@@@Z`
- size: `237`
- prototype: `__int64 __fastcall(struct ISimpleTableRead2 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180021c40`

## callees

- `0x1800255c4`
- `0x1800309d0`
- `0x180031010`

## import_xrefs

- `IisRTL!PuDbgPrintW` at `0x18002565c`
- `IisRTL!PuDbgPrintW` at `0x18002565c`

## string_xrefs

- `0x1800255df`: `AdminACL`

## pseudocode

```c
_BOOL8 __fastcall SchemaTreeInTable(struct ISimpleTableRead2 *a1)
{
  int v2; // eax
  int v3; // ebx
  __int64 v4; // rax
  int v6; // [rsp+28h] [rbp-40h]
  int v7; // [rsp+30h] [rbp-38h] BYREF
  int v8; // [rsp+34h] [rbp-34h] BYREF
  _QWORD v9[3]; // [rsp+38h] [rbp-30h] BYREF

  v7 = 66;
  v9[0] = L"AdminACL";
  v8 = 0;
  v9[1] = L"/Schema";
  v9[2] = &v7;
  v2 = (*(__int64 (__fastcall **)(struct ISimpleTableRead2 *, _QWORD, _QWORD *, int *))(*(_QWORD *)a1 + 24LL))(
         a1,
         0,
         v9,
         &v8);
  v3 = v2;
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    v6 = v2;
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
      12729,
      "SchemaTreeInTable",
      L"[SchemaTreeInTable] GetRowIndexByIdentity returned hr=0x%x\n",
      v6);
  }
  if ( v3 >= 0 )
    return 1;
  v4 = *(_QWORD *)a1;
  v7 = 0;
  return (*(int (__fastcall **)(struct ISimpleTableRead2 *, _QWORD, _QWORD *, int *))(v4 + 24))(a1, 0, v9, &v8) >= 0;
}

```

## disassembly

```asm
0x1800255c4  mov     r11, rsp
0x1800255c7  mov     [r11+10h], rbx
0x1800255cb  push    rdi
0x1800255cc  sub     rsp, 60h
0x1800255d0  mov     rax, cs:__security_cookie
0x1800255d7  xor     rax, rsp
0x1800255da  mov     [rsp+68h+var_18], rax
0x1800255df  lea     rax, aAdminacl; "AdminACL"
0x1800255e6  mov     [rsp+68h+var_38], 42h ; 'B'
0x1800255ee  mov     [r11-30h], rax
0x1800255f2  lea     r9, [r11-34h]
0x1800255f6  lea     rax, aSchema_3; "/Schema"
0x1800255fd  mov     [rsp+68h+var_34], 0
0x180025605  mov     [r11-28h], rax
0x180025609  lea     r8, [r11-30h]
0x18002560d  lea     rax, [r11-38h]
0x180025611  xor     edx, edx
0x180025613  mov     [r11-20h], rax
0x180025617  mov     rdi, rcx
0x18002561a  mov     rax, [rcx]
0x18002561d  mov     rax, [rax+18h]
0x180025621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025626  test    byte ptr cs:g_dwDebugFlags, 3
0x18002562d  mov     ebx, eax
0x18002562f  jz      short loc_180025662
0x180025631  mov     rcx, cs:g_pDebug
0x180025638  lea     r9, aSchematreeinta; "SchemaTreeInTable"
0x18002563f  mov     [rsp+68h+var_40], eax
0x180025643  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18002564a  lea     rax, aSchematreeinta_0; "[SchemaTreeInTable] GetRowIndexByIdenti"...
0x180025651  mov     r8d, 31B9h
0x180025657  mov     [rsp+68h+var_48], rax
0x18002565c  call    cs:__imp_PuDbgPrintW
0x180025662  test    ebx, ebx
0x180025664  jns     short loc_180025694
0x180025666  mov     rax, [rdi]
0x180025669  lea     r9, [rsp+68h+var_34]
0x18002566e  lea     r8, [rsp+68h+var_30]
0x180025673  mov     [rsp+68h+var_38], 0
0x18002567b  xor     edx, edx
0x18002567d  mov     rcx, rdi
0x180025680  mov     rax, [rax+18h]
0x180025684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025689  xor     ecx, ecx
0x18002568b  test    eax, eax
0x18002568d  setns   cl
0x180025690  mov     eax, ecx
0x180025692  jmp     short loc_180025699
0x180025694  mov     eax, 1
0x180025699  mov     rcx, [rsp+68h+var_18]
0x18002569e  xor     rcx, rsp; StackCookie
0x1800256a1  call    __security_check_cookie
0x1800256a6  mov     rbx, [rsp+68h+arg_8]
0x1800256ab  add     rsp, 60h
0x1800256af  pop     rdi
0x1800256b0  retn
```
