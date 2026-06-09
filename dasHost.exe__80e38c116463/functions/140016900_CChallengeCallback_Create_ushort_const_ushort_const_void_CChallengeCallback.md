# CChallengeCallback::Create(ushort const *,ushort const *,void *,CChallengeCallback * *)

- ea: `0x140016900`
- end: `0x1400169ea`
- name: `?Create@CChallengeCallback@@SAJPEBG0PEAXPEAPEAV1@@Z`
- size: `234`
- prototype: `__int64 __fastcall(const unsigned __int16 *Src, const unsigned __int16 *, void *, struct CChallengeCallback **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x140009850`

## callees

- `0x14000190c`
- `0x140009060`
- `0x140009090`
- `0x140016900`
- `0x14001a83c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1400169b7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1400169b7`

## pseudocode

```c
__int64 __fastcall CChallengeCallback::Create(
        const unsigned __int16 *Src,
        const unsigned __int16 *a2,
        void *a3,
        struct CChallengeCallback **a4)
{
  unsigned int v7; // edi
  __int64 v8; // rbx
  __int64 v9; // rcx
  void *v10; // rax
  void *v11; // rsi
  char *v12; // rbx
  void *v14; // [rsp+68h] [rbp+20h]

  v7 = 0;
  *a4 = 0;
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( Src[v9] );
  v10 = DAF_user_alloc(2 * v9 + 2);
  v11 = v10;
  v14 = v10;
  if ( v10 )
  {
    do
      ++v8;
    while ( Src[v8] );
    memcpy_0(v10, Src, 2 * v8 + 2);
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v12 = (char *)operator new(0x58u);
      *(_QWORD *)v12 = &CChallengeCallback::`vftable'{for `IAepDevicePresenceChallengeCallback'};
      *((_QWORD *)v12 + 1) = &CChallengeCallback::`vftable'{for `IServiceProvider'};
      *((_DWORD *)v12 + 4) = 1;
      *((_QWORD *)v12 + 3) = v11;
      *((_QWORD *)v12 + 4) = 0;
      *((_QWORD *)v12 + 5) = a3;
      InitializeCriticalSection((LPCRITICAL_SECTION)(v12 + 48));
      *a4 = (struct CChallengeCallback *)v12;
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_1400169C2);
        MIDL_user_free(v14);
        return (unsigned int)-2147024882;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v7;
}

```

## disassembly

```asm
0x140016900  mov     [rsp+arg_0], rbx
0x140016905  mov     [rsp+arg_10], rsi
0x14001690a  mov     [rsp+arg_8], rdx
0x14001690f  push    rdi
0x140016910  push    r12
0x140016912  push    r13
0x140016914  push    r14
0x140016916  push    r15
0x140016918  sub     rsp, 20h
0x14001691c  mov     r15, r9
0x14001691f  mov     r12, r8
0x140016922  mov     r14, rcx
0x140016925  xor     r13d, r13d
0x140016928  mov     edi, r13d
0x14001692b  mov     [r9], r13
0x14001692e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140016932  mov     rcx, rbx
0x140016935  inc     rcx
0x140016938  cmp     [r14+rcx*2], r13w
0x14001693d  jnz     short loc_140016935
0x14001693f  lea     rcx, ds:2[rcx*2]
0x140016947  call    DAF_user_alloc
0x14001694c  mov     rsi, rax
0x14001694f  mov     [rsp+48h+arg_18], rax
0x140016954  test    rax, rax
0x140016957  jnz     short loc_140016960
0x140016959  mov     edi, 8007000Eh
0x14001695e  jmp     short loc_1400169D0
0x140016960  inc     rbx
0x140016963  cmp     [r14+rbx*2], r13w
0x140016968  jnz     short loc_140016960
0x14001696a  lea     r8, ds:2[rbx*2]; Size
0x140016972  mov     rdx, r14; Src
0x140016975  mov     rcx, rsi; void *
0x140016978  call    memcpy_0
0x14001697d  nop
0x14001697e  mov     ecx, 58h ; 'X'; Size
0x140016983  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140016988  mov     rbx, rax
0x14001698b  lea     rax, ??_7CChallengeCallback@@6BIAepDevicePresenceChallengeCallback@@@; const CChallengeCallback::`vftable'{for `IAepDevicePresenceChallengeCallback'}
0x140016992  mov     [rbx], rax
0x140016995  lea     rax, ??_7CChallengeCallback@@6BIServiceProvider@@@; const CChallengeCallback::`vftable'{for `IServiceProvider'}
0x14001699c  mov     [rbx+8], rax
0x1400169a0  mov     dword ptr [rbx+10h], 1
0x1400169a7  mov     [rbx+18h], rsi
0x1400169ab  mov     [rbx+20h], r13
0x1400169af  mov     [rbx+28h], r12
0x1400169b3  lea     rcx, [rbx+30h]; lpCriticalSection
0x1400169b7  call    cs:__imp_InitializeCriticalSection
0x1400169bd  mov     [r15], rbx
0x1400169c0  jmp     short loc_1400169D0
0x1400169c2  mov     rcx, [rsp+48h+arg_18]; void *
0x1400169c7  call    MIDL_user_free
0x1400169cc  mov     edi, dword ptr [rsp+48h+arg_8]
0x1400169d0  mov     eax, edi
0x1400169d2  mov     rbx, [rsp+48h+arg_0]
0x1400169d7  mov     rsi, [rsp+48h+arg_10]
0x1400169dc  add     rsp, 20h
0x1400169e0  pop     r15
0x1400169e2  pop     r14
0x1400169e4  pop     r13
0x1400169e6  pop     r12
0x1400169e8  pop     rdi
0x1400169e9  retn
```
