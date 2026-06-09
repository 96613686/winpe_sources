# CADMCOMW::SetHistoryAndEWR(ulong,ulong)

- ea: `0x1800093bc`
- end: `0x180009515`
- name: `?SetHistoryAndEWR@CADMCOMW@@AEAAJKK@Z`
- size: `345`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004388`
- `0x180008ae0`

## callees

- `0x1800093bc`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CADMCOMW::SetHistoryAndEWR(CADMCOMW *this, int a2, int a3)
{
  __int64 v4; // rcx
  int v5; // ebx
  __int64 v6; // rcx
  __int64 v8; // [rsp+40h] [rbp-9h] BYREF
  int v9; // [rsp+48h] [rbp-1h]
  int v10; // [rsp+4Ch] [rbp+3h]
  __int64 v11; // [rsp+50h] [rbp+7h]
  int *v12; // [rsp+58h] [rbp+Fh]
  __int64 v13; // [rsp+60h] [rbp+17h]
  __int64 v14; // [rsp+68h] [rbp+1Fh] BYREF
  int v15; // [rsp+70h] [rbp+27h]
  int v16; // [rsp+74h] [rbp+2Bh]
  __int64 v17; // [rsp+78h] [rbp+2Fh]
  int *v18; // [rsp+80h] [rbp+37h]
  __int64 v19; // [rsp+88h] [rbp+3Fh]
  unsigned int v20; // [rsp+B0h] [rbp+67h] BYREF
  int v21; // [rsp+B8h] [rbp+6Fh] BYREF
  int v22; // [rsp+C0h] [rbp+77h] BYREF

  v22 = a3;
  v21 = a2;
  v20 = 0;
  v15 = 1;
  v18 = &v21;
  v16 = 1;
  v9 = 1;
  v4 = *((_QWORD *)this + 4);
  v10 = 1;
  v12 = &v22;
  v14 = 9996;
  v17 = 4;
  v19 = 0;
  v8 = 9998;
  v11 = 4;
  v13 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *, __int64, int, unsigned int *))(*(_QWORD *)v4 + 280LL))(
         v4,
         0,
         L"/LM",
         2,
         5000,
         &v20);
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const unsigned __int16 *, __int64 *))(**((_QWORD **)this + 4) + 152LL))(
           *((_QWORD *)this + 4),
           v20,
           &byte_1800127D8,
           &v8);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const unsigned __int16 *, __int64 *))(**((_QWORD **)this + 4)
                                                                                          + 152LL))(
             *((_QWORD *)this + 4),
             v20,
             &byte_1800127D8,
             &v14);
      if ( v5 >= 0 )
      {
        (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 4) + 288LL))(*((_QWORD *)this + 4), v20);
        v6 = *((_QWORD *)this + 4);
        v20 = 0;
        v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v6 + 304LL))(v6, 0);
      }
    }
  }
  if ( v20 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 288LL))(*((_QWORD *)this + 4));
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800093bc  mov     [rsp-8+arg_10], r8d
0x1800093c1  mov     [rsp-8+arg_8], edx
0x1800093c5  push    rbp
0x1800093c6  push    rbx
0x1800093c7  push    rdi
0x1800093c8  lea     rbp, [rsp-47h]
0x1800093cd  sub     rsp, 90h
0x1800093d4  mov     edx, 1
0x1800093d9  mov     [rbp+57h+arg_0], 0
0x1800093e0  mov     [rbp+57h+var_30], edx
0x1800093e3  lea     rax, [rbp+57h+arg_8]
0x1800093e7  mov     [rbp+57h+var_20], rax
0x1800093eb  lea     r8, aLm; "/LM"
0x1800093f2  mov     [rbp+57h+var_2C], edx
0x1800093f5  lea     rax, [rbp+57h+arg_10]
0x1800093f9  mov     [rbp+57h+var_58], edx
0x1800093fc  mov     rdi, rcx
0x1800093ff  mov     rcx, [rcx+20h]
0x180009403  mov     r9d, 2
0x180009409  mov     [rbp+57h+var_54], edx
0x18000940c  lea     rdx, [rbp+57h+arg_0]
0x180009410  mov     [rbp+57h+var_48], rax
0x180009414  mov     [rsp+0A0h+var_78], rdx
0x180009419  xor     edx, edx
0x18000941b  mov     [rbp+57h+var_38], 270Ch
0x180009423  mov     [rbp+57h+var_28], 4
0x18000942b  mov     [rbp+57h+var_18], 0
0x180009433  mov     [rbp+57h+var_60], 270Eh
0x18000943b  mov     [rbp+57h+var_50], 4
0x180009443  mov     [rbp+57h+var_40], 0
0x18000944b  mov     rax, [rcx]
0x18000944e  mov     [rsp+0A0h+var_80], 1388h
0x180009456  mov     rax, [rax+118h]
0x18000945d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009462  mov     ebx, eax
0x180009464  test    eax, eax
0x180009466  js      loc_1800094EE
0x18000946c  mov     rcx, [rdi+20h]
0x180009470  lea     r9, [rbp+57h+var_60]
0x180009474  mov     edx, [rbp+57h+arg_0]
0x180009477  lea     r8, byte_1800127D8
0x18000947e  mov     rax, [rcx]
0x180009481  mov     rax, [rax+98h]
0x180009488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000948d  mov     ebx, eax
0x18000948f  test    eax, eax
0x180009491  js      short loc_1800094EE
0x180009493  mov     rcx, [rdi+20h]
0x180009497  lea     r9, [rbp+57h+var_38]
0x18000949b  mov     edx, [rbp+57h+arg_0]
0x18000949e  lea     r8, byte_1800127D8
0x1800094a5  mov     rax, [rcx]
0x1800094a8  mov     rax, [rax+98h]
0x1800094af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094b4  mov     ebx, eax
0x1800094b6  test    eax, eax
0x1800094b8  js      short loc_1800094EE
0x1800094ba  mov     rcx, [rdi+20h]
0x1800094be  mov     edx, [rbp+57h+arg_0]
0x1800094c1  mov     rax, [rcx]
0x1800094c4  mov     rax, [rax+120h]
0x1800094cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094d0  mov     rcx, [rdi+20h]
0x1800094d4  xor     edx, edx
0x1800094d6  mov     [rbp+57h+arg_0], 0
0x1800094dd  mov     rax, [rcx]
0x1800094e0  mov     rax, [rax+130h]
0x1800094e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094ec  mov     ebx, eax
0x1800094ee  mov     edx, [rbp+57h+arg_0]
0x1800094f1  test    edx, edx
0x1800094f3  jz      short loc_180009508
0x1800094f5  mov     rcx, [rdi+20h]
0x1800094f9  mov     rax, [rcx]
0x1800094fc  mov     rax, [rax+120h]
0x180009503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009508  mov     eax, ebx
0x18000950a  add     rsp, 90h
0x180009511  pop     rdi
0x180009512  pop     rbx
0x180009513  pop     rbp
0x180009514  retn
```
