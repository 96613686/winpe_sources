# CallEventOutboundTunnelEstablished

- ea: `0x1400102fc`
- end: `0x14001096c`
- name: `CallEventOutboundTunnelEstablished`
- size: `1648`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140011d04`
- `0x140013954`

## callees

- `0x140001a70`
- `0x140002e78`
- `0x1400039f8`
- `0x140003d58`
- `0x140003d9c`
- `0x140003e08`
- `0x140003e38`
- `0x140003e7c`
- `0x140004374`
- `0x1400043e0`
- `0x140004468`
- `0x1400076d0`
- `0x140007ac0`
- `0x1400102fc`
- `0x140011b90`
- `0x140013164`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140010431`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010885`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010939`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010431`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010885`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010939`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001039b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001039b`
- `NDIS!NdisCancelTimerObject` at `0x140010469`
- `NDIS!NdisCancelTimerObject` at `0x140010469`

## pseudocode

```c
__int64 __fastcall CallEventOutboundTunnelEstablished(__int64 a1)
{
  __int64 v1; // r13
  char v2; // bl
  struct _DEVICE_OBJECT *AttachedDevice; // rdi
  int StringFromSockAddr; // eax
  int v5; // r8d
  KIRQL v6; // al
  __int64 v7; // r8
  __int64 v8; // r9
  unsigned int v9; // ebx
  void *v10; // rcx
  __int16 v11; // dx
  bool v12; // zf
  __int16 v13; // dx
  __int16 v14; // cx
  __int64 v15; // rdi
  const char *v16; // r8
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rcx
  __int16 v20; // bx
  int v21; // edi
  struct _DEVICE_OBJECT *v22; // rsi
  int v23; // eax
  int v24; // edx
  int v25; // r8d
  unsigned int v26; // eax
  __int64 v27; // r8
  BOOLEAN v29; // [rsp+A0h] [rbp-D8h]
  __int64 v31; // [rsp+C0h] [rbp-B8h]
  _BYTE v32[80]; // [rsp+D0h] [rbp-A8h] BYREF

  v1 = a1;
  memset(v32, 0, 0x41u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v2 = *(_BYTE *)(v1 + 192);
    AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
    StringFromSockAddr = GetStringFromSockAddr(v1 + 280, v32);
    WPP_SF_sd((_DWORD)AttachedDevice, 71, v5, StringFromSockAddr, v2);
  }
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 96));
  *(_BYTE *)(v1 + 104) = v6;
  if ( *(_BYTE *)(v1 + 192) || *(_DWORD *)(v1 + 112) != 7 )
  {
    v9 = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 96), v6);
  }
  else
  {
    v31 = CtlAllocPacket(*(_QWORD *)(v1 + 80), 7);
    if ( v31 )
    {
      LOBYTE(v8) = 1;
      CallSetState(v1, 8, v7, v8);
      v10 = *(void **)(v1 + 512);
      *(_DWORD *)(v1 + 116) = 2;
      v29 = NdisCancelTimerObject(v10);
      v11 = _InterlockedIncrement(&g_CallSerialNumber);
      v12 = PptpClientSide == 0;
      *(_WORD *)(v1 + 216) = v11;
      if ( v12 )
      {
        v14 = *(_WORD *)(v1 + 208);
      }
      else
      {
        v13 = *(_WORD *)(v1 + 200) + (v11 << 14);
        v14 = v13 + 0x4000;
        if ( *(_WORD *)(v1 + 320) != v13 )
          v14 = v13;
      }
      *(_WORD *)(v1 + 320) = v14;
      *(_WORD *)(v31 + 12) = __ROR2__(v14, 8);
      *(_WORD *)(v31 + 14) = __ROR2__(*(_WORD *)(v1 + 216), 8);
      v15 = -1;
      *(_DWORD *)(v31 + 32) = 0x4000;
      *(_DWORD *)(v31 + 24) = 50331648;
      v16 = (const char *)(v1 + 332);
      *(_DWORD *)(v31 + 28) = 50331648;
      v17 = -1;
      *(_DWORD *)(v31 + 16) = 738263040;
      *(_DWORD *)(v31 + 20) = 14808325;
      do
        ++v17;
      while ( v16[v17] );
      *(_WORD *)(v31 + 36) = __ROR2__(v17, 8);
      StringCbCopyA((STRSAFE_LPSTR)(v31 + 40), 0x40u, v16);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_s(
          WPP_GLOBAL_Control->AttachedDevice,
          73,
          WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids,
          *(_QWORD *)(v1 + 80) + 472LL);
      }
      do
        ++v15;
      while ( *(_BYTE *)(v15 + v1 + 397) );
      if ( v15 != 16 )
        goto LABEL_39;
      v18 = *(_QWORD *)(v1 + 80);
      v19 = *(_QWORD *)(v18 + 472) - 0x666F736F7263694DLL;
      if ( *(_QWORD *)(v18 + 472) == 0x666F736F7263694DLL )
        v19 = *(unsigned __int16 *)(v18 + 480) - 116LL;
      if ( v19 )
      {
LABEL_39:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 76, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids);
        }
      }
      else
      {
        *(_OWORD *)(v31 + 104) = *(_OWORD *)(v1 + 397);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_DDDDDDDDDDDDDDDD(
              WPP_GLOBAL_Control->AttachedDevice,
              74,
              (unsigned int)WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids,
              *(unsigned __int8 *)(a1 + 400),
              *(_BYTE *)(a1 + 399),
              *(_BYTE *)(a1 + 398),
              *(_BYTE *)(v1 + 397),
              *(_BYTE *)(v1 + 402),
              *(_BYTE *)(v1 + 401),
              *(_BYTE *)(v1 + 404),
              *(_BYTE *)(v1 + 403),
              *(_BYTE *)(v1 + 405),
              *(_BYTE *)(v1 + 406),
              *(_BYTE *)(v1 + 407),
              *(_BYTE *)(v1 + 408),
              *(_BYTE *)(v1 + 409),
              *(_BYTE *)(v1 + 410),
              *(_BYTE *)(v1 + 411),
              *(_BYTE *)(v1 + 412));
            v1 = a1;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_DDDDDDDDDDDDDDDD(
              WPP_GLOBAL_Control->AttachedDevice,
              75,
              (unsigned int)WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids,
              *(unsigned __int8 *)(a1 + 397),
              *(_BYTE *)(a1 + 398),
              *(_BYTE *)(a1 + 399),
              *(_BYTE *)(v1 + 400),
              *(_BYTE *)(v1 + 401),
              *(_BYTE *)(v1 + 402),
              *(_BYTE *)(v1 + 403),
              *(_BYTE *)(v1 + 404),
              *(_BYTE *)(v1 + 405),
              *(_BYTE *)(v1 + 406),
              *(_BYTE *)(v1 + 407),
              *(_BYTE *)(v1 + 408),
              *(_BYTE *)(v1 + 409),
              *(_BYTE *)(v1 + 410),
              *(_BYTE *)(v1 + 411),
              *(_BYTE *)(v1 + 412));
          }
        }
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), *(_BYTE *)(a1 + 104));
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v20 = *(_WORD *)(a1 + 320);
        v21 = *(_DWORD *)(a1 + 200);
        v22 = WPP_GLOBAL_Control->AttachedDevice;
        v23 = GetStringFromSockAddr(a1 + 280, v32);
        WPP_SF_sdd((_DWORD)v22, v24, v25, v23, v21, v20);
      }
      v26 = CtlSend(*(_QWORD *)(a1 + 80), v31);
      v9 = v26;
      if ( v26 != 259 && v26 )
      {
        CallSetState(a1, 11, v27, 0);
        CallCleanup(a1);
      }
      if ( v29 )
        DereferenceRefCount(a1);
    }
    else
    {
      v9 = -1073741670;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          72,
          WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids,
          *(unsigned int *)(v1 + 200));
      }
      LOBYTE(v8) = 1;
      CallSetState(v1, 11, v7, v8);
      KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 96), *(_BYTE *)(v1 + 104));
      CallCleanup(v1);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x1400102fc  push    rbx
0x1400102fe  push    rbp
0x1400102ff  push    rsi
0x140010300  push    rdi
0x140010301  push    r12
0x140010303  push    r13
0x140010305  push    r14
0x140010307  push    r15
0x140010309  sub     rsp, 138h
0x140010310  mov     rax, cs:__security_cookie
0x140010317  xor     rax, rsp
0x14001031a  mov     [rsp+178h+var_58], rax
0x140010322  xor     edx, edx; Val
0x140010324  mov     [rsp+178h+var_C8], rcx
0x14001032c  mov     r13, rcx
0x14001032f  lea     rcx, [rsp+178h+var_A8]; void *
0x140010337  lea     r8d, [rdx+41h]; Size
0x14001033b  call    memset
0x140010340  mov     rdi, cs:WPP_GLOBAL_Control
0x140010347  lea     rbp, WPP_GLOBAL_Control
0x14001034e  cmp     rdi, rbp
0x140010351  jz      short loc_140010394
0x140010353  mov     eax, [rdi+2Ch]
0x140010356  test    al, 8
0x140010358  jz      short loc_140010394
0x14001035a  cmp     byte ptr [rdi+29h], 2
0x14001035e  jb      short loc_140010394
0x140010360  movzx   ebx, byte ptr [r13+0C0h]
0x140010368  lea     rcx, [r13+118h]
0x14001036f  mov     rdi, [rdi+18h]
0x140010373  lea     rdx, [rsp+178h+var_A8]
0x14001037b  call    GetStringFromSockAddr
0x140010380  mov     r9, rax
0x140010383  mov     [rsp+178h+var_158], ebx
0x140010387  mov     edx, 47h ; 'G'
0x14001038c  mov     rcx, rdi
0x14001038f  call    WPP_SF_sd
0x140010394  lea     rdi, [r13+60h]
0x140010398  mov     rcx, rdi; SpinLock
0x14001039b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400103a2  nop     dword ptr [rax+rax+00h]
0x1400103a7  xor     esi, esi
0x1400103a9  mov     [r13+68h], al
0x1400103ad  cmp     [r13+0C0h], sil
0x1400103b4  jnz     loc_140010932
0x1400103ba  lea     edx, [rsi+7]
0x1400103bd  cmp     [r13+70h], edx
0x1400103c1  jnz     loc_140010932
0x1400103c7  mov     rcx, [r13+50h]
0x1400103cb  call    CtlAllocPacket
0x1400103d0  mov     [rsp+178h+var_B8], rax
0x1400103d8  mov     rbx, rax
0x1400103db  test    rax, rax
0x1400103de  jnz     short loc_14001044A
0x1400103e0  mov     ebx, 0C000009Ah
0x1400103e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400103ec  cmp     rcx, rbp
0x1400103ef  jz      short loc_14001041A
0x1400103f1  test    dword ptr [rcx+2Ch], 100h
0x1400103f8  jz      short loc_14001041A
0x1400103fa  cmp     byte ptr [rcx+29h], 1
0x1400103fe  jb      short loc_14001041A
0x140010400  mov     r9d, [r13+0C8h]
0x140010407  lea     edx, [rsi+48h]
0x14001040a  mov     rcx, [rcx+18h]
0x14001040e  lea     r8, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids
0x140010415  call    WPP_SF_d
0x14001041a  mov     r9b, 1
0x14001041d  mov     edx, 0Bh
0x140010422  mov     rcx, r13
0x140010425  call    CallSetState
0x14001042a  mov     dl, [r13+68h]; NewIrql
0x14001042e  mov     rcx, rdi; SpinLock
0x140010431  call    cs:__imp_KeReleaseSpinLock
0x140010438  nop     dword ptr [rax+rax+00h]
0x14001043d  mov     rcx, r13
0x140010440  call    CallCleanup
0x140010445  jmp     loc_140010945
0x14001044a  mov     r9b, 1
0x14001044d  mov     edx, 8
0x140010452  mov     rcx, r13
0x140010455  call    CallSetState
0x14001045a  mov     rcx, [r13+200h]; TimerObject
0x140010461  mov     dword ptr [r13+74h], 2
0x140010469  call    cs:__imp_NdisCancelTimerObject
0x140010470  nop     dword ptr [rax+rax+00h]
0x140010475  mov     [rsp+178h+var_D8], al
0x14001047c  mov     edx, 1
0x140010481  lock xadd cs:g_CallSerialNumber, edx
0x140010489  inc     edx
0x14001048b  mov     r8d, 4000h
0x140010491  cmp     cs:PptpClientSide, sil
0x140010498  mov     [r13+0D8h], dx
0x1400104a0  jz      short loc_1400104C3
0x1400104a2  movzx   edx, dx
0x1400104a5  imul    edx, r8d
0x1400104a9  add     dx, [r13+0C8h]
0x1400104b1  cmp     [r13+140h], dx
0x1400104b9  lea     ecx, [r8+rdx]
0x1400104bd  cmovnz  cx, dx
0x1400104c1  jmp     short loc_1400104CB
0x1400104c3  movzx   ecx, word ptr [r13+0D0h]
0x1400104cb  mov     [r13+140h], cx
0x1400104d3  ror     cx, 8
0x1400104d7  mov     [rbx+0Ch], cx
0x1400104db  movzx   eax, word ptr [r13+0D8h]
0x1400104e3  ror     ax, 8
0x1400104e7  mov     [rbx+0Eh], ax
0x1400104eb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400104ef  mov     eax, 3000000h
0x1400104f4  mov     [rbx+20h], r8d
0x1400104f8  mov     [rbx+18h], eax
0x1400104fb  lea     r8, [r13+14Ch]; pszSrc
0x140010502  mov     [rbx+1Ch], eax
0x140010505  mov     rax, rdi
0x140010508  mov     dword ptr [rbx+10h], 2C010000h
0x14001050f  mov     dword ptr [rbx+14h], 0E1F505h
0x140010516  inc     rax
0x140010519  cmp     [r8+rax], sil
0x14001051d  jnz     short loc_140010516
0x14001051f  ror     ax, 8
0x140010523  lea     rcx, [rbx+28h]; pszDest
0x140010527  mov     edx, 40h ; '@'; cbDest
0x14001052c  mov     [rbx+24h], ax
0x140010530  call    StringCbCopyA
0x140010535  mov     rcx, cs:WPP_GLOBAL_Control
0x14001053c  mov     r14d, 1D8h
0x140010542  cmp     rcx, rbp
0x140010545  jz      short loc_140010570
0x140010547  mov     eax, [rcx+2Ch]
0x14001054a  test    al, 8
0x14001054c  jz      short loc_140010570
0x14001054e  cmp     byte ptr [rcx+29h], 2
0x140010552  jb      short loc_140010570
0x140010554  mov     r9, [r13+50h]
0x140010558  lea     r8, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids
0x14001055f  mov     rcx, [rcx+18h]
0x140010563  add     r9, r14
0x140010566  mov     edx, 49h ; 'I'
0x14001056b  call    WPP_SF_s
0x140010570  inc     rdi
0x140010573  cmp     [rdi+r13+18Dh], sil
0x14001057b  jnz     short loc_140010570
0x14001057d  cmp     rdi, 10h
0x140010581  jnz     loc_140010848
0x140010587  mov     rax, [r13+50h]
0x14001058b  mov     rdx, 666F736F7263694Dh
0x140010595  mov     rcx, [rax+r14]
0x140010599  sub     rcx, rdx
0x14001059c  jnz     short loc_1400105AD
0x14001059e  movzx   ecx, word ptr [rax+r14+8]
0x1400105a4  lea     eax, [rdi+64h]
0x1400105a7  movzx   eax, ax
0x1400105aa  sub     rcx, rax
0x1400105ad  test    rcx, rcx
0x1400105b0  jnz     loc_140010848
0x1400105b6  movups  xmm0, xmmword ptr [r13+18Dh]
0x1400105be  movdqu  xmmword ptr [rbx+68h], xmm0
0x1400105c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400105ca  mov     [rsp+178h+var_C0], rcx
0x1400105d2  cmp     rcx, rbp
0x1400105d5  jz      loc_140010876
0x1400105db  mov     eax, [rcx+2Ch]
0x1400105de  test    al, 10h
0x1400105e0  jz      loc_14001070C
0x1400105e6  cmp     byte ptr [rcx+29h], 2
0x1400105ea  jb      loc_14001070C
0x1400105f0  movzx   eax, byte ptr [r13+19Ch]
0x1400105f8  movzx   ecx, byte ptr [r13+19Bh]
0x140010600  movzx   r8d, byte ptr [r13+19Ah]
0x140010608  mov     r9, [rsp+178h+var_C8]
0x140010610  movzx   r10d, byte ptr [r13+199h]
0x140010618  movzx   r11d, byte ptr [r13+198h]
0x140010620  movzx   ebx, byte ptr [r13+197h]
0x140010628  movzx   edx, byte ptr [r9+18Eh]
0x140010630  movzx   edi, byte ptr [r13+196h]
0x140010638  movzx   esi, byte ptr [r13+195h]
0x140010640  movzx   ebp, byte ptr [r13+193h]
0x140010648  movzx   r14d, byte ptr [r13+194h]
0x140010650  movzx   r15d, byte ptr [r13+191h]
0x140010658  movzx   r12d, byte ptr [r13+192h]
0x140010660  movzx   r13d, byte ptr [r13+18Dh]
0x140010668  mov     [rsp+178h+var_E8], eax
0x14001066f  mov     [rsp+178h+var_F0], ecx
0x140010676  mov     rcx, [rsp+178h+var_C0]
0x14001067e  mov     [rsp+178h+var_F8], r8d
0x140010686  lea     r8, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids
0x14001068d  mov     [rsp+178h+var_100], r10d
0x140010692  mov     [rsp+178h+var_108], r11d
0x140010697  mov     rcx, [rcx+18h]
0x14001069b  mov     [rsp+178h+var_110], ebx
0x14001069f  mov     [rsp+178h+var_118], edi
0x1400106a3  mov     [rsp+178h+var_120], esi
0x1400106a7  mov     [rsp+178h+var_128], ebp
0x1400106ab  mov     [rsp+178h+var_130], r14d
0x1400106b0  mov     [rsp+178h+var_D4], edx
0x1400106b7  movzx   edx, byte ptr [r9+18Fh]
0x1400106bf  mov     eax, [rsp+178h+var_D4]
0x1400106c6  movzx   r9d, byte ptr [r9+190h]
0x1400106ce  mov     [rsp+178h+var_138], r15d
0x1400106d3  mov     [rsp+178h+var_140], r12d
0x1400106d8  mov     [rsp+178h+var_D0], edx
0x1400106df  mov     edx, 4Ah ; 'J'
0x1400106e4  mov     [rsp+178h+var_148], r13d
0x1400106e9  mov     [rsp+178h+var_150], eax
0x1400106ed  mov     eax, [rsp+178h+var_D0]
0x1400106f4  mov     [rsp+178h+var_158], eax
0x1400106f8  call    WPP_SF_DDDDDDDDDDDDDDDD
0x1400106fd  mov     r13, [rsp+178h+var_C8]
0x140010705  lea     rbp, WPP_GLOBAL_Control
0x14001070c  mov     rcx, cs:WPP_GLOBAL_Control
0x140010713  mov     [rsp+178h+var_C0], rcx
0x14001071b  cmp     rcx, rbp
0x14001071e  jz      loc_140010876
0x140010724  mov     eax, [rcx+2Ch]
0x140010727  test    al, 8
0x140010729  jz      loc_140010876
0x14001072f  cmp     byte ptr [rcx+29h], 2
0x140010733  jb      loc_140010876
0x140010739  movzx   eax, byte ptr [r13+19Ch]
0x140010741  movzx   ecx, byte ptr [r13+19Bh]
0x140010749  movzx   r8d, byte ptr [r13+19Ah]
0x140010751  mov     r9, [rsp+178h+var_C8]
0x140010759  movzx   r10d, byte ptr [r13+199h]
0x140010761  movzx   r11d, byte ptr [r13+198h]
0x140010769  movzx   ebx, byte ptr [r13+197h]
0x140010771  movzx   edx, byte ptr [r9+18Fh]
0x140010779  movzx   edi, byte ptr [r13+196h]
0x140010781  movzx   esi, byte ptr [r13+195h]
0x140010789  movzx   ebp, byte ptr [r13+194h]
0x140010791  movzx   r14d, byte ptr [r13+193h]
0x140010799  movzx   r15d, byte ptr [r13+192h]
0x1400107a1  movzx   r12d, byte ptr [r13+191h]
0x1400107a9  movzx   r13d, byte ptr [r13+190h]
0x1400107b1  mov     [rsp+178h+var_E8], eax
0x1400107b8  mov     [rsp+178h+var_F0], ecx
0x1400107bf  mov     rcx, [rsp+178h+var_C0]
0x1400107c7  mov     [rsp+178h+var_F8], r8d
0x1400107cf  lea     r8, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids
0x1400107d6  mov     [rsp+178h+var_100], r10d
0x1400107db  mov     [rsp+178h+var_108], r11d
0x1400107e0  mov     rcx, [rcx+18h]
0x1400107e4  mov     [rsp+178h+var_110], ebx
0x1400107e8  mov     [rsp+178h+var_118], edi
0x1400107ec  mov     [rsp+178h+var_120], esi
0x1400107f0  mov     [rsp+178h+var_128], ebp
0x1400107f4  mov     [rsp+178h+var_130], r14d
0x1400107f9  mov     [rsp+178h+var_D0], edx
0x140010800  movzx   edx, byte ptr [r9+18Eh]
0x140010808  mov     eax, [rsp+178h+var_D0]
0x14001080f  movzx   r9d, byte ptr [r9+18Dh]
0x140010817  mov     [rsp+178h+var_138], r15d
0x14001081c  mov     [rsp+178h+var_140], r12d
0x140010821  mov     [rsp+178h+var_D4], edx
0x140010828  mov     edx, 4Bh ; 'K'
0x14001082d  mov     [rsp+178h+var_148], r13d
0x140010832  mov     [rsp+178h+var_150], eax
0x140010836  mov     eax, [rsp+178h+var_D4]
0x14001083d  mov     [rsp+178h+var_158], eax
0x140010841  call    WPP_SF_DDDDDDDDDDDDDDDD
0x140010846  jmp     short loc_140010876
0x140010848  mov     rcx, cs:WPP_GLOBAL_Control
0x14001084f  cmp     rcx, rbp
0x140010852  jz      short loc_140010876
0x140010854  mov     eax, [rcx+2Ch]
0x140010857  test    al, 8
0x140010859  jz      short loc_140010876
0x14001085b  cmp     byte ptr [rcx+29h], 2
0x14001085f  jb      short loc_140010876
0x140010861  mov     rcx, [rcx+18h]
0x140010865  lea     r8, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids
0x14001086c  mov     edx, 4Ch ; 'L'
0x140010871  call    WPP_SF_
0x140010876  mov     rbp, [rsp+178h+var_C8]
0x14001087e  mov     dl, [rbp+68h]; NewIrql
0x140010881  lea     rcx, [rbp+60h]; SpinLock
0x140010885  call    cs:__imp_KeReleaseSpinLock
0x14001088c  nop     dword ptr [rax+rax+00h]
0x140010891  mov     rsi, cs:WPP_GLOBAL_Control
0x140010898  lea     rax, WPP_GLOBAL_Control
0x14001089f  cmp     rsi, rax
0x1400108a2  jz      short loc_1400108E9
0x1400108a4  mov     eax, [rsi+2Ch]
0x1400108a7  test    al, 8
0x1400108a9  jz      short loc_1400108E9
0x1400108ab  cmp     byte ptr [rsi+29h], 2
0x1400108af  jb      short loc_1400108E9
0x1400108b1  movzx   ebx, word ptr [rbp+140h]
0x1400108b8  lea     rcx, [rbp+118h]
0x1400108bf  mov     edi, [rbp+0C8h]
0x1400108c5  lea     rdx, [rsp+178h+var_A8]
0x1400108cd  mov     rsi, [rsi+18h]
0x1400108d1  call    GetStringFromSockAddr
0x1400108d6  mov     r9, rax
0x1400108d9  mov     [rsp+178h+var_150], ebx
0x1400108dd  mov     rcx, rsi
0x1400108e0  mov     [rsp+178h+var_158], edi
0x1400108e4  call    WPP_SF_sdd
0x1400108e9  mov     rdx, [rsp+178h+var_B8]
0x1400108f1  mov     rcx, [rbp+50h]
  ... truncated ...
```
