# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x1800061a8`
- end: `0x180006285`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `221`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005a20`
- `0x1800061a8`

## callees

- `0x1800061a8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000626f`
- `msvcrt!memcpy_s` at `0x18000626f`

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
0x1800061a8  push    rbx
0x1800061aa  push    rbp
0x1800061ab  push    rsi
0x1800061ac  push    rdi
0x1800061ad  sub     rsp, 28h
0x1800061b1  xor     al, al
0x1800061b3  mov     byte ptr [r8], 0
0x1800061b7  mov     rbp, r9
0x1800061ba  mov     rdi, r8
0x1800061bd  mov     rsi, rdx
0x1800061c0  mov     rbx, rcx
0x1800061c3  test    rdx, rdx
0x1800061c6  jz      loc_18000627C
0x1800061cc  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x1800061d0  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800061d5  mov     rdx, [rsi+20h]
0x1800061d9  test    rdx, rdx
0x1800061dc  jz      loc_18000627C
0x1800061e2  cmp     dword ptr [rdx], 0
0x1800061e5  jnz     short loc_1800061F8
0x1800061e7  mov     eax, 1
0x1800061ec  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x1800061f4  inc     eax
0x1800061f6  mov     [rdx], eax
0x1800061f8  cmp     dword ptr [rbx+50h], 0
0x1800061fc  jnz     short loc_18000620F
0x1800061fe  movups  xmm0, xmmword ptr [rdx]
0x180006201  movups  xmmword ptr [rbx+50h], xmm0
0x180006205  movsd   xmm1, qword ptr [rdx+10h]
0x18000620a  movsd   qword ptr [rbx+60h], xmm1
0x18000620f  movups  xmm0, xmmword ptr [rdx]
0x180006212  lea     r10, [rdi+rbp]
0x180006216  movups  xmmword ptr [rbx+68h], xmm0
0x18000621a  movsd   xmm1, qword ptr [rdx+10h]
0x18000621f  movsd   qword ptr [rbx+78h], xmm1
0x180006224  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180006228  mov     rax, rbx
0x18000622b  inc     rax
0x18000622e  cmp     byte ptr [rdi+rax], 0
0x180006232  jnz     short loc_18000622B
0x180006234  lea     rcx, [rax+rdi]
0x180006238  mov     rax, r10
0x18000623b  sub     rax, rcx
0x18000623e  cmp     rax, 2
0x180006242  jle     short loc_18000627A
0x180006244  mov     byte ptr [rcx], 5Ch ; '\'
0x180006247  lea     rdi, [rcx+1]
0x18000624b  mov     r8, [rdx+8]; Source
0x18000624f  inc     rbx
0x180006252  cmp     byte ptr [r8+rbx], 0
0x180006257  jnz     short loc_18000624F
0x180006259  sub     r10, rdi
0x18000625c  inc     rbx
0x18000625f  cmp     rbx, r10
0x180006262  mov     rdx, r10; DestinationSize
0x180006265  mov     rcx, rdi; Destination
0x180006268  cmovnb  rbx, r10
0x18000626c  mov     r9, rbx; SourceSize
0x18000626f  call    cs:__imp_memcpy_s
0x180006275  mov     byte ptr [rbx+rdi-1], 0
0x18000627a  mov     al, 1
0x18000627c  add     rsp, 28h
0x180006280  pop     rdi
0x180006281  pop     rsi
0x180006282  pop     rbp
0x180006283  pop     rbx
0x180006284  retn
```
