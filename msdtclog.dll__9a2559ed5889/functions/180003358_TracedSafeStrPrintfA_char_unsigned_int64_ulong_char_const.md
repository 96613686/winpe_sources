# TracedSafeStrPrintfA(char *,unsigned __int64,ulong *,char const *,...)

- ea: `0x180003358`
- end: `0x180003414`
- name: `?TracedSafeStrPrintfA@@YAXPEAD_KPEAKPEBDZZ`
- size: `188`
- prototype: `void(char *, unsigned __int64, unsigned int *, const char *, ...)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000341c`
- `0x18000392c`
- `0x180003a5c`

## callees

- `0x180003358`
- `0x18000d998`
- `0x18000dc8c`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x18000339a`
- `msvcrt!_vsnprintf` at `0x18000339a`

## string_xrefs

- `0x1800033ee`: `com\complus\dtc\inc\tracedstrsafe.h`

## pseudocode

```c
void TracedSafeStrPrintfA(char *a1, unsigned __int64 a2, unsigned int *a3, const char *a4, ...)
{
  int v6; // ecx
  unsigned __int64 v7; // rbx
  int v8; // eax
  __int64 v9; // rax
  va_list ArgList; // [rsp+70h] [rbp+28h] BYREF

  va_start(ArgList, a4);
  if ( !a2 )
  {
    v6 = -2147024809;
    goto LABEL_14;
  }
  if ( a2 > 0x7FFFFFFF )
  {
    v6 = -2147024809;
    *a1 = 0;
    goto LABEL_14;
  }
  v7 = a2 - 1;
  v8 = _vsnprintf(a1, a2 - 1, a4, ArgList);
  if ( v8 < 0 || v8 > v7 )
  {
    a1[v7] = 0;
    v6 = -2147024774;
  }
  else
  {
    v6 = 0;
    if ( v8 == v7 )
      a1[v7] = 0;
  }
  if ( v6 < 0 )
  {
LABEL_14:
    TraceFile(v6, "failed in TracedSafeStrPrintfA", "com\\complus\\dtc\\inc\\tracedstrsafe.h", 0x1Eu);
    *a3 = 0;
    DtcInternalErrorW(L"failed in TracedSafeStrPrintfA");
  }
  v9 = -1;
  do
    ++v9;
  while ( a1[v9] );
  *a3 = v9;
}

```

## disassembly

```asm
0x180003358  mov     [rsp+arg_18], r9
0x18000335d  push    rbx
0x18000335e  push    rsi
0x18000335f  push    rdi
0x180003360  sub     rsp, 30h
0x180003364  mov     [rsp+48h+var_28], 0
0x18000336d  mov     rax, r9
0x180003370  lea     r9, [rsp+48h+ArgList]; ArgList
0x180003375  mov     rsi, r8
0x180003378  mov     rdi, rcx
0x18000337b  test    rdx, rdx
0x18000337e  jz      short loc_1800033DB
0x180003380  cmp     rdx, 7FFFFFFFh
0x180003387  jbe     short loc_180003390
0x180003389  mov     ecx, 80070057h; Buffer
0x18000338e  jmp     short loc_1800033E5
0x180003390  lea     rbx, [rdx-1]
0x180003394  mov     r8, rax; Format
0x180003397  mov     rdx, rbx; BufferCount
0x18000339a  call    cs:__imp__vsnprintf
0x1800033a0  test    eax, eax
0x1800033a2  js      short loc_1800033B7
0x1800033a4  cdqe
0x1800033a6  cmp     rax, rbx
0x1800033a9  ja      short loc_1800033B7
0x1800033ab  xor     ecx, ecx
0x1800033ad  cmp     rax, rbx
0x1800033b0  jnz     short loc_1800033C0
0x1800033b2  mov     [rbx+rdi], cl
0x1800033b5  jmp     short loc_1800033C0
0x1800033b7  mov     byte ptr [rbx+rdi], 0
0x1800033bb  mov     ecx, 8007007Ah
0x1800033c0  test    ecx, ecx
0x1800033c2  js      short loc_1800033E8
0x1800033c4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800033c8  inc     rax
0x1800033cb  cmp     byte ptr [rdi+rax], 0
0x1800033cf  jnz     short loc_1800033C8
0x1800033d1  mov     [rsi], eax
0x1800033d3  add     rsp, 30h
0x1800033d7  pop     rdi
0x1800033d8  pop     rsi
0x1800033d9  pop     rbx
0x1800033da  retn
0x1800033db  mov     ecx, 80070057h; int
0x1800033e0  test    rdx, rdx
0x1800033e3  jz      short loc_1800033E8
0x1800033e5  mov     byte ptr [rdi], 0
0x1800033e8  mov     r9d, 1Eh; unsigned int
0x1800033ee  lea     r8, aComComplusDtcI; "com\\complus\\dtc\\inc\\tracedstrsafe.h"
0x1800033f5  lea     rdx, aFailedInTraced_9; "failed in TracedSafeStrPrintfA"
0x1800033fc  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180003401  lea     rcx, aFailedInTraced_6; "failed in TracedSafeStrPrintfA"
0x180003408  mov     dword ptr [rsi], 0
0x18000340e  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
```
