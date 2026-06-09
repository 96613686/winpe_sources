# CFileStream::InitGlobal(ulong,ulong)

- ea: `0x18001daa0`
- end: `0x18001db8b`
- name: `?InitGlobal@CFileStream@@QEAAJKK@Z`
- size: `235`
- prototype: `__int64 __fastcall(CFileStream *__hidden this, unsigned int, unsigned int)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18001c2ac`
- `0x18001cd84`
- `0x1800362a4`
- `0x18004a130`
- `0x18005ac70`

## callees

- `0x180018680`
- `0x18001daa0`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001db54`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001db54`

## pseudocode

```c
__int64 __fastcall CFileStream::InitGlobal(CFileStream *this, int a2, int a3)
{
  struct CSmAllocator *TlsSmAllocator; // rax
  __int64 v7; // rax
  _QWORD *v8; // rbx
  __int64 v9; // rcx
  unsigned int v10; // esi
  unsigned __int64 v11; // rdi

  TlsSmAllocator = GetTlsSmAllocator();
  v7 = (*(__int64 (__fastcall **)(struct CSmAllocator *, __int64))(*(_QWORD *)TlsSmAllocator + 24LL))(
         TlsSmAllocator,
         624);
  v8 = (_QWORD *)v7;
  if ( v7 )
  {
    v9 = *((_QWORD *)this + 11);
    *(_QWORD *)v7 = 0;
    *(_DWORD *)(v7 + 8) = 1;
    *(_QWORD *)(v7 + 40) = v9;
    *(GUID *)(v7 + 16) = GUID_b505dc81_f56c_4e77_8760_a05a9b1c070a;
    *(_QWORD *)(v7 + 616) = 0;
    *(_WORD *)(v7 + 72) = 0;
    *(_DWORD *)(v7 + 32) = a3;
    v10 = 0;
    *(_DWORD *)(v7 + 68) = 1;
    *(_DWORD *)(v7 + 596) = 1;
    *(_DWORD *)(v7 + 36) = a2;
    *(_QWORD *)(v7 + 60) = 0;
    *(_QWORD *)(v7 + 608) = 0;
    *(_QWORD *)(v7 + 600) = 0;
    *(_QWORD *)(v7 + 48) = -1;
    *(_DWORD *)(v7 + 56) = 512;
    *((_QWORD *)this + 6) = v7;
    v11 = ((unsigned __int64)this + 32) & -(__int64)(this != 0);
    *(_QWORD *)(v11 + 8) = *(_QWORD *)v7;
    *(_DWORD *)v11 = GetCurrentProcessId();
    if ( v11 )
      v11 -= *(_QWORD *)NtCurrentTeb()->ReservedForOle;
    *v8 = v11;
  }
  else
  {
    return (unsigned int)-2147287032;
  }
  return v10;
}

```

## disassembly

```asm
0x18001daa0  push    rbx
0x18001daa2  push    rbp
0x18001daa3  push    rsi
0x18001daa4  push    rdi
0x18001daa5  sub     rsp, 28h
0x18001daa9  mov     esi, r8d
0x18001daac  mov     ebp, edx
0x18001daae  mov     rdi, rcx
0x18001dab1  call    ?GetTlsSmAllocator@@YAAEAVCSmAllocator@@XZ; GetTlsSmAllocator(void)
0x18001dab6  mov     rcx, rax
0x18001dab9  mov     edx, 270h
0x18001dabe  mov     r9, [rax]
0x18001dac1  mov     rax, [r9+18h]
0x18001dac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001daca  mov     rbx, rax
0x18001dacd  test    rax, rax
0x18001dad0  jz      loc_18001DB84
0x18001dad6  mov     rcx, [rdi+58h]
0x18001dada  mov     qword ptr [rax], 0
0x18001dae1  mov     eax, 1
0x18001dae6  mov     [rbx+8], eax
0x18001dae9  movups  xmm0, xmmword ptr cs:_GUID_b505dc81_f56c_4e77_8760_a05a9b1c070a.Data1
0x18001daf0  mov     [rbx+28h], rcx
0x18001daf4  xor     ecx, ecx
0x18001daf6  movdqu  xmmword ptr [rbx+10h], xmm0
0x18001dafb  mov     qword ptr [rbx+268h], 0
0x18001db06  mov     [rbx+48h], cx
0x18001db0a  mov     [rbx+20h], esi
0x18001db0d  xor     esi, esi
0x18001db0f  mov     [rbx+44h], eax
0x18001db12  mov     [rbx+254h], eax
0x18001db18  lea     rax, [rdi+20h]
0x18001db1c  mov     [rbx+24h], ebp
0x18001db1f  mov     [rbx+3Ch], rcx
0x18001db23  mov     [rbx+260h], rcx
0x18001db2a  mov     [rbx+258h], rcx
0x18001db31  mov     qword ptr [rbx+30h], 0FFFFFFFFFFFFFFFFh
0x18001db39  mov     dword ptr [rbx+38h], 200h
0x18001db40  mov     [rdi+30h], rbx
0x18001db44  neg     rdi
0x18001db47  sbb     rdi, rdi
0x18001db4a  and     rdi, rax
0x18001db4d  mov     rax, [rbx]
0x18001db50  mov     [rdi+8], rax
0x18001db54  call    cs:__imp_GetCurrentProcessId
0x18001db5a  mov     [rdi], eax
0x18001db5c  test    rdi, rdi
0x18001db5f  jz      short loc_18001DB74
0x18001db61  mov     rax, gs:30h
0x18001db6a  mov     rcx, [rax+1758h]
0x18001db71  sub     rdi, [rcx]
0x18001db74  mov     [rbx], rdi
0x18001db77  mov     eax, esi
0x18001db79  add     rsp, 28h
0x18001db7d  pop     rdi
0x18001db7e  pop     rsi
0x18001db7f  pop     rbp
0x18001db80  pop     rbx
0x18001db81  retn
0x18001db82  jmp     short loc_18001DB74
0x18001db84  mov     esi, 80030008h
0x18001db89  jmp     short loc_18001DB77
```
