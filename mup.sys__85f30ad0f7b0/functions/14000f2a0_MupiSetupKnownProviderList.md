# MupiSetupKnownProviderList

- ea: `0x14000f2a0`
- end: `0x14000f63d`
- name: `MupiSetupKnownProviderList`
- size: `925`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x140012560`
- `0x140013610`

## callees

- `0x140003b80`
- `0x140003c3c`
- `0x140003c54`
- `0x140003c98`
- `0x14000f2a0`
- `0x14000f644`
- `0x140012930`
- `0x1400129cc`
- `0x14001379c`
- `0x1400138d4`
- `0x140019860`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000f3d5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f3e8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f417`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f547`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f3d5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f3e8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f417`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f547`
- `ntoskrnl!ExAllocatePool2` at `0x14000f4c7`
- `ntoskrnl!ExAllocatePool2` at `0x14000f4c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f50c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f522`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f50c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f522`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000f4ec`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000f4ec`
- `ntoskrnl!wcschr` at `0x14000f30c`
- `ntoskrnl!wcschr` at `0x14000f30c`

## pseudocode

```c
void __fastcall MupiSetupKnownProviderList(PCWSTR SourceString, char a2)
{
  __int64 v2; // rax
  PCWSTR v3; // rbx
  unsigned int v4; // r13d
  char v5; // r15
  wchar_t *v6; // rax
  wchar_t *v7; // r12
  __int64 v8; // rax
  _WORD *i; // rcx
  int v10; // eax
  unsigned int v11; // edi
  __int64 ProviderInfoFromRegistry; // rax
  WCHAR *v13; // r14
  __int64 v14; // rsi
  __int64 ProviderByName; // rax
  __int64 v16; // rbx
  __int64 v17; // rax
  _QWORD *v18; // rax
  __int64 v19; // rdx
  _QWORD *v20; // rcx
  __int64 Pool2; // rax
  __int64 v22; // rax
  __int64 j; // rax
  __int64 NextKnownPriorityProvider; // rbx
  __int64 v25; // r11
  __int64 v26; // rdx
  __int64 *v27; // rbx
  __int64 **v28; // rax
  unsigned int v29; // [rsp+30h] [rbp-49h] BYREF
  struct _UNICODE_STRING v30; // [rsp+38h] [rbp-41h] BYREF
  UNICODE_STRING SourceStringa; // [rsp+48h] [rbp-31h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-21h] BYREF
  __int128 v33; // [rsp+88h] [rbp+Fh]
  unsigned int v35; // [rsp+F0h] [rbp+77h] BYREF
  char v36; // [rsp+F8h] [rbp+7Fh]

  v2 = -1;
  v3 = SourceString;
  do
    ++v2;
  while ( SourceString[v2] );
  if ( v2 )
  {
    v4 = 1;
    v36 = 0;
    v29 = 0;
    LOBYTE(v35) = 0;
    while ( 1 )
    {
      v5 = 0;
      while ( *v3 == 32 || *v3 == 9 )
        ++v3;
      v6 = wcschr(v3, 0x2Cu);
      v7 = v6;
      if ( v6 )
        *v6 = 0;
      else
        LOBYTE(v35) = 1;
      v8 = -1;
      do
        ++v8;
      while ( v3[v8] );
      for ( i = &v3[v8 - 1]; i > v3 && (*i == 32 || *i == 9); --i )
        *i = 0;
      v10 = MupiReadNetworkProviderOrderFromRegistry(v3, &v29);
      if ( v10 < 0 )
      {
        if ( v10 == -1073741772 )
        {
          v5 = 1;
          v29 = v4;
          v36 = 1;
          v11 = v4;
        }
        else
        {
          v11 = 0x7FFFFFFF;
          v29 = 0x7FFFFFFF;
        }
      }
      else
      {
        v11 = v29;
        if ( v29 > v4 )
          v4 = v29;
      }
      ProviderInfoFromRegistry = MupiReadProviderInfoFromRegistry((__int64)&DestinationString, v3);
      v13 = *(WCHAR **)ProviderInfoFromRegistry;
      v33 = *(_OWORD *)(ProviderInfoFromRegistry + 16);
      if ( v13 )
      {
        v14 = *(_QWORD *)(ProviderInfoFromRegistry + 8);
        SourceStringa = 0;
        DestinationString = 0;
        v30 = 0;
        RtlInitUnicodeString(&DestinationString, v13);
        RtlInitUnicodeString(&SourceStringa, v3);
        if ( v14 )
        {
          v30.Buffer = (PWSTR)(v14 + *(unsigned int *)(v14 + 8));
          v30.Length = *(_WORD *)(v14 + 12);
          v30.MaximumLength = v30.Length;
        }
        else
        {
          RtlInitUnicodeString(&v30, 0);
        }
        ProviderByName = MupiFindProviderByName(&DestinationString);
        v16 = ProviderByName;
        if ( ProviderByName )
        {
          if ( a2 && *(_DWORD *)(ProviderByName + 60) == 0x7FFFFFFF )
          {
            v18 = (_QWORD *)(ProviderByName + 8);
            v19 = *v18;
            if ( *(_QWORD **)(*v18 + 8LL) != v18 || (v20 = (_QWORD *)v18[1], (_QWORD *)*v20 != v18) )
LABEL_61:
              __fastfail(3u);
            *v20 = v19;
            *(_QWORD *)(v19 + 8) = v20;
            --dword_14000A7E8;
            if ( !*(_QWORD *)(v16 + 48) )
            {
              Pool2 = ExAllocatePool2(258, SourceStringa.MaximumLength, 1313895757);
              *(_QWORD *)(v16 + 48) = Pool2;
              if ( Pool2 )
              {
                *(_WORD *)(v16 + 42) = SourceStringa.MaximumLength;
                RtlCopyUnicodeString((PUNICODE_STRING)(v16 + 40), &SourceStringa);
              }
            }
            *(_DWORD *)(v16 + 60) = v11;
            *(_BYTE *)(v16 + 64) = v5;
            MupiAddProviderToList(v16);
          }
        }
        else
        {
          v17 = MupiAddKnownProvider(&DestinationString, &SourceStringa, &v30, v11);
          if ( v17 )
            *(_BYTE *)(v17 + 64) = v5;
          if ( v14 )
            *(_OWORD *)(v17 + 88) = v33;
        }
        ExFreePoolWithTag(v13, 0);
        if ( v14 )
          ExFreePoolWithTag((PVOID)v14, 0);
      }
      else
      {
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString, v3);
        v22 = MupiAddKnownProvider(&DestinationString, &DestinationString, 0, v11);
        if ( v22 )
        {
          *(_DWORD *)(v22 + 148) |= 0x40u;
          *(_BYTE *)(v22 + 64) = v5;
        }
      }
      if ( (_BYTE)v35 )
        break;
      v3 = v7 + 1;
    }
    if ( v36 )
    {
      for ( j = MupiGetFirstUncProvider(&qword_14000A768);
            ;
            j = MupiGetNextUncProvider(&qword_14000A768, NextKnownPriorityProvider) )
      {
        NextKnownPriorityProvider = j;
        if ( !j )
          break;
        if ( *(_BYTE *)(j + 64) )
        {
          v35 = 0;
          NextKnownPriorityProvider = MupiGetNextKnownPriorityProvider(j, &v35);
          MupiAssignProvidersPriorityValue(v25, NextKnownPriorityProvider, v35);
          if ( !NextKnownPriorityProvider )
            break;
        }
      }
    }
    v26 = qword_14000A768;
    if ( (__int64 *)qword_14000A768 != &qword_14000A768 )
    {
      do
      {
        v27 = *(__int64 **)v26;
        if ( (*(_DWORD *)(v26 - 8 + 148) & 0x40) != 0 )
        {
          if ( v27[1] != v26 )
            goto LABEL_61;
          v28 = *(__int64 ***)(v26 + 8);
          if ( *v28 != (__int64 *)v26 )
            goto LABEL_61;
          *v28 = v27;
          v27[1] = (__int64)v28;
          --dword_14000A7E8;
          MupiFreeProvider((PVOID)(v26 - 8));
        }
        v26 = (__int64)v27;
      }
      while ( v27 != &qword_14000A768 );
    }
  }
}

```

## disassembly

```asm
0x14000f2a0  mov     [rsp-8+arg_0], rbx
0x14000f2a5  mov     [rsp-8+arg_8], dl
0x14000f2a9  push    rbp
0x14000f2aa  push    rsi
0x14000f2ab  push    rdi
0x14000f2ac  push    r12
0x14000f2ae  push    r13
0x14000f2b0  push    r14
0x14000f2b2  push    r15
0x14000f2b4  lea     rbp, [rsp-27h]
0x14000f2b9  sub     rsp, 0A0h
0x14000f2c0  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000f2c4  mov     rbx, rcx
0x14000f2c7  xor     esi, esi
0x14000f2c9  inc     rax
0x14000f2cc  cmp     [rcx+rax*2], si
0x14000f2d0  jnz     short loc_14000F2C9
0x14000f2d2  test    rax, rax
0x14000f2d5  jz      loc_14000F61A
0x14000f2db  mov     r13d, 1
0x14000f2e1  mov     [rbp+57h+arg_18], sil
0x14000f2e5  mov     [rbp+57h+var_A0], esi
0x14000f2e8  mov     byte ptr [rbp+57h+arg_10], sil
0x14000f2ec  mov     r15b, sil
0x14000f2ef  movzx   eax, word ptr [rbx]
0x14000f2f2  cmp     ax, 20h ; ' '
0x14000f2f6  jz      short loc_14000F2FE
0x14000f2f8  cmp     ax, 9
0x14000f2fc  jnz     short loc_14000F304
0x14000f2fe  add     rbx, 2
0x14000f302  jmp     short loc_14000F2EF
0x14000f304  mov     edx, 2Ch ; ','; Ch
0x14000f309  mov     rcx, rbx; Str
0x14000f30c  call    cs:__imp_wcschr
0x14000f313  nop     dword ptr [rax+rax+00h]
0x14000f318  mov     r12, rax
0x14000f31b  test    rax, rax
0x14000f31e  jnz     short loc_14000F326
0x14000f320  mov     byte ptr [rbp+57h+arg_10], 1
0x14000f324  jmp     short loc_14000F329
0x14000f326  mov     [rax], si
0x14000f329  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000f32d  inc     rax
0x14000f330  cmp     [rbx+rax*2], si
0x14000f334  jnz     short loc_14000F32D
0x14000f336  lea     rcx, [rax-1]
0x14000f33a  lea     rcx, [rbx+rcx*2]
0x14000f33e  jmp     short loc_14000F356
0x14000f340  movzx   eax, word ptr [rcx]
0x14000f343  cmp     ax, 20h ; ' '
0x14000f347  jz      short loc_14000F34F
0x14000f349  cmp     ax, 9
0x14000f34d  jnz     short loc_14000F35B
0x14000f34f  mov     [rcx], si
0x14000f352  sub     rcx, 2
0x14000f356  cmp     rcx, rbx
0x14000f359  ja      short loc_14000F340
0x14000f35b  lea     rdx, [rbp+57h+var_A0]
0x14000f35f  mov     rcx, rbx; SourceString
0x14000f362  call    MupiReadNetworkProviderOrderFromRegistry
0x14000f367  test    eax, eax
0x14000f369  js      short loc_14000F378
0x14000f36b  mov     edi, [rbp+57h+var_A0]
0x14000f36e  cmp     edi, r13d
0x14000f371  jbe     short loc_14000F397
0x14000f373  mov     r13d, edi
0x14000f376  jmp     short loc_14000F397
0x14000f378  cmp     eax, 0C0000034h
0x14000f37d  jnz     short loc_14000F38F
0x14000f37f  mov     r15b, 1
0x14000f382  mov     [rbp+57h+var_A0], r13d
0x14000f386  mov     [rbp+57h+arg_18], r15b
0x14000f38a  mov     edi, r13d
0x14000f38d  jmp     short loc_14000F397
0x14000f38f  mov     edi, 7FFFFFFFh
0x14000f394  mov     [rbp+57h+var_A0], edi
0x14000f397  mov     rdx, rbx
0x14000f39a  lea     rcx, [rbp+57h+DestinationString]
0x14000f39e  call    MupiReadProviderInfoFromRegistry
0x14000f3a3  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000f3a7  movups  xmm0, xmmword ptr [rax+10h]
0x14000f3ab  mov     r14, [rax]
0x14000f3ae  movdqu  [rbp+57h+var_48], xmm0
0x14000f3b3  xorps   xmm0, xmm0
0x14000f3b6  test    r14, r14
0x14000f3b9  jz      loc_14000F540
0x14000f3bf  mov     rsi, [rax+8]
0x14000f3c3  xorps   xmm1, xmm1
0x14000f3c6  mov     rdx, r14; SourceString
0x14000f3c9  movups  xmmword ptr [rbp+57h+SourceString.Length], xmm1
0x14000f3cd  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14000f3d1  movups  xmmword ptr [rbp+57h+var_98.Length], xmm0
0x14000f3d5  call    cs:__imp_RtlInitUnicodeString
0x14000f3dc  nop     dword ptr [rax+rax+00h]
0x14000f3e1  mov     rdx, rbx; SourceString
0x14000f3e4  lea     rcx, [rbp+57h+SourceString]; DestinationString
0x14000f3e8  call    cs:__imp_RtlInitUnicodeString
0x14000f3ef  nop     dword ptr [rax+rax+00h]
0x14000f3f4  test    rsi, rsi
0x14000f3f7  jz      short loc_14000F411
0x14000f3f9  mov     eax, [rsi+8]
0x14000f3fc  add     rax, rsi
0x14000f3ff  mov     [rbp+57h+var_98.Buffer], rax
0x14000f403  movzx   eax, word ptr [rsi+0Ch]
0x14000f407  mov     [rbp+57h+var_98.Length], ax
0x14000f40b  mov     [rbp+57h+var_98.MaximumLength], ax
0x14000f40f  jmp     short loc_14000F423
0x14000f411  xor     edx, edx; SourceString
0x14000f413  lea     rcx, [rbp+57h+var_98]; DestinationString
0x14000f417  call    cs:__imp_RtlInitUnicodeString
0x14000f41e  nop     dword ptr [rax+rax+00h]
0x14000f423  lea     rcx, [rbp+57h+DestinationString]; String1
0x14000f427  call    MupiFindProviderByName
0x14000f42c  mov     rbx, rax
0x14000f42f  test    rax, rax
0x14000f432  jnz     short loc_14000F46F
0x14000f434  mov     r9d, edi
0x14000f437  lea     r8, [rbp+57h+var_98]
0x14000f43b  lea     rdx, [rbp+57h+SourceString]
0x14000f43f  lea     rcx, [rbp+57h+DestinationString]
0x14000f443  call    MupiAddKnownProvider
0x14000f448  test    rax, rax
0x14000f44b  jz      short loc_14000F451
0x14000f44d  mov     [rax+40h], r15b
0x14000f451  test    rsi, rsi
0x14000f454  jz      loc_14000F507
0x14000f45a  mov     rcx, qword ptr [rbp+57h+var_48]
0x14000f45e  mov     [rax+58h], rcx
0x14000f462  mov     rcx, qword ptr [rbp+57h+var_48+8]
0x14000f466  mov     [rax+60h], rcx
0x14000f46a  jmp     loc_14000F507
0x14000f46f  cmp     [rbp+57h+arg_8], 0
0x14000f473  jz      loc_14000F507
0x14000f479  cmp     dword ptr [rax+3Ch], 7FFFFFFFh
0x14000f480  jnz     loc_14000F507
0x14000f486  add     rax, 8
0x14000f48a  mov     rdx, [rax]
0x14000f48d  cmp     [rdx+8], rax
0x14000f491  jnz     loc_14000F636
0x14000f497  mov     rcx, [rax+8]
0x14000f49b  cmp     [rcx], rax
0x14000f49e  jnz     loc_14000F636
0x14000f4a4  mov     [rcx], rdx
0x14000f4a7  mov     [rdx+8], rcx
0x14000f4ab  dec     cs:dword_14000A7E8
0x14000f4b1  cmp     qword ptr [rbx+30h], 0
0x14000f4b6  jnz     short loc_14000F4F8
0x14000f4b8  movzx   edx, [rbp+57h+SourceString.MaximumLength]
0x14000f4bc  mov     ecx, 102h
0x14000f4c1  mov     r8d, 4E50754Dh
0x14000f4c7  call    cs:__imp_ExAllocatePool2
0x14000f4ce  nop     dword ptr [rax+rax+00h]
0x14000f4d3  mov     [rbx+30h], rax
0x14000f4d7  test    rax, rax
0x14000f4da  jz      short loc_14000F4F8
0x14000f4dc  movzx   eax, [rbp+57h+SourceString.MaximumLength]
0x14000f4e0  lea     rcx, [rbx+28h]; DestinationString
0x14000f4e4  lea     rdx, [rbp+57h+SourceString]; SourceString
0x14000f4e8  mov     [rbx+2Ah], ax
0x14000f4ec  call    cs:__imp_RtlCopyUnicodeString
0x14000f4f3  nop     dword ptr [rax+rax+00h]
0x14000f4f8  mov     rcx, rbx
0x14000f4fb  mov     [rbx+3Ch], edi
0x14000f4fe  mov     [rbx+40h], r15b
0x14000f502  call    MupiAddProviderToList
0x14000f507  xor     edx, edx; Tag
0x14000f509  mov     rcx, r14; P
0x14000f50c  call    cs:__imp_ExFreePoolWithTag
0x14000f513  nop     dword ptr [rax+rax+00h]
0x14000f518  test    rsi, rsi
0x14000f51b  jz      short loc_14000F52E
0x14000f51d  xor     edx, edx; Tag
0x14000f51f  mov     rcx, rsi; P
0x14000f522  call    cs:__imp_ExFreePoolWithTag
0x14000f529  nop     dword ptr [rax+rax+00h]
0x14000f52e  xor     esi, esi
0x14000f530  cmp     byte ptr [rbp+57h+arg_10], sil
0x14000f534  jnz     short loc_14000F578
0x14000f536  lea     rbx, [r12+2]
0x14000f53b  jmp     loc_14000F2EC
0x14000f540  mov     rdx, rbx; SourceString
0x14000f543  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14000f547  call    cs:__imp_RtlInitUnicodeString
0x14000f54e  nop     dword ptr [rax+rax+00h]
0x14000f553  mov     r9d, edi
0x14000f556  lea     rdx, [rbp+57h+DestinationString]
0x14000f55a  xor     r8d, r8d
0x14000f55d  lea     rcx, [rbp+57h+DestinationString]
0x14000f561  call    MupiAddKnownProvider
0x14000f566  test    rax, rax
0x14000f569  jz      short loc_14000F530
0x14000f56b  or      dword ptr [rax+94h], 40h
0x14000f572  mov     [rax+40h], r15b
0x14000f576  jmp     short loc_14000F530
0x14000f578  lea     rdi, qword_14000A768
0x14000f57f  cmp     [rbp+57h+arg_18], sil
0x14000f583  jz      short loc_14000F5D4
0x14000f585  mov     rcx, rdi
0x14000f588  mov     r11, rsi
0x14000f58b  call    MupiGetFirstUncProvider
0x14000f590  jmp     short loc_14000F5CC
0x14000f592  cmp     [rbx+40h], sil
0x14000f596  jz      short loc_14000F5BE
0x14000f598  lea     rdx, [rbp+57h+arg_10]
0x14000f59c  mov     [rbp+57h+arg_10], esi
0x14000f59f  mov     rcx, rbx
0x14000f5a2  call    MupiGetNextKnownPriorityProvider
0x14000f5a7  mov     r8d, [rbp+57h+arg_10]
0x14000f5ab  mov     rdx, rax
0x14000f5ae  mov     rcx, r11
0x14000f5b1  mov     rbx, rax
0x14000f5b4  call    MupiAssignProvidersPriorityValue
0x14000f5b9  test    rbx, rbx
0x14000f5bc  jz      short loc_14000F5D4
0x14000f5be  mov     rdx, rbx
0x14000f5c1  mov     rcx, rdi
0x14000f5c4  mov     r11, rbx
0x14000f5c7  call    MupiGetNextUncProvider
0x14000f5cc  mov     rbx, rax
0x14000f5cf  test    rax, rax
0x14000f5d2  jnz     short loc_14000F592
0x14000f5d4  mov     rdx, cs:qword_14000A768
0x14000f5db  cmp     rdx, rdi
0x14000f5de  jz      short loc_14000F61A
0x14000f5e0  mov     rbx, [rdx]
0x14000f5e3  lea     rcx, [rdx-8]; P
0x14000f5e7  mov     eax, [rcx+94h]
0x14000f5ed  test    al, 40h
0x14000f5ef  jz      short loc_14000F612
0x14000f5f1  cmp     [rbx+8], rdx
0x14000f5f5  jnz     short loc_14000F636
0x14000f5f7  mov     rax, [rdx+8]
0x14000f5fb  cmp     [rax], rdx
0x14000f5fe  jnz     short loc_14000F636
0x14000f600  mov     [rax], rbx
0x14000f603  mov     [rbx+8], rax
0x14000f607  dec     cs:dword_14000A7E8
0x14000f60d  call    MupiFreeProvider
0x14000f612  mov     rdx, rbx
0x14000f615  cmp     rbx, rdi
0x14000f618  jnz     short loc_14000F5E0
0x14000f61a  mov     rbx, [rsp+0D0h+arg_0]
0x14000f622  add     rsp, 0A0h
0x14000f629  pop     r15
0x14000f62b  pop     r14
0x14000f62d  pop     r13
0x14000f62f  pop     r12
0x14000f631  pop     rdi
0x14000f632  pop     rsi
0x14000f633  pop     rbp
0x14000f634  retn
0x14000f636  mov     ecx, 3
0x14000f63b  int     29h; Win8: RtlFailFast(ecx)
```
