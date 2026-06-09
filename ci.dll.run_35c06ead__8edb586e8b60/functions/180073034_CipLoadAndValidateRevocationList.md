# CipLoadAndValidateRevocationList

- ea: `0x180073034`
- end: `0x18007351c`
- name: `CipLoadAndValidateRevocationList`
- size: `1256`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180058048`
- `0x18008d750`
- `0x1800e5228`

## callees

- `0x18001e160`
- `0x18002c0d0`
- `0x180060768`
- `0x180073034`
- `0x180073524`
- `0x18008eddc`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x18007315b`
- `ntoskrnl!KeStackAttachProcess` at `0x18007315b`
- `ntoskrnl!ExFreePoolWithTag` at `0x180073389`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800733a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800733b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800733d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x180073389`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800733a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800733b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800733d1`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1800734e6`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1800734e6`
- `ntoskrnl!MmUnlockPages` at `0x1800733e9`
- `ntoskrnl!MmUnlockPages` at `0x18007342d`
- `ntoskrnl!MmUnlockPages` at `0x18007346d`
- `ntoskrnl!MmUnlockPages` at `0x1800734ac`
- `ntoskrnl!MmUnlockPages` at `0x1800733e9`
- `ntoskrnl!MmUnlockPages` at `0x18007342d`
- `ntoskrnl!MmUnlockPages` at `0x18007346d`
- `ntoskrnl!MmUnlockPages` at `0x1800734ac`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x180073415`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x180073455`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x180073494`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x1800734d3`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x180073415`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x180073455`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x180073494`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x1800734d3`
- `ntoskrnl!IoFreeMdl` at `0x1800733f8`
- `ntoskrnl!IoFreeMdl` at `0x18007343c`
- `ntoskrnl!IoFreeMdl` at `0x18007347c`
- `ntoskrnl!IoFreeMdl` at `0x1800734bb`
- `ntoskrnl!IoFreeMdl` at `0x1800733f8`
- `ntoskrnl!IoFreeMdl` at `0x18007343c`
- `ntoskrnl!IoFreeMdl` at `0x18007347c`
- `ntoskrnl!IoFreeMdl` at `0x1800734bb`

## string_xrefs

- `0x18007307b`: `\SystemRoot\System32\CodeIntegrity\driver.stl`
- `0x180073091`: `\SystemRoot\System32\CodeIntegrity\previous.driver.stl`
- `0x1800730aa`: `\SystemRoot\System32\CodeIntegrity\Update\driver.stl`
- `0x1800730b5`: `\SystemRoot\System32\CodeIntegrity\Update\Previous\driver.stl`

## pseudocode

```c
__int64 __fastcall CipLoadAndValidateRevocationList(__int64 a1)
{
  int v2; // ebx
  int v3; // eax
  int v4; // eax
  int v5; // eax
  struct _MDL *v6; // rdi
  struct _MDL *v7; // rdi
  struct _MDL *v8; // rdi
  struct _MDL *v9; // rdi
  int v11; // [rsp+40h] [rbp-C0h] BYREF
  int v12; // [rsp+44h] [rbp-BCh] BYREF
  int v13; // [rsp+48h] [rbp-B8h] BYREF
  int v14; // [rsp+4Ch] [rbp-B4h] BYREF
  PVOID P; // [rsp+50h] [rbp-B0h] BYREF
  PVOID v16; // [rsp+58h] [rbp-A8h] BYREF
  PVOID v17; // [rsp+60h] [rbp-A0h] BYREF
  PVOID v18; // [rsp+68h] [rbp-98h] BYREF
  PVOID BaseAddress; // [rsp+70h] [rbp-90h] BYREF
  PVOID v20; // [rsp+78h] [rbp-88h] BYREF
  PVOID v21; // [rsp+80h] [rbp-80h] BYREF
  PVOID v22; // [rsp+88h] [rbp-78h] BYREF
  PMDL MemoryDescriptorList; // [rsp+90h] [rbp-70h] BYREF
  PMDL Mdl; // [rsp+98h] [rbp-68h] BYREF
  PMDL v25; // [rsp+A0h] [rbp-60h] BYREF
  PMDL v26; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v27[2]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v28[2]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v29[2]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v30[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v31; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v32; // [rsp+100h] [rbp+0h]
  __int128 v33; // [rsp+110h] [rbp+10h]
  __int128 v34; // [rsp+120h] [rbp+20h] BYREF
  __int128 v35; // [rsp+130h] [rbp+30h]
  __int128 v36; // [rsp+140h] [rbp+40h]
  __int128 v37; // [rsp+150h] [rbp+50h] BYREF
  __int128 v38; // [rsp+160h] [rbp+60h]
  __int128 v39; // [rsp+170h] [rbp+70h]
  __int128 v40; // [rsp+180h] [rbp+80h] BYREF
  __int128 v41; // [rsp+190h] [rbp+90h]
  __int128 v42; // [rsp+1A0h] [rbp+A0h]
  struct _KAPC_STATE ApcState; // [rsp+1B0h] [rbp+B0h] BYREF

  v27[0] = 6029402;
  v16 = 0;
  v21 = 0;
  v13 = 0;
  v27[1] = L"\\SystemRoot\\System32\\CodeIntegrity\\driver.stl";
  v25 = 0;
  v28[1] = L"\\SystemRoot\\System32\\CodeIntegrity\\previous.driver.stl";
  v29[1] = L"\\SystemRoot\\System32\\CodeIntegrity\\Update\\driver.stl";
  v30[1] = L"\\SystemRoot\\System32\\CodeIntegrity\\Update\\Previous\\driver.stl";
  memset(&ApcState, 0, sizeof(ApcState));
  P = 0;
  v22 = 0;
  v14 = 0;
  v34 = 0;
  v26 = 0;
  v35 = 0;
  v28[0] = 7209068;
  v36 = 0;
  v29[0] = 6946920;
  v31 = 0;
  v30[0] = 8126586;
  v32 = 0;
  v17 = 0;
  v33 = 0;
  v18 = 0;
  v37 = 0;
  BaseAddress = 0;
  v38 = 0;
  v11 = 0;
  v39 = 0;
  MemoryDescriptorList = 0;
  v40 = 0;
  v20 = 0;
  v41 = 0;
  v12 = 0;
  v42 = 0;
  Mdl = 0;
  KeStackAttachProcess(g_CiSystemProcess, &ApcState);
  v2 = CipParseRevocationListAtPath(
         (unsigned int)v27,
         (unsigned int)&v22,
         (unsigned int)&v14,
         (unsigned int)&P,
         (__int64)&v31,
         (__int64)qword_180049E40,
         (__int64)&v26);
  if ( v2 < 0 )
    goto LABEL_17;
  v2 = CipParseRevocationListAtPath(
         (unsigned int)v28,
         (unsigned int)&v21,
         (unsigned int)&v13,
         (unsigned int)&v16,
         (__int64)&v34,
         (__int64)&qword_180049E48,
         (__int64)&v25);
  if ( v2 < 0 )
    goto LABEL_17;
  v3 = CipParseRevocationListAtPath(
         (unsigned int)v29,
         (unsigned int)&v20,
         (unsigned int)&v12,
         (unsigned int)&v17,
         (__int64)&v37,
         (__int64)&qword_180049E50,
         (__int64)&Mdl);
  v2 = v3;
  if ( v3 < 0 )
  {
    if ( v3 != -1073741766 && v3 != -1073741772 )
      goto LABEL_17;
  }
  else
  {
    v2 = CipParseRevocationListAtPath(
           (unsigned int)v30,
           (unsigned int)&BaseAddress,
           (unsigned int)&v11,
           (unsigned int)&v18,
           (__int64)&v40,
           (__int64)&qword_180049E58,
           (__int64)&MemoryDescriptorList);
    if ( v2 < 0 )
      goto LABEL_17;
    if ( qword_180049E50 > qword_180049E40[0] )
    {
      if ( g_CiBlocklistUpdateTime <= qword_180049E50 )
        v4 = CipSetRevocationList((unsigned int)&v17, (unsigned int)&v37, (_DWORD)v20, v12, 2, a1);
      else
        v4 = CipSetRevocationList((unsigned int)&v18, (unsigned int)&v40, (_DWORD)BaseAddress, v11, 3, a1);
      v2 = v4;
      goto LABEL_17;
    }
  }
  if ( g_CiBlocklistUpdateTime <= qword_180049E40[0] )
    v5 = CipSetRevocationList((unsigned int)&P, (unsigned int)&v31, (_DWORD)v22, v14, 0, a1);
  else
    v5 = CipSetRevocationList((unsigned int)&v16, (unsigned int)&v34, (_DWORD)v21, v13, 1, a1);
  v2 = v5;
  if ( v5 >= 0 )
    CiBlackBoxRevocationListUpdate(&qword_180049E40[g_CiRevocationListInfo]);
LABEL_17:
  if ( (_DWORD)v31 )
    I_MincryptFreeChainInfo(v32);
  if ( (_DWORD)v34 )
    I_MincryptFreeChainInfo(v35);
  if ( (_DWORD)v37 )
    I_MincryptFreeChainInfo(v38);
  if ( (_DWORD)v40 )
    I_MincryptFreeChainInfo(v41);
  if ( P )
    ExFreePoolWithTag(P, 0x63734943u);
  if ( v16 )
    ExFreePoolWithTag(v16, 0x63734943u);
  if ( v17 )
    ExFreePoolWithTag(v17, 0x63734943u);
  if ( v18 )
    ExFreePoolWithTag(v18, 0x63734943u);
  v6 = MemoryDescriptorList;
  if ( MemoryDescriptorList )
  {
    MmUnlockPages(MemoryDescriptorList);
    IoFreeMdl(v6);
  }
  if ( BaseAddress )
    ZwUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, BaseAddress);
  v7 = Mdl;
  if ( Mdl )
  {
    MmUnlockPages(Mdl);
    IoFreeMdl(v7);
  }
  if ( v20 )
    ZwUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, v20);
  v8 = v25;
  if ( v25 )
  {
    MmUnlockPages(v25);
    IoFreeMdl(v8);
  }
  if ( v21 )
    ZwUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, v21);
  v9 = v26;
  if ( v26 )
  {
    MmUnlockPages(v26);
    IoFreeMdl(v9);
  }
  if ( v22 )
    ZwUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, v22);
  KeUnstackDetachProcess(&ApcState);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180073034  mov     [rsp-8+arg_8], rbx
0x180073039  mov     [rsp-8+arg_10], rsi
0x18007303e  push    rbp
0x18007303f  push    rdi
0x180073040  push    r14
0x180073042  lea     rbp, [rsp-0F0h]
0x18007304a  sub     rsp, 1F0h
0x180073051  mov     rax, cs:__security_cookie
0x180073058  xor     rax, rsp
0x18007305b  mov     [rbp+100h+var_20], rax
0x180073062  xor     esi, esi
0x180073064  mov     [rbp+100h+var_150], 5C005Ah
0x18007306c  xorps   xmm0, xmm0
0x18007306f  mov     [rsp+200h+var_1A8], rsi
0x180073074  xorps   xmm1, xmm1
0x180073077  mov     [rbp+100h+var_180], rsi
0x18007307b  lea     rax, aSystemrootSyst_8; "\\SystemRoot\\System32\\CodeIntegrity\\"...
0x180073082  mov     [rsp+200h+var_1B8], esi
0x180073086  mov     [rbp+100h+var_148], rax
0x18007308a  lea     rdx, [rbp+100h+ApcState]; ApcState
0x180073091  lea     rax, aSystemrootSyst_0; "\\SystemRoot\\System32\\CodeIntegrity\\"...
0x180073098  mov     [rbp+100h+var_160], rsi
0x18007309c  mov     [rbp+100h+var_138], rax
0x1800730a0  mov     rdi, rcx
0x1800730a3  mov     rcx, cs:g_CiSystemProcess; PROCESS
0x1800730aa  lea     rax, aSystemrootSyst; "\\SystemRoot\\System32\\CodeIntegrity\\"...
0x1800730b1  mov     [rbp+100h+var_128], rax
0x1800730b5  lea     rax, aSystemrootSyst_2; "\\SystemRoot\\System32\\CodeIntegrity\\"...
0x1800730bc  mov     [rbp+100h+var_118], rax
0x1800730c0  movups  xmmword ptr [rbp+100h+ApcState.ApcListHead.Flink], xmm0
0x1800730c7  mov     [rsp+200h+P], rsi
0x1800730cc  movups  xmmword ptr [rbp+100h+ApcState.ApcListHead.Flink+10h], xmm0
0x1800730d3  mov     [rbp+100h+var_178], rsi
0x1800730d7  movups  xmmword ptr [rbp+100h+ApcState.Process], xmm0
0x1800730de  mov     [rsp+200h+var_1B4], esi
0x1800730e2  movups  [rbp+100h+var_E0], xmm0
0x1800730e6  mov     [rbp+100h+var_158], rsi
0x1800730ea  movups  [rbp+100h+var_D0], xmm0
0x1800730ee  mov     [rbp+100h+var_140], 6E006Ch
0x1800730f6  movups  [rbp+100h+var_C0], xmm0
0x1800730fa  mov     [rbp+100h+var_130], 6A0068h
0x180073102  movups  [rbp+100h+var_110], xmm0
0x180073106  mov     [rbp+100h+var_120], 7C007Ah
0x18007310e  movups  [rbp+100h+var_100], xmm0
0x180073112  mov     [rsp+200h+var_1A0], rsi
0x180073117  movups  [rbp+100h+var_F0], xmm0
0x18007311b  mov     [rsp+200h+var_198], rsi
0x180073120  movups  [rbp+100h+var_B0], xmm0
0x180073124  mov     [rsp+200h+BaseAddress], rsi
0x180073129  movups  [rbp+100h+var_A0], xmm0
0x18007312d  mov     [rsp+200h+var_1C0], esi
0x180073131  movups  [rbp+100h+var_90], xmm0
0x180073135  mov     [rbp+100h+MemoryDescriptorList], rsi
0x180073139  movups  [rbp+100h+var_80], xmm1
0x180073140  mov     [rsp+200h+var_188], rsi
0x180073145  movups  [rbp+100h+var_70], xmm1
0x18007314c  mov     [rsp+200h+var_1BC], esi
0x180073150  movups  [rbp+100h+var_60], xmm1
0x180073157  mov     [rbp+100h+Mdl], rsi
0x18007315b  call    cs:__imp_KeStackAttachProcess
0x180073162  nop     dword ptr [rax+rax+00h]
0x180073167  lea     rax, [rbp+100h+var_158]
0x18007316b  mov     [rsp+200h+var_1D0], rax
0x180073170  lea     r14, qword_180049E40
0x180073177  lea     rax, [rbp+100h+var_110]
0x18007317b  mov     [rsp+200h+var_1D8], r14
0x180073180  lea     r9, [rsp+200h+P]
0x180073185  mov     [rsp+200h+var_1E0], rax
0x18007318a  lea     r8, [rsp+200h+var_1B4]
0x18007318f  lea     rdx, [rbp+100h+var_178]
0x180073193  lea     rcx, [rbp+100h+var_150]
0x180073197  call    CipParseRevocationListAtPath
0x18007319c  mov     ebx, eax
0x18007319e  test    eax, eax
0x1800731a0  js      loc_18007333A
0x1800731a6  lea     rax, [rbp+100h+var_160]
0x1800731aa  mov     [rsp+200h+var_1D0], rax
0x1800731af  lea     r9, [rsp+200h+var_1A8]
0x1800731b4  lea     rax, qword_180049E48
0x1800731bb  mov     [rsp+200h+var_1D8], rax
0x1800731c0  lea     r8, [rsp+200h+var_1B8]
0x1800731c5  lea     rax, [rbp+100h+var_E0]
0x1800731c9  lea     rdx, [rbp+100h+var_180]
0x1800731cd  mov     [rsp+200h+var_1E0], rax
0x1800731d2  lea     rcx, [rbp+100h+var_140]
0x1800731d6  call    CipParseRevocationListAtPath
0x1800731db  mov     ebx, eax
0x1800731dd  test    eax, eax
0x1800731df  js      loc_18007333A
0x1800731e5  lea     rax, [rbp+100h+Mdl]
0x1800731e9  mov     [rsp+200h+var_1D0], rax
0x1800731ee  lea     r9, [rsp+200h+var_1A0]
0x1800731f3  lea     rax, qword_180049E50
0x1800731fa  mov     [rsp+200h+var_1D8], rax
0x1800731ff  lea     r8, [rsp+200h+var_1BC]
0x180073204  lea     rax, [rbp+100h+var_B0]
0x180073208  lea     rdx, [rsp+200h+var_188]
0x18007320d  mov     [rsp+200h+var_1E0], rax
0x180073212  lea     rcx, [rbp+100h+var_130]
0x180073216  call    CipParseRevocationListAtPath
0x18007321b  mov     ebx, eax
0x18007321d  test    eax, eax
0x18007321f  js      loc_1800732CA
0x180073225  lea     rax, [rbp+100h+MemoryDescriptorList]
0x180073229  mov     [rsp+200h+var_1D0], rax
0x18007322e  lea     r9, [rsp+200h+var_198]
0x180073233  lea     rax, qword_180049E58
0x18007323a  mov     [rsp+200h+var_1D8], rax
0x18007323f  lea     r8, [rsp+200h+var_1C0]
0x180073244  lea     rax, [rbp+100h+var_80]
0x18007324b  lea     rdx, [rsp+200h+BaseAddress]
0x180073250  mov     [rsp+200h+var_1E0], rax
0x180073255  lea     rcx, [rbp+100h+var_120]
0x180073259  call    CipParseRevocationListAtPath
0x18007325e  mov     ebx, eax
0x180073260  test    eax, eax
0x180073262  js      loc_18007333A
0x180073268  mov     rax, cs:qword_180049E50
0x18007326f  cmp     rax, cs:qword_180049E40
0x180073276  jle     short loc_1800732D8
0x180073278  cmp     cs:g_CiBlocklistUpdateTime, rax
0x18007327f  mov     [rsp+200h+var_1D8], rdi
0x180073284  jle     short loc_1800732A6
0x180073286  mov     r9d, [rsp+200h+var_1C0]
0x18007328b  lea     rdx, [rbp+100h+var_80]
0x180073292  mov     r8, [rsp+200h+BaseAddress]
0x180073297  lea     rcx, [rsp+200h+var_198]
0x18007329c  mov     dword ptr [rsp+200h+var_1E0], 3
0x1800732a4  jmp     short loc_1800732C1
0x1800732a6  mov     r9d, [rsp+200h+var_1BC]
0x1800732ab  lea     rdx, [rbp+100h+var_B0]
0x1800732af  mov     r8, [rsp+200h+var_188]
0x1800732b4  lea     rcx, [rsp+200h+var_1A0]
0x1800732b9  mov     dword ptr [rsp+200h+var_1E0], 2
0x1800732c1  call    CipSetRevocationList
0x1800732c6  mov     ebx, eax
0x1800732c8  jmp     short loc_18007333A
0x1800732ca  cmp     eax, 0C000003Ah
0x1800732cf  jz      short loc_1800732D8
0x1800732d1  cmp     eax, 0C0000034h
0x1800732d6  jnz     short loc_18007333A
0x1800732d8  mov     rax, cs:qword_180049E40
0x1800732df  cmp     cs:g_CiBlocklistUpdateTime, rax
0x1800732e6  mov     [rsp+200h+var_1D8], rdi
0x1800732eb  jle     short loc_180073309
0x1800732ed  mov     r9d, [rsp+200h+var_1B8]
0x1800732f2  lea     rdx, [rbp+100h+var_E0]
0x1800732f6  mov     r8, [rbp+100h+var_180]
0x1800732fa  lea     rcx, [rsp+200h+var_1A8]
0x1800732ff  mov     dword ptr [rsp+200h+var_1E0], 1
0x180073307  jmp     short loc_18007331F
0x180073309  mov     r9d, [rsp+200h+var_1B4]
0x18007330e  lea     rdx, [rbp+100h+var_110]
0x180073312  mov     r8, [rbp+100h+var_178]
0x180073316  lea     rcx, [rsp+200h+P]
0x18007331b  mov     dword ptr [rsp+200h+var_1E0], esi
0x18007331f  call    CipSetRevocationList
0x180073324  mov     ebx, eax
0x180073326  test    eax, eax
0x180073328  js      short loc_18007333A
0x18007332a  movsxd  rax, cs:g_CiRevocationListInfo
0x180073331  lea     rcx, [r14+rax*8]
0x180073335  call    CiBlackBoxRevocationListUpdate
0x18007333a  cmp     dword ptr [rbp+100h+var_110], esi
0x18007333d  jz      short loc_180073348
0x18007333f  mov     rcx, qword ptr [rbp+100h+var_100]
0x180073343  call    I_MincryptFreeChainInfo
0x180073348  cmp     dword ptr [rbp+100h+var_E0], esi
0x18007334b  jz      short loc_180073356
0x18007334d  mov     rcx, qword ptr [rbp+100h+var_D0]
0x180073351  call    I_MincryptFreeChainInfo
0x180073356  cmp     dword ptr [rbp+100h+var_B0], esi
0x180073359  jz      short loc_180073364
0x18007335b  mov     rcx, qword ptr [rbp+100h+var_A0]
0x18007335f  call    I_MincryptFreeChainInfo
0x180073364  cmp     dword ptr [rbp+100h+var_80], esi
0x18007336a  jz      short loc_180073378
0x18007336c  mov     rcx, qword ptr [rbp+100h+var_70]
0x180073373  call    I_MincryptFreeChainInfo
0x180073378  mov     rcx, [rsp+200h+P]; P
0x18007337d  mov     edi, 63734943h
0x180073382  test    rcx, rcx
0x180073385  jz      short loc_180073395
0x180073387  mov     edx, edi; Tag
0x180073389  call    cs:__imp_ExFreePoolWithTag
0x180073390  nop     dword ptr [rax+rax+00h]
0x180073395  mov     rcx, [rsp+200h+var_1A8]; P
0x18007339a  test    rcx, rcx
0x18007339d  jz      short loc_1800733AD
0x18007339f  mov     edx, edi; Tag
0x1800733a1  call    cs:__imp_ExFreePoolWithTag
0x1800733a8  nop     dword ptr [rax+rax+00h]
0x1800733ad  mov     rcx, [rsp+200h+var_1A0]; P
0x1800733b2  test    rcx, rcx
0x1800733b5  jz      short loc_1800733C5
0x1800733b7  mov     edx, edi; Tag
0x1800733b9  call    cs:__imp_ExFreePoolWithTag
0x1800733c0  nop     dword ptr [rax+rax+00h]
0x1800733c5  mov     rcx, [rsp+200h+var_198]; P
0x1800733ca  test    rcx, rcx
0x1800733cd  jz      short loc_1800733DD
0x1800733cf  mov     edx, edi; Tag
0x1800733d1  call    cs:__imp_ExFreePoolWithTag
0x1800733d8  nop     dword ptr [rax+rax+00h]
0x1800733dd  mov     rdi, [rbp+100h+MemoryDescriptorList]
0x1800733e1  test    rdi, rdi
0x1800733e4  jz      short loc_180073404
0x1800733e6  mov     rcx, rdi; MemoryDescriptorList
0x1800733e9  call    cs:__imp_MmUnlockPages
0x1800733f0  nop     dword ptr [rax+rax+00h]
0x1800733f5  mov     rcx, rdi; Mdl
0x1800733f8  call    cs:__imp_IoFreeMdl
0x1800733ff  nop     dword ptr [rax+rax+00h]
0x180073404  mov     rdx, [rsp+200h+BaseAddress]; BaseAddress
0x180073409  or      r14, 0FFFFFFFFFFFFFFFFh
0x18007340d  test    rdx, rdx
0x180073410  jz      short loc_180073421
0x180073412  mov     rcx, r14; ProcessHandle
0x180073415  call    cs:__imp_ZwUnmapViewOfSection
0x18007341c  nop     dword ptr [rax+rax+00h]
0x180073421  mov     rdi, [rbp+100h+Mdl]
0x180073425  test    rdi, rdi
0x180073428  jz      short loc_180073448
0x18007342a  mov     rcx, rdi; MemoryDescriptorList
0x18007342d  call    cs:__imp_MmUnlockPages
0x180073434  nop     dword ptr [rax+rax+00h]
0x180073439  mov     rcx, rdi; Mdl
0x18007343c  call    cs:__imp_IoFreeMdl
0x180073443  nop     dword ptr [rax+rax+00h]
0x180073448  mov     rdx, [rsp+200h+var_188]; BaseAddress
0x18007344d  test    rdx, rdx
0x180073450  jz      short loc_180073461
0x180073452  mov     rcx, r14; ProcessHandle
0x180073455  call    cs:__imp_ZwUnmapViewOfSection
0x18007345c  nop     dword ptr [rax+rax+00h]
0x180073461  mov     rdi, [rbp+100h+var_160]
0x180073465  test    rdi, rdi
0x180073468  jz      short loc_180073488
0x18007346a  mov     rcx, rdi; MemoryDescriptorList
0x18007346d  call    cs:__imp_MmUnlockPages
0x180073474  nop     dword ptr [rax+rax+00h]
0x180073479  mov     rcx, rdi; Mdl
0x18007347c  call    cs:__imp_IoFreeMdl
0x180073483  nop     dword ptr [rax+rax+00h]
0x180073488  mov     rdx, [rbp+100h+var_180]; BaseAddress
0x18007348c  test    rdx, rdx
0x18007348f  jz      short loc_1800734A0
0x180073491  mov     rcx, r14; ProcessHandle
0x180073494  call    cs:__imp_ZwUnmapViewOfSection
0x18007349b  nop     dword ptr [rax+rax+00h]
0x1800734a0  mov     rdi, [rbp+100h+var_158]
0x1800734a4  test    rdi, rdi
0x1800734a7  jz      short loc_1800734C7
0x1800734a9  mov     rcx, rdi; MemoryDescriptorList
0x1800734ac  call    cs:__imp_MmUnlockPages
0x1800734b3  nop     dword ptr [rax+rax+00h]
0x1800734b8  mov     rcx, rdi; Mdl
0x1800734bb  call    cs:__imp_IoFreeMdl
0x1800734c2  nop     dword ptr [rax+rax+00h]
0x1800734c7  mov     rdx, [rbp+100h+var_178]; BaseAddress
0x1800734cb  test    rdx, rdx
0x1800734ce  jz      short loc_1800734DF
0x1800734d0  mov     rcx, r14; ProcessHandle
0x1800734d3  call    cs:__imp_ZwUnmapViewOfSection
0x1800734da  nop     dword ptr [rax+rax+00h]
0x1800734df  lea     rcx, [rbp+100h+ApcState]; ApcState
0x1800734e6  call    cs:__imp_KeUnstackDetachProcess
0x1800734ed  nop     dword ptr [rax+rax+00h]
0x1800734f2  mov     eax, ebx
0x1800734f4  mov     rcx, [rbp+100h+var_20]
0x1800734fb  xor     rcx, rsp; StackCookie
0x1800734fe  call    __security_check_cookie
0x180073503  lea     r11, [rsp+200h+var_10]
0x18007350b  mov     rbx, [r11+28h]
0x18007350f  mov     rsi, [r11+30h]
0x180073513  mov     rsp, r11
0x180073516  pop     r14
0x180073518  pop     rdi
0x180073519  pop     rbp
0x18007351a  retn
```
