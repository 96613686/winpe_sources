# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x14000eec4`
- end: `0x14000efa8`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `228`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000e910`
- `0x14000eec4`

## callees

- `0x14000eec4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000ef8b`
- `msvcrt!memcpy_s` at `0x14000ef8b`

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
0x14000eec4  push    rbx
0x14000eec6  push    rbp
0x14000eec7  push    rsi
0x14000eec8  push    rdi
0x14000eec9  sub     rsp, 28h
0x14000eecd  xor     al, al
0x14000eecf  mov     byte ptr [r8], 0
0x14000eed3  mov     rbp, r9
0x14000eed6  mov     rdi, r8
0x14000eed9  mov     rsi, rdx
0x14000eedc  mov     rbx, rcx
0x14000eedf  test    rdx, rdx
0x14000eee2  jz      loc_14000EF9E
0x14000eee8  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x14000eeec  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x14000eef1  mov     rdx, [rsi+20h]
0x14000eef5  test    rdx, rdx
0x14000eef8  jz      loc_14000EF9E
0x14000eefe  cmp     dword ptr [rdx], 0
0x14000ef01  jnz     short loc_14000EF14
0x14000ef03  mov     eax, 1
0x14000ef08  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x14000ef10  inc     eax
0x14000ef12  mov     [rdx], eax
0x14000ef14  cmp     dword ptr [rbx+50h], 0
0x14000ef18  jnz     short loc_14000EF2B
0x14000ef1a  movups  xmm0, xmmword ptr [rdx]
0x14000ef1d  movups  xmmword ptr [rbx+50h], xmm0
0x14000ef21  movsd   xmm1, qword ptr [rdx+10h]
0x14000ef26  movsd   qword ptr [rbx+60h], xmm1
0x14000ef2b  movups  xmm0, xmmword ptr [rdx]
0x14000ef2e  lea     r10, [rdi+rbp]
0x14000ef32  movups  xmmword ptr [rbx+68h], xmm0
0x14000ef36  movsd   xmm1, qword ptr [rdx+10h]
0x14000ef3b  movsd   qword ptr [rbx+78h], xmm1
0x14000ef40  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000ef44  mov     rax, rbx
0x14000ef47  inc     rax
0x14000ef4a  cmp     byte ptr [rdi+rax], 0
0x14000ef4e  jnz     short loc_14000EF47
0x14000ef50  lea     rcx, [rax+rdi]
0x14000ef54  mov     rax, r10
0x14000ef57  sub     rax, rcx
0x14000ef5a  cmp     rax, 2
0x14000ef5e  jle     short loc_14000EF9C
0x14000ef60  mov     byte ptr [rcx], 5Ch ; '\'
0x14000ef63  lea     rdi, [rcx+1]
0x14000ef67  mov     r8, [rdx+8]; Source
0x14000ef6b  inc     rbx
0x14000ef6e  cmp     byte ptr [r8+rbx], 0
0x14000ef73  jnz     short loc_14000EF6B
0x14000ef75  sub     r10, rdi
0x14000ef78  inc     rbx
0x14000ef7b  cmp     rbx, r10
0x14000ef7e  mov     rdx, r10; DestinationSize
0x14000ef81  mov     rcx, rdi; Destination
0x14000ef84  cmovnb  rbx, r10
0x14000ef88  mov     r9, rbx; SourceSize
0x14000ef8b  call    cs:__imp_memcpy_s
0x14000ef92  nop     dword ptr [rax+rax+00h]
0x14000ef97  mov     byte ptr [rbx+rdi-1], 0
0x14000ef9c  mov     al, 1
0x14000ef9e  add     rsp, 28h
0x14000efa2  pop     rdi
0x14000efa3  pop     rsi
0x14000efa4  pop     rbp
0x14000efa5  pop     rbx
0x14000efa6  retn
```
