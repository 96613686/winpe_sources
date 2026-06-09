# WfpSwprintf

- ea: `0x180010a00`
- end: `0x180010c8d`
- name: `WfpSwprintf`
- size: `653`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800026e6`
- `0x18000ee60`
- `0x18000eed4`
- `0x180010a00`
- `0x180010e48`
- `0x180010ee8`
- `0x180010f48`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180010ae8`
- `msvcrt!_vsnwprintf` at `0x180010ae8`

## string_xrefs

- `0x180010a6a`: `WfpStringCreate`

## pseudocode

```c
__int64 WfpSwprintf(__int64 a1, const wchar_t *a2, ...)
{
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 result; // rax
  wchar_t *v6; // r12
  __int64 v7; // r13
  unsigned __int64 v8; // r14
  unsigned __int64 v9; // rsi
  wchar_t *v10; // r15
  unsigned __int64 v11; // rdi
  int v12; // eax
  int v13; // edx
  __int64 v14; // rcx
  unsigned __int64 v15; // rdi
  __int64 v16; // r14
  __int64 v17; // rax
  SIZE_T v18; // rsi
  __int64 v19; // rax
  const void *v20; // rbp
  __int64 v21; // rax
  __int64 v22; // rax
  _QWORD v23[10]; // [rsp+28h] [rbp-50h] BYREF
  va_list va; // [rsp+90h] [rbp+18h] BYREF

  va_start(va, a2);
  v23[0] = 0;
  if ( !*(_QWORD *)a1 )
  {
    *(_OWORD *)a1 = 0;
    *(_OWORD *)(a1 + 16) = 0;
    v3 = WfpMemAlloc(0x100u, 0);
    if ( v3 && (v4 = WfpReportError(v3, "WfpPoolAllocNonPaged")) != 0 )
    {
      if ( WfpReportError(v4, "WfpStringCreate") )
      {
LABEL_5:
        WfpMemFree(a1);
        result = 0xFFFFFFFFLL;
        *(_OWORD *)a1 = 0;
        *(_OWORD *)(a1 + 16) = 0;
        return result;
      }
    }
    else
    {
      *(_QWORD *)(a1 + 16) = *(_QWORD *)a1;
      *(_QWORD *)(a1 + 8) = 256;
      *(_QWORD *)(a1 + 24) = 256;
    }
  }
  v6 = 0;
  v7 = 0;
  while ( 1 )
  {
    v8 = *(_QWORD *)(a1 + 24);
    v9 = v8 >> 1;
    if ( (v8 >> 1) - 1 <= 0x7FFFFFFE )
    {
      v10 = *(wchar_t **)(a1 + 16);
      v11 = v9 - 1;
      v12 = _vsnwprintf(v10, v9 - 1, a2, va);
      if ( v12 < 0 || v12 > v11 )
      {
        v13 = -2147024774;
      }
      else
      {
        v13 = 0;
        if ( v12 != v11 )
        {
          v11 = v12;
LABEL_15:
          v6 = &v10[v11];
          v7 = (v8 & 1) + 2 * (v9 - v11);
          goto LABEL_16;
        }
      }
      v10[v11] = 0;
      goto LABEL_15;
    }
    v13 = -2147024809;
LABEL_16:
    result = 0;
    v14 = v13;
    if ( v13 >= 0 )
      v14 = 0;
    if ( !v14 )
      break;
    v15 = *(_QWORD *)(a1 + 8);
    v16 = *(_QWORD *)(a1 + 24);
    if ( v15 <= 0xFFFFFFFFFFFFFEFFuLL )
    {
      v18 = v15 + 256;
    }
    else
    {
      v17 = WfpReportSysErrorAsNtStatus(v14, "WfpSizeTAdd", 3221225621LL);
      v18 = 0;
      if ( v17 )
      {
        v19 = WfpReportError(v17, "WfpSizeTAdd");
        if ( v19 )
          goto LABEL_31;
      }
    }
    if ( v18 <= 0xFFFF )
    {
      v20 = *(const void **)a1;
      v23[0] = *(_QWORD *)a1;
      v21 = WfpMemAlloc(v18, 0);
      if ( v21 && (v22 = WfpReportError(v21, "WfpPoolAllocNonPaged")) != 0 )
      {
        v19 = WfpReportError(v22, "WfpMemReAllocNonPaged");
        if ( !v19 )
          goto LABEL_34;
LABEL_31:
        if ( WfpReportError(v19, "WfpStringExpand") )
          goto LABEL_5;
      }
      else
      {
        memcpy_0(0, v20, v18 - 256);
        WfpMemFree(v23);
LABEL_34:
        *(_QWORD *)(a1 + 8) += 256LL;
        *(_QWORD *)(a1 + 24) += 256LL;
        *(_QWORD *)a1 = 0;
        *(_QWORD *)(a1 + 16) = v15 - v16;
      }
    }
    else
    {
      v19 = WfpReportSysErrorAsWinError(v14, "WfpStringExpand", 87);
      if ( v19 )
        goto LABEL_31;
    }
  }
  *(_QWORD *)(a1 + 24) = v7;
  *(_QWORD *)(a1 + 16) = v6;
  return result;
}

```

## disassembly

```asm
0x180010a00  mov     rax, rsp
0x180010a03  mov     [rax+10h], rdx
0x180010a07  mov     [rax+18h], r8
0x180010a0b  mov     [rax+20h], r9
0x180010a0f  push    rbx
0x180010a10  push    rbp
0x180010a11  push    rsi
0x180010a12  push    rdi
0x180010a13  push    r12
0x180010a15  push    r13
0x180010a17  push    r14
0x180010a19  push    r15
0x180010a1b  sub     rsp, 38h
0x180010a1f  mov     rbx, rcx
0x180010a22  mov     qword ptr [rax-50h], 0
0x180010a2a  lea     rcx, [rax+18h]
0x180010a2e  mov     r15d, 100h
0x180010a34  cmp     qword ptr [rbx], 0
0x180010a38  jnz     short loc_180010AAF
0x180010a3a  xorps   xmm0, xmm0
0x180010a3d  mov     r8, rbx
0x180010a40  movups  xmmword ptr [rbx], xmm0
0x180010a43  xor     edx, edx; dwFlags
0x180010a45  mov     ecx, r15d; dwBytes
0x180010a48  movups  xmmword ptr [rbx+10h], xmm0
0x180010a4c  call    WfpMemAlloc
0x180010a51  test    rax, rax
0x180010a54  jz      short loc_180010A98
0x180010a56  lea     rdx, aWfppoolallocno; "WfpPoolAllocNonPaged"
0x180010a5d  mov     rcx, rax
0x180010a60  call    WfpReportError
0x180010a65  test    rax, rax
0x180010a68  jz      short loc_180010A98
0x180010a6a  lea     rdx, aWfpstringcreat; "WfpStringCreate"
0x180010a71  mov     rcx, rax
0x180010a74  call    WfpReportError
0x180010a79  test    rax, rax
0x180010a7c  jz      short loc_180010AA7
0x180010a7e  mov     rcx, rbx
0x180010a81  call    WfpMemFree
0x180010a86  xorps   xmm0, xmm0
0x180010a89  or      eax, 0FFFFFFFFh
0x180010a8c  movups  xmmword ptr [rbx], xmm0
0x180010a8f  movups  xmmword ptr [rbx+10h], xmm0
0x180010a93  jmp     loc_180010C7C
0x180010a98  mov     rax, [rbx]
0x180010a9b  mov     [rbx+10h], rax
0x180010a9f  mov     [rbx+8], r15
0x180010aa3  mov     [rbx+18h], r15
0x180010aa7  lea     rcx, [rsp+78h+arg_10]
0x180010aaf  xor     r12d, r12d
0x180010ab2  xor     r13d, r13d
0x180010ab5  mov     r14, [rbx+18h]
0x180010ab9  mov     rsi, r14
0x180010abc  shr     rsi, 1
0x180010abf  lea     rax, [rsi-1]
0x180010ac3  cmp     rax, 7FFFFFFEh
0x180010ac9  ja      loc_180010B8C
0x180010acf  mov     r15, [rbx+10h]
0x180010ad3  lea     rdi, [rsi-1]
0x180010ad7  mov     r8, [rsp+78h+Format]; Format
0x180010adf  mov     r9, rcx; Args
0x180010ae2  mov     rdx, rdi; BufferCount
0x180010ae5  mov     rcx, r15; Buffer
0x180010ae8  call    cs:__imp__vsnwprintf
0x180010aee  test    eax, eax
0x180010af0  js      short loc_180010B05
0x180010af2  cdqe
0x180010af4  cmp     rax, rdi
0x180010af7  ja      short loc_180010B05
0x180010af9  xor     edx, edx
0x180010afb  cmp     rax, rdi
0x180010afe  jz      short loc_180010B0A
0x180010b00  mov     rdi, rax
0x180010b03  jmp     short loc_180010B11
0x180010b05  mov     edx, 8007007Ah
0x180010b0a  xor     eax, eax
0x180010b0c  mov     [r15+rdi*2], ax
0x180010b11  sub     rsi, rdi
0x180010b14  lea     rax, [r15+rdi*2]
0x180010b18  test    edx, edx
0x180010b1a  jns     short loc_180010B24
0x180010b1c  cmp     edx, 8007007Ah
0x180010b22  jnz     short loc_180010B2F
0x180010b24  and     r14d, 1
0x180010b28  mov     r12, rax
0x180010b2b  lea     r13, [r14+rsi*2]
0x180010b2f  mov     r15d, 100h
0x180010b35  xor     eax, eax
0x180010b37  movsxd  rcx, edx
0x180010b3a  test    edx, edx
0x180010b3c  cmovns  rcx, rax
0x180010b40  test    rcx, rcx
0x180010b43  jz      loc_180010C74
0x180010b49  mov     rdi, [rbx+8]
0x180010b4d  mov     r14, [rbx+18h]
0x180010b51  cmp     rdi, 0FFFFFFFFFFFFFEFFh
0x180010b58  jbe     short loc_180010B93
0x180010b5a  mov     r8d, 0C0000095h
0x180010b60  lea     rdx, aWfpsizetadd; "WfpSizeTAdd"
0x180010b67  call    WfpReportSysErrorAsNtStatus
0x180010b6c  xor     esi, esi
0x180010b6e  test    rax, rax
0x180010b71  jz      short loc_180010B9A
0x180010b73  lea     rdx, aWfpsizetadd; "WfpSizeTAdd"
0x180010b7a  mov     rcx, rax
0x180010b7d  call    WfpReportError
0x180010b82  test    rax, rax
0x180010b85  jz      short loc_180010B9A
0x180010b87  jmp     loc_180010C17
0x180010b8c  mov     edx, 80070057h
0x180010b91  jmp     short loc_180010B35
0x180010b93  lea     rsi, [rdi+100h]
0x180010b9a  cmp     rsi, 0FFFFh
0x180010ba1  jbe     short loc_180010BC8
0x180010ba3  mov     r8d, 57h ; 'W'
0x180010ba9  lea     rdx, aWfpstringexpan; "WfpStringExpand"
0x180010bb0  call    WfpReportSysErrorAsWinError
0x180010bb5  lea     rcx, [rsp+78h+arg_10]
0x180010bbd  test    rax, rax
0x180010bc0  jz      loc_180010AB5
0x180010bc6  jmp     short loc_180010C17
0x180010bc8  mov     rbp, [rbx]
0x180010bcb  lea     r8, [rsp+78h+var_58]
0x180010bd0  xor     edx, edx; dwFlags
0x180010bd2  mov     [rsp+78h+var_50], rbp
0x180010bd7  mov     rcx, rsi; dwBytes
0x180010bda  mov     [rsp+78h+var_58], 0
0x180010be3  call    WfpMemAlloc
0x180010be8  test    rax, rax
0x180010beb  jz      short loc_180010C31
0x180010bed  lea     rdx, aWfppoolallocno; "WfpPoolAllocNonPaged"
0x180010bf4  mov     rcx, rax
0x180010bf7  call    WfpReportError
0x180010bfc  test    rax, rax
0x180010bff  jz      short loc_180010C31
0x180010c01  lea     rdx, aWfpmemreallocn; "WfpMemReAllocNonPaged"
0x180010c08  mov     rcx, rax
0x180010c0b  xor     esi, esi
0x180010c0d  call    WfpReportError
0x180010c12  test    rax, rax
0x180010c15  jz      short loc_180010C52
0x180010c17  lea     rdx, aWfpstringexpan; "WfpStringExpand"
0x180010c1e  mov     rcx, rax
0x180010c21  call    WfpReportError
0x180010c26  test    rax, rax
0x180010c29  jnz     loc_180010A7E
0x180010c2f  jmp     short loc_180010C67
0x180010c31  lea     r8, [rsi-100h]; Size
0x180010c38  mov     rdx, rbp; Src
0x180010c3b  mov     rsi, [rsp+78h+var_58]
0x180010c40  mov     rcx, rsi; void *
0x180010c43  call    memcpy_0
0x180010c48  lea     rcx, [rsp+78h+var_50]
0x180010c4d  call    WfpMemFree
0x180010c52  add     [rbx+8], r15
0x180010c56  sub     rdi, r14
0x180010c59  add     [rbx+18h], r15
0x180010c5d  add     rdi, rsi
0x180010c60  mov     [rbx], rsi
0x180010c63  mov     [rbx+10h], rdi
0x180010c67  lea     rcx, [rsp+78h+arg_10]
0x180010c6f  jmp     loc_180010AB5
0x180010c74  mov     [rbx+18h], r13
0x180010c78  mov     [rbx+10h], r12
0x180010c7c  add     rsp, 38h
0x180010c80  pop     r15
0x180010c82  pop     r14
0x180010c84  pop     r13
0x180010c86  pop     r12
0x180010c88  pop     rdi
0x180010c89  pop     rsi
0x180010c8a  pop     rbp
0x180010c8b  pop     rbx
0x180010c8c  retn
```
