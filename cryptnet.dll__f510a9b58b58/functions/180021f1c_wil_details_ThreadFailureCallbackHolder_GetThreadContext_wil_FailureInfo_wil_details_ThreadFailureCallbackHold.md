# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180021f1c`
- end: `0x180022008`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `236`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180021874`
- `0x180021f1c`

## callees

- `0x180021f1c`

## import_xrefs

- `ntdll!memcpy_s` at `0x180021ff2`
- `ntdll!memcpy_s` at `0x180021ff2`

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
  __int64 v10; // rcx
  char *v11; // r10
  __int64 v12; // rax
  char *v13; // r8
  _BYTE *v14; // rdi
  _BYTE *v15; // r8
  rsize_t v16; // r10
  rsize_t v17; // rbx

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
      v10 = -1;
      v11 = &a3[a4];
      v12 = -1;
      *(_OWORD *)((char *)a1 + 104) = *(_OWORD *)v9;
      *((_QWORD *)a1 + 15) = *((_QWORD *)v9 + 2);
      do
        ++v12;
      while ( a3[v12] );
      v13 = &a3[(int)v12];
      if ( v11 - v13 > 2 )
      {
        *v13 = 92;
        v14 = v13 + 1;
        v15 = (_BYTE *)*((_QWORD *)v9 + 1);
        if ( v15 )
        {
          do
            ++v10;
          while ( v15[v10] );
        }
        else
        {
          LODWORD(v10) = 0;
        }
        v16 = v11 - v14;
        v17 = (int)v10 + 1LL;
        if ( v17 >= v16 )
          v17 = v16;
        memcpy_s(v14, v16, v15, v17);
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
0x180021f1c  push    rbx
0x180021f1e  push    rbp
0x180021f1f  push    rsi
0x180021f20  push    rdi
0x180021f21  sub     rsp, 28h
0x180021f25  xor     al, al
0x180021f27  mov     byte ptr [r8], 0
0x180021f2b  mov     rbp, r9
0x180021f2e  mov     rdi, r8
0x180021f31  mov     rsi, rdx
0x180021f34  mov     rbx, rcx
0x180021f37  test    rdx, rdx
0x180021f3a  jz      loc_180021FFF
0x180021f40  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180021f44  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180021f49  mov     rdx, [rsi+20h]
0x180021f4d  test    rdx, rdx
0x180021f50  jz      loc_180021FFF
0x180021f56  cmp     dword ptr [rdx], 0
0x180021f59  jnz     short loc_180021F6C
0x180021f5b  mov     eax, 1
0x180021f60  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180021f68  inc     eax
0x180021f6a  mov     [rdx], eax
0x180021f6c  cmp     dword ptr [rbx+50h], 0
0x180021f70  jnz     short loc_180021F83
0x180021f72  movups  xmm0, xmmword ptr [rdx]
0x180021f75  movups  xmmword ptr [rbx+50h], xmm0
0x180021f79  movsd   xmm1, qword ptr [rdx+10h]
0x180021f7e  movsd   qword ptr [rbx+60h], xmm1
0x180021f83  movups  xmm0, xmmword ptr [rdx]
0x180021f86  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180021f8a  lea     r10, [rdi+rbp]
0x180021f8e  mov     rax, rcx
0x180021f91  movups  xmmword ptr [rbx+68h], xmm0
0x180021f95  movsd   xmm1, qword ptr [rdx+10h]
0x180021f9a  movsd   qword ptr [rbx+78h], xmm1
0x180021f9f  inc     rax
0x180021fa2  cmp     byte ptr [rdi+rax], 0
0x180021fa6  jnz     short loc_180021F9F
0x180021fa8  movsxd  r8, eax
0x180021fab  mov     rax, r10
0x180021fae  add     r8, rdi
0x180021fb1  sub     rax, r8
0x180021fb4  cmp     rax, 2
0x180021fb8  jle     short loc_180021FFD
0x180021fba  mov     byte ptr [r8], 5Ch ; '\'
0x180021fbe  lea     rdi, [r8+1]
0x180021fc2  mov     r8, [rdx+8]; Source
0x180021fc6  test    r8, r8
0x180021fc9  jz      short loc_180021FD7
0x180021fcb  inc     rcx
0x180021fce  cmp     byte ptr [r8+rcx], 0
0x180021fd3  jnz     short loc_180021FCB
0x180021fd5  jmp     short loc_180021FD9
0x180021fd7  xor     ecx, ecx
0x180021fd9  sub     r10, rdi
0x180021fdc  movsxd  rbx, ecx
0x180021fdf  inc     rbx
0x180021fe2  mov     rdx, r10; DestinationSize
0x180021fe5  cmp     rbx, r10
0x180021fe8  mov     rcx, rdi; Destination
0x180021feb  cmovnb  rbx, r10
0x180021fef  mov     r9, rbx; SourceSize
0x180021ff2  call    cs:__imp_memcpy_s
0x180021ff8  mov     byte ptr [rbx+rdi-1], 0
0x180021ffd  mov     al, 1
0x180021fff  add     rsp, 28h
0x180022003  pop     rdi
0x180022004  pop     rsi
0x180022005  pop     rbp
0x180022006  pop     rbx
0x180022007  retn
```
