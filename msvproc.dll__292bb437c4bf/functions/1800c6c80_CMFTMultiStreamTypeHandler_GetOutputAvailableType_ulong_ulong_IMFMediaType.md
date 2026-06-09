# CMFTMultiStreamTypeHandler::GetOutputAvailableType(ulong,ulong,IMFMediaType * *)

- ea: `0x1800c6c80`
- end: `0x1800c6d9f`
- name: `?GetOutputAvailableType@CMFTMultiStreamTypeHandler@@UEAAJKKPEAPEAUIMFMediaType@@@Z`
- size: `287`
- prototype: `__int64 __fastcall(CMFTMultiStreamTypeHandler *__hidden this, unsigned int, unsigned int, struct IMFMediaType **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800c6c80`
- `0x1800c7b40`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c6ca4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c6ca4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c6d88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c6d88`
- `MFPlat!MFCreateMediaType` at `0x1800c6d37`
- `MFPlat!MFCreateMediaType` at `0x1800c6d37`

## pseudocode

```c
__int64 __fastcall CMFTMultiStreamTypeHandler::GetOutputAvailableType(
        CMFTMultiStreamTypeHandler *this,
        unsigned int a2,
        int a3,
        struct IMFMediaType **a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  __int64 v5; // rbp
  HRESULT v9; // edi
  __int64 v10; // r15
  __int64 v11; // rbp
  __int64 v12; // r9
  __int64 v13; // rcx
  unsigned __int64 v14; // rcx
  int v15; // r8d
  unsigned int v16; // edx
  __int64 v17; // r14
  __int64 v18; // rcx

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 304);
  v5 = a2;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 304));
  if ( (unsigned int)v5 >= *((_DWORD *)this + 74) )
  {
    v9 = -1072875853;
    goto LABEL_21;
  }
  if ( !a4 )
  {
    v9 = -2147467261;
    goto LABEL_21;
  }
  if ( !*((_DWORD *)this + 69) && !(unsigned int)CMFTMultiStreamTypeHandler::IsAnyInputTypeSet(this) )
  {
    v9 = -1072861856;
    goto LABEL_21;
  }
  v10 = *((_QWORD *)this + 5);
  v11 = 3 * v5;
  v12 = *(_QWORD *)(v10 + 8 * v11);
  v13 = *(_QWORD *)(v10 + 8 * v11 + 8) - v12;
  if ( !v13 || (v14 = v13 >> 4) == 0 )
  {
LABEL_8:
    v9 = -1072875847;
    goto LABEL_21;
  }
  v15 = 0;
  v16 = 0;
  while ( 1 )
  {
    v17 = 2LL * v16;
    if ( *(_DWORD *)(v12 + 16LL * v16 + 8) )
      break;
LABEL_14:
    if ( ++v16 >= v14 )
      goto LABEL_8;
  }
  if ( v15 != a3 )
  {
    ++v15;
    goto LABEL_14;
  }
  v9 = MFCreateMediaType(a4);
  if ( v9 >= 0 )
  {
    v18 = *(_QWORD *)(*(_QWORD *)(v10 + 8 * v11) + 8 * v17);
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v18 + 256LL))(v18, *a4);
    if ( v9 < 0 )
    {
      if ( *a4 )
      {
        ((void (__fastcall *)(_QWORD))(*a4)->lpVtbl->Release)(*a4);
        *a4 = 0;
      }
    }
  }
LABEL_21:
  LeaveCriticalSection(v4);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800c6c80  push    rbx
0x1800c6c82  push    rbp
0x1800c6c83  push    rsi
0x1800c6c84  push    rdi
0x1800c6c85  push    r12
0x1800c6c87  push    r14
0x1800c6c89  push    r15
0x1800c6c8b  sub     rsp, 20h
0x1800c6c8f  lea     rbx, [rcx+130h]
0x1800c6c96  mov     ebp, edx
0x1800c6c98  mov     rdi, rcx
0x1800c6c9b  mov     rsi, r9
0x1800c6c9e  mov     rcx, rbx; lpCriticalSection
0x1800c6ca1  mov     r12d, r8d
0x1800c6ca4  call    cs:__imp_EnterCriticalSection
0x1800c6caa  cmp     ebp, [rdi+128h]
0x1800c6cb0  jnb     loc_1800C6D80
0x1800c6cb6  test    rsi, rsi
0x1800c6cb9  jnz     short loc_1800C6CC5
0x1800c6cbb  mov     edi, 80004003h
0x1800c6cc0  jmp     loc_1800C6D85
0x1800c6cc5  cmp     dword ptr [rdi+114h], 0
0x1800c6ccc  jnz     short loc_1800C6CE4
0x1800c6cce  mov     rcx, rdi; this
0x1800c6cd1  call    ?IsAnyInputTypeSet@CMFTMultiStreamTypeHandler@@QEAAHXZ; CMFTMultiStreamTypeHandler::IsAnyInputTypeSet(void)
0x1800c6cd6  test    eax, eax
0x1800c6cd8  jnz     short loc_1800C6CE4
0x1800c6cda  mov     edi, 0C00D6D60h
0x1800c6cdf  jmp     loc_1800C6D85
0x1800c6ce4  mov     r15, [rdi+28h]
0x1800c6ce8  lea     rbp, [rbp+rbp*2+0]
0x1800c6ced  mov     r9, [r15+rbp*8]
0x1800c6cf1  mov     rcx, [r15+rbp*8+8]
0x1800c6cf6  sub     rcx, r9
0x1800c6cf9  jnz     short loc_1800C6D05
0x1800c6cfb  mov     edi, 0C00D36B9h
0x1800c6d00  jmp     loc_1800C6D85
0x1800c6d05  sar     rcx, 4
0x1800c6d09  test    rcx, rcx
0x1800c6d0c  jz      short loc_1800C6CFB
0x1800c6d0e  xor     r8d, r8d
0x1800c6d11  xor     edx, edx
0x1800c6d13  mov     r14d, edx
0x1800c6d16  add     r14, r14
0x1800c6d19  cmp     dword ptr [r9+r14*8+8], 0
0x1800c6d1f  jz      short loc_1800C6D29
0x1800c6d21  cmp     r8d, r12d
0x1800c6d24  jz      short loc_1800C6D34
0x1800c6d26  inc     r8d
0x1800c6d29  inc     edx
0x1800c6d2b  mov     eax, edx
0x1800c6d2d  cmp     rax, rcx
0x1800c6d30  jb      short loc_1800C6D13
0x1800c6d32  jmp     short loc_1800C6CFB
0x1800c6d34  mov     rcx, rsi; ppMFType
0x1800c6d37  call    cs:__imp_MFCreateMediaType
0x1800c6d3d  mov     edi, eax
0x1800c6d3f  test    eax, eax
0x1800c6d41  js      short loc_1800C6D85
0x1800c6d43  mov     rax, [r15+rbp*8]
0x1800c6d47  mov     rdx, [rsi]
0x1800c6d4a  mov     rcx, [rax+r14*8]
0x1800c6d4e  mov     rax, [rcx]
0x1800c6d51  mov     rax, [rax+100h]
0x1800c6d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6d5d  mov     edi, eax
0x1800c6d5f  test    eax, eax
0x1800c6d61  jns     short loc_1800C6D85
0x1800c6d63  mov     rcx, [rsi]
0x1800c6d66  test    rcx, rcx
0x1800c6d69  jz      short loc_1800C6D85
0x1800c6d6b  mov     rax, [rcx]
0x1800c6d6e  mov     rax, [rax+10h]
0x1800c6d72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6d77  mov     qword ptr [rsi], 0
0x1800c6d7e  jmp     short loc_1800C6D85
0x1800c6d80  mov     edi, 0C00D36B3h
0x1800c6d85  mov     rcx, rbx; lpCriticalSection
0x1800c6d88  call    cs:__imp_LeaveCriticalSection
0x1800c6d8e  mov     eax, edi
0x1800c6d90  add     rsp, 20h
0x1800c6d94  pop     r15
0x1800c6d96  pop     r14
0x1800c6d98  pop     r12
0x1800c6d9a  pop     rdi
0x1800c6d9b  pop     rsi
0x1800c6d9c  pop     rbp
0x1800c6d9d  pop     rbx
0x1800c6d9e  retn
```
