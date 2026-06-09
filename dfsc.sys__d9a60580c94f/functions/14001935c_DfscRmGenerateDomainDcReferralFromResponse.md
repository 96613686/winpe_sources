# DfscRmGenerateDomainDcReferralFromResponse

- ea: `0x14001935c`
- end: `0x1400195d3`
- name: `DfscRmGenerateDomainDcReferralFromResponse`
- size: `631`
- prototype: `int __fastcall(__int64, __int64, unsigned int, __int64 *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140011604`

## callees

- `0x140001394`
- `0x140002134`
- `0x140006080`
- `0x14001935c`
- `0x1400198ac`
- `0x14001d090`
- `0x14001ef20`
- `0x140027aa4`
- `0x140027b74`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14001949b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001949b`

## pseudocode

```c
int __fastcall DfscRmGenerateDomainDcReferralFromResponse(__int64 a1, __int64 a2, unsigned int a3, __int64 *a4)
{
  unsigned int v4; // r12d
  __int16 v5; // r13
  int result; // eax
  int inited; // edi
  __int64 Referral; // rax
  __int64 v11; // r14
  __int64 v12; // rcx
  const wchar_t *v13; // rsi
  char *v14; // r12
  unsigned __int16 v15; // bx
  NTSTATUS v16; // eax
  size_t v17; // r15
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rcx
  unsigned int v22; // eax
  unsigned int v23; // [rsp+20h] [rbp-48h] BYREF
  __int64 v24; // [rsp+28h] [rbp-40h]
  size_t pcbLength; // [rsp+30h] [rbp-38h] BYREF
  UNICODE_STRING SourceString; // [rsp+38h] [rbp-30h] BYREF
  __int128 v27; // [rsp+48h] [rbp-20h] BYREF

  v4 = DWORD2(xmmword_14000C740);
  v5 = a3;
  v23 = 0;
  v27 = 0;
  SourceString = 0;
  result = DfscRmCheckReferralSyntax(a2, a3, 1, &v23);
  if ( result >= 0 )
  {
    if ( *(_WORD *)(a2 + 2) == 1 && (*(_BYTE *)(a2 + 14) & 2) != 0 && *(_WORD *)(a2 + 22) )
    {
      result = DfscRmGetDomainDcReferralSize(a2, &v23);
      if ( result >= 0 )
      {
        result = DfscRmGetPathConsumed(a1, (USHORT *)a2, &SourceString, 0);
        inited = result;
        if ( result >= 0 )
        {
          Referral = DfscRmAllocateReferral(v23 + 2 + SourceString.Length);
          v11 = Referral;
          if ( !Referral )
            return -1073741670;
          v12 = *(unsigned __int16 *)(a2 + 22);
          *(_DWORD *)(Referral + 24) = (unsigned __int16)v12;
          if ( *(_DWORD *)(a2 + 16) < v4 )
            v4 = *(_DWORD *)(a2 + 16);
          *(_DWORD *)(Referral + 40) = v4;
          *(_DWORD *)(Referral + 20) = *(_DWORD *)(a1 + 232);
          v24 = Referral + 160;
          *(_BYTE *)(Referral + 15) = 1;
          *(_QWORD *)(Referral + 152) = Referral + 112 * v12 + 160;
          *(_WORD *)(Referral + 146) = SourceString.Length + 2;
          RtlCopyUnicodeString((PUNICODE_STRING)(Referral + 144), &SourceString);
          v13 = (const wchar_t *)(a2 + 8 + *(unsigned __int16 *)(a2 + 24));
          v14 = (char *)(*(_QWORD *)(v11 + 152) + *(unsigned __int16 *)(v11 + 146));
          v15 = v5 - (*(_WORD *)(a2 + 24) + 8);
          v23 = 0;
          if ( *(_WORD *)(v11 + 24) )
          {
            do
            {
              while ( *v13 == 92 )
              {
                ++v13;
                v15 -= 2;
              }
              pcbLength = 0;
              v16 = RtlStringCbLengthW(v13, v15, &pcbLength);
              v17 = pcbLength;
              inited = v16;
              if ( !pcbLength || v16 )
                break;
              memmove(v14, v13, pcbLength);
              v18 = v24 + 16;
              *(_WORD *)&v14[2 * (v17 >> 1)] = 0;
              *((_QWORD *)&v27 + 1) = v14;
              WORD1(v27) = v17;
              LOWORD(v27) = v17;
              inited = DfscInitDfsPath(&v27, v18, v19, v20);
              if ( inited < 0 )
                goto LABEL_20;
              v21 = v24;
              v14 += v17 + 2;
              v15 += -2 - v17;
              v13 += (v17 >> 1) + 1;
              *(_DWORD *)(v24 + 8) = -1;
              v22 = *(unsigned __int16 *)(v11 + 24);
              v24 = v21 + 112;
              ++v23;
            }
            while ( v23 < v22 );
            if ( inited >= 0 )
              goto LABEL_21;
LABEL_20:
            DfscRmDereferenceReferral((PVOID)v11);
          }
          else
          {
LABEL_21:
            *a4 = v11;
          }
          return inited;
        }
      }
    }
    else
    {
      return -1073741629;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001935c  mov     [rsp-40h+arg_18], r9
0x140019361  push    rbp
0x140019362  push    rbx
0x140019363  push    rsi
0x140019364  push    rdi
0x140019365  push    r12
0x140019367  push    r13
0x140019369  push    r14
0x14001936b  push    r15
0x14001936d  mov     rbp, rsp
0x140019370  sub     rsp, 68h
0x140019374  mov     r12d, dword ptr cs:xmmword_14000C740+8
0x14001937b  lea     r9, [rbp+var_48]
0x14001937f  mov     r13d, r8d
0x140019382  mov     rbx, rdx
0x140019385  xor     r14d, r14d
0x140019388  mov     rsi, rcx
0x14001938b  xorps   xmm0, xmm0
0x14001938e  mov     [rbp+var_48], r14d
0x140019392  xorps   xmm1, xmm1
0x140019395  mov     edx, r13d
0x140019398  mov     rcx, rbx
0x14001939b  lea     edi, [r14+1]
0x14001939f  mov     r8b, dil
0x1400193a2  movups  [rbp+var_20], xmm0
0x1400193a6  movups  xmmword ptr [rbp+SourceString.Length], xmm1
0x1400193aa  call    DfscRmCheckReferralSyntax
0x1400193af  test    eax, eax
0x1400193b1  js      loc_1400195C1
0x1400193b7  cmp     [rbx+2], di
0x1400193bb  jnz     loc_1400195BC
0x1400193c1  lea     r15, [rbx+8]
0x1400193c5  test    byte ptr [r15+6], 2
0x1400193ca  jz      loc_1400195BC
0x1400193d0  cmp     [r15+0Eh], r14w
0x1400193d5  jz      loc_1400195BC
0x1400193db  lea     rdx, [rbp+var_48]
0x1400193df  mov     rcx, rbx
0x1400193e2  call    DfscRmGetDomainDcReferralSize
0x1400193e7  test    eax, eax
0x1400193e9  js      loc_1400195C1
0x1400193ef  xor     r9d, r9d
0x1400193f2  lea     r8, [rbp+SourceString]
0x1400193f6  mov     rdx, rbx
0x1400193f9  mov     rcx, rsi
0x1400193fc  call    DfscRmGetPathConsumed
0x140019401  mov     edi, eax
0x140019403  test    eax, eax
0x140019405  js      loc_1400195C1
0x14001940b  mov     eax, [rbp+var_48]
0x14001940e  mov     edx, 72436644h
0x140019413  movzx   ecx, [rbp+SourceString.Length]
0x140019417  add     eax, 2
0x14001941a  add     ecx, eax; Size
0x14001941c  call    DfscRmAllocateReferral
0x140019421  mov     r14, rax
0x140019424  test    rax, rax
0x140019427  jnz     short loc_140019433
0x140019429  mov     edi, 0C000009Ah
0x14001942e  jmp     loc_1400195B8
0x140019433  movzx   ecx, word ptr [r15+0Eh]
0x140019438  lea     rdx, [rbp+SourceString]; SourceString
0x14001943c  mov     [rax+18h], cx
0x140019440  xor     eax, eax
0x140019442  mov     [r14+1Ah], ax
0x140019447  mov     eax, [r15+8]
0x14001944b  cmp     eax, r12d
0x14001944e  cmovb   r12d, eax
0x140019452  mov     [r14+28h], r12d
0x140019456  mov     eax, [rsi+0E8h]
0x14001945c  mov     [r14+14h], eax
0x140019460  lea     rax, [r14+0A0h]
0x140019467  mov     [rbp+var_40], rax
0x14001946b  imul    rax, rcx, 70h ; 'p'
0x14001946f  mov     byte ptr [r14+0Fh], 1
0x140019474  lea     rcx, [r14+90h]; DestinationString
0x14001947b  add     rax, 0A0h
0x140019481  add     rax, r14
0x140019484  mov     [r14+98h], rax
0x14001948b  movzx   eax, [rbp+SourceString.Length]
0x14001948f  add     ax, 2
0x140019493  mov     [r14+92h], ax
0x14001949b  call    cs:__imp_RtlCopyUnicodeString
0x1400194a2  nop     dword ptr [rax+rax+00h]
0x1400194a7  movzx   esi, word ptr [r15+10h]
0x1400194ac  xor     eax, eax
0x1400194ae  movzx   r12d, word ptr [r14+92h]
0x1400194b6  add     rsi, r15
0x1400194b9  add     r12, [r14+98h]
0x1400194c0  sub     bx, si
0x1400194c3  add     bx, r13w
0x1400194c7  mov     [rbp+var_48], 0
0x1400194ce  cmp     ax, [r14+18h]
0x1400194d3  jnb     loc_1400195B1
0x1400194d9  mov     eax, 0FFFEh
0x1400194de  jmp     short loc_1400194E7
0x1400194e0  add     rsi, 2
0x1400194e4  add     bx, ax
0x1400194e7  cmp     word ptr [rsi], 5Ch ; '\'
0x1400194eb  jz      short loc_1400194E0
0x1400194ed  movzx   edx, bx; cbMax
0x1400194f0  lea     r8, [rbp+pcbLength]; pcbLength
0x1400194f4  mov     rcx, rsi; psz
0x1400194f7  mov     [rbp+pcbLength], 0
0x1400194ff  call    RtlStringCbLengthW
0x140019504  mov     r15, [rbp+pcbLength]
0x140019508  mov     edi, eax
0x14001950a  test    r15, r15
0x14001950d  jz      loc_1400195A3
0x140019513  test    eax, eax
0x140019515  jnz     loc_1400195A3
0x14001951b  mov     r8, r15; Size
0x14001951e  mov     rdx, rsi; Src
0x140019521  mov     rcx, r12; void *
0x140019524  call    memmove
0x140019529  mov     rdx, [rbp+var_40]
0x14001952d  lea     rcx, [rbp+var_20]
0x140019531  xor     eax, eax
0x140019533  mov     r13, r15
0x140019536  shr     r13, 1
0x140019539  add     rdx, 10h
0x14001953d  mov     [r12+r13*2], ax
0x140019542  mov     qword ptr [rbp+var_20+8], r12
0x140019546  mov     word ptr [rbp+var_20+2], r15w
0x14001954b  mov     word ptr [rbp+var_20], r15w
0x140019550  call    DfscInitDfsPath
0x140019555  mov     edi, eax
0x140019557  test    eax, eax
0x140019559  js      short loc_1400195A7
0x14001955b  mov     rcx, [rbp+var_40]
0x14001955f  lea     rsi, [rsi+r13*2]
0x140019563  mov     eax, 0FFFEh
0x140019568  add     r12, 2
0x14001956c  sub     ax, r15w
0x140019570  add     r12, r15
0x140019573  add     bx, ax
0x140019576  add     rsi, 2
0x14001957a  mov     dword ptr [rcx+8], 0FFFFFFFFh
0x140019581  add     rcx, 70h ; 'p'
0x140019585  movzx   eax, word ptr [r14+18h]
0x14001958a  mov     [rbp+var_40], rcx
0x14001958e  mov     ecx, [rbp+var_48]
0x140019591  inc     ecx
0x140019593  cmp     ecx, eax
0x140019595  mov     [rbp+var_48], ecx
0x140019598  mov     eax, 0FFFEh
0x14001959d  jb      loc_1400194E7
0x1400195a3  test    edi, edi
0x1400195a5  jns     short loc_1400195B1
0x1400195a7  mov     rcx, r14; P
0x1400195aa  call    DfscRmDereferenceReferral
0x1400195af  jmp     short loc_1400195B8
0x1400195b1  mov     rax, [rbp+arg_18]
0x1400195b5  mov     [rax], r14
0x1400195b8  mov     eax, edi
0x1400195ba  jmp     short loc_1400195C1
0x1400195bc  mov     eax, 0C00000C3h
0x1400195c1  add     rsp, 68h
0x1400195c5  pop     r15
0x1400195c7  pop     r14
0x1400195c9  pop     r13
0x1400195cb  pop     r12
0x1400195cd  pop     rdi
0x1400195ce  pop     rsi
0x1400195cf  pop     rbx
0x1400195d0  pop     rbp
0x1400195d1  retn
```
