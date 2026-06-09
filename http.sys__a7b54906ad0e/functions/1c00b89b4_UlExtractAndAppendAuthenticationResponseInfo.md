# UlExtractAndAppendAuthenticationResponseInfo

- ea: `0x1c00b89b4`
- end: `0x1c00b8acf`
- name: `UlExtractAndAppendAuthenticationResponseInfo`
- size: `283`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `registry_config, installer_update`

## callers

- `0x1c00b4cf0`
- `0x1c00b6c70`
- `0x1c00bbfe0`

## callees

- `0x1c0017104`
- `0x1c001a4b0`
- `0x1c001b900`
- `0x1c004bf6c`
- `0x1c004c348`
- `0x1c0050dac`
- `0x1c008f374`
- `0x1c009d178`
- `0x1c00a8400`
- `0x1c00b89b4`
- `0x1c0138aa4`
- `0x1c013a200`
- `0x1c013a2e0`
- `0x1c013a348`

## import_xrefs

- `ntoskrnl!IoIs32bitProcess` at `0x1c00ea437`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00ea4eb`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00ea58f`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00ea437`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00ea4eb`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00ea58f`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c00ea873`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c00eaa02`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c00ea873`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c00eaa02`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c00ea818`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c00ea9b4`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c00ea818`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c00ea9b4`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c00ea7cc`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c00ea968`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c00ea7cc`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c00ea968`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1c00ea797`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1c00ea940`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1c00ea797`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1c00ea940`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00ea7d8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00ea87f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00ea974`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00eaa0e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00ea7d8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00ea87f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00ea974`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00eaa0e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00ea782`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00ea805`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00ea92b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00ea9a1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00ea782`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00ea805`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00ea92b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00ea9a1`

## pseudocode

```c
__int64 __fastcall UlExtractAndAppendAuthenticationResponseInfo(
        __int64 a1,
        __int64 a2,
        IRP *a3,
        char a4,
        unsigned __int8 a5,
        char *a6)
{
  unsigned int v6; // r12d
  char v9; // di
  char v10; // r15
  __int64 v11; // rdx
  int updated; // esi
  __int64 v13; // r13
  char *v14; // r12
  __int64 v16; // rcx
  __m128i *v17; // r12
  __int64 v18; // r9
  char v19; // bl
  unsigned int i; // edx
  int v21; // ecx
  __int64 v22; // r9
  __int64 v23; // r8
  BOOLEAN v24; // al
  char v25; // r12
  __int64 v26; // r15
  __int64 v27; // r15
  __int64 v28; // rbx
  int v29; // r9d
  int v30; // ecx
  __int64 v31; // r9
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // r15
  __int64 v35; // r15
  const char *v36; // r12
  __int64 v37; // rbx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rdx
  __int64 v41; // rcx
  int v42; // [rsp+20h] [rbp-158h]
  char v44; // [rsp+50h] [rbp-128h]
  char v45; // [rsp+51h] [rbp-127h]
  char v46; // [rsp+52h] [rbp-126h] BYREF
  char v47; // [rsp+53h] [rbp-125h] BYREF
  char v48; // [rsp+54h] [rbp-124h]
  char v49; // [rsp+58h] [rbp-120h]
  unsigned __int16 v50; // [rsp+60h] [rbp-118h]
  int v51; // [rsp+64h] [rbp-114h]
  unsigned int v52; // [rsp+68h] [rbp-110h]
  PIRP Irp; // [rsp+70h] [rbp-108h]
  __m128i v54; // [rsp+78h] [rbp-100h] BYREF
  __int64 v55; // [rsp+88h] [rbp-F0h]
  char *v56; // [rsp+90h] [rbp-E8h]
  _OWORD v57[5]; // [rsp+A0h] [rbp-D8h] BYREF
  __int64 v58; // [rsp+F0h] [rbp-88h]
  __m128i *v59; // [rsp+F8h] [rbp-80h]
  __int64 v60; // [rsp+100h] [rbp-78h]
  __int64 v61; // [rsp+108h] [rbp-70h]
  IRP *v62; // [rsp+110h] [rbp-68h]
  _QWORD v63[3]; // [rsp+118h] [rbp-60h] BYREF
  char v64; // [rsp+130h] [rbp-48h]
  int v65; // [rsp+131h] [rbp-47h]
  __int16 v66; // [rsp+135h] [rbp-43h]
  char v67; // [rsp+137h] [rbp-41h]

  v6 = a4;
  Irp = a3;
  v61 = a1;
  v62 = a3;
  v49 = a4;
  v56 = a6;
  v9 = 0;
  v10 = 0;
  v48 = 0;
  memset(v57, 0, sizeof(v57));
  v46 = 0;
  v47 = 0;
  updated = 0;
  v45 = 0;
  v58 = 0;
  v13 = *(_QWORD *)(*(_QWORD *)(a1 + 24) + 960LL);
  v60 = v13;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x2000) != 0 )
  {
    v16 = v6;
    v14 = v56;
    WPP_SF_qiqqllq(v16, v11, a1, *(_QWORD *)(a1 + 64), a2, Irp, v16, a5, v56);
  }
  else
  {
    v14 = v56;
  }
  if ( v14 )
    *v14 = 0;
  if ( a2 )
  {
    v50 = *(_WORD *)(a2 + 552);
    if ( v50 )
    {
      v17 = *(__m128i **)(a2 + 560);
      v19 = a4;
      if ( !IoIs32bitProcess(Irp) )
      {
        LOBYTE(v18) = a4;
        UlProbeForRead(v17, 16LL * v50, 8, v18);
      }
      for ( i = 0; ; ++i )
      {
        v52 = i;
        v59 = v17;
        if ( i >= v50 )
          break;
        v54 = *v17;
        v21 = _mm_cvtsi128_si32(v54);
        if ( v21 >= 4 )
        {
          updated = -1073741811;
          v51 = -1073741811;
          if ( (WPP_MAIN_CB.StackSize & 0x20) != 0 )
            WPP_SF_D(118, WPP_3afd2232e6fe39b48106b10d7c60087a_Traceguids);
          goto LABEL_7;
        }
        if ( ((v21 - 1) & 0xFFFFFFFD) == 0 )
        {
          if ( v21 != 1 || v10 )
          {
            if ( v21 == 3 && !v45 )
            {
              v45 = 1;
              v58 = v54.m128i_i64[1];
            }
          }
          else
          {
            if ( IoIs32bitProcess(Irp) )
            {
              if ( v54.m128i_i32[1] < 0x24u )
              {
                updated = -1073741811;
                v51 = -1073741811;
                if ( (WPP_MAIN_CB.StackSize & 0x20) != 0 )
                  WPP_SF_D(119, WPP_3afd2232e6fe39b48106b10d7c60087a_Traceguids);
                goto LABEL_7;
              }
              v23 = 4;
            }
            else
            {
              if ( v54.m128i_i32[1] < 0x40u )
              {
                updated = -1073741811;
                v51 = -1073741811;
                if ( (WPP_MAIN_CB.StackSize & 0x20) != 0 )
                  WPP_SF_D(120, WPP_3afd2232e6fe39b48106b10d7c60087a_Traceguids);
                goto LABEL_7;
              }
              v23 = 8;
            }
            LOBYTE(v22) = v19;
            UlProbeForRead(v54.m128i_i64[1], v54.m128i_u32[1], v23, v22);
            v24 = IoIs32bitProcess(Irp);
            *(_QWORD *)&v57[0] = *(_QWORD *)v54.m128i_i64[1];
            DWORD2(v57[0]) = *(_DWORD *)(v54.m128i_i64[1] + 8);
            if ( v24 )
            {
              *((_QWORD *)&v57[2] + 1) = *(unsigned int *)(v54.m128i_i64[1] + 24);
              LOWORD(v57[2]) = *(_WORD *)(v54.m128i_i64[1] + 20);
              *((_QWORD *)&v57[1] + 1) = *(unsigned int *)(v54.m128i_i64[1] + 16);
              LOWORD(v57[1]) = *(_WORD *)(v54.m128i_i64[1] + 12);
              *((_QWORD *)&v57[3] + 1) = *(unsigned int *)(v54.m128i_i64[1] + 32);
              LOWORD(v57[3]) = *(_WORD *)(v54.m128i_i64[1] + 28);
            }
            else
            {
              *((_QWORD *)&v57[2] + 1) = *(_QWORD *)(v54.m128i_i64[1] + 40);
              LOWORD(v57[2]) = *(_WORD *)(v54.m128i_i64[1] + 32);
              *((_QWORD *)&v57[1] + 1) = *(_QWORD *)(v54.m128i_i64[1] + 24);
              LOWORD(v57[1]) = *(_WORD *)(v54.m128i_i64[1] + 16);
              *((_QWORD *)&v57[3] + 1) = *(_QWORD *)(v54.m128i_i64[1] + 56);
              LOWORD(v57[3]) = *(_WORD *)(v54.m128i_i64[1] + 48);
              v57[4] = 0;
            }
            v57[4] = 0;
            v10 = 1;
            v48 = 1;
            i = v52;
          }
        }
        ++v17;
        v19 = a4;
      }
      if ( !v10 )
      {
        if ( !v45 )
          goto LABEL_7;
        goto LABEL_63;
      }
      updated = UlVerifyAuthConfig(v13, v57);
      if ( updated < 0 )
        goto LABEL_7;
      v25 = 0;
      v26 = *(_QWORD *)(a1 + 1528);
      if ( v26 )
      {
        v25 = 1;
      }
      else
      {
        if ( *(_BYTE *)(a1 + 1521) )
        {
          v27 = *(_QWORD *)(a1 + 1304) + 296LL;
          goto LABEL_51;
        }
        v26 = *(_QWORD *)(a1 + 1312);
      }
      v27 = v26 + 304;
LABEL_51:
      KeEnterCriticalRegion();
      v28 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(v13 + 1360), 0);
      LOBYTE(v29) = a4;
      updated = UlIsAuthChangeNeeded(v30, v27, (unsigned int)v57, v29, (__int64)&v46);
      ExReleaseCacheAwarePushLockSharedEx(v28, 0);
      KeLeaveCriticalRegion();
      if ( updated < 0 )
        goto LABEL_7;
      if ( !v46 || !a5 )
      {
        v19 = a4;
        goto LABEL_63;
      }
      KeEnterCriticalRegion();
      ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(v13 + 1360));
      if ( !v25 || (v32 = *(_QWORD *)(a1 + 1312), *(_QWORD *)(a1 + 1528) == v32) )
      {
        v19 = a4;
        v33 = v27;
      }
      else
      {
        v19 = a4;
        if ( (v57[0] & 1) == 0 )
          goto LABEL_60;
        v33 = v32 + 304;
      }
      LOBYTE(v31) = v19;
      updated = UlUpdateAuthConfig(v13, v33, v57, v31);
LABEL_60:
      ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(v13 + 1360));
      KeLeaveCriticalRegion();
      if ( updated < 0 )
        goto LABEL_7;
LABEL_63:
      if ( !v45 )
      {
LABEL_83:
        if ( v56 )
        {
          if ( v46 || v47 )
            v9 = 1;
          *v56 = v9;
        }
        goto LABEL_7;
      }
      v54 = 0;
      v55 = 0;
      LOBYTE(v42) = v19;
      updated = UlCaptureChannelBindConfig(v13, v58, &v54, Irp, v42);
      if ( updated < 0 )
        goto LABEL_7;
      v44 = 0;
      v34 = *(_QWORD *)(a1 + 1568);
      if ( v34 )
      {
        v44 = 1;
      }
      else
      {
        if ( *(_BYTE *)(a1 + 1561) )
        {
          v35 = *(_QWORD *)(a1 + 1304) + 376LL;
          v36 = "SERVER_SESSION";
LABEL_71:
          KeEnterCriticalRegion();
          v37 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(v13 + 1360), 0);
          updated = UlIsChannelBindChangeNeeded(v35, &v54, &v47);
          ExReleaseCacheAwarePushLockSharedEx(v37, 0);
          KeLeaveCriticalRegion();
          if ( updated < 0 || !v47 || !a5 )
            goto LABEL_82;
          KeEnterCriticalRegion();
          ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(v13 + 1360));
          if ( !v44 || (v38 = *(_QWORD *)(a1 + 1312), *(_QWORD *)(a1 + 1568) == v38) )
          {
            v39 = v35;
          }
          else
          {
            v36 = "OWNER_GROUP";
            if ( (v54.m128i_i8[0] & 1) == 0 )
              goto LABEL_80;
            v39 = v38 + 384;
          }
          UlUpdateChannelBindConfig(v39, &v54);
LABEL_80:
          ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(v13 + 1360));
          KeLeaveCriticalRegion();
          if ( *(_BYTE *)(v13 + 1568) )
          {
            v65 = 0;
            v66 = 0;
            v67 = 0;
            v63[2] = v13;
            v63[0] = a1 + 72;
            v63[1] = 0;
            v64 = 0;
            McTemplateK0s_UlEtwWriteEventWrapper(v41, v40, v63, v36);
          }
LABEL_82:
          UlCleanupChannelBindConfig(&v54);
          if ( updated < 0 )
            goto LABEL_7;
          goto LABEL_83;
        }
        v34 = *(_QWORD *)(a1 + 1312);
      }
      v36 = "DEFAULT_GROUP";
      v35 = v34 + 384;
      goto LABEL_71;
    }
  }
LABEL_7:
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x2000) != 0 )
    WPP_SF_D(121, WPP_3afd2232e6fe39b48106b10d7c60087a_Traceguids);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1c00b89b4  push    rbx
0x1c00b89b6  push    rsi
0x1c00b89b7  push    rdi
0x1c00b89b8  push    r12
0x1c00b89ba  push    r13
0x1c00b89bc  push    r14
0x1c00b89be  push    r15
0x1c00b89c0  sub     rsp, 140h
0x1c00b89c7  mov     rax, cs:__security_cookie
0x1c00b89ce  xor     rax, rsp
0x1c00b89d1  mov     [rsp+178h+var_40], rax
0x1c00b89d9  movsx   r12d, r9b
0x1c00b89dd  mov     [rsp+178h+var_128], r12b
0x1c00b89e2  mov     rax, r8
0x1c00b89e5  mov     [rsp+178h+Irp], rax
0x1c00b89ea  mov     rbx, rdx
0x1c00b89ed  mov     r14, rcx
0x1c00b89f0  mov     [rsp+178h+var_70], rcx
0x1c00b89f8  mov     [rsp+178h+var_68], rax
0x1c00b8a00  mov     [rsp+178h+var_120], r12b
0x1c00b8a05  mov     rax, [rsp+178h+arg_28]
0x1c00b8a0d  mov     [rsp+178h+var_E8], rax
0x1c00b8a15  xor     edi, edi
0x1c00b8a17  mov     r15b, dil
0x1c00b8a1a  mov     [rsp+178h+var_124], dil
0x1c00b8a1f  xor     edx, edx; Val
0x1c00b8a21  lea     r8d, [rdi+50h]; Size
0x1c00b8a25  lea     rcx, [rsp+178h+var_D8]; void *
0x1c00b8a2d  call    memset
0x1c00b8a32  mov     [rsp+178h+var_126], dil
0x1c00b8a37  mov     [rsp+178h+var_125], dil
0x1c00b8a3c  mov     esi, edi
0x1c00b8a3e  mov     [rsp+178h+var_127], dil
0x1c00b8a43  mov     [rsp+178h+var_88], rdi
0x1c00b8a4b  mov     rax, [r14+18h]
0x1c00b8a4f  mov     r13, [rax+3C0h]
0x1c00b8a56  mov     [rsp+178h+var_78], r13
0x1c00b8a5e  test    dword ptr cs:WPP_MAIN_CB.Queue, 2000h
0x1c00b8a68  jnz     loc_1C00EA3EA
0x1c00b8a6e  mov     r12, [rsp+178h+var_E8]
0x1c00b8a76  test    r12, r12
0x1c00b8a79  jz      short loc_1C00B8A7F
0x1c00b8a7b  mov     [r12], dil
0x1c00b8a7f  test    rbx, rbx
0x1c00b8a82  jz      short loc_1C00B8A99
0x1c00b8a84  movzx   eax, word ptr [rbx+228h]
0x1c00b8a8b  mov     [rsp+178h+var_118], ax
0x1c00b8a90  test    ax, ax
0x1c00b8a93  jnz     loc_1C00EA42B
0x1c00b8a99  test    dword ptr cs:WPP_MAIN_CB.Queue, 2000h
0x1c00b8aa3  jnz     loc_1C00EAAAA
0x1c00b8aa9  mov     eax, esi
0x1c00b8aab  mov     rcx, [rsp+178h+var_40]
0x1c00b8ab3  xor     rcx, rsp; StackCookie
0x1c00b8ab6  call    __security_check_cookie
0x1c00b8abb  add     rsp, 140h
0x1c00b8ac2  pop     r15
0x1c00b8ac4  pop     r14
0x1c00b8ac6  pop     r13
0x1c00b8ac8  pop     r12
0x1c00b8aca  pop     rdi
0x1c00b8acb  pop     rsi
0x1c00b8acc  pop     rbx
0x1c00b8acd  retn
0x1c00ea3ea  movzx   eax, [rsp+178h+arg_20]
0x1c00ea3f2  mov     ecx, r12d
0x1c00ea3f5  mov     r12, [rsp+178h+var_E8]
0x1c00ea3fd  mov     [rsp+178h+var_138], r12
0x1c00ea402  mov     [rsp+178h+var_140], eax
0x1c00ea406  mov     [rsp+178h+var_148], ecx
0x1c00ea40a  mov     rax, [rsp+178h+Irp]
0x1c00ea40f  mov     [rsp+178h+var_150], rax
0x1c00ea414  mov     [rsp+178h+var_158], rbx
0x1c00ea419  mov     r9, [r14+40h]
0x1c00ea41d  mov     r8, r14
0x1c00ea420  call    WPP_SF_qiqqllq
0x1c00ea425  nop
0x1c00ea426  jmp     loc_1C00B8A76
0x1c00ea42b  mov     r12, [rbx+230h]
0x1c00ea432  mov     rcx, [rsp+178h+Irp]; Irp
0x1c00ea437  call    cs:__imp_IoIs32bitProcess
0x1c00ea43e  nop     dword ptr [rax+rax+00h]
0x1c00ea443  mov     bl, [rsp+178h+var_128]
0x1c00ea447  test    al, al
0x1c00ea449  jnz     short loc_1C00EA465
0x1c00ea44b  movzx   edx, [rsp+178h+var_118]
0x1c00ea450  shl     rdx, 4
0x1c00ea454  mov     r9b, bl
0x1c00ea457  mov     r8d, 8
0x1c00ea45d  mov     rcx, r12
0x1c00ea460  call    UlProbeForRead
0x1c00ea465  mov     edx, edi
0x1c00ea467  mov     [rsp+178h+var_110], edx
0x1c00ea46b  mov     [rsp+178h+var_80], r12
0x1c00ea473  movzx   eax, [rsp+178h+var_118]
0x1c00ea478  cmp     edx, eax
0x1c00ea47a  jnb     loc_1C00EA6BF
0x1c00ea480  movups  xmm0, xmmword ptr [r12]
0x1c00ea485  movups  [rsp+178h+var_100], xmm0
0x1c00ea48a  movd    ecx, xmm0
0x1c00ea48e  cmp     ecx, 4
0x1c00ea491  jl      short loc_1C00EA4C2
0x1c00ea493  mov     r8d, 0C000000Dh
0x1c00ea499  mov     esi, r8d
0x1c00ea49c  mov     [rsp+178h+var_114], r8d
0x1c00ea4a1  mov     eax, dword ptr cs:WPP_MAIN_CB.StackSize
0x1c00ea4a7  test    al, 20h
0x1c00ea4a9  jz      short loc_1C00EA4BD
0x1c00ea4ab  mov     ecx, 76h ; 'v'
0x1c00ea4b0  lea     rdx, WPP_3afd2232e6fe39b48106b10d7c60087a_Traceguids
0x1c00ea4b7  call    WPP_SF_D
0x1c00ea4bc  nop
0x1c00ea4bd  jmp     loc_1C00B8A99
0x1c00ea4c2  lea     eax, [rcx-1]
0x1c00ea4c5  test    eax, 0FFFFFFFDh
0x1c00ea4ca  jz      short loc_1C00EA4D1
0x1c00ea4cc  jmp     loc_1C00EA6B0
0x1c00ea4d1  cmp     ecx, 1
0x1c00ea4d4  jnz     loc_1C00EA68F
0x1c00ea4da  test    r15b, r15b
0x1c00ea4dd  jnz     loc_1C00EA68F
0x1c00ea4e3  mov     r15, [rsp+178h+Irp]
0x1c00ea4e8  mov     rcx, r15; Irp
0x1c00ea4eb  call    cs:__imp_IoIs32bitProcess
0x1c00ea4f2  nop     dword ptr [rax+rax+00h]
0x1c00ea4f7  test    al, al
0x1c00ea4f9  jz      short loc_1C00EA539
0x1c00ea4fb  cmp     dword ptr [rsp+178h+var_100+4], 24h ; '$'
0x1c00ea500  jnb     short loc_1C00EA531
0x1c00ea502  mov     r8d, 0C000000Dh
0x1c00ea508  mov     esi, r8d
0x1c00ea50b  mov     [rsp+178h+var_114], r8d
0x1c00ea510  mov     eax, dword ptr cs:WPP_MAIN_CB.StackSize
0x1c00ea516  test    al, 20h
0x1c00ea518  jz      short loc_1C00EA52C
0x1c00ea51a  mov     ecx, 77h ; 'w'
0x1c00ea51f  lea     rdx, WPP_3afd2232e6fe39b48106b10d7c60087a_Traceguids
0x1c00ea526  call    WPP_SF_D
0x1c00ea52b  nop
0x1c00ea52c  jmp     loc_1C00B8A99
0x1c00ea531  mov     r8d, 4
0x1c00ea537  jmp     short loc_1C00EA575
0x1c00ea539  cmp     dword ptr [rsp+178h+var_100+4], 40h ; '@'
0x1c00ea53e  jnb     short loc_1C00EA56F
0x1c00ea540  mov     r8d, 0C000000Dh
0x1c00ea546  mov     esi, r8d
0x1c00ea549  mov     [rsp+178h+var_114], r8d
0x1c00ea54e  mov     eax, dword ptr cs:WPP_MAIN_CB.StackSize
0x1c00ea554  test    al, 20h
0x1c00ea556  jz      short loc_1C00EA56A
0x1c00ea558  mov     ecx, 78h ; 'x'
0x1c00ea55d  lea     rdx, WPP_3afd2232e6fe39b48106b10d7c60087a_Traceguids
0x1c00ea564  call    WPP_SF_D
0x1c00ea569  nop
0x1c00ea56a  jmp     loc_1C00B8A99
0x1c00ea56f  mov     r8d, 8
0x1c00ea575  mov     r9b, bl
0x1c00ea578  mov     rbx, qword ptr [rsp+178h+var_100+8]
0x1c00ea580  mov     edx, dword ptr [rsp+178h+var_100+4]
0x1c00ea584  mov     rcx, rbx
0x1c00ea587  call    UlProbeForRead
0x1c00ea58c  mov     rcx, r15; Irp
0x1c00ea58f  call    cs:__imp_IoIs32bitProcess
0x1c00ea596  nop     dword ptr [rax+rax+00h]
0x1c00ea59b  test    al, al
0x1c00ea59d  mov     eax, [rbx]
0x1c00ea59f  mov     dword ptr [rsp+178h+var_D8], eax
0x1c00ea5a6  mov     eax, [rbx+4]
0x1c00ea5a9  mov     dword ptr [rsp+178h+var_D8+4], eax
0x1c00ea5b0  mov     al, [rbx+8]
0x1c00ea5b3  mov     byte ptr [rsp+178h+var_D0], al
0x1c00ea5ba  mov     al, [rbx+9]
0x1c00ea5bd  mov     byte ptr [rsp+178h+var_D0+1], al
0x1c00ea5c4  mov     al, [rbx+0Ah]
0x1c00ea5c7  mov     byte ptr [rsp+178h+var_D0+2], al
0x1c00ea5ce  mov     al, [rbx+0Bh]
0x1c00ea5d1  mov     byte ptr [rsp+178h+var_D0+3], al
0x1c00ea5d8  jz      short loc_1C00EA621
0x1c00ea5da  mov     eax, [rbx+18h]
0x1c00ea5dd  mov     [rsp+178h+var_B0], rax
0x1c00ea5e5  movzx   eax, word ptr [rbx+14h]
0x1c00ea5e9  mov     [rsp+178h+var_B8], ax
0x1c00ea5f1  mov     eax, [rbx+10h]
0x1c00ea5f4  mov     [rsp+178h+var_C0], rax
0x1c00ea5fc  movzx   eax, word ptr [rbx+0Ch]
0x1c00ea600  mov     [rsp+178h+var_C8], ax
0x1c00ea608  mov     eax, [rbx+20h]
0x1c00ea60b  mov     [rsp+178h+var_A0], rax
0x1c00ea613  movzx   eax, word ptr [rbx+1Ch]
0x1c00ea617  mov     [rsp+178h+var_A8], ax
0x1c00ea61f  jmp     short loc_1C00EA675
0x1c00ea621  mov     rax, [rbx+28h]
0x1c00ea625  mov     [rsp+178h+var_B0], rax
0x1c00ea62d  movzx   eax, word ptr [rbx+20h]
0x1c00ea631  mov     [rsp+178h+var_B8], ax
0x1c00ea639  mov     rax, [rbx+18h]
0x1c00ea63d  mov     [rsp+178h+var_C0], rax
0x1c00ea645  movzx   eax, word ptr [rbx+10h]
0x1c00ea649  mov     [rsp+178h+var_C8], ax
0x1c00ea651  mov     rax, [rbx+38h]
0x1c00ea655  mov     [rsp+178h+var_A0], rax
0x1c00ea65d  movzx   eax, word ptr [rbx+30h]
0x1c00ea661  mov     [rsp+178h+var_A8], ax
0x1c00ea669  xorps   xmm0, xmm0
0x1c00ea66c  movdqa  [rsp+178h+var_98], xmm0
0x1c00ea675  xorps   xmm0, xmm0
0x1c00ea678  movdqa  [rsp+178h+var_98], xmm0
0x1c00ea681  mov     r15b, 1
0x1c00ea684  mov     [rsp+178h+var_124], r15b
0x1c00ea689  mov     edx, [rsp+178h+var_110]
0x1c00ea68d  jmp     short loc_1C00EA6B0
0x1c00ea68f  cmp     ecx, 3
0x1c00ea692  jnz     short loc_1C00EA6B0
0x1c00ea694  cmp     [rsp+178h+var_127], dil
0x1c00ea699  jnz     short loc_1C00EA6B0
0x1c00ea69b  mov     [rsp+178h+var_127], 1
0x1c00ea6a0  mov     rax, qword ptr [rsp+178h+var_100+8]
0x1c00ea6a8  mov     [rsp+178h+var_88], rax
0x1c00ea6b0  inc     edx
0x1c00ea6b2  add     r12, 10h
0x1c00ea6b6  mov     bl, [rsp+178h+var_128]
0x1c00ea6ba  jmp     loc_1C00EA467
0x1c00ea6bf  jmp     short loc_1C00EA714
0x1c00ea6c1  mov     esi, eax
0x1c00ea6c3  and     eax, 0C0000000h
0x1c00ea6c8  cmp     eax, 80000000h
0x1c00ea6cd  jnz     short loc_1C00EA6DC
0x1c00ea6cf  cmp     esi, 80000005h
0x1c00ea6d5  jz      short loc_1C00EA6DC
0x1c00ea6d7  mov     esi, 0C000000Dh
0x1c00ea6dc  mov     [rsp+178h+var_114], esi
0x1c00ea6e0  test    esi, esi
0x1c00ea6e2  js      loc_1C00B8A99
0x1c00ea6e8  xor     edi, edi
0x1c00ea6ea  mov     r15b, [rsp+178h+var_124]
0x1c00ea6ef  mov     r13, [rsp+178h+var_78]
0x1c00ea6f7  mov     r14, [rsp+178h+var_70]
0x1c00ea6ff  mov     rax, [rsp+178h+var_68]
0x1c00ea707  mov     [rsp+178h+Irp], rax
0x1c00ea70c  mov     bl, [rsp+178h+var_120]
0x1c00ea710  mov     [rsp+178h+var_128], bl
0x1c00ea714  test    r15b, r15b
0x1c00ea717  jnz     short loc_1C00EA72D
0x1c00ea719  cmp     [rsp+178h+var_127], dil
0x1c00ea71e  jz      loc_1C00B8A99
0x1c00ea724  test    r15b, r15b
0x1c00ea727  jz      loc_1C00EA899
0x1c00ea72d  lea     rdx, [rsp+178h+var_D8]
0x1c00ea735  mov     rcx, r13
0x1c00ea738  call    UlVerifyAuthConfig
0x1c00ea73d  mov     esi, eax
0x1c00ea73f  test    eax, eax
0x1c00ea741  js      loc_1C00B8A99
0x1c00ea747  mov     r12b, dil
0x1c00ea74a  mov     r15, [r14+5F8h]
0x1c00ea751  test    r15, r15
0x1c00ea754  jz      short loc_1C00EA75B
0x1c00ea756  mov     r12b, 1
0x1c00ea759  jmp     short loc_1C00EA77B
0x1c00ea75b  cmp     [r14+5F1h], dil
0x1c00ea762  jz      short loc_1C00EA774
0x1c00ea764  mov     r15, [r14+518h]
0x1c00ea76b  add     r15, 128h
0x1c00ea772  jmp     short loc_1C00EA782
0x1c00ea774  mov     r15, [r14+520h]
0x1c00ea77b  add     r15, 130h
0x1c00ea782  call    cs:__imp_KeEnterCriticalRegion
0x1c00ea789  nop     dword ptr [rax+rax+00h]
0x1c00ea78e  xor     edx, edx
0x1c00ea790  mov     rcx, [r13+550h]
0x1c00ea797  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x1c00ea79e  nop     dword ptr [rax+rax+00h]
0x1c00ea7a3  mov     rbx, rax
0x1c00ea7a6  lea     rax, [rsp+178h+var_126]
0x1c00ea7ab  mov     [rsp+178h+var_158], rax
0x1c00ea7b0  mov     r9b, [rsp+178h+var_128]
0x1c00ea7b5  lea     r8, [rsp+178h+var_D8]
0x1c00ea7bd  mov     rdx, r15
0x1c00ea7c0  call    UlIsAuthChangeNeeded
0x1c00ea7c5  mov     esi, eax
0x1c00ea7c7  xor     edx, edx
0x1c00ea7c9  mov     rcx, rbx
0x1c00ea7cc  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1c00ea7d3  nop     dword ptr [rax+rax+00h]
0x1c00ea7d8  call    cs:__imp_KeLeaveCriticalRegion
0x1c00ea7df  nop     dword ptr [rax+rax+00h]
0x1c00ea7e4  test    esi, esi
0x1c00ea7e6  js      loc_1C00B8A99
0x1c00ea7ec  cmp     [rsp+178h+var_126], dil
0x1c00ea7f1  jz      loc_1C00EA895
0x1c00ea7f7  cmp     [rsp+178h+arg_20], dil
0x1c00ea7ff  jz      loc_1C00EA895
0x1c00ea805  call    cs:__imp_KeEnterCriticalRegion
0x1c00ea80c  nop     dword ptr [rax+rax+00h]
0x1c00ea811  mov     rcx, [r13+550h]
0x1c00ea818  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1c00ea81f  nop     dword ptr [rax+rax+00h]
0x1c00ea824  test    r12b, r12b
0x1c00ea827  jz      short loc_1C00EA850
0x1c00ea829  mov     rdx, [r14+520h]
  ... truncated ...
```
