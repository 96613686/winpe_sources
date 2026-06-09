# wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)

- ea: `0x18001345c`
- end: `0x180013547`
- name: `?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z`
- size: `235`
- prototype: `bool __fastcall(struct wil::FailureInfo *, struct wil::details::ThreadFailureCallbackHolder **, char *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180012c24`
- `0x18001345c`

## callees

- `0x18000ec1c`
- `0x18001345c`

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
0x18001345c  push    rbx
0x18001345e  push    rbp
0x18001345f  push    rsi
0x180013460  push    rdi
0x180013461  sub     rsp, 28h
0x180013465  xor     al, al
0x180013467  mov     byte ptr [r8], 0
0x18001346b  mov     rbp, r9
0x18001346e  mov     rdi, r8
0x180013471  mov     rsi, rdx
0x180013474  mov     rbx, rcx
0x180013477  test    rdx, rdx
0x18001347a  jz      loc_18001353E
0x180013480  mov     rdx, [rdx+10h]; struct wil::details::ThreadFailureCallbackHolder *
0x180013484  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180013489  mov     rdx, [rsi+20h]
0x18001348d  test    rdx, rdx
0x180013490  jz      loc_18001353E
0x180013496  cmp     dword ptr [rdx], 0
0x180013499  jnz     short loc_1800134AC
0x18001349b  mov     eax, 1
0x1800134a0  lock xadd cs:?s_telemetryId@ThreadFailureCallbackHolder@details@wil@@0JC, eax; long volatile wil::details::ThreadFailureCallbackHolder::s_telemetryId
0x1800134a8  inc     eax
0x1800134aa  mov     [rdx], eax
0x1800134ac  cmp     dword ptr [rbx+50h], 0
0x1800134b0  jnz     short loc_1800134C3
0x1800134b2  movups  xmm0, xmmword ptr [rdx]
0x1800134b5  movups  xmmword ptr [rbx+50h], xmm0
0x1800134b9  movsd   xmm1, qword ptr [rdx+10h]
0x1800134be  movsd   qword ptr [rbx+60h], xmm1
0x1800134c3  movups  xmm0, xmmword ptr [rdx]
0x1800134c6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800134ca  lea     r10, [rdi+rbp]
0x1800134ce  mov     rax, rcx
0x1800134d1  movups  xmmword ptr [rbx+68h], xmm0
0x1800134d5  movsd   xmm1, qword ptr [rdx+10h]
0x1800134da  movsd   qword ptr [rbx+78h], xmm1
0x1800134df  inc     rax
0x1800134e2  cmp     byte ptr [rdi+rax], 0
0x1800134e6  jnz     short loc_1800134DF
0x1800134e8  movsxd  r8, eax
0x1800134eb  mov     rax, r10
0x1800134ee  add     r8, rdi
0x1800134f1  sub     rax, r8
0x1800134f4  cmp     rax, 2
0x1800134f8  jle     short loc_18001353C
0x1800134fa  mov     byte ptr [r8], 5Ch ; '\'
0x1800134fe  lea     rdi, [r8+1]
0x180013502  mov     r8, [rdx+8]; Source
0x180013506  test    r8, r8
0x180013509  jz      short loc_180013517
0x18001350b  inc     rcx
0x18001350e  cmp     byte ptr [r8+rcx], 0
0x180013513  jnz     short loc_18001350B
0x180013515  jmp     short loc_180013519
0x180013517  xor     ecx, ecx
0x180013519  sub     r10, rdi
0x18001351c  movsxd  rbx, ecx
0x18001351f  inc     rbx
0x180013522  mov     rdx, r10; DestinationSize
0x180013525  cmp     rbx, r10
0x180013528  mov     rcx, rdi; Destination
0x18001352b  cmovnb  rbx, r10
0x18001352f  mov     r9, rbx; SourceSize
0x180013532  call    memcpy_s
0x180013537  mov     byte ptr [rbx+rdi-1], 0
0x18001353c  mov     al, 1
0x18001353e  add     rsp, 28h
0x180013542  pop     rdi
0x180013543  pop     rsi
0x180013544  pop     rbp
0x180013545  pop     rbx
0x180013546  retn
```
