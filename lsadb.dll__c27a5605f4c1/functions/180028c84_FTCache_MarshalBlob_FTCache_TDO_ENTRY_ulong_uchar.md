# FTCache::MarshalBlob(FTCache::TDO_ENTRY *,ulong *,uchar * *)

- ea: `0x180028c84`
- end: `0x180029013`
- name: `?MarshalBlob@FTCache@@CAJPEAUTDO_ENTRY@1@PEAKPEAPEAE@Z`
- size: `911`
- prototype: `__int64 __fastcall(struct FTCache::TDO_ENTRY *, unsigned int *, unsigned __int8 **)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180025ba8`
- `0x180028510`

## callees

- `0x18000fd18`
- `0x18000fd40`
- `0x1800221cc`
- `0x180028c84`
- `0x180037768`
- `0x180037e10`
- `0x1800384f0`
- `0x1800387c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028fde`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028fe7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028fde`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028fe7`

## pseudocode

```c
__int64 __fastcall FTCache::MarshalBlob(struct FTCache::TDO_ENTRY *a1, unsigned int *a2, unsigned __int8 **a3)
{
  unsigned __int8 *v3; // r14
  void *v4; // r15
  char *v8; // rdi
  char *i; // rbx
  char v10; // al
  unsigned int v11; // eax
  FTCache::TLN_ENTRY *v12; // rcx
  __int128 *v13; // rcx
  __int64 *j; // rbx
  unsigned int v15; // ebx
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  _QWORD *v18; // rcx
  _OWORD *v19; // rax
  __int64 *k; // rbx
  _QWORD *v21; // rcx
  _OWORD *v22; // rax
  __int64 *m; // rbx
  __int64 v24; // rax
  int v25; // eax
  _QWORD v27[2]; // [rsp+20h] [rbp-60h] BYREF
  __int128 v28; // [rsp+30h] [rbp-50h]
  __int128 v29; // [rsp+40h] [rbp-40h] BYREF
  __int128 v30; // [rsp+50h] [rbp-30h]
  _OWORD v31[2]; // [rsp+60h] [rbp-20h] BYREF
  unsigned int v32; // [rsp+C0h] [rbp+40h] BYREF
  unsigned __int8 *v33; // [rsp+C8h] [rbp+48h] BYREF

  *(_QWORD *)&v31[1] = 0;
  v3 = 0;
  v32 = 0;
  v4 = 0;
  *a2 = 0;
  *a3 = 0;
  v27[1] = v27;
  v27[0] = v27;
  v33 = 0;
  v29 = 0;
  v30 = 0;
  v31[0] = 0;
  v28 = 0;
  if ( a1 )
  {
    v8 = (char *)a1 + 24;
    for ( i = (char *)*((_QWORD *)a1 + 3); ; i = *(char **)i )
    {
      if ( i == v8 )
      {
        for ( j = (__int64 *)*((_QWORD *)a1 + 5); ; j = (__int64 *)*j )
        {
          if ( j == (__int64 *)((char *)a1 + 40) )
          {
            for ( k = (__int64 *)*((_QWORD *)a1 + 7); ; k = (__int64 *)*k )
            {
              if ( k == (__int64 *)((char *)a1 + 56) )
              {
                for ( m = (__int64 *)*((_QWORD *)a1 + 9); m != (__int64 *)((char *)a1 + 72); m = (__int64 *)*m )
                {
                  LODWORD(v29) = *((_DWORD *)m + 12);
                  *((_QWORD *)&v29 + 1) = m[2];
                  *(_QWORD *)&v30 = *((unsigned int *)m + 8);
                  *((_QWORD *)&v30 + 1) = m[5];
                  memset(v31, 0, 24);
                  DWORD1(v29) = 3;
                  if ( !NetpAllocFtinfoEntry2(v27, (unsigned int *)&v29) )
                  {
                    v15 = -1073741670;
                    v16 = WPP_GLOBAL_Control;
                    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
                      goto LABEL_50;
                    v17 = 264;
                    goto LABEL_17;
                  }
                }
                v24 = NetpCopyFtinfoContext2(v27);
                v4 = (void *)v24;
                if ( v24 )
                {
                  v25 = NetpMarshalFtinfo2(v24, &v33, &v32);
                  v15 = v25;
                  if ( v25 >= 0 )
                  {
                    *a2 = v32;
                    *a3 = v33;
                  }
                  else
                  {
                    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        266,
                        &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids,
                        (unsigned int)v25);
                    v3 = v33;
                  }
                  goto LABEL_50;
                }
                v15 = -1073741670;
                v16 = WPP_GLOBAL_Control;
                if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
                  goto LABEL_50;
                v17 = 265;
                goto LABEL_17;
              }
              v21 = (_QWORD *)k[10];
              LODWORD(v29) = *((_DWORD *)k + 24);
              *((_QWORD *)&v29 + 1) = k[6];
              *(_QWORD *)&v30 = k[8];
              *((_QWORD *)&v30 + 1) = *v21;
              *(_QWORD *)&v31[0] = v21[1];
              v22 = (_OWORD *)k[11];
              DWORD1(v29) = 4;
              *(_OWORD *)((char *)v31 + 8) = 0;
              if ( v22 )
                *(_OWORD *)((char *)v31 + 8) = *v22;
              if ( !NetpAllocFtinfoEntry2(v27, (unsigned int *)&v29) )
                break;
            }
            v15 = -1073741670;
            v16 = WPP_GLOBAL_Control;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
              goto LABEL_50;
            v17 = 263;
            goto LABEL_17;
          }
          v18 = (_QWORD *)j[14];
          LODWORD(v29) = *((_DWORD *)j + 32);
          *((_QWORD *)&v29 + 1) = j[8];
          *(_QWORD *)&v30 = j[10];
          *((_QWORD *)&v30 + 1) = *v18;
          *(_QWORD *)&v31[0] = v18[1];
          v19 = (_OWORD *)j[15];
          DWORD1(v29) = 2;
          *(_OWORD *)((char *)v31 + 8) = 0;
          if ( v19 )
            *(_OWORD *)((char *)v31 + 8) = *v19;
          if ( !NetpAllocFtinfoEntry2(v27, (unsigned int *)&v29) )
            break;
        }
        v15 = -1073741670;
        v16 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          goto LABEL_50;
        v17 = 262;
        goto LABEL_17;
      }
      v10 = i[40];
      if ( v10 || !*((_QWORD *)i + 7) )
      {
        memset(v31, 0, 24);
        if ( v10 )
        {
          v11 = *((_DWORD *)i + 18);
          DWORD1(v29) = 1;
        }
        else
        {
          v12 = (FTCache::TLN_ENTRY *)*((_QWORD *)i + 7);
          v11 = v12 ? FTCache::TLN_ENTRY::Flags(v12) : *((_DWORD *)i + 18);
          DWORD1(v29) = 0;
        }
        v13 = (__int128 *)*((_QWORD *)i + 8);
        LODWORD(v29) = v11;
        *((_QWORD *)&v29 + 1) = *((_QWORD *)i + 4);
        v30 = *v13;
        if ( !NetpAllocFtinfoEntry2(v27, (unsigned int *)&v29) )
          break;
      }
    }
    v15 = -1073741670;
    v16 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_50;
    v17 = 261;
LABEL_17:
    WPP_SF_(v16[2], v17, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
  }
  else
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 260, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
    v15 = -1073741811;
  }
LABEL_50:
  LocalFree(v3);
  LocalFree(v4);
  NetpCleanFtinfoContext(v27);
  return v15;
}

```

## disassembly

```asm
0x180028c84  mov     [rsp-38h+arg_10], rbx
0x180028c89  push    rbp
0x180028c8a  push    rsi
0x180028c8b  push    rdi
0x180028c8c  push    r12
0x180028c8e  push    r13
0x180028c90  push    r14
0x180028c92  push    r15
0x180028c94  mov     rbp, rsp
0x180028c97  sub     rsp, 80h
0x180028c9e  xor     eax, eax
0x180028ca0  xorps   xmm0, xmm0
0x180028ca3  mov     [rbp+var_10], rax
0x180028ca7  xor     r14d, r14d
0x180028caa  mov     [rbp+arg_0], eax
0x180028cad  xor     r15d, r15d
0x180028cb0  mov     [rdx], eax
0x180028cb2  mov     r12, r8
0x180028cb5  mov     [r8], rax
0x180028cb8  lea     rax, [rbp+var_60]
0x180028cbc  mov     [rbp+var_58], rax
0x180028cc0  lea     rax, [rbp+var_60]
0x180028cc4  mov     [rbp+var_60], rax
0x180028cc8  mov     r13, rdx
0x180028ccb  mov     [rbp+arg_8], r14
0x180028ccf  mov     rsi, rcx
0x180028cd2  movups  [rbp+var_40], xmm0
0x180028cd6  movups  [rbp+var_30], xmm0
0x180028cda  movups  [rbp+var_20], xmm0
0x180028cde  movdqu  [rbp+var_50], xmm0
0x180028ce3  test    rcx, rcx
0x180028ce6  jz      loc_180028FB4
0x180028cec  lea     rdi, [rcx+18h]
0x180028cf0  mov     rbx, [rdi]
0x180028cf3  jmp     short loc_180028D68
0x180028cf5  mov     al, [rbx+28h]
0x180028cf8  test    al, al
0x180028cfa  jnz     short loc_180028D02
0x180028cfc  cmp     [rbx+38h], r14
0x180028d00  jnz     short loc_180028D65
0x180028d02  mov     qword ptr [rbp+var_20], r14
0x180028d06  xorps   xmm0, xmm0
0x180028d09  movdqu  [rbp+var_20+8], xmm0
0x180028d0e  test    al, al
0x180028d10  jz      short loc_180028D1E
0x180028d12  mov     eax, [rbx+48h]
0x180028d15  mov     dword ptr [rbp+var_40+4], 1
0x180028d1c  jmp     short loc_180028D35
0x180028d1e  mov     rcx, [rbx+38h]; this
0x180028d22  test    rcx, rcx
0x180028d25  jz      short loc_180028D2E
0x180028d27  call    ?Flags@TLN_ENTRY@FTCache@@QEAAKXZ; FTCache::TLN_ENTRY::Flags(void)
0x180028d2c  jmp     short loc_180028D31
0x180028d2e  mov     eax, [rbx+48h]
0x180028d31  mov     dword ptr [rbp+var_40+4], r14d
0x180028d35  mov     rcx, [rbx+40h]
0x180028d39  lea     rdx, [rbp+var_40]
0x180028d3d  mov     dword ptr [rbp+var_40], eax
0x180028d40  mov     rax, [rbx+20h]
0x180028d44  mov     qword ptr [rbp+var_40+8], rax
0x180028d48  mov     rax, [rcx]
0x180028d4b  mov     qword ptr [rbp+var_30], rax
0x180028d4f  mov     rax, [rcx+8]
0x180028d53  lea     rcx, [rbp+var_60]
0x180028d57  mov     qword ptr [rbp+var_30+8], rax
0x180028d5b  call    NetpAllocFtinfoEntry2
0x180028d60  test    rax, rax
0x180028d63  jz      short loc_180028D79
0x180028d65  mov     rbx, [rbx]
0x180028d68  cmp     rbx, rdi
0x180028d6b  jnz     short loc_180028CF5
0x180028d6d  lea     rdi, [rsi+28h]
0x180028d71  mov     rbx, [rdi]
0x180028d74  jmp     loc_180028E0A
0x180028d79  mov     ebx, 0C000009Ah
0x180028d7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180028d85  test    byte ptr [rcx+1Ch], 8
0x180028d89  jz      loc_180028FDB
0x180028d8f  mov     edx, 105h
0x180028d94  mov     rcx, [rcx+10h]
0x180028d98  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180028d9f  call    WPP_SF_
0x180028da4  jmp     loc_180028FDB
0x180028da9  mov     eax, [rbx+80h]
0x180028daf  xorps   xmm0, xmm0
0x180028db2  mov     rcx, [rbx+70h]
0x180028db6  mov     dword ptr [rbp+var_40], eax
0x180028db9  mov     rax, [rbx+40h]
0x180028dbd  mov     qword ptr [rbp+var_40+8], rax
0x180028dc1  mov     rax, [rbx+50h]
0x180028dc5  mov     qword ptr [rbp+var_30], rax
0x180028dc9  mov     rax, [rcx]
0x180028dcc  mov     qword ptr [rbp+var_30+8], rax
0x180028dd0  mov     rax, [rcx+8]
0x180028dd4  mov     qword ptr [rbp+var_20], rax
0x180028dd8  mov     rax, [rbx+78h]
0x180028ddc  mov     dword ptr [rbp+var_40+4], 2
0x180028de3  movdqu  [rbp+var_20+8], xmm0
0x180028de8  test    rax, rax
0x180028deb  jz      short loc_180028DF5
0x180028ded  movups  xmm0, xmmword ptr [rax]
0x180028df0  movdqu  [rbp+var_20+8], xmm0
0x180028df5  lea     rdx, [rbp+var_40]
0x180028df9  lea     rcx, [rbp+var_60]
0x180028dfd  call    NetpAllocFtinfoEntry2
0x180028e02  test    rax, rax
0x180028e05  jz      short loc_180028E18
0x180028e07  mov     rbx, [rbx]
0x180028e0a  cmp     rbx, rdi
0x180028e0d  jnz     short loc_180028DA9
0x180028e0f  lea     rdi, [rsi+38h]
0x180028e13  mov     rbx, [rdi]
0x180028e16  jmp     short loc_180028E96
0x180028e18  mov     ebx, 0C000009Ah
0x180028e1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180028e24  test    byte ptr [rcx+1Ch], 8
0x180028e28  jz      loc_180028FDB
0x180028e2e  mov     edx, 106h
0x180028e33  jmp     loc_180028D94
0x180028e38  mov     eax, [rbx+60h]
0x180028e3b  xorps   xmm0, xmm0
0x180028e3e  mov     rcx, [rbx+50h]
0x180028e42  mov     dword ptr [rbp+var_40], eax
0x180028e45  mov     rax, [rbx+30h]
0x180028e49  mov     qword ptr [rbp+var_40+8], rax
0x180028e4d  mov     rax, [rbx+40h]
0x180028e51  mov     qword ptr [rbp+var_30], rax
0x180028e55  mov     rax, [rcx]
0x180028e58  mov     qword ptr [rbp+var_30+8], rax
0x180028e5c  mov     rax, [rcx+8]
0x180028e60  mov     qword ptr [rbp+var_20], rax
0x180028e64  mov     rax, [rbx+58h]
0x180028e68  mov     dword ptr [rbp+var_40+4], 4
0x180028e6f  movdqu  [rbp+var_20+8], xmm0
0x180028e74  test    rax, rax
0x180028e77  jz      short loc_180028E81
0x180028e79  movups  xmm0, xmmword ptr [rax]
0x180028e7c  movdqu  [rbp+var_20+8], xmm0
0x180028e81  lea     rdx, [rbp+var_40]
0x180028e85  lea     rcx, [rbp+var_60]
0x180028e89  call    NetpAllocFtinfoEntry2
0x180028e8e  test    rax, rax
0x180028e91  jz      short loc_180028EA4
0x180028e93  mov     rbx, [rbx]
0x180028e96  cmp     rbx, rdi
0x180028e99  jnz     short loc_180028E38
0x180028e9b  lea     rdi, [rsi+48h]
0x180028e9f  mov     rbx, [rdi]
0x180028ea2  jmp     short loc_180028F0C
0x180028ea4  mov     ebx, 0C000009Ah
0x180028ea9  mov     rcx, cs:WPP_GLOBAL_Control
0x180028eb0  test    byte ptr [rcx+1Ch], 8
0x180028eb4  jz      loc_180028FDB
0x180028eba  mov     edx, 107h
0x180028ebf  jmp     loc_180028D94
0x180028ec4  mov     eax, [rbx+30h]
0x180028ec7  lea     rdx, [rbp+var_40]
0x180028ecb  mov     dword ptr [rbp+var_40], eax
0x180028ece  lea     rcx, [rbp+var_60]
0x180028ed2  mov     rax, [rbx+10h]
0x180028ed6  xorps   xmm0, xmm0
0x180028ed9  mov     qword ptr [rbp+var_40+8], rax
0x180028edd  mov     eax, [rbx+20h]
0x180028ee0  mov     dword ptr [rbp+var_30], eax
0x180028ee3  mov     rax, [rbx+28h]
0x180028ee7  mov     qword ptr [rbp+var_30+8], rax
0x180028eeb  mov     dword ptr [rbp+var_30+4], r14d
0x180028eef  mov     qword ptr [rbp+var_20], r14
0x180028ef3  movdqu  [rbp+var_20+8], xmm0
0x180028ef8  mov     dword ptr [rbp+var_40+4], 3
0x180028eff  call    NetpAllocFtinfoEntry2
0x180028f04  test    rax, rax
0x180028f07  jz      short loc_180028F42
0x180028f09  mov     rbx, [rbx]
0x180028f0c  cmp     rbx, rdi
0x180028f0f  jnz     short loc_180028EC4
0x180028f11  lea     rcx, [rbp+var_60]
0x180028f15  call    NetpCopyFtinfoContext2
0x180028f1a  mov     r15, rax
0x180028f1d  test    rax, rax
0x180028f20  jnz     short loc_180028F62
0x180028f22  mov     ebx, 0C000009Ah
0x180028f27  mov     rcx, cs:WPP_GLOBAL_Control
0x180028f2e  test    byte ptr [rcx+1Ch], 8
0x180028f32  jz      loc_180028FDB
0x180028f38  mov     edx, 109h
0x180028f3d  jmp     loc_180028D94
0x180028f42  mov     ebx, 0C000009Ah
0x180028f47  mov     rcx, cs:WPP_GLOBAL_Control
0x180028f4e  test    byte ptr [rcx+1Ch], 8
0x180028f52  jz      loc_180028FDB
0x180028f58  mov     edx, 108h
0x180028f5d  jmp     loc_180028D94
0x180028f62  lea     r8, [rbp+arg_0]
0x180028f66  mov     rcx, rax
0x180028f69  lea     rdx, [rbp+arg_8]
0x180028f6d  call    NetpMarshalFtinfo2
0x180028f72  mov     ebx, eax
0x180028f74  test    eax, eax
0x180028f76  jns     short loc_180028FA3
0x180028f78  mov     rcx, cs:WPP_GLOBAL_Control
0x180028f7f  test    byte ptr [rcx+1Ch], 8
0x180028f83  jz      short loc_180028F9D
0x180028f85  mov     rcx, [rcx+10h]
0x180028f89  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180028f90  mov     edx, 10Ah
0x180028f95  mov     r9d, eax
0x180028f98  call    WPP_SF_d
0x180028f9d  mov     r14, [rbp+arg_8]
0x180028fa1  jmp     short loc_180028FDB
0x180028fa3  mov     eax, [rbp+arg_0]
0x180028fa6  mov     [r13+0], eax
0x180028faa  mov     rax, [rbp+arg_8]
0x180028fae  mov     [r12], rax
0x180028fb2  jmp     short loc_180028FDB
0x180028fb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180028fbb  test    byte ptr [rcx+1Ch], 8
0x180028fbf  jz      short loc_180028FD6
0x180028fc1  mov     rcx, [rcx+10h]
0x180028fc5  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180028fcc  mov     edx, 104h
0x180028fd1  call    WPP_SF_
0x180028fd6  mov     ebx, 0C000000Dh
0x180028fdb  mov     rcx, r14; hMem
0x180028fde  call    cs:__imp_LocalFree
0x180028fe4  mov     rcx, r15; hMem
0x180028fe7  call    cs:__imp_LocalFree
0x180028fed  lea     rcx, [rbp+var_60]
0x180028ff1  call    NetpCleanFtinfoContext
0x180028ff6  mov     eax, ebx
0x180028ff8  mov     rbx, [rsp+80h+arg_10]
0x180029000  add     rsp, 80h
0x180029007  pop     r15
0x180029009  pop     r14
0x18002900b  pop     r13
0x18002900d  pop     r12
0x18002900f  pop     rdi
0x180029010  pop     rsi
0x180029011  pop     rbp
0x180029012  retn
```
