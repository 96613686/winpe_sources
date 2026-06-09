# Wow64RedirectKeyPathInternal

- ea: `0x18001dea8`
- end: `0x18001e2ce`
- name: `Wow64RedirectKeyPathInternal`
- size: `1062`
- prototype: `__int64 __fastcall(__int64, const UNICODE_STRING *, struct _UNICODE_STRING *, __int64, int, __int16)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800035a0`

## callees

- `0x180007740`
- `0x18001d87c`
- `0x18001dce0`
- `0x18001dea8`

## import_xrefs

- `ntdll!RtlAppendUnicodeStringToString` at `0x18001e1d5`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18001e1d5`
- `ntdll!RtlCopyUnicodeString` at `0x18001dfc6`
- `ntdll!RtlCopyUnicodeString` at `0x18001dfc6`
- `ntdll!RtlFreeHeap` at `0x18001e29e`
- `ntdll!RtlFreeHeap` at `0x18001e29e`
- `ntdll!RtlAllocateHeap` at `0x18001df98`
- `ntdll!RtlAllocateHeap` at `0x18001df98`

## pseudocode

```c
__int64 __fastcall Wow64RedirectKeyPathInternal(
        __int64 a1,
        const UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        __int64 a4,
        int a5,
        __int16 a6)
{
  unsigned __int16 v9; // r8
  __int16 *v10; // r12
  unsigned int Length; // eax
  unsigned int v12; // ecx
  unsigned __int16 v13; // si
  __int64 MaximumLength; // rbx
  WCHAR *Heap; // rax
  NTSTATUS appended; // r13d
  int Buffer; // r12d
  __int16 v19; // si
  unsigned __int16 v20; // r14
  char v21; // r11
  unsigned __int16 v22; // bx
  __int64 v23; // rax
  int v24; // edx
  __int64 v25; // rcx
  unsigned __int16 v26; // si
  __int64 v27; // rax
  unsigned __int16 v28; // dx
  unsigned __int16 v29; // bx
  int v30; // r12d
  char v31; // dl
  unsigned __int16 v32; // r8
  int v33; // r15d
  __int64 v34; // r9
  __int16 v35; // r10
  __int16 v36; // dx
  __int16 v37; // cx
  PUNICODE_STRING v38; // r8
  __int16 *v39; // rdx
  __int16 v40; // r9
  char v41; // [rsp+30h] [rbp-49h]
  char v42[3]; // [rsp+31h] [rbp-48h] BYREF
  unsigned __int16 v43; // [rsp+34h] [rbp-45h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-41h] BYREF
  UNICODE_STRING Source; // [rsp+48h] [rbp-31h] BYREF
  PUNICODE_STRING Destination; // [rsp+58h] [rbp-21h]
  __int16 *v47; // [rsp+60h] [rbp-19h]
  __int16 v48; // [rsp+68h] [rbp-11h]
  _WORD v49[7]; // [rsp+6Ah] [rbp-Fh]

  Destination = a3;
  *(_DWORD *)(a4 + 2) = 0;
  *(_DWORD *)(a4 + 8) = 0;
  v42[0] = 0;
  *(_BYTE *)a4 = 0;
  DestinationString = 0;
  Source = 0;
  if ( ((a5 - 256) & 0xFFFFFEFF) != 0 )
    return 3221225485LL;
  if ( a6 != 332 )
  {
    if ( a6 == 452 )
    {
      v9 = WowArmNodeString;
      v10 = &WowArmNodeString;
      goto LABEL_6;
    }
    return 3221225485LL;
  }
  v9 = Wowx86NodeString;
  v10 = &Wowx86NodeString;
LABEL_6:
  Length = a2->Length;
  v47 = v10;
  v12 = Length / v9;
  if ( v9 <= 0x18u )
    v13 = v12 * (24 - v9);
  else
    v13 = v12 * (v9 - 24);
  MaximumLength = a2->MaximumLength;
  Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, MaximumLength + v13);
  *(_QWORD *)&DestinationString.Length = 0;
  *(_DWORD *)&DestinationString.MaximumLength = (unsigned __int16)(v13 + MaximumLength);
  DestinationString.Buffer = Heap;
  if ( !Heap )
    return 3221225495LL;
  RtlCopyUnicodeString(&DestinationString, a2);
  appended = PathReplaceGreedy(v10, &Wowx86NodeString, &DestinationString);
  if ( appended < 0 )
    goto LABEL_63;
  Buffer = (int)DestinationString.Buffer;
  v19 = 0;
  v20 = DestinationString.Length >> 1;
  v21 = 0;
  v48 = 0;
  v41 = 0;
  v22 = 1;
LABEL_13:
  if ( a1 )
  {
    while ( 1 )
    {
      v43 = 0;
      v23 = LookupRedirectionNode(a1, Buffer, v20, (unsigned int)&v43, (__int64)v42);
      if ( !v23 )
      {
        v21 = v41;
        if ( v42[0] )
          *(_DWORD *)(a4 + 8) |= 0x400u;
        goto LABEL_26;
      }
      v20 -= v43;
      v19 += v43;
      Buffer += 2 * v43;
      v24 = *(_DWORD *)(v23 + 36);
      if ( (v24 & 2) != 0 )
        break;
      if ( (v24 & 4) != 0 )
      {
        v25 = v22;
        v49[v22 - 1] = v19 - 12;
        goto LABEL_19;
      }
LABEL_20:
      v21 = v24 & 1;
      v41 = v24 & 1;
      if ( (v24 & 8) != 0 )
        *(_DWORD *)(a4 + 8) |= 1u;
      a1 = *(_QWORD *)(v23 + 8);
      if ( !a1 )
      {
        *(_DWORD *)(a4 + 8) |= 0x400u;
        goto LABEL_13;
      }
    }
    v25 = v22;
    v49[v22 - 1] = v19;
LABEL_19:
    v22 += 2;
    v49[v25] = v19;
    goto LABEL_20;
  }
LABEL_26:
  v26 = 1;
  v27 = v22;
  v28 = 2;
  v29 = v22 + 1;
  v49[v27 - 1] = DestinationString.Length >> 1;
  while ( v28 < v29 )
  {
    if ( *((_WORD *)&v47 + v28 + 3) != v49[v28 - 1] )
    {
      *(_DWORD *)(a4 + 8) |= 0xA00u;
      v30 = 512;
      goto LABEL_32;
    }
    v28 += 2;
  }
  v30 = a5;
LABEL_32:
  v31 = *(_BYTE *)a4;
  v32 = 2;
  v33 = v29 - 2;
  if ( v33 > 2 )
  {
    do
    {
      if ( *((_WORD *)&v47 + v32 + 3) != v49[v32 - 1] )
        v31 = 1;
      v32 += 2;
    }
    while ( v32 < v33 );
  }
  *(_BYTE *)a4 = v31;
  if ( v21 && v30 == 512 )
  {
    if ( v29 > 2u && *((_WORD *)&v47 + v29 + 1) == *((_WORD *)&v47 + v29 + 2) )
    {
      *(_BYTE *)a4 = 1;
      v31 = 1;
    }
    goto LABEL_41;
  }
  if ( v29 > 2u )
  {
    v37 = *((_WORD *)&v47 + v29 + 2);
    if ( *((_WORD *)&v47 + v29 + 1) != v37 && v37 != *((_WORD *)&v47 + v29 + 3) )
    {
      *(_BYTE *)a4 = 1;
      while ( 1 )
      {
LABEL_42:
        if ( v26 >= v29 )
        {
          v38 = Destination;
          v39 = v47;
          v40 = 2 * v49[0];
          *(_WORD *)(a4 + 2) = 2 * v49[0];
          *(_WORD *)(a4 + 4) = v38->Length - v40;
          appended = PathReplaceGreedy(&Wowx86NodeString, v39, v38);
          goto LABEL_63;
        }
        v34 = *((unsigned __int16 *)&v47 + v26 + 3);
        v35 = v49[v26 - 1];
        v36 = v35 - v34;
        switch ( v26 )
        {
          case 1u:
            goto LABEL_48;
          case 2u:
            goto LABEL_56;
          case 3u:
            goto LABEL_48;
          case 4u:
LABEL_56:
            if ( !v21 )
            {
              if ( v35 != *((_WORD *)&v47 + v29 + 3) )
                goto LABEL_51;
LABEL_48:
              Source.MaximumLength = 2 * v36;
              Source.Length = 2 * v36;
              Source.Buffer = &DestinationString.Buffer[v34];
              break;
            }
            if ( v30 != 512 || v26 != v33 )
              goto LABEL_51;
            *(_DWORD *)&Source.Length = 1572888;
            Source.Buffer = L"\\WOW6432Node";
            break;
          case 5u:
            goto LABEL_48;
        }
        appended = RtlAppendUnicodeStringToString(Destination, &Source);
        if ( appended < 0 )
          goto LABEL_63;
        v21 = v41;
LABEL_51:
        ++v26;
      }
    }
  }
LABEL_41:
  if ( v31 )
    goto LABEL_42;
LABEL_63:
  if ( DestinationString.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, DestinationString.Buffer);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18001dea8  push    rbp
0x18001deaa  push    rbx
0x18001deab  push    rsi
0x18001deac  push    rdi
0x18001dead  push    r12
0x18001deaf  push    r13
0x18001deb1  push    r14
0x18001deb3  push    r15
0x18001deb5  lea     rbp, [rsp-0Fh]
0x18001deba  sub     rsp, 88h
0x18001dec1  mov     rax, cs:__security_cookie
0x18001dec8  xor     rax, rsp
0x18001decb  mov     [rbp+47h+var_48], rax
0x18001decf  xor     eax, eax
0x18001ded1  mov     [rbp+47h+Destination], r8
0x18001ded5  mov     [r9+2], eax
0x18001ded9  xorps   xmm0, xmm0
0x18001dedc  mov     [r9+8], eax
0x18001dee0  xorps   xmm1, xmm1
0x18001dee3  mov     eax, [rbp+47h+arg_20]
0x18001dee6  mov     rdi, r9
0x18001dee9  add     eax, 0FFFFFF00h
0x18001deee  mov     [rbp+47h+var_8F], 0
0x18001def2  mov     byte ptr [r9], 0
0x18001def6  mov     r14, rdx
0x18001def9  mov     r15, rcx
0x18001defc  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm0
0x18001df00  movups  xmmword ptr [rbp+47h+Source.Length], xmm1
0x18001df04  test    eax, 0FFFFFEFFh
0x18001df09  jnz     loc_18001E2A9
0x18001df0f  movzx   ecx, [rbp+47h+arg_28]
0x18001df13  sub     ecx, 14Ch
0x18001df19  jz      short loc_18001DF35
0x18001df1b  cmp     ecx, 78h ; 'x'
0x18001df1e  jnz     loc_18001E2A9
0x18001df24  movzx   r8d, cs:WowArmNodeString
0x18001df2c  lea     r12, WowArmNodeString
0x18001df33  jmp     short loc_18001DF44
0x18001df35  movzx   r8d, cs:Wowx86NodeString
0x18001df3d  lea     r12, Wowx86NodeString
0x18001df44  movzx   eax, word ptr [rdx]
0x18001df47  xor     edx, edx
0x18001df49  movzx   ecx, r8w
0x18001df4d  div     ecx
0x18001df4f  mov     [rbp+47h+var_60], r12
0x18001df53  mov     ecx, eax
0x18001df55  mov     eax, 18h
0x18001df5a  cmp     r8w, ax
0x18001df5e  jbe     short loc_18001DF70
0x18001df60  sub     r8w, ax
0x18001df64  movzx   eax, cx
0x18001df67  movzx   esi, r8w
0x18001df6b  imul    esi, eax
0x18001df6e  jmp     short loc_18001DF7D
0x18001df70  sub     ax, r8w
0x18001df74  movzx   ecx, cx
0x18001df77  movzx   esi, ax
0x18001df7a  imul    esi, ecx
0x18001df7d  mov     rcx, gs:60h
0x18001df86  xor     edx, edx; Flags
0x18001df88  movzx   ebx, word ptr [r14+2]
0x18001df8d  movzx   r8d, si
0x18001df91  add     r8, rbx; Size
0x18001df94  mov     rcx, [rcx+30h]; HeapHandle
0x18001df98  call    cs:__imp_RtlAllocateHeap
0x18001df9e  add     bx, si
0x18001dfa1  xorps   xmm0, xmm0
0x18001dfa4  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm0
0x18001dfa8  mov     [rbp+47h+DestinationString.MaximumLength], bx
0x18001dfac  mov     [rbp+47h+DestinationString.Buffer], rax
0x18001dfb0  test    rax, rax
0x18001dfb3  jnz     short loc_18001DFBF
0x18001dfb5  mov     eax, 0C0000017h
0x18001dfba  jmp     loc_18001E2AE
0x18001dfbf  mov     rdx, r14; SourceString
0x18001dfc2  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x18001dfc6  call    cs:__imp_RtlCopyUnicodeString
0x18001dfcc  lea     r8, [rbp+47h+DestinationString]
0x18001dfd0  mov     rcx, r12
0x18001dfd3  lea     rdx, Wowx86NodeString
0x18001dfda  call    PathReplaceGreedy
0x18001dfdf  mov     r13d, eax
0x18001dfe2  test    eax, eax
0x18001dfe4  js      loc_18001E286
0x18001dfea  movzx   r14d, [rbp+47h+DestinationString.Length]
0x18001dfef  xor     ecx, ecx
0x18001dff1  mov     r12, [rbp+47h+DestinationString.Buffer]
0x18001dff5  xor     esi, esi
0x18001dff7  shr     r14w, 1
0x18001dffb  xor     r11b, r11b
0x18001dffe  mov     [rbp+47h+var_58], cx
0x18001e002  mov     [rbp+47h+var_90], r11b
0x18001e006  lea     ebx, [rcx+1]
0x18001e009  lea     r10d, [rcx+2]
0x18001e00d  test    r15, r15
0x18001e010  jz      loc_18001E0BD
0x18001e016  xor     eax, eax
0x18001e018  lea     r9, [rbp+47h+var_8C]
0x18001e01c  mov     [rbp+47h+var_8C], ax
0x18001e020  movzx   r8d, r14w
0x18001e024  lea     rax, [rbp+47h+var_8F]
0x18001e028  mov     rdx, r12
0x18001e02b  mov     rcx, r15
0x18001e02e  mov     [rsp+0C0h+var_A0], rax
0x18001e033  call    LookupRedirectionNode
0x18001e038  mov     r15, rax
0x18001e03b  mov     r10d, 2
0x18001e041  test    rax, rax
0x18001e044  jz      short loc_18001E0AE
0x18001e046  movzx   edx, [rbp+47h+var_8C]
0x18001e04a  sub     r14w, dx
0x18001e04e  add     si, dx
0x18001e051  lea     r12, [r12+rdx*2]
0x18001e055  mov     edx, [rax+24h]
0x18001e058  test    r10b, dl
0x18001e05b  jz      short loc_18001E067
0x18001e05d  movzx   ecx, bx
0x18001e060  mov     [rbp+rcx*2+47h+var_58], si
0x18001e065  jmp     short loc_18001E077
0x18001e067  test    dl, 4
0x18001e06a  jz      short loc_18001E080
0x18001e06c  movzx   ecx, bx
0x18001e06f  lea     eax, [rsi-0Ch]
0x18001e072  mov     [rbp+rcx*2+47h+var_58], ax
0x18001e077  add     bx, r10w
0x18001e07b  mov     [rbp+rcx*2+47h+var_56], si
0x18001e080  mov     r11b, dl
0x18001e083  mov     eax, 1
0x18001e088  and     r11b, al
0x18001e08b  mov     [rbp+47h+var_90], r11b
0x18001e08f  test    dl, 8
0x18001e092  jz      short loc_18001E097
0x18001e094  or      [rdi+8], eax
0x18001e097  mov     r15, [r15+8]
0x18001e09b  test    r15, r15
0x18001e09e  jnz     loc_18001E016
0x18001e0a4  bts     dword ptr [rdi+8], 0Ah
0x18001e0a9  jmp     loc_18001E00D
0x18001e0ae  cmp     [rbp+47h+var_8F], 0
0x18001e0b2  mov     r11b, [rbp+47h+var_90]
0x18001e0b6  jz      short loc_18001E0BD
0x18001e0b8  bts     dword ptr [rdi+8], 0Ah
0x18001e0bd  movzx   ecx, [rbp+47h+DestinationString.Length]
0x18001e0c1  mov     esi, 1
0x18001e0c6  movzx   eax, bx
0x18001e0c9  movzx   edx, r10w
0x18001e0cd  shr     cx, 1
0x18001e0d0  add     bx, si
0x18001e0d3  mov     [rbp+rax*2+47h+var_58], cx
0x18001e0d8  mov     r14d, 200h
0x18001e0de  cmp     dx, bx
0x18001e0e1  jnb     short loc_18001E104
0x18001e0e3  movzx   ecx, dx
0x18001e0e6  movzx   eax, [rbp+rcx*2+47h+var_58]
0x18001e0eb  cmp     word ptr [rbp+rcx*2+47h+var_60+6], ax
0x18001e0f0  jnz     short loc_18001E0F8
0x18001e0f2  add     dx, r10w
0x18001e0f6  jmp     short loc_18001E0D8
0x18001e0f8  or      dword ptr [rdi+8], 0A00h
0x18001e0ff  mov     r12d, r14d
0x18001e102  jmp     short loc_18001E108
0x18001e104  mov     r12d, [rbp+47h+arg_20]
0x18001e108  mov     dl, [rdi]
0x18001e10a  movzx   r8d, r10w
0x18001e10e  movzx   r9d, bx
0x18001e112  lea     r15d, [r9-2]
0x18001e116  cmp     r15d, r10d
0x18001e119  jle     short loc_18001E13C
0x18001e11b  movzx   ecx, r8w
0x18001e11f  movzx   edx, dl
0x18001e122  movzx   eax, [rbp+rcx*2+47h+var_58]
0x18001e127  cmp     word ptr [rbp+rcx*2+47h+var_60+6], ax
0x18001e12c  cmovnz  edx, esi
0x18001e12f  add     r8w, r10w
0x18001e133  movzx   eax, r8w
0x18001e137  cmp     eax, r15d
0x18001e13a  jl      short loc_18001E11B
0x18001e13c  mov     [rdi], dl
0x18001e13e  test    r11b, r11b
0x18001e141  jz      loc_18001E1EF
0x18001e147  cmp     r12d, r14d
0x18001e14a  jnz     loc_18001E1EF
0x18001e150  cmp     r10w, bx
0x18001e154  jnb     short loc_18001E16B
0x18001e156  movsxd  rcx, r9d
0x18001e159  movzx   eax, word ptr [rbp+rcx*2+47h+var_60+4]
0x18001e15e  cmp     word ptr [rbp+rcx*2+47h+var_60+2], ax
0x18001e163  jnz     short loc_18001E16B
0x18001e165  mov     [rdi], sil
0x18001e168  mov     dl, sil
0x18001e16b  test    dl, dl
0x18001e16d  jz      loc_18001E286
0x18001e173  mov     r14, r9
0x18001e176  cmp     si, bx
0x18001e179  jnb     loc_18001E253
0x18001e17f  movzx   r8d, si
0x18001e183  movzx   eax, si
0x18001e186  mov     ecx, r8d
0x18001e189  movzx   r9d, word ptr [rbp+r8*2+47h+var_60+6]
0x18001e18f  movzx   r10d, [rbp+rax*2+47h+var_58]
0x18001e195  movzx   edx, r10w
0x18001e199  sub     dx, r9w
0x18001e19d  sub     ecx, 1
0x18001e1a0  jz      short loc_18001E1B6
0x18001e1a2  sub     ecx, 1
0x18001e1a5  jz      short loc_18001E21F
0x18001e1a7  sub     ecx, 1
0x18001e1aa  jz      short loc_18001E1B6
0x18001e1ac  sub     ecx, 1
0x18001e1af  jz      short loc_18001E21F
0x18001e1b1  cmp     ecx, 1
0x18001e1b4  jnz     short loc_18001E1CD
0x18001e1b6  mov     rax, [rbp+47h+DestinationString.Buffer]
0x18001e1ba  add     dx, dx
0x18001e1bd  mov     [rbp+47h+Source.MaximumLength], dx
0x18001e1c1  mov     [rbp+47h+Source.Length], dx
0x18001e1c5  lea     rcx, [rax+r9*2]
0x18001e1c9  mov     [rbp+47h+Source.Buffer], rcx
0x18001e1cd  mov     rcx, [rbp+47h+Destination]; Destination
0x18001e1d1  lea     rdx, [rbp+47h+Source]; Source
0x18001e1d5  call    cs:__imp_RtlAppendUnicodeStringToString
0x18001e1db  mov     r13d, eax
0x18001e1de  test    eax, eax
0x18001e1e0  js      loc_18001E286
0x18001e1e6  mov     r11b, [rbp+47h+var_90]
0x18001e1ea  inc     si
0x18001e1ed  jmp     short loc_18001E176
0x18001e1ef  cmp     r10w, bx
0x18001e1f3  jnb     loc_18001E16B
0x18001e1f9  movsxd  rax, r9d
0x18001e1fc  movzx   ecx, word ptr [rbp+rax*2+47h+var_60+4]
0x18001e201  cmp     word ptr [rbp+rax*2+47h+var_60+2], cx
0x18001e206  jz      loc_18001E16B
0x18001e20c  cmp     cx, word ptr [rbp+rax*2+47h+var_60+6]
0x18001e211  jz      loc_18001E16B
0x18001e217  mov     [rdi], sil
0x18001e21a  jmp     loc_18001E173
0x18001e21f  test    r11b, r11b
0x18001e222  jnz     short loc_18001E22E
0x18001e224  cmp     r10w, word ptr [rbp+r14*2+47h+var_60+6]
0x18001e22a  jnz     short loc_18001E1EA
0x18001e22c  jmp     short loc_18001E1B6
0x18001e22e  cmp     r12d, 200h
0x18001e235  jnz     short loc_18001E1EA
0x18001e237  cmp     r8d, r15d
0x18001e23a  jnz     short loc_18001E1EA
0x18001e23c  lea     rax, aWow6432node; "\\WOW6432Node"
0x18001e243  mov     dword ptr [rbp+47h+Source.Length], 180018h
0x18001e24a  mov     [rbp+47h+Source.Buffer], rax
0x18001e24e  jmp     loc_18001E1CD
0x18001e253  mov     rcx, [rbp+47h+Destination]
0x18001e257  movzx   r9d, [rbp+47h+var_56]
0x18001e25c  mov     r8, rcx
0x18001e25f  mov     rdx, [rbp+47h+var_60]
0x18001e263  add     r9w, r9w
0x18001e267  mov     [rdi+2], r9w
0x18001e26c  movzx   eax, word ptr [rcx]
0x18001e26f  lea     rcx, Wowx86NodeString
0x18001e276  sub     ax, r9w
0x18001e27a  mov     [rdi+4], ax
0x18001e27e  call    PathReplaceGreedy
0x18001e283  mov     r13d, eax
0x18001e286  mov     r8, [rbp+47h+DestinationString.Buffer]; P
0x18001e28a  test    r8, r8
0x18001e28d  jz      short loc_18001E2A4
0x18001e28f  mov     rcx, gs:60h
0x18001e298  xor     edx, edx; Flags
0x18001e29a  mov     rcx, [rcx+30h]; HeapHandle
0x18001e29e  call    cs:__imp_RtlFreeHeap
0x18001e2a4  mov     eax, r13d
0x18001e2a7  jmp     short loc_18001E2AE
0x18001e2a9  mov     eax, 0C000000Dh
0x18001e2ae  mov     rcx, [rbp+47h+var_48]
0x18001e2b2  xor     rcx, rsp; StackCookie
0x18001e2b5  call    __security_check_cookie
0x18001e2ba  add     rsp, 88h
0x18001e2c1  pop     r15
0x18001e2c3  pop     r14
0x18001e2c5  pop     r13
0x18001e2c7  pop     r12
0x18001e2c9  pop     rdi
0x18001e2ca  pop     rsi
0x18001e2cb  pop     rbx
0x18001e2cc  pop     rbp
0x18001e2cd  retn
```
