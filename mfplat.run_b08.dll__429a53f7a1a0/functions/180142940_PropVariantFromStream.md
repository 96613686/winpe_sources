# PropVariantFromStream

- ea: `0x180142940`
- end: `0x180142cb3`
- name: `PropVariantFromStream`
- size: `883`
- prototype: `__int64 __fastcall(__int64 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1801942e0`

## callees

- `0x18011fff0`
- `0x180120030`
- `0x180142940`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180142b13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180142b7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180142c10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180142c67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180142b13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180142b7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180142c10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180142c67`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180142a7c`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180142a7c`

## pseudocode

```c
__int64 __fastcall PropVariantFromStream(__int64 *a1, unsigned __int16 *a2)
{
  __int64 v4; // rax
  unsigned int v5; // edi
  unsigned int v6; // ebx
  unsigned int v7; // ecx
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  OLECHAR *v16; // rax
  OLECHAR *v17; // rdi
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  LPVOID v26; // rax
  LPVOID v27; // rax
  unsigned __int16 *v28; // rdx
  __int64 v29; // r8
  SIZE_T v30; // rcx
  unsigned __int16 *v31; // rax
  unsigned __int16 *v32; // rax
  SIZE_T cb; // [rsp+50h] [rbp+20h] BYREF

  if ( a1 && a2 )
  {
    v4 = *a1;
    LODWORD(cb) = 0;
    v5 = 2;
    v6 = (*(__int64 (__fastcall **)(__int64 *, unsigned __int16 *, __int64))(v4 + 24))(a1, a2, 2);
    if ( v6 )
      return v6;
    v7 = *a2;
    if ( v7 > 0x41 )
    {
      if ( v7 == 72 )
      {
        v32 = (unsigned __int16 *)CoTaskMemAlloc(0x10u);
        *((_QWORD *)a2 + 1) = v32;
        v28 = v32;
        if ( v32 )
        {
          v29 = 16;
          return (*(unsigned int (__fastcall **)(__int64 *, unsigned __int16 *, __int64, _QWORD))(*a1 + 24))(
                   a1,
                   v28,
                   v29,
                   0);
        }
        return (unsigned int)-2147024882;
      }
      if ( v7 != 4113 )
        return (unsigned int)-2147023266;
      v6 = (*(__int64 (__fastcall **)(__int64 *, SIZE_T *, __int64))(*a1 + 24))(a1, &cb, 4);
      if ( v6 )
        return v6;
    }
    else
    {
      if ( v7 != 65 )
      {
        if ( v7 <= 0x10 )
        {
          if ( v7 != 16 )
          {
            v8 = v7 - 2;
            if ( !v8 )
            {
LABEL_46:
              v28 = a2 + 4;
              v29 = v5;
              return (*(unsigned int (__fastcall **)(__int64 *, unsigned __int16 *, __int64, _QWORD))(*a1 + 24))(
                       a1,
                       v28,
                       v29,
                       0);
            }
            v9 = v8 - 1;
            if ( v9 )
            {
              v10 = v9 - 1;
              if ( v10 )
              {
                v11 = v10 - 1;
                if ( v11 )
                {
                  v12 = v11 - 1;
                  if ( v12 )
                  {
                    v13 = v12 - 1;
                    if ( v13 )
                    {
                      v14 = v13 - 1;
                      if ( v14 )
                      {
                        v15 = v14 - 2;
                        if ( v15 )
                        {
                          if ( v15 != 1 )
                            return (unsigned int)-2147023266;
                          goto LABEL_46;
                        }
                        goto LABEL_44;
                      }
                      v6 = (*(__int64 (__fastcall **)(__int64 *, SIZE_T *, __int64))(*a1 + 24))(a1, &cb, 4);
                      if ( !v6 )
                      {
                        if ( (cb & 1) != 0 )
                          return (unsigned int)-1072875845;
                        v16 = (OLECHAR *)operator new((unsigned int)cb);
                        v17 = v16;
                        if ( v16 )
                        {
                          v6 = (*(__int64 (__fastcall **)(__int64 *, OLECHAR *, _QWORD, _QWORD))(*a1 + 24))(
                                 a1,
                                 v16,
                                 (unsigned int)cb,
                                 0);
                          if ( !v6 )
                            *((_QWORD *)a2 + 1) = SysAllocStringLen(v17, (unsigned int)cb >> 1);
                          operator delete(v17);
                          return v6;
                        }
                        return (unsigned int)-2147024882;
                      }
                      return v6;
                    }
                  }
                }
                goto LABEL_26;
              }
            }
            goto LABEL_44;
          }
LABEL_45:
          v5 = 1;
          goto LABEL_46;
        }
        v18 = v7 - 17;
        if ( !v18 )
          goto LABEL_45;
        v19 = v18 - 1;
        if ( !v19 )
          goto LABEL_46;
        v20 = v19 - 1;
        if ( !v20 )
          goto LABEL_44;
        v21 = v20 - 1;
        if ( !v21 || (v22 = v21 - 1) == 0 )
        {
LABEL_26:
          v5 = 8;
          goto LABEL_46;
        }
        v23 = v22 - 1;
        if ( !v23 || (v24 = v23 - 1) == 0 )
        {
LABEL_44:
          v5 = 4;
          goto LABEL_46;
        }
        v25 = v24 - 7;
        if ( !v25 )
        {
          v6 = (*(__int64 (__fastcall **)(__int64 *, SIZE_T *, __int64))(*a1 + 24))(a1, &cb, 4);
          if ( v6 )
            return v6;
          v27 = CoTaskMemAlloc((unsigned int)cb);
          *((_QWORD *)a2 + 1) = v27;
          if ( v27 )
          {
            if ( (int)cb - 1 <= (unsigned int)cb )
            {
              v6 = (*(__int64 (__fastcall **)(__int64 *, LPVOID, _QWORD, _QWORD))(*a1 + 24))(
                     a1,
                     v27,
                     (unsigned int)cb,
                     0);
              *(_BYTE *)((unsigned int)(cb - 1) + *((_QWORD *)a2 + 1)) = 0;
              return v6;
            }
            return (unsigned int)-1072875845;
          }
          return (unsigned int)-2147024882;
        }
        if ( v25 == 1 )
        {
          v6 = (*(__int64 (__fastcall **)(__int64 *, SIZE_T *, __int64, _QWORD))(*a1 + 24))(a1, &cb, 4, 0);
          if ( v6 )
            return v6;
          if ( (cb & 1) != 0 )
            return (unsigned int)-1072875845;
          v26 = CoTaskMemAlloc((unsigned int)cb);
          *((_QWORD *)a2 + 1) = v26;
          if ( v26 )
          {
            v6 = (*(__int64 (__fastcall **)(__int64 *, LPVOID, _QWORD, _QWORD))(*a1 + 24))(a1, v26, (unsigned int)cb, 0);
            *(_WORD *)(*((_QWORD *)a2 + 1) + 2 * ((unsigned __int64)(unsigned int)cb >> 1) - 2) = 0;
            return v6;
          }
          return (unsigned int)-2147024882;
        }
        return (unsigned int)-2147023266;
      }
      v6 = (*(__int64 (__fastcall **)(__int64 *, SIZE_T *, __int64))(*a1 + 24))(a1, &cb, 4);
      if ( (v6 & 0x80000000) != 0 )
        return v6;
    }
    v30 = (unsigned int)cb;
    *((_DWORD *)a2 + 2) = cb;
    v31 = (unsigned __int16 *)CoTaskMemAlloc(v30);
    *((_QWORD *)a2 + 2) = v31;
    v28 = v31;
    if ( v31 )
    {
      v29 = (unsigned int)cb;
      return (*(unsigned int (__fastcall **)(__int64 *, unsigned __int16 *, __int64, _QWORD))(*a1 + 24))(
               a1,
               v28,
               v29,
               0);
    }
    return (unsigned int)-2147024882;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180142940  mov     [rsp-18h+arg_8], rbx
0x180142945  mov     [rsp-18h+arg_10], rsi
0x18014294a  push    rbp
0x18014294b  push    rdi
0x18014294c  push    r14
0x18014294e  mov     rbp, rsp
0x180142951  sub     rsp, 30h
0x180142955  mov     r14, rdx
0x180142958  mov     rsi, rcx
0x18014295b  test    rcx, rcx
0x18014295e  jz      loc_180142C9B
0x180142964  test    rdx, rdx
0x180142967  jz      loc_180142C9B
0x18014296d  mov     rax, [rcx]
0x180142970  xor     r9d, r9d
0x180142973  mov     dword ptr [rbp+cb], 0
0x18014297a  mov     rax, [rax+18h]
0x18014297e  lea     edi, [r9+2]
0x180142982  mov     r8d, edi
0x180142985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014298a  mov     ebx, eax
0x18014298c  test    eax, eax
0x18014298e  jnz     loc_180142C97
0x180142994  movzx   ecx, word ptr [r14]
0x180142998  cmp     ecx, 41h ; 'A'
0x18014299b  ja      loc_180142C2C
0x1801429a1  jz      loc_180142BE3
0x1801429a7  cmp     ecx, 10h
0x1801429aa  ja      loc_180142A9D
0x1801429b0  jz      loc_180142BD2
0x1801429b6  sub     ecx, edi
0x1801429b8  jz      loc_180142BD7
0x1801429be  sub     ecx, 1
0x1801429c1  jz      loc_180142BCB
0x1801429c7  sub     ecx, 1
0x1801429ca  jz      loc_180142BCB
0x1801429d0  sub     ecx, 1
0x1801429d3  jz      loc_180142A93
0x1801429d9  sub     ecx, 1
0x1801429dc  jz      loc_180142A93
0x1801429e2  sub     ecx, 1
0x1801429e5  jz      loc_180142A93
0x1801429eb  sub     ecx, 1
0x1801429ee  jz      short loc_180142A06
0x1801429f0  sub     ecx, edi
0x1801429f2  jz      loc_180142BCB
0x1801429f8  cmp     ecx, 1
0x1801429fb  jz      loc_180142BD7
0x180142a01  jmp     loc_180142C39
0x180142a06  mov     rax, [rsi]
0x180142a09  lea     rdx, [rbp+cb]
0x180142a0d  xor     r9d, r9d
0x180142a10  mov     rcx, rsi
0x180142a13  mov     rax, [rax+18h]
0x180142a17  lea     r8d, [r9+4]
0x180142a1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180142a20  mov     ebx, eax
0x180142a22  test    eax, eax
0x180142a24  jnz     loc_180142C97
0x180142a2a  mov     eax, dword ptr [rbp+cb]
0x180142a2d  test    al, 1
0x180142a2f  jz      short loc_180142A3B
0x180142a31  mov     ebx, 0C00D36BBh
0x180142a36  jmp     loc_180142C97
0x180142a3b  mov     ecx, dword ptr [rbp+cb]; Size
0x180142a3e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180142a43  mov     rdi, rax
0x180142a46  test    rax, rax
0x180142a49  jnz     short loc_180142A55
0x180142a4b  mov     ebx, 8007000Eh
0x180142a50  jmp     loc_180142C97
0x180142a55  mov     rax, [rsi]
0x180142a58  xor     r9d, r9d
0x180142a5b  mov     r8d, dword ptr [rbp+cb]
0x180142a5f  mov     rdx, rdi
0x180142a62  mov     rcx, rsi
0x180142a65  mov     rax, [rax+18h]
0x180142a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180142a6e  mov     ebx, eax
0x180142a70  test    eax, eax
0x180142a72  jnz     short loc_180142A86
0x180142a74  mov     edx, dword ptr [rbp+cb]
0x180142a77  mov     rcx, rdi; strIn
0x180142a7a  shr     edx, 1; ui
0x180142a7c  call    cs:__imp_SysAllocStringLen
0x180142a82  mov     [r14+8], rax
0x180142a86  mov     rcx, rdi; void *
0x180142a89  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180142a8e  jmp     loc_180142C97
0x180142a93  mov     edi, 8
0x180142a98  jmp     loc_180142BD7
0x180142a9d  sub     ecx, 11h
0x180142aa0  jz      loc_180142BD2
0x180142aa6  sub     ecx, 1
0x180142aa9  jz      loc_180142BD7
0x180142aaf  sub     ecx, 1
0x180142ab2  jz      loc_180142BCB
0x180142ab8  sub     ecx, 1
0x180142abb  jz      short loc_180142A93
0x180142abd  sub     ecx, 1
0x180142ac0  jz      short loc_180142A93
0x180142ac2  sub     ecx, 1
0x180142ac5  jz      loc_180142BCB
0x180142acb  sub     ecx, 1
0x180142ace  jz      loc_180142BCB
0x180142ad4  sub     ecx, 7
0x180142ad7  jz      short loc_180142B57
0x180142ad9  cmp     ecx, 1
0x180142adc  jnz     loc_180142C39
0x180142ae2  mov     rax, [rsi]
0x180142ae5  lea     r8d, [rcx+3]
0x180142ae9  xor     r9d, r9d
0x180142aec  lea     rdx, [rbp+cb]
0x180142af0  mov     rcx, rsi
0x180142af3  mov     rax, [rax+18h]
0x180142af7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180142afc  mov     ebx, eax
0x180142afe  test    eax, eax
0x180142b00  jnz     loc_180142C97
0x180142b06  mov     eax, dword ptr [rbp+cb]
0x180142b09  test    al, 1
0x180142b0b  jnz     loc_180142A31
0x180142b11  mov     ecx, eax; cb
0x180142b13  call    cs:__imp_CoTaskMemAlloc
0x180142b19  mov     [r14+8], rax
0x180142b1d  mov     rdx, rax
0x180142b20  test    rax, rax
0x180142b23  jz      loc_180142A4B
0x180142b29  mov     rax, [rsi]
0x180142b2c  xor     r9d, r9d
0x180142b2f  mov     r8d, dword ptr [rbp+cb]
0x180142b33  mov     rcx, rsi
0x180142b36  mov     rax, [rax+18h]
0x180142b3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180142b3f  mov     edx, dword ptr [rbp+cb]
0x180142b42  mov     ebx, eax
0x180142b44  mov     rcx, [r14+8]
0x180142b48  shr     rdx, 1
0x180142b4b  xor     eax, eax
0x180142b4d  mov     [rcx+rdx*2-2], ax
0x180142b52  jmp     loc_180142C97
0x180142b57  mov     rax, [rsi]
0x180142b5a  lea     rdx, [rbp+cb]
0x180142b5e  xor     r9d, r9d
0x180142b61  mov     rcx, rsi
0x180142b64  mov     rax, [rax+18h]
0x180142b68  lea     r8d, [r9+4]
0x180142b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180142b71  mov     ebx, eax
0x180142b73  test    eax, eax
0x180142b75  jnz     loc_180142C97
0x180142b7b  mov     ecx, dword ptr [rbp+cb]; cb
0x180142b7e  call    cs:__imp_CoTaskMemAlloc
0x180142b84  mov     [r14+8], rax
0x180142b88  mov     rdx, rax
0x180142b8b  test    rax, rax
0x180142b8e  jz      loc_180142A4B
0x180142b94  mov     r8d, dword ptr [rbp+cb]
0x180142b98  lea     eax, [r8-1]
0x180142b9c  cmp     eax, r8d
0x180142b9f  ja      loc_180142A31
0x180142ba5  mov     rax, [rsi]
0x180142ba8  xor     r9d, r9d
0x180142bab  mov     rcx, rsi
0x180142bae  mov     rax, [rax+18h]
0x180142bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180142bb7  mov     ecx, dword ptr [rbp+cb]
0x180142bba  mov     ebx, eax
0x180142bbc  mov     rax, [r14+8]
0x180142bc0  dec     ecx
0x180142bc2  mov     byte ptr [rcx+rax], 0
0x180142bc6  jmp     loc_180142C97
0x180142bcb  mov     edi, 4
0x180142bd0  jmp     short loc_180142BD7
0x180142bd2  mov     edi, 1
0x180142bd7  lea     rdx, [r14+8]
0x180142bdb  mov     r8d, edi
0x180142bde  jmp     loc_180142C83
0x180142be3  mov     rax, [rsi]
0x180142be6  lea     rdx, [rbp+cb]
0x180142bea  xor     r9d, r9d
0x180142bed  mov     rcx, rsi
0x180142bf0  mov     rax, [rax+18h]
0x180142bf4  lea     r8d, [r9+4]
0x180142bf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180142bfd  mov     ebx, eax
0x180142bff  test    eax, eax
0x180142c01  js      loc_180142C97
0x180142c07  mov     eax, dword ptr [rbp+cb]
0x180142c0a  mov     ecx, eax; cb
0x180142c0c  mov     [r14+8], eax
0x180142c10  call    cs:__imp_CoTaskMemAlloc
0x180142c16  mov     [r14+10h], rax
0x180142c1a  mov     rdx, rax
0x180142c1d  test    rax, rax
0x180142c20  jz      loc_180142A4B
0x180142c26  mov     r8d, dword ptr [rbp+cb]
0x180142c2a  jmp     short loc_180142C83
0x180142c2c  cmp     ecx, 48h ; 'H'
0x180142c2f  jz      short loc_180142C62
0x180142c31  cmp     ecx, 1011h
0x180142c37  jz      short loc_180142C40
0x180142c39  mov     ebx, 8007065Eh
0x180142c3e  jmp     short loc_180142C97
0x180142c40  mov     rax, [rsi]
0x180142c43  lea     rdx, [rbp+cb]
0x180142c47  xor     r9d, r9d
0x180142c4a  mov     rcx, rsi
0x180142c4d  mov     rax, [rax+18h]
0x180142c51  lea     r8d, [r9+4]
0x180142c55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180142c5a  mov     ebx, eax
0x180142c5c  test    eax, eax
0x180142c5e  jnz     short loc_180142C97
0x180142c60  jmp     short loc_180142C07
0x180142c62  mov     ecx, 10h; cb
0x180142c67  call    cs:__imp_CoTaskMemAlloc
0x180142c6d  mov     [r14+8], rax
0x180142c71  mov     rdx, rax
0x180142c74  test    rax, rax
0x180142c77  jz      loc_180142A4B
0x180142c7d  mov     r8d, 10h
0x180142c83  mov     rax, [rsi]
0x180142c86  xor     r9d, r9d
0x180142c89  mov     rcx, rsi
0x180142c8c  mov     rax, [rax+18h]
0x180142c90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180142c95  mov     ebx, eax
0x180142c97  mov     eax, ebx
0x180142c99  jmp     short loc_180142CA0
0x180142c9b  mov     eax, 80070057h
0x180142ca0  mov     rbx, [rsp+30h+arg_8]
0x180142ca5  mov     rsi, [rsp+30h+arg_10]
0x180142caa  add     rsp, 30h
0x180142cae  pop     r14
0x180142cb0  pop     rdi
0x180142cb1  pop     rbp
0x180142cb2  retn
```
