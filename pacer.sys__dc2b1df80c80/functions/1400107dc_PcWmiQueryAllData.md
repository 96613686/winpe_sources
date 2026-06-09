# PcWmiQueryAllData

- ea: `0x1400107dc`
- end: `0x140010b61`
- name: `PcWmiQueryAllData`
- size: `901`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140010c70`

## callees

- `0x140003770`
- `0x14000aa3c`
- `0x140010360`
- `0x1400107dc`
- `0x140013300`
- `0x14001f140`

## import_xrefs

- `NDIS!NdisAcquireRWLockRead` at `0x14001083b`
- `NDIS!NdisAcquireRWLockRead` at `0x1400108e9`
- `NDIS!NdisAcquireRWLockRead` at `0x140010939`
- `NDIS!NdisAcquireRWLockRead` at `0x1400109b9`
- `NDIS!NdisAcquireRWLockRead` at `0x140010ada`
- `NDIS!NdisAcquireRWLockRead` at `0x140010b05`
- `NDIS!NdisAcquireRWLockRead` at `0x14001083b`
- `NDIS!NdisAcquireRWLockRead` at `0x1400108e9`
- `NDIS!NdisAcquireRWLockRead` at `0x140010939`
- `NDIS!NdisAcquireRWLockRead` at `0x1400109b9`
- `NDIS!NdisAcquireRWLockRead` at `0x140010ada`
- `NDIS!NdisAcquireRWLockRead` at `0x140010b05`
- `NDIS!NdisReleaseRWLock` at `0x14001086d`
- `NDIS!NdisReleaseRWLock` at `0x140010922`
- `NDIS!NdisReleaseRWLock` at `0x140010979`
- `NDIS!NdisReleaseRWLock` at `0x1400109f4`
- `NDIS!NdisReleaseRWLock` at `0x140010a59`
- `NDIS!NdisReleaseRWLock` at `0x140010ac0`
- `NDIS!NdisReleaseRWLock` at `0x140010b24`
- `NDIS!NdisReleaseRWLock` at `0x14001086d`
- `NDIS!NdisReleaseRWLock` at `0x140010922`
- `NDIS!NdisReleaseRWLock` at `0x140010979`
- `NDIS!NdisReleaseRWLock` at `0x1400109f4`
- `NDIS!NdisReleaseRWLock` at `0x140010a59`
- `NDIS!NdisReleaseRWLock` at `0x140010ac0`
- `NDIS!NdisReleaseRWLock` at `0x140010b24`

## pseudocode

```c
__int64 __fastcall PcWmiQueryAllData(__int64 a1, __int64 a2, unsigned int a3, unsigned int *a4)
{
  int Guid; // esi
  unsigned int v7; // r14d
  PVOID *v8; // rax
  UCHAR v9; // r8
  unsigned int v10; // r13d
  unsigned int v11; // r12d
  unsigned int v12; // r15d
  volatile signed __int32 *v13; // rbx
  __int64 v14; // rax
  unsigned int v15; // esi
  _WORD *v16; // rcx
  unsigned int v17; // eax
  int v18; // r12d
  int v19; // ecx
  struct _LOCK_STATE_EX LockState; // [rsp+30h] [rbp-40h] BYREF
  char v22; // [rsp+34h] [rbp-3Ch]
  int v23; // [rsp+38h] [rbp-38h] BYREF
  _WORD *v24; // [rsp+40h] [rbp-30h]
  PVOID P; // [rsp+48h] [rbp-28h]
  unsigned int v26; // [rsp+50h] [rbp-20h]
  __int64 v27; // [rsp+58h] [rbp-18h] BYREF
  __int64 v28; // [rsp+60h] [rbp-10h]

  v27 = 0;
  v23 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  *a4 = 0;
  if ( a3 >= 0x38 )
  {
    v7 = 0;
    NdisAcquireRWLockRead(PcgLineListLock, &LockState, 0);
    v8 = (PVOID *)PcgLineList;
    while ( v8 != &PcgLineList )
    {
      v8 = (PVOID *)*v8;
      ++v7;
    }
    NdisReleaseRWLock(PcgLineListLock, &LockState);
    Guid = PcpWmiGetGuid(&v27, a1, 0);
    if ( Guid >= 0 )
    {
      *(_QWORD *)(a2 + 16) = MEMORY[0xFFFFF78000000014];
      *(_DWORD *)(a2 + 56) = 8 * v7 + 72;
      v28 = a2 + 8 * v7 + 72;
      v10 = 0;
      v22 = 0;
      v11 = (12 * v7 + 79) & 0xFFFFFFF8;
      v12 = v11;
      v24 = (_WORD *)(a2 + v11);
      NdisAcquireRWLockRead(PcgLineListLock, &LockState, v9);
      v13 = (volatile signed __int32 *)PcgLineList;
      while ( v13 != (volatile signed __int32 *)&PcgLineList )
      {
        P = (PVOID)v13;
        _InterlockedIncrement(v13 + 62);
        NdisReleaseRWLock(PcgLineListLock, &LockState);
        NdisAcquireRWLockRead(*((PNDIS_RW_LOCK_EX *)v13 + 2), &LockState, 0);
        if ( *((_DWORD *)v13 + 61) != 2
          || (v14 = *((_QWORD *)v13 + 32)) != 0
          && *(_DWORD *)(v14 + 16) == 3
          && *(volatile signed __int32 **)(v14 + 160) == v13 )
        {
          NdisReleaseRWLock(*((PNDIS_RW_LOCK_EX *)v13 + 2), &LockState);
        }
        else
        {
          NdisReleaseRWLock(*((PNDIS_RW_LOCK_EX *)v13 + 2), &LockState);
          Guid = PcQueryGuidDataSize(v13, 0, *(unsigned int *)(v27 + 16), &v23);
          if ( Guid >= 0 )
          {
            if ( v10 >= v7 )
              goto LABEL_21;
            NdisAcquireRWLockRead(*((PNDIS_RW_LOCK_EX *)v13 + 2), &LockState, 0);
            v15 = (*((unsigned __int16 *)v13 + 132) + 9) & 0xFFFFFFF8;
            v26 = (v23 + 7) & 0xFFFFFFF8;
            v12 += v15 + v26;
            if ( a3 >= v12 )
            {
              *(_DWORD *)(v28 + 4LL * v10) = v11;
              v16 = v24;
              *v24 = *((_WORD *)v13 + 132);
              memmove(v16 + 1, *((const void **)v13 + 34), *((unsigned __int16 *)v13 + 132));
              NdisReleaseRWLock(*((PNDIS_RW_LOCK_EX *)v13 + 2), &LockState);
              v17 = v15 + v11;
              v18 = v23;
              LODWORD(v24) = v17;
              Guid = PcQueryGuidData((_DWORD)v13, 0, *(_DWORD *)(v27 + 16), (unsigned int)a2 + v17, v23);
              if ( Guid < 0 )
              {
LABEL_21:
                NdisAcquireRWLockRead(PcgLineListLock, &LockState, 0);
                PcpLineDereference((PVOID)v13);
                break;
              }
              v19 = (int)v24;
              *(_DWORD *)(a2 + 8LL * v10 + 64) = v18;
              v11 = v19 + v26;
              *(_DWORD *)(a2 + 8LL * v10 + 60) = v19;
              v24 = (_WORD *)(a2 + v11);
              ++v10;
            }
            else
            {
              NdisReleaseRWLock(*((PNDIS_RW_LOCK_EX *)v13 + 2), &LockState);
              *(_DWORD *)(a2 + 44) |= 0x20u;
              *(_DWORD *)a2 = 56;
              Guid = 0;
              *(_DWORD *)(a2 + 48) = v12;
              *a4 = 56;
              v22 = 1;
            }
          }
        }
        NdisAcquireRWLockRead(PcgLineListLock, &LockState, 0);
        v13 = *(volatile signed __int32 **)v13;
        PcpLineDereference(P);
      }
      NdisReleaseRWLock(PcgLineListLock, &LockState);
      if ( !v22 )
      {
        Guid = 0;
        *(_DWORD *)a2 = v12;
        *(_DWORD *)(a2 + 52) = v10;
        *a4 = v12;
      }
    }
  }
  else
  {
    return (unsigned int)-1073741789;
  }
  return (unsigned int)Guid;
}

```

## disassembly

```asm
0x1400107dc  mov     [rsp-38h+arg_0], rbx
0x1400107e1  mov     [rsp-38h+arg_18], r9
0x1400107e6  mov     [rsp-38h+arg_10], r8d
0x1400107eb  push    rbp
0x1400107ec  push    rsi
0x1400107ed  push    rdi
0x1400107ee  push    r12
0x1400107f0  push    r13
0x1400107f2  push    r14
0x1400107f4  push    r15
0x1400107f6  mov     rbp, rsp
0x1400107f9  sub     rsp, 70h
0x1400107fd  xor     r15d, r15d
0x140010800  mov     rbx, rcx
0x140010803  xor     ecx, ecx
0x140010805  mov     [rbp+var_18], r15
0x140010809  mov     [rbp+var_38], r15d
0x14001080d  mov     rdi, rdx
0x140010810  mov     word ptr [rbp+LockState.OldIrql], cx
0x140010814  mov     [rbp+LockState.Flags], cl
0x140010817  mov     [r9], r15d
0x14001081a  cmp     r8d, 38h ; '8'
0x14001081e  jnb     short loc_14001082A
0x140010820  mov     esi, 0C0000023h
0x140010825  jmp     loc_140010B46
0x14001082a  mov     rcx, cs:PcgLineListLock; Lock
0x140010831  lea     rdx, [rbp+LockState]; LockState
0x140010835  xor     r8d, r8d; Flags
0x140010838  mov     r14d, r15d
0x14001083b  call    cs:__imp_NdisAcquireRWLockRead
0x140010842  nop     dword ptr [rax+rax+00h]
0x140010847  mov     rax, cs:PcgLineList
0x14001084e  lea     rcx, PcgLineList
0x140010855  jmp     short loc_14001085D
0x140010857  mov     rax, [rax]
0x14001085a  inc     r14d
0x14001085d  cmp     rax, rcx
0x140010860  jnz     short loc_140010857
0x140010862  mov     rcx, cs:PcgLineListLock; Lock
0x140010869  lea     rdx, [rbp+LockState]; LockState
0x14001086d  call    cs:__imp_NdisReleaseRWLock
0x140010874  nop     dword ptr [rax+rax+00h]
0x140010879  xor     r8d, r8d
0x14001087c  lea     rcx, [rbp+var_18]
0x140010880  mov     rdx, rbx
0x140010883  call    PcpWmiGetGuid
0x140010888  mov     esi, eax
0x14001088a  test    eax, eax
0x14001088c  js      loc_140010B46
0x140010892  mov     rax, ds:0FFFFF78000000014h
0x14001089c  lea     ecx, ds:48h[r14*8]
0x1400108a4  mov     [rdi+10h], rax
0x1400108a8  lea     rdx, [rbp+LockState]; LockState
0x1400108ac  mov     [rdi+38h], ecx
0x1400108af  lea     eax, ds:48h[r14*8]
0x1400108b7  mov     rcx, cs:PcgLineListLock; Lock
0x1400108be  add     rax, rdi
0x1400108c1  mov     [rbp+var_10], rax
0x1400108c5  mov     r13d, r15d
0x1400108c8  lea     eax, [r14+r14*2]
0x1400108cc  mov     [rbp+var_3C], r15b
0x1400108d0  lea     r12d, ds:4Fh[rax*4]
0x1400108d8  and     r12d, 0FFFFFFF8h
0x1400108dc  mov     eax, r12d
0x1400108df  mov     r15d, r12d
0x1400108e2  add     rax, rdi
0x1400108e5  mov     [rbp+var_30], rax
0x1400108e9  call    cs:__imp_NdisAcquireRWLockRead
0x1400108f0  nop     dword ptr [rax+rax+00h]
0x1400108f5  mov     rbx, cs:PcgLineList
0x1400108fc  lea     rax, PcgLineList
0x140010903  cmp     rbx, rax
0x140010906  jz      loc_140010B19
0x14001090c  mov     [rbp+P], rbx
0x140010910  lock inc dword ptr [rbx+0F8h]
0x140010917  mov     rcx, cs:PcgLineListLock; Lock
0x14001091e  lea     rdx, [rbp+LockState]; LockState
0x140010922  call    cs:__imp_NdisReleaseRWLock
0x140010929  nop     dword ptr [rax+rax+00h]
0x14001092e  mov     rcx, [rbx+10h]; Lock
0x140010932  lea     rdx, [rbp+LockState]; LockState
0x140010936  xor     r8d, r8d; Flags
0x140010939  call    cs:__imp_NdisAcquireRWLockRead
0x140010940  nop     dword ptr [rax+rax+00h]
0x140010945  cmp     dword ptr [rbx+0F4h], 2
0x14001094c  jnz     loc_140010AB8
0x140010952  mov     rax, [rbx+100h]
0x140010959  test    rax, rax
0x14001095c  jz      short loc_140010971
0x14001095e  cmp     dword ptr [rax+10h], 3
0x140010962  jnz     short loc_140010971
0x140010964  cmp     [rax+0A0h], rbx
0x14001096b  jz      loc_140010AB8
0x140010971  mov     rcx, [rbx+10h]; Lock
0x140010975  lea     rdx, [rbp+LockState]; LockState
0x140010979  call    cs:__imp_NdisReleaseRWLock
0x140010980  nop     dword ptr [rax+rax+00h]
0x140010985  mov     rax, [rbp+var_18]
0x140010989  lea     r9, [rbp+var_38]
0x14001098d  xor     edx, edx
0x14001098f  mov     rcx, rbx
0x140010992  mov     r8d, [rax+10h]
0x140010996  call    PcQueryGuidDataSize
0x14001099b  mov     esi, eax
0x14001099d  test    eax, eax
0x14001099f  js      loc_140010ACC
0x1400109a5  xor     r8d, r8d; Flags
0x1400109a8  lea     rdx, [rbp+LockState]; LockState
0x1400109ac  cmp     r13d, r14d
0x1400109af  jnb     loc_140010AFE
0x1400109b5  mov     rcx, [rbx+10h]; Lock
0x1400109b9  call    cs:__imp_NdisAcquireRWLockRead
0x1400109c0  nop     dword ptr [rax+rax+00h]
0x1400109c5  mov     eax, [rbp+var_38]
0x1400109c8  mov     ecx, 0FFFFFFF8h
0x1400109cd  movzx   esi, word ptr [rbx+108h]
0x1400109d4  add     eax, 7
0x1400109d7  and     eax, ecx
0x1400109d9  add     esi, 9
0x1400109dc  and     esi, ecx
0x1400109de  mov     [rbp+var_20], eax
0x1400109e1  add     eax, esi
0x1400109e3  add     r15d, eax
0x1400109e6  cmp     [rbp+arg_10], r15d
0x1400109ea  jnb     short loc_140010A20
0x1400109ec  mov     rcx, [rbx+10h]; Lock
0x1400109f0  lea     rdx, [rbp+LockState]; LockState
0x1400109f4  call    cs:__imp_NdisReleaseRWLock
0x1400109fb  nop     dword ptr [rax+rax+00h]
0x140010a00  mov     rax, [rbp+arg_18]
0x140010a04  mov     ecx, 38h ; '8'
0x140010a09  or      dword ptr [rdi+2Ch], 20h
0x140010a0d  mov     [rdi], ecx
0x140010a0f  xor     esi, esi
0x140010a11  mov     [rdi+30h], r15d
0x140010a15  mov     [rax], ecx
0x140010a17  mov     [rbp+var_3C], 1
0x140010a1b  jmp     loc_140010ACC
0x140010a20  mov     rcx, [rbp+var_10]
0x140010a24  mov     eax, r13d
0x140010a27  mov     [rcx+rax*4], r12d
0x140010a2b  mov     rcx, [rbp+var_30]
0x140010a2f  movzx   eax, word ptr [rbx+108h]
0x140010a36  mov     [rcx], ax
0x140010a39  add     rcx, 2; void *
0x140010a3d  movzx   r8d, word ptr [rbx+108h]; Size
0x140010a45  mov     rdx, [rbx+110h]; Src
0x140010a4c  call    memmove
0x140010a51  mov     rcx, [rbx+10h]; Lock
0x140010a55  lea     rdx, [rbp+LockState]; LockState
0x140010a59  call    cs:__imp_NdisReleaseRWLock
0x140010a60  nop     dword ptr [rax+rax+00h]
0x140010a65  lea     eax, [rsi+r12]
0x140010a69  xor     edx, edx
0x140010a6b  mov     r12d, [rbp+var_38]
0x140010a6f  mov     rcx, rbx
0x140010a72  mov     r9d, eax
0x140010a75  mov     dword ptr [rbp+var_30], eax
0x140010a78  add     r9, rdi
0x140010a7b  mov     rax, [rbp+var_18]
0x140010a7f  mov     [rsp+70h+var_50], r12d
0x140010a84  mov     r8d, [rax+10h]
0x140010a88  call    PcQueryGuidData
0x140010a8d  mov     esi, eax
0x140010a8f  test    eax, eax
0x140010a91  js      short loc_140010AF7
0x140010a93  mov     ecx, dword ptr [rbp+var_30]
0x140010a96  mov     eax, r13d
0x140010a99  mov     [rdi+rax*8+40h], r12d
0x140010a9e  mov     r12d, [rbp+var_20]
0x140010aa2  add     r12d, ecx
0x140010aa5  mov     [rdi+rax*8+3Ch], ecx
0x140010aa9  mov     eax, r12d
0x140010aac  add     rax, rdi
0x140010aaf  mov     [rbp+var_30], rax
0x140010ab3  inc     r13d
0x140010ab6  jmp     short loc_140010ACC
0x140010ab8  mov     rcx, [rbx+10h]; Lock
0x140010abc  lea     rdx, [rbp+LockState]; LockState
0x140010ac0  call    cs:__imp_NdisReleaseRWLock
0x140010ac7  nop     dword ptr [rax+rax+00h]
0x140010acc  mov     rcx, cs:PcgLineListLock; Lock
0x140010ad3  lea     rdx, [rbp+LockState]; LockState
0x140010ad7  xor     r8d, r8d; Flags
0x140010ada  call    cs:__imp_NdisAcquireRWLockRead
0x140010ae1  nop     dword ptr [rax+rax+00h]
0x140010ae6  mov     rcx, [rbp+P]; P
0x140010aea  mov     rbx, [rbx]
0x140010aed  call    PcpLineDereference
0x140010af2  jmp     loc_1400108FC
0x140010af7  xor     r8d, r8d; Flags
0x140010afa  lea     rdx, [rbp+LockState]; LockState
0x140010afe  mov     rcx, cs:PcgLineListLock; Lock
0x140010b05  call    cs:__imp_NdisAcquireRWLockRead
0x140010b0c  nop     dword ptr [rax+rax+00h]
0x140010b11  mov     rcx, rbx; P
0x140010b14  call    PcpLineDereference
0x140010b19  mov     rcx, cs:PcgLineListLock; Lock
0x140010b20  lea     rdx, [rbp+LockState]; LockState
0x140010b24  call    cs:__imp_NdisReleaseRWLock
0x140010b2b  nop     dword ptr [rax+rax+00h]
0x140010b30  cmp     [rbp+var_3C], 0
0x140010b34  jnz     short loc_140010B46
0x140010b36  mov     rax, [rbp+arg_18]
0x140010b3a  xor     esi, esi
0x140010b3c  mov     [rdi], r15d
0x140010b3f  mov     [rdi+34h], r13d
0x140010b43  mov     [rax], r15d
0x140010b46  mov     rbx, [rsp+70h+arg_0]
0x140010b4e  mov     eax, esi
0x140010b50  add     rsp, 70h
0x140010b54  pop     r15
0x140010b56  pop     r14
0x140010b58  pop     r13
0x140010b5a  pop     r12
0x140010b5c  pop     rdi
0x140010b5d  pop     rsi
0x140010b5e  pop     rbp
0x140010b5f  retn
```
