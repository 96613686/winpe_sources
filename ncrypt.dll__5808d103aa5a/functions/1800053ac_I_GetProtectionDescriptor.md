# I_GetProtectionDescriptor

- ea: `0x1800053ac`
- end: `0x1800058a7`
- name: `I_GetProtectionDescriptor`
- size: `1275`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18000260c`
- `0x180007274`

## callees

- `0x180004a70`
- `0x1800053ac`
- `0x1800058b0`
- `0x180007958`
- `0x180007ae0`
- `0x18000d02c`
- `0x18000e120`
- `0x18001f151`
- `0x18001f175`
- `0x180020010`

## import_xrefs

- `NTASN1!__imp_RtlAsn1DecodeAndAllocate` at `0x18000546c`
- `NTASN1!__imp_RtlAsn1DecodeAndAllocate` at `0x180005514`
- `NTASN1!__imp_RtlAsn1DecodeAndAllocate` at `0x18000546c`
- `NTASN1!__imp_RtlAsn1DecodeAndAllocate` at `0x180005514`

## string_xrefs

- `0x180005472`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\ncryptcms.c`
- `0x1800057f2`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\ncryptcms.c`
- `0x180005867`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\ncryptcms.c`
- `0x18000562e`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`
- `0x180005699`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`
- `0x1800056ed`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`
- `0x1800057ba`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`
- `0x180005838`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`

## pseudocode

```c
__int64 __fastcall I_GetProtectionDescriptor(__int64 a1, unsigned int a2, __int64 a3, _QWORD *a4)
{
  __int64 v4; // rsi
  __int64 v5; // rdi
  _DWORD *v9; // rax
  _DWORD *v10; // r14
  __int64 v11; // rcx
  char *v12; // r12
  unsigned int v13; // eax
  unsigned int DescriptorFromMessage; // ebx
  __int64 i; // rbx
  __int64 v16; // rdx
  _DWORD *v17; // rdi
  __int64 v18; // rax
  __int64 v19; // rbp
  int v20; // edx
  int v21; // r8d
  _QWORD *v22; // rcx
  PVOID *v23; // rcx
  PVOID *v25; // rcx
  char v26; // [rsp+30h] [rbp-58h]
  __int64 v27; // [rsp+A8h] [rbp+20h] BYREF

  v4 = 0;
  v5 = a2;
  v27 = 0;
  *a4 = 0;
  if ( a3 && *(_DWORD *)a3 == 24 )
  {
    v9 = (_DWORD *)(*(__int64 (__fastcall **)(__int64))(a3 + 8))(368);
    v10 = v9;
    if ( v9 )
    {
      memset_0(v9, 0, 0x170u);
      v11 = ASN1_NCRYPT_MODULE_HANDLE;
      v12 = (char *)(v10 + 14);
      *v10 = 368;
      v10[4] = 24;
      *((_QWORD *)v10 + 3) = *(_QWORD *)(a3 + 8);
      *((_QWORD *)v10 + 4) = *(_QWORD *)(a3 + 16);
      v10[2] = 1;
      v13 = RtlAsn1DecodeAndAllocate(v11, 20, 5, a1, v5, v10 + 12, v10 + 4, v10 + 14);
      DescriptorFromMessage = v13;
      if ( v13 )
      {
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v26 = 3;
LABEL_22:
          WPP_SF_sDsd(
            v22[2],
            a2,
            a3,
            (unsigned int)"Status",
            v13,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\ncryptcms.c",
            v26);
        }
      }
      else
      {
        for ( i = 0; !i; i = 1 )
        {
          if ( **(_DWORD **)v12 == 11 && !memcmp_0(*(const void **)(*(_QWORD *)v12 + 8LL), qword_180023BC8, 0xBu) )
          {
            *((_QWORD *)v10 + 8) = &off_180021000;
            break;
          }
        }
        v16 = *((_QWORD *)v10 + 8);
        if ( v16 )
        {
          v13 = RtlAsn1DecodeAndAllocate(
                  ASN1_NCRYPT_MODULE_HANDLE,
                  *(unsigned int *)(v16 + 24),
                  5,
                  *(_QWORD *)(*(_QWORD *)v12 + 24LL),
                  *(unsigned int *)(*(_QWORD *)v12 + 16LL),
                  0,
                  v10 + 4,
                  v10 + 52);
          DescriptorFromMessage = v13;
          if ( !v13 )
          {
            v17 = v10;
            if ( *v10 == 368 )
            {
              v18 = *((_QWORD *)v10 + 8);
              if ( v18 )
                LODWORD(v18) = *(_DWORD *)(v18 + 28);
              if ( (_DWORD)v18 == 3 )
              {
                v19 = *((_QWORD *)v10 + 26);
                DescriptorFromMessage = CNG_GetDescriptorFromMessage(v19, &v27);
                if ( DescriptorFromMessage )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    WPP_SF_sDsd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      v20,
                      v21,
                      (unsigned int)"Status",
                      DescriptorFromMessage,
                      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
                      171);
                  v4 = v27;
                }
                else
                {
                  v4 = v27;
                  if ( v27 )
                  {
                    *(_QWORD *)(v27 + 32) = v19;
                    *(_QWORD *)(v4 + 24) = v10;
                    *a4 = v4;
                    v4 = 0;
                    goto LABEL_31;
                  }
                  DescriptorFromMessage = -2146893814;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    WPP_SF_sDsd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      v20,
                      v21,
                      (unsigned int)"Status",
                      10,
                      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
                      182);
                }
              }
              else
              {
                DescriptorFromMessage = -2146893819;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_sDsd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    a2,
                    a3,
                    (unsigned int)"Status",
                    5,
                    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
                    144);
              }
LABEL_41:
              NCryptMsgClose(v17);
LABEL_31:
              if ( v4 )
                NCryptCloseProtectionDescriptor(v4);
              return DescriptorFromMessage;
            }
LABEL_24:
            v23 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  a2,
                  a3,
                  (unsigned int)"Status",
                  38,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\ncryptcms.c",
                  96);
                v23 = (PVOID *)WPP_GLOBAL_Control;
              }
              if ( v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 1) != 0 )
                WPP_SF_sDsd(
                  (unsigned int)v23[2],
                  a2,
                  a3,
                  (unsigned int)"Status",
                  38,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
                  137);
            }
            DescriptorFromMessage = -2146893786;
            if ( !v17 )
              goto LABEL_31;
            goto LABEL_41;
          }
          v22 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_23;
          v26 = 42;
          goto LABEL_22;
        }
        DescriptorFromMessage = -2146893783;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            0,
            a3,
            (unsigned int)"Status",
            41,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\ncryptcms.c",
            26);
      }
LABEL_23:
      v17 = 0;
      I_CMsgFree(v10);
      if ( !DescriptorFromMessage )
        goto LABEL_24;
      goto LABEL_54;
    }
    DescriptorFromMessage = -2146893810;
    DebugTraceError(
      2148073486LL,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\ncryptcms.c",
      225);
  }
  else
  {
    DescriptorFromMessage = -2146893785;
    v25 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return DescriptorFromMessage;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_55;
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      a3,
      (unsigned int)"Status",
      39,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\ncryptcms.c",
      212);
  }
LABEL_54:
  v25 = (PVOID *)WPP_GLOBAL_Control;
LABEL_55:
  if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 1) != 0 )
    WPP_SF_sDsd(
      (unsigned int)v25[2],
      a2,
      a3,
      (unsigned int)"Status",
      DescriptorFromMessage,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
      124);
  return DescriptorFromMessage;
}

```

## disassembly

```asm
0x1800053ac  mov     rax, rsp
0x1800053af  push    rbx
0x1800053b0  push    rbp
0x1800053b1  push    rsi
0x1800053b2  push    rdi
0x1800053b3  push    r12
0x1800053b5  push    r13
0x1800053b7  push    r14
0x1800053b9  push    r15
0x1800053bb  sub     rsp, 48h
0x1800053bf  xor     esi, esi
0x1800053c1  mov     edi, edx
0x1800053c3  mov     [rax+20h], rsi
0x1800053c7  mov     r15, r9
0x1800053ca  mov     [r9], rsi
0x1800053cd  mov     rbx, r8
0x1800053d0  lea     r12, WPP_GLOBAL_Control
0x1800053d7  mov     rbp, rcx
0x1800053da  test    r8, r8
0x1800053dd  jz      loc_1800057D3
0x1800053e3  cmp     dword ptr [r8], 18h
0x1800053e7  jnz     loc_1800057D3
0x1800053ed  mov     rax, [r8+8]
0x1800053f1  mov     r13d, 170h
0x1800053f7  mov     ecx, r13d
0x1800053fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053ff  mov     r14, rax
0x180005402  test    rax, rax
0x180005405  jz      loc_180005861
0x18000540b  mov     r8d, r13d; Size
0x18000540e  xor     edx, edx; Val
0x180005410  mov     rcx, rax; void *
0x180005413  call    memset_0
0x180005418  mov     rcx, cs:ASN1_NCRYPT_MODULE_HANDLE
0x18000541f  lea     r12, [r14+38h]
0x180005423  mov     [r14], r13d
0x180005426  lea     edx, [rsi+14h]
0x180005429  mov     [rsp+88h+var_50], r12
0x18000542e  lea     r13, [r14+10h]
0x180005432  mov     dword ptr [r13+0], 18h
0x18000543a  lea     r8d, [rsi+5]
0x18000543e  mov     rax, [rbx+8]
0x180005442  mov     r9, rbp
0x180005445  mov     [r14+18h], rax
0x180005449  mov     rax, [rbx+10h]
0x18000544d  mov     [r14+20h], rax
0x180005451  lea     rax, [r14+30h]
0x180005455  mov     [rsp+88h+var_58], r13
0x18000545a  mov     [rsp+88h+var_60], rax
0x18000545f  mov     [rsp+88h+var_68], rdi
0x180005464  mov     dword ptr [r14+8], 1
0x18000546c  call    cs:__imp_RtlAsn1DecodeAndAllocate
0x180005472  lea     rbp, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005479  mov     ebx, eax
0x18000547b  test    eax, eax
0x18000547d  jnz     loc_18000575E
0x180005483  xor     ebx, ebx
0x180005485  lea     rdx, off_180021000; "1.2.840.113549.1.7.3"
0x18000548c  cmp     rbx, 1
0x180005490  jnb     short loc_1800054D0
0x180005492  mov     rcx, [r12]
0x180005496  mov     rdi, rbx
0x180005499  shl     rdi, 5
0x18000549d  mov     eax, [rdi+rdx+8]
0x1800054a1  cmp     eax, [rcx]
0x1800054a3  jnz     loc_18000588D
0x1800054a9  mov     rdx, [rdi+rdx+10h]; Buf2
0x1800054ae  mov     r8d, eax; Size
0x1800054b1  mov     rcx, [rcx+8]; Buf1
0x1800054b5  call    memcmp_0
0x1800054ba  test    eax, eax
0x1800054bc  jnz     loc_180005886
0x1800054c2  lea     rax, off_180021000; "1.2.840.113549.1.7.3"
0x1800054c9  add     rax, rdi
0x1800054cc  mov     [r14+40h], rax
0x1800054d0  mov     rdx, [r14+40h]
0x1800054d4  test    rdx, rdx
0x1800054d7  jz      loc_18000571E
0x1800054dd  mov     r9, [r12]
0x1800054e1  lea     rax, [r14+0D0h]
0x1800054e8  mov     edx, [rdx+18h]
0x1800054eb  mov     r8d, 5
0x1800054f1  mov     [rsp+88h+var_50], rax
0x1800054f6  mov     [rsp+88h+var_58], r13
0x1800054fb  mov     ecx, [r9+10h]
0x1800054ff  mov     r9, [r9+18h]
0x180005503  mov     [rsp+88h+var_60], rsi
0x180005508  mov     [rsp+88h+var_68], rcx
0x18000550d  mov     rcx, cs:ASN1_NCRYPT_MODULE_HANDLE
0x180005514  call    cs:__imp_RtlAsn1DecodeAndAllocate
0x18000551a  mov     ebx, eax
0x18000551c  test    eax, eax
0x18000551e  jnz     short loc_18000558D
0x180005520  cmp     dword ptr [r14], 170h
0x180005527  mov     rdi, r14
0x18000552a  jnz     loc_1800055D9
0x180005530  mov     rax, [r14+40h]
0x180005534  test    rax, rax
0x180005537  jz      loc_180005895
0x18000553d  mov     eax, [rax+1Ch]
0x180005540  cmp     eax, 3
0x180005543  jnz     loc_18000578C
0x180005549  mov     rbp, [r14+0D0h]
0x180005550  lea     rdx, [rsp+88h+arg_18]
0x180005558  mov     rcx, rbp
0x18000555b  call    CNG_GetDescriptorFromMessage
0x180005560  mov     ebx, eax
0x180005562  test    eax, eax
0x180005564  jnz     loc_18000567C
0x18000556a  mov     rsi, [rsp+88h+arg_18]
0x180005572  test    rsi, rsi
0x180005575  jz      loc_1800056C7
0x18000557b  mov     [rsi+20h], rbp
0x18000557f  mov     [rsi+18h], r14
0x180005583  mov     [r15], rsi
0x180005586  xor     esi, esi
0x180005588  jmp     loc_180005660
0x18000558d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005594  lea     r12, WPP_GLOBAL_Control
0x18000559b  cmp     rcx, r12
0x18000559e  jz      short loc_1800055C7
0x1800055a0  test    byte ptr [rcx+1Ch], 1
0x1800055a4  jz      short loc_1800055C7
0x1800055a6  mov     dword ptr [rsp+88h+var_58], 12Ah
0x1800055ae  mov     [rsp+88h+var_60], rbp
0x1800055b3  mov     dword ptr [rsp+88h+var_68], eax
0x1800055b7  mov     rcx, [rcx+10h]
0x1800055bb  lea     r9, aStatus; "Status"
0x1800055c2  call    WPP_SF_sDsd
0x1800055c7  mov     rcx, r14
0x1800055ca  xor     edi, edi
0x1800055cc  call    I_CMsgFree
0x1800055d1  test    ebx, ebx
0x1800055d3  jnz     loc_18000581A
0x1800055d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800055e0  lea     r14, WPP_GLOBAL_Control
0x1800055e7  mov     ebx, 80090026h
0x1800055ec  cmp     rcx, r14
0x1800055ef  jz      short loc_180005652
0x1800055f1  test    byte ptr [rcx+1Ch], 1
0x1800055f5  jz      short loc_18000561F
0x1800055f7  mov     rcx, [rcx+10h]
0x1800055fb  lea     r9, aStatus; "Status"
0x180005602  mov     dword ptr [rsp+88h+var_58], 260h
0x18000560a  mov     [rsp+88h+var_60], rbp
0x18000560f  mov     dword ptr [rsp+88h+var_68], ebx
0x180005613  call    WPP_SF_sDsd
0x180005618  mov     rcx, cs:WPP_GLOBAL_Control
0x18000561f  cmp     rcx, r14
0x180005622  jz      short loc_180005652
0x180005624  test    byte ptr [rcx+1Ch], 1
0x180005628  jz      short loc_180005652
0x18000562a  mov     rcx, [rcx+10h]
0x18000562e  lea     rax, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005635  mov     dword ptr [rsp+88h+var_58], 589h
0x18000563d  lea     r9, aStatus; "Status"
0x180005644  mov     [rsp+88h+var_60], rax
0x180005649  mov     dword ptr [rsp+88h+var_68], ebx
0x18000564d  call    WPP_SF_sDsd
0x180005652  mov     ebx, 80090026h
0x180005657  test    rdi, rdi
0x18000565a  jnz     loc_180005711
0x180005660  test    rsi, rsi
0x180005663  jnz     loc_18000589A
0x180005669  mov     eax, ebx
0x18000566b  add     rsp, 48h
0x18000566f  pop     r15
0x180005671  pop     r14
0x180005673  pop     r13
0x180005675  pop     r12
0x180005677  pop     rdi
0x180005678  pop     rsi
0x180005679  pop     rbp
0x18000567a  pop     rbx
0x18000567b  retn
0x18000567c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005683  lea     r14, WPP_GLOBAL_Control
0x18000568a  cmp     rcx, r14
0x18000568d  jz      short loc_1800056BD
0x18000568f  test    byte ptr [rcx+1Ch], 1
0x180005693  jz      short loc_1800056BD
0x180005695  mov     rcx, [rcx+10h]
0x180005699  lea     rax, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800056a0  mov     dword ptr [rsp+88h+var_58], 5ABh
0x1800056a8  lea     r9, aStatus; "Status"
0x1800056af  mov     [rsp+88h+var_60], rax
0x1800056b4  mov     dword ptr [rsp+88h+var_68], ebx
0x1800056b8  call    WPP_SF_sDsd
0x1800056bd  mov     rsi, [rsp+88h+arg_18]
0x1800056c5  jmp     short loc_180005711
0x1800056c7  mov     ebx, 8009000Ah
0x1800056cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800056d3  lea     r14, WPP_GLOBAL_Control
0x1800056da  cmp     rcx, r14
0x1800056dd  jz      short loc_180005711
0x1800056df  test    byte ptr [rcx+1Ch], 1
0x1800056e3  jz      short loc_180005711
0x1800056e5  mov     dword ptr [rsp+88h+var_58], 5B6h
0x1800056ed  lea     rax, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800056f4  mov     [rsp+88h+var_60], rax
0x1800056f9  mov     dword ptr [rsp+88h+var_68], 8009000Ah
0x180005701  mov     rcx, [rcx+10h]
0x180005705  lea     r9, aStatus; "Status"
0x18000570c  call    WPP_SF_sDsd
0x180005711  mov     rcx, rdi
0x180005714  call    NCryptMsgClose
0x180005719  jmp     loc_180005660
0x18000571e  mov     ebx, 80090029h
0x180005723  mov     rcx, cs:WPP_GLOBAL_Control
0x18000572a  lea     r12, WPP_GLOBAL_Control
0x180005731  cmp     rcx, r12
0x180005734  jz      loc_1800055C7
0x18000573a  test    byte ptr [rcx+1Ch], 1
0x18000573e  jz      loc_1800055C7
0x180005744  mov     dword ptr [rsp+88h+var_58], 11Ah
0x18000574c  mov     [rsp+88h+var_60], rbp
0x180005751  mov     dword ptr [rsp+88h+var_68], 80090029h
0x180005759  jmp     loc_1800055B7
0x18000575e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005765  lea     r12, WPP_GLOBAL_Control
0x18000576c  cmp     rcx, r12
0x18000576f  jz      loc_1800055C7
0x180005775  test    byte ptr [rcx+1Ch], 1
0x180005779  jz      loc_1800055C7
0x18000577f  mov     dword ptr [rsp+88h+var_58], 103h
0x180005787  jmp     loc_1800055AE
0x18000578c  mov     ebx, 80090005h
0x180005791  mov     rcx, cs:WPP_GLOBAL_Control
0x180005798  lea     r14, WPP_GLOBAL_Control
0x18000579f  cmp     rcx, r14
0x1800057a2  jz      loc_180005711
0x1800057a8  test    byte ptr [rcx+1Ch], 1
0x1800057ac  jz      loc_180005711
0x1800057b2  mov     dword ptr [rsp+88h+var_58], 590h
0x1800057ba  lea     rax, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800057c1  mov     [rsp+88h+var_60], rax
0x1800057c6  mov     dword ptr [rsp+88h+var_68], 80090005h
0x1800057ce  jmp     loc_180005701
0x1800057d3  mov     ebx, 80090027h
0x1800057d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800057df  cmp     rcx, r12
0x1800057e2  jz      loc_180005669
0x1800057e8  test    byte ptr [rcx+1Ch], 1
0x1800057ec  jz      short loc_180005821
0x1800057ee  mov     rcx, [rcx+10h]
0x1800057f2  lea     rbp, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800057f9  mov     dword ptr [rsp+88h+var_58], 0D4h
0x180005801  lea     r9, aStatus; "Status"
0x180005808  mov     [rsp+88h+var_60], rbp
0x18000580d  mov     dword ptr [rsp+88h+var_68], 80090027h
0x180005815  call    WPP_SF_sDsd
0x18000581a  mov     rcx, cs:WPP_GLOBAL_Control
0x180005821  cmp     rcx, r12
0x180005824  jz      loc_180005669
0x18000582a  test    byte ptr [rcx+1Ch], 1
0x18000582e  jz      loc_180005669
0x180005834  mov     rcx, [rcx+10h]
0x180005838  lea     rax, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000583f  mov     dword ptr [rsp+88h+var_58], 57Ch
0x180005847  lea     r9, aStatus; "Status"
0x18000584e  mov     [rsp+88h+var_60], rax
0x180005853  mov     dword ptr [rsp+88h+var_68], ebx
0x180005857  call    WPP_SF_sDsd
0x18000585c  jmp     loc_180005669
0x180005861  mov     r9d, 0E1h
0x180005867  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000586e  lea     rdx, aStatus; "Status"
0x180005875  mov     ecx, 8009000Eh
0x18000587a  mov     ebx, 8009000Eh
0x18000587f  call    DebugTraceError
0x180005884  jmp     short loc_18000581A
0x180005886  lea     rdx, off_180021000; "1.2.840.113549.1.7.3"
0x18000588d  inc     rbx
0x180005890  jmp     loc_18000548C
0x180005895  jmp     loc_180005540
0x18000589a  mov     rcx, rsi
0x18000589d  call    NCryptCloseProtectionDescriptor
0x1800058a2  jmp     loc_180005669
```
