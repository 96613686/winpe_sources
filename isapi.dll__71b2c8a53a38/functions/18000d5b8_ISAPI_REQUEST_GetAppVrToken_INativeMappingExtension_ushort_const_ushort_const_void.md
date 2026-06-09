# ISAPI_REQUEST::GetAppVrToken(INativeMappingExtension *,ushort const *,ushort const *,void * *)

- ea: `0x18000d5b8`
- end: `0x18000d722`
- name: `?GetAppVrToken@ISAPI_REQUEST@@QEAAJPEAVINativeMappingExtension@@PEBG1PEAPEAX@Z`
- size: `362`
- prototype: `__int64 __usercall@<rax>(ISAPI_REQUEST *__hidden this@<rcx>, struct INativeMappingExtension *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000eff0`

## callees

- `0x18000c898`
- `0x18000d5b8`
- `0x180011d4c`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ISAPI_REQUEST::GetAppVrToken(
        ISAPI_REQUEST *this,
        struct INativeMappingExtension *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        void **a5)
{
  __int64 (__fastcall *v6)(struct INativeMappingExtension *, const unsigned __int16 *, const unsigned __int16 *, _QWORD, _QWORD, __int64 *, __int64 *, _QWORD); // rax
  __int64 result; // rax
  int Token; // ebx
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // [rsp+50h] [rbp-28h] BYREF
  unsigned __int16 *v12; // [rsp+58h] [rbp-20h] BYREF
  __int64 v13; // [rsp+60h] [rbp-18h] BYREF
  unsigned __int16 *v14; // [rsp+68h] [rbp-10h] BYREF
  unsigned int v15; // [rsp+A8h] [rbp+30h] BYREF

  v6 = *(__int64 (__fastcall **)(struct INativeMappingExtension *, const unsigned __int16 *, const unsigned __int16 *, _QWORD, _QWORD, __int64 *, __int64 *, _QWORD))(*(_QWORD *)a2 + 40LL);
  v11 = 0;
  v13 = 0;
  result = v6(a2, a3, a4, 0, 0, &v11, &v13, 0);
  if ( (int)result >= 0 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v12 = 0;
    Token = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v11 + 64LL))(
              v11,
              L"userName",
              &v12,
              0,
              0);
    if ( Token >= 0 )
    {
      if ( !*v12 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        *a5 = 0;
        return 0;
      }
      v14 = 0;
      v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v11 + 64LL))(
             v11,
             L"password",
             &v14,
             0,
             0);
      v10 = v11;
      Token = v9;
      if ( v9 < 0 )
        goto LABEL_10;
      v15 = 0;
      Token = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned int *, _QWORD, _QWORD))(*(_QWORD *)v11 + 48LL))(
                v11,
                L"logonMethod",
                &v15,
                0,
                0);
      if ( Token >= 0 )
      {
        Token = TranslateLogonMethod(&v15);
        if ( Token >= 0 )
          Token = ISAPI_REQUEST::CreateToken(this, v12, v14, 0, v15, a5);
      }
    }
    v10 = v11;
LABEL_10:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    return (unsigned int)Token;
  }
  return result;
}

```

## disassembly

```asm
0x18000d5b8  push    rbp
0x18000d5ba  push    rbx
0x18000d5bb  push    rsi
0x18000d5bc  push    rdi
0x18000d5bd  mov     rbp, rsp
0x18000d5c0  sub     rsp, 78h
0x18000d5c4  mov     rax, [rdx]
0x18000d5c7  mov     rdi, rcx
0x18000d5ca  xor     esi, esi
0x18000d5cc  lea     rcx, [rbp+var_18]
0x18000d5d0  mov     [rsp+78h+var_40], rsi
0x18000d5d5  mov     r10, r9
0x18000d5d8  mov     [rsp+78h+var_48], rcx
0x18000d5dd  mov     r11, r8
0x18000d5e0  mov     rax, [rax+28h]
0x18000d5e4  lea     rcx, [rbp+var_28]
0x18000d5e8  mov     rbx, rdx
0x18000d5eb  mov     [rsp+78h+var_50], rcx
0x18000d5f0  mov     rcx, rbx
0x18000d5f3  mov     [rbp+var_28], rsi
0x18000d5f7  xor     r9d, r9d
0x18000d5fa  mov     [rbp+var_18], rsi
0x18000d5fe  mov     r8, r10
0x18000d601  mov     qword ptr [rsp+78h+var_58], rsi
0x18000d606  mov     rdx, r11
0x18000d609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d60e  test    eax, eax
0x18000d610  js      loc_18000D719
0x18000d616  mov     rcx, [rbp+var_18]
0x18000d61a  mov     rax, [rcx]
0x18000d61d  mov     rax, [rax+10h]
0x18000d621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d626  mov     rcx, [rbp+var_28]
0x18000d62a  lea     r8, [rbp+var_20]
0x18000d62e  mov     [rbp+var_20], rsi
0x18000d632  lea     rdx, aUsername; "userName"
0x18000d639  xor     r9d, r9d
0x18000d63c  mov     qword ptr [rsp+78h+var_58], rsi
0x18000d641  mov     rax, [rcx]
0x18000d644  mov     rax, [rax+40h]
0x18000d648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d64d  mov     ebx, eax
0x18000d64f  test    eax, eax
0x18000d651  js      loc_18000D707
0x18000d657  mov     rax, [rbp+var_20]
0x18000d65b  mov     rcx, [rbp+var_28]
0x18000d65f  cmp     [rax], si
0x18000d662  jnz     short loc_18000D67E
0x18000d664  mov     rax, [rcx]
0x18000d667  mov     rax, [rax+10h]
0x18000d66b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d670  mov     rax, [rbp+arg_20]
0x18000d674  mov     [rax], rsi
0x18000d677  xor     eax, eax
0x18000d679  jmp     loc_18000D719
0x18000d67e  mov     [rbp+var_10], rsi
0x18000d682  lea     r8, [rbp+var_10]
0x18000d686  mov     rax, [rcx]
0x18000d689  lea     rdx, aPassword; "password"
0x18000d690  xor     r9d, r9d
0x18000d693  mov     qword ptr [rsp+78h+var_58], rsi
0x18000d698  mov     rax, [rax+40h]
0x18000d69c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6a1  mov     rcx, [rbp+var_28]
0x18000d6a5  mov     ebx, eax
0x18000d6a7  test    eax, eax
0x18000d6a9  js      short loc_18000D70B
0x18000d6ab  mov     [rbp+arg_8], esi
0x18000d6ae  lea     r8, [rbp+arg_8]
0x18000d6b2  mov     rax, [rcx]
0x18000d6b5  lea     rdx, aLogonmethod; "logonMethod"
0x18000d6bc  xor     r9d, r9d
0x18000d6bf  mov     qword ptr [rsp+78h+var_58], rsi
0x18000d6c4  mov     rax, [rax+30h]
0x18000d6c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6cd  mov     ebx, eax
0x18000d6cf  test    eax, eax
0x18000d6d1  js      short loc_18000D707
0x18000d6d3  lea     rcx, [rbp+arg_8]; unsigned int *
0x18000d6d7  call    ?TranslateLogonMethod@@YAJPEAK@Z; TranslateLogonMethod(ulong *)
0x18000d6dc  mov     ebx, eax
0x18000d6de  test    eax, eax
0x18000d6e0  js      short loc_18000D707
0x18000d6e2  mov     rax, [rbp+arg_20]
0x18000d6e6  xor     r9d, r9d; unsigned __int16 *
0x18000d6e9  mov     r8, [rbp+var_10]; unsigned __int16 *
0x18000d6ed  mov     rcx, rdi; this
0x18000d6f0  mov     rdx, [rbp+var_20]; unsigned __int16 *
0x18000d6f4  mov     [rsp+78h+var_50], rax; void **
0x18000d6f9  mov     eax, [rbp+arg_8]
0x18000d6fc  mov     [rsp+78h+var_58], eax; unsigned int
0x18000d700  call    ?CreateToken@ISAPI_REQUEST@@QEAAJPEBG00KPEAPEAX@Z; ISAPI_REQUEST::CreateToken(ushort const *,ushort const *,ushort const *,ulong,void * *)
0x18000d705  mov     ebx, eax
0x18000d707  mov     rcx, [rbp+var_28]
0x18000d70b  mov     rdx, [rcx]
0x18000d70e  mov     rax, [rdx+10h]
0x18000d712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d717  mov     eax, ebx
0x18000d719  add     rsp, 78h
0x18000d71d  pop     rdi
0x18000d71e  pop     rsi
0x18000d71f  pop     rbx
0x18000d720  pop     rbp
0x18000d721  retn
```
