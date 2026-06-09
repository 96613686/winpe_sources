# TMetaInferrence::InferDatabaseMeta(void)

- ea: `0x18001e9d4`
- end: `0x18001ec6b`
- name: `?InferDatabaseMeta@TMetaInferrence@@AEAAXXZ`
- size: `663`
- prototype: `void __fastcall(TMetaInferrence *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001e000`

## callees

- `0x180017ad8`
- `0x18001e9d4`
- `0x180020c1c`
- `0x180030010`

## string_xrefs

- `0x18001ebca`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001ec1b`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x18001ec51`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`

## pseudocode

```c
void __fastcall TMetaInferrence::InferDatabaseMeta(TMetaInferrence *this)
{
  unsigned int i; // r14d
  unsigned int *v3; // rsi
  const unsigned __int16 *v4; // rax
  __int64 v5; // rax
  unsigned __int64 v6; // rcx
  const unsigned __int16 *v7; // rax
  unsigned int j; // ebx
  unsigned int v9; // edi
  unsigned int v10; // ebx
  _DWORD *v11; // rax
  unsigned int v12; // ecx
  void (***v13)(_QWORD, const wchar_t *, ...); // rdi
  void (*v14)(_QWORD, const wchar_t *, ...); // rbx
  __int64 v15; // rax
  void (***v16)(_QWORD, const wchar_t *, ...); // rdi
  void (*v17)(_QWORD, const wchar_t *, ...); // rbx
  __int64 v18; // rax

  for ( i = 0; i < (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 272LL))(*((_QWORD *)this + 1)); ++i )
  {
    v3 = (unsigned int *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 184LL))(
                           *((_QWORD *)this + 1),
                           i);
    if ( !*v3 )
    {
      (***((void (****)(_QWORD, const wchar_t *, ...))this + 2))(
        *((_QWORD *)this + 2),
        L"Validation Error in DatabaseMeta Row %d. DatabaseMeta.InternalName is a primarykey, so it must not be NULL.",
        i);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
        L"ERROR - VALIDATION ERROR",
        0x136u,
        0);
    }
    v4 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1));
    TMetaInferrence::ValidateStringAsLegalVariableName(this, v4, 0, 0);
    v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1), *v3);
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(v5 + 2 * v6) );
    if ( v6 > 0xF )
    {
      v16 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
      v17 = **v16;
      v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1), *v3);
      v17(v16, L"Error - DatabaseMeta.InternalName (%s) is too long.  Must be 15 characters or less.", v18);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
        L"ERROR - VALIDATION ERROR",
        0x143u,
        0);
    }
    if ( v3[1] )
    {
      v7 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1));
      TMetaInferrence::ValidateStringAsLegalVariableName(this, v7, 0, 0);
    }
    else
    {
      v3[1] = *v3;
    }
    if ( !v3[2] )
      v3[2] = *((_DWORD *)this + 6);
    if ( !v3[3] )
      v3[3] = *((_DWORD *)this + 6);
    v3[10] = 0;
    for ( j = 0;
          j < (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 320LL))(*((_QWORD *)this + 1))
       && *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 232LL))(
                       *((_QWORD *)this + 1),
                       j) != *v3;
          j = v3[10] )
    {
      ++v3[10];
    }
    v9 = v3[10];
    if ( v9 == (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 320LL))(*((_QWORD *)this + 1)) )
    {
      v13 = (void (***)(_QWORD, const wchar_t *, ...))*((_QWORD *)this + 2);
      v14 = **v13;
      v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1), *v3);
      v14(v13, L"Error - No tables belong to Database (%s)", v15);
      ThrowException(
        L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
        L"ERROR - VALIDATION ERROR",
        0x16Fu,
        0);
    }
    v3[4] = 0;
    while ( v9 < (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 320LL))(*((_QWORD *)this + 1)) )
    {
      v10 = *v3;
      v11 = (_DWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 232LL))(
                        *((_QWORD *)this + 1),
                        v9);
      v12 = v3[4];
      if ( *v11 == v10 )
      {
        v3[4] = v12 + 1;
      }
      else if ( v12 )
      {
        break;
      }
      ++v9;
    }
    v3[4] = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 16LL))(*((_QWORD *)this + 1), v3[4]);
  }
}

```

## disassembly

```asm
0x18001e9d4  push    rbx
0x18001e9d6  push    rbp
0x18001e9d7  push    rsi
0x18001e9d8  push    rdi
0x18001e9d9  push    r14
0x18001e9db  push    r15
0x18001e9dd  sub     rsp, 28h
0x18001e9e1  xor     r15d, r15d
0x18001e9e4  mov     rbp, rcx
0x18001e9e7  mov     r14d, r15d
0x18001e9ea  mov     rcx, [rbp+8]
0x18001e9ee  mov     rax, [rcx]
0x18001e9f1  mov     rax, [rax+110h]
0x18001e9f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9fd  cmp     r14d, eax
0x18001ea00  jnb     loc_18001EC5E
0x18001ea06  mov     rcx, [rbp+8]
0x18001ea0a  mov     edx, r14d
0x18001ea0d  mov     rax, [rcx]
0x18001ea10  mov     rax, [rax+0B8h]
0x18001ea17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea1c  mov     rsi, rax
0x18001ea1f  mov     edx, [rax]
0x18001ea21  test    edx, edx
0x18001ea23  jz      loc_18001EC28
0x18001ea29  mov     rcx, [rbp+8]
0x18001ea2d  mov     r8, [rcx]
0x18001ea30  mov     rax, [r8+90h]
0x18001ea37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea3c  mov     rdx, rax; unsigned __int16 *
0x18001ea3f  xor     r9d, r9d; bool
0x18001ea42  xor     r8d, r8d; unsigned __int16 *
0x18001ea45  mov     rcx, rbp; this
0x18001ea48  call    ?ValidateStringAsLegalVariableName@TMetaInferrence@@AEAAXPEBG0_N@Z; TMetaInferrence::ValidateStringAsLegalVariableName(ushort const *,ushort const *,bool)
0x18001ea4d  mov     rcx, [rbp+8]
0x18001ea51  mov     edx, [rsi]
0x18001ea53  mov     rax, [rcx]
0x18001ea56  mov     rax, [rax+90h]
0x18001ea5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea62  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001ea66  inc     rcx
0x18001ea69  cmp     [rax+rcx*2], r15w
0x18001ea6e  jnz     short loc_18001EA66
0x18001ea70  cmp     rcx, 0Fh
0x18001ea74  ja      loc_18001EBD7
0x18001ea7a  mov     edx, [rsi+4]
0x18001ea7d  test    edx, edx
0x18001ea7f  jnz     short loc_18001EA88
0x18001ea81  mov     eax, [rsi]
0x18001ea83  mov     [rsi+4], eax
0x18001ea86  jmp     short loc_18001EAAC
0x18001ea88  mov     rcx, [rbp+8]
0x18001ea8c  mov     rax, [rcx]
0x18001ea8f  mov     rax, [rax+90h]
0x18001ea96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea9b  mov     rdx, rax; unsigned __int16 *
0x18001ea9e  xor     r9d, r9d; bool
0x18001eaa1  xor     r8d, r8d; unsigned __int16 *
0x18001eaa4  mov     rcx, rbp; this
0x18001eaa7  call    ?ValidateStringAsLegalVariableName@TMetaInferrence@@AEAAXPEBG0_N@Z; TMetaInferrence::ValidateStringAsLegalVariableName(ushort const *,ushort const *,bool)
0x18001eaac  cmp     [rsi+8], r15d
0x18001eab0  jnz     short loc_18001EAB8
0x18001eab2  mov     eax, [rbp+18h]
0x18001eab5  mov     [rsi+8], eax
0x18001eab8  cmp     [rsi+0Ch], r15d
0x18001eabc  jnz     short loc_18001EAC4
0x18001eabe  mov     eax, [rbp+18h]
0x18001eac1  mov     [rsi+0Ch], eax
0x18001eac4  mov     [rsi+28h], r15d
0x18001eac8  mov     ebx, r15d
0x18001eacb  mov     rcx, [rbp+8]
0x18001eacf  mov     rax, [rcx]
0x18001ead2  mov     rax, [rax+140h]
0x18001ead9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eade  cmp     ebx, eax
0x18001eae0  jnb     short loc_18001EB05
0x18001eae2  mov     rcx, [rbp+8]
0x18001eae6  mov     edx, ebx
0x18001eae8  mov     rax, [rcx]
0x18001eaeb  mov     rax, [rax+0E8h]
0x18001eaf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eaf7  mov     ecx, [rsi]
0x18001eaf9  cmp     [rax], ecx
0x18001eafb  jz      short loc_18001EB05
0x18001eafd  inc     dword ptr [rsi+28h]
0x18001eb00  mov     ebx, [rsi+28h]
0x18001eb03  jmp     short loc_18001EACB
0x18001eb05  mov     rcx, [rbp+8]
0x18001eb09  mov     edi, [rsi+28h]
0x18001eb0c  mov     rax, [rcx]
0x18001eb0f  mov     rax, [rax+140h]
0x18001eb16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb1b  cmp     edi, eax
0x18001eb1d  jz      short loc_18001EB86
0x18001eb1f  mov     [rsi+10h], r15d
0x18001eb23  mov     rcx, [rbp+8]
0x18001eb27  mov     rax, [rcx]
0x18001eb2a  mov     rax, [rax+140h]
0x18001eb31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb36  cmp     edi, eax
0x18001eb38  jnb     short loc_18001EB68
0x18001eb3a  mov     rcx, [rbp+8]
0x18001eb3e  mov     edx, edi
0x18001eb40  mov     ebx, [rsi]
0x18001eb42  mov     rax, [rcx]
0x18001eb45  mov     rax, [rax+0E8h]
0x18001eb4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb51  mov     ecx, [rsi+10h]
0x18001eb54  cmp     [rax], ebx
0x18001eb56  jnz     short loc_18001EB60
0x18001eb58  lea     eax, [rcx+1]
0x18001eb5b  mov     [rsi+10h], eax
0x18001eb5e  jmp     short loc_18001EB64
0x18001eb60  test    ecx, ecx
0x18001eb62  jnz     short loc_18001EB68
0x18001eb64  inc     edi
0x18001eb66  jmp     short loc_18001EB23
0x18001eb68  mov     rcx, [rbp+8]
0x18001eb6c  mov     edx, [rsi+10h]
0x18001eb6f  mov     rax, [rcx]
0x18001eb72  mov     rax, [rax+10h]
0x18001eb76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb7b  mov     [rsi+10h], eax
0x18001eb7e  inc     r14d
0x18001eb81  jmp     loc_18001E9EA
0x18001eb86  mov     rdi, [rbp+10h]
0x18001eb8a  mov     rcx, [rbp+8]
0x18001eb8e  mov     rax, [rdi]
0x18001eb91  mov     rdx, [rcx]
0x18001eb94  mov     rbx, [rax]
0x18001eb97  mov     rax, [rdx+90h]
0x18001eb9e  mov     edx, [rsi]
0x18001eba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eba5  mov     r8, rax
0x18001eba8  lea     rdx, aErrorNoTablesB; "Error - No tables belong to Database (%"...
0x18001ebaf  mov     rax, rbx
0x18001ebb2  mov     rcx, rdi
0x18001ebb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebba  xor     r9d, r9d; unsigned int
0x18001ebbd  lea     rdx, aErrorValidatio; "ERROR - VALIDATION ERROR"
0x18001ebc4  mov     r8d, 16Fh; unsigned int
0x18001ebca  lea     rcx, aInetsrvIisMbCo_13; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001ebd1  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x18001ebd7  mov     rdi, [rbp+10h]
0x18001ebdb  mov     rcx, [rbp+8]
0x18001ebdf  mov     rax, [rdi]
0x18001ebe2  mov     rdx, [rcx]
0x18001ebe5  mov     rbx, [rax]
0x18001ebe8  mov     rax, [rdx+90h]
0x18001ebef  mov     edx, [rsi]
0x18001ebf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebf6  mov     r8, rax
0x18001ebf9  lea     rdx, aErrorDatabasem; "Error - DatabaseMeta.InternalName (%s) "...
0x18001ec00  mov     rax, rbx
0x18001ec03  mov     rcx, rdi
0x18001ec06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec0b  xor     r9d, r9d; unsigned int
0x18001ec0e  lea     rdx, aErrorValidatio; "ERROR - VALIDATION ERROR"
0x18001ec15  mov     r8d, 143h; unsigned int
0x18001ec1b  lea     rcx, aInetsrvIisMbCo_13; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001ec22  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x18001ec28  mov     rcx, [rbp+10h]
0x18001ec2c  lea     rdx, aValidationErro; "Validation Error in DatabaseMeta Row %d"...
0x18001ec33  mov     r8d, r14d
0x18001ec36  mov     rax, [rcx]
0x18001ec39  mov     rax, [rax]
0x18001ec3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec41  xor     r9d, r9d; unsigned int
0x18001ec44  lea     rdx, aErrorValidatio; "ERROR - VALIDATION ERROR"
0x18001ec4b  mov     r8d, 136h; unsigned int
0x18001ec51  lea     rcx, aInetsrvIisMbCo_13; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x18001ec58  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x18001ec5e  add     rsp, 28h
0x18001ec62  pop     r15
0x18001ec64  pop     r14
0x18001ec66  pop     rdi
0x18001ec67  pop     rsi
0x18001ec68  pop     rbp
0x18001ec69  pop     rbx
0x18001ec6a  retn
```
