# FatGetRetrievalPointers

- ea: `0x14003f6e0`
- end: `0x14003fcf5`
- name: `FatGetRetrievalPointers`
- size: `1557`
- prototype: `__int64 __fastcall(PVOID Entry, PIRP Irp)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x140042ac0`

## callees

- `0x140005c80`
- `0x14002006c`
- `0x140020168`
- `0x1400201b0`
- `0x1400226b8`
- `0x14002d5a8`
- `0x140038eb4`
- `0x14003d880`
- `0x14003f50c`
- `0x14003f6e0`
- `0x140040330`
- `0x1400465f4`
- `0x1400466c8`
- `0x1400468c4`
- `0x140049fa8`
- `0x14004a1d4`

## import_xrefs

- `ntoskrnl!FsRtlNumberOfRunsInLargeMcb` at `0x14003f9ec`
- `ntoskrnl!FsRtlNumberOfRunsInLargeMcb` at `0x14003f9ec`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14003fa79`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14003fa9c`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14003fbf3`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14003fc16`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14003fc86`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14003fca9`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14003fa79`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14003fa9c`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14003fbf3`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14003fc16`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14003fc86`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14003fca9`
- `ntoskrnl!ProbeForWrite` at `0x14003f93d`
- `ntoskrnl!ProbeForWrite` at `0x14003f93d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003fc70`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ecee`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003fc70`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ecee`
- `ntoskrnl!KeBugCheckEx` at `0x14003f9dd`
- `ntoskrnl!KeBugCheckEx` at `0x14003fb02`
- `ntoskrnl!KeBugCheckEx` at `0x14003f9dd`
- `ntoskrnl!KeBugCheckEx` at `0x14003fb02`
- `ntoskrnl!ExRaiseStatus` at `0x14003f8b6`
- `ntoskrnl!ExRaiseStatus` at `0x14003fab2`
- `ntoskrnl!ExRaiseStatus` at `0x14003fc2c`
- `ntoskrnl!ExRaiseStatus` at `0x14003fcbf`
- `ntoskrnl!ExRaiseStatus` at `0x14003f8b6`
- `ntoskrnl!ExRaiseStatus` at `0x14003fab2`
- `ntoskrnl!ExRaiseStatus` at `0x14003fc2c`
- `ntoskrnl!ExRaiseStatus` at `0x14003fcbf`

## pseudocode

```c
__int64 __fastcall FatGetRetrievalPointers(_DWORD *Entry, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r13
  __int64 v5; // r9
  int v6; // r12d
  __int64 v7; // rcx
  IRP *v8; // rdx
  unsigned int v9; // ebx
  unsigned int Options; // ebx
  unsigned int v11; // edi
  __int64 v12; // r8
  __int64 v13; // rbx
  __int64 v14; // r15
  ULONG_PTR v15; // rdi
  unsigned __int8 v16; // bl
  __int64 ULong64FromUser; // rax
  ULONG_PTR BugCheckParameter4; // r12
  LARGE_MCB *v19; // r13
  ULONG v20; // eax
  unsigned int v21; // ebx
  ULONG v22; // r12d
  __int64 v23; // rdx
  __int64 *v24; // r13
  __int64 v25; // rdx
  unsigned int v26; // eax
  unsigned __int64 v27; // rdx
  struct _ERESOURCE *v28; // rcx
  unsigned int v30; // [rsp+34h] [rbp-94h] BYREF
  volatile void *Address; // [rsp+38h] [rbp-90h]
  __int64 v32; // [rsp+40h] [rbp-88h] BYREF
  __int64 v33; // [rsp+48h] [rbp-80h] BYREF
  unsigned int Length; // [rsp+50h] [rbp-78h]
  ULONG Length_4; // [rsp+54h] [rbp-74h]
  int v36; // [rsp+58h] [rbp-70h]
  ULONG_PTR BugCheckParameter2; // [rsp+60h] [rbp-68h] BYREF
  ULONG_PTR BugCheckParameter3; // [rsp+68h] [rbp-60h]
  __int64 v39; // [rsp+70h] [rbp-58h] BYREF
  int v40; // [rsp+78h] [rbp-50h]
  int v41; // [rsp+7Ch] [rbp-4Ch]
  ULONG v42; // [rsp+80h] [rbp-48h]
  unsigned __int64 v43[8]; // [rsp+88h] [rbp-40h] BYREF
  unsigned __int8 v44; // [rsp+E0h] [rbp+18h]
  ULONG_PTR v45; // [rsp+E8h] [rbp+20h] BYREF

  v33 = 0;
  BugCheckParameter2 = 0;
  v32 = 0;
  LODWORD(v45) = 0;
  v30 = 0;
  v39 = 0;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  Entry[17] |= 2u;
  v6 = FatDecodeFileObject(CurrentStackLocation->FileObject, &v33, &BugCheckParameter2, &v32);
  v36 = v6;
  v7 = (unsigned int)(v6 - 2);
  v8 = Irp;
  if ( (unsigned int)v7 <= 2 )
  {
    Options = CurrentStackLocation->Parameters.Create.Options;
    v11 = CurrentStackLocation->Parameters.Read.Length;
    Length = v11;
    Address = (volatile void *)FatMapUserBuffer(v7, Irp);
    if ( Options < 8 || v11 < 0x20 )
    {
      v9 = -1073741789;
      goto LABEL_69;
    }
    BugCheckParameter3 = 0;
    v44 = 0;
    v13 = 0;
    if ( (unsigned int)(v6 - 2) <= 1 )
    {
      v15 = BugCheckParameter2;
      if ( (*(_DWORD *)(*(_QWORD *)(BugCheckParameter2 + 184) + 200LL) & 0x4000) != 0 )
        FatAcquireSharedFcb(Entry, BugCheckParameter2, v12, v5);
      else
        FatAcquireExclusiveFcb(Entry, BugCheckParameter2, v12, v5);
    }
    else
    {
      if ( v6 == 4 )
      {
        if ( !v32 || (*(_DWORD *)(v32 + 4) & 0x20000) == 0 )
        {
          v9 = -1073741790;
          goto LABEL_69;
        }
        v14 = v33;
        FatAcquireExclusiveVcb_Real(Entry, v33, 0, v5);
        v15 = BugCheckParameter2;
LABEL_16:
        if ( (unsigned int)(v6 - 2) <= 1 )
        {
          FatVerifyFcb(Entry, v15);
          if ( *(_QWORD *)(v15 + 24) == -1 )
          {
            FatLookupFileAllocationSize(Entry, v15);
            if ( *(_WORD *)v15 == 1283 || *(_WORD *)v15 == 1284 && *(_BYTE *)(v14 + 376) == 32 )
              *(_DWORD *)(v15 + 32) = *(_DWORD *)(v15 + 24);
          }
          v44 = *(_BYTE *)(v14 + 378);
          v40 = v44;
          v13 = *(unsigned int *)(v15 + 24);
          BugCheckParameter3 = v15 + 288;
        }
        else if ( v6 == 4 )
        {
          FatQuickVerifyVcb(Entry, v14, v12, v5);
          if ( (*(_DWORD *)(v14 + 200) & 0x100000) == 0 )
          {
            Entry[18] = -1073741566;
            ExRaiseStatus(-1073741566);
          }
          v16 = *(_BYTE *)(v14 + 378);
          v44 = v16;
          v40 = v16;
          BugCheckParameter3 = v14 + 416;
          if ( (unsigned __int8)FatLookupLastMcbEntry(v14, v14 + 416, &v30, &v39, &v32) )
            v13 = -(__int64)(unsigned int)(1 << v16) & ((unsigned int)(1 << v16) + v30 - 1LL);
          else
            v13 = 0;
        }
        if ( Irp->RequestorMode )
          ProbeForWrite(Address, Length, 1u);
        if ( Irp->RequestorMode )
          ULong64FromUser = RtlReadULong64FromUser(CurrentStackLocation->Parameters.CreatePipe.Parameters);
        else
          ULong64FromUser = *(_QWORD *)CurrentStackLocation->Parameters.CreatePipe.Parameters;
        if ( HIDWORD(ULong64FromUser)
          || (BugCheckParameter4 = (unsigned int)ULong64FromUser, (unsigned int)ULong64FromUser >= v13 >> v44) )
        {
          v9 = -1073741807;
        }
        else
        {
          v43[0] = 0;
          v19 = (LARGE_MCB *)BugCheckParameter3;
          if ( !(unsigned __int8)FatLookupMcbEntry(
                                   v14,
                                   BugCheckParameter3,
                                   (unsigned int)((_DWORD)ULong64FromUser << v44),
                                   v43,
                                   0,
                                   &v45) )
            KeBugCheckEx(0x23u, 0x1315F7u, v15, (ULONG_PTR)v19, BugCheckParameter4);
          v20 = FsRtlNumberOfRunsInLargeMcb(v19);
          Length_4 = v20;
          v21 = 0;
          v41 = 0;
          v22 = v45;
          v42 = v45;
          while ( 1 )
          {
            if ( v22 >= v20 )
            {
              Irp->IoStatus.Information = (int)(16 * (v21 + 1));
              v9 = 0;
              goto LABEL_63;
            }
            v30 = 0;
            v39 = 0;
            LODWORD(v32) = 0;
            if ( 16 * (v21 + 2) > Length )
              break;
            if ( !(unsigned __int8)FatGetNextMcbEntry(v14, v19, v22, &v30, &v39, &v32) )
              KeBugCheckEx(0x23u, 0x13162Cu, v15, (ULONG_PTR)v19, v22);
            v43[0] = v30;
            v23 = (__int64)(v30 + (unsigned __int64)(unsigned int)v32) >> v44;
            v24 = (__int64 *)((char *)Address + 16 * v21 + 16);
            if ( Irp->RequestorMode )
              RtlWriteULong64ToUser((char *)Address + 16 * v21 + 16, v23);
            else
              *v24 = v23;
            v25 = (unsigned int)((v39 - *(_QWORD *)(v14 + 352)) >> *(_BYTE *)(v14 + 378));
            if ( Irp->RequestorMode )
              RtlWriteULong64ToUser(v24 + 1, v25);
            else
              v24[1] = v25;
            if ( !v21 )
            {
              v26 = Length_4 - v45;
              if ( Irp->RequestorMode )
                RtlWriteULongToUser(Address, v26);
              else
                *(_DWORD *)Address = v26;
              v27 = v43[0] >> v44;
              if ( Irp->RequestorMode )
                RtlWriteULong64ToUser((char *)Address + 8, v27);
              else
                *((_QWORD *)Address + 1) = v27;
            }
            v41 = ++v21;
            v42 = ++v22;
            v19 = (LARGE_MCB *)BugCheckParameter3;
            v20 = Length_4;
          }
          if ( Irp->RequestorMode )
            RtlWriteULongToUser(Address, v21);
          else
            *(_DWORD *)Address = v21;
          Irp->IoStatus.Information = (int)(16 * (v21 + 1));
          v9 = -2147483643;
        }
LABEL_63:
        if ( (unsigned int)(v36 - 2) <= 1 )
        {
          v28 = *(struct _ERESOURCE **)(v15 + 8);
          goto LABEL_67;
        }
        if ( v36 == 4 )
        {
          v28 = (struct _ERESOURCE *)(v14 + 520);
LABEL_67:
          ExReleaseResourceLite(v28);
        }
LABEL_69:
        v8 = Irp;
        goto LABEL_70;
      }
      v15 = BugCheckParameter2;
    }
    v14 = v33;
    goto LABEL_16;
  }
  v9 = -1073741811;
LABEL_70:
  FatCompleteRequest_Real(Entry, v8, v9, v5);
  return v9;
}

```

## disassembly

```asm
0x14003f6e0  mov     rax, rsp
0x14003f6e3  mov     [rax+10h], rdx
0x14003f6e7  mov     [rax+8], rcx
0x14003f6eb  push    rbx
0x14003f6ec  push    rsi
0x14003f6ed  push    rdi
0x14003f6ee  push    r12
0x14003f6f0  push    r13
0x14003f6f2  push    r14
0x14003f6f4  push    r15
0x14003f6f6  sub     rsp, 90h
0x14003f6fd  mov     rsi, rdx
0x14003f700  mov     r14, rcx
0x14003f703  xor     r15d, r15d
0x14003f706  mov     [rax-80h], r15
0x14003f70a  mov     [rax-68h], r15
0x14003f70e  mov     [rsp+0C8h+var_88], r15
0x14003f713  mov     [rax+20h], r15d
0x14003f717  mov     [rsp+0C8h+var_94], r15d
0x14003f71c  mov     [rax-58h], r15
0x14003f720  mov     r13, [rdx+0B8h]
0x14003f727  or      dword ptr [rcx+44h], 2
0x14003f72b  lea     r9, [rsp+0C8h+var_88]
0x14003f730  lea     r8, [rax-68h]
0x14003f734  lea     rdx, [rax-80h]
0x14003f738  mov     rcx, [r13+30h]
0x14003f73c  call    FatDecodeFileObject
0x14003f741  mov     r12d, eax
0x14003f744  mov     [rsp+0C8h+var_70], eax
0x14003f748  lea     ecx, [rax-2]
0x14003f74b  mov     rdx, rsi
0x14003f74e  cmp     ecx, 2
0x14003f751  jbe     short loc_14003F75D
0x14003f753  mov     ebx, 0C000000Dh
0x14003f758  jmp     loc_14003FCD4
0x14003f75d  mov     ebx, [r13+10h]
0x14003f761  mov     edi, [r13+8]
0x14003f765  mov     dword ptr [rsp+0C8h+Length], edi
0x14003f769  call    FatMapUserBuffer
0x14003f76e  mov     [rsp+0C8h+Address], rax
0x14003f773  cmp     ebx, 8
0x14003f776  jb      loc_14003FCCC
0x14003f77c  cmp     edi, 20h ; ' '
0x14003f77f  jb      loc_14003FCCC
0x14003f785  mov     [rsp+0C8h+var_98], r15d
0x14003f78a  mov     [rsp+0C8h+BugCheckParameter3], r15
0x14003f78f  mov     [rsp+0C8h+arg_10], r15d
0x14003f797  mov     rbx, r15
0x14003f79a  lea     eax, [r12-2]
0x14003f79f  cmp     eax, 1
0x14003f7a2  jbe     short loc_14003F7E8
0x14003f7a4  cmp     r12d, 4
0x14003f7a8  jnz     short loc_14003F7E1
0x14003f7aa  mov     rax, [rsp+0C8h+var_88]
0x14003f7af  test    rax, rax
0x14003f7b2  jz      short loc_14003F7D7
0x14003f7b4  test    dword ptr [rax+4], 20000h
0x14003f7bb  jz      short loc_14003F7D7
0x14003f7bd  xor     r8d, r8d
0x14003f7c0  mov     r15, [rsp+0C8h+var_80]
0x14003f7c5  mov     rdx, r15
0x14003f7c8  mov     rcx, r14
0x14003f7cb  call    FatAcquireExclusiveVcb_Real
0x14003f7d0  mov     rdi, [rsp+0C8h+BugCheckParameter2]
0x14003f7d5  jmp     short loc_14003F817
0x14003f7d7  mov     ebx, 0C0000022h
0x14003f7dc  jmp     loc_14003FCD1
0x14003f7e1  mov     rdi, [rsp+0C8h+BugCheckParameter2]
0x14003f7e6  jmp     short loc_14003F812
0x14003f7e8  mov     rdi, [rsp+0C8h+BugCheckParameter2]
0x14003f7ed  mov     rax, [rdi+0B8h]
0x14003f7f4  mov     ecx, [rax+0C8h]
0x14003f7fa  mov     rdx, rdi
0x14003f7fd  bt      ecx, 0Eh
0x14003f801  mov     rcx, r14
0x14003f804  jnb     short loc_14003F80D
0x14003f806  call    FatAcquireSharedFcb
0x14003f80b  jmp     short loc_14003F812
0x14003f80d  call    FatAcquireExclusiveFcb
0x14003f812  mov     r15, [rsp+0C8h+var_80]
0x14003f817  lea     eax, [r12-2]
0x14003f81c  cmp     eax, 1
0x14003f81f  jbe     loc_14003F8C2
0x14003f825  cmp     r12d, 4
0x14003f829  jnz     loc_14003F928
0x14003f82f  mov     rdx, r15
0x14003f832  mov     rcx, r14
0x14003f835  call    FatQuickVerifyVcb
0x14003f83a  mov     eax, [r15+0C8h]
0x14003f841  bt      eax, 14h
0x14003f845  jnb     short loc_14003F8AD
0x14003f847  movzx   ebx, byte ptr [r15+17Ah]
0x14003f84f  mov     [rsp+0C8h+arg_10], ebx
0x14003f856  mov     [rsp+0C8h+var_50], ebx
0x14003f85a  lea     r12, [r15+1A0h]
0x14003f861  mov     [rsp+0C8h+BugCheckParameter3], r12
0x14003f866  lea     rax, [rsp+0C8h+var_88]
0x14003f86b  mov     [rsp+0C8h+BugCheckParameter4], rax
0x14003f870  lea     r9, [rsp+0C8h+var_58]
0x14003f875  lea     r8, [rsp+0C8h+var_94]
0x14003f87a  mov     rdx, r12
0x14003f87d  mov     rcx, r15
0x14003f880  call    FatLookupLastMcbEntry
0x14003f885  test    al, al
0x14003f887  jnz     short loc_14003F890
0x14003f889  xor     ebx, ebx
0x14003f88b  jmp     loc_14003F928
0x14003f890  mov     ecx, ebx
0x14003f892  mov     eax, 1
0x14003f897  shl     eax, cl
0x14003f899  mov     ecx, eax
0x14003f89b  mov     ebx, [rsp+0C8h+var_94]
0x14003f89f  dec     rbx
0x14003f8a2  add     rbx, rcx
0x14003f8a5  neg     rcx
0x14003f8a8  and     rbx, rcx
0x14003f8ab  jmp     short loc_14003F928
0x14003f8ad  mov     ecx, 0C0000102h; Status
0x14003f8b2  mov     [r14+48h], ecx
0x14003f8b6  call    cs:__imp_ExRaiseStatus
0x14003f8c2  mov     rdx, rdi
0x14003f8c5  mov     rcx, r14
0x14003f8c8  call    FatVerifyFcb
0x14003f8cd  cmp     qword ptr [rdi+18h], 0FFFFFFFFFFFFFFFFh
0x14003f8d2  jnz     short loc_14003F906
0x14003f8d4  mov     rdx, rdi
0x14003f8d7  mov     rcx, r14
0x14003f8da  call    FatLookupFileAllocationSize
0x14003f8df  movzx   eax, word ptr [rdi]
0x14003f8e2  mov     ecx, 503h
0x14003f8e7  cmp     ax, cx
0x14003f8ea  jz      short loc_14003F900
0x14003f8ec  mov     ecx, 504h
0x14003f8f1  cmp     ax, cx
0x14003f8f4  jnz     short loc_14003F906
0x14003f8f6  cmp     byte ptr [r15+178h], 20h ; ' '
0x14003f8fe  jnz     short loc_14003F906
0x14003f900  mov     eax, [rdi+18h]
0x14003f903  mov     [rdi+20h], eax
0x14003f906  movzx   edx, byte ptr [r15+17Ah]
0x14003f90e  mov     [rsp+0C8h+arg_10], edx
0x14003f915  mov     [rsp+0C8h+var_50], edx
0x14003f919  mov     ebx, [rdi+18h]
0x14003f91c  lea     rax, [rdi+120h]
0x14003f923  mov     [rsp+0C8h+BugCheckParameter3], rax
0x14003f928  cmp     byte ptr [rsi+40h], 0
0x14003f92c  jz      short loc_14003F949
0x14003f92e  mov     edx, dword ptr [rsp+0C8h+Length]; Length
0x14003f932  mov     r8d, 1; Alignment
0x14003f938  mov     rcx, [rsp+0C8h+Address]; Address
0x14003f93d  call    cs:__imp_ProbeForWrite
0x14003f944  nop     dword ptr [rax+rax+00h]
0x14003f949  mov     rax, [r13+20h]
0x14003f94d  cmp     byte ptr [rsi+40h], 0
0x14003f951  jz      short loc_14003F95D
0x14003f953  mov     rcx, rax
0x14003f956  call    RtlReadULong64FromUser
0x14003f95b  jmp     short loc_14003F960
0x14003f95d  mov     rax, [rax]
0x14003f960  mov     rcx, rax
0x14003f963  sar     rcx, 20h
0x14003f967  test    ecx, ecx
0x14003f969  jnz     loc_14003FC49
0x14003f96f  mov     r12d, eax
0x14003f972  mov     ecx, [rsp+0C8h+arg_10]
0x14003f979  sar     rbx, cl
0x14003f97c  cmp     r12, rbx
0x14003f97f  jge     loc_14003FC49
0x14003f985  mov     [rsp+0C8h+var_40], 0
0x14003f991  shl     eax, cl
0x14003f993  lea     rcx, [rsp+0C8h+arg_18]
0x14003f99b  mov     [rsp+0C8h+var_A0], rcx
0x14003f9a0  mov     [rsp+0C8h+BugCheckParameter4], 0
0x14003f9a9  lea     r9, [rsp+0C8h+var_40]
0x14003f9b1  mov     r8d, eax
0x14003f9b4  mov     r13, [rsp+0C8h+BugCheckParameter3]
0x14003f9b9  mov     rdx, r13
0x14003f9bc  mov     rcx, r15
0x14003f9bf  call    FatLookupMcbEntry
0x14003f9c4  test    al, al
0x14003f9c6  jnz     short loc_14003F9E9
0x14003f9c8  mov     [rsp+0C8h+BugCheckParameter4], r12; BugCheckParameter4
0x14003f9cd  mov     r9, r13; BugCheckParameter3
0x14003f9d0  mov     r8, rdi; BugCheckParameter2
0x14003f9d3  mov     edx, 1315F7h; BugCheckParameter1
0x14003f9d8  mov     ecx, 23h ; '#'; BugCheckCode
0x14003f9dd  call    cs:__imp_KeBugCheckEx
0x14003f9e9  mov     rcx, r13; Mcb
0x14003f9ec  call    cs:__imp_FsRtlNumberOfRunsInLargeMcb
0x14003f9f3  nop     dword ptr [rax+rax+00h]
0x14003f9f8  mov     dword ptr [rsp+0C8h+Length+4], eax
0x14003f9fc  xor     ebx, ebx
0x14003f9fe  mov     [rsp+0C8h+var_4C], ebx
0x14003fa02  mov     r12d, dword ptr [rsp+0C8h+arg_18]
0x14003fa0a  mov     [rsp+0C8h+var_48], r12d
0x14003fa12  cmp     r12d, eax
0x14003fa15  jnb     loc_14003FC39
0x14003fa1b  mov     [rsp+0C8h+var_94], 0
0x14003fa23  mov     [rsp+0C8h+var_58], 0
0x14003fa2c  mov     dword ptr [rsp+0C8h+var_88], 0
0x14003fa34  lea     eax, [rbx+2]
0x14003fa37  shl     eax, 4
0x14003fa3a  cmp     eax, dword ptr [rsp+0C8h+Length]
0x14003fa3e  jbe     short loc_14003FABF
0x14003fa40  cmp     byte ptr [rsi+40h], 0
0x14003fa44  jz      short loc_14003FA54
0x14003fa46  mov     edx, ebx
0x14003fa48  mov     rcx, [rsp+0C8h+Address]
0x14003fa4d  call    RtlWriteULongToUser
0x14003fa52  jmp     short loc_14003FA5B
0x14003fa54  mov     rax, [rsp+0C8h+Address]
0x14003fa59  mov     [rax], ebx
0x14003fa5b  lea     eax, [rbx+1]
0x14003fa5e  shl     eax, 4
0x14003fa61  cdqe
0x14003fa63  mov     [rsi+38h], rax
0x14003fa67  mov     ebx, 80000005h
0x14003fa6c  jmp     loc_14003FC4E
0x14003fa71  mov     ebx, eax
0x14003fa73  mov     [rsp+0C8h+var_98], eax
0x14003fa77  mov     ecx, eax; Exception
0x14003fa79  call    cs:__imp_FsRtlIsNtstatusExpected
0x14003fa80  nop     dword ptr [rax+rax+00h]
0x14003fa85  mov     edx, 0C00000E8h
0x14003fa8a  test    al, al
0x14003fa8c  cmovnz  edx, ebx
0x14003fa8f  mov     rcx, [rsp+0C8h+arg_0]
0x14003fa97  mov     [rcx+48h], edx
0x14003fa9a  mov     ecx, ebx; Exception
0x14003fa9c  call    cs:__imp_FsRtlIsNtstatusExpected
0x14003faa3  nop     dword ptr [rax+rax+00h]
0x14003faa8  mov     ecx, 0C00000E8h
0x14003faad  test    al, al
0x14003faaf  cmovnz  ecx, ebx; Status
0x14003fab2  call    cs:__imp_ExRaiseStatus
0x14003fabf  lea     rax, [rsp+0C8h+var_88]
0x14003fac4  mov     [rsp+0C8h+var_A0], rax
0x14003fac9  lea     rax, [rsp+0C8h+var_58]
0x14003face  mov     [rsp+0C8h+BugCheckParameter4], rax
0x14003fad3  lea     r9, [rsp+0C8h+var_94]
0x14003fad8  mov     r8d, r12d
0x14003fadb  mov     rdx, r13
0x14003fade  mov     rcx, r15
0x14003fae1  call    FatGetNextMcbEntry
0x14003fae6  test    al, al
0x14003fae8  jnz     short loc_14003FB0F
0x14003faea  mov     eax, r12d
0x14003faed  mov     [rsp+0C8h+BugCheckParameter4], rax; BugCheckParameter4
0x14003faf2  mov     r9, r13; BugCheckParameter3
0x14003faf5  mov     r8, rdi; BugCheckParameter2
0x14003faf8  mov     edx, 13162Ch; BugCheckParameter1
0x14003fafd  mov     ecx, 23h ; '#'; BugCheckCode
0x14003fb02  call    cs:__imp_KeBugCheckEx
0x14003fb0f  mov     eax, [rsp+0C8h+var_94]
0x14003fb13  mov     [rsp+0C8h+var_40], rax
0x14003fb1b  mov     edx, dword ptr [rsp+0C8h+var_88]
0x14003fb1f  add     rdx, rax
0x14003fb22  mov     ecx, [rsp+0C8h+arg_10]
0x14003fb29  sar     rdx, cl
0x14003fb2c  mov     r13d, ebx
0x14003fb2f  inc     r13
0x14003fb32  shl     r13, 4
0x14003fb36  add     r13, [rsp+0C8h+Address]
0x14003fb3b  cmp     byte ptr [rsi+40h], 0
0x14003fb3f  jz      short loc_14003FB4B
0x14003fb41  mov     rcx, r13
0x14003fb44  call    RtlWriteULong64ToUser
0x14003fb49  jmp     short loc_14003FB4F
0x14003fb4b  mov     [r13+0], rdx
0x14003fb4f  mov     rdx, [rsp+0C8h+var_58]
0x14003fb54  sub     rdx, [r15+160h]
0x14003fb5b  mov     cl, [r15+17Ah]
0x14003fb62  sar     rdx, cl
0x14003fb65  mov     edx, edx
0x14003fb67  cmp     byte ptr [rsi+40h], 0
0x14003fb6b  jz      short loc_14003FB78
0x14003fb6d  lea     rcx, [r13+8]
0x14003fb71  call    RtlWriteULong64ToUser
0x14003fb76  jmp     short loc_14003FB7C
0x14003fb78  mov     [r13+8], rdx
0x14003fb7c  test    ebx, ebx
0x14003fb7e  jnz     short loc_14003FBCC
0x14003fb80  mov     eax, dword ptr [rsp+0C8h+Length+4]
0x14003fb84  sub     eax, dword ptr [rsp+0C8h+arg_18]
0x14003fb8b  mov     rcx, [rsp+0C8h+Address]
0x14003fb90  cmp     [rsi+40h], bl
0x14003fb93  jz      short loc_14003FB9E
0x14003fb95  mov     edx, eax
0x14003fb97  call    RtlWriteULongToUser
0x14003fb9c  jmp     short loc_14003FBA0
0x14003fb9e  mov     [rcx], eax
0x14003fba0  mov     ecx, [rsp+0C8h+arg_10]
0x14003fba7  mov     rdx, [rsp+0C8h+var_40]
0x14003fbaf  shr     rdx, cl
0x14003fbb2  mov     rax, [rsp+0C8h+Address]
0x14003fbb7  cmp     byte ptr [rsi+40h], 0
0x14003fbbb  jz      short loc_14003FBC8
0x14003fbbd  lea     rcx, [rax+8]
0x14003fbc1  call    RtlWriteULong64ToUser
0x14003fbc6  jmp     short loc_14003FBCC
  ... truncated ...
```
