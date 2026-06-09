# CFveApiBase::RefreshTrustedWimDataForBootEntry(_GUID const *,int,ushort,_FVE_DATUM_VALIDATION_ENTRY *,ushort *)

- ea: `0x18009d1d0`
- end: `0x18009d84f`
- name: `?RefreshTrustedWimDataForBootEntry@CFveApiBase@@QEAAJPEBU_GUID@@HGPEAU_FVE_DATUM_VALIDATION_ENTRY@@PEAG@Z`
- size: `1663`
- prototype: `__int64 __fastcall(CFveApiBase *__hidden this, const struct _GUID *, int, unsigned __int16, struct _FVE_DATUM_VALIDATION_ENTRY *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x18009eca8`

## callees

- `0x180008d70`
- `0x1800090c0`
- `0x180018b10`
- `0x18001b260`
- `0x18001d0a0`
- `0x180044da4`
- `0x1800476f0`
- `0x180071210`
- `0x18009d1d0`
- `0x18009e740`
- `0x18011efc2`
- `0x18011f010`

## import_xrefs

- `bcd!BcdCloseStore` at `0x18009d2b8`
- `bcd!BcdCloseStore` at `0x18009d2b8`
- `bcd!BcdOpenSystemStore` at `0x18009d6a2`
- `bcd!BcdOpenSystemStore` at `0x18009d6a2`

## pseudocode

```c
__int64 __fastcall CFveApiBase::RefreshTrustedWimDataForBootEntry(
        CFveApiBase *this,
        __int64 a2,
        int a3,
        __int64 a4,
        struct _FVE_DATUM_VALIDATION_ENTRY *a5,
        unsigned __int16 *a6)
{
  __int64 v6; // rdi
  __int64 v8; // r13
  CFveApiBase *v9; // r10
  PVOID *v10; // rcx
  unsigned int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // r9
  int First; // eax
  int v16; // eax
  __int64 v17; // rdx
  int DataSegment; // eax
  int v19; // eax
  __int64 v20; // rsi
  int v21; // eax
  unsigned __int16 v22; // r14
  int v23; // eax
  unsigned __int16 v24; // di
  __int64 v25; // rbx
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // r9
  unsigned __int16 v29; // di
  __int64 v30; // rcx
  unsigned __int16 v31; // cx
  __int64 v32; // rcx
  int v33; // eax
  int v34; // r13d
  __int64 v35; // rax
  __int64 v36; // rcx
  __int64 v37; // [rsp+50h] [rbp-49h] BYREF
  unsigned __int16 v38; // [rsp+58h] [rbp-41h] BYREF
  __int64 v39; // [rsp+60h] [rbp-39h] BYREF
  CFveApiBase *v40; // [rsp+68h] [rbp-31h]
  const struct _GUID *v41; // [rsp+70h] [rbp-29h]
  void *v42; // [rsp+78h] [rbp-21h] BYREF
  _OWORD Buf2[2]; // [rsp+80h] [rbp-19h] BYREF
  __int64 v44; // [rsp+A0h] [rbp+7h]

  v6 = 0;
  v38 = 0;
  v44 = 0;
  v42 = 0;
  v8 = a2;
  v41 = (const struct _GUID *)a2;
  v9 = this;
  v40 = this;
  v37 = 0;
  v39 = 0;
  memset(Buf2, 0, sizeof(Buf2));
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 138, &WPP_1559182127783aab3882fe828952d989_Traceguids);
    v10 = (PVOID *)WPP_GLOBAL_Control;
    v9 = v40;
  }
  if ( a3 )
  {
    First = FveDatasetGetFirst(*((_QWORD *)v9 + 146), 17, 7, &v37);
    v16 = FromNtStatus(First);
    v11 = v16;
    if ( v16 < 0 )
    {
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v17 = 140;
LABEL_22:
        WPP_SF_d(v10[2], v17, &WPP_1559182127783aab3882fe828952d989_Traceguids, (unsigned int)v16);
LABEL_23:
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
LABEL_24:
      v6 = v37;
      goto LABEL_10;
    }
    v6 = v37;
    DataSegment = FveDatumGetDataSegment(v37, &v39, &v38);
    v19 = FromNtStatus(DataSegment);
    v11 = v19;
    if ( v19 >= 0 )
    {
      v20 = v39;
      if ( v39 )
      {
        v22 = v38 / 0x28u;
        if ( v38 / 0x28u > 0x179 )
        {
          v11 = -2147024883;
          v10 = (PVOID *)WPP_GLOBAL_Control;
          a2 = (__int64)&WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_DDD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              143,
              &WPP_1559182127783aab3882fe828952d989_Traceguids,
              v22,
              377,
              -2147024883);
            goto LABEL_9;
          }
          goto LABEL_10;
        }
        v23 = FveDatumValidationInfoDataEntry(0, v8, 16, Buf2);
        v21 = FromNtStatus(v23);
        v11 = v21;
        if ( v21 >= 0 )
        {
          v24 = 0;
          if ( v22 )
          {
            while ( 1 )
            {
              v25 = 5LL * v24;
              if ( *(_WORD *)(v20 + 40LL * v24) == 4
                && !memcmp_0((const void *)(v20 + 8 + 40LL * v24), (char *)Buf2 + 8, 0x20u) )
              {
                break;
              }
              if ( *a6 >= 0x179u )
              {
                v11 = -2147024883;
                v10 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  v27 = 151;
                  goto LABEL_83;
                }
                goto LABEL_85;
              }
              ++v24;
              v26 = 5LL * *a6;
              *(_OWORD *)((char *)a5 + 8 * v26) = *(_OWORD *)(v20 + 8 * v25);
              *(_OWORD *)((char *)a5 + 8 * v26 + 16) = *(_OWORD *)(v20 + 8 * v25 + 16);
              *((_QWORD *)a5 + v26 + 4) = *(_QWORD *)(v20 + 8 * v25 + 32);
              ++*a6;
              if ( v24 >= v22 )
                goto LABEL_47;
            }
            if ( *a6 >= 0x179u )
            {
              v16 = -2147024883;
              v11 = -2147024883;
              v10 = (PVOID *)WPP_GLOBAL_Control;
              a2 = (__int64)&WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v17 = 145;
                goto LABEL_22;
              }
              goto LABEL_24;
            }
            v29 = v24 + 1;
            v30 = 5LL * *a6;
            *(_OWORD *)((char *)a5 + 8 * v30) = *(_OWORD *)(v20 + 8 * v25);
            *(_OWORD *)((char *)a5 + 8 * v30 + 16) = *(_OWORD *)(v20 + 8 * v25 + 16);
            *((_QWORD *)a5 + v30 + 4) = *(_QWORD *)(v20 + 8 * v25 + 32);
            v31 = ++*a6;
            if ( v29 < v22 )
            {
              while ( 1 )
              {
                a2 = 5LL * v29;
                if ( *(_WORD *)(v20 + 40LL * v29) != 3 )
                {
LABEL_64:
                  while ( v29 < v22 && *(_WORD *)(v20 + 40LL * v29) == 2 )
                    ++v29;
                  goto LABEL_65;
                }
                if ( v31 >= 0x179u )
                  break;
                ++v29;
                v32 = 5LL * v31;
                *(_OWORD *)((char *)a5 + 8 * v32) = *(_OWORD *)(v20 + 8 * a2);
                *(_OWORD *)((char *)a5 + 8 * v32 + 16) = *(_OWORD *)(v20 + 8 * a2 + 16);
                *((_QWORD *)a5 + v32 + 4) = *(_QWORD *)(v20 + 8 * a2 + 32);
                v31 = ++*a6;
                if ( v29 >= v22 )
                  goto LABEL_64;
              }
              v16 = -2147024883;
              v11 = -2147024883;
              v10 = (PVOID *)WPP_GLOBAL_Control;
              a2 = (__int64)&WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v17 = 146;
                goto LABEL_22;
              }
              goto LABEL_24;
            }
LABEL_65:
            v33 = BcdOpenSystemStore(&v42, a2);
            v16 = FromNtStatus(v33);
            v11 = v16;
            if ( v16 < 0 )
            {
              v10 = (PVOID *)WPP_GLOBAL_Control;
              a2 = (__int64)&WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v17 = 147;
                goto LABEL_22;
              }
              goto LABEL_24;
            }
            v34 = *a6;
            v16 = CFveApiBase::StoreValidationDataForAppEx(v40, v42, v41, 4u, 0x179u, a5, a6, 0, 0);
            v11 = v16;
            if ( v16 < 0 )
            {
              v10 = (PVOID *)WPP_GLOBAL_Control;
              a2 = (__int64)&WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v17 = 148;
                goto LABEL_22;
              }
              goto LABEL_24;
            }
            v10 = (PVOID *)WPP_GLOBAL_Control;
            a2 = (__int64)&WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                149,
                &WPP_1559182127783aab3882fe828952d989_Traceguids,
                (unsigned int)*a6 - v34);
              v10 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v29 >= v22 )
              goto LABEL_24;
            while ( *a6 < 0x179u )
            {
              v35 = v29++;
              a2 = 5 * v35;
              v36 = 5LL * *a6;
              *(_OWORD *)((char *)a5 + 8 * v36) = *(_OWORD *)(v20 + 40 * v35);
              *(_OWORD *)((char *)a5 + 8 * v36 + 16) = *(_OWORD *)(v20 + 40 * v35 + 16);
              *((_QWORD *)a5 + v36 + 4) = *(_QWORD *)(v20 + 40 * v35 + 32);
              ++*a6;
              if ( v29 >= v22 )
                goto LABEL_23;
            }
            v11 = -2147024883;
            v10 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v27 = 150;
LABEL_83:
              v28 = 2147942413LL;
              goto LABEL_84;
            }
          }
          else
          {
LABEL_47:
            v11 = -2147023728;
            v10 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v27 = 152;
              v28 = 2147943568LL;
LABEL_84:
              WPP_SF_d(v10[2], v27, &WPP_1559182127783aab3882fe828952d989_Traceguids, v28);
              v10 = (PVOID *)WPP_GLOBAL_Control;
            }
          }
LABEL_85:
          v6 = v37;
          goto LABEL_10;
        }
        v10 = (PVOID *)WPP_GLOBAL_Control;
        a2 = (__int64)&WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_10;
        v12 = 144;
      }
      else
      {
        v21 = -2147024883;
        v11 = -2147024883;
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_10;
        v12 = 142;
      }
      v13 = (unsigned int)v21;
      goto LABEL_8;
    }
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v12 = 141;
      v13 = (unsigned int)v19;
      goto LABEL_8;
    }
  }
  else
  {
    v11 = -2147024809;
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 2) != 0 )
    {
      v12 = 139;
      v13 = 2147942487LL;
LABEL_8:
      WPP_SF_d(v10[2], v12, &WPP_1559182127783aab3882fe828952d989_Traceguids, v13);
LABEL_9:
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
LABEL_10:
  if ( v42 )
  {
    BcdCloseStore(v42, a2);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 )
  {
    FveDatumFree(v6);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x20) != 0 )
    WPP_SF_d(v10[2], 153, &WPP_1559182127783aab3882fe828952d989_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x18009d1d0  mov     [rsp-8+arg_10], rbx
0x18009d1d5  push    rbp
0x18009d1d6  push    rsi
0x18009d1d7  push    rdi
0x18009d1d8  push    r12
0x18009d1da  push    r13
0x18009d1dc  push    r14
0x18009d1de  push    r15
0x18009d1e0  lea     rbp, [rsp-17h]
0x18009d1e5  sub     rsp, 0B0h
0x18009d1ec  mov     rax, cs:__security_cookie
0x18009d1f3  xor     rax, rsp
0x18009d1f6  mov     [rbp+47h+var_38], rax
0x18009d1fa  mov     r12, [rbp+47h+arg_20]
0x18009d1fe  xor     edi, edi
0x18009d200  mov     r15, [rbp+47h+arg_28]
0x18009d204  xor     eax, eax
0x18009d206  xorps   xmm0, xmm0
0x18009d209  mov     [rbp+47h+var_88], ax
0x18009d20d  mov     [rbp+47h+var_40], rax
0x18009d211  mov     ebx, r8d
0x18009d214  mov     [rbp+47h+var_68], rax
0x18009d218  mov     r13, rdx
0x18009d21b  mov     [rbp+47h+var_70], rdx
0x18009d21f  mov     r10, rcx
0x18009d222  mov     [rbp+47h+var_78], rcx
0x18009d226  mov     [rbp+47h+var_90], rdi
0x18009d22a  mov     [rbp+47h+var_80], rdi
0x18009d22e  movups  [rbp+47h+Buf2], xmm0
0x18009d232  movups  [rbp+47h+var_50], xmm0
0x18009d236  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d23d  lea     r14, WPP_GLOBAL_Control
0x18009d244  lea     rsi, WPP_1559182127783aab3882fe828952d989_Traceguids
0x18009d24b  cmp     rcx, r14
0x18009d24e  jz      short loc_18009D272
0x18009d250  test    byte ptr [rcx+1Ch], 20h
0x18009d254  jz      short loc_18009D272
0x18009d256  mov     rcx, [rcx+10h]
0x18009d25a  mov     edx, 8Ah
0x18009d25f  mov     r8, rsi
0x18009d262  call    WPP_SF_
0x18009d267  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d26e  mov     r10, [rbp+47h+var_78]
0x18009d272  test    ebx, ebx
0x18009d274  jnz     loc_18009D32C
0x18009d27a  mov     ebx, 80070057h
0x18009d27f  cmp     rcx, r14
0x18009d282  jz      short loc_18009D2A5
0x18009d284  test    byte ptr [rcx+1Ch], 2
0x18009d288  jz      short loc_18009D2A5
0x18009d28a  mov     edx, 8Bh
0x18009d28f  mov     r9d, ebx
0x18009d292  mov     r8, rsi
0x18009d295  mov     rcx, [rcx+10h]
0x18009d299  call    WPP_SF_d
0x18009d29e  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d2a5  lea     rsi, WPP_GLOBAL_Control
0x18009d2ac  mov     rax, [rbp+47h+var_68]
0x18009d2b0  test    rax, rax
0x18009d2b3  jz      short loc_18009D2CB
0x18009d2b5  mov     rcx, rax
0x18009d2b8  call    cs:__imp_BcdCloseStore
0x18009d2bf  nop     dword ptr [rax+rax+00h]
0x18009d2c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d2cb  test    rdi, rdi
0x18009d2ce  jz      short loc_18009D2DF
0x18009d2d0  mov     rcx, rdi
0x18009d2d3  call    FveDatumFree
0x18009d2d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d2df  cmp     rcx, rsi
0x18009d2e2  jz      short loc_18009D302
0x18009d2e4  test    byte ptr [rcx+1Ch], 20h
0x18009d2e8  jz      short loc_18009D302
0x18009d2ea  mov     rcx, [rcx+10h]
0x18009d2ee  lea     r8, WPP_1559182127783aab3882fe828952d989_Traceguids
0x18009d2f5  mov     edx, 99h
0x18009d2fa  mov     r9d, ebx
0x18009d2fd  call    WPP_SF_d
0x18009d302  mov     eax, ebx
0x18009d304  mov     rcx, [rbp+47h+var_38]
0x18009d308  xor     rcx, rsp; StackCookie
0x18009d30b  call    __security_check_cookie
0x18009d310  mov     rbx, [rsp+0E0h+arg_10]
0x18009d318  add     rsp, 0B0h
0x18009d31f  pop     r15
0x18009d321  pop     r14
0x18009d323  pop     r13
0x18009d325  pop     r12
0x18009d327  pop     rdi
0x18009d328  pop     rsi
0x18009d329  pop     rbp
0x18009d32a  retn
0x18009d32c  mov     rcx, [r10+490h]
0x18009d333  lea     r9, [rbp+47h+var_90]
0x18009d337  mov     edx, 11h
0x18009d33c  lea     r8d, [rdx-0Ah]
0x18009d340  call    FveDatasetGetFirst
0x18009d345  mov     ecx, eax; int
0x18009d347  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009d34c  mov     ebx, eax
0x18009d34e  test    eax, eax
0x18009d350  jns     short loc_18009D388
0x18009d352  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d359  cmp     rcx, r14
0x18009d35c  jz      short loc_18009D37F
0x18009d35e  test    byte ptr [rcx+1Ch], 2
0x18009d362  jz      short loc_18009D37F
0x18009d364  mov     edx, 8Ch
0x18009d369  mov     r8, rsi
0x18009d36c  mov     rcx, [rcx+10h]
0x18009d370  mov     r9d, eax
0x18009d373  call    WPP_SF_d
0x18009d378  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d37f  mov     rdi, [rbp+47h+var_90]
0x18009d383  jmp     loc_18009D2A5
0x18009d388  mov     rdi, [rbp+47h+var_90]
0x18009d38c  lea     r8, [rbp+47h+var_88]
0x18009d390  mov     rcx, rdi
0x18009d393  lea     rdx, [rbp+47h+var_80]
0x18009d397  call    FveDatumGetDataSegment
0x18009d39c  mov     ecx, eax; int
0x18009d39e  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009d3a3  mov     ebx, eax
0x18009d3a5  test    eax, eax
0x18009d3a7  jns     short loc_18009D3D0
0x18009d3a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d3b0  cmp     rcx, r14
0x18009d3b3  jz      loc_18009D2A5
0x18009d3b9  test    byte ptr [rcx+1Ch], 2
0x18009d3bd  jz      loc_18009D2A5
0x18009d3c3  mov     edx, 8Dh
0x18009d3c8  mov     r9d, eax
0x18009d3cb  jmp     loc_18009D292
0x18009d3d0  mov     rsi, [rbp+47h+var_80]
0x18009d3d4  test    rsi, rsi
0x18009d3d7  jnz     short loc_18009D40E
0x18009d3d9  mov     eax, 8007000Dh
0x18009d3de  mov     ebx, eax
0x18009d3e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d3e7  cmp     rcx, r14
0x18009d3ea  jz      loc_18009D2A5
0x18009d3f0  test    byte ptr [rcx+1Ch], 2
0x18009d3f4  jz      loc_18009D2A5
0x18009d3fa  mov     edx, 8Eh
0x18009d3ff  mov     r9d, eax
0x18009d402  lea     r8, WPP_1559182127783aab3882fe828952d989_Traceguids
0x18009d409  jmp     loc_18009D295
0x18009d40e  movzx   ecx, [rbp+47h+var_88]
0x18009d412  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18009d41c  mul     rcx
0x18009d41f  mov     r8d, 179h
0x18009d425  mov     r14, rdx
0x18009d428  shr     r14, 5
0x18009d42c  cmp     r14w, r8w
0x18009d430  jbe     short loc_18009D481
0x18009d432  mov     eax, 8007000Dh
0x18009d437  mov     ebx, eax
0x18009d439  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d440  lea     rdx, WPP_GLOBAL_Control
0x18009d447  cmp     rcx, rdx
0x18009d44a  jz      loc_18009D2A5
0x18009d450  test    byte ptr [rcx+1Ch], 2
0x18009d454  jz      loc_18009D2A5
0x18009d45a  mov     rcx, [rcx+10h]
0x18009d45e  mov     edx, 8Fh
0x18009d463  mov     dword ptr [rsp+0E0h+var_B8], eax
0x18009d467  mov     [rsp+0E0h+var_C0], r8d
0x18009d46c  lea     r8, WPP_1559182127783aab3882fe828952d989_Traceguids
0x18009d473  movzx   r9d, r14w
0x18009d477  call    WPP_SF_DDD
0x18009d47c  jmp     loc_18009D29E
0x18009d481  lea     r9, [rbp+47h+Buf2]
0x18009d485  mov     r8d, 10h
0x18009d48b  mov     rdx, r13
0x18009d48e  xor     ecx, ecx
0x18009d490  call    FveDatumValidationInfoDataEntry
0x18009d495  mov     ecx, eax; int
0x18009d497  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009d49c  mov     ebx, eax
0x18009d49e  test    eax, eax
0x18009d4a0  jns     short loc_18009D4CD
0x18009d4a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d4a9  lea     rdx, WPP_GLOBAL_Control
0x18009d4b0  cmp     rcx, rdx
0x18009d4b3  jz      loc_18009D2A5
0x18009d4b9  test    byte ptr [rcx+1Ch], 2
0x18009d4bd  jz      loc_18009D2A5
0x18009d4c3  mov     edx, 90h
0x18009d4c8  jmp     loc_18009D3FF
0x18009d4cd  xor     edi, edi
0x18009d4cf  xor     eax, eax
0x18009d4d1  cmp     ax, r14w
0x18009d4d5  jnb     short loc_18009D54A
0x18009d4d7  mov     r13d, 179h
0x18009d4dd  movzx   eax, di
0x18009d4e0  mov     ecx, 4
0x18009d4e5  lea     rbx, [rax+rax*4]
0x18009d4e9  cmp     [rsi+rbx*8], cx
0x18009d4ed  jnz     short loc_18009D50A
0x18009d4ef  lea     rcx, [rsi+8]
0x18009d4f3  mov     r8d, 20h ; ' '; Size
0x18009d4f9  lea     rcx, [rcx+rbx*8]; Buf1
0x18009d4fd  lea     rdx, [rbp+47h+Buf2+8]; Buf2
0x18009d501  call    memcmp_0
0x18009d506  test    eax, eax
0x18009d508  jz      short loc_18009D57D
0x18009d50a  cmp     [r15], r13w
0x18009d50e  jnb     loc_18009D828
0x18009d514  movzx   eax, word ptr [r15]
0x18009d518  inc     di
0x18009d51b  movups  xmm0, xmmword ptr [rsi+rbx*8]
0x18009d51f  lea     rcx, [rax+rax*4]
0x18009d523  movups  xmmword ptr [r12+rcx*8], xmm0
0x18009d528  movups  xmm1, xmmword ptr [rsi+rbx*8+10h]
0x18009d52d  movups  xmmword ptr [r12+rcx*8+10h], xmm1
0x18009d533  movsd   xmm0, qword ptr [rsi+rbx*8+20h]
0x18009d539  movsd   qword ptr [r12+rcx*8+20h], xmm0
0x18009d540  inc     word ptr [r15]
0x18009d544  cmp     di, r14w
0x18009d548  jb      short loc_18009D4DD
0x18009d54a  mov     ebx, 80070490h
0x18009d54f  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d556  lea     rsi, WPP_GLOBAL_Control
0x18009d55d  cmp     rcx, rsi
0x18009d560  jz      loc_18009D81F
0x18009d566  test    byte ptr [rcx+1Ch], 2
0x18009d56a  jz      loc_18009D81F
0x18009d570  mov     edx, 98h
0x18009d575  mov     r9d, ebx
0x18009d578  jmp     loc_18009D808
0x18009d57d  cmp     [r15], r13w
0x18009d581  jb      short loc_18009D5BC
0x18009d583  mov     eax, 8007000Dh
0x18009d588  mov     ebx, eax
0x18009d58a  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d591  lea     rdx, WPP_GLOBAL_Control
0x18009d598  cmp     rcx, rdx
0x18009d59b  jz      loc_18009D37F
0x18009d5a1  test    byte ptr [rcx+1Ch], 2
0x18009d5a5  jz      loc_18009D37F
0x18009d5ab  mov     edx, 91h
0x18009d5b0  lea     r8, WPP_1559182127783aab3882fe828952d989_Traceguids
0x18009d5b7  jmp     loc_18009D36C
0x18009d5bc  movzx   eax, word ptr [r15]
0x18009d5c0  mov     r8w, 1
0x18009d5c5  movups  xmm0, xmmword ptr [rsi+rbx*8]
0x18009d5c9  add     di, r8w
0x18009d5cd  lea     rcx, [rax+rax*4]
0x18009d5d1  movups  xmmword ptr [r12+rcx*8], xmm0
0x18009d5d6  movups  xmm1, xmmword ptr [rsi+rbx*8+10h]
0x18009d5db  movups  xmmword ptr [r12+rcx*8+10h], xmm1
0x18009d5e1  movsd   xmm0, qword ptr [rsi+rbx*8+20h]
0x18009d5e7  movsd   qword ptr [r12+rcx*8+20h], xmm0
0x18009d5ee  add     [r15], r8w
0x18009d5f2  movzx   ecx, word ptr [r15]
0x18009d5f6  cmp     di, r14w
0x18009d5fa  jnb     loc_18009D69E
0x18009d600  movzx   eax, di
0x18009d603  lea     rdx, [rax+rax*4]
0x18009d607  cmp     word ptr [rsi+rdx*8], 3
0x18009d60c  jnz     loc_18009D698
0x18009d612  cmp     cx, r13w
0x18009d616  jnb     short loc_18009D654
0x18009d618  movups  xmm0, xmmword ptr [rsi+rdx*8]
0x18009d61c  movzx   eax, cx
0x18009d61f  add     di, r8w
0x18009d623  lea     rcx, [rax+rax*4]
0x18009d627  movups  xmmword ptr [r12+rcx*8], xmm0
0x18009d62c  movups  xmm1, xmmword ptr [rsi+rdx*8+10h]
0x18009d631  movups  xmmword ptr [r12+rcx*8+10h], xmm1
0x18009d637  movsd   xmm0, qword ptr [rsi+rdx*8+20h]
0x18009d63d  movsd   qword ptr [r12+rcx*8+20h], xmm0
0x18009d644  add     [r15], r8w
0x18009d648  movzx   ecx, word ptr [r15]
0x18009d64c  cmp     di, r14w
0x18009d650  jb      short loc_18009D600
0x18009d652  jmp     short loc_18009D698
0x18009d654  mov     eax, 8007000Dh
0x18009d659  mov     ebx, eax
0x18009d65b  mov     rcx, cs:WPP_GLOBAL_Control
0x18009d662  lea     rdx, WPP_GLOBAL_Control
0x18009d669  cmp     rcx, rdx
0x18009d66c  jz      loc_18009D37F
0x18009d672  test    byte ptr [rcx+1Ch], 2
0x18009d676  jz      loc_18009D37F
0x18009d67c  mov     edx, 92h
0x18009d681  jmp     loc_18009D5B0
0x18009d686  movzx   eax, di
0x18009d689  lea     rcx, [rax+rax*4]
0x18009d68d  cmp     word ptr [rsi+rcx*8], 2
0x18009d692  jnz     short loc_18009D69E
0x18009d694  add     di, r8w
0x18009d698  cmp     di, r14w
0x18009d69c  jb      short loc_18009D686
0x18009d69e  lea     rcx, [rbp+47h+var_68]
0x18009d6a2  call    cs:__imp_BcdOpenSystemStore
0x18009d6a9  nop     dword ptr [rax+rax+00h]
0x18009d6ae  mov     ecx, eax; int
0x18009d6b0  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009d6b5  mov     ebx, eax
  ... truncated ...
```
