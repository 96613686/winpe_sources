# ATL::CAxHostWindow::GetOptionKeyPath(ushort * *,ulong)

- ea: `0x140010b90`
- end: `0x140010c98`
- name: `?GetOptionKeyPath@CAxHostWindow@ATL@@UEAAJPEAPEAGK@Z`
- size: `264`
- prototype: `__int64 __fastcall(ATL::CAxHostWindow *__hidden this, unsigned __int16 **, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x140010b90`
- `0x14004d010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140010c6d`
- `msvcrt!memcpy_s` at `0x140010c6d`
- `ole32!CoTaskMemAlloc` at `0x140010c20`
- `ole32!CoTaskMemAlloc` at `0x140010c20`
- `OLEAUT32!__imp_SysStringLen` at `0x140010bf3`
- `OLEAUT32!__imp_SysStringLen` at `0x140010bf3`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140010c0e`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140010c0e`

## pseudocode

```c
__int64 __fastcall ATL::CAxHostWindow::GetOptionKeyPath(ATL::CAxHostWindow *this, unsigned __int16 **a2)
{
  __int64 v5; // rcx
  int v6; // ebx
  __int64 v7; // rbp
  void *v8; // rbx
  _WORD *v9; // r8
  __int64 v10; // rax

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v5 = *((_QWORD *)this + 13);
  if ( v5 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 136LL))(v5);
    if ( v6 < 0 || !*a2 )
      return 1;
  }
  else
  {
    v6 = 1;
    if ( SysStringLen(*((BSTR *)this + 29)) )
    {
      v7 = SysStringByteLen(*((BSTR *)this + 29));
      v8 = CoTaskMemAlloc(v7 + 2);
      if ( !v8 )
        return 2147942414LL;
      v9 = (_WORD *)*((_QWORD *)this + 29);
      if ( v9 )
      {
        v10 = -1;
        do
          ++v10;
        while ( v9[v10] );
      }
      else
      {
        LODWORD(v10) = 0;
      }
      if ( memcpy_s(v8, (v7 & 0xFFFFFFFFFFFFFFFEuLL) + 2, v9, 2LL * ((int)v10 + 1)) )
        return 2147500037LL;
      *a2 = (unsigned __int16 *)v8;
      return 0;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140010b90  push    rbx
0x140010b92  push    rbp
0x140010b93  push    rsi
0x140010b94  push    rdi
0x140010b95  push    r14
0x140010b97  sub     rsp, 20h
0x140010b9b  xor     r14d, r14d
0x140010b9e  mov     rdi, rdx
0x140010ba1  mov     rsi, rcx
0x140010ba4  test    rdx, rdx
0x140010ba7  jnz     short loc_140010BB3
0x140010ba9  mov     eax, 80004003h
0x140010bae  jmp     loc_140010C8C
0x140010bb3  mov     [rdx], r14
0x140010bb6  mov     rcx, [rcx+68h]
0x140010bba  test    rcx, rcx
0x140010bbd  jz      short loc_140010BE7
0x140010bbf  mov     rax, [rcx]
0x140010bc2  mov     rax, [rax+88h]
0x140010bc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010bce  mov     ebx, eax
0x140010bd0  test    eax, eax
0x140010bd2  js      short loc_140010BDD
0x140010bd4  cmp     [rdi], r14
0x140010bd7  jnz     loc_140010C8A
0x140010bdd  mov     ebx, 1
0x140010be2  jmp     loc_140010C8A
0x140010be7  mov     rcx, [rsi+0E8h]; pbstr
0x140010bee  mov     ebx, 1
0x140010bf3  call    cs:__imp_SysStringLen
0x140010bfa  nop     dword ptr [rax+rax+00h]
0x140010bff  test    eax, eax
0x140010c01  jz      loc_140010C8A
0x140010c07  mov     rcx, [rsi+0E8h]; bstr
0x140010c0e  call    cs:__imp_SysStringByteLen
0x140010c15  nop     dword ptr [rax+rax+00h]
0x140010c1a  mov     ebp, eax
0x140010c1c  lea     rcx, [rbp+2]; cb
0x140010c20  call    cs:__imp_CoTaskMemAlloc
0x140010c27  nop     dword ptr [rax+rax+00h]
0x140010c2c  mov     rbx, rax
0x140010c2f  test    rax, rax
0x140010c32  jnz     short loc_140010C3B
0x140010c34  mov     eax, 8007000Eh
0x140010c39  jmp     short loc_140010C8C
0x140010c3b  mov     r8, [rsi+0E8h]; Source
0x140010c42  test    r8, r8
0x140010c45  jnz     short loc_140010C4C
0x140010c47  mov     eax, r14d
0x140010c4a  jmp     short loc_140010C5A
0x140010c4c  or      rax, 0FFFFFFFFFFFFFFFFh
0x140010c50  inc     rax
0x140010c53  cmp     [r8+rax*2], r14w
0x140010c58  jnz     short loc_140010C50
0x140010c5a  inc     eax
0x140010c5c  and     rbp, 0FFFFFFFFFFFFFFFEh
0x140010c60  movsxd  r9, eax
0x140010c63  mov     rcx, rbx; Destination
0x140010c66  add     r9, r9; SourceSize
0x140010c69  lea     rdx, [rbp+2]; DestinationSize
0x140010c6d  call    cs:__imp_memcpy_s
0x140010c74  nop     dword ptr [rax+rax+00h]
0x140010c79  test    eax, eax
0x140010c7b  jz      short loc_140010C84
0x140010c7d  mov     eax, 80004005h
0x140010c82  jmp     short loc_140010C8C
0x140010c84  mov     [rdi], rbx
0x140010c87  mov     ebx, r14d
0x140010c8a  mov     eax, ebx
0x140010c8c  add     rsp, 20h
0x140010c90  pop     r14
0x140010c92  pop     rdi
0x140010c93  pop     rsi
0x140010c94  pop     rbp
0x140010c95  pop     rbx
0x140010c96  retn
```
