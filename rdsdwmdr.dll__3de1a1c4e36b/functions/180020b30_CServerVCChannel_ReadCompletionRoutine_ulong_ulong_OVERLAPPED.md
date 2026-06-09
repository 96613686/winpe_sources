# CServerVCChannel::ReadCompletionRoutine(ulong,ulong,_OVERLAPPED *)

- ea: `0x180020b30`
- end: `0x180020e30`
- name: `?ReadCompletionRoutine@CServerVCChannel@@AEAAJKKPEAU_OVERLAPPED@@@Z`
- size: `768`
- prototype: `__int64 __fastcall(CServerVCChannel *__hidden this, unsigned int, unsigned int, struct _OVERLAPPED *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800214c0`

## callees

- `0x1800032d4`
- `0x180003314`
- `0x18000f068`
- `0x18000f08c`
- `0x1800144c8`
- `0x180017330`
- `0x18001d098`
- `0x18001ef44`
- `0x18002081c`
- `0x180020b30`
- `0x18002b922`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall CServerVCChannel::ReadCompletionRoutine(
        CServerVCChannel *this,
        unsigned int a2,
        unsigned int a3,
        struct _OVERLAPPED *a4)
{
  CTSCriticalSection *v4; // rbp
  unsigned int *v8; // rbx
  char v9; // si
  void *v10; // rcx
  void *v11; // rax
  __int64 v12; // rcx
  unsigned int v13; // r14d
  __int64 v14; // rbx
  __int64 v15; // rbx
  void *v16; // rax
  int CurrentThreadActivityIdPrefix; // eax
  struct _OVERLAPPED *v18; // rsi
  struct _OVERLAPPED *v20; // [rsp+68h] [rbp+20h] BYREF

  v20 = a4;
  v4 = (CServerVCChannel *)((char *)this + 56);
  CTSCriticalSection::Lock((CServerVCChannel *)((char *)this + 56));
  if ( (*((_BYTE *)this + 36) & 4) != 0 )
  {
    a2 = -1073741536;
LABEL_27:
    CTSCriticalSection::UnLock(v4);
    return a2;
  }
  if ( a2 )
  {
    if ( a2 == 234 )
    {
      operator delete(*((void **)this + 46));
      v16 = operator new((unsigned int)(2 * *((_DWORD *)this + 94)));
      *((_QWORD *)this + 46) = v16;
      if ( v16 )
      {
        *((_DWORD *)this + 94) *= 2;
        a2 = CServerVCChannel::IssueARead(this);
        goto LABEL_27;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          (unsigned int)&WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"BYTE[]");
      }
      goto LABEL_11;
    }
    if ( (int)a2 > 0 )
      a2 = (unsigned __int16)a2 | 0x80070000;
    v18 = (struct _OVERLAPPED *)*((_QWORD *)this + 9);
    v20 = v18;
    TCntPtr<ITSAsyncCallback>::SafeAddRef(&v20);
    if ( *((_QWORD *)this + 9) )
    {
      TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease((char *)this + 72);
      *((_QWORD *)this + 9) = 0;
      TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 72);
    }
    CTSCriticalSection::UnLock(v4);
    (*(void (__fastcall **)(struct _OVERLAPPED *))(v18->Internal + 32))(v18);
    TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(&v20);
  }
  else
  {
    if ( *((_DWORD *)this + 90) )
    {
      if ( a3 < 8 )
      {
LABEL_6:
        a2 = -2147418113;
        goto LABEL_27;
      }
      v8 = (unsigned int *)*((_QWORD *)this + 46);
      v9 = 1;
      if ( (v8[1] & 1) != 0 )
      {
        v10 = (void *)*((_QWORD *)this + 48);
        if ( v10 )
          operator delete(v10);
        *((_QWORD *)this + 49) = 0;
        v11 = operator new(*v8);
        *((_QWORD *)this + 48) = v11;
        if ( !v11 )
        {
LABEL_11:
          a2 = -2147024882;
          goto LABEL_27;
        }
        *((_DWORD *)this + 98) = *v8;
      }
      v12 = *((unsigned int *)this + 99);
      v13 = a3 - 8;
      if ( v13 > *((_DWORD *)this + 98) - (int)v12 )
        goto LABEL_6;
      memcpy_0((void *)(*((_QWORD *)this + 48) + v12), (const void *)(*((_QWORD *)this + 46) + 8LL), v13);
      *((_DWORD *)this + 99) += v13;
      if ( (v8[1] & 2) != 0 )
      {
        if ( *((_DWORD *)this + 99) != *((_DWORD *)this + 98) )
          goto LABEL_6;
        v14 = *((_QWORD *)this + 9);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
        CTSCriticalSection::UnLock(v4);
        v9 = 0;
        (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v14 + 24LL))(
          v14,
          *((unsigned int *)this + 98),
          *((_QWORD *)this + 48));
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        operator delete(*((void **)this + 48));
        *((_QWORD *)this + 48) = 0;
        *((_QWORD *)this + 49) = 0;
      }
    }
    else
    {
      v15 = *((_QWORD *)this + 9);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
      CTSCriticalSection::UnLock(v4);
      v9 = 0;
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v15 + 24LL))(v15, a3, *((_QWORD *)this + 46));
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    a2 = CServerVCChannel::IssueARead(this);
    if ( v9 )
      goto LABEL_27;
  }
  return a2;
}

```

## disassembly

```asm
0x180020b30  mov     [rsp+arg_0], rbx
0x180020b35  mov     [rsp+arg_8], rbp
0x180020b3a  mov     [rsp+arg_18], r9
0x180020b3f  push    rsi
0x180020b40  push    rdi
0x180020b41  push    r14
0x180020b43  sub     rsp, 30h
0x180020b47  lea     rbp, [rcx+38h]
0x180020b4b  mov     rdi, rcx
0x180020b4e  mov     rcx, rbp; this
0x180020b51  mov     r14d, r8d
0x180020b54  mov     ebx, edx
0x180020b56  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x180020b5b  test    byte ptr [rdi+24h], 4
0x180020b5f  jz      short loc_180020B6B
0x180020b61  mov     ebx, 0C0000120h
0x180020b66  jmp     loc_180020DAF
0x180020b6b  test    ebx, ebx
0x180020b6d  jnz     loc_180020D05
0x180020b73  cmp     [rdi+168h], ebx
0x180020b79  jz      loc_180020CA7
0x180020b7f  cmp     r14d, 8
0x180020b83  jnb     short loc_180020B8F
0x180020b85  mov     ebx, 8000FFFFh
0x180020b8a  jmp     loc_180020DAF
0x180020b8f  mov     rbx, [rdi+170h]
0x180020b96  mov     esi, 1
0x180020b9b  mov     eax, [rbx+4]
0x180020b9e  and     eax, esi
0x180020ba0  test    al, al
0x180020ba2  jz      short loc_180020BE5
0x180020ba4  mov     rcx, [rdi+180h]; Block
0x180020bab  test    rcx, rcx
0x180020bae  jz      short loc_180020BB5
0x180020bb0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180020bb5  mov     qword ptr [rdi+188h], 0
0x180020bc0  mov     ecx, [rbx]; Size
0x180020bc2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020bc7  mov     [rdi+180h], rax
0x180020bce  test    rax, rax
0x180020bd1  jnz     short loc_180020BDD
0x180020bd3  mov     ebx, 8007000Eh
0x180020bd8  jmp     loc_180020DAF
0x180020bdd  mov     eax, [rbx]
0x180020bdf  mov     [rdi+188h], eax
0x180020be5  mov     ecx, [rdi+18Ch]
0x180020beb  add     r14d, 0FFFFFFF8h
0x180020bef  mov     eax, [rdi+188h]
0x180020bf5  sub     eax, ecx
0x180020bf7  cmp     r14d, eax
0x180020bfa  ja      short loc_180020B85
0x180020bfc  mov     rdx, [rdi+170h]
0x180020c03  add     rcx, [rdi+180h]; void *
0x180020c0a  add     rdx, 8; Src
0x180020c0e  mov     r8d, r14d; Size
0x180020c11  call    memcpy_0
0x180020c16  add     [rdi+18Ch], r14d
0x180020c1d  mov     eax, [rbx+4]
0x180020c20  mov     ecx, [rdi+18Ch]
0x180020c26  test    al, 2
0x180020c28  jz      loc_180020CED
0x180020c2e  cmp     ecx, [rdi+188h]
0x180020c34  jnz     loc_180020B85
0x180020c3a  mov     rbx, [rdi+48h]
0x180020c3e  mov     rcx, rbx
0x180020c41  mov     rax, [rbx]
0x180020c44  mov     rax, [rax+8]
0x180020c48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c4d  mov     rcx, rbp; this
0x180020c50  call    ?UnLock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::UnLock(void)
0x180020c55  mov     rax, [rbx]
0x180020c58  mov     rcx, rbx
0x180020c5b  mov     r8, [rdi+180h]
0x180020c62  xor     sil, sil
0x180020c65  mov     edx, [rdi+188h]
0x180020c6b  mov     rax, [rax+18h]
0x180020c6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c74  mov     rax, [rbx]
0x180020c77  mov     rcx, rbx
0x180020c7a  mov     rax, [rax+10h]
0x180020c7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c83  mov     rcx, [rdi+180h]; Block
0x180020c8a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180020c8f  mov     qword ptr [rdi+180h], 0
0x180020c9a  mov     qword ptr [rdi+188h], 0
0x180020ca5  jmp     short loc_180020CED
0x180020ca7  mov     rbx, [rdi+48h]
0x180020cab  mov     rcx, rbx
0x180020cae  mov     rax, [rbx]
0x180020cb1  mov     rax, [rax+8]
0x180020cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020cba  mov     rcx, rbp; this
0x180020cbd  call    ?UnLock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::UnLock(void)
0x180020cc2  mov     rax, [rbx]
0x180020cc5  mov     edx, r14d
0x180020cc8  mov     r8, [rdi+170h]
0x180020ccf  mov     rcx, rbx
0x180020cd2  xor     sil, sil
0x180020cd5  mov     rax, [rax+18h]
0x180020cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020cde  mov     rax, [rbx]
0x180020ce1  mov     rcx, rbx
0x180020ce4  mov     rax, [rax+10h]
0x180020ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ced  mov     rcx, rdi; this
0x180020cf0  call    ?IssueARead@CServerVCChannel@@AEAAJXZ; CServerVCChannel::IssueARead(void)
0x180020cf5  mov     ebx, eax
0x180020cf7  test    sil, sil
0x180020cfa  jz      loc_180020E1B
0x180020d00  jmp     loc_180020DAF
0x180020d05  cmp     ebx, 0EAh
0x180020d0b  jnz     loc_180020DB9
0x180020d11  mov     rcx, [rdi+170h]; Block
0x180020d18  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180020d1d  mov     eax, [rdi+178h]
0x180020d23  lea     ecx, [rax+rax]; Size
0x180020d26  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020d2b  mov     [rdi+170h], rax
0x180020d32  test    rax, rax
0x180020d35  jnz     short loc_180020D97
0x180020d37  mov     rax, cs:WPP_GLOBAL_Control
0x180020d3e  lea     rcx, WPP_GLOBAL_Control
0x180020d45  cmp     rax, rcx
0x180020d48  jz      loc_180020BD3
0x180020d4e  test    byte ptr [rax+1Ch], 8
0x180020d52  jz      loc_180020BD3
0x180020d58  cmp     byte ptr [rax+19h], 2
0x180020d5c  jb      loc_180020BD3
0x180020d62  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180020d67  lea     rcx, aByte; "BYTE[]"
0x180020d6e  mov     edx, 0Ch
0x180020d73  mov     [rsp+48h+var_28], rcx
0x180020d78  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x180020d7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d86  mov     r9d, eax
0x180020d89  mov     rcx, [rcx+10h]
0x180020d8d  call    WPP_SF_Ds
0x180020d92  jmp     loc_180020BD3
0x180020d97  mov     eax, [rdi+178h]
0x180020d9d  mov     rcx, rdi; this
0x180020da0  add     eax, eax
0x180020da2  mov     [rdi+178h], eax
0x180020da8  call    ?IssueARead@CServerVCChannel@@AEAAJXZ; CServerVCChannel::IssueARead(void)
0x180020dad  mov     ebx, eax
0x180020daf  mov     rcx, rbp; this
0x180020db2  call    ?UnLock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::UnLock(void)
0x180020db7  jmp     short loc_180020E1B
0x180020db9  test    ebx, ebx
0x180020dbb  jle     short loc_180020DC6
0x180020dbd  movzx   ebx, bx
0x180020dc0  or      ebx, 80070000h
0x180020dc6  mov     rsi, [rdi+48h]
0x180020dca  lea     rcx, [rsp+48h+arg_18]
0x180020dcf  mov     [rsp+48h+arg_18], rsi
0x180020dd4  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180020dd9  cmp     qword ptr [rdi+48h], 0
0x180020dde  jz      short loc_180020DFA
0x180020de0  lea     rcx, [rdi+48h]
0x180020de4  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x180020de9  lea     rcx, [rdi+48h]
0x180020ded  mov     qword ptr [rdi+48h], 0
0x180020df5  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180020dfa  mov     rcx, rbp; this
0x180020dfd  call    ?UnLock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::UnLock(void)
0x180020e02  mov     rax, [rsi]
0x180020e05  mov     rcx, rsi
0x180020e08  mov     rax, [rax+20h]
0x180020e0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e11  lea     rcx, [rsp+48h+arg_18]
0x180020e16  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x180020e1b  mov     rbp, [rsp+48h+arg_8]
0x180020e20  mov     eax, ebx
0x180020e22  mov     rbx, [rsp+48h+arg_0]
0x180020e27  add     rsp, 30h
0x180020e2b  pop     r14
0x180020e2d  pop     rdi
0x180020e2e  pop     rsi
0x180020e2f  retn
```
