# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180004ba4`
- end: `0x180004c77`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `211`
- prototype: `static bool(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004504`
- `0x180004ba4`

## callees

- `0x180004ba4`
- `0x180007dcc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180004c61`
- `msvcrt!memcpy_s` at `0x180004c61`

## pseudocode

```c
bool __fastcall wil::details::ThreadFailureCallbackHolder::GetThreadContext(
        struct wil::FailureInfo *a1,
        struct wil::details::ThreadFailureCallbackHolder **a2,
        char *a3,
        unsigned __int64 a4)
{
  bool result; // al
  struct wil::details::ThreadFailureCallbackHolder *v9; // rsi
  char *v10; // rbp
  char *v11; // rdi
  _BYTE *v12; // rdi
  rsize_t v13; // rbp
  rsize_t v14; // rbx

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
      v11 = &a3[mqstrlen(a3)];
      if ( v10 - v11 > 2 )
      {
        *v11 = 92;
        v12 = v11 + 1;
        v13 = v10 - v12;
        v14 = mqstrlen(*((const char **)v9 + 1)) + 1;
        if ( v14 >= v13 )
          v14 = v13;
        memcpy_s(v12, v13, *((const void *const *)v9 + 1), v14);
        v12[v14 - 1] = 0;
      }
      return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004ba4  push    rbx
0x180004ba6  push    rbp
0x180004ba7  push    rsi
0x180004ba8  push    rdi
0x180004ba9  sub     rsp, 28h
0x180004bad  xor     al, al
0x180004baf  mov     byte ptr [r8], 0
0x180004bb3  mov     rbp, r9
0x180004bb6  mov     rdi, r8
0x180004bb9  mov     rsi, rdx
0x180004bbc  mov     rbx, rcx
0x180004bbf  test    rdx, rdx
0x180004bc2  jz      loc_180004C6E
0x180004bc8  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180004bcc  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004bd1  mov     rsi, [rsi+20h]
0x180004bd5  test    rsi, rsi
0x180004bd8  jz      loc_180004C6E
0x180004bde  cmp     dword ptr [rsi], 0
0x180004be1  jnz     short loc_180004BF4
0x180004be3  mov     eax, 1
0x180004be8  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x180004bf0  inc     eax
0x180004bf2  mov     [rsi], eax
0x180004bf4  cmp     dword ptr [rbx+50h], 0
0x180004bf8  jnz     short loc_180004C0B
0x180004bfa  movups  xmm0, xmmword ptr [rsi]
0x180004bfd  movups  xmmword ptr [rbx+50h], xmm0
0x180004c01  movsd   xmm1, qword ptr [rsi+10h]
0x180004c06  movsd   qword ptr [rbx+60h], xmm1
0x180004c0b  movups  xmm0, xmmword ptr [rsi]
0x180004c0e  mov     rcx, rdi; char *
0x180004c11  add     rbp, rdi
0x180004c14  movups  xmmword ptr [rbx+68h], xmm0
0x180004c18  movsd   xmm1, qword ptr [rsi+10h]
0x180004c1d  movsd   qword ptr [rbx+78h], xmm1
0x180004c22  call    ?mqstrlen@@YAIPEBD@Z; mqstrlen(char const *)
0x180004c27  mov     eax, eax
0x180004c29  add     rdi, rax
0x180004c2c  mov     rax, rbp
0x180004c2f  sub     rax, rdi
0x180004c32  cmp     rax, 2
0x180004c36  jle     short loc_180004C6C
0x180004c38  mov     byte ptr [rdi], 5Ch ; '\'
0x180004c3b  inc     rdi
0x180004c3e  mov     rcx, [rsi+8]; char *
0x180004c42  sub     rbp, rdi
0x180004c45  call    ?mqstrlen@@YAIPEBD@Z; mqstrlen(char const *)
0x180004c4a  mov     r8, [rsi+8]; Source
0x180004c4e  mov     rdx, rbp; DestinationSize
0x180004c51  mov     rcx, rdi; Destination
0x180004c54  lea     ebx, [rax+1]
0x180004c57  cmp     rbx, rbp
0x180004c5a  cmovnb  rbx, rbp
0x180004c5e  mov     r9, rbx; SourceSize
0x180004c61  call    cs:__imp_memcpy_s
0x180004c67  mov     byte ptr [rbx+rdi-1], 0
0x180004c6c  mov     al, 1
0x180004c6e  add     rsp, 28h
0x180004c72  pop     rdi
0x180004c73  pop     rsi
0x180004c74  pop     rbp
0x180004c75  pop     rbx
0x180004c76  retn
```
