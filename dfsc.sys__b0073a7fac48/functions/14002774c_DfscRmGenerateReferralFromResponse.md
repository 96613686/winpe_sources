# DfscRmGenerateReferralFromResponse

- ea: `0x14002774c`
- end: `0x140027a9e`
- name: `DfscRmGenerateReferralFromResponse`
- size: `850`
- prototype: `__int64(__int64, __int64, unsigned int, __int64 *, ...)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14001b9ec`

## callees

- `0x140001394`
- `0x140002134`
- `0x140006080`
- `0x14001109c`
- `0x1400117ec`
- `0x14001d090`
- `0x14001ef20`
- `0x14002774c`
- `0x140027aa4`
- `0x140027b74`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140027892`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140027892`

## pseudocode

```c
__int64 DfscRmGenerateReferralFromResponse(__int64 a1, __int64 a2, unsigned int a3, __int64 *a4, ...)
{
  __int64 v4; // r14
  __int16 v5; // r12
  __int64 *v7; // r15
  unsigned int v9; // esi
  __int64 result; // rax
  __int64 v11; // r9
  int inited; // edi
  __int64 Referral; // rax
  __int64 v14; // rbx
  int v15; // ecx
  __int16 v16; // ax
  int v17; // eax
  __int64 v18; // r14
  _DWORD *v19; // r15
  int v20; // edx
  int v21; // r8d
  const wchar_t *v22; // r11
  unsigned int v23; // ecx
  __int64 v24; // r11
  NTSTATUS v25; // eax
  _WORD *v26; // r11
  size_t v27; // r12
  __int64 v28; // r8
  __int64 v29; // r9
  __int16 v30; // dx
  __int16 v31; // cx
  __int16 v32; // dx
  char *v33; // rax
  int v34; // [rsp+20h] [rbp-48h]
  int v35; // [rsp+24h] [rbp-44h]
  unsigned int v36; // [rsp+28h] [rbp-40h]
  char *v37; // [rsp+30h] [rbp-38h]
  size_t pcbLength; // [rsp+38h] [rbp-30h] BYREF
  UNICODE_STRING SourceString; // [rsp+40h] [rbp-28h] BYREF
  __int128 v40; // [rsp+50h] [rbp-18h] BYREF
  __int16 v42; // [rsp+B8h] [rbp+50h]
  __int16 v43; // [rsp+C0h] [rbp+58h]
  __int64 v45; // [rsp+D0h] [rbp+68h] BYREF
  va_list va; // [rsp+D0h] [rbp+68h]
  va_list va1; // [rsp+D8h] [rbp+70h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v45 = va_arg(va1, _QWORD);
  v43 = a3;
  v4 = *(unsigned __int16 *)(a2 + 2);
  v5 = a3;
  v7 = a4;
  v42 = *(_WORD *)(a2 + 2);
  v36 = DWORD2(xmmword_14000C740);
  v9 = 0;
  LODWORD(v45) = 0;
  v40 = 0;
  SourceString = 0;
  result = DfscRmCheckReferralSyntax(a2, a3, 0, (__int64 *)va);
  if ( (int)result >= 0 )
  {
    result = DfscRmGetNormalReferralSize(a2, (__int64 *)va);
    if ( (int)result >= 0 )
    {
      LOBYTE(v11) = 1;
      result = DfscRmGetPathConsumed(a1, a2, &SourceString, v11);
      inited = result;
      if ( (int)result >= 0 )
      {
        Referral = DfscRmAllocateReferral((_DWORD)v45 + 2 + (unsigned int)SourceString.Length);
        v14 = Referral;
        if ( !Referral )
          return (unsigned int)-1073741670;
        *(_WORD *)(Referral + 24) = v4;
        v15 = 0;
        if ( !(_WORD)v4 )
          v9 = 300;
        v34 = 0;
        v16 = 0;
        if ( !(_WORD)v4 )
          v16 = -1;
        *(_WORD *)(v14 + 26) = v16;
        v17 = *(_DWORD *)(a2 + 4);
        if ( (v17 & 1) != 0 && (v17 & 2) == 0 )
        {
          if ( (_WORD)v4 == 1 )
            v15 = 1;
          v34 = v15;
        }
        if ( (v17 & 4) != 0 )
          *(_WORD *)(v14 + 12) |= 4u;
        *(_QWORD *)(v14 + 152) = v14 + 112 * v4 + 160;
        *(_WORD *)(v14 + 146) = SourceString.Length + 2;
        RtlCopyUnicodeString((PUNICODE_STRING)(v14 + 144), &SourceString);
        if ( !(_WORD)v4 )
        {
LABEL_46:
          if ( v9 >= v36 )
            v9 = v36;
          *(_DWORD *)(v14 + 40) = v9;
          *(_DWORD *)(v14 + 20) = *(_DWORD *)(a1 + 232);
          if ( inited < 0 )
            DfscRmDereferenceReferral((PVOID)v14);
          else
            *v7 = v14;
          return (unsigned int)inited;
        }
        v18 = a2 + 8;
        v19 = (_DWORD *)(v14 + 160);
        v20 = 0;
        v37 = (char *)(*(_QWORD *)(v14 + 152) + *(unsigned __int16 *)(v14 + 146));
        LODWORD(v45) = 0;
        LOWORD(v21) = 0;
        v35 = 0;
        while ( 1 )
        {
          v22 = 0;
          if ( *(_WORD *)v18 == 1 )
            break;
          switch ( *(_WORD *)v18 )
          {
            case 2:
              v23 = *(_DWORD *)(v18 + 12);
              v24 = *(unsigned __int16 *)(v18 + 20);
              goto LABEL_27;
            case 3:
              goto LABEL_26;
            case 4:
              if ( (*(_BYTE *)(v18 + 6) & 4) != 0 )
              {
                *v19 |= 2u;
                v35 = ++v20;
              }
              v19[1] = v20;
LABEL_26:
              v23 = *(_DWORD *)(v18 + 8);
              v24 = *(unsigned __int16 *)(v18 + 16);
LABEL_27:
              v22 = (const wchar_t *)(v18 + v24);
              v21 = (unsigned __int16)a2;
              LOWORD(v21) = v5 + a2 - (_WORD)v22;
              if ( v9 > v23 )
                v23 = v9;
              v9 = v23;
LABEL_32:
              LODWORD(v45) = v21;
              break;
          }
          pcbLength = 0;
          v25 = RtlStringCbLengthW(v22, (unsigned __int16)v21, &pcbLength);
          v27 = pcbLength;
          inited = v25;
          if ( pcbLength && !v25 )
          {
            if ( v26[(pcbLength >> 1) - 1] == 92 )
              v27 = pcbLength - 2;
            memmove(v37, v26, v27);
            *(_WORD *)&v37[2 * (v27 >> 1)] = 0;
            *((_QWORD *)&v40 + 1) = v37;
            WORD1(v40) = v27;
            LOWORD(v40) = v27;
            inited = DfscInitDfsPath(&v40, v19 + 4, v28, v29);
            if ( inited >= 0 )
            {
              v19[2] = -1;
              --v42;
              if ( v34 || *(_WORD *)(v14 + 24) == 1 && (unsigned __int8)DfscIsKnownDomainName(a1, v19 + 4) )
                *v19 |= 1u;
              v30 = *(_WORD *)(v14 + 12);
              v31 = v30 & 0xFFFD;
              v32 = v30 | 2;
              LOWORD(v21) = v45;
              if ( *(_WORD *)(v18 + 4) != 1 )
                v32 = v31;
              v33 = &v37[v27 + 2];
              *(_WORD *)(v14 + 12) = v32;
              v20 = v35;
              v19 += 28;
              v5 = v43;
              v37 = v33;
              v18 += *(unsigned __int16 *)(v18 + 2);
              if ( v42 )
                continue;
            }
          }
          v7 = a4;
          goto LABEL_46;
        }
        v21 = *(unsigned __int16 *)(v18 + 2);
        v22 = (const wchar_t *)(v18 + 8);
        LOWORD(v21) = v21 - 8;
        goto LABEL_32;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14002774c  mov     [rsp-40h+arg_18], r9
0x140027751  mov     [rsp-40h+arg_10], r8d
0x140027756  mov     [rsp-40h+arg_0], rcx
0x14002775b  push    rbp
0x14002775c  push    rbx
0x14002775d  push    rsi
0x14002775e  push    rdi
0x14002775f  push    r12
0x140027761  push    r13
0x140027763  push    r14
0x140027765  push    r15
0x140027767  mov     rbp, rsp
0x14002776a  sub     rsp, 68h
0x14002776e  movzx   r14d, word ptr [rdx+2]
0x140027773  mov     r12d, r8d
0x140027776  mov     eax, dword ptr cs:xmmword_14000C740+8
0x14002777c  mov     r13, rdx
0x14002777f  mov     r15, r9
0x140027782  mov     [rbp+arg_8], r14w
0x140027787  mov     rbx, rcx
0x14002778a  mov     [rbp+var_40], eax
0x14002778d  xor     esi, esi
0x14002778f  lea     r9, [rbp+arg_20]
0x140027793  xorps   xmm0, xmm0
0x140027796  mov     dword ptr [rbp+arg_20], esi
0x140027799  xorps   xmm1, xmm1
0x14002779c  mov     edx, r12d
0x14002779f  mov     rcx, r13
0x1400277a2  xor     r8d, r8d
0x1400277a5  movups  [rbp+var_18], xmm0
0x1400277a9  movups  xmmword ptr [rbp+SourceString.Length], xmm1
0x1400277ad  call    DfscRmCheckReferralSyntax
0x1400277b2  test    eax, eax
0x1400277b4  js      loc_140027A8C
0x1400277ba  lea     rdx, [rbp+arg_20]
0x1400277be  mov     rcx, r13
0x1400277c1  call    DfscRmGetNormalReferralSize
0x1400277c6  test    eax, eax
0x1400277c8  js      loc_140027A8C
0x1400277ce  mov     r9b, 1
0x1400277d1  lea     r8, [rbp+SourceString]
0x1400277d5  mov     rdx, r13
0x1400277d8  mov     rcx, rbx
0x1400277db  call    DfscRmGetPathConsumed
0x1400277e0  mov     edi, eax
0x1400277e2  test    eax, eax
0x1400277e4  js      loc_140027A8C
0x1400277ea  mov     eax, dword ptr [rbp+arg_20]
0x1400277ed  mov     edx, 72436644h
0x1400277f2  movzx   ecx, [rbp+SourceString.Length]
0x1400277f6  add     eax, 2
0x1400277f9  add     ecx, eax; Size
0x1400277fb  call    DfscRmAllocateReferral
0x140027800  mov     rbx, rax
0x140027803  test    rax, rax
0x140027806  jnz     short loc_140027812
0x140027808  mov     edi, 0C000009Ah
0x14002780d  jmp     loc_140027A8A
0x140027812  xor     edx, edx
0x140027814  mov     [rax+18h], r14w
0x140027819  test    r14w, r14w
0x14002781d  mov     eax, 12Ch
0x140027822  mov     ecx, esi
0x140027824  mov     r8d, 0FFFFh
0x14002782a  cmovz   esi, eax
0x14002782d  mov     [rbp+var_48], ecx
0x140027830  mov     eax, edx
0x140027832  mov     edx, 1
0x140027837  cmovz   ax, r8w
0x14002783c  mov     [rbx+1Ah], ax
0x140027840  mov     eax, [r13+4]
0x140027844  lea     r8d, [rdx+1]
0x140027848  test    dl, al
0x14002784a  jz      short loc_14002785B
0x14002784c  test    r8b, al
0x14002784f  jnz     short loc_14002785B
0x140027851  cmp     r14w, dx
0x140027855  cmovz   ecx, edx
0x140027858  mov     [rbp+var_48], ecx
0x14002785b  test    al, 4
0x14002785d  jz      short loc_140027864
0x14002785f  or      word ptr [rbx+0Ch], 4
0x140027864  imul    rax, r14, 70h ; 'p'
0x140027868  lea     rcx, [rbx+90h]; DestinationString
0x14002786f  add     rax, 0A0h
0x140027875  lea     rdx, [rbp+SourceString]; SourceString
0x140027879  add     rax, rbx
0x14002787c  mov     [rbx+98h], rax
0x140027883  movzx   eax, [rbp+SourceString.Length]
0x140027887  add     ax, r8w
0x14002788b  mov     [rbx+92h], ax
0x140027892  call    cs:__imp_RtlCopyUnicodeString
0x140027899  nop     dword ptr [rax+rax+00h]
0x14002789e  xor     r10d, r10d
0x1400278a1  test    r14w, r14w
0x1400278a5  jz      loc_140027A62
0x1400278ab  movzx   r9d, word ptr [rbx+92h]
0x1400278b3  lea     r14, [r13+8]
0x1400278b7  add     r9, [rbx+98h]
0x1400278be  lea     r15, [rbx+0A0h]
0x1400278c5  mov     edx, r10d
0x1400278c8  mov     [rbp+var_38], r9
0x1400278cc  lea     r9d, [r10+1]
0x1400278d0  mov     dword ptr [rbp+arg_20], r10d
0x1400278d4  mov     r8d, r10d
0x1400278d7  mov     [rbp+var_44], edx
0x1400278da  movzx   ecx, word ptr [r14]
0x1400278de  mov     r11, r10
0x1400278e1  sub     ecx, 1
0x1400278e4  jz      short loc_140027936
0x1400278e6  sub     ecx, 1
0x1400278e9  jz      short loc_14002792B
0x1400278eb  sub     ecx, 1
0x1400278ee  jz      short loc_14002790A
0x1400278f0  cmp     ecx, 1
0x1400278f3  jnz     short loc_140027948
0x1400278f5  test    byte ptr [r14+6], 4
0x1400278fa  jz      short loc_140027906
0x1400278fc  or      dword ptr [r15], 2
0x140027900  add     edx, r9d
0x140027903  mov     [rbp+var_44], edx
0x140027906  mov     [r15+4], edx
0x14002790a  mov     ecx, [r14+8]
0x14002790e  movzx   r11d, word ptr [r14+10h]
0x140027913  add     r11, r14
0x140027916  movzx   r8d, r13w
0x14002791a  sub     r8w, r11w
0x14002791e  add     r8w, r12w
0x140027922  cmp     esi, ecx
0x140027924  cmova   ecx, esi
0x140027927  mov     esi, ecx
0x140027929  jmp     short loc_140027944
0x14002792b  mov     ecx, [r14+0Ch]
0x14002792f  movzx   r11d, word ptr [r14+14h]
0x140027934  jmp     short loc_140027913
0x140027936  movzx   r8d, word ptr [r14+2]
0x14002793b  lea     r11, [r14+8]
0x14002793f  sub     r8w, 8
0x140027944  mov     dword ptr [rbp+arg_20], r8d
0x140027948  movzx   edx, r8w; cbMax
0x14002794c  mov     rcx, r11; psz
0x14002794f  lea     r8, [rbp+pcbLength]; pcbLength
0x140027953  mov     [rbp+pcbLength], r10
0x140027957  call    RtlStringCbLengthW
0x14002795c  mov     r12, [rbp+pcbLength]
0x140027960  mov     edi, eax
0x140027962  test    r12, r12
0x140027965  jz      loc_140027A5E
0x14002796b  test    eax, eax
0x14002796d  jnz     loc_140027A5E
0x140027973  mov     rax, r12
0x140027976  shr     rax, 1
0x140027979  cmp     word ptr [r11+rax*2-2], 5Ch ; '\'
0x140027980  jnz     short loc_140027986
0x140027982  sub     r12, 2
0x140027986  mov     rdi, [rbp+var_38]
0x14002798a  mov     r8, r12; Size
0x14002798d  mov     rcx, rdi; void *
0x140027990  mov     rdx, r11; Src
0x140027993  call    memmove
0x140027998  xor     edx, edx
0x14002799a  mov     rcx, r12
0x14002799d  shr     rcx, 1
0x1400279a0  mov     [rdi+rcx*2], dx
0x1400279a4  lea     rdx, [r15+10h]
0x1400279a8  lea     rcx, [rbp+var_18]
0x1400279ac  mov     qword ptr [rbp+var_18+8], rdi
0x1400279b0  mov     word ptr [rbp+var_18+2], r12w
0x1400279b5  mov     word ptr [rbp+var_18], r12w
0x1400279ba  call    DfscInitDfsPath
0x1400279bf  xor     r10d, r10d
0x1400279c2  mov     edi, eax
0x1400279c4  test    eax, eax
0x1400279c6  js      loc_140027A5E
0x1400279cc  mov     eax, 0FFFFh
0x1400279d1  mov     dword ptr [r15+8], 0FFFFFFFFh
0x1400279d9  add     [rbp+arg_8], ax
0x1400279dd  cmp     [rbp+var_48], r10d
0x1400279e1  jnz     short loc_140027A01
0x1400279e3  lea     eax, [r10+1]
0x1400279e7  cmp     [rbx+18h], ax
0x1400279eb  jnz     short loc_140027A05
0x1400279ed  mov     rcx, [rbp+arg_0]
0x1400279f1  lea     rdx, [r15+10h]
0x1400279f5  call    DfscIsKnownDomainName
0x1400279fa  xor     r10d, r10d
0x1400279fd  test    al, al
0x1400279ff  jz      short loc_140027A05
0x140027a01  or      dword ptr [r15], 1
0x140027a05  movzx   edx, word ptr [rbx+0Ch]
0x140027a09  mov     r8d, 0FFFDh
0x140027a0f  mov     rax, [rbp+var_38]
0x140027a13  movzx   ecx, dx
0x140027a16  and     cx, r8w
0x140027a1a  or      dx, 2
0x140027a1e  mov     r8d, dword ptr [rbp+arg_20]
0x140027a22  mov     r9d, 1
0x140027a28  cmp     [r14+4], r9w
0x140027a2d  cmovnz  dx, cx
0x140027a31  add     rax, 2
0x140027a35  add     rax, r12
0x140027a38  mov     [rbx+0Ch], dx
0x140027a3c  mov     edx, [rbp+var_44]
0x140027a3f  add     r15, 70h ; 'p'
0x140027a43  mov     r12d, [rbp+arg_10]
0x140027a47  mov     [rbp+var_38], rax
0x140027a4b  movzx   eax, word ptr [r14+2]
0x140027a50  add     r14, rax
0x140027a53  cmp     [rbp+arg_8], r10w
0x140027a58  jnz     loc_1400278DA
0x140027a5e  mov     r15, [rbp+arg_18]
0x140027a62  cmp     esi, [rbp+var_40]
0x140027a65  mov     rax, [rbp+arg_0]
0x140027a69  cmovnb  esi, [rbp+var_40]
0x140027a6d  mov     [rbx+28h], esi
0x140027a70  mov     eax, [rax+0E8h]
0x140027a76  mov     [rbx+14h], eax
0x140027a79  test    edi, edi
0x140027a7b  js      short loc_140027A82
0x140027a7d  mov     [r15], rbx
0x140027a80  jmp     short loc_140027A8A
0x140027a82  mov     rcx, rbx; P
0x140027a85  call    DfscRmDereferenceReferral
0x140027a8a  mov     eax, edi
0x140027a8c  add     rsp, 68h
0x140027a90  pop     r15
0x140027a92  pop     r14
0x140027a94  pop     r13
0x140027a96  pop     r12
0x140027a98  pop     rdi
0x140027a99  pop     rsi
0x140027a9a  pop     rbx
0x140027a9b  pop     rbp
0x140027a9c  retn
```
