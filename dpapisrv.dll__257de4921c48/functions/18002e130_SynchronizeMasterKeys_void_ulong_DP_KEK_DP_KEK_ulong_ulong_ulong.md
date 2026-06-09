# SynchronizeMasterKeys(void *,ulong,DP_KEK *,DP_KEK *,ulong,ulong *,ulong *)

- ea: `0x18002e130`
- end: `0x18002e308`
- name: `?SynchronizeMasterKeys@@YAKPEAXKPEAUDP_KEK@@1KPEAK2@Z`
- size: `472`
- prototype: `__int64 __fastcall(_DWORD *, unsigned int, struct DP_KEK *, struct DP_KEK *, unsigned int, unsigned int *, unsigned int *)`
- caller_count: `7`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008af0`
- `0x18002a03c`
- `0x18002ae48`
- `0x18002b0ec`
- `0x18002c0a0`
- `0x18002ca70`
- `0x18002d7e0`

## callees

- `0x1800065b0`
- `0x180007f10`
- `0x1800090e8`
- `0x180013f2c`
- `0x18002e130`
- `0x18002e310`
- `0x18002efa0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e2b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e2c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e2b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e2c9`

## string_xrefs

- `0x18002e1c8`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18002e261`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`

## pseudocode

```c
__int64 __fastcall SynchronizeMasterKeys(
        _DWORD *a1,
        unsigned int a2,
        struct DP_KEK *a3,
        struct DP_KEK *a4,
        unsigned int a5,
        unsigned int *a6,
        unsigned int *a7)
{
  unsigned int v7; // r15d
  unsigned int v8; // r14d
  unsigned int v10; // eax
  void **v11; // rsi
  unsigned int v12; // ebx
  __int64 i; // rdi
  void *v14; // rdx
  unsigned int v15; // eax
  HLOCAL v16; // rdi
  unsigned __int16 *v17; // rdx
  unsigned int v19; // [rsp+50h] [rbp-20h] BYREF
  unsigned int v20; // [rsp+54h] [rbp-1Ch] BYREF
  unsigned int v21; // [rsp+58h] [rbp-18h] BYREF
  HLOCAL hMem[2]; // [rsp+60h] [rbp-10h] BYREF

  v7 = 0;
  hMem[0] = 0;
  v8 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 28, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids, a5);
  v10 = CPSGetSidHistory(a1, (void ***)hMem, &v19);
  v11 = (void **)hMem[0];
  v12 = v10;
  if ( v10 )
  {
    DebugTraceError(v10, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 1498);
  }
  else
  {
    for ( i = 0; (unsigned int)i < v19; i = (unsigned int)(i + 1) )
    {
      if ( (_DWORD)i )
        v14 = v11[i];
      else
        v14 = 0;
      v12 = SynchronizeSidMasterKeys(a1, v14, a2, i != 0, a3, a4, a5, &v20, &v21);
      if ( v12 - 2 > 1 && v12 && v12 != 1018 )
      {
        DebugTraceError(v12, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 1521);
        hMem[0] = 0;
        v21 = 0;
        v15 = CPSGetUserName(a1, (unsigned __int16 **)hMem, &v21);
        v16 = hMem[0];
        v17 = 0;
        if ( !v15 )
          v17 = (unsigned __int16 *)hMem[0];
        WriteCredKeyEventLog(a4, v17, *v11);
        if ( v16 )
          LocalFree(v16);
        break;
      }
      v7 += v20;
      v12 = 0;
      v8 += v21;
    }
  }
  if ( v11 )
    LocalFree(v11);
  if ( a6 )
    *a6 = v7;
  if ( a7 )
    *a7 = v8;
  return v12;
}

```

## disassembly

```asm
0x18002e130  mov     rax, rsp
0x18002e133  mov     [rax+8], rbx
0x18002e137  mov     [rax+20h], r9
0x18002e13b  mov     [rax+18h], r8
0x18002e13f  mov     [rax+10h], edx
0x18002e142  push    rbp
0x18002e143  push    rsi
0x18002e144  push    rdi
0x18002e145  push    r12
0x18002e147  push    r13
0x18002e149  push    r14
0x18002e14b  push    r15
0x18002e14d  mov     rbp, rsp
0x18002e150  sub     rsp, 70h
0x18002e154  xor     r15d, r15d
0x18002e157  mov     [rbp+hMem], 0
0x18002e15f  xor     r14d, r14d
0x18002e162  mov     [rbp+var_20], 0
0x18002e169  mov     [rbp+var_1C], r14d
0x18002e16d  mov     r12, rcx
0x18002e170  mov     [rbp+var_18], r14d
0x18002e174  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e17b  lea     rax, WPP_GLOBAL_Control
0x18002e182  mov     r13d, [rbp+arg_20]
0x18002e186  cmp     rcx, rax
0x18002e189  jz      short loc_18002E1A8
0x18002e18b  test    byte ptr [rcx+1Ch], 4
0x18002e18f  jz      short loc_18002E1A8
0x18002e191  mov     rcx, [rcx+10h]
0x18002e195  lea     edx, [r15+1Ch]
0x18002e199  mov     r9d, r13d
0x18002e19c  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x18002e1a3  call    WPP_SF_d
0x18002e1a8  lea     r8, [rbp+var_20]; unsigned int *
0x18002e1ac  mov     rcx, r12; void *
0x18002e1af  lea     rdx, [rbp+hMem]; void ***
0x18002e1b3  call    ?CPSGetSidHistory@@YAKPEAXPEAPEAPEAXPEAK@Z; CPSGetSidHistory(void *,void * * *,ulong *)
0x18002e1b8  mov     rsi, [rbp+hMem]
0x18002e1bc  mov     ebx, eax
0x18002e1be  test    eax, eax
0x18002e1c0  jz      short loc_18002E1E2
0x18002e1c2  mov     r9d, 5DAh
0x18002e1c8  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002e1cf  lea     rdx, aDwlasterror; "dwLastError"
0x18002e1d6  mov     ecx, eax
0x18002e1d8  call    DebugTraceError
0x18002e1dd  jmp     loc_18002E2C1
0x18002e1e2  xor     edi, edi
0x18002e1e4  cmp     edi, [rbp+var_20]
0x18002e1e7  jnb     loc_18002E2C1
0x18002e1ed  xor     r9d, r9d
0x18002e1f0  test    edi, edi
0x18002e1f2  setnz   r9b; int
0x18002e1f6  test    edi, edi
0x18002e1f8  jz      short loc_18002E200
0x18002e1fa  mov     rdx, [rsi+rdi*8]
0x18002e1fe  jmp     short loc_18002E202
0x18002e200  xor     edx, edx; void *
0x18002e202  mov     r8d, [rbp+arg_8]; unsigned int
0x18002e206  lea     rax, [rbp+var_18]
0x18002e20a  mov     [rsp+70h+var_30], rax; unsigned int *
0x18002e20f  mov     rcx, r12; void *
0x18002e212  lea     rax, [rbp+var_1C]
0x18002e216  mov     [rsp+70h+var_38], rax; unsigned int *
0x18002e21b  mov     rax, [rbp+arg_18]
0x18002e21f  mov     [rsp+70h+var_40], r13d; unsigned int
0x18002e224  mov     [rsp+70h+var_48], rax; struct DP_KEK *
0x18002e229  mov     rax, [rbp+arg_10]
0x18002e22d  mov     [rsp+70h+var_50], rax; struct DP_KEK *
0x18002e232  call    ?SynchronizeSidMasterKeys@@YAKPEAX0KHPEAUDP_KEK@@1KPEAK2@Z; SynchronizeSidMasterKeys(void *,void *,ulong,int,DP_KEK *,DP_KEK *,ulong,ulong *,ulong *)
0x18002e237  mov     ebx, eax
0x18002e239  add     eax, 0FFFFFFFEh
0x18002e23c  cmp     eax, 1
0x18002e23f  jbe     short loc_18002E24D
0x18002e241  test    ebx, ebx
0x18002e243  jz      short loc_18002E24D
0x18002e245  cmp     ebx, 3FAh
0x18002e24b  jnz     short loc_18002E25B
0x18002e24d  add     r15d, [rbp+var_1C]
0x18002e251  xor     ebx, ebx
0x18002e253  add     r14d, [rbp+var_18]
0x18002e257  inc     edi
0x18002e259  jmp     short loc_18002E1E4
0x18002e25b  mov     r9d, 5F1h
0x18002e261  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002e268  lea     rdx, aDwlasterror; "dwLastError"
0x18002e26f  mov     ecx, ebx
0x18002e271  call    DebugTraceError
0x18002e276  lea     r8, [rbp+var_18]; unsigned int *
0x18002e27a  mov     [rbp+hMem], 0
0x18002e282  lea     rdx, [rbp+hMem]; unsigned __int16 **
0x18002e286  mov     [rbp+var_18], 0
0x18002e28d  mov     rcx, r12; void *
0x18002e290  call    ?CPSGetUserName@@YAKPEAXPEAPEAGPEAK@Z; CPSGetUserName(void *,ushort * *,ulong *)
0x18002e295  mov     rdi, [rbp+hMem]
0x18002e299  xor     edx, edx
0x18002e29b  mov     r8, [rsi]; void *
0x18002e29e  test    eax, eax
0x18002e2a0  mov     rcx, [rbp+arg_18]; struct DP_KEK *
0x18002e2a4  cmovz   rdx, rdi; unsigned __int16 *
0x18002e2a8  call    ?WriteCredKeyEventLog@@YAXPEAUDP_KEK@@PEAGPEAX@Z; WriteCredKeyEventLog(DP_KEK *,ushort *,void *)
0x18002e2ad  test    rdi, rdi
0x18002e2b0  jz      short loc_18002E2C1
0x18002e2b2  mov     rcx, rdi; hMem
0x18002e2b5  call    cs:__imp_LocalFree
0x18002e2bc  nop     dword ptr [rax+rax+00h]
0x18002e2c1  test    rsi, rsi
0x18002e2c4  jz      short loc_18002E2D5
0x18002e2c6  mov     rcx, rsi; hMem
0x18002e2c9  call    cs:__imp_LocalFree
0x18002e2d0  nop     dword ptr [rax+rax+00h]
0x18002e2d5  mov     rax, [rbp+arg_28]
0x18002e2d9  test    rax, rax
0x18002e2dc  jz      short loc_18002E2E1
0x18002e2de  mov     [rax], r15d
0x18002e2e1  mov     rax, [rbp+arg_30]
0x18002e2e5  test    rax, rax
0x18002e2e8  jz      short loc_18002E2ED
0x18002e2ea  mov     [rax], r14d
0x18002e2ed  mov     eax, ebx
0x18002e2ef  mov     rbx, [rsp+70h+arg_0]
0x18002e2f7  add     rsp, 70h
0x18002e2fb  pop     r15
0x18002e2fd  pop     r14
0x18002e2ff  pop     r13
0x18002e301  pop     r12
0x18002e303  pop     rdi
0x18002e304  pop     rsi
0x18002e305  pop     rbp
0x18002e306  retn
```
