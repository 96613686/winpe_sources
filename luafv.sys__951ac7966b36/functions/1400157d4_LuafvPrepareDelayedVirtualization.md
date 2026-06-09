# LuafvPrepareDelayedVirtualization

- ea: `0x1400157d4`
- end: `0x140015b2d`
- name: `LuafvPrepareDelayedVirtualization`
- size: `857`
- prototype: `__int64 __fastcall(__int64, struct _FLT_CALLBACK_DATA *, UNICODE_STRING **, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400247e0`

## callees

- `0x14001432c`
- `0x14001513c`
- `0x1400157d4`
- `0x14001860c`
- `0x14001b6a0`
- `0x14001dd90`
- `0x140023d14`

## import_xrefs

- `ntoskrnl!SeCaptureSubjectContext` at `0x140015a61`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140015a61`
- `ntoskrnl!KeInitializeEvent` at `0x14001598f`
- `ntoskrnl!KeInitializeEvent` at `0x14001598f`
- `ntoskrnl!IoCheckShareAccess` at `0x1400158cf`
- `ntoskrnl!IoCheckShareAccess` at `0x1400158cf`
- `ntoskrnl!IoFileObjectType` at `0x140015829`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001584d`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001584d`
- `ntoskrnl!ObfDereferenceObject` at `0x14001593a`
- `ntoskrnl!ObfDereferenceObject` at `0x14001593a`
- `FLTMGR!FltReferenceContext` at `0x140015a4e`
- `FLTMGR!FltReferenceContext` at `0x140015a4e`
- `FLTMGR!FltReleasePushLockEx` at `0x1400158ea`
- `FLTMGR!FltReleasePushLockEx` at `0x140015ae5`
- `FLTMGR!FltReleasePushLockEx` at `0x1400158ea`
- `FLTMGR!FltReleasePushLockEx` at `0x140015ae5`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400158b3`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400158b3`
- `FLTMGR!FltClose` at `0x14001594e`
- `FLTMGR!FltClose` at `0x14001594e`

## pseudocode

```c
__int64 __fastcall LuafvPrepareDelayedVirtualization(
        __int64 a1,
        struct _FLT_CALLBACK_DATA *a2,
        UNICODE_STRING **a3,
        void *a4)
{
  UNICODE_STRING *v4; // rsi
  char *Pool; // rbx
  __int64 *Dvfcb; // rbp
  NTSTATUS v10; // edi
  PFLT_IO_PARAMETER_BLOCK Iopb; // rcx
  struct _FILE_OBJECT *v12; // r13
  ACCESS_MASK v13; // esi
  ULONG ShareAccess; // edi
  _OWORD *v16; // rcx
  char v17; // al
  PVOID v18; // rax
  PVOID v19; // rax
  ULONG Options; // ecx
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r8
  ULONG v24; // [rsp+30h] [rbp-68h] BYREF
  PVOID Object; // [rsp+38h] [rbp-60h] BYREF
  UNICODE_STRING *v26; // [rsp+40h] [rbp-58h]

  v4 = *a3;
  v24 = 0;
  Object = 0;
  v26 = v4;
  Pool = 0;
  Dvfcb = FindOrCreateDvfcb(v4 + 3, (int *)&v24);
  if ( !Dvfcb )
    goto LABEL_2;
  v10 = ObReferenceObjectByHandle(a4, 0x80000000, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
  if ( v10 < 0 )
  {
    Object = 0;
    goto LABEL_10;
  }
  Pool = LuafvAllocatePool(512, 0x138u, 6);
  if ( !Pool )
  {
LABEL_2:
    v10 = -1073741670;
    goto LABEL_11;
  }
  Iopb = a2->Iopb;
  v12 = *(struct _FILE_OBJECT **)(a1 + 32);
  v13 = *(_DWORD *)(Iopb->Parameters.WMI.ProviderId + 16);
  if ( (v13 & 0x2000000) != 0 )
    v13 = v13 & 0xFDE0FE00 | 0x1F01FF;
  ShareAccess = Iopb->Parameters.Create.ShareAccess;
  v24 = ShareAccess;
  FltAcquirePushLockExclusiveEx(Dvfcb + 8, 0);
  v10 = IoCheckShareAccess(v13, ShareAccess, v12, (PSHARE_ACCESS)(Dvfcb + 9), 1u);
  if ( v10 < 0 )
  {
    FltReleasePushLockEx(Dvfcb + 8, 0);
    LODWORD(v4) = (_DWORD)v26;
LABEL_10:
    if ( v10 == -1073741757 )
    {
LABEL_12:
      a2->IoStatus.Status = v10;
      a2->IoStatus.Information = 0;
      if ( Pool )
        LuafvFreePool((__int64)Pool);
      if ( Object )
        ObfDereferenceObject(Object);
      if ( a4 )
        FltClose(a4);
      if ( Dvfcb )
        DereferenceDvfcb(Dvfcb);
      return (unsigned int)v10;
    }
LABEL_11:
    LuafvLogFileError((int)a2, (int)v4, (const EVENT_DESCRIPTOR *)LuafvPrepareDelayedFailed, v10);
    goto LABEL_12;
  }
  *((_DWORD *)Pool + 30) = 1;
  *((_QWORD *)Pool + 16) = 0;
  *((_DWORD *)Pool + 34) = 0;
  KeInitializeEvent((PRKEVENT)Pool + 6, SynchronizationEvent, 0);
  v16 = (_OWORD *)*((_QWORD *)Object + 3);
  *(_OWORD *)Pool = *v16;
  *((_OWORD *)Pool + 1) = v16[1];
  *((_OWORD *)Pool + 2) = v16[2];
  *(_DWORD *)Pool = 20477542;
  v17 = Pool[7];
  Pool[4] |= 0x40u;
  Pool[6] |= 2u;
  Pool[7] = v17 & 0xF | 0x50;
  *((_QWORD *)Pool + 8) = Pool + 56;
  *((_QWORD *)Pool + 7) = Pool + 56;
  if ( Pool != (char *)-120LL )
    *((_QWORD *)Pool + 6) = Pool + 120;
  *((_QWORD *)Pool + 9) = 0;
  *((_QWORD *)Pool + 10) = 0;
  *((_QWORD *)Pool + 11) = 0;
  *((_QWORD *)Pool + 12) = 0;
  *((_DWORD *)Pool + 26) = 0;
  *((_QWORD *)Pool + 14) = 0;
  if ( Dvfcb != (__int64 *)-104LL )
    *((_QWORD *)Pool + 10) = Dvfcb + 13;
  *((_QWORD *)Pool + 26) = a4;
  v18 = Object;
  *((_QWORD *)Pool + 28) = 0;
  *((_QWORD *)Pool + 29) = 0;
  *((_QWORD *)Pool + 27) = v18;
  v19 = Object;
  Pool[252] = 0;
  *((_QWORD *)Pool + 32) = a3;
  *((_QWORD *)Pool + 30) = v19;
  FltReferenceContext(a3);
  SeCaptureSubjectContext((PSECURITY_SUBJECT_CONTEXT)(Pool + 264));
  *((_DWORD *)Pool + 75) = v24;
  *((_DWORD *)Pool + 74) = v13;
  Options = a2->Iopb->Parameters.Create.Options;
  *((_QWORD *)Pool + 25) = v12;
  *((_DWORD *)Pool + 76) = Options & 0xFFFFFF;
  v12->FsContext = Pool;
  v12->FsContext2 = 0;
  v12->SectionObjectPointer = (PSECTION_OBJECT_POINTERS)*((_QWORD *)Object + 5);
  v21 = Dvfcb + 3;
  v22 = Dvfcb[3];
  if ( *(__int64 **)(v22 + 8) != Dvfcb + 3 )
    __fastfail(3u);
  *((_QWORD *)Pool + 22) = v22;
  *((_QWORD *)Pool + 23) = v21;
  *(_QWORD *)(v22 + 8) = Pool + 176;
  *v21 = Pool + 176;
  *((_QWORD *)Pool + 24) = Dvfcb;
  FltReleasePushLockEx(Dvfcb + 8, 0);
  LuafvLogUtcEvent((int *)&qword_14000E1E8, (__int64)qword_14000E1F0, v23, a2, v26, 3);
  return 0;
}

```

## disassembly

```asm
0x1400157d4  mov     rax, rsp
0x1400157d7  mov     [rax+18h], r8
0x1400157db  push    rbx
0x1400157dc  push    rbp
0x1400157dd  push    rsi
0x1400157de  push    rdi
0x1400157df  push    r12
0x1400157e1  push    r13
0x1400157e3  push    r14
0x1400157e5  push    r15
0x1400157e7  sub     rsp, 58h
0x1400157eb  mov     rsi, [r8]
0x1400157ee  xor     r12d, r12d
0x1400157f1  mov     r14, rdx
0x1400157f4  mov     [rax-68h], r12d
0x1400157f8  mov     r13, rcx
0x1400157fb  mov     [rax-60h], r12
0x1400157ff  lea     rdx, [rax-68h]
0x140015803  mov     [rsp+98h+var_58], rsi
0x140015808  lea     rcx, [rsi+30h]; String2
0x14001580c  mov     r15, r9
0x14001580f  mov     ebx, r12d
0x140015812  call    FindOrCreateDvfcb
0x140015817  mov     rbp, rax
0x14001581a  test    rax, rax
0x14001581d  jnz     short loc_140015829
0x14001581f  mov     edi, 0C000009Ah
0x140015824  jmp     loc_140015906
0x140015829  mov     r8, cs:__imp_IoFileObjectType
0x140015830  lea     rax, [rsp+98h+var_60]
0x140015835  mov     [rsp+98h+HandleInformation], r12; HandleInformation
0x14001583a  xor     r9d, r9d; AccessMode
0x14001583d  mov     edx, 80000000h; DesiredAccess
0x140015842  mov     [rsp+98h+Object], rax; Object
0x140015847  mov     rcx, r15; Handle
0x14001584a  mov     r8, [r8]; ObjectType
0x14001584d  call    cs:__imp_ObReferenceObjectByHandle
0x140015854  nop     dword ptr [rax+rax+00h]
0x140015859  mov     edi, eax
0x14001585b  test    eax, eax
0x14001585d  jns     short loc_140015869
0x14001585f  mov     [rsp+98h+var_60], r12
0x140015864  jmp     loc_1400158FE
0x140015869  mov     r8b, 6
0x14001586c  mov     edx, 138h
0x140015871  mov     ecx, 200h
0x140015876  call    LuafvAllocatePool
0x14001587b  mov     rbx, rax
0x14001587e  test    rax, rax
0x140015881  jz      short loc_14001581F
0x140015883  mov     rcx, [r14+10h]
0x140015887  mov     r13, [r13+20h]
0x14001588b  mov     rax, [rcx+18h]
0x14001588f  mov     esi, [rax+10h]
0x140015892  bt      esi, 19h
0x140015896  jnb     short loc_1400158A2
0x140015898  btr     esi, 19h
0x14001589c  or      esi, 1F01FFh
0x1400158a2  movzx   edi, word ptr [rcx+2Ah]
0x1400158a6  lea     r12, [rbp+40h]
0x1400158aa  mov     rcx, r12
0x1400158ad  mov     [rsp+98h+var_68], edi
0x1400158b1  xor     edx, edx
0x1400158b3  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x1400158ba  nop     dword ptr [rax+rax+00h]
0x1400158bf  lea     r9, [rbp+48h]; ShareAccess
0x1400158c3  mov     byte ptr [rsp+98h+Object], 1; Update
0x1400158c8  mov     r8, r13; FileObject
0x1400158cb  mov     edx, edi; DesiredShareAccess
0x1400158cd  mov     ecx, esi; DesiredAccess
0x1400158cf  call    cs:__imp_IoCheckShareAccess
0x1400158d6  nop     dword ptr [rax+rax+00h]
0x1400158db  mov     edi, eax
0x1400158dd  test    eax, eax
0x1400158df  jns     loc_14001596E
0x1400158e5  xor     edx, edx
0x1400158e7  mov     rcx, r12
0x1400158ea  call    cs:__imp_FltReleasePushLockEx
0x1400158f1  nop     dword ptr [rax+rax+00h]
0x1400158f6  mov     rsi, [rsp+98h+var_58]
0x1400158fb  xor     r12d, r12d
0x1400158fe  cmp     edi, 0C0000043h
0x140015904  jz      short loc_14001591B
0x140015906  mov     r9d, edi
0x140015909  lea     r8, LuafvPrepareDelayedFailed
0x140015910  mov     rdx, rsi
0x140015913  mov     rcx, r14
0x140015916  call    LuafvLogFileError
0x14001591b  mov     [r14+18h], edi
0x14001591f  mov     [r14+20h], r12
0x140015923  test    rbx, rbx
0x140015926  jz      short loc_140015930
0x140015928  mov     rcx, rbx
0x14001592b  call    LuafvFreePool
0x140015930  mov     rcx, [rsp+98h+var_60]; Object
0x140015935  test    rcx, rcx
0x140015938  jz      short loc_140015946
0x14001593a  call    cs:__imp_ObfDereferenceObject
0x140015941  nop     dword ptr [rax+rax+00h]
0x140015946  test    r15, r15
0x140015949  jz      short loc_14001595A
0x14001594b  mov     rcx, r15; FileHandle
0x14001594e  call    cs:__imp_FltClose
0x140015955  nop     dword ptr [rax+rax+00h]
0x14001595a  test    rbp, rbp
0x14001595d  jz      short loc_140015967
0x14001595f  mov     rcx, rbp
0x140015962  call    DereferenceDvfcb
0x140015967  mov     eax, edi
0x140015969  jmp     loc_140015B1B
0x14001596e  lea     rdi, [rbx+78h]
0x140015972  mov     edx, 1; Type
0x140015977  lea     rcx, [rdi+18h]; Event
0x14001597b  mov     [rdi], edx
0x14001597d  xor     r8d, r8d; State
0x140015980  mov     qword ptr [rdi+8], 0
0x140015988  mov     dword ptr [rdi+10h], 0
0x14001598f  call    cs:__imp_KeInitializeEvent
0x140015996  nop     dword ptr [rax+rax+00h]
0x14001599b  mov     rax, [rsp+98h+var_60]
0x1400159a0  mov     rcx, [rax+18h]
0x1400159a4  movups  xmm0, xmmword ptr [rcx]
0x1400159a7  movups  xmmword ptr [rbx], xmm0
0x1400159aa  movups  xmm1, xmmword ptr [rcx+10h]
0x1400159ae  movups  xmmword ptr [rbx+10h], xmm1
0x1400159b2  movups  xmm0, xmmword ptr [rcx+20h]
0x1400159b6  xor     ecx, ecx
0x1400159b8  movups  xmmword ptr [rbx+20h], xmm0
0x1400159bc  mov     dword ptr [rbx], 1387666h
0x1400159c2  mov     al, [rbx+7]
0x1400159c5  or      byte ptr [rbx+4], 40h
0x1400159c9  and     al, 0Fh
0x1400159cb  or      byte ptr [rbx+6], 2
0x1400159cf  or      al, 50h
0x1400159d1  mov     [rbx+7], al
0x1400159d4  lea     rax, [rbx+38h]
0x1400159d8  mov     [rax+8], rax
0x1400159dc  mov     [rax], rax
0x1400159df  test    rdi, rdi
0x1400159e2  jz      short loc_1400159E8
0x1400159e4  mov     [rbx+30h], rdi
0x1400159e8  lea     rax, [rbp+68h]
0x1400159ec  mov     [rbx+48h], rcx
0x1400159f0  mov     [rbx+50h], rcx
0x1400159f4  mov     [rbx+58h], rcx
0x1400159f8  mov     [rbx+60h], rcx
0x1400159fc  mov     [rbx+68h], ecx
0x1400159ff  mov     [rbx+70h], rcx
0x140015a03  test    rax, rax
0x140015a06  jz      short loc_140015A0C
0x140015a08  mov     [rbx+50h], rax
0x140015a0c  mov     [rbx+0D0h], r15
0x140015a13  mov     rax, [rsp+98h+var_60]
0x140015a18  mov     [rbx+0E0h], rcx
0x140015a1f  mov     [rbx+0E8h], rcx
0x140015a26  mov     [rbx+0D8h], rax
0x140015a2d  mov     rax, [rsp+98h+var_60]
0x140015a32  mov     [rbx+0FCh], cl
0x140015a38  mov     rcx, [rsp+98h+Context]; Context
0x140015a40  mov     [rbx+100h], rcx
0x140015a47  mov     [rbx+0F0h], rax
0x140015a4e  call    cs:__imp_FltReferenceContext
0x140015a55  nop     dword ptr [rax+rax+00h]
0x140015a5a  lea     rcx, [rbx+108h]; SubjectContext
0x140015a61  call    cs:__imp_SeCaptureSubjectContext
0x140015a68  nop     dword ptr [rax+rax+00h]
0x140015a6d  mov     eax, [rsp+98h+var_68]
0x140015a71  mov     [rbx+12Ch], eax
0x140015a77  mov     [rbx+128h], esi
0x140015a7d  mov     rax, [r14+10h]
0x140015a81  mov     ecx, [rax+20h]
0x140015a84  mov     [rbx+0C8h], r13
0x140015a8b  and     ecx, 0FFFFFFh
0x140015a91  mov     [rbx+130h], ecx
0x140015a97  mov     [r13+18h], rbx
0x140015a9b  mov     qword ptr [r13+20h], 0
0x140015aa3  mov     rax, [rsp+98h+var_60]
0x140015aa8  mov     rcx, [rax+28h]
0x140015aac  mov     [r13+28h], rcx
0x140015ab0  lea     rcx, [rbp+18h]
0x140015ab4  mov     rdx, [rcx]
0x140015ab7  cmp     [rdx+8], rcx
0x140015abb  jz      short loc_140015AC4
0x140015abd  mov     ecx, 3
0x140015ac2  int     29h; Win8: RtlFailFast(ecx)
0x140015ac4  lea     rax, [rbx+0B0h]
0x140015acb  mov     [rax], rdx
0x140015ace  mov     [rax+8], rcx
0x140015ad2  mov     [rdx+8], rax
0x140015ad6  xor     edx, edx
0x140015ad8  mov     [rcx], rax
0x140015adb  mov     rcx, r12
0x140015ade  mov     [rbx+0C0h], rbp
0x140015ae5  call    cs:__imp_FltReleasePushLockEx
0x140015aec  nop     dword ptr [rax+rax+00h]
0x140015af1  mov     rax, [rsp+98h+var_58]
0x140015af6  lea     rdx, qword_14000E1F0
0x140015afd  mov     dword ptr [rsp+98h+HandleInformation], 3
0x140015b05  lea     rcx, qword_14000E1E8
0x140015b0c  mov     r9, r14
0x140015b0f  mov     [rsp+98h+Object], rax
0x140015b14  call    LuafvLogUtcEvent
0x140015b19  xor     eax, eax
0x140015b1b  add     rsp, 58h
0x140015b1f  pop     r15
0x140015b21  pop     r14
0x140015b23  pop     r13
0x140015b25  pop     r12
0x140015b27  pop     rdi
0x140015b28  pop     rsi
0x140015b29  pop     rbp
0x140015b2a  pop     rbx
0x140015b2b  retn
```
