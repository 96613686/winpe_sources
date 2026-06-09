# FormatMsgToBuffer(STRA *,_DEBUG_PRINTS *,char const *,ulong,char const *,char const *,char * *)

- ea: `0x180002154`
- end: `0x1800022a4`
- name: `?FormatMsgToBuffer@@YAXPEAVSTRA@@PEAU_DEBUG_PRINTS@@PEBDK22PEAPEAD@Z`
- size: `336`
- prototype: `void __usercall(struct STRA *this@<rcx>, struct _DEBUG_PRINTS *@<rdx>, const char *@<r8>, unsigned int@<r9d>, const char *, const char *, char **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800024c0`
- `0x1800025bc`

## callees

- `0x180002154`
- `0x1800029c0`

## import_xrefs

- `msvcrt!strnlen` at `0x18000228e`
- `msvcrt!strnlen` at `0x18000228e`
- `msvcrt!_vsnprintf_s` at `0x180002204`
- `msvcrt!_vsnprintf_s` at `0x180002267`
- `msvcrt!_vsnprintf_s` at `0x180002204`
- `msvcrt!_vsnprintf_s` at `0x180002267`
- `msvcrt!strrchr` at `0x180002175`
- `msvcrt!strrchr` at `0x180002175`
- `msvcrt!sprintf_s` at `0x1800021cc`
- `msvcrt!sprintf_s` at `0x1800021cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000218b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000218b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002224`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002224`

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
  signed int LastError; // eax
  bool v18; // sf
  int v19; // eax
  const char *v20; // rcx

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
    if ( *((_DWORD *)this + 10) < 0x2800u && !BUFFER::ReallocStorage((BUFFER *)this, 0x2800u) )
    {
      LastError = GetLastError();
      v18 = LastError < 0;
      if ( LastError > 0 )
        v18 = 1;
      if ( v18 )
      {
        *this[4] = 0;
        v19 = 0;
        goto LABEL_18;
      }
    }
    if ( _vsnprintf_s(
           &this[4][v15],
           (unsigned int)(*((_DWORD *)this + 10) - v15),
           (unsigned int)(v16 + *((_DWORD *)this + 10)),
           Format,
           *a7) == -1 )
      this[4][*((_DWORD *)this + 10) - 1] = 0;
  }
  v20 = this[4];
  if ( v20 )
    v19 = strnlen(v20, *((unsigned int *)this + 10));
  else
    v19 = 0;
LABEL_18:
  *((_DWORD *)this + 12) = v19;
}

```

## disassembly

```asm
0x180002154  push    rbx
0x180002156  push    rbp
0x180002157  push    rsi
0x180002158  push    rdi
0x180002159  push    r14
0x18000215b  push    r15
0x18000215d  sub     rsp, 48h
0x180002161  mov     rbp, rdx
0x180002164  mov     rbx, rcx
0x180002167  mov     edx, 5Ch ; '\'; Ch
0x18000216c  mov     rcx, r8; Str
0x18000216f  mov     r14d, r9d
0x180002172  mov     rsi, r8
0x180002175  call    cs:__imp_strrchr
0x18000217b  mov     rdi, rax
0x18000217e  test    rax, rax
0x180002181  jnz     short loc_180002188
0x180002183  mov     rdi, rsi
0x180002186  jmp     short loc_18000218B
0x180002188  inc     rdi
0x18000218b  call    cs:__imp_GetCurrentThreadId
0x180002191  mov     edx, [rbx+28h]; BufferCount
0x180002194  lea     rcx, asc_180004894; "??"
0x18000219b  mov     [rsp+78h+var_40], r14d
0x1800021a0  lea     r8, Format; "%lu %hs!%hs [%hs @ %d]:"
0x1800021a7  mov     [rsp+78h+var_48], rdi
0x1800021ac  test    rbp, rbp
0x1800021af  mov     r9d, eax
0x1800021b2  cmovz   rbp, rcx
0x1800021b6  mov     rcx, [rsp+78h+arg_20]
0x1800021be  mov     [rsp+78h+var_50], rcx
0x1800021c3  mov     rcx, [rbx+20h]; Buffer
0x1800021c7  mov     [rsp+78h+ArgList], rbp
0x1800021cc  call    cs:__imp_sprintf_s
0x1800021d2  mov     edx, [rbx+28h]
0x1800021d5  or      ebp, 0FFFFFFFFh
0x1800021d8  mov     rcx, [rbx+20h]
0x1800021dc  mov     esi, ebp
0x1800021de  mov     r15, [rsp+78h+arg_30]
0x1800021e6  mov     r9, [rsp+78h+Format]; Format
0x1800021ee  movsxd  rdi, eax
0x1800021f1  sub     esi, edi
0x1800021f3  add     rcx, rdi; Buffer
0x1800021f6  mov     rax, [r15]
0x1800021f9  mov     [rsp+78h+ArgList], rax; ArgList
0x1800021fe  lea     r8d, [rsi+rdx]; MaxCount
0x180002202  sub     edx, edi; BufferCount
0x180002204  call    cs:__imp__vsnprintf_s
0x18000220a  cmp     eax, ebp
0x18000220c  jnz     short loc_18000227E
0x18000220e  mov     edx, 2800h; unsigned int
0x180002213  cmp     [rbx+28h], edx
0x180002216  jnb     short loc_180002245
0x180002218  mov     rcx, rbx; this
0x18000221b  call    ?ReallocStorage@BUFFER@@AEAA_NK@Z; BUFFER::ReallocStorage(ulong)
0x180002220  test    al, al
0x180002222  jnz     short loc_180002245
0x180002224  call    cs:__imp_GetLastError
0x18000222a  test    eax, eax
0x18000222c  jle     short loc_180002238
0x18000222e  movzx   eax, ax
0x180002231  or      eax, 80070000h
0x180002236  test    eax, eax
0x180002238  jns     short loc_180002245
0x18000223a  mov     rax, [rbx+20h]
0x18000223e  mov     byte ptr [rax], 0
0x180002241  xor     eax, eax
0x180002243  jmp     short loc_180002294
0x180002245  mov     ecx, [rbx+28h]
0x180002248  mov     rax, [r15]
0x18000224b  mov     r9, [rsp+78h+Format]; Format
0x180002253  mov     [rsp+78h+ArgList], rax; ArgList
0x180002258  lea     r8d, [rsi+rcx]; MaxCount
0x18000225c  sub     ecx, edi
0x18000225e  mov     edx, ecx; BufferCount
0x180002260  mov     rcx, [rbx+20h]
0x180002264  add     rcx, rdi; Buffer
0x180002267  call    cs:__imp__vsnprintf_s
0x18000226d  cmp     eax, ebp
0x18000226f  jnz     short loc_18000227E
0x180002271  mov     ecx, [rbx+28h]
0x180002274  mov     rax, [rbx+20h]
0x180002278  dec     ecx
0x18000227a  mov     byte ptr [rcx+rax], 0
0x18000227e  mov     rcx, [rbx+20h]; String
0x180002282  test    rcx, rcx
0x180002285  jnz     short loc_18000228B
0x180002287  xor     eax, eax
0x180002289  jmp     short loc_180002294
0x18000228b  mov     edx, [rbx+28h]; MaxCount
0x18000228e  call    cs:__imp_strnlen
0x180002294  mov     [rbx+30h], eax
0x180002297  add     rsp, 48h
0x18000229b  pop     r15
0x18000229d  pop     r14
0x18000229f  pop     rdi
0x1800022a0  pop     rsi
0x1800022a1  pop     rbp
0x1800022a2  pop     rbx
0x1800022a3  retn
```
