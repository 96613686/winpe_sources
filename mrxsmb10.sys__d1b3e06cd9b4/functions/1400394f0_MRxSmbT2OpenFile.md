# MRxSmbT2OpenFile

- ea: `0x1400394f0`
- end: `0x1400399de`
- name: `MRxSmbT2OpenFile`
- size: `1262`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext)`
- caller_count: `1`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x140037780`

## callees

- `0x140002470`
- `0x140003e20`
- `0x140004030`
- `0x14000b210`
- `0x14000cbbc`
- `0x14000dfa8`
- `0x14001086c`
- `0x140016560`
- `0x1400169c0`
- `0x1400288dc`
- `0x140028990`
- `0x14003608c`
- `0x140038f6c`
- `0x1400394f0`
- `0x14003b2d4`
- `0x14003b320`
- `0x14003b370`
- `0x14003b8d4`
- `0x14003ee9c`
- `0x14003ef9c`
- `0x140044700`
- `0x14004b5f0`
- `0x140051880`
- `0x1400526a4`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x1400395ad`
- `ntoskrnl!DbgPrint` at `0x1400397c3`
- `ntoskrnl!DbgPrint` at `0x1400397e6`
- `ntoskrnl!DbgPrint` at `0x1400395ad`
- `ntoskrnl!DbgPrint` at `0x1400397c3`
- `ntoskrnl!DbgPrint` at `0x1400397e6`
- `ntoskrnl!ExAllocatePool2` at `0x1400395d9`
- `ntoskrnl!ExAllocatePool2` at `0x14003981d`
- `ntoskrnl!ExAllocatePool2` at `0x1400395d9`
- `ntoskrnl!ExAllocatePool2` at `0x14003981d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039999`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400399af`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039999`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400399af`
- `rdbss!RxProcessFcbChangeBufferingStateRequest` at `0x140039913`
- `rdbss!RxFcbGetOutstandingBufferingChangeEvent` at `0x1400398f9`
- `rdbss!RxFcbGetOutstandingBufferingChangeEvent` at `0x1400398f9`

## string_xrefs

- `0x1400395a3`: `MRxSmbT2Open---%p %08lx\n`
- `0x14003970e`: `MRxSmbT2OpenFile`
- `0x14003972c`: `MRxSmbT2OpenFile`
- `0x1400397dc`: `MRxSmbT2Open again---%p %08lx\n`

## pseudocode

```c
__int64 __fastcall MRxSmbT2OpenFile(PRX_CONTEXT RxContext)
{
  ULONG AcquireRelease; // edi
  PERESOURCE *p_Resource; // r12
  PSZ FileName; // rbx
  int v5; // r13d
  char *Pool2; // r14
  int v7; // ebx
  __int64 PipeCompletionMode; // rcx
  __int16 v9; // ax
  __int64 PipeType; // rcx
  __int16 v11; // ax
  __int64 v12; // rcx
  __int16 v13; // ax
  __int16 v14; // r10
  __int16 v15; // r10
  __int16 v16; // ax
  __int64 v17; // rcx
  __int64 v18; // rdi
  int v19; // eax
  char v20; // bl
  int v21; // r13d
  PSZ v22; // r12
  unsigned int v23; // eax
  unsigned int v24; // ebx
  void *v25; // rdi
  __int64 v26; // rax
  unsigned int v27; // r13d
  PSZ v28; // rax
  PMRX_FCB v29; // r15
  __int64 v30; // rax
  __int64 v31; // r8
  int v33; // [rsp+80h] [rbp-80h] BYREF
  __int16 v34; // [rsp+84h] [rbp-7Ch]
  __int16 v35; // [rsp+86h] [rbp-7Ah]
  __int16 v36; // [rsp+88h] [rbp-78h] BYREF
  int v37; // [rsp+8Ch] [rbp-74h] BYREF
  char *v38; // [rsp+90h] [rbp-70h] BYREF
  int v39; // [rsp+98h] [rbp-68h]
  ULONG EaLength; // [rsp+9Ch] [rbp-64h]
  int v41; // [rsp+A0h] [rbp-60h]
  ULONG v42; // [rsp+A4h] [rbp-5Ch]
  _BYTE v43[24]; // [rsp+A8h] [rbp-58h] BYREF
  PSZ v44; // [rsp+C0h] [rbp-40h]
  PMRX_FCB pFcb; // [rsp+C8h] [rbp-38h]
  _QWORD v46[14]; // [rsp+D0h] [rbp-30h] BYREF
  _OWORD v47[2]; // [rsp+140h] [rbp+40h] BYREF

  pFcb = RxContext->pFcb;
  v36 = 0;
  memset(v46, 0, 0x68u);
  AcquireRelease = RxContext->TrackerHistory[3].AcquireRelease;
  p_Resource = &pFcb[2].Header.Resource;
  FileName = RxContext->TrackerHistory[2].FileName;
  v38 = 0;
  memset(v47, 0, 30);
  v37 = 0;
  v42 = AcquireRelease;
  memset(v43, 0, sizeof(v43));
  v44 = FileName;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xAu) )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 61, WPP_d95790c14120305e97e490eb33b089fe_Traceguids);
  }
  DbgPrint("MRxSmbT2Open---%p %08lx\n", FileName, AcquireRelease);
  MRxSmbAdjustCreateParameters((__int64)RxContext, (__int64)&v38);
  v5 = *(unsigned __int16 *)p_Resource;
  Pool2 = (char *)ExAllocatePool2(258, (unsigned int)(v5 + 30), 1651340120);
  if ( !Pool2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xAu) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 62, WPP_d95790c14120305e97e490eb33b089fe_Traceguids);
    }
    return (unsigned int)-1073741670;
  }
  PipeCompletionMode = RxContext->Create.PipeCompletionMode;
  LOWORD(v39) = 1;
  v9 = MRxSmbMapDisposition(PipeCompletionMode);
  PipeType = RxContext->Create.PipeType;
  LOWORD(v33) = v9;
  v11 = MRxSmbMapFileAttributes(PipeType);
  v12 = *((unsigned __int16 *)&RxContext->9 + 66);
  v35 = v11;
  EaLength = RxContext->Create.EaLength;
  MRxSmbMapShareAccess(v12);
  v13 = MRxSmbMapDesiredAccess(*((unsigned int *)&RxContext->9 + 28));
  v15 = v13 | v14;
  v16 = v15 | 0x4000;
  if ( (*((_BYTE *)&RxContext->9 + 140) & 2) == 0 )
    v16 = v15;
  v34 = v16;
  if ( !RxContext->TrackerHistory[0].FileName[77] && !(unsigned __int8)MRxSmbIsStreamFile(p_Resource, 0) )
  {
    v39 = 7;
    *(&RxContext->TrackerHistory[3].Flags + 1) = 31;
  }
  v17 = *(_QWORD *)&RxContext->TrackerHistory[0].AcquireRelease;
  v38 = 0;
  v18 = SmbCeReferenceAssociatedServerEntry(v17);
  v19 = *(_DWORD *)(v18 + 420) & 0x8000;
  v38 = (char *)MEMORY[0xFFFFF78000000014];
  v41 = v19;
  v20 = MRxSmbTimeToSecondsSince1970(&v38, v18 + 400, &v37);
  MRxSmbTrackDerefCount(v18, "MRxSmbT2OpenFile", 3591);
  SmbReferenceRecord(v18 + 792, "MRxSmbT2OpenFile", 3591);
  SmbCepDereferenceServerEntry((char *)v18);
  if ( !v20 )
    v37 = 0;
  *(_WORD *)Pool2 = v39;
  *((_WORD *)Pool2 + 1) = v34;
  v21 = v5 + 2;
  *((_WORD *)Pool2 + 3) = v35;
  *((_WORD *)Pool2 + 2) = 22;
  *((_DWORD *)Pool2 + 2) = v37;
  *((_WORD *)Pool2 + 6) = v33;
  *(_DWORD *)(Pool2 + 14) = EaLength;
  *(_QWORD *)(Pool2 + 18) = 0;
  *((_WORD *)Pool2 + 13) = 0;
  v38 = Pool2 + 28;
  v33 = v21;
  if ( v41 )
  {
    SmbPutUnicodeString(&v38, p_Resource, &v33);
  }
  else
  {
    SmbPutUnicodeStringAsOemString(&v38, p_Resource, &v33);
    DbgPrint("This is the name <%s>\n", Pool2 + 28);
  }
  if ( !v42 )
  {
    v24 = 0;
    v25 = 0;
LABEL_26:
    v27 = v21 - v33 + 28;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_dq(WPP_GLOBAL_Control->AttachedDevice, 63, WPP_d95790c14120305e97e490eb33b089fe_Traceguids);
    *(_DWORD *)v43 = RxDefaultTransactionOptions | 0x40000000;
    *(_DWORD *)&v43[20] = HIDWORD(qword_14001F6B0);
    v28 = RxContext->TrackerHistory[0].FileName;
    *(_OWORD *)&v43[4] = *(__int128 *)((char *)&RxDefaultTransactionOptions + 4);
    if ( (*((_DWORD *)v28 + 14) & 2) != 0 && RxContext->Create.TransportName.Buffer == (PWSTR)4282664531LL )
      *(_WORD *)&v43[2] = WORD1(RxDefaultTransactionOptions) | 0x4200;
    *(_DWORD *)&v43[20] = 0xFFFF;
    SmbCeInitializeTransactionResumptionContext(v46);
    v29 = pFcb;
    v30 = RxFcbGetOutstandingBufferingChangeEvent(pFcb);
    v46[12] = v29;
    v46[10] = v30;
    v46[11] = RxProcessFcbChangeBufferingStateRequest;
    v7 = SmbCeTransact(
           (int)RxContext,
           (__int64)v43,
           (struct _MDL *)&v36,
           2u,
           0,
           0,
           (__int64)Pool2,
           v27,
           (__int64)v47,
           0x1Eu,
           (__int64)v25,
           v24,
           0,
           0,
           (__int64)v46);
    if ( v7 >= 0 )
    {
      MRxSmbFinishT2OpenFile(RxContext, (__int64)v47, v31, v46[9]);
      if ( RxContext->Create.PipeCompletionMode == 1 )
        MRxSmbAdjustReturnedCreateAction(RxContext);
    }
    goto LABEL_35;
  }
  v22 = v44;
  DbgPrint("MRxSmbT2Open again---%p %08lx\n", v44, v42);
  v23 = MRxSmbNtFullEaSizeToOs2(v22);
  v24 = v23;
  if ( v23 > 0xFFFF )
  {
    v25 = 0;
    v7 = -1073741744;
    goto LABEL_35;
  }
  v26 = ExAllocatePool2(258, v23, 1164078451);
  v25 = (void *)v26;
  if ( v26 )
  {
    MRxSmbNtFullListToOs2(v22, v26);
    goto LABEL_26;
  }
  v7 = -1073741670;
LABEL_35:
  ExFreePoolWithTag(Pool2, 0);
  if ( v25 )
    ExFreePoolWithTag(v25, 0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400394f0  push    rbp
0x1400394f2  push    rbx
0x1400394f3  push    rsi
0x1400394f4  push    rdi
0x1400394f5  push    r12
0x1400394f7  push    r13
0x1400394f9  push    r14
0x1400394fb  push    r15
0x1400394fd  lea     rbp, [rsp-78h]
0x140039502  sub     rsp, 178h
0x140039509  mov     rax, cs:__security_cookie
0x140039510  xor     rax, rsp
0x140039513  mov     [rbp+0B0h+var_50], rax
0x140039517  mov     rbx, [rcx+38h]
0x14003951b  xor     eax, eax
0x14003951d  mov     rsi, rcx
0x140039520  mov     [rbp+0B0h+var_E8], rbx
0x140039524  xor     edx, edx; Val
0x140039526  mov     [rbp+0B0h+var_128], ax
0x14003952a  lea     rcx, [rbp+0B0h+var_E0]; void *
0x14003952e  lea     r8d, [rax+68h]; Size
0x140039532  call    memset
0x140039537  mov     edi, [rsi+2C8h]
0x14003953d  lea     r12, [rbx+168h]
0x140039544  mov     rbx, [rsi+2B8h]
0x14003954b  xor     eax, eax
0x14003954d  xorps   xmm1, xmm1
0x140039550  mov     [rbp+0B0h+var_F8], rax
0x140039554  xorps   xmm0, xmm0
0x140039557  mov     [rbp+0B0h+var_120], rax
0x14003955b  movups  [rbp+0B0h+var_70], xmm1
0x14003955f  mov     [rbp+0B0h+var_124], eax
0x140039562  movups  [rbp+0B0h+var_70+0Eh], xmm1
0x140039566  mov     [rbp+0B0h+var_10C], edi
0x140039569  movups  [rbp+0B0h+var_108], xmm0
0x14003956d  mov     [rbp+0B0h+var_F0], rbx
0x140039571  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140039578  lea     rax, WPP_GLOBAL_Control
0x14003957f  cmp     rcx, rax
0x140039582  jz      short loc_1400395A0
0x140039584  bt      dword ptr [rcx+2Ch], 0Ah
0x140039589  jnb     short loc_1400395A0
0x14003958b  mov     rcx, [rcx+18h]
0x14003958f  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x140039596  mov     edx, 3Dh ; '='
0x14003959b  call    WPP_SF_
0x1400395a0  mov     r8d, edi
0x1400395a3  lea     rcx, aMrxsmbt2openP0; "MRxSmbT2Open---%p %08lx\n"
0x1400395aa  mov     rdx, rbx
0x1400395ad  call    cs:__imp_DbgPrint
0x1400395b4  nop     dword ptr [rax+rax+00h]
0x1400395b9  lea     rdx, [rbp+0B0h+var_120]
0x1400395bd  mov     rcx, rsi
0x1400395c0  call    MRxSmbAdjustCreateParameters
0x1400395c5  movzx   r13d, word ptr [r12]
0x1400395ca  mov     ecx, 102h
0x1400395cf  mov     r8d, 626D7358h
0x1400395d5  lea     edx, [r13+1Eh]
0x1400395d9  call    cs:__imp_ExAllocatePool2
0x1400395e0  nop     dword ptr [rax+rax+00h]
0x1400395e5  mov     r14, rax
0x1400395e8  test    rax, rax
0x1400395eb  jnz     short loc_140039625
0x1400395ed  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400395f4  lea     rax, WPP_GLOBAL_Control
0x1400395fb  cmp     rcx, rax
0x1400395fe  jz      short loc_14003961B
0x140039600  bt      dword ptr [rcx+2Ch], 0Ah
0x140039605  jnb     short loc_14003961B
0x140039607  mov     rcx, [rcx+18h]
0x14003960b  lea     edx, [r14+3Eh]
0x14003960f  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x140039616  call    WPP_SF_
0x14003961b  mov     ebx, 0C000009Ah
0x140039620  jmp     loc_1400399BB
0x140039625  mov     ecx, [rsi+218h]
0x14003962b  mov     eax, 1
0x140039630  mov     word ptr [rbp+0B0h+var_118], ax
0x140039634  call    MRxSmbMapDisposition
0x140039639  mov     ecx, [rsi+210h]
0x14003963f  mov     word ptr [rbp+0B0h+var_130], ax
0x140039643  call    MRxSmbMapFileAttributes
0x140039648  movzx   ecx, word ptr [rsi+214h]
0x14003964f  mov     [rbp+0B0h+var_12A], ax
0x140039653  mov     eax, [rsi+208h]
0x140039659  mov     [rbp+0B0h+var_114], eax
0x14003965c  call    MRxSmbMapShareAccess
0x140039661  mov     ecx, [rsi+200h]
0x140039667  movzx   r10d, ax
0x14003966b  call    MRxSmbMapDesiredAccess
0x140039670  or      r10w, ax
0x140039674  mov     r15d, 4000h
0x14003967a  movzx   eax, r10w
0x14003967e  or      ax, r15w
0x140039682  test    byte ptr [rsi+21Ch], 2
0x140039689  cmovz   ax, r10w
0x14003968e  mov     [rbp+0B0h+var_12C], ax
0x140039692  mov     rax, [rsi+288h]
0x140039699  cmp     byte ptr [rax+4Dh], 0
0x14003969d  jnz     short loc_1400396BE
0x14003969f  xor     edx, edx
0x1400396a1  mov     rcx, r12
0x1400396a4  call    MRxSmbIsStreamFile
0x1400396a9  test    al, al
0x1400396ab  jnz     short loc_1400396BE
0x1400396ad  mov     [rbp+0B0h+var_118], 7
0x1400396b4  mov     dword ptr [rsi+2DCh], 1Fh
0x1400396be  mov     rcx, [rsi+280h]
0x1400396c5  mov     [rbp+0B0h+var_120], 0
0x1400396cd  call    SmbCeReferenceAssociatedServerEntry
0x1400396d2  mov     rdi, rax
0x1400396d5  lea     r8, [rbp+0B0h+var_124]
0x1400396d9  mov     rcx, 0FFFFF78000000014h
0x1400396e3  mov     eax, [rax+1A4h]
0x1400396e9  and     eax, 8000h
0x1400396ee  lea     rdx, [rdi+190h]
0x1400396f5  mov     rcx, [rcx]
0x1400396f8  mov     [rbp+0B0h+var_120], rcx
0x1400396fc  lea     rcx, [rbp+0B0h+var_120]
0x140039700  mov     [rbp+0B0h+var_110], eax
0x140039703  call    MRxSmbTimeToSecondsSince1970
0x140039708  mov     r8d, 0E07h
0x14003970e  lea     rdx, aMrxsmbt2openfi; "MRxSmbT2OpenFile"
0x140039715  mov     rcx, rdi
0x140039718  mov     bl, al
0x14003971a  call    MRxSmbTrackDerefCount
0x14003971f  lea     rcx, [rdi+318h]
0x140039726  mov     r8d, 0E07h
0x14003972c  lea     rdx, aMrxsmbt2openfi; "MRxSmbT2OpenFile"
0x140039733  call    SmbReferenceRecord
0x140039738  mov     rcx, rdi; pContext
0x14003973b  call    SmbCepDereferenceServerEntry
0x140039740  test    bl, bl
0x140039742  jnz     short loc_14003974B
0x140039744  mov     [rbp+0B0h+var_124], 0
0x14003974b  mov     eax, [rbp+0B0h+var_118]
0x14003974e  lea     rbx, [r14+1Ch]
0x140039752  mov     [r14], ax
0x140039756  lea     r8, [rbp+0B0h+var_130]
0x14003975a  movzx   eax, [rbp+0B0h+var_12C]
0x14003975e  lea     rcx, [rbp+0B0h+var_120]
0x140039762  mov     [r14+2], ax
0x140039767  add     r13d, 2
0x14003976b  movzx   eax, [rbp+0B0h+var_12A]
0x14003976f  mov     rdx, r12
0x140039772  mov     [r14+6], ax
0x140039777  mov     word ptr [r14+4], 16h
0x14003977e  mov     eax, [rbp+0B0h+var_124]
0x140039781  mov     [r14+8], eax
0x140039785  movzx   eax, word ptr [rbp+0B0h+var_130]
0x140039789  mov     [r14+0Ch], ax
0x14003978e  mov     eax, [rbp+0B0h+var_114]
0x140039791  mov     [r14+0Eh], eax
0x140039795  xor     eax, eax
0x140039797  mov     [r14+12h], rax
0x14003979b  mov     [r14+1Ah], ax
0x1400397a0  mov     [rbp+0B0h+var_120], rbx
0x1400397a4  mov     [rbp+0B0h+var_130], r13d
0x1400397a8  cmp     [rbp+0B0h+var_110], eax
0x1400397ab  jz      short loc_1400397B4
0x1400397ad  call    SmbPutUnicodeString
0x1400397b2  jmp     short loc_1400397CF
0x1400397b4  call    SmbPutUnicodeStringAsOemString
0x1400397b9  mov     rdx, rbx
0x1400397bc  lea     rcx, aThisIsTheNameS; "This is the name <%s>\n"
0x1400397c3  call    cs:__imp_DbgPrint
0x1400397ca  nop     dword ptr [rax+rax+00h]
0x1400397cf  mov     r8d, [rbp+0B0h+var_10C]
0x1400397d3  test    r8d, r8d
0x1400397d6  jz      short loc_140039848
0x1400397d8  mov     r12, [rbp+0B0h+var_F0]
0x1400397dc  lea     rcx, aMrxsmbt2openAg; "MRxSmbT2Open again---%p %08lx\n"
0x1400397e3  mov     rdx, r12
0x1400397e6  call    cs:__imp_DbgPrint
0x1400397ed  nop     dword ptr [rax+rax+00h]
0x1400397f2  mov     rcx, r12
0x1400397f5  call    MRxSmbNtFullEaSizeToOs2
0x1400397fa  mov     ebx, eax
0x1400397fc  cmp     eax, 0FFFFh
0x140039801  jbe     short loc_14003980F
0x140039803  xor     edi, edi
0x140039805  mov     ebx, 0C0000050h
0x14003980a  jmp     loc_140039994
0x14003980f  mov     rdx, rbx
0x140039812  mov     ecx, 102h
0x140039817  mov     r8d, 45626D73h
0x14003981d  call    cs:__imp_ExAllocatePool2
0x140039824  nop     dword ptr [rax+rax+00h]
0x140039829  mov     rdi, rax
0x14003982c  test    rax, rax
0x14003982f  jnz     short loc_14003983B
0x140039831  mov     ebx, 0C000009Ah
0x140039836  jmp     loc_140039994
0x14003983b  mov     rdx, rax
0x14003983e  mov     rcx, r12
0x140039841  call    MRxSmbNtFullListToOs2
0x140039846  jmp     short loc_14003984C
0x140039848  xor     ebx, ebx
0x14003984a  xor     edi, edi
0x14003984c  sub     r13d, [rbp+0B0h+var_130]; __annotation("TMF:",
0x140039850  lea     rax, WPP_GLOBAL_Control
0x140039857  mov     rcx, cs:WPP_GLOBAL_Control
0x14003985e  add     r13d, 1Ch
0x140039862  cmp     rcx, rax
0x140039865  jz      short loc_14003988D
0x140039867  test    dword ptr [rcx+2Ch], 400h
0x14003986e  jz      short loc_14003988D
0x140039870  mov     rcx, [rcx+18h]
0x140039874  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x14003987b  mov     edx, 3Fh ; '?'
0x140039880  mov     [rsp+1B0h+var_190], rdi
0x140039885  mov     r9d, ebx
0x140039888  call    WPP_SF_dq
0x14003988d  movzx   eax, word ptr cs:RxDefaultTransactionOptions
0x140039894  or      r15w, word ptr cs:RxDefaultTransactionOptions+2
0x14003989c  movups  xmm0, cs:RxDefaultTransactionOptions+4
0x1400398a3  mov     word ptr [rbp+0B0h+var_108], ax
0x1400398a7  mov     eax, dword ptr cs:qword_14001F6B0+4
0x1400398ad  mov     dword ptr [rbp+0B0h+var_F8+4], eax
0x1400398b0  mov     rax, [rsi+288h]
0x1400398b7  movdqu  [rbp+0B0h+var_108+4], xmm0
0x1400398bc  mov     word ptr [rbp+0B0h+var_108+2], r15w
0x1400398c1  mov     ecx, [rax+38h]
0x1400398c4  test    cl, 2
0x1400398c7  jz      short loc_1400398E2
0x1400398c9  mov     eax, 0FF444653h
0x1400398ce  cmp     [rsi+230h], rax
0x1400398d5  jnz     short loc_1400398E2
0x1400398d7  or      r15w, 200h
0x1400398dd  mov     word ptr [rbp+0B0h+var_108+2], r15w
0x1400398e2  lea     rcx, [rbp+0B0h+var_E0]
0x1400398e6  mov     dword ptr [rbp+0B0h+var_F8+4], 0FFFFh
0x1400398ed  call    SmbCeInitializeTransactionResumptionContext
0x1400398f2  mov     r15, [rbp+0B0h+var_E8]
0x1400398f6  mov     rcx, r15
0x1400398f9  call    cs:__imp_RxFcbGetOutstandingBufferingChangeEvent
0x140039900  nop     dword ptr [rax+rax+00h]
0x140039905  xor     ecx, ecx
0x140039907  mov     [rbp+0B0h+var_80], r15
0x14003990b  mov     [rbp+0B0h+var_90], rax
0x14003990f  lea     r8, [rbp+0B0h+var_128]
0x140039913  mov     rax, cs:__imp_RxProcessFcbChangeBufferingStateRequest
0x14003991a  lea     rdx, [rbp+0B0h+var_108]
0x14003991e  mov     [rbp+0B0h+var_88], rax
0x140039922  lea     rax, [rbp+0B0h+var_E0]
0x140039926  mov     [rsp+1B0h+var_140], rax
0x14003992b  lea     r9d, [rcx+2]
0x14003992f  mov     [rsp+1B0h+var_148], ecx
0x140039933  lea     rax, [rbp+0B0h+var_70]
0x140039937  mov     [rsp+1B0h+var_150], rcx
0x14003993c  mov     [rsp+1B0h+var_158], ebx
0x140039940  mov     [rsp+1B0h+var_160], rdi
0x140039945  mov     [rsp+1B0h+var_168], 1Eh
0x14003994d  mov     [rsp+1B0h+var_170], rax
0x140039952  mov     [rsp+1B0h+var_178], r13d
0x140039957  mov     [rsp+1B0h+var_180], r14
0x14003995c  mov     [rsp+1B0h+var_188], ecx
0x140039960  mov     [rsp+1B0h+var_190], rcx
0x140039965  mov     rcx, rsi
0x140039968  call    _SmbCeTransact
0x14003996d  mov     ebx, eax
0x14003996f  test    eax, eax
0x140039971  js      short loc_140039994
0x140039973  mov     r9d, [rbp+0B0h+var_98]
0x140039977  lea     rdx, [rbp+0B0h+var_70]
0x14003997b  mov     rcx, rsi; RxContext
0x14003997e  call    MRxSmbFinishT2OpenFile
0x140039983  cmp     dword ptr [rsi+218h], 1
0x14003998a  jnz     short loc_140039994
0x14003998c  mov     rcx, rsi
0x14003998f  call    MRxSmbAdjustReturnedCreateAction
0x140039994  xor     edx, edx; Tag
0x140039996  mov     rcx, r14; P
0x140039999  call    cs:__imp_ExFreePoolWithTag
0x1400399a0  nop     dword ptr [rax+rax+00h]
0x1400399a5  test    rdi, rdi
0x1400399a8  jz      short loc_1400399BB
0x1400399aa  xor     edx, edx; Tag
0x1400399ac  mov     rcx, rdi; P
0x1400399af  call    cs:__imp_ExFreePoolWithTag
0x1400399b6  nop     dword ptr [rax+rax+00h]
0x1400399bb  mov     eax, ebx
0x1400399bd  mov     rcx, [rbp+0B0h+var_50]
0x1400399c1  xor     rcx, rsp; StackCookie
0x1400399c4  call    __security_check_cookie
0x1400399c9  add     rsp, 178h
0x1400399d0  pop     r15
0x1400399d2  pop     r14
0x1400399d4  pop     r13
0x1400399d6  pop     r12
0x1400399d8  pop     rdi
0x1400399d9  pop     rsi
0x1400399da  pop     rbx
0x1400399db  pop     rbp
0x1400399dc  retn
```
