# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18001dea4`
- end: `0x18001df9d`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `249`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder *, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001d820`
- `0x18001dea4`

## callees

- `0x18001dea4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001df74`
- `msvcrt!memcpy_s` at `0x18001df74`

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
  char *v10; // rcx
  __int64 v11; // rbx
  __int64 v12; // rax
  char *v13; // rdi
  _BYTE *v14; // rdi
  _BYTE *v15; // r8
  rsize_t v16; // rcx
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
      v10 = &a3[a4];
      *(_OWORD *)((char *)a1 + 104) = *(_OWORD *)v9;
      *((_QWORD *)a1 + 15) = *((_QWORD *)v9 + 2);
      v11 = -1;
      v12 = -1;
      do
        ++v12;
      while ( a3[v12] );
      v13 = &a3[v12];
      if ( v10 - v13 > 2 )
      {
        *v13 = 92;
        v14 = v13 + 1;
        v15 = (_BYTE *)*((_QWORD *)v9 + 1);
        do
          ++v11;
        while ( v15[v11] );
        v16 = v10 - v14;
        v17 = v11 + 1;
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
0x18001dea4  mov     [rsp+arg_0], rbx
0x18001dea9  mov     [rsp+arg_8], rbp
0x18001deae  mov     [rsp+arg_10], rsi
0x18001deb3  push    rdi
0x18001deb4  sub     rsp, 20h
0x18001deb8  xor     al, al
0x18001deba  mov     byte ptr [r8], 0
0x18001debe  mov     rbp, r9
0x18001dec1  mov     rdi, r8
0x18001dec4  mov     rsi, rdx
0x18001dec7  mov     rbx, rcx
0x18001deca  test    rdx, rdx
0x18001decd  jz      loc_18001DF87
0x18001ded3  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x18001ded7  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18001dedc  mov     rdx, [rsi+20h]
0x18001dee0  test    rdx, rdx
0x18001dee3  jz      loc_18001DF87
0x18001dee9  cmp     dword ptr [rdx], 0
0x18001deec  jnz     short loc_18001DEFF
0x18001deee  mov     eax, 1
0x18001def3  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x18001defb  inc     eax
0x18001defd  mov     [rdx], eax
0x18001deff  cmp     dword ptr [rbx+50h], 0
0x18001df03  jnz     short loc_18001DF16
0x18001df05  movups  xmm0, xmmword ptr [rdx]
0x18001df08  movups  xmmword ptr [rbx+50h], xmm0
0x18001df0c  movsd   xmm1, qword ptr [rdx+10h]
0x18001df11  movsd   qword ptr [rbx+60h], xmm1
0x18001df16  movups  xmm0, xmmword ptr [rdx]
0x18001df19  lea     rcx, [rdi+rbp]
0x18001df1d  movups  xmmword ptr [rbx+68h], xmm0
0x18001df21  movsd   xmm1, qword ptr [rdx+10h]
0x18001df26  movsd   qword ptr [rbx+78h], xmm1
0x18001df2b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001df2f  mov     rax, rbx
0x18001df32  inc     rax
0x18001df35  cmp     byte ptr [rdi+rax], 0
0x18001df39  jnz     short loc_18001DF32
0x18001df3b  add     rdi, rax
0x18001df3e  mov     rax, rcx
0x18001df41  sub     rax, rdi
0x18001df44  cmp     rax, 2
0x18001df48  jle     short loc_18001DF85
0x18001df4a  mov     byte ptr [rdi], 5Ch ; '\'
0x18001df4d  inc     rdi
0x18001df50  mov     r8, [rdx+8]; Source
0x18001df54  inc     rbx
0x18001df57  cmp     byte ptr [r8+rbx], 0
0x18001df5c  jnz     short loc_18001DF54
0x18001df5e  sub     rcx, rdi
0x18001df61  inc     rbx
0x18001df64  cmp     rbx, rcx
0x18001df67  mov     rdx, rcx; DestinationSize
0x18001df6a  cmovnb  rbx, rcx
0x18001df6e  mov     rcx, rdi; Destination
0x18001df71  mov     r9, rbx; SourceSize
0x18001df74  call    cs:__imp_memcpy_s
0x18001df7b  nop     dword ptr [rax+rax+00h]
0x18001df80  mov     byte ptr [rbx+rdi-1], 0
0x18001df85  mov     al, 1
0x18001df87  mov     rbx, [rsp+28h+arg_0]
0x18001df8c  mov     rbp, [rsp+28h+arg_8]
0x18001df91  mov     rsi, [rsp+28h+arg_10]
0x18001df96  add     rsp, 20h
0x18001df9a  pop     rdi
0x18001df9b  retn
```
