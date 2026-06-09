# EfspPostCreate

- ea: `0x14005202c`
- end: `0x140052525`
- name: `EfspPostCreate`
- size: `1273`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140051de0`

## callees

- `0x140001010`
- `0x1400010b4`
- `0x140008008`
- `0x1400080d4`
- `0x14000c230`
- `0x14002006c`
- `0x14005202c`
- `0x140052604`
- `0x1400528bc`
- `0x140054390`
- `0x140054ce4`
- `0x14005693c`
- `0x140057890`
- `0x140058ce4`
- `0x1400592f0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400521ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400521ac`
- `ntoskrnl!PsGetCurrentThreadTeb` at `0x14005221f`
- `ntoskrnl!PsGetCurrentThreadTeb` at `0x14005221f`
- `ntoskrnl!FsRtlGetEcpListFromIrp` at `0x1400522b1`
- `ntoskrnl!FsRtlGetEcpListFromIrp` at `0x1400522b1`

## pseudocode

```c
__int64 __fastcall EfspPostCreate(
        __int64 a1,
        __int64 a2,
        IRP *a3,
        __int64 a4,
        void *a5,
        char a6,
        __int64 a7,
        __int64 *a8,
        __int64 *a9,
        __int64 a10,
        SECURITY_IMPERSONATION_LEVEL a11,
        __int64 a12,
        char a13,
        __int64 a14,
        __int64 a15)
{
  __int64 v15; // rdi
  char *v16; // r13
  int EcpListFromIrp; // edi
  BOOL v18; // esi
  int v19; // esi
  unsigned int v20; // esi
  __int64 v21; // rcx
  bool v22; // r13
  __int64 ULong64FromUser; // rdi
  char *CurrentThreadTeb; // rax
  int v25; // r13d
  __int64 v26; // r10
  __int64 *v27; // rsi
  char v29; // [rsp+28h] [rbp-130h]
  _BYTE v30[4]; // [rsp+50h] [rbp-108h] BYREF
  int v31; // [rsp+54h] [rbp-104h] BYREF
  __int64 v32; // [rsp+58h] [rbp-100h] BYREF
  __int64 v33; // [rsp+60h] [rbp-F8h]
  void *v34; // [rsp+68h] [rbp-F0h]
  int *v35; // [rsp+70h] [rbp-E8h]
  PIRP Irp; // [rsp+78h] [rbp-E0h]
  __int64 v37; // [rsp+80h] [rbp-D8h] BYREF
  __int64 v38; // [rsp+88h] [rbp-D0h] BYREF
  __int64 v39; // [rsp+90h] [rbp-C8h]
  __int64 v40; // [rsp+98h] [rbp-C0h]
  PECP_LIST EcpList; // [rsp+A0h] [rbp-B8h] BYREF
  __int64 v42; // [rsp+A8h] [rbp-B0h]
  __int64 v43; // [rsp+B0h] [rbp-A8h]
  __int64 *v44; // [rsp+B8h] [rbp-A0h]
  __int64 v45; // [rsp+C0h] [rbp-98h]
  __int64 v46; // [rsp+C8h] [rbp-90h]
  IRP *v47; // [rsp+D0h] [rbp-88h]
  __int64 *v48; // [rsp+D8h] [rbp-80h]
  __int64 v49; // [rsp+E0h] [rbp-78h]
  __int128 v50; // [rsp+E8h] [rbp-70h] BYREF
  _BYTE v51[32]; // [rsp+F8h] [rbp-60h] BYREF
  __int64 *v52; // [rsp+118h] [rbp-40h]
  __int64 v53; // [rsp+120h] [rbp-38h]

  v32 = a4;
  Irp = a3;
  v42 = a2;
  v43 = a1;
  v49 = a15;
  v45 = a1;
  v46 = a2;
  v47 = a3;
  v34 = a5;
  v33 = a7;
  v44 = a8;
  v48 = a9;
  v40 = a12;
  v15 = a15;
  v35 = (int *)a15;
  v31 = 0;
  v50 = 0;
  v38 = 0;
  v37 = 0;
  EcpList = 0;
  v30[0] = 0;
  v16 = *(char **)(a15 + 8);
  if ( (*(_DWORD *)a15 & 0x40000000) == 0 )
  {
    EcpListFromIrp = 0;
    v18 = 0;
    if ( *a8 && *a9 && v16 )
    {
      v18 = (unsigned __int8)EfsFindInCache(v16 + 16, *a8, *a9, a10) != 0;
      a4 = v32;
    }
    if ( v18 )
      goto LABEL_47;
    v15 = a15;
  }
  *(_DWORD *)a15 &= ~0x40000000u;
  v19 = *(_DWORD *)a15;
  if ( (*(_DWORD *)(*(_QWORD *)(a4 + 8) + 20LL) & 0x27) == 0 && v19 < 0 && (v19 & 3) == 0 )
  {
    if ( v16 )
    {
      ExFreePoolWithTag(v16, 0);
      *(_QWORD *)(v15 + 8) = 0;
    }
    v19 = -2147483640;
    *(_DWORD *)a15 = -2147483640;
  }
  v20 = v19 & 0xFFFFFFF;
  LODWORD(v32) = v20;
  if ( !(unsigned int)EfspPostCreateActionNeedsData(v20) )
  {
    v25 = a15;
    goto LABEL_39;
  }
  if ( v20 == 1 || (v22 = 0, v20 == 2) )
  {
    if ( (*(_DWORD *)(v15 + 4) & 1) != 0 )
    {
      EcpListFromIrp = -1073741662;
      EfspTraceLogAssert(v21, 1, 453, 3221225634LL);
      goto LABEL_47;
    }
    ULong64FromUser = 0;
    v39 = 0;
    CurrentThreadTeb = (char *)PsGetCurrentThreadTeb();
    if ( CurrentThreadTeb )
    {
      ULong64FromUser = RtlReadULong64FromUser(CurrentThreadTeb + 5920);
      v39 = ULong64FromUser;
    }
    v22 = ULong64FromUser == 3644083109LL;
  }
  EcpListFromIrp = FsRtlGetEcpListFromIrp(Irp, &EcpList);
  if ( EcpListFromIrp < 0 )
    goto LABEL_47;
  v29 = v22;
  v25 = (int)v35;
  EcpListFromIrp = EfspPostCreateImpersonateAndGetData(
                     v35,
                     v34,
                     a11,
                     (__int64)EcpList,
                     v33,
                     v29,
                     v40,
                     (__int64)v30,
                     &v37,
                     &v38);
  if ( v20 - 1 <= 1 )
    EdpEnforcementLog_AutomaticEncryption(v33 + 88, *a9, (unsigned int)EcpListFromIrp);
  if ( EcpListFromIrp < 0 )
  {
    if ( v20 - 1 <= 1
      && (unsigned __int8)EfspHasPrivilege(v34)
      && (unsigned int)dword_140017130 > 5
      && (unsigned __int8)tlgKeywordOn(&dword_140017130, 0x200000000000LL) )
    {
      LODWORD(v32) = EcpListFromIrp;
      v52 = &v32;
      v53 = 4;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140017130, &unk_140010D74, 0, 0, 3, v51);
    }
    if ( v20 == 4 )
      EdpEnforcementLog_FileAccessDenied(v33 + 88, *a9, (unsigned int)EcpListFromIrp);
    goto LABEL_33;
  }
  if ( !v30[0] )
  {
LABEL_39:
    v26 = 0;
    if ( !a13 )
      v26 = v38;
    EcpListFromIrp = EfspPostCreatePrepareAndSendFsctl(
                       v43,
                       v42,
                       (_DWORD)Irp,
                       v25,
                       a6,
                       v37,
                       v26,
                       a14,
                       (__int64)&v31,
                       (__int64)&v50);
    if ( EcpListFromIrp >= 0 )
    {
      if ( v31 )
      {
        v27 = v44;
        if ( *v44 )
        {
          if ( (int)EfsRefreshCache(&v50, *v44, *a9, a10) >= 0 )
          {
            *v27 = 0;
            *a9 = 0;
          }
          EcpListFromIrp = 0;
        }
      }
    }
    goto LABEL_47;
  }
  if ( v20 != 4 || (*(_DWORD *)a15 & 0x20000000) == 0 )
LABEL_33:
    EcpListFromIrp = -1073741790;
LABEL_47:
  if ( v37 )
    FreeKRpcMemory(v37);
  if ( v38 )
    FreeKRpcMemory(v38);
  return (unsigned int)EcpListFromIrp;
}

```

## disassembly

```asm
0x14005202c  mov     r11, rsp
0x14005202f  mov     [r11+20h], rsi
0x140052033  push    rdi
0x140052034  push    r12
0x140052036  push    r13
0x140052038  push    r14
0x14005203a  push    r15
0x14005203c  sub     rsp, 130h
0x140052043  mov     rax, cs:__security_cookie
0x14005204a  xor     rax, rsp
0x14005204d  mov     [rsp+158h+var_30], rax
0x140052055  mov     [rsp+158h+var_100], r9
0x14005205a  mov     rax, r8
0x14005205d  mov     [rsp+158h+Irp], rax
0x140052062  mov     [rsp+158h+var_B0], rdx
0x14005206a  mov     [rsp+158h+var_A8], rcx
0x140052072  mov     r15, [rsp+158h+arg_70]
0x14005207a  mov     [rsp+158h+var_78], r15
0x140052082  mov     [rsp+158h+var_98], rcx
0x14005208a  mov     [rsp+158h+var_90], rdx
0x140052092  mov     [rsp+158h+var_88], rax
0x14005209a  mov     rax, [rsp+158h+arg_20]
0x1400520a2  mov     [rsp+158h+var_F0], rax
0x1400520a7  mov     rax, [rsp+158h+arg_30]
0x1400520af  mov     [rsp+158h+var_F8], rax
0x1400520b4  mov     rcx, [rsp+158h+arg_38]
0x1400520bc  mov     [rsp+158h+var_A0], rcx
0x1400520c4  mov     r12, [rsp+158h+arg_40]
0x1400520cc  mov     [rsp+158h+var_80], r12
0x1400520d4  mov     rax, [rsp+158h+arg_58]
0x1400520dc  mov     [rsp+158h+var_C0], rax
0x1400520e4  mov     rdi, r15
0x1400520e7  mov     [rsp+158h+var_E8], r15
0x1400520ec  mov     [rsp+158h+var_104], 0
0x1400520f4  xorps   xmm0, xmm0
0x1400520f7  movups  xmmword ptr [r11-70h], xmm0
0x1400520fc  mov     qword ptr [r11-0D0h], 0
0x140052107  mov     qword ptr [r11-0D8h], 0
0x140052112  mov     qword ptr [r11-0B8h], 0
0x14005211d  mov     [rsp+158h+var_108], 0
0x140052122  mov     r13, [r15+8]
0x140052126  test    dword ptr [r15], 40000000h
0x14005212d  jnz     short loc_14005217E
0x14005212f  xor     edi, edi
0x140052131  mov     rdx, [rcx]
0x140052134  xor     esi, esi
0x140052136  test    rdx, rdx
0x140052139  jz      short loc_14005216B
0x14005213b  mov     r8, [r12]
0x14005213f  test    r8, r8
0x140052142  jz      short loc_14005216B
0x140052144  test    r13, r13
0x140052147  jz      short loc_14005216B
0x140052149  lea     rcx, [r13+10h]
0x14005214d  mov     r9, [rsp+158h+arg_48]
0x140052155  call    EfsFindInCache
0x14005215a  lea     r14d, [rdi+1]
0x14005215e  test    al, al
0x140052160  cmovnz  esi, r14d
0x140052164  mov     r9, [rsp+158h+var_100]
0x140052169  jmp     short loc_140052171
0x14005216b  mov     r14d, 1
0x140052171  test    esi, esi
0x140052173  jnz     loc_1400524D5
0x140052179  mov     rdi, r15
0x14005217c  jmp     short loc_140052184
0x14005217e  mov     r14d, 1
0x140052184  btr     dword ptr [r15], 1Eh
0x140052189  mov     esi, [r15]
0x14005218c  mov     rax, [r9+8]
0x140052190  mov     ecx, [rax+14h]
0x140052193  test    cl, 27h
0x140052196  jnz     short loc_1400521C8
0x140052198  test    esi, esi
0x14005219a  jns     short loc_1400521C8
0x14005219c  test    sil, 3
0x1400521a0  jnz     short loc_1400521C8
0x1400521a2  test    r13, r13
0x1400521a5  jz      short loc_1400521C0
0x1400521a7  xor     edx, edx; Tag
0x1400521a9  mov     rcx, r13; P
0x1400521ac  call    cs:__imp_ExFreePoolWithTag
0x1400521b3  nop     dword ptr [rax+rax+00h]
0x1400521b8  mov     qword ptr [rdi+8], 0
0x1400521c0  mov     esi, 80000008h
0x1400521c5  mov     [r15], esi
0x1400521c8  and     esi, 0FFFFFFFh
0x1400521ce  mov     dword ptr [rsp+158h+var_100], esi
0x1400521d2  mov     ecx, esi
0x1400521d4  call    EfspPostCreateActionNeedsData
0x1400521d9  test    eax, eax
0x1400521db  jz      loc_140052415
0x1400521e1  cmp     esi, r14d
0x1400521e4  jz      short loc_1400521F2
0x1400521e6  xor     r13b, r13b
0x1400521e9  cmp     esi, 2
0x1400521ec  jnz     loc_1400522A4
0x1400521f2  mov     eax, [rdi+4]
0x1400521f5  test    r14b, al
0x1400521f8  jz      short loc_140052215
0x1400521fa  mov     edi, 0C00000A2h
0x1400521ff  mov     r9d, edi
0x140052202  mov     r8d, 1C5h
0x140052208  mov     edx, r14d
0x14005220b  call    EfspTraceLogAssert
0x140052210  jmp     loc_1400524D5
0x140052215  xor     edi, edi
0x140052217  mov     [rsp+158h+var_C8], rdi
0x14005221f  call    cs:__imp_PsGetCurrentThreadTeb
0x140052226  nop     dword ptr [rax+rax+00h]
0x14005222b  test    rax, rax
0x14005222e  jz      short loc_140052298
0x140052230  lea     rcx, [rax+1720h]
0x140052237  call    RtlReadULong64FromUser
0x14005223c  mov     rdi, rax
0x14005223f  mov     [rsp+158h+var_C8], rax
0x140052247  jmp     short loc_140052298
0x140052249  mov     r14d, 1
0x14005224f  mov     rdi, [rsp+158h+var_C8]
0x140052257  mov     rax, [rsp+158h+var_98]
0x14005225f  mov     [rsp+158h+var_A8], rax
0x140052267  mov     rax, [rsp+158h+var_90]
0x14005226f  mov     [rsp+158h+var_B0], rax
0x140052277  mov     rax, [rsp+158h+var_88]
0x14005227f  mov     [rsp+158h+Irp], rax
0x140052284  mov     r12, [rsp+158h+var_80]
0x14005228c  mov     r15, [rsp+158h+var_78]
0x140052294  mov     esi, dword ptr [rsp+158h+var_100]
0x140052298  mov     eax, 0D9344BA5h
0x14005229d  cmp     rdi, rax
0x1400522a0  setz    r13b
0x1400522a4  lea     rdx, [rsp+158h+EcpList]; EcpList
0x1400522ac  mov     rcx, [rsp+158h+Irp]; Irp
0x1400522b1  call    cs:__imp_FsRtlGetEcpListFromIrp
0x1400522b8  nop     dword ptr [rax+rax+00h]
0x1400522bd  mov     edi, eax
0x1400522bf  test    eax, eax
0x1400522c1  js      loc_1400524D5
0x1400522c7  lea     rax, [rsp+158h+var_D0]
0x1400522cf  mov     [rsp+158h+var_110], rax
0x1400522d4  lea     rax, [rsp+158h+var_D8]
0x1400522dc  mov     [rsp+158h+var_118], rax
0x1400522e1  lea     rax, [rsp+158h+var_108]
0x1400522e6  mov     [rsp+158h+var_120], rax
0x1400522eb  mov     rax, [rsp+158h+var_C0]
0x1400522f3  mov     [rsp+158h+var_128], rax
0x1400522f8  mov     byte ptr [rsp+158h+var_130], r13b
0x1400522fd  mov     rax, [rsp+158h+var_F8]
0x140052302  mov     [rsp+158h+var_138], rax
0x140052307  mov     r9, [rsp+158h+EcpList]
0x14005230f  mov     r8d, [rsp+158h+arg_50]
0x140052317  mov     rdx, [rsp+158h+var_F0]
0x14005231c  mov     r13, [rsp+158h+var_E8]
0x140052321  mov     rcx, r13
0x140052324  call    EfspPostCreateImpersonateAndGetData
0x140052329  mov     edi, eax
0x14005232b  lea     eax, [rsi-1]
0x14005232e  cmp     eax, r14d
0x140052331  ja      short loc_140052348
0x140052333  mov     rcx, [rsp+158h+var_F8]
0x140052338  add     rcx, 58h ; 'X'
0x14005233c  mov     r8d, edi
0x14005233f  mov     rdx, [r12]
0x140052343  call    EdpEnforcementLog_AutomaticEncryption
0x140052348  test    edi, edi
0x14005234a  jns     loc_1400523FA
0x140052350  lea     eax, [rsi-1]
0x140052353  cmp     eax, r14d
0x140052356  ja      short loc_1400523D6
0x140052358  mov     rcx, [rsp+158h+var_F0]
0x14005235d  call    EfspHasPrivilege
0x140052362  test    al, al
0x140052364  jz      short loc_1400523D6
0x140052366  mov     eax, cs:dword_140017130
0x14005236c  cmp     eax, 5
0x14005236f  jbe     short loc_1400523D6
0x140052371  mov     rdx, 200000000000h
0x14005237b  lea     rcx, dword_140017130
0x140052382  call    _tlgKeywordOn
0x140052387  test    al, al
0x140052389  jz      short loc_1400523D6
0x14005238b  mov     dword ptr [rsp+158h+var_100], edi
0x14005238f  lea     rax, [rsp+158h+var_100]
0x140052394  mov     [rsp+158h+var_40], rax
0x14005239c  mov     [rsp+158h+var_38], 4
0x1400523a8  lea     rax, [rsp+158h+var_60]
0x1400523b0  mov     [rsp+158h+var_130], rax
0x1400523b5  mov     dword ptr [rsp+158h+var_138], 3
0x1400523bd  xor     r9d, r9d
0x1400523c0  xor     r8d, r8d
0x1400523c3  lea     rdx, unk_140010D74
0x1400523ca  lea     rcx, dword_140017130
0x1400523d1  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400523d6  cmp     esi, 4
0x1400523d9  jnz     short loc_1400523F0
0x1400523db  mov     rcx, [rsp+158h+var_F8]
0x1400523e0  add     rcx, 58h ; 'X'
0x1400523e4  mov     r8d, edi
0x1400523e7  mov     rdx, [r12]
0x1400523eb  call    EdpEnforcementLog_FileAccessDenied
0x1400523f0  mov     edi, 0C0000022h
0x1400523f5  jmp     loc_1400524D5
0x1400523fa  cmp     [rsp+158h+var_108], 0
0x1400523ff  jz      short loc_140052418
0x140052401  cmp     esi, 4
0x140052404  jnz     short loc_1400523F0
0x140052406  test    dword ptr [r15], 20000000h
0x14005240d  jnz     loc_1400524D5
0x140052413  jmp     short loc_1400523F0
0x140052415  mov     r13, r15
0x140052418  xor     r10d, r10d
0x14005241b  cmp     [rsp+158h+arg_60], r10b
0x140052423  cmovz   r10, [rsp+158h+var_D0]
0x14005242c  lea     rax, [rsp+158h+var_70]
0x140052434  mov     [rsp+158h+var_110], rax
0x140052439  lea     rax, [rsp+158h+var_104]
0x14005243e  mov     [rsp+158h+var_118], rax
0x140052443  mov     rax, [rsp+158h+arg_68]
0x14005244b  mov     [rsp+158h+var_120], rax
0x140052450  mov     [rsp+158h+var_128], r10
0x140052455  mov     rax, [rsp+158h+var_D8]
0x14005245d  mov     [rsp+158h+var_130], rax
0x140052462  mov     eax, dword ptr [rsp+158h+arg_28]
0x140052469  mov     dword ptr [rsp+158h+var_138], eax
0x14005246d  mov     r9, r13
0x140052470  mov     r8, [rsp+158h+Irp]
0x140052475  mov     rdx, [rsp+158h+var_B0]
0x14005247d  mov     rcx, [rsp+158h+var_A8]
0x140052485  call    EfspPostCreatePrepareAndSendFsctl
0x14005248a  mov     edi, eax
0x14005248c  test    eax, eax
0x14005248e  js      short loc_1400524D5
0x140052490  cmp     [rsp+158h+var_104], 0
0x140052495  jz      short loc_1400524D5
0x140052497  mov     rsi, [rsp+158h+var_A0]
0x14005249f  mov     rdx, [rsi]
0x1400524a2  test    rdx, rdx
0x1400524a5  jz      short loc_1400524D5
0x1400524a7  mov     r9, [rsp+158h+arg_48]
0x1400524af  mov     r8, [r12]
0x1400524b3  lea     rcx, [rsp+158h+var_70]
0x1400524bb  call    EfsRefreshCache
0x1400524c0  test    eax, eax
0x1400524c2  js      short loc_1400524D3
0x1400524c4  mov     qword ptr [rsi], 0
0x1400524cb  mov     qword ptr [r12], 0
0x1400524d3  xor     edi, edi
0x1400524d5  mov     rcx, [rsp+158h+var_D8]
0x1400524dd  test    rcx, rcx
0x1400524e0  jz      short loc_1400524E7
0x1400524e2  call    FreeKRpcMemory
0x1400524e7  mov     rcx, [rsp+158h+var_D0]
0x1400524ef  test    rcx, rcx
0x1400524f2  jz      short loc_1400524F9
0x1400524f4  call    FreeKRpcMemory
0x1400524f9  mov     eax, edi
0x1400524fb  mov     rcx, [rsp+158h+var_30]
0x140052503  xor     rcx, rsp; StackCookie
0x140052506  call    __security_check_cookie
0x14005250b  mov     rsi, [rsp+158h+arg_18]
0x140052513  add     rsp, 130h
0x14005251a  pop     r15
0x14005251c  pop     r14
0x14005251e  pop     r13
0x140052520  pop     r12
0x140052522  pop     rdi
0x140052523  retn
```
