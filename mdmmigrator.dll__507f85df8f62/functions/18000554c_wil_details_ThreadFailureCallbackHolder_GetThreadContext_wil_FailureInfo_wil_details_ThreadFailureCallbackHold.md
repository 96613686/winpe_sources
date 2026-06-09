# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18000554c`
- end: `0x180005628`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004e50`
- `0x18000554c`

## callees

- `0x18000554c`
- `0x1800075ac`

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
  char *v10; // r10
  __int64 v11; // rbx
  __int64 v12; // rax
  char *v13; // rcx
  char *v14; // rdi
  _BYTE *v15; // r8
  rsize_t v16; // r10
  rsize_t v17; // rbx
  void *v18; // rcx

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
      if ( (__int64)(a4 - v12) > 2 )
      {
        *v13 = 92;
        v14 = v13 + 1;
        v15 = (_BYTE *)*((_QWORD *)v9 + 1);
        do
          ++v11;
        while ( v15[v11] );
        v16 = v10 - v14;
        v17 = v11 + 1;
        v18 = v13 + 1;
        if ( v17 >= v16 )
          v17 = v16;
        memcpy_s(v18, v16, v15, v17);
        v14[v17 - 1] = 0;
      }
      return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000554c  push    rbx
0x18000554e  push    rbp
0x18000554f  push    rsi
0x180005550  push    rdi
0x180005551  sub     rsp, 28h
0x180005555  xor     al, al
0x180005557  mov     byte ptr [r8], 0
0x18000555b  mov     rbp, r9
0x18000555e  mov     rdi, r8
0x180005561  mov     rsi, rdx
0x180005564  mov     rbx, rcx
0x180005567  test    rdx, rdx
0x18000556a  jz      loc_18000561F
0x180005570  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180005574  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005579  mov     rdx, [rsi+20h]
0x18000557d  test    rdx, rdx
0x180005580  jz      loc_18000561F
0x180005586  cmp     dword ptr [rdx], 0
0x180005589  jnz     short loc_18000559C
0x18000558b  mov     eax, 1
0x180005590  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180005598  inc     eax
0x18000559a  mov     [rdx], eax
0x18000559c  cmp     dword ptr [rbx+50h], 0
0x1800055a0  jnz     short loc_1800055B3
0x1800055a2  movups  xmm0, xmmword ptr [rdx]
0x1800055a5  movups  xmmword ptr [rbx+50h], xmm0
0x1800055a9  movsd   xmm1, qword ptr [rdx+10h]
0x1800055ae  movsd   qword ptr [rbx+60h], xmm1
0x1800055b3  movups  xmm0, xmmword ptr [rdx]
0x1800055b6  lea     r10, [rdi+rbp]
0x1800055ba  movups  xmmword ptr [rbx+68h], xmm0
0x1800055be  movsd   xmm1, qword ptr [rdx+10h]
0x1800055c3  movsd   qword ptr [rbx+78h], xmm1
0x1800055c8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800055cc  mov     rax, rbx
0x1800055cf  inc     rax
0x1800055d2  cmp     byte ptr [rdi+rax], 0
0x1800055d6  jnz     short loc_1800055CF
0x1800055d8  lea     rcx, [rax+rdi]
0x1800055dc  mov     rax, r10
0x1800055df  sub     rax, rcx
0x1800055e2  cmp     rax, 2
0x1800055e6  jle     short loc_18000561D
0x1800055e8  mov     byte ptr [rcx], 5Ch ; '\'
0x1800055eb  lea     rdi, [rcx+1]
0x1800055ef  mov     r8, [rdx+8]; Source
0x1800055f3  inc     rbx
0x1800055f6  cmp     byte ptr [r8+rbx], 0
0x1800055fb  jnz     short loc_1800055F3
0x1800055fd  sub     r10, rdi
0x180005600  inc     rbx
0x180005603  cmp     rbx, r10
0x180005606  mov     rdx, r10; DestinationSize
0x180005609  mov     rcx, rdi; Destination
0x18000560c  cmovnb  rbx, r10
0x180005610  mov     r9, rbx; SourceSize
0x180005613  call    memcpy_s
0x180005618  mov     byte ptr [rbx+rdi-1], 0
0x18000561d  mov     al, 1
0x18000561f  add     rsp, 28h
0x180005623  pop     rdi
0x180005624  pop     rsi
0x180005625  pop     rbp
0x180005626  pop     rbx
0x180005627  retn
```
