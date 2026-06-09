# IIS_CONFIG::~IIS_CONFIG(void)

- ea: `0x180009b4c`
- end: `0x180009bfa`
- name: `??1IIS_CONFIG@@QEAA@XZ`
- size: `174`
- prototype: `void __fastcall(IIS_CONFIG *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x18000b180`
- `0x18000e510`

## callees

- `0x180001048`
- `0x180009b4c`
- `0x180009c00`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009b69`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009b69`

## pseudocode

```c
void __fastcall IIS_CONFIG::~IIS_CONFIG(IIS_CONFIG *this)
{
  __int64 v2; // rax
  void *v3; // r14
  __int64 v4; // rdi
  IIS_CONFIG_RECORD *i; // rsi
  __int64 v6; // rcx

  if ( *((_DWORD *)this + 272) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1096));
    *((_DWORD *)this + 272) = 0;
  }
  v2 = *((_QWORD *)this + 133);
  if ( v2 )
  {
    v3 = (void *)(v2 - 8);
    v4 = *(_QWORD *)(v2 - 8);
    for ( i = (IIS_CONFIG_RECORD *)(v2 + 416 * v4); v4; --v4 )
    {
      i = (IIS_CONFIG_RECORD *)((char *)i - 416);
      IIS_CONFIG_RECORD::~IIS_CONFIG_RECORD(i);
    }
    operator delete(v3);
    *((_QWORD *)this + 133) = 0;
  }
  v6 = *((_QWORD *)this + 134);
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    *((_QWORD *)this + 134) = 0;
  }
  *((_DWORD *)this + 271) = 1667720038;
}

```

## disassembly

```asm
0x180009b4c  push    rbx
0x180009b4e  push    rsi
0x180009b4f  push    rdi
0x180009b50  push    r14
0x180009b52  sub     rsp, 28h
0x180009b56  cmp     dword ptr [rcx+440h], 0
0x180009b5d  mov     rbx, rcx
0x180009b60  jz      short loc_180009B79
0x180009b62  add     rcx, 448h; lpCriticalSection
0x180009b69  call    cs:__imp_DeleteCriticalSection
0x180009b6f  mov     dword ptr [rbx+440h], 0
0x180009b79  mov     rax, [rbx+428h]
0x180009b80  test    rax, rax
0x180009b83  jz      short loc_180009BC3
0x180009b85  lea     r14, [rax-8]
0x180009b89  mov     rdi, [r14]
0x180009b8c  imul    rsi, rdi, 1A0h
0x180009b93  add     rsi, rax
0x180009b96  test    rdi, rdi
0x180009b99  jz      short loc_180009BB0
0x180009b9b  sub     rsi, 1A0h
0x180009ba2  mov     rcx, rsi; this
0x180009ba5  call    ??1IIS_CONFIG_RECORD@@QEAA@XZ; IIS_CONFIG_RECORD::~IIS_CONFIG_RECORD(void)
0x180009baa  sub     rdi, 1
0x180009bae  jnz     short loc_180009B9B
0x180009bb0  mov     rcx, r14; Block
0x180009bb3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009bb8  mov     qword ptr [rbx+428h], 0
0x180009bc3  mov     rcx, [rbx+430h]
0x180009bca  test    rcx, rcx
0x180009bcd  jz      short loc_180009BE6
0x180009bcf  mov     rax, [rcx]
0x180009bd2  mov     rax, [rax+10h]
0x180009bd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bdb  mov     qword ptr [rbx+430h], 0
0x180009be6  mov     dword ptr [rbx+43Ch], 63676366h
0x180009bf0  add     rsp, 28h
0x180009bf4  pop     r14
0x180009bf6  pop     rdi
0x180009bf7  pop     rsi
0x180009bf8  pop     rbx
0x180009bf9  retn
```
