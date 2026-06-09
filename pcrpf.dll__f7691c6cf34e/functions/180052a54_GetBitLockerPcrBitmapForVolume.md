# GetBitLockerPcrBitmapForVolume

- ea: `0x180052a54`
- end: `0x180052e9e`
- name: `GetBitLockerPcrBitmapForVolume`
- size: `1098`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180052ea4`

## callees

- `0x180003270`
- `0x180009c64`
- `0x18002d5ec`
- `0x180052a54`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180052aef`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180052c32`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180052aef`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180052c32`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052adb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052c1e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052d14`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052d64`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052de1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052e30`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052adb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052c1e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052d14`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052d64`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052de1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180052e30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180052d28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180052d78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180052df5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180052e44`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180052d28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180052d78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180052df5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180052e44`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180052b64`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180052b64`
- `FVEAPI!FveGetAuthMethodGuids` at `0x180052aa4`
- `FVEAPI!FveGetAuthMethodGuids` at `0x180052b1b`
- `FVEAPI!FveGetAuthMethodGuids` at `0x180052aa4`
- `FVEAPI!FveGetAuthMethodGuids` at `0x180052b1b`
- `FVEAPI!FveGetAuthMethodInformation` at `0x180052bef`
- `FVEAPI!FveGetAuthMethodInformation` at `0x180052c80`
- `FVEAPI!FveGetAuthMethodInformation` at `0x180052bef`
- `FVEAPI!FveGetAuthMethodInformation` at `0x180052c80`

## string_xrefs

- `0x180052abd`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`
- `0x180052b95`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`
- `0x180052ce6`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`
- `0x180052d52`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`
- `0x180052d94`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`
- `0x180052daf`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`
- `0x180052dd0`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`
- `0x180052e1e`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`
- `0x180052e60`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetBitLockerPcrBitmapForVolume(__int64 a1, int *a2)
{
  __int64 v2; // r15
  int AuthMethodGuids; // eax
  unsigned int v4; // ebx
  SIZE_T v5; // rbx
  HANDLE ProcessHeap; // rax
  GUID *v7; // rax
  GUID *v8; // r14
  int v9; // eax
  __int64 v10; // r9
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // r12d
  void *v14; // rbx
  int AuthMethodInformation; // eax
  unsigned int v16; // esi
  __int128 *v17; // rsi
  __int128 *v18; // r13
  SIZE_T v19; // rbx
  HANDLE v20; // rax
  _OWORD *v21; // rax
  int v22; // eax
  unsigned __int64 v23; // r15
  int v24; // r14d
  __int64 v25; // rax
  HANDLE v26; // rax
  HANDLE v27; // rax
  HANDLE v28; // rax
  HANDLE v29; // rax
  unsigned int v31; // [rsp+30h] [rbp-99h] BYREF
  __int64 v32; // [rsp+38h] [rbp-91h]
  SIZE_T dwBytes; // [rsp+40h] [rbp-89h] BYREF
  _OWORD *v34; // [rsp+48h] [rbp-81h]
  GUID *v35; // [rsp+50h] [rbp-79h]
  __int64 v36; // [rsp+58h] [rbp-71h]
  int *v37; // [rsp+60h] [rbp-69h]
  __int128 v38; // [rsp+68h] [rbp-61h] BYREF
  __int128 v39; // [rsp+78h] [rbp-51h]
  _BYTE v40[24]; // [rsp+88h] [rbp-41h] BYREF
  OLECHAR sz[40]; // [rsp+A0h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v37 = a2;
  v2 = a1;
  v36 = a1;
  *a2 = 0;
  v31 = 0;
  AuthMethodGuids = FveGetAuthMethodGuids(a1, 0, 0, &v31);
  v4 = AuthMethodGuids;
  if ( AuthMethodGuids < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x55,
      (int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
      (const char *)(unsigned int)AuthMethodGuids);
    return v4;
  }
  v5 = 16LL * v31;
  ProcessHeap = GetProcessHeap();
  v7 = (GUID *)HeapAlloc(ProcessHeap, 0, v5);
  v8 = v7;
  v35 = v7;
  if ( !v7 )
  {
    v4 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x57,
      (int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
      (const char *)0x8007000ELL);
    return v4;
  }
  v9 = FveGetAuthMethodGuids(v2, v7, v31, &v31);
  v4 = v9;
  if ( v9 < 0 )
  {
    v10 = (unsigned int)v9;
    v11 = 88;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
      (const char *)v10);
    goto LABEL_32;
  }
  v12 = 0;
  LODWORD(v32) = 0;
  v13 = 0;
  if ( !v31 )
    goto LABEL_34;
  while ( 1 )
  {
    if ( StringFromGUID2(&v8[v13], sz, 39) != 39 )
    {
      v4 = -2147418113;
      v10 = 2147549183LL;
      v11 = 94;
      goto LABEL_31;
    }
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
      0x5Fu,
      "GetBitLockerPcrBitmapForVolume",
      "Checking BitLocker protector %ws",
      sz);
    v39 = 0;
    memset(v40, 0, sizeof(v40));
    *(_QWORD *)&v38 = 0x100000038LL;
    *((_QWORD *)&v38 + 1) = 1;
    *(GUID *)&v40[8] = v8[v13];
    dwBytes = 0;
    v14 = 0;
    v34 = 0;
    AuthMethodInformation = FveGetAuthMethodInformation(v2, &v38, 56, &dwBytes);
    v16 = AuthMethodInformation;
    if ( AuthMethodInformation )
    {
      if ( AuthMethodInformation == -2147024774 )
      {
        v19 = dwBytes;
        v20 = GetProcessHeap();
        v21 = HeapAlloc(v20, 0, v19);
        v14 = v21;
        v34 = v21;
        if ( !v21 )
        {
          v4 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x73,
            (int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
            (const char *)0x8007000ELL);
LABEL_32:
          v28 = GetProcessHeap();
          HeapFree(v28, 0, v8);
          return v4;
        }
        *v21 = v38;
        v21[1] = v39;
        v21[2] = *(_OWORD *)v40;
        *((_QWORD *)v21 + 6) = *(_QWORD *)&v40[16];
        v22 = FveGetAuthMethodInformation(v2, v21, dwBytes, &dwBytes);
        v16 = v22;
        if ( v22 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x75,
            (int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
            (const char *)(unsigned int)v22);
          v27 = GetProcessHeap();
          HeapFree(v27, 0, v14);
LABEL_27:
          v4 = v16;
          goto LABEL_32;
        }
        v17 = (__int128 *)v14;
        v18 = (__int128 *)v14;
      }
      else
      {
        if ( AuthMethodInformation < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x78,
            (int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
            (const char *)(unsigned int)AuthMethodInformation);
          goto LABEL_27;
        }
        v17 = 0;
        v18 = 0;
      }
    }
    else
    {
      v17 = &v38;
      v18 = &v38;
    }
    v23 = 0;
    if ( *((_DWORD *)v17 + 3) )
    {
      v24 = v32;
      do
      {
        v25 = *(_QWORD *)(*((_QWORD *)v18 + 2) + 8 * v23);
        v32 = v25;
        if ( *(_DWORD *)(v25 + 12) == 3 )
        {
          PpfTraceLogFormat(
            "onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
            0x80u,
            "GetBitLockerPcrBitmapForVolume",
            "TPM protector PCR bitmap: 0x%x",
            *(_DWORD *)(v25 + 16));
          v24 |= *(_DWORD *)(v32 + 16);
        }
        ++v23;
      }
      while ( v23 < *((unsigned int *)v17 + 3) );
      LODWORD(v32) = v24;
      v8 = v35;
    }
    if ( v14 )
    {
      v26 = GetProcessHeap();
      HeapFree(v26, 0, v14);
    }
    if ( ++v13 >= v31 )
      break;
    v2 = v36;
  }
  v12 = v32;
LABEL_34:
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
    0x86u,
    "GetBitLockerPcrBitmapForVolume",
    "TPM protector PCR bitmap (all TPM protectors): 0x%x",
    v12);
  *v37 = v12;
  v29 = GetProcessHeap();
  HeapFree(v29, 0, v8);
  return 0;
}

```

## disassembly

```asm
0x180052a54  mov     [rsp-8+arg_10], rbx
0x180052a59  mov     [rsp-8+arg_18], rsi
0x180052a5e  push    rbp
0x180052a5f  push    r12
0x180052a61  push    r13
0x180052a63  push    r14
0x180052a65  push    r15
0x180052a67  lea     rbp, [rsp-37h]
0x180052a6c  sub     rsp, 100h
0x180052a73  mov     rax, cs:__security_cookie
0x180052a7a  xor     rax, rsp
0x180052a7d  mov     [rbp+57h+var_30], rax
0x180052a81  mov     [rbp+57h+var_C0], rdx
0x180052a85  mov     r15, rcx
0x180052a88  mov     [rbp+57h+var_C8], rcx
0x180052a8c  mov     dword ptr [rdx], 0
0x180052a92  mov     [rsp+120h+var_F0], 0
0x180052a9a  lea     r9, [rsp+120h+var_F0]
0x180052a9f  xor     r8d, r8d
0x180052aa2  xor     edx, edx
0x180052aa4  call    cs:__imp_FveGetAuthMethodGuids
0x180052aab  nop     dword ptr [rax+rax+00h]
0x180052ab0  mov     ebx, eax
0x180052ab2  test    eax, eax
0x180052ab4  jns     short loc_180052AD3
0x180052ab6  mov     rcx, [rbp+5Fh]; this
0x180052aba  mov     r9d, eax; char *
0x180052abd  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x180052ac4  mov     edx, 55h ; 'U'; void *
0x180052ac9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052ace  jmp     loc_180052E72
0x180052ad3  mov     ebx, [rsp+120h+var_F0]
0x180052ad7  shl     rbx, 4
0x180052adb  call    cs:__imp_GetProcessHeap
0x180052ae2  nop     dword ptr [rax+rax+00h]
0x180052ae7  mov     r8, rbx; dwBytes
0x180052aea  xor     edx, edx; dwFlags
0x180052aec  mov     rcx, rax; hHeap
0x180052aef  call    cs:__imp_HeapAlloc
0x180052af6  nop     dword ptr [rax+rax+00h]
0x180052afb  mov     r14, rax
0x180052afe  mov     [rbp+57h+var_D0], rax
0x180052b02  test    rax, rax
0x180052b05  jz      loc_180052E54
0x180052b0b  lea     r9, [rsp+120h+var_F0]
0x180052b10  mov     r8d, [rsp+120h+var_F0]
0x180052b15  mov     rdx, rax
0x180052b18  mov     rcx, r15
0x180052b1b  call    cs:__imp_FveGetAuthMethodGuids
0x180052b22  nop     dword ptr [rax+rax+00h]
0x180052b27  mov     ebx, eax
0x180052b29  test    eax, eax
0x180052b2b  jns     short loc_180052B3A
0x180052b2d  mov     r9d, eax
0x180052b30  mov     edx, 58h ; 'X'
0x180052b35  jmp     loc_180052DD0
0x180052b3a  xor     ebx, ebx
0x180052b3c  mov     dword ptr [rsp+120h+var_E8], ebx
0x180052b40  xor     r12d, r12d
0x180052b43  cmp     [rsp+120h+var_F0], ebx
0x180052b47  jbe     loc_180052E07
0x180052b4d  mov     ebx, r12d
0x180052b50  shl     rbx, 4
0x180052b54  add     rbx, r14
0x180052b57  mov     r8d, 27h ; '''; cchMax
0x180052b5d  lea     rdx, [rbp+57h+sz]; lpsz
0x180052b61  mov     rcx, rbx; rguid
0x180052b64  call    cs:__imp_StringFromGUID2
0x180052b6b  nop     dword ptr [rax+rax+00h]
0x180052b70  cmp     eax, 27h ; '''
0x180052b73  jnz     loc_180052DC3
0x180052b79  lea     rax, [rbp+57h+sz]
0x180052b7d  mov     qword ptr [rsp+120h+var_100], rax; int
0x180052b82  lea     r9, aCheckingBitloc; "Checking BitLocker protector %ws"
0x180052b89  lea     r8, aGetbitlockerpc; "GetBitLockerPcrBitmapForVolume"
0x180052b90  mov     edx, 5Fh ; '_'; unsigned int
0x180052b95  lea     rcx, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x180052b9c  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180052ba1  xorps   xmm0, xmm0
0x180052ba4  xor     eax, eax
0x180052ba6  movups  [rbp+57h+var_B8], xmm0
0x180052baa  movups  [rbp+57h+var_A8], xmm0
0x180052bae  movups  [rbp+57h+var_98], xmm0
0x180052bb2  mov     [rbp+57h+var_88], rax
0x180052bb6  mov     dword ptr [rbp+57h+var_B8], 38h ; '8'
0x180052bbd  mov     dword ptr [rbp+57h+var_B8+4], 1
0x180052bc4  mov     dword ptr [rbp+57h+var_B8+8], 1
0x180052bcb  movups  xmm0, xmmword ptr [rbx]
0x180052bce  movdqu  [rbp+57h+var_98+8], xmm0
0x180052bd3  mov     [rsp+120h+dwBytes], rax
0x180052bd8  xor     ebx, ebx
0x180052bda  mov     [rsp+120h+var_D8], rbx
0x180052bdf  lea     r9, [rsp+120h+dwBytes]
0x180052be4  lea     r8d, [rax+38h]
0x180052be8  lea     rdx, [rbp+57h+var_B8]
0x180052bec  mov     rcx, r15
0x180052bef  call    cs:__imp_FveGetAuthMethodInformation
0x180052bf6  nop     dword ptr [rax+rax+00h]
0x180052bfb  mov     esi, eax
0x180052bfd  test    eax, eax
0x180052bff  jnz     short loc_180052C0D
0x180052c01  lea     rsi, [rbp+57h+var_B8]
0x180052c05  mov     r13, rsi
0x180052c08  jmp     loc_180052CAB
0x180052c0d  cmp     esi, 8007007Ah
0x180052c13  jnz     loc_180052C9E
0x180052c19  mov     rbx, [rsp+120h+dwBytes]
0x180052c1e  call    cs:__imp_GetProcessHeap
0x180052c25  nop     dword ptr [rax+rax+00h]
0x180052c2a  mov     r8, rbx; dwBytes
0x180052c2d  xor     edx, edx; dwFlags
0x180052c2f  mov     rcx, rax; hHeap
0x180052c32  call    cs:__imp_HeapAlloc
0x180052c39  nop     dword ptr [rax+rax+00h]
0x180052c3e  mov     rbx, rax
0x180052c41  mov     [rsp+120h+var_D8], rax
0x180052c46  test    rax, rax
0x180052c49  jz      loc_180052D88
0x180052c4f  movups  xmm0, [rbp+57h+var_B8]
0x180052c53  movups  xmmword ptr [rax], xmm0
0x180052c56  movups  xmm1, [rbp+57h+var_A8]
0x180052c5a  movups  xmmword ptr [rax+10h], xmm1
0x180052c5e  movups  xmm0, [rbp+57h+var_98]
0x180052c62  movups  xmmword ptr [rax+20h], xmm0
0x180052c66  movsd   xmm1, [rbp+57h+var_88]
0x180052c6b  movsd   qword ptr [rax+30h], xmm1
0x180052c70  lea     r9, [rsp+120h+dwBytes]
0x180052c75  mov     r8, [rsp+120h+dwBytes]
0x180052c7a  mov     rdx, rax
0x180052c7d  mov     rcx, r15
0x180052c80  call    cs:__imp_FveGetAuthMethodInformation
0x180052c87  nop     dword ptr [rax+rax+00h]
0x180052c8c  mov     esi, eax
0x180052c8e  test    eax, eax
0x180052c90  js      loc_180052D4B
0x180052c96  mov     rsi, rbx
0x180052c99  mov     r13, rbx
0x180052c9c  jmp     short loc_180052CAB
0x180052c9e  test    esi, esi
0x180052ca0  js      loc_180052DA8
0x180052ca6  xor     esi, esi
0x180052ca8  xor     r13d, r13d
0x180052cab  xor     r15d, r15d
0x180052cae  cmp     [rsi+0Ch], r15d
0x180052cb2  jbe     short loc_180052D0F
0x180052cb4  mov     r14d, dword ptr [rsp+120h+var_E8]
0x180052cb9  mov     rax, [r13+10h]
0x180052cbd  mov     rax, [rax+r15*8]
0x180052cc1  mov     [rsp+120h+var_E8], rax
0x180052cc6  cmp     dword ptr [rax+0Ch], 3
0x180052cca  jnz     short loc_180052CFB
0x180052ccc  mov     eax, [rax+10h]
0x180052ccf  mov     [rsp+120h+var_100], eax
0x180052cd3  lea     r9, aTpmProtectorPc; "TPM protector PCR bitmap: 0x%x"
0x180052cda  lea     r8, aGetbitlockerpc; "GetBitLockerPcrBitmapForVolume"
0x180052ce1  mov     edx, 80h; unsigned int
0x180052ce6  lea     rcx, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x180052ced  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180052cf2  mov     rax, [rsp+120h+var_E8]
0x180052cf7  or      r14d, [rax+10h]
0x180052cfb  inc     r15
0x180052cfe  mov     eax, [rsi+0Ch]
0x180052d01  cmp     r15, rax
0x180052d04  jb      short loc_180052CB9
0x180052d06  mov     dword ptr [rsp+120h+var_E8], r14d
0x180052d0b  mov     r14, [rbp+57h+var_D0]
0x180052d0f  test    rbx, rbx
0x180052d12  jz      short loc_180052D34
0x180052d14  call    cs:__imp_GetProcessHeap
0x180052d1b  nop     dword ptr [rax+rax+00h]
0x180052d20  mov     rcx, rax; hHeap
0x180052d23  mov     r8, rbx; lpMem
0x180052d26  xor     edx, edx; dwFlags
0x180052d28  call    cs:__imp_HeapFree
0x180052d2f  nop     dword ptr [rax+rax+00h]
0x180052d34  inc     r12d
0x180052d37  cmp     r12d, [rsp+120h+var_F0]
0x180052d3c  jnb     loc_180052E03
0x180052d42  mov     r15, [rbp+57h+var_C8]
0x180052d46  jmp     loc_180052B4D
0x180052d4b  mov     rcx, [rbp+5Fh]; this
0x180052d4f  mov     r9d, esi; char *
0x180052d52  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x180052d59  mov     edx, 75h ; 'u'; void *
0x180052d5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052d63  nop
0x180052d64  call    cs:__imp_GetProcessHeap
0x180052d6b  nop     dword ptr [rax+rax+00h]
0x180052d70  mov     rcx, rax; hHeap
0x180052d73  mov     r8, rbx; lpMem
0x180052d76  xor     edx, edx; dwFlags
0x180052d78  call    cs:__imp_HeapFree
0x180052d7f  nop     dword ptr [rax+rax+00h]
0x180052d84  mov     ebx, esi
0x180052d86  jmp     short loc_180052DE1
0x180052d88  mov     rcx, [rbp+5Fh]; this
0x180052d8c  mov     ebx, 8007000Eh
0x180052d91  mov     r9d, ebx; char *
0x180052d94  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x180052d9b  mov     edx, 73h ; 's'; void *
0x180052da0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052da5  nop
0x180052da6  jmp     short loc_180052DE1
0x180052da8  mov     rcx, [rbp+5Fh]; this
0x180052dac  mov     r9d, esi; char *
0x180052daf  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x180052db6  mov     edx, 78h ; 'x'; void *
0x180052dbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052dc0  nop
0x180052dc1  jmp     short loc_180052D84
0x180052dc3  mov     ebx, 8000FFFFh
0x180052dc8  mov     r9d, ebx; char *
0x180052dcb  mov     edx, 5Eh ; '^'; void *
0x180052dd0  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x180052dd7  mov     rcx, [rbp+5Fh]; this
0x180052ddb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052de0  nop
0x180052de1  call    cs:__imp_GetProcessHeap
0x180052de8  nop     dword ptr [rax+rax+00h]
0x180052ded  mov     rcx, rax; hHeap
0x180052df0  mov     r8, r14; lpMem
0x180052df3  xor     edx, edx; dwFlags
0x180052df5  call    cs:__imp_HeapFree
0x180052dfc  nop     dword ptr [rax+rax+00h]
0x180052e01  jmp     short loc_180052E72
0x180052e03  mov     ebx, dword ptr [rsp+120h+var_E8]
0x180052e07  mov     [rsp+120h+var_100], ebx
0x180052e0b  lea     r9, aTpmProtectorPc_0; "TPM protector PCR bitmap (all TPM prote"...
0x180052e12  lea     r8, aGetbitlockerpc; "GetBitLockerPcrBitmapForVolume"
0x180052e19  mov     edx, 86h; unsigned int
0x180052e1e  lea     rcx, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x180052e25  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180052e2a  mov     rax, [rbp+57h+var_C0]
0x180052e2e  mov     [rax], ebx
0x180052e30  call    cs:__imp_GetProcessHeap
0x180052e37  nop     dword ptr [rax+rax+00h]
0x180052e3c  mov     rcx, rax; hHeap
0x180052e3f  mov     r8, r14; lpMem
0x180052e42  xor     edx, edx; dwFlags
0x180052e44  call    cs:__imp_HeapFree
0x180052e4b  nop     dword ptr [rax+rax+00h]
0x180052e50  xor     eax, eax
0x180052e52  jmp     short loc_180052E74
0x180052e54  mov     rcx, [rbp+5Fh]; this
0x180052e58  mov     ebx, 8007000Eh
0x180052e5d  mov     r9d, ebx; char *
0x180052e60  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x180052e67  mov     edx, 57h ; 'W'; void *
0x180052e6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052e71  nop
0x180052e72  mov     eax, ebx
0x180052e74  mov     rcx, [rbp+57h+var_30]
0x180052e78  xor     rcx, rsp; StackCookie
0x180052e7b  call    __security_check_cookie
0x180052e80  lea     r11, [rsp+120h+var_20]
0x180052e88  mov     rbx, [r11+40h]
0x180052e8c  mov     rsi, [r11+48h]
0x180052e90  mov     rsp, r11
0x180052e93  pop     r15
0x180052e95  pop     r14
0x180052e97  pop     r13
0x180052e99  pop     r12
0x180052e9b  pop     rbp
0x180052e9c  retn
```
