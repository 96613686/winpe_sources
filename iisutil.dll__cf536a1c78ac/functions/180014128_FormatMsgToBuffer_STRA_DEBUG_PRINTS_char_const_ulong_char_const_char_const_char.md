# FormatMsgToBuffer(STRA *,_DEBUG_PRINTS *,char const *,ulong,char const *,char const *,char * *)

- ea: `0x180014128`
- end: `0x180014282`
- name: `?FormatMsgToBuffer@@YAXPEAVSTRA@@PEAU_DEBUG_PRINTS@@PEBDK22PEAPEAD@Z`
- size: `346`
- prototype: `void __fastcall(char **this, struct _DEBUG_PRINTS *, const char *, int, const char *, char *Format, char **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180008000`
- `0x180018ec0`

## callees

- `0x180011b40`
- `0x180014128`

## import_xrefs

- `msvcrt!_vsnprintf_s` at `0x1800141ea`
- `msvcrt!_vsnprintf_s` at `0x180014238`
- `msvcrt!_vsnprintf_s` at `0x1800141ea`
- `msvcrt!_vsnprintf_s` at `0x180014238`
- `msvcrt!strrchr` at `0x180014149`
- `msvcrt!strrchr` at `0x180014149`
- `msvcrt!sprintf_s` at `0x1800141ac`
- `msvcrt!sprintf_s` at `0x1800141ac`
- `msvcrt!strnlen` at `0x180014265`
- `msvcrt!strnlen` at `0x180014265`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014165`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014165`

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
0x180014128  push    rbx
0x18001412a  push    rbp
0x18001412b  push    rsi
0x18001412c  push    rdi
0x18001412d  push    r14
0x18001412f  push    r15
0x180014131  sub     rsp, 48h
0x180014135  mov     rbp, rdx
0x180014138  mov     rbx, rcx
0x18001413b  mov     edx, 5Ch ; '\'; Ch
0x180014140  mov     rcx, r8; Str
0x180014143  mov     r14d, r9d
0x180014146  mov     rsi, r8
0x180014149  call    cs:__imp_strrchr
0x180014150  nop     dword ptr [rax+rax+00h]
0x180014155  mov     rdi, rax
0x180014158  test    rax, rax
0x18001415b  jnz     short loc_180014162
0x18001415d  mov     rdi, rsi
0x180014160  jmp     short loc_180014165
0x180014162  inc     rdi
0x180014165  call    cs:__imp_GetCurrentThreadId
0x18001416c  nop     dword ptr [rax+rax+00h]
0x180014171  mov     edx, [rbx+28h]; BufferCount
0x180014174  lea     rcx, asc_180032BDC; "??"
0x18001417b  mov     [rsp+78h+var_40], r14d
0x180014180  lea     r8, aLuHsHsHsD_0; "%lu %hs!%hs [%hs @ %d]:"
0x180014187  mov     [rsp+78h+var_48], rdi
0x18001418c  test    rbp, rbp
0x18001418f  mov     r9d, eax
0x180014192  cmovz   rbp, rcx
0x180014196  mov     rcx, [rsp+78h+arg_20]
0x18001419e  mov     [rsp+78h+var_50], rcx
0x1800141a3  mov     rcx, [rbx+20h]; Buffer
0x1800141a7  mov     [rsp+78h+ArgList], rbp
0x1800141ac  call    cs:__imp_sprintf_s
0x1800141b3  nop     dword ptr [rax+rax+00h]
0x1800141b8  mov     edx, [rbx+28h]
0x1800141bb  or      ebp, 0FFFFFFFFh
0x1800141be  mov     rcx, [rbx+20h]
0x1800141c2  mov     esi, ebp
0x1800141c4  mov     r15, [rsp+78h+arg_30]
0x1800141cc  mov     r9, [rsp+78h+Format]; Format
0x1800141d4  movsxd  rdi, eax
0x1800141d7  sub     esi, edi
0x1800141d9  add     rcx, rdi; Buffer
0x1800141dc  mov     rax, [r15]
0x1800141df  mov     [rsp+78h+ArgList], rax; ArgList
0x1800141e4  lea     r8d, [rsi+rdx]; MaxCount
0x1800141e8  sub     edx, edi; BufferCount
0x1800141ea  call    cs:__imp__vsnprintf_s
0x1800141f1  nop     dword ptr [rax+rax+00h]
0x1800141f6  cmp     eax, ebp
0x1800141f8  jnz     short loc_180014255
0x1800141fa  mov     edx, 2800h; unsigned int
0x1800141ff  mov     rcx, rbx; this
0x180014202  call    ?Resize@STRA@@QEAAJK@Z; STRA::Resize(ulong)
0x180014207  test    eax, eax
0x180014209  jns     short loc_180014216
0x18001420b  mov     rax, [rbx+20h]
0x18001420f  mov     byte ptr [rax], 0
0x180014212  xor     eax, eax
0x180014214  jmp     short loc_180014271
0x180014216  mov     ecx, [rbx+28h]
0x180014219  mov     rax, [r15]
0x18001421c  mov     r9, [rsp+78h+Format]; Format
0x180014224  mov     [rsp+78h+ArgList], rax; ArgList
0x180014229  lea     r8d, [rsi+rcx]; MaxCount
0x18001422d  sub     ecx, edi
0x18001422f  mov     edx, ecx; BufferCount
0x180014231  mov     rcx, [rbx+20h]
0x180014235  add     rcx, rdi; Buffer
0x180014238  call    cs:__imp__vsnprintf_s
0x18001423f  nop     dword ptr [rax+rax+00h]
0x180014244  cmp     eax, ebp
0x180014246  jnz     short loc_180014255
0x180014248  mov     ecx, [rbx+28h]
0x18001424b  mov     rax, [rbx+20h]
0x18001424f  dec     ecx
0x180014251  mov     byte ptr [rcx+rax], 0
0x180014255  mov     rcx, [rbx+20h]; String
0x180014259  test    rcx, rcx
0x18001425c  jnz     short loc_180014262
0x18001425e  xor     eax, eax
0x180014260  jmp     short loc_180014271
0x180014262  mov     edx, [rbx+28h]; MaxCount
0x180014265  call    cs:__imp_strnlen
0x18001426c  nop     dword ptr [rax+rax+00h]
0x180014271  mov     [rbx+30h], eax
0x180014274  add     rsp, 48h
0x180014278  pop     r15
0x18001427a  pop     r14
0x18001427c  pop     rdi
0x18001427d  pop     rsi
0x18001427e  pop     rbp
0x18001427f  pop     rbx
0x180014280  retn
```
