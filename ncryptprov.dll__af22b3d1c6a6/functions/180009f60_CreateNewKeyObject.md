# CreateNewKeyObject

- ea: `0x180009f60`
- end: `0x18000a494`
- name: `CreateNewKeyObject`
- size: `1332`
- prototype: `__int64 __fastcall(_WORD *Src, __int64, int **, __int64, unsigned int, _QWORD *)`
- caller_count: `8`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009b60`
- `0x180027778`
- `0x18002b460`
- `0x1800489c8`
- `0x180049dec`
- `0x18005b338`
- `0x18005bbcc`
- `0x18005e958`

## callees

- `0x1800096e0`
- `0x180009f60`
- `0x18000b250`
- `0x18000bdd0`
- `0x180016550`
- `0x180017580`
- `0x18001a6d8`
- `0x180028114`
- `0x18004c630`
- `0x180062310`

## import_xrefs

- `ntdll!RtlCompareUnicodeStrings` at `0x180009fd9`
- `ntdll!RtlCompareUnicodeStrings` at `0x180009fd9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000a431`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000a431`

## string_xrefs

- `0x18000a002`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18000a460`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`

## pseudocode

```c
__int64 __fastcall CreateNewKeyObject(_WORD *Src, __int64 a2, int **a3, __int64 a4, unsigned int a5, _QWORD *a6)
{
  __int64 v9; // rdi
  __int64 v10; // rax
  int v11; // r8d
  unsigned int v13; // eax
  int v14; // r8d
  _DWORD *v15; // r15
  unsigned int v16; // ebx
  int v17; // r8d
  int v18; // r8d
  int v19; // r8d
  int *v20; // rax
  int v22; // edi
  char *v23; // r9
  char *v24; // rax
  char v25; // cl
  char v28; // cl
  char v29; // dl
  __int64 v30; // rcx
  char UserDataCount; // [rsp+20h] [rbp-E0h]
  void *v32; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v33; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v34; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v35; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v36; // [rsp+74h] [rbp-8Ch] BYREF
  int v37; // [rsp+78h] [rbp-88h] BYREF
  int v38; // [rsp+7Ch] [rbp-84h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+80h] [rbp-80h] BYREF
  __int64 v40; // [rsp+90h] [rbp-70h] BYREF
  __int64 v41; // [rsp+98h] [rbp-68h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+A0h] [rbp-60h] BYREF
  __int16 *v43; // [rsp+B0h] [rbp-50h]
  unsigned int v44; // [rsp+B8h] [rbp-48h]
  int v45; // [rsp+BCh] [rbp-44h]
  __int64 *v46; // [rsp+C0h] [rbp-40h]
  _QWORD v47[6]; // [rsp+C8h] [rbp-38h]
  int v48; // [rsp+F8h] [rbp-8h]
  int v49; // [rsp+FCh] [rbp-4h]
  unsigned int *v50; // [rsp+100h] [rbp+0h]
  __int64 v51; // [rsp+108h] [rbp+8h]
  unsigned int *v52; // [rsp+110h] [rbp+10h]
  __int64 v53; // [rsp+118h] [rbp+18h]
  unsigned int *v54; // [rsp+120h] [rbp+20h]
  __int64 v55; // [rsp+128h] [rbp+28h]
  int *v56; // [rsp+130h] [rbp+30h]
  __int64 v57; // [rsp+138h] [rbp+38h]
  int *v58; // [rsp+140h] [rbp+40h]
  __int64 v59; // [rsp+148h] [rbp+48h]

  v32 = 0;
  v9 = -1;
  if ( Src )
  {
    v10 = -1;
    do
      ++v10;
    while ( Src[v10] );
    if ( (unsigned int)v10 >= 4 && !(unsigned int)RtlCompareUnicodeStrings(Src, 4, L"\\\\~\\") )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)WPP_GLOBAL_Control,
          v11,
          (unsigned int)"Status",
          39,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
          70);
      return 2148073511LL;
    }
  }
  v13 = InitializeNewKeyObject(
          Src,
          *(void **)(a2 + 16),
          a5,
          *(_DWORD *)(a2 + 48),
          *(_DWORD *)(a2 + 52),
          *(_DWORD *)(a2 + 56),
          *(_DWORD *)(a2 + 60),
          *(void **)(a2 + 40),
          (__int64)&v32);
  v15 = v32;
  v16 = v13;
  if ( v13 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)WPP_GLOBAL_Control,
        v14,
        (unsigned int)"Status",
        v13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
        90);
  }
  else
  {
    v16 = FinishNewKeyObject(0, v32);
    if ( !v16 )
    {
      if ( (a5 & 0x30000) != 0 )
      {
        v16 = FinishNewKeyObject_VirtualIso(v15, 1, (a5 >> 18) & 1);
        if ( v16 )
        {
          if ( (a5 & 0x10000) == 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                (_DWORD)WPP_GLOBAL_Control,
                v18,
                (unsigned int)"Status",
                v16,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
                142);
            goto LABEL_54;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_5b095617bbfd389ce3c01d1846ed1dee_Traceguids, v16);
          if ( (unsigned int)Feature_KG_Ncrypt_Telemetry__private_IsEnabledDeviceUsageNoInline()
            && (unsigned int)dword_1800790F0 > 5
            && (qword_180079100 & 0x400000000000LL) != 0
            && (qword_180079108 & 0x400000000000LL) == qword_180079108 )
          {
            v40 = 1;
            v46 = &v40;
            v47[0] = 8;
            v47[1] = &v41;
            v47[3] = &v33;
            v20 = *a3;
            v41 = 0x1000000;
            v47[2] = 8;
            v33 = v16;
            v47[4] = 4;
            if ( v20 )
            {
              while ( *((_WORD *)v20 + ++v9) != 0 )
                ;
              v22 = 2 * v9 + 2;
            }
            else
            {
              v20 = &dword_18006B48C;
              v22 = 2;
            }
            v47[5] = v20;
            v50 = &v34;
            v52 = &v35;
            v54 = &v36;
            v34 = a5;
            v49 = 0;
            v48 = v22;
            v51 = 4;
            v53 = 4;
            v36 = (a5 >> 18) & 1;
            v55 = 4;
            *(_DWORD *)&EventDescriptor.Id = 184549376;
            v35 = (a5 >> 5) & 1;
            v37 = v15[142];
            v56 = &v37;
            v57 = 4;
            v38 = v15[7];
            v58 = &v38;
            *(_DWORD *)&EventDescriptor.Level = 5;
            UserData.Ptr = (ULONGLONG)off_1800790F8;
            v59 = 4;
            EventDescriptor.Keyword = 0x400000000000LL;
            UserData.Size = *(unsigned __int16 *)off_1800790F8;
            v43 = word_180070762;
            UserData.Reserved = 2;
            v44 = 159;
            v45 = 1;
            LODWORD(v32) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            if ( (void (__fastcall *)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))qword_180079118 == TlgAggregateInternalRegisteredProviderEtwCallback )
            {
              LOBYTE(v19) = 0;
              v23 = (char *)v43 + v44;
              v24 = (char *)(v43 + 1);
              do
                v25 = *v24++;
              while ( v25 < 0 );
              while ( *v24++ )
                ;
              if ( v24 >= v23 )
                goto LABEL_50;
              while ( 1 )
              {
                while ( *v24++ )
                  ;
                if ( *v24 >= 0 )
                  break;
                v28 = *v24 & 0x7F;
                if ( v24[1] >= 0 )
                  break;
                v29 = v24[2];
                v24 += 2;
                if ( v29 < 0 )
                {
                  while ( v29 == (char)0x80 )
                  {
                    v29 = *++v24;
                    if ( v29 >= 0 )
                      goto LABEL_43;
                  }
                  break;
                }
LABEL_43:
                if ( v28 == 9 && (unsigned __int8)(v29 - 113) <= 2u )
                {
                  v30 = (unsigned __int8)v19;
                  LOBYTE(v19) = v19 + 1;
                  BYTE5(v47[2 * v30]) = v29;
                  if ( v24 < v23 )
                    continue;
                }
                break;
              }
              if ( (_BYTE)v19 )
              {
                UserDataCount = v19;
                LOBYTE(v19) = 11;
                InsertEventEntryInLookUpTable(
                  (unsigned int)&dword_1800790F0,
                  (unsigned int)&EventDescriptor,
                  v19,
                  (unsigned int)&UserData,
                  UserDataCount);
              }
              else
              {
LABEL_50:
                EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 0xBu, &UserData);
              }
            }
          }
        }
      }
      *a6 = v15;
      return 0;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)WPP_GLOBAL_Control,
        v17,
        (unsigned int)"Status",
        v16,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c",
        97);
  }
LABEL_54:
  if ( v15 )
    DeleteKeyObject(v15);
  return v16;
}

```

## disassembly

```asm
0x180009f60  push    rbp
0x180009f62  push    rbx
0x180009f63  push    rdi
0x180009f64  push    r12
0x180009f66  push    r13
0x180009f68  push    r14
0x180009f6a  push    r15
0x180009f6c  lea     rbp, [rsp-70h]
0x180009f71  sub     rsp, 170h
0x180009f78  mov     rax, cs:__security_cookie
0x180009f7f  xor     rax, rsp
0x180009f82  mov     [rbp+0A0h+var_50], rax
0x180009f86  mov     r13, [rbp+0A0h+arg_28]
0x180009f8d  mov     r15d, r9d
0x180009f90  mov     [rsp+1A0h+var_140], 0
0x180009f99  mov     r12, r8
0x180009f9c  mov     r14, rdx
0x180009f9f  mov     rbx, rcx
0x180009fa2  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180009fa9  test    rcx, rcx
0x180009fac  jz      loc_18000A038
0x180009fb2  mov     rax, rdi
0x180009fb5  inc     rax
0x180009fb8  cmp     word ptr [rcx+rax*2], 0
0x180009fbd  jnz     short loc_180009FB5
0x180009fbf  cmp     eax, 4
0x180009fc2  jb      short loc_18000A038
0x180009fc4  mov     r9d, 4
0x180009fca  mov     [rsp+1A0h+UserDataCount], 0
0x180009fcf  mov     edx, r9d
0x180009fd2  lea     r8, asc_18006E280; "\\\\~\\"
0x180009fd9  call    cs:__imp_RtlCompareUnicodeStrings
0x180009fe0  nop     dword ptr [rax+rax+00h]
0x180009fe5  test    eax, eax
0x180009fe7  jnz     short loc_18000A038
0x180009fe9  mov     rdx, cs:WPP_GLOBAL_Control
0x180009ff0  lea     rax, WPP_GLOBAL_Control
0x180009ff7  cmp     rdx, rax
0x180009ffa  jz      short loc_18000A02E
0x180009ffc  test    byte ptr [rdx+1Ch], 1
0x18000a000  jz      short loc_18000A02E
0x18000a002  lea     rcx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a009  mov     [rsp+1A0h+var_170], 546h
0x18000a011  mov     [rsp+1A0h+UserData], rcx
0x18000a016  lea     r9, aStatus; "Status"
0x18000a01d  mov     rcx, [rdx+10h]
0x18000a021  mov     dword ptr [rsp+1A0h+UserDataCount], 80090027h
0x18000a029  call    WPP_SF_sDsd
0x18000a02e  mov     eax, 80090027h
0x18000a033  jmp     loc_18000A3EF
0x18000a038  mov     rdx, [r14+10h]; void *
0x18000a03c  lea     rax, [rsp+1A0h+var_140]
0x18000a041  mov     [rsp+1A0h+var_150], rax; __int64
0x18000a046  mov     r9d, r15d
0x18000a049  mov     rax, [r14+28h]
0x18000a04d  mov     r8, r12
0x18000a050  mov     [rsp+1A0h+var_158], rax; void *
0x18000a055  mov     rcx, rbx; Src
0x18000a058  mov     eax, [r14+3Ch]
0x18000a05c  mov     [rsp+1A0h+var_160], eax; int
0x18000a060  mov     eax, [r14+38h]
0x18000a064  mov     [rsp+1A0h+var_168], eax; int
0x18000a068  mov     eax, [r14+34h]
0x18000a06c  mov     [rsp+1A0h+var_170], eax; int
0x18000a070  mov     eax, [r14+30h]
0x18000a074  mov     dword ptr [rsp+1A0h+UserData], eax; int
0x18000a078  mov     [rsp+1A0h+var_38], rsi
0x18000a080  mov     esi, [rbp+0A0h+arg_20]
0x18000a086  mov     dword ptr [rsp+1A0h+UserDataCount], esi; int
0x18000a08a  call    InitializeNewKeyObject
0x18000a08f  mov     r15, [rsp+1A0h+var_140]
0x18000a094  mov     ebx, eax
0x18000a096  test    eax, eax
0x18000a098  jz      short loc_18000A0C8
0x18000a09a  mov     rdx, cs:WPP_GLOBAL_Control
0x18000a0a1  lea     rax, WPP_GLOBAL_Control
0x18000a0a8  cmp     rdx, rax
0x18000a0ab  jz      loc_18000A480
0x18000a0b1  test    byte ptr [rdx+1Ch], 1
0x18000a0b5  jz      loc_18000A480
0x18000a0bb  mov     [rsp+1A0h+var_170], 55Ah
0x18000a0c3  jmp     loc_18000A460
0x18000a0c8  mov     rdx, r15
0x18000a0cb  xor     ecx, ecx
0x18000a0cd  call    FinishNewKeyObject
0x18000a0d2  mov     ebx, eax
0x18000a0d4  test    eax, eax
0x18000a0d6  jz      short loc_18000A106
0x18000a0d8  mov     rdx, cs:WPP_GLOBAL_Control
0x18000a0df  lea     rax, WPP_GLOBAL_Control
0x18000a0e6  cmp     rdx, rax
0x18000a0e9  jz      loc_18000A480
0x18000a0ef  test    byte ptr [rdx+1Ch], 1
0x18000a0f3  jz      loc_18000A480
0x18000a0f9  mov     [rsp+1A0h+var_170], 561h
0x18000a101  jmp     loc_18000A460
0x18000a106  test    esi, 30000h
0x18000a10c  jz      loc_18000A3E1
0x18000a112  mov     r14d, esi
0x18000a115  mov     edx, 1
0x18000a11a  shr     r14d, 12h
0x18000a11e  mov     rcx, r15
0x18000a121  and     r14d, 1
0x18000a125  mov     r8d, r14d
0x18000a128  call    FinishNewKeyObject_VirtualIso
0x18000a12d  mov     ebx, eax
0x18000a12f  test    eax, eax
0x18000a131  jz      loc_18000A3E1
0x18000a137  bt      esi, 10h
0x18000a13b  jnb     loc_18000A43F
0x18000a141  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a148  lea     rax, WPP_GLOBAL_Control
0x18000a14f  cmp     rcx, rax
0x18000a152  jz      short loc_18000A172
0x18000a154  test    byte ptr [rcx+1Ch], 2
0x18000a158  jz      short loc_18000A172
0x18000a15a  mov     rcx, [rcx+10h]
0x18000a15e  lea     r8, WPP_5b095617bbfd389ce3c01d1846ed1dee_Traceguids
0x18000a165  mov     edx, 0Dh
0x18000a16a  mov     r9d, ebx
0x18000a16d  call    WPP_SF_D
0x18000a172  call    Feature_KG_Ncrypt_Telemetry__private_IsEnabledDeviceUsageNoInline
0x18000a177  test    eax, eax
0x18000a179  jz      loc_18000A3E1
0x18000a17f  mov     eax, cs:dword_1800790F0
0x18000a185  cmp     eax, 5
0x18000a188  jbe     loc_18000A3E1
0x18000a18e  mov     rcx, cs:qword_180079108
0x18000a195  mov     rdx, 400000000000h
0x18000a19f  mov     rax, cs:qword_180079100
0x18000a1a6  test    rdx, rax
0x18000a1a9  jz      loc_18000A3E1
0x18000a1af  mov     rax, rcx
0x18000a1b2  and     rax, rdx
0x18000a1b5  cmp     rax, rcx
0x18000a1b8  jnz     loc_18000A3E1
0x18000a1be  lea     rax, [rbp+0A0h+var_110]
0x18000a1c2  mov     [rbp+0A0h+var_110], 1
0x18000a1ca  mov     [rbp+0A0h+var_E0], rax
0x18000a1ce  xor     ecx, ecx
0x18000a1d0  lea     rax, [rbp+0A0h+var_108]
0x18000a1d4  mov     [rbp+0A0h+var_D8], 8
0x18000a1dc  mov     [rbp+0A0h+var_D0], rax
0x18000a1e0  lea     rax, [rsp+1A0h+var_138]
0x18000a1e5  mov     [rbp+0A0h+var_C0], rax
0x18000a1e9  mov     rax, [r12]
0x18000a1ed  mov     [rbp+0A0h+var_108], 1000000h
0x18000a1f5  mov     [rbp+0A0h+var_C8], 8
0x18000a1fd  mov     [rsp+1A0h+var_138], ebx
0x18000a201  mov     [rbp+0A0h+var_B8], 4
0x18000a209  test    rax, rax
0x18000a20c  jz      short loc_18000A224
0x18000a20e  xchg    ax, ax
0x18000a210  cmp     [rax+rdi*2+2], cx
0x18000a215  lea     rdi, [rdi+1]
0x18000a219  jnz     short loc_18000A210
0x18000a21b  lea     edi, ds:2[rdi*2]
0x18000a222  jmp     short loc_18000A230
0x18000a224  lea     rax, dword_18006B48C
0x18000a22b  mov     edi, 2
0x18000a230  mov     [rbp+0A0h+var_B0], rax
0x18000a234  lea     rax, [rsp+1A0h+var_134]
0x18000a239  mov     [rbp+0A0h+var_A0], rax
0x18000a23d  lea     rax, [rsp+1A0h+var_130]
0x18000a242  mov     [rbp+0A0h+var_90], rax
0x18000a246  lea     rax, [rsp+1A0h+var_12C]
0x18000a24b  mov     [rbp+0A0h+var_80], rax
0x18000a24f  mov     [rsp+1A0h+var_134], esi
0x18000a253  mov     [rbp+0A0h+var_A4], ecx
0x18000a256  lea     rcx, _TraceLoggingMetadata
0x18000a25d  mov     [rbp+0A0h+var_A8], edi
0x18000a260  mov     [rbp+0A0h+var_98], 4
0x18000a268  mov     [rbp+0A0h+var_88], 4
0x18000a270  mov     [rsp+1A0h+var_12C], r14d
0x18000a275  mov     [rbp+0A0h+var_78], 4
0x18000a27d  shr     esi, 5
0x18000a280  and     esi, 1
0x18000a283  mov     dword ptr [rbp+0A0h+EventDescriptor.Id], 0B000000h
0x18000a28a  mov     [rsp+1A0h+var_130], esi
0x18000a28e  mov     eax, [r15+238h]
0x18000a295  mov     [rsp+1A0h+var_128], eax
0x18000a299  lea     rax, [rsp+1A0h+var_128]
0x18000a29e  mov     [rbp+0A0h+var_70], rax
0x18000a2a2  mov     [rbp+0A0h+var_68], 4
0x18000a2aa  mov     eax, [r15+1Ch]
0x18000a2ae  mov     [rsp+1A0h+var_124], eax
0x18000a2b2  lea     rax, [rsp+1A0h+var_124]
0x18000a2b7  mov     [rbp+0A0h+var_60], rax
0x18000a2bb  movzx   eax, cs:word_180070758
0x18000a2c2  mov     dword ptr [rbp+0A0h+EventDescriptor.Level], eax
0x18000a2c5  mov     rax, cs:off_1800790F8
0x18000a2cc  mov     [rbp+0A0h+var_100.Ptr], rax
0x18000a2d0  mov     [rbp+0A0h+var_58], 4
0x18000a2d8  mov     [rbp+0A0h+EventDescriptor.Keyword], rdx
0x18000a2dc  movzx   eax, word ptr [rax]
0x18000a2df  mov     [rbp+0A0h+var_100.Size], eax
0x18000a2e2  lea     rax, word_180070762
0x18000a2e9  mov     [rbp+0A0h+var_F0], rax
0x18000a2ed  lea     rax, _TraceLoggingMetadataEnd
0x18000a2f4  sub     eax, ecx
0x18000a2f6  mov     dword ptr [rbp+0A0h+var_100.0Ch], 2
0x18000a2fd  mov     [rbp+0A0h+var_E8], 9Fh
0x18000a304  mov     [rbp+0A0h+var_E4], 1
0x18000a30b  mov     dword ptr [rsp+1A0h+var_140], eax
0x18000a30f  mov     eax, dword ptr [rsp+1A0h+var_140]
0x18000a313  lea     rax, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x18000a31a  cmp     cs:qword_180079118, rax
0x18000a321  jnz     loc_18000A3E1
0x18000a327  mov     rax, [rbp+0A0h+var_F0]
0x18000a32b  xor     r8b, r8b
0x18000a32e  mov     r9d, [rbp+0A0h+var_E8]
0x18000a332  add     r9, rax
0x18000a335  add     rax, 2
0x18000a339  nop     dword ptr [rax+00000000h]
0x18000a340  movzx   ecx, byte ptr [rax]
0x18000a343  inc     rax
0x18000a346  test    cl, cl
0x18000a348  js      short loc_18000A340
0x18000a34a  nop     word ptr [rax+rax+00h]
0x18000a350  movzx   ecx, byte ptr [rax]
0x18000a353  inc     rax
0x18000a356  test    cl, cl
0x18000a358  jnz     short loc_18000A350
0x18000a35a  cmp     rax, r9
0x18000a35d  jnb     loc_18000A40F
0x18000a363  movzx   ecx, byte ptr [rax]
0x18000a366  inc     rax
0x18000a369  test    cl, cl
0x18000a36b  jnz     short loc_18000A363
0x18000a36d  movzx   ecx, byte ptr [rax]
0x18000a370  test    cl, cl
0x18000a372  jns     short loc_18000A3C0
0x18000a374  and     cl, 7Fh
0x18000a377  cmp     byte ptr [rax+1], 0
0x18000a37b  jge     short loc_18000A3C0
0x18000a37d  movzx   edx, byte ptr [rax+2]
0x18000a381  add     rax, 2
0x18000a385  test    dl, dl
0x18000a387  jns     short loc_18000A3A0
0x18000a389  nop     dword ptr [rax+00000000h]
0x18000a390  cmp     dl, 80h
0x18000a393  jnz     short loc_18000A3C0
0x18000a395  movzx   edx, byte ptr [rax+1]
0x18000a399  inc     rax
0x18000a39c  test    dl, dl
0x18000a39e  js      short loc_18000A390
0x18000a3a0  cmp     cl, 9
0x18000a3a3  jnz     short loc_18000A3C0
0x18000a3a5  lea     ecx, [rdx-71h]
0x18000a3a8  cmp     cl, 2
0x18000a3ab  ja      short loc_18000A3C0
0x18000a3ad  movzx   ecx, r8b
0x18000a3b1  inc     r8b
0x18000a3b4  add     rcx, rcx
0x18000a3b7  mov     byte ptr [rbp+rcx*8+0A0h+var_D8+5], dl
0x18000a3bb  cmp     rax, r9
0x18000a3be  jb      short loc_18000A363
0x18000a3c0  test    r8b, r8b
0x18000a3c3  jz      short loc_18000A40F
0x18000a3c5  mov     [rsp+1A0h+UserDataCount], r8b
0x18000a3ca  lea     r9, [rbp+0A0h+var_100]
0x18000a3ce  mov     r8b, 0Bh
0x18000a3d1  lea     rdx, [rbp+0A0h+EventDescriptor]
0x18000a3d5  lea     rcx, dword_1800790F0
0x18000a3dc  call    InsertEventEntryInLookUpTable
0x18000a3e1  mov     [r13+0], r15
0x18000a3e5  xor     eax, eax
0x18000a3e7  mov     rsi, [rsp+1A0h+var_38]
0x18000a3ef  mov     rcx, [rbp+0A0h+var_50]
0x18000a3f3  xor     rcx, rsp; StackCookie
0x18000a3f6  call    __security_check_cookie
0x18000a3fb  add     rsp, 170h
0x18000a402  pop     r15
0x18000a404  pop     r14
0x18000a406  pop     r13
0x18000a408  pop     r12
0x18000a40a  pop     rdi
0x18000a40b  pop     rbx
0x18000a40c  pop     rbp
0x18000a40d  retn
0x18000a40f  mov     rcx, cs:RegHandle; RegHandle
0x18000a416  lea     rax, [rbp+0A0h+var_100]
0x18000a41a  mov     [rsp+1A0h+UserData], rax; UserData
0x18000a41f  lea     rdx, [rbp+0A0h+EventDescriptor]; EventDescriptor
0x18000a423  xor     r9d, r9d; RelatedActivityId
0x18000a426  mov     dword ptr [rsp+1A0h+UserDataCount], 0Bh; UserDataCount
0x18000a42e  xor     r8d, r8d; ActivityId
0x18000a431  call    cs:__imp_EventWriteTransfer
0x18000a438  nop     dword ptr [rax+rax+00h]
0x18000a43d  jmp     short loc_18000A3E1
0x18000a43f  mov     rdx, cs:WPP_GLOBAL_Control
0x18000a446  lea     rax, WPP_GLOBAL_Control
0x18000a44d  cmp     rdx, rax
0x18000a450  jz      short loc_18000A480
0x18000a452  test    byte ptr [rdx+1Ch], 1
0x18000a456  jz      short loc_18000A480
0x18000a458  mov     [rsp+1A0h+var_170], 58Eh
0x18000a460  lea     rcx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a467  mov     [rsp+1A0h+UserData], rcx
0x18000a46c  lea     r9, aStatus; "Status"
  ... truncated ...
```
