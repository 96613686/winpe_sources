# FormatMsgToBuffer(STRA *,_DEBUG_PRINTS *,char const *,ulong,char const *,char const *,char * *)

- ea: `0x180002224`
- end: `0x18000239f`
- name: `?FormatMsgToBuffer@@YAXPEAVSTRA@@PEAU_DEBUG_PRINTS@@PEBDK22PEAPEAD@Z`
- size: `379`
- prototype: `void __usercall(struct STRA *this@<rcx>, struct _DEBUG_PRINTS *@<rdx>, const char *@<r8>, unsigned int@<r9d>, const char *, const char *, char **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002600`
- `0x180002714`

## callees

- `0x180002224`
- `0x180002b94`

## import_xrefs

- `msvcrt!strnlen` at `0x180002382`
- `msvcrt!strnlen` at `0x180002382`
- `msvcrt!_vsnprintf_s` at `0x1800022e6`
- `msvcrt!_vsnprintf_s` at `0x180002355`
- `msvcrt!_vsnprintf_s` at `0x1800022e6`
- `msvcrt!_vsnprintf_s` at `0x180002355`
- `msvcrt!strrchr` at `0x180002245`
- `msvcrt!strrchr` at `0x180002245`
- `msvcrt!sprintf_s` at `0x1800022a8`
- `msvcrt!sprintf_s` at `0x1800022a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002261`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002261`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000230c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000230c`

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
0x180002224  push    rbx
0x180002226  push    rbp
0x180002227  push    rsi
0x180002228  push    rdi
0x180002229  push    r14
0x18000222b  push    r15
0x18000222d  sub     rsp, 48h
0x180002231  mov     rbp, rdx
0x180002234  mov     rbx, rcx
0x180002237  mov     edx, 5Ch ; '\'; Ch
0x18000223c  mov     rcx, r8; Str
0x18000223f  mov     r14d, r9d
0x180002242  mov     rsi, r8
0x180002245  call    cs:__imp_strrchr
0x18000224c  nop     dword ptr [rax+rax+00h]
0x180002251  mov     rdi, rax
0x180002254  test    rax, rax
0x180002257  jnz     short loc_18000225E
0x180002259  mov     rdi, rsi
0x18000225c  jmp     short loc_180002261
0x18000225e  inc     rdi
0x180002261  call    cs:__imp_GetCurrentThreadId
0x180002268  nop     dword ptr [rax+rax+00h]
0x18000226d  mov     edx, [rbx+28h]; BufferCount
0x180002270  lea     rcx, asc_180005894; "??"
0x180002277  mov     [rsp+78h+var_40], r14d
0x18000227c  lea     r8, Format; "%lu %hs!%hs [%hs @ %d]:"
0x180002283  mov     [rsp+78h+var_48], rdi
0x180002288  test    rbp, rbp
0x18000228b  mov     r9d, eax
0x18000228e  cmovz   rbp, rcx
0x180002292  mov     rcx, [rsp+78h+arg_20]
0x18000229a  mov     [rsp+78h+var_50], rcx
0x18000229f  mov     rcx, [rbx+20h]; Buffer
0x1800022a3  mov     [rsp+78h+ArgList], rbp
0x1800022a8  call    cs:__imp_sprintf_s
0x1800022af  nop     dword ptr [rax+rax+00h]
0x1800022b4  mov     edx, [rbx+28h]
0x1800022b7  or      ebp, 0FFFFFFFFh
0x1800022ba  mov     rcx, [rbx+20h]
0x1800022be  mov     esi, ebp
0x1800022c0  mov     r15, [rsp+78h+arg_30]
0x1800022c8  mov     r9, [rsp+78h+Format]; Format
0x1800022d0  movsxd  rdi, eax
0x1800022d3  sub     esi, edi
0x1800022d5  add     rcx, rdi; Buffer
0x1800022d8  mov     rax, [r15]
0x1800022db  mov     [rsp+78h+ArgList], rax; ArgList
0x1800022e0  lea     r8d, [rsi+rdx]; MaxCount
0x1800022e4  sub     edx, edi; BufferCount
0x1800022e6  call    cs:__imp__vsnprintf_s
0x1800022ed  nop     dword ptr [rax+rax+00h]
0x1800022f2  cmp     eax, ebp
0x1800022f4  jnz     short loc_180002372
0x1800022f6  mov     edx, 2800h; unsigned int
0x1800022fb  cmp     [rbx+28h], edx
0x1800022fe  jnb     short loc_180002333
0x180002300  mov     rcx, rbx; this
0x180002303  call    ?ReallocStorage@BUFFER@@AEAA_NK@Z; BUFFER::ReallocStorage(ulong)
0x180002308  test    al, al
0x18000230a  jnz     short loc_180002333
0x18000230c  call    cs:__imp_GetLastError
0x180002313  nop     dword ptr [rax+rax+00h]
0x180002318  test    eax, eax
0x18000231a  jle     short loc_180002326
0x18000231c  movzx   eax, ax
0x18000231f  or      eax, 80070000h
0x180002324  test    eax, eax
0x180002326  jns     short loc_180002333
0x180002328  mov     rax, [rbx+20h]
0x18000232c  mov     byte ptr [rax], 0
0x18000232f  xor     eax, eax
0x180002331  jmp     short loc_18000238E
0x180002333  mov     ecx, [rbx+28h]
0x180002336  mov     rax, [r15]
0x180002339  mov     r9, [rsp+78h+Format]; Format
0x180002341  mov     [rsp+78h+ArgList], rax; ArgList
0x180002346  lea     r8d, [rsi+rcx]; MaxCount
0x18000234a  sub     ecx, edi
0x18000234c  mov     edx, ecx; BufferCount
0x18000234e  mov     rcx, [rbx+20h]
0x180002352  add     rcx, rdi; Buffer
0x180002355  call    cs:__imp__vsnprintf_s
0x18000235c  nop     dword ptr [rax+rax+00h]
0x180002361  cmp     eax, ebp
0x180002363  jnz     short loc_180002372
0x180002365  mov     ecx, [rbx+28h]
0x180002368  mov     rax, [rbx+20h]
0x18000236c  dec     ecx
0x18000236e  mov     byte ptr [rcx+rax], 0
0x180002372  mov     rcx, [rbx+20h]; String
0x180002376  test    rcx, rcx
0x180002379  jnz     short loc_18000237F
0x18000237b  xor     eax, eax
0x18000237d  jmp     short loc_18000238E
0x18000237f  mov     edx, [rbx+28h]; MaxCount
0x180002382  call    cs:__imp_strnlen
0x180002389  nop     dword ptr [rax+rax+00h]
0x18000238e  mov     [rbx+30h], eax
0x180002391  add     rsp, 48h
0x180002395  pop     r15
0x180002397  pop     r14
0x180002399  pop     rdi
0x18000239a  pop     rsi
0x18000239b  pop     rbp
0x18000239c  pop     rbx
0x18000239d  retn
```
