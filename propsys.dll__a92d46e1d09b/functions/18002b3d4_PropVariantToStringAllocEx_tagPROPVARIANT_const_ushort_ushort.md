# _PropVariantToStringAllocEx(tagPROPVARIANT const &,ushort,ushort * *)

- ea: `0x18002b3d4`
- end: `0x18002b6be`
- name: `?_PropVariantToStringAllocEx@@YAJAEBUtagPROPVARIANT@@GPEAPEAG@Z`
- size: `746`
- prototype: `__int64 __fastcall(PROPVARIANT *propvarSrc, unsigned __int16, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002b3c0`
- `0x18008ed10`

## callees

- `0x180015170`
- `0x1800272f8`
- `0x18002a824`
- `0x18002b3d4`
- `0x18002b6c4`
- `0x18002d070`
- `0x1800344e8`
- `0x1800477f8`
- `0x180065b84`
- `0x18006ed20`
- `0x18006fb98`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b68c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b68c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b4f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b4f4`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b611`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b611`
- `OLEAUT32!__imp_VariantClear` at `0x18002b697`
- `OLEAUT32!__imp_VariantClear` at `0x18002b697`

## pseudocode

```c
__int64 __fastcall _PropVariantToStringAllocEx(PROPVARIANT *propvarSrc, __int64 a2, unsigned __int16 **a3)
{
  unsigned __int16 v4; // bp
  __int64 v6; // rcx
  unsigned __int16 *v7; // r15
  unsigned __int64 v8; // rsi
  unsigned __int64 v9; // rdi
  HRESULT v10; // ebx
  int v11; // r8d
  HRESULT v13; // eax
  __int64 v14; // rax
  unsigned __int16 *v15; // rdx
  unsigned __int64 v16; // r8
  __int64 v17; // rcx
  __int64 v18; // r9
  __int64 v19; // rdi
  bool v20; // cf
  const unsigned __int16 *v21; // rcx
  unsigned __int16 *v22; // rax
  LPVOID pv; // [rsp+30h] [rbp-68h] BYREF
  VARIANT pVar; // [rsp+38h] [rbp-60h] BYREF

  *a3 = 0;
  v4 = a2;
  if ( (*(_WORD *)propvarSrc & 0x1000) != 0 )
  {
    v13 = _PropVariantVectorToStringAlloc(propvarSrc, a2, a3);
    goto LABEL_16;
  }
  if ( (*(_WORD *)propvarSrc & 0x2000) == 0 )
  {
    v6 = *(unsigned __int16 *)propvarSrc;
    if ( (_DWORD)v6 && (v6 = (unsigned int)(v6 - 1), (_DWORD)v6) )
    {
      LODWORD(v6) = v6 - 7;
      if ( (_DWORD)v6 )
      {
        if ( (_DWORD)v6 == 23 )
        {
          v7 = (unsigned __int16 *)propvarSrc[1];
          if ( !v7 )
          {
            v10 = -2147024809;
            goto LABEL_13;
          }
          if ( (_WORD)a2 == 31 )
          {
            v8 = -1;
            do
              ++v8;
            while ( v7[v8] );
            v9 = v8 + 1;
            if ( v8 + 1 < v8 || !is_mul_ok(v9, 2u) )
            {
              v10 = -2147024362;
              goto LABEL_13;
            }
            v14 = (__int64)CoTaskMemAlloc(2 * v9);
            *a3 = (unsigned __int16 *)v14;
            v6 = -v14;
            v15 = (unsigned __int16 *)v14;
            v10 = v14 == 0 ? 0x8007000E : 0;
            if ( !v14 )
              goto LABEL_13;
            if ( v9 <= 0x7FFFFFFF )
            {
              if ( v8 < 0x7FFFFFFF )
              {
                v16 = v8 + 1;
                v17 = 0;
                do
                {
                  if ( !v8 )
                    break;
                  if ( !*v7 )
                    break;
                  *(_WORD *)v14 = *v7++;
                  v14 += 2;
                  --v8;
                  ++v17;
                  --v16;
                }
                while ( v16 );
                v18 = v17 - 1;
                if ( v16 )
                  v18 = v17;
                v6 = v14 - 2;
                if ( v16 )
                  v6 = v14;
                *(_WORD *)v6 = 0;
                if ( v16 )
                {
                  v20 = v9 == v18;
                  v19 = v9 - v18;
                  if ( !v20 && v19 != 1 && (unsigned __int64)(2 * v19) > 2 )
                    memset_0(&v15[v18 + 1], 0, 2 * v19 - 2);
                }
                goto LABEL_13;
              }
              if ( v8 == -1 )
                goto LABEL_13;
            }
            *(_WORD *)v14 = 0;
            goto LABEL_13;
          }
          v13 = SHSysAllocString((const unsigned __int16 *)propvarSrc[1], a3);
        }
        else
        {
          v13 = _PropVariantToStringAllocExHelper(propvarSrc, a2, a3);
        }
      }
      else
      {
        v21 = &Src;
        if ( propvarSrc[1] )
          v21 = (const unsigned __int16 *)propvarSrc[1];
        v13 = _AllocStringAs(v21, a2, a3);
      }
    }
    else
    {
      if ( (_WORD)a2 != 31 )
      {
        v22 = SysAllocString(&Src);
        *a3 = v22;
        v10 = v22 == 0 ? 0x8007000E : 0;
        goto LABEL_13;
      }
      v13 = _AllocString<CTCoAllocPolicy>(v6, a2, &Src, a3);
    }
LABEL_16:
    v10 = v13;
    goto LABEL_13;
  }
  memset(&pVar, 0, sizeof(pVar));
  v10 = PropVariantToVariant(propvarSrc, &pVar);
  if ( v10 >= 0 )
  {
    pv = 0;
    v10 = _VariantArrayToStringAlloc(&pVar, (unsigned __int16 **)&pv);
    if ( v10 >= 0 )
    {
      if ( v4 == 31 )
      {
        *a3 = (unsigned __int16 *)pv;
      }
      else
      {
        v10 = SHSysAllocString((const unsigned __int16 *)pv, a3);
        CoTaskMemFree(pv);
      }
    }
    VariantClear(&pVar);
  }
LABEL_13:
  v11 = *(unsigned __int16 *)propvarSrc;
  if ( (_WORD)v11 != 31 && (_WORD)v11 && (byte_1800F1382 & 0x10) != 0 )
    McTemplateU0hhq_EtwEventWriteTransfer(
      v6,
      (unsigned int)ShellTraceId_Properties_PropVariantHelper_Coercion_Info,
      v11,
      v4,
      v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002b3d4  mov     [rsp+arg_18], rbx
0x18002b3d9  push    rbp
0x18002b3da  push    rsi
0x18002b3db  push    rdi
0x18002b3dc  push    r12
0x18002b3de  push    r13
0x18002b3e0  push    r14
0x18002b3e2  push    r15
0x18002b3e4  sub     rsp, 60h
0x18002b3e8  mov     rax, cs:__security_cookie
0x18002b3ef  xor     rax, rsp
0x18002b3f2  mov     [rsp+98h+var_48], rax
0x18002b3f7  xor     r13d, r13d
0x18002b3fa  mov     eax, 1000h
0x18002b3ff  mov     [r8], r13
0x18002b402  mov     r14, r8
0x18002b405  movzx   ebp, dx
0x18002b408  mov     r12, rcx
0x18002b40b  lea     edi, [r13+1Fh]
0x18002b40f  test    [rcx], ax
0x18002b412  jnz     loc_18002B4B6
0x18002b418  mov     eax, 2000h
0x18002b41d  test    [rcx], ax
0x18002b420  jnz     loc_18002B62C
0x18002b426  movzx   ecx, word ptr [rcx]
0x18002b429  test    ecx, ecx
0x18002b42b  jz      loc_18002B5B8
0x18002b431  sub     ecx, 1
0x18002b434  jz      loc_18002B5B8
0x18002b43a  sub     ecx, 7
0x18002b43d  jz      loc_18002B5EE
0x18002b443  cmp     ecx, 17h
0x18002b446  jnz     loc_18002B5D1
0x18002b44c  mov     r15, [r12+8]
0x18002b451  test    r15, r15
0x18002b454  jz      loc_18002B6B4
0x18002b45a  cmp     di, dx
0x18002b45d  jnz     loc_18002B5DE
0x18002b463  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002b467  inc     rsi
0x18002b46a  cmp     [r15+rsi*2], r13w
0x18002b46f  jnz     short loc_18002B467
0x18002b471  lea     rdi, [rsi+1]
0x18002b475  cmp     rdi, rsi
0x18002b478  jnb     short loc_18002B4E4
0x18002b47a  mov     ebx, 80070216h
0x18002b47f  mov     edi, 1Fh
0x18002b484  movzx   r8d, word ptr [r12]
0x18002b489  cmp     r8w, di
0x18002b48d  jnz     short loc_18002B4BF
0x18002b48f  mov     eax, ebx
0x18002b491  mov     rcx, [rsp+98h+var_48]
0x18002b496  xor     rcx, rsp; StackCookie
0x18002b499  call    __security_check_cookie
0x18002b49e  mov     rbx, [rsp+98h+arg_18]
0x18002b4a6  add     rsp, 60h
0x18002b4aa  pop     r15
0x18002b4ac  pop     r14
0x18002b4ae  pop     r13
0x18002b4b0  pop     r12
0x18002b4b2  pop     rdi
0x18002b4b3  pop     rsi
0x18002b4b4  pop     rbp
0x18002b4b5  retn
0x18002b4b6  call    ?_PropVariantVectorToStringAlloc@@YAJAEBUtagPROPVARIANT@@GPEAPEAG@Z; _PropVariantVectorToStringAlloc(tagPROPVARIANT const &,ushort,ushort * *)
0x18002b4bb  mov     ebx, eax
0x18002b4bd  jmp     short loc_18002B484
0x18002b4bf  test    r8w, r8w
0x18002b4c3  jz      short loc_18002B48F
0x18002b4c5  test    cs:byte_1800F1382, 10h
0x18002b4cc  jz      short loc_18002B48F
0x18002b4ce  movzx   r9d, bp
0x18002b4d2  mov     [rsp+98h+var_78], ebx
0x18002b4d6  lea     rdx, ShellTraceId_Properties_PropVariantHelper_Coercion_Info
0x18002b4dd  call    McTemplateU0hhq_EtwEventWriteTransfer
0x18002b4e2  jmp     short loc_18002B48F
0x18002b4e4  mov     eax, 2
0x18002b4e9  mul     rdi
0x18002b4ec  test    rdx, rdx
0x18002b4ef  jnz     short loc_18002B47A
0x18002b4f1  mov     rcx, rax; cb
0x18002b4f4  call    cs:__imp_CoTaskMemAlloc
0x18002b4fa  mov     rcx, rax
0x18002b4fd  mov     [r14], rax
0x18002b500  neg     rcx
0x18002b503  mov     rdx, rax
0x18002b506  sbb     ebx, ebx
0x18002b508  not     ebx
0x18002b50a  and     ebx, 8007000Eh
0x18002b510  test    rax, rax
0x18002b513  jz      loc_18002B47F
0x18002b519  mov     eax, 7FFFFFFFh
0x18002b51e  cmp     rdi, rax
0x18002b521  ja      loc_18002B6AB
0x18002b527  cmp     rsi, rax
0x18002b52a  jnb     loc_18002B6A2
0x18002b530  test    rdi, rdi
0x18002b533  jz      loc_18002B47F
0x18002b539  mov     r8, rdi
0x18002b53c  mov     rax, rdx
0x18002b53f  mov     rcx, r13
0x18002b542  test    rsi, rsi
0x18002b545  jz      short loc_18002B569
0x18002b547  movzx   r9d, word ptr [r15]
0x18002b54b  test    r9w, r9w
0x18002b54f  jz      short loc_18002B569
0x18002b551  mov     [rax], r9w
0x18002b555  add     r15, 2
0x18002b559  add     rax, 2
0x18002b55d  dec     rsi
0x18002b560  inc     rcx
0x18002b563  sub     r8, 1
0x18002b567  jnz     short loc_18002B542
0x18002b569  lea     r9, [rcx-1]
0x18002b56d  test    r8, r8
0x18002b570  cmovnz  r9, rcx
0x18002b574  lea     rcx, [rax-2]
0x18002b578  cmovnz  rcx, rax
0x18002b57c  mov     [rcx], r13w
0x18002b580  jz      loc_18002B47F
0x18002b586  sub     rdi, r9
0x18002b589  cmp     rdi, 1
0x18002b58d  jbe     loc_18002B47F
0x18002b593  lea     r8, [rdi+rdi]
0x18002b597  cmp     r8, 2
0x18002b59b  jbe     loc_18002B47F
0x18002b5a1  inc     r9
0x18002b5a4  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18002b5a8  lea     rcx, [rdx+r9*2]; void *
0x18002b5ac  xor     edx, edx; Val
0x18002b5ae  call    memset_0
0x18002b5b3  jmp     loc_18002B47F
0x18002b5b8  cmp     di, bp
0x18002b5bb  jnz     short loc_18002B60A
0x18002b5bd  mov     r9, r14
0x18002b5c0  lea     r8, Src
0x18002b5c7  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18002b5cc  jmp     loc_18002B4BB
0x18002b5d1  mov     rcx, r12; propvarSrc
0x18002b5d4  call    ?_PropVariantToStringAllocExHelper@@YAJAEBUtagPROPVARIANT@@GPEAPEAG@Z; _PropVariantToStringAllocExHelper(tagPROPVARIANT const &,ushort,ushort * *)
0x18002b5d9  jmp     loc_18002B4BB
0x18002b5de  mov     rdx, r14; unsigned __int16 **
0x18002b5e1  mov     rcx, r15; unsigned __int16 *
0x18002b5e4  call    ?SHSysAllocString@@YAJPEBGPEAPEAG@Z; SHSysAllocString(ushort const *,ushort * *)
0x18002b5e9  jmp     loc_18002B4BB
0x18002b5ee  cmp     [r12+8], r13
0x18002b5f3  lea     rcx, Src
0x18002b5fa  cmovnz  rcx, [r12+8]; unsigned __int16 *
0x18002b600  call    ?_AllocStringAs@@YAJPEBGGPEAPEAG@Z; _AllocStringAs(ushort const *,ushort,ushort * *)
0x18002b605  jmp     loc_18002B4BB
0x18002b60a  lea     rcx, Src; psz
0x18002b611  call    cs:__imp_SysAllocString
0x18002b617  mov     [r14], rax
0x18002b61a  neg     rax
0x18002b61d  sbb     ebx, ebx
0x18002b61f  not     ebx
0x18002b621  and     ebx, 8007000Eh
0x18002b627  jmp     loc_18002B484
0x18002b62c  xorps   xmm0, xmm0
0x18002b62f  lea     rdx, [rsp+98h+pVar]; pVar
0x18002b634  xor     eax, eax
0x18002b636  movups  xmmword ptr [rsp+98h+pVar], xmm0
0x18002b63b  mov     qword ptr [rsp+98h+pVar+10h], rax
0x18002b640  call    PropVariantToVariant
0x18002b645  mov     ebx, eax
0x18002b647  test    eax, eax
0x18002b649  js      loc_18002B484
0x18002b64f  lea     rdx, [rsp+98h+pv]; unsigned __int16 **
0x18002b654  mov     [rsp+98h+pv], r13
0x18002b659  lea     rcx, [rsp+98h+pVar]; varIn
0x18002b65e  call    ?_VariantArrayToStringAlloc@@YAJAEBUtagVARIANT@@PEAPEAG@Z; _VariantArrayToStringAlloc(tagVARIANT const &,ushort * *)
0x18002b663  mov     ebx, eax
0x18002b665  test    eax, eax
0x18002b667  js      short loc_18002B692
0x18002b669  cmp     di, bp
0x18002b66c  jnz     short loc_18002B678
0x18002b66e  mov     rax, [rsp+98h+pv]
0x18002b673  mov     [r14], rax
0x18002b676  jmp     short loc_18002B692
0x18002b678  mov     rcx, [rsp+98h+pv]; unsigned __int16 *
0x18002b67d  mov     rdx, r14; unsigned __int16 **
0x18002b680  call    ?SHSysAllocString@@YAJPEBGPEAPEAG@Z; SHSysAllocString(ushort const *,ushort * *)
0x18002b685  mov     rcx, [rsp+98h+pv]; pv
0x18002b68a  mov     ebx, eax
0x18002b68c  call    cs:__imp_CoTaskMemFree
0x18002b692  lea     rcx, [rsp+98h+pVar]; pvarg
0x18002b697  call    cs:__imp_VariantClear
0x18002b69d  jmp     loc_18002B484
0x18002b6a2  test    rdi, rdi
0x18002b6a5  jz      loc_18002B47F
0x18002b6ab  mov     [rdx], r13w
0x18002b6af  jmp     loc_18002B47F
0x18002b6b4  mov     ebx, 80070057h
0x18002b6b9  jmp     loc_18002B484
```
