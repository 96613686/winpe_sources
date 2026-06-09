# NpQueryDirectory

- ea: `0x140014ed4`
- end: `0x14001543d`
- name: `NpQueryDirectory`
- size: `1385`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140014e30`

## callees

- `0x140001e10`
- `0x140001e40`
- `0x140001e60`
- `0x140001f40`
- `0x140002240`
- `0x14000b054`
- `0x14000b0b8`
- `0x14000b118`
- `0x140014ed4`

## import_xrefs

- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140015057`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140015057`
- `ntoskrnl!ExAllocatePool2` at `0x14001500a`
- `ntoskrnl!ExAllocatePool2` at `0x14001500a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001540b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001540b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001507e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001507e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400150aa`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400150aa`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400153cf`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400153cf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400153f5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400153f5`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x140015156`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x140015156`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400153e9`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400153e9`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140015098`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140015098`

## pseudocode

```c
__int64 __fastcall NpQueryDirectory(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // r9
  __int64 v5; // rax
  USHORT v6; // di
  WCHAR *v8; // rdx
  char v9; // r15
  __int64 v10; // r12
  struct _UNICODE_STRING *v11; // r14
  USHORT v12; // ax
  struct _UNICODE_STRING *Pool2; // rax
  __int64 v14; // r8
  __int64 v15; // r9
  struct _UNICODE_STRING *v16; // rsi
  unsigned int v17; // edi
  unsigned int v18; // r12d
  __int64 *v19; // rax
  __int64 *v20; // r15
  unsigned __int16 *v21; // rdi
  unsigned int v22; // edx
  unsigned int v23; // ecx
  unsigned int v24; // eax
  unsigned int v25; // r8d
  bool v26; // cf
  _DWORD *v27; // r15
  _DWORD *v28; // rcx
  __int16 v29; // ax
  void *v30; // rdx
  void *v31; // rcx
  __int64 v32; // rdx
  _DWORD *v33; // rcx
  unsigned int v34; // edx
  char v35; // [rsp+20h] [rbp-128h]
  char v36; // [rsp+21h] [rbp-127h]
  unsigned int Size; // [rsp+24h] [rbp-124h]
  unsigned int Size_4; // [rsp+28h] [rbp-120h]
  unsigned int v39; // [rsp+30h] [rbp-118h]
  unsigned int v40; // [rsp+34h] [rbp-114h]
  unsigned int v41; // [rsp+38h] [rbp-110h]
  __int64 *v42; // [rsp+40h] [rbp-108h]
  UNICODE_STRING SourceString; // [rsp+50h] [rbp-F8h] BYREF
  unsigned int v45; // [rsp+60h] [rbp-E8h]
  int v46; // [rsp+64h] [rbp-E4h]
  unsigned int v47; // [rsp+68h] [rbp-E0h]
  unsigned int v48; // [rsp+6Ch] [rbp-DCh]
  unsigned int v49; // [rsp+70h] [rbp-D8h]
  __int64 v50; // [rsp+78h] [rbp-D0h]
  struct _UNICODE_STRING *v51; // [rsp+80h] [rbp-C8h]
  __int64 v52; // [rsp+88h] [rbp-C0h]
  __int64 v53; // [rsp+90h] [rbp-B8h]
  __int64 v54; // [rsp+98h] [rbp-B0h]
  __int64 *v55; // [rsp+A0h] [rbp-A8h]
  _QWORD Src[10]; // [rsp+B0h] [rbp-98h] BYREF

  v54 = a3;
  v52 = a1;
  v53 = a2;
  v4 = *(_QWORD *)(a3 + 184);
  v5 = *(_QWORD *)(v4 + 16);
  if ( v5 )
  {
    v6 = *(_WORD *)v5;
    if ( (*(_WORD *)v5 & 1) != 0 )
      return 3221225485LL;
    v8 = *(WCHAR **)(v5 + 8);
  }
  else
  {
    v6 = 0;
    v8 = 0;
  }
  v46 = *(_DWORD *)(v4 + 24);
  switch ( v46 )
  {
    case 1:
      Size = 64;
      break;
    case 2:
      Size = 68;
      break;
    case 3:
      Size = 94;
      break;
    case 12:
      Size = 12;
      break;
    default:
      return 3221225475LL;
  }
  v45 = *(_DWORD *)(v4 + 8);
  v39 = *(_DWORD *)(v4 + 32);
  v9 = *(_BYTE *)(v4 + 2);
  v10 = *(_QWORD *)(v4 + 48);
  v50 = *(_QWORD *)(a3 + 112);
  v35 = *(_BYTE *)(a3 + 64);
  v11 = 0;
  if ( !*(_QWORD *)(a2 + 16) )
  {
    *(_QWORD *)&SourceString.Length = 0;
    if ( v6 )
    {
      v12 = v6;
      SourceString.Buffer = v8;
    }
    else
    {
      v12 = 2;
      SourceString.Buffer = (PWSTR)qword_140006080;
    }
    SourceString.Length = v12;
    Pool2 = (struct _UNICODE_STRING *)ExAllocatePool2(257, v12 + 16LL, 1900441678);
    v11 = Pool2;
    if ( !Pool2 )
      return 3221225626LL;
    Pool2->Length = 0;
    Pool2->MaximumLength = SourceString.Length;
    Pool2->Buffer = &Pool2[1].Length;
    if ( (NpCompatFlags & 1) != 0 || !v6 )
    {
      memmove(&Pool2[1], SourceString.Buffer, SourceString.Length);
      v11->Length = SourceString.Length;
    }
    else
    {
      RtlUpcaseUnicodeString(Pool2, &SourceString, 0);
    }
  }
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(a1 + 192, 0);
  ExAcquirePushLockExclusiveEx(a2 + 8, 0, v14, v15);
  if ( (*(_QWORD *)(v10 + 32) & 1) == 0 )
  {
    v16 = v11;
    v17 = -1073741811;
    goto LABEL_72;
  }
  v36 = v9 & 2;
  Size_4 = 0;
  v41 = 0;
  v18 = 0;
  if ( *(_QWORD *)(a2 + 16) )
  {
    v16 = v11;
    v11 = *(struct _UNICODE_STRING **)(a2 + 16);
  }
  else
  {
    v16 = 0;
    *(_QWORD *)(a2 + 16) = v11;
  }
  v51 = v16;
  if ( (v9 & 1) != 0 )
  {
    v39 = 0;
  }
  else if ( (v9 & 4) == 0 )
  {
    v39 = *(_DWORD *)(a2 + 4);
  }
  v19 = (__int64 *)(a1 + 200);
  v55 = (__int64 *)(a1 + 200);
  v20 = *(__int64 **)(a1 + 200);
  while ( 1 )
  {
    v42 = v20;
    if ( v20 == v19 )
      break;
    v21 = (unsigned __int16 *)(v20 + 3);
    if ( !FsRtlIsNameInExpression(v11, (PUNICODE_STRING)(v20 + 3), 1u, 0) )
      goto LABEL_70;
    v22 = Size_4;
    if ( Size_4 >= v39 )
    {
      v23 = v45 - v18;
      v49 = v45 - v18;
      if ( v18 && (Size + *v21 > v23 || v45 < v18) )
        goto LABEL_41;
      v24 = *v21;
      v40 = v24;
      v25 = v24 + Size;
      v48 = v24 + Size;
      v26 = v23 < v24 + Size;
      if ( v23 < v24 + Size )
      {
        v24 = v23 - Size;
        v40 = v23 - Size;
        v26 = v23 < v25;
      }
      v17 = v26 ? 0x80000005 : 0;
      v47 = Size + v24;
      v27 = (_DWORD *)(v50 + v18);
      if ( v35 )
        RtlSetUserMemory(v27);
      else
        RtlSetVolatileMemory(v27, 0, Size);
      if ( v46 != 1 && (unsigned int)(v46 - 2) >= 2 )
      {
        v28 = v27 + 2;
        if ( v35 )
          RtlWriteULongToUser(v28, *((unsigned __int16 *)v42 + 12));
        else
          *v28 = *((unsigned __int16 *)v42 + 12);
        goto LABEL_60;
      }
      memset(Src, 0, 0x48u);
      v29 = *((_WORD *)v42 - 68);
      if ( v29 == 514 )
      {
        Src[5] = *((unsigned int *)v42 - 4);
        Src[6] = *((unsigned int *)v42 + 29);
        goto LABEL_56;
      }
      if ( v29 == 519 )
      {
        Src[5] = *((unsigned int *)v42 - 4);
        Src[6] = 1;
LABEL_56:
        LODWORD(Src[7]) = 128;
        HIDWORD(Src[7]) = *((unsigned __int16 *)v42 + 12);
      }
      if ( v35 )
        RtlCopyToUser(v27, Src, 0x48u);
      else
        RtlCopyVolatileMemory(v27, Src, 0x48u);
LABEL_60:
      v20 = v42;
      v30 = (void *)v42[4];
      v31 = (void *)(v50 + v18 + Size);
      if ( v35 )
        RtlCopyToUser(v31, v30, v40);
      else
        RtlCopyVolatileMemory(v31, v30, v40);
      v32 = v18 - v41;
      v33 = (_DWORD *)(v41 + v50);
      if ( v35 )
        RtlWriteULongToUser(v33, v32);
      else
        *v33 = v32;
      v34 = v47;
      *(_QWORD *)(v54 + 56) = v47 + v18;
      if ( v48 > v49 )
        goto LABEL_72;
      *(_DWORD *)(a2 + 4) = Size_4 + 1;
      if ( v36 )
      {
LABEL_41:
        v17 = 0;
        goto LABEL_72;
      }
      v41 = v18;
      v18 += (v34 + 7) & 0xFFFFFFF8;
      v22 = Size_4;
    }
    Size_4 = v22 + 1;
LABEL_70:
    v20 = (__int64 *)*v20;
    v19 = v55;
  }
  v17 = v18 == 0 ? 0x80000006 : 0;
LABEL_72:
  ExReleasePushLockExclusiveEx(a2 + 8, 0);
  ExReleasePushLockSharedEx(a1 + 192, 0);
  KeLeaveCriticalRegion();
  if ( v16 )
    ExFreePoolWithTag(v16, 0);
  return v17;
}

```

## disassembly

```asm
0x140014ed4  push    rbx
0x140014ed6  push    rsi
0x140014ed7  push    rdi
0x140014ed8  push    r12
0x140014eda  push    r13
0x140014edc  push    r14
0x140014ede  push    r15
0x140014ee0  sub     rsp, 110h
0x140014ee7  mov     rax, cs:__security_cookie
0x140014eee  xor     rax, rsp
0x140014ef1  mov     [rsp+148h+var_48], rax
0x140014ef9  mov     [rsp+148h+var_B0], r8
0x140014f01  mov     r13, rdx
0x140014f04  mov     [rsp+148h+var_100], rcx
0x140014f09  mov     [rsp+148h+var_C0], rcx
0x140014f11  mov     [rsp+148h+var_B8], rdx
0x140014f19  mov     r9, [r8+0B8h]
0x140014f20  mov     rax, [r9+10h]
0x140014f24  xor     ebx, ebx
0x140014f26  test    rax, rax
0x140014f29  jz      short loc_140014F44
0x140014f2b  movzx   edi, word ptr [rax]
0x140014f2e  test    dil, 1
0x140014f32  jz      short loc_140014F3E
0x140014f34  mov     eax, 0C000000Dh
0x140014f39  jmp     loc_140015419
0x140014f3e  mov     rdx, [rax+8]
0x140014f42  jmp     short loc_140014F49
0x140014f44  mov     edi, ebx
0x140014f46  mov     rdx, rbx
0x140014f49  mov     ecx, [r9+18h]
0x140014f4d  mov     [rsp+148h+var_E4], ecx
0x140014f51  sub     ecx, 1
0x140014f54  jz      short loc_140014F8D
0x140014f56  sub     ecx, 1
0x140014f59  jz      short loc_140014F83
0x140014f5b  sub     ecx, 1
0x140014f5e  jz      short loc_140014F79
0x140014f60  cmp     ecx, 9
0x140014f63  jz      short loc_140014F6F
0x140014f65  mov     eax, 0C0000003h
0x140014f6a  jmp     loc_140015419
0x140014f6f  mov     dword ptr [rsp+148h+Size], 0Ch
0x140014f77  jmp     short loc_140014F95
0x140014f79  mov     dword ptr [rsp+148h+Size], 5Eh ; '^'
0x140014f81  jmp     short loc_140014F95
0x140014f83  mov     dword ptr [rsp+148h+Size], 44h ; 'D'
0x140014f8b  jmp     short loc_140014F95
0x140014f8d  mov     dword ptr [rsp+148h+Size], 40h ; '@'
0x140014f95  mov     eax, [r9+8]
0x140014f99  mov     [rsp+148h+var_E8], eax
0x140014f9d  mov     eax, [r9+20h]
0x140014fa1  mov     [rsp+148h+var_118], eax
0x140014fa5  mov     r15b, [r9+2]
0x140014fa9  mov     r12, [r9+30h]
0x140014fad  mov     rax, [r8+70h]
0x140014fb1  mov     [rsp+148h+var_D0], rax
0x140014fb6  mov     al, [r8+40h]
0x140014fba  mov     [rsp+148h+var_128], al
0x140014fbe  mov     r14, rbx
0x140014fc1  mov     esi, 2
0x140014fc6  cmp     [r13+10h], rbx
0x140014fca  jnz     loc_14001507E
0x140014fd0  mov     qword ptr [rsp+148h+SourceString.Length], rbx
0x140014fd5  test    di, di
0x140014fd8  jnz     short loc_140014FEB
0x140014fda  movzx   eax, si
0x140014fdd  lea     rcx, qword_140006080
0x140014fe4  mov     [rsp+148h+SourceString.Buffer], rcx
0x140014fe9  jmp     short loc_140014FF3
0x140014feb  movzx   eax, di
0x140014fee  mov     [rsp+148h+SourceString.Buffer], rdx
0x140014ff3  mov     [rsp+148h+SourceString.Length], ax
0x140014ff8  movzx   edx, ax
0x140014ffb  add     rdx, 10h
0x140014fff  mov     ecx, 101h
0x140015004  mov     r8d, 7146704Eh
0x14001500a  call    cs:__imp_ExAllocatePool2
0x140015011  nop     dword ptr [rax+rax+00h]
0x140015016  mov     r14, rax
0x140015019  test    rax, rax
0x14001501c  jnz     short loc_140015028
0x14001501e  mov     eax, 0C000009Ah
0x140015023  jmp     loc_140015419
0x140015028  mov     [rax], bx
0x14001502b  movzx   eax, [rsp+148h+SourceString.Length]
0x140015030  mov     [r14+2], ax
0x140015035  lea     rcx, [r14+10h]; void *
0x140015039  mov     [r14+8], rcx
0x14001503d  mov     eax, cs:NpCompatFlags
0x140015043  test    al, 1
0x140015045  jnz     short loc_140015065
0x140015047  cmp     bx, di
0x14001504a  jz      short loc_140015065
0x14001504c  xor     r8d, r8d; AllocateDestinationString
0x14001504f  lea     rdx, [rsp+148h+SourceString]; SourceString
0x140015054  mov     rcx, r14; DestinationString
0x140015057  call    cs:__imp_RtlUpcaseUnicodeString
0x14001505e  nop     dword ptr [rax+rax+00h]
0x140015063  jmp     short loc_14001507E
0x140015065  movzx   r8d, [rsp+148h+SourceString.Length]; Size
0x14001506b  mov     rdx, [rsp+148h+SourceString.Buffer]; Src
0x140015070  call    memmove
0x140015075  movzx   eax, [rsp+148h+SourceString.Length]
0x14001507a  mov     [r14], ax
0x14001507e  call    cs:__imp_KeEnterCriticalRegion
0x140015085  nop     dword ptr [rax+rax+00h]
0x14001508a  mov     rdi, [rsp+148h+var_100]
0x14001508f  lea     rcx, [rdi+0C0h]
0x140015096  xor     edx, edx
0x140015098  call    cs:__imp_ExAcquirePushLockSharedEx
0x14001509f  nop     dword ptr [rax+rax+00h]
0x1400150a4  lea     rcx, [r13+8]
0x1400150a8  xor     edx, edx
0x1400150aa  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400150b1  nop     dword ptr [rax+rax+00h]
0x1400150b6  mov     rax, [r12+20h]
0x1400150bb  test    al, 1
0x1400150bd  jnz     short loc_1400150CC
0x1400150bf  mov     rsi, r14
0x1400150c2  mov     edi, 0C000000Dh
0x1400150c7  jmp     loc_1400153C9
0x1400150cc  mov     al, r15b
0x1400150cf  and     al, 1
0x1400150d1  mov     cl, r15b
0x1400150d4  and     cl, sil
0x1400150d7  mov     [rsp+148h+var_127], cl
0x1400150db  mov     dl, [rsp+148h+var_128]
0x1400150df  mov     [rsp+148h+var_126], dl
0x1400150e3  mov     dword ptr [rsp+148h+Size+4], ebx
0x1400150e7  mov     dword ptr [rsp+148h+var_114+4], ebx
0x1400150eb  mov     r12d, ebx
0x1400150ee  mov     rcx, [r13+10h]
0x1400150f2  test    rcx, rcx
0x1400150f5  jnz     short loc_140015100
0x1400150f7  mov     rsi, rbx
0x1400150fa  mov     [r13+10h], r14
0x1400150fe  jmp     short loc_140015106
0x140015100  mov     rsi, r14
0x140015103  mov     r14, rcx
0x140015106  mov     [rsp+148h+var_C8], rsi
0x14001510e  test    al, al
0x140015110  jz      short loc_140015118
0x140015112  mov     [rsp+148h+var_118], ebx
0x140015116  jmp     short loc_140015126
0x140015118  test    r15b, 4
0x14001511c  jnz     short loc_140015126
0x14001511e  mov     eax, [r13+4]
0x140015122  mov     [rsp+148h+var_118], eax
0x140015126  lea     rax, [rdi+0C8h]
0x14001512d  mov     [rsp+148h+var_A8], rax
0x140015135  mov     r15, [rax]
0x140015138  mov     [rsp+148h+var_108], r15
0x14001513d  cmp     r15, rax
0x140015140  jz      loc_1400153BC
0x140015146  lea     rdi, [r15+18h]
0x14001514a  xor     r9d, r9d; UpcaseTable
0x14001514d  mov     r8b, 1; IgnoreCase
0x140015150  mov     rdx, rdi; Name
0x140015153  mov     rcx, r14; Expression
0x140015156  call    cs:__imp_FsRtlIsNameInExpression
0x14001515d  nop     dword ptr [rax+rax+00h]
0x140015162  mov     [rsp+148h+var_11C], al
0x140015166  test    al, al
0x140015168  jz      loc_14001538B
0x14001516e  mov     edx, dword ptr [rsp+148h+Size+4]
0x140015172  cmp     edx, [rsp+148h+var_118]
0x140015176  jb      loc_140015385
0x14001517c  mov     r8d, [rsp+148h+var_E8]
0x140015181  mov     ecx, r8d
0x140015184  sub     ecx, r12d
0x140015187  mov     [rsp+148h+var_D8], ecx
0x14001518b  mov     edx, dword ptr [rsp+148h+Size]
0x14001518f  test    r12d, r12d
0x140015192  jz      short loc_1400151A9
0x140015194  movzx   eax, word ptr [rdi]
0x140015197  add     eax, edx
0x140015199  cmp     eax, ecx
0x14001519b  ja      short loc_1400151A2
0x14001519d  cmp     r8d, r12d
0x1400151a0  jnb     short loc_1400151A9
0x1400151a2  mov     edi, ebx
0x1400151a4  jmp     loc_1400153C9
0x1400151a9  movzx   eax, word ptr [rdi]
0x1400151ac  mov     dword ptr [rsp+148h+var_114], eax
0x1400151b0  lea     r8d, [rax+rdx]
0x1400151b4  mov     [rsp+148h+var_DC], r8d
0x1400151b9  cmp     ecx, r8d
0x1400151bc  jnb     short loc_1400151C9
0x1400151be  mov     eax, ecx
0x1400151c0  sub     eax, edx
0x1400151c2  mov     dword ptr [rsp+148h+var_114], eax
0x1400151c6  cmp     ecx, r8d
0x1400151c9  sbb     edi, edi
0x1400151cb  and     edi, 80000005h
0x1400151d1  add     eax, edx
0x1400151d3  mov     [rsp+148h+var_E0], eax
0x1400151d7  mov     r8d, edx; Size
0x1400151da  mov     r15d, r12d
0x1400151dd  add     r15, [rsp+148h+var_D0]
0x1400151e2  xor     edx, edx; Val
0x1400151e4  mov     rcx, r15; void *
0x1400151e7  cmp     [rsp+148h+var_128], bl
0x1400151eb  jz      short loc_1400151F4
0x1400151ed  call    RtlSetUserMemory
0x1400151f2  jmp     short loc_1400151F9
0x1400151f4  call    RtlSetVolatileMemory
0x1400151f9  mov     ecx, [rsp+148h+var_E4]
0x1400151fd  sub     ecx, 1
0x140015200  jz      short loc_140015233
0x140015202  sub     ecx, 1
0x140015205  jz      short loc_140015233
0x140015207  cmp     ecx, 1
0x14001520a  jz      short loc_140015233
0x14001520c  mov     rax, [rsp+148h+var_108]
0x140015211  movzx   eax, word ptr [rax+18h]
0x140015215  lea     rcx, [r15+8]
0x140015219  cmp     [rsp+148h+var_128], 0
0x14001521e  jz      short loc_14001522C
0x140015220  mov     edx, eax
0x140015222  call    RtlWriteULongToUser
0x140015227  jmp     loc_1400152CE
0x14001522c  mov     [rcx], eax
0x14001522e  jmp     loc_1400152CE
0x140015233  xor     edx, edx; Val
0x140015235  lea     r8d, [rdx+48h]; Size
0x140015239  lea     rcx, [rsp+148h+Src]; void *
0x140015241  call    memset
0x140015246  mov     rcx, [rsp+148h+var_108]
0x14001524b  movzx   eax, word ptr [rcx-88h]
0x140015252  mov     edx, 202h
0x140015257  cmp     ax, dx
0x14001525a  jnz     short loc_140015274
0x14001525c  mov     eax, [rcx-10h]
0x14001525f  mov     [rsp+148h+var_70], rax
0x140015267  mov     eax, [rcx+74h]
0x14001526a  mov     [rsp+148h+var_68], rax
0x140015272  jmp     short loc_140015295
0x140015274  mov     edx, 207h
0x140015279  cmp     ax, dx
0x14001527c  jnz     short loc_1400152AB
0x14001527e  mov     eax, [rcx-10h]
0x140015281  mov     [rsp+148h+var_70], rax
0x140015289  mov     [rsp+148h+var_68], 1
0x140015295  mov     [rsp+148h+var_60], 80h
0x1400152a0  movzx   eax, word ptr [rcx+18h]
0x1400152a4  mov     [rsp+148h+var_5C], eax
0x1400152ab  mov     r8d, 48h ; 'H'; Size
0x1400152b1  lea     rdx, [rsp+148h+Src]; Src
0x1400152b9  mov     rcx, r15; void *
0x1400152bc  cmp     [rsp+148h+var_128], bl
0x1400152c0  jz      short loc_1400152C9
0x1400152c2  call    RtlCopyToUser
0x1400152c7  jmp     short loc_1400152CE
0x1400152c9  call    RtlCopyVolatileMemory
0x1400152ce  mov     r8d, dword ptr [rsp+148h+var_114]; Size
0x1400152d3  mov     r15, [rsp+148h+var_108]
0x1400152d8  mov     rdx, [r15+20h]; Src
0x1400152dc  mov     ecx, dword ptr [rsp+148h+Size]
0x1400152e0  add     ecx, r12d
0x1400152e3  add     rcx, [rsp+148h+var_D0]; void *
0x1400152e8  cmp     [rsp+148h+var_128], bl
0x1400152ec  jz      short loc_1400152F5
0x1400152ee  call    RtlCopyToUser
0x1400152f3  jmp     short loc_1400152FA
0x1400152f5  call    RtlCopyVolatileMemory
0x1400152fa  mov     edx, r12d
0x1400152fd  mov     eax, dword ptr [rsp+148h+var_114+4]
0x140015301  sub     edx, eax
0x140015303  mov     rcx, [rsp+148h+var_D0]
0x140015308  add     rcx, rax
0x14001530b  cmp     [rsp+148h+var_128], bl
0x14001530f  jz      short loc_140015318
0x140015311  call    RtlWriteULongToUser
0x140015316  jmp     short loc_14001531A
0x140015318  mov     [rcx], edx
0x14001531a  mov     edx, [rsp+148h+var_E0]
0x14001531e  lea     ecx, [rdx+r12]
0x140015322  mov     rax, [rsp+148h+var_B0]
0x14001532a  mov     [rax+38h], rcx
0x14001532e  mov     eax, [rsp+148h+var_DC]
0x140015332  cmp     eax, [rsp+148h+var_D8]
0x140015336  ja      loc_1400153C9
0x14001533c  mov     eax, dword ptr [rsp+148h+Size+4]
0x140015340  inc     eax
0x140015342  mov     [r13+4], eax
0x140015346  cmp     [rsp+148h+var_127], bl
0x14001534a  jnz     loc_1400151A2
0x140015350  mov     dword ptr [rsp+148h+var_114+4], r12d
0x140015355  lea     eax, [rdx+7]
0x140015358  and     eax, 0FFFFFFF8h
0x14001535b  add     r12d, eax
0x14001535e  mov     edx, dword ptr [rsp+148h+Size+4]
0x140015362  jmp     short loc_140015385
0x140015364  mov     edi, eax
0x140015366  mov     rsi, [rsp+148h+var_C8]
0x14001536e  mov     rax, [rsp+148h+var_C0]
0x140015376  mov     [rsp+148h+var_100], rax
0x14001537b  mov     r13, [rsp+148h+var_B8]
0x140015383  jmp     short loc_1400153C9
  ... truncated ...
```
