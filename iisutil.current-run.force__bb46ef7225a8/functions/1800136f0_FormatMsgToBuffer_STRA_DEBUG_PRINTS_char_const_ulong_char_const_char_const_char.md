# FormatMsgToBuffer(STRA *,_DEBUG_PRINTS *,char const *,ulong,char const *,char const *,char * *)

- ea: `0x1800136f0`
- end: `0x180013825`
- name: `?FormatMsgToBuffer@@YAXPEAVSTRA@@PEAU_DEBUG_PRINTS@@PEBDK22PEAPEAD@Z`
- size: `309`
- prototype: `void __usercall(struct STRA *this@<rcx>, struct _DEBUG_PRINTS *@<rdx>, const char *@<r8>, unsigned int@<r9d>, const char *, const char *, char **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180007300`
- `0x1800180c0`

## callees

- `0x180010910`
- `0x1800136f0`

## import_xrefs

- `msvcrt!_vsnprintf_s` at `0x1800137a0`
- `msvcrt!_vsnprintf_s` at `0x1800137e8`
- `msvcrt!_vsnprintf_s` at `0x1800137a0`
- `msvcrt!_vsnprintf_s` at `0x1800137e8`
- `msvcrt!strrchr` at `0x180013711`
- `msvcrt!strrchr` at `0x180013711`
- `msvcrt!sprintf_s` at `0x180013768`
- `msvcrt!sprintf_s` at `0x180013768`
- `msvcrt!strnlen` at `0x18001380f`
- `msvcrt!strnlen` at `0x18001380f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013727`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013727`

## pseudocode

```c
void __fastcall FormatMsgToBuffer(
        char **this,
        struct _DEBUG_PRINTS *a2,
        const char *a3,
        int a4,
        const char *a5,
        char *Format,
        char **a7)
{
  char *v11; // rax
  const char *v12; // rdi
  DWORD CurrentThreadId; // eax
  int v14; // eax
  __int64 v15; // rdi
  int v16; // esi
  int v17; // eax
  const char *v18; // rcx

  v11 = strrchr(a3, 92);
  if ( v11 )
    v12 = v11 + 1;
  else
    v12 = a3;
  CurrentThreadId = GetCurrentThreadId();
  if ( !a2 )
    a2 = (struct _DEBUG_PRINTS *)"??";
  v14 = sprintf_s(this[4], *((unsigned int *)this + 10), "%lu %hs!%hs [%hs @ %d]:", CurrentThreadId, a2, a5, v12, a4);
  v15 = v14;
  v16 = -1 - v14;
  if ( _vsnprintf_s(
         &this[4][v14],
         (unsigned int)(*((_DWORD *)this + 10) - v14),
         (unsigned int)(-1 - v14 + *((_DWORD *)this + 10)),
         Format,
         *a7) == -1 )
  {
    if ( STRA::Resize((STRA *)this, 0x2800u) < 0 )
    {
      *this[4] = 0;
      v17 = 0;
      goto LABEL_14;
    }
    if ( _vsnprintf_s(
           &this[4][v15],
           (unsigned int)(*((_DWORD *)this + 10) - v15),
           (unsigned int)(v16 + *((_DWORD *)this + 10)),
           Format,
           *a7) == -1 )
      this[4][*((_DWORD *)this + 10) - 1] = 0;
  }
  v18 = this[4];
  if ( v18 )
    v17 = strnlen(v18, *((unsigned int *)this + 10));
  else
    v17 = 0;
LABEL_14:
  *((_DWORD *)this + 12) = v17;
}

```

## disassembly

```asm
0x1800136f0  push    rbx
0x1800136f2  push    rbp
0x1800136f3  push    rsi
0x1800136f4  push    rdi
0x1800136f5  push    r14
0x1800136f7  push    r15
0x1800136f9  sub     rsp, 48h
0x1800136fd  mov     rbp, rdx
0x180013700  mov     rbx, rcx
0x180013703  mov     edx, 5Ch ; '\'; Ch
0x180013708  mov     rcx, r8; Str
0x18001370b  mov     r14d, r9d
0x18001370e  mov     rsi, r8
0x180013711  call    cs:__imp_strrchr
0x180013717  mov     rdi, rax
0x18001371a  test    rax, rax
0x18001371d  jnz     short loc_180013724
0x18001371f  mov     rdi, rsi
0x180013722  jmp     short loc_180013727
0x180013724  inc     rdi
0x180013727  call    cs:__imp_GetCurrentThreadId
0x18001372d  mov     edx, [rbx+28h]; BufferCount
0x180013730  lea     rcx, asc_180030BCC; "??"
0x180013737  mov     [rsp+78h+var_40], r14d
0x18001373c  lea     r8, aLuHsHsHsD_0; "%lu %hs!%hs [%hs @ %d]:"
0x180013743  mov     [rsp+78h+var_48], rdi
0x180013748  test    rbp, rbp
0x18001374b  mov     r9d, eax
0x18001374e  cmovz   rbp, rcx
0x180013752  mov     rcx, [rsp+78h+arg_20]
0x18001375a  mov     [rsp+78h+var_50], rcx
0x18001375f  mov     rcx, [rbx+20h]; Buffer
0x180013763  mov     [rsp+78h+ArgList], rbp
0x180013768  call    cs:__imp_sprintf_s
0x18001376e  mov     edx, [rbx+28h]
0x180013771  or      ebp, 0FFFFFFFFh
0x180013774  mov     rcx, [rbx+20h]
0x180013778  mov     esi, ebp
0x18001377a  mov     r15, [rsp+78h+arg_30]
0x180013782  mov     r9, [rsp+78h+Format]; Format
0x18001378a  movsxd  rdi, eax
0x18001378d  sub     esi, edi
0x18001378f  add     rcx, rdi; Buffer
0x180013792  mov     rax, [r15]
0x180013795  mov     [rsp+78h+ArgList], rax; ArgList
0x18001379a  lea     r8d, [rsi+rdx]; MaxCount
0x18001379e  sub     edx, edi; BufferCount
0x1800137a0  call    cs:__imp__vsnprintf_s
0x1800137a6  cmp     eax, ebp
0x1800137a8  jnz     short loc_1800137FF
0x1800137aa  mov     edx, 2800h; unsigned int
0x1800137af  mov     rcx, rbx; this
0x1800137b2  call    ?Resize@STRA@@QEAAJK@Z; STRA::Resize(ulong)
0x1800137b7  test    eax, eax
0x1800137b9  jns     short loc_1800137C6
0x1800137bb  mov     rax, [rbx+20h]
0x1800137bf  mov     byte ptr [rax], 0
0x1800137c2  xor     eax, eax
0x1800137c4  jmp     short loc_180013815
0x1800137c6  mov     ecx, [rbx+28h]
0x1800137c9  mov     rax, [r15]
0x1800137cc  mov     r9, [rsp+78h+Format]; Format
0x1800137d4  mov     [rsp+78h+ArgList], rax; ArgList
0x1800137d9  lea     r8d, [rsi+rcx]; MaxCount
0x1800137dd  sub     ecx, edi
0x1800137df  mov     edx, ecx; BufferCount
0x1800137e1  mov     rcx, [rbx+20h]
0x1800137e5  add     rcx, rdi; Buffer
0x1800137e8  call    cs:__imp__vsnprintf_s
0x1800137ee  cmp     eax, ebp
0x1800137f0  jnz     short loc_1800137FF
0x1800137f2  mov     ecx, [rbx+28h]
0x1800137f5  mov     rax, [rbx+20h]
0x1800137f9  dec     ecx
0x1800137fb  mov     byte ptr [rcx+rax], 0
0x1800137ff  mov     rcx, [rbx+20h]; String
0x180013803  test    rcx, rcx
0x180013806  jnz     short loc_18001380C
0x180013808  xor     eax, eax
0x18001380a  jmp     short loc_180013815
0x18001380c  mov     edx, [rbx+28h]; MaxCount
0x18001380f  call    cs:__imp_strnlen
0x180013815  mov     [rbx+30h], eax
0x180013818  add     rsp, 48h
0x18001381c  pop     r15
0x18001381e  pop     r14
0x180013820  pop     rdi
0x180013821  pop     rsi
0x180013822  pop     rbp
0x180013823  pop     rbx
0x180013824  retn
```
