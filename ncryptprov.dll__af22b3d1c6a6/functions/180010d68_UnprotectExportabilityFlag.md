# UnprotectExportabilityFlag

- ea: `0x180010d68`
- end: `0x180010fa4`
- name: `UnprotectExportabilityFlag`
- size: `572`
- prototype: `__int64 __fastcall(int, __int64, int, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000f8e8`

## callees

- `0x18000af80`
- `0x18000b250`
- `0x180010d68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010e67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010e67`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010e44`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010e44`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180010e9f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180010e9f`
- `DPAPI!CryptUnprotectDataNoUI` at `0x180010e15`
- `DPAPI!CryptUnprotectDataNoUI` at `0x180010e15`

## string_xrefs

- `0x180010dd5`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`
- `0x180010f74`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`
- `0x180010f18`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`
- `0x180010f50`: `onecore\ds\security\cryptoapi\ncrypt\storage\legacy.c`

## pseudocode

```c
__int64 __fastcall UnprotectExportabilityFlag(int a1, __int64 a2, int a3, _DWORD *a4)
{
  int v4; // r13d
  unsigned int v6; // esi
  DWORD v7; // r14d
  unsigned int v8; // ebx
  DWORD LastError; // eax
  PVOID *v11; // rcx
  _QWORD v12[2]; // [rsp+50h] [rbp-39h] BYREF
  _DWORD v13[2]; // [rsp+60h] [rbp-29h] BYREF
  __int64 v14; // [rsp+68h] [rbp-21h]
  HLOCAL hMem[2]; // [rsp+70h] [rbp-19h] BYREF
  __int128 v16; // [rsp+80h] [rbp-9h] BYREF
  __int64 v17; // [rsp+90h] [rbp+7h]

  v12[0] = 17;
  v17 = 0;
  v13[1] = 0;
  v13[0] = a3;
  v4 = a1 != 0 ? 4 : 0;
  v14 = a2;
  v12[1] = "Hj1diQ6kpUx7VC4m";
  v16 = 0;
  LODWORD(v16) = 24;
  *(_OWORD *)hMem = 0;
  if ( a2 )
  {
    v6 = 0;
    v7 = 10;
    while ( !(unsigned int)CryptUnprotectDataNoUI(v13, 0, v12, 0, &v16, v4, 0, 0, hMem) )
    {
      LastError = GetLastError();
      v8 = LastError;
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          a2,
          a3,
          (unsigned int)"dwSts",
          LastError,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c",
          21);
        v11 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v8 != 1723 || v6 >= 5 )
      {
        if ( v8 )
          goto LABEL_18;
        break;
      }
      Sleep(v7);
      v7 *= 2;
      ++v6;
    }
    if ( LODWORD(hMem[0]) == 4 )
    {
      v8 = 0;
      *a4 = *(_DWORD *)hMem[1];
    }
    else
    {
      v8 = -2146893802;
      DebugTraceError(2148073494LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c", 2671);
    }
  }
  else
  {
    v8 = 87;
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          0,
          a3,
          (unsigned int)"dwReturn",
          87,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c",
          232);
        v11 = (PVOID *)WPP_GLOBAL_Control;
      }
LABEL_18:
      if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 )
        WPP_SF_sDsd(
          (unsigned int)v11[2],
          a2,
          a3,
          (unsigned int)"Status",
          v8,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\legacy.c",
          104);
    }
  }
  if ( hMem[1] )
    LocalFree(hMem[1]);
  return v8;
}

```

## disassembly

```asm
0x180010d68  push    rbp
0x180010d6a  push    rbx
0x180010d6b  push    rsi
0x180010d6c  push    rdi
0x180010d6d  push    r12
0x180010d6f  push    r13
0x180010d71  push    r14
0x180010d73  push    r15
0x180010d75  lea     rbp, [rsp-1Fh]
0x180010d7a  sub     rsp, 0A8h
0x180010d81  xor     eax, eax
0x180010d83  mov     [rbp+57h+var_90], 11h
0x180010d8b  neg     ecx
0x180010d8d  mov     [rbp+57h+var_50], rax
0x180010d91  xorps   xmm0, xmm0
0x180010d94  mov     [rbp+57h+var_7C], eax
0x180010d97  sbb     r13d, r13d
0x180010d9a  mov     [rbp+57h+var_80], r8d
0x180010d9e  and     r13d, 4
0x180010da2  mov     [rbp+57h+var_78], rdx
0x180010da6  lea     rax, aHj1diq6kpux7vc; "Hj1diQ6kpUx7VC4m"
0x180010dad  mov     r12, r9
0x180010db0  mov     [rbp+57h+var_88], rax
0x180010db4  movups  [rbp+57h+var_60], xmm0
0x180010db8  mov     dword ptr [rbp+57h+var_60], 18h
0x180010dbf  movups  xmmword ptr [rbp+57h+hMem], xmm0
0x180010dc3  test    rdx, rdx
0x180010dc6  jz      loc_180010EDF
0x180010dcc  xor     esi, esi
0x180010dce  lea     rdi, WPP_GLOBAL_Control
0x180010dd5  lea     r15, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010ddc  lea     r14d, [rsi+0Ah]
0x180010de0  lea     rax, [rbp+57h+hMem]
0x180010de4  xor     r9d, r9d
0x180010de7  mov     [rsp+0E0h+var_A0], rax
0x180010dec  lea     r8, [rbp+57h+var_90]
0x180010df0  mov     [rsp+0E0h+var_A8], 0
0x180010df8  lea     rax, [rbp+57h+var_60]
0x180010dfc  mov     [rsp+0E0h+var_B0], 0
0x180010e05  lea     rcx, [rbp+57h+var_80]
0x180010e09  mov     dword ptr [rsp+0E0h+var_B8], r13d
0x180010e0e  xor     edx, edx
0x180010e10  mov     [rsp+0E0h+var_C0], rax
0x180010e15  call    cs:__imp_CryptUnprotectDataNoUI
0x180010e1c  nop     dword ptr [rax+rax+00h]
0x180010e21  test    eax, eax
0x180010e23  jz      short loc_180010E67
0x180010e25  cmp     dword ptr [rbp+57h+hMem], 4
0x180010e29  jnz     loc_180010F4B
0x180010e2f  mov     rax, [rbp+57h+hMem+8]
0x180010e33  xor     ebx, ebx
0x180010e35  mov     ecx, [rax]
0x180010e37  mov     [r12], ecx
0x180010e3b  mov     rcx, [rbp+57h+hMem+8]; hMem
0x180010e3f  test    rcx, rcx
0x180010e42  jz      short loc_180010E50
0x180010e44  call    cs:__imp_LocalFree
0x180010e4b  nop     dword ptr [rax+rax+00h]
0x180010e50  mov     eax, ebx
0x180010e52  add     rsp, 0A8h
0x180010e59  pop     r15
0x180010e5b  pop     r14
0x180010e5d  pop     r13
0x180010e5f  pop     r12
0x180010e61  pop     rdi
0x180010e62  pop     rsi
0x180010e63  pop     rbx
0x180010e64  pop     rbp
0x180010e65  retn
0x180010e67  call    cs:__imp_GetLastError
0x180010e6e  nop     dword ptr [rax+rax+00h]
0x180010e73  mov     ebx, eax
0x180010e75  mov     rcx, cs:WPP_GLOBAL_Control
0x180010e7c  cmp     rcx, rdi
0x180010e7f  jz      short loc_180010E87
0x180010e81  test    byte ptr [rcx+1Ch], 1
0x180010e85  jnz     short loc_180010EB5
0x180010e87  cmp     ebx, 6BBh
0x180010e8d  jnz     loc_180010F41
0x180010e93  cmp     esi, 5
0x180010e96  jnb     loc_180010F41
0x180010e9c  mov     ecx, r14d; dwMilliseconds
0x180010e9f  call    cs:__imp_Sleep
0x180010ea6  nop     dword ptr [rax+rax+00h]
0x180010eab  add     r14d, r14d
0x180010eae  inc     esi
0x180010eb0  jmp     loc_180010DE0
0x180010eb5  mov     rcx, [rcx+10h]
0x180010eb9  lea     r9, aDwsts; "dwSts"
0x180010ec0  mov     dword ptr [rsp+0E0h+var_B0], 215h
0x180010ec8  mov     [rsp+0E0h+var_B8], r15
0x180010ecd  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x180010ed1  call    WPP_SF_sDsd
0x180010ed6  mov     rcx, cs:WPP_GLOBAL_Control
0x180010edd  jmp     short loc_180010E87
0x180010edf  mov     ebx, 57h ; 'W'
0x180010ee4  mov     rcx, cs:WPP_GLOBAL_Control
0x180010eeb  lea     rdi, WPP_GLOBAL_Control
0x180010ef2  cmp     rcx, rdi
0x180010ef5  jz      loc_180010E3B
0x180010efb  test    byte ptr [rcx+1Ch], 1
0x180010eff  jnz     short loc_180010F70
0x180010f01  cmp     rcx, rdi
0x180010f04  jz      loc_180010E3B
0x180010f0a  test    byte ptr [rcx+1Ch], 1
0x180010f0e  jz      loc_180010E3B
0x180010f14  mov     rcx, [rcx+10h]
0x180010f18  lea     rax, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010f1f  mov     dword ptr [rsp+0E0h+var_B0], 0A68h
0x180010f27  lea     r9, aStatus; "Status"
0x180010f2e  mov     [rsp+0E0h+var_B8], rax
0x180010f33  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x180010f37  call    WPP_SF_sDsd
0x180010f3c  jmp     loc_180010E3B
0x180010f41  test    ebx, ebx
0x180010f43  jz      loc_180010E25
0x180010f49  jmp     short loc_180010F01
0x180010f4b  mov     ebx, 80090016h
0x180010f50  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010f57  mov     ecx, ebx
0x180010f59  lea     rdx, aStatus; "Status"
0x180010f60  mov     r9d, 0A6Fh
0x180010f66  call    DebugTraceError
0x180010f6b  jmp     loc_180010E3B
0x180010f70  mov     rcx, [rcx+10h]
0x180010f74  lea     r15, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010f7b  mov     dword ptr [rsp+0E0h+var_B0], 1E8h
0x180010f83  lea     r9, aDwreturn; "dwReturn"
0x180010f8a  mov     [rsp+0E0h+var_B8], r15
0x180010f8f  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x180010f93  call    WPP_SF_sDsd
0x180010f98  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f9f  jmp     loc_180010F01
```
