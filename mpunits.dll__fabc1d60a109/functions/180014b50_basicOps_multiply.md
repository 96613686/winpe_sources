# basicOps_multiply

- ea: `0x180014b50`
- end: `0x180014dcc`
- name: `basicOps_multiply`
- size: `636`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x180006ef8`
- `0x180007c80`
- `0x18000e650`
- `0x180014b50`
- `0x180015bcc`
- `0x180015e14`
- `0x18001602c`
- `0x180016518`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180014c99`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180014d25`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180014d52`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180014c99`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180014d25`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180014d52`

## string_xrefs

- `0x180014c8e`: `mpunits.dll`
- `0x180014d1a`: `mpunits.dll`
- `0x180014d47`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall basicOps_multiply(__int64 a1, int *a2, __int64 a3)
{
  int v5; // r14d
  int v6; // ebx
  __int64 v7; // r15
  int v8; // r8d
  __int64 v9; // rax
  int v10; // eax
  int *v11; // r9
  __int64 v12; // rax
  __int64 v13; // rax
  int v14; // eax
  HMODULE ModuleHandleA; // rax
  __int64 v16; // rdx
  HMODULE v17; // rax
  __int64 String_LoadString; // rax
  int v19; // ecx
  __int64 result; // rax
  _DWORD v21[2]; // [rsp+30h] [rbp-30h] BYREF
  int *v22; // [rsp+38h] [rbp-28h]
  __int128 v23; // [rsp+40h] [rbp-20h] BYREF
  _BYTE v24[16]; // [rsp+50h] [rbp-10h] BYREF

  if ( *(_BYTE *)a2 != 0xFF )
  {
    v8 = *a2;
    if ( (*a2 & 0x100) != 0 )
    {
      v7 = 0;
      v6 = (unsigned __int8)v8 | 0x100;
      v5 = 0;
      goto LABEL_29;
    }
    if ( (unsigned __int8)(*(_BYTE *)a2 - 1) <= 0xAu )
    {
      v9 = multiply_numeric(&v23, a2, a3);
LABEL_28:
      v7 = *(_QWORD *)(v9 + 8);
      v5 = *(_DWORD *)(v9 + 4);
      v6 = *(_DWORD *)v9;
      goto LABEL_29;
    }
    if ( !*(_BYTE *)a2 )
    {
      v10 = a2[1];
      v11 = (int *)*((_QWORD *)a2 + 1);
      if ( (unsigned __int8)(v8 - 1) > 0xAu )
      {
        LODWORD(v23) = *a2;
        DWORD1(v23) = v10;
        *((_QWORD *)&v23 + 1) = v11;
        v12 = MintValue_CoerceToNumberImpl(v24, &v23);
        v11 = *(int **)(v12 + 8);
        v8 = *(_DWORD *)v12;
        v10 = *(_DWORD *)(v12 + 4);
      }
      else if ( (char)v8 >= 12 && *v11 != -1 )
      {
        ++*v11;
      }
      v21[0] = v8;
      v21[1] = v10;
      v22 = v11;
      v13 = multiply_numeric(v24, v21, a3);
      v6 = *(_DWORD *)v13;
      v5 = *(_DWORD *)(v13 + 4);
      v7 = *(_QWORD *)(v13 + 8);
      if ( SLOBYTE(v21[0]) >= 12 && (v21[0] & 0x100) == 0 && *v22 != -1 )
      {
        v14 = *v22 - 1;
        *v22 = v14;
        if ( !v14 )
          (*((void (__fastcall **)(_DWORD *))v22 + 1))(v21);
      }
      goto LABEL_29;
    }
    if ( *(_BYTE *)a2 == 13 )
    {
      v9 = multiply_string(v24, a2, a3);
      goto LABEL_28;
    }
    if ( *(_BYTE *)a2 != 12 )
      goto LABEL_26;
    if ( *(_DWORD *)(*((_QWORD *)a2 + 1) + 16LL) )
    {
      v23 = 0;
      ModuleHandleA = GetModuleHandleA("mpunits.dll");
      v16 = 2060;
LABEL_34:
      String_LoadString = Intlstr_GetString_LoadString(ModuleHandleA, v16);
      v19 = 4;
      goto LABEL_35;
    }
    if ( *(_BYTE *)a2 == 12 )
    {
      if ( !*(_DWORD *)(*((_QWORD *)a2 + 1) + 16LL) )
      {
        v9 = multiply_interval(v24, a2, a3);
        goto LABEL_28;
      }
    }
    else
    {
LABEL_26:
      if ( (*(_BYTE *)a2 & 0xF0) == 0x10 )
      {
        v9 = multiply_array(v24, a2, a3);
        goto LABEL_28;
      }
      if ( *(_BYTE *)a2 == 15
        && ((__int64 (__fastcall *)(_QWORD))Observable_FromInstance)(*(_QWORD *)(*((_QWORD *)a2 + 1) + 24LL)) )
      {
        v23 = 0;
        v17 = GetModuleHandleA("mpunits.dll");
        String_LoadString = Intlstr_GetString_LoadString(v17, 2066);
        v19 = 7;
LABEL_35:
        *(_QWORD *)&v23 = String_LoadString;
        BYTE8(v23) = 0;
        MI_ReportErrorDetails_ForCustomError(v19, (int)L"MI", 0, 0);
        *(_DWORD *)(a1 + 4) = 0;
        *(_QWORD *)(a1 + 8) = 0;
        v6 = 254;
        goto LABEL_36;
      }
    }
    v23 = 0;
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    v16 = 2061;
    goto LABEL_34;
  }
  v5 = 0;
  v6 = 255;
  v7 = 0;
LABEL_29:
  *(_DWORD *)(a1 + 4) = v5;
  *(_QWORD *)(a1 + 8) = v7;
LABEL_36:
  result = a1;
  *(_DWORD *)a1 = v6;
  return result;
}

```

## disassembly

```asm
0x180014b50  push    rbp
0x180014b52  push    rbx
0x180014b53  push    rsi
0x180014b54  push    r14
0x180014b56  push    r15
0x180014b58  mov     rbp, rsp
0x180014b5b  sub     rsp, 60h
0x180014b5f  cmp     byte ptr [rdx], 0FFh
0x180014b62  mov     rbx, r8
0x180014b65  mov     rsi, rcx
0x180014b68  jnz     short loc_180014B7A
0x180014b6a  xor     r14d, r14d
0x180014b6d  mov     ebx, 0FFh
0x180014b72  xor     r15d, r15d
0x180014b75  jmp     loc_180014CE8
0x180014b7a  mov     r8d, [rdx]
0x180014b7d  bt      r8d, 8
0x180014b82  jnb     short loc_180014B97
0x180014b84  movzx   ebx, r8b
0x180014b88  xor     r15d, r15d
0x180014b8b  bts     ebx, 8
0x180014b8f  xor     r14d, r14d
0x180014b92  jmp     loc_180014CE8
0x180014b97  mov     al, [rdx]
0x180014b99  dec     al
0x180014b9b  cmp     al, 0Ah
0x180014b9d  ja      short loc_180014BB0
0x180014b9f  mov     r8, rbx
0x180014ba2  lea     rcx, [rbp+var_20]
0x180014ba6  call    multiply_numeric
0x180014bab  jmp     loc_180014CDE
0x180014bb0  cmp     byte ptr [rdx], 0
0x180014bb3  jnz     loc_180014C69
0x180014bb9  mov     eax, [rdx+4]
0x180014bbc  lea     ecx, [r8-1]
0x180014bc0  mov     r9, [rdx+8]
0x180014bc4  cmp     cl, 0Ah
0x180014bc7  ja      short loc_180014BDE
0x180014bc9  cmp     r8b, 0Ch
0x180014bcd  jl      short loc_180014C00
0x180014bcf  mov     ecx, [r9]
0x180014bd2  cmp     ecx, 0FFFFFFFFh
0x180014bd5  jz      short loc_180014C00
0x180014bd7  inc     ecx
0x180014bd9  mov     [r9], ecx
0x180014bdc  jmp     short loc_180014C00
0x180014bde  lea     rdx, [rbp+var_20]
0x180014be2  mov     dword ptr [rbp+var_20], r8d
0x180014be6  lea     rcx, [rbp+var_10]
0x180014bea  mov     dword ptr [rbp+var_20+4], eax
0x180014bed  mov     qword ptr [rbp+var_20+8], r9
0x180014bf1  call    MintValue_CoerceToNumberImpl
0x180014bf6  mov     r9, [rax+8]
0x180014bfa  mov     r8d, [rax]
0x180014bfd  mov     eax, [rax+4]
0x180014c00  mov     [rbp+var_30], r8d
0x180014c04  lea     rdx, [rbp+var_30]
0x180014c08  mov     r8, rbx
0x180014c0b  mov     [rbp+var_2C], eax
0x180014c0e  lea     rcx, [rbp+var_10]
0x180014c12  mov     [rbp+var_28], r9
0x180014c16  call    multiply_numeric
0x180014c1b  cmp     byte ptr [rbp+var_30], 0Ch
0x180014c1f  mov     ebx, [rax]
0x180014c21  mov     r14d, [rax+4]
0x180014c25  mov     r15, [rax+8]
0x180014c29  jl      loc_180014CE8
0x180014c2f  test    [rbp+var_30], 100h
0x180014c36  jnz     loc_180014CE8
0x180014c3c  mov     rcx, [rbp+var_28]
0x180014c40  mov     eax, [rcx]
0x180014c42  cmp     eax, 0FFFFFFFFh
0x180014c45  jz      loc_180014CE8
0x180014c4b  sub     eax, 1
0x180014c4e  mov     [rcx], eax
0x180014c50  jnz     loc_180014CE8
0x180014c56  mov     rax, [rbp+var_28]
0x180014c5a  lea     rcx, [rbp+var_30]
0x180014c5e  mov     rax, [rax+8]
0x180014c62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c67  jmp     short loc_180014CE8
0x180014c69  cmp     byte ptr [rdx], 0Dh
0x180014c6c  jnz     short loc_180014C7C
0x180014c6e  mov     r8, rbx
0x180014c71  lea     rcx, [rbp+var_10]
0x180014c75  call    multiply_string
0x180014c7a  jmp     short loc_180014CDE
0x180014c7c  cmp     byte ptr [rdx], 0Ch
0x180014c7f  jnz     short loc_180014CCA
0x180014c81  mov     rax, [rdx+8]
0x180014c85  cmp     dword ptr [rax+10h], 0
0x180014c89  jz      short loc_180014CA9
0x180014c8b  xorps   xmm0, xmm0
0x180014c8e  lea     rcx, ModuleName; "mpunits.dll"
0x180014c95  movups  [rbp+var_20], xmm0
0x180014c99  call    cs:__imp_GetModuleHandleA
0x180014c9f  mov     edx, 80Ch
0x180014ca4  jmp     loc_180014D5D
0x180014ca9  cmp     byte ptr [rdx], 0Ch
0x180014cac  jnz     short loc_180014CCA
0x180014cae  mov     rax, [rdx+8]
0x180014cb2  cmp     dword ptr [rax+10h], 0
0x180014cb6  jnz     loc_180014D44
0x180014cbc  mov     r8, rbx
0x180014cbf  lea     rcx, [rbp+var_10]
0x180014cc3  call    multiply_interval
0x180014cc8  jmp     short loc_180014CDE
0x180014cca  mov     al, [rdx]
0x180014ccc  and     al, 0F0h
0x180014cce  cmp     al, 10h
0x180014cd0  jnz     short loc_180014CF5
0x180014cd2  mov     r8, rbx
0x180014cd5  lea     rcx, [rbp+var_10]
0x180014cd9  call    multiply_array
0x180014cde  mov     r15, [rax+8]
0x180014ce2  mov     r14d, [rax+4]
0x180014ce6  mov     ebx, [rax]
0x180014ce8  mov     [rsi+4], r14d
0x180014cec  mov     [rsi+8], r15
0x180014cf0  jmp     loc_180014DBB
0x180014cf5  cmp     byte ptr [rdx], 0Fh
0x180014cf8  jnz     short loc_180014D44
0x180014cfa  mov     rcx, [rdx+8]
0x180014cfe  mov     rax, cs:off_180047B90
0x180014d05  mov     rcx, [rcx+18h]
0x180014d09  mov     rax, [rax+8]
0x180014d0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d12  test    rax, rax
0x180014d15  jz      short loc_180014D44
0x180014d17  xorps   xmm0, xmm0
0x180014d1a  lea     rcx, ModuleName; "mpunits.dll"
0x180014d21  movups  [rbp+var_20], xmm0
0x180014d25  call    cs:__imp_GetModuleHandleA
0x180014d2b  mov     rcx, rax
0x180014d2e  mov     edx, 812h
0x180014d33  call    _Intlstr_GetString_LoadString
0x180014d38  mov     r8d, 0Bh
0x180014d3e  lea     ecx, [r8-4]
0x180014d42  jmp     short loc_180014D6F
0x180014d44  xorps   xmm0, xmm0
0x180014d47  lea     rcx, ModuleName; "mpunits.dll"
0x180014d4e  movups  [rbp+var_20], xmm0
0x180014d52  call    cs:__imp_GetModuleHandleA
0x180014d58  mov     edx, 80Dh
0x180014d5d  mov     rcx, rax
0x180014d60  call    _Intlstr_GetString_LoadString
0x180014d65  mov     r8d, 5
0x180014d6b  lea     ecx, [r8-1]; int
0x180014d6f  mov     qword ptr [rbp+var_20], rax
0x180014d73  lea     r9, [rbp+var_20]
0x180014d77  mov     byte ptr [rbp+var_20+8], 0
0x180014d7b  lea     rdx, aMi; "MI"
0x180014d82  movaps  xmm0, [rbp+var_20]
0x180014d86  mov     [rsp+60h+var_38], 0; __int64
0x180014d8f  movdqa  [rbp+var_20], xmm0
0x180014d94  mov     [rsp+60h+var_40], 0; __int64
0x180014d9d  call    MI_ReportErrorDetails_ForCustomError
0x180014da2  xor     ecx, ecx
0x180014da4  xor     eax, eax
0x180014da6  mov     ebx, 0FFh
0x180014dab  mov     [rsi+4], ecx
0x180014dae  and     ebx, 0FFFFFFFEh
0x180014db1  mov     [rsi+8], rax
0x180014db5  or      ebx, 0FEh
0x180014dbb  mov     rax, rsi
0x180014dbe  mov     [rsi], ebx
0x180014dc0  add     rsp, 60h
0x180014dc4  pop     r15
0x180014dc6  pop     r14
0x180014dc8  pop     rsi
0x180014dc9  pop     rbx
0x180014dca  pop     rbp
0x180014dcb  retn
```
