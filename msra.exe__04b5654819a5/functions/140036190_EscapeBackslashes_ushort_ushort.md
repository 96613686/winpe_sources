# EscapeBackslashes(ushort *,ushort * *)

- ea: `0x140036190`
- end: `0x14003639c`
- name: `?EscapeBackslashes@@YAJPEAGPEAPEAG@Z`
- size: `524`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400231d8`

## callees

- `0x140002463`
- `0x140034ce4`
- `0x140036190`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14003634a`
- `KERNEL32!HeapFree` at `0x14003634a`
- `KERNEL32!GetProcessHeap` at `0x140036260`
- `KERNEL32!GetProcessHeap` at `0x140036336`
- `KERNEL32!GetProcessHeap` at `0x140036260`
- `KERNEL32!GetProcessHeap` at `0x140036336`
- `KERNEL32!HeapAlloc` at `0x14003627e`
- `KERNEL32!HeapAlloc` at `0x14003627e`
- `OLEAUT32!__imp_SysAllocString` at `0x1400362f0`
- `OLEAUT32!__imp_SysAllocString` at `0x1400362f0`

## string_xrefs

- `0x1400361c9`: `base\diagnosis\ra\racommon\src\stringutils.cpp`
- `0x14003631e`: `base\diagnosis\ra\racommon\src\stringutils.cpp`
- `0x140036370`: `base\diagnosis\ra\racommon\src\stringutils.cpp`

## pseudocode

```c
__int64 __fastcall EscapeBackslashes(CEventLogger *a1, unsigned __int16 **a2)
{
  CEventLogger *v3; // rdi
  CEventLogger *v5; // rax
  __int64 v6; // rcx
  unsigned int v7; // ebx
  __int64 v8; // rbp
  OLECHAR v9; // cx
  int v10; // esi
  CEventLogger *v11; // rdx
  bool v12; // zf
  int v13; // eax
  HANDLE ProcessHeap; // rax
  SIZE_T v15; // r14
  OLECHAR *v16; // rax
  CEventLogger *v17; // rcx
  OLECHAR *v18; // rsi
  OLECHAR v19; // ax
  unsigned int v20; // ecx
  __int64 v21; // rdx
  unsigned __int16 *v22; // rax
  CEventLogger *v23; // rcx
  HANDLE v24; // rax

  v3 = a1;
  if ( !a2 )
  {
    CEventLogger::LogError(
      a1,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\racommon\\src\\stringutils.cpp",
      0x178u,
      L"EscapeBackslashes",
      0x80070057);
    return 2147942487LL;
  }
  if ( a1 )
  {
    v5 = a1;
    v6 = 0x7FFFFFFF;
    do
    {
      if ( !*(_WORD *)v5 )
        break;
      v5 = (CEventLogger *)((char *)v5 + 2);
      --v6;
    }
    while ( v6 );
    v7 = v6 == 0 ? 0x80070057 : 0;
    v8 = (0x7FFFFFFF - v6) & -(__int64)(v6 != 0);
    if ( v6 )
    {
      v9 = *(_WORD *)v3;
      v10 = 0;
      if ( *(_WORD *)v3 )
      {
        v11 = v3;
        do
        {
          v12 = v9 == 92;
          v13 = v10 + 1;
          v11 = (CEventLogger *)((char *)v11 + 2);
          v9 = *(_WORD *)v11;
          if ( !v12 )
            v13 = v10;
          v10 = v13;
        }
        while ( v9 );
      }
      ProcessHeap = GetProcessHeap();
      v15 = 2 * (v8 + (unsigned int)(v10 + 1));
      v16 = (OLECHAR *)HeapAlloc(ProcessHeap, 0, v15);
      v18 = v16;
      if ( v16 )
      {
        memset_0(v16, 0, v15);
        v19 = *(_WORD *)v3;
        if ( *(_WORD *)v3 )
        {
          v20 = 0;
          do
          {
            v21 = v20;
            if ( v19 == 92 )
            {
              ++v20;
              v18[v21] = 92;
              v18[v20] = 92;
            }
            else
            {
              v18[v20] = *(_WORD *)v3;
            }
            v3 = (CEventLogger *)((char *)v3 + 2);
            ++v20;
            v19 = *(_WORD *)v3;
          }
          while ( *(_WORD *)v3 );
        }
        v22 = SysAllocString(v18);
        *a2 = v22;
        if ( !v22 )
        {
          v7 = -2147024882;
          CEventLogger::LogError(
            v23,
            &Recoverable_Error,
            L"base\\diagnosis\\ra\\racommon\\src\\stringutils.cpp",
            0x1A7u,
            L"EscapeBackslashes",
            0x8007000E);
        }
        v24 = GetProcessHeap();
        HeapFree(v24, 0, v18);
      }
      else
      {
        v7 = -2147024882;
        CEventLogger::LogError(
          v17,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\racommon\\src\\stringutils.cpp",
          0x18Au,
          L"EscapeBackslashes",
          0x8007000E);
      }
      return v7;
    }
  }
  else
  {
    v7 = -2147024809;
  }
  CEventLogger::LogError(
    0,
    &Recoverable_Error,
    L"base\\diagnosis\\ra\\racommon\\src\\stringutils.cpp",
    0x17Du,
    L"EscapeBackslashes",
    0x80070057);
  return v7;
}

```

## disassembly

```asm
0x140036190  push    rbx
0x140036192  push    rbp
0x140036193  push    rsi
0x140036194  push    rdi
0x140036195  push    r12
0x140036197  push    r13
0x140036199  push    r14
0x14003619b  push    r15
0x14003619d  sub     rsp, 38h
0x1400361a1  xor     r12d, r12d
0x1400361a4  mov     r15, rdx
0x1400361a7  mov     rdi, rcx
0x1400361aa  test    rdx, rdx
0x1400361ad  jnz     short loc_1400361E6
0x1400361af  lea     rax, aEscapebackslas; "EscapeBackslashes"
0x1400361b6  mov     [rsp+78h+var_50], 80070057h; unsigned int
0x1400361be  mov     r9d, 178h; unsigned int
0x1400361c4  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x1400361c9  lea     r8, aBaseDiagnosisR_33; "base\\diagnosis\\ra\\racommon\\src\\str"...
0x1400361d0  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x1400361d7  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400361dc  mov     eax, 80070057h
0x1400361e1  jmp     loc_14003638A
0x1400361e6  test    rdi, rdi
0x1400361e9  jz      loc_140036358
0x1400361ef  mov     edx, 7FFFFFFFh
0x1400361f4  mov     rax, rdi
0x1400361f7  mov     ecx, edx
0x1400361f9  cmp     [rax], r12w
0x1400361fd  jz      short loc_140036209
0x1400361ff  add     rax, 2
0x140036203  sub     rcx, 1
0x140036207  jnz     short loc_1400361F9
0x140036209  mov     rax, rcx
0x14003620c  neg     rax
0x14003620f  mov     rax, rcx
0x140036212  sbb     ebx, ebx
0x140036214  sub     rdx, rcx
0x140036217  not     ebx
0x140036219  and     ebx, 80070057h
0x14003621f  neg     rax
0x140036222  sbb     rbp, rbp
0x140036225  and     rbp, rdx
0x140036228  test    rcx, rcx
0x14003622b  jnz     short loc_140036234
0x14003622d  mov     eax, ebx
0x14003622f  jmp     loc_14003635F
0x140036234  movzx   ecx, word ptr [rdi]
0x140036237  mov     esi, r12d
0x14003623a  mov     r13d, 5Ch ; '\'
0x140036240  test    cx, cx
0x140036243  jz      short loc_140036260
0x140036245  mov     rdx, rdi
0x140036248  cmp     cx, r13w
0x14003624c  lea     eax, [rsi+1]
0x14003624f  lea     rdx, [rdx+2]
0x140036253  movzx   ecx, word ptr [rdx]
0x140036256  cmovnz  eax, esi
0x140036259  mov     esi, eax
0x14003625b  test    cx, cx
0x14003625e  jnz     short loc_140036248
0x140036260  call    cs:__imp_GetProcessHeap
0x140036267  nop     dword ptr [rax+rax+00h]
0x14003626c  lea     r14d, [rsi+1]
0x140036270  xor     edx, edx; dwFlags
0x140036272  add     r14, rbp
0x140036275  mov     rcx, rax; hHeap
0x140036278  add     r14, r14
0x14003627b  mov     r8, r14; dwBytes
0x14003627e  call    cs:__imp_HeapAlloc
0x140036285  nop     dword ptr [rax+rax+00h]
0x14003628a  mov     rsi, rax
0x14003628d  test    rax, rax
0x140036290  jnz     short loc_1400362AA
0x140036292  mov     ebx, 8007000Eh
0x140036297  mov     [rsp+78h+var_50], 8007000Eh
0x14003629f  mov     r9d, 18Ah
0x1400362a5  jmp     loc_140036369
0x1400362aa  mov     r8, r14; Size
0x1400362ad  xor     edx, edx; Val
0x1400362af  mov     rcx, rsi; void *
0x1400362b2  call    memset_0
0x1400362b7  movzx   eax, word ptr [rdi]
0x1400362ba  test    ax, ax
0x1400362bd  jz      short loc_1400362ED
0x1400362bf  mov     ecx, r12d
0x1400362c2  mov     edx, ecx
0x1400362c4  cmp     ax, r13w
0x1400362c8  jnz     short loc_1400362D8
0x1400362ca  inc     ecx
0x1400362cc  mov     [rsi+rdx*2], r13w
0x1400362d1  mov     [rsi+rcx*2], r13w
0x1400362d6  jmp     short loc_1400362DF
0x1400362d8  movzx   eax, word ptr [rdi]
0x1400362db  mov     [rsi+rdx*2], ax
0x1400362df  add     rdi, 2
0x1400362e3  inc     ecx
0x1400362e5  movzx   eax, word ptr [rdi]
0x1400362e8  test    ax, ax
0x1400362eb  jnz     short loc_1400362C2
0x1400362ed  mov     rcx, rsi; psz
0x1400362f0  call    cs:__imp_SysAllocString
0x1400362f7  nop     dword ptr [rax+rax+00h]
0x1400362fc  mov     [r15], rax
0x1400362ff  test    rax, rax
0x140036302  jnz     short loc_140036336
0x140036304  lea     rax, aEscapebackslas; "EscapeBackslashes"
0x14003630b  mov     [rsp+78h+var_50], 8007000Eh; unsigned int
0x140036313  mov     r9d, 1A7h; unsigned int
0x140036319  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x14003631e  lea     r8, aBaseDiagnosisR_33; "base\\diagnosis\\ra\\racommon\\src\\str"...
0x140036325  mov     ebx, 8007000Eh
0x14003632a  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140036331  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140036336  call    cs:__imp_GetProcessHeap
0x14003633d  nop     dword ptr [rax+rax+00h]
0x140036342  mov     r8, rsi; lpMem
0x140036345  xor     edx, edx; dwFlags
0x140036347  mov     rcx, rax; hHeap
0x14003634a  call    cs:__imp_HeapFree
0x140036351  nop     dword ptr [rax+rax+00h]
0x140036356  jmp     short loc_140036388
0x140036358  mov     eax, 80070057h
0x14003635d  mov     ebx, eax
0x14003635f  mov     [rsp+78h+var_50], eax; unsigned int
0x140036363  mov     r9d, 17Dh; unsigned int
0x140036369  lea     rax, aEscapebackslas; "EscapeBackslashes"
0x140036370  lea     r8, aBaseDiagnosisR_33; "base\\diagnosis\\ra\\racommon\\src\\str"...
0x140036377  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x14003637c  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140036383  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140036388  mov     eax, ebx
0x14003638a  add     rsp, 38h
0x14003638e  pop     r15
0x140036390  pop     r14
0x140036392  pop     r13
0x140036394  pop     r12
0x140036396  pop     rdi
0x140036397  pop     rsi
0x140036398  pop     rbp
0x140036399  pop     rbx
0x14003639a  retn
```
