# CProxy_DDiscFormat2EraseEvents<CMsftDiscFormat2Erase>::Fire_Update(long,long)

- ea: `0x180026b20`
- end: `0x180026c91`
- name: `?Fire_Update@?$CProxy_DDiscFormat2EraseEvents@VCMsftDiscFormat2Erase@@@@QEAAXJJ@Z`
- size: `369`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800263d0`
- `0x180027df0`

## callees

- `0x180026b20`
- `0x180049880`
- `0x18004a010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180026b6c`
- `OLEAUT32!__imp_VariantInit` at `0x180026b76`
- `OLEAUT32!__imp_VariantInit` at `0x180026b80`
- `OLEAUT32!__imp_VariantInit` at `0x180026b6c`
- `OLEAUT32!__imp_VariantInit` at `0x180026b76`
- `OLEAUT32!__imp_VariantInit` at `0x180026b80`
- `KERNEL32!EnterCriticalSection` at `0x180026bd1`
- `KERNEL32!EnterCriticalSection` at `0x180026bd1`
- `KERNEL32!LeaveCriticalSection` at `0x180026c02`
- `KERNEL32!LeaveCriticalSection` at `0x180026c02`

## pseudocode

```c
void __fastcall CProxy_DDiscFormat2EraseEvents<CMsftDiscFormat2Erase>::Fire_Update(__int64 a1, LONG a2, LONG a3)
{
  LONGLONG v6; // r14
  int v7; // r15d
  __int64 v8; // rbx
  struct _RTL_CRITICAL_SECTION *v9; // rdi
  void (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // rcx
  int v11; // [rsp+20h] [rbp-89h]
  __int64 v12; // [rsp+50h] [rbp-59h] BYREF
  __int128 v13; // [rsp+58h] [rbp-51h] BYREF
  __int64 v14; // [rsp+68h] [rbp-41h]
  VARIANTARG v15; // [rsp+70h] [rbp-39h] BYREF
  VARIANTARG v16; // [rsp+88h] [rbp-21h] BYREF
  VARIANTARG pvarg; // [rsp+A0h] [rbp-9h] BYREF

  v14 = 0;
  v6 = (a1 - 24) & -(__int64)(a1 != 0);
  v13 = 0;
  VariantInit(&pvarg);
  VariantInit(&v16);
  VariantInit(&v15);
  v7 = *(_DWORD *)(a1 + 16);
  v16.lVal = a2;
  v8 = 0;
  pvarg.vt = 9;
  pvarg.llVal = v6;
  v15.lVal = a3;
  v16.vt = 3;
  *(_QWORD *)&v13 = &v15;
  v15.vt = 3;
  LODWORD(v14) = 3;
  if ( v7 > 0 )
  {
    v9 = (struct _RTL_CRITICAL_SECTION *)(v6 + 112);
    do
    {
      v12 = 0;
      EnterCriticalSection(v9);
      if ( (int)v8 < *(_DWORD *)(a1 + 16) )
      {
        v10 = *(void (__fastcall ****)(_QWORD, GUID *, __int64 *))(*(_QWORD *)(a1 + 8) + 8 * v8);
        if ( v10 )
          (**v10)(v10, &GUID_00020400_0000_0000_c000_000000000046, &v12);
      }
      LeaveCriticalSection(v9);
      if ( v12 )
      {
        LOWORD(v11) = 1;
        (*(void (__fastcall **)(__int64, __int64, GUID *, __int64, int, __int128 *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v12 + 48LL))(
          v12,
          512,
          &GUID_NULL,
          2048,
          v11,
          &v13,
          0,
          0,
          0);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      }
      v8 = (unsigned int)(v8 + 1);
    }
    while ( (int)v8 < v7 );
  }
}

```

## disassembly

```asm
0x180026b20  push    rbp
0x180026b22  push    rbx
0x180026b23  push    rsi
0x180026b24  push    rdi
0x180026b25  push    r14
0x180026b27  push    r15
0x180026b29  lea     rbp, [rsp-2Fh]
0x180026b2e  sub     rsp, 0D8h
0x180026b35  mov     rax, cs:__security_cookie
0x180026b3c  xor     rax, rsp
0x180026b3f  mov     [rbp+57h+var_40], rax
0x180026b43  mov     rax, rcx
0x180026b46  lea     r9, [rcx-18h]
0x180026b4a  neg     rax
0x180026b4d  mov     rsi, rcx
0x180026b50  xorps   xmm0, xmm0
0x180026b53  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180026b57  sbb     r14, r14
0x180026b5a  mov     edi, r8d
0x180026b5d  xor     eax, eax
0x180026b5f  mov     ebx, edx
0x180026b61  mov     [rbp+57h+var_98], rax
0x180026b65  and     r14, r9
0x180026b68  movups  [rbp+57h+var_A8], xmm0
0x180026b6c  call    cs:__imp_VariantInit
0x180026b72  lea     rcx, [rbp+57h+var_78]; pvarg
0x180026b76  call    cs:__imp_VariantInit
0x180026b7c  lea     rcx, [rbp+57h+var_90]; pvarg
0x180026b80  call    cs:__imp_VariantInit
0x180026b86  mov     r15d, [rsi+10h]
0x180026b8a  mov     eax, 9
0x180026b8f  mov     dword ptr [rbp+57h+var_78+8], ebx
0x180026b92  xor     ebx, ebx
0x180026b94  mov     word ptr [rbp+57h+pvarg], ax
0x180026b98  mov     qword ptr [rbp+57h+pvarg+8], r14
0x180026b9c  mov     dword ptr [rbp+57h+var_90+8], edi
0x180026b9f  lea     ecx, [rax-6]
0x180026ba2  mov     word ptr [rbp+57h+var_78], cx
0x180026ba6  lea     rax, [rbp+57h+var_90]
0x180026baa  mov     qword ptr [rbp+57h+var_A8], rax
0x180026bae  mov     word ptr [rbp+57h+var_90], cx
0x180026bb2  mov     dword ptr [rbp+57h+var_98], ecx
0x180026bb5  test    r15d, r15d
0x180026bb8  jle     loc_180026C75
0x180026bbe  lea     rdi, [r14+70h]
0x180026bc2  lea     r14d, [rcx-2]
0x180026bc6  mov     rcx, rdi; lpCriticalSection
0x180026bc9  mov     [rbp+57h+var_B0], 0
0x180026bd1  call    cs:__imp_EnterCriticalSection
0x180026bd7  cmp     ebx, [rsi+10h]
0x180026bda  jge     short loc_180026BFF
0x180026bdc  mov     rax, [rsi+8]
0x180026be0  mov     rcx, [rax+rbx*8]
0x180026be4  test    rcx, rcx
0x180026be7  jz      short loc_180026BFF
0x180026be9  mov     rax, [rcx]
0x180026bec  lea     r8, [rbp+57h+var_B0]
0x180026bf0  lea     rdx, _GUID_00020400_0000_0000_c000_000000000046
0x180026bf7  mov     rax, [rax]
0x180026bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026bff  mov     rcx, rdi; lpCriticalSection
0x180026c02  call    cs:__imp_LeaveCriticalSection
0x180026c08  mov     rcx, [rbp+57h+var_B0]
0x180026c0c  test    rcx, rcx
0x180026c0f  jz      short loc_180026C69
0x180026c11  mov     rax, [rcx]
0x180026c14  lea     rdx, [rbp+57h+var_A8]
0x180026c18  mov     [rsp+100h+var_C0], 0
0x180026c21  lea     r8, GUID_NULL
0x180026c28  mov     [rsp+100h+var_C8], 0
0x180026c31  mov     r9d, 800h
0x180026c37  mov     [rsp+100h+var_D0], 0
0x180026c40  mov     rax, [rax+30h]
0x180026c44  mov     [rsp+100h+var_D8], rdx
0x180026c49  mov     edx, 200h
0x180026c4e  mov     [rsp+100h+var_E0], r14w
0x180026c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c59  mov     rcx, [rbp+57h+var_B0]
0x180026c5d  mov     rax, [rcx]
0x180026c60  mov     rax, [rax+10h]
0x180026c64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c69  add     ebx, r14d
0x180026c6c  cmp     ebx, r15d
0x180026c6f  jl      loc_180026BC6
0x180026c75  mov     rcx, [rbp+57h+var_40]
0x180026c79  xor     rcx, rsp; StackCookie
0x180026c7c  call    __security_check_cookie
0x180026c81  add     rsp, 0D8h
0x180026c88  pop     r15
0x180026c8a  pop     r14
0x180026c8c  pop     rdi
0x180026c8d  pop     rsi
0x180026c8e  pop     rbx
0x180026c8f  pop     rbp
0x180026c90  retn
```
