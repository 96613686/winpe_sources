# SPSslExpandPreSharedKey

- ea: `0x180005240`
- end: `0x180005858`
- name: `SPSslExpandPreSharedKey`
- size: `1560`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003ef0`
- `0x180005240`
- `0x180005860`
- `0x18000b594`
- `0x18000b654`
- `0x180020cb4`
- `0x180024fb0`

## import_xrefs

- `bcrypt!BCryptKeyDerivation` at `0x180005527`
- `bcrypt!BCryptKeyDerivation` at `0x180005527`
- `ntdll!RtlFreeHeap` at `0x18000560f`
- `ntdll!RtlFreeHeap` at `0x18000560f`
- `ntdll!RtlAllocateHeap` at `0x180005381`
- `ntdll!RtlAllocateHeap` at `0x180005483`
- `ntdll!RtlAllocateHeap` at `0x180005381`
- `ntdll!RtlAllocateHeap` at `0x180005483`

## string_xrefs

- `0x18000555d`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800055a9`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800057a9`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180005698`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800056f7`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000574a`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800057d1`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000580e`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180005830`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslExpandPreSharedKey(
        _DWORD *a1,
        _DWORD *a2,
        const void *a3,
        unsigned int a4,
        _QWORD *a5,
        __int64 a6,
        int a7)
{
  unsigned __int8 v7; // r14
  _DWORD *v9; // rbp
  __int64 v10; // rcx
  _QWORD *v11; // rdi
  wchar_t *v12; // rcx
  __int64 HashInfoFromAlgorithmName; // rax
  int v14; // edx
  int v15; // r8d
  unsigned int v16; // r13d
  size_t v17; // rdx
  _DWORD *v18; // rsi
  __int64 v19; // rbx
  unsigned __int8 v20; // al
  int v21; // edx
  int v22; // r8d
  unsigned __int8 v23; // bl
  SIZE_T v24; // rsi
  _BYTE *v25; // rax
  int v26; // edx
  int v27; // r8d
  _BYTE *v28; // rdi
  int v29; // edx
  int v30; // r8d
  int v31; // r14d
  unsigned int v32; // ebx
  _BYTE *v33; // rax
  _DWORD *Heap; // [rsp+48h] [rbp-80h]
  unsigned __int8 v36; // [rsp+50h] [rbp-78h]
  _BYTE *P; // [rsp+58h] [rbp-70h]
  __int64 v38; // [rsp+60h] [rbp-68h]
  _DWORD v39[2]; // [rsp+68h] [rbp-60h] BYREF
  _BYTE *v40; // [rsp+70h] [rbp-58h]
  _DWORD v41[2]; // [rsp+78h] [rbp-50h] BYREF
  _DWORD *v42; // [rsp+80h] [rbp-48h]
  int v43; // [rsp+D8h] [rbp+10h] BYREF
  char v44; // [rsp+DEh] [rbp+16h]

  v7 = a4;
  v9 = a2;
  if ( !a1 || *a1 < 0x310u || a1[1] != 1936944177 )
    a1 = 0;
  if ( !a2 || *a2 < 0x70u || a2[1] != 1936944179 )
    v9 = 0;
  if ( a1 && v9 && (v10 = *((_QWORD *)v9 + 2)) != 0 )
  {
    if ( a4 > 0xFF || (v11 = a5) == 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)a2,
          (_DWORD)a3,
          (unsigned int)"NTE_INVALID_PARAMETER",
          39,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
          5);
      return 2148073511LL;
    }
    if ( v9[2] == 772 && v9[27] == 7 )
    {
      if ( a7 )
      {
        DebugTraceError(
          2148073481LL,
          "NTE_BAD_FLAGS",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
          6929);
        return 2148073481LL;
      }
      v12 = *(wchar_t **)(v10 + 136);
      if ( !v12 || !*v12 )
        v12 = L"SHA256";
      HashInfoFromAlgorithmName = I_GetHashInfoFromAlgorithmName(v12);
      if ( HashInfoFromAlgorithmName )
      {
        v16 = *(_DWORD *)(HashInfoFromAlgorithmName + 8);
        if ( v16 > 0xFFFF )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v14,
              v15,
              (unsigned int)"NTE_INVALID_PARAMETER",
              39,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
              32);
          return 2148073511LL;
        }
      }
      else
      {
        v16 = 0;
      }
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v16 + 16);
      v18 = Heap;
      if ( !Heap )
      {
        v32 = -2146893810;
        DebugTraceError(2148073486LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", 6954);
        return v32;
      }
      v19 = *((_QWORD *)v9 + 4);
      v44 = aTls13[6];
      v38 = v19;
      v20 = strnlen_s("resumption", v17);
      v36 = v20;
      v42 = v39;
      v39[0] = 0;
      v39[1] = 20;
      v40 = 0;
      v41[0] = 0;
      v41[1] = 1;
      v43 = 0;
      if ( v19 )
      {
        v23 = v20 + 6;
        if ( v20 != 0xF9 )
        {
          if ( a3 )
          {
            if ( !v7 )
              goto LABEL_62;
          }
          else if ( v7 )
          {
            goto LABEL_62;
          }
          if ( Heap != (_DWORD *)-12LL && (_WORD)v16 )
          {
            v24 = (unsigned __int16)(v23 + v7 + 4);
            v25 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v24);
            P = v25;
            if ( v25 )
            {
              v25[2] = v23;
              v28 = v25 + 9;
              v25[1] = v16;
              *v25 = BYTE1(v16);
              qmemcpy(v25 + 3, "tls13 ", 6);
              memmove(v25 + 9, "resumption", v36);
              v28[v36] = v7;
              memmove(&v28[v36 + 1], a3, v7);
              v39[0] = v24;
              v40 = P;
              v31 = BCryptKeyDerivation(v38, v41, Heap + 3, (unsigned __int16)v16, &v43, 0);
              if ( (v31 || v43 != (unsigned __int16)v16)
                && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v29,
                  v30,
                  (unsigned int)"Status",
                  v31,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                  195);
              }
              v33 = P;
              do
              {
                *v33++ = 0;
                --v24;
              }
              while ( v24 );
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
              v11 = a5;
            }
            else
            {
              v32 = -1073741801;
              v31 = -1073741801;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v26,
                  v27,
                  (unsigned int)"Status",
                  23,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                  169);
                v18 = Heap;
                goto LABEL_65;
              }
            }
            v18 = Heap;
LABEL_45:
            v32 = v31;
            if ( v31 >= 0 )
            {
              *v18 = v16 + 16;
              v18[1] = 1936944184;
              v18[2] = v9[2];
              *v11 = v18;
              return v32;
            }
LABEL_65:
            DebugTraceError(
              (unsigned int)v31,
              "Status",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
              6967);
            MSCryptFree(v18);
            return v32;
          }
        }
      }
LABEL_62:
      v32 = -1073741811;
      v31 = -1073741811;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v21,
          v22,
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
          150);
        goto LABEL_65;
      }
      goto LABEL_45;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"NTE_NOT_SUPPORTED",
        41,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        11);
    return 2148073513LL;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"NTE_INVALID_HANDLE",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        255);
    return 2148073510LL;
  }
}

```

## disassembly

```asm
0x180005240  push    rbp
0x180005242  push    r14
0x180005244  push    r15
0x180005246  sub     rsp, 0B0h
0x18000524d  mov     r14d, r9d
0x180005250  mov     r15, r8
0x180005253  mov     rbp, rdx
0x180005256  test    rcx, rcx
0x180005259  jz      short loc_18000526C
0x18000525b  cmp     dword ptr [rcx], 310h
0x180005261  jb      short loc_18000526C
0x180005263  cmp     dword ptr [rcx+4], 73736C31h
0x18000526a  jz      short loc_18000526E
0x18000526c  xor     ecx, ecx
0x18000526e  test    rdx, rdx
0x180005271  jz      short loc_180005281
0x180005273  cmp     dword ptr [rdx], 70h ; 'p'
0x180005276  jb      short loc_180005281
0x180005278  cmp     dword ptr [rdx+4], 73736C33h
0x18000527f  jz      short loc_180005283
0x180005281  xor     ebp, ebp
0x180005283  test    rcx, rcx
0x180005286  jz      loc_18000567B
0x18000528c  test    rbp, rbp
0x18000528f  jz      loc_18000567B
0x180005295  mov     rcx, [rbp+10h]
0x180005299  test    rcx, rcx
0x18000529c  jz      loc_18000567B
0x1800052a2  mov     [rsp+0C8h+var_28], rdi
0x1800052aa  mov     [rsp+0C8h+var_38], r13
0x1800052b2  cmp     r14d, 0FFh
0x1800052b9  ja      loc_1800056D2
0x1800052bf  mov     rdi, [rsp+0C8h+arg_20]
0x1800052c7  test    rdi, rdi
0x1800052ca  jz      loc_1800056D2
0x1800052d0  cmp     dword ptr [rbp+8], 304h
0x1800052d7  jnz     loc_18000572D
0x1800052dd  cmp     dword ptr [rbp+6Ch], 7
0x1800052e1  jnz     loc_18000572D
0x1800052e7  cmp     [rsp+0C8h+arg_30], 0
0x1800052ef  jnz     loc_180005808
0x1800052f5  mov     rcx, [rcx+88h]; String1
0x1800052fc  test    rcx, rcx
0x1800052ff  jz      loc_180005721
0x180005305  cmp     word ptr [rcx], 0
0x180005309  jz      loc_180005721
0x18000530f  call    I_GetHashInfoFromAlgorithmName
0x180005314  test    rax, rax
0x180005317  jz      short loc_180005354
0x180005319  mov     r13d, [rax+8]
0x18000531d  cmp     r13d, 0FFFFh
0x180005324  jbe     short loc_180005357
0x180005326  mov     rcx, cs:WPP_GLOBAL_Control
0x18000532d  lea     rax, WPP_GLOBAL_Control
0x180005334  cmp     rcx, rax
0x180005337  jz      loc_180005717
0x18000533d  test    byte ptr [rcx+1Ch], 1
0x180005341  jz      loc_180005717
0x180005347  mov     [rsp+0C8h+var_98], 1B20h
0x18000534f  jmp     loc_1800056F3
0x180005354  xor     r13d, r13d
0x180005357  mov     rcx, gs:60h
0x180005360  lea     eax, [r13+10h]
0x180005364  mov     [rsp+0C8h+arg_10], rbx
0x18000536c  xor     edx, edx; Flags
0x18000536e  mov     r8d, eax; Size
0x180005371  mov     [rsp+0C8h+var_20], rsi
0x180005379  mov     rcx, [rcx+30h]; HeapHandle
0x18000537d  mov     [rsp+0C8h+var_84], eax
0x180005381  call    cs:__imp_RtlAllocateHeap
0x180005387  mov     [rsp+0C8h+var_80], rax
0x18000538c  mov     rsi, rax
0x18000538f  test    rax, rax
0x180005392  jz      loc_180005830
0x180005398  mov     eax, dword ptr cs:aTls13; "tls13 "
0x18000539e  lea     rcx, String; "resumption"
0x1800053a5  mov     rbx, [rbp+20h]
0x1800053a9  mov     [rsp+0C8h+var_88], eax
0x1800053ad  movzx   eax, word ptr cs:aTls13+4; "3 "
0x1800053b4  mov     [rsp+0C8h+arg_0], ax
0x1800053bc  movzx   eax, byte ptr cs:aTls13+6; ""
0x1800053c3  mov     [rsp+0C8h+arg_E], al
0x1800053ca  mov     [rsp+0C8h+var_30], r12
0x1800053d2  mov     [rsp+0C8h+var_68], rbx
0x1800053d7  call    strnlen_s
0x1800053dc  mov     [rsp+0C8h+var_78], rax
0x1800053e1  lea     rcx, [rsp+0C8h+var_60]
0x1800053e6  mov     [rsp+0C8h+var_48], rcx
0x1800053ee  mov     [rsp+0C8h+var_60], 0
0x1800053f6  mov     [rsp+0C8h+var_5C], 14h
0x1800053fe  mov     [rsp+0C8h+var_58], 0
0x180005407  mov     [rsp+0C8h+var_50], 0
0x18000540f  mov     [rsp+0C8h+var_4C], 1
0x180005417  mov     [rsp+0C8h+arg_8], 0
0x180005422  test    rbx, rbx
0x180005425  jz      loc_18000577C
0x18000542b  lea     ebx, [rax+6]
0x18000542e  cmp     bl, 0FFh
0x180005431  jnb     loc_18000577C
0x180005437  test    r15, r15
0x18000543a  jz      loc_1800057FA
0x180005440  test    r14b, r14b
0x180005443  jz      loc_18000577C
0x180005449  lea     r12, [rsi+0Ch]
0x18000544d  test    r12, r12
0x180005450  jz      loc_18000577C
0x180005456  test    r13w, r13w
0x18000545a  jz      loc_18000577C
0x180005460  movzx   ecx, r14b
0x180005464  xor     edx, edx; Flags
0x180005466  add     cx, 4
0x18000546a  movzx   eax, bl
0x18000546d  add     cx, ax
0x180005470  movzx   esi, cx
0x180005473  mov     rcx, gs:60h
0x18000547c  mov     r8d, esi; Size
0x18000547f  mov     rcx, [rcx+30h]; HeapHandle
0x180005483  call    cs:__imp_RtlAllocateHeap
0x180005489  mov     [rsp+0C8h+P], rax
0x18000548e  mov     rcx, rax
0x180005491  test    rax, rax
0x180005494  jz      loc_180005584
0x18000549a  mov     [rcx+2], bl
0x18000549d  lea     rdi, [rcx+9]
0x1800054a1  movzx   ebx, byte ptr [rsp+0C8h+var_78]
0x1800054a6  lea     rdx, String; "resumption"
0x1800054ad  mov     [rcx+1], r13b
0x1800054b1  movzx   eax, r13w
0x1800054b5  shr     ax, 8
0x1800054b9  mov     r8d, ebx; Size
0x1800054bc  mov     [rcx], al
0x1800054be  mov     eax, [rsp+0C8h+var_88]
0x1800054c2  mov     [rcx+3], eax
0x1800054c5  movzx   eax, [rsp+0C8h+arg_0]
0x1800054cd  mov     [rcx+7], ax
0x1800054d1  mov     rcx, rdi; void *
0x1800054d4  call    memmove
0x1800054d9  lea     rcx, [rbx+1]
0x1800054dd  movzx   r8d, r14b; Size
0x1800054e1  add     rcx, rdi; void *
0x1800054e4  mov     [rdi+rbx], r14b
0x1800054e8  mov     rdx, r15; Src
0x1800054eb  call    memmove
0x1800054f0  mov     rdi, [rsp+0C8h+P]
0x1800054f5  lea     rax, [rsp+0C8h+arg_8]
0x1800054fd  mov     rcx, [rsp+0C8h+var_68]
0x180005502  lea     rdx, [rsp+0C8h+var_50]
0x180005507  movzx   ebx, r13w
0x18000550b  mov     r8, r12
0x18000550e  mov     r9d, ebx
0x180005511  mov     dword ptr [rsp+0C8h+var_A0], 0
0x180005519  mov     [rsp+0C8h+var_A8], rax
0x18000551e  mov     [rsp+0C8h+var_60], esi
0x180005522  mov     [rsp+0C8h+var_58], rdi
0x180005527  call    cs:__imp_BCryptKeyDerivation
0x18000552d  mov     r14d, eax
0x180005530  test    eax, eax
0x180005532  jz      loc_1800055DB
0x180005538  mov     rcx, cs:WPP_GLOBAL_Control
0x18000553f  lea     rax, WPP_GLOBAL_Control
0x180005546  cmp     rcx, rax
0x180005549  jz      loc_1800055E8
0x18000554f  test    byte ptr [rcx+1Ch], 1
0x180005553  jz      loc_1800055E8
0x180005559  mov     rcx, [rcx+10h]
0x18000555d  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005564  mov     [rsp+0C8h+var_98], 0FC3h
0x18000556c  lea     r9, aStatus; "Status"
0x180005573  mov     [rsp+0C8h+var_A0], rax
0x180005578  mov     dword ptr [rsp+0C8h+var_A8], r14d
0x18000557d  call    WPP_SF_sDsd
0x180005582  jmp     short loc_1800055E8
0x180005584  mov     ebx, 0C0000017h
0x180005589  mov     r14d, ebx
0x18000558c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005593  lea     rax, WPP_GLOBAL_Control
0x18000559a  cmp     rcx, rax
0x18000559d  jz      short loc_18000561D
0x18000559f  test    byte ptr [rcx+1Ch], 1
0x1800055a3  jz      short loc_18000561D
0x1800055a5  mov     rcx, [rcx+10h]
0x1800055a9  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800055b0  mov     [rsp+0C8h+var_98], 0FA9h
0x1800055b8  lea     r9, aStatus; "Status"
0x1800055bf  mov     [rsp+0C8h+var_A0], rax
0x1800055c4  mov     dword ptr [rsp+0C8h+var_A8], 0C0000017h
0x1800055cc  call    WPP_SF_sDsd
0x1800055d1  mov     rsi, [rsp+0C8h+var_80]
0x1800055d6  jmp     loc_1800057D1
0x1800055db  cmp     [rsp+0C8h+arg_8], ebx
0x1800055e2  jnz     loc_180005538
0x1800055e8  mov     rax, rdi
0x1800055eb  nop     dword ptr [rax+rax+00h]
0x1800055f0  mov     byte ptr [rax], 0
0x1800055f3  lea     rax, [rax+1]
0x1800055f7  sub     rsi, 1
0x1800055fb  jnz     short loc_1800055F0
0x1800055fd  mov     rcx, gs:60h
0x180005606  mov     r8, rdi; P
0x180005609  xor     edx, edx; Flags
0x18000560b  mov     rcx, [rcx+30h]; HeapHandle
0x18000560f  call    cs:__imp_RtlFreeHeap
0x180005615  mov     rdi, [rsp+0C8h+arg_20]
0x18000561d  mov     rsi, [rsp+0C8h+var_80]
0x180005622  mov     ebx, r14d
0x180005625  test    r14d, r14d
0x180005628  js      loc_1800057D1
0x18000562e  mov     eax, [rsp+0C8h+var_84]
0x180005632  mov     [rsi], eax
0x180005634  mov     dword ptr [rsi+4], 73736C38h
0x18000563b  mov     ecx, [rbp+8]
0x18000563e  mov     [rsi+8], ecx
0x180005641  mov     [rdi], rsi
0x180005644  mov     r12, [rsp+0C8h+var_30]
0x18000564c  mov     rsi, [rsp+0C8h+var_20]
0x180005654  mov     eax, ebx
0x180005656  mov     rbx, [rsp+0C8h+arg_10]
0x18000565e  mov     rdi, [rsp+0C8h+var_28]
0x180005666  mov     r13, [rsp+0C8h+var_38]
0x18000566e  add     rsp, 0B0h
0x180005675  pop     r15
0x180005677  pop     r14
0x180005679  pop     rbp
0x18000567a  retn
0x18000567b  mov     rcx, cs:WPP_GLOBAL_Control
0x180005682  lea     rax, WPP_GLOBAL_Control
0x180005689  cmp     rcx, rax
0x18000568c  jz      short loc_1800056C0
0x18000568e  test    byte ptr [rcx+1Ch], 1
0x180005692  jz      short loc_1800056C0
0x180005694  mov     rcx, [rcx+10h]
0x180005698  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000569f  mov     [rsp+0C8h+var_98], 1AFFh
0x1800056a7  lea     r9, aNteInvalidHand; "NTE_INVALID_HANDLE"
0x1800056ae  mov     [rsp+0C8h+var_A0], rax
0x1800056b3  mov     dword ptr [rsp+0C8h+var_A8], 80090026h
0x1800056bb  call    WPP_SF_sDsd
0x1800056c0  mov     eax, 80090026h
0x1800056c5  add     rsp, 0B0h
0x1800056cc  pop     r15
0x1800056ce  pop     r14
0x1800056d0  pop     rbp
0x1800056d1  retn
0x1800056d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800056d9  lea     rax, WPP_GLOBAL_Control
0x1800056e0  cmp     rcx, rax
0x1800056e3  jz      short loc_180005717
0x1800056e5  test    byte ptr [rcx+1Ch], 1
0x1800056e9  jz      short loc_180005717
0x1800056eb  mov     [rsp+0C8h+var_98], 1B05h
0x1800056f3  mov     rcx, [rcx+10h]
0x1800056f7  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800056fe  mov     [rsp+0C8h+var_A0], rax
0x180005703  lea     r9, aNteInvalidPara; "NTE_INVALID_PARAMETER"
0x18000570a  mov     dword ptr [rsp+0C8h+var_A8], 80090027h
0x180005712  call    WPP_SF_sDsd
0x180005717  mov     eax, 80090027h
0x18000571c  jmp     loc_18000565E
0x180005721  lea     rcx, aSha256; "SHA256"
0x180005728  jmp     loc_18000530F
0x18000572d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005734  lea     rax, WPP_GLOBAL_Control
0x18000573b  cmp     rcx, rax
0x18000573e  jz      short loc_180005772
0x180005740  test    byte ptr [rcx+1Ch], 1
0x180005744  jz      short loc_180005772
0x180005746  mov     rcx, [rcx+10h]
0x18000574a  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005751  mov     [rsp+0C8h+var_98], 1B0Bh
0x180005759  lea     r9, aNteNotSupporte; "NTE_NOT_SUPPORTED"
0x180005760  mov     [rsp+0C8h+var_A0], rax
0x180005765  mov     dword ptr [rsp+0C8h+var_A8], 80090029h
0x18000576d  call    WPP_SF_sDsd
0x180005772  mov     eax, 80090029h
0x180005777  jmp     loc_18000565E
0x18000577c  mov     ebx, 0C000000Dh
0x180005781  mov     r14d, ebx
0x180005784  mov     rcx, cs:WPP_GLOBAL_Control
0x18000578b  lea     rax, WPP_GLOBAL_Control
0x180005792  cmp     rcx, rax
0x180005795  jz      loc_180005622
0x18000579b  test    byte ptr [rcx+1Ch], 1
0x18000579f  jz      loc_180005622
0x1800057a5  mov     rcx, [rcx+10h]
0x1800057a9  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800057b0  mov     [rsp+0C8h+var_98], 0F96h
0x1800057b8  lea     r9, aStatus; "Status"
0x1800057bf  mov     [rsp+0C8h+var_A0], rax
0x1800057c4  mov     dword ptr [rsp+0C8h+var_A8], 0C000000Dh
0x1800057cc  call    WPP_SF_sDsd
0x1800057d1  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800057d8  mov     r9d, 1B37h
0x1800057de  lea     rdx, aStatus; "Status"
0x1800057e5  mov     ecx, r14d
0x1800057e8  call    DebugTraceError
0x1800057ed  mov     rcx, rsi
0x1800057f0  call    MSCryptFree
0x1800057f5  jmp     loc_180005644
0x1800057fa  test    r14b, r14b
0x1800057fd  jz      loc_180005449
  ... truncated ...
```
