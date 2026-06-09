# CADMCOMW::Terminate(int)

- ea: `0x180009920`
- end: `0x180009a88`
- name: `?Terminate@CADMCOMW@@AEAAXH@Z`
- size: `360`
- prototype: `void __fastcall(CADMCOMW *__hidden this, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180001bd4`
- `0x18000dc5c`

## callees

- `0x1800010a4`
- `0x180009678`
- `0x180009920`
- `0x18000b08c`
- `0x18000d6a4`
- `0x180010010`

## import_xrefs

- `KERNEL32!Sleep` at `0x180009a65`
- `KERNEL32!Sleep` at `0x180009a65`
- `KERNEL32!DeleteCriticalSection` at `0x180009a54`
- `KERNEL32!DeleteCriticalSection` at `0x180009a54`
- `KERNEL32!LocalFree` at `0x1800099bf`
- `KERNEL32!LocalFree` at `0x1800099d0`
- `KERNEL32!LocalFree` at `0x1800099bf`
- `KERNEL32!LocalFree` at `0x1800099d0`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800099f3`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800099f3`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180009973`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180009973`
- `ADMWPROX!ReleaseObjectSecurityContextW` at `0x180009955`
- `ADMWPROX!ReleaseObjectSecurityContextW` at `0x180009955`

## pseudocode

```c
void __fastcall CADMCOMW::Terminate(CADMCOMW *this, int a2)
{
  __int64 i; // rsi
  unsigned int *v5; // rdi
  int v6; // edx
  HLOCAL *v7; // r14
  unsigned int *v8; // rbp
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx

  if ( !_InterlockedCompareExchange((volatile signed __int32 *)this + 3, 1, 0) )
  {
    CADMCOMW::ShutdownCallerWatch(this);
    ReleaseObjectSecurityContextW(this);
    COConnectionPoint::Terminate((CADMCOMW *)((char *)this + 840), a2);
    CReaderWriterLock3::WriteLock((CADMCOMW *)((char *)this + 800));
    for ( i = 0; i != 5; ++i )
    {
      v5 = (unsigned int *)*((_QWORD *)this + i + 6);
      if ( v5 )
      {
        do
        {
          v6 = v5[2];
          if ( v6 != -1 )
          {
            AdminAclNotifyClose(this, v6);
            (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 4) + 288LL))(*((_QWORD *)this + 4), v5[3]);
          }
          v7 = (HLOCAL *)*((_QWORD *)v5 + 3);
          v8 = *(unsigned int **)v5;
          if ( v7 )
          {
            if ( *v7 )
              LocalFree(*v7);
            operator delete(v7);
          }
          LocalFree(v5);
          v5 = v8;
        }
        while ( v8 );
      }
      *((_QWORD *)this + i + 6) = 0;
    }
    CReaderWriterLock3::WriteUnlock((CADMCOMW *)((char *)this + 800));
    v9 = *((_QWORD *)this + 11);
    if ( v9 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      *((_QWORD *)this + 11) = 0;
    }
    v10 = *((_QWORD *)this + 4);
    if ( v10 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      *((_QWORD *)this + 4) = 0;
    }
    v11 = *((_QWORD *)this + 3);
    if ( v11 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      *((_QWORD *)this + 3) = 0;
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
    *((_DWORD *)this + 4) = 1;
  }
  while ( *((_DWORD *)this + 4) != 1 )
    Sleep(0x64u);
}

```

## disassembly

```asm
0x180009920  mov     [rsp+arg_8], rbx
0x180009925  mov     [rsp+arg_10], rbp
0x18000992a  push    rsi
0x18000992b  push    rdi
0x18000992c  push    r13
0x18000992e  push    r14
0x180009930  push    r15
0x180009932  sub     rsp, 20h
0x180009936  xor     eax, eax
0x180009938  mov     edi, edx
0x18000993a  mov     rbx, rcx
0x18000993d  lea     r13d, [rax+1]
0x180009941  lock cmpxchg [rcx+0Ch], r13d
0x180009947  jnz     loc_180009A6B
0x18000994d  call    ?ShutdownCallerWatch@CADMCOMW@@AEAAJXZ; CADMCOMW::ShutdownCallerWatch(void)
0x180009952  mov     rcx, rbx
0x180009955  call    cs:__imp_ReleaseObjectSecurityContextW
0x18000995b  lea     rcx, [rbx+348h]; this
0x180009962  mov     edx, edi; int
0x180009964  call    ?Terminate@COConnectionPoint@@QEAAJH@Z; COConnectionPoint::Terminate(int)
0x180009969  lea     r15, [rbx+320h]
0x180009970  mov     rcx, r15
0x180009973  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180009979  xor     esi, esi
0x18000997b  mov     rdi, [rbx+rsi*8+30h]
0x180009980  test    rdi, rdi
0x180009983  jz      short loc_1800099DE
0x180009985  mov     edx, [rdi+8]; unsigned int
0x180009988  cmp     edx, 0FFFFFFFFh
0x18000998b  jz      short loc_1800099AB
0x18000998d  mov     rcx, rbx; void *
0x180009990  call    ?AdminAclNotifyClose@@YAHPEAXK@Z; AdminAclNotifyClose(void *,ulong)
0x180009995  mov     rcx, [rbx+20h]
0x180009999  mov     edx, [rdi+0Ch]
0x18000999c  mov     rax, [rcx]
0x18000999f  mov     rax, [rax+120h]
0x1800099a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099ab  mov     r14, [rdi+18h]
0x1800099af  mov     rbp, [rdi]
0x1800099b2  test    r14, r14
0x1800099b5  jz      short loc_1800099CD
0x1800099b7  mov     rcx, [r14]; hMem
0x1800099ba  test    rcx, rcx
0x1800099bd  jz      short loc_1800099C5
0x1800099bf  call    cs:__imp_LocalFree
0x1800099c5  mov     rcx, r14; Block
0x1800099c8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800099cd  mov     rcx, rdi; hMem
0x1800099d0  call    cs:__imp_LocalFree
0x1800099d6  mov     rdi, rbp
0x1800099d9  test    rbp, rbp
0x1800099dc  jnz     short loc_180009985
0x1800099de  mov     qword ptr [rbx+rsi*8+30h], 0
0x1800099e7  inc     rsi
0x1800099ea  cmp     rsi, 5
0x1800099ee  jnz     short loc_18000997B
0x1800099f0  mov     rcx, r15
0x1800099f3  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x1800099f9  mov     rcx, [rbx+58h]
0x1800099fd  test    rcx, rcx
0x180009a00  jz      short loc_180009A16
0x180009a02  mov     rax, [rcx]
0x180009a05  mov     rax, [rax+10h]
0x180009a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a0e  mov     qword ptr [rbx+58h], 0
0x180009a16  mov     rcx, [rbx+20h]
0x180009a1a  test    rcx, rcx
0x180009a1d  jz      short loc_180009A33
0x180009a1f  mov     rax, [rcx]
0x180009a22  mov     rax, [rax+10h]
0x180009a26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a2b  mov     qword ptr [rbx+20h], 0
0x180009a33  mov     rcx, [rbx+18h]
0x180009a37  test    rcx, rcx
0x180009a3a  jz      short loc_180009A50
0x180009a3c  mov     rax, [rcx]
0x180009a3f  mov     rax, [rax+10h]
0x180009a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a48  mov     qword ptr [rbx+18h], 0
0x180009a50  lea     rcx, [rbx+68h]; lpCriticalSection
0x180009a54  call    cs:__imp_DeleteCriticalSection
0x180009a5a  mov     [rbx+10h], r13d
0x180009a5e  jmp     short loc_180009A6B
0x180009a60  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180009a65  call    cs:__imp_Sleep
0x180009a6b  cmp     [rbx+10h], r13d
0x180009a6f  jnz     short loc_180009A60
0x180009a71  mov     rbx, [rsp+48h+arg_8]
0x180009a76  mov     rbp, [rsp+48h+arg_10]
0x180009a7b  add     rsp, 20h
0x180009a7f  pop     r15
0x180009a81  pop     r14
0x180009a83  pop     r13
0x180009a85  pop     rdi
0x180009a86  pop     rsi
0x180009a87  retn
```
