# PsmpFindOrCreateHostJobContext

- ea: `0x18000e3d0`
- end: `0x18000e5f8`
- name: `PsmpFindOrCreateHostJobContext`
- size: `552`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18000abf0`
- `0x18000c7b0`

## callees

- `0x18000a8d0`
- `0x18000e3d0`
- `0x180013610`
- `0x1800137a4`
- `0x1800192fc`
- `0x18001b7e0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000e5d2`
- `ntdll!RtlFreeHeap` at `0x18000e5d2`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000e41f`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000e41f`
- `ntdll!RtlAllocateHeap` at `0x18000e449`
- `ntdll!RtlAllocateHeap` at `0x18000e449`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000e4a6`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000e4a6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e4ee`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e4ee`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000e408`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000e408`

## pseudocode

```c
__int64 __fastcall PsmpFindOrCreateHostJobContext(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v3; // r15
  _QWORD *HostJobContext; // rbx
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  char *Heap; // rax
  char *v12; // rbx
  __int64 result; // rax
  void *v14; // rdi
  _QWORD *v15; // rax
  _QWORD *v16; // rsi
  _QWORD *v17; // rdx
  int v18; // edx
  char *v19; // rdx
  int v20; // ecx
  int v21; // [rsp+30h] [rbp-79h] BYREF
  int v22; // [rsp+34h] [rbp-75h] BYREF
  BOOL v23; // [rsp+38h] [rbp-71h] BYREF
  __int64 v24; // [rsp+40h] [rbp-69h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v25; // [rsp+50h] [rbp-59h] BYREF
  int *v26; // [rsp+70h] [rbp-39h]
  __int64 v27; // [rsp+78h] [rbp-31h]
  _BYTE v28[16]; // [rsp+80h] [rbp-29h] BYREF
  int *v29; // [rsp+90h] [rbp-19h]
  __int64 v30; // [rsp+98h] [rbp-11h]
  __int64 *v31; // [rsp+A0h] [rbp-9h]
  __int64 v32; // [rsp+A8h] [rbp-1h]
  BOOL *v33; // [rsp+B0h] [rbp+7h]
  __int64 v34; // [rsp+B8h] [rbp+Fh]

  v3 = a1 + 328;
  RtlAcquireSRWLockShared(a1 + 328);
  HostJobContext = PsmpFindHostJobContext(a1, a2);
  RtlReleaseSRWLockShared(v3, v8, v9, v10);
  if ( HostJobContext )
  {
    *a3 = HostJobContext;
    return 0;
  }
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x78u);
  v12 = Heap;
  if ( !Heap )
    return 3221225495LL;
  *((_DWORD *)Heap + 18) = 1;
  *((_QWORD *)Heap + 5) = a2;
  v14 = Heap;
  v15 = Heap + 104;
  v15[1] = v15;
  *v15 = v15;
  *((_QWORD *)v12 + 1) = 0;
  *(_QWORD *)(v12 + 20) = 0;
  *(_QWORD *)(v12 + 28) = 0;
  *((_DWORD *)v12 + 9) = 0;
  *(_QWORD *)v12 = a1;
  *((_DWORD *)v12 + 4) = 4;
  RtlAcquireSRWLockExclusive(v3);
  v16 = PsmpFindHostJobContext(a1, a2);
  if ( !v16 )
  {
    v17 = *(_QWORD **)(a1 + 6824);
    if ( *v17 != a1 + 6816 )
      __fastfail(3u);
    v16 = v12;
    *((_QWORD *)v12 + 7) = a1 + 6816;
    v14 = 0;
    *((_QWORD *)v12 + 8) = v17;
    *v17 = v12 + 56;
    *(_QWORD *)(a1 + 6824) = v12 + 56;
  }
  RtlReleaseSRWLockExclusive(v3);
  if ( (unsigned int)dword_18003F048 > 5 && tlgKeywordOn((__int64)&dword_18003F048, 1) )
  {
    v21 = v18;
    v19 = (char *)(*v16 + 7040LL);
    v26 = &v21;
    v27 = 4;
    tlgCreate1Sz_wchar_t((__int64)v28, v19);
    v20 = *((_DWORD *)v16 + 4);
    v29 = &v22;
    v24 = v16[5];
    v31 = &v24;
    v22 = v20;
    v30 = 4;
    v32 = 8;
    v23 = v14 != 0;
    v34 = 4;
    v33 = &v23;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18003F048, (unsigned __int8 *)&dword_1800383CC, 0, 0, 7u, &v25);
  }
  *a3 = v16;
  result = 0;
  if ( v14 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000e3d0  push    rbp
0x18000e3d2  push    rbx
0x18000e3d3  push    rsi
0x18000e3d4  push    rdi
0x18000e3d5  push    r12
0x18000e3d7  push    r14
0x18000e3d9  push    r15
0x18000e3db  lea     rbp, [rsp-27h]
0x18000e3e0  sub     rsp, 0D0h
0x18000e3e7  mov     rax, cs:__security_cookie
0x18000e3ee  xor     rax, rsp
0x18000e3f1  mov     [rbp+57h+var_40], rax
0x18000e3f5  lea     r15, [rcx+148h]
0x18000e3fc  mov     r14, rcx
0x18000e3ff  mov     rcx, r15
0x18000e402  mov     r12, r8
0x18000e405  mov     rsi, rdx
0x18000e408  call    cs:__imp_RtlAcquireSRWLockShared
0x18000e40e  mov     rdx, rsi
0x18000e411  mov     rcx, r14
0x18000e414  call    PsmpFindHostJobContext
0x18000e419  mov     rcx, r15
0x18000e41c  mov     rbx, rax
0x18000e41f  call    cs:__imp_RtlReleaseSRWLockShared
0x18000e425  test    rbx, rbx
0x18000e428  jz      short loc_18000E433
0x18000e42a  mov     [r12], rbx
0x18000e42e  jmp     loc_18000E5D8
0x18000e433  mov     rcx, gs:60h
0x18000e43c  mov     edx, 8; Flags
0x18000e441  mov     rcx, [rcx+30h]; HeapHandle
0x18000e445  lea     r8d, [rdx+70h]; Size
0x18000e449  call    cs:__imp_RtlAllocateHeap
0x18000e44f  mov     rbx, rax
0x18000e452  test    rax, rax
0x18000e455  jnz     short loc_18000E461
0x18000e457  mov     eax, 0C0000017h
0x18000e45c  jmp     loc_18000E5DA
0x18000e461  mov     dword ptr [rax+48h], 1
0x18000e468  mov     rcx, r15
0x18000e46b  mov     [rax+28h], rsi
0x18000e46f  mov     rdi, rbx
0x18000e472  add     rax, 68h ; 'h'
0x18000e476  mov     [rax+8], rax
0x18000e47a  mov     [rax], rax
0x18000e47d  mov     qword ptr [rbx+8], 0
0x18000e485  mov     qword ptr [rbx+14h], 0
0x18000e48d  mov     qword ptr [rbx+1Ch], 0
0x18000e495  mov     dword ptr [rbx+24h], 0
0x18000e49c  mov     [rbx], r14
0x18000e49f  mov     dword ptr [rbx+10h], 4
0x18000e4a6  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000e4ac  mov     rdx, rsi
0x18000e4af  mov     rcx, r14
0x18000e4b2  call    PsmpFindHostJobContext
0x18000e4b7  mov     rsi, rax
0x18000e4ba  test    rax, rax
0x18000e4bd  jnz     short loc_18000E4EB
0x18000e4bf  lea     rcx, [r14+1AA0h]
0x18000e4c6  mov     rdx, [rcx+8]
0x18000e4ca  cmp     [rdx], rcx
0x18000e4cd  jz      short loc_18000E4D4
0x18000e4cf  lea     ecx, [rax+3]
0x18000e4d2  int     29h; Win8: RtlFailFast(ecx)
0x18000e4d4  lea     rax, [rbx+38h]
0x18000e4d8  mov     rsi, rbx
0x18000e4db  mov     [rax], rcx
0x18000e4de  xor     edi, edi
0x18000e4e0  mov     [rax+8], rdx
0x18000e4e4  mov     [rdx], rax
0x18000e4e7  mov     [rcx+8], rax
0x18000e4eb  mov     rcx, r15
0x18000e4ee  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000e4f4  mov     eax, cs:dword_18003F048
0x18000e4fa  cmp     eax, 5
0x18000e4fd  jbe     loc_18000E5B5
0x18000e503  mov     edx, 1
0x18000e508  lea     rcx, dword_18003F048
0x18000e50f  call    _tlgKeywordOn
0x18000e514  test    al, al
0x18000e516  jz      loc_18000E5B5
0x18000e51c  mov     [rbp+57h+var_D0], edx
0x18000e51f  lea     rax, [rbp+57h+var_D0]
0x18000e523  mov     rdx, [rsi]
0x18000e526  lea     rcx, [rbp+57h+var_80]
0x18000e52a  add     rdx, 1B80h
0x18000e531  mov     [rbp+57h+var_90], rax
0x18000e535  mov     [rbp+57h+var_88], 4
0x18000e53d  call    _tlgCreate1Sz_wchar_t
0x18000e542  mov     ecx, [rsi+10h]
0x18000e545  lea     rax, [rbp+57h+var_CC]
0x18000e549  mov     [rbp+57h+var_70], rax
0x18000e54d  lea     rdx, dword_1800383CC
0x18000e554  mov     rax, [rsi+28h]
0x18000e558  mov     [rbp+57h+var_C0], rax
0x18000e55c  lea     rax, [rbp+57h+var_C0]
0x18000e560  mov     [rbp+57h+var_60], rax
0x18000e564  xor     eax, eax
0x18000e566  test    rdi, rdi
0x18000e569  mov     [rbp+57h+var_CC], ecx
0x18000e56c  lea     rcx, dword_18003F048
0x18000e573  mov     [rbp+57h+var_68], 4
0x18000e57b  setnz   al
0x18000e57e  mov     [rbp+57h+var_58], 8
0x18000e586  mov     [rbp+57h+var_C8], eax
0x18000e589  xor     r9d, r9d
0x18000e58c  lea     rax, [rbp+57h+var_C8]
0x18000e590  mov     [rbp+57h+var_48], 4
0x18000e598  mov     [rbp+57h+var_50], rax
0x18000e59c  xor     r8d, r8d
0x18000e59f  lea     rax, [rbp+57h+var_B0]
0x18000e5a3  mov     [rsp+100h+var_D8], rax
0x18000e5a8  mov     [rsp+100h+var_E0], 7
0x18000e5b0  call    _tlgWriteTransfer_EventWriteTransfer
0x18000e5b5  mov     [r12], rsi
0x18000e5b9  xor     eax, eax
0x18000e5bb  test    rdi, rdi
0x18000e5be  jz      short loc_18000E5DA
0x18000e5c0  mov     rcx, gs:60h
0x18000e5c9  mov     r8, rdi; P
0x18000e5cc  xor     edx, edx; Flags
0x18000e5ce  mov     rcx, [rcx+30h]; HeapHandle
0x18000e5d2  call    cs:__imp_RtlFreeHeap
0x18000e5d8  xor     eax, eax
0x18000e5da  mov     rcx, [rbp+57h+var_40]
0x18000e5de  xor     rcx, rsp; StackCookie
0x18000e5e1  call    __security_check_cookie
0x18000e5e6  add     rsp, 0D0h
0x18000e5ed  pop     r15
0x18000e5ef  pop     r14
0x18000e5f1  pop     r12
0x18000e5f3  pop     rdi
0x18000e5f4  pop     rsi
0x18000e5f5  pop     rbx
0x18000e5f6  pop     rbp
0x18000e5f7  retn
```
