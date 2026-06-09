# QueryPointsFromSymbolicLinkName

- ea: `0x140017760`
- end: `0x140017a14`
- name: `QueryPointsFromSymbolicLinkName`
- size: `692`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1400168b0`

## callees

- `0x140001ae0`
- `0x140002f80`
- `0x1400144a0`
- `0x140017760`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x1400177b8`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400177b8`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140017840`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140017881`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140017840`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140017881`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400177d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400177d7`

## pseudocode

```c
__int64 __fastcall QueryPointsFromSymbolicLinkName(__int64 a1, UNICODE_STRING *a2, _QWORD *a3)
{
  const UNICODE_STRING **v4; // rsi
  int v6; // eax
  __int64 v7; // r8
  const UNICODE_STRING *v8; // rdi
  unsigned __int16 v9; // bp
  const UNICODE_STRING *j; // rbx
  __int64 v11; // r8
  __int64 *i; // rdi
  __int64 v14; // rsi
  unsigned int v15; // edx
  __int64 v16; // rcx
  __int64 v17; // rax
  size_t v18; // rdx
  UNICODE_STRING String1; // [rsp+20h] [rbp-38h] BYREF

  v4 = (const UNICODE_STRING **)(a1 + 16);
  String1 = 0;
  v6 = QueryDeviceName(a2, &String1);
  v8 = *v4;
  v9 = 0;
  if ( v6 < 0 )
  {
    j = *v4;
LABEL_16:
    if ( j == (const UNICODE_STRING *)v4 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 204, v7, 3221225524LL);
      }
      return 3221225524LL;
    }
    else
    {
      for ( i = *(__int64 **)&j[1].Length; ; i = (__int64 *)*i )
      {
        if ( i == (__int64 *)&j[1] )
        {
          j = *(const UNICODE_STRING **)&j->Length;
          goto LABEL_16;
        }
        if ( !i )
          return 3221226021LL;
        if ( RtlEqualUnicodeString(a2, (PCUNICODE_STRING)(i + 3), 1u) )
          break;
      }
LABEL_23:
      if ( !j )
        return 3221226021LL;
      v14 = a3[3];
      v15 = *((unsigned __int16 *)i + 12) + 32 + **(unsigned __int16 **)&j[6].Length + j[5].Length;
      v16 = a3[23];
      *(_DWORD *)v14 = v15;
      *(_DWORD *)(v14 + 4) = 1;
      a3[7] = v15;
      if ( v15 <= *(_DWORD *)(v16 + 8) )
      {
        v17 = a3[3];
        *(_OWORD *)(v17 + 8) = 0;
        *(_QWORD *)(v17 + 24) = 0;
        *(_DWORD *)(v14 + 8) = 32;
        v18 = *((unsigned __int16 *)i + 12);
        *(_WORD *)(v14 + 12) = v18;
        if ( *((_BYTE *)i + 16) )
        {
          *(_DWORD *)(v14 + 16) = v18 + 32;
          v9 = **(_WORD **)&j[6].Length;
        }
        else
        {
          *(_DWORD *)(v14 + 16) = 0;
        }
        *(_WORD *)(v14 + 20) = v9;
        *(_DWORD *)(v14 + 24) = v9 + v18 + 32;
        *(_WORD *)(v14 + 28) = j[5].Length;
        memmove((void *)(v14 + 32), (const void *)i[4], v18);
        if ( *((_BYTE *)i + 16) )
          memmove(
            (void *)(v14 + *(unsigned int *)(v14 + 16)),
            (const void *)(*(_QWORD *)&j[6].Length + 2LL),
            *(unsigned __int16 *)(v14 + 20));
        memmove((void *)(v14 + *(unsigned int *)(v14 + 24)), j[5].Buffer, *(unsigned __int16 *)(v14 + 28));
        return 0;
      }
      else
      {
        a3[7] = 32;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 205, v7, 2147483653LL);
        }
        return 2147483653LL;
      }
    }
  }
  else
  {
    for ( j = 0; v8 != (const UNICODE_STRING *)v4; v8 = *(const UNICODE_STRING **)&v8->Length )
    {
      j = v8;
      if ( !RtlCompareUnicodeString(&String1, v8 + 5, 1u) )
        break;
    }
    ExFreePoolWithTag(String1.Buffer, 0);
    if ( v8 == (const UNICODE_STRING *)v4 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 203, v11, 3221225485LL);
    }
    else
    {
      for ( i = *(__int64 **)&j[1].Length; i != (__int64 *)&j[1]; i = (__int64 *)*i )
      {
        if ( !i )
          return 3221226021LL;
        if ( RtlEqualUnicodeString(a2, (PCUNICODE_STRING)(i + 3), 1u) )
          goto LABEL_23;
      }
    }
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x140017760  mov     [rsp+arg_0], rbx
0x140017765  mov     [rsp+arg_8], rbp
0x14001776a  push    rsi
0x14001776b  push    rdi
0x14001776c  push    r12
0x14001776e  push    r14
0x140017770  push    r15
0x140017772  sub     rsp, 30h
0x140017776  mov     r15, rdx
0x140017779  lea     rsi, [rcx+10h]
0x14001777d  xorps   xmm0, xmm0
0x140017780  lea     rdx, [rsp+58h+String1]; StringOut
0x140017785  mov     rcx, r15; ObjectName
0x140017788  mov     r14, r8
0x14001778b  movups  xmmword ptr [rsp+58h+String1.Length], xmm0
0x140017790  call    QueryDeviceName
0x140017795  mov     rdi, [rsi]
0x140017798  xor     ebp, ebp
0x14001779a  test    eax, eax
0x14001779c  js      loc_140017855
0x1400177a2  mov     ebx, ebp
0x1400177a4  cmp     rdi, rsi
0x1400177a7  jz      short loc_1400177D0
0x1400177a9  lea     rdx, [rdi+50h]; String2
0x1400177ad  mov     r8b, 1; CaseInSensitive
0x1400177b0  lea     rcx, [rsp+58h+String1]; String1
0x1400177b5  mov     rbx, rdi
0x1400177b8  call    cs:__imp_RtlCompareUnicodeString
0x1400177bf  nop     dword ptr [rax+rax+00h]
0x1400177c4  test    eax, eax
0x1400177c6  jz      short loc_1400177D0
0x1400177c8  mov     rdi, [rdi]
0x1400177cb  cmp     rdi, rsi
0x1400177ce  jnz     short loc_1400177A9
0x1400177d0  mov     rcx, [rsp+58h+String1.Buffer]; P
0x1400177d5  xor     edx, edx; Tag
0x1400177d7  call    cs:__imp_ExFreePoolWithTag
0x1400177de  nop     dword ptr [rax+rax+00h]
0x1400177e3  cmp     rdi, rsi
0x1400177e6  jnz     short loc_140017820
0x1400177e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400177ef  lea     rax, WPP_GLOBAL_Control
0x1400177f6  cmp     rcx, rax
0x1400177f9  jz      short loc_140017816
0x1400177fb  mov     eax, [rcx+2Ch]
0x1400177fe  test    al, 1
0x140017800  jz      short loc_140017816
0x140017802  mov     rcx, [rcx+18h]
0x140017806  mov     edx, 0CBh
0x14001780b  mov     r9d, 0C000000Dh
0x140017811  call    WPP_SF_L
0x140017816  mov     eax, 0C000000Dh
0x14001781b  jmp     loc_1400179FC
0x140017820  mov     rdi, [rbx+10h]
0x140017824  lea     rsi, [rbx+10h]
0x140017828  cmp     rdi, rsi
0x14001782b  jz      short loc_140017816
0x14001782d  test    rdi, rdi
0x140017830  jz      loc_1400179BC
0x140017836  lea     rdx, [rdi+18h]; String2
0x14001783a  mov     r8b, 1; CaseInSensitive
0x14001783d  mov     rcx, r15; String1
0x140017840  call    cs:__imp_RtlEqualUnicodeString
0x140017847  nop     dword ptr [rax+rax+00h]
0x14001784c  test    al, al
0x14001784e  jnz     short loc_14001789B
0x140017850  mov     rdi, [rdi]
0x140017853  jmp     short loc_140017828
0x140017855  mov     rbx, rdi
0x140017858  cmp     rbx, rsi
0x14001785b  jz      loc_1400179C3
0x140017861  mov     rdi, [rbx+10h]
0x140017865  lea     r12, [rbx+10h]
0x140017869  cmp     rdi, r12
0x14001786c  jz      short loc_140017896
0x14001786e  test    rdi, rdi
0x140017871  jz      loc_1400179BC
0x140017877  lea     rdx, [rdi+18h]; String2
0x14001787b  mov     r8b, 1; CaseInSensitive
0x14001787e  mov     rcx, r15; String1
0x140017881  call    cs:__imp_RtlEqualUnicodeString
0x140017888  nop     dword ptr [rax+rax+00h]
0x14001788d  test    al, al
0x14001788f  jnz     short loc_14001789B
0x140017891  mov     rdi, [rdi]
0x140017894  jmp     short loc_140017869
0x140017896  mov     rbx, [rbx]
0x140017899  jmp     short loc_140017858
0x14001789b  test    rbx, rbx
0x14001789e  jz      loc_1400179BC
0x1400178a4  test    rdi, rdi
0x1400178a7  jz      loc_1400179BC
0x1400178ad  mov     rax, [rbx+60h]
0x1400178b1  movzx   edx, word ptr [rbx+50h]
0x1400178b5  mov     rsi, [r14+18h]
0x1400178b9  movzx   ecx, word ptr [rax]
0x1400178bc  movzx   eax, word ptr [rdi+18h]
0x1400178c0  add     eax, 20h ; ' '
0x1400178c3  add     ecx, eax
0x1400178c5  add     edx, ecx
0x1400178c7  mov     rcx, [r14+0B8h]
0x1400178ce  mov     [rsi], edx
0x1400178d0  mov     dword ptr [rsi+4], 1
0x1400178d7  mov     eax, edx
0x1400178d9  mov     [r14+38h], rax
0x1400178dd  cmp     edx, [rcx+8]
0x1400178e0  jbe     short loc_140017928
0x1400178e2  mov     qword ptr [r14+38h], 20h ; ' '
0x1400178ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400178f1  lea     rax, WPP_GLOBAL_Control
0x1400178f8  cmp     rcx, rax
0x1400178fb  jz      short loc_14001791E
0x1400178fd  mov     eax, [rcx+2Ch]
0x140017900  test    al, 1
0x140017902  jz      short loc_14001791E
0x140017904  cmp     byte ptr [rcx+29h], 1
0x140017908  jb      short loc_14001791E
0x14001790a  mov     rcx, [rcx+18h]
0x14001790e  mov     edx, 0CDh
0x140017913  mov     r9d, 80000005h
0x140017919  call    WPP_SF_L
0x14001791e  mov     eax, 80000005h
0x140017923  jmp     loc_1400179FC
0x140017928  mov     rax, [r14+18h]
0x14001792c  xor     ecx, ecx
0x14001792e  xorps   xmm0, xmm0
0x140017931  movups  xmmword ptr [rax+8], xmm0
0x140017935  mov     [rax+18h], rcx
0x140017939  mov     dword ptr [rsi+8], 20h ; ' '
0x140017940  movzx   edx, word ptr [rdi+18h]
0x140017944  mov     [rsi+0Ch], dx
0x140017948  cmp     [rdi+10h], cl
0x14001794b  jz      short loc_14001795C
0x14001794d  lea     eax, [rdx+20h]
0x140017950  mov     [rsi+10h], eax
0x140017953  mov     rax, [rbx+60h]
0x140017957  movzx   ebp, word ptr [rax]
0x14001795a  jmp     short loc_14001795F
0x14001795c  mov     [rsi+10h], ebp
0x14001795f  mov     [rsi+14h], bp
0x140017963  lea     ecx, [rdx+20h]
0x140017966  movzx   eax, bp
0x140017969  mov     r8, rdx; Size
0x14001796c  add     ecx, eax
0x14001796e  mov     [rsi+18h], ecx
0x140017971  lea     rcx, [rsi+20h]; void *
0x140017975  movzx   eax, word ptr [rbx+50h]
0x140017979  mov     [rsi+1Ch], ax
0x14001797d  mov     rdx, [rdi+20h]; Src
0x140017981  call    memmove
0x140017986  cmp     byte ptr [rdi+10h], 0
0x14001798a  jz      short loc_1400179A4
0x14001798c  mov     rdx, [rbx+60h]
0x140017990  mov     ecx, [rsi+10h]
0x140017993  add     rdx, 2; Src
0x140017997  movzx   r8d, word ptr [rsi+14h]; Size
0x14001799c  add     rcx, rsi; void *
0x14001799f  call    memmove
0x1400179a4  mov     ecx, [rsi+18h]
0x1400179a7  movzx   r8d, word ptr [rsi+1Ch]; Size
0x1400179ac  add     rcx, rsi; void *
0x1400179af  mov     rdx, [rbx+58h]; Src
0x1400179b3  call    memmove
0x1400179b8  xor     eax, eax
0x1400179ba  jmp     short loc_1400179FC
0x1400179bc  mov     eax, 0C0000225h
0x1400179c1  jmp     short loc_1400179FC
0x1400179c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400179ca  lea     rax, WPP_GLOBAL_Control
0x1400179d1  cmp     rcx, rax
0x1400179d4  jz      short loc_1400179F7
0x1400179d6  mov     eax, [rcx+2Ch]
0x1400179d9  test    al, 1
0x1400179db  jz      short loc_1400179F7
0x1400179dd  cmp     byte ptr [rcx+29h], 2
0x1400179e1  jb      short loc_1400179F7
0x1400179e3  mov     rcx, [rcx+18h]
0x1400179e7  mov     edx, 0CCh
0x1400179ec  mov     r9d, 0C0000034h
0x1400179f2  call    WPP_SF_L
0x1400179f7  mov     eax, 0C0000034h
0x1400179fc  mov     rbx, [rsp+58h+arg_0]
0x140017a01  mov     rbp, [rsp+58h+arg_8]
0x140017a06  add     rsp, 30h
0x140017a0a  pop     r15
0x140017a0c  pop     r14
0x140017a0e  pop     r12
0x140017a10  pop     rdi
0x140017a11  pop     rsi
0x140017a12  retn
```
