# CProxy_DDiscFormat2TrackAtOnceEvents<CMsftDiscFormat2TrackAtOnce>::Fire_Update(IDiscFormat2TrackAtOnceEventArgs *)

- ea: `0x180023cf8`
- end: `0x180023e3c`
- name: `?Fire_Update@?$CProxy_DDiscFormat2TrackAtOnceEvents@VCMsftDiscFormat2TrackAtOnce@@@@QEAAXPEAUIDiscFormat2TrackAtOnceEventArgs@@@Z`
- size: `324`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180023f8c`
- `0x180024020`
- `0x180039f2c`
- `0x18003a7e0`

## callees

- `0x180023cf8`
- `0x18004a010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180023d34`
- `OLEAUT32!__imp_VariantInit` at `0x180023d3e`
- `OLEAUT32!__imp_VariantInit` at `0x180023d34`
- `OLEAUT32!__imp_VariantInit` at `0x180023d3e`
- `KERNEL32!EnterCriticalSection` at `0x180023d87`
- `KERNEL32!EnterCriticalSection` at `0x180023d87`
- `KERNEL32!LeaveCriticalSection` at `0x180023db9`
- `KERNEL32!LeaveCriticalSection` at `0x180023db9`

## pseudocode

```c
void __fastcall CProxy_DDiscFormat2TrackAtOnceEvents<CMsftDiscFormat2TrackAtOnce>::Fire_Update(__int64 a1, LONGLONG a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  int v5; // r14d
  __int64 v6; // rbx
  void (__fastcall ***v7)(_QWORD, GUID *, __int64 *); // rcx
  int v8; // [rsp+20h] [rbp-59h]
  __int128 v9; // [rsp+50h] [rbp-29h] BYREF
  __int64 v10; // [rsp+60h] [rbp-19h]
  VARIANTARG v11; // [rsp+68h] [rbp-11h] BYREF
  VARIANTARG pvarg; // [rsp+80h] [rbp+7h] BYREF
  __int64 v13; // [rsp+E0h] [rbp+67h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((a1 - 24) & -(__int64)(a1 != 0));
  v10 = 0;
  v9 = 0;
  VariantInit(&pvarg);
  VariantInit(&v11);
  v5 = *(_DWORD *)(a1 + 16);
  v11.llVal = a2;
  v6 = 0;
  pvarg.vt = 9;
  v11.vt = 9;
  *(_QWORD *)&v9 = &v11;
  pvarg.llVal = (LONGLONG)v4;
  for ( LODWORD(v10) = 2; (int)v6 < v5; v6 = (unsigned int)(v6 + 1) )
  {
    v13 = 0;
    EnterCriticalSection(v4 + 3);
    if ( (int)v6 < *(_DWORD *)(a1 + 16) )
    {
      v7 = *(void (__fastcall ****)(_QWORD, GUID *, __int64 *))(*(_QWORD *)(a1 + 8) + 8 * v6);
      if ( v7 )
        (**v7)(v7, &GUID_00020400_0000_0000_c000_000000000046, &v13);
    }
    LeaveCriticalSection(v4 + 3);
    if ( v13 )
    {
      LOWORD(v8) = 1;
      (*(void (__fastcall **)(__int64, __int64, GUID *, __int64, int, __int128 *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v13 + 48LL))(
        v13,
        512,
        &GUID_NULL,
        2048,
        v8,
        &v9,
        0,
        0,
        0);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
  }
}

```

## disassembly

```asm
0x180023cf8  push    rbp
0x180023cfa  push    rbx
0x180023cfb  push    rsi
0x180023cfc  push    rdi
0x180023cfd  push    r12
0x180023cff  push    r14
0x180023d01  lea     rbp, [rsp-2Fh]
0x180023d06  sub     rsp, 0A8h
0x180023d0d  mov     rax, rcx
0x180023d10  lea     r8, [rcx-18h]
0x180023d14  neg     rax
0x180023d17  mov     rdi, rcx
0x180023d1a  xorps   xmm0, xmm0
0x180023d1d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180023d21  sbb     rsi, rsi
0x180023d24  mov     rbx, rdx
0x180023d27  xor     eax, eax
0x180023d29  and     rsi, r8
0x180023d2c  mov     [rbp+57h+var_70], rax
0x180023d30  movups  [rbp+57h+var_80], xmm0
0x180023d34  call    cs:__imp_VariantInit
0x180023d3a  lea     rcx, [rbp+57h+var_68]; pvarg
0x180023d3e  call    cs:__imp_VariantInit
0x180023d44  mov     r14d, [rdi+10h]
0x180023d48  mov     eax, 9
0x180023d4d  mov     qword ptr [rbp+57h+var_68+8], rbx
0x180023d51  xor     ebx, ebx
0x180023d53  mov     word ptr [rbp+57h+pvarg], ax
0x180023d57  mov     word ptr [rbp+57h+var_68], ax
0x180023d5b  lea     rax, [rbp+57h+var_68]
0x180023d5f  mov     qword ptr [rbp+57h+var_80], rax
0x180023d63  mov     qword ptr [rbp+57h+pvarg+8], rsi
0x180023d67  mov     dword ptr [rbp+57h+var_70], 2
0x180023d6e  test    r14d, r14d
0x180023d71  jle     loc_180023E2C
0x180023d77  lea     r12d, [rbx+1]
0x180023d7b  lea     rcx, [rsi+78h]; lpCriticalSection
0x180023d7f  mov     [rbp+57h+arg_0], 0
0x180023d87  call    cs:__imp_EnterCriticalSection
0x180023d8d  cmp     ebx, [rdi+10h]
0x180023d90  jge     short loc_180023DB5
0x180023d92  mov     rax, [rdi+8]
0x180023d96  mov     rcx, [rax+rbx*8]
0x180023d9a  test    rcx, rcx
0x180023d9d  jz      short loc_180023DB5
0x180023d9f  mov     rax, [rcx]
0x180023da2  lea     r8, [rbp+57h+arg_0]
0x180023da6  lea     rdx, _GUID_00020400_0000_0000_c000_000000000046
0x180023dad  mov     rax, [rax]
0x180023db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023db5  lea     rcx, [rsi+78h]; lpCriticalSection
0x180023db9  call    cs:__imp_LeaveCriticalSection
0x180023dbf  mov     rcx, [rbp+57h+arg_0]
0x180023dc3  test    rcx, rcx
0x180023dc6  jz      short loc_180023E20
0x180023dc8  mov     rax, [rcx]
0x180023dcb  lea     rdx, [rbp+57h+var_80]
0x180023dcf  mov     [rsp+0D0h+var_90], 0
0x180023dd8  lea     r8, GUID_NULL
0x180023ddf  mov     [rsp+0D0h+var_98], 0
0x180023de8  mov     r9d, 800h
0x180023dee  mov     [rsp+0D0h+var_A0], 0
0x180023df7  mov     rax, [rax+30h]
0x180023dfb  mov     [rsp+0D0h+var_A8], rdx
0x180023e00  mov     edx, 200h
0x180023e05  mov     [rsp+0D0h+var_B0], r12w
0x180023e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e10  mov     rcx, [rbp+57h+arg_0]
0x180023e14  mov     rax, [rcx]
0x180023e17  mov     rax, [rax+10h]
0x180023e1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e20  add     ebx, r12d
0x180023e23  cmp     ebx, r14d
0x180023e26  jl      loc_180023D7B
0x180023e2c  add     rsp, 0A8h
0x180023e33  pop     r14
0x180023e35  pop     r12
0x180023e37  pop     rdi
0x180023e38  pop     rsi
0x180023e39  pop     rbx
0x180023e3a  pop     rbp
0x180023e3b  retn
```
