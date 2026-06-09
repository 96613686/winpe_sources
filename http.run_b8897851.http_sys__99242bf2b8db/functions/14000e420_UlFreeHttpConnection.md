# UlFreeHttpConnection

- ea: `0x14000e420`
- end: `0x14000eb5a`
- name: `UlFreeHttpConnection`
- size: `1850`
- prototype: ``
- caller_count: `44`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000a520`
- `0x14000c390`
- `0x14000eb60`
- `0x140019730`
- `0x14001f2c0`
- `0x140020594`
- `0x140020e50`
- `0x140025918`
- `0x14002b040`
- `0x140033330`
- `0x1400356b0`
- `0x140037440`
- `0x140037b00`
- `0x140039ff0`
- `0x14003cde0`
- `0x14004a9ec`
- `0x140054bc4`
- `0x1400558a0`
- `0x1400568e0`
- `0x140056f90`
- `0x140057810`
- `0x14005e0f0`
- `0x14005f3c0`
- `0x140067250`
- `0x14006ce40`
- `0x14006eb10`
- `0x1400705f0`
- `0x140071790`
- `0x140071f80`
- `0x1400aa118`
- `0x1400b0814`
- `0x1400b0b08`
- `0x1400b0e94`
- `0x1400c8b88`
- `0x1400e3c44`
- `0x1400e7a70`
- `0x1400e8570`
- `0x1400eb3f0`
- `0x1400eccf0`
- `0x1400f03c0`
- `0x1400f1630`
- `0x1400f2c7c`
- `0x140128da0`
- `0x14013e658`

## callees

- `0x14000a350`
- `0x14000e420`
- `0x140022610`
- `0x140049d28`
- `0x14005dff0`
- `0x14006caf0`
- `0x140074af8`
- `0x1400b3a0c`
- `0x140145800`
- `0x140147fb8`
- `0x140148c04`
- `0x140167700`
- `0x1401677e0`
- `0x140167b40`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000e525`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000e715`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000e525`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000e715`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14000e68c`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14000e68c`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x14000eaf5`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x14000eaf5`
- `ntoskrnl!KeSetEvent` at `0x14000eb14`
- `ntoskrnl!KeSetEvent` at `0x14000eb14`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000e8b0`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000e8d7`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000e8b0`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000e8d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e9dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ea35`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000eabf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140170a51`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e9dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ea35`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000eabf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140170a51`

## pseudocode

```c
void __fastcall UlFreeHttpConnection(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  char *v5; // rbx
  _QWORD **v6; // rdi
  _QWORD *v7; // rdx
  __int64 v8; // r15
  void (__fastcall *v9)(__int64); // r14
  __int64 v10; // rsi
  _BYTE *v11; // rsi
  unsigned __int64 v12; // rdi
  __int64 v13; // rax
  volatile signed __int32 *v14; // rdi
  volatile signed __int32 *v15; // rdx
  int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rax
  _QWORD *v19; // rdi
  __int64 v20; // rbp
  __int64 v21; // rdx
  _BYTE *v22; // rcx
  void *v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  int v26; // eax
  void *v27; // rdi
  __int64 v28; // rdx
  ULONG_PTR v29; // rdx
  int v30; // esi
  bool v31; // zf
  unsigned __int64 v32; // rdi
  _QWORD *v33; // rax
  volatile signed __int32 *v34; // rdx
  int v35; // eax
  volatile signed __int32 *v36; // rdx
  int v37; // eax
  __int64 v38; // rdi
  USHORT v39; // ax
  __int64 v40; // rdi
  USHORT CurrentNodeNumber; // ax
  ULONG_PTR v42; // rdx
  _DWORD *v43; // rcx
  __int64 v44; // rax
  __int64 v45; // [rsp+30h] [rbp-A8h] BYREF
  _DWORD v46[24]; // [rsp+40h] [rbp-98h] BYREF

  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_q(1032, 20, WPP_682cf469470432b235cb9a4961616e40_Traceguids, a1);
  v5 = (char *)(a1 - 64);
  v6 = (_QWORD **)(v5 + 584);
  while ( 1 )
  {
    v7 = *v6;
    if ( *v6 == v6 )
      break;
    if ( (_QWORD **)v7[1] != v6 || (v33 = (_QWORD *)*v7, *(_QWORD **)(*v7 + 8LL) != v7) )
      __fastfail(3u);
    *v6 = v33;
    v33[1] = v6;
    *v7 = 0;
    v7[1] = 0;
    UlReleaseRequestBuffer(v5, v7 - 6);
  }
  if ( *((_DWORD *)v5 + 128) == 4 )
  {
    v8 = *((_QWORD *)v5 + 62);
    v9 = *(void (__fastcall **)(__int64))(*((_QWORD *)v5 + 63) + 16LL);
  }
  else
  {
    v9 = 0;
    v8 = 0;
  }
  *((_DWORD *)v5 + 128) = 5;
  *((_QWORD *)v5 + 63) = 0;
  v10 = *((_QWORD *)v5 + 138);
  if ( v10 )
  {
    v11 = (_BYTE *)(v10 - 21);
    *((_DWORD *)v11 + 4) = 1885886581;
    if ( v11[20] )
    {
      memset(v46, 0, sizeof(v46));
      if ( UxDebugDisableLookaside )
      {
        v46[10] = dword_1401A05C8;
        ((void (__fastcall *)(_BYTE *, _DWORD *))off_1401A05D8)(v11, v46);
      }
      else if ( UxCompactMode )
      {
        v40 = qword_1401A05B0;
        CurrentNodeNumber = KeGetCurrentNodeNumber();
        PplFreeToLookasideListProcessor(v40, v11, CurrentNodeNumber);
      }
      else
      {
        v12 = qword_1401A05B0 + ((unsigned __int64)(unsigned int)(*(_DWORD *)v11 + 1) << 7);
        if ( !*(_BYTE *)(v12 + 176) )
          PplpLazyInitializeLookasideList(qword_1401A05B0, v12 + 64);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v12 + 64), v11);
      }
    }
    else
    {
      ExFreePoolWithTag(v11, 0);
    }
    *((_QWORD *)v5 + 138) = 0;
  }
  v13 = *((_QWORD *)v5 + 76);
  if ( v13 )
  {
    v14 = (volatile signed __int32 *)(v13 + 8);
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_q(1032, 87, WPP_682cf469470432b235cb9a4961616e40_Traceguids, v13 + 8);
    a4 = (unsigned int)_InterlockedDecrement(v14);
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_d(1032, 88, WPP_682cf469470432b235cb9a4961616e40_Traceguids, a4);
    v15 = (volatile signed __int32 *)(*((_QWORD *)v5 + 76) + 4LL);
    v16 = _InterlockedDecrement(v15);
    if ( UxDebugCheckRefcount && v16 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)v15, 0xFu, v16);
    if ( !v16 )
    {
      v43 = (_DWORD *)*((_QWORD *)v5 + 76);
      *v43 = 2036550773;
      ExFreePoolWithTag(v43, 0);
    }
    *((_QWORD *)v5 + 76) = 0;
  }
  v17 = *((_QWORD *)v5 + 77);
  if ( v17 )
  {
    _InterlockedDecrement((volatile signed __int32 *)(v17 + 28));
    v36 = (volatile signed __int32 *)(*((_QWORD *)v5 + 77) + 4LL);
    v37 = _InterlockedDecrement(v36);
    if ( UxDebugCheckRefcount && v37 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)v36, 0xFu, v37);
    if ( !v37 )
      UlScFreeEntry(*((PVOID *)v5 + 77));
    *((_QWORD *)v5 + 77) = 0;
  }
  v18 = *((_QWORD *)v5 + 78);
  if ( v18 )
  {
    _InterlockedDecrement((volatile signed __int32 *)(v18 + 412));
    v34 = (volatile signed __int32 *)(*((_QWORD *)v5 + 78) + 4LL);
    v35 = _InterlockedDecrement(v34);
    if ( UxDebugCheckRefcount && v35 <= -1 )
      UlBugCheckEx(3u, (ULONG_PTR)v34, 0xFu, v35);
    if ( !v35 )
      UlFreeConfigGroup(*((PVOID *)v5 + 78));
    *((_QWORD *)v5 + 78) = 0;
  }
  v19 = v5 + 792;
  v20 = *((_QWORD *)v5 + 137);
  if ( *((_QWORD *)v5 + 100) != -1 && *((_QWORD *)v5 + 101) != -1 )
    UlpDeleteClientContextHandle(*((_QWORD *)v5 + 137), v5 + 792);
  v21 = *((_QWORD *)v5 + 106);
  if ( v21 )
  {
    UlpFreeAuthToken(*v19, v21, *((unsigned int *)v5 + 215));
    *((_QWORD *)v5 + 106) = 0;
    *((_QWORD *)v5 + 107) = 0;
  }
  if ( !v5[836] )
  {
    v22 = (_BYTE *)*((_QWORD *)v5 + 103);
    if ( v22 )
    {
      if ( *v19 == v20 + 256 )
      {
        v44 = *((unsigned int *)v5 + 208);
        if ( *((_DWORD *)v5 + 208) )
        {
          do
          {
            *v22++ = 0;
            --v44;
          }
          while ( v44 );
        }
      }
      if ( !v5[837] )
        ExFreePoolWithTag(*((PVOID *)v5 + 103), 0);
    }
  }
  v23 = (void *)*((_QWORD *)v5 + 105);
  *((_WORD *)v5 + 418) = 0;
  *((_QWORD *)v5 + 103) = 0;
  *((_DWORD *)v5 + 208) = 0;
  if ( v23 )
    ExFreePoolWithTag(v23, 0);
  *((_QWORD *)v5 + 105) = 0;
  v24 = *v19;
  if ( *v19 && *(_BYTE *)(v24 + 109) )
    UlDereferenceAlternateCredential((PVOID)(v24 - 16), 0x20u);
  *v19 = 0;
  v25 = *((_QWORD *)v5 + 61);
  if ( v25 )
  {
    v26 = _InterlockedDecrement((volatile signed __int32 *)(v25 + 8));
    if ( UxDebugCheckRefcount && v26 <= -1 )
      UlBugCheckEx(3u, v25 + 8, 0xAu, v26);
    if ( !v26 )
    {
      v42 = v25 + 48;
      if ( *(_QWORD *)(v25 + 48) || *(_QWORD *)(v25 + 64) || *(_QWORD *)(v25 + 80) )
        UlBugCheckEx(1u, v42, (ULONG_PTR)"minio\\http\\sys\\tl.h", 0x400u);
      LOBYTE(a4) = 1;
      UlThreadPoolEnqueueWorkItem(0, v42, UxTlDestroyListenEndpoint, a4, *(_QWORD *)(v25 + 192), -1);
    }
    *((_QWORD *)v5 + 61) = 0;
  }
  v27 = (void *)*((_QWORD *)v5 + 136);
  v28 = (unsigned int)UxPodMonitorSlot;
  *((_QWORD *)v5 + 137) = 0;
  v45 = 0;
  PsGetPermanentSiloContext(v27, v28, &v45);
  if ( v27 )
    ObfDereferenceObjectWithTag(v27, 0x43546C55u);
  v29 = v45 + 24;
  v30 = _InterlockedDecrement((volatile signed __int32 *)(v45 + 24));
  if ( UxDebugCheckRefcount && v30 <= -1 )
    UlBugCheckEx(3u, v29, 0xFu, v30);
  if ( !v30 )
    KeSetEvent((PRKEVENT)(v45 + 32), 0, 0);
  v31 = UxDebugDisableLookaside == 0;
  *((_QWORD *)v5 + 136) = 0;
  *((_DWORD *)v5 + 4) = 1667779701;
  if ( v31 )
  {
    if ( UxCompactMode )
    {
      v38 = qword_1401A03A0;
      v39 = KeGetCurrentNodeNumber();
      PplFreeToLookasideListProcessor(v38, v5, v39);
    }
    else
    {
      v32 = qword_1401A03A0 + ((unsigned __int64)(unsigned int)(*(_DWORD *)v5 + 1) << 7);
      if ( !*(_BYTE *)(v32 + 176) )
        PplpLazyInitializeLookasideList(qword_1401A03A0, v32 + 64);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v32 + 64), v5);
    }
  }
  else
  {
    memset(v46, 0, sizeof(v46));
    v46[10] = dword_1401A03B8;
    ((void (__fastcall *)(char *, _DWORD *))off_1401A03C8)(v5, v46);
  }
  if ( v9 )
    v9(v8);
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_(1032, 21, WPP_682cf469470432b235cb9a4961616e40_Traceguids);
}

```

## disassembly

```asm
0x14000e420  push    rbx
0x14000e422  push    rdi
0x14000e423  push    r12
0x14000e425  sub     rsp, 0C0h
0x14000e42c  mov     rax, cs:__security_cookie
0x14000e433  xor     rax, rsp
0x14000e436  mov     [rsp+0D8h+var_38], rax
0x14000e43e  mov     rbx, rcx
0x14000e441  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14000e448  jnz     loc_14000E919
0x14000e44e  add     rbx, 0FFFFFFFFFFFFFFC0h
0x14000e452  xor     r12d, r12d
0x14000e455  lea     rdi, [rbx+248h]
0x14000e45c  mov     rdx, [rdi]
0x14000e45f  cmp     rdx, rdi
0x14000e462  jnz     loc_14000E773
0x14000e468  cmp     dword ptr [rbx+200h], 4
0x14000e46f  mov     [rsp+0D8h+arg_10], rsi
0x14000e477  mov     [rsp+0D8h+var_20], r14
0x14000e47f  mov     [rsp+0D8h+var_28], r15
0x14000e487  jnz     loc_14000E9AB
0x14000e48d  mov     rax, [rbx+1F8h]
0x14000e494  mov     r15, [rbx+1F0h]
0x14000e49b  mov     r14, [rax+10h]
0x14000e49f  mov     dword ptr [rbx+200h], 5
0x14000e4a9  mov     [rbx+1F8h], r12
0x14000e4b0  mov     rsi, [rbx+450h]
0x14000e4b7  test    rsi, rsi
0x14000e4ba  jz      short loc_14000E538
0x14000e4bc  add     rsi, 0FFFFFFFFFFFFFFEBh
0x14000e4c0  xor     edx, edx; Val
0x14000e4c2  mov     dword ptr [rsi+10h], 70685875h
0x14000e4c9  cmp     [rsi+14h], r12b
0x14000e4cd  jz      loc_14000E9D9
0x14000e4d3  mov     r8d, 60h ; '`'; Size
0x14000e4d9  lea     rcx, [rsp+0D8h+var_98]; void *
0x14000e4de  call    memset
0x14000e4e3  cmp     cs:UxDebugDisableLookaside, r12b
0x14000e4ea  jnz     loc_14000E9B6
0x14000e4f0  cmp     cs:UxCompactMode, r12b
0x14000e4f7  jnz     loc_14000E8D0
0x14000e4fd  mov     edi, [rsi]
0x14000e4ff  mov     rcx, cs:qword_1401A05B0
0x14000e506  inc     edi
0x14000e508  shl     rdi, 7
0x14000e50c  add     rdi, rcx
0x14000e50f  movzx   eax, byte ptr [rdi+0B0h]
0x14000e516  test    al, al
0x14000e518  jz      loc_14000E937
0x14000e51e  mov     rdx, rsi; Entry
0x14000e521  lea     rcx, [rdi+40h]; Lookaside
0x14000e525  call    cs:__imp_ExFreeToLookasideListEx
0x14000e52c  nop     dword ptr [rax+rax+00h]
0x14000e531  mov     [rbx+450h], r12
0x14000e538  mov     rax, [rbx+260h]
0x14000e53f  mov     esi, 0FFFFFFFFh
0x14000e544  test    rax, rax
0x14000e547  jz      short loc_14000E5A1
0x14000e549  lea     rdi, [rax+8]
0x14000e54d  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14000e554  jnz     loc_14000E9ED
0x14000e55a  mov     r9d, esi
0x14000e55d  lock xadd [rdi], r9d
0x14000e562  dec     r9d
0x14000e565  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14000e56c  jnz     loc_14000EA0B
0x14000e572  mov     rdx, [rbx+260h]
0x14000e579  mov     eax, esi
0x14000e57b  add     rdx, 4; BugCheckParameter2
0x14000e57f  lock xadd [rdx], eax
0x14000e583  dec     eax
0x14000e585  cmp     cs:UxDebugCheckRefcount, r12b
0x14000e58c  jnz     loc_14000E855
0x14000e592  test    eax, eax
0x14000e594  jz      loc_14000EA26
0x14000e59a  mov     [rbx+260h], r12
0x14000e5a1  mov     rax, [rbx+268h]
0x14000e5a8  test    rax, rax
0x14000e5ab  jnz     loc_14000E7E4
0x14000e5b1  mov     rax, [rbx+270h]
0x14000e5b8  test    rax, rax
0x14000e5bb  jnz     loc_14000E7A9
0x14000e5c1  lea     rdi, [rbx+318h]
0x14000e5c8  mov     [rsp+0D8h+arg_8], rbp
0x14000e5d0  cmp     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x14000e5d5  mov     rbp, [rbx+448h]
0x14000e5dc  jnz     loc_14000EA68
0x14000e5e2  mov     rdx, [rdi+38h]
0x14000e5e6  test    rdx, rdx
0x14000e5e9  jnz     loc_14000EA83
0x14000e5ef  cmp     [rdi+2Ch], r12b
0x14000e5f3  jnz     short loc_14000E602
0x14000e5f5  mov     rcx, [rdi+20h]
0x14000e5f9  test    rcx, rcx
0x14000e5fc  jnz     loc_14000EA9C
0x14000e602  mov     rcx, [rdi+30h]; P
0x14000e606  mov     rbp, [rsp+0D8h+arg_8]
0x14000e60e  mov     [rdi+2Ch], r12w
0x14000e613  mov     [rdi+20h], r12
0x14000e617  mov     [rdi+28h], r12d
0x14000e61b  test    rcx, rcx
0x14000e61e  jnz     loc_14000EABD
0x14000e624  mov     [rdi+30h], r12
0x14000e628  mov     rcx, [rdi]
0x14000e62b  test    rcx, rcx
0x14000e62e  jnz     loc_14000EAD0
0x14000e634  mov     [rdi], r12
0x14000e637  mov     rcx, [rbx+1E8h]
0x14000e63e  test    rcx, rcx
0x14000e641  jz      short loc_14000E66B
0x14000e643  lea     rdx, [rcx+8]; BugCheckParameter2
0x14000e647  mov     eax, esi
0x14000e649  lock xadd [rdx], eax
0x14000e64d  dec     eax
0x14000e64f  cmp     cs:UxDebugCheckRefcount, r12b
0x14000e656  jnz     loc_14000E839
0x14000e65c  test    eax, eax
0x14000e65e  jz      loc_14000E953
0x14000e664  mov     [rbx+1E8h], r12
0x14000e66b  mov     rdi, [rbx+440h]
0x14000e672  lea     r8, [rsp+0D8h+var_A8]
0x14000e677  mov     edx, cs:UxPodMonitorSlot
0x14000e67d  mov     rcx, rdi
0x14000e680  mov     [rbx+448h], r12
0x14000e687  mov     [rsp+0D8h+var_A8], r12
0x14000e68c  call    cs:__imp_PsGetPermanentSiloContext
0x14000e693  nop     dword ptr [rax+rax+00h]
0x14000e698  test    rdi, rdi
0x14000e69b  jnz     loc_14000EAED
0x14000e6a1  mov     rdx, [rsp+0D8h+var_A8]
0x14000e6a6  add     rdx, 18h; BugCheckParameter2
0x14000e6aa  lock xadd [rdx], esi
0x14000e6ae  dec     esi
0x14000e6b0  cmp     cs:UxDebugCheckRefcount, r12b
0x14000e6b7  jnz     loc_14000E81C
0x14000e6bd  test    esi, esi
0x14000e6bf  jz      loc_14000EB06
0x14000e6c5  cmp     cs:UxDebugDisableLookaside, r12b
0x14000e6cc  mov     [rbx+440h], r12
0x14000e6d3  mov     dword ptr [rbx+10h], 63684C75h
0x14000e6da  jnz     loc_14000EB25
0x14000e6e0  cmp     cs:UxCompactMode, r12b
0x14000e6e7  jnz     loc_14000E8A9
0x14000e6ed  mov     edi, [rbx]
0x14000e6ef  mov     rcx, cs:qword_1401A03A0
0x14000e6f6  inc     edi
0x14000e6f8  shl     rdi, 7
0x14000e6fc  add     rdi, rcx
0x14000e6ff  movzx   eax, byte ptr [rdi+0B0h]
0x14000e706  test    al, al
0x14000e708  jz      loc_14000E945
0x14000e70e  mov     rdx, rbx; Entry
0x14000e711  lea     rcx, [rdi+40h]; Lookaside
0x14000e715  call    cs:__imp_ExFreeToLookasideListEx
0x14000e71c  nop     dword ptr [rax+rax+00h]
0x14000e721  test    r14, r14
0x14000e724  jz      short loc_14000E731
0x14000e726  mov     rcx, r15
0x14000e729  mov     rax, r14
0x14000e72c  call    _guard_dispatch_icall
0x14000e731  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x14000e738  jnz     loc_14000E8F7
0x14000e73e  mov     r14, [rsp+0D8h+var_20]
0x14000e746  mov     rsi, [rsp+0D8h+arg_10]
0x14000e74e  mov     r15, [rsp+0D8h+var_28]
0x14000e756  mov     rcx, [rsp+0D8h+var_38]
0x14000e75e  xor     rcx, rsp; StackCookie
0x14000e761  call    __security_check_cookie
0x14000e766  add     rsp, 0C0h
0x14000e76d  pop     r12
0x14000e76f  pop     rdi
0x14000e770  pop     rbx
0x14000e771  retn
0x14000e773  cmp     [rdx+8], rdi
0x14000e777  jnz     loc_14000E912
0x14000e77d  mov     rax, [rdx]
0x14000e780  cmp     [rax+8], rdx
0x14000e784  jnz     loc_14000E912
0x14000e78a  mov     [rdi], rax
0x14000e78d  mov     rcx, rbx
0x14000e790  mov     [rax+8], rdi
0x14000e794  mov     [rdx], r12
0x14000e797  mov     [rdx+8], r12
0x14000e79b  add     rdx, 0FFFFFFFFFFFFFFD0h
0x14000e79f  call    UlReleaseRequestBuffer
0x14000e7a4  jmp     loc_14000E45C
0x14000e7a9  lock dec dword ptr [rax+19Ch]
0x14000e7b0  mov     eax, esi
0x14000e7b2  mov     rdx, [rbx+270h]
0x14000e7b9  add     rdx, 4; BugCheckParameter2
0x14000e7bd  lock xadd [rdx], eax
0x14000e7c1  dec     eax
0x14000e7c3  cmp     cs:UxDebugCheckRefcount, r12b
0x14000e7ca  jnz     loc_14000E871
0x14000e7d0  test    eax, eax
0x14000e7d2  jz      loc_14000EA57
0x14000e7d8  mov     [rbx+270h], r12
0x14000e7df  jmp     loc_14000E5C1
0x14000e7e4  lock dec dword ptr [rax+1Ch]
0x14000e7e8  mov     eax, esi
0x14000e7ea  mov     rdx, [rbx+268h]
0x14000e7f1  add     rdx, 4; BugCheckParameter2
0x14000e7f5  lock xadd [rdx], eax
0x14000e7f9  dec     eax
0x14000e7fb  cmp     cs:UxDebugCheckRefcount, r12b
0x14000e802  jnz     loc_14000E88D
0x14000e808  test    eax, eax
0x14000e80a  jz      loc_14000EA46
0x14000e810  mov     [rbx+268h], r12
0x14000e817  jmp     loc_14000E5B1
0x14000e81c  cmp     esi, 0FFFFFFFFh
0x14000e81f  jg      loc_14000E6BD
0x14000e825  movsxd  r9, esi; BugCheckParameter4
0x14000e828  mov     ecx, 3; BugCheckParameter1
0x14000e82d  mov     r8d, 0Fh; BugCheckParameter3
0x14000e833  call    UlBugCheckEx
0x14000e839  cmp     eax, esi
0x14000e83b  jg      loc_14000E65C
0x14000e841  movsxd  r9, eax; BugCheckParameter4
0x14000e844  mov     ecx, 3; BugCheckParameter1
0x14000e849  mov     r8d, 0Ah; BugCheckParameter3
0x14000e84f  call    UlBugCheckEx
0x14000e855  cmp     eax, esi
0x14000e857  jg      loc_14000E592
0x14000e85d  movsxd  r9, eax; BugCheckParameter4
0x14000e860  mov     ecx, 3; BugCheckParameter1
0x14000e865  mov     r8d, 0Fh; BugCheckParameter3
0x14000e86b  call    UlBugCheckEx
0x14000e871  cmp     eax, esi
0x14000e873  jg      loc_14000E7D0
0x14000e879  movsxd  r9, eax; BugCheckParameter4
0x14000e87c  mov     ecx, 3; BugCheckParameter1
0x14000e881  mov     r8d, 0Fh; BugCheckParameter3
0x14000e887  call    UlBugCheckEx
0x14000e88d  cmp     eax, esi
0x14000e88f  jg      loc_14000E808
0x14000e895  movsxd  r9, eax; BugCheckParameter4
0x14000e898  mov     ecx, 3; BugCheckParameter1
0x14000e89d  mov     r8d, 0Fh; BugCheckParameter3
0x14000e8a3  call    UlBugCheckEx
0x14000e8a9  mov     rdi, cs:qword_1401A03A0
0x14000e8b0  call    cs:__imp_KeGetCurrentNodeNumber
0x14000e8b7  nop     dword ptr [rax+rax+00h]
0x14000e8bc  movzx   r8d, ax
0x14000e8c0  mov     rdx, rbx
0x14000e8c3  mov     rcx, rdi
0x14000e8c6  call    PplFreeToLookasideListProcessor
0x14000e8cb  jmp     loc_14000E721
0x14000e8d0  mov     rdi, cs:qword_1401A05B0
0x14000e8d7  call    cs:__imp_KeGetCurrentNodeNumber
0x14000e8de  nop     dword ptr [rax+rax+00h]
0x14000e8e3  movzx   r8d, ax
0x14000e8e7  mov     rdx, rsi
0x14000e8ea  mov     rcx, rdi
0x14000e8ed  call    PplFreeToLookasideListProcessor
0x14000e8f2  jmp     loc_14000E531
0x14000e8f7  mov     edx, 15h
0x14000e8fc  lea     r8, WPP_682cf469470432b235cb9a4961616e40_Traceguids
0x14000e903  mov     ecx, 408h
0x14000e908  call    WPP_SF_
0x14000e90d  jmp     loc_14000E73E
0x14000e912  mov     ecx, 3
0x14000e917  int     29h; Win8: RtlFailFast(ecx)
0x14000e919  mov     edx, 14h
0x14000e91e  lea     r8, WPP_682cf469470432b235cb9a4961616e40_Traceguids
0x14000e925  mov     ecx, 408h
0x14000e92a  mov     r9, rbx
0x14000e92d  call    WPP_SF_q
0x14000e932  jmp     loc_14000E44E
0x14000e937  lea     rdx, [rdi+40h]
0x14000e93b  call    PplpLazyInitializeLookasideList
0x14000e940  jmp     loc_14000E51E
0x14000e945  lea     rdx, [rdi+40h]
0x14000e949  call    PplpLazyInitializeLookasideList
0x14000e94e  jmp     loc_14000E70E
0x14000e953  cmp     [rcx+30h], r12
0x14000e957  lea     rdx, [rcx+30h]; BugCheckParameter2
0x14000e95b  jnz     short loc_14000E963
0x14000e95d  cmp     [rdx+10h], r12
0x14000e961  jz      short loc_14000E97B
0x14000e963  mov     r9d, 400h; BugCheckParameter4
0x14000e969  lea     r8, aMinioHttpSysTl; "minio\\http\\sys\\tl.h"
0x14000e970  mov     ecx, 1; BugCheckParameter1
0x14000e975  call    UlBugCheckEx
0x14000e97b  cmp     [rdx+20h], r12
0x14000e97f  jnz     short loc_14000E963
0x14000e981  mov     rax, [rcx+0C0h]
0x14000e988  lea     r8, UxTlDestroyListenEndpoint
0x14000e98f  xor     ecx, ecx
0x14000e991  mov     [rsp+0D8h+var_B0], 0FFFFFFFFh
0x14000e999  mov     r9b, 1
0x14000e99c  mov     [rsp+0D8h+var_B8], rax
0x14000e9a1  call    UlThreadPoolEnqueueWorkItem
0x14000e9a6  jmp     loc_14000E664
0x14000e9ab  mov     r14, r12
0x14000e9ae  mov     r15, r12
0x14000e9b1  jmp     loc_14000E49F
0x14000e9b6  mov     eax, cs:dword_1401A05C8
0x14000e9bc  lea     rdx, [rsp+0D8h+var_98]
0x14000e9c1  mov     [rsp+0D8h+var_70], eax
  ... truncated ...
```
