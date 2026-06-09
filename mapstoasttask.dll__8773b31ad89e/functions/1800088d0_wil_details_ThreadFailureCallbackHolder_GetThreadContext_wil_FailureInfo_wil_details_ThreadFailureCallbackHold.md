# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x1800088d0`
- end: `0x1800089f5`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `293`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180008600`
- `0x1800088d0`

## callees

- `0x180001f9a`
- `0x180001fe2`
- `0x1800088d0`
- `0x180009540`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008995`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800089d4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008995`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800089d4`

## pseudocode

```c
bool __fastcall wil::details::ThreadFailureCallbackHolder::GetThreadContext(
        struct wil::FailureInfo *a1,
        struct wil::details::ThreadFailureCallbackHolder **a2,
        char *a3,
        unsigned __int64 a4)
{
  bool result; // al
  struct wil::details::ThreadFailureCallbackHolder *v9; // rdx
  char *v10; // rdi
  __int64 v11; // rbx
  __int64 v12; // rax
  char *v13; // rsi
  _BYTE *v14; // rsi
  __int64 v15; // rbp
  size_t v16; // rbx
  size_t v17; // rdi

  result = 0;
  *a3 = 0;
  if ( a2 )
  {
    result = wil::details::ThreadFailureCallbackHolder::GetThreadContext(a1, a2[2], a3, a4);
    v9 = a2[4];
    if ( v9 )
    {
      if ( !*(_DWORD *)v9 )
        *(_DWORD *)v9 = _InterlockedIncrement(&wil::details::ThreadFailureCallbackHolder::s_telemetryId);
      if ( !*((_DWORD *)a1 + 20) )
      {
        *((_OWORD *)a1 + 5) = *(_OWORD *)v9;
        *((_QWORD *)a1 + 12) = *((_QWORD *)v9 + 2);
      }
      v10 = &a3[a4];
      *(_OWORD *)((char *)a1 + 104) = *(_OWORD *)v9;
      *((_QWORD *)a1 + 15) = *((_QWORD *)v9 + 2);
      v11 = -1;
      v12 = -1;
      do
        ++v12;
      while ( a3[v12] );
      v13 = &a3[v12];
      if ( v10 - v13 <= 2 )
        return 1;
      *v13 = 92;
      v14 = v13 + 1;
      v15 = *((_QWORD *)v9 + 1);
      do
        ++v11;
      while ( *(_BYTE *)(v11 + v15) );
      v16 = v11 + 1;
      v17 = v10 - v14;
      if ( v16 >= v17 )
        v16 = v17;
      if ( v16 )
      {
        if ( !v14 )
        {
LABEL_16:
          *(_DWORD *)_o__errno() = 22;
LABEL_23:
          invalid_parameter_noinfo();
          goto LABEL_24;
        }
        if ( v15 && v17 >= v16 )
        {
          memcpy_0(v14, *((const void **)v9 + 1), v16);
        }
        else
        {
          memset_0(v14, 0, v17);
          if ( !v15 )
            goto LABEL_16;
          if ( v17 < v16 )
          {
            *(_DWORD *)_o__errno() = 34;
            goto LABEL_23;
          }
        }
      }
LABEL_24:
      v14[v16 - 1] = 0;
      return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800088d0  push    rbx
0x1800088d2  push    rbp
0x1800088d3  push    rsi
0x1800088d4  push    rdi
0x1800088d5  sub     rsp, 28h
0x1800088d9  xor     al, al
0x1800088db  mov     byte ptr [r8], 0
0x1800088df  mov     rbp, r9
0x1800088e2  mov     rsi, r8
0x1800088e5  mov     rdi, rdx
0x1800088e8  mov     rbx, rcx
0x1800088eb  test    rdx, rdx
0x1800088ee  jz      loc_1800089EC
0x1800088f4  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x1800088f8  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800088fd  mov     rdx, [rdi+20h]
0x180008901  test    rdx, rdx
0x180008904  jz      loc_1800089EC
0x18000890a  cmp     dword ptr [rdx], 0
0x18000890d  jnz     short loc_180008920
0x18000890f  mov     eax, 1
0x180008914  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18000891c  inc     eax
0x18000891e  mov     [rdx], eax
0x180008920  cmp     dword ptr [rbx+50h], 0
0x180008924  jnz     short loc_180008937
0x180008926  movups  xmm0, xmmword ptr [rdx]
0x180008929  movups  xmmword ptr [rbx+50h], xmm0
0x18000892d  movsd   xmm1, qword ptr [rdx+10h]
0x180008932  movsd   qword ptr [rbx+60h], xmm1
0x180008937  movups  xmm0, xmmword ptr [rdx]
0x18000893a  lea     rdi, [rsi+rbp]
0x18000893e  movups  xmmword ptr [rbx+68h], xmm0
0x180008942  movsd   xmm1, qword ptr [rdx+10h]
0x180008947  movsd   qword ptr [rbx+78h], xmm1
0x18000894c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180008950  mov     rax, rbx
0x180008953  inc     rax
0x180008956  cmp     byte ptr [rsi+rax], 0
0x18000895a  jnz     short loc_180008953
0x18000895c  add     rsi, rax
0x18000895f  mov     rax, rdi
0x180008962  sub     rax, rsi
0x180008965  cmp     rax, 2
0x180008969  jle     short loc_1800089EA
0x18000896b  mov     byte ptr [rsi], 5Ch ; '\'
0x18000896e  inc     rsi
0x180008971  mov     rbp, [rdx+8]
0x180008975  inc     rbx
0x180008978  cmp     byte ptr [rbx+rbp], 0
0x18000897c  jnz     short loc_180008975
0x18000897e  inc     rbx
0x180008981  sub     rdi, rsi
0x180008984  cmp     rbx, rdi
0x180008987  cmovnb  rbx, rdi
0x18000898b  test    rbx, rbx
0x18000898e  jz      short loc_1800089E5
0x180008990  test    rsi, rsi
0x180008993  jnz     short loc_1800089A3
0x180008995  call    cs:__imp__o__errno
0x18000899b  mov     dword ptr [rax], 16h
0x1800089a1  jmp     short loc_1800089E0
0x1800089a3  test    rbp, rbp
0x1800089a6  jz      short loc_1800089BD
0x1800089a8  cmp     rdi, rbx
0x1800089ab  jb      short loc_1800089BD
0x1800089ad  mov     r8, rbx; Size
0x1800089b0  mov     rdx, rbp; Src
0x1800089b3  mov     rcx, rsi; void *
0x1800089b6  call    memcpy_0
0x1800089bb  jmp     short loc_1800089E5
0x1800089bd  mov     r8, rdi; Size
0x1800089c0  xor     edx, edx; Val
0x1800089c2  mov     rcx, rsi; void *
0x1800089c5  call    memset_0
0x1800089ca  test    rbp, rbp
0x1800089cd  jz      short loc_180008995
0x1800089cf  cmp     rdi, rbx
0x1800089d2  jnb     short loc_1800089E5
0x1800089d4  call    cs:__imp__o__errno
0x1800089da  mov     dword ptr [rax], 22h ; '"'
0x1800089e0  call    _invalid_parameter_noinfo
0x1800089e5  mov     byte ptr [rbx+rsi-1], 0
0x1800089ea  mov     al, 1
0x1800089ec  add     rsp, 28h
0x1800089f0  pop     rdi
0x1800089f1  pop     rsi
0x1800089f2  pop     rbp
0x1800089f3  pop     rbx
0x1800089f4  retn
```
