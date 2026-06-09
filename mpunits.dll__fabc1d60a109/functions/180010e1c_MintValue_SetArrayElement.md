# MintValue_SetArrayElement

- ea: `0x180010e1c`
- end: `0x180011159`
- name: `MintValue_SetArrayElement`
- size: `829`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x18000f830`

## callees

- `0x180006ef8`
- `0x180007030`
- `0x1800074b0`
- `0x180007c80`
- `0x180007d60`
- `0x180007ea0`
- `0x180010820`
- `0x180010e1c`
- `0x180013840`
- `0x180013b30`
- `0x180044842`
- `0x180044880`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180010e6e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180010e6e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010f86`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010f86`

## string_xrefs

- `0x180010e5d`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall MintValue_SetArrayElement(char *a1, __int64 a2, unsigned int a3)
{
  int v3; // eax
  __int64 v5; // r14
  unsigned int v7; // ebx
  HMODULE ModuleHandleA; // rax
  __int64 v9; // rax
  _QWORD *v10; // rcx
  bool v11; // zf
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // ecx
  unsigned int v15; // eax
  __int64 v16; // r9
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // rcx
  int v23; // [rsp+30h] [rbp-99h] BYREF
  _DWORD v24[3]; // [rsp+34h] [rbp-95h] BYREF
  __int128 v25; // [rsp+40h] [rbp-89h] BYREF
  _QWORD v26[16]; // [rsp+50h] [rbp-79h] BYREF
  _OWORD v27[2]; // [rsp+D0h] [rbp+7h] BYREF
  __int64 v28; // [rsp+F0h] [rbp+27h]

  v3 = *a1;
  v5 = a3;
  if ( *a1 == 31 )
  {
    v7 = 0;
  }
  else
  {
    if ( (*(_DWORD *)a2 & 0x100) != 0 )
    {
      v25 = 0;
      v7 = 4;
      ModuleHandleA = GetModuleHandleA("mpunits.dll");
      *(_QWORD *)&v25 = Intlstr_GetString_LoadString(ModuleHandleA, 2106);
      BYTE8(v25) = 0;
      MI_ReportErrorDetails_ForCustomError(4, (int)L"MI", 0, 0);
      return v7;
    }
    v7 = 0;
    if ( (char)v3 <= 23 )
    {
      if ( (_BYTE)v3 != 23 )
      {
        if ( v3 == 16 || v3 == 17 || v3 == 18 )
        {
          *(_BYTE *)(a3 + *(_QWORD *)(*((_QWORD *)a1 + 1) + 16LL)) = *(_BYTE *)(a2 + 8);
          return v7;
        }
        if ( v3 != 19 && v3 != 20 )
        {
          if ( (unsigned int)(v3 - 21) <= 1 )
          {
            *(_DWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 1) + 16LL) + 4LL * a3) = *(_DWORD *)(a2 + 8);
            return v7;
          }
LABEL_24:
          RaiseException(0xC0000025, 1u, 0, 0);
          return v7;
        }
LABEL_13:
        *(_WORD *)(*(_QWORD *)(*((_QWORD *)a1 + 1) + 16LL) + 2LL * a3) = *(_WORD *)(a2 + 8);
        return v7;
      }
      v9 = *((_QWORD *)a1 + 1);
LABEL_50:
      *(_QWORD *)(*(_QWORD *)(v9 + 16) + 8LL * a3) = *(_QWORD *)(a2 + 8);
      return v7;
    }
  }
  switch ( v3 )
  {
    case 24:
      goto LABEL_49;
    case 25:
      *(float *)(*(_QWORD *)(*((_QWORD *)a1 + 1) + 16LL) + 4LL * a3) = *(double *)(a2 + 8);
      return v7;
    case 26:
LABEL_49:
      v9 = *((_QWORD *)a1 + 1);
      goto LABEL_50;
    case 27:
      goto LABEL_13;
    case 28:
      v19 = *(_QWORD *)(a2 + 8);
      v20 = 9 * v5;
      v21 = *(_QWORD *)(*((_QWORD *)a1 + 1) + 16LL);
      *(_OWORD *)(v21 + 4 * v20) = *(_OWORD *)(v19 + 16);
      *(_OWORD *)(v21 + 4 * v20 + 16) = *(_OWORD *)(v19 + 32);
      *(_DWORD *)(v21 + 4 * v20 + 32) = *(_DWORD *)(v19 + 48);
      return v7;
    case 29:
      v16 = PoolTls_Tcsdup(*(void **)(*(_QWORD *)(a2 + 8) + 16LL));
      if ( v16 )
      {
        v17 = *(_QWORD *)(*((_QWORD *)a1 + 1) + 16LL);
        v18 = *(_QWORD *)(v17 + 8 * v5);
        *(_QWORD *)(v17 + 8 * v5) = v16;
        PoolTls_Free(v18);
      }
      else
      {
        v7 = 27;
        MI_ReportErrorDetails_OutOfMemory();
      }
      return v7;
  }
  if ( v3 != 31 )
    goto LABEL_24;
  v11 = *(_BYTE *)a2 == 15;
  *(_QWORD *)&v25 = 0;
  if ( !v11 || (*(_DWORD *)a2 & 0x100) != 0 )
  {
    v28 = 0;
    v24[0] = 0;
    memset(v27, 0, sizeof(v27));
    v23 = 0;
    memset_0(v26, 0, 0x78u);
    MintValue_GetMiValue(a2, v27, v24, &v23);
    v15 = Box(v27, v24[0], (v23 & 0x20000000) != 0, v26);
    v7 = v15;
    if ( v15 )
    {
      v14 = v15;
      goto LABEL_36;
    }
    if ( v26[0] && *(_QWORD *)v26[0] )
      v7 = (**(__int64 (__fastcall ***)(_QWORD, __int128 *))v26[0])(v26[0], &v25);
    else
      v7 = 4;
    BoxFree(v26);
    v11 = v7 == 0;
  }
  else
  {
    v10 = *(_QWORD **)(*(_QWORD *)(a2 + 8) + 24LL);
    if ( !v10 || !*v10 )
    {
      v7 = 4;
      goto LABEL_35;
    }
    v7 = (*(__int64 (__fastcall **)(_QWORD *, __int128 *))*v10)(v10, &v25);
    v11 = v7 == 0;
  }
  if ( !v11 )
  {
LABEL_35:
    v14 = v7;
LABEL_36:
    MI_ReportErrorDetails_ForMiResult(v14);
    return v7;
  }
  v12 = *(_QWORD *)(*((_QWORD *)a1 + 1) + 16LL);
  v13 = *(_QWORD *)(v12 + 8 * v5);
  *(_QWORD *)(v12 + 8 * v5) = v25;
  if ( v13 && *(_QWORD *)v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  return v7;
}

```

## disassembly

```asm
0x180010e1c  push    rbp
0x180010e1e  push    rbx
0x180010e1f  push    rsi
0x180010e20  push    rdi
0x180010e21  push    r14
0x180010e23  lea     rbp, [rsp-37h]
0x180010e28  sub     rsp, 100h
0x180010e2f  mov     rax, cs:__security_cookie
0x180010e36  xor     rax, rsp
0x180010e39  mov     [rbp+57h+var_28], rax
0x180010e3d  movsx   eax, byte ptr [rcx]
0x180010e40  mov     rdi, rdx
0x180010e43  mov     r14d, r8d
0x180010e46  mov     rsi, rcx
0x180010e49  mov     edx, 100h
0x180010e4e  cmp     al, 1Fh
0x180010e50  jz      loc_180010F3C
0x180010e56  test    [rdi], edx
0x180010e58  jz      short loc_180010EC4
0x180010e5a  xorps   xmm0, xmm0
0x180010e5d  lea     rcx, ModuleName; "mpunits.dll"
0x180010e64  movups  [rsp+120h+var_E0], xmm0
0x180010e69  mov     ebx, 4
0x180010e6e  call    cs:__imp_GetModuleHandleA
0x180010e74  mov     rcx, rax
0x180010e77  mov     edx, 83Ah
0x180010e7c  call    _Intlstr_GetString_LoadString
0x180010e81  mov     qword ptr [rsp+120h+var_E0], rax
0x180010e86  lea     r9, [rsp+120h+var_E0]
0x180010e8b  mov     byte ptr [rsp+120h+var_E0+8], 0
0x180010e90  lea     r8d, [rbx+1]
0x180010e94  movaps  xmm0, [rsp+120h+var_E0]
0x180010e99  lea     rdx, aMi; "MI"
0x180010ea0  mov     [rsp+120h+var_F8], 0; __int64
0x180010ea9  mov     ecx, ebx; int
0x180010eab  movdqa  [rsp+120h+var_E0], xmm0
0x180010eb1  mov     [rsp+120h+var_100], 0; __int64
0x180010eba  call    MI_ReportErrorDetails_ForCustomError
0x180010ebf  jmp     loc_18001113D
0x180010ec4  xor     ebx, ebx
0x180010ec6  cmp     al, 17h
0x180010ec8  jg      short loc_180010F3E
0x180010eca  jz      short loc_180010F33
0x180010ecc  mov     ecx, eax
0x180010ece  sub     ecx, 10h
0x180010ed1  jz      short loc_180010F1F
0x180010ed3  sub     ecx, 1
0x180010ed6  jz      short loc_180010F1F
0x180010ed8  sub     ecx, 1
0x180010edb  jz      short loc_180010F1F
0x180010edd  sub     ecx, 1
0x180010ee0  jz      short loc_180010F09
0x180010ee2  sub     ecx, 1
0x180010ee5  jz      short loc_180010F09
0x180010ee7  sub     ecx, 1
0x180010eea  jz      short loc_180010EF5
0x180010eec  cmp     ecx, 1
0x180010eef  jnz     loc_180010F77
0x180010ef5  mov     rax, [rsi+8]
0x180010ef9  mov     rcx, [rax+10h]
0x180010efd  mov     eax, [rdi+8]
0x180010f00  mov     [rcx+r14*4], eax
0x180010f04  jmp     loc_18001113D
0x180010f09  mov     rax, [rsi+8]
0x180010f0d  mov     rcx, [rax+10h]
0x180010f11  movzx   eax, word ptr [rdi+8]
0x180010f15  mov     [rcx+r14*2], ax
0x180010f1a  jmp     loc_18001113D
0x180010f1f  mov     rax, [rsi+8]
0x180010f23  mov     rcx, [rax+10h]
0x180010f27  mov     al, [rdi+8]
0x180010f2a  mov     [r14+rcx], al
0x180010f2e  jmp     loc_18001113D
0x180010f33  mov     rax, [rcx+8]
0x180010f37  jmp     loc_180011131
0x180010f3c  xor     ebx, ebx
0x180010f3e  mov     ecx, eax
0x180010f40  sub     ecx, 18h
0x180010f43  jz      loc_18001112D
0x180010f49  sub     ecx, 1
0x180010f4c  jz      loc_180011114
0x180010f52  sub     ecx, 1
0x180010f55  jz      loc_18001112D
0x180010f5b  sub     ecx, 1
0x180010f5e  jz      short loc_180010F09
0x180010f60  sub     ecx, 1
0x180010f63  jz      loc_1800110E7
0x180010f69  sub     ecx, 1
0x180010f6c  jz      loc_1800110B1
0x180010f72  cmp     ecx, 2
0x180010f75  jz      short loc_180010F91
0x180010f77  xor     r9d, r9d; lpArguments
0x180010f7a  xor     r8d, r8d; nNumberOfArguments
0x180010f7d  mov     ecx, 0C0000025h; dwExceptionCode
0x180010f82  lea     edx, [r9+1]; dwExceptionFlags
0x180010f86  call    cs:__imp_RaiseException
0x180010f8c  jmp     loc_18001113D
0x180010f91  cmp     byte ptr [rdi], 0Fh
0x180010f94  mov     qword ptr [rsp+120h+var_E0], 0
0x180010f9d  jnz     short loc_180011014
0x180010f9f  test    [rdi], edx
0x180010fa1  jnz     short loc_180011014
0x180010fa3  mov     rax, [rdi+8]
0x180010fa7  mov     rcx, [rax+18h]
0x180010fab  test    rcx, rcx
0x180010fae  jz      short loc_180011003
0x180010fb0  mov     rax, [rcx]
0x180010fb3  test    rax, rax
0x180010fb6  jz      short loc_180011003
0x180010fb8  mov     rax, [rax]
0x180010fbb  lea     rdx, [rsp+120h+var_E0]
0x180010fc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fc5  mov     ebx, eax
0x180010fc7  test    eax, eax
0x180010fc9  jnz     short loc_180011008
0x180010fcb  mov     rax, [rsi+8]
0x180010fcf  mov     rdx, [rax+10h]
0x180010fd3  mov     rax, qword ptr [rsp+120h+var_E0]
0x180010fd8  mov     rcx, [rdx+r14*8]
0x180010fdc  mov     [rdx+r14*8], rax
0x180010fe0  test    rcx, rcx
0x180010fe3  jz      loc_18001113D
0x180010fe9  mov     rax, [rcx]
0x180010fec  test    rax, rax
0x180010fef  jz      loc_18001113D
0x180010ff5  mov     rax, [rax+10h]
0x180010ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ffe  jmp     loc_18001113D
0x180011003  mov     ebx, 4
0x180011008  mov     ecx, ebx; int
0x18001100a  call    MI_ReportErrorDetails_ForMiResult
0x18001100f  jmp     loc_18001113D
0x180011014  xor     eax, eax
0x180011016  lea     rcx, [rbp+57h+var_D0]; void *
0x18001101a  xorps   xmm0, xmm0
0x18001101d  mov     [rbp+57h+var_30], rax
0x180011021  xor     edx, edx; Val
0x180011023  mov     [rsp+120h+var_EC], eax
0x180011027  movups  [rbp+57h+var_50], xmm0
0x18001102b  lea     r8d, [rax+78h]; Size
0x18001102f  mov     [rsp+120h+var_F0], eax
0x180011033  movups  [rbp+57h+var_40], xmm0
0x180011037  call    memset_0
0x18001103c  lea     r9, [rsp+120h+var_F0]
0x180011041  mov     rcx, rdi
0x180011044  lea     r8, [rsp+120h+var_EC]
0x180011049  lea     rdx, [rbp+57h+var_50]
0x18001104d  call    MintValue_GetMiValue
0x180011052  mov     r8d, [rsp+120h+var_F0]
0x180011057  lea     r9, [rbp+57h+var_D0]
0x18001105b  mov     edx, [rsp+120h+var_EC]
0x18001105f  lea     rcx, [rbp+57h+var_50]
0x180011063  shr     r8d, 1Dh
0x180011067  and     r8b, 1
0x18001106b  call    Box
0x180011070  mov     ebx, eax
0x180011072  test    eax, eax
0x180011074  jz      short loc_18001107A
0x180011076  mov     ecx, eax
0x180011078  jmp     short loc_18001100A
0x18001107a  mov     rcx, [rbp+57h+var_D0]
0x18001107e  test    rcx, rcx
0x180011081  jz      short loc_18001109C
0x180011083  mov     rax, [rcx]
0x180011086  test    rax, rax
0x180011089  jz      short loc_18001109C
0x18001108b  mov     rax, [rax]
0x18001108e  lea     rdx, [rsp+120h+var_E0]
0x180011093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011098  mov     ebx, eax
0x18001109a  jmp     short loc_1800110A1
0x18001109c  mov     ebx, 4
0x1800110a1  lea     rcx, [rbp+57h+var_D0]
0x1800110a5  call    BoxFree
0x1800110aa  test    ebx, ebx
0x1800110ac  jmp     loc_180010FC9
0x1800110b1  mov     rcx, [rdi+8]
0x1800110b5  mov     rcx, [rcx+10h]; Src
0x1800110b9  call    PoolTls_Tcsdup
0x1800110be  mov     r9, rax
0x1800110c1  test    rax, rax
0x1800110c4  jnz     short loc_1800110D0
0x1800110c6  lea     ebx, [rax+1Bh]
0x1800110c9  call    MI_ReportErrorDetails_OutOfMemory
0x1800110ce  jmp     short loc_18001113D
0x1800110d0  mov     rax, [rsi+8]
0x1800110d4  mov     rdx, [rax+10h]
0x1800110d8  mov     rcx, [rdx+r14*8]
0x1800110dc  mov     [rdx+r14*8], r9
0x1800110e0  call    PoolTls_Free
0x1800110e5  jmp     short loc_18001113D
0x1800110e7  mov     r8, [rdi+8]
0x1800110eb  lea     rdx, [r14+r14*8]
0x1800110ef  mov     rax, [rsi+8]
0x1800110f3  movups  xmm0, xmmword ptr [r8+10h]
0x1800110f8  mov     rcx, [rax+10h]
0x1800110fc  movups  xmmword ptr [rcx+rdx*4], xmm0
0x180011100  movups  xmm1, xmmword ptr [r8+20h]
0x180011105  movups  xmmword ptr [rcx+rdx*4+10h], xmm1
0x18001110a  mov     eax, [r8+30h]
0x18001110e  mov     [rcx+rdx*4+20h], eax
0x180011112  jmp     short loc_18001113D
0x180011114  movsd   xmm0, qword ptr [rdi+8]
0x180011119  mov     rax, [rsi+8]
0x18001111d  cvtpd2ps xmm0, xmm0
0x180011121  mov     rax, [rax+10h]
0x180011125  movss   dword ptr [rax+r14*4], xmm0
0x18001112b  jmp     short loc_18001113D
0x18001112d  mov     rax, [rsi+8]
0x180011131  mov     rcx, [rax+10h]
0x180011135  mov     rax, [rdi+8]
0x180011139  mov     [rcx+r14*8], rax
0x18001113d  mov     eax, ebx
0x18001113f  mov     rcx, [rbp+57h+var_28]
0x180011143  xor     rcx, rsp; StackCookie
0x180011146  call    __security_check_cookie
0x18001114b  add     rsp, 100h
0x180011152  pop     r14
0x180011154  pop     rdi
0x180011155  pop     rsi
0x180011156  pop     rbx
0x180011157  pop     rbp
0x180011158  retn
```
