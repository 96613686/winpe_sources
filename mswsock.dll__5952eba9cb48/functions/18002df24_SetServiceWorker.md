# SetServiceWorker

- ea: `0x18002df24`
- end: `0x18002e195`
- name: `SetServiceWorker`
- size: `625`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18002dcc0`
- `0x18002def0`

## callees

- `0x180022bd2`
- `0x18002cffc`
- `0x18002d414`
- `0x18002da98`
- `0x18002df24`
- `0x18002ff9c`
- `0x180030078`
- `0x180053010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18002e084`
- `ntdll!RtlFreeHeap` at `0x18002e0c3`
- `ntdll!RtlFreeHeap` at `0x18002e156`
- `ntdll!RtlFreeHeap` at `0x18002e084`
- `ntdll!RtlFreeHeap` at `0x18002e0c3`
- `ntdll!RtlFreeHeap` at `0x18002e156`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e0a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e11f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e171`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e0a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e11f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e171`

## pseudocode

```c
__int64 __fastcall SetServiceWorker(
        unsigned int a1,
        unsigned int a2,
        unsigned int a3,
        __m128i *a4,
        __int64 a5,
        unsigned int a6,
        _DWORD *a7)
{
  int v7; // esi
  void *v11; // rdi
  DWORD v12; // ecx
  bool v13; // zf
  DWORD UnicodeString; // eax
  __m128i v15; // xmm1
  __m128i v16; // xmm1
  __m128i v17; // xmm0
  unsigned __int64 v18; // xmm0_8
  CHAR *v19; // rbx
  DWORD v20; // eax
  DWORD v21; // eax
  DWORD v22; // esi
  __int64 *v23; // rbx
  __int64 (__fastcall *v24)(_QWORD, _QWORD, _QWORD, _OWORD *); // rax
  DWORD v25; // eax
  __int32 v27; // [rsp+30h] [rbp-61h] BYREF
  void *v28; // [rsp+38h] [rbp-59h] BYREF
  _OWORD v29[4]; // [rsp+40h] [rbp-51h] BYREF
  __m128i v30; // [rsp+80h] [rbp-11h]

  v7 = 0;
  v28 = 0;
  v27 = 0;
  v11 = 0;
  memset_0(v29, 0, 0x50u);
  if ( a5 )
  {
    v12 = 50;
LABEL_39:
    SetLastError(v12);
    return 0xFFFFFFFFLL;
  }
  if ( !a4 || !a7 )
    goto LABEL_38;
  v13 = NspInitialized == 0;
  *a7 = 0;
  if ( v13 )
  {
    UnicodeString = InitializeNsp();
    if ( UnicodeString )
      goto LABEL_7;
  }
  v15 = a4[1];
  v29[0] = *a4;
  v29[1] = v15;
  v16 = a4[3];
  v29[2] = a4[2];
  v29[3] = v16;
  v17 = a4[4];
  v30 = v17;
  if ( a2 - 4 <= 1 )
  {
    if ( _mm_cvtsi128_si32(v17) )
    {
      v18 = _mm_srli_si128(v17, 8).m128i_u64[0];
      if ( v18 )
      {
        v19 = *(CHAR **)v18;
        if ( !a6 )
        {
          UnicodeString = AllocateUnicodeString(*(LPCCH *)v18);
          if ( UnicodeString )
          {
LABEL_7:
            v12 = UnicodeString;
            goto LABEL_39;
          }
          v19 = 0;
        }
        if ( v19 && *(_WORD *)v19 )
        {
          v20 = SSRegistrySettings(a2, (const WCHAR *)v19, *(const UUID **)&v29[0]);
          if ( !v20 )
          {
            v21 = PackBlobWorker(
                    *(_QWORD *)v18,
                    *(_DWORD *)(v18 + 8),
                    (int)v18 + 16,
                    (unsigned int)&v28,
                    (__int64)&v27,
                    a6 == 0);
            v11 = v28;
            v22 = v21;
            if ( !v21 )
            {
              v30.m128i_i32[0] = v27;
              v30.m128i_i64[1] = (__int64)v28;
            }
            if ( !a6 )
              RtlFreeHeap(SockPrivateHeap, 0, v19);
            if ( v22 )
            {
              v12 = v22;
              goto LABEL_39;
            }
            v7 = 0;
            goto LABEL_27;
          }
        }
        else
        {
          v20 = 87;
        }
        SetLastError(v20);
        if ( !a6 )
          RtlFreeHeap(SockPrivateHeap, 0, v19);
        return 0xFFFFFFFFLL;
      }
    }
LABEL_38:
    v12 = 87;
    goto LABEL_39;
  }
LABEL_27:
  v23 = (__int64 *)NameSpaceListHead;
  if ( (__int64 *)NameSpaceListHead != &NameSpaceListHead )
  {
    do
    {
      if ( (unsigned int)IsValidNameSpace(a1, v23) )
      {
        v24 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _OWORD *))v23[4];
        if ( v24 )
        {
          v25 = v24(a2, a3, a6, v29);
          if ( v25 )
          {
            *a7 |= 1u;
            SetLastError(v25);
          }
          else
          {
            v7 = 1;
          }
        }
      }
      v23 = (__int64 *)*v23;
    }
    while ( v23 != &NameSpaceListHead );
    v11 = v28;
  }
  if ( v11 )
    RtlFreeHeap(SockPrivateHeap, 0, v11);
  return (unsigned int)(v7 != 0) - 1;
}

```

## disassembly

```asm
0x18002df24  mov     [rsp-8+arg_10], r8d
0x18002df29  push    rbp
0x18002df2a  push    rbx
0x18002df2b  push    rsi
0x18002df2c  push    rdi
0x18002df2d  push    r12
0x18002df2f  push    r13
0x18002df31  push    r14
0x18002df33  push    r15
0x18002df35  lea     rbp, [rsp-7]
0x18002df3a  sub     rsp, 98h
0x18002df41  xor     esi, esi
0x18002df43  mov     r13d, edx
0x18002df46  mov     r12d, ecx
0x18002df49  mov     [rbp+3Fh+var_98], rsi
0x18002df4d  xor     edx, edx; Val
0x18002df4f  mov     [rbp+3Fh+var_A0], esi
0x18002df52  lea     rcx, [rbp+3Fh+var_90]; void *
0x18002df56  mov     rbx, r9
0x18002df59  lea     r8d, [rsi+50h]; Size
0x18002df5d  mov     edi, esi
0x18002df5f  call    memset_0
0x18002df64  cmp     [rbp+3Fh+arg_20], rsi
0x18002df68  jz      short loc_18002DF72
0x18002df6a  lea     ecx, [rsi+32h]
0x18002df6d  jmp     loc_18002E171
0x18002df72  test    rbx, rbx
0x18002df75  jz      loc_18002E16C
0x18002df7b  mov     r14, [rbp+3Fh+arg_30]
0x18002df7f  test    r14, r14
0x18002df82  jz      loc_18002E16C
0x18002df88  cmp     cs:NspInitialized, esi
0x18002df8e  mov     [r14], esi
0x18002df91  jnz     short loc_18002DFA3
0x18002df93  call    InitializeNsp
0x18002df98  test    eax, eax
0x18002df9a  jz      short loc_18002DFA3
0x18002df9c  mov     ecx, eax
0x18002df9e  jmp     loc_18002E171
0x18002dfa3  movups  xmm0, xmmword ptr [rbx]
0x18002dfa6  mov     r15d, [rbp+3Fh+arg_28]
0x18002dfaa  lea     eax, [r13-4]
0x18002dfae  movups  xmm1, xmmword ptr [rbx+10h]
0x18002dfb2  movaps  [rbp+3Fh+var_90], xmm0
0x18002dfb6  movaps  [rbp+3Fh+var_80], xmm1
0x18002dfba  movups  xmm0, xmmword ptr [rbx+20h]
0x18002dfbe  movups  xmm1, xmmword ptr [rbx+30h]
0x18002dfc2  movaps  [rbp+3Fh+var_70], xmm0
0x18002dfc6  movaps  [rbp+3Fh+var_60], xmm1
0x18002dfca  movups  xmm0, xmmword ptr [rbx+40h]
0x18002dfce  movaps  [rbp+3Fh+var_50], xmm0
0x18002dfd2  cmp     eax, 1
0x18002dfd5  ja      loc_18002E0D6
0x18002dfdb  movd    eax, xmm0
0x18002dfdf  mov     [rbp+3Fh+arg_20], rsi
0x18002dfe3  test    eax, eax
0x18002dfe5  jz      loc_18002E16C
0x18002dfeb  psrldq  xmm0, 8
0x18002dff0  movq    rdi, xmm0
0x18002dff5  test    rdi, rdi
0x18002dff8  jz      loc_18002E16C
0x18002dffe  mov     rbx, [rdi]
0x18002e001  test    r15d, r15d
0x18002e004  jnz     short loc_18002E01A
0x18002e006  lea     rdx, [rbp+3Fh+arg_20]
0x18002e00a  mov     rcx, rbx; lpMultiByteStr
0x18002e00d  call    AllocateUnicodeString
0x18002e012  test    eax, eax
0x18002e014  jnz     short loc_18002DF9C
0x18002e016  mov     rbx, [rbp+3Fh+arg_20]
0x18002e01a  test    rbx, rbx
0x18002e01d  jz      short loc_18002E09B
0x18002e01f  cmp     [rbx], si
0x18002e022  jz      short loc_18002E09B
0x18002e024  mov     r8, qword ptr [rbp+3Fh+var_90]
0x18002e028  mov     rdx, rbx
0x18002e02b  mov     ecx, r13d
0x18002e02e  call    SSRegistrySettings
0x18002e033  test    eax, eax
0x18002e035  jnz     short loc_18002E0A0
0x18002e037  mov     edx, [rdi+8]
0x18002e03a  lea     r8, [rdi+10h]
0x18002e03e  mov     rcx, [rdi]
0x18002e041  lea     r9, [rbp+3Fh+var_98]
0x18002e045  mov     eax, esi
0x18002e047  test    r15d, r15d
0x18002e04a  setz    al
0x18002e04d  mov     [rsp+0D0h+var_A8], eax
0x18002e051  lea     rax, [rbp+3Fh+var_A0]
0x18002e055  mov     [rsp+0D0h+var_B0], rax
0x18002e05a  call    PackBlobWorker
0x18002e05f  mov     rdi, [rbp+3Fh+var_98]
0x18002e063  mov     esi, eax
0x18002e065  test    eax, eax
0x18002e067  jnz     short loc_18002E073
0x18002e069  mov     ecx, [rbp+3Fh+var_A0]
0x18002e06c  mov     dword ptr [rbp+3Fh+var_50], ecx
0x18002e06f  mov     qword ptr [rbp+3Fh+var_50+8], rdi
0x18002e073  test    r15d, r15d
0x18002e076  jnz     short loc_18002E090
0x18002e078  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18002e07f  mov     r8, rbx; P
0x18002e082  xor     edx, edx; Flags
0x18002e084  call    cs:__imp_RtlFreeHeap
0x18002e08b  nop     dword ptr [rax+rax+00h]
0x18002e090  test    esi, esi
0x18002e092  jz      short loc_18002E0D4
0x18002e094  mov     ecx, esi
0x18002e096  jmp     loc_18002E171
0x18002e09b  mov     eax, 57h ; 'W'
0x18002e0a0  mov     ecx, eax; dwErrCode
0x18002e0a2  call    cs:__imp_SetLastError
0x18002e0a9  nop     dword ptr [rax+rax+00h]
0x18002e0ae  test    r15d, r15d
0x18002e0b1  jnz     loc_18002E17D
0x18002e0b7  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18002e0be  mov     r8, rbx; P
0x18002e0c1  xor     edx, edx; Flags
0x18002e0c3  call    cs:__imp_RtlFreeHeap
0x18002e0ca  nop     dword ptr [rax+rax+00h]
0x18002e0cf  jmp     loc_18002E17D
0x18002e0d4  xor     esi, esi
0x18002e0d6  mov     rbx, cs:NameSpaceListHead
0x18002e0dd  lea     rax, NameSpaceListHead
0x18002e0e4  cmp     rbx, rax
0x18002e0e7  jz      short loc_18002E145
0x18002e0e9  mov     edi, [rbp+3Fh+arg_10]
0x18002e0ec  mov     rdx, rbx
0x18002e0ef  mov     ecx, r12d
0x18002e0f2  call    IsValidNameSpace
0x18002e0f7  test    eax, eax
0x18002e0f9  jz      short loc_18002E132
0x18002e0fb  mov     rax, [rbx+20h]
0x18002e0ff  test    rax, rax
0x18002e102  jz      short loc_18002E132
0x18002e104  lea     r9, [rbp+3Fh+var_90]
0x18002e108  mov     r8d, r15d
0x18002e10b  mov     edx, edi
0x18002e10d  mov     ecx, r13d
0x18002e110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e115  test    eax, eax
0x18002e117  jz      short loc_18002E12D
0x18002e119  or      dword ptr [r14], 1
0x18002e11d  mov     ecx, eax; dwErrCode
0x18002e11f  call    cs:__imp_SetLastError
0x18002e126  nop     dword ptr [rax+rax+00h]
0x18002e12b  jmp     short loc_18002E132
0x18002e12d  mov     esi, 1
0x18002e132  mov     rbx, [rbx]
0x18002e135  lea     rax, NameSpaceListHead
0x18002e13c  cmp     rbx, rax
0x18002e13f  jnz     short loc_18002E0EC
0x18002e141  mov     rdi, [rbp+3Fh+var_98]
0x18002e145  test    rdi, rdi
0x18002e148  jz      short loc_18002E162
0x18002e14a  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18002e151  mov     r8, rdi; P
0x18002e154  xor     edx, edx; Flags
0x18002e156  call    cs:__imp_RtlFreeHeap
0x18002e15d  nop     dword ptr [rax+rax+00h]
0x18002e162  neg     esi
0x18002e164  sbb     eax, eax
0x18002e166  neg     eax
0x18002e168  dec     eax
0x18002e16a  jmp     short loc_18002E180
0x18002e16c  mov     ecx, 57h ; 'W'; dwErrCode
0x18002e171  call    cs:__imp_SetLastError
0x18002e178  nop     dword ptr [rax+rax+00h]
0x18002e17d  or      eax, 0FFFFFFFFh
0x18002e180  add     rsp, 98h
0x18002e187  pop     r15
0x18002e189  pop     r14
0x18002e18b  pop     r13
0x18002e18d  pop     r12
0x18002e18f  pop     rdi
0x18002e190  pop     rsi
0x18002e191  pop     rbx
0x18002e192  pop     rbp
0x18002e193  retn
```
