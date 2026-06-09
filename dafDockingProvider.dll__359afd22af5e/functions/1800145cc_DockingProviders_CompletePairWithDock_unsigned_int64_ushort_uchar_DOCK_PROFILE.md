# DockingProviders::CompletePairWithDock(unsigned __int64,ushort,uchar *,_DOCK_PROFILE *)

- ea: `0x1800145cc`
- end: `0x180014715`
- name: `?CompletePairWithDock@DockingProviders@@QEAAJ_KGPEAEPEAU_DOCK_PROFILE@@@Z`
- size: `329`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock, _QWORD *Block, unsigned __int16, unsigned __int8 *, struct _DOCK_PROFILE *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800090a8`
- `0x180009660`

## callees

- `0x1800014d0`
- `0x18000c308`
- `0x18000c348`
- `0x18000d460`
- `0x1800144a8`
- `0x1800145cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180014625`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180014625`

## pseudocode

```c
__int64 __fastcall DockingProviders::CompletePairWithDock(
        PSRWLOCK SRWLock,
        _QWORD *Block,
        unsigned __int16 a3,
        unsigned __int8 *a4,
        struct _DOCK_PROFILE *a5)
{
  int v9; // eax
  unsigned int v10; // esi
  PSRWLOCK v12; // [rsp+30h] [rbp-48h] BYREF
  char v13; // [rsp+38h] [rbp-40h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_664df381f3e33d6bde707323c6216c8b_Traceguids, SRWLock);
  }
  v12 = SRWLock;
  AcquireSRWLockShared(SRWLock);
  v13 = 1;
  if ( Block && *Block < (unsigned __int64)LODWORD(SRWLock[2].Ptr) )
  {
    v9 = DockingProvider::CompletePairWithDock(*((DockingProvider **)SRWLock[3].Ptr + *Block), Block[1], a3, a4, a5);
    v10 = v9;
    if ( v9 >= 0 )
      *((_QWORD *)a5 + 143) = *Block;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_664df381f3e33d6bde707323c6216c8b_Traceguids, SRWLock, v9);
    }
LABEL_19:
    operator delete(Block);
    goto LABEL_20;
  }
  v10 = -2147024809;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      82,
      &WPP_664df381f3e33d6bde707323c6216c8b_Traceguids,
      SRWLock,
      -2147024809);
  }
  if ( Block )
    goto LABEL_19;
LABEL_20:
  ReadLock::~ReadLock(&v12);
  return v10;
}

```

## disassembly

```asm
0x1800145cc  push    rbx
0x1800145ce  push    rbp
0x1800145cf  push    rsi
0x1800145d0  push    rdi
0x1800145d1  push    r13
0x1800145d3  push    r14
0x1800145d5  sub     rsp, 48h
0x1800145d9  mov     rsi, r9
0x1800145dc  movzx   r14d, r8w
0x1800145e0  mov     rbx, rdx
0x1800145e3  mov     rdi, rcx
0x1800145e6  lea     r13, WPP_GLOBAL_Control
0x1800145ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800145f4  cmp     rcx, r13
0x1800145f7  jz      short loc_18001461D
0x1800145f9  cmp     byte ptr [rcx+19h], 4
0x1800145fd  jb      short loc_18001461D
0x1800145ff  test    byte ptr [rcx+1Ch], 1
0x180014603  jz      short loc_18001461D
0x180014605  mov     edx, 51h ; 'Q'
0x18001460a  mov     r9, rdi
0x18001460d  lea     r8, WPP_664df381f3e33d6bde707323c6216c8b_Traceguids
0x180014614  mov     rcx, [rcx+10h]
0x180014618  call    WPP_SF_q
0x18001461d  mov     [rsp+78h+var_48], rdi
0x180014622  mov     rcx, rdi; SRWLock
0x180014625  call    cs:__imp_AcquireSRWLockShared
0x18001462b  mov     [rsp+78h+var_40], 1
0x180014630  mov     [rsp+78h+arg_0], rbx
0x180014638  test    rbx, rbx
0x18001463b  jz      short loc_1800146B4
0x18001463d  mov     r10, [rbx]
0x180014640  mov     eax, [rdi+10h]
0x180014643  cmp     r10, rax
0x180014646  jnb     short loc_1800146B4
0x180014648  mov     rcx, [rdi+18h]
0x18001464c  mov     rbp, [rsp+78h+arg_20]
0x180014654  mov     [rsp+78h+var_58], rbp; struct _DOCK_PROFILE *
0x180014659  mov     r9, rsi; unsigned __int8 *
0x18001465c  movzx   r8d, r14w; unsigned __int16
0x180014660  mov     rdx, [rbx+8]; unsigned __int64
0x180014664  mov     rcx, [rcx+r10*8]; this
0x180014668  call    ?CompletePairWithDock@DockingProvider@@QEAAJ_KGPEAEPEAU_DOCK_PROFILE@@@Z; DockingProvider::CompletePairWithDock(unsigned __int64,ushort,uchar *,_DOCK_PROFILE *)
0x18001466d  mov     esi, eax
0x18001466f  test    eax, eax
0x180014671  js      short loc_18001467D
0x180014673  mov     rcx, [rbx]
0x180014676  mov     [rbp+478h], rcx
0x18001467d  mov     rcx, cs:WPP_GLOBAL_Control
0x180014684  cmp     rcx, r13
0x180014687  jz      short loc_1800146B2
0x180014689  cmp     byte ptr [rcx+19h], 4
0x18001468d  jb      short loc_1800146B2
0x18001468f  test    byte ptr [rcx+1Ch], 1
0x180014693  jz      short loc_1800146B2
0x180014695  mov     edx, 53h ; 'S'
0x18001469a  mov     dword ptr [rsp+78h+var_58], eax
0x18001469e  mov     r9, rdi
0x1800146a1  lea     r8, WPP_664df381f3e33d6bde707323c6216c8b_Traceguids
0x1800146a8  mov     rcx, [rcx+10h]
0x1800146ac  call    WPP_SF_qD
0x1800146b1  nop
0x1800146b2  jmp     short loc_1800146F3
0x1800146b4  mov     esi, 80070057h
0x1800146b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800146c0  cmp     rcx, r13
0x1800146c3  jz      short loc_1800146EE
0x1800146c5  cmp     byte ptr [rcx+19h], 4
0x1800146c9  jb      short loc_1800146EE
0x1800146cb  test    byte ptr [rcx+1Ch], 1
0x1800146cf  jz      short loc_1800146EE
0x1800146d1  mov     edx, 52h ; 'R'
0x1800146d6  mov     dword ptr [rsp+78h+var_58], esi
0x1800146da  mov     r9, rdi
0x1800146dd  lea     r8, WPP_664df381f3e33d6bde707323c6216c8b_Traceguids
0x1800146e4  mov     rcx, [rcx+10h]
0x1800146e8  call    WPP_SF_qD
0x1800146ed  nop
0x1800146ee  test    rbx, rbx
0x1800146f1  jz      short loc_1800146FC
0x1800146f3  mov     rcx, rbx; Block
0x1800146f6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800146fb  nop
0x1800146fc  lea     rcx, [rsp+78h+var_48]; this
0x180014701  call    ??1ReadLock@@QEAA@XZ; ReadLock::~ReadLock(void)
0x180014706  mov     eax, esi
0x180014708  add     rsp, 48h
0x18001470c  pop     r14
0x18001470e  pop     r13
0x180014710  pop     rdi
0x180014711  pop     rsi
0x180014712  pop     rbp
0x180014713  pop     rbx
0x180014714  retn
```
