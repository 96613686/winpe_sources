# CTitleFTS::Initialize(void)

- ea: `0x180028c38`
- end: `0x180028dc1`
- name: `?Initialize@CTitleFTS@@QEAAJXZ`
- size: `393`
- prototype: `__int64 __fastcall(CTitleFTS *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800286f4`

## callees

- `0x180028c38`
- `0x180078010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180028cc7`
- `ole32!CoCreateInstance` at `0x180028cf1`
- `ole32!CoCreateInstance` at `0x180028d89`
- `ole32!CoCreateInstance` at `0x180028cc7`
- `ole32!CoCreateInstance` at `0x180028cf1`
- `ole32!CoCreateInstance` at `0x180028d89`

## pseudocode

```c
__int64 __fastcall CTitleFTS::Initialize(CTitleFTS *this)
{
  __int16 v3; // ax
  bool v4; // cc
  int v5; // eax
  int v6; // eax
  _QWORD *v7; // rsi
  _QWORD *v8; // r14

  if ( *((_DWORD *)this + 9) )
    return 2147500037LL;
  if ( *((_DWORD *)this + 4) )
    return 0;
  v3 = *((_WORD *)this + 45) & 0x3FF;
  *((_DWORD *)this + 9) = 1;
  if ( v3 == 4 || (v4 = (unsigned __int16)(v3 - 17) <= 1u, v5 = 0, v4) )
    v5 = 1;
  *((_DWORD *)this + 23) = v5;
  v6 = 589824;
  if ( *((_DWORD *)this + 12) != 1033 )
    v6 = 0x80000;
  *((_DWORD *)this + 11) = v6;
  if ( !*((_WORD *)this + 48) )
    goto LABEL_19;
  v7 = (_QWORD *)((char *)this + 56);
  if ( CoCreateInstance(&CLSID_IITIndexLocal, 0, 1u, &IID_IITIndex, (LPVOID *)this + 7) < 0 )
    goto LABEL_19;
  v8 = (_QWORD *)((char *)this + 80);
  if ( CoCreateInstance(&CLSID_IITDatabaseLocal, 0, 1u, &IID_IITDatabase, (LPVOID *)this + 10) < 0 )
    goto LABEL_19;
  if ( (*(int (__fastcall **)(_QWORD, _QWORD, char *, _QWORD))(*(_QWORD *)*v8 + 24LL))(*v8, 0, (char *)this + 96, 0) >= 0
    && (*(int (__fastcall **)(_QWORD, _QWORD, const wchar_t *, __int64))(*(_QWORD *)*v7 + 24LL))(
         *v7,
         *v8,
         L"ftiMain",
         1) >= 0 )
  {
    if ( (*(int (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v7 + 56LL))(*v7, (char *)this + 64) >= 0
      && (*(int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 8) + 40LL))(
           *((_QWORD *)this + 8),
           *((unsigned int *)this + 11)) >= 0
      && CoCreateInstance(&CLSID_IITResultSet, 0, 1u, &IID_IITResultSet, (LPVOID *)this + 9) >= 0 )
    {
      *((_DWORD *)this + 4) = 1;
      *((_DWORD *)this + 9) = 0;
      return 0;
    }
LABEL_19:
    *((_DWORD *)this + 8) = -2147221403;
    return 2147500037LL;
  }
  *((_DWORD *)this + 8) = -2147221404;
  return 2147500037LL;
}

```

## disassembly

```asm
0x180028c38  push    rbx
0x180028c3a  push    rbp
0x180028c3b  push    rsi
0x180028c3c  push    rdi
0x180028c3d  push    r14
0x180028c3f  push    r15
0x180028c41  sub     rsp, 38h
0x180028c45  xor     ebp, ebp
0x180028c47  mov     rbx, rcx
0x180028c4a  cmp     [rcx+24h], ebp
0x180028c4d  jnz     loc_180028DAF
0x180028c53  cmp     [rcx+10h], ebp
0x180028c56  jz      short loc_180028C5F
0x180028c58  xor     eax, eax
0x180028c5a  jmp     loc_180028DB4
0x180028c5f  mov     eax, 3FFh
0x180028c64  mov     r15d, 1
0x180028c6a  and     ax, [rcx+5Ah]
0x180028c6e  mov     [rcx+24h], r15d
0x180028c72  cmp     ax, 4
0x180028c76  jz      short loc_180028C84
0x180028c78  sub     ax, 11h
0x180028c7c  cmp     ax, r15w
0x180028c80  mov     eax, ebp
0x180028c82  ja      short loc_180028C87
0x180028c84  mov     eax, r15d
0x180028c87  mov     [rcx+5Ch], eax
0x180028c8a  mov     eax, 90000h
0x180028c8f  cmp     dword ptr [rbx+30h], 409h
0x180028c96  mov     ecx, 80000h
0x180028c9b  cmovnz  eax, ecx
0x180028c9e  mov     [rbx+2Ch], eax
0x180028ca1  cmp     [rbx+60h], bp
0x180028ca5  jz      loc_180028DA8
0x180028cab  lea     rsi, [rbx+38h]
0x180028caf  mov     r8d, r15d; dwClsContext
0x180028cb2  lea     r9, IID_IITIndex; riid
0x180028cb9  mov     [rsp+68h+ppv], rsi; ppv
0x180028cbe  xor     edx, edx; pUnkOuter
0x180028cc0  lea     rcx, CLSID_IITIndexLocal; rclsid
0x180028cc7  call    cs:__imp_CoCreateInstance
0x180028ccd  test    eax, eax
0x180028ccf  js      loc_180028DA8
0x180028cd5  lea     r14, [rbx+50h]
0x180028cd9  mov     r8d, r15d; dwClsContext
0x180028cdc  lea     r9, IID_IITDatabase; riid
0x180028ce3  mov     [rsp+68h+ppv], r14; ppv
0x180028ce8  xor     edx, edx; pUnkOuter
0x180028cea  lea     rcx, CLSID_IITDatabaseLocal; rclsid
0x180028cf1  call    cs:__imp_CoCreateInstance
0x180028cf7  test    eax, eax
0x180028cf9  js      loc_180028DA8
0x180028cff  mov     rcx, [r14]
0x180028d02  lea     r8, [rbx+60h]
0x180028d06  xor     r9d, r9d
0x180028d09  xor     edx, edx
0x180028d0b  mov     rax, [rcx]
0x180028d0e  mov     rax, [rax+18h]
0x180028d12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d17  test    eax, eax
0x180028d19  js      loc_180028D9F
0x180028d1f  mov     rcx, [rsi]
0x180028d22  lea     r8, aFtimain; "ftiMain"
0x180028d29  mov     rdx, [r14]
0x180028d2c  mov     r9d, r15d
0x180028d2f  mov     rax, [rcx]
0x180028d32  mov     rax, [rax+18h]
0x180028d36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d3b  test    eax, eax
0x180028d3d  js      short loc_180028D9F
0x180028d3f  mov     rcx, [rsi]
0x180028d42  lea     rdx, [rbx+40h]
0x180028d46  mov     rax, [rcx]
0x180028d49  mov     rax, [rax+38h]
0x180028d4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d52  test    eax, eax
0x180028d54  js      short loc_180028DA8
0x180028d56  mov     rcx, [rbx+40h]
0x180028d5a  mov     edx, [rbx+2Ch]
0x180028d5d  mov     rax, [rcx]
0x180028d60  mov     rax, [rax+28h]
0x180028d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d69  test    eax, eax
0x180028d6b  js      short loc_180028DA8
0x180028d6d  lea     rax, [rbx+48h]
0x180028d71  mov     r8d, r15d; dwClsContext
0x180028d74  lea     r9, IID_IITResultSet; riid
0x180028d7b  mov     [rsp+68h+ppv], rax; ppv
0x180028d80  xor     edx, edx; pUnkOuter
0x180028d82  lea     rcx, CLSID_IITResultSet; rclsid
0x180028d89  call    cs:__imp_CoCreateInstance
0x180028d8f  test    eax, eax
0x180028d91  js      short loc_180028DA8
0x180028d93  mov     [rbx+10h], r15d
0x180028d97  mov     [rbx+24h], ebp
0x180028d9a  jmp     loc_180028C58
0x180028d9f  mov     dword ptr [rbx+20h], 80040064h
0x180028da6  jmp     short loc_180028DAF
0x180028da8  mov     dword ptr [rbx+20h], 80040065h
0x180028daf  mov     eax, 80004005h
0x180028db4  add     rsp, 38h
0x180028db8  pop     r15
0x180028dba  pop     r14
0x180028dbc  pop     rdi
0x180028dbd  pop     rsi
0x180028dbe  pop     rbp
0x180028dbf  pop     rbx
0x180028dc0  retn
```
