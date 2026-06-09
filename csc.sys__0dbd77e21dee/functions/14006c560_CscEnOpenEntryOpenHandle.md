# CscEnOpenEntryOpenHandle

- ea: `0x14006c560`
- end: `0x14006cdb8`
- name: `CscEnOpenEntryOpenHandle`
- size: `2136`
- prototype: `__int64 __fastcall(_QWORD *, __int64, char, __int64, unsigned int, int, _BYTE *, unsigned int, _DWORD *)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140012860`

## callees

- `0x140004e84`
- `0x1400052c0`
- `0x140005390`
- `0x140007420`
- `0x14000a884`
- `0x14000b5a0`
- `0x14000d960`
- `0x140010b00`
- `0x140010f6c`
- `0x14001463c`
- `0x140016a04`
- `0x140018930`
- `0x140018cf4`
- `0x14001ac1c`
- `0x140027cc4`
- `0x14006c560`
- `0x14006cdc0`
- `0x14006d6d0`
- `0x14007d610`
- `0x14008675c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14006ca75`
- `ntoskrnl!ObfDereferenceObject` at `0x14006ca75`
- `ntoskrnl!IoFileObjectType` at `0x14006ca37`
- `ntoskrnl!ExAllocatePool2` at `0x14006c69c`
- `ntoskrnl!ExAllocatePool2` at `0x14006c99c`
- `ntoskrnl!ExAllocatePool2` at `0x14006c69c`
- `ntoskrnl!ExAllocatePool2` at `0x14006c99c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14006ca60`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14006ca60`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006cd15`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006cd15`
- `ntoskrnl!ExInitializeResourceLite` at `0x14006c9b7`
- `ntoskrnl!ExInitializeResourceLite` at `0x14006c9b7`

## pseudocode

```c
__int64 __fastcall CscEnOpenEntryOpenHandle(
        _QWORD *a1,
        __int64 a2,
        char a3,
        __int64 a4,
        unsigned int a5,
        int a6,
        _BYTE *a7,
        unsigned int a8,
        _DWORD *a9)
{
  _WORD *v9; // rdi
  __int64 v11; // rdx
  __int64 v12; // r12
  char v13; // r14
  __int64 v15; // r8
  char v16; // bp
  int CanSidDecryptEntry; // esi
  _DWORD *v19; // rdi
  int v20; // eax
  int v21; // ebp
  char v22; // r13
  unsigned int v23; // esi
  _WORD *Pool2; // rax
  int v25; // ebp
  __int64 v26; // r8
  int TokenUserInformation; // eax
  struct _ERESOURCE *v29; // rax
  struct _ERESOURCE *v30; // rbp
  char v31; // r14
  int v32; // r8d
  char HandleInformation; // [rsp+28h] [rbp-90h]
  __int64 v34; // [rsp+30h] [rbp-88h]
  unsigned int v35; // [rsp+60h] [rbp-58h]
  HANDLE Handle; // [rsp+68h] [rbp-50h] BYREF
  _QWORD v37[2]; // [rsp+70h] [rbp-48h] BYREF
  char v38; // [rsp+C0h] [rbp+8h] BYREF
  char v39; // [rsp+C8h] [rbp+10h] BYREF
  __int64 v40; // [rsp+D8h] [rbp+20h]

  v40 = a4;
  v9 = 0;
  v11 = 0;
  v12 = 0;
  v13 = a6;
  v15 = 0;
  v16 = a6 & 1;
  Handle = 0;
  v35 = 0;
  a8 = 0;
  v37[0] = 0;
  v39 = 0;
  v38 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
  {
    if ( a7 )
    {
      v26 = 89;
      if ( !*a7 )
        v26 = 78;
    }
    else
    {
      v26 = 63;
    }
    HIDWORD(v34) = HIDWORD(a4);
    HandleInformation = a3;
    WPP_SF_qqDqDccqq(WPP_GLOBAL_Control->AttachedDevice, a5, v26, a1, a2);
  }
  if ( a2 )
  {
    CscEnpMainAcquireExclusive(a2);
    CanSidDecryptEntry = CscEnpCheckState(a2);
    if ( CanSidDecryptEntry < 0 )
    {
      v25 = 10466;
      v11 = 0;
      goto LABEL_27;
    }
    v19 = a9;
    a6 = *(_DWORD *)(a2 + 336) & 0x10;
    v20 = CscEnAccessCheck(a2, a3, v40, 1, a5, HandleInformation, a9, &v38);
    CanSidDecryptEntry = v20;
    if ( v20 != -1073741790 )
    {
      if ( v20 >= 0 )
      {
        v21 = a6;
        v22 = a5;
        goto LABEL_7;
      }
LABEL_28:
      v9 = 0;
      v25 = 10529;
      if ( CanSidDecryptEntry < 0 )
      {
        v11 = 0;
        goto LABEL_27;
      }
LABEL_29:
      v11 = *(unsigned int *)(a2 + 160);
      v15 = *(unsigned int *)(a2 + 164);
      v35 = *(_DWORD *)(a2 + 160);
      a8 = *(_DWORD *)(a2 + 164);
      goto LABEL_30;
    }
    if ( !v38 )
      goto LABEL_28;
    v32 = *(_DWORD *)(a2 + 192);
    if ( (v32 & 0x10020) == 0 && (!v16 || (v32 & 0x10) == 0) )
      goto LABEL_28;
    if ( v16 )
    {
      v22 = a5;
      if ( (a5 & 0x30117) != 0 )
      {
        if ( (v13 & 2) == 0 )
          goto LABEL_83;
        v21 = a6;
        if ( !a6 || (a5 & 0x30116) != 0 )
          goto LABEL_83;
      }
      else
      {
        v21 = a6;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
      {
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 96, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids, a2, v32);
      }
      if ( v19 )
        *v19 = 128;
LABEL_7:
      v23 = 64;
      if ( !v21 )
        v23 = 20;
      Pool2 = (_WORD *)ExAllocatePool2(256, v23, 692089667);
      v9 = Pool2;
      if ( !Pool2 )
      {
        CanSidDecryptEntry = -1073741670;
        v25 = 10545;
LABEL_63:
        v31 = 1;
        goto LABEL_64;
      }
      *Pool2 = -9720;
      Pool2[1] = v23;
      a6 = 0;
      if ( v21 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 97, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids, a2);
        }
        *((_DWORD *)v9 + 4) |= 0x100u;
        if ( a7 )
        {
          if ( *a7 )
          {
            CanSidDecryptEntry = CscEnpUnghostEntry(a2);
            if ( CanSidDecryptEntry < 0 )
            {
              v25 = 10569;
              v11 = 0;
              goto LABEL_27;
            }
          }
        }
        if ( (*(_DWORD *)(a2 + 336) & 0x10) != 0 )
        {
          CanSidDecryptEntry = CscStorepLowIoOpenFileByFileIdPoster(
                                 (int)v9 + 24,
                                 *(_QWORD *)(a2 + 144),
                                 *(_QWORD *)(a2 + 136),
                                 1048577,
                                 7,
                                 32);
          if ( CanSidDecryptEntry >= 0 )
          {
            CanSidDecryptEntry = CscStorepLowIoDisableImplicitTimeUpdates(*((_QWORD *)v9 + 3));
            if ( CanSidDecryptEntry < 0 )
            {
              v25 = 10577;
              v11 = 0;
              goto LABEL_27;
            }
            v25 = 0;
            goto LABEL_19;
          }
        }
        else
        {
          *((_QWORD *)v9 + 3) = 0;
          CanSidDecryptEntry = -1073741565;
        }
        v25 = 10574;
        v11 = 0;
LABEL_27:
        v15 = 0;
LABEL_30:
        if ( v12 )
        {
          CscSeReleaseTokenUserInformation(v37, v11, v15);
          v11 = v35;
          v15 = a8;
        }
        if ( CanSidDecryptEntry >= 0 )
        {
          *((_QWORD *)v9 + 1) = a2;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 100, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids, a2);
          }
          CscEnReferenceEntry(a2);
LABEL_35:
          CscEnpMainRelease(a2);
          goto LABEL_36;
        }
        a8 = v15;
        v35 = v11;
        if ( v9 )
        {
          *((_DWORD *)v9 + 4) |= 0x800u;
          CscEnCloseEntryOpenHandle(v9, 0, 0);
          v9 = 0;
        }
        else
        {
          v35 = v11;
          a8 = v15;
        }
        goto LABEL_63;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 98, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids, a2);
      }
      if ( (v22 & 0x27) == 0 )
      {
        ++*(_DWORD *)(a2 + 160);
        v25 = 10598;
        CanSidDecryptEntry = 0;
        goto LABEL_29;
      }
      if ( v40 )
      {
        TokenUserInformation = CscSeGetTokenUserInformation(v40, v37);
        v12 = v37[0];
        CanSidDecryptEntry = TokenUserInformation;
        if ( TokenUserInformation < 0 )
        {
          v25 = 10609;
          goto LABEL_69;
        }
        CanSidDecryptEntry = CscEnQueryCanSidDecryptEntry(a2, *(_QWORD *)v37[0], &v39);
        if ( CanSidDecryptEntry < 0 )
        {
          v25 = 10614;
          goto LABEL_69;
        }
        if ( !v39 )
        {
          CanSidDecryptEntry = -1073741790;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              99,
              WPP_2d57263f6f6237979220aa59cf47311d_Traceguids,
              3221225506LL);
          }
          v11 = 0;
          v25 = 10620;
          goto LABEL_27;
        }
      }
      *((_DWORD *)v9 + 4) |= 0x400u;
      if ( *(_QWORD *)(a2 + 168) )
      {
        ++*(_DWORD *)(a2 + 160);
        v25 = 10641;
        ++*(_DWORD *)(a2 + 164);
        CanSidDecryptEntry = 0;
        goto LABEL_29;
      }
      CanSidDecryptEntry = CscEnpUnghostEntry(a2);
      if ( CanSidDecryptEntry < 0 )
      {
        v25 = 10656;
        goto LABEL_69;
      }
      if ( !*(_QWORD *)(a2 + 184) )
      {
        v29 = (struct _ERESOURCE *)ExAllocatePool2(66, 104, 574649155);
        v30 = v29;
        if ( v29 )
        {
          CanSidDecryptEntry = ExInitializeResourceLite(v29);
          if ( CanSidDecryptEntry >= 0 )
          {
            *(_QWORD *)(a2 + 184) = v30;
            goto LABEL_57;
          }
          ExFreePoolWithTag(v30, 0x22407343u);
        }
        else
        {
          CanSidDecryptEntry = -1073741670;
        }
        *(_QWORD *)(a2 + 184) = 0;
        v25 = 10665;
        goto LABEL_69;
      }
LABEL_57:
      CanSidDecryptEntry = CscStorepLowIoOpenFileByFileIdPoster(
                             (unsigned int)&Handle,
                             *(_QWORD *)(a2 + 144),
                             *(_QWORD *)(a2 + 136),
                             2032127,
                             7,
                             40);
      if ( CanSidDecryptEntry < 0 )
      {
        v25 = 10679;
      }
      else
      {
        CanSidDecryptEntry = CscStorepLowIoDisableImplicitTimeUpdates(Handle);
        if ( CanSidDecryptEntry < 0 )
        {
          v25 = 10682;
        }
        else
        {
          CanSidDecryptEntry = CscDiffTransferOpenHandle(a2, (struct _LIST_ENTRY *)Handle);
          if ( CanSidDecryptEntry < 0 )
          {
            v25 = 10690;
          }
          else
          {
            CanSidDecryptEntry = ObReferenceObjectByHandle(
                                   Handle,
                                   0,
                                   (POBJECT_TYPE)IoFileObjectType,
                                   0,
                                   (PVOID *)(a2 + 176),
                                   0);
            if ( CanSidDecryptEntry >= 0 )
            {
              ObfDereferenceObject(*(PVOID *)(a2 + 176));
              v25 = a6;
              *(_QWORD *)(a2 + 168) = Handle;
              *(_DWORD *)(a2 + 164) = 1;
              Handle = 0;
LABEL_19:
              ++*(_DWORD *)(a2 + 160);
              goto LABEL_29;
            }
            v25 = 10698;
          }
        }
      }
LABEL_69:
      v11 = 0;
      goto LABEL_27;
    }
LABEL_83:
    CanSidDecryptEntry = -1073741209;
    goto LABEL_28;
  }
  v31 = 0;
  CanSidDecryptEntry = -1073741811;
  v25 = 10459;
LABEL_64:
  if ( Handle )
  {
    CscStorepLowIoClosePoster(Handle, v11);
    Handle = 0;
  }
  if ( v31 )
    goto LABEL_35;
LABEL_36:
  *a1 = v9;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
  {
    LODWORD(v34) = CanSidDecryptEntry;
    WPP_SF_ddqDD(WPP_GLOBAL_Control->AttachedDevice, v11, v15, v35, a8, v9, v34, v25);
  }
  return (unsigned int)CanSidDecryptEntry;
}

```

## disassembly

```asm
0x14006c560  mov     rax, rsp
0x14006c563  mov     [rax+20h], r9
0x14006c567  push    rbp
0x14006c568  push    rdi
0x14006c569  sub     rsp, 0A8h
0x14006c570  mov     [rax+18h], rbx
0x14006c574  xor     edi, edi
0x14006c576  mov     [rax-20h], r12
0x14006c57a  mov     rbx, rdx
0x14006c57d  xor     edx, edx
0x14006c57f  mov     [rax-28h], r13
0x14006c583  mov     [rax-30h], r14
0x14006c587  xor     r12d, r12d
0x14006c58a  movzx   r14d, byte ptr [rsp+0B8h+arg_28]
0x14006c593  movsx   r13d, r8b
0x14006c597  movzx   ebp, r14b
0x14006c59b  xor     r8d, r8d
0x14006c59e  mov     [rax-38h], r15
0x14006c5a2  and     bpl, 1
0x14006c5a6  mov     qword ptr [rax-50h], 0
0x14006c5ae  mov     r15, rcx
0x14006c5b1  mov     [rsp+0B8h+var_58], edx
0x14006c5b5  mov     [rsp+0B8h+arg_38], r8d
0x14006c5bd  mov     [rax-48h], r12
0x14006c5c1  mov     [rax+10h], dl
0x14006c5c4  mov     [rax+8], dl
0x14006c5c7  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c5ce  lea     r10, WPP_GLOBAL_Control
0x14006c5d5  cmp     rcx, r10
0x14006c5d8  jnz     loc_14006C75D
0x14006c5de  mov     [rsp+0B8h+var_18], rsi
0x14006c5e6  test    rbx, rbx
0x14006c5e9  jz      loc_14006CB3C
0x14006c5ef  mov     rcx, rbx
0x14006c5f2  call    CscEnpMainAcquireExclusive
0x14006c5f7  mov     rcx, rbx
0x14006c5fa  call    CscEnpCheckState
0x14006c5ff  mov     esi, eax
0x14006c601  test    eax, eax
0x14006c603  js      loc_14006CB4E
0x14006c609  mov     eax, [rbx+150h]
0x14006c60f  mov     r9b, 1
0x14006c612  mov     rdi, [rsp+0B8h+arg_40]
0x14006c61a  and     eax, 10h
0x14006c61d  mov     r8, [rsp+0B8h+arg_18]
0x14006c625  movzx   edx, r13b
0x14006c629  mov     [rsp+0B8h+arg_28], eax
0x14006c630  mov     rcx, rbx
0x14006c633  lea     rax, [rsp+0B8h+arg_0]
0x14006c63b  mov     [rsp+0B8h+var_80], rax
0x14006c640  mov     eax, [rsp+0B8h+arg_20]
0x14006c647  mov     [rsp+0B8h+var_88], rdi
0x14006c64c  mov     dword ptr [rsp+0B8h+Object], eax
0x14006c650  call    CscEnAccessCheck
0x14006c655  mov     esi, eax
0x14006c657  cmp     eax, 0C0000022h
0x14006c65c  jz      loc_14006CB5A
0x14006c662  test    eax, eax
0x14006c664  js      loc_14006C7B2
0x14006c66a  mov     ebp, [rsp+0B8h+arg_28]
0x14006c671  lea     r14, WPP_GLOBAL_Control
0x14006c678  mov     r13d, [rsp+0B8h+arg_20]
0x14006c680  mov     eax, 14h
0x14006c685  test    ebp, ebp
0x14006c687  mov     esi, 40h ; '@'
0x14006c68c  mov     r8d, 29407343h
0x14006c692  cmovz   esi, eax
0x14006c695  mov     ecx, 100h
0x14006c69a  mov     edx, esi
0x14006c69c  call    cs:__imp_ExAllocatePool2
0x14006c6a3  nop     dword ptr [rax+rax+00h]
0x14006c6a8  mov     rdi, rax
0x14006c6ab  test    rax, rax
0x14006c6ae  jz      loc_14006CAAC
0x14006c6b4  mov     word ptr [rax], 0DA08h
0x14006c6b9  mov     [rax+2], si
0x14006c6bd  mov     [rsp+0B8h+arg_28], r12d
0x14006c6c5  test    ebp, ebp
0x14006c6c7  jz      loc_14006C8EC
0x14006c6cd  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c6d4  cmp     rcx, r14
0x14006c6d7  jz      short loc_14006C6E6
0x14006c6d9  test    dword ptr [rcx+2Ch], 40000h
0x14006c6e0  jnz     loc_14006CC20
0x14006c6e6  or      dword ptr [rdi+10h], 100h
0x14006c6ed  mov     rax, [rsp+0B8h+arg_30]
0x14006c6f5  test    rax, rax
0x14006c6f8  jnz     loc_14006C8C4
0x14006c6fe  mov     eax, [rbx+150h]
0x14006c704  test    al, 10h
0x14006c706  jz      loc_14006C795
0x14006c70c  mov     r8, [rbx+88h]
0x14006c713  lea     rcx, [rdi+18h]
0x14006c717  mov     rdx, [rbx+90h]
0x14006c71e  mov     r9d, 100001h
0x14006c724  mov     dword ptr [rsp+0B8h+HandleInformation], 20h ; ' '
0x14006c72c  mov     dword ptr [rsp+0B8h+Object], 7
0x14006c734  call    CscStorepLowIoOpenFileByFileIdPoster
0x14006c739  mov     esi, eax
0x14006c73b  test    eax, eax
0x14006c73d  js      short loc_14006C79E
0x14006c73f  mov     rcx, [rdi+18h]
0x14006c743  call    CscStorepLowIoDisableImplicitTimeUpdates
0x14006c748  mov     esi, eax
0x14006c74a  test    eax, eax
0x14006c74c  js      loc_14006CC3D
0x14006c752  mov     ebp, r12d
0x14006c755  inc     dword ptr [rbx+0A0h]
0x14006c75b  jmp     short loc_14006C7C1
0x14006c75d  test    dword ptr [rcx+2Ch], 20000h
0x14006c764  jz      loc_14006C5DE
0x14006c76a  mov     rax, [rsp+0B8h+arg_30]
0x14006c772  mov     edx, 4Eh ; 'N'
0x14006c777  mov     r10d, 59h ; 'Y'
0x14006c77d  test    rax, rax
0x14006c780  jz      loc_14006CAED
0x14006c786  cmp     [rax], dil
0x14006c789  mov     r8d, r10d
0x14006c78c  cmovz   r8d, edx
0x14006c790  jmp     loc_14006CAF3
0x14006c795  mov     [rdi+18h], r12
0x14006c799  mov     esi, 0C0000103h
0x14006c79e  mov     ebp, 294Eh
0x14006c7a3  mov     edx, r12d
0x14006c7a6  lea     r10, WPP_GLOBAL_Control
0x14006c7ad  mov     r8d, edx
0x14006c7b0  jmp     short loc_14006C7E1
0x14006c7b2  xor     edi, edi
0x14006c7b4  mov     ebp, 2921h
0x14006c7b9  test    esi, esi
0x14006c7bb  js      loc_14006CC19
0x14006c7c1  mov     edx, [rbx+0A0h]
0x14006c7c7  lea     r10, WPP_GLOBAL_Control
0x14006c7ce  mov     r8d, [rbx+0A4h]
0x14006c7d5  mov     [rsp+0B8h+var_58], edx
0x14006c7d9  mov     [rsp+0B8h+arg_38], r8d
0x14006c7e1  test    r12, r12
0x14006c7e4  jnz     loc_14006CD59
0x14006c7ea  test    esi, esi
0x14006c7ec  js      loc_14006CD7B
0x14006c7f2  mov     [rdi+8], rbx
0x14006c7f6  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c7fd  cmp     rcx, r10
0x14006c800  jnz     loc_14006C89A
0x14006c806  mov     rcx, rbx
0x14006c809  call    CscEnReferenceEntry
0x14006c80e  mov     rcx, rbx
0x14006c811  call    CscEnpMainRelease
0x14006c816  mov     [r15], rdi
0x14006c819  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c820  lea     rax, WPP_GLOBAL_Control
0x14006c827  mov     r15, [rsp+0B8h+var_38]
0x14006c82f  mov     r14, [rsp+0B8h+var_30]
0x14006c837  mov     r13, [rsp+0B8h+var_28]
0x14006c83f  mov     r12, [rsp+0B8h+var_20]
0x14006c847  mov     rbx, [rsp+0B8h+arg_10]
0x14006c84f  cmp     rcx, rax
0x14006c852  jnz     short loc_14006C869
0x14006c854  mov     eax, esi
0x14006c856  mov     rsi, [rsp+0B8h+var_18]
0x14006c85e  add     rsp, 0A8h
0x14006c865  pop     rdi
0x14006c866  pop     rbp
0x14006c867  retn
0x14006c869  test    dword ptr [rcx+2Ch], 20000h
0x14006c870  jz      short loc_14006C854
0x14006c872  mov     eax, [rsp+0B8h+arg_38]
0x14006c879  mov     r9d, [rsp+0B8h+var_58]
0x14006c87e  mov     rcx, [rcx+18h]
0x14006c882  mov     dword ptr [rsp+0B8h+var_80], ebp
0x14006c886  mov     dword ptr [rsp+0B8h+var_88], esi
0x14006c88a  mov     [rsp+0B8h+HandleInformation], rdi
0x14006c88f  mov     dword ptr [rsp+0B8h+Object], eax
0x14006c893  call    WPP_SF_ddqDD
0x14006c898  jmp     short loc_14006C854
0x14006c89a  test    dword ptr [rcx+2Ch], 40000h
0x14006c8a1  jz      loc_14006C806
0x14006c8a7  mov     rcx, [rcx+18h]
0x14006c8ab  lea     r8, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids
0x14006c8b2  mov     edx, 64h ; 'd'
0x14006c8b7  mov     r9, rbx
0x14006c8ba  call    WPP_SF_q
0x14006c8bf  jmp     loc_14006C806
0x14006c8c4  cmp     [rax], r12b
0x14006c8c7  jz      loc_14006C6FE
0x14006c8cd  mov     rcx, rbx
0x14006c8d0  call    CscEnpUnghostEntry
0x14006c8d5  mov     esi, eax
0x14006c8d7  test    eax, eax
0x14006c8d9  jns     loc_14006C6FE
0x14006c8df  mov     ebp, 2949h
0x14006c8e4  mov     edx, r12d
0x14006c8e7  jmp     loc_14006C7A6
0x14006c8ec  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c8f3  cmp     rcx, r14
0x14006c8f6  jnz     loc_14006CC4A
0x14006c8fc  test    r13b, 27h
0x14006c900  jz      loc_14006CC74
0x14006c906  mov     rax, [rsp+0B8h+arg_18]
0x14006c90e  test    rax, rax
0x14006c911  jz      short loc_14006C95B
0x14006c913  lea     rdx, [rsp+0B8h+var_48]
0x14006c918  mov     rcx, rax
0x14006c91b  call    CscSeGetTokenUserInformation
0x14006c920  mov     r12, [rsp+0B8h+var_48]
0x14006c925  mov     esi, eax
0x14006c927  test    eax, eax
0x14006c929  js      loc_14006CC86
0x14006c92f  mov     rdx, [r12]
0x14006c933  lea     r8, [rsp+0B8h+arg_8]
0x14006c93b  mov     rcx, rbx
0x14006c93e  call    CscEnQueryCanSidDecryptEntry
0x14006c943  mov     esi, eax
0x14006c945  test    eax, eax
0x14006c947  js      loc_14006CC90
0x14006c94d  cmp     [rsp+0B8h+arg_8], 0
0x14006c955  jz      loc_14006CC9A
0x14006c95b  or      dword ptr [rdi+10h], 400h
0x14006c962  cmp     qword ptr [rbx+0A8h], 0
0x14006c96a  jnz     loc_14006CCEB
0x14006c970  mov     rcx, rbx
0x14006c973  call    CscEnpUnghostEntry
0x14006c978  mov     esi, eax
0x14006c97a  test    eax, eax
0x14006c97c  js      loc_14006CD03
0x14006c982  cmp     qword ptr [rbx+0B8h], 0
0x14006c98a  jnz     short loc_14006C9D4
0x14006c98c  mov     edx, 68h ; 'h'
0x14006c991  mov     ecx, 42h ; 'B'
0x14006c996  mov     r8d, 22407343h
0x14006c99c  call    cs:__imp_ExAllocatePool2
0x14006c9a3  nop     dword ptr [rax+rax+00h]
0x14006c9a8  mov     rbp, rax
0x14006c9ab  test    rax, rax
0x14006c9ae  jz      loc_14006CD25
0x14006c9b4  mov     rcx, rax; Resource
0x14006c9b7  call    cs:__imp_ExInitializeResourceLite
0x14006c9be  nop     dword ptr [rax+rax+00h]
0x14006c9c3  mov     esi, eax
0x14006c9c5  test    eax, eax
0x14006c9c7  js      loc_14006CD0D
0x14006c9cd  mov     [rbx+0B8h], rbp
0x14006c9d4  mov     r8, [rbx+88h]
0x14006c9db  lea     rcx, [rsp+0B8h+Handle]
0x14006c9e0  mov     rdx, [rbx+90h]
0x14006c9e7  mov     r9d, 1F01FFh
0x14006c9ed  mov     dword ptr [rsp+0B8h+HandleInformation], 28h ; '('
0x14006c9f5  mov     dword ptr [rsp+0B8h+Object], 7
0x14006c9fd  call    CscStorepLowIoOpenFileByFileIdPoster
0x14006ca02  mov     esi, eax
0x14006ca04  test    eax, eax
0x14006ca06  js      loc_14006CD3B
0x14006ca0c  mov     rcx, [rsp+0B8h+Handle]
0x14006ca11  call    CscStorepLowIoDisableImplicitTimeUpdates
0x14006ca16  mov     esi, eax
0x14006ca18  test    eax, eax
0x14006ca1a  js      loc_14006CD45
0x14006ca20  mov     rdx, [rsp+0B8h+Handle]
0x14006ca25  mov     rcx, rbx
0x14006ca28  call    CscDiffTransferOpenHandle
0x14006ca2d  mov     esi, eax
0x14006ca2f  test    eax, eax
0x14006ca31  js      loc_14006CD4F
0x14006ca37  mov     r8, cs:__imp_IoFileObjectType
0x14006ca3e  lea     r14, [rbx+0B0h]
0x14006ca45  mov     rcx, [rsp+0B8h+Handle]; Handle
0x14006ca4a  xor     r9d, r9d; AccessMode
0x14006ca4d  mov     [rsp+0B8h+HandleInformation], 0; HandleInformation
0x14006ca56  xor     edx, edx; DesiredAccess
0x14006ca58  mov     [rsp+0B8h+Object], r14; Object
0x14006ca5d  mov     r8, [r8]; ObjectType
0x14006ca60  call    cs:__imp_ObReferenceObjectByHandle
0x14006ca67  nop     dword ptr [rax+rax+00h]
0x14006ca6c  mov     esi, eax
0x14006ca6e  test    eax, eax
0x14006ca70  js      short loc_14006CADF
0x14006ca72  mov     rcx, [r14]; Object
0x14006ca75  call    cs:__imp_ObfDereferenceObject
0x14006ca7c  nop     dword ptr [rax+rax+00h]
0x14006ca81  mov     rax, [rsp+0B8h+Handle]
0x14006ca86  mov     ebp, [rsp+0B8h+arg_28]
0x14006ca8d  mov     [rbx+0A8h], rax
0x14006ca94  mov     dword ptr [rbx+0A4h], 1
0x14006ca9e  mov     [rsp+0B8h+Handle], 0
0x14006caa7  jmp     loc_14006C755
0x14006caac  mov     esi, 0C000009Ah
0x14006cab1  mov     ebp, 2931h
0x14006cab6  mov     r14b, 1
0x14006cab9  mov     rcx, [rsp+0B8h+Handle]
0x14006cabe  test    rcx, rcx
0x14006cac1  jz      short loc_14006CAD1
0x14006cac3  call    CscStorepLowIoClosePoster
0x14006cac8  mov     [rsp+0B8h+Handle], 0
0x14006cad1  test    r14b, r14b
0x14006cad4  jz      loc_14006C816
0x14006cada  jmp     loc_14006C80E
0x14006cadf  mov     ebp, 29CAh
0x14006cae4  mov     edx, [rsp+0B8h+var_58]
0x14006cae8  jmp     loc_14006C7A6
0x14006caed  mov     r8d, 3Fh ; '?'
  ... truncated ...
```
