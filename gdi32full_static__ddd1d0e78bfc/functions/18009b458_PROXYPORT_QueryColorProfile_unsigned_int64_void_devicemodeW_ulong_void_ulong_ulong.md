# PROXYPORT::QueryColorProfile(unsigned __int64,void *,_devicemodeW *,ulong,void *,ulong *,ulong *)

- ea: `0x18009b458`
- end: `0x18009b5c5`
- name: `?QueryColorProfile@PROXYPORT@@QEAAH_KPEAXPEAU_devicemodeW@@K1PEAK3@Z`
- size: `365`
- prototype: `__int64 __usercall@<rax>(PROXYPORT *__hidden this@<rcx>, unsigned __int64@<rdx>, void *@<r8>, struct _devicemodeW *@<r9>, unsigned int, void *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18003ba20`

## callees

- `0x180040be4`
- `0x180040c4c`
- `0x180040c74`
- `0x180040cb4`
- `0x18009b458`
- `0x1800a68d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009b4c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009b4c7`
- `GDI32!GdiSetLastError` at `0x18009b57a`
- `GDI32!GdiSetLastError` at `0x18009b57a`

## pseudocode

```c
__int64 __fastcall PROXYPORT::QueryColorProfile(
        PROXYPORT *this,
        __int64 a2,
        void *a3,
        struct _devicemodeW *a4,
        unsigned int a5,
        void *a6,
        unsigned int *a7,
        unsigned int *a8)
{
  int v9; // r15d
  PROXYPORT *v11; // rcx
  unsigned __int8 *v12; // rbp
  __int64 v13; // rcx
  __int64 v14; // r10
  unsigned __int8 *v15; // r14
  unsigned __int8 *v16; // rsi
  DWORD CurrentProcessId; // eax
  unsigned __int8 *v18; // rax
  PROXYPORT *v19; // rcx
  char *v20; // rbx
  __int64 v21; // rcx

  v9 = (int)a3;
  if ( (*(_BYTE *)(*(_QWORD *)this + 108LL) & 2) == 0 )
    *(_DWORD *)(*(_QWORD *)this + 88LL) = 0;
  v12 = PROXYPORT::HeapAlloc(this, 0x50u);
  if ( !v12 )
    return 0xFFFFFFFFLL;
  v15 = PROXYPORT::HeapAlloc(v11, 4u);
  if ( !v15 )
    return 0xFFFFFFFFLL;
  v16 = &v12[-*(_QWORD *)(*(_QWORD *)v13 + 80LL)];
  *((_DWORD *)v16 + 1) = 116;
  *v16 = 0;
  *((_QWORD *)v16 + 3) = v14;
  CurrentProcessId = GetCurrentProcessId();
  *((_DWORD *)v16 + 9) = v9;
  *((_DWORD *)v16 + 8) = CurrentProcessId;
  *((_QWORD *)v16 + 5) = a4;
  *((_DWORD *)v16 + 12) = a5;
  *((_DWORD *)v16 + 16) = *a7;
  *(_QWORD *)(v16 + 68) = *a8;
  v18 = PROXYPORT::HeapAllocOffset(this, *a7, v12);
  *((_QWORD *)v16 + 7) = v18;
  if ( !v18
    || !PROXYPORT::ThunkMemBlock(v19, (struct _OffsetPointer *)(v16 + 40), a4->dmSize + a4->dmDriverExtra, v12)
    || (int)PROXYPORT::SendRequest(this, v12, v15, 4, 0) < 0 )
  {
    return 0xFFFFFFFFLL;
  }
  v20 = (char *)*((_QWORD *)v16 + 7);
  if ( v20 )
    v20 = &v20[(_QWORD)v12 - *(_QWORD *)(*(_QWORD *)this + 80LL)];
  v21 = *((unsigned int *)v16 + 18);
  if ( (_DWORD)v21 )
    GdiSetLastError(v21);
  memcpy_0(a6, v20, *a7);
  *a7 = *((_DWORD *)v16 + 16);
  *a8 = *((_DWORD *)v16 + 17);
  return *(unsigned int *)&v15[-*(_QWORD *)(*(_QWORD *)this + 80LL)];
}

```

## disassembly

```asm
0x18009b458  push    rbx
0x18009b45a  push    rbp
0x18009b45b  push    rsi
0x18009b45c  push    rdi
0x18009b45d  push    r12
0x18009b45f  push    r14
0x18009b461  push    r15
0x18009b463  sub     rsp, 30h
0x18009b467  mov     rax, [rcx]
0x18009b46a  mov     rbx, r9
0x18009b46d  mov     r15, r8
0x18009b470  mov     r10, rdx
0x18009b473  mov     rdi, rcx
0x18009b476  test    byte ptr [rax+6Ch], 2
0x18009b47a  jnz     short loc_18009B483
0x18009b47c  mov     dword ptr [rax+58h], 0
0x18009b483  mov     edx, 50h ; 'P'; unsigned int
0x18009b488  call    ?HeapAlloc@PROXYPORT@@QEAAPEAEK@Z; PROXYPORT::HeapAlloc(ulong)
0x18009b48d  mov     rbp, rax
0x18009b490  test    rax, rax
0x18009b493  jz      loc_18009B5B2
0x18009b499  mov     edx, 4; unsigned int
0x18009b49e  call    ?HeapAlloc@PROXYPORT@@QEAAPEAEK@Z; PROXYPORT::HeapAlloc(ulong)
0x18009b4a3  mov     r14, rax
0x18009b4a6  test    rax, rax
0x18009b4a9  jz      loc_18009B5B2
0x18009b4af  mov     rcx, [rcx]
0x18009b4b2  mov     rsi, rbp
0x18009b4b5  sub     rsi, [rcx+50h]
0x18009b4b9  mov     dword ptr [rsi+4], 74h ; 't'
0x18009b4c0  mov     byte ptr [rsi], 0
0x18009b4c3  mov     [rsi+18h], r10
0x18009b4c7  call    cs:__imp_GetCurrentProcessId
0x18009b4ce  nop     dword ptr [rax+rax+00h]
0x18009b4d3  mov     r12, [rsp+68h+arg_38]
0x18009b4db  mov     r8, rbp; unsigned __int8 *
0x18009b4de  mov     [rsi+24h], r15d
0x18009b4e2  mov     rcx, rdi; this
0x18009b4e5  mov     r15, [rsp+68h+arg_30]
0x18009b4ed  mov     [rsi+20h], eax
0x18009b4f0  mov     eax, [rsp+68h+arg_20]
0x18009b4f7  mov     [rsi+28h], rbx
0x18009b4fb  mov     [rsi+30h], eax
0x18009b4fe  mov     eax, [r15]
0x18009b501  mov     [rsi+40h], eax
0x18009b504  mov     eax, [r12]
0x18009b508  mov     [rsi+44h], eax
0x18009b50b  mov     dword ptr [rsi+48h], 0
0x18009b512  mov     edx, [r15]; unsigned int
0x18009b515  call    ?HeapAllocOffset@PROXYPORT@@QEAAPEAEKPEAE@Z; PROXYPORT::HeapAllocOffset(ulong,uchar *)
0x18009b51a  mov     [rsi+38h], rax
0x18009b51e  test    rax, rax
0x18009b521  jz      loc_18009B5B2
0x18009b527  movzx   r8d, word ptr [rbx+46h]
0x18009b52c  lea     rdx, [rsi+28h]; struct _OffsetPointer *
0x18009b530  movzx   eax, word ptr [rbx+44h]
0x18009b534  mov     r9, rbp; unsigned __int8 *
0x18009b537  add     r8d, eax; unsigned int
0x18009b53a  call    ?ThunkMemBlock@PROXYPORT@@QEAAHPEAU_OffsetPointer@@KPEAE@Z; PROXYPORT::ThunkMemBlock(_OffsetPointer *,ulong,uchar *)
0x18009b53f  test    eax, eax
0x18009b541  jz      short loc_18009B5B2
0x18009b543  mov     r9d, 4; unsigned int
0x18009b549  mov     [rsp+68h+var_48], 0; bool
0x18009b54e  mov     r8, r14; unsigned __int8 *
0x18009b551  mov     rdx, rbp; unsigned __int8 *
0x18009b554  mov     rcx, rdi; this
0x18009b557  call    ?SendRequest@PROXYPORT@@QEAAJPEAE0K_N@Z; PROXYPORT::SendRequest(uchar *,uchar *,ulong,bool)
0x18009b55c  test    eax, eax
0x18009b55e  js      short loc_18009B5B2
0x18009b560  mov     rbx, [rsi+38h]
0x18009b564  test    rbx, rbx
0x18009b567  jz      short loc_18009B573
0x18009b569  mov     rax, [rdi]
0x18009b56c  sub     rbx, [rax+50h]
0x18009b570  add     rbx, rbp
0x18009b573  mov     ecx, [rsi+48h]
0x18009b576  test    ecx, ecx
0x18009b578  jz      short loc_18009B586
0x18009b57a  call    cs:__imp_GdiSetLastError
0x18009b581  nop     dword ptr [rax+rax+00h]
0x18009b586  mov     r8d, [r15]; Size
0x18009b589  mov     rdx, rbx; Src
0x18009b58c  mov     rcx, [rsp+68h+arg_28]; void *
0x18009b594  call    memcpy_0
0x18009b599  mov     eax, [rsi+40h]
0x18009b59c  mov     [r15], eax
0x18009b59f  mov     eax, [rsi+44h]
0x18009b5a2  mov     [r12], eax
0x18009b5a6  mov     rax, [rdi]
0x18009b5a9  sub     r14, [rax+50h]
0x18009b5ad  mov     eax, [r14]
0x18009b5b0  jmp     short loc_18009B5B5
0x18009b5b2  or      eax, 0FFFFFFFFh
0x18009b5b5  add     rsp, 30h
0x18009b5b9  pop     r15
0x18009b5bb  pop     r14
0x18009b5bd  pop     r12
0x18009b5bf  pop     rdi
0x18009b5c0  pop     rsi
0x18009b5c1  pop     rbp
0x18009b5c2  pop     rbx
0x18009b5c3  retn
```
