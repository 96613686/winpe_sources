# IkeRemoveImpersonateEntry

- ea: `0x1800f81f8`
- end: `0x1800f8513`
- name: `IkeRemoveImpersonateEntry`
- size: `795`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800be508`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x1800037c4`
- `0x180008388`
- `0x18001afe0`
- `0x1800488f0`
- `0x18004890c`
- `0x180050850`
- `0x18006e080`
- `0x1800f813c`
- `0x1800f81f8`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x1800f839b`
- `ntdll!RtlRemoveEntryHashTable` at `0x1800f839b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f84d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f84d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f823d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f823d`

## string_xrefs

- `0x1800f84dc`: `IkeRemoveImpersonateEntry`

## pseudocode

```c
__int64 __fastcall IkeRemoveImpersonateEntry(__int64 a1, __int64 a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 ImpersonateEntry; // r13
  __int64 v8; // r15
  unsigned int v9; // ecx
  char v10; // r14
  _UNKNOWN **v11; // rcx
  int v12; // ebx
  __int64 v13; // rsi
  __int64 v14; // rdi
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rax
  int v22; // r8d
  int v23; // r9d
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  _UNKNOWN **v27; // rcx
  int v28; // edi
  int v29; // esi
  __int64 v30; // r14
  __int64 TlsPeerAddr; // rbx
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // r9
  int TlsMmLuid; // eax
  __int64 v37; // rcx
  __int64 v38; // rax
  int v39; // r8d
  int v40; // r9d
  int v42; // [rsp+40h] [rbp-69h] BYREF
  int v43; // [rsp+44h] [rbp-65h] BYREF
  __int64 v44; // [rsp+48h] [rbp-61h] BYREF
  __int64 v45; // [rsp+50h] [rbp-59h] BYREF
  __int64 v46; // [rsp+58h] [rbp-51h] BYREF
  _BYTE v47[32]; // [rsp+60h] [rbp-49h] BYREF
  __int64 *v48; // [rsp+80h] [rbp-29h]
  __int64 v49; // [rsp+88h] [rbp-21h]
  _BYTE v50[16]; // [rsp+90h] [rbp-19h] BYREF
  __int64 *v51; // [rsp+A0h] [rbp-9h]
  __int64 v52; // [rsp+A8h] [rbp-1h]
  int *v53; // [rsp+B0h] [rbp+7h]
  __int64 v54; // [rsp+B8h] [rbp+Fh]
  int *v55; // [rsp+C0h] [rbp+17h]
  __int64 v56; // [rsp+C8h] [rbp+1Fh]

  v44 = 0;
  EnterCriticalSection(gIkeExtGlobals + 3);
  ImpersonateEntry = IkeFindImpersonateEntry(a1, a2, &v44);
  if ( !ImpersonateEntry )
  {
    v8 = v44;
    v9 = *(_DWORD *)(v44 + 368);
    if ( v9 <= 1 )
    {
      RtlRemoveEntryHashTable(&gIkeExtGlobals[57].LockCount, v44, 0);
      WfpRestructureHashtable(&gIkeExtGlobals[57].LockCount);
      v27 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v28 = *(_DWORD *)(v8 + 372);
        v29 = *(_DWORD *)(v8 + 368);
        v30 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        TlsPeerAddr = IkeGetTlsPeerAddr(&WPP_GLOBAL_Control);
        TlsMmLuid = IkeGetTlsMmLuid(v33, v32, v34, v35);
        WPP_SF_iSqDd(
          v30,
          13,
          (unsigned int)WPP_2dcdeb16648d3796f5f1a1f816de0bc8_Traceguids,
          TlsMmLuid,
          TlsPeerAddr,
          v8,
          v29,
          v28);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v45 = IkeGetTlsMmLuid(v27, v24, v25, v26);
        v48 = &v45;
        v49 = 8;
        v38 = IkeGetTlsPeerAddr(v37);
        tlgCreate1Sz_wchar_t(v50, v38);
        v46 = v8;
        v51 = &v46;
        v52 = 8;
        v43 = *(_DWORD *)(v8 + 368);
        v53 = &v43;
        v54 = 4;
        v42 = *(_DWORD *)(v8 + 372);
        v55 = &v42;
        v56 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_180173278,
          (unsigned int)byte_18016396D,
          v39,
          v40,
          7,
          (__int64)v47);
      }
      WfpMemFree(&v44);
    }
    else
    {
      v10 = v9 - 1;
      *(_DWORD *)(v44 + 368) = v9 - 1;
      v11 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v12 = *(_DWORD *)(v8 + 372);
        v13 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v14 = IkeGetTlsPeerAddr(&WPP_GLOBAL_Control);
        v19 = IkeGetTlsMmLuid(v16, v15, v17, v18);
        WPP_SF_iSqDd(v13, 12, (unsigned int)WPP_2dcdeb16648d3796f5f1a1f816de0bc8_Traceguids, v19, v14, v8, v10, v12);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v44 = IkeGetTlsMmLuid(v11, v4, v5, v6);
        v48 = &v44;
        v49 = 8;
        v21 = IkeGetTlsPeerAddr(v20);
        tlgCreate1Sz_wchar_t(v50, v21);
        v45 = v8;
        v51 = &v45;
        v52 = 8;
        v42 = *(_DWORD *)(v8 + 368);
        v53 = &v42;
        v54 = 4;
        v43 = *(_DWORD *)(v8 + 372);
        v55 = &v43;
        v56 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_180173278,
          (unsigned int)&word_180163A46,
          v22,
          v23,
          7,
          (__int64)v47);
      }
    }
  }
  LeaveCriticalSection(gIkeExtGlobals + 3);
  return IkeReturnError(ImpersonateEntry, "IkeRemoveImpersonateEntry");
}

```

## disassembly

```asm
0x1800f81f8  mov     [rsp-8+arg_10], rbx
0x1800f81fd  mov     [rsp-8+arg_18], rsi
0x1800f8202  push    rbp
0x1800f8203  push    rdi
0x1800f8204  push    r13
0x1800f8206  push    r14
0x1800f8208  push    r15
0x1800f820a  lea     rbp, [rsp-37h]
0x1800f820f  sub     rsp, 0E0h
0x1800f8216  mov     rax, cs:__security_cookie
0x1800f821d  xor     rax, rsp
0x1800f8220  mov     [rbp+57h+var_30], rax
0x1800f8224  mov     rbx, rcx
0x1800f8227  mov     [rbp+57h+var_B8], 0
0x1800f822f  mov     rcx, cs:gIkeExtGlobals
0x1800f8236  mov     rdi, rdx
0x1800f8239  add     rcx, 78h ; 'x'; lpCriticalSection
0x1800f823d  call    cs:__imp_EnterCriticalSection
0x1800f8243  lea     r8, [rbp+57h+var_B8]
0x1800f8247  mov     rdx, rdi
0x1800f824a  mov     rcx, rbx
0x1800f824d  call    IkeFindImpersonateEntry
0x1800f8252  mov     r13, rax
0x1800f8255  test    rax, rax
0x1800f8258  jnz     loc_1800F84CB
0x1800f825e  mov     r15, [rbp+57h+var_B8]
0x1800f8262  mov     ecx, [r15+170h]
0x1800f8269  cmp     ecx, 1
0x1800f826c  jbe     loc_1800F8387
0x1800f8272  lea     r14d, [rcx-1]
0x1800f8276  mov     [r15+170h], r14d
0x1800f827d  mov     rsi, cs:WPP_GLOBAL_Control
0x1800f8284  lea     rcx, WPP_GLOBAL_Control
0x1800f828b  cmp     rsi, rcx
0x1800f828e  jz      short loc_1800F82DD
0x1800f8290  cmp     byte ptr [rsi+19h], 4
0x1800f8294  jb      short loc_1800F82DD
0x1800f8296  test    byte ptr [rsi+1Ch], 10h
0x1800f829a  jz      short loc_1800F82DD
0x1800f829c  mov     ebx, [r15+174h]
0x1800f82a3  mov     rsi, [rsi+10h]
0x1800f82a7  call    IkeGetTlsPeerAddr
0x1800f82ac  mov     rdi, rax
0x1800f82af  call    IkeGetTlsMmLuid
0x1800f82b4  mov     [rsp+100h+var_C8], ebx
0x1800f82b8  lea     edx, [r13+0Ch]
0x1800f82bc  mov     [rsp+100h+var_D0], r14d
0x1800f82c1  lea     r8, WPP_2dcdeb16648d3796f5f1a1f816de0bc8_Traceguids
0x1800f82c8  mov     [rsp+100h+var_D8], r15
0x1800f82cd  mov     r9, rax
0x1800f82d0  mov     rcx, rsi
0x1800f82d3  mov     [rsp+100h+var_E0], rdi
0x1800f82d8  call    WPP_SF_iSqDd
0x1800f82dd  mov     eax, cs:dword_180173278
0x1800f82e3  cmp     eax, 4
0x1800f82e6  jbe     loc_1800F84CB
0x1800f82ec  call    IkeGetTlsMmLuid
0x1800f82f1  mov     [rbp+57h+var_B8], rax
0x1800f82f5  lea     rax, [rbp+57h+var_B8]
0x1800f82f9  mov     [rbp+57h+var_80], rax
0x1800f82fd  mov     [rbp+57h+var_78], 8
0x1800f8305  call    IkeGetTlsPeerAddr
0x1800f830a  mov     rdx, rax
0x1800f830d  lea     rcx, [rbp+57h+var_70]
0x1800f8311  call    _tlgCreate1Sz_wchar_t
0x1800f8316  lea     rax, [rbp+57h+var_B0]
0x1800f831a  mov     [rbp+57h+var_B0], r15
0x1800f831e  mov     [rbp+57h+var_60], rax
0x1800f8322  lea     rdx, word_180163A46
0x1800f8329  mov     [rbp+57h+var_58], 8
0x1800f8331  lea     rcx, dword_180173278
0x1800f8338  mov     eax, [r15+170h]
0x1800f833f  mov     [rbp+57h+var_C0], eax
0x1800f8342  lea     rax, [rbp+57h+var_C0]
0x1800f8346  mov     [rbp+57h+var_50], rax
0x1800f834a  mov     [rbp+57h+var_48], 4
0x1800f8352  mov     eax, [r15+174h]
0x1800f8359  mov     [rbp+57h+var_BC], eax
0x1800f835c  lea     rax, [rbp+57h+var_BC]
0x1800f8360  mov     [rbp+57h+var_40], rax
0x1800f8364  lea     rax, [rbp+57h+var_A0]
0x1800f8368  mov     [rsp+100h+var_D8], rax
0x1800f836d  mov     dword ptr [rsp+100h+var_E0], 7
0x1800f8375  mov     [rbp+57h+var_38], 4
0x1800f837d  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x1800f8382  jmp     loc_1800F84CB
0x1800f8387  mov     rcx, cs:gIkeExtGlobals
0x1800f838e  xor     r8d, r8d
0x1800f8391  add     rcx, 8F0h
0x1800f8398  mov     rdx, r15
0x1800f839b  call    cs:__imp_RtlRemoveEntryHashTable
0x1800f83a1  mov     rcx, cs:gIkeExtGlobals
0x1800f83a8  add     rcx, 8F0h
0x1800f83af  call    WfpRestructureHashtable
0x1800f83b4  mov     r14, cs:WPP_GLOBAL_Control
0x1800f83bb  lea     rcx, WPP_GLOBAL_Control
0x1800f83c2  cmp     r14, rcx
0x1800f83c5  jz      short loc_1800F841D
0x1800f83c7  cmp     byte ptr [r14+19h], 4
0x1800f83cc  jb      short loc_1800F841D
0x1800f83ce  test    byte ptr [r14+1Ch], 10h
0x1800f83d3  jz      short loc_1800F841D
0x1800f83d5  mov     edi, [r15+174h]
0x1800f83dc  mov     esi, [r15+170h]
0x1800f83e3  mov     r14, [r14+10h]
0x1800f83e7  call    IkeGetTlsPeerAddr
0x1800f83ec  mov     rbx, rax
0x1800f83ef  call    IkeGetTlsMmLuid
0x1800f83f4  mov     [rsp+100h+var_C8], edi
0x1800f83f8  lea     r8, WPP_2dcdeb16648d3796f5f1a1f816de0bc8_Traceguids
0x1800f83ff  mov     [rsp+100h+var_D0], esi
0x1800f8403  mov     r9, rax
0x1800f8406  mov     [rsp+100h+var_D8], r15
0x1800f840b  mov     edx, 0Dh
0x1800f8410  mov     rcx, r14
0x1800f8413  mov     [rsp+100h+var_E0], rbx
0x1800f8418  call    WPP_SF_iSqDd
0x1800f841d  mov     eax, cs:dword_180173278
0x1800f8423  cmp     eax, 4
0x1800f8426  jbe     loc_1800F84C2
0x1800f842c  call    IkeGetTlsMmLuid
0x1800f8431  mov     [rbp+57h+var_B0], rax
0x1800f8435  lea     rax, [rbp+57h+var_B0]
0x1800f8439  mov     [rbp+57h+var_80], rax
0x1800f843d  mov     [rbp+57h+var_78], 8
0x1800f8445  call    IkeGetTlsPeerAddr
0x1800f844a  mov     rdx, rax
0x1800f844d  lea     rcx, [rbp+57h+var_70]
0x1800f8451  call    _tlgCreate1Sz_wchar_t
0x1800f8456  lea     rax, [rbp+57h+var_A8]
0x1800f845a  mov     [rbp+57h+var_A8], r15
0x1800f845e  mov     [rbp+57h+var_60], rax
0x1800f8462  lea     rdx, byte_18016396D
0x1800f8469  mov     [rbp+57h+var_58], 8
0x1800f8471  lea     rcx, dword_180173278
0x1800f8478  mov     eax, [r15+170h]
0x1800f847f  mov     [rbp+57h+var_BC], eax
0x1800f8482  lea     rax, [rbp+57h+var_BC]
0x1800f8486  mov     [rbp+57h+var_50], rax
0x1800f848a  mov     [rbp+57h+var_48], 4
0x1800f8492  mov     eax, [r15+174h]
0x1800f8499  mov     [rbp+57h+var_C0], eax
0x1800f849c  lea     rax, [rbp+57h+var_C0]
0x1800f84a0  mov     [rbp+57h+var_40], rax
0x1800f84a4  lea     rax, [rbp+57h+var_A0]
0x1800f84a8  mov     [rsp+100h+var_D8], rax
0x1800f84ad  mov     dword ptr [rsp+100h+var_E0], 7
0x1800f84b5  mov     [rbp+57h+var_38], 4
0x1800f84bd  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x1800f84c2  lea     rcx, [rbp+57h+var_B8]
0x1800f84c6  call    WfpMemFree
0x1800f84cb  mov     rcx, cs:gIkeExtGlobals
0x1800f84d2  add     rcx, 78h ; 'x'; lpCriticalSection
0x1800f84d6  call    cs:__imp_LeaveCriticalSection
0x1800f84dc  lea     rdx, aIkeremoveimper; "IkeRemoveImpersonateEntry"
0x1800f84e3  mov     rcx, r13
0x1800f84e6  call    IkeReturnError
0x1800f84eb  mov     rcx, [rbp+57h+var_30]
0x1800f84ef  xor     rcx, rsp; StackCookie
0x1800f84f2  call    __security_check_cookie
0x1800f84f7  lea     r11, [rsp+100h+var_20]
0x1800f84ff  mov     rbx, [r11+40h]
0x1800f8503  mov     rsi, [r11+48h]
0x1800f8507  mov     rsp, r11
0x1800f850a  pop     r15
0x1800f850c  pop     r14
0x1800f850e  pop     r13
0x1800f8510  pop     rdi
0x1800f8511  pop     rbp
0x1800f8512  retn
```
