# DoRemoveSmartCard(tagDISPPARAMS *,tagVARIANT *)

- ea: `0x180006df0`
- end: `0x18000715c`
- name: `?DoRemoveSmartCard@@YAJPEAUtagDISPPARAMS@@PEAUtagVARIANT@@@Z`
- size: `876`
- prototype: `__int64 __fastcall(struct tagDISPPARAMS *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001bb0`
- `0x180006df0`

## import_xrefs

- `KERNEL32!HeapSize` at `0x180006fc6`
- `KERNEL32!HeapSize` at `0x180007045`
- `KERNEL32!HeapSize` at `0x1800070f4`
- `KERNEL32!HeapSize` at `0x180006fc6`
- `KERNEL32!HeapSize` at `0x180007045`
- `KERNEL32!HeapSize` at `0x1800070f4`
- `KERNEL32!HeapFree` at `0x180007073`
- `KERNEL32!HeapFree` at `0x1800070db`
- `KERNEL32!HeapFree` at `0x180007122`
- `KERNEL32!HeapFree` at `0x180007073`
- `KERNEL32!HeapFree` at `0x1800070db`
- `KERNEL32!HeapFree` at `0x180007122`
- `KERNEL32!HeapAlloc` at `0x180006ea7`
- `KERNEL32!HeapAlloc` at `0x180006f6c`
- `KERNEL32!HeapAlloc` at `0x180006ea7`
- `KERNEL32!HeapAlloc` at `0x180006f6c`
- `KERNEL32!GetProcessHeap` at `0x180006e98`
- `KERNEL32!GetProcessHeap` at `0x180006f5b`
- `KERNEL32!GetProcessHeap` at `0x180006fb8`
- `KERNEL32!GetProcessHeap` at `0x180007037`
- `KERNEL32!GetProcessHeap` at `0x180007065`
- `KERNEL32!GetProcessHeap` at `0x1800070cd`
- `KERNEL32!GetProcessHeap` at `0x1800070e6`
- `KERNEL32!GetProcessHeap` at `0x180007114`
- `KERNEL32!GetProcessHeap` at `0x180006e98`
- `KERNEL32!GetProcessHeap` at `0x180006f5b`
- `KERNEL32!GetProcessHeap` at `0x180006fb8`
- `KERNEL32!GetProcessHeap` at `0x180007037`
- `KERNEL32!GetProcessHeap` at `0x180007065`
- `KERNEL32!GetProcessHeap` at `0x1800070cd`
- `KERNEL32!GetProcessHeap` at `0x1800070e6`
- `KERNEL32!GetProcessHeap` at `0x180007114`
- `FVEAPI!FveGetAuthMethodInformation` at `0x180006f3d`
- `FVEAPI!FveGetAuthMethodInformation` at `0x180006fae`
- `FVEAPI!FveGetAuthMethodInformation` at `0x180006f3d`
- `FVEAPI!FveGetAuthMethodInformation` at `0x180006fae`
- `FVEAPI!FveGetAuthMethodGuids` at `0x180006e7b`
- `FVEAPI!FveGetAuthMethodGuids` at `0x180006ece`
- `FVEAPI!FveGetAuthMethodGuids` at `0x180006e7b`
- `FVEAPI!FveGetAuthMethodGuids` at `0x180006ece`
- `FVEAPI!FveDeleteAuthMethod` at `0x180007031`
- `FVEAPI!FveDeleteAuthMethod` at `0x180007031`
- `FVEAPI!FveCloseVolume` at `0x1800070ba`
- `FVEAPI!FveCloseVolume` at `0x1800070ba`
- `FVEAPI!FveCommitChanges` at `0x1800070a5`
- `FVEAPI!FveCommitChanges` at `0x1800070a5`
- `FVEAPI!FveOpenVolumeW` at `0x180006e5e`
- `FVEAPI!FveOpenVolumeW` at `0x180006e5e`

## pseudocode

```c
__int64 __fastcall DoRemoveSmartCard(struct tagDISPPARAMS *a1, struct tagVARIANT *a2)
{
  VARIANTARG *rgvarg; // rcx
  unsigned int v3; // esi
  SHORT iVal; // r12
  LONGLONG llVal; // rcx
  char *v7; // r14
  LONG v8; // ebx
  LONG AuthMethodGuids; // eax
  SIZE_T v10; // rbx
  HANDLE ProcessHeap; // rax
  char *v12; // rax
  unsigned int v13; // r15d
  char *v14; // r12
  int AuthMethodInformation; // ecx
  SIZE_T v16; // rbx
  HANDLE v17; // rax
  _OWORD *v18; // rax
  _OWORD *v19; // rdi
  HANDLE v20; // rax
  SIZE_T v21; // rax
  _BYTE *i; // rcx
  __int64 j; // rdx
  __int64 v24; // r8
  __int64 v25; // rax
  HANDLE v26; // rax
  SIZE_T v27; // rax
  _BYTE *k; // rcx
  HANDLE v29; // rax
  HANDLE v30; // rax
  __int64 result; // rax
  unsigned int v32; // [rsp+20h] [rbp-60h] BYREF
  __int64 v33; // [rsp+28h] [rbp-58h] BYREF
  SHORT v34; // [rsp+30h] [rbp-50h]
  SIZE_T dwBytes; // [rsp+38h] [rbp-48h] BYREF
  __int128 v36; // [rsp+40h] [rbp-40h] BYREF
  __int128 v37; // [rsp+50h] [rbp-30h]
  _BYTE v38[24]; // [rsp+60h] [rbp-20h] BYREF

  rgvarg = a1->rgvarg;
  v3 = 0;
  v33 = -1;
  dwBytes = 0;
  v36 = 0;
  v32 = 0;
  v37 = 0;
  memset(v38, 0, sizeof(v38));
  iVal = rgvarg[1].iVal;
  llVal = rgvarg->llVal;
  v34 = iVal;
  v7 = 0;
  v8 = FveOpenVolumeW(llVal, 1, &v33);
  if ( v8 >= 0 )
  {
    AuthMethodGuids = FveGetAuthMethodGuids(v33, 0, 0, &v32);
    v8 = 0;
    if ( AuthMethodGuids != 1 )
      v8 = AuthMethodGuids;
    if ( v8 >= 0 )
    {
      v10 = 16LL * v32;
      ProcessHeap = GetProcessHeap();
      v12 = (char *)HeapAlloc(ProcessHeap, 8u, v10);
      v7 = v12;
      if ( !v12 )
      {
        v8 = -2147024882;
        goto LABEL_36;
      }
      v8 = FveGetAuthMethodGuids(v33, v12, v32, &v32);
      if ( v8 >= 0 )
      {
        v13 = 0;
        while ( 1 )
        {
          if ( v3 >= v32 )
          {
            if ( v13 <= 1 || v34 )
              v8 = FveCommitChanges(v33);
            else
              v8 = 1;
            break;
          }
          *(_QWORD *)&v36 = 0x100000038LL;
          memset(v38, 0, sizeof(v38));
          v37 = 0;
          *((_QWORD *)&v36 + 1) = 1;
          v14 = &v7[16 * v3];
          *(_OWORD *)&v38[8] = *(_OWORD *)v14;
          AuthMethodInformation = FveGetAuthMethodInformation(v33, &v36, 56, &dwBytes);
          if ( ((AuthMethodInformation + 0x80000000) & 0x80000000) != 0 || AuthMethodInformation == -2147024774 )
          {
            v16 = dwBytes;
            v17 = GetProcessHeap();
            v18 = HeapAlloc(v17, 8u, v16);
            v19 = v18;
            if ( !v18 )
            {
              v8 = -2147024882;
              break;
            }
            *v18 = v36;
            v18[1] = v37;
            v18[2] = *(_OWORD *)v38;
            *((_QWORD *)v18 + 6) = *(_QWORD *)&v38[16];
            if ( (int)FveGetAuthMethodInformation(v33, v18, dwBytes, &dwBytes) < 0 )
            {
              v20 = GetProcessHeap();
              v21 = HeapSize(v20, 0, v19);
              if ( v21 == -1 )
                goto LABEL_30;
              for ( i = v19; v21; --v21 )
                *i++ = 0;
              goto LABEL_29;
            }
            if ( (*((_DWORD *)v19 + 2) & 0x200000) != 0 )
            {
              for ( j = 0; (unsigned int)j < *((_DWORD *)v19 + 3); j = (unsigned int)(j + 1) )
              {
                v24 = *(_QWORD *)(*((_QWORD *)v19 + 2) + 8 * j);
                if ( *(_DWORD *)(v24 + 12) == 7 )
                {
                  v25 = *(unsigned int *)(v24 + 28);
                  if ( (*(_BYTE *)(v25 + v24 + 24) & 1) == 0 && (*(_BYTE *)(v25 + v24 + 24) & 4) == 0 )
                  {
                    ++v13;
                    FveDeleteAuthMethod(v33, v14);
                  }
                  break;
                }
              }
            }
            v26 = GetProcessHeap();
            v27 = HeapSize(v26, 0, v19);
            if ( v27 != -1 )
            {
              for ( k = v19; v27; --v27 )
                *k++ = 0;
LABEL_29:
              v29 = GetProcessHeap();
              HeapFree(v29, 0, v19);
            }
          }
LABEL_30:
          ++v3;
        }
      }
    }
  }
LABEL_36:
  if ( v33 != -1 )
  {
    FveCloseVolume();
    v33 = -1;
  }
  if ( v7 )
  {
    v30 = GetProcessHeap();
    HeapFree(v30, 0, v7);
  }
  a2->vt = 19;
  result = (unsigned int)v8;
  a2->lVal = v8;
  return result;
}

```

## disassembly

```asm
0x180006df0  mov     [rsp-38h+arg_10], rbx
0x180006df5  push    rbp
0x180006df6  push    rsi
0x180006df7  push    rdi
0x180006df8  push    r12
0x180006dfa  push    r13
0x180006dfc  push    r14
0x180006dfe  push    r15
0x180006e00  mov     rbp, rsp
0x180006e03  sub     rsp, 80h
0x180006e0a  mov     rax, cs:__security_cookie
0x180006e11  xor     rax, rsp
0x180006e14  mov     [rbp+var_8], rax
0x180006e18  mov     rcx, [rcx]
0x180006e1b  lea     r8, [rbp+var_58]
0x180006e1f  xor     esi, esi
0x180006e21  mov     [rbp+var_58], 0FFFFFFFFFFFFFFFFh
0x180006e29  xorps   xmm0, xmm0
0x180006e2c  mov     [rbp+dwBytes], rsi
0x180006e30  movups  [rbp+var_40], xmm0
0x180006e34  mov     [rbp+var_60], esi
0x180006e37  xor     eax, eax
0x180006e39  movups  [rbp+var_30], xmm0
0x180006e3d  mov     [rbp+var_10], rax
0x180006e41  mov     r13, rdx
0x180006e44  movups  [rbp+var_20], xmm0
0x180006e48  movzx   r12d, word ptr [rcx+20h]
0x180006e4d  lea     edx, [rsi+1]
0x180006e50  mov     rcx, [rcx+8]
0x180006e54  mov     edi, esi
0x180006e56  mov     [rbp+var_50], r12w
0x180006e5b  mov     r14d, esi
0x180006e5e  call    cs:__imp_FveOpenVolumeW
0x180006e64  mov     ebx, eax
0x180006e66  test    eax, eax
0x180006e68  js      loc_1800070B0
0x180006e6e  mov     rcx, [rbp+var_58]
0x180006e72  lea     r9, [rbp+var_60]
0x180006e76  xor     r8d, r8d
0x180006e79  xor     edx, edx
0x180006e7b  call    cs:__imp_FveGetAuthMethodGuids
0x180006e81  cmp     eax, 1
0x180006e84  mov     ebx, esi
0x180006e86  cmovnz  ebx, eax
0x180006e89  test    ebx, ebx
0x180006e8b  js      loc_1800070B0
0x180006e91  mov     ebx, [rbp+var_60]
0x180006e94  shl     rbx, 4
0x180006e98  call    cs:__imp_GetProcessHeap
0x180006e9e  mov     r8, rbx; dwBytes
0x180006ea1  lea     edx, [rsi+8]; dwFlags
0x180006ea4  mov     rcx, rax; hHeap
0x180006ea7  call    cs:__imp_HeapAlloc
0x180006ead  mov     r14, rax
0x180006eb0  test    rax, rax
0x180006eb3  jnz     short loc_180006EBF
0x180006eb5  mov     ebx, 8007000Eh
0x180006eba  jmp     loc_1800070B0
0x180006ebf  mov     r8d, [rbp+var_60]
0x180006ec3  lea     r9, [rbp+var_60]
0x180006ec7  mov     rcx, [rbp+var_58]
0x180006ecb  mov     rdx, r14
0x180006ece  call    cs:__imp_FveGetAuthMethodGuids
0x180006ed4  mov     ebx, eax
0x180006ed6  test    eax, eax
0x180006ed8  js      loc_1800070B0
0x180006ede  mov     r15d, esi
0x180006ee1  mov     ebx, 80000000h
0x180006ee6  cmp     esi, [rbp+var_60]
0x180006ee9  jnb     loc_18000708E
0x180006eef  mov     rcx, [rbp+var_58]
0x180006ef3  lea     r9, [rbp+dwBytes]
0x180006ef7  xorps   xmm0, xmm0
0x180006efa  mov     r12d, esi
0x180006efd  movups  [rbp+var_40], xmm0
0x180006f01  xor     eax, eax
0x180006f03  mov     dword ptr [rbp+var_40], 38h ; '8'
0x180006f0a  movups  [rbp+var_20], xmm0
0x180006f0e  mov     [rbp+var_10], rax
0x180006f12  lea     rdx, [rbp+var_40]
0x180006f16  movups  [rbp+var_30], xmm0
0x180006f1a  mov     dword ptr [rbp+var_40+4], 1
0x180006f21  lea     r8d, [rax+38h]
0x180006f25  mov     dword ptr [rbp+var_40+8], 1
0x180006f2c  shl     r12, 4
0x180006f30  add     r12, r14
0x180006f33  movups  xmm0, xmmword ptr [r12]
0x180006f38  movdqu  [rbp+var_20+8], xmm0
0x180006f3d  call    cs:__imp_FveGetAuthMethodInformation
0x180006f43  mov     ecx, eax
0x180006f45  add     eax, ebx
0x180006f47  test    ebx, eax
0x180006f49  jnz     short loc_180006F57
0x180006f4b  cmp     ecx, 8007007Ah
0x180006f51  jnz     loc_18000707E
0x180006f57  mov     rbx, [rbp+dwBytes]
0x180006f5b  call    cs:__imp_GetProcessHeap
0x180006f61  mov     r8, rbx; dwBytes
0x180006f64  mov     edx, 8; dwFlags
0x180006f69  mov     rcx, rax; hHeap
0x180006f6c  call    cs:__imp_HeapAlloc
0x180006f72  mov     rdi, rax
0x180006f75  test    rax, rax
0x180006f78  jz      loc_180007085
0x180006f7e  movups  xmm0, [rbp+var_40]
0x180006f82  lea     r9, [rbp+dwBytes]
0x180006f86  mov     rdx, rax
0x180006f89  movups  xmmword ptr [rax], xmm0
0x180006f8c  movups  xmm1, [rbp+var_30]
0x180006f90  movups  xmmword ptr [rax+10h], xmm1
0x180006f94  movups  xmm0, [rbp+var_20]
0x180006f98  movups  xmmword ptr [rax+20h], xmm0
0x180006f9c  movsd   xmm1, [rbp+var_10]
0x180006fa1  movsd   qword ptr [rax+30h], xmm1
0x180006fa6  mov     r8, [rbp+dwBytes]
0x180006faa  mov     rcx, [rbp+var_58]
0x180006fae  call    cs:__imp_FveGetAuthMethodInformation
0x180006fb4  test    eax, eax
0x180006fb6  jns     short loc_180006FF0
0x180006fb8  call    cs:__imp_GetProcessHeap
0x180006fbe  mov     r8, rdi; lpMem
0x180006fc1  xor     edx, edx; dwFlags
0x180006fc3  mov     rcx, rax; hHeap
0x180006fc6  call    cs:__imp_HeapSize
0x180006fcc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180006fd0  jz      loc_180007079
0x180006fd6  mov     rcx, rdi
0x180006fd9  test    rax, rax
0x180006fdc  jz      loc_180007065
0x180006fe2  mov     byte ptr [rcx], 0
0x180006fe5  inc     rcx
0x180006fe8  sub     rax, 1
0x180006fec  jnz     short loc_180006FE2
0x180006fee  jmp     short loc_180007065
0x180006ff0  test    dword ptr [rdi+8], 200000h
0x180006ff7  jz      short loc_180007037
0x180006ff9  xor     edx, edx
0x180006ffb  cmp     edx, [rdi+0Ch]
0x180006ffe  jnb     short loc_180007037
0x180007000  mov     rax, [rdi+10h]
0x180007004  mov     r8, [rax+rdx*8]
0x180007008  cmp     dword ptr [r8+0Ch], 7
0x18000700d  jz      short loc_180007013
0x18000700f  inc     edx
0x180007011  jmp     short loc_180006FFB
0x180007013  mov     eax, [r8+1Ch]
0x180007017  test    byte ptr [rax+r8+18h], 1
0x18000701d  jnz     short loc_180007037
0x18000701f  test    byte ptr [rax+r8+18h], 4
0x180007025  jnz     short loc_180007037
0x180007027  mov     rcx, [rbp+var_58]
0x18000702b  inc     r15d
0x18000702e  mov     rdx, r12
0x180007031  call    cs:__imp_FveDeleteAuthMethod
0x180007037  call    cs:__imp_GetProcessHeap
0x18000703d  mov     r8, rdi; lpMem
0x180007040  xor     edx, edx; dwFlags
0x180007042  mov     rcx, rax; hHeap
0x180007045  call    cs:__imp_HeapSize
0x18000704b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000704f  jz      short loc_180007079
0x180007051  mov     rcx, rdi
0x180007054  test    rax, rax
0x180007057  jz      short loc_180007065
0x180007059  mov     byte ptr [rcx], 0
0x18000705c  inc     rcx
0x18000705f  sub     rax, 1
0x180007063  jnz     short loc_180007059
0x180007065  call    cs:__imp_GetProcessHeap
0x18000706b  mov     r8, rdi; lpMem
0x18000706e  xor     edx, edx; dwFlags
0x180007070  mov     rcx, rax; hHeap
0x180007073  call    cs:__imp_HeapFree
0x180007079  mov     ebx, 80000000h
0x18000707e  inc     esi
0x180007080  jmp     loc_180006EE6
0x180007085  mov     ebx, 8007000Eh
0x18000708a  xor     esi, esi
0x18000708c  jmp     short loc_1800070B0
0x18000708e  xor     esi, esi
0x180007090  cmp     r15d, 1
0x180007094  jbe     short loc_1800070A1
0x180007096  cmp     [rbp+var_50], si
0x18000709a  jnz     short loc_1800070A1
0x18000709c  lea     ebx, [rsi+1]
0x18000709f  jmp     short loc_1800070AD
0x1800070a1  mov     rcx, [rbp+var_58]
0x1800070a5  call    cs:__imp_FveCommitChanges
0x1800070ab  mov     ebx, eax
0x1800070ad  mov     rdi, rsi
0x1800070b0  mov     rcx, [rbp+var_58]
0x1800070b4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800070b8  jz      short loc_1800070C8
0x1800070ba  call    cs:__imp_FveCloseVolume
0x1800070c0  mov     [rbp+var_58], 0FFFFFFFFFFFFFFFFh
0x1800070c8  test    r14, r14
0x1800070cb  jz      short loc_1800070E1
0x1800070cd  call    cs:__imp_GetProcessHeap
0x1800070d3  mov     r8, r14; lpMem
0x1800070d6  xor     edx, edx; dwFlags
0x1800070d8  mov     rcx, rax; hHeap
0x1800070db  call    cs:__imp_HeapFree
0x1800070e1  test    rdi, rdi
0x1800070e4  jz      short loc_180007128
0x1800070e6  call    cs:__imp_GetProcessHeap
0x1800070ec  mov     r8, rdi; lpMem
0x1800070ef  xor     edx, edx; dwFlags
0x1800070f1  mov     rcx, rax; hHeap
0x1800070f4  call    cs:__imp_HeapSize
0x1800070fa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800070fe  jz      short loc_180007128
0x180007100  mov     rcx, rdi
0x180007103  test    rax, rax
0x180007106  jz      short loc_180007114
0x180007108  mov     [rcx], sil
0x18000710b  inc     rcx
0x18000710e  sub     rax, 1
0x180007112  jnz     short loc_180007108
0x180007114  call    cs:__imp_GetProcessHeap
0x18000711a  mov     r8, rdi; lpMem
0x18000711d  xor     edx, edx; dwFlags
0x18000711f  mov     rcx, rax; hHeap
0x180007122  call    cs:__imp_HeapFree
0x180007128  mov     word ptr [r13+0], 13h
0x18000712f  mov     eax, ebx
0x180007131  mov     [r13+8], ebx
0x180007135  mov     rcx, [rbp+var_8]
0x180007139  xor     rcx, rsp; StackCookie
0x18000713c  call    __security_check_cookie
0x180007141  mov     rbx, [rsp+80h+arg_10]
0x180007149  add     rsp, 80h
0x180007150  pop     r15
0x180007152  pop     r14
0x180007154  pop     r13
0x180007156  pop     r12
0x180007158  pop     rdi
0x180007159  pop     rsi
0x18000715a  pop     rbp
0x18000715b  retn
```
