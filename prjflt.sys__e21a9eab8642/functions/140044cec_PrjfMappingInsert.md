# PrjfMappingInsert

- ea: `0x140044cec`
- end: `0x1400453b3`
- name: `PrjfMappingInsert`
- size: `1735`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140045694`

## callees

- `0x14000a560`
- `0x14000d008`
- `0x14000d128`
- `0x14004437c`
- `0x140044794`
- `0x140044af0`
- `0x140044bb4`
- `0x140044c20`
- `0x140044cec`
- `0x1400455d8`

## import_xrefs

- `ntoskrnl!RtlRbInsertNodeEx` at `0x140045244`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x140045244`
- `ntoskrnl!RtlRbRemoveNode` at `0x140045331`
- `ntoskrnl!RtlRbRemoveNode` at `0x140045331`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045381`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045381`
- `FLTMGR!FltAcquireResourceExclusive` at `0x140044d34`
- `FLTMGR!FltAcquireResourceExclusive` at `0x140044d34`
- `FLTMGR!FltReleaseResource` at `0x140045390`
- `FLTMGR!FltReleaseResource` at `0x140045390`

## pseudocode

```c
__int64 __fastcall PrjfMappingInsert(__int64 a1, __int64 *a2)
{
  struct _ERESOURCE *v2; // r14
  __int64 v3; // rbx
  __int64 v4; // r12
  __int64 *v5; // r13
  __int64 v6; // rdx
  _QWORD *v7; // rsi
  int PathTree; // edi
  int v9; // r8d
  __int64 v10; // rcx
  __int128 v11; // xmm0
  int v12; // edx
  int v13; // r8d
  char v14; // r15
  __int64 v15; // rbx
  unsigned __int64 v16; // rax
  int v17; // edx
  int v18; // r8d
  bool v19; // zf
  unsigned __int64 v20; // rdi
  int v21; // r14d
  int v22; // eax
  __int64 v23; // rdx
  int v24; // r8d
  unsigned __int64 v25; // rax
  __int64 v26; // rdi
  __int64 v27; // rcx
  __int64 *v28; // r14
  __int64 v29; // rcx
  int v30; // edx
  int v31; // r8d
  char *v32; // r14
  int v33; // edx
  __int64 v34; // r8
  __int64 v35; // r13
  unsigned __int64 v36; // rdi
  int v37; // r15d
  unsigned __int64 v38; // rax
  __int64 v39; // rdx
  __int64 v40; // rcx
  void *v41; // rcx
  int v43; // [rsp+20h] [rbp-59h]
  struct _ERESOURCE *v44; // [rsp+60h] [rbp-19h]
  __int64 v45; // [rsp+68h] [rbp-11h] BYREF
  UNICODE_STRING SourceString; // [rsp+70h] [rbp-9h] BYREF
  _OWORD v47[5]; // [rsp+80h] [rbp+7h] BYREF
  PVOID P; // [rsp+F0h] [rbp+77h] BYREF
  char v51; // [rsp+F8h] [rbp+7Fh]

  v2 = (struct _ERESOURCE *)(a1 + 696);
  v3 = a1;
  v4 = 0;
  v44 = (struct _ERESOURCE *)(a1 + 696);
  P = 0;
  v45 = 0;
  v5 = a2;
  SourceString = 0;
  FltAcquireResourceExclusive((PERESOURCE)(a1 + 696));
  v7 = *(_QWORD **)(v3 + 688);
  if ( v7 )
  {
    v51 = 1;
LABEL_9:
    v10 = *v5;
    v11 = 0;
    v47[0] = 0;
    WORD1(v47[0]) = *(_WORD *)(v10 + 2);
    LOWORD(v47[0]) = WORD1(v47[0]);
    *((_QWORD *)&v47[0] + 1) = v10 + 4;
    v14 = PrjfWalkPath(v47, v6, &SourceString);
    v15 = v7[1];
    LOBYTE(P) = v14;
    if ( SourceString.Length )
    {
      while ( 1 )
      {
        v19 = (*(_BYTE *)(v15 + 8) & 1) == 0;
        v20 = *(_QWORD *)v15;
        *((_QWORD *)&v47[0] + 1) = *((_QWORD *)&v11 + 1);
        *(_QWORD *)&v47[0] = &SourceString;
        BYTE8(v47[0]) = 1;
        if ( !v19 )
        {
          if ( v20 )
            v20 ^= v15;
          else
            v20 = 0;
        }
        v21 = *(_BYTE *)(v15 + 8) & 1;
        if ( !v20 )
          break;
        do
        {
          v22 = PrjfRBComparePathNodes(v47, v20);
          if ( v22 >= 0 )
          {
            if ( v22 <= 0 )
              break;
            v25 = *(_QWORD *)(v20 + 8);
          }
          else
          {
            v25 = *(_QWORD *)v20;
          }
          if ( v21 && v25 )
            v20 ^= v25;
          else
            v20 = v25;
        }
        while ( v20 );
        if ( !v20 )
          break;
        v26 = v20 - 8;
        v45 = v26;
        if ( !v14 )
        {
          if ( (BYTE2(xmmword_14001A3D0) & 0x10) != 0
            || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v23) = BYTE2(xmmword_14001A3D0) & 0x10;
            LOBYTE(v24) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sD(
              532,
              v23,
              v24,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              2,
              20,
              32,
              (__int64)WPP_5c05f7cae5513ff3734adbc0d3bd9537_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\mapping.c",
              32);
          }
          PathTree = -1073741811;
          goto LABEL_87;
        }
        v27 = *v5;
        v11 = 0;
        v47[0] = 0;
        WORD1(v47[0]) = *(_WORD *)(v27 + 2);
        LOWORD(v47[0]) = WORD1(v47[0]);
        *((_QWORD *)&v47[0] + 1) = v27 + 4;
        v28 = (__int64 *)(v26 + 56);
        LOBYTE(P) = PrjfWalkPath(v47, v23, &SourceString);
        v15 = *(_QWORD *)(v26 + 56);
        v14 = (char)P;
        if ( !v15 )
        {
          PathTree = PrjfCreatePathTree(v26 + 56);
          if ( PathTree < 0 )
          {
            if ( (BYTE2(xmmword_14001A3D0) & 0x10) != 0
              || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v30) = BYTE2(xmmword_14001A3D0) & 0x10;
              LOBYTE(v31) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              WPP_RECORDER_AND_TRACE_SF_sDL(
                532,
                v30,
                v31,
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                2,
                20,
                33,
                (__int64)WPP_5c05f7cae5513ff3734adbc0d3bd9537_Traceguids,
                (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\mapping.c",
                70,
                PathTree);
            }
            goto LABEL_87;
          }
LABEL_51:
          v15 = *v28;
          v45 = 0;
          break;
        }
        if ( (*(_BYTE *)(v15 + 8) & 1) != 0 )
        {
          if ( !*(_QWORD *)v15 )
            goto LABEL_51;
          v29 = *(_QWORD *)v15 ^ v15;
        }
        else
        {
          v29 = *(_QWORD *)v15;
        }
        if ( !v29 )
          goto LABEL_51;
        v45 = 0;
      }
      v32 = 0;
      while ( 1 )
      {
        v43 = *((_DWORD *)v5 + 2);
        v47[0] = 0;
        PathTree = PrjfCreatePathTierNode(&SourceString, v43, 0, (__int64)&v45);
        if ( PathTree < 0 )
          break;
        v19 = (*(_BYTE *)(v15 + 8) & 1) == 0;
        v35 = v45;
        v36 = *(_QWORD *)v15;
        BYTE8(v47[0]) = 0;
        *(_QWORD *)&v47[0] = v45 + 32;
        if ( !v19 )
        {
          if ( v36 )
            v36 ^= v15;
          else
            v36 = 0;
        }
        LOBYTE(v34) = 0;
        v37 = *(_BYTE *)(v15 + 8) & 1;
        if ( v36 )
        {
          while ( 1 )
          {
            if ( (int)PrjfRBComparePathNodes(v47, v36) < 0 )
            {
              v38 = *(_QWORD *)v36;
              if ( v37 )
              {
                if ( !v38 )
                  goto LABEL_74;
                v38 ^= v36;
              }
              if ( !v38 )
              {
LABEL_74:
                LOBYTE(v34) = 0;
                break;
              }
            }
            else
            {
              v38 = *(_QWORD *)(v36 + 8);
              if ( v37 )
              {
                if ( !v38 )
                  goto LABEL_68;
                v38 ^= v36;
              }
              if ( !v38 )
              {
LABEL_68:
                LOBYTE(v34) = 1;
                break;
              }
            }
            v36 = v38;
          }
        }
        RtlRbInsertNodeEx(v15, v36, v34, v35 + 8);
        if ( !v32 )
        {
          v32 = (char *)v35;
          v4 = v15;
        }
        if ( (_BYTE)P )
          v15 = *(_QWORD *)(v35 + 56);
        v5 = a2;
        v47[0] = 0;
        v40 = *a2;
        WORD1(v47[0]) = *(_WORD *)(*a2 + 2);
        LOWORD(v47[0]) = WORD1(v47[0]);
        *((_QWORD *)&v47[0] + 1) = v40 + 4;
        LOBYTE(P) = PrjfWalkPath(v47, v39, &SourceString);
        if ( !SourceString.Length )
        {
          v2 = v44;
          goto LABEL_81;
        }
      }
      LOBYTE(v34) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( (BYTE2(xmmword_14001A3D0) & 0x10) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v33) = BYTE2(xmmword_14001A3D0) & 0x10;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          532,
          v33,
          v34,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          20,
          34,
          (__int64)WPP_5c05f7cae5513ff3734adbc0d3bd9537_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\mapping.c",
          125,
          PathTree);
      }
      if ( v32 )
      {
        RtlRbRemoveNode(v4, v32 + 8, v34);
        PrjfDeletePathTierNode(v32);
      }
LABEL_87:
      v2 = v44;
      goto LABEL_88;
    }
    if ( v7[2] )
    {
LABEL_20:
      if ( (BYTE2(xmmword_14001A3D0) & 0x10) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v12) = BYTE2(xmmword_14001A3D0) & 0x10;
        LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sD(
          532,
          v12,
          v13,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          20,
          30,
          (__int64)WPP_5c05f7cae5513ff3734adbc0d3bd9537_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\mapping.c",
          228);
      }
      PathTree = -1073741811;
LABEL_88:
      if ( v51 )
        goto LABEL_94;
      v3 = a1;
      goto LABEL_90;
    }
    if ( v15 )
    {
      v16 = *(_QWORD *)v15;
      if ( (*(_BYTE *)(v15 + 8) & 1) == 0 )
        goto LABEL_15;
      if ( v16 )
      {
        v16 ^= v15;
LABEL_15:
        if ( !v16 )
          goto LABEL_16;
        goto LABEL_20;
      }
    }
LABEL_16:
    PathTree = PrjfCreatePathTierNode(&stru_1400155B0, *((_DWORD *)v5 + 2), v15, (__int64)(v7 + 2));
    if ( PathTree >= 0 )
    {
LABEL_81:
      PathTree = 0;
      goto LABEL_94;
    }
    if ( (BYTE2(xmmword_14001A3D0) & 0x10) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v17) = BYTE2(xmmword_14001A3D0) & 0x10;
      LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        532,
        v17,
        v18,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        20,
        31,
        (__int64)WPP_5c05f7cae5513ff3734adbc0d3bd9537_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\mapping.c",
        245,
        PathTree);
    }
    goto LABEL_88;
  }
  PathTree = PrjfCreateInstanceTierNode(v3, &P);
  if ( PathTree >= 0 )
  {
    v7 = P;
    *(_QWORD *)(v3 + 688) = P;
    v51 = 0;
    goto LABEL_9;
  }
  if ( (BYTE2(xmmword_14001A3D0) & 0x10) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = BYTE2(xmmword_14001A3D0) & 0x10;
    LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDL(
      532,
      v6,
      v9,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      20,
      29,
      (__int64)WPP_5c05f7cae5513ff3734adbc0d3bd9537_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\mapping.c",
      189,
      PathTree);
  }
  v7 = P;
LABEL_90:
  if ( v7 )
  {
    *(_QWORD *)(v3 + 688) = 0;
    PrjfDeletePathTree((PVOID)v7[1]);
    v41 = (void *)v7[2];
    if ( v41 )
      PrjfDeletePathTierNode(v41);
    ExFreePoolWithTag(v7, 0x6D6E4A50u);
  }
LABEL_94:
  FltReleaseResource(v2);
  return (unsigned int)PathTree;
}

```

## disassembly

```asm
0x140044cec  mov     [rsp-8+arg_8], rdx
0x140044cf1  mov     [rsp-8+arg_0], rcx
0x140044cf6  push    rbp
0x140044cf7  push    rbx
0x140044cf8  push    rsi
0x140044cf9  push    rdi
0x140044cfa  push    r12
0x140044cfc  push    r13
0x140044cfe  push    r14
0x140044d00  push    r15
0x140044d02  lea     rbp, [rsp-1Fh]
0x140044d07  sub     rsp, 98h
0x140044d0e  lea     r14, [rcx+2B8h]
0x140044d15  mov     rbx, rcx
0x140044d18  xor     r12d, r12d
0x140044d1b  mov     [rbp+57h+var_70], r14
0x140044d1f  xorps   xmm0, xmm0
0x140044d22  mov     [rbp+57h+P], r12
0x140044d26  mov     rcx, r14; Resource
0x140044d29  mov     [rbp+57h+var_68], r12
0x140044d2d  mov     r13, rdx
0x140044d30  movups  xmmword ptr [rbp+57h+SourceString.Length], xmm0
0x140044d34  call    cs:__imp_FltAcquireResourceExclusive
0x140044d3b  nop     dword ptr [rax+rax+00h]
0x140044d40  mov     rsi, [rbx+2B0h]
0x140044d47  test    rsi, rsi
0x140044d4a  jnz     loc_140044DEB
0x140044d50  lea     rdx, [rbp+57h+P]
0x140044d54  mov     rcx, rbx
0x140044d57  call    PrjfCreateInstanceTierNode
0x140044d5c  mov     edi, eax
0x140044d5e  test    eax, eax
0x140044d60  jns     short loc_140044DDA
0x140044d62  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x140044d68  lea     rax, WPP_RECORDER_INITIALIZED
0x140044d6f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140044d76  setnz   r8b
0x140044d7a  and     dl, 10h
0x140044d7d  jnz     short loc_140044D84
0x140044d7f  test    r8b, r8b
0x140044d82  jz      short loc_140044DD1
0x140044d84  mov     r9, cs:WPP_GLOBAL_Control
0x140044d8b  lea     rax, aOnecoreBaseFsG_11; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140044d92  mov     [rsp+0D0h+var_80], edi
0x140044d96  mov     ecx, 214h
0x140044d9b  mov     [rsp+0D0h+var_88], 2BDh
0x140044da3  mov     [rsp+0D0h+var_90], rax
0x140044da8  lea     rax, WPP_5c05f7cae5513ff3734adbc0d3bd9537_Traceguids
0x140044daf  mov     r9, [r9+40h]
0x140044db3  mov     [rsp+0D0h+var_98], rax
0x140044db8  mov     word ptr [rsp+0D0h+var_A0], 1Dh
0x140044dbf  mov     dword ptr [rsp+0D0h+var_A8], 14h
0x140044dc7  mov     byte ptr [rsp+0D0h+var_B0], 2
0x140044dcc  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140044dd1  mov     rsi, [rbp+57h+P]
0x140044dd5  jmp     loc_140045356
0x140044dda  mov     rsi, [rbp+57h+P]
0x140044dde  mov     [rbx+2B0h], rsi
0x140044de5  mov     [rbp+57h+arg_18], r12b
0x140044de9  jmp     short loc_140044DEF
0x140044deb  mov     [rbp+57h+arg_18], 1
0x140044def  mov     rcx, [r13+0]
0x140044df3  lea     r8, [rbp+57h+SourceString]
0x140044df7  xorps   xmm0, xmm0
0x140044dfa  movups  [rbp+57h+var_50], xmm0
0x140044dfe  movzx   eax, word ptr [rcx+2]
0x140044e02  mov     word ptr [rbp+57h+var_50+2], ax
0x140044e06  mov     word ptr [rbp+57h+var_50], ax
0x140044e0a  lea     rax, [rcx+4]
0x140044e0e  lea     rcx, [rbp+57h+var_50]
0x140044e12  mov     qword ptr [rbp+57h+var_50+8], rax
0x140044e16  call    PrjfWalkPath
0x140044e1b  mov     r15b, al
0x140044e1e  mov     rbx, [rsi+8]
0x140044e22  mov     byte ptr [rbp+57h+P], al
0x140044e25  cmp     [rbp+57h+SourceString.Length], r12w
0x140044e2a  jnz     loc_140044F7D
0x140044e30  lea     rcx, [rsi+10h]
0x140044e34  cmp     [rcx], r12
0x140044e37  jnz     loc_140044F08
0x140044e3d  test    rbx, rbx
0x140044e40  jz      short loc_140044E5C
0x140044e42  test    byte ptr [rbx+8], 1
0x140044e46  mov     rax, [rbx]
0x140044e49  jz      short loc_140044E53
0x140044e4b  test    rax, rax
0x140044e4e  jz      short loc_140044E5C
0x140044e50  xor     rax, rbx
0x140044e53  test    rax, rax
0x140044e56  jnz     loc_140044F08
0x140044e5c  mov     eax, [r13+8]
0x140044e60  mov     r8b, 1
0x140044e63  mov     r9, [r13+0]
0x140044e67  mov     edx, 11h
0x140044e6c  mov     [rsp+0D0h+var_A0], rcx; __int64
0x140044e71  lea     rcx, stru_1400155B0; SourceString
0x140044e78  mov     [rsp+0D0h+var_A8], rbx; __int64
0x140044e7d  mov     [rsp+0D0h+var_B0], eax; int
0x140044e81  call    PrjfCreatePathTierNode
0x140044e86  mov     edi, eax
0x140044e88  test    eax, eax
0x140044e8a  jns     loc_1400452AE
0x140044e90  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x140044e96  lea     rax, WPP_RECORDER_INITIALIZED
0x140044e9d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140044ea4  setnz   r8b
0x140044ea8  and     dl, 10h
0x140044eab  jnz     short loc_140044EB6
0x140044ead  test    r8b, r8b
0x140044eb0  jz      loc_14004534C
0x140044eb6  mov     r9, cs:WPP_GLOBAL_Control
0x140044ebd  lea     rax, aOnecoreBaseFsG_11; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140044ec4  mov     [rsp+0D0h+var_80], edi
0x140044ec8  mov     ecx, 214h
0x140044ecd  mov     [rsp+0D0h+var_88], 2F5h
0x140044ed5  mov     [rsp+0D0h+var_90], rax
0x140044eda  lea     rax, WPP_5c05f7cae5513ff3734adbc0d3bd9537_Traceguids
0x140044ee1  mov     r9, [r9+40h]
0x140044ee5  mov     [rsp+0D0h+var_98], rax
0x140044eea  mov     word ptr [rsp+0D0h+var_A0], 1Fh
0x140044ef1  mov     dword ptr [rsp+0D0h+var_A8], 14h
0x140044ef9  mov     byte ptr [rsp+0D0h+var_B0], 2
0x140044efe  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140044f03  jmp     loc_14004534C
0x140044f08  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x140044f0e  lea     rax, WPP_RECORDER_INITIALIZED
0x140044f15  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140044f1c  setnz   r8b
0x140044f20  and     dl, 10h
0x140044f23  jnz     short loc_140044F2A
0x140044f25  test    r8b, r8b
0x140044f28  jz      short loc_140044F73
0x140044f2a  mov     r9, cs:WPP_GLOBAL_Control
0x140044f31  lea     rax, aOnecoreBaseFsG_11; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140044f38  mov     [rsp+0D0h+var_88], 2E4h
0x140044f40  mov     ecx, 214h
0x140044f45  mov     [rsp+0D0h+var_90], rax
0x140044f4a  lea     rax, WPP_5c05f7cae5513ff3734adbc0d3bd9537_Traceguids
0x140044f51  mov     [rsp+0D0h+var_98], rax
0x140044f56  mov     r9, [r9+40h]
0x140044f5a  mov     word ptr [rsp+0D0h+var_A0], 1Eh
0x140044f61  mov     dword ptr [rsp+0D0h+var_A8], 14h
0x140044f69  mov     byte ptr [rsp+0D0h+var_B0], 2
0x140044f6e  call    WPP_RECORDER_AND_TRACE_SF_sD
0x140044f73  mov     edi, 0C000000Dh
0x140044f78  jmp     loc_14004534C
0x140044f7d  test    byte ptr [rbx+8], 1
0x140044f81  lea     rax, [rbp+57h+SourceString]
0x140044f85  mov     rdi, [rbx]
0x140044f88  movups  [rbp+57h+var_50], xmm0
0x140044f8c  mov     qword ptr [rbp+57h+var_50], rax
0x140044f90  mov     byte ptr [rbp+57h+var_50+8], 1
0x140044f94  jz      short loc_140044FA3
0x140044f96  test    rdi, rdi
0x140044f99  jz      short loc_140044FA0
0x140044f9b  xor     rdi, rbx
0x140044f9e  jmp     short loc_140044FA3
0x140044fa0  mov     rdi, r12
0x140044fa3  movzx   r14d, byte ptr [rbx+8]
0x140044fa8  and     r14d, 1
0x140044fac  test    rdi, rdi
0x140044faf  jz      loc_1400450FB
0x140044fb5  mov     rdx, rdi
0x140044fb8  lea     rcx, [rbp+57h+var_50]
0x140044fbc  call    PrjfRBComparePathNodes
0x140044fc1  test    eax, eax
0x140044fc3  jns     short loc_140044FCA
0x140044fc5  mov     rax, [rdi]
0x140044fc8  jmp     short loc_140044FD0
0x140044fca  jle     short loc_140044FE7
0x140044fcc  mov     rax, [rdi+8]
0x140044fd0  test    r14d, r14d
0x140044fd3  jz      short loc_140044FDF
0x140044fd5  test    rax, rax
0x140044fd8  jz      short loc_140044FDF
0x140044fda  xor     rdi, rax
0x140044fdd  jmp     short loc_140044FE2
0x140044fdf  mov     rdi, rax
0x140044fe2  test    rdi, rdi
0x140044fe5  jnz     short loc_140044FB5
0x140044fe7  test    rdi, rdi
0x140044fea  jz      loc_1400450FB
0x140044ff0  add     rdi, 0FFFFFFFFFFFFFFF8h
0x140044ff4  mov     [rbp+57h+var_68], rdi
0x140044ff8  test    r15b, r15b
0x140044ffb  jz      loc_140045167
0x140045001  mov     rcx, [r13+0]
0x140045005  lea     r8, [rbp+57h+SourceString]
0x140045009  xorps   xmm0, xmm0
0x14004500c  movups  [rbp+57h+var_50], xmm0
0x140045010  movzx   eax, word ptr [rcx+2]
0x140045014  mov     word ptr [rbp+57h+var_50+2], ax
0x140045018  mov     word ptr [rbp+57h+var_50], ax
0x14004501c  lea     rax, [rcx+4]
0x140045020  lea     rcx, [rbp+57h+var_50]
0x140045024  mov     qword ptr [rbp+57h+var_50+8], rax
0x140045028  call    PrjfWalkPath
0x14004502d  lea     r14, [rdi+38h]
0x140045031  mov     byte ptr [rbp+57h+P], al
0x140045034  mov     rbx, [r14]
0x140045037  mov     r15b, al
0x14004503a  test    rbx, rbx
0x14004503d  jz      short loc_14004506E
0x14004503f  test    byte ptr [rbx+8], 1
0x140045043  jz      short loc_140045059
0x140045045  mov     rdx, [rbx]
0x140045048  test    rdx, rdx
0x14004504b  jz      loc_1400450F4
0x140045051  mov     rcx, rbx
0x140045054  xor     rcx, rdx
0x140045057  jmp     short loc_14004505C
0x140045059  mov     rcx, [rbx]
0x14004505c  test    rcx, rcx
0x14004505f  jz      loc_1400450F4
0x140045065  mov     [rbp+57h+var_68], r12
0x140045069  jmp     loc_140044F7D
0x14004506e  mov     rcx, r14
0x140045071  call    PrjfCreatePathTree
0x140045076  mov     edi, eax
0x140045078  test    eax, eax
0x14004507a  jns     short loc_1400450F4
0x14004507c  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x140045082  lea     rax, WPP_RECORDER_INITIALIZED
0x140045089  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140045090  setnz   r8b
0x140045094  and     dl, 10h
0x140045097  jnz     short loc_1400450A2
0x140045099  test    r8b, r8b
0x14004509c  jz      loc_140045348
0x1400450a2  mov     r9, cs:WPP_GLOBAL_Control
0x1400450a9  lea     rax, aOnecoreBaseFsG_11; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400450b0  mov     [rsp+0D0h+var_80], edi
0x1400450b4  mov     ecx, 214h
0x1400450b9  mov     [rsp+0D0h+var_88], 346h
0x1400450c1  mov     [rsp+0D0h+var_90], rax
0x1400450c6  lea     rax, WPP_5c05f7cae5513ff3734adbc0d3bd9537_Traceguids
0x1400450cd  mov     r9, [r9+40h]
0x1400450d1  mov     [rsp+0D0h+var_98], rax
0x1400450d6  mov     word ptr [rsp+0D0h+var_A0], 21h ; '!'
0x1400450dd  mov     dword ptr [rsp+0D0h+var_A8], 14h
0x1400450e5  mov     byte ptr [rsp+0D0h+var_B0], 2
0x1400450ea  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x1400450ef  jmp     loc_140045348
0x1400450f4  mov     rbx, [r14]
0x1400450f7  mov     [rbp+57h+var_68], r12
0x1400450fb  mov     r14, r12
0x1400450fe  xor     edi, edi
0x140045100  mov     r9, [r13+0]
0x140045104  lea     rax, [rbp+57h+var_68]
0x140045108  mov     [rsp+0D0h+var_A0], rax; __int64
0x14004510d  lea     rcx, [rbp+57h+SourceString]; SourceString
0x140045111  mov     eax, [r13+8]
0x140045115  mov     edx, edi
0x140045117  xorps   xmm0, xmm0
0x14004511a  mov     [rsp+0D0h+var_A8], rdi; __int64
0x14004511f  test    r15b, r15b
0x140045122  mov     [rsp+0D0h+var_B0], eax; int
0x140045126  mov     r8b, r15b
0x140045129  setz    dl
0x14004512c  movups  [rbp+57h+var_50], xmm0
0x140045130  call    PrjfCreatePathTierNode
0x140045135  xor     ecx, ecx
0x140045137  mov     edi, eax
0x140045139  test    eax, eax
0x14004513b  js      loc_1400452B6
0x140045141  test    byte ptr [rbx+8], 1
0x140045145  mov     r13, [rbp+57h+var_68]
0x140045149  mov     rdi, [rbx]
0x14004514c  mov     byte ptr [rbp+57h+var_50+8], cl
0x14004514f  lea     rax, [r13+20h]
0x140045153  mov     qword ptr [rbp+57h+var_50], rax
0x140045157  jz      loc_1400451DF
0x14004515d  test    rdi, rdi
0x140045160  jz      short loc_1400451DC
0x140045162  xor     rdi, rbx
0x140045165  jmp     short loc_1400451DF
0x140045167  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x14004516d  lea     rax, WPP_RECORDER_INITIALIZED
0x140045174  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004517b  setnz   r8b
0x14004517f  and     dl, 10h
0x140045182  jnz     short loc_140045189
0x140045184  test    r8b, r8b
0x140045187  jz      short loc_1400451D2
0x140045189  mov     r9, cs:WPP_GLOBAL_Control
0x140045190  lea     rax, aOnecoreBaseFsG_11; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140045197  mov     [rsp+0D0h+var_88], 320h
0x14004519f  mov     ecx, 214h
0x1400451a4  mov     [rsp+0D0h+var_90], rax
0x1400451a9  lea     rax, WPP_5c05f7cae5513ff3734adbc0d3bd9537_Traceguids
0x1400451b0  mov     [rsp+0D0h+var_98], rax
0x1400451b5  mov     r9, [r9+40h]
0x1400451b9  mov     word ptr [rsp+0D0h+var_A0], 20h ; ' '
0x1400451c0  mov     dword ptr [rsp+0D0h+var_A8], 14h
0x1400451c8  mov     byte ptr [rsp+0D0h+var_B0], 2
0x1400451cd  call    WPP_RECORDER_AND_TRACE_SF_sD
0x1400451d2  mov     edi, 0C000000Dh
0x1400451d7  jmp     loc_140045348
0x1400451dc  mov     rdi, rcx
0x1400451df  movzx   r15d, byte ptr [rbx+8]
  ... truncated ...
```
