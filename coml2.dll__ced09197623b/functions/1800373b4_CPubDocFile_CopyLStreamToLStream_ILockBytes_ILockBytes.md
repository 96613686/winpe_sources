# CPubDocFile::CopyLStreamToLStream(ILockBytes *,ILockBytes *)

- ea: `0x1800373b4`
- end: `0x1800375c2`
- name: `?CopyLStreamToLStream@CPubDocFile@@IEAAJPEAUILockBytes@@0@Z`
- size: `526`
- prototype: `__int64 __fastcall(CPubDocFile *__hidden this, struct ILockBytes *, struct ILockBytes *)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000745c`
- `0x1800362a4`

## callees

- `0x1800373b4`
- `0x180042800`
- `0x180043100`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037412`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037412`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003756c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003756c`

## pseudocode

```c
__int64 __fastcall CPubDocFile::CopyLStreamToLStream(CPubDocFile *this, struct ILockBytes *a2, struct ILockBytes *a3)
{
  unsigned __int64 v3; // rbx
  unsigned int v6; // edi
  void *v7; // r15
  int v8; // esi
  unsigned int v9; // r14d
  int v10; // r12d
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rax
  int v15; // [rsp+34h] [rbp-55h] BYREF
  CPubDocFile *v16; // [rsp+38h] [rbp-51h]
  struct ILockBytes *v17; // [rsp+40h] [rbp-49h]
  _BYTE v18[16]; // [rsp+50h] [rbp-39h] BYREF
  __int64 v19; // [rsp+60h] [rbp-29h]

  v3 = 0;
  v17 = a3;
  v16 = this;
  v15 = 0;
  memset_0(v18, 0, 0x50u);
  v6 = 0x10000;
  while ( 1 )
  {
    v7 = CoTaskMemAlloc(v6);
    if ( v7 )
      break;
    v6 >>= 1;
    if ( v6 < 0x200 )
    {
      v8 = -2147287032;
      goto LABEL_22;
    }
  }
  v8 = ((__int64 (__fastcall *)(struct ILockBytes *, _BYTE *, __int64))a2->lpVtbl->Stat)(a2, v18, 1);
  if ( v8 >= 0 )
  {
    v8 = ((__int64 (__fastcall *)(struct ILockBytes *, __int64))a3->lpVtbl->SetSize)(a3, v19);
    if ( v8 >= 0 )
    {
      v9 = 0;
      while ( 1 )
      {
        if ( v3 + v6 <= 0x7FFFFF00 || v3 > 0x7FFFFFE3 )
        {
          v10 = 0;
        }
        else
        {
          v10 = 1;
          v9 = v6;
          v12 = *((_QWORD *)v16 + 20);
          v13 = v12 ? v12 + *(_QWORD *)NtCurrentTeb()->ReservedForOle : 0LL;
          v6 = ((*(_DWORD *)(v13 + 56) & 0x80000) != 0 ? 2147479552 : 2147483136) - v3;
        }
        v11 = 0;
        if ( v6 )
        {
          v8 = ((__int64 (__fastcall *)(struct ILockBytes *, unsigned __int64, void *, _QWORD, int *))a2->lpVtbl->ReadAt)(
                 a2,
                 v3,
                 v7,
                 v6,
                 &v15);
          if ( v8 < 0 )
            goto LABEL_22;
          if ( !v15 )
            goto LABEL_22;
          v8 = ((__int64 (__fastcall *)(struct ILockBytes *, unsigned __int64, void *))v17->lpVtbl->WriteAt)(
                 v17,
                 v3,
                 v7);
          if ( v8 < 0 )
            goto LABEL_22;
          v11 = 0;
          if ( v15 )
            break;
        }
        if ( v10 )
        {
          v11 = v9;
          v6 = v9;
        }
        v3 += v11;
      }
      v8 = -2147287011;
    }
  }
LABEL_22:
  CoTaskMemFree(v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800373b4  mov     [rsp-8+arg_0], rbx
0x1800373b9  push    rbp
0x1800373ba  push    rsi
0x1800373bb  push    rdi
0x1800373bc  push    r12
0x1800373be  push    r13
0x1800373c0  push    r14
0x1800373c2  push    r15
0x1800373c4  lea     rbp, [rsp-27h]
0x1800373c9  sub     rsp, 0B0h
0x1800373d0  mov     rax, cs:__security_cookie
0x1800373d7  xor     rax, rsp
0x1800373da  mov     [rbp+57h+var_40], rax
0x1800373de  xor     ebx, ebx
0x1800373e0  mov     [rbp+57h+var_A0], r8
0x1800373e4  mov     r14, r8
0x1800373e7  mov     [rbp+57h+var_A8], rcx
0x1800373eb  mov     r13, rdx
0x1800373ee  mov     [rbp+57h+var_AC], 0
0x1800373f5  xor     edx, edx; Val
0x1800373f7  mov     [rbp+57h+var_B0], 0
0x1800373fe  lea     r8d, [rbx+50h]; Size
0x180037402  lea     rcx, [rbp+57h+var_90]; void *
0x180037406  call    memset_0
0x18003740b  mov     edi, 10000h
0x180037410  mov     ecx, edi; cb
0x180037412  call    cs:__imp_CoTaskMemAlloc
0x180037418  mov     r15, rax
0x18003741b  test    rax, rax
0x18003741e  jz      loc_180037556
0x180037424  mov     rax, [r13+0]
0x180037428  lea     rdx, [rbp+57h+var_90]
0x18003742c  mov     r8d, 1
0x180037432  mov     rcx, r13
0x180037435  mov     rax, [rax+48h]
0x180037439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003743e  mov     esi, eax
0x180037440  test    eax, eax
0x180037442  js      loc_180037569
0x180037448  mov     rax, [r14]
0x18003744b  mov     rcx, r14
0x18003744e  mov     rdx, [rbp+57h+var_80]
0x180037452  mov     rax, [rax+30h]
0x180037456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003745b  mov     esi, eax
0x18003745d  test    eax, eax
0x18003745f  js      loc_180037569
0x180037465  xor     r14d, r14d
0x180037468  mov     eax, edi
0x18003746a  add     rax, rbx
0x18003746d  cmp     rax, 7FFFFF00h
0x180037473  ja      loc_18003759B
0x180037479  xor     r12d, r12d
0x18003747c  xor     eax, eax
0x18003747e  mov     [rbp+57h+var_B0], eax
0x180037481  test    edi, edi
0x180037483  jz      short loc_1800374F3
0x180037485  mov     rax, [r13+0]
0x180037489  lea     rcx, [rbp+57h+var_AC]
0x18003748d  mov     [rsp+0E0h+var_C0], rcx
0x180037492  mov     r9d, edi
0x180037495  mov     r8, r15
0x180037498  mov     rdx, rbx
0x18003749b  mov     rcx, r13
0x18003749e  mov     rax, [rax+18h]
0x1800374a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800374a7  mov     esi, eax
0x1800374a9  test    eax, eax
0x1800374ab  js      loc_180037569
0x1800374b1  mov     r9d, [rbp+57h+var_AC]
0x1800374b5  test    r9d, r9d
0x1800374b8  jz      loc_180037569
0x1800374be  mov     rcx, [rbp+57h+var_A0]
0x1800374c2  lea     rdx, [rbp+57h+var_B0]
0x1800374c6  mov     [rsp+0E0h+var_C0], rdx
0x1800374cb  mov     r8, r15
0x1800374ce  mov     rdx, rbx
0x1800374d1  mov     rax, [rcx]
0x1800374d4  mov     rax, [rax+20h]
0x1800374d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800374dd  mov     esi, eax
0x1800374df  test    eax, eax
0x1800374e1  js      loc_180037569
0x1800374e7  mov     eax, [rbp+57h+var_B0]
0x1800374ea  cmp     [rbp+57h+var_AC], eax
0x1800374ed  jnz     loc_1800375BB
0x1800374f3  test    r12d, r12d
0x1800374f6  jnz     loc_1800375AD
0x1800374fc  add     rbx, rax
0x1800374ff  jmp     loc_180037468
0x180037504  mov     rax, [rbp+57h+var_A8]
0x180037508  mov     r12d, 1
0x18003750e  mov     r14d, edi
0x180037511  mov     rdx, [rax+0A0h]
0x180037518  test    rdx, rdx
0x18003751b  jz      short loc_180037552
0x18003751d  mov     rax, gs:30h
0x180037526  mov     rcx, [rax+1758h]
0x18003752d  mov     rax, [rcx]
0x180037530  add     rax, rdx
0x180037533  mov     eax, [rax+38h]
0x180037536  and     eax, 80000h
0x18003753b  neg     eax
0x18003753d  sbb     edi, edi
0x18003753f  and     edi, 0FFFFF200h
0x180037545  add     edi, 7FFFFE00h
0x18003754b  sub     edi, ebx
0x18003754d  jmp     loc_18003747C
0x180037552  xor     eax, eax
0x180037554  jmp     short loc_180037533
0x180037556  shr     edi, 1
0x180037558  cmp     edi, 200h
0x18003755e  jnb     loc_180037410
0x180037564  mov     esi, 80030008h
0x180037569  mov     rcx, r15; pv
0x18003756c  call    cs:__imp_CoTaskMemFree
0x180037572  mov     eax, esi
0x180037574  mov     rcx, [rbp+57h+var_40]
0x180037578  xor     rcx, rsp; StackCookie
0x18003757b  call    __security_check_cookie
0x180037580  mov     rbx, [rsp+0E0h+arg_0]
0x180037588  add     rsp, 0B0h
0x18003758f  pop     r15
0x180037591  pop     r14
0x180037593  pop     r13
0x180037595  pop     r12
0x180037597  pop     rdi
0x180037598  pop     rsi
0x180037599  pop     rbp
0x18003759a  retn
0x18003759b  cmp     rbx, 7FFFFFE3h
0x1800375a2  ja      loc_180037479
0x1800375a8  jmp     loc_180037504
0x1800375ad  mov     eax, r14d
0x1800375b0  mov     edi, r14d
0x1800375b3  mov     [rbp+57h+var_B0], eax
0x1800375b6  jmp     loc_1800374FC
0x1800375bb  mov     esi, 8003001Dh
0x1800375c0  jmp     short loc_180037569
```
