# DelegateFromPropertyArgument

- ea: `0x180001b44`
- end: `0x180001cb9`
- name: `DelegateFromPropertyArgument`
- size: `373`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002780`
- `0x180003160`
- `0x1800032d0`
- `0x180003440`
- `0x1800037d0`

## callees

- `0x180001b44`
- `0x180006e64`
- `0x1800076d0`
- `0x180007c80`
- `0x180033e34`
- `0x180044880`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180001c36`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180001c36`

## string_xrefs

- `0x180001c2b`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall DelegateFromPropertyArgument(__int64 a1, _QWORD *a2)
{
  void (__fastcall ***v4)(_QWORD, _QWORD *); // rax
  void (__fastcall **v5)(_QWORD, _QWORD *); // r8
  unsigned int v6; // ebx
  char *v7; // rcx
  HMODULE ModuleHandleA; // rax
  _QWORD v10[2]; // [rsp+30h] [rbp-9h] BYREF
  __int128 v11; // [rsp+40h] [rbp+7h] BYREF
  void (__fastcall ***v12)(_QWORD, _QWORD *); // [rsp+50h] [rbp+17h] BYREF
  _OWORD v13[3]; // [rsp+58h] [rbp+1Fh] BYREF

  v4 = (void (__fastcall ***)(_QWORD, _QWORD *))Delegate_FromInstance();
  v12 = v4;
  if ( !v4 )
  {
    LODWORD(v10[0]) = 0;
    memset(v13, 0, sizeof(v13));
    Unbox(a1, v10, v13);
    if ( !LODWORD(v10[0]) )
    {
      v6 = 4;
      goto LABEL_13;
    }
    if ( (DWORD1(v13[0]) & 0x20000000) == 0 )
    {
      if ( LODWORD(v13[0]) == 13 )
      {
        v7 = (char *)&v11;
        v10[0] = *((_QWORD *)&v13[0] + 1);
        *(_QWORD *)&v11 = v10;
        *((_QWORD *)&v11 + 1) = 1;
LABEL_11:
        v6 = MemberSelectorFromStringArray(v7, &v12);
        goto LABEL_13;
      }
      if ( LODWORD(v13[0]) == 29 )
      {
        v7 = (char *)v13 + 8;
        goto LABEL_11;
      }
    }
    v11 = 0;
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    *(_QWORD *)&v11 = Intlstr_FormatString_FormatMessage(ModuleHandleA, 2098, L"Property");
    BYTE8(v11) = 1;
    v6 = 4;
    MI_ReportErrorDetails_ForCustomError(4, (int)L"MI", 0, 0);
    goto LABEL_13;
  }
  v5 = *v4;
  v6 = 0;
  v10[0] = 0;
  if ( v5 )
    (*v5)(v4, v10);
LABEL_13:
  *a2 = v12;
  return v6;
}

```

## disassembly

```asm
0x180001b44  mov     [rsp-8+arg_10], rbx
0x180001b49  mov     [rsp-8+arg_18], rdi
0x180001b4e  push    rbp
0x180001b4f  lea     rbp, [rsp-57h]
0x180001b54  sub     rsp, 90h
0x180001b5b  mov     rax, cs:__security_cookie
0x180001b62  xor     rax, rsp
0x180001b65  mov     [rbp+57h+var_8], rax
0x180001b69  mov     rax, cs:off_180047B98
0x180001b70  mov     rdi, rdx
0x180001b73  mov     rbx, rcx
0x180001b76  mov     rax, [rax+8]
0x180001b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b7f  mov     [rbp+57h+var_40], rax
0x180001b83  test    rax, rax
0x180001b86  jz      short loc_180001BAE
0x180001b88  mov     r8, [rax]
0x180001b8b  xor     ebx, ebx
0x180001b8d  mov     [rbp+57h+var_60], rbx
0x180001b91  test    r8, r8
0x180001b94  jz      loc_180001C8F
0x180001b9a  mov     rcx, rax
0x180001b9d  lea     rdx, [rbp+57h+var_60]
0x180001ba1  mov     rax, [r8]
0x180001ba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ba9  jmp     loc_180001C8F
0x180001bae  xorps   xmm0, xmm0
0x180001bb1  mov     dword ptr [rbp+57h+var_60], 0
0x180001bb8  lea     r8, [rbp+57h+var_38]
0x180001bbc  mov     rcx, rbx
0x180001bbf  lea     rdx, [rbp+57h+var_60]
0x180001bc3  movups  [rbp+57h+var_38], xmm0
0x180001bc7  movups  [rbp+57h+var_28], xmm0
0x180001bcb  movups  [rbp+57h+var_18], xmm0
0x180001bcf  call    Unbox
0x180001bd4  cmp     dword ptr [rbp+57h+var_60], 0
0x180001bd8  jnz     short loc_180001BE4
0x180001bda  mov     ebx, 4
0x180001bdf  jmp     loc_180001C8F
0x180001be4  test    dword ptr [rbp+57h+var_38+4], 20000000h
0x180001beb  jnz     short loc_180001C28
0x180001bed  cmp     dword ptr [rbp+57h+var_38], 0Dh
0x180001bf1  jnz     short loc_180001C11
0x180001bf3  mov     rax, qword ptr [rbp+57h+var_38+8]
0x180001bf7  lea     rcx, [rbp+57h+var_50]
0x180001bfb  mov     [rbp+57h+var_60], rax
0x180001bff  lea     rax, [rbp+57h+var_60]
0x180001c03  mov     qword ptr [rbp+57h+var_50], rax
0x180001c07  mov     qword ptr [rbp+57h+var_50+8], 1
0x180001c0f  jmp     short loc_180001C1B
0x180001c11  cmp     dword ptr [rbp+57h+var_38], 1Dh
0x180001c15  jnz     short loc_180001C28
0x180001c17  lea     rcx, [rbp+57h+var_38+8]
0x180001c1b  lea     rdx, [rbp+57h+var_40]
0x180001c1f  call    MemberSelectorFromStringArray
0x180001c24  mov     ebx, eax
0x180001c26  jmp     short loc_180001C8F
0x180001c28  xorps   xmm0, xmm0
0x180001c2b  lea     rcx, ModuleName; "mpunits.dll"
0x180001c32  movups  [rbp+57h+var_50], xmm0
0x180001c36  call    cs:__imp_GetModuleHandleA
0x180001c3c  lea     r8, aProperty; "Property"
0x180001c43  mov     edx, 832h
0x180001c48  mov     rcx, rax
0x180001c4b  call    _Intlstr_FormatString_FormatMessage
0x180001c50  mov     qword ptr [rbp+57h+var_50], rax
0x180001c54  lea     r9, [rbp+57h+var_50]
0x180001c58  mov     byte ptr [rbp+57h+var_50+8], 1
0x180001c5c  lea     rdx, aMi; "MI"
0x180001c63  movaps  xmm0, [rbp+57h+var_50]
0x180001c67  mov     r8d, 5
0x180001c6d  mov     [rsp+90h+var_68], 0; __int64
0x180001c76  movdqa  [rbp+57h+var_50], xmm0
0x180001c7b  mov     [rsp+90h+var_70], 0; __int64
0x180001c84  lea     ebx, [r8-1]
0x180001c88  mov     ecx, ebx; int
0x180001c8a  call    MI_ReportErrorDetails_ForCustomError
0x180001c8f  mov     rax, [rbp+57h+var_40]
0x180001c93  mov     [rdi], rax
0x180001c96  mov     eax, ebx
0x180001c98  mov     rcx, [rbp+57h+var_8]
0x180001c9c  xor     rcx, rsp; StackCookie
0x180001c9f  call    __security_check_cookie
0x180001ca4  lea     r11, [rsp+90h+var_s0]
0x180001cac  mov     rbx, [r11+20h]
0x180001cb0  mov     rdi, [r11+28h]
0x180001cb4  mov     rsp, r11
0x180001cb7  pop     rbp
0x180001cb8  retn
```
