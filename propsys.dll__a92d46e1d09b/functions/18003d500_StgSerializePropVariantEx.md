# StgSerializePropVariantEx

- ea: `0x18003d500`
- end: `0x18003d624`
- name: `StgSerializePropVariantEx`
- size: `292`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18003b820`
- `0x18003bff0`
- `0x18003cce0`
- `0x18003d34c`

## callees

- `0x18003d500`
- `0x18003d630`
- `0x18003ef7c`
- `0x18006ed20`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18003d5d8`
- `ntdll!RtlNtStatusToDosError` at `0x18003d5d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d60c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d60c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d579`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d579`

## pseudocode

```c
__int64 __fastcall StgSerializePropVariantEx(__int64 a1, __int64 a2, _QWORD *a3, _DWORD *a4)
{
  unsigned int v7; // ebp
  LPVOID v8; // rbx
  __int64 result; // rax
  unsigned int v10; // edi

  v7 = a1;
  if ( a3 && a4 )
  {
    StgConvertVariantToPropertyNoEH(a1, a2);
    v8 = CoTaskMemAlloc(0);
    if ( v8 )
    {
      *a4 = 0;
      StgConvertVariantToPropertyNoEH(v7, a2);
      result = 0;
      *a3 = v8;
      return result;
    }
    v10 = -2147024882;
    goto LABEL_6;
  }
  v10 = -2147024809;
  if ( a3 )
LABEL_6:
    *a3 = 0;
  return v10;
}

```

## disassembly

```asm
0x18003d500  push    rbx
0x18003d502  push    rbp
0x18003d503  push    rsi
0x18003d504  push    rdi
0x18003d505  push    r12
0x18003d507  push    r14
0x18003d509  push    r15
0x18003d50b  sub     rsp, 60h
0x18003d50f  mov     rax, cs:__security_cookie
0x18003d516  xor     rax, rsp
0x18003d519  mov     [rsp+98h+var_40], rax
0x18003d51e  xor     r12d, r12d
0x18003d521  mov     rsi, r9
0x18003d524  mov     dword ptr [rsp+98h+cb], r12d
0x18003d529  mov     r15, r8
0x18003d52c  mov     dword ptr [rsp+98h+cb+4], r12d
0x18003d531  mov     r14, rdx
0x18003d534  mov     ebp, ecx
0x18003d536  mov     ebx, r12d
0x18003d539  test    r8, r8
0x18003d53c  jz      loc_18003D5F7
0x18003d542  test    r9, r9
0x18003d545  jz      loc_18003D5F7
0x18003d54b  lea     rax, [rsp+98h+cb+4]
0x18003d550  xor     r9d, r9d
0x18003d553  mov     [rsp+98h+var_58], rax
0x18003d558  lea     rax, [rsp+98h+cb]
0x18003d55d  mov     [rsp+98h+var_78], rax
0x18003d562  call    StgConvertVariantToPropertyNoEH
0x18003d567  mov     ecx, dword ptr [rsp+98h+cb+4]; int
0x18003d56b  test    ecx, ecx
0x18003d56d  js      loc_18003D614
0x18003d573  mov     edi, dword ptr [rsp+98h+cb]
0x18003d577  mov     ecx, edi; cb
0x18003d579  call    cs:__imp_CoTaskMemAlloc
0x18003d57f  mov     rbx, rax
0x18003d582  test    rax, rax
0x18003d585  jz      loc_18003D61D
0x18003d58b  lea     rax, [rsp+98h+cb+4]
0x18003d590  mov     [rsi], edi
0x18003d592  mov     [rsp+98h+var_58], rax
0x18003d597  mov     r9, rbx
0x18003d59a  lea     rax, [rsp+98h+cb]
0x18003d59f  mov     rdx, r14
0x18003d5a2  mov     ecx, ebp
0x18003d5a4  mov     [rsp+98h+var_78], rax
0x18003d5a9  call    StgConvertVariantToPropertyNoEH
0x18003d5ae  mov     ecx, dword ptr [rsp+98h+cb+4]; Status
0x18003d5b2  test    ecx, ecx
0x18003d5b4  js      short loc_18003D5D8
0x18003d5b6  mov     eax, r12d
0x18003d5b9  mov     [r15], rbx
0x18003d5bc  mov     rcx, [rsp+98h+var_40]
0x18003d5c1  xor     rcx, rsp; StackCookie
0x18003d5c4  call    __security_check_cookie
0x18003d5c9  add     rsp, 60h
0x18003d5cd  pop     r15
0x18003d5cf  pop     r14
0x18003d5d1  pop     r12
0x18003d5d3  pop     rdi
0x18003d5d4  pop     rsi
0x18003d5d5  pop     rbp
0x18003d5d6  pop     rbx
0x18003d5d7  retn
0x18003d5d8  call    cs:__imp_RtlNtStatusToDosError
0x18003d5de  mov     edi, eax
0x18003d5e0  test    eax, eax
0x18003d5e2  jg      short loc_18003D5EC
0x18003d5e4  test    edi, edi
0x18003d5e6  js      short loc_18003D5FC
0x18003d5e8  mov     eax, edi
0x18003d5ea  jmp     short loc_18003D5BC
0x18003d5ec  movzx   edi, ax
0x18003d5ef  or      edi, 80070000h
0x18003d5f5  jmp     short loc_18003D5E4
0x18003d5f7  mov     edi, 80070057h
0x18003d5fc  test    r15, r15
0x18003d5ff  jz      short loc_18003D604
0x18003d601  mov     [r15], r12
0x18003d604  test    rbx, rbx
0x18003d607  jz      short loc_18003D5E8
0x18003d609  mov     rcx, rbx; pv
0x18003d60c  call    cs:__imp_CoTaskMemFree
0x18003d612  jmp     short loc_18003D5E8
0x18003d614  call    ?MapNTStatusToHResult@@YAJJ@Z; MapNTStatusToHResult(long)
0x18003d619  mov     edi, eax
0x18003d61b  jmp     short loc_18003D5E4
0x18003d61d  mov     edi, 8007000Eh
0x18003d622  jmp     short loc_18003D601
```
