# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180004b9c`
- end: `0x180004c78`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800044a0`
- `0x180004b9c`

## callees

- `0x180004b9c`
- `0x1800069d8`

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
0x180004b9c  push    rbx
0x180004b9e  push    rbp
0x180004b9f  push    rsi
0x180004ba0  push    rdi
0x180004ba1  sub     rsp, 28h
0x180004ba5  xor     al, al
0x180004ba7  mov     byte ptr [r8], 0
0x180004bab  mov     rbp, r9
0x180004bae  mov     rdi, r8
0x180004bb1  mov     rsi, rdx
0x180004bb4  mov     rbx, rcx
0x180004bb7  test    rdx, rdx
0x180004bba  jz      loc_180004C6F
0x180004bc0  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180004bc4  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004bc9  mov     rdx, [rsi+20h]
0x180004bcd  test    rdx, rdx
0x180004bd0  jz      loc_180004C6F
0x180004bd6  cmp     dword ptr [rdx], 0
0x180004bd9  jnz     short loc_180004BEC
0x180004bdb  mov     eax, 1
0x180004be0  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180004be8  inc     eax
0x180004bea  mov     [rdx], eax
0x180004bec  cmp     dword ptr [rbx+50h], 0
0x180004bf0  jnz     short loc_180004C03
0x180004bf2  movups  xmm0, xmmword ptr [rdx]
0x180004bf5  movups  xmmword ptr [rbx+50h], xmm0
0x180004bf9  movsd   xmm1, qword ptr [rdx+10h]
0x180004bfe  movsd   qword ptr [rbx+60h], xmm1
0x180004c03  movups  xmm0, xmmword ptr [rdx]
0x180004c06  lea     r10, [rdi+rbp]
0x180004c0a  movups  xmmword ptr [rbx+68h], xmm0
0x180004c0e  movsd   xmm1, qword ptr [rdx+10h]
0x180004c13  movsd   qword ptr [rbx+78h], xmm1
0x180004c18  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180004c1c  mov     rax, rbx
0x180004c1f  inc     rax
0x180004c22  cmp     byte ptr [rdi+rax], 0
0x180004c26  jnz     short loc_180004C1F
0x180004c28  lea     rcx, [rax+rdi]
0x180004c2c  mov     rax, r10
0x180004c2f  sub     rax, rcx
0x180004c32  cmp     rax, 2
0x180004c36  jle     short loc_180004C6D
0x180004c38  mov     byte ptr [rcx], 5Ch ; '\'
0x180004c3b  lea     rdi, [rcx+1]
0x180004c3f  mov     r8, [rdx+8]; Source
0x180004c43  inc     rbx
0x180004c46  cmp     byte ptr [r8+rbx], 0
0x180004c4b  jnz     short loc_180004C43
0x180004c4d  sub     r10, rdi
0x180004c50  inc     rbx
0x180004c53  cmp     rbx, r10
0x180004c56  mov     rdx, r10; DestinationSize
0x180004c59  mov     rcx, rdi; Destination
0x180004c5c  cmovnb  rbx, r10
0x180004c60  mov     r9, rbx; SourceSize
0x180004c63  call    memcpy_s
0x180004c68  mov     byte ptr [rbx+rdi-1], 0
0x180004c6d  mov     al, 1
0x180004c6f  add     rsp, 28h
0x180004c73  pop     rdi
0x180004c74  pop     rsi
0x180004c75  pop     rbp
0x180004c76  pop     rbx
0x180004c77  retn
```
