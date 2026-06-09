# basicOps_plus

- ea: `0x180014de0`
- end: `0x180015052`
- name: `basicOps_plus`
- size: `626`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x1800150d0`
- `0x180031b70`
- `0x180033090`

## callees

- `0x180006ef8`
- `0x180007c80`
- `0x18000e650`
- `0x180013c9c`
- `0x180013f10`
- `0x1800140d8`
- `0x180014570`
- `0x180014748`
- `0x180014de0`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180014f7c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180014fa9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180014f7c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180014fa9`

## string_xrefs

- `0x180014f71`: `mpunits.dll`
- `0x180014f9e`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall basicOps_plus(__int64 a1, int *a2, __int128 *a3)
{
  int v5; // r8d
  __int128 *v6; // rax
  int v7; // eax
  int *v8; // r9
  __int64 v9; // rax
  __int128 v10; // xmm6
  int v11; // eax
  HMODULE v12; // rax
  __int64 String_LoadString; // rax
  int v14; // ecx
  HMODULE ModuleHandleA; // rax
  _DWORD *v16; // rcx
  _DWORD v18[2]; // [rsp+30h] [rbp-40h] BYREF
  int *v19; // [rsp+38h] [rbp-38h]
  __int128 v20; // [rsp+40h] [rbp-30h] BYREF
  _BYTE v21[16]; // [rsp+50h] [rbp-20h] BYREF

  if ( *(_BYTE *)a2 == 0xFF || (v5 = *a2, (*a2 & 0x100) != 0) )
  {
    if ( *(char *)a3 >= 12 && (*(_DWORD *)a3 & 0x100) == 0 )
    {
      v16 = (_DWORD *)*((_QWORD *)a3 + 1);
      if ( *v16 != -1 )
        ++*v16;
    }
    v10 = *a3;
    goto LABEL_37;
  }
  if ( (unsigned __int8)(v5 - 1) <= 0xAu )
  {
    v6 = (__int128 *)add_numeric(&v20, a2, a3);
LABEL_26:
    v10 = *v6;
LABEL_37:
    *(_OWORD *)a1 = v10;
    return a1;
  }
  switch ( *(_BYTE *)a2 )
  {
    case 0:
      v7 = a2[1];
      v8 = (int *)*((_QWORD *)a2 + 1);
      if ( (unsigned __int8)(v5 - 1) > 0xAu )
      {
        LODWORD(v20) = *a2;
        DWORD1(v20) = v7;
        *((_QWORD *)&v20 + 1) = v8;
        v9 = MintValue_CoerceToNumberImpl(v21, &v20);
        v8 = *(int **)(v9 + 8);
        v5 = *(_DWORD *)v9;
        v7 = *(_DWORD *)(v9 + 4);
      }
      else if ( (char)v5 >= 12 && *v8 != -1 )
      {
        ++*v8;
      }
      v18[0] = v5;
      v18[1] = v7;
      v19 = v8;
      v10 = *(_OWORD *)add_numeric(v21, v18, a3);
      if ( SLOBYTE(v18[0]) >= 12 && (v18[0] & 0x100) == 0 && *v19 != -1 )
      {
        v11 = *v19 - 1;
        *v19 = v11;
        if ( !v11 )
          (*((void (__fastcall **)(_DWORD *))v19 + 1))(v18);
      }
      goto LABEL_37;
    case 0xD:
      v6 = (__int128 *)add_string(v21, a2, a3);
      goto LABEL_26;
    case 0xC:
      if ( *(_DWORD *)(*((_QWORD *)a2 + 1) + 16LL) )
      {
        v6 = (__int128 *)add_timestamp(v21, a2, a3);
        goto LABEL_26;
      }
      if ( *(_BYTE *)a2 == 12 )
      {
        if ( !*(_DWORD *)(*((_QWORD *)a2 + 1) + 16LL) )
        {
          v6 = (__int128 *)add_interval(v21, a2, a3);
          goto LABEL_26;
        }
        goto LABEL_30;
      }
      break;
  }
  if ( (*(_BYTE *)a2 & 0xF0) == 0x10 )
  {
    v6 = (__int128 *)add_array(v21, a2, a3);
    goto LABEL_26;
  }
  if ( *(_BYTE *)a2 != 15
    || !((__int64 (__fastcall *)(_QWORD))Observable_FromInstance)(*(_QWORD *)(*((_QWORD *)a2 + 1) + 24LL)) )
  {
LABEL_30:
    v20 = 0;
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    String_LoadString = Intlstr_GetString_LoadString(ModuleHandleA, 2048);
    v14 = 4;
    goto LABEL_31;
  }
  v20 = 0;
  v12 = GetModuleHandleA("mpunits.dll");
  String_LoadString = Intlstr_GetString_LoadString(v12, 2066);
  v14 = 7;
LABEL_31:
  *(_QWORD *)&v20 = String_LoadString;
  BYTE8(v20) = 0;
  MI_ReportErrorDetails_ForCustomError(v14, (int)L"MI", 0, 0);
  *(_DWORD *)(a1 + 4) = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_DWORD *)a1 = 254;
  return a1;
}

```

## disassembly

```asm
0x180014de0  mov     [rsp-8+arg_0], rbx
0x180014de5  mov     [rsp-8+arg_8], rdi
0x180014dea  push    rbp
0x180014deb  mov     rbp, rsp
0x180014dee  sub     rsp, 70h
0x180014df2  cmp     byte ptr [rdx], 0FFh
0x180014df5  mov     rbx, r8
0x180014df8  movaps  [rsp+70h+var_10], xmm6
0x180014dfd  mov     rdi, rcx
0x180014e00  jz      loc_180015015
0x180014e06  mov     r8d, [rdx]
0x180014e09  bt      r8d, 8
0x180014e0e  jb      loc_180015015
0x180014e14  mov     al, r8b
0x180014e17  dec     al
0x180014e19  cmp     al, 0Ah
0x180014e1b  ja      short loc_180014E2E
0x180014e1d  mov     r8, rbx
0x180014e20  lea     rcx, [rbp+var_30]
0x180014e24  call    add_numeric
0x180014e29  jmp     loc_180014F44
0x180014e2e  cmp     byte ptr [rdx], 0
0x180014e31  jnz     loc_180014EE3
0x180014e37  mov     eax, [rdx+4]
0x180014e3a  lea     ecx, [r8-1]
0x180014e3e  mov     r9, [rdx+8]
0x180014e42  cmp     cl, 0Ah
0x180014e45  ja      short loc_180014E5C
0x180014e47  cmp     r8b, 0Ch
0x180014e4b  jl      short loc_180014E7E
0x180014e4d  mov     ecx, [r9]
0x180014e50  cmp     ecx, 0FFFFFFFFh
0x180014e53  jz      short loc_180014E7E
0x180014e55  inc     ecx
0x180014e57  mov     [r9], ecx
0x180014e5a  jmp     short loc_180014E7E
0x180014e5c  lea     rdx, [rbp+var_30]
0x180014e60  mov     dword ptr [rbp+var_30], r8d
0x180014e64  lea     rcx, [rbp+var_20]
0x180014e68  mov     dword ptr [rbp+var_30+4], eax
0x180014e6b  mov     qword ptr [rbp+var_30+8], r9
0x180014e6f  call    MintValue_CoerceToNumberImpl
0x180014e74  mov     r9, [rax+8]
0x180014e78  mov     r8d, [rax]
0x180014e7b  mov     eax, [rax+4]
0x180014e7e  mov     [rbp+var_40], r8d
0x180014e82  lea     rdx, [rbp+var_40]
0x180014e86  mov     r8, rbx
0x180014e89  mov     [rbp+var_3C], eax
0x180014e8c  lea     rcx, [rbp+var_20]
0x180014e90  mov     [rbp+var_38], r9
0x180014e94  call    add_numeric
0x180014e99  cmp     byte ptr [rbp+var_40], 0Ch
0x180014e9d  movups  xmm6, xmmword ptr [rax]
0x180014ea0  jl      loc_180015034
0x180014ea6  test    [rbp+var_40], 100h
0x180014ead  jnz     loc_180015034
0x180014eb3  mov     rcx, [rbp+var_38]
0x180014eb7  mov     eax, [rcx]
0x180014eb9  cmp     eax, 0FFFFFFFFh
0x180014ebc  jz      loc_180015034
0x180014ec2  sub     eax, 1
0x180014ec5  mov     [rcx], eax
0x180014ec7  jnz     loc_180015034
0x180014ecd  mov     rax, [rbp+var_38]
0x180014ed1  lea     rcx, [rbp+var_40]
0x180014ed5  mov     rax, [rax+8]
0x180014ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ede  jmp     loc_180015034
0x180014ee3  cmp     byte ptr [rdx], 0Dh
0x180014ee6  jnz     short loc_180014EF6
0x180014ee8  mov     r8, rbx
0x180014eeb  lea     rcx, [rbp+var_20]
0x180014eef  call    add_string
0x180014ef4  jmp     short loc_180014F44
0x180014ef6  cmp     byte ptr [rdx], 0Ch
0x180014ef9  jnz     short loc_180014F30
0x180014efb  mov     rax, [rdx+8]
0x180014eff  cmp     dword ptr [rax+10h], 0
0x180014f03  jz      short loc_180014F13
0x180014f05  mov     r8, rbx
0x180014f08  lea     rcx, [rbp+var_20]
0x180014f0c  call    add_timestamp
0x180014f11  jmp     short loc_180014F44
0x180014f13  cmp     byte ptr [rdx], 0Ch
0x180014f16  jnz     short loc_180014F30
0x180014f18  mov     rax, [rdx+8]
0x180014f1c  cmp     dword ptr [rax+10h], 0
0x180014f20  jnz     short loc_180014F9B
0x180014f22  mov     r8, rbx
0x180014f25  lea     rcx, [rbp+var_20]
0x180014f29  call    add_interval
0x180014f2e  jmp     short loc_180014F44
0x180014f30  mov     al, [rdx]
0x180014f32  and     al, 0F0h
0x180014f34  cmp     al, 10h
0x180014f36  jnz     short loc_180014F4C
0x180014f38  mov     r8, rbx
0x180014f3b  lea     rcx, [rbp+var_20]
0x180014f3f  call    add_array
0x180014f44  movups  xmm6, xmmword ptr [rax]
0x180014f47  jmp     loc_180015034
0x180014f4c  cmp     byte ptr [rdx], 0Fh
0x180014f4f  jnz     short loc_180014F9B
0x180014f51  mov     rcx, [rdx+8]
0x180014f55  mov     rax, cs:off_180047B90
0x180014f5c  mov     rcx, [rcx+18h]
0x180014f60  mov     rax, [rax+8]
0x180014f64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f69  test    rax, rax
0x180014f6c  jz      short loc_180014F9B
0x180014f6e  xorps   xmm0, xmm0
0x180014f71  lea     rcx, ModuleName; "mpunits.dll"
0x180014f78  movups  [rbp+var_30], xmm0
0x180014f7c  call    cs:__imp_GetModuleHandleA
0x180014f82  mov     rcx, rax
0x180014f85  mov     edx, 812h
0x180014f8a  call    _Intlstr_GetString_LoadString
0x180014f8f  mov     r8d, 0Bh
0x180014f95  lea     ecx, [r8-4]
0x180014f99  jmp     short loc_180014FC6
0x180014f9b  xorps   xmm0, xmm0
0x180014f9e  lea     rcx, ModuleName; "mpunits.dll"
0x180014fa5  movups  [rbp+var_30], xmm0
0x180014fa9  call    cs:__imp_GetModuleHandleA
0x180014faf  mov     rcx, rax
0x180014fb2  mov     edx, 800h
0x180014fb7  call    _Intlstr_GetString_LoadString
0x180014fbc  mov     r8d, 5
0x180014fc2  lea     ecx, [r8-1]; int
0x180014fc6  mov     qword ptr [rbp+var_30], rax
0x180014fca  lea     r9, [rbp+var_30]
0x180014fce  mov     byte ptr [rbp+var_30+8], 0
0x180014fd2  lea     rdx, aMi; "MI"
0x180014fd9  movaps  xmm0, [rbp+var_30]
0x180014fdd  mov     [rsp+70h+var_48], 0; __int64
0x180014fe6  movdqa  [rbp+var_30], xmm0
0x180014feb  mov     [rsp+70h+var_50], 0; __int64
0x180014ff4  call    MI_ReportErrorDetails_ForCustomError
0x180014ff9  xor     edx, edx
0x180014ffb  xor     ecx, ecx
0x180014ffd  mov     eax, 0FFh
0x180015002  mov     [rdi+4], edx
0x180015005  and     eax, 0FFFFFFFEh
0x180015008  mov     [rdi+8], rcx
0x18001500c  or      eax, 0FEh
0x180015011  mov     [rdi], eax
0x180015013  jmp     short loc_180015038
0x180015015  cmp     byte ptr [rbx], 0Ch
0x180015018  jl      short loc_180015031
0x18001501a  test    dword ptr [rbx], 100h
0x180015020  jnz     short loc_180015031
0x180015022  mov     rcx, [rbx+8]
0x180015026  mov     eax, [rcx]
0x180015028  cmp     eax, 0FFFFFFFFh
0x18001502b  jz      short loc_180015031
0x18001502d  inc     eax
0x18001502f  mov     [rcx], eax
0x180015031  movups  xmm6, xmmword ptr [rbx]
0x180015034  movdqu  xmmword ptr [rdi], xmm6
0x180015038  movaps  xmm6, [rsp+70h+var_10]
0x18001503d  lea     r11, [rsp+70h+var_s0]
0x180015042  mov     rbx, [r11+10h]
0x180015046  mov     rax, rdi
0x180015049  mov     rdi, [r11+18h]
0x18001504d  mov     rsp, r11
0x180015050  pop     rbp
0x180015051  retn
```
