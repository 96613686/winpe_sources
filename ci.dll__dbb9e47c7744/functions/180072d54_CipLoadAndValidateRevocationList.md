# CipLoadAndValidateRevocationList

- ea: `0x180072d54`
- end: `0x18007323c`
- name: `CipLoadAndValidateRevocationList`
- size: `1256`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180058120`
- `0x180096f80`
- `0x1800e4ca8`

## callees

- `0x18001e08c`
- `0x18002bf20`
- `0x1800607c8`
- `0x180072d54`
- `0x180073244`
- `0x18009860c`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x180072e7b`
- `ntoskrnl!KeStackAttachProcess` at `0x180072e7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800730a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800730c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800730d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800730f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800730a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800730c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800730d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800730f1`
- `ntoskrnl!KeUnstackDetachProcess` at `0x180073206`
- `ntoskrnl!KeUnstackDetachProcess` at `0x180073206`
- `ntoskrnl!MmUnlockPages` at `0x180073109`
- `ntoskrnl!MmUnlockPages` at `0x18007314d`
- `ntoskrnl!MmUnlockPages` at `0x18007318d`
- `ntoskrnl!MmUnlockPages` at `0x1800731cc`
- `ntoskrnl!MmUnlockPages` at `0x180073109`
- `ntoskrnl!MmUnlockPages` at `0x18007314d`
- `ntoskrnl!MmUnlockPages` at `0x18007318d`
- `ntoskrnl!MmUnlockPages` at `0x1800731cc`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x180073135`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x180073175`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x1800731b4`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x1800731f3`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x180073135`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x180073175`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x1800731b4`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x1800731f3`
- `ntoskrnl!IoFreeMdl` at `0x180073118`
- `ntoskrnl!IoFreeMdl` at `0x18007315c`
- `ntoskrnl!IoFreeMdl` at `0x18007319c`
- `ntoskrnl!IoFreeMdl` at `0x1800731db`
- `ntoskrnl!IoFreeMdl` at `0x180073118`
- `ntoskrnl!IoFreeMdl` at `0x18007315c`
- `ntoskrnl!IoFreeMdl` at `0x18007319c`
- `ntoskrnl!IoFreeMdl` at `0x1800731db`

## string_xrefs

- `0x180072d9b`: `\SystemRoot\System32\CodeIntegrity\driver.stl`
- `0x180072db1`: `\SystemRoot\System32\CodeIntegrity\previous.driver.stl`
- `0x180072dca`: `\SystemRoot\System32\CodeIntegrity\Update\driver.stl`
- `0x180072dd5`: `\SystemRoot\System32\CodeIntegrity\Update\Previous\driver.stl`

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
0x180072d54  mov     [rsp-8+arg_8], rbx
0x180072d59  mov     [rsp-8+arg_10], rsi
0x180072d5e  push    rbp
0x180072d5f  push    rdi
0x180072d60  push    r14
0x180072d62  lea     rbp, [rsp-0F0h]
0x180072d6a  sub     rsp, 1F0h
0x180072d71  mov     rax, cs:__security_cookie
0x180072d78  xor     rax, rsp
0x180072d7b  mov     [rbp+100h+var_20], rax
0x180072d82  xor     esi, esi
0x180072d84  mov     [rbp+100h+var_150], 5C005Ah
0x180072d8c  xorps   xmm0, xmm0
0x180072d8f  mov     [rsp+200h+var_1A8], rsi
0x180072d94  xorps   xmm1, xmm1
0x180072d97  mov     [rbp+100h+var_180], rsi
0x180072d9b  lea     rax, aSystemrootSyst_8; "\\SystemRoot\\System32\\CodeIntegrity\\"...
0x180072da2  mov     [rsp+200h+var_1B8], esi
0x180072da6  mov     [rbp+100h+var_148], rax
0x180072daa  lea     rdx, [rbp+100h+ApcState]; ApcState
0x180072db1  lea     rax, aSystemrootSyst_0; "\\SystemRoot\\System32\\CodeIntegrity\\"...
0x180072db8  mov     [rbp+100h+var_160], rsi
0x180072dbc  mov     [rbp+100h+var_138], rax
0x180072dc0  mov     rdi, rcx
0x180072dc3  mov     rcx, cs:g_CiSystemProcess; PROCESS
0x180072dca  lea     rax, aSystemrootSyst; "\\SystemRoot\\System32\\CodeIntegrity\\"...
0x180072dd1  mov     [rbp+100h+var_128], rax
0x180072dd5  lea     rax, aSystemrootSyst_2; "\\SystemRoot\\System32\\CodeIntegrity\\"...
0x180072ddc  mov     [rbp+100h+var_118], rax
0x180072de0  movups  xmmword ptr [rbp+100h+ApcState.ApcListHead.Flink], xmm0
0x180072de7  mov     [rsp+200h+P], rsi
0x180072dec  movups  xmmword ptr [rbp+100h+ApcState.ApcListHead.Flink+10h], xmm0
0x180072df3  mov     [rbp+100h+var_178], rsi
0x180072df7  movups  xmmword ptr [rbp+100h+ApcState.Process], xmm0
0x180072dfe  mov     [rsp+200h+var_1B4], esi
0x180072e02  movups  [rbp+100h+var_E0], xmm0
0x180072e06  mov     [rbp+100h+var_158], rsi
0x180072e0a  movups  [rbp+100h+var_D0], xmm0
0x180072e0e  mov     [rbp+100h+var_140], 6E006Ch
0x180072e16  movups  [rbp+100h+var_C0], xmm0
0x180072e1a  mov     [rbp+100h+var_130], 6A0068h
0x180072e22  movups  [rbp+100h+var_110], xmm0
0x180072e26  mov     [rbp+100h+var_120], 7C007Ah
0x180072e2e  movups  [rbp+100h+var_100], xmm0
0x180072e32  mov     [rsp+200h+var_1A0], rsi
0x180072e37  movups  [rbp+100h+var_F0], xmm0
0x180072e3b  mov     [rsp+200h+var_198], rsi
0x180072e40  movups  [rbp+100h+var_B0], xmm0
0x180072e44  mov     [rsp+200h+BaseAddress], rsi
0x180072e49  movups  [rbp+100h+var_A0], xmm0
0x180072e4d  mov     [rsp+200h+var_1C0], esi
0x180072e51  movups  [rbp+100h+var_90], xmm0
0x180072e55  mov     [rbp+100h+MemoryDescriptorList], rsi
0x180072e59  movups  [rbp+100h+var_80], xmm1
0x180072e60  mov     [rsp+200h+var_188], rsi
0x180072e65  movups  [rbp+100h+var_70], xmm1
0x180072e6c  mov     [rsp+200h+var_1BC], esi
0x180072e70  movups  [rbp+100h+var_60], xmm1
0x180072e77  mov     [rbp+100h+Mdl], rsi
0x180072e7b  call    cs:__imp_KeStackAttachProcess
0x180072e82  nop     dword ptr [rax+rax+00h]
0x180072e87  lea     rax, [rbp+100h+var_158]
0x180072e8b  mov     [rsp+200h+var_1D0], rax
0x180072e90  lea     r14, qword_180049E40
0x180072e97  lea     rax, [rbp+100h+var_110]
0x180072e9b  mov     [rsp+200h+var_1D8], r14
0x180072ea0  lea     r9, [rsp+200h+P]
0x180072ea5  mov     [rsp+200h+var_1E0], rax
0x180072eaa  lea     r8, [rsp+200h+var_1B4]
0x180072eaf  lea     rdx, [rbp+100h+var_178]
0x180072eb3  lea     rcx, [rbp+100h+var_150]
0x180072eb7  call    CipParseRevocationListAtPath
0x180072ebc  mov     ebx, eax
0x180072ebe  test    eax, eax
0x180072ec0  js      loc_18007305A
0x180072ec6  lea     rax, [rbp+100h+var_160]
0x180072eca  mov     [rsp+200h+var_1D0], rax
0x180072ecf  lea     r9, [rsp+200h+var_1A8]
0x180072ed4  lea     rax, qword_180049E48
0x180072edb  mov     [rsp+200h+var_1D8], rax
0x180072ee0  lea     r8, [rsp+200h+var_1B8]
0x180072ee5  lea     rax, [rbp+100h+var_E0]
0x180072ee9  lea     rdx, [rbp+100h+var_180]
0x180072eed  mov     [rsp+200h+var_1E0], rax
0x180072ef2  lea     rcx, [rbp+100h+var_140]
0x180072ef6  call    CipParseRevocationListAtPath
0x180072efb  mov     ebx, eax
0x180072efd  test    eax, eax
0x180072eff  js      loc_18007305A
0x180072f05  lea     rax, [rbp+100h+Mdl]
0x180072f09  mov     [rsp+200h+var_1D0], rax
0x180072f0e  lea     r9, [rsp+200h+var_1A0]
0x180072f13  lea     rax, qword_180049E50
0x180072f1a  mov     [rsp+200h+var_1D8], rax
0x180072f1f  lea     r8, [rsp+200h+var_1BC]
0x180072f24  lea     rax, [rbp+100h+var_B0]
0x180072f28  lea     rdx, [rsp+200h+var_188]
0x180072f2d  mov     [rsp+200h+var_1E0], rax
0x180072f32  lea     rcx, [rbp+100h+var_130]
0x180072f36  call    CipParseRevocationListAtPath
0x180072f3b  mov     ebx, eax
0x180072f3d  test    eax, eax
0x180072f3f  js      loc_180072FEA
0x180072f45  lea     rax, [rbp+100h+MemoryDescriptorList]
0x180072f49  mov     [rsp+200h+var_1D0], rax
0x180072f4e  lea     r9, [rsp+200h+var_198]
0x180072f53  lea     rax, qword_180049E58
0x180072f5a  mov     [rsp+200h+var_1D8], rax
0x180072f5f  lea     r8, [rsp+200h+var_1C0]
0x180072f64  lea     rax, [rbp+100h+var_80]
0x180072f6b  lea     rdx, [rsp+200h+BaseAddress]
0x180072f70  mov     [rsp+200h+var_1E0], rax
0x180072f75  lea     rcx, [rbp+100h+var_120]
0x180072f79  call    CipParseRevocationListAtPath
0x180072f7e  mov     ebx, eax
0x180072f80  test    eax, eax
0x180072f82  js      loc_18007305A
0x180072f88  mov     rax, cs:qword_180049E50
0x180072f8f  cmp     rax, cs:qword_180049E40
0x180072f96  jle     short loc_180072FF8
0x180072f98  cmp     cs:g_CiBlocklistUpdateTime, rax
0x180072f9f  mov     [rsp+200h+var_1D8], rdi
0x180072fa4  jle     short loc_180072FC6
0x180072fa6  mov     r9d, [rsp+200h+var_1C0]
0x180072fab  lea     rdx, [rbp+100h+var_80]
0x180072fb2  mov     r8, [rsp+200h+BaseAddress]
0x180072fb7  lea     rcx, [rsp+200h+var_198]
0x180072fbc  mov     dword ptr [rsp+200h+var_1E0], 3
0x180072fc4  jmp     short loc_180072FE1
0x180072fc6  mov     r9d, [rsp+200h+var_1BC]
0x180072fcb  lea     rdx, [rbp+100h+var_B0]
0x180072fcf  mov     r8, [rsp+200h+var_188]
0x180072fd4  lea     rcx, [rsp+200h+var_1A0]
0x180072fd9  mov     dword ptr [rsp+200h+var_1E0], 2
0x180072fe1  call    CipSetRevocationList
0x180072fe6  mov     ebx, eax
0x180072fe8  jmp     short loc_18007305A
0x180072fea  cmp     eax, 0C000003Ah
0x180072fef  jz      short loc_180072FF8
0x180072ff1  cmp     eax, 0C0000034h
0x180072ff6  jnz     short loc_18007305A
0x180072ff8  mov     rax, cs:qword_180049E40
0x180072fff  cmp     cs:g_CiBlocklistUpdateTime, rax
0x180073006  mov     [rsp+200h+var_1D8], rdi
0x18007300b  jle     short loc_180073029
0x18007300d  mov     r9d, [rsp+200h+var_1B8]
0x180073012  lea     rdx, [rbp+100h+var_E0]
0x180073016  mov     r8, [rbp+100h+var_180]
0x18007301a  lea     rcx, [rsp+200h+var_1A8]
0x18007301f  mov     dword ptr [rsp+200h+var_1E0], 1
0x180073027  jmp     short loc_18007303F
0x180073029  mov     r9d, [rsp+200h+var_1B4]
0x18007302e  lea     rdx, [rbp+100h+var_110]
0x180073032  mov     r8, [rbp+100h+var_178]
0x180073036  lea     rcx, [rsp+200h+P]
0x18007303b  mov     dword ptr [rsp+200h+var_1E0], esi
0x18007303f  call    CipSetRevocationList
0x180073044  mov     ebx, eax
0x180073046  test    eax, eax
0x180073048  js      short loc_18007305A
0x18007304a  movsxd  rax, cs:g_CiRevocationListInfo
0x180073051  lea     rcx, [r14+rax*8]
0x180073055  call    CiBlackBoxRevocationListUpdate
0x18007305a  cmp     dword ptr [rbp+100h+var_110], esi
0x18007305d  jz      short loc_180073068
0x18007305f  mov     rcx, qword ptr [rbp+100h+var_100]
0x180073063  call    I_MincryptFreeChainInfo
0x180073068  cmp     dword ptr [rbp+100h+var_E0], esi
0x18007306b  jz      short loc_180073076
0x18007306d  mov     rcx, qword ptr [rbp+100h+var_D0]
0x180073071  call    I_MincryptFreeChainInfo
0x180073076  cmp     dword ptr [rbp+100h+var_B0], esi
0x180073079  jz      short loc_180073084
0x18007307b  mov     rcx, qword ptr [rbp+100h+var_A0]
0x18007307f  call    I_MincryptFreeChainInfo
0x180073084  cmp     dword ptr [rbp+100h+var_80], esi
0x18007308a  jz      short loc_180073098
0x18007308c  mov     rcx, qword ptr [rbp+100h+var_70]
0x180073093  call    I_MincryptFreeChainInfo
0x180073098  mov     rcx, [rsp+200h+P]; P
0x18007309d  mov     edi, 63734943h
0x1800730a2  test    rcx, rcx
0x1800730a5  jz      short loc_1800730B5
0x1800730a7  mov     edx, edi; Tag
0x1800730a9  call    cs:__imp_ExFreePoolWithTag
0x1800730b0  nop     dword ptr [rax+rax+00h]
0x1800730b5  mov     rcx, [rsp+200h+var_1A8]; P
0x1800730ba  test    rcx, rcx
0x1800730bd  jz      short loc_1800730CD
0x1800730bf  mov     edx, edi; Tag
0x1800730c1  call    cs:__imp_ExFreePoolWithTag
0x1800730c8  nop     dword ptr [rax+rax+00h]
0x1800730cd  mov     rcx, [rsp+200h+var_1A0]; P
0x1800730d2  test    rcx, rcx
0x1800730d5  jz      short loc_1800730E5
0x1800730d7  mov     edx, edi; Tag
0x1800730d9  call    cs:__imp_ExFreePoolWithTag
0x1800730e0  nop     dword ptr [rax+rax+00h]
0x1800730e5  mov     rcx, [rsp+200h+var_198]; P
0x1800730ea  test    rcx, rcx
0x1800730ed  jz      short loc_1800730FD
0x1800730ef  mov     edx, edi; Tag
0x1800730f1  call    cs:__imp_ExFreePoolWithTag
0x1800730f8  nop     dword ptr [rax+rax+00h]
0x1800730fd  mov     rdi, [rbp+100h+MemoryDescriptorList]
0x180073101  test    rdi, rdi
0x180073104  jz      short loc_180073124
0x180073106  mov     rcx, rdi; MemoryDescriptorList
0x180073109  call    cs:__imp_MmUnlockPages
0x180073110  nop     dword ptr [rax+rax+00h]
0x180073115  mov     rcx, rdi; Mdl
0x180073118  call    cs:__imp_IoFreeMdl
0x18007311f  nop     dword ptr [rax+rax+00h]
0x180073124  mov     rdx, [rsp+200h+BaseAddress]; BaseAddress
0x180073129  or      r14, 0FFFFFFFFFFFFFFFFh
0x18007312d  test    rdx, rdx
0x180073130  jz      short loc_180073141
0x180073132  mov     rcx, r14; ProcessHandle
0x180073135  call    cs:__imp_ZwUnmapViewOfSection
0x18007313c  nop     dword ptr [rax+rax+00h]
0x180073141  mov     rdi, [rbp+100h+Mdl]
0x180073145  test    rdi, rdi
0x180073148  jz      short loc_180073168
0x18007314a  mov     rcx, rdi; MemoryDescriptorList
0x18007314d  call    cs:__imp_MmUnlockPages
0x180073154  nop     dword ptr [rax+rax+00h]
0x180073159  mov     rcx, rdi; Mdl
0x18007315c  call    cs:__imp_IoFreeMdl
0x180073163  nop     dword ptr [rax+rax+00h]
0x180073168  mov     rdx, [rsp+200h+var_188]; BaseAddress
0x18007316d  test    rdx, rdx
0x180073170  jz      short loc_180073181
0x180073172  mov     rcx, r14; ProcessHandle
0x180073175  call    cs:__imp_ZwUnmapViewOfSection
0x18007317c  nop     dword ptr [rax+rax+00h]
0x180073181  mov     rdi, [rbp+100h+var_160]
0x180073185  test    rdi, rdi
0x180073188  jz      short loc_1800731A8
0x18007318a  mov     rcx, rdi; MemoryDescriptorList
0x18007318d  call    cs:__imp_MmUnlockPages
0x180073194  nop     dword ptr [rax+rax+00h]
0x180073199  mov     rcx, rdi; Mdl
0x18007319c  call    cs:__imp_IoFreeMdl
0x1800731a3  nop     dword ptr [rax+rax+00h]
0x1800731a8  mov     rdx, [rbp+100h+var_180]; BaseAddress
0x1800731ac  test    rdx, rdx
0x1800731af  jz      short loc_1800731C0
0x1800731b1  mov     rcx, r14; ProcessHandle
0x1800731b4  call    cs:__imp_ZwUnmapViewOfSection
0x1800731bb  nop     dword ptr [rax+rax+00h]
0x1800731c0  mov     rdi, [rbp+100h+var_158]
0x1800731c4  test    rdi, rdi
0x1800731c7  jz      short loc_1800731E7
0x1800731c9  mov     rcx, rdi; MemoryDescriptorList
0x1800731cc  call    cs:__imp_MmUnlockPages
0x1800731d3  nop     dword ptr [rax+rax+00h]
0x1800731d8  mov     rcx, rdi; Mdl
0x1800731db  call    cs:__imp_IoFreeMdl
0x1800731e2  nop     dword ptr [rax+rax+00h]
0x1800731e7  mov     rdx, [rbp+100h+var_178]; BaseAddress
0x1800731eb  test    rdx, rdx
0x1800731ee  jz      short loc_1800731FF
0x1800731f0  mov     rcx, r14; ProcessHandle
0x1800731f3  call    cs:__imp_ZwUnmapViewOfSection
0x1800731fa  nop     dword ptr [rax+rax+00h]
0x1800731ff  lea     rcx, [rbp+100h+ApcState]; ApcState
0x180073206  call    cs:__imp_KeUnstackDetachProcess
0x18007320d  nop     dword ptr [rax+rax+00h]
0x180073212  mov     eax, ebx
0x180073214  mov     rcx, [rbp+100h+var_20]
0x18007321b  xor     rcx, rsp; StackCookie
0x18007321e  call    __security_check_cookie
0x180073223  lea     r11, [rsp+200h+var_10]
0x18007322b  mov     rbx, [r11+28h]
0x18007322f  mov     rsi, [r11+30h]
0x180073233  mov     rsp, r11
0x180073236  pop     r14
0x180073238  pop     rdi
0x180073239  pop     rbp
0x18007323a  retn
```
