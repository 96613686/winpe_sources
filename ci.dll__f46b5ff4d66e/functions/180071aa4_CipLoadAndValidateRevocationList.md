# CipLoadAndValidateRevocationList

- ea: `0x180071aa4`
- end: `0x180071f8c`
- name: `CipLoadAndValidateRevocationList`
- size: `1256`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180057408`
- `0x180095950`
- `0x1800e4cb8`

## callees

- `0x18001e148`
- `0x18002bef0`
- `0x180060014`
- `0x180071aa4`
- `0x180071f94`
- `0x180096fdc`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x180071bcb`
- `ntoskrnl!KeStackAttachProcess` at `0x180071bcb`
- `ntoskrnl!ExFreePoolWithTag` at `0x180071df9`
- `ntoskrnl!ExFreePoolWithTag` at `0x180071e11`
- `ntoskrnl!ExFreePoolWithTag` at `0x180071e29`
- `ntoskrnl!ExFreePoolWithTag` at `0x180071e41`
- `ntoskrnl!ExFreePoolWithTag` at `0x180071df9`
- `ntoskrnl!ExFreePoolWithTag` at `0x180071e11`
- `ntoskrnl!ExFreePoolWithTag` at `0x180071e29`
- `ntoskrnl!ExFreePoolWithTag` at `0x180071e41`
- `ntoskrnl!KeUnstackDetachProcess` at `0x180071f56`
- `ntoskrnl!KeUnstackDetachProcess` at `0x180071f56`
- `ntoskrnl!MmUnlockPages` at `0x180071e59`
- `ntoskrnl!MmUnlockPages` at `0x180071e9d`
- `ntoskrnl!MmUnlockPages` at `0x180071edd`
- `ntoskrnl!MmUnlockPages` at `0x180071f1c`
- `ntoskrnl!MmUnlockPages` at `0x180071e59`
- `ntoskrnl!MmUnlockPages` at `0x180071e9d`
- `ntoskrnl!MmUnlockPages` at `0x180071edd`
- `ntoskrnl!MmUnlockPages` at `0x180071f1c`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x180071e85`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x180071ec5`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x180071f04`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x180071f43`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x180071e85`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x180071ec5`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x180071f04`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x180071f43`
- `ntoskrnl!IoFreeMdl` at `0x180071e68`
- `ntoskrnl!IoFreeMdl` at `0x180071eac`
- `ntoskrnl!IoFreeMdl` at `0x180071eec`
- `ntoskrnl!IoFreeMdl` at `0x180071f2b`
- `ntoskrnl!IoFreeMdl` at `0x180071e68`
- `ntoskrnl!IoFreeMdl` at `0x180071eac`
- `ntoskrnl!IoFreeMdl` at `0x180071eec`
- `ntoskrnl!IoFreeMdl` at `0x180071f2b`

## string_xrefs

- `0x180071aeb`: `\SystemRoot\System32\CodeIntegrity\driver.stl`
- `0x180071b1a`: `\SystemRoot\System32\CodeIntegrity\Update\driver.stl`
- `0x180071b25`: `\SystemRoot\System32\CodeIntegrity\Update\Previous\driver.stl`
- `0x180071b01`: `\SystemRoot\System32\CodeIntegrity\previous.driver.stl`

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
         (__int64)qword_180048E50,
         (__int64)&v26);
  if ( v2 < 0 )
    goto LABEL_17;
  v2 = CipParseRevocationListAtPath(
         (unsigned int)v28,
         (unsigned int)&v21,
         (unsigned int)&v13,
         (unsigned int)&v16,
         (__int64)&v34,
         (__int64)&qword_180048E58,
         (__int64)&v25);
  if ( v2 < 0 )
    goto LABEL_17;
  v3 = CipParseRevocationListAtPath(
         (unsigned int)v29,
         (unsigned int)&v20,
         (unsigned int)&v12,
         (unsigned int)&v17,
         (__int64)&v37,
         (__int64)&qword_180048E60,
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
           (__int64)&qword_180048E68,
           (__int64)&MemoryDescriptorList);
    if ( v2 < 0 )
      goto LABEL_17;
    if ( qword_180048E60 > qword_180048E50[0] )
    {
      if ( g_CiBlocklistUpdateTime <= qword_180048E60 )
        v4 = CipSetRevocationList((unsigned int)&v17, (unsigned int)&v37, (_DWORD)v20, v12, 2, a1);
      else
        v4 = CipSetRevocationList((unsigned int)&v18, (unsigned int)&v40, (_DWORD)BaseAddress, v11, 3, a1);
      v2 = v4;
      goto LABEL_17;
    }
  }
  if ( g_CiBlocklistUpdateTime <= qword_180048E50[0] )
    v5 = CipSetRevocationList((unsigned int)&P, (unsigned int)&v31, (_DWORD)v22, v14, 0, a1);
  else
    v5 = CipSetRevocationList((unsigned int)&v16, (unsigned int)&v34, (_DWORD)v21, v13, 1, a1);
  v2 = v5;
  if ( v5 >= 0 )
    CiBlackBoxRevocationListUpdate(&qword_180048E50[g_CiRevocationListInfo]);
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
0x180071aa4  mov     [rsp-8+arg_8], rbx
0x180071aa9  mov     [rsp-8+arg_10], rsi
0x180071aae  push    rbp
0x180071aaf  push    rdi
0x180071ab0  push    r14
0x180071ab2  lea     rbp, [rsp-0F0h]
0x180071aba  sub     rsp, 1F0h
0x180071ac1  mov     rax, cs:__security_cookie
0x180071ac8  xor     rax, rsp
0x180071acb  mov     [rbp+100h+var_20], rax
0x180071ad2  xor     esi, esi
0x180071ad4  mov     [rbp+100h+var_150], 5C005Ah
0x180071adc  xorps   xmm0, xmm0
0x180071adf  mov     [rsp+200h+var_1A8], rsi
0x180071ae4  xorps   xmm1, xmm1
0x180071ae7  mov     [rbp+100h+var_180], rsi
0x180071aeb  lea     rax, aSystemrootSyst_8; "\\SystemRoot\\System32\\CodeIntegrity\\"...
0x180071af2  mov     [rsp+200h+var_1B8], esi
0x180071af6  mov     [rbp+100h+var_148], rax
0x180071afa  lea     rdx, [rbp+100h+ApcState]; ApcState
0x180071b01  lea     rax, aSystemrootSyst_0; "\\SystemRoot\\System32\\CodeIntegrity\\"...
0x180071b08  mov     [rbp+100h+var_160], rsi
0x180071b0c  mov     [rbp+100h+var_138], rax
0x180071b10  mov     rdi, rcx
0x180071b13  mov     rcx, cs:g_CiSystemProcess; PROCESS
0x180071b1a  lea     rax, aSystemrootSyst; "\\SystemRoot\\System32\\CodeIntegrity\\"...
0x180071b21  mov     [rbp+100h+var_128], rax
0x180071b25  lea     rax, aSystemrootSyst_2; "\\SystemRoot\\System32\\CodeIntegrity\\"...
0x180071b2c  mov     [rbp+100h+var_118], rax
0x180071b30  movups  xmmword ptr [rbp+100h+ApcState.ApcListHead.Flink], xmm0
0x180071b37  mov     [rsp+200h+P], rsi
0x180071b3c  movups  xmmword ptr [rbp+100h+ApcState.ApcListHead.Flink+10h], xmm0
0x180071b43  mov     [rbp+100h+var_178], rsi
0x180071b47  movups  xmmword ptr [rbp+100h+ApcState.Process], xmm0
0x180071b4e  mov     [rsp+200h+var_1B4], esi
0x180071b52  movups  [rbp+100h+var_E0], xmm0
0x180071b56  mov     [rbp+100h+var_158], rsi
0x180071b5a  movups  [rbp+100h+var_D0], xmm0
0x180071b5e  mov     [rbp+100h+var_140], 6E006Ch
0x180071b66  movups  [rbp+100h+var_C0], xmm0
0x180071b6a  mov     [rbp+100h+var_130], 6A0068h
0x180071b72  movups  [rbp+100h+var_110], xmm0
0x180071b76  mov     [rbp+100h+var_120], 7C007Ah
0x180071b7e  movups  [rbp+100h+var_100], xmm0
0x180071b82  mov     [rsp+200h+var_1A0], rsi
0x180071b87  movups  [rbp+100h+var_F0], xmm0
0x180071b8b  mov     [rsp+200h+var_198], rsi
0x180071b90  movups  [rbp+100h+var_B0], xmm0
0x180071b94  mov     [rsp+200h+BaseAddress], rsi
0x180071b99  movups  [rbp+100h+var_A0], xmm0
0x180071b9d  mov     [rsp+200h+var_1C0], esi
0x180071ba1  movups  [rbp+100h+var_90], xmm0
0x180071ba5  mov     [rbp+100h+MemoryDescriptorList], rsi
0x180071ba9  movups  [rbp+100h+var_80], xmm1
0x180071bb0  mov     [rsp+200h+var_188], rsi
0x180071bb5  movups  [rbp+100h+var_70], xmm1
0x180071bbc  mov     [rsp+200h+var_1BC], esi
0x180071bc0  movups  [rbp+100h+var_60], xmm1
0x180071bc7  mov     [rbp+100h+Mdl], rsi
0x180071bcb  call    cs:__imp_KeStackAttachProcess
0x180071bd2  nop     dword ptr [rax+rax+00h]
0x180071bd7  lea     rax, [rbp+100h+var_158]
0x180071bdb  mov     [rsp+200h+var_1D0], rax
0x180071be0  lea     r14, qword_180048E50
0x180071be7  lea     rax, [rbp+100h+var_110]
0x180071beb  mov     [rsp+200h+var_1D8], r14
0x180071bf0  lea     r9, [rsp+200h+P]
0x180071bf5  mov     [rsp+200h+var_1E0], rax
0x180071bfa  lea     r8, [rsp+200h+var_1B4]
0x180071bff  lea     rdx, [rbp+100h+var_178]
0x180071c03  lea     rcx, [rbp+100h+var_150]
0x180071c07  call    CipParseRevocationListAtPath
0x180071c0c  mov     ebx, eax
0x180071c0e  test    eax, eax
0x180071c10  js      loc_180071DAA
0x180071c16  lea     rax, [rbp+100h+var_160]
0x180071c1a  mov     [rsp+200h+var_1D0], rax
0x180071c1f  lea     r9, [rsp+200h+var_1A8]
0x180071c24  lea     rax, qword_180048E58
0x180071c2b  mov     [rsp+200h+var_1D8], rax
0x180071c30  lea     r8, [rsp+200h+var_1B8]
0x180071c35  lea     rax, [rbp+100h+var_E0]
0x180071c39  lea     rdx, [rbp+100h+var_180]
0x180071c3d  mov     [rsp+200h+var_1E0], rax
0x180071c42  lea     rcx, [rbp+100h+var_140]
0x180071c46  call    CipParseRevocationListAtPath
0x180071c4b  mov     ebx, eax
0x180071c4d  test    eax, eax
0x180071c4f  js      loc_180071DAA
0x180071c55  lea     rax, [rbp+100h+Mdl]
0x180071c59  mov     [rsp+200h+var_1D0], rax
0x180071c5e  lea     r9, [rsp+200h+var_1A0]
0x180071c63  lea     rax, qword_180048E60
0x180071c6a  mov     [rsp+200h+var_1D8], rax
0x180071c6f  lea     r8, [rsp+200h+var_1BC]
0x180071c74  lea     rax, [rbp+100h+var_B0]
0x180071c78  lea     rdx, [rsp+200h+var_188]
0x180071c7d  mov     [rsp+200h+var_1E0], rax
0x180071c82  lea     rcx, [rbp+100h+var_130]
0x180071c86  call    CipParseRevocationListAtPath
0x180071c8b  mov     ebx, eax
0x180071c8d  test    eax, eax
0x180071c8f  js      loc_180071D3A
0x180071c95  lea     rax, [rbp+100h+MemoryDescriptorList]
0x180071c99  mov     [rsp+200h+var_1D0], rax
0x180071c9e  lea     r9, [rsp+200h+var_198]
0x180071ca3  lea     rax, qword_180048E68
0x180071caa  mov     [rsp+200h+var_1D8], rax
0x180071caf  lea     r8, [rsp+200h+var_1C0]
0x180071cb4  lea     rax, [rbp+100h+var_80]
0x180071cbb  lea     rdx, [rsp+200h+BaseAddress]
0x180071cc0  mov     [rsp+200h+var_1E0], rax
0x180071cc5  lea     rcx, [rbp+100h+var_120]
0x180071cc9  call    CipParseRevocationListAtPath
0x180071cce  mov     ebx, eax
0x180071cd0  test    eax, eax
0x180071cd2  js      loc_180071DAA
0x180071cd8  mov     rax, cs:qword_180048E60
0x180071cdf  cmp     rax, cs:qword_180048E50
0x180071ce6  jle     short loc_180071D48
0x180071ce8  cmp     cs:g_CiBlocklistUpdateTime, rax
0x180071cef  mov     [rsp+200h+var_1D8], rdi
0x180071cf4  jle     short loc_180071D16
0x180071cf6  mov     r9d, [rsp+200h+var_1C0]
0x180071cfb  lea     rdx, [rbp+100h+var_80]
0x180071d02  mov     r8, [rsp+200h+BaseAddress]
0x180071d07  lea     rcx, [rsp+200h+var_198]
0x180071d0c  mov     dword ptr [rsp+200h+var_1E0], 3
0x180071d14  jmp     short loc_180071D31
0x180071d16  mov     r9d, [rsp+200h+var_1BC]
0x180071d1b  lea     rdx, [rbp+100h+var_B0]
0x180071d1f  mov     r8, [rsp+200h+var_188]
0x180071d24  lea     rcx, [rsp+200h+var_1A0]
0x180071d29  mov     dword ptr [rsp+200h+var_1E0], 2
0x180071d31  call    CipSetRevocationList
0x180071d36  mov     ebx, eax
0x180071d38  jmp     short loc_180071DAA
0x180071d3a  cmp     eax, 0C000003Ah
0x180071d3f  jz      short loc_180071D48
0x180071d41  cmp     eax, 0C0000034h
0x180071d46  jnz     short loc_180071DAA
0x180071d48  mov     rax, cs:qword_180048E50
0x180071d4f  cmp     cs:g_CiBlocklistUpdateTime, rax
0x180071d56  mov     [rsp+200h+var_1D8], rdi
0x180071d5b  jle     short loc_180071D79
0x180071d5d  mov     r9d, [rsp+200h+var_1B8]
0x180071d62  lea     rdx, [rbp+100h+var_E0]
0x180071d66  mov     r8, [rbp+100h+var_180]
0x180071d6a  lea     rcx, [rsp+200h+var_1A8]
0x180071d6f  mov     dword ptr [rsp+200h+var_1E0], 1
0x180071d77  jmp     short loc_180071D8F
0x180071d79  mov     r9d, [rsp+200h+var_1B4]
0x180071d7e  lea     rdx, [rbp+100h+var_110]
0x180071d82  mov     r8, [rbp+100h+var_178]
0x180071d86  lea     rcx, [rsp+200h+P]
0x180071d8b  mov     dword ptr [rsp+200h+var_1E0], esi
0x180071d8f  call    CipSetRevocationList
0x180071d94  mov     ebx, eax
0x180071d96  test    eax, eax
0x180071d98  js      short loc_180071DAA
0x180071d9a  movsxd  rax, cs:g_CiRevocationListInfo
0x180071da1  lea     rcx, [r14+rax*8]
0x180071da5  call    CiBlackBoxRevocationListUpdate
0x180071daa  cmp     dword ptr [rbp+100h+var_110], esi
0x180071dad  jz      short loc_180071DB8
0x180071daf  mov     rcx, qword ptr [rbp+100h+var_100]
0x180071db3  call    I_MincryptFreeChainInfo
0x180071db8  cmp     dword ptr [rbp+100h+var_E0], esi
0x180071dbb  jz      short loc_180071DC6
0x180071dbd  mov     rcx, qword ptr [rbp+100h+var_D0]
0x180071dc1  call    I_MincryptFreeChainInfo
0x180071dc6  cmp     dword ptr [rbp+100h+var_B0], esi
0x180071dc9  jz      short loc_180071DD4
0x180071dcb  mov     rcx, qword ptr [rbp+100h+var_A0]
0x180071dcf  call    I_MincryptFreeChainInfo
0x180071dd4  cmp     dword ptr [rbp+100h+var_80], esi
0x180071dda  jz      short loc_180071DE8
0x180071ddc  mov     rcx, qword ptr [rbp+100h+var_70]
0x180071de3  call    I_MincryptFreeChainInfo
0x180071de8  mov     rcx, [rsp+200h+P]; P
0x180071ded  mov     edi, 63734943h
0x180071df2  test    rcx, rcx
0x180071df5  jz      short loc_180071E05
0x180071df7  mov     edx, edi; Tag
0x180071df9  call    cs:__imp_ExFreePoolWithTag
0x180071e00  nop     dword ptr [rax+rax+00h]
0x180071e05  mov     rcx, [rsp+200h+var_1A8]; P
0x180071e0a  test    rcx, rcx
0x180071e0d  jz      short loc_180071E1D
0x180071e0f  mov     edx, edi; Tag
0x180071e11  call    cs:__imp_ExFreePoolWithTag
0x180071e18  nop     dword ptr [rax+rax+00h]
0x180071e1d  mov     rcx, [rsp+200h+var_1A0]; P
0x180071e22  test    rcx, rcx
0x180071e25  jz      short loc_180071E35
0x180071e27  mov     edx, edi; Tag
0x180071e29  call    cs:__imp_ExFreePoolWithTag
0x180071e30  nop     dword ptr [rax+rax+00h]
0x180071e35  mov     rcx, [rsp+200h+var_198]; P
0x180071e3a  test    rcx, rcx
0x180071e3d  jz      short loc_180071E4D
0x180071e3f  mov     edx, edi; Tag
0x180071e41  call    cs:__imp_ExFreePoolWithTag
0x180071e48  nop     dword ptr [rax+rax+00h]
0x180071e4d  mov     rdi, [rbp+100h+MemoryDescriptorList]
0x180071e51  test    rdi, rdi
0x180071e54  jz      short loc_180071E74
0x180071e56  mov     rcx, rdi; MemoryDescriptorList
0x180071e59  call    cs:__imp_MmUnlockPages
0x180071e60  nop     dword ptr [rax+rax+00h]
0x180071e65  mov     rcx, rdi; Mdl
0x180071e68  call    cs:__imp_IoFreeMdl
0x180071e6f  nop     dword ptr [rax+rax+00h]
0x180071e74  mov     rdx, [rsp+200h+BaseAddress]; BaseAddress
0x180071e79  or      r14, 0FFFFFFFFFFFFFFFFh
0x180071e7d  test    rdx, rdx
0x180071e80  jz      short loc_180071E91
0x180071e82  mov     rcx, r14; ProcessHandle
0x180071e85  call    cs:__imp_ZwUnmapViewOfSection
0x180071e8c  nop     dword ptr [rax+rax+00h]
0x180071e91  mov     rdi, [rbp+100h+Mdl]
0x180071e95  test    rdi, rdi
0x180071e98  jz      short loc_180071EB8
0x180071e9a  mov     rcx, rdi; MemoryDescriptorList
0x180071e9d  call    cs:__imp_MmUnlockPages
0x180071ea4  nop     dword ptr [rax+rax+00h]
0x180071ea9  mov     rcx, rdi; Mdl
0x180071eac  call    cs:__imp_IoFreeMdl
0x180071eb3  nop     dword ptr [rax+rax+00h]
0x180071eb8  mov     rdx, [rsp+200h+var_188]; BaseAddress
0x180071ebd  test    rdx, rdx
0x180071ec0  jz      short loc_180071ED1
0x180071ec2  mov     rcx, r14; ProcessHandle
0x180071ec5  call    cs:__imp_ZwUnmapViewOfSection
0x180071ecc  nop     dword ptr [rax+rax+00h]
0x180071ed1  mov     rdi, [rbp+100h+var_160]
0x180071ed5  test    rdi, rdi
0x180071ed8  jz      short loc_180071EF8
0x180071eda  mov     rcx, rdi; MemoryDescriptorList
0x180071edd  call    cs:__imp_MmUnlockPages
0x180071ee4  nop     dword ptr [rax+rax+00h]
0x180071ee9  mov     rcx, rdi; Mdl
0x180071eec  call    cs:__imp_IoFreeMdl
0x180071ef3  nop     dword ptr [rax+rax+00h]
0x180071ef8  mov     rdx, [rbp+100h+var_180]; BaseAddress
0x180071efc  test    rdx, rdx
0x180071eff  jz      short loc_180071F10
0x180071f01  mov     rcx, r14; ProcessHandle
0x180071f04  call    cs:__imp_ZwUnmapViewOfSection
0x180071f0b  nop     dword ptr [rax+rax+00h]
0x180071f10  mov     rdi, [rbp+100h+var_158]
0x180071f14  test    rdi, rdi
0x180071f17  jz      short loc_180071F37
0x180071f19  mov     rcx, rdi; MemoryDescriptorList
0x180071f1c  call    cs:__imp_MmUnlockPages
0x180071f23  nop     dword ptr [rax+rax+00h]
0x180071f28  mov     rcx, rdi; Mdl
0x180071f2b  call    cs:__imp_IoFreeMdl
0x180071f32  nop     dword ptr [rax+rax+00h]
0x180071f37  mov     rdx, [rbp+100h+var_178]; BaseAddress
0x180071f3b  test    rdx, rdx
0x180071f3e  jz      short loc_180071F4F
0x180071f40  mov     rcx, r14; ProcessHandle
0x180071f43  call    cs:__imp_ZwUnmapViewOfSection
0x180071f4a  nop     dword ptr [rax+rax+00h]
0x180071f4f  lea     rcx, [rbp+100h+ApcState]; ApcState
0x180071f56  call    cs:__imp_KeUnstackDetachProcess
0x180071f5d  nop     dword ptr [rax+rax+00h]
0x180071f62  mov     eax, ebx
0x180071f64  mov     rcx, [rbp+100h+var_20]
0x180071f6b  xor     rcx, rsp; StackCookie
0x180071f6e  call    __security_check_cookie
0x180071f73  lea     r11, [rsp+200h+var_10]
0x180071f7b  mov     rbx, [r11+28h]
0x180071f7f  mov     rsi, [r11+30h]
0x180071f83  mov     rsp, r11
0x180071f86  pop     r14
0x180071f88  pop     rdi
0x180071f89  pop     rbp
0x180071f8a  retn
```
