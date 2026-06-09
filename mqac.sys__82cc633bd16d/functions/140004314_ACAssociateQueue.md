# ACAssociateQueue

- ea: `0x140004314`
- end: `0x140004711`
- name: `ACAssociateQueue`
- size: `1021`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000a3b0`

## callees

- `0x140001010`
- `0x1400010a4`
- `0x140001c04`
- `0x140004314`
- `0x140009008`
- `0x1400095e0`
- `0x14000b5d8`
- `0x1400126fc`
- `0x14001aa94`
- `0x14001b384`
- `0x14001cf7c`
- `0x14001d15c`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14000435c`
- `ntoskrnl!ProbeForRead` at `0x14000435c`
- `ntoskrnl!IoCheckShareAccess` at `0x140004618`
- `ntoskrnl!IoCheckShareAccess` at `0x140004618`

## pseudocode

```c
int __fastcall ACAssociateQueue(__int64 a1, struct CACOpenQueueRequest *a2, __int64 a3)
{
  struct CACOpenQueueRequest *v4; // rsi
  wchar_t *v5; // rdi
  wchar_t *v6; // r14
  int v8; // r12d
  const wchar_t *v9; // r13
  wchar_t *v10; // r15
  NTSTATUS v11; // ebx
  struct _FILE_OBJECT *v12; // r13
  struct CACOpenQueueRequest *SubqueueByName; // r15
  wchar_t *v14; // rax
  int v15; // r8d
  unsigned int v16; // edx
  CQMInterface *FsContext2; // rcx
  int v18; // eax
  unsigned int v19; // eax
  char v20; // r8
  int v21; // [rsp+34h] [rbp-64h]
  struct _GUID v22; // [rsp+50h] [rbp-48h] BYREF
  struct CACOpenQueueRequest *v24; // [rsp+A8h] [rbp+10h] BYREF
  char v25; // [rsp+B8h] [rbp+20h]

  v24 = a2;
  v4 = a2;
  v5 = 0;
  v6 = 0;
  if ( !a2 )
    return -1073741816;
  ProbeForRead((volatile void *)a3, 0x30u, 1u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_qD(
      WPP_GLOBAL_Control->Queue.ListEntry.Blink,
      101,
      WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids,
      v4,
      *(unsigned __int8 *)(a3 + 24));
  }
  v22 = *(struct _GUID *)a3;
  v21 = *(_DWORD *)(a3 + 16);
  v8 = *(_DWORD *)(a3 + 20);
  v9 = *(const wchar_t **)(a3 + 32);
  v10 = *(wchar_t **)(a3 + 40);
  if ( v9 )
  {
    ACWCUserStringLen(*(wchar_t **)(a3 + 32));
    v5 = ACpDupString(v9);
    if ( !v5 )
      return -1073741670;
  }
  if ( v10 )
  {
    ACWCUserStringLen(v10);
    v6 = ACpDupString(v10);
    if ( !v6 )
    {
      operator delete(v5);
      return -1073741670;
    }
  }
  v25 = *(_BYTE *)(a3 + 24);
  v24 = 0;
  v11 = CQMInterface::TakeOpenQueueRequest((CQMInterface *)(*(_QWORD *)(a1 + 64) + 72LL), &v22, &v24);
  if ( v11 < 0 )
  {
    if ( v5 )
      operator delete(v5);
    if ( v6 )
      operator delete(v6);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_Dq(
        WPP_GLOBAL_Control->Queue.ListEntry.Blink,
        103,
        WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids,
        (unsigned int)v11,
        v4);
    }
    return v11;
  }
  *(_QWORD *)&v22.Data1 = v24;
  v12 = (struct _FILE_OBJECT *)*((_QWORD *)v24 + 3);
  if ( v5 )
  {
    SubqueueByName = CQueue::GetSubqueueByName(v4, v5);
    v24 = SubqueueByName;
    v11 = SubqueueByName == 0 ? 0xC00E0003 : 0;
    if ( !SubqueueByName )
    {
      if ( !*((_QWORD *)v4 + 47) )
      {
        v14 = ACpDupString(v6);
        if ( !v14 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 14, WPP_fa0c76334f1634ba991c664600eb5d12_Traceguids);
          }
          v11 = -1073741670;
          goto LABEL_31;
        }
        *((_QWORD *)v4 + 47) = v14;
      }
      v11 = CQueue::CreateSubQueue(v4, v5, v12, &v24);
      SubqueueByName = v24;
    }
LABEL_31:
    if ( v11 >= 0 )
    {
      *((_DWORD *)SubqueueByName + 14) ^= (*((_DWORD *)v4 + 14) ^ *((_DWORD *)SubqueueByName + 14)) & 2;
      v4 = SubqueueByName;
    }
    operator delete(v5);
  }
  if ( v6 )
    operator delete(v6);
  v15 = *((_DWORD *)v12->FsContext2 + 4);
  v16 = ((v21 & 0x25) != 0) | 0x10000;
  if ( (v21 & 1) == 0 )
    v16 = (v21 & 0x25) != 0;
  FsContext2 = (CQMInterface *)(v16 | 2);
  if ( (v21 & 2) == 0 )
    FsContext2 = (CQMInterface *)v16;
  if ( (((unsigned __int8)v15 ^ (unsigned __int8)FsContext2) & 1) != 0 )
    v11 = -1073741790;
  if ( (((unsigned __int8)v15 ^ (unsigned __int8)FsContext2) & 2) != 0 )
    v11 = -1073741790;
  if ( v11 >= 0 )
  {
    v11 = IoCheckShareAccess(
            (ACCESS_MASK)FsContext2,
            4 * ((v8 & 1) == 0) + 3,
            v12,
            (PSHARE_ACCESS)((char *)v4 + 120),
            1u);
    if ( v11 >= 0 )
    {
      FsContext2 = (CQMInterface *)v12->FsContext2;
      v18 = *((_DWORD *)FsContext2 + 5);
      if ( v21 == 4 )
        v19 = v18 | 8;
      else
        v19 = v18 & 0xFFFFFFF7;
      *((_DWORD *)FsContext2 + 5) = v19;
      v11 = 0;
    }
    if ( v11 >= 0 )
    {
      v12->FsContext = v4;
      v20 = v25;
      *((_DWORD *)v12->FsContext2 + 5) = (v25 != 0 ? 2 : 0) | *((_DWORD *)v12->FsContext2 + 5) & 0xFFFFFFFD;
      *((_DWORD *)v12->FsContext2 + 5) = (4 * (v20 == 0)) | *((_DWORD *)v12->FsContext2 + 5) & 0xFFFFFFFB;
      CBaseObject::AddRef(v4);
    }
  }
  return CQMInterface::CompleteOpenQueueRequest(FsContext2, *(struct CACOpenQueueRequest **)&v22.Data1, v11);
}

```

## disassembly

```asm
0x140004314  mov     rax, rsp
0x140004317  mov     [rax+10h], rdx
0x14000431b  mov     [rax+8], rcx
0x14000431f  push    rbx
0x140004320  push    rsi
0x140004321  push    rdi
0x140004322  push    r12
0x140004324  push    r13
0x140004326  push    r14
0x140004328  push    r15
0x14000432a  sub     rsp, 60h
0x14000432e  mov     rbx, r8
0x140004331  mov     rsi, rdx
0x140004334  xor     edi, edi
0x140004336  mov     [rax-58h], rdi
0x14000433a  xor     r14d, r14d
0x14000433d  mov     [rax-50h], r14
0x140004341  test    rdx, rdx
0x140004344  jnz     short loc_140004350
0x140004346  mov     eax, 0C0000008h
0x14000434b  jmp     loc_140004700
0x140004350  mov     edx, 30h ; '0'; Length
0x140004355  lea     r8d, [rdx-2Fh]; Alignment
0x140004359  mov     rcx, rbx; Address
0x14000435c  call    cs:__imp_ProbeForRead
0x140004363  nop     dword ptr [rax+rax+00h]
0x140004368  lea     rax, WPP_GLOBAL_Control
0x14000436f  mov     rcx, cs:WPP_GLOBAL_Control
0x140004376  cmp     rcx, rax
0x140004379  jz      short loc_1400043A2
0x14000437b  mov     eax, [rcx+6Ch]
0x14000437e  test    al, 4
0x140004380  jz      short loc_1400043A2
0x140004382  movzx   eax, byte ptr [rbx+18h]
0x140004386  mov     edx, 65h ; 'e'
0x14000438b  mov     dword ptr [rsp+98h+Update], eax
0x14000438f  mov     r9, rsi
0x140004392  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140004399  mov     rcx, [rcx+58h]
0x14000439d  call    WPP_SF_qD
0x1400043a2  movups  xmm0, xmmword ptr [rbx]
0x1400043a5  movdqu  xmmword ptr [rsp+98h+var_48.Data1], xmm0
0x1400043ab  mov     eax, [rbx+10h]
0x1400043ae  mov     [rsp+98h+var_64], eax
0x1400043b2  mov     [rsp+98h+var_60], eax
0x1400043b6  mov     r12d, [rbx+14h]
0x1400043ba  mov     [rsp+98h+var_5C], r12d
0x1400043bf  mov     r13, [rbx+20h]
0x1400043c3  mov     r15, [rbx+28h]
0x1400043c7  test    r13, r13
0x1400043ca  jz      short loc_1400043F3
0x1400043cc  mov     rcx, r13; wchar_t *
0x1400043cf  call    ?ACWCUserStringLen@@YAKPEA_W@Z; ACWCUserStringLen(wchar_t *)
0x1400043d4  mov     rcx, r13; Src
0x1400043d7  call    ?ACpDupString@@YAPEA_WPEB_W@Z; ACpDupString(wchar_t const *)
0x1400043dc  mov     rdi, rax
0x1400043df  mov     [rsp+98h+var_58], rax
0x1400043e4  test    rax, rax
0x1400043e7  jnz     short loc_1400043F3
0x1400043e9  mov     eax, 0C000009Ah
0x1400043ee  jmp     loc_140004700
0x1400043f3  test    r15, r15
0x1400043f6  jz      short loc_140004427
0x1400043f8  mov     rcx, r15; wchar_t *
0x1400043fb  call    ?ACWCUserStringLen@@YAKPEA_W@Z; ACWCUserStringLen(wchar_t *)
0x140004400  mov     rcx, r15; Src
0x140004403  call    ?ACpDupString@@YAPEA_WPEB_W@Z; ACpDupString(wchar_t const *)
0x140004408  mov     r14, rax
0x14000440b  mov     [rsp+98h+var_50], rax
0x140004410  test    rax, rax
0x140004413  jnz     short loc_140004427
0x140004415  mov     rcx, rdi; void *
0x140004418  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000441d  mov     eax, 0C000009Ah
0x140004422  jmp     loc_140004700
0x140004427  mov     al, [rbx+18h]
0x14000442a  mov     [rsp+98h+arg_18], al
0x140004431  mov     [rsp+98h+var_68], al
0x140004435  mov     [rsp+98h+arg_8], 0
0x140004441  mov     rcx, [rsp+98h+arg_0]
0x140004449  mov     rcx, [rcx+40h]
0x14000444d  add     rcx, 48h ; 'H'; this
0x140004451  lea     r8, [rsp+98h+arg_8]; struct CACOpenQueueRequest **
0x140004459  lea     rdx, [rsp+98h+var_48]; struct _GUID *
0x14000445e  call    ?TakeOpenQueueRequest@CQMInterface@@QEAAJAEBU_GUID@@PEAPEAVCACOpenQueueRequest@@@Z; CQMInterface::TakeOpenQueueRequest(_GUID const &,CACOpenQueueRequest * *)
0x140004463  mov     ebx, eax
0x140004465  test    eax, eax
0x140004467  jns     short loc_1400044C1
0x140004469  test    rdi, rdi
0x14000446c  jz      short loc_140004476
0x14000446e  mov     rcx, rdi; void *
0x140004471  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140004476  test    r14, r14
0x140004479  jz      short loc_140004483
0x14000447b  mov     rcx, r14; void *
0x14000447e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140004483  mov     rcx, cs:WPP_GLOBAL_Control
0x14000448a  lea     rax, WPP_GLOBAL_Control
0x140004491  cmp     rcx, rax
0x140004494  jz      short loc_1400044BA
0x140004496  mov     eax, [rcx+6Ch]
0x140004499  test    al, 1
0x14000449b  jz      short loc_1400044BA
0x14000449d  mov     edx, 67h ; 'g'
0x1400044a2  mov     qword ptr [rsp+98h+Update], rsi
0x1400044a7  mov     r9d, ebx
0x1400044aa  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x1400044b1  mov     rcx, [rcx+58h]
0x1400044b5  call    WPP_SF_Dq
0x1400044ba  mov     eax, ebx
0x1400044bc  jmp     loc_140004700
0x1400044c1  mov     rax, [rsp+98h+arg_8]
0x1400044c9  mov     qword ptr [rsp+98h+var_48.Data1], rax
0x1400044ce  mov     r13, [rax+18h]
0x1400044d2  test    rdi, rdi
0x1400044d5  jz      loc_14000459E
0x1400044db  mov     rdx, rdi; wchar_t *
0x1400044de  mov     rcx, rsi; this
0x1400044e1  call    ?GetSubqueueByName@CQueue@@QEAAPEAV1@PEB_W@Z; CQueue::GetSubqueueByName(wchar_t const *)
0x1400044e6  mov     r15, rax
0x1400044e9  mov     [rsp+98h+arg_8], rax
0x1400044f1  mov     rcx, rax
0x1400044f4  neg     rcx
0x1400044f7  sbb     ebx, ebx
0x1400044f9  not     ebx
0x1400044fb  and     ebx, 0C00E0003h
0x140004501  test    rax, rax
0x140004504  jnz     short loc_140004578
0x140004506  cmp     [rsi+178h], rax
0x14000450d  jnz     short loc_140004558
0x14000450f  mov     rcx, r14; Src
0x140004512  call    ?ACpDupString@@YAPEA_WPEB_W@Z; ACpDupString(wchar_t const *)
0x140004517  test    rax, rax
0x14000451a  jnz     short loc_140004551
0x14000451c  mov     rcx, cs:WPP_GLOBAL_Control
0x140004523  lea     rax, WPP_GLOBAL_Control
0x14000452a  cmp     rcx, rax
0x14000452d  jz      short loc_14000454A
0x14000452f  mov     eax, [rcx+6Ch]
0x140004532  test    al, 1
0x140004534  jz      short loc_14000454A
0x140004536  lea     edx, [r15+0Eh]
0x14000453a  lea     r8, WPP_fa0c76334f1634ba991c664600eb5d12_Traceguids
0x140004541  mov     rcx, [rcx+58h]
0x140004545  call    WPP_SF_
0x14000454a  mov     ebx, 0C000009Ah
0x14000454f  jmp     short loc_140004578
0x140004551  mov     [rsi+178h], rax
0x140004558  lea     r9, [rsp+98h+arg_8]; struct CQueue **
0x140004560  mov     r8, r13; struct _FILE_OBJECT *
0x140004563  mov     rdx, rdi; wchar_t *
0x140004566  mov     rcx, rsi; this
0x140004569  call    ?CreateSubQueue@CQueue@@QEAAJPEB_WPEAU_FILE_OBJECT@@PEAPEAV1@@Z; CQueue::CreateSubQueue(wchar_t const *,_FILE_OBJECT *,CQueue * *)
0x14000456e  mov     ebx, eax
0x140004570  mov     r15, [rsp+98h+arg_8]
0x140004578  test    ebx, ebx
0x14000457a  js      short loc_140004591
0x14000457c  mov     eax, [r15+38h]
0x140004580  mov     ecx, eax
0x140004582  xor     ecx, [rsi+38h]
0x140004585  and     ecx, 2
0x140004588  xor     ecx, eax
0x14000458a  mov     [r15+38h], ecx
0x14000458e  mov     rsi, r15
0x140004591  test    rdi, rdi
0x140004594  jz      short loc_14000459E
0x140004596  mov     rcx, rdi; void *
0x140004599  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000459e  test    r14, r14
0x1400045a1  jz      short loc_1400045AB
0x1400045a3  mov     rcx, r14; void *
0x1400045a6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400045ab  mov     rax, [r13+20h]
0x1400045af  mov     r8d, [rax+10h]
0x1400045b3  mov     edi, [rsp+98h+var_64]
0x1400045b7  test    dil, 25h
0x1400045bb  mov     ecx, 0
0x1400045c0  setnz   cl
0x1400045c3  mov     edx, ecx
0x1400045c5  bts     edx, 10h
0x1400045c9  test    dil, 1
0x1400045cd  cmovz   edx, ecx
0x1400045d0  mov     ecx, edx
0x1400045d2  or      ecx, 2
0x1400045d5  test    dil, 2
0x1400045d9  cmovz   ecx, edx; DesiredAccess
0x1400045dc  mov     al, cl
0x1400045de  xor     al, r8b
0x1400045e1  test    al, 1
0x1400045e3  mov     edx, 0C0000022h
0x1400045e8  cmovnz  ebx, edx
0x1400045eb  mov     al, cl
0x1400045ed  xor     al, r8b
0x1400045f0  test    al, 2
0x1400045f2  cmovnz  ebx, edx
0x1400045f5  test    ebx, ebx
0x1400045f7  js      loc_140004690
0x1400045fd  lea     r9, [rsi+78h]; ShareAccess
0x140004601  not     r12d
0x140004604  and     r12d, 1
0x140004608  lea     edx, ds:3[r12*4]; DesiredShareAccess
0x140004610  mov     [rsp+98h+Update], 1; Update
0x140004615  mov     r8, r13; FileObject
0x140004618  call    cs:__imp_IoCheckShareAccess
0x14000461f  nop     dword ptr [rax+rax+00h]
0x140004624  mov     ebx, eax
0x140004626  test    eax, eax
0x140004628  js      short loc_140004643
0x14000462a  mov     rcx, [r13+20h]
0x14000462e  mov     eax, [rcx+14h]
0x140004631  cmp     edi, 4
0x140004634  jnz     short loc_14000463B
0x140004636  or      eax, 8
0x140004639  jmp     short loc_14000463E
0x14000463b  and     eax, 0FFFFFFF7h
0x14000463e  mov     [rcx+14h], eax
0x140004641  xor     ebx, ebx
0x140004643  test    ebx, ebx
0x140004645  js      short loc_140004690
0x140004647  mov     [r13+18h], rsi
0x14000464b  mov     r8b, [rsp+98h+arg_18]
0x140004653  mov     al, r8b
0x140004656  neg     al
0x140004658  sbb     edx, edx
0x14000465a  and     edx, 2
0x14000465d  mov     rcx, [r13+20h]
0x140004661  mov     eax, [rcx+14h]
0x140004664  and     eax, 0FFFFFFFDh
0x140004667  or      eax, edx
0x140004669  mov     [rcx+14h], eax
0x14000466c  xor     eax, eax
0x14000466e  test    r8b, r8b
0x140004671  setz    al
0x140004674  mov     r9, [r13+20h]
0x140004678  mov     ecx, [r9+14h]
0x14000467c  and     ecx, 0FFFFFFFBh
0x14000467f  shl     eax, 2
0x140004682  or      ecx, eax
0x140004684  mov     [r9+14h], ecx
0x140004688  mov     rcx, rsi; this
0x14000468b  call    ?AddRef@CBaseObject@@QEAAKXZ; CBaseObject::AddRef(void)
0x140004690  mov     r8d, ebx; int
0x140004693  mov     rdx, qword ptr [rsp+98h+var_48.Data1]; struct CACOpenQueueRequest *
0x140004698  call    ?CompleteOpenQueueRequest@CQMInterface@@QEAAJPEAVCACOpenQueueRequest@@J@Z; CQMInterface::CompleteOpenQueueRequest(CACOpenQueueRequest *,long)
0x14000469d  jmp     short loc_140004700
0x14000469f  mov     ebx, eax
0x1400046a1  mov     rcx, [rsp+98h+var_58]; void *
0x1400046a6  test    rcx, rcx
0x1400046a9  jz      short loc_1400046B0
0x1400046ab  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400046b0  mov     rcx, [rsp+98h+var_50]; void *
0x1400046b5  test    rcx, rcx
0x1400046b8  jz      short loc_1400046BF
0x1400046ba  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400046bf  lea     rax, WPP_GLOBAL_Control
0x1400046c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400046cd  cmp     rcx, rax
0x1400046d0  jz      short loc_1400046FE
0x1400046d2  mov     eax, [rcx+6Ch]
0x1400046d5  test    al, 1
0x1400046d7  jz      short loc_1400046FE
0x1400046d9  mov     edx, 66h ; 'f'
0x1400046de  mov     rax, [rsp+98h+arg_8]
0x1400046e6  mov     qword ptr [rsp+98h+Update], rax
0x1400046eb  mov     r9d, ebx
0x1400046ee  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x1400046f5  mov     rcx, [rcx+58h]
0x1400046f9  call    WPP_SF_Dq
0x1400046fe  mov     eax, ebx
0x140004700  add     rsp, 60h
0x140004704  pop     r15
0x140004706  pop     r14
0x140004708  pop     r13
0x14000470a  pop     r12
0x14000470c  pop     rdi
0x14000470d  pop     rsi
0x14000470e  pop     rbx
0x14000470f  retn
```
