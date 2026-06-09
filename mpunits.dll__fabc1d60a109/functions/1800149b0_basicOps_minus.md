# basicOps_minus

- ea: `0x1800149b0`
- end: `0x180014b47`
- name: `basicOps_minus`
- size: `407`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180015080`

## callees

- `0x180006ef8`
- `0x180007c80`
- `0x1800149b0`
- `0x180016c6c`
- `0x180016d50`
- `0x180016f78`
- `0x180017418`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180014a56`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180014a93`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180014ac0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180014a56`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180014a93`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180014ac0`

## string_xrefs

- `0x180014a4b`: `mpunits.dll`
- `0x180014a88`: `mpunits.dll`
- `0x180014ab5`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall basicOps_minus(__int64 a1, __int64 a2)
{
  _OWORD *v3; // rax
  HMODULE ModuleHandleA; // rax
  __int64 v5; // rdx
  HMODULE v6; // rax
  __int64 String_LoadString; // rax
  int v8; // ecx
  __int128 v10; // [rsp+30h] [rbp-10h] BYREF

  if ( *(_BYTE *)a2 == 0xFF || (*(_DWORD *)a2 & 0x100) != 0 )
    goto LABEL_21;
  if ( (unsigned __int8)(*(_BYTE *)a2 - 1) <= 0xAu )
  {
    v3 = (_OWORD *)subtract_numeric(&v10);
LABEL_22:
    *(_OWORD *)a1 = *v3;
    return a1;
  }
  if ( !*(_BYTE *)a2 || *(_BYTE *)a2 == 13 )
  {
LABEL_21:
    v3 = (_OWORD *)subtract_convertLhsToNumber(&v10);
    goto LABEL_22;
  }
  if ( *(_BYTE *)a2 == 12 )
  {
    if ( *(_DWORD *)(*(_QWORD *)(a2 + 8) + 16LL) )
    {
      v3 = (_OWORD *)subtract_timestamp(&v10);
      goto LABEL_22;
    }
    if ( *(_BYTE *)a2 == 12 )
    {
      if ( !*(_DWORD *)(*(_QWORD *)(a2 + 8) + 16LL) )
      {
        v3 = (_OWORD *)subtract_interval(&v10);
        goto LABEL_22;
      }
      goto LABEL_18;
    }
  }
  if ( (*(_BYTE *)a2 & 0xF0) == 0x10 )
  {
    v10 = 0;
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    v5 = 2056;
LABEL_19:
    String_LoadString = Intlstr_GetString_LoadString(ModuleHandleA, v5);
    v8 = 4;
    goto LABEL_20;
  }
  if ( *(_BYTE *)a2 != 15
    || !((__int64 (__fastcall *)(_QWORD))Observable_FromInstance)(*(_QWORD *)(*(_QWORD *)(a2 + 8) + 24LL)) )
  {
LABEL_18:
    v10 = 0;
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    v5 = 2057;
    goto LABEL_19;
  }
  v10 = 0;
  v6 = GetModuleHandleA("mpunits.dll");
  String_LoadString = Intlstr_GetString_LoadString(v6, 2066);
  v8 = 7;
LABEL_20:
  *(_QWORD *)&v10 = String_LoadString;
  BYTE8(v10) = 0;
  MI_ReportErrorDetails_ForCustomError(v8, (int)L"MI", 0, 0);
  *(_DWORD *)(a1 + 4) = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_DWORD *)a1 = 254;
  return a1;
}

```

## disassembly

```asm
0x1800149b0  mov     [rsp-8+arg_0], rbx
0x1800149b5  mov     [rsp-8+arg_8], rdi
0x1800149ba  push    rbp
0x1800149bb  mov     rbp, rsp
0x1800149be  sub     rsp, 40h
0x1800149c2  cmp     byte ptr [rdx], 0FFh
0x1800149c5  mov     rbx, rcx
0x1800149c8  jz      loc_180014B24
0x1800149ce  test    dword ptr [rdx], 100h
0x1800149d4  jnz     loc_180014B24
0x1800149da  mov     al, [rdx]
0x1800149dc  dec     al
0x1800149de  cmp     al, 0Ah
0x1800149e0  ja      short loc_1800149F0
0x1800149e2  lea     rcx, [rbp+var_10]
0x1800149e6  call    subtract_numeric
0x1800149eb  jmp     loc_180014B2D
0x1800149f0  xor     edi, edi
0x1800149f2  cmp     [rdx], dil
0x1800149f5  jz      loc_180014B24
0x1800149fb  cmp     byte ptr [rdx], 0Dh
0x1800149fe  jz      loc_180014B24
0x180014a04  cmp     byte ptr [rdx], 0Ch
0x180014a07  jnz     short loc_180014A40
0x180014a09  mov     rax, [rdx+8]
0x180014a0d  cmp     [rax+10h], edi
0x180014a10  jz      short loc_180014A20
0x180014a12  lea     rcx, [rbp+var_10]
0x180014a16  call    subtract_timestamp
0x180014a1b  jmp     loc_180014B2D
0x180014a20  cmp     byte ptr [rdx], 0Ch
0x180014a23  jnz     short loc_180014A40
0x180014a25  mov     rax, [rdx+8]
0x180014a29  cmp     [rax+10h], edi
0x180014a2c  jnz     loc_180014AB2
0x180014a32  lea     rcx, [rbp+var_10]
0x180014a36  call    subtract_interval
0x180014a3b  jmp     loc_180014B2D
0x180014a40  mov     al, [rdx]
0x180014a42  and     al, 0F0h
0x180014a44  cmp     al, 10h
0x180014a46  jnz     short loc_180014A63
0x180014a48  xorps   xmm0, xmm0
0x180014a4b  lea     rcx, ModuleName; "mpunits.dll"
0x180014a52  movups  [rbp+var_10], xmm0
0x180014a56  call    cs:__imp_GetModuleHandleA
0x180014a5c  mov     edx, 808h
0x180014a61  jmp     short loc_180014ACB
0x180014a63  cmp     byte ptr [rdx], 0Fh
0x180014a66  jnz     short loc_180014AB2
0x180014a68  mov     rcx, [rdx+8]
0x180014a6c  mov     rax, cs:off_180047B90
0x180014a73  mov     rcx, [rcx+18h]
0x180014a77  mov     rax, [rax+8]
0x180014a7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a80  test    rax, rax
0x180014a83  jz      short loc_180014AB2
0x180014a85  xorps   xmm0, xmm0
0x180014a88  lea     rcx, ModuleName; "mpunits.dll"
0x180014a8f  movups  [rbp+var_10], xmm0
0x180014a93  call    cs:__imp_GetModuleHandleA
0x180014a99  mov     rcx, rax
0x180014a9c  mov     edx, 812h
0x180014aa1  call    _Intlstr_GetString_LoadString
0x180014aa6  mov     r8d, 0Bh
0x180014aac  lea     ecx, [r8-4]
0x180014ab0  jmp     short loc_180014ADD
0x180014ab2  xorps   xmm0, xmm0
0x180014ab5  lea     rcx, ModuleName; "mpunits.dll"
0x180014abc  movups  [rbp+var_10], xmm0
0x180014ac0  call    cs:__imp_GetModuleHandleA
0x180014ac6  mov     edx, 809h
0x180014acb  mov     rcx, rax
0x180014ace  call    _Intlstr_GetString_LoadString
0x180014ad3  mov     r8d, 5
0x180014ad9  lea     ecx, [r8-1]; int
0x180014add  mov     qword ptr [rbp+var_10], rax
0x180014ae1  lea     r9, [rbp+var_10]
0x180014ae5  mov     byte ptr [rbp+var_10+8], dil
0x180014ae9  lea     rdx, aMi; "MI"
0x180014af0  movaps  xmm0, [rbp+var_10]
0x180014af4  mov     [rsp+40h+var_18], rdi; __int64
0x180014af9  movdqa  [rbp+var_10], xmm0
0x180014afe  mov     [rsp+40h+var_20], rdi; __int64
0x180014b03  call    MI_ReportErrorDetails_ForCustomError
0x180014b08  xor     edx, edx
0x180014b0a  xor     ecx, ecx
0x180014b0c  mov     eax, 0FFh
0x180014b11  mov     [rbx+4], edx
0x180014b14  and     eax, 0FFFFFFFEh
0x180014b17  mov     [rbx+8], rcx
0x180014b1b  or      eax, 0FEh
0x180014b20  mov     [rbx], eax
0x180014b22  jmp     short loc_180014B34
0x180014b24  lea     rcx, [rbp+var_10]
0x180014b28  call    subtract_convertLhsToNumber
0x180014b2d  movups  xmm0, xmmword ptr [rax]
0x180014b30  movdqu  xmmword ptr [rbx], xmm0
0x180014b34  mov     rdi, [rsp+40h+arg_8]
0x180014b39  mov     rax, rbx
0x180014b3c  mov     rbx, [rsp+40h+arg_0]
0x180014b41  add     rsp, 40h
0x180014b45  pop     rbp
0x180014b46  retn
```
