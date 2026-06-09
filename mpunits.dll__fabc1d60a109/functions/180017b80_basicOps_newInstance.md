# basicOps_newInstance

- ea: `0x180017b80`
- end: `0x180017e8b`
- name: `basicOps_newInstance`
- size: `779`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006ef8`
- `0x180007c80`
- `0x180007d60`
- `0x180007ea0`
- `0x1800080c0`
- `0x18000f9d0`
- `0x180010820`
- `0x180013bb0`
- `0x1800178ec`
- `0x180017b80`
- `0x180044880`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180017db1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180017db1`

## string_xrefs

- `0x180017da6`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall basicOps_newInstance(__int64 a1, __int128 *a2, __int64 a3, unsigned int a4)
{
  _OWORD *v7; // rax
  __int64 v8; // rdx
  __int64 DynamicInstance; // rdi
  int v10; // eax
  int v11; // r14d
  int v12; // r15d
  __int64 v13; // rsi
  _BYTE *v14; // rcx
  int v15; // eax
  __int64 v16; // rax
  int v17; // eax
  HMODULE ModuleHandleA; // rax
  int v19; // eax
  __m128i v21; // [rsp+30h] [rbp-49h] BYREF
  int v22; // [rsp+40h] [rbp-39h] BYREF
  _DWORD v23[3]; // [rsp+44h] [rbp-35h] BYREF
  __int128 v24; // [rsp+50h] [rbp-29h] BYREF
  _BYTE v25[16]; // [rsp+60h] [rbp-19h] BYREF
  _OWORD v26[2]; // [rsp+70h] [rbp-9h] BYREF
  __int64 v27; // [rsp+90h] [rbp+17h]

  v21 = (__m128i)0x10FuLL;
  if ( (a4 & 1) == 0 )
  {
    v24 = *a2;
    v21 = *(__m128i *)MintValue_CoerceAndRaiseInvalidCastException_0(v25, a2, &v24);
    if ( (unsigned __int8)_mm_cvtsi128_si32(v21) != 0xFE )
    {
      DynamicInstance = CreateDynamicInstance(*(_QWORD *)(v21.m128i_i64[1] + 16));
      if ( DynamicInstance )
      {
        if ( v21.m128i_i8[0] >= 12 && (v21.m128i_i16[0] & 0x100) == 0 && *(_DWORD *)v21.m128i_i64[1] != -1 )
        {
          v10 = *(_DWORD *)v21.m128i_i64[1] - 1;
          *(_DWORD *)v21.m128i_i64[1] = v10;
          if ( !v10 )
            (*(void (__fastcall **)(__m128i *))(v21.m128i_i64[1] + 8))(&v21);
        }
        v11 = 0;
        v12 = a4 - 1;
        if ( (int)(a4 - 1) <= 0 )
        {
LABEL_27:
          v7 = (_OWORD *)MintValue_CreateFromInstance(v25, DynamicInstance, 1);
          goto LABEL_3;
        }
        while ( 1 )
        {
          memset(v26, 0, sizeof(v26));
          v13 = 16LL * v11;
          v27 = 0;
          v23[0] = 0;
          v22 = 0;
          v24 = *(_OWORD *)(v13 + a3);
          v21 = *(__m128i *)MintValue_CoerceAndRaiseInvalidCastException_0(v25, v8, &v24);
          v21.m128i_i8[0] = _mm_cvtsi128_si32(v21);
          if ( v21.m128i_i8[0] == -2 )
            break;
          v14 = (_BYTE *)(v13 + a3 + 16);
          if ( *v14 > 0x1Fu )
          {
            if ( *(_BYTE *)(a3 + 16 * (v11 + 1LL)) != 0xFF )
            {
              v24 = 0;
              ModuleHandleA = GetModuleHandleA("mpunits.dll");
              *(_QWORD *)&v24 = Intlstr_GetString_LoadString(ModuleHandleA, 2075);
              BYTE8(v24) = 0;
              MI_ReportErrorDetails_ForCustomError(4, (int)L"MI", 0, 0);
              break;
            }
            v16 = *(_QWORD *)DynamicInstance;
            *(_QWORD *)&v26[0] = 0;
            if ( !v16 )
            {
LABEL_28:
              v15 = 4;
LABEL_29:
              MI_ReportErrorDetails_ForMiResult(v15);
              break;
            }
            v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, _OWORD *, __int64, int))(v16 + 64))(
                    DynamicInstance,
                    *(_QWORD *)(v21.m128i_i64[1] + 16),
                    v26,
                    15,
                    0x20000000);
          }
          else
          {
            MintValue_GetMiValue(v14, v26, v23, &v22);
            if ( !*(_QWORD *)DynamicInstance )
              goto LABEL_28;
            v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, _OWORD *, _QWORD, int))(*(_QWORD *)DynamicInstance + 64LL))(
                    DynamicInstance,
                    *(_QWORD *)(v21.m128i_i64[1] + 16),
                    v26,
                    v23[0],
                    v22);
          }
          if ( v15 )
            goto LABEL_29;
          if ( v21.m128i_i8[0] >= 12 && (v21.m128i_i16[0] & 0x100) == 0 && *(_DWORD *)v21.m128i_i64[1] != -1 )
          {
            v17 = *(_DWORD *)v21.m128i_i64[1] - 1;
            *(_DWORD *)v21.m128i_i64[1] = v17;
            if ( !v17 )
              (*(void (__fastcall **)(__m128i *))(v21.m128i_i64[1] + 8))(&v21);
          }
          v11 += 2;
          if ( v11 >= v12 )
            goto LABEL_27;
        }
        if ( *(_QWORD *)DynamicInstance )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)DynamicInstance + 16LL))(DynamicInstance);
      }
      else
      {
        MI_ReportErrorDetails_OutOfMemory();
      }
      if ( v21.m128i_i8[0] >= 12 && (v21.m128i_i16[0] & 0x100) == 0 && *(_DWORD *)v21.m128i_i64[1] != -1 )
      {
        v19 = *(_DWORD *)v21.m128i_i64[1] - 1;
        *(_DWORD *)v21.m128i_i64[1] = v19;
        if ( !v19 )
          (*(void (__fastcall **)(__m128i *))(v21.m128i_i64[1] + 8))(&v21);
      }
    }
    *(_DWORD *)(a1 + 4) = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)a1 = 254;
    return a1;
  }
  v7 = (_OWORD *)BuiltinsError_WrongNumberOfArguments(&v24, a4);
LABEL_3:
  *(_OWORD *)a1 = *v7;
  return a1;
}

```

## disassembly

```asm
0x180017b80  mov     [rsp-8+arg_0], rbx
0x180017b85  push    rbp
0x180017b86  push    rsi
0x180017b87  push    rdi
0x180017b88  push    r12
0x180017b8a  push    r13
0x180017b8c  push    r14
0x180017b8e  push    r15
0x180017b90  lea     rbp, [rsp-27h]
0x180017b95  sub     rsp, 0A0h
0x180017b9c  mov     rax, cs:__security_cookie
0x180017ba3  xor     rax, rsp
0x180017ba6  mov     [rbp+57h+var_38], rax
0x180017baa  mov     qword ptr [rbp+57h+var_A0], 10Fh
0x180017bb2  mov     esi, r9d
0x180017bb5  mov     qword ptr [rbp+57h+var_A0+8], 0
0x180017bbd  mov     r12, r8
0x180017bc0  mov     rbx, rcx
0x180017bc3  test    r9b, 1
0x180017bc7  jz      short loc_180017BE1
0x180017bc9  mov     edx, r9d
0x180017bcc  lea     rcx, [rbp+57h+var_80]
0x180017bd0  call    BuiltinsError_WrongNumberOfArguments
0x180017bd5  movups  xmm0, xmmword ptr [rax]
0x180017bd8  movdqu  xmmword ptr [rbx], xmm0
0x180017bdc  jmp     loc_180017E61
0x180017be1  movups  xmm0, xmmword ptr [rdx]
0x180017be4  lea     r8, [rbp+57h+var_80]
0x180017be8  lea     rcx, [rbp+57h+var_70]
0x180017bec  movdqu  [rbp+57h+var_80], xmm0
0x180017bf1  call    MintValue_CoerceAndRaiseInvalidCastException_0
0x180017bf6  movups  xmm0, xmmword ptr [rax]
0x180017bf9  movd    eax, xmm0
0x180017bfd  movups  [rbp+57h+var_A0], xmm0
0x180017c01  cmp     al, 0FEh
0x180017c03  jz      loc_180017E47
0x180017c09  mov     rcx, qword ptr [rbp+57h+var_A0+8]
0x180017c0d  mov     rcx, [rcx+10h]
0x180017c11  call    CreateDynamicInstance
0x180017c16  mov     rdi, rax
0x180017c19  test    rax, rax
0x180017c1c  jnz     short loc_180017C28
0x180017c1e  call    MI_ReportErrorDetails_OutOfMemory
0x180017c23  jmp     loc_180017E15
0x180017c28  cmp     byte ptr [rbp+57h+var_A0], 0Ch
0x180017c2c  jl      short loc_180017C5A
0x180017c2e  test    dword ptr [rbp+57h+var_A0], 100h
0x180017c35  jnz     short loc_180017C5A
0x180017c37  mov     rcx, qword ptr [rbp+57h+var_A0+8]
0x180017c3b  mov     eax, [rcx]
0x180017c3d  cmp     eax, 0FFFFFFFFh
0x180017c40  jz      short loc_180017C5A
0x180017c42  sub     eax, 1
0x180017c45  mov     [rcx], eax
0x180017c47  jnz     short loc_180017C5A
0x180017c49  mov     rax, qword ptr [rbp+57h+var_A0+8]
0x180017c4d  lea     rcx, [rbp+57h+var_A0]
0x180017c51  mov     rax, [rax+8]
0x180017c55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c5a  xor     r14d, r14d
0x180017c5d  lea     r15d, [rsi-1]
0x180017c61  test    r15d, r15d
0x180017c64  jle     loc_180017D7E
0x180017c6a  xorps   xmm0, xmm0
0x180017c6d  movsxd  r13, r14d
0x180017c70  xor     eax, eax
0x180017c72  lea     r8, [rbp+57h+var_80]
0x180017c76  movups  [rbp+57h+var_60], xmm0
0x180017c7a  mov     rsi, r13
0x180017c7d  lea     rcx, [rbp+57h+var_70]
0x180017c81  movups  [rbp+57h+var_50], xmm0
0x180017c85  shl     rsi, 4
0x180017c89  mov     [rbp+57h+var_40], rax
0x180017c8d  mov     [rbp+57h+var_8C], eax
0x180017c90  mov     [rbp+57h+var_90], eax
0x180017c93  movups  xmm0, xmmword ptr [rsi+r12]
0x180017c98  movdqu  [rbp+57h+var_80], xmm0
0x180017c9d  call    MintValue_CoerceAndRaiseInvalidCastException_0
0x180017ca2  movups  xmm0, xmmword ptr [rax]
0x180017ca5  movd    eax, xmm0
0x180017ca9  movups  [rbp+57h+var_A0], xmm0
0x180017cad  mov     byte ptr [rbp+57h+var_A0], al
0x180017cb0  cmp     al, 0FEh
0x180017cb2  jz      loc_180017E01
0x180017cb8  lea     rcx, [r12+10h]
0x180017cbd  add     rcx, rsi
0x180017cc0  cmp     byte ptr [rcx], 1Fh
0x180017cc3  ja      short loc_180017CEF
0x180017cc5  lea     r9, [rbp+57h+var_90]
0x180017cc9  lea     r8, [rbp+57h+var_8C]
0x180017ccd  lea     rdx, [rbp+57h+var_60]
0x180017cd1  call    MintValue_GetMiValue
0x180017cd6  mov     rax, [rdi]
0x180017cd9  test    rax, rax
0x180017cdc  jz      loc_180017D95
0x180017ce2  mov     ecx, [rbp+57h+var_90]
0x180017ce5  mov     r9d, [rbp+57h+var_8C]
0x180017ce9  mov     dword ptr [rsp+0D0h+var_B0], ecx
0x180017ced  jmp     short loc_180017D23
0x180017cef  lea     rax, [r13+1]
0x180017cf3  add     rax, rax
0x180017cf6  cmp     byte ptr [r12+rax*8], 0FFh
0x180017cfb  jnz     loc_180017DA3
0x180017d01  mov     rax, [rdi]
0x180017d04  mov     qword ptr [rbp+57h+var_60], 0
0x180017d0c  test    rax, rax
0x180017d0f  jz      loc_180017D95
0x180017d15  mov     dword ptr [rsp+0D0h+var_B0], 20000000h
0x180017d1d  mov     r9d, 0Fh
0x180017d23  mov     rdx, qword ptr [rbp+57h+var_A0+8]
0x180017d27  lea     r8, [rbp+57h+var_60]
0x180017d2b  mov     rax, [rax+40h]
0x180017d2f  mov     rcx, rdi
0x180017d32  mov     rdx, [rdx+10h]
0x180017d36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d3b  test    eax, eax
0x180017d3d  jnz     short loc_180017D9A
0x180017d3f  cmp     byte ptr [rbp+57h+var_A0], 0Ch
0x180017d43  jl      short loc_180017D71
0x180017d45  test    dword ptr [rbp+57h+var_A0], 100h
0x180017d4c  jnz     short loc_180017D71
0x180017d4e  mov     rcx, qword ptr [rbp+57h+var_A0+8]
0x180017d52  mov     eax, [rcx]
0x180017d54  cmp     eax, 0FFFFFFFFh
0x180017d57  jz      short loc_180017D71
0x180017d59  sub     eax, 1
0x180017d5c  mov     [rcx], eax
0x180017d5e  jnz     short loc_180017D71
0x180017d60  mov     rax, qword ptr [rbp+57h+var_A0+8]
0x180017d64  lea     rcx, [rbp+57h+var_A0]
0x180017d68  mov     rax, [rax+8]
0x180017d6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d71  add     r14d, 2
0x180017d75  cmp     r14d, r15d
0x180017d78  jl      loc_180017C6A
0x180017d7e  mov     r8d, 1
0x180017d84  lea     rcx, [rbp+57h+var_70]
0x180017d88  mov     rdx, rdi
0x180017d8b  call    MintValue_CreateFromInstance
0x180017d90  jmp     loc_180017BD5
0x180017d95  mov     eax, 4
0x180017d9a  mov     ecx, eax; int
0x180017d9c  call    MI_ReportErrorDetails_ForMiResult
0x180017da1  jmp     short loc_180017E01
0x180017da3  xorps   xmm0, xmm0
0x180017da6  lea     rcx, ModuleName; "mpunits.dll"
0x180017dad  movups  [rbp+57h+var_80], xmm0
0x180017db1  call    cs:__imp_GetModuleHandleA
0x180017db7  mov     rcx, rax
0x180017dba  mov     edx, 81Bh
0x180017dbf  call    _Intlstr_GetString_LoadString
0x180017dc4  mov     qword ptr [rbp+57h+var_80], rax
0x180017dc8  lea     r9, [rbp+57h+var_80]
0x180017dcc  mov     byte ptr [rbp+57h+var_80+8], 0
0x180017dd0  lea     rdx, aMi; "MI"
0x180017dd7  movaps  xmm0, [rbp+57h+var_80]
0x180017ddb  mov     r8d, 5
0x180017de1  mov     [rsp+0D0h+var_A8], 0; __int64
0x180017dea  movdqa  [rbp+57h+var_80], xmm0
0x180017def  mov     [rsp+0D0h+var_B0], 0; __int64
0x180017df8  lea     ecx, [r8-1]; int
0x180017dfc  call    MI_ReportErrorDetails_ForCustomError
0x180017e01  mov     rax, [rdi]
0x180017e04  test    rax, rax
0x180017e07  jz      short loc_180017E15
0x180017e09  mov     rax, [rax+10h]
0x180017e0d  mov     rcx, rdi
0x180017e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e15  cmp     byte ptr [rbp+57h+var_A0], 0Ch
0x180017e19  jl      short loc_180017E47
0x180017e1b  test    dword ptr [rbp+57h+var_A0], 100h
0x180017e22  jnz     short loc_180017E47
0x180017e24  mov     rcx, qword ptr [rbp+57h+var_A0+8]
0x180017e28  mov     eax, [rcx]
0x180017e2a  cmp     eax, 0FFFFFFFFh
0x180017e2d  jz      short loc_180017E47
0x180017e2f  sub     eax, 1
0x180017e32  mov     [rcx], eax
0x180017e34  jnz     short loc_180017E47
0x180017e36  mov     rax, qword ptr [rbp+57h+var_A0+8]
0x180017e3a  lea     rcx, [rbp+57h+var_A0]
0x180017e3e  mov     rax, [rax+8]
0x180017e42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e47  xor     edx, edx
0x180017e49  xor     ecx, ecx
0x180017e4b  mov     eax, 0FFh
0x180017e50  mov     [rbx+4], edx
0x180017e53  and     eax, 0FFFFFFFEh
0x180017e56  mov     [rbx+8], rcx
0x180017e5a  or      eax, 0FEh
0x180017e5f  mov     [rbx], eax
0x180017e61  mov     rax, rbx
0x180017e64  mov     rcx, [rbp+57h+var_38]
0x180017e68  xor     rcx, rsp; StackCookie
0x180017e6b  call    __security_check_cookie
0x180017e70  mov     rbx, [rsp+0D0h+arg_0]
0x180017e78  add     rsp, 0A0h
0x180017e7f  pop     r15
0x180017e81  pop     r14
0x180017e83  pop     r13
0x180017e85  pop     r12
0x180017e87  pop     rdi
0x180017e88  pop     rsi
0x180017e89  pop     rbp
0x180017e8a  retn
```
