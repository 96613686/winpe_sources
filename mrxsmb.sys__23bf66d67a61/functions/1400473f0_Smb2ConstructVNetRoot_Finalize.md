# Smb2ConstructVNetRoot_Finalize

- ea: `0x1400473f0`
- end: `0x14004786f`
- name: `Smb2ConstructVNetRoot_Finalize`
- size: `1151`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140003480`
- `0x140028960`
- `0x14002f7a8`
- `0x14003838c`
- `0x1400423fc`
- `0x1400460d0`
- `0x1400471e0`
- `0x1400473f0`
- `0x140047ba8`
- `0x14004827c`

## import_xrefs

- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x1400475da`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x1400475da`
- `ntoskrnl!IoGetRequestorProcess` at `0x140047729`
- `ntoskrnl!IoGetRequestorProcess` at `0x140047729`
- `ntoskrnl!PsGetProcessId` at `0x14004775f`
- `ntoskrnl!PsGetProcessId` at `0x14004775f`
- `ntoskrnl!SeLocateProcessImageName` at `0x140047779`
- `ntoskrnl!SeLocateProcessImageName` at `0x140047779`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14004757e`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14004757e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400477e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400477e8`

## pseudocode

```c
__int64 __fastcall Smb2ConstructVNetRoot_Finalize(__int64 a1)
{
  _QWORD *v1; // r14
  int v3; // ebp
  __int64 v4; // rdi
  char v5; // r15
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rbx
  KIRQL v9; // r15
  __int64 v10; // rax
  __int64 v11; // rax
  NTSTATUS v12; // eax
  bool v13; // bl
  char v14; // al
  __int64 v15; // rcx
  IRP *v16; // rcx
  struct _KPROCESS *RequestorProcess; // rbx
  __int64 v18; // rax
  __int64 v19; // rcx
  unsigned __int16 v20; // di
  __int64 v21; // r14
  char ProcessId; // r15
  NTSTATUS v23; // eax
  int v24; // r8d
  BOOL v25; // ecx
  wchar_t *Buffer; // rdx
  int Length; // r9d
  PUNICODE_STRING pImageFileName; // [rsp+A0h] [rbp+8h] BYREF

  v1 = *(_QWORD **)(a1 + 88);
  v3 = *(_DWORD *)(a1 + 16);
  v4 = v1[52];
  v5 = *(_BYTE *)(v4 + 469);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqdddddddd(
      WPP_GLOBAL_Control->AttachedDevice,
      *(unsigned __int8 *)(v4 + 465),
      *(unsigned __int8 *)(a1 + 1032),
      v1,
      v4,
      v3,
      *(unsigned __int8 *)(a1 + 1032),
      *(unsigned __int8 *)(v4 + 465),
      *(unsigned __int8 *)(v4 + 466),
      *(_BYTE *)(a1 + 1016) & 1,
      (*(unsigned __int8 *)(a1 + 1016) >> 1) & 1,
      (*(unsigned __int8 *)(a1 + 1016) >> 2) & 1,
      *(unsigned __int8 *)(v4 + 469));
  }
  SmbCeDecrementNtlmOpenCounts(v4, a1 + 1033);
  if ( v3 >= 0 )
  {
    if ( *(_BYTE *)(a1 + 1032) )
    {
      v8 = v1[3];
      v9 = SmbCeAcquireSpinLock(v8, v6, v7);
      if ( !*(_BYTE *)(v4 + 465) || *(_BYTE *)(v4 + 466) )
      {
        if ( *(_DWORD *)(v4 + 12) )
        {
          v10 = *(unsigned __int16 *)(v4 + 2);
          if ( (_WORD)v10 )
            v11 = v4 + v10;
          else
            v11 = 0;
          v3 = *(_DWORD *)(v11 + 208);
        }
        else
        {
          *(_BYTE *)(v4 + 656) = 1;
        }
      }
      else
      {
        v3 = -1073740776;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qZd(
            WPP_GLOBAL_Control->AttachedDevice,
            11,
            (unsigned int)WPP_c2a8e7a4add33c98a1c08e02d1cd8763_Traceguids,
            (_DWORD)v1,
            v1[53] + 96LL,
            24);
        }
      }
      *(_DWORD *)(v8 + 2352) = -1;
      ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v8 + 1920), v9);
      goto LABEL_56;
    }
    if ( !*(_BYTE *)(v4 + 465) || *(_BYTE *)(v4 + 466) || v5 )
      goto LABEL_56;
    if ( (*(_BYTE *)(a1 + 1016) & 3) == 2 )
    {
      v12 = RtlRunOnceExecuteOnce((PRTL_RUN_ONCE)(v4 + 472), SmbCeIsServerTrustedZoneRunOnce, (PVOID)v4, 0);
      v13 = *(_BYTE *)(v4 + 480) == 0;
      if ( v12 >= 0 )
      {
LABEL_29:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qqD(
            WPP_GLOBAL_Control->AttachedDevice,
            13,
            WPP_c2a8e7a4add33c98a1c08e02d1cd8763_Traceguids,
            v1,
            a1,
            v13);
        }
        goto LABEL_34;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            12,
            WPP_c2a8e7a4add33c98a1c08e02d1cd8763_Traceguids,
            (unsigned int)v12);
        goto LABEL_29;
      }
    }
    else
    {
      v13 = 1;
    }
LABEL_34:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_Zqqqddd(
        WPP_GLOBAL_Control->AttachedDevice,
        (*(unsigned __int8 *)(a1 + 1016) >> 2) & 1,
        *(_BYTE *)(a1 + 1016) & 1,
        *(_QWORD *)(v4 + 384) + 128,
        (char)v1,
        v4,
        a1,
        *(_BYTE *)(a1 + 1016) & 1,
        (*(_BYTE *)(a1 + 1016) & 2) != 0,
        (*(_BYTE *)(a1 + 1016) & 4) != 0);
    }
    v14 = *(_BYTE *)(a1 + 1016);
    if ( (v14 & 1) != 0 || (v14 & 2) != 0 && v13 )
    {
      if ( (v14 & 4) != 0 )
      {
        v15 = *(_QWORD *)(a1 + 48);
        if ( (*(_BYTE *)(v15 + 749) & 8) != 0 )
        {
          v16 = *(IRP **)(v15 + 40);
          if ( v16 )
          {
            RequestorProcess = IoGetRequestorProcess(v16);
            if ( RequestorProcess )
            {
              v18 = *(_QWORD *)(a1 + 88);
              pImageFileName = 0;
              v19 = *(_QWORD *)(v18 + 424);
              v20 = *(_WORD *)(v19 + 96);
              v21 = *(_QWORD *)(v19 + 104);
              ProcessId = (unsigned __int8)PsGetProcessId(RequestorProcess);
              v23 = SeLocateProcessImageName(RequestorProcess, &pImageFileName);
              if ( (byte_1400712C4 & 0x10) != 0 )
              {
                if ( v23 < 0 )
                {
                  Length = 0;
                  Buffer = 0;
                }
                else
                {
                  Length = pImageFileName->Length;
                  Buffer = pImageFileName->Buffer;
                  LOWORD(Length) = (unsigned __int16)Length >> 1;
                }
                v25 = (*(_BYTE *)(a1 + 1016) & 1) == 0;
                McTemplateK0hzr0qqhzr4hzr6_EtwWriteTransfer(
                  v25,
                  (_DWORD)Buffer,
                  v24,
                  Length,
                  (__int64)Buffer,
                  ProcessId,
                  v25,
                  v20 >> 1,
                  v21);
              }
              if ( pImageFileName )
                ExFreePoolWithTag(pImageFileName, 0);
            }
          }
        }
      }
      else
      {
        v3 = -1067646964;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qZd(
            WPP_GLOBAL_Control->AttachedDevice,
            15,
            (unsigned int)WPP_c2a8e7a4add33c98a1c08e02d1cd8763_Traceguids,
            (_DWORD)v1,
            v1[53] + 96LL,
            12);
        }
      }
    }
  }
LABEL_56:
  SmbCeCompleteVNetRootConstruction(*(_QWORD **)(a1 + 88), *(PVOID *)(a1 + 1024), (unsigned int)v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400473f0  mov     [rsp+arg_8], rbx
0x1400473f5  mov     [rsp+arg_10], rbp
0x1400473fa  push    rsi
0x1400473fb  push    rdi
0x1400473fc  push    r12
0x1400473fe  push    r14
0x140047400  push    r15
0x140047402  sub     rsp, 70h
0x140047406  mov     r14, [rcx+58h]
0x14004740a  mov     rsi, rcx
0x14004740d  mov     ebp, [rcx+10h]
0x140047410  mov     rdi, [r14+1A0h]
0x140047417  movzx   r15d, byte ptr [rdi+1D5h]
0x14004741f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140047426  lea     rax, WPP_GLOBAL_Control
0x14004742d  cmp     rcx, rax
0x140047430  jz      short loc_1400474A9
0x140047432  mov     eax, [rcx+2Ch]
0x140047435  test    al, 40h
0x140047437  jz      short loc_1400474A9
0x140047439  cmp     byte ptr [rcx+29h], 4
0x14004743d  jb      short loc_1400474A9
0x14004743f  movzx   ebx, byte ptr [rsi+3F8h]
0x140047446  movzx   eax, byte ptr [rdi+1D2h]
0x14004744d  mov     r11d, ebx
0x140047450  movzx   edx, byte ptr [rdi+1D1h]
0x140047457  mov     r9d, ebx
0x14004745a  movzx   r8d, byte ptr [rsi+408h]
0x140047462  and     ebx, 1
0x140047465  mov     rcx, [rcx+18h]
0x140047469  mov     [rsp+98h+var_38], r15d
0x14004746e  shr     r9d, 1
0x140047471  and     r9d, 1
0x140047475  shr     r11d, 2
0x140047479  and     r11d, 1
0x14004747d  mov     [rsp+98h+var_40], r11d
0x140047482  mov     [rsp+98h+var_48], r9d
0x140047487  mov     r9, r14
0x14004748a  mov     [rsp+98h+var_50], ebx
0x14004748e  mov     dword ptr [rsp+98h+var_58], eax
0x140047492  mov     [rsp+98h+var_60], edx
0x140047496  mov     dword ptr [rsp+98h+var_68], r8d
0x14004749b  mov     dword ptr [rsp+98h+var_70], ebp
0x14004749f  mov     [rsp+98h+var_78], rdi
0x1400474a4  call    WPP_SF_qqdddddddd
0x1400474a9  lea     rdx, [rsi+409h]
0x1400474b0  mov     rcx, rdi
0x1400474b3  call    SmbCeDecrementNtlmOpenCounts
0x1400474b8  xor     r12d, r12d
0x1400474bb  test    ebp, ebp
0x1400474bd  js      loc_140047840
0x1400474c3  cmp     [rsi+408h], r12b
0x1400474ca  jz      loc_14004758F
0x1400474d0  mov     rbx, [r14+18h]
0x1400474d4  mov     rcx, rbx
0x1400474d7  call    SmbCeAcquireSpinLock
0x1400474dc  mov     r15b, al
0x1400474df  cmp     [rdi+1D1h], r12b
0x1400474e6  jz      short loc_140047544
0x1400474e8  cmp     [rdi+1D2h], r12b
0x1400474ef  jnz     short loc_140047544
0x1400474f1  mov     ebp, 0C0000418h
0x1400474f6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400474fd  lea     rax, WPP_GLOBAL_Control
0x140047504  cmp     rcx, rax
0x140047507  jz      short loc_14004756A
0x140047509  mov     eax, [rcx+2Ch]
0x14004750c  test    al, 40h
0x14004750e  jz      short loc_14004756A
0x140047510  cmp     byte ptr [rcx+29h], 1
0x140047514  jb      short loc_14004756A
0x140047516  mov     rax, [r14+1A8h]
0x14004751d  lea     edx, [r12+0Bh]
0x140047522  mov     rcx, [rcx+18h]
0x140047526  lea     r8, WPP_c2a8e7a4add33c98a1c08e02d1cd8763_Traceguids
0x14004752d  add     rax, 60h ; '`'
0x140047531  mov     dword ptr [rsp+98h+var_70], ebp
0x140047535  mov     r9, r14
0x140047538  mov     [rsp+98h+var_78], rax
0x14004753d  call    WPP_SF_qZd
0x140047542  jmp     short loc_14004756A
0x140047544  cmp     [rdi+0Ch], r12d
0x140047548  jnz     short loc_140047553
0x14004754a  mov     byte ptr [rdi+290h], 1
0x140047551  jmp     short loc_14004756A
0x140047553  movzx   eax, word ptr [rdi+2]
0x140047557  test    ax, ax
0x14004755a  jnz     short loc_140047561
0x14004755c  mov     rax, r12
0x14004755f  jmp     short loc_140047564
0x140047561  add     rax, rdi
0x140047564  mov     ebp, [rax+0D0h]
0x14004756a  lea     rcx, [rbx+780h]; SpinLock
0x140047571  mov     dword ptr [rbx+930h], 0FFFFFFFFh
0x14004757b  mov     dl, r15b; OldIrql
0x14004757e  call    cs:__imp_ExReleaseSpinLockExclusive
0x140047585  nop     dword ptr [rax+rax+00h]
0x14004758a  jmp     loc_140047840
0x14004758f  cmp     [rdi+1D1h], r12b
0x140047596  jz      loc_140047840
0x14004759c  cmp     [rdi+1D2h], r12b
0x1400475a3  jnz     loc_140047840
0x1400475a9  test    r15b, r15b
0x1400475ac  jnz     loc_140047840
0x1400475b2  mov     al, [rsi+3F8h]
0x1400475b8  mov     r15b, 2
0x1400475bb  and     al, 3
0x1400475bd  cmp     al, r15b
0x1400475c0  jnz     loc_140047672
0x1400475c6  lea     rcx, [rdi+1D8h]; RunOnce
0x1400475cd  xor     r9d, r9d; Context
0x1400475d0  mov     r8, rdi; Parameter
0x1400475d3  lea     rdx, SmbCeIsServerTrustedZoneRunOnce; InitFn
0x1400475da  call    cs:__imp_RtlRunOnceExecuteOnce
0x1400475e1  nop     dword ptr [rax+rax+00h]
0x1400475e6  cmp     [rdi+1E0h], r12b
0x1400475ed  mov     r9d, eax
0x1400475f0  setz    bl
0x1400475f3  test    eax, eax
0x1400475f5  jns     short loc_14004762C
0x1400475f7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400475fe  lea     rax, WPP_GLOBAL_Control
0x140047605  cmp     rcx, rax
0x140047608  jz      short loc_140047674
0x14004760a  mov     eax, [rcx+2Ch]
0x14004760d  test    al, 40h
0x14004760f  jz      short loc_14004762C
0x140047611  cmp     byte ptr [rcx+29h], 1
0x140047615  jb      short loc_14004762C
0x140047617  mov     rcx, [rcx+18h]
0x14004761b  lea     r8, WPP_c2a8e7a4add33c98a1c08e02d1cd8763_Traceguids
0x140047622  mov     edx, 0Ch
0x140047627  call    WPP_SF_d
0x14004762c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140047633  lea     rax, WPP_GLOBAL_Control
0x14004763a  cmp     rcx, rax
0x14004763d  jz      short loc_140047674
0x14004763f  mov     eax, [rcx+2Ch]
0x140047642  test    al, 40h
0x140047644  jz      short loc_140047674
0x140047646  cmp     [rcx+29h], r15b
0x14004764a  jb      short loc_140047674
0x14004764c  mov     rcx, [rcx+18h]
0x140047650  lea     r8, WPP_c2a8e7a4add33c98a1c08e02d1cd8763_Traceguids
0x140047657  movzx   eax, bl
0x14004765a  mov     edx, 0Dh
0x14004765f  mov     dword ptr [rsp+98h+var_70], eax
0x140047663  mov     r9, r14
0x140047666  mov     [rsp+98h+var_78], rsi
0x14004766b  call    WPP_SF_qqD
0x140047670  jmp     short loc_140047674
0x140047672  mov     bl, 1
0x140047674  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004767b  lea     r9, WPP_GLOBAL_Control
0x140047682  cmp     rcx, r9
0x140047685  jz      short loc_1400476E8
0x140047687  mov     eax, [rcx+2Ch]
0x14004768a  test    al, 40h
0x14004768c  jz      short loc_1400476E8
0x14004768e  cmp     [rcx+29h], r15b
0x140047692  jb      short loc_1400476E8
0x140047694  movzx   r8d, byte ptr [rsi+3F8h]
0x14004769c  mov     r9, [rdi+180h]
0x1400476a3  mov     edx, r8d
0x1400476a6  mov     rcx, [rcx+18h]
0x1400476aa  mov     eax, r8d
0x1400476ad  shr     edx, 2
0x1400476b0  and     r8d, 1
0x1400476b4  shr     eax, 1
0x1400476b6  and     edx, 1
0x1400476b9  mov     [rsp+98h+var_50], edx
0x1400476bd  and     eax, 1
0x1400476c0  mov     dword ptr [rsp+98h+var_58], eax
0x1400476c4  sub     r9, 0FFFFFFFFFFFFFF80h
0x1400476c8  mov     [rsp+98h+var_60], r8d
0x1400476cd  mov     [rsp+98h+var_68], rsi
0x1400476d2  mov     [rsp+98h+var_70], rdi
0x1400476d7  mov     [rsp+98h+var_78], r14
0x1400476dc  call    WPP_SF_Zqqqddd
0x1400476e1  lea     r9, WPP_GLOBAL_Control
0x1400476e8  mov     al, [rsi+3F8h]
0x1400476ee  test    al, 1
0x1400476f0  jnz     short loc_140047703
0x1400476f2  test    r15b, al
0x1400476f5  jz      loc_140047840
0x1400476fb  test    bl, bl
0x1400476fd  jz      loc_140047840
0x140047703  test    al, 4
0x140047705  jz      loc_1400477F6
0x14004770b  mov     rcx, [rsi+30h]
0x14004770f  test    byte ptr [rcx+2EDh], 8
0x140047716  jz      loc_140047840
0x14004771c  mov     rcx, [rcx+28h]; Irp
0x140047720  test    rcx, rcx
0x140047723  jz      loc_140047840
0x140047729  call    cs:__imp_IoGetRequestorProcess
0x140047730  nop     dword ptr [rax+rax+00h]
0x140047735  mov     rbx, rax
0x140047738  test    rax, rax
0x14004773b  jz      loc_140047840
0x140047741  mov     rax, [rsi+58h]
0x140047745  mov     [rsp+98h+pImageFileName], r12
0x14004774d  mov     rcx, [rax+1A8h]
0x140047754  movzx   edi, word ptr [rcx+60h]
0x140047758  mov     r14, [rcx+68h]
0x14004775c  mov     rcx, rbx; Process
0x14004775f  call    cs:__imp_PsGetProcessId
0x140047766  nop     dword ptr [rax+rax+00h]
0x14004776b  lea     rdx, [rsp+98h+pImageFileName]; pImageFileName
0x140047773  mov     rcx, rbx; Process
0x140047776  mov     r15, rax
0x140047779  call    cs:__imp_SeLocateProcessImageName
0x140047780  nop     dword ptr [rax+rax+00h]
0x140047785  test    cs:byte_1400712C4, 10h
0x14004778c  jz      short loc_1400477D9
0x14004778e  mov     cl, [rsi+3F8h]
0x140047794  not     cl
0x140047796  and     ecx, 1
0x140047799  test    eax, eax
0x14004779b  js      short loc_1400477B3
0x14004779d  mov     rax, [rsp+98h+pImageFileName]
0x1400477a5  movzx   r9d, word ptr [rax]
0x1400477a9  mov     rdx, [rax+8]
0x1400477ad  shr     r9w, 1
0x1400477b1  jmp     short loc_1400477B9
0x1400477b3  mov     r9d, r12d
0x1400477b6  mov     rdx, r12
0x1400477b9  mov     [rsp+98h+var_58], r14
0x1400477be  shr     di, 1
0x1400477c1  mov     word ptr [rsp+98h+var_60], di
0x1400477c6  mov     dword ptr [rsp+98h+var_68], ecx
0x1400477ca  mov     dword ptr [rsp+98h+var_70], r15d
0x1400477cf  mov     [rsp+98h+var_78], rdx
0x1400477d4  call    McTemplateK0hzr0qqhzr4hzr6_EtwWriteTransfer
0x1400477d9  mov     rcx, [rsp+98h+pImageFileName]; P
0x1400477e1  test    rcx, rcx
0x1400477e4  jz      short loc_140047840
0x1400477e6  xor     edx, edx; Tag
0x1400477e8  call    cs:__imp_ExFreePoolWithTag
0x1400477ef  nop     dword ptr [rax+rax+00h]
0x1400477f4  jmp     short loc_140047840
0x1400477f6  mov     ebp, 0C05D000Ch
0x1400477fb  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140047802  cmp     rcx, r9
0x140047805  jz      short loc_140047840
0x140047807  mov     eax, [rcx+2Ch]
0x14004780a  test    al, 40h
0x14004780c  jz      short loc_140047840
0x14004780e  cmp     byte ptr [rcx+29h], 1
0x140047812  jb      short loc_140047840
0x140047814  mov     r8, [r14+1A8h]
0x14004781b  mov     edx, 0Fh
0x140047820  mov     rcx, [rcx+18h]
0x140047824  add     r8, 60h ; '`'
0x140047828  mov     dword ptr [rsp+98h+var_70], ebp
0x14004782c  mov     r9, r14
0x14004782f  mov     [rsp+98h+var_78], r8
0x140047834  lea     r8, WPP_c2a8e7a4add33c98a1c08e02d1cd8763_Traceguids
0x14004783b  call    WPP_SF_qZd
0x140047840  mov     rdx, [rsi+400h]; pContext
0x140047847  mov     r8d, ebp
0x14004784a  mov     rcx, [rsi+58h]; BugCheckParameter2
0x14004784e  call    SmbCeCompleteVNetRootConstruction
0x140047853  lea     r11, [rsp+98h+var_28]
0x140047858  mov     eax, ebp
0x14004785a  mov     rbx, [r11+38h]
0x14004785e  mov     rbp, [r11+40h]
0x140047862  mov     rsp, r11
0x140047865  pop     r15
0x140047867  pop     r14
0x140047869  pop     r12
0x14004786b  pop     rdi
0x14004786c  pop     rsi
0x14004786d  retn
```
