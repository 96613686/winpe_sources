# LuafvPrepareDelayedVirtualization

- ea: `0x1400157d4`
- end: `0x140015b2d`
- name: `LuafvPrepareDelayedVirtualization`
- size: `857`
- prototype: `__int64 __fastcall(__int64, __int64, const UNICODE_STRING **, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140024790`

## callees

- `0x14001432c`
- `0x14001513c`
- `0x1400157d4`
- `0x1400185bc`
- `0x14001b650`
- `0x14001dd40`
- `0x140023cc4`

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
__int64 __fastcall LuafvPrepareDelayedVirtualization(__int64 a1, __int64 a2, const UNICODE_STRING **a3, void *a4)
{
  const UNICODE_STRING *v4; // rsi
  __int64 Pool; // rbx
  __int64 *Dvfcb; // rbp
  NTSTATUS v10; // edi
  __int64 v11; // r8
  __int64 v12; // rcx
  struct _FILE_OBJECT *v13; // r13
  ACCESS_MASK v14; // esi
  ULONG v15; // edi
  _OWORD *v17; // rcx
  char v18; // al
  PVOID v19; // rax
  PVOID v20; // rax
  int v21; // ecx
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r8
  ULONG v25; // [rsp+30h] [rbp-68h] BYREF
  PVOID Object; // [rsp+38h] [rbp-60h] BYREF
  const UNICODE_STRING *v27; // [rsp+40h] [rbp-58h]

  v4 = *a3;
  v25 = 0;
  Object = 0;
  v27 = v4;
  Pool = 0;
  Dvfcb = FindOrCreateDvfcb(v4 + 3, (int *)&v25);
  if ( !Dvfcb )
    goto LABEL_2;
  v10 = ObReferenceObjectByHandle(a4, 0x80000000, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
  if ( v10 < 0 )
  {
    Object = 0;
    goto LABEL_10;
  }
  LOBYTE(v11) = 6;
  Pool = LuafvAllocatePool(512, 312, v11);
  if ( !Pool )
  {
LABEL_2:
    v10 = -1073741670;
    goto LABEL_11;
  }
  v12 = *(_QWORD *)(a2 + 16);
  v13 = *(struct _FILE_OBJECT **)(a1 + 32);
  v14 = *(_DWORD *)(*(_QWORD *)(v12 + 24) + 16LL);
  if ( (v14 & 0x2000000) != 0 )
    v14 = v14 & 0xFDE0FE00 | 0x1F01FF;
  v15 = *(unsigned __int16 *)(v12 + 42);
  v25 = v15;
  FltAcquirePushLockExclusiveEx(Dvfcb + 8, 0);
  v10 = IoCheckShareAccess(v14, v15, v13, (PSHARE_ACCESS)(Dvfcb + 9), 1u);
  if ( v10 < 0 )
  {
    FltReleasePushLockEx(Dvfcb + 8, 0);
    v4 = v27;
LABEL_10:
    if ( v10 == -1073741757 )
    {
LABEL_12:
      *(_DWORD *)(a2 + 24) = v10;
      *(_QWORD *)(a2 + 32) = 0;
      if ( Pool )
        LuafvFreePool(Pool);
      if ( Object )
        ObfDereferenceObject(Object);
      if ( a4 )
        FltClose(a4);
      if ( Dvfcb )
        DereferenceDvfcb((__int64)Dvfcb);
      return (unsigned int)v10;
    }
LABEL_11:
    LuafvLogFileError(a2, v4, LuafvPrepareDelayedFailed, (unsigned int)v10);
    goto LABEL_12;
  }
  *(_DWORD *)(Pool + 120) = 1;
  *(_QWORD *)(Pool + 128) = 0;
  *(_DWORD *)(Pool + 136) = 0;
  KeInitializeEvent((PRKEVENT)(Pool + 144), SynchronizationEvent, 0);
  v17 = (_OWORD *)*((_QWORD *)Object + 3);
  *(_OWORD *)Pool = *v17;
  *(_OWORD *)(Pool + 16) = v17[1];
  *(_OWORD *)(Pool + 32) = v17[2];
  *(_DWORD *)Pool = 20477542;
  v18 = *(_BYTE *)(Pool + 7);
  *(_BYTE *)(Pool + 4) |= 0x40u;
  *(_BYTE *)(Pool + 6) |= 2u;
  *(_BYTE *)(Pool + 7) = v18 & 0xF | 0x50;
  *(_QWORD *)(Pool + 64) = Pool + 56;
  *(_QWORD *)(Pool + 56) = Pool + 56;
  if ( Pool != -120 )
    *(_QWORD *)(Pool + 48) = Pool + 120;
  *(_QWORD *)(Pool + 72) = 0;
  *(_QWORD *)(Pool + 80) = 0;
  *(_QWORD *)(Pool + 88) = 0;
  *(_QWORD *)(Pool + 96) = 0;
  *(_DWORD *)(Pool + 104) = 0;
  *(_QWORD *)(Pool + 112) = 0;
  if ( Dvfcb != (__int64 *)-104LL )
    *(_QWORD *)(Pool + 80) = Dvfcb + 13;
  *(_QWORD *)(Pool + 208) = a4;
  v19 = Object;
  *(_QWORD *)(Pool + 224) = 0;
  *(_QWORD *)(Pool + 232) = 0;
  *(_QWORD *)(Pool + 216) = v19;
  v20 = Object;
  *(_BYTE *)(Pool + 252) = 0;
  *(_QWORD *)(Pool + 256) = a3;
  *(_QWORD *)(Pool + 240) = v20;
  FltReferenceContext(a3);
  SeCaptureSubjectContext((PSECURITY_SUBJECT_CONTEXT)(Pool + 264));
  *(_DWORD *)(Pool + 300) = v25;
  *(_DWORD *)(Pool + 296) = v14;
  v21 = *(_DWORD *)(*(_QWORD *)(a2 + 16) + 32LL);
  *(_QWORD *)(Pool + 200) = v13;
  *(_DWORD *)(Pool + 304) = v21 & 0xFFFFFF;
  v13->FsContext = (PVOID)Pool;
  v13->FsContext2 = 0;
  v13->SectionObjectPointer = (PSECTION_OBJECT_POINTERS)*((_QWORD *)Object + 5);
  v22 = Dvfcb + 3;
  v23 = Dvfcb[3];
  if ( *(__int64 **)(v23 + 8) != Dvfcb + 3 )
    __fastfail(3u);
  *(_QWORD *)(Pool + 176) = v23;
  *(_QWORD *)(Pool + 184) = v22;
  *(_QWORD *)(v23 + 8) = Pool + 176;
  *v22 = Pool + 176;
  *(_QWORD *)(Pool + 192) = Dvfcb;
  FltReleasePushLockEx(Dvfcb + 8, 0);
  LuafvLogUtcEvent(&qword_14000E1E8, qword_14000E1F0, v24, a2, v27, 3);
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
