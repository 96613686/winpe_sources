# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180006c9c`
- end: `0x180006d78`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006310`
- `0x180006c9c`

## callees

- `0x180006c9c`
- `0x18000cdd0`

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
0x180006c9c  push    rbx
0x180006c9e  push    rbp
0x180006c9f  push    rsi
0x180006ca0  push    rdi
0x180006ca1  sub     rsp, 28h
0x180006ca5  xor     al, al
0x180006ca7  mov     byte ptr [r8], 0
0x180006cab  mov     rbp, r9
0x180006cae  mov     rdi, r8
0x180006cb1  mov     rsi, rdx
0x180006cb4  mov     rbx, rcx
0x180006cb7  test    rdx, rdx
0x180006cba  jz      loc_180006D6F
0x180006cc0  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180006cc4  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180006cc9  mov     rdx, [rsi+20h]
0x180006ccd  test    rdx, rdx
0x180006cd0  jz      loc_180006D6F
0x180006cd6  cmp     dword ptr [rdx], 0
0x180006cd9  jnz     short loc_180006CEC
0x180006cdb  mov     eax, 1
0x180006ce0  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180006ce8  inc     eax
0x180006cea  mov     [rdx], eax
0x180006cec  cmp     dword ptr [rbx+50h], 0
0x180006cf0  jnz     short loc_180006D03
0x180006cf2  movups  xmm0, xmmword ptr [rdx]
0x180006cf5  movups  xmmword ptr [rbx+50h], xmm0
0x180006cf9  movsd   xmm1, qword ptr [rdx+10h]
0x180006cfe  movsd   qword ptr [rbx+60h], xmm1
0x180006d03  movups  xmm0, xmmword ptr [rdx]
0x180006d06  lea     r10, [rdi+rbp]
0x180006d0a  movups  xmmword ptr [rbx+68h], xmm0
0x180006d0e  movsd   xmm1, qword ptr [rdx+10h]
0x180006d13  movsd   qword ptr [rbx+78h], xmm1
0x180006d18  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180006d1c  mov     rax, rbx
0x180006d1f  inc     rax
0x180006d22  cmp     byte ptr [rdi+rax], 0
0x180006d26  jnz     short loc_180006D1F
0x180006d28  lea     rcx, [rax+rdi]
0x180006d2c  mov     rax, r10
0x180006d2f  sub     rax, rcx
0x180006d32  cmp     rax, 2
0x180006d36  jle     short loc_180006D6D
0x180006d38  mov     byte ptr [rcx], 5Ch ; '\'
0x180006d3b  lea     rdi, [rcx+1]
0x180006d3f  mov     r8, [rdx+8]; Source
0x180006d43  inc     rbx
0x180006d46  cmp     byte ptr [r8+rbx], 0
0x180006d4b  jnz     short loc_180006D43
0x180006d4d  sub     r10, rdi
0x180006d50  inc     rbx
0x180006d53  cmp     rbx, r10
0x180006d56  mov     rdx, r10; DestinationSize
0x180006d59  mov     rcx, rdi; Destination
0x180006d5c  cmovnb  rbx, r10
0x180006d60  mov     r9, rbx; SourceSize
0x180006d63  call    memcpy_s
0x180006d68  mov     byte ptr [rbx+rdi-1], 0
0x180006d6d  mov     al, 1
0x180006d6f  add     rsp, 28h
0x180006d73  pop     rdi
0x180006d74  pop     rsi
0x180006d75  pop     rbp
0x180006d76  pop     rbx
0x180006d77  retn
```
