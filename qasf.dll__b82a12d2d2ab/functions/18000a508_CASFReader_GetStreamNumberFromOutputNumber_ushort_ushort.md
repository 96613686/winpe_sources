# CASFReader::GetStreamNumberFromOutputNumber(ushort,ushort *)

- ea: `0x18000a508`
- end: `0x18000a709`
- name: `?GetStreamNumberFromOutputNumber@CASFReader@@AEAAJGPEAG@Z`
- size: `513`
- prototype: `__int64 __fastcall(CASFReader *__hidden this, unsigned __int16, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ab04`

## callees

- `0x180001460`
- `0x18000a508`
- `0x18001f010`

## import_xrefs

- `KERNEL32!lstrcmpW` at `0x18000a65b`
- `KERNEL32!lstrcmpW` at `0x18000a65b`

## pseudocode

```c
__int64 __fastcall CASFReader::GetStreamNumberFromOutputNumber(
        CASFReader *this,
        unsigned __int16 a2,
        unsigned __int16 *a3)
{
  __int64 v4; // rcx
  int v6; // ebx
  unsigned int v7; // edi
  _WORD v9[2]; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v10; // [rsp+24h] [rbp-DCh] BYREF
  __int64 v11; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v13; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR String2[256]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR String1[256]; // [rsp+240h] [rbp+140h] BYREF

  v10 = 0;
  *a3 = 0;
  v4 = *((_QWORD *)this + 43);
  v13 = 0;
  v12 = 0;
  v9[0] = 256;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v4 + 48LL))(v4, a2, &v13);
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, WCHAR *, _WORD *))(*(_QWORD *)v13 + 56LL))(v13, String1, v9);
    if ( v6 >= 0 )
    {
      v6 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 43))(
             *((_QWORD *)this + 43),
             &IID_IWMProfile,
             &v12);
      if ( v6 >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v12 + 64LL))(v12, &v10);
        if ( v6 >= 0 )
        {
          v7 = 0;
          while ( 1 )
          {
            if ( v7 >= v10 )
            {
              v6 = -2147024809;
              goto LABEL_18;
            }
            v11 = 0;
            v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v12 + 72LL))(v12, v7, &v11);
            if ( v6 >= 0 )
            {
              v9[0] = 256;
              v6 = (*(__int64 (__fastcall **)(__int64, WCHAR *, _WORD *))(*(_QWORD *)v11 + 64LL))(v11, String2, v9);
              if ( v6 >= 0 && !lstrcmpW(String1, String2) )
              {
                v6 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v11 + 32LL))(v11, a3);
                if ( v6 >= 0 )
                  break;
              }
            }
            if ( v11 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
            ++v7;
            if ( v6 < 0 )
              goto LABEL_18;
          }
          if ( v11 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        }
      }
    }
  }
LABEL_18:
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000a508  push    rbp
0x18000a50a  push    rbx
0x18000a50b  push    rsi
0x18000a50c  push    rdi
0x18000a50d  push    r15
0x18000a50f  lea     rbp, [rsp-350h]
0x18000a517  sub     rsp, 450h
0x18000a51e  mov     rax, cs:__security_cookie
0x18000a525  xor     rax, rsp
0x18000a528  mov     [rbp+370h+var_30], rax
0x18000a52f  xor     eax, eax
0x18000a531  mov     [rsp+470h+var_44C], 0
0x18000a539  mov     [r8], ax
0x18000a53d  mov     rdi, rcx
0x18000a540  mov     rcx, [rcx+158h]
0x18000a547  mov     rsi, r8
0x18000a54a  mov     [rsp+470h+var_438], 0
0x18000a553  lea     r8, [rsp+470h+var_438]
0x18000a558  mov     [rsp+470h+var_440], 0
0x18000a561  mov     r15d, 100h
0x18000a567  mov     [rsp+470h+var_450], r15w
0x18000a56d  mov     rax, [rcx]
0x18000a570  movzx   edx, dx
0x18000a573  mov     rax, [rax+30h]
0x18000a577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a57c  mov     ebx, eax
0x18000a57e  test    eax, eax
0x18000a580  js      loc_18000A6BE
0x18000a586  mov     rcx, [rsp+470h+var_438]
0x18000a58b  lea     r8, [rsp+470h+var_450]
0x18000a590  lea     rdx, [rbp+370h+String1]
0x18000a597  mov     rax, [rcx]
0x18000a59a  mov     rax, [rax+38h]
0x18000a59e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5a3  mov     ebx, eax
0x18000a5a5  test    eax, eax
0x18000a5a7  js      loc_18000A6BE
0x18000a5ad  mov     rcx, [rdi+158h]
0x18000a5b4  lea     r8, [rsp+470h+var_440]
0x18000a5b9  lea     rdx, IID_IWMProfile
0x18000a5c0  mov     rax, [rcx]
0x18000a5c3  mov     rax, [rax]
0x18000a5c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5cb  mov     ebx, eax
0x18000a5cd  test    eax, eax
0x18000a5cf  js      loc_18000A6BE
0x18000a5d5  mov     rcx, [rsp+470h+var_440]
0x18000a5da  lea     rdx, [rsp+470h+var_44C]
0x18000a5df  mov     rax, [rcx]
0x18000a5e2  mov     rax, [rax+40h]
0x18000a5e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5eb  mov     ebx, eax
0x18000a5ed  test    eax, eax
0x18000a5ef  js      loc_18000A6BE
0x18000a5f5  xor     edi, edi
0x18000a5f7  cmp     edi, [rsp+470h+var_44C]
0x18000a5fb  jnb     loc_18000A6B9
0x18000a601  mov     rcx, [rsp+470h+var_440]
0x18000a606  lea     r8, [rsp+470h+var_448]
0x18000a60b  mov     [rsp+470h+var_448], 0
0x18000a614  mov     edx, edi
0x18000a616  mov     rax, [rcx]
0x18000a619  mov     rax, [rax+48h]
0x18000a61d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a622  mov     ebx, eax
0x18000a624  test    eax, eax
0x18000a626  js      short loc_18000A67F
0x18000a628  mov     rcx, [rsp+470h+var_448]
0x18000a62d  lea     r8, [rsp+470h+var_450]
0x18000a632  mov     [rsp+470h+var_450], r15w
0x18000a638  lea     rdx, [rsp+470h+String2]
0x18000a63d  mov     rax, [rcx]
0x18000a640  mov     rax, [rax+40h]
0x18000a644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a649  mov     ebx, eax
0x18000a64b  test    eax, eax
0x18000a64d  js      short loc_18000A67F
0x18000a64f  lea     rdx, [rsp+470h+String2]; lpString2
0x18000a654  lea     rcx, [rbp+370h+String1]; lpString1
0x18000a65b  call    cs:__imp_lstrcmpW
0x18000a661  test    eax, eax
0x18000a663  jnz     short loc_18000A67F
0x18000a665  mov     rcx, [rsp+470h+var_448]
0x18000a66a  mov     rdx, rsi
0x18000a66d  mov     rax, [rcx]
0x18000a670  mov     rax, [rax+20h]
0x18000a674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a679  mov     ebx, eax
0x18000a67b  test    eax, eax
0x18000a67d  jns     short loc_18000A6A1
0x18000a67f  mov     rcx, [rsp+470h+var_448]
0x18000a684  test    rcx, rcx
0x18000a687  jz      short loc_18000A695
0x18000a689  mov     rax, [rcx]
0x18000a68c  mov     rax, [rax+10h]
0x18000a690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a695  inc     edi
0x18000a697  test    ebx, ebx
0x18000a699  jns     loc_18000A5F7
0x18000a69f  jmp     short loc_18000A6BE
0x18000a6a1  mov     rcx, [rsp+470h+var_448]
0x18000a6a6  test    rcx, rcx
0x18000a6a9  jz      short loc_18000A6BE
0x18000a6ab  mov     rax, [rcx]
0x18000a6ae  mov     rax, [rax+10h]
0x18000a6b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6b7  jmp     short loc_18000A6BE
0x18000a6b9  mov     ebx, 80070057h
0x18000a6be  mov     rcx, [rsp+470h+var_440]
0x18000a6c3  test    rcx, rcx
0x18000a6c6  jz      short loc_18000A6D4
0x18000a6c8  mov     rax, [rcx]
0x18000a6cb  mov     rax, [rax+10h]
0x18000a6cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6d4  mov     rcx, [rsp+470h+var_438]
0x18000a6d9  test    rcx, rcx
0x18000a6dc  jz      short loc_18000A6EA
0x18000a6de  mov     rax, [rcx]
0x18000a6e1  mov     rax, [rax+10h]
0x18000a6e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6ea  mov     eax, ebx
0x18000a6ec  mov     rcx, [rbp+370h+var_30]
0x18000a6f3  xor     rcx, rsp; StackCookie
0x18000a6f6  call    __security_check_cookie
0x18000a6fb  add     rsp, 450h
0x18000a702  pop     r15
0x18000a704  pop     rdi
0x18000a705  pop     rsi
0x18000a706  pop     rbx
0x18000a707  pop     rbp
0x18000a708  retn
```
