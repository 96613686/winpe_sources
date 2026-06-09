# RxFcbTableLookupFcb

- ea: `0x140055fc0`
- end: `0x14005650a`
- name: `RxFcbTableLookupFcb`
- size: `1354`
- prototype: `PFCB __stdcall(PRX_FCB_TABLE FcbTable, PUNICODE_STRING Path)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000d7c0`
- `0x140055950`

## callees

- `0x140024b0c`
- `0x140025d00`
- `0x140055fc0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400560fc`
- `ntoskrnl!ExAllocatePool2` at `0x1400560fc`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400561dd`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400562db`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14005640c`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400561dd`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400562db`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14005640c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14005612c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14005612c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140056433`
- `ntoskrnl!ExFreePoolWithTag` at `0x140056433`
- `ntoskrnl!RtlHashUnicodeString` at `0x140056012`
- `ntoskrnl!RtlHashUnicodeString` at `0x140056012`
- `ntoskrnl!KeBugCheckEx` at `0x1400564c9`
- `ntoskrnl!KeBugCheckEx` at `0x1400564c9`

## pseudocode

```c
PFCB __stdcall RxFcbTableLookupFcb(PRX_FCB_TABLE FcbTable, PUNICODE_STRING Path)
{
  char v2; // r8
  char v3; // r9
  unsigned __int64 v5; // r15
  BOOLEAN Blink; // cl
  char v7; // r13
  volatile signed __int64 *v9; // r12
  volatile signed __int64 v10; // rax
  __int64 (__fastcall *v11)(); // rdi
  unsigned __int64 Flink; // rbx
  char v13; // r13
  int v14; // eax
  unsigned __int64 v15; // rax
  char v16; // r14
  ULONG v17; // r15d
  __int64 Pool2; // rax
  __int64 v19; // rdi
  signed __int64 v20; // rax
  signed __int64 v21; // rtt
  struct _FCB *v22; // rbx
  char v24; // di
  unsigned __int64 i; // r14
  char v26; // cl
  char v27; // cl
  bool v28; // cf
  signed __int64 v29; // rax
  signed __int64 v30; // rtt
  bool v31; // zf
  _QWORD **v32; // rax
  _QWORD *v33; // rcx
  __int64 (__fastcall *v34)(); // rdi
  struct _LIST_ENTRY *v35; // r14
  int v36; // r14d
  int v37; // eax
  unsigned __int64 v38; // rax
  unsigned __int64 v39; // rax
  unsigned __int64 v40; // rax
  unsigned __int64 v41; // rax
  ULONG HashValue; // [rsp+70h] [rbp+8h] BYREF
  char v43; // [rsp+80h] [rbp+18h]
  char v44; // [rsp+88h] [rbp+20h]

  v44 = v3;
  v43 = v2;
  v5 = 0;
  Blink = (BOOLEAN)FcbTable->HashBuckets[2].Blink;
  v7 = v2;
  HashValue = 0;
  if ( !FcbTable->HashBuckets[2].Flink )
  {
    v9 = 0;
    v34 = RxpCompareFcbNamesCaseInsensitive;
    if ( !Blink )
      v34 = RxpCompareFcbNamesCaseSensitive;
    v35 = FcbTable->HashBuckets[1].Blink;
    Flink = (unsigned __int64)FcbTable->HashBuckets[1].Flink;
    if ( ((unsigned __int8)v35 & 1) != 0 )
    {
      if ( !Flink )
        goto LABEL_22;
      Flink ^= (unsigned __int64)&FcbTable->HashBuckets[1];
    }
    v36 = (unsigned __int8)v35 & 1;
    if ( !Flink )
      goto LABEL_23;
    while ( 1 )
    {
      v37 = ((__int64 (__fastcall *)(PUNICODE_STRING, unsigned __int64))v34)(Path, Flink);
      if ( v37 < 0 )
      {
        v38 = *(_QWORD *)Flink;
        if ( !v36 || !v38 )
          goto LABEL_92;
      }
      else
      {
        if ( v37 <= 0 )
          goto LABEL_22;
        v38 = *(_QWORD *)(Flink + 8);
        if ( !v36 || !v38 )
        {
LABEL_92:
          Flink = v38;
          goto LABEL_68;
        }
      }
      Flink ^= v38;
LABEL_68:
      if ( !Flink )
        goto LABEL_22;
    }
  }
  RtlHashUnicodeString(Path, Blink, 0, &HashValue);
  v9 = (volatile signed __int64 *)FcbTable->HashBuckets[2].Flink
     + (HashValue
      & 3
      ^ ((HashValue
        ^ ((HashValue ^ ((unsigned __int64)HashValue >> 6) ^ ((HashValue ^ ((unsigned __int64)HashValue >> 6)) >> 12)) >> 6)) >> 2)
      & 0x3F);
  v10 = *v9;
  if ( *v9 )
  {
    Flink = v10 & 0xFFFFFFFFFFFFFFFEuLL;
    if ( (v10 & 1) != 0 )
    {
      if ( *(_DWORD *)(Flink + 24) == HashValue
        && RtlEqualUnicodeString(Path, (PCUNICODE_STRING)(Flink + 8), (BOOLEAN)FcbTable->HashBuckets[2].Blink) )
      {
        goto LABEL_23;
      }
    }
    else
    {
      v5 = v10 & 0xFFFFFFFFFFFFFFFEuLL;
      if ( HashValue == *(_DWORD *)(Flink + 44)
        && RtlEqualUnicodeString(Path, (PCUNICODE_STRING)(Flink + 24), (BOOLEAN)FcbTable->HashBuckets[2].Blink) )
      {
        goto LABEL_30;
      }
    }
  }
  v11 = RxpCompareFcbNamesCaseInsensitive;
  Flink = (unsigned __int64)FcbTable->HashBuckets[1].Flink;
  if ( !LOBYTE(FcbTable->HashBuckets[2].Blink) )
    v11 = RxpCompareFcbNamesCaseSensitive;
  v13 = 0;
  if ( !Flink )
    goto LABEL_21;
  while ( 1 )
  {
    v14 = ((__int64 (__fastcall *)(PUNICODE_STRING, unsigned __int64))v11)(Path, Flink);
    if ( v14 > 0 )
    {
      v15 = *(_QWORD *)(Flink + 8);
      if ( !v15 )
      {
        v16 = 1;
        goto LABEL_13;
      }
      goto LABEL_8;
    }
    if ( v14 >= 0 )
      break;
    v15 = *(_QWORD *)Flink;
    if ( !*(_QWORD *)Flink )
      goto LABEL_58;
LABEL_8:
    Flink = v15;
  }
  v13 = 1;
LABEL_58:
  v16 = 0;
LABEL_13:
  if ( Flink && !v13 )
  {
    if ( (*v9 & 1) == 0 )
    {
      v17 = HashValue;
      Pool2 = ExAllocatePool2(258, Path->MaximumLength + 40LL, 1934456914);
      v19 = Pool2;
      if ( Pool2 )
      {
        *(_QWORD *)(Pool2 + 16) = Pool2 + 40;
        *(_WORD *)(Pool2 + 8) = 0;
        *(_WORD *)(Pool2 + 10) = Path->MaximumLength;
        RtlCopyUnicodeString((PUNICODE_STRING)(Pool2 + 8), Path);
        *(_QWORD *)v19 = Flink;
        *(_DWORD *)(v19 + 24) = v17;
        *(_DWORD *)(v19 + 28) = FcbTable->Version;
        *(_BYTE *)(v19 + 32) = v16;
        v20 = *v9;
        while ( (v20 & 1) == 0 )
        {
          v21 = v20;
          v20 = _InterlockedCompareExchange64(v9, v19 | 1, v20);
          if ( v21 == v20 )
          {
            _InterlockedIncrement16((volatile signed __int16 *)(Flink + 40));
            _InterlockedIncrement((volatile signed __int32 *)&FcbTable->CaseInsensitiveMatch);
            goto LABEL_25;
          }
        }
        ExFreePoolWithTag((PVOID)v19, 0);
        _InterlockedIncrement((volatile signed __int32 *)&FcbTable->CaseInsensitiveMatch);
        goto LABEL_25;
      }
    }
LABEL_23:
    _InterlockedIncrement((volatile signed __int32 *)&FcbTable->CaseInsensitiveMatch);
    goto LABEL_25;
  }
LABEL_21:
  v7 = v43;
LABEL_22:
  if ( !Flink )
    goto LABEL_23;
LABEL_30:
  v24 = 0;
  do
  {
    for ( i = Flink; i; v5 = 0 )
    {
      v26 = *(_BYTE *)(i + 43);
      if ( (v26 & 1) == v7 )
      {
        v27 = v26 & 0x3C;
        v5 = i;
        if ( v27 == 16 )
          break;
        v31 = v44 ? v27 == 8 : v27 == 12;
        if ( v31 || (v27 & 0xFB) == 0 )
          break;
      }
      if ( v24 )
      {
        v32 = *(_QWORD ***)(i + 8);
        if ( v32 )
        {
          v33 = *v32;
          if ( *v32 )
          {
            do
            {
              i = (unsigned __int64)v33;
              v33 = (_QWORD *)*v33;
            }
            while ( v33 );
          }
          else
          {
            i = *(_QWORD *)(i + 8);
          }
        }
        else
        {
          v39 = i;
          for ( i = *(_QWORD *)(i + 16) & 0xFFFFFFFFFFFFFFFCuLL; i; i = *(_QWORD *)(i + 16) & 0xFFFFFFFFFFFFFFFCuLL )
          {
            if ( *(_QWORD *)i == v39 )
              break;
            v39 = i;
          }
        }
      }
      else
      {
        v40 = *(_QWORD *)i;
        if ( *(_QWORD *)i )
        {
          i = *(_QWORD *)i;
          if ( *(_QWORD *)(v40 + 8) )
          {
            do
              i = *(_QWORD *)(i + 8);
            while ( *(_QWORD *)(i + 8) );
          }
        }
        else
        {
          v41 = i;
          for ( i = *(_QWORD *)(i + 16) & 0xFFFFFFFFFFFFFFFCuLL; i; i = *(_QWORD *)(i + 16) & 0xFFFFFFFFFFFFFFFCuLL )
          {
            if ( *(_QWORD *)(i + 8) == v41 )
              break;
            v41 = i;
          }
        }
      }
      if ( i && !RtlEqualUnicodeString((PCUNICODE_STRING)(i + 24), Path, (BOOLEAN)FcbTable->HashBuckets[2].Blink) )
      {
        v5 = 0;
        break;
      }
    }
    v28 = v24++ == -1;
  }
  while ( v28 || v24 == 1 );
  _InterlockedIncrement((volatile signed __int32 *)&FcbTable->CaseInsensitiveMatch);
  if ( v5 )
  {
    if ( FcbTable->HashBuckets[2].Flink )
    {
      v29 = *v9;
      do
      {
        if ( (v29 & 1) != 0 )
          break;
        v30 = v29;
        v29 = _InterlockedCompareExchange64(v9, v5 & 0xFFFFFFFFFFFFFFFEuLL, v29);
      }
      while ( v30 != v29 );
    }
    v22 = (struct _FCB *)(v5 - 312);
    if ( _InterlockedIncrement((volatile signed __int32 *)(v5 - 312 + 152)) == 1 )
      KeBugCheckEx(0x27u, 0xFCB003A5, v5 - 312, 1u, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qdZ(
        WPP_GLOBAL_Control->AttachedDevice,
        (*(unsigned __int8 *)(v5 + 43) >> 2) & 0xF,
        v2,
        v5 - 312,
        (*(_BYTE *)(v5 + 43) >> 2) & 0xF,
        (__int64)Path);
    }
  }
  else
  {
LABEL_25:
    v22 = 0;
    _InterlockedIncrement(&FcbTable->Lookups);
  }
  return v22;
}

```

## disassembly

```asm
0x140055fc0  mov     [rsp+arg_8], rbx
0x140055fc5  mov     [rsp+arg_18], r9b
0x140055fca  mov     [rsp+arg_10], r8b
0x140055fcf  push    rbp
0x140055fd0  push    rsi
0x140055fd1  push    rdi
0x140055fd2  push    r12
0x140055fd4  push    r13
0x140055fd6  push    r14
0x140055fd8  push    r15
0x140055fda  sub     rsp, 30h
0x140055fde  mov     rbp, rcx
0x140055fe1  xor     r15d, r15d
0x140055fe4  movzx   ecx, byte ptr [rcx+0B0h]
0x140055feb  movzx   r13d, r8b
0x140055fef  mov     rsi, rdx
0x140055ff2  mov     [rsp+68h+HashValue], r15d
0x140055ff7  cmp     [rbp+0A8h], r15
0x140055ffe  jz      loc_14005635E
0x140056004  movzx   edx, cl; CaseInSensitive
0x140056007  lea     r9, [rsp+68h+HashValue]; HashValue
0x14005600c  mov     rcx, rsi; String
0x14005600f  xor     r8d, r8d; HashAlgorithm
0x140056012  call    cs:__imp_RtlHashUnicodeString
0x140056019  nop     dword ptr [rax+rax+00h]
0x14005601e  mov     edx, [rsp+68h+HashValue]
0x140056022  mov     eax, edx
0x140056024  shr     rax, 6
0x140056028  mov     rcx, rax
0x14005602b  xor     rcx, rdx
0x14005602e  shr     rcx, 0Ch
0x140056032  xor     rcx, rax
0x140056035  mov     rax, [rbp+0A8h]
0x14005603c  xor     rcx, rdx
0x14005603f  shr     rcx, 6
0x140056043  xor     rcx, rdx
0x140056046  and     edx, 3
0x140056049  shr     rcx, 2
0x14005604d  and     ecx, 3Fh
0x140056050  xor     rcx, rdx
0x140056053  lea     r12, [rax+rcx*8]
0x140056057  mov     rax, [rax+rcx*8]
0x14005605b  test    rax, rax
0x14005605e  jnz     loc_1400561AF
0x140056064  cmp     byte ptr [rbp+0B0h], 0
0x14005606b  lea     rdi, RxpCompareFcbNamesCaseInsensitive
0x140056072  mov     rbx, [rbp+98h]
0x140056079  lea     rax, RxpCompareFcbNamesCaseSensitive
0x140056080  cmovz   rdi, rax
0x140056084  xor     r13b, r13b
0x140056087  test    rbx, rbx
0x14005608a  jz      loc_14005616F
0x140056090  mov     rdx, rbx
0x140056093  mov     rcx, rsi
0x140056096  mov     rax, rdi
0x140056099  call    _guard_dispatch_icall
0x14005609e  test    eax, eax
0x1400560a0  jle     short loc_1400560B0
0x1400560a2  mov     rax, [rbx+8]
0x1400560a6  test    rax, rax
0x1400560a9  jz      short loc_1400560C3
0x1400560ab  mov     rbx, rax
0x1400560ae  jmp     short loc_140056090
0x1400560b0  jns     loc_140056353
0x1400560b6  mov     rax, [rbx]
0x1400560b9  test    rax, rax
0x1400560bc  jnz     short loc_1400560AB
0x1400560be  jmp     loc_140056356
0x1400560c3  mov     r14b, 1
0x1400560c6  test    rbx, rbx
0x1400560c9  jz      loc_14005616F
0x1400560cf  test    r13b, r13b
0x1400560d2  jnz     loc_14005616F
0x1400560d8  mov     rax, [r12]
0x1400560dc  test    al, 1
0x1400560de  jnz     loc_14005617D
0x1400560e4  movzx   edx, word ptr [rsi+2]
0x1400560e8  mov     ecx, 102h
0x1400560ed  mov     r15d, [rsp+68h+HashValue]
0x1400560f2  add     rdx, 28h ; '('
0x1400560f6  mov     r8d, 734D7852h
0x1400560fc  call    cs:__imp_ExAllocatePool2
0x140056103  nop     dword ptr [rax+rax+00h]
0x140056108  mov     rdi, rax
0x14005610b  test    rax, rax
0x14005610e  jz      short loc_14005617D
0x140056110  add     rax, 28h ; '('
0x140056114  lea     rcx, [rdi+8]; DestinationString
0x140056118  mov     [rdi+10h], rax
0x14005611c  mov     rdx, rsi; SourceString
0x14005611f  xor     eax, eax
0x140056121  mov     [rcx], ax
0x140056124  movzx   eax, word ptr [rsi+2]
0x140056128  mov     [rdi+0Ah], ax
0x14005612c  call    cs:__imp_RtlCopyUnicodeString
0x140056133  nop     dword ptr [rax+rax+00h]
0x140056138  mov     [rdi], rbx
0x14005613b  mov     [rdi+18h], r15d
0x14005613f  mov     eax, [rbp+4]
0x140056142  mov     [rdi+1Ch], eax
0x140056145  mov     [rdi+20h], r14b
0x140056149  mov     rax, [r12]
0x14005614d  mov     rcx, rdi; P
0x140056150  test    al, 1
0x140056152  jnz     loc_140056431
0x140056158  or      rcx, 1
0x14005615c  lock cmpxchg [r12], rcx
0x140056162  jnz     short loc_14005614D
0x140056164  lock inc word ptr [rbx+28h]
0x140056169  lock inc dword ptr [rbp+8]
0x14005616d  jmp     short loc_140056190
0x14005616f  movzx   r13d, [rsp+68h+arg_10]
0x140056178  test    rbx, rbx
0x14005617b  jnz     short loc_1400561F1
0x14005617d  lock inc dword ptr [rbp+8]
0x140056181  jmp     short loc_140056190
0x140056183  lock inc dword ptr [rbp+8]
0x140056187  test    r15, r15
0x14005618a  jnz     loc_14005622C
0x140056190  xor     ebx, ebx
0x140056192  lock inc dword ptr [rbp+0Ch]
0x140056196  mov     rax, rbx
0x140056199  mov     rbx, [rsp+68h+arg_8]
0x14005619e  add     rsp, 30h
0x1400561a2  pop     r15
0x1400561a4  pop     r14
0x1400561a6  pop     r13
0x1400561a8  pop     r12
0x1400561aa  pop     rdi
0x1400561ab  pop     rsi
0x1400561ac  pop     rbp
0x1400561ad  retn
0x1400561af  mov     rbx, rax
0x1400561b2  and     rbx, 0FFFFFFFFFFFFFFFEh
0x1400561b6  test    al, 1
0x1400561b8  jnz     loc_1400562BF
0x1400561be  mov     eax, [rbx+2Ch]
0x1400561c1  mov     r15, rbx
0x1400561c4  cmp     [rsp+68h+HashValue], eax
0x1400561c8  jnz     loc_140056064
0x1400561ce  movzx   r8d, byte ptr [rbp+0B0h]; CaseInSensitive
0x1400561d6  lea     rdx, [rbx+18h]; String2
0x1400561da  mov     rcx, rsi; String1
0x1400561dd  call    cs:__imp_RtlEqualUnicodeString
0x1400561e4  nop     dword ptr [rax+rax+00h]
0x1400561e9  test    al, al
0x1400561eb  jz      loc_140056064
0x1400561f1  xor     dil, dil
0x1400561f4  mov     r14, rbx
0x1400561f7  test    rbx, rbx
0x1400561fa  jz      short loc_14005621E
0x1400561fc  movzx   ecx, byte ptr [r14+2Bh]
0x140056201  movzx   eax, cl
0x140056204  and     al, 1
0x140056206  cmp     al, r13b
0x140056209  jnz     loc_140056314
0x14005620f  and     cl, 3Ch
0x140056212  mov     r15, r14
0x140056215  cmp     cl, 10h
0x140056218  jnz     loc_1400562F4
0x14005621e  inc     dil
0x140056221  cmp     dil, 1
0x140056225  jbe     short loc_1400561F4
0x140056227  jmp     loc_140056183
0x14005622c  cmp     qword ptr [rbp+0A8h], 0
0x140056234  jz      short loc_14005624D
0x140056236  mov     rax, [r12]
0x14005623a  test    al, 1
0x14005623c  jnz     short loc_14005624D
0x14005623e  mov     rcx, r15
0x140056241  and     rcx, 0FFFFFFFFFFFFFFFEh
0x140056245  lock cmpxchg [r12], rcx
0x14005624b  jnz     short loc_14005623A
0x14005624d  lea     rbx, [r15-138h]
0x140056254  mov     eax, 1
0x140056259  lock xadd [rbx+98h], eax
0x140056261  inc     eax
0x140056263  cmp     eax, 1
0x140056266  jz      loc_1400564AD
0x14005626c  mov     rcx, cs:WPP_GLOBAL_Control
0x140056273  lea     rax, WPP_GLOBAL_Control
0x14005627a  cmp     rcx, rax
0x14005627d  jz      loc_140056196
0x140056283  test    dword ptr [rcx+2Ch], 100h
0x14005628a  jz      loc_140056196
0x140056290  cmp     byte ptr [rcx+29h], 4
0x140056294  jb      loc_140056196
0x14005629a  movzx   edx, byte ptr [r15+2Bh]
0x14005629f  mov     r9, rbx
0x1400562a2  mov     rcx, [rcx+18h]
0x1400562a6  shr     edx, 2
0x1400562a9  and     edx, 0Fh
0x1400562ac  mov     [rsp+68h+var_40], rsi
0x1400562b1  mov     dword ptr [rsp+68h+BugCheckParameter4], edx
0x1400562b5  call    WPP_SF_qdZ
0x1400562ba  jmp     loc_140056196
0x1400562bf  mov     eax, [rsp+68h+HashValue]
0x1400562c3  cmp     [rbx+18h], eax
0x1400562c6  jnz     loc_140056064
0x1400562cc  movzx   r8d, byte ptr [rbp+0B0h]; CaseInSensitive
0x1400562d4  lea     rdx, [rbx+8]; String2
0x1400562d8  mov     rcx, rsi; String1
0x1400562db  call    cs:__imp_RtlEqualUnicodeString
0x1400562e2  nop     dword ptr [rax+rax+00h]
0x1400562e7  test    al, al
0x1400562e9  jz      loc_140056064
0x1400562ef  jmp     loc_14005617D
0x1400562f4  cmp     [rsp+68h+arg_18], 0
0x1400562fc  jnz     loc_140056448
0x140056302  cmp     cl, 0Ch
0x140056305  jz      loc_14005621E
0x14005630b  test    cl, 0FBh
0x14005630e  jz      loc_14005621E
0x140056314  test    dil, dil
0x140056317  jz      loc_140056455
0x14005631d  mov     rax, [r14+8]
0x140056321  test    rax, rax
0x140056324  jz      loc_1400563D9
0x14005632a  mov     rcx, [rax]
0x14005632d  test    rcx, rcx
0x140056330  jz      loc_140056450
0x140056336  nop     word ptr [rax+rax+00000000h]
0x140056340  mov     rax, [rcx]
0x140056343  mov     r14, rcx
0x140056346  mov     rcx, rax
0x140056349  test    rax, rax
0x14005634c  jnz     short loc_140056340
0x14005634e  jmp     loc_1400563F8
0x140056353  mov     r13b, 1
0x140056356  xor     r14b, r14b
0x140056359  jmp     loc_1400560C6
0x14005635e  xor     r12d, r12d
0x140056361  lea     rax, RxpCompareFcbNamesCaseSensitive
0x140056368  test    cl, cl
0x14005636a  lea     rdi, RxpCompareFcbNamesCaseInsensitive
0x140056371  cmovz   rdi, rax
0x140056375  lea     rax, [rbp+98h]
0x14005637c  mov     r14, [rax+8]
0x140056380  mov     rbx, [rax]
0x140056383  test    r14b, 1
0x140056387  jnz     loc_1400564D6
0x14005638d  and     r14d, 1
0x140056391  test    rbx, rbx
0x140056394  jz      loc_14005617D
0x14005639a  mov     rdx, rbx
0x14005639d  mov     rcx, rsi
0x1400563a0  mov     rax, rdi
0x1400563a3  call    _guard_dispatch_icall
0x1400563a8  test    eax, eax
0x1400563aa  js      loc_1400564F0
0x1400563b0  jle     loc_140056178
0x1400563b6  mov     rax, [rbx+8]
0x1400563ba  test    r14d, r14d
0x1400563bd  jz      loc_1400564E8
0x1400563c3  test    rax, rax
0x1400563c6  jz      loc_1400564E8
0x1400563cc  xor     rbx, rax
0x1400563cf  test    rbx, rbx
0x1400563d2  jnz     short loc_14005639A
0x1400563d4  jmp     loc_140056178
0x1400563d9  mov     rax, r14
0x1400563dc  mov     r14, [r14+10h]
0x1400563e0  and     r14, 0FFFFFFFFFFFFFFFCh
0x1400563e4  jz      short loc_1400563F8
0x1400563e6  cmp     [r14], rax
0x1400563e9  jz      short loc_1400563F8
0x1400563eb  mov     rax, r14
0x1400563ee  mov     r14, [r14+10h]
0x1400563f2  and     r14, 0FFFFFFFFFFFFFFFCh
0x1400563f6  jnz     short loc_1400563E6
0x1400563f8  test    r14, r14
0x1400563fb  jz      short loc_140056420
0x1400563fd  movzx   r8d, byte ptr [rbp+0B0h]; CaseInSensitive
0x140056405  lea     rcx, [r14+18h]; String1
0x140056409  mov     rdx, rsi; String2
0x14005640c  call    cs:__imp_RtlEqualUnicodeString
0x140056413  nop     dword ptr [rax+rax+00h]
0x140056418  test    al, al
0x14005641a  jz      loc_140056502
0x140056420  xor     r15d, r15d
0x140056423  test    r14, r14
0x140056426  jz      loc_14005621E
0x14005642c  jmp     loc_1400561FC
0x140056431  xor     edx, edx; Tag
0x140056433  call    cs:__imp_ExFreePoolWithTag
0x14005643a  nop     dword ptr [rax+rax+00h]
0x14005643f  lock inc dword ptr [rbp+8]
0x140056443  jmp     loc_140056190
0x140056448  cmp     cl, 8
0x14005644b  jmp     loc_140056305
0x140056450  mov     r14, rax
0x140056453  jmp     short loc_1400563F8
0x140056455  mov     rax, [r14]
0x140056458  test    rax, rax
0x14005645b  jz      short loc_140056477
0x14005645d  cmp     qword ptr [rax+8], 0
0x140056462  mov     r14, rax
0x140056465  jz      short loc_1400563F8
0x140056467  mov     rax, [r14+8]
0x14005646b  mov     r14, rax
  ... truncated ...
```
