# sfac_GetSbitComponentInfo(sfac_ClientRec const *,ushort,uint,uint,ushort *,ushort *,ushort *)

- ea: `0x140026c04`
- end: `0x140026d59`
- name: `?sfac_GetSbitComponentInfo@@YAHPEBUsfac_ClientRec@@GIIPEAG11@Z`
- size: `341`
- prototype: `__int64 __fastcall(const struct sfac_ClientRec *, unsigned __int16, unsigned int, unsigned int, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140027870`

## callees

- `0x140013240`
- `0x140026c04`
- `0x140072578`
- `0x140098010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall sfac_GetSbitComponentInfo(
        const struct sfac_ClientRec *a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7)
{
  unsigned __int64 v7; // rbx
  __int64 v8; // rbp
  __int64 v10; // rdi
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  unsigned __int64 v14; // rbx
  __int64 v16; // [rsp+30h] [rbp-58h] BYREF
  __int64 v17; // [rsp+38h] [rbp-50h] BYREF
  char v18[8]; // [rsp+40h] [rbp-48h] BYREF
  const struct sfac_ClientRec *v19; // [rsp+48h] [rbp-40h]
  __int64 v20; // [rsp+50h] [rbp-38h]

  v8 = (unsigned __int16)a2;
  v10 = 0;
  v16 = 0;
  if ( a4 && *((_DWORD *)a1 + 41) )
  {
    if ( a4 > 0x7FFFFFFF || (a2 = a3 + *((_DWORD *)a1 + 40), (unsigned int)a2 > 0x7FFFFFFF) || (unsigned int)a2 < a3 )
    {
      SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(0x7FFFFFFF, a2);
      goto LABEL_17;
    }
    v11 = (*((__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64 *))a1 + 1))(*(_QWORD *)a1, a2, a4, &v16);
    v10 = v16;
    if ( v11 )
      LODWORD(v7) = 0;
    else
      LODWORD(v7) = 5128;
  }
  else
  {
    v11 = 0;
    LODWORD(v7) = 5129;
  }
  v19 = a1;
  v20 = v10;
  if ( !(_DWORD)v7 )
  {
    v7 = v11 + 2;
    v17 = 4 * v8;
    v13 = *(_QWORD *)SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(
                       &v17,
                       v18,
                       1);
    if ( v13 >= 0 )
    {
      if ( v13 + v7 >= v7 )
      {
        v14 = v13 + v7;
LABEL_13:
        *a5 = _byteswap_ushort(*(_WORD *)v14);
        *a6 = *(unsigned __int8 *)(v14 + 2);
        *a7 = *(unsigned __int8 *)(v14 + 3);
        if ( v10 )
          (*((void (__fastcall **)(__int64))a1 + 2))(v10);
        return 0;
      }
LABEL_18:
      SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(v13, v12);
      goto LABEL_19;
    }
LABEL_17:
    v13 = -v13;
    if ( v13 <= v7 )
    {
      v14 = v7 - v13;
      goto LABEL_13;
    }
    goto LABEL_18;
  }
LABEL_19:
  if ( v10 )
    (*((void (__fastcall **)(__int64))a1 + 2))(v10);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140026c04  push    rbx
0x140026c06  push    rbp
0x140026c07  push    rsi
0x140026c08  push    rdi
0x140026c09  sub     rsp, 68h
0x140026c0d  mov     r10d, r9d
0x140026c10  movzx   ebp, dx
0x140026c13  mov     rsi, rcx
0x140026c16  xor     edi, edi
0x140026c18  mov     [rsp+88h+var_58], rdi
0x140026c1d  test    r9d, r9d
0x140026c20  jz      short loc_140026C2A
0x140026c22  cmp     [rcx+0A4h], edi
0x140026c28  ja      short loc_140026C33
0x140026c2a  xor     eax, eax
0x140026c2c  mov     ebx, 1409h
0x140026c31  jmp     short loc_140026C7F
0x140026c33  mov     ecx, 7FFFFFFFh
0x140026c38  cmp     r10d, ecx
0x140026c3b  ja      loc_140026D0E
0x140026c41  mov     edx, [rsi+0A0h]
0x140026c47  add     edx, r8d
0x140026c4a  cmp     edx, ecx
0x140026c4c  ja      loc_140026D0E
0x140026c52  cmp     edx, r8d
0x140026c55  jb      loc_140026D0E
0x140026c5b  lea     r9, [rsp+88h+var_58]
0x140026c60  mov     r8d, r10d
0x140026c63  mov     rcx, [rsi]
0x140026c66  mov     rax, [rsi+8]
0x140026c6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026c6f  mov     rdi, [rsp+88h+var_58]
0x140026c74  test    rax, rax
0x140026c77  jz      loc_140026D2B
0x140026c7d  xor     ebx, ebx
0x140026c7f  mov     [rsp+88h+var_40], rsi
0x140026c84  mov     [rsp+88h+var_38], rdi
0x140026c89  test    ebx, ebx
0x140026c8b  jnz     loc_140026D22
0x140026c91  lea     rbx, [rax+2]
0x140026c95  shl     rbp, 2
0x140026c99  mov     [rsp+88h+var_50], rbp
0x140026c9e  mov     r8d, 1
0x140026ca4  lea     rdx, [rsp+88h+var_48]
0x140026ca9  lea     rcx, [rsp+88h+var_50]
0x140026cae  call    ??$?D_K@?$SafeInt@_JV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@QEBA?AV0@_K@Z; SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(unsigned __int64)
0x140026cb3  mov     rcx, [rax]
0x140026cb6  test    rcx, rcx
0x140026cb9  js      short loc_140026D14
0x140026cbb  lea     rax, [rcx+rbx]
0x140026cbf  cmp     rax, rbx
0x140026cc2  jb      short loc_140026D1C
0x140026cc4  mov     rbx, rax
0x140026cc7  movzx   ecx, byte ptr [rbx]
0x140026cca  shl     cx, 8
0x140026cce  movzx   eax, byte ptr [rbx+1]
0x140026cd2  or      cx, ax
0x140026cd5  mov     rax, [rsp+88h+arg_20]
0x140026cdd  mov     [rax], cx
0x140026ce0  movzx   ecx, byte ptr [rbx+2]
0x140026ce4  mov     rax, [rsp+88h+arg_28]
0x140026cec  mov     [rax], cx
0x140026cef  movzx   ecx, byte ptr [rbx+3]
0x140026cf3  mov     rax, [rsp+88h+arg_30]
0x140026cfb  mov     [rax], cx
0x140026cfe  test    rdi, rdi
0x140026d01  jnz     short loc_140026D4B
0x140026d03  xor     eax, eax
0x140026d05  add     rsp, 68h
0x140026d09  pop     rdi
0x140026d0a  pop     rsi
0x140026d0b  pop     rbp
0x140026d0c  pop     rbx
0x140026d0d  retn
0x140026d0e  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@SAXXZ; SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(void)
0x140026d13  nop
0x140026d14  neg     rcx
0x140026d17  cmp     rcx, rbx
0x140026d1a  jbe     short loc_140026D43
0x140026d1c  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@SAXXZ; SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(void)
0x140026d21  nop
0x140026d22  test    rdi, rdi
0x140026d25  jnz     short loc_140026D35
0x140026d27  mov     eax, ebx
0x140026d29  jmp     short loc_140026D05
0x140026d2b  mov     ebx, 1408h
0x140026d30  jmp     loc_140026C7F
0x140026d35  mov     rcx, rdi
0x140026d38  mov     rax, [rsi+10h]
0x140026d3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026d41  jmp     short loc_140026D27
0x140026d43  sub     rbx, rcx
0x140026d46  jmp     loc_140026CC7
0x140026d4b  mov     rcx, rdi
0x140026d4e  mov     rax, [rsi+10h]
0x140026d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026d57  jmp     short loc_140026D03
```
