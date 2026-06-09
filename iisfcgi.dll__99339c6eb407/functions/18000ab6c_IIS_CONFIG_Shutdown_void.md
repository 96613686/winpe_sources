# IIS_CONFIG::Shutdown(void)

- ea: `0x18000ab6c`
- end: `0x18000abf4`
- name: `?Shutdown@IIS_CONFIG@@QEAAJXZ`
- size: `136`
- prototype: `__int64 __fastcall(IIS_CONFIG *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x18000b180`
- `0x18000e5f0`
- `0x18000e770`

## callees

- `0x180001048`
- `0x180009c00`
- `0x18000ab6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ab84`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ab84`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000abe1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000abe1`

## pseudocode

```c
__int64 __fastcall IIS_CONFIG::Shutdown(IIS_CONFIG *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbp
  __int64 v3; // rax
  void *v4; // r14
  __int64 v5; // rbx
  IIS_CONFIG_RECORD *i; // rdi

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1096);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1096));
  v3 = *((_QWORD *)this + 133);
  *((_DWORD *)this + 284) = 1;
  if ( v3 )
  {
    v4 = (void *)(v3 - 8);
    v5 = *(_QWORD *)(v3 - 8);
    for ( i = (IIS_CONFIG_RECORD *)(v3 + 416 * v5); v5; --v5 )
    {
      i = (IIS_CONFIG_RECORD *)((char *)i - 416);
      IIS_CONFIG_RECORD::~IIS_CONFIG_RECORD(i);
    }
    operator delete(v4);
    *((_QWORD *)this + 133) = 0;
  }
  LeaveCriticalSection(v1);
  return 0;
}

```

## disassembly

```asm
0x18000ab6c  push    rbx
0x18000ab6e  push    rbp
0x18000ab6f  push    rsi
0x18000ab70  push    rdi
0x18000ab71  push    r14
0x18000ab73  sub     rsp, 20h
0x18000ab77  lea     rbp, [rcx+448h]
0x18000ab7e  mov     rsi, rcx
0x18000ab81  mov     rcx, rbp; lpCriticalSection
0x18000ab84  call    cs:__imp_EnterCriticalSection
0x18000ab8a  mov     rax, [rsi+428h]
0x18000ab91  mov     dword ptr [rsi+470h], 1
0x18000ab9b  test    rax, rax
0x18000ab9e  jz      short loc_18000ABDE
0x18000aba0  lea     r14, [rax-8]
0x18000aba4  mov     rbx, [r14]
0x18000aba7  imul    rdi, rbx, 1A0h
0x18000abae  add     rdi, rax
0x18000abb1  test    rbx, rbx
0x18000abb4  jz      short loc_18000ABCB
0x18000abb6  sub     rdi, 1A0h
0x18000abbd  mov     rcx, rdi; this
0x18000abc0  call    ??1IIS_CONFIG_RECORD@@QEAA@XZ; IIS_CONFIG_RECORD::~IIS_CONFIG_RECORD(void)
0x18000abc5  sub     rbx, 1
0x18000abc9  jnz     short loc_18000ABB6
0x18000abcb  mov     rcx, r14; Block
0x18000abce  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000abd3  mov     qword ptr [rsi+428h], 0
0x18000abde  mov     rcx, rbp; lpCriticalSection
0x18000abe1  call    cs:__imp_LeaveCriticalSection
0x18000abe7  xor     eax, eax
0x18000abe9  add     rsp, 20h
0x18000abed  pop     r14
0x18000abef  pop     rdi
0x18000abf0  pop     rsi
0x18000abf1  pop     rbp
0x18000abf2  pop     rbx
0x18000abf3  retn
```
