# CFtpEfe_Create(ulong,tagFORMATETC * const,tagSTGMEDIUM * const,CFtpObj *,IEnumFORMATETC * *)

- ea: `0x180014dd8`
- end: `0x180014f11`
- name: `?CFtpEfe_Create@@YAJKQEAUtagFORMATETC@@QEAUtagSTGMEDIUM@@PEAVCFtpObj@@PEAPEAUIEnumFORMATETC@@@Z`
- size: `313`
- prototype: `__int64 __fastcall(unsigned int, struct tagFORMATETC *const, struct tagSTGMEDIUM *const, struct CFtpObj *, struct IEnumFORMATETC **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180019b50`

## callees

- `0x180014dd8`
- `0x180023adc`
- `0x180026b34`
- `0x180026d60`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014eb4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014eb4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014ed0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014ed0`

## pseudocode

```c
__int64 __fastcall CFtpEfe_Create(
        unsigned int a1,
        struct tagFORMATETC *const a2,
        struct tagSTGMEDIUM *const a3,
        struct CFtpObj *a4,
        struct IEnumFORMATETC **a5)
{
  unsigned int v9; // ebp
  __int64 *v10; // rbx
  HDSA v11; // rax
  __int64 i; // rsi
  struct tagFORMATETC *v13; // r8
  DWORD tymed; // edx
  __int64 v15; // rax

  v9 = -2147024882;
  v10 = (__int64 *)operator new(0x28u);
  if ( v10 )
  {
    *((_DWORD *)v10 + 2) = 1;
    *v10 = (__int64)&CFtpEfe::`vftable';
    _InterlockedIncrement((volatile signed __int32 *)&g_cRef);
    v10[4] = 0;
    v11 = DSA_Create(32, 10);
    v10[3] = (__int64)v11;
    if ( v11 )
    {
      for ( i = 0; (unsigned int)i < a1; i = (unsigned int)(i + 1) )
      {
        v13 = &a2[(unsigned int)i];
        tymed = v13->tymed;
        if ( tymed == 4 || a3 && tymed == a3[i].tymed )
          DSA_SetItem((HDSA)v10[3], i, v13);
      }
    }
    if ( a4 )
    {
      v10[4] = (__int64)a4;
      (*(void (__fastcall **)(struct CFtpObj *))(*(_QWORD *)a4 + 8LL))(a4);
    }
    v15 = *v10;
    if ( v10[3] )
    {
      v9 = (*(__int64 (__fastcall **)(__int64 *, GUID *, struct IEnumFORMATETC **))v15)(v10, &IID_IEnumFORMATETC, a5);
      (*(void (__fastcall **)(__int64 *))(*v10 + 16))(v10);
    }
    else
    {
      (*(void (__fastcall **)(__int64 *))(v15 + 16))(v10);
      EnterCriticalSection(&g_csDll);
      (*(void (__fastcall **)(__int64 *))(*v10 + 16))(v10);
      LeaveCriticalSection(&g_csDll);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180014dd8  push    rbx
0x180014dda  push    rbp
0x180014ddb  push    rsi
0x180014ddc  push    rdi
0x180014ddd  push    r12
0x180014ddf  push    r14
0x180014de1  push    r15
0x180014de3  sub     rsp, 20h
0x180014de7  mov     r14d, ecx
0x180014dea  mov     rdi, r9
0x180014ded  mov     ecx, 28h ; '('; unsigned __int64
0x180014df2  mov     r15, r8
0x180014df5  mov     r12, rdx
0x180014df8  mov     ebp, 8007000Eh
0x180014dfd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014e02  mov     rbx, rax
0x180014e05  test    rax, rax
0x180014e08  jz      loc_180014F00
0x180014e0e  lea     rax, ??_7CFtpEfe@@6B@; const CFtpEfe::`vftable'
0x180014e15  mov     dword ptr [rbx+8], 1
0x180014e1c  mov     [rbx], rax
0x180014e1f  lock inc cs:?g_cRef@@3KA; ulong g_cRef
0x180014e26  mov     edx, 0Ah; cItemGrow
0x180014e2b  mov     qword ptr [rbx+20h], 0
0x180014e33  lea     ecx, [rdx+16h]; cbItem
0x180014e36  call    DSA_Create
0x180014e3b  mov     [rbx+18h], rax
0x180014e3f  test    rax, rax
0x180014e42  jz      short loc_180014E7F
0x180014e44  xor     esi, esi
0x180014e46  test    r14d, r14d
0x180014e49  jz      short loc_180014E7F
0x180014e4b  mov     r8d, esi
0x180014e4e  shl     r8, 5
0x180014e52  add     r8, r12; pitem
0x180014e55  mov     edx, [r8+18h]
0x180014e59  cmp     edx, 4
0x180014e5c  jz      short loc_180014E6D
0x180014e5e  test    r15, r15
0x180014e61  jz      short loc_180014E78
0x180014e63  lea     rax, [rsi+rsi*2]
0x180014e67  cmp     edx, [r15+rax*8]
0x180014e6b  jnz     short loc_180014E78
0x180014e6d  mov     rcx, [rbx+18h]; hdsa
0x180014e71  mov     edx, esi; i
0x180014e73  call    DSA_SetItem
0x180014e78  inc     esi
0x180014e7a  cmp     esi, r14d
0x180014e7d  jb      short loc_180014E4B
0x180014e7f  test    rdi, rdi
0x180014e82  jz      short loc_180014E97
0x180014e84  mov     [rbx+20h], rdi
0x180014e88  mov     rcx, rdi
0x180014e8b  mov     rax, [rdi]
0x180014e8e  mov     rax, [rax+8]
0x180014e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e97  cmp     qword ptr [rbx+18h], 0
0x180014e9c  mov     rcx, rbx
0x180014e9f  mov     rax, [rbx]
0x180014ea2  jnz     short loc_180014ED8
0x180014ea4  mov     rax, [rax+10h]
0x180014ea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ead  lea     rcx, g_csDll; lpCriticalSection
0x180014eb4  call    cs:__imp_EnterCriticalSection
0x180014eba  mov     rax, [rbx]
0x180014ebd  mov     rcx, rbx
0x180014ec0  mov     rax, [rax+10h]
0x180014ec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ec9  lea     rcx, g_csDll; lpCriticalSection
0x180014ed0  call    cs:__imp_LeaveCriticalSection
0x180014ed6  jmp     short loc_180014F00
0x180014ed8  mov     r8, [rsp+58h+arg_20]
0x180014ee0  lea     rdx, IID_IEnumFORMATETC
0x180014ee7  mov     rax, [rax]
0x180014eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014eef  mov     rcx, [rbx]
0x180014ef2  mov     ebp, eax
0x180014ef4  mov     rax, [rcx+10h]
0x180014ef8  mov     rcx, rbx
0x180014efb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f00  mov     eax, ebp
0x180014f02  add     rsp, 20h
0x180014f06  pop     r15
0x180014f08  pop     r14
0x180014f0a  pop     r12
0x180014f0c  pop     rdi
0x180014f0d  pop     rsi
0x180014f0e  pop     rbp
0x180014f0f  pop     rbx
0x180014f10  retn
```
