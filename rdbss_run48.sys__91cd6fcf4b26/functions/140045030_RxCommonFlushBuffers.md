# RxCommonFlushBuffers

- ea: `0x140045030`
- end: `0x140045404`
- name: `RxCommonFlushBuffers`
- size: `980`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140007ca0`
- `0x140009b80`
- `0x14000f130`
- `0x14000f2c0`
- `0x140010630`
- `0x140010730`
- `0x140016d40`
- `0x140016e20`
- `0x140017280`
- `0x14001810c`
- `0x140025d00`
- `0x140045030`
- `0x140057660`
- `0x14006d6e0`

## import_xrefs

- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x1400452a6`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x1400452a6`
- `ntoskrnl!MmIsFileSectionActive` at `0x140045388`
- `ntoskrnl!MmIsFileSectionActive` at `0x140045388`

## string_xrefs

- `0x14007ba88`: `RxCommonFlushBuffers`

## pseudocode

```c
__int64 __fastcall RxCommonFlushBuffers(PRX_CONTEXT RxContext, __int64 a2)
{
  ULONG v3; // r8d
  const CHAR *v4; // r9
  int v5; // r12d
  PFCB v6; // rdi
  NTSTATUS v7; // ebx
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  char v11; // r15
  LARGE_INTEGER ValidDataLength; // rcx
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // r8
  const CHAR *v16; // [rsp+20h] [rbp-48h]
  ULONG v17; // [rsp+28h] [rbp-40h]
  __int64 v18; // [rsp+78h] [rbp+10h] BYREF
  PFCB Fcb; // [rsp+80h] [rbp+18h] BYREF

  Fcb = 0;
  v18 = 0;
  v5 = (unsigned __int16)RxDecodeFileObject2(*(_QWORD *)(*(_QWORD *)(a2 + 184) + 48LL), &Fcb, &v18);
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
  {
    v6 = Fcb;
  }
  else
  {
    v6 = Fcb;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_qqq(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        &WPP_aa2c0bb7317938a782fd85b9c42c319a_Traceguids,
        RxContext,
        Fcb,
        v18);
  }
  if ( ((__int64)RxContext->RdbssDbgExtension & 2) == 0 )
  {
    v7 = RxFsdPostRequest(RxContext);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      v9 = 11;
LABEL_11:
      WPP_SF_d(v8->AttachedDevice, v9, &WPP_aa2c0bb7317938a782fd85b9c42c319a_Traceguids, (unsigned int)v7);
      return (unsigned int)v7;
    }
    return (unsigned int)v7;
  }
  v11 = 0;
  v7 = 0;
  ValidDataLength.QuadPart = (unsigned int)(v5 - 60450);
  if ( v5 == 60450 )
  {
    if ( *(_BYTE *)(*((_QWORD *)&v6->1 + 15) + 77LL) != 1 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, &WPP_aa2c0bb7317938a782fd85b9c42c319a_Traceguids);
      }
      if ( v6->RxDeviceObject->DeviceObject.DriverObject )
      {
        v7 = _RxAcquireFcb(v6, RxContext, 1u, 0, v16, v17);
        if ( v7 < 0 )
          goto LABEL_50;
        v11 = 1;
        LOBYTE(v13) = 1;
        v7 = RxFlushFcbInSystemCacheEx(v6, v13, 0);
        if ( v7 < 0 )
          goto LABEL_50;
        ExConvertExclusiveToSharedLite(v6->Header.Resource);
      }
      else
      {
        v7 = _RxAcquireFcb(v6, RxContext, 2u, 0, v16, v17);
        if ( v7 < 0 )
          goto LABEL_50;
        v11 = 1;
      }
    }
    if ( (*(_DWORD *)(*(_QWORD *)&v6->NumberOfLinks + 336LL) & 0x4000) == 0
      || ((__int64)v6->FcbTableEntry.HashLinks.Blink & 1) != 0
      || v6->LastChangeTime.LowPart )
    {
      ValidDataLength = RxContext->pFcb[2].Header.ValidDataLength;
      if ( !*(_QWORD *)(ValidDataLength.QuadPart + 88) )
        goto LABEL_40;
      if ( ((__int64)RxContext->ScavengerEntry.List.Flink & 2) != 0 )
      {
        v7 = -1073741536;
      }
      else
      {
        *(_OWORD *)&RxContext->MRxContext[2] = 0;
        *(_OWORD *)&RxContext->WriteOnlyOpenRetryContext = 0;
        RxContext->ResumeRoutine = 0;
        v7 = (*(__int64 (__fastcall **)(PRX_CONTEXT))(RxContext->pFcb[2].Header.ValidDataLength.QuadPart + 88))(RxContext);
      }
    }
    if ( v7 >= 0 )
    {
      ((void (__fastcall *)(_QWORD))RxAcquirePowerContextLock)((LARGE_INTEGER)ValidDataLength.QuadPart);
      LODWORD(v18) = 0;
      MmIsFileSectionActive(&v6->RxDeviceObject->DriverObject, 7, &v18);
      if ( !(_DWORD)v18 )
        BYTE2(v6->PrivateAlreadyPrefixedName.Buffer) &= ~0x80u;
      if ( (BYTE2(v6->PrivateAlreadyPrefixedName.Buffer) & 4) != 0 )
      {
        LOBYTE(v15) = 2;
        LOBYTE(v14) = 4;
        RxUpdateFcbPowerState(v6, v14, v15);
      }
      RxReleasePowerContextLock();
    }
  }
  else
  {
    if ( v5 != 60455 )
    {
      v7 = -1073741808;
      goto LABEL_50;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, &WPP_aa2c0bb7317938a782fd85b9c42c319a_Traceguids);
    }
    v7 = _RxAcquireFcb(v6, RxContext, 1u, 0, v16, v17);
    if ( !v7 )
    {
      v11 = 1;
      if ( *(_QWORD *)(RxContext->pFcb[2].Header.ValidDataLength.QuadPart + 88) )
      {
        if ( ((__int64)RxContext->ScavengerEntry.List.Flink & 2) != 0 )
        {
          v7 = -1073741536;
        }
        else
        {
          *(_OWORD *)&RxContext->MRxContext[2] = 0;
          *(_OWORD *)&RxContext->WriteOnlyOpenRetryContext = 0;
          RxContext->ResumeRoutine = 0;
          v7 = (*(__int64 (__fastcall **)(PRX_CONTEXT))(RxContext->pFcb[2].Header.ValidDataLength.QuadPart + 88))(RxContext);
        }
        goto LABEL_50;
      }
LABEL_40:
      v7 = -1073741822;
    }
  }
LABEL_50:
  if ( v11 )
    _RxReleaseFcb(RxContext, (PMRX_FCB)&v6->Header, v3, v4, (ULONG)v16);
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    v9 = 14;
    goto LABEL_11;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140045030  mov     rax, rsp
0x140045033  mov     [rax+8], rcx
0x140045037  push    rbx
0x140045038  push    rsi
0x140045039  push    rdi
0x14004503a  push    r12
0x14004503c  push    r15
0x14004503e  sub     rsp, 40h
0x140045042  mov     rsi, rcx
0x140045045  mov     qword ptr [rax+18h], 0
0x14004504d  mov     qword ptr [rax+10h], 0
0x140045055  mov     rcx, [rdx+0B8h]
0x14004505c  lea     r8, [rax+10h]
0x140045060  lea     rdx, [rax+18h]
0x140045064  mov     rcx, [rcx+30h]
0x140045068  call    RxDecodeFileObject2
0x14004506d  movzx   r12d, ax
0x140045071  lea     rdx, WPP_GLOBAL_Control
0x140045078  mov     rcx, cs:WPP_GLOBAL_Control
0x14004507f  cmp     rcx, rdx
0x140045082  jz      short loc_1400450C9
0x140045084  mov     eax, [rcx+2Ch]
0x140045087  test    al, 4
0x140045089  jz      short loc_1400450C9
0x14004508b  mov     rdi, [rsp+68h+Fcb]
0x140045093  cmp     byte ptr [rcx+29h], 2
0x140045097  jb      short loc_1400450D1
0x140045099  mov     edx, 0Ah
0x14004509e  mov     rax, [rsp+68h+arg_8]
0x1400450a3  mov     [rsp+68h+var_40], rax
0x1400450a8  mov     [rsp+68h+var_48], rdi
0x1400450ad  mov     r9, rsi
0x1400450b0  lea     r8, WPP_aa2c0bb7317938a782fd85b9c42c319a_Traceguids
0x1400450b7  mov     rcx, [rcx+18h]
0x1400450bb  call    WPP_SF_qqq
0x1400450c0  lea     rdx, WPP_GLOBAL_Control
0x1400450c7  jmp     short loc_1400450D1
0x1400450c9  mov     rdi, [rsp+68h+Fcb]
0x1400450d1  mov     eax, [rsi+78h]
0x1400450d4  test    al, 2
0x1400450d6  jnz     short loc_14004512A
0x1400450d8  mov     rcx, rsi; RxContext
0x1400450db  call    RxFsdPostRequest
0x1400450e0  mov     ebx, eax
0x1400450e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400450e9  lea     rax, WPP_GLOBAL_Control
0x1400450f0  cmp     rcx, rax
0x1400450f3  jz      short loc_14004511B
0x1400450f5  mov     edx, [rcx+2Ch]
0x1400450f8  test    dl, 2
0x1400450fb  jz      short loc_14004511B
0x1400450fd  cmp     byte ptr [rcx+29h], 4
0x140045101  jb      short loc_14004511B
0x140045103  mov     edx, 0Bh
0x140045108  mov     r9d, ebx
0x14004510b  lea     r8, WPP_aa2c0bb7317938a782fd85b9c42c319a_Traceguids
0x140045112  mov     rcx, [rcx+18h]
0x140045116  call    WPP_SF_d
0x14004511b  mov     eax, ebx
0x14004511d  add     rsp, 40h
0x140045121  pop     r15
0x140045123  pop     r12
0x140045125  pop     rdi
0x140045126  pop     rsi
0x140045127  pop     rbx
0x140045128  retn
0x14004512a  xor     r15b, r15b
0x14004512d  mov     [rsp+68h+var_38], r15b
0x140045132  xor     ebx, ebx
0x140045134  mov     ecx, r12d
0x140045137  sub     ecx, 0EC22h
0x14004513d  jz      loc_140045212
0x140045143  cmp     ecx, 5
0x140045146  jz      short loc_140045156
0x140045148  mov     ebx, 0C0000010h
0x14004514d  mov     [rsp+68h+var_34], ebx
0x140045151  jmp     loc_1400453BE
0x140045156  mov     rcx, cs:WPP_GLOBAL_Control
0x14004515d  cmp     rcx, rdx
0x140045160  jz      short loc_140045184
0x140045162  mov     eax, [rcx+2Ch]
0x140045165  test    al, 2
0x140045167  jz      short loc_140045184
0x140045169  cmp     byte ptr [rcx+29h], 4
0x14004516d  jb      short loc_140045184
0x14004516f  mov     edx, 0Dh
0x140045174  lea     r8, WPP_aa2c0bb7317938a782fd85b9c42c319a_Traceguids
0x14004517b  mov     rcx, [rcx+18h]
0x14004517f  call    WPP_SF_
0x140045184  xor     r9d, r9d; LineNumber
0x140045187  lea     r8d, [r9+1]; Mode
0x14004518b  mov     rdx, rsi; RxContext
0x14004518e  mov     rcx, rdi; Fcb
0x140045191  call    __RxAcquireFcb
0x140045196  mov     ebx, eax
0x140045198  mov     [rsp+68h+var_34], eax
0x14004519c  test    eax, eax
0x14004519e  jnz     loc_1400453BE
0x1400451a4  mov     r15b, 1
0x1400451a7  mov     [rsp+68h+var_38], r15b
0x1400451ac  mov     rax, [rsi+38h]
0x1400451b0  mov     rcx, [rax+188h]
0x1400451b7  cmp     qword ptr [rcx+58h], 0
0x1400451bc  jz      loc_14004530C
0x1400451c2  mov     eax, [rsi+80h]
0x1400451c8  test    al, 2
0x1400451ca  jnz     short loc_140045208
0x1400451cc  xorps   xmm0, xmm0
0x1400451cf  xor     eax, eax
0x1400451d1  movups  xmmword ptr [rsi+0D0h], xmm0
0x1400451d8  movups  xmmword ptr [rsi+0E0h], xmm0
0x1400451df  mov     [rsi+0F0h], rax
0x1400451e6  mov     rax, [rsi+38h]
0x1400451ea  mov     rcx, [rax+188h]
0x1400451f1  mov     rax, [rcx+58h]
0x1400451f5  mov     rcx, rsi
0x1400451f8  call    _guard_dispatch_icall
0x1400451fd  mov     ebx, eax
0x1400451ff  mov     [rsp+68h+var_34], eax
0x140045203  jmp     loc_1400453BE
0x140045208  mov     ebx, 0C0000120h
0x14004520d  jmp     loc_14004514D
0x140045212  mov     rax, [rdi+78h]
0x140045216  cmp     byte ptr [rax+4Dh], 1
0x14004521a  jz      loc_1400452D5
0x140045220  mov     rcx, cs:WPP_GLOBAL_Control
0x140045227  cmp     rcx, rdx
0x14004522a  jz      short loc_14004524E
0x14004522c  mov     eax, [rcx+2Ch]
0x14004522f  test    al, 2
0x140045231  jz      short loc_14004524E
0x140045233  cmp     byte ptr [rcx+29h], 4
0x140045237  jb      short loc_14004524E
0x140045239  mov     edx, 0Ch
0x14004523e  lea     r8, WPP_aa2c0bb7317938a782fd85b9c42c319a_Traceguids
0x140045245  mov     rcx, [rcx+18h]
0x140045249  call    WPP_SF_
0x14004524e  mov     rax, [rdi+130h]
0x140045255  xor     r9d, r9d; LineNumber
0x140045258  mov     rdx, rsi; RxContext
0x14004525b  mov     rcx, rdi; Fcb
0x14004525e  cmp     [rax+8], r9
0x140045262  jz      short loc_1400452B4
0x140045264  lea     r8d, [r9+1]; Mode
0x140045268  call    __RxAcquireFcb
0x14004526d  mov     ebx, eax
0x14004526f  mov     [rsp+68h+var_34], eax
0x140045273  test    eax, eax
0x140045275  js      loc_1400453BE
0x14004527b  mov     r15b, 1
0x14004527e  mov     [rsp+68h+var_38], r15b
0x140045283  xor     r9d, r9d
0x140045286  xor     r8d, r8d
0x140045289  mov     dl, r15b
0x14004528c  mov     rcx, rdi
0x14004528f  call    RxFlushFcbInSystemCacheEx
0x140045294  mov     ebx, eax
0x140045296  mov     [rsp+68h+var_34], eax
0x14004529a  test    eax, eax
0x14004529c  js      loc_1400453BE
0x1400452a2  mov     rcx, [rdi+8]; Resource
0x1400452a6  call    cs:__imp_ExConvertExclusiveToSharedLite
0x1400452ad  nop     dword ptr [rax+rax+00h]
0x1400452b2  jmp     short loc_1400452D5
0x1400452b4  mov     r8d, 2; Mode
0x1400452ba  call    __RxAcquireFcb
0x1400452bf  mov     ebx, eax
0x1400452c1  mov     [rsp+68h+var_34], eax
0x1400452c5  test    eax, eax
0x1400452c7  js      loc_1400453BE
0x1400452cd  mov     r15b, 1
0x1400452d0  mov     [rsp+68h+var_38], r15b
0x1400452d5  mov     rax, [rdi+190h]
0x1400452dc  test    dword ptr [rax+150h], 4000h
0x1400452e6  jz      short loc_1400452FA
0x1400452e8  test    byte ptr [rdi+100h], 1
0x1400452ef  jnz     short loc_1400452FA
0x1400452f1  cmp     dword ptr [rdi+1B0h], 0
0x1400452f8  jz      short loc_140045362
0x1400452fa  mov     rax, [rsi+38h]
0x1400452fe  mov     rcx, [rax+188h]
0x140045305  cmp     qword ptr [rcx+58h], 0
0x14004530a  jnz     short loc_140045316
0x14004530c  mov     ebx, 0C0000002h
0x140045311  jmp     loc_14004514D
0x140045316  mov     eax, [rsi+80h]
0x14004531c  test    al, 2
0x14004531e  jnz     short loc_140045359
0x140045320  xorps   xmm0, xmm0
0x140045323  xor     eax, eax
0x140045325  movups  xmmword ptr [rsi+0D0h], xmm0
0x14004532c  movups  xmmword ptr [rsi+0E0h], xmm0
0x140045333  mov     [rsi+0F0h], rax
0x14004533a  mov     rax, [rsi+38h]
0x14004533e  mov     rcx, [rax+188h]
0x140045345  mov     rax, [rcx+58h]
0x140045349  mov     rcx, rsi
0x14004534c  call    _guard_dispatch_icall
0x140045351  mov     ebx, eax
0x140045353  mov     [rsp+68h+var_34], eax
0x140045357  jmp     short loc_140045362
0x140045359  mov     ebx, 0C0000120h
0x14004535e  mov     [rsp+68h+var_34], ebx
0x140045362  test    ebx, ebx
0x140045364  js      short loc_1400453BE
0x140045366  call    RxAcquirePowerContextLock
0x14004536b  mov     dword ptr [rsp+68h+arg_8], 0
0x140045373  mov     rcx, [rdi+130h]
0x14004537a  add     rcx, 8
0x14004537e  lea     r8, [rsp+68h+arg_8]
0x140045383  mov     edx, 7
0x140045388  call    cs:__imp_MmIsFileSectionActive
0x14004538f  nop     dword ptr [rax+rax+00h]
0x140045394  cmp     dword ptr [rsp+68h+arg_8], 0
0x140045399  jnz     short loc_1400453A2
0x14004539b  and     byte ptr [rdi+11Ah], 7Fh
0x1400453a2  test    byte ptr [rdi+11Ah], 4
0x1400453a9  jz      short loc_1400453B8
0x1400453ab  mov     r8b, 2
0x1400453ae  mov     dl, 4
0x1400453b0  mov     rcx, rdi
0x1400453b3  call    RxUpdateFcbPowerState
0x1400453b8  call    RxReleasePowerContextLock
0x1400453bd  nop
0x1400453be  test    r15b, r15b
0x1400453c1  jz      short loc_1400453CE
0x1400453c3  mov     rdx, rdi; MrxFcb
0x1400453c6  mov     rcx, rsi; RxContext
0x1400453c9  call    __RxReleaseFcb
0x1400453ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400453d5  lea     rax, WPP_GLOBAL_Control
0x1400453dc  cmp     rcx, rax
0x1400453df  jz      loc_14004511B
0x1400453e5  mov     eax, [rcx+2Ch]
0x1400453e8  test    al, 2
0x1400453ea  jz      loc_14004511B
0x1400453f0  cmp     byte ptr [rcx+29h], 4
0x1400453f4  jb      loc_14004511B
0x1400453fa  mov     edx, 0Eh
0x1400453ff  jmp     loc_140045108
0x14007ba73  push    rbp
0x14007ba75  sub     rsp, 30h
0x14007ba79  mov     rbp, rdx
0x14007ba7c  movzx   eax, cl
0x14007ba7f  test    cl, cl
0x14007ba81  jz      short loc_14007BA95
0x14007ba83  mov     edx, 0D9h
0x14007ba88  lea     rcx, aRxcommonflushb; "RxCommonFlushBuffers"
0x14007ba8f  call    RxLogAbnormalTermination
0x14007ba94  nop
0x14007ba95  cmp     byte ptr [rbp+30h], 0
0x14007ba99  jz      short loc_14007BAAC
0x14007ba9b  mov     rdx, [rbp+80h]; MrxFcb
0x14007baa2  mov     rcx, [rbp+70h]; RxContext
0x14007baa6  call    __RxReleaseFcb
0x14007baab  nop
0x14007baac  add     rsp, 30h
0x14007bab0  pop     rbp
0x14007bab1  retn
```
