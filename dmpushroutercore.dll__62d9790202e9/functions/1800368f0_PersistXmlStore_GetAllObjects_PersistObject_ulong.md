# PersistXmlStore::GetAllObjects(PersistObject * *,ulong *)

- ea: `0x1800368f0`
- end: `0x180036a6c`
- name: `?GetAllObjects@PersistXmlStore@@UEAAJPEAPEAVPersistObject@@PEAK@Z`
- size: `380`
- prototype: `__int64 __fastcall(PersistXmlStore *__hidden this, struct PersistObject **, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180006090`
- `0x18001974c`
- `0x180019904`
- `0x1800368f0`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800369b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800369e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800369b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800369e2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800369a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800369c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800369a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800369c2`
- `DMCmnUtils!CopyString` at `0x1800369d7`
- `DMCmnUtils!CopyString` at `0x1800369d7`

## pseudocode

```c
__int64 __fastcall PersistXmlStore::GetAllObjects(PersistXmlStore *this, struct PersistObject **a2, unsigned int *a3)
{
  int v6; // ebx
  __int64 v7; // rbp
  PersistObject *v8; // rsi
  __int64 v9; // r15
  PersistObject *v10; // rax
  __int64 v11; // rbx
  struct _RTL_CRITICAL_SECTION *v12; // rdi
  const unsigned __int16 *v13; // rbx
  __int64 i; // rdi
  struct PersistObject *v15; // rcx

  if ( a2 && a3 )
  {
    v7 = (__int64)(*((_QWORD *)this + 12) - *((_QWORD *)this + 11)) >> 3;
    if ( (unsigned int)v7 <= *a3 )
    {
      v6 = 0;
      v9 = 0;
      if ( !(_DWORD)v7 )
        return (unsigned int)v6;
      while ( 1 )
      {
        v10 = (PersistObject *)operator new(0x60u, (const struct std::nothrow_t *)&std::nothrow);
        v8 = v10 ? PersistObject::PersistObject(v10) : 0LL;
        if ( !v8 )
          break;
        v6 = PersistObject::CopyData(v8, *(struct PersistObject **)(*((_QWORD *)this + 11) + 8 * v9));
        if ( v6 < 0 )
          goto LABEL_16;
        v11 = *(_QWORD *)(*((_QWORD *)this + 11) + 8 * v9);
        v12 = (struct _RTL_CRITICAL_SECTION *)(v11 + 32);
        EnterCriticalSection((LPCRITICAL_SECTION)(v11 + 32));
        v13 = *(const unsigned __int16 **)(v11 + 24);
        LeaveCriticalSection(v12);
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)v8 + 32));
        v6 = CopyString(v13, 0xFFFFFFFF, (unsigned __int16 **)v8 + 3);
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v8 + 32));
        if ( v6 < 0 )
          goto LABEL_16;
        a2[v9] = v8;
        v9 = (unsigned int)(v9 + 1);
        *a3 = v9;
        if ( (unsigned int)v9 >= (unsigned int)v7 )
          return (unsigned int)v6;
      }
      v6 = -2147024882;
    }
    else
    {
      v8 = 0;
      v6 = -2147467259;
    }
LABEL_16:
    for ( i = 0; (unsigned int)i < *a3; i = (unsigned int)(i + 1) )
    {
      v15 = a2[i];
      if ( v15 )
        (**(void (__fastcall ***)(struct PersistObject *, __int64))v15)(v15, 1);
      a2[i] = 0;
    }
    *a3 = 0;
    if ( v8 )
      (**(void (__fastcall ***)(PersistObject *, __int64))v8)(v8, 1);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800368f0  push    rbx
0x1800368f2  push    rbp
0x1800368f3  push    rsi
0x1800368f4  push    rdi
0x1800368f5  push    r12
0x1800368f7  push    r13
0x1800368f9  push    r14
0x1800368fb  push    r15
0x1800368fd  sub     rsp, 38h
0x180036901  mov     r14, r8
0x180036904  mov     r12, rdx
0x180036907  mov     r13, rcx
0x18003690a  test    rdx, rdx
0x18003690d  jz      short loc_180036914
0x18003690f  test    r8, r8
0x180036912  jnz     short loc_18003691E
0x180036914  mov     ebx, 80070057h
0x180036919  jmp     loc_180036A59
0x18003691e  mov     rbp, [rcx+60h]
0x180036922  sub     rbp, [rcx+58h]
0x180036926  sar     rbp, 3
0x18003692a  cmp     ebp, [r8]
0x18003692d  jbe     short loc_18003693B
0x18003692f  xor     esi, esi
0x180036931  mov     ebx, 80004005h
0x180036936  jmp     loc_180036A0B
0x18003693b  xor     ebx, ebx
0x18003693d  xor     r15d, r15d
0x180036940  test    ebp, ebp
0x180036942  jz      loc_180036A59
0x180036948  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003694f  mov     ecx, 60h ; '`'; unsigned __int64
0x180036954  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180036959  mov     [rsp+78h+arg_8], rax
0x180036961  test    rax, rax
0x180036964  jz      short loc_180036973
0x180036966  mov     rcx, rax; this
0x180036969  call    ??0PersistObject@@QEAA@XZ; PersistObject::PersistObject(void)
0x18003696e  mov     rsi, rax
0x180036971  jmp     short loc_180036975
0x180036973  xor     esi, esi
0x180036975  test    rsi, rsi
0x180036978  jz      loc_180036A06
0x18003697e  mov     rdx, [r13+58h]
0x180036982  mov     rdx, [rdx+r15*8]; struct PersistObject *
0x180036986  mov     rcx, rsi; this
0x180036989  call    ?CopyData@PersistObject@@QEAAJPEAV1@@Z; PersistObject::CopyData(PersistObject *)
0x18003698e  mov     ebx, eax
0x180036990  test    eax, eax
0x180036992  js      short loc_180036A0B
0x180036994  mov     rax, [r13+58h]
0x180036998  mov     rbx, [rax+r15*8]
0x18003699c  lea     rdi, [rbx+20h]
0x1800369a0  mov     rcx, rdi; lpCriticalSection
0x1800369a3  call    cs:__imp_EnterCriticalSection
0x1800369a9  mov     rbx, [rbx+18h]
0x1800369ad  mov     rcx, rdi; lpCriticalSection
0x1800369b0  call    cs:__imp_LeaveCriticalSection
0x1800369b6  lea     rdi, [rsi+20h]
0x1800369ba  mov     [rsp+78h+var_58], rdi
0x1800369bf  mov     rcx, rdi; lpCriticalSection
0x1800369c2  call    cs:__imp_EnterCriticalSection
0x1800369c8  mov     [rsp+78h+var_50], 1
0x1800369cd  lea     r8, [rsi+18h]
0x1800369d1  or      edx, 0FFFFFFFFh
0x1800369d4  mov     rcx, rbx
0x1800369d7  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x1800369dd  mov     ebx, eax
0x1800369df  mov     rcx, rdi; lpCriticalSection
0x1800369e2  call    cs:__imp_LeaveCriticalSection
0x1800369e8  mov     [rsp+78h+var_50], 0
0x1800369ed  test    ebx, ebx
0x1800369ef  js      short loc_180036A0B
0x1800369f1  mov     [r12+r15*8], rsi
0x1800369f5  inc     r15d
0x1800369f8  mov     [r14], r15d
0x1800369fb  cmp     r15d, ebp
0x1800369fe  jb      loc_180036948
0x180036a04  jmp     short loc_180036A59
0x180036a06  mov     ebx, 8007000Eh
0x180036a0b  xor     edi, edi
0x180036a0d  cmp     [r14], edi
0x180036a10  jbe     short loc_180036A3A
0x180036a12  mov     rcx, [r12+rdi*8]
0x180036a16  test    rcx, rcx
0x180036a19  jz      short loc_180036A2B
0x180036a1b  mov     rax, [rcx]
0x180036a1e  mov     edx, 1
0x180036a23  mov     rax, [rax]
0x180036a26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a2b  mov     qword ptr [r12+rdi*8], 0
0x180036a33  inc     edi
0x180036a35  cmp     edi, [r14]
0x180036a38  jb      short loc_180036A12
0x180036a3a  mov     dword ptr [r14], 0
0x180036a41  test    rsi, rsi
0x180036a44  jz      short loc_180036A59
0x180036a46  mov     rax, [rsi]
0x180036a49  mov     edx, 1
0x180036a4e  mov     rcx, rsi
0x180036a51  mov     rax, [rax]
0x180036a54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a59  mov     eax, ebx
0x180036a5b  add     rsp, 38h
0x180036a5f  pop     r15
0x180036a61  pop     r14
0x180036a63  pop     r13
0x180036a65  pop     r12
0x180036a67  pop     rdi
0x180036a68  pop     rsi
0x180036a69  pop     rbp
0x180036a6a  pop     rbx
0x180036a6b  retn
```
