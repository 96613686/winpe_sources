# CMemoryTable::CopyWriteRowFromReadRow(ulong,ulong)

- ea: `0x18000ecb8`
- end: `0x18000ee81`
- name: `?CopyWriteRowFromReadRow@CMemoryTable@@AEAAJKK@Z`
- size: `457`
- prototype: `__int64 __fastcall(CMemoryTable *__hidden this, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000e450`
- `0x18000e540`

## callees

- `0x18000ecb8`
- `0x18000f6bc`
- `0x18002e0ca`
- `0x18002e110`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000ee33`
- `ole32!CoTaskMemFree` at `0x18000ee4e`
- `ole32!CoTaskMemFree` at `0x18000ee33`
- `ole32!CoTaskMemFree` at `0x18000ee4e`
- `ole32!CoTaskMemAlloc` at `0x18000ed3a`
- `ole32!CoTaskMemAlloc` at `0x18000ed61`
- `ole32!CoTaskMemAlloc` at `0x18000ed3a`
- `ole32!CoTaskMemAlloc` at `0x18000ed61`

## pseudocode

```c
__int64 __fastcall CMemoryTable::CopyWriteRowFromReadRow(CMemoryTable *this, unsigned int a2, unsigned int a3)
{
  unsigned __int64 v3; // rbp
  _BYTE *v7; // rsi
  int RowFromIndex; // ebx
  _BYTE *v9; // rdi
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // r8
  _BYTE *v13; // r9
  __int64 v14; // rdx
  void *v16; // [rsp+40h] [rbp-2B8h] BYREF
  _BYTE v17[208]; // [rsp+50h] [rbp-2A8h] BYREF
  _BYTE v18[400]; // [rsp+120h] [rbp-1D8h] BYREF

  v3 = *((unsigned int *)this + 9);
  memset_0(v17, 0, 0xC8u);
  memset_0(v18, 0, sizeof(v18));
  v16 = 0;
  if ( (unsigned int)v3 <= 0x32 )
  {
    v9 = v18;
    v7 = v17;
    goto LABEL_7;
  }
  v7 = CoTaskMemAlloc(saturated_mul(v3, 4u));
  if ( !v7 )
    return (unsigned int)-2147024882;
  v9 = CoTaskMemAlloc(saturated_mul((unsigned int)v3, 8u));
  if ( v9 )
  {
LABEL_7:
    RowFromIndex = (*(__int64 (__fastcall **)(char *, _QWORD, _QWORD, _QWORD, _BYTE *, _BYTE *))(*((_QWORD *)this + 1)
                                                                                               + 32LL))(
                     (char *)this + 8,
                     a2,
                     (unsigned int)v3,
                     0,
                     v7,
                     v9);
    if ( RowFromIndex >= 0 )
    {
      v10 = *((_QWORD *)this + 1);
      *((_DWORD *)this + 23) |= 0x20u;
      v11 = (*(__int64 (__fastcall **)(char *, _QWORD, _QWORD, _QWORD, _BYTE *, _BYTE *))(v10 + 88))(
              (char *)this + 8,
              a3,
              (unsigned int)v3,
              0,
              v7,
              v9);
      *((_DWORD *)this + 23) &= ~0x20u;
      RowFromIndex = v11;
      if ( v11 >= 0 )
      {
        RowFromIndex = CMemoryTable::GetRowFromIndex(this, 1u, a3, &v16);
        if ( RowFromIndex >= 0 )
        {
          v12 = 0;
          if ( (_DWORD)v3 )
          {
            v13 = v16;
            do
            {
              v14 = *(unsigned __int16 *)(*((_QWORD *)this + 8) + 8 * v12);
              v12 = (unsigned int)(v12 + 1);
              v13[v14] &= ~1u;
            }
            while ( (unsigned int)v12 < (unsigned int)v3 );
          }
        }
      }
    }
    if ( !v7 )
      goto LABEL_16;
    goto LABEL_14;
  }
  RowFromIndex = -2147024882;
LABEL_14:
  if ( v7 != v17 )
    CoTaskMemFree(v7);
LABEL_16:
  if ( v9 && v9 != v18 )
    CoTaskMemFree(v9);
  return (unsigned int)RowFromIndex;
}

```

## disassembly

```asm
0x18000ecb8  mov     [rsp+arg_18], rbx
0x18000ecbd  push    rbp
0x18000ecbe  push    rsi
0x18000ecbf  push    rdi
0x18000ecc0  push    r12
0x18000ecc2  push    r13
0x18000ecc4  push    r14
0x18000ecc6  push    r15
0x18000ecc8  sub     rsp, 2C0h
0x18000eccf  mov     rax, cs:__security_cookie
0x18000ecd6  xor     rax, rsp
0x18000ecd9  mov     [rsp+2F8h+var_48], rax
0x18000ece1  mov     ebp, [rcx+24h]
0x18000ece4  mov     r12d, r8d
0x18000ece7  mov     r13d, edx
0x18000ecea  mov     r14, rcx
0x18000eced  xor     edx, edx; Val
0x18000ecef  lea     rcx, [rsp+2F8h+var_2A8]; void *
0x18000ecf4  mov     r8d, 0C8h; Size
0x18000ecfa  call    memset_0
0x18000ecff  xor     edx, edx; Val
0x18000ed01  lea     rcx, [rsp+2F8h+var_1D8]; void *
0x18000ed09  mov     r8d, 190h; Size
0x18000ed0f  call    memset_0
0x18000ed14  mov     [rsp+2F8h+var_2B8], 0
0x18000ed1d  cmp     ebp, 32h ; '2'
0x18000ed20  jbe     short loc_18000ED79
0x18000ed22  mov     eax, 4
0x18000ed27  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18000ed2e  mul     rbp
0x18000ed31  mov     ebx, ebp
0x18000ed33  cmovb   rax, rdi
0x18000ed37  mov     rcx, rax; cb
0x18000ed3a  call    cs:__imp_CoTaskMemAlloc
0x18000ed40  mov     rsi, rax
0x18000ed43  test    rax, rax
0x18000ed46  jnz     short loc_18000ED52
0x18000ed48  mov     ebx, 8007000Eh
0x18000ed4d  jmp     loc_18000EE54
0x18000ed52  mov     eax, 8
0x18000ed57  mul     rbx
0x18000ed5a  cmovb   rax, rdi
0x18000ed5e  mov     rcx, rax; cb
0x18000ed61  call    cs:__imp_CoTaskMemAlloc
0x18000ed67  mov     rdi, rax
0x18000ed6a  test    rax, rax
0x18000ed6d  jnz     short loc_18000ED86
0x18000ed6f  mov     ebx, 8007000Eh
0x18000ed74  jmp     loc_18000EE26
0x18000ed79  lea     rdi, [rsp+2F8h+var_1D8]
0x18000ed81  lea     rsi, [rsp+2F8h+var_2A8]
0x18000ed86  lea     r15, [r14+8]
0x18000ed8a  mov     [rsp+2F8h+var_2D0], rdi
0x18000ed8f  mov     rax, [r15]
0x18000ed92  xor     r9d, r9d
0x18000ed95  mov     r8d, ebp
0x18000ed98  mov     [rsp+2F8h+var_2D8], rsi
0x18000ed9d  mov     edx, r13d
0x18000eda0  mov     rcx, r15
0x18000eda3  mov     rax, [rax+20h]
0x18000eda7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edac  mov     ebx, eax
0x18000edae  test    eax, eax
0x18000edb0  js      short loc_18000EE21
0x18000edb2  mov     rax, [r15]
0x18000edb5  xor     r9d, r9d
0x18000edb8  or      dword ptr [r14+5Ch], 20h
0x18000edbd  mov     r8d, ebp
0x18000edc0  mov     [rsp+2F8h+var_2D0], rdi
0x18000edc5  mov     edx, r12d
0x18000edc8  mov     rcx, r15
0x18000edcb  mov     [rsp+2F8h+var_2D8], rsi
0x18000edd0  mov     rax, [rax+58h]
0x18000edd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edd9  and     dword ptr [r14+5Ch], 0FFFFFFDFh
0x18000edde  mov     ebx, eax
0x18000ede0  test    eax, eax
0x18000ede2  js      short loc_18000EE21
0x18000ede4  lea     r9, [rsp+2F8h+var_2B8]; void **
0x18000ede9  mov     r8d, r12d; unsigned int
0x18000edec  mov     edx, 1; unsigned int
0x18000edf1  mov     rcx, r14; this
0x18000edf4  call    ?GetRowFromIndex@CMemoryTable@@AEAAJKKPEAPEAX@Z; CMemoryTable::GetRowFromIndex(ulong,ulong,void * *)
0x18000edf9  mov     ebx, eax
0x18000edfb  test    eax, eax
0x18000edfd  js      short loc_18000EE21
0x18000edff  xor     r8d, r8d
0x18000ee02  test    ebp, ebp
0x18000ee04  jz      short loc_18000EE21
0x18000ee06  mov     r9, [rsp+2F8h+var_2B8]
0x18000ee0b  mov     rax, [r14+40h]
0x18000ee0f  movzx   edx, word ptr [rax+r8*8]
0x18000ee14  inc     r8d
0x18000ee17  and     byte ptr [rdx+r9], 0FEh
0x18000ee1c  cmp     r8d, ebp
0x18000ee1f  jb      short loc_18000EE0B
0x18000ee21  test    rsi, rsi
0x18000ee24  jz      short loc_18000EE39
0x18000ee26  lea     rax, [rsp+2F8h+var_2A8]
0x18000ee2b  cmp     rsi, rax
0x18000ee2e  jz      short loc_18000EE39
0x18000ee30  mov     rcx, rsi; pv
0x18000ee33  call    cs:__imp_CoTaskMemFree
0x18000ee39  test    rdi, rdi
0x18000ee3c  jz      short loc_18000EE54
0x18000ee3e  lea     rax, [rsp+2F8h+var_1D8]
0x18000ee46  cmp     rdi, rax
0x18000ee49  jz      short loc_18000EE54
0x18000ee4b  mov     rcx, rdi; pv
0x18000ee4e  call    cs:__imp_CoTaskMemFree
0x18000ee54  mov     eax, ebx
0x18000ee56  mov     rcx, [rsp+2F8h+var_48]
0x18000ee5e  xor     rcx, rsp; StackCookie
0x18000ee61  call    __security_check_cookie
0x18000ee66  mov     rbx, [rsp+2F8h+arg_18]
0x18000ee6e  add     rsp, 2C0h
0x18000ee75  pop     r15
0x18000ee77  pop     r14
0x18000ee79  pop     r13
0x18000ee7b  pop     r12
0x18000ee7d  pop     rdi
0x18000ee7e  pop     rsi
0x18000ee7f  pop     rbp
0x18000ee80  retn
```
