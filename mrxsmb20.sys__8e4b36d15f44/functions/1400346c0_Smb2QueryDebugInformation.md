# Smb2QueryDebugInformation

- ea: `0x1400346c0`
- end: `0x140034c9b`
- name: `Smb2QueryDebugInformation`
- size: `1499`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14001cc00`

## callees

- `0x1400040a0`
- `0x140004640`
- `0x140012210`
- `0x1400122d0`
- `0x1400346c0`
- `0x140037120`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140034c52`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140034c52`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140034ac4`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x140034ac4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140034a76`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140034a76`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003484d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003484d`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x1400347ea`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x1400347ea`
- `mrxsmb!MRxSmbCheckDevFcbXXXControlFileAccess` at `0x140034782`
- `mrxsmb!MRxSmbCheckDevFcbXXXControlFileAccess` at `0x140034782`

## pseudocode

```c
__int64 __fastcall Smb2QueryDebugInformation(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rax
  __int64 v4; // rdx
  __int64 v5; // r10
  __int64 v6; // r15
  unsigned int v7; // ebx
  bool v8; // zf
  __int64 v9; // r9
  __int64 v10; // r13
  __int64 v11; // r12
  volatile LONG *v12; // r8
  int v13; // esi
  unsigned int v14; // r12d
  __int64 v15; // rsi
  __int64 v16; // r15
  _QWORD *v17; // rax
  __int64 v18; // r13
  char v19; // al
  __int64 v20; // rcx
  unsigned __int64 v21; // rdx
  __int64 v22; // rcx
  _QWORD *v23; // rcx
  volatile LONG *v24; // rcx
  __int64 v25; // rsi
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  PEX_SPIN_LOCK v30; // r15
  KIRQL v31; // r12
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 FirstBindingObject; // rax
  __int64 v36; // rcx
  KIRQL OldIrql; // [rsp+40h] [rbp-39h]
  _DWORD *v39; // [rsp+48h] [rbp-31h] BYREF
  PEX_SPIN_LOCK SpinLock; // [rsp+50h] [rbp-29h]
  _QWORD *v41; // [rsp+58h] [rbp-21h]
  _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+60h] [rbp-19h] BYREF
  _OWORD v43[2]; // [rsp+78h] [rbp-1h] BYREF
  __int64 v44; // [rsp+98h] [rbp+1Fh]

  v44 = 0;
  v2 = *(_QWORD *)(a1 + 56);
  memset(v43, 0, sizeof(v43));
  v3 = *(_QWORD *)(v2 + 120);
  if ( !v3 )
    return (unsigned int)-1073741811;
  v4 = *(_QWORD *)(a1 + 72);
  if ( !v4 )
    return (unsigned int)-1073741811;
  v5 = *(_QWORD *)(v3 + 40);
  if ( !v5 )
    return (unsigned int)-1073741811;
  v6 = *(_QWORD *)(v4 + 48);
  if ( !v6 )
    return (unsigned int)-1073741811;
  v7 = 0;
  v8 = *(_DWORD *)(a1 + 568) == 4;
  v9 = *(_QWORD *)(*(_QWORD *)(v4 + 40) + 40LL);
  v39 = (_DWORD *)v9;
  v10 = *(_QWORD *)(v9 + 416);
  v11 = *(_QWORD *)(v10 + 384);
  v41 = (_QWORD *)v11;
  v12 = *(volatile LONG **)(v11 + 24);
  SpinLock = v12;
  if ( v8 )
  {
    v13 = **(_DWORD **)(a1 + 552);
    if ( v13 != -65536 )
    {
      if ( (int)MRxSmbCheckDevFcbXXXControlFileAccess(1) < 0 )
        return (unsigned int)-1073741790;
      if ( v13 == -536870911 )
      {
        if ( *(_DWORD *)(a1 + 572) >= 0x40u )
        {
          v22 = *(_QWORD *)(a1 + 560);
          *(_QWORD *)(v22 + 24) = *(_QWORD *)(v6 + 248);
          *(_DWORD *)(v22 + 16) = *(_DWORD *)(v6 + 44);
          *(_DWORD *)(v22 + 8) = *(_DWORD *)(v6 + 8);
          *(_QWORD *)(v22 + 32) = *(_QWORD *)(v6 + 28);
          *(_DWORD *)(v22 + 48) = 1;
          *(_QWORD *)(v22 + 56) = *(_QWORD *)(v6 + 256);
          *(_DWORD *)(v22 + 12) = *(_DWORD *)(v6 + 4);
          *(_QWORD *)v22 = (unsigned __int64)Smb2QueryDebugInformation ^ v6;
          *(_QWORD *)(v22 + 40) = *(_QWORD *)(v6 + 36);
          *(_QWORD *)(a1 + 184) = 64;
          return v7;
        }
      }
      else
      {
        if ( v13 != -536870904 )
          return v7;
        if ( *(_DWORD *)(a1 + 572) >= 0x70u )
        {
          v20 = *(_QWORD *)(a1 + 560);
          v21 = (unsigned __int64)v39;
          *(_QWORD *)(v20 + 56) = (unsigned __int64)Smb2QueryDebugInformation ^ v11;
          *(_DWORD *)(v20 + 100) = *(_DWORD *)(v11 + 716);
          *(_DWORD *)(v20 + 68) = *(_DWORD *)(v11 + 392);
          *(_BYTE *)(v20 + 104) = *(_BYTE *)(v11 + 736) & 1;
          *(_BYTE *)(v20 + 106) = (*(_BYTE *)(v11 + 736) & 4) != 0;
          *(_BYTE *)(v20 + 105) = (*(_BYTE *)(v11 + 736) & 2) != 0;
          *(_DWORD *)(v20 + 88) = *(_DWORD *)(v11 + 704);
          *(_DWORD *)(v20 + 96) = *(_DWORD *)(v11 + 712);
          *(_DWORD *)(v20 + 92) = *(_DWORD *)(v11 + 708);
          *(_OWORD *)(v20 + 72) = *(_OWORD *)(v11 + 656);
          *(_DWORD *)(v20 + 64) = *(_DWORD *)(v11 + 12);
          *(_QWORD *)(v20 + 24) = (unsigned __int64)Smb2QueryDebugInformation ^ v10;
          *(_DWORD *)(v20 + 36) = *(_DWORD *)(v10 + 264);
          *(_QWORD *)(v20 + 48) = *(_QWORD *)(v10 + 600);
          *(_QWORD *)(v20 + 40) = *(_QWORD *)(v10 + 440);
          *(_DWORD *)(v20 + 32) = *(_DWORD *)(v10 + 12);
          *(_QWORD *)v20 = (unsigned __int64)Smb2QueryDebugInformation ^ v21;
          *(_DWORD *)(v20 + 12) = *(_DWORD *)(v21 + 264);
          *(_DWORD *)(v20 + 8) = *(_DWORD *)(v21 + 12);
          *(_DWORD *)(v20 + 16) = *(_DWORD *)(v21 + 436);
          *(_QWORD *)(a1 + 184) = 112;
          return v7;
        }
      }
      return (unsigned int)-1073741789;
    }
    v14 = *(_DWORD *)(a1 + 572);
    if ( v14 < 0x50 )
      return (unsigned int)-1073741789;
    v15 = *(_QWORD *)(a1 + 560);
    SpinLock = v12 + 480;
    OldIrql = ExAcquireSpinLockShared(v12 + 480);
    v16 = 0;
    v17 = v41 + 77;
    v41 = v17;
    if ( (_QWORD *)*v17 != v17 )
      v16 = *v17 - 536LL;
    while ( v16 )
    {
      memset(&LockHandle, 0, sizeof(LockHandle));
      if ( v14 < 0x50 )
      {
        v7 = -2147483643;
        break;
      }
      v18 = *(_QWORD *)(v16 + 512);
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v18 + 256), &LockHandle);
      *(_DWORD *)v15 = *(_DWORD *)(v18 + 80);
      *(_DWORD *)(v15 + 4) = *(_DWORD *)(v18 + 84);
      *(_DWORD *)(v15 + 12) = *(_DWORD *)(v18 + 96);
      *(_DWORD *)(v15 + 8) = *(_DWORD *)(v18 + 144);
      if ( *(_DWORD *)(v16 + 320) <= 1u )
      {
        *(_QWORD *)(v15 + 32) = *(_QWORD *)(v16 + 280);
        *(_QWORD *)(v15 + 40) = *(_QWORD *)(v16 + 272);
        *(_BYTE *)(v15 + 48) = *(_BYTE *)(v16 + 292);
        v19 = *(_BYTE *)(v16 + 293);
      }
      else
      {
        v19 = 0;
        *(_QWORD *)(v15 + 32) = 0;
        *(_QWORD *)(v15 + 40) = 0;
        *(_BYTE *)(v15 + 48) = 0;
      }
      *(_BYTE *)(v15 + 49) = v19;
      *(_QWORD *)(v15 + 16) = *(_QWORD *)(v18 + 64);
      *(_QWORD *)(v15 + 24) = *(_QWORD *)(v18 + 72);
      *(_QWORD *)(v15 + 56) = *(_QWORD *)(v16 + 296);
      *(_QWORD *)(v15 + 64) = *(_QWORD *)(v16 + 304);
      *(_QWORD *)(v15 + 72) = *(_QWORD *)(v16 + 312);
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      v23 = *(_QWORD **)(v16 + 536);
      v14 -= 80;
      v16 = 0;
      v15 += 80;
      if ( v23 != v41 )
        v16 = (__int64)(v23 - 67);
    }
    v24 = SpinLock;
    *(_QWORD *)(a1 + 184) = *(_DWORD *)(a1 + 572) - v14;
    ExReleaseSpinLockShared(v24, OldIrql);
  }
  else
  {
    if ( *(_DWORD *)(a1 + 572) < 0x38u )
      return (unsigned int)-1073741789;
    v25 = *(_QWORD *)(a1 + 560);
    *(_OWORD *)v25 = 0;
    *(_OWORD *)(v25 + 16) = 0;
    *(_OWORD *)(v25 + 32) = 0;
    *(_QWORD *)(v25 + 48) = 0;
    *(_WORD *)v25 = 514;
    *(_WORD *)(v25 + 2) = *(_WORD *)(v6 + 24);
    *(_DWORD *)(v25 + 4) = *(_DWORD *)(v6 + 44);
    *(_DWORD *)(v25 + 8) = *(_DWORD *)(v9 + 264);
    *(_QWORD *)(v25 + 16) = *(_QWORD *)(v6 + 36);
    *(_QWORD *)(v25 + 24) = *(_QWORD *)(v6 + 28);
    *(_QWORD *)(v25 + 32) = *(_QWORD *)(v10 + 440);
    *(_BYTE *)(v25 + 48) = *(_BYTE *)(v2 + 282);
    if ( (*(_DWORD *)(v4 + 72) & 0x100000) != 0 )
      *(_BYTE *)(v25 + 46) = 1;
    if ( (*(_DWORD *)(v2 + 160) & 0x8000000) != 0 )
      *(_BYTE *)(v25 + 40) = 1;
    if ( (*(_DWORD *)(v2 + 160) & 0x2000000) != 0 )
      *(_BYTE *)(v25 + 41) = 1;
    if ( (*(_DWORD *)(v2 + 160) & 0x200000) != 0 )
      *(_BYTE *)(v25 + 42) = 1;
    if ( (*(_DWORD *)(v2 + 160) & 0x800) != 0 )
      *(_BYTE *)(v25 + 43) = 1;
    LODWORD(v39) = 40;
    if ( (unsigned int)Smb2FetchFileInfoFromCache(a1, v5 + 376, 1, 4, 0, v43, &v39) != -1073741802 )
      *(_BYTE *)(v25 + 44) = 1;
    LODWORD(v39) = 40;
    if ( !(unsigned int)Smb2QueryFileInformationFromDirCache(a1, v26, 0, 4, v43, &v39) )
      *(_BYTE *)(v25 + 45) = 1;
    if ( !*(_DWORD *)(v10 + 12) )
    {
      v30 = SpinLock;
      v31 = SmbCeAcquireSpinLock(SpinLock, v27, v28, v29);
      FirstBindingObject = SmbCeGetFirstBindingObjectEx(v10, v32, v33, v34);
      if ( FirstBindingObject )
      {
        v36 = *(_QWORD *)(FirstBindingObject + 392);
        if ( v36 )
          *(_BYTE *)(v25 + 47) = *(_DWORD *)(v36 + 320) == 1;
      }
      *(_DWORD *)(v25 + 52) = *(_DWORD *)(v10 + 88);
      *((_DWORD *)v30 + 588) = -1;
      ExReleaseSpinLockExclusive(v30 + 480, v31);
    }
    *(_QWORD *)(a1 + 184) = 56;
  }
  return v7;
}

```

## disassembly

```asm
0x1400346c0  mov     [rsp-8+arg_8], rbx
0x1400346c5  mov     [rsp-8+arg_10], rsi
0x1400346ca  push    rbp
0x1400346cb  push    rdi
0x1400346cc  push    r12
0x1400346ce  push    r13
0x1400346d0  push    r15
0x1400346d2  lea     rbp, [rsp-37h]
0x1400346d7  sub     rsp, 0B0h
0x1400346de  mov     rax, cs:__security_cookie
0x1400346e5  xor     rax, rsp
0x1400346e8  mov     [rbp+57h+var_30], rax
0x1400346ec  xor     edx, edx
0x1400346ee  xorps   xmm0, xmm0
0x1400346f1  mov     rdi, rcx
0x1400346f4  mov     [rbp+57h+var_38], rdx
0x1400346f8  mov     rcx, [rcx+38h]
0x1400346fc  movups  [rbp+57h+var_58], xmm0
0x140034700  movups  [rbp+57h+var_48], xmm0
0x140034704  mov     rax, [rcx+78h]
0x140034708  test    rax, rax
0x14003470b  jz      loc_140034C6B
0x140034711  mov     rdx, [rdi+48h]
0x140034715  test    rdx, rdx
0x140034718  jz      loc_140034C6B
0x14003471e  mov     r10, [rax+28h]
0x140034722  test    r10, r10
0x140034725  jz      loc_140034C6B
0x14003472b  mov     r15, [rdx+30h]
0x14003472f  test    r15, r15
0x140034732  jz      loc_140034C6B
0x140034738  mov     rax, [rdx+28h]
0x14003473c  xor     ebx, ebx
0x14003473e  cmp     dword ptr [rdi+238h], 4
0x140034745  mov     r9, [rax+28h]
0x140034749  mov     [rbp+57h+var_88], r9
0x14003474d  mov     r13, [r9+1A0h]
0x140034754  mov     r12, [r13+180h]
0x14003475b  mov     [rbp+57h+var_78], r12
0x14003475f  mov     r8, [r12+18h]
0x140034764  mov     [rbp+57h+SpinLock], r8
0x140034768  jnz     loc_140034AD5
0x14003476e  mov     rax, [rdi+228h]
0x140034775  mov     esi, [rax]
0x140034777  cmp     esi, 0FFFF0000h
0x14003477d  jz      short loc_1400347C4
0x14003477f  lea     ecx, [rbx+1]
0x140034782  call    cs:__imp_MRxSmbCheckDevFcbXXXControlFileAccess
0x140034789  nop     dword ptr [rax+rax+00h]
0x14003478e  test    eax, eax
0x140034790  jns     short loc_14003479C
0x140034792  mov     ebx, 0C0000022h
0x140034797  jmp     loc_140034C70
0x14003479c  cmp     esi, 0E0000001h
0x1400347a2  jz      loc_14003499B
0x1400347a8  cmp     esi, 0E0000008h
0x1400347ae  jz      loc_140034897
0x1400347b4  cmp     esi, 0FFFF0000h
0x1400347ba  jnz     loc_140034C70
0x1400347c0  mov     r8, [rbp+57h+SpinLock]
0x1400347c4  mov     r12d, [rdi+23Ch]
0x1400347cb  cmp     r12d, 50h ; 'P'
0x1400347cf  jb      loc_1400349A4
0x1400347d5  mov     rsi, [rdi+230h]
0x1400347dc  lea     r13, [r8+780h]
0x1400347e3  mov     rcx, r13; SpinLock
0x1400347e6  mov     [rbp+57h+SpinLock], r13
0x1400347ea  call    cs:__imp_ExAcquireSpinLockShared
0x1400347f1  nop     dword ptr [rax+rax+00h]
0x1400347f6  mov     [rbp+57h+OldIrql], al
0x1400347f9  xor     r15d, r15d
0x1400347fc  mov     rax, [rbp+57h+var_78]
0x140034800  add     rax, 268h
0x140034806  mov     [rbp+57h+var_78], rax
0x14003480a  mov     rdx, [rax]
0x14003480d  cmp     rdx, rax
0x140034810  lea     rcx, [rdx-218h]
0x140034817  cmovnz  r15, rcx
0x14003481b  test    r15, r15
0x14003481e  jz      loc_140034AAD
0x140034824  xor     eax, eax
0x140034826  xorps   xmm0, xmm0
0x140034829  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x14003482d  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x140034831  cmp     r12d, 50h ; 'P'
0x140034835  jb      loc_140034AA8
0x14003483b  mov     r13, [r15+200h]
0x140034842  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x140034846  lea     rcx, [r13+100h]; SpinLock
0x14003484d  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140034854  nop     dword ptr [rax+rax+00h]
0x140034859  mov     eax, [r13+50h]
0x14003485d  mov     [rsi], eax
0x14003485f  mov     eax, [r13+54h]
0x140034863  mov     [rsi+4], eax
0x140034866  mov     eax, [r13+60h]
0x14003486a  mov     [rsi+0Ch], eax
0x14003486d  mov     eax, [r13+90h]
0x140034874  mov     [rsi+8], eax
0x140034877  cmp     dword ptr [r15+140h], 1
0x14003487f  jbe     loc_140034A17
0x140034885  xor     eax, eax
0x140034887  mov     [rsi+20h], rax
0x14003488b  mov     [rsi+28h], rax
0x14003488f  mov     [rsi+30h], al
0x140034892  jmp     loc_140034A3E
0x140034897  cmp     dword ptr [rdi+23Ch], 70h ; 'p'
0x14003489e  jb      loc_1400349A4
0x1400348a4  mov     rcx, [rdi+230h]
0x1400348ab  lea     r8, Smb2QueryDebugInformation
0x1400348b2  mov     rdx, [rbp+57h+var_88]
0x1400348b6  mov     rax, r12
0x1400348b9  xor     rax, r8
0x1400348bc  mov     [rcx+38h], rax
0x1400348c0  mov     eax, [r12+2CCh]
0x1400348c8  mov     [rcx+64h], eax
0x1400348cb  mov     eax, [r12+188h]
0x1400348d3  mov     [rcx+44h], eax
0x1400348d6  mov     al, [r12+2E0h]
0x1400348de  and     al, 1
0x1400348e0  mov     [rcx+68h], al
0x1400348e3  mov     al, [r12+2E0h]
0x1400348eb  shr     al, 2
0x1400348ee  and     al, 1
0x1400348f0  mov     [rcx+6Ah], al
0x1400348f3  mov     al, [r12+2E0h]
0x1400348fb  shr     al, 1
0x1400348fd  and     al, 1
0x1400348ff  mov     [rcx+69h], al
0x140034902  mov     eax, [r12+2C0h]
0x14003490a  mov     [rcx+58h], eax
0x14003490d  mov     eax, [r12+2C8h]
0x140034915  mov     [rcx+60h], eax
0x140034918  mov     eax, [r12+2C4h]
0x140034920  mov     [rcx+5Ch], eax
0x140034923  movups  xmm0, xmmword ptr [r12+290h]
0x14003492c  movdqu  xmmword ptr [rcx+48h], xmm0
0x140034931  mov     eax, [r12+0Ch]
0x140034936  mov     [rcx+40h], eax
0x140034939  mov     rax, r13
0x14003493c  xor     rax, r8
0x14003493f  mov     [rcx+18h], rax
0x140034943  mov     eax, [r13+108h]
0x14003494a  mov     [rcx+24h], eax
0x14003494d  mov     rax, [r13+258h]
0x140034954  mov     [rcx+30h], rax
0x140034958  mov     rax, [r13+1B8h]
0x14003495f  mov     [rcx+28h], rax
0x140034963  mov     eax, [r13+0Ch]
0x140034967  mov     [rcx+20h], eax
0x14003496a  mov     rax, rdx
0x14003496d  xor     rax, r8
0x140034970  mov     [rcx], rax
0x140034973  mov     eax, [rdx+108h]
0x140034979  mov     [rcx+0Ch], eax
0x14003497c  mov     eax, [rdx+0Ch]
0x14003497f  mov     [rcx+8], eax
0x140034982  mov     eax, [rdx+1B4h]
0x140034988  mov     [rcx+10h], eax
0x14003498b  mov     qword ptr [rdi+0B8h], 70h ; 'p'
0x140034996  jmp     loc_140034C70
0x14003499b  cmp     dword ptr [rdi+23Ch], 40h ; '@'
0x1400349a2  jnb     short loc_1400349AE
0x1400349a4  mov     ebx, 0C0000023h
0x1400349a9  jmp     loc_140034C70
0x1400349ae  mov     rax, [r15+0F8h]
0x1400349b5  lea     r8, Smb2QueryDebugInformation
0x1400349bc  mov     rcx, [rdi+230h]
0x1400349c3  mov     [rcx+18h], rax
0x1400349c7  mov     eax, [r15+2Ch]
0x1400349cb  mov     [rcx+10h], eax
0x1400349ce  mov     eax, [r15+8]
0x1400349d2  mov     [rcx+8], eax
0x1400349d5  mov     rax, [r15+1Ch]
0x1400349d9  mov     [rcx+20h], rax
0x1400349dd  mov     dword ptr [rcx+30h], 1
0x1400349e4  mov     rax, [r15+100h]
0x1400349eb  mov     [rcx+38h], rax
0x1400349ef  mov     eax, [r15+4]
0x1400349f3  mov     [rcx+0Ch], eax
0x1400349f6  mov     rax, r15
0x1400349f9  xor     rax, r8
0x1400349fc  mov     [rcx], rax
0x1400349ff  mov     rax, [r15+24h]
0x140034a03  mov     [rcx+28h], rax
0x140034a07  mov     qword ptr [rdi+0B8h], 40h ; '@'
0x140034a12  jmp     loc_140034C70
0x140034a17  mov     rax, [r15+118h]
0x140034a1e  mov     [rsi+20h], rax
0x140034a22  mov     rax, [r15+110h]
0x140034a29  mov     [rsi+28h], rax
0x140034a2d  mov     al, [r15+124h]
0x140034a34  mov     [rsi+30h], al
0x140034a37  mov     al, [r15+125h]
0x140034a3e  mov     [rsi+31h], al
0x140034a41  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x140034a45  mov     rax, [r13+40h]
0x140034a49  mov     [rsi+10h], rax
0x140034a4d  mov     rax, [r13+48h]
0x140034a51  mov     [rsi+18h], rax
0x140034a55  mov     rax, [r15+128h]
0x140034a5c  mov     [rsi+38h], rax
0x140034a60  mov     rax, [r15+130h]
0x140034a67  mov     [rsi+40h], rax
0x140034a6b  mov     rax, [r15+138h]
0x140034a72  mov     [rsi+48h], rax
0x140034a76  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140034a7d  nop     dword ptr [rax+rax+00h]
0x140034a82  mov     rcx, [r15+218h]
0x140034a89  add     r12d, 0FFFFFFB0h
0x140034a8d  xor     r15d, r15d
0x140034a90  add     rsi, 50h ; 'P'
0x140034a94  cmp     rcx, [rbp+57h+var_78]
0x140034a98  lea     rax, [rcx-218h]
0x140034a9f  cmovnz  r15, rax
0x140034aa3  jmp     loc_14003481B
0x140034aa8  mov     ebx, 80000005h
0x140034aad  mov     eax, [rdi+23Ch]
0x140034ab3  mov     dl, [rbp+57h+OldIrql]; OldIrql
0x140034ab6  sub     eax, r12d
0x140034ab9  mov     rcx, [rbp+57h+SpinLock]; SpinLock
0x140034abd  mov     [rdi+0B8h], rax
0x140034ac4  call    cs:__imp_ExReleaseSpinLockShared
0x140034acb  nop     dword ptr [rax+rax+00h]
0x140034ad0  jmp     loc_140034C70
0x140034ad5  cmp     dword ptr [rdi+23Ch], 38h ; '8'
0x140034adc  jb      loc_1400349A4
0x140034ae2  mov     rsi, [rdi+230h]
0x140034ae9  xor     eax, eax
0x140034aeb  movups  xmmword ptr [rsi], xmm0
0x140034aee  movups  xmmword ptr [rsi+10h], xmm0
0x140034af2  movups  xmmword ptr [rsi+20h], xmm0
0x140034af6  mov     [rsi+30h], rax
0x140034afa  mov     word ptr [rsi], 202h
0x140034aff  movzx   eax, word ptr [r15+18h]
0x140034b04  mov     [rsi+2], ax
0x140034b08  mov     eax, [r15+2Ch]
0x140034b0c  mov     [rsi+4], eax
0x140034b0f  mov     eax, [r9+108h]
0x140034b16  mov     [rsi+8], eax
0x140034b19  mov     rax, [r15+24h]
0x140034b1d  mov     [rsi+10h], rax
0x140034b21  mov     rax, [r15+1Ch]
0x140034b25  mov     [rsi+18h], rax
0x140034b29  mov     rax, [r13+1B8h]
0x140034b30  mov     [rsi+20h], rax
0x140034b34  mov     al, [rcx+11Ah]
0x140034b3a  mov     [rsi+30h], al
0x140034b3d  test    dword ptr [rdx+48h], 100000h
0x140034b44  jz      short loc_140034B4A
0x140034b46  mov     byte ptr [rsi+2Eh], 1
0x140034b4a  test    dword ptr [rcx+0A0h], 8000000h
0x140034b54  jz      short loc_140034B5A
0x140034b56  mov     byte ptr [rsi+28h], 1
0x140034b5a  test    dword ptr [rcx+0A0h], 2000000h
0x140034b64  jz      short loc_140034B6A
0x140034b66  mov     byte ptr [rsi+29h], 1
0x140034b6a  test    dword ptr [rcx+0A0h], 200000h
0x140034b74  jz      short loc_140034B7A
0x140034b76  mov     byte ptr [rsi+2Ah], 1
0x140034b7a  test    dword ptr [rcx+0A0h], 800h
0x140034b84  jz      short loc_140034B8A
0x140034b86  mov     byte ptr [rsi+2Bh], 1
0x140034b8a  mov     r15d, 28h ; '('
0x140034b90  lea     rax, [rbp+57h+var_88]
0x140034b94  mov     [rsp+0D0h+var_A0], rax
0x140034b99  lea     rdx, [r10+178h]
0x140034ba0  lea     rax, [rbp+57h+var_58]
0x140034ba4  mov     dword ptr [rbp+57h+var_88], r15d
0x140034ba8  mov     [rsp+0D0h+var_A8], rax
0x140034bad  mov     rcx, rdi
0x140034bb0  lea     r9d, [r15-24h]
0x140034bb4  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x140034bb8  lea     r8d, [r15-27h]
0x140034bbc  call    Smb2FetchFileInfoFromCache
0x140034bc1  cmp     eax, 0C0000016h
0x140034bc6  jz      short loc_140034BCC
0x140034bc8  mov     byte ptr [rsi+2Ch], 1
0x140034bcc  lea     rax, [rbp+57h+var_88]
0x140034bd0  mov     dword ptr [rbp+57h+var_88], r15d
0x140034bd4  mov     [rsp+0D0h+var_A8], rax
0x140034bd9  mov     r9d, 4
0x140034bdf  lea     rax, [rbp+57h+var_58]
0x140034be3  xor     r8d, r8d
0x140034be6  mov     rcx, rdi
0x140034be9  mov     [rsp+0D0h+var_B0], rax
0x140034bee  call    Smb2QueryFileInformationFromDirCache
0x140034bf3  test    eax, eax
0x140034bf5  jnz     short loc_140034BFB
0x140034bf7  mov     byte ptr [rsi+2Dh], 1
0x140034bfb  cmp     [r13+0Ch], ebx
0x140034bff  jnz     short loc_140034C5E
0x140034c01  mov     r15, [rbp+57h+SpinLock]
0x140034c05  mov     rcx, r15
0x140034c08  call    SmbCeAcquireSpinLock
0x140034c0d  mov     rcx, r13
0x140034c10  mov     r12b, al
0x140034c13  call    SmbCeGetFirstBindingObjectEx
0x140034c18  test    rax, rax
0x140034c1b  jz      short loc_140034C36
  ... truncated ...
```
