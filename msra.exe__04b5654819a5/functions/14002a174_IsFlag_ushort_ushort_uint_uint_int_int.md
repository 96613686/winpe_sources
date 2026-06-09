# IsFlag(ushort *,ushort *,uint,uint,int *,int *)

- ea: `0x14002a174`
- end: `0x14002a3ca`
- name: `?IsFlag@@YAHPEAG0IIPEAH1@Z`
- size: `598`
- prototype: `__int64 __usercall@<rax>(PCNZWCH lpString1@<rcx>, unsigned __int16 *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, int *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140012794`

## callees

- `0x1400020f4`
- `0x140002463`
- `0x140008088`
- `0x14002a174`
- `0x140034ce4`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x14002a2ad`
- `KERNEL32!CompareStringW` at `0x14002a2dc`
- `KERNEL32!CompareStringW` at `0x14002a30d`
- `KERNEL32!CompareStringW` at `0x14002a33a`
- `KERNEL32!CompareStringW` at `0x14002a2ad`
- `KERNEL32!CompareStringW` at `0x14002a2dc`
- `KERNEL32!CompareStringW` at `0x14002a30d`
- `KERNEL32!CompareStringW` at `0x14002a33a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14002a37a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14002a37a`

## string_xrefs

- `0x14002a2be`: `CreateRAConnectionString`
- `0x14002a251`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x14002a39e`: `base\diagnosis\ra\ui\commonfunc.cpp`

## pseudocode

```c
__int64 __fastcall IsFlag(PCNZWCH lpString1, unsigned __int16 *a2, int a3, int a4, int *a5, int *a6)
{
  unsigned int v10; // ebx
  __int64 v11; // r10
  unsigned __int16 *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rbp
  unsigned __int64 v15; // rax
  unsigned __int16 *v16; // rax
  CEventLogger *v17; // rcx
  unsigned __int16 *lpString2; // rdi
  signed int v19; // eax
  CEventLogger *v20; // rcx

  v10 = 0;
  if ( !a2 )
  {
    v13 = 2147942487LL;
LABEL_25:
    CEventLogger::LogError(
      (CEventLogger *)v13,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x1153u,
      L"IsFlag",
      v13);
    return v10;
  }
  v11 = 0x7FFFFFFF;
  v12 = a2;
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v11;
  }
  while ( v11 );
  v13 = v11 == 0 ? 0x80070057 : 0;
  v14 = (0x7FFFFFFF - v11) & -(__int64)(v11 != 0);
  if ( !v11 )
    goto LABEL_25;
  v15 = 2 * (v14 + 4);
  if ( !is_mul_ok(v14 + 4, 2u) )
    v15 = -1;
  v16 = (unsigned __int16 *)operator new[](v15, (const struct std::nothrow_t *)&std::nothrow);
  lpString2 = v16;
  if ( v16 )
  {
    memset_0(v16, 0, 2 * v14 + 4);
    v19 = StringCchCopyW(lpString2 + 1, v14 + 1, a2);
    if ( v19 >= 0 )
    {
      if ( *((_DWORD *)_AtlModule + 211) != 1
        || CompareStringW(0x7Fu, 1u, a2, -1, L"offerra", -1) == 2
        || CompareStringW(0x7Fu, 1u, a2, -1, L"CreateRAConnectionString", -1) == 2 )
      {
        *lpString2 = 45;
        if ( CompareStringW(0x7Fu, 1u, lpString1, -1, lpString2, -1) == 2
          || (*lpString2 = 47, CompareStringW(0x7Fu, 1u, lpString1, -1, lpString2, -1) == 2) )
        {
          v10 = 1;
          if ( a5 )
            *a5 = 1;
          if ( a3 == a4 )
          {
            if ( a6 )
              *a6 = 1;
          }
          else
          {
            v10 = 0;
          }
        }
      }
    }
    else
    {
      CEventLogger::LogError(
        v20,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
        0x115Du,
        L"IsFlag",
        v19);
    }
    operator delete[](lpString2);
  }
  else
  {
    CEventLogger::LogError(
      v17,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x115Au,
      L"IsFlag",
      0x8007000E);
  }
  return v10;
}

```

## disassembly

```asm
0x14002a174  push    rbx
0x14002a176  push    rbp
0x14002a177  push    rsi
0x14002a178  push    rdi
0x14002a179  push    r12
0x14002a17b  push    r13
0x14002a17d  push    r14
0x14002a17f  push    r15
0x14002a181  sub     rsp, 38h
0x14002a185  mov     r12d, r8d
0x14002a188  mov     r15d, r9d
0x14002a18b  xor     r8d, r8d
0x14002a18e  mov     rsi, rdx
0x14002a191  mov     r14, rcx
0x14002a194  mov     ebx, r8d
0x14002a197  test    rdx, rdx
0x14002a19a  jz      loc_14002A388
0x14002a1a0  mov     edx, 7FFFFFFFh
0x14002a1a5  lea     r13d, [r8+1]
0x14002a1a9  mov     r10d, edx
0x14002a1ac  mov     rax, rsi
0x14002a1af  cmp     [rax], r8w
0x14002a1b3  jz      short loc_14002A1BE
0x14002a1b5  add     rax, 2
0x14002a1b9  sub     r10, r13
0x14002a1bc  jnz     short loc_14002A1AF
0x14002a1be  mov     rax, r10
0x14002a1c1  neg     rax
0x14002a1c4  mov     rax, r10
0x14002a1c7  sbb     ecx, ecx
0x14002a1c9  sub     rdx, r10
0x14002a1cc  not     ecx
0x14002a1ce  and     ecx, 80070057h
0x14002a1d4  neg     rax
0x14002a1d7  sbb     rbp, rbp
0x14002a1da  and     rbp, rdx
0x14002a1dd  test    r10, r10
0x14002a1e0  jz      loc_14002A38D
0x14002a1e6  lea     rcx, [rbp+4]
0x14002a1ea  mov     eax, 2
0x14002a1ef  mul     rcx
0x14002a1f2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14002a1f9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002a200  cmovb   rax, rcx
0x14002a204  mov     rcx, rax; unsigned __int64
0x14002a207  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14002a20c  mov     rdi, rax
0x14002a20f  test    rax, rax
0x14002a212  jnz     short loc_14002A227
0x14002a214  mov     [rsp+78h+cchCount2], 8007000Eh
0x14002a21c  mov     r9d, 115Ah
0x14002a222  jmp     loc_14002A397
0x14002a227  lea     r8, ds:4[rbp*2]; Size
0x14002a22f  xor     edx, edx; Val
0x14002a231  mov     rcx, rdi; void *
0x14002a234  call    memset_0
0x14002a239  lea     rdx, [rbp+1]; unsigned __int64
0x14002a23d  mov     r8, rsi; unsigned __int16 *
0x14002a240  lea     rcx, [rdi+2]; unsigned __int16 *
0x14002a244  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14002a249  test    eax, eax
0x14002a24b  jns     short loc_14002A27B
0x14002a24d  mov     [rsp+78h+cchCount2], eax; unsigned int
0x14002a251  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x14002a258  lea     rax, aIsflag; "IsFlag"
0x14002a25f  mov     r9d, 115Dh; unsigned int
0x14002a265  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14002a26c  mov     [rsp+78h+lpString2], rax; unsigned __int16 *
0x14002a271  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002a276  jmp     loc_14002A377
0x14002a27b  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002a282  or      rbp, 0FFFFFFFFFFFFFFFFh
0x14002a286  cmp     [rax+34Ch], r13d
0x14002a28d  jnz     short loc_14002A2F1
0x14002a28f  lea     rax, aOfferra; "offerra"
0x14002a296  mov     [rsp+78h+cchCount2], ebp; cchCount2
0x14002a29a  mov     r9d, ebp; cchCount1
0x14002a29d  mov     [rsp+78h+lpString2], rax; lpString2
0x14002a2a2  mov     r8, rsi; lpString1
0x14002a2a5  mov     edx, r13d; dwCmpFlags
0x14002a2a8  mov     ecx, 7Fh; Locale
0x14002a2ad  call    cs:__imp_CompareStringW
0x14002a2b4  nop     dword ptr [rax+rax+00h]
0x14002a2b9  cmp     eax, 2
0x14002a2bc  jz      short loc_14002A2F1
0x14002a2be  lea     rax, aCreateraconnec; "CreateRAConnectionString"
0x14002a2c5  mov     [rsp+78h+cchCount2], ebp; cchCount2
0x14002a2c9  mov     r9d, ebp; cchCount1
0x14002a2cc  mov     [rsp+78h+lpString2], rax; lpString2
0x14002a2d1  mov     r8, rsi; lpString1
0x14002a2d4  mov     edx, r13d; dwCmpFlags
0x14002a2d7  mov     ecx, 7Fh; Locale
0x14002a2dc  call    cs:__imp_CompareStringW
0x14002a2e3  nop     dword ptr [rax+rax+00h]
0x14002a2e8  cmp     eax, 2
0x14002a2eb  jnz     loc_14002A377
0x14002a2f1  mov     [rsp+78h+cchCount2], ebp; cchCount2
0x14002a2f5  mov     r9d, ebp; cchCount1
0x14002a2f8  mov     r8, r14; lpString1
0x14002a2fb  mov     [rsp+78h+lpString2], rdi; lpString2
0x14002a300  mov     edx, r13d; dwCmpFlags
0x14002a303  mov     word ptr [rdi], 2Dh ; '-'
0x14002a308  mov     ecx, 7Fh; Locale
0x14002a30d  call    cs:__imp_CompareStringW
0x14002a314  nop     dword ptr [rax+rax+00h]
0x14002a319  cmp     eax, 2
0x14002a31c  jz      short loc_14002A34B
0x14002a31e  mov     [rsp+78h+cchCount2], ebp; cchCount2
0x14002a322  mov     r9d, ebp; cchCount1
0x14002a325  mov     r8, r14; lpString1
0x14002a328  mov     [rsp+78h+lpString2], rdi; lpString2
0x14002a32d  mov     edx, r13d; dwCmpFlags
0x14002a330  mov     word ptr [rdi], 2Fh ; '/'
0x14002a335  mov     ecx, 7Fh; Locale
0x14002a33a  call    cs:__imp_CompareStringW
0x14002a341  nop     dword ptr [rax+rax+00h]
0x14002a346  cmp     eax, 2
0x14002a349  jnz     short loc_14002A377
0x14002a34b  mov     rax, [rsp+78h+arg_20]
0x14002a353  mov     ebx, r13d
0x14002a356  test    rax, rax
0x14002a359  jz      short loc_14002A35E
0x14002a35b  mov     [rax], r13d
0x14002a35e  cmp     r12d, r15d
0x14002a361  jz      short loc_14002A367
0x14002a363  xor     ebx, ebx
0x14002a365  jmp     short loc_14002A377
0x14002a367  mov     rax, [rsp+78h+arg_28]
0x14002a36f  test    rax, rax
0x14002a372  jz      short loc_14002A377
0x14002a374  mov     [rax], r13d
0x14002a377  mov     rcx, rdi
0x14002a37a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x14002a381  nop     dword ptr [rax+rax+00h]
0x14002a386  jmp     short loc_14002A3B6
0x14002a388  mov     ecx, 80070057h; this
0x14002a38d  mov     [rsp+78h+cchCount2], ecx; unsigned int
0x14002a391  mov     r9d, 1153h; unsigned int
0x14002a397  lea     rax, aIsflag; "IsFlag"
0x14002a39e  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x14002a3a5  mov     [rsp+78h+lpString2], rax; unsigned __int16 *
0x14002a3aa  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14002a3b1  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002a3b6  mov     eax, ebx
0x14002a3b8  add     rsp, 38h
0x14002a3bc  pop     r15
0x14002a3be  pop     r14
0x14002a3c0  pop     r13
0x14002a3c2  pop     r12
0x14002a3c4  pop     rdi
0x14002a3c5  pop     rsi
0x14002a3c6  pop     rbp
0x14002a3c7  pop     rbx
0x14002a3c8  retn
```
