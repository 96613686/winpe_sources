# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x180004810`
- end: `0x1800048ec`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `220`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800040c0`
- `0x180004810`

## callees

- `0x180004810`
- `0x180007d88`

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
0x180004810  push    rbx
0x180004812  push    rbp
0x180004813  push    rsi
0x180004814  push    rdi
0x180004815  sub     rsp, 28h
0x180004819  xor     al, al
0x18000481b  mov     byte ptr [r8], 0
0x18000481f  mov     rbp, r9
0x180004822  mov     rdi, r8
0x180004825  mov     rsi, rdx
0x180004828  mov     rbx, rcx
0x18000482b  test    rdx, rdx
0x18000482e  jz      loc_1800048E3
0x180004834  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180004838  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000483d  mov     rdx, [rsi+20h]
0x180004841  test    rdx, rdx
0x180004844  jz      loc_1800048E3
0x18000484a  cmp     dword ptr [rdx], 0
0x18000484d  jnz     short loc_180004860
0x18000484f  mov     eax, 1
0x180004854  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18000485c  inc     eax
0x18000485e  mov     [rdx], eax
0x180004860  cmp     dword ptr [rbx+50h], 0
0x180004864  jnz     short loc_180004877
0x180004866  movups  xmm0, xmmword ptr [rdx]
0x180004869  movups  xmmword ptr [rbx+50h], xmm0
0x18000486d  movsd   xmm1, qword ptr [rdx+10h]
0x180004872  movsd   qword ptr [rbx+60h], xmm1
0x180004877  movups  xmm0, xmmword ptr [rdx]
0x18000487a  lea     r10, [rdi+rbp]
0x18000487e  movups  xmmword ptr [rbx+68h], xmm0
0x180004882  movsd   xmm1, qword ptr [rdx+10h]
0x180004887  movsd   qword ptr [rbx+78h], xmm1
0x18000488c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180004890  mov     rax, rbx
0x180004893  inc     rax
0x180004896  cmp     byte ptr [rdi+rax], 0
0x18000489a  jnz     short loc_180004893
0x18000489c  lea     rcx, [rax+rdi]
0x1800048a0  mov     rax, r10
0x1800048a3  sub     rax, rcx
0x1800048a6  cmp     rax, 2
0x1800048aa  jle     short loc_1800048E1
0x1800048ac  mov     byte ptr [rcx], 5Ch ; '\'
0x1800048af  lea     rdi, [rcx+1]
0x1800048b3  mov     r8, [rdx+8]; Source
0x1800048b7  inc     rbx
0x1800048ba  cmp     byte ptr [r8+rbx], 0
0x1800048bf  jnz     short loc_1800048B7
0x1800048c1  sub     r10, rdi
0x1800048c4  inc     rbx
0x1800048c7  cmp     rbx, r10
0x1800048ca  mov     rdx, r10; DestinationSize
0x1800048cd  mov     rcx, rdi; Destination
0x1800048d0  cmovnb  rbx, r10
0x1800048d4  mov     r9, rbx; SourceSize
0x1800048d7  call    memcpy_s
0x1800048dc  mov     byte ptr [rbx+rdi-1], 0
0x1800048e1  mov     al, 1
0x1800048e3  add     rsp, 28h
0x1800048e7  pop     rdi
0x1800048e8  pop     rsi
0x1800048e9  pop     rbp
0x1800048ea  pop     rbx
0x1800048eb  retn
```
