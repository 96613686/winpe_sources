# EfspCopyAesKeyBlob

- ea: `0x140055574`
- end: `0x140055845`
- name: `EfspCopyAesKeyBlob`
- size: `721`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14005584c`

## callees

- `0x14000c380`
- `0x14004e610`
- `0x140055574`
- `0x14005693c`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005582c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005582c`
- `ksecdd!BCryptGenerateSymmetricKey` at `0x1400557ae`
- `ksecdd!BCryptGenerateSymmetricKey` at `0x1400557ae`

## pseudocode

```c
__int64 __fastcall EfspCopyAesKeyBlob(unsigned int *a1, unsigned int *a2)
{
  unsigned int v2; // eax
  NTSTATUS SymmetricKey; // edi
  __int64 v6; // rcx
  _DWORD *KeyBlobBuffer; // rsi
  char *v8; // rcx
  __int64 v9; // rcx
  ULONG v10; // r9d
  char *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  char *v14; // rax
  _BYTE *v15; // rcx
  __int64 v16; // rax

  v2 = a2[1];
  if ( v2 != 26126 && v2 != 26128 && v2 != 536897040 && v2 != 1073767952 || a2[20] != 1 )
  {
    SymmetricKey = -1073741823;
    EfspTraceLogAssert(a1, 6, 3152);
    return (unsigned int)SymmetricKey;
  }
  KeyBlobBuffer = GetKeyBlobBufferEx(a1[1], a1[6]);
  if ( !KeyBlobBuffer )
    return (unsigned int)-1073741670;
  if ( *KeyBlobBuffer >= *a1 )
  {
    SymmetricKey = 0;
    memmove(KeyBlobBuffer, a1, *a1);
    a1[1] = a2[1];
    a1[6] = a2[6];
    *((_QWORD *)a1 + 4) = *((_QWORD *)a2 + 4);
    *((_QWORD *)a1 + 5) = *((_QWORD *)a2 + 5);
    *((_BYTE *)a1 + 48) = *((_BYTE *)a2 + 48);
    a1[20] = a2[20];
    a1[24] = a2[24];
    a1[25] = a2[25];
    if ( a1[1] == 26126 || a1[1] == 26128 )
    {
      *((_QWORD *)a1 + 14) = a1 + 34;
      v11 = (char *)a1 + ((dword_1400178CC + 7) & 0xFFFFFFF8) + 136;
      *((_QWORD *)a1 + 15) = v11;
      *((_QWORD *)a1 + 16) = &v11[((_DWORD)Size + 7) & 0xFFFFFFF8];
      memmove(v11, *((const void **)a2 + 15), (unsigned int)Size);
      memmove(*((void **)a1 + 16), *((const void **)a2 + 16), (unsigned int)dword_140017920);
      v9 = *((_QWORD *)a2 + 11);
      if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        v10 = dword_1400178CC;
LABEL_20:
        SymmetricKey = BCryptGenerateSymmetricKey(
                         qword_1400178C0,
                         (BCRYPT_KEY_HANDLE *)a1 + 11,
                         *((PUCHAR *)a1 + 14),
                         v10,
                         *((PUCHAR *)a1 + 15),
                         a1[25],
                         0);
        if ( SymmetricKey < 0 )
          goto LABEL_27;
LABEL_23:
        v12 = *a2;
        if ( *a1 > (unsigned int)v12 )
        {
          v13 = *a1 - (unsigned int)v12;
          v14 = (char *)a1 + v12;
          if ( *a1 != (_DWORD)v12 )
          {
            do
            {
              *v14++ = 0;
              --v13;
            }
            while ( v13 );
          }
        }
        *(_OWORD *)(a1 + 14) = *(_OWORD *)(a2 + 14);
        goto LABEL_28;
      }
    }
    else
    {
      if ( a1[1] != 536897040 && a1[1] != 1073767952 )
      {
        SymmetricKey = -1073741823;
        EfspTraceLogAssert(a1[1] - 536897040, 6, 3253);
LABEL_27:
        memmove(a1, KeyBlobBuffer, *a1);
        a1[1] = KeyBlobBuffer[1];
        a1[6] = KeyBlobBuffer[6];
        goto LABEL_28;
      }
      *((_QWORD *)a1 + 14) = a1 + 34;
      v8 = (char *)a1 + ((dword_1400178D8 + 7) & 0xFFFFFFF8) + 136;
      *((_QWORD *)a1 + 15) = v8;
      *((_QWORD *)a1 + 16) = &v8[((_DWORD)Size + 7) & 0xFFFFFFF8];
      memmove(v8, *((const void **)a2 + 15), (unsigned int)Size);
      memmove(*((void **)a1 + 16), *((const void **)a2 + 16), (unsigned int)dword_140017920);
      v9 = *((_QWORD *)a2 + 11);
      if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        v10 = dword_1400178D8;
        goto LABEL_20;
      }
    }
    *((_QWORD *)a1 + 11) = v9;
    goto LABEL_23;
  }
  SymmetricKey = -1073741823;
  EfspTraceLogAssert(v6, 6, 3167);
LABEL_28:
  v15 = KeyBlobBuffer + 20;
  v16 = (unsigned int)*KeyBlobBuffer - 87LL;
  if ( *KeyBlobBuffer != 87 )
  {
    do
    {
      *v15++ = 0;
      --v16;
    }
    while ( v16 );
  }
  ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)KeyBlobBuffer + 9), KeyBlobBuffer);
  return (unsigned int)SymmetricKey;
}

```

## disassembly

```asm
0x140055574  push    rbx
0x140055576  push    rsi
0x140055577  push    rdi
0x140055578  push    r14
0x14005557a  sub     rsp, 48h
0x14005557e  mov     eax, [rdx+4]
0x140055581  mov     r14, rdx
0x140055584  mov     rbx, rcx
0x140055587  cmp     eax, 660Eh
0x14005558c  jz      short loc_1400555A3
0x14005558e  cmp     eax, 6610h
0x140055593  jz      short loc_1400555A3
0x140055595  cmp     eax, 20006610h
0x14005559a  jz      short loc_1400555A3
0x14005559c  cmp     eax, 40006610h
0x1400555a1  jnz     short loc_1400555A9
0x1400555a3  cmp     dword ptr [rdx+50h], 1
0x1400555a7  jz      short loc_1400555C7
0x1400555a9  mov     r9d, 0C0000001h
0x1400555af  mov     edx, 6
0x1400555b4  mov     r8d, 0C50h
0x1400555ba  mov     edi, r9d
0x1400555bd  call    EfspTraceLogAssert
0x1400555c2  jmp     loc_140055838
0x1400555c7  mov     edx, [rcx+18h]
0x1400555ca  mov     ecx, [rcx+4]
0x1400555cd  call    GetKeyBlobBufferEx
0x1400555d2  mov     rsi, rax
0x1400555d5  test    rax, rax
0x1400555d8  jnz     short loc_1400555E4
0x1400555da  mov     edi, 0C000009Ah
0x1400555df  jmp     loc_140055838
0x1400555e4  mov     eax, [rbx]
0x1400555e6  cmp     [rsi], eax
0x1400555e8  jnb     short loc_140055608
0x1400555ea  mov     r9d, 0C0000001h
0x1400555f0  mov     edx, 6
0x1400555f5  mov     r8d, 0C5Fh
0x1400555fb  mov     edi, r9d
0x1400555fe  call    EfspTraceLogAssert
0x140055603  jmp     loc_14005580D
0x140055608  mov     r8, rax; Size
0x14005560b  mov     rdx, rbx; Src
0x14005560e  mov     rcx, rsi; void *
0x140055611  xor     edi, edi
0x140055613  call    memmove
0x140055618  mov     eax, [r14+4]
0x14005561c  mov     [rbx+4], eax
0x14005561f  mov     eax, [r14+18h]
0x140055623  mov     [rbx+18h], eax
0x140055626  mov     rax, [r14+20h]
0x14005562a  mov     [rbx+20h], rax
0x14005562e  mov     rax, [r14+28h]
0x140055632  mov     [rbx+28h], rax
0x140055636  mov     al, [r14+30h]
0x14005563a  mov     [rbx+30h], al
0x14005563d  mov     eax, [r14+50h]
0x140055641  mov     [rbx+50h], eax
0x140055644  mov     eax, [r14+60h]
0x140055648  mov     [rbx+60h], eax
0x14005564b  mov     eax, [r14+64h]
0x14005564f  mov     [rbx+64h], eax
0x140055652  mov     ecx, [rbx+4]
0x140055655  sub     ecx, 660Eh
0x14005565b  jz      loc_140055713
0x140055661  sub     ecx, 2
0x140055664  jz      loc_140055713
0x14005566a  mov     eax, 20000000h
0x14005566f  sub     ecx, eax
0x140055671  jz      short loc_140055695
0x140055673  cmp     ecx, eax
0x140055675  jz      short loc_140055695
0x140055677  mov     r9d, 0C0000001h
0x14005567d  mov     edx, 6
0x140055682  mov     r8d, 0CB5h
0x140055688  mov     edi, r9d
0x14005568b  call    EfspTraceLogAssert
0x140055690  jmp     loc_1400557F3
0x140055695  mov     edx, 0FFFFFFF8h
0x14005569a  lea     rcx, [rbx+88h]
0x1400556a1  mov     [rbx+70h], rcx
0x1400556a5  mov     eax, cs:dword_1400178D8
0x1400556ab  add     eax, 7
0x1400556ae  and     rax, rdx
0x1400556b1  add     rcx, rax; void *
0x1400556b4  mov     [rbx+78h], rcx
0x1400556b8  mov     eax, cs:Size
0x1400556be  add     eax, 7
0x1400556c1  and     rax, rdx
0x1400556c4  add     rax, rcx
0x1400556c7  mov     [rbx+80h], rax
0x1400556ce  mov     r8d, cs:Size; Size
0x1400556d5  mov     rdx, [r14+78h]; Src
0x1400556d9  call    memmove
0x1400556de  mov     r8d, cs:dword_140017920; Size
0x1400556e5  mov     rdx, [r14+80h]; Src
0x1400556ec  mov     rcx, [rbx+80h]; void *
0x1400556f3  call    memmove
0x1400556f8  mov     rcx, [r14+58h]
0x1400556fc  lea     rax, [rcx-1]
0x140055700  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140055704  ja      loc_1400557C2
0x14005570a  mov     r9d, cs:dword_1400178D8
0x140055711  jmp     short loc_14005578B
0x140055713  mov     edx, 0FFFFFFF8h
0x140055718  lea     rcx, [rbx+88h]
0x14005571f  mov     [rbx+70h], rcx
0x140055723  mov     eax, cs:dword_1400178CC
0x140055729  add     eax, 7
0x14005572c  and     rax, rdx
0x14005572f  add     rcx, rax; void *
0x140055732  mov     [rbx+78h], rcx
0x140055736  mov     eax, cs:Size
0x14005573c  add     eax, 7
0x14005573f  and     rax, rdx
0x140055742  add     rax, rcx
0x140055745  mov     [rbx+80h], rax
0x14005574c  mov     r8d, cs:Size; Size
0x140055753  mov     rdx, [r14+78h]; Src
0x140055757  call    memmove
0x14005575c  mov     r8d, cs:dword_140017920; Size
0x140055763  mov     rdx, [r14+80h]; Src
0x14005576a  mov     rcx, [rbx+80h]; void *
0x140055771  call    memmove
0x140055776  mov     rcx, [r14+58h]
0x14005577a  lea     rax, [rcx-1]
0x14005577e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140055782  ja      short loc_1400557C2
0x140055784  mov     r9d, cs:dword_1400178CC; cbKeyObject
0x14005578b  mov     eax, [rbx+64h]
0x14005578e  lea     rdx, [rbx+58h]; phKey
0x140055792  mov     r8, [rbx+70h]; pbKeyObject
0x140055796  mov     rcx, cs:qword_1400178C0; hAlgorithm
0x14005579d  mov     [rsp+68h+dwFlags], edi; dwFlags
0x1400557a1  mov     [rsp+68h+cbSecret], eax; cbSecret
0x1400557a5  mov     rax, [rbx+78h]
0x1400557a9  mov     [rsp+68h+pbSecret], rax; pbSecret
0x1400557ae  call    cs:__imp_BCryptGenerateSymmetricKey
0x1400557b5  nop     dword ptr [rax+rax+00h]
0x1400557ba  mov     edi, eax
0x1400557bc  test    eax, eax
0x1400557be  jns     short loc_1400557C6
0x1400557c0  jmp     short loc_1400557F3
0x1400557c2  mov     [rbx+58h], rcx
0x1400557c6  mov     edx, [r14]
0x1400557c9  mov     eax, [rbx]
0x1400557cb  cmp     eax, edx
0x1400557cd  jbe     short loc_1400557E5
0x1400557cf  sub     eax, edx
0x1400557d1  mov     ecx, eax
0x1400557d3  lea     rax, [rbx+rdx]
0x1400557d7  jz      short loc_1400557E5
0x1400557d9  mov     byte ptr [rax], 0
0x1400557dc  inc     rax
0x1400557df  sub     rcx, 1
0x1400557e3  jnz     short loc_1400557D9
0x1400557e5  movups  xmm0, xmmword ptr [r14+38h]
0x1400557ea  movdqu  xmmword ptr [rbx+38h], xmm0
0x1400557ef  test    edi, edi
0x1400557f1  jns     short loc_14005580D
0x1400557f3  mov     r8d, [rbx]; Size
0x1400557f6  mov     rdx, rsi; Src
0x1400557f9  mov     rcx, rbx; void *
0x1400557fc  call    memmove
0x140055801  mov     eax, [rsi+4]
0x140055804  mov     [rbx+4], eax
0x140055807  mov     eax, [rsi+18h]
0x14005580a  mov     [rbx+18h], eax
0x14005580d  mov     eax, [rsi]
0x14005580f  lea     rcx, [rsi+50h]
0x140055813  sub     rax, 57h ; 'W'
0x140055817  jz      short loc_140055825
0x140055819  mov     byte ptr [rcx], 0
0x14005581c  inc     rcx
0x14005581f  sub     rax, 1
0x140055823  jnz     short loc_140055819
0x140055825  mov     rcx, [rsi+48h]; Lookaside
0x140055829  mov     rdx, rsi; Entry
0x14005582c  call    cs:__imp_ExFreeToNPagedLookasideList
0x140055833  nop     dword ptr [rax+rax+00h]
0x140055838  mov     eax, edi
0x14005583a  add     rsp, 48h
0x14005583e  pop     r14
0x140055840  pop     rdi
0x140055841  pop     rsi
0x140055842  pop     rbx
0x140055843  retn
```
