# CONFIG_CHANGE_NOTIFIER::RemoveChangeListener(IUnknown *,CHANGE_LISTENER_TYPE)

- ea: `0x1800522c8`
- end: `0x1800523a6`
- name: `?RemoveChangeListener@CONFIG_CHANGE_NOTIFIER@@QEAAJPEAUIUnknown@@W4CHANGE_LISTENER_TYPE@@@Z`
- size: `222`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001f440`
- `0x18001f460`

## callees

- `0x180051c64`
- `0x1800522c8`
- `0x180059bde`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180052371`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180052371`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800522f5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800522f5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180052387`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180052387`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800522fe`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800522fe`

## pseudocode

```c
__int64 __fastcall CONFIG_CHANGE_NOTIFIER::RemoveChangeListener(__int64 a1, __int64 a2, int a3)
{
  unsigned int v6; // edi
  CHANGE_LISTENER *v7; // rbx
  _QWORD *Ptr; // r12
  unsigned __int16 i; // cx
  char *v10; // r9
  struct _TP_WORK *v11; // rcx

  if ( a2 )
  {
    v7 = 0;
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 56));
    v6 = -2147024894;
    Ptr = BUFFER::QueryPtr((BUFFER *)a1);
    for ( i = 0; i < *(_WORD *)(a1 + 48); ++i )
    {
      v10 = (char *)&Ptr[i];
      if ( *(_QWORD *)(*(_QWORD *)v10 + 72LL) == a2 && *(_DWORD *)(*(_QWORD *)v10 + 48LL) == a3 )
      {
        v7 = *(CHANGE_LISTENER **)v10;
        memmove_0(&Ptr[i], v10 + 8, 8LL * (*(unsigned __int16 *)(a1 + 48) - i - 1));
        --*(_WORD *)(a1 + 48);
        v6 = 0;
        Ptr[*(unsigned __int16 *)(a1 + 48)] = 0;
        break;
      }
    }
    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 56));
    if ( v7 )
    {
      v11 = (struct _TP_WORK *)*((_QWORD *)v7 + 10);
      if ( v11 )
        WaitForThreadpoolWorkCallbacks(v11, 0);
      CHANGE_LISTENER::DereferenceChangeListener(v7);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x1800522c8  push    rbx
0x1800522ca  push    rbp
0x1800522cb  push    rsi
0x1800522cc  push    rdi
0x1800522cd  push    r12
0x1800522cf  push    r14
0x1800522d1  push    r15
0x1800522d3  sub     rsp, 20h
0x1800522d7  mov     r15d, r8d
0x1800522da  mov     rbp, rdx
0x1800522dd  mov     rsi, rcx
0x1800522e0  test    rdx, rdx
0x1800522e3  jnz     short loc_1800522EF
0x1800522e5  mov     edi, 80070057h
0x1800522ea  jmp     loc_180052395
0x1800522ef  add     rcx, 38h ; '8'; SRWLock
0x1800522f3  xor     ebx, ebx
0x1800522f5  call    cs:__imp_AcquireSRWLockExclusive
0x1800522fb  mov     rcx, rsi
0x1800522fe  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180052304  mov     edi, 80070002h
0x180052309  lea     r8d, [rbx+1]
0x18005230d  mov     r12, rax
0x180052310  xor     ecx, ecx
0x180052312  cmp     cx, [rsi+30h]
0x180052316  jnb     short loc_18005236D
0x180052318  movzx   eax, cx
0x18005231b  lea     r9, [r12+rax*8]
0x18005231f  mov     rax, [r9]
0x180052322  cmp     [rax+48h], rbp
0x180052326  jnz     short loc_18005232E
0x180052328  cmp     [rax+30h], r15d
0x18005232c  jz      short loc_180052334
0x18005232e  add     cx, r8w
0x180052332  jmp     short loc_180052312
0x180052334  movzx   edx, word ptr [rsi+30h]
0x180052338  mov     rbx, rax
0x18005233b  movzx   eax, cx
0x18005233e  mov     rcx, r9; void *
0x180052341  sub     edx, eax
0x180052343  sub     edx, r8d
0x180052346  movsxd  r8, edx
0x180052349  lea     rdx, [r9+8]; Src
0x18005234d  shl     r8, 3; Size
0x180052351  call    memmove_0
0x180052356  mov     eax, 0FFFFh
0x18005235b  add     [rsi+30h], ax
0x18005235f  movzx   eax, word ptr [rsi+30h]
0x180052363  xor     edi, edi
0x180052365  mov     qword ptr [r12+rax*8], 0
0x18005236d  lea     rcx, [rsi+38h]; SRWLock
0x180052371  call    cs:__imp_ReleaseSRWLockExclusive
0x180052377  test    rbx, rbx
0x18005237a  jz      short loc_180052395
0x18005237c  mov     rcx, [rbx+50h]; pwk
0x180052380  test    rcx, rcx
0x180052383  jz      short loc_18005238D
0x180052385  xor     edx, edx; fCancelPendingCallbacks
0x180052387  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18005238d  mov     rcx, rbx; this
0x180052390  call    ?DereferenceChangeListener@CHANGE_LISTENER@@QEAAXXZ; CHANGE_LISTENER::DereferenceChangeListener(void)
0x180052395  mov     eax, edi
0x180052397  add     rsp, 20h
0x18005239b  pop     r15
0x18005239d  pop     r14
0x18005239f  pop     r12
0x1800523a1  pop     rdi
0x1800523a2  pop     rsi
0x1800523a3  pop     rbp
0x1800523a4  pop     rbx
0x1800523a5  retn
```
