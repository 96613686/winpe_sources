# BinaryLogReader_Core_OpenFile

- ea: `0x1800290f4`
- end: `0x18002919f`
- name: `BinaryLogReader_Core_OpenFile`
- size: `171`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180025e90`
- `0x18002add0`

## callees

- `0x180007dc0`
- `0x18000abb8`
- `0x1800290f4`
- `0x180044880`

## import_xrefs

- `msvcrt!_wsopen_s` at `0x18002912f`
- `msvcrt!_wsopen_s` at `0x18002912f`

## string_xrefs

- `0x18002915d`: `MSFT DSC CU BINARY-LOG-READER`

## pseudocode

```c
__int64 __fastcall BinaryLogReader_Core_OpenFile(__int64 a1, const wchar_t *a2)
{
  unsigned int v3; // edi
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+30h] [rbp-20h] BYREF

  *(_DWORD *)&EventDescriptor.Level = 4;
  EventDescriptor.Keyword = 1;
  v3 = _wsopen_s((int *)(a1 + 4), a2, 0x8000, 64, 384);
  if ( v3 )
  {
    *(_DWORD *)&EventDescriptor.Id = 210;
    Etw_Trace1_LPCWSTR(&EventDescriptor);
    MI_ReportErrorDetails_FromFOpen(a2, v3, L"MSFT DSC CU BINARY-LOG-READER");
    return 1;
  }
  else
  {
    *(_DWORD *)&EventDescriptor.Id = 10201;
    Etw_Trace1_LPCWSTR(&EventDescriptor);
    return 0;
  }
}

```

## disassembly

```asm
0x1800290f4  mov     [rsp-8+arg_10], rbx
0x1800290f9  mov     [rsp-8+arg_18], rdi
0x1800290fe  push    rbp
0x1800290ff  mov     rbp, rsp
0x180029102  sub     rsp, 50h
0x180029106  mov     rax, cs:__security_cookie
0x18002910d  xor     rax, rsp
0x180029110  mov     [rbp+var_10], rax
0x180029114  add     rcx, 4; FileHandle
0x180029118  mov     [rsp+50h+PermissionFlag], 180h; PermissionFlag
0x180029120  mov     r9d, 40h ; '@'; ShareFlag
0x180029126  mov     r8d, 8000h; OpenFlag
0x18002912c  mov     rbx, rdx
0x18002912f  call    cs:__imp__wsopen_s
0x180029135  mov     dword ptr [rbp+EventDescriptor.Level], 4
0x18002913c  lea     rcx, [rbp+EventDescriptor]; EventDescriptor
0x180029140  mov     [rbp+EventDescriptor.Keyword], 1
0x180029148  mov     edi, eax
0x18002914a  mov     rdx, rbx
0x18002914d  test    eax, eax
0x18002914f  jz      short loc_180029175
0x180029151  mov     dword ptr [rbp+EventDescriptor.Id], 0D2h
0x180029158  call    Etw_Trace1_LPCWSTR
0x18002915d  lea     r8, aMsftDscCuBinar_0; "MSFT DSC CU BINARY-LOG-READER"
0x180029164  mov     edx, edi
0x180029166  mov     rcx, rbx
0x180029169  call    MI_ReportErrorDetails_FromFOpen
0x18002916e  mov     eax, 1
0x180029173  jmp     short loc_180029183
0x180029175  mov     dword ptr [rbp+EventDescriptor.Id], 27D9h
0x18002917c  call    Etw_Trace1_LPCWSTR
0x180029181  xor     eax, eax
0x180029183  mov     rcx, [rbp+var_10]
0x180029187  xor     rcx, rsp; StackCookie
0x18002918a  call    __security_check_cookie
0x18002918f  mov     rbx, [rsp+50h+arg_10]
0x180029194  mov     rdi, [rsp+50h+arg_18]
0x180029199  add     rsp, 50h
0x18002919d  pop     rbp
0x18002919e  retn
```
