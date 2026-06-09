# CADMCOMW::DeleteNode(ulong)

- ea: `0x1800042bc`
- end: `0x180004382`
- name: `?DeleteNode@CADMCOMW@@QEAAKK@Z`
- size: `198`
- prototype: `unsigned int __fastcall(CADMCOMW *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000be20`

## callees

- `0x1800010a4`
- `0x1800042bc`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180004316`
- `KERNEL32!LocalFree` at `0x180004357`
- `KERNEL32!LocalFree` at `0x180004368`
- `KERNEL32!LocalFree` at `0x180004316`
- `KERNEL32!LocalFree` at `0x180004357`
- `KERNEL32!LocalFree` at `0x180004368`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180004371`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180004371`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800042dc`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800042dc`

## pseudocode

```c
__int64 __fastcall CADMCOMW::DeleteNode(CADMCOMW *this, unsigned int a2)
{
  CReaderWriterLock3 *v4; // rbp
  __int64 v5; // rcx
  _DWORD *v6; // rbx
  HLOCAL *v7; // rdi
  void *v8; // rcx
  void *v9; // rdi
  HLOCAL *v10; // rbx

  if ( a2 )
  {
    v4 = (CADMCOMW *)((char *)this + 800);
    CReaderWriterLock3::WriteLock((CADMCOMW *)((char *)this + 800));
    v5 = a2 % 5;
    v6 = (_DWORD *)*((_QWORD *)this + v5 + 6);
    if ( v6[2] == a2 )
    {
      *((_QWORD *)this + v5 + 6) = *(_QWORD *)v6;
      v7 = (HLOCAL *)*((_QWORD *)v6 + 3);
      if ( v7 )
      {
        if ( *v7 )
          LocalFree(*v7);
        operator delete(v7);
      }
      v8 = v6;
    }
    else
    {
      while ( 1 )
      {
        v9 = *(void **)v6;
        if ( *(_QWORD *)v6 )
        {
          if ( *((_DWORD *)v9 + 2) == a2 )
            break;
        }
        v6 = *(_DWORD **)v6;
        if ( !v9 )
          goto LABEL_18;
      }
      *(_QWORD *)v6 = *(_QWORD *)v9;
      v10 = (HLOCAL *)*((_QWORD *)v9 + 3);
      if ( v10 )
      {
        if ( *v10 )
          LocalFree(*v10);
        operator delete(v10);
      }
      v8 = v9;
    }
    LocalFree(v8);
LABEL_18:
    CReaderWriterLock3::WriteUnlock(v4);
  }
  return 0;
}

```

## disassembly

```asm
0x1800042bc  push    rbx
0x1800042be  push    rbp
0x1800042bf  push    rsi
0x1800042c0  push    rdi
0x1800042c1  sub     rsp, 28h
0x1800042c5  mov     esi, edx
0x1800042c7  mov     rdi, rcx
0x1800042ca  test    edx, edx
0x1800042cc  jz      loc_180004377
0x1800042d2  lea     rbp, [rcx+320h]
0x1800042d9  mov     rcx, rbp
0x1800042dc  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800042e2  mov     ecx, esi
0x1800042e4  mov     eax, 0CCCCCCCDh
0x1800042e9  mul     esi
0x1800042eb  shr     edx, 2
0x1800042ee  lea     eax, [rdx+rdx*4]
0x1800042f1  sub     ecx, eax
0x1800042f3  mov     rbx, [rdi+rcx*8+30h]
0x1800042f8  cmp     [rbx+8], esi
0x1800042fb  jnz     short loc_180004329
0x1800042fd  mov     rax, [rbx]
0x180004300  mov     [rdi+rcx*8+30h], rax
0x180004305  mov     rdi, [rbx+18h]
0x180004309  test    rdi, rdi
0x18000430c  jz      short loc_180004324
0x18000430e  mov     rcx, [rdi]; hMem
0x180004311  test    rcx, rcx
0x180004314  jz      short loc_18000431C
0x180004316  call    cs:__imp_LocalFree
0x18000431c  mov     rcx, rdi; Block
0x18000431f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004324  mov     rcx, rbx
0x180004327  jmp     short loc_180004368
0x180004329  mov     rdi, [rbx]
0x18000432c  test    rdi, rdi
0x18000432f  jz      short loc_180004336
0x180004331  cmp     [rdi+8], esi
0x180004334  jz      short loc_180004340
0x180004336  mov     rbx, rdi
0x180004339  test    rdi, rdi
0x18000433c  jnz     short loc_180004329
0x18000433e  jmp     short loc_18000436E
0x180004340  mov     rax, [rdi]
0x180004343  mov     [rbx], rax
0x180004346  mov     rbx, [rdi+18h]
0x18000434a  test    rbx, rbx
0x18000434d  jz      short loc_180004365
0x18000434f  mov     rcx, [rbx]; hMem
0x180004352  test    rcx, rcx
0x180004355  jz      short loc_18000435D
0x180004357  call    cs:__imp_LocalFree
0x18000435d  mov     rcx, rbx; Block
0x180004360  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004365  mov     rcx, rdi; hMem
0x180004368  call    cs:__imp_LocalFree
0x18000436e  mov     rcx, rbp
0x180004371  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180004377  xor     eax, eax
0x180004379  add     rsp, 28h
0x18000437d  pop     rdi
0x18000437e  pop     rsi
0x18000437f  pop     rbp
0x180004380  pop     rbx
0x180004381  retn
```
