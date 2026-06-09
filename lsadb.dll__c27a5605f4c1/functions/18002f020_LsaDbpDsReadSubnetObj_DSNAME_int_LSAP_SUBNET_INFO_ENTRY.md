# LsaDbpDsReadSubnetObj(_DSNAME *,int *,_LSAP_SUBNET_INFO_ENTRY *)

- ea: `0x18002f020`
- end: `0x18002f361`
- name: `?LsaDbpDsReadSubnetObj@@YAJPEAU_DSNAME@@PEAHPEAU_LSAP_SUBNET_INFO_ENTRY@@@Z`
- size: `833`
- prototype: `__int64 __fastcall(struct _DSNAME *, int *, struct _LSAP_SUBNET_INFO_ENTRY *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18002d7a0`

## callees

- `0x180001670`
- `0x18000fd18`
- `0x18000fd40`
- `0x180011d30`
- `0x180011f90`
- `0x18002f020`
- `0x18003ad30`

## import_xrefs

- `LSASRV!LsapAllocateLsaHeap` at `0x18002f19c`
- `LSASRV!LsapAllocateLsaHeap` at `0x18002f2ab`
- `LSASRV!LsapAllocateLsaHeap` at `0x18002f30f`
- `LSASRV!LsapAllocateLsaHeap` at `0x18002f19c`
- `LSASRV!LsapAllocateLsaHeap` at `0x18002f2ab`
- `LSASRV!LsapAllocateLsaHeap` at `0x18002f30f`
- `LSASRV!LsapFreeLsaHeap` at `0x18002f10c`
- `LSASRV!LsapFreeLsaHeap` at `0x18002f11c`
- `LSASRV!LsapFreeLsaHeap` at `0x18002f12a`
- `LSASRV!LsapFreeLsaHeap` at `0x18002f10c`
- `LSASRV!LsapFreeLsaHeap` at `0x18002f11c`
- `LSASRV!LsapFreeLsaHeap` at `0x18002f12a`
- `DNSAPI!DnsValidateName_W` at `0x18002f2e6`
- `DNSAPI!DnsValidateName_W` at `0x18002f2e6`
- `NTDSA!GetRDNInfoExternal` at `0x18002f0cd`
- `NTDSA!GetRDNInfoExternal` at `0x18002f26b`
- `NTDSA!GetRDNInfoExternal` at `0x18002f0cd`
- `NTDSA!GetRDNInfoExternal` at `0x18002f26b`
- `NTDSA!IsMangledRDNExternal` at `0x18002f0eb`
- `NTDSA!IsMangledRDNExternal` at `0x18002f28d`
- `NTDSA!IsMangledRDNExternal` at `0x18002f0eb`
- `NTDSA!IsMangledRDNExternal` at `0x18002f28d`

## pseudocode

```c
__int64 __fastcall LsaDbpDsReadSubnetObj(struct _DSNAME *a1, int *a2, struct _LSAP_SUBNET_INFO_ENTRY *a3)
{
  __int128 v3; // xmm6
  const WCHAR *v4; // rsi
  unsigned int RDNInfoExternal; // eax
  __int64 v9; // rdx
  int v10; // ebx
  __int64 v11; // r8
  _WORD *v12; // rdi
  __int64 v14; // rbx
  _WORD *LsaHeap; // rax
  int v16; // eax
  __int128 v17; // xmm0
  unsigned int v18; // eax
  WCHAR *v19; // rax
  DNS_STATUS v20; // eax
  __int64 v21; // r12
  _WORD *v22; // rax
  _WORD *v23; // r15
  __int64 v24; // [rsp+28h] [rbp-E0h] BYREF
  __int128 v25; // [rsp+30h] [rbp-D8h]
  __int128 v26; // [rsp+40h] [rbp-C8h]
  _DWORD v27[2]; // [rsp+50h] [rbp-B8h] BYREF
  _DWORD *v28; // [rsp+58h] [rbp-B0h]
  __int128 v29; // [rsp+60h] [rbp-A8h] BYREF
  _DWORD v30[4]; // [rsp+70h] [rbp-98h] BYREF
  __int64 v31; // [rsp+80h] [rbp-88h]
  _BYTE Src[512]; // [rsp+88h] [rbp-80h] BYREF

  v30[0] = 590336;
  v30[2] = 0;
  v3 = 0;
  v31 = 0;
  v25 = 0;
  v4 = 0;
  v27[1] = 0;
  v26 = 0;
  v24 = 0;
  v29 = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_7f33ecf7a2c235901ed508f416bf6f8a_Traceguids);
  RDNInfoExternal = GetRDNInfoExternal(a1, Src, &v24, (char *)&v24 + 4);
  v10 = LsaDbpDsMapDsReturnToStatus(RDNInfoExternal);
  if ( v10 < 0 )
    goto LABEL_6;
  if ( (unsigned int)IsMangledRDNExternal(Src, (unsigned int)v24, 0) )
  {
    v10 = 0;
    *a2 = 0;
LABEL_6:
    v12 = (_WORD *)*((_QWORD *)&v25 + 1);
    goto LABEL_7;
  }
  v14 = (unsigned __int16)(2 * (v24 + 1));
  WORD1(v25) = 2 * (v24 + 1);
  LsaHeap = (_WORD *)LsapAllocateLsaHeap(v14);
  *((_QWORD *)&v25 + 1) = LsaHeap;
  v12 = LsaHeap;
  if ( !LsaHeap )
  {
LABEL_17:
    v10 = -1073741670;
    goto LABEL_7;
  }
  LOWORD(v25) = v14 - 2;
  memcpy_0(LsaHeap, Src, (unsigned __int16)(v14 - 2));
  v27[0] = 1;
  v28 = v30;
  v12[(unsigned int)v24] = 0;
  v16 = LsaDbpDsReadByDsName(a1, 0, (struct _ATTRBLOCKSIMPLE *)v27, (struct _ATTRBLOCKSIMPLE *)&v29);
  v10 = v16;
  if ( v16 == -1073741275 )
  {
    v10 = 0;
    goto LABEL_20;
  }
  if ( v16 < 0 )
    goto LABEL_7;
  if ( !(_DWORD)v29 )
  {
LABEL_20:
    v17 = v25;
    *a2 = 1;
    *((_OWORD *)a3 + 1) = v3;
    *(_OWORD *)a3 = v17;
    goto LABEL_11;
  }
  if ( **((_DWORD **)&v29 + 1) != 590336 || !*(_DWORD *)(*((_QWORD *)&v29 + 1) + 8LL) )
  {
    v10 = -1073741811;
    goto LABEL_7;
  }
  v18 = GetRDNInfoExternal(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)&v29 + 1) + 16LL) + 8LL), Src, &v24, (char *)&v24 + 4);
  v10 = LsaDbpDsMapDsReturnToStatus(v18);
  if ( v10 >= 0 )
  {
    if ( (unsigned int)IsMangledRDNExternal(Src, (unsigned int)v24, 0) )
      goto LABEL_27;
    v19 = (WCHAR *)LsapAllocateLsaHeap(2LL * (unsigned int)(v24 + 1));
    v4 = v19;
    if ( !v19 )
      goto LABEL_17;
    memcpy_0(v19, Src, 2LL * (unsigned int)v24);
    v4[(unsigned int)v24] = 0;
    v20 = DnsValidateName_W(v4, DnsNameDomainLabel);
    if ( v20 )
    {
      if ( v20 != 9556 )
      {
LABEL_27:
        v10 = 0;
        *a2 = 0;
        goto LABEL_7;
      }
    }
    v21 = (unsigned __int16)(2 * (v24 + 1));
    WORD1(v26) = 2 * (v24 + 1);
    v22 = (_WORD *)LsapAllocateLsaHeap(v21);
    *((_QWORD *)&v26 + 1) = v22;
    v23 = v22;
    if ( !v22 )
      goto LABEL_17;
    LOWORD(v26) = v21 - 2;
    memcpy_0(v22, Src, (unsigned __int16)(v21 - 2));
    v3 = v26;
    v23[(unsigned int)v24] = 0;
    goto LABEL_20;
  }
LABEL_7:
  if ( v12 )
    LsapFreeLsaHeap(v12, v9, v11);
  if ( *((_QWORD *)&v26 + 1) )
    LsapFreeLsaHeap(*((_QWORD *)&v26 + 1), v9, v11);
LABEL_11:
  if ( v4 )
    LsapFreeLsaHeap(v4, v9, v11);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_7f33ecf7a2c235901ed508f416bf6f8a_Traceguids,
      (unsigned int)v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002f020  mov     rax, rsp
0x18002f023  mov     [rax+20h], rbx
0x18002f027  push    rbp
0x18002f028  push    rsi
0x18002f029  push    rdi
0x18002f02a  push    r12
0x18002f02c  push    r13
0x18002f02e  push    r14
0x18002f030  push    r15
0x18002f032  lea     rbp, [rax-1D8h]
0x18002f039  sub     rsp, 2A0h
0x18002f040  movaps  xmmword ptr [rax-48h], xmm6
0x18002f044  mov     rax, cs:__security_cookie
0x18002f04b  xor     rax, rsp
0x18002f04e  mov     [rbp+1D0h+var_50], rax
0x18002f055  xor     r12d, r12d
0x18002f058  mov     [rsp+2D0h+var_268], 90200h
0x18002f060  xorps   xmm0, xmm0
0x18002f063  mov     dword ptr [rsp+2D0h+var_260], r12d
0x18002f068  xorps   xmm6, xmm6
0x18002f06b  mov     [rsp+2D0h+var_258], r12
0x18002f070  movups  [rsp+2D0h+var_2B0+8], xmm0
0x18002f075  mov     esi, r12d
0x18002f078  mov     dword ptr [rsp+2D0h+var_288+4], r12d
0x18002f07d  movups  [rsp+2D0h+var_2A0+8], xmm6
0x18002f082  mov     dword ptr [rsp+2D0h+var_2B0], r12d
0x18002f087  mov     r13, r8
0x18002f08a  movups  [rsp+2D0h+var_280+8], xmm0
0x18002f08f  mov     dword ptr [rsp+2D0h+var_2B0+4], r12d
0x18002f094  mov     r14, rdx
0x18002f097  mov     r15, rcx
0x18002f09a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f0a1  test    byte ptr [rcx+1Ch], 40h
0x18002f0a5  jz      short loc_18002F0BC
0x18002f0a7  mov     rcx, [rcx+10h]
0x18002f0ab  lea     edx, [r12+0Ah]
0x18002f0b0  lea     r8, WPP_7f33ecf7a2c235901ed508f416bf6f8a_Traceguids
0x18002f0b7  call    WPP_SF_
0x18002f0bc  lea     r9, [rsp+2D0h+var_2B0+4]
0x18002f0c1  mov     rcx, r15
0x18002f0c4  lea     r8, [rsp+2D0h+var_2B0]
0x18002f0c9  lea     rdx, [rbp+1D0h+Src]
0x18002f0cd  call    cs:__imp_GetRDNInfoExternal
0x18002f0d3  mov     ecx, eax; unsigned int
0x18002f0d5  call    ?LsaDbpDsMapDsReturnToStatus@@YAJK@Z; LsaDbpDsMapDsReturnToStatus(ulong)
0x18002f0da  mov     ebx, eax
0x18002f0dc  test    eax, eax
0x18002f0de  js      short loc_18002F0FF
0x18002f0e0  mov     edx, dword ptr [rsp+2D0h+var_2B0]
0x18002f0e4  lea     rcx, [rbp+1D0h+Src]
0x18002f0e8  xor     r8d, r8d
0x18002f0eb  call    cs:__imp_IsMangledRDNExternal
0x18002f0f1  test    eax, eax
0x18002f0f3  jz      loc_18002F186
0x18002f0f9  mov     ebx, r12d
0x18002f0fc  mov     [r14], r12d
0x18002f0ff  mov     rdi, qword ptr [rsp+2D0h+var_2A0]
0x18002f104  test    rdi, rdi
0x18002f107  jz      short loc_18002F112
0x18002f109  mov     rcx, rdi
0x18002f10c  call    cs:__imp_LsapFreeLsaHeap
0x18002f112  mov     rcx, qword ptr [rsp+2D0h+var_290]
0x18002f117  test    rcx, rcx
0x18002f11a  jz      short loc_18002F122
0x18002f11c  call    cs:__imp_LsapFreeLsaHeap
0x18002f122  test    rsi, rsi
0x18002f125  jz      short loc_18002F130
0x18002f127  mov     rcx, rsi
0x18002f12a  call    cs:__imp_LsapFreeLsaHeap
0x18002f130  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f137  test    byte ptr [rcx+1Ch], 40h
0x18002f13b  jz      short loc_18002F155
0x18002f13d  mov     rcx, [rcx+10h]
0x18002f141  lea     r8, WPP_7f33ecf7a2c235901ed508f416bf6f8a_Traceguids
0x18002f148  mov     edx, 0Bh
0x18002f14d  mov     r9d, ebx
0x18002f150  call    WPP_SF_d
0x18002f155  mov     eax, ebx
0x18002f157  mov     rcx, [rbp+1D0h+var_50]
0x18002f15e  xor     rcx, rsp; StackCookie
0x18002f161  call    __security_check_cookie
0x18002f166  lea     r11, [rsp+2D0h+var_30]
0x18002f16e  mov     rbx, [r11+58h]
0x18002f172  movaps  xmm6, xmmword ptr [r11-10h]
0x18002f177  mov     rsp, r11
0x18002f17a  pop     r15
0x18002f17c  pop     r14
0x18002f17e  pop     r13
0x18002f180  pop     r12
0x18002f182  pop     rdi
0x18002f183  pop     rsi
0x18002f184  pop     rbp
0x18002f185  retn
0x18002f186  movzx   eax, word ptr [rsp+2D0h+var_2B0]
0x18002f18b  inc     ax
0x18002f18e  add     ax, ax
0x18002f191  movzx   ecx, ax
0x18002f194  movzx   ebx, cx
0x18002f197  mov     word ptr [rsp+2D0h+var_2B0+0Ah], cx
0x18002f19c  call    cs:__imp_LsapAllocateLsaHeap
0x18002f1a2  mov     qword ptr [rsp+2D0h+var_2A0], rax
0x18002f1a7  mov     rdi, rax
0x18002f1aa  test    rax, rax
0x18002f1ad  jnz     short loc_18002F1B9
0x18002f1af  mov     ebx, 0C000009Ah
0x18002f1b4  jmp     loc_18002F104
0x18002f1b9  sub     bx, 2
0x18002f1bd  lea     rdx, [rbp+1D0h+Src]; Src
0x18002f1c1  movzx   r8d, bx; Size
0x18002f1c5  mov     rcx, rdi; void *
0x18002f1c8  mov     word ptr [rsp+2D0h+var_2B0+8], r8w
0x18002f1ce  call    memcpy_0
0x18002f1d3  mov     edx, dword ptr [rsp+2D0h+var_2B0]
0x18002f1d7  lea     rax, [rsp+2D0h+var_268]
0x18002f1dc  lea     r9, [rsp+2D0h+var_280+8]; struct _ATTRBLOCKSIMPLE *
0x18002f1e1  mov     dword ptr [rsp+2D0h+var_288], 1
0x18002f1e9  lea     r8, [rsp+2D0h+var_288]; struct _ATTRBLOCKSIMPLE *
0x18002f1ee  mov     qword ptr [rsp+2D0h+var_280], rax
0x18002f1f3  mov     rcx, r15; struct _DSNAME *
0x18002f1f6  mov     [rdi+rdx*2], r12w
0x18002f1fb  xor     edx, edx; unsigned int
0x18002f1fd  call    ?LsaDbpDsReadByDsName@@YAJPEAU_DSNAME@@KPEAU_ATTRBLOCKSIMPLE@@1@Z; LsaDbpDsReadByDsName(_DSNAME *,ulong,_ATTRBLOCKSIMPLE *,_ATTRBLOCKSIMPLE *)
0x18002f202  mov     ebx, eax
0x18002f204  cmp     eax, 0C0000225h
0x18002f209  jnz     short loc_18002F22B
0x18002f20b  mov     ebx, r12d
0x18002f20e  movups  xmm0, [rsp+2D0h+var_2B0+8]
0x18002f213  mov     dword ptr [r14], 1
0x18002f21a  movdqu  xmmword ptr [r13+10h], xmm6
0x18002f220  movdqu  xmmword ptr [r13+0], xmm0
0x18002f226  jmp     loc_18002F122
0x18002f22b  test    eax, eax
0x18002f22d  js      loc_18002F104
0x18002f233  cmp     dword ptr [rsp+2D0h+var_280+8], r12d
0x18002f238  jbe     short loc_18002F20E
0x18002f23a  mov     rcx, qword ptr [rsp+2D0h+var_270]
0x18002f23f  cmp     dword ptr [rcx], 90200h
0x18002f245  jnz     loc_18002F357
0x18002f24b  cmp     [rcx+8], r12d
0x18002f24f  jz      loc_18002F357
0x18002f255  mov     rcx, [rcx+10h]
0x18002f259  lea     r9, [rsp+2D0h+var_2B0+4]
0x18002f25e  lea     r8, [rsp+2D0h+var_2B0]
0x18002f263  lea     rdx, [rbp+1D0h+Src]
0x18002f267  mov     rcx, [rcx+8]
0x18002f26b  call    cs:__imp_GetRDNInfoExternal
0x18002f271  mov     ecx, eax; unsigned int
0x18002f273  call    ?LsaDbpDsMapDsReturnToStatus@@YAJK@Z; LsaDbpDsMapDsReturnToStatus(ulong)
0x18002f278  mov     ebx, eax
0x18002f27a  test    eax, eax
0x18002f27c  js      loc_18002F104
0x18002f282  mov     edx, dword ptr [rsp+2D0h+var_2B0]
0x18002f286  lea     rcx, [rbp+1D0h+Src]
0x18002f28a  xor     r8d, r8d
0x18002f28d  call    cs:__imp_IsMangledRDNExternal
0x18002f293  test    eax, eax
0x18002f295  jz      short loc_18002F2A2
0x18002f297  mov     ebx, r12d
0x18002f29a  mov     [r14], r12d
0x18002f29d  jmp     loc_18002F104
0x18002f2a2  mov     ecx, dword ptr [rsp+2D0h+var_2B0]
0x18002f2a6  inc     ecx
0x18002f2a8  add     rcx, rcx
0x18002f2ab  call    cs:__imp_LsapAllocateLsaHeap
0x18002f2b1  mov     rsi, rax
0x18002f2b4  test    rax, rax
0x18002f2b7  jz      loc_18002F1AF
0x18002f2bd  mov     r8d, dword ptr [rsp+2D0h+var_2B0]
0x18002f2c2  lea     rdx, [rbp+1D0h+Src]; Src
0x18002f2c6  add     r8, r8; Size
0x18002f2c9  mov     rcx, rax; void *
0x18002f2cc  call    memcpy_0
0x18002f2d1  mov     ecx, dword ptr [rsp+2D0h+var_2B0]
0x18002f2d5  mov     r15d, 1
0x18002f2db  mov     edx, r15d; Format
0x18002f2de  mov     [rsi+rcx*2], r12w
0x18002f2e3  mov     rcx, rsi; pszName
0x18002f2e6  call    cs:__imp_DnsValidateName_W
0x18002f2ec  test    eax, eax
0x18002f2ee  jz      short loc_18002F2F7
0x18002f2f0  cmp     eax, 2554h
0x18002f2f5  jnz     short loc_18002F297
0x18002f2f7  movzx   eax, word ptr [rsp+2D0h+var_2B0]
0x18002f2fc  add     ax, r15w
0x18002f300  add     ax, ax
0x18002f303  movzx   ecx, ax
0x18002f306  movzx   r12d, cx
0x18002f30a  mov     word ptr [rsp+2D0h+var_2A0+0Ah], cx
0x18002f30f  call    cs:__imp_LsapAllocateLsaHeap
0x18002f315  mov     qword ptr [rsp+2D0h+var_290], rax
0x18002f31a  mov     r15, rax
0x18002f31d  test    rax, rax
0x18002f320  jz      loc_18002F1AF
0x18002f326  sub     r12w, 2
0x18002f32b  lea     rdx, [rbp+1D0h+Src]; Src
0x18002f32f  movzx   r8d, r12w; Size
0x18002f333  mov     rcx, rax; void *
0x18002f336  mov     word ptr [rsp+2D0h+var_2A0+8], r8w
0x18002f33c  call    memcpy_0
0x18002f341  mov     ecx, dword ptr [rsp+2D0h+var_2B0]
0x18002f345  xor     r12d, r12d
0x18002f348  movups  xmm6, [rsp+2D0h+var_2A0+8]
0x18002f34d  mov     [r15+rcx*2], r12w
0x18002f352  jmp     loc_18002F20E
0x18002f357  mov     ebx, 0C000000Dh
0x18002f35c  jmp     loc_18002F104
```
