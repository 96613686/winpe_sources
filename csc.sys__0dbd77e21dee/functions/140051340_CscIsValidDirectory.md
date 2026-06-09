# CscIsValidDirectory

- ea: `0x140051340`
- end: `0x14005170a`
- name: `CscIsValidDirectory`
- size: `970`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x14000a4f0`
- `0x14000a634`
- `0x14000f8b0`
- `0x14001328c`
- `0x1400169d4`
- `0x140016a04`
- `0x1400190ec`
- `0x14001a4f4`
- `0x14001f854`
- `0x14002f010`
- `0x14002f440`
- `0x140051340`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400514cf`
- `ntoskrnl!ExAllocatePool2` at `0x1400514cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051658`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051658`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400514f2`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140051506`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400514f2`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140051506`

## pseudocode

```c
__int64 __fastcall CscIsValidDirectory(__int64 a1, const UNICODE_STRING *a2)
{
  __int64 v2; // r15
  int v5; // r9d
  int v6; // esi
  __int64 v7; // r14
  __int64 v8; // rdi
  bool v9; // bl
  unsigned int *v10; // r14
  unsigned int InformationEntry; // ebx
  char v12; // di
  __int64 v13; // r9
  int v14; // eax
  int v16; // [rsp+20h] [rbp-B9h]
  __int64 v17; // [rsp+40h] [rbp-99h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+48h] [rbp-91h] BYREF
  __int64 v19; // [rsp+58h] [rbp-81h]
  _OWORD v20[3]; // [rsp+60h] [rbp-79h] BYREF
  __int64 v21; // [rsp+90h] [rbp-49h]
  _DWORD v22[20]; // [rsp+A0h] [rbp-39h] BYREF

  v2 = 0;
  v17 = 0;
  v21 = 0;
  memset(v20, 0, sizeof(v20));
  memset(v22, 0, sizeof(v22));
  v6 = 0;
  v7 = *(_QWORD *)(a1 + 648);
  v8 = *(_QWORD *)(a1 + 656);
  v9 = *(_QWORD *)(a1 + 80) != (_QWORD)CscDeviceObject;
  v19 = v7;
  Destination = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
  {
    LOBYTE(v5) = v9 ? 89 : 78;
    WPP_SF_cZ(
      WPP_GLOBAL_Control->AttachedDevice,
      45,
      (unsigned int)WPP_f1d0093ed16337749994f41f70b429cb_Traceguids,
      v5,
      (__int64)a2);
  }
  if ( !v9 )
    goto LABEL_16;
  v10 = (unsigned int *)(a1 + 176);
  InformationEntry = 0;
  if ( (*(_DWORD *)(v8 + 56) & 0x50) != 0
    || (unsigned __int8)CscTransitnOKToGoOffline(*v10)
    || *v10 == -1073741766
    || *v10 == -1073741772 )
  {
    v12 = 1;
  }
  else
  {
    v12 = 0;
    InformationEntry = *v10;
    v6 = 5101;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
  {
    LOBYTE(v16) = v12 != 0 ? 89 : 78;
    WPP_SF_Dc(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_f1d0093ed16337749994f41f70b429cb_Traceguids, *v10, v16);
  }
  if ( v12 )
  {
    v7 = v19;
LABEL_16:
    if ( a2->Length )
    {
      Destination.MaximumLength = **(_WORD **)(v7 + 88) + a2->Length + 2;
      Destination.Buffer = (PWSTR)ExAllocatePool2(258, Destination.MaximumLength, 1917088579);
      if ( Destination.Buffer )
      {
        RtlAppendUnicodeStringToString(&Destination, *(PCUNICODE_STRING *)(v7 + 88));
        RtlAppendUnicodeStringToString(&Destination, a2);
        if ( (unsigned int)CscStoreFindEntry(&v17, 0, &Destination, v13) )
        {
          v14 = *(_DWORD *)(a1 + 176);
          v2 = v17;
          v6 = 5170;
          if ( v14 >= 0 )
            v14 = -1073741634;
          InformationEntry = v14;
        }
        else
        {
          v2 = v17;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_f1d0093ed16337749994f41f70b429cb_Traceguids, v17);
          }
          InformationEntry = CscStoreQueryInformationEntryEx(v2, 0, (unsigned int)v22, (unsigned int)v20, 0, 0, 0);
          if ( InformationEntry )
          {
            v6 = 5157;
          }
          else if ( (v21 & 0x10) == 0 || (v22[0] & 0x10) != 0 )
          {
            InformationEntry = -1073741634;
            v6 = 5148;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
            {
              WPP_SF_Dd(
                WPP_GLOBAL_Control->AttachedDevice,
                49,
                WPP_f1d0093ed16337749994f41f70b429cb_Traceguids,
                v21,
                v22[0]);
            }
          }
          else
          {
            InformationEntry = 0;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_f1d0093ed16337749994f41f70b429cb_Traceguids);
            }
          }
        }
      }
      else
      {
        InformationEntry = -1073741801;
        v6 = 5176;
      }
    }
    else
    {
      v6 = 5185;
      InformationEntry = -1073741811;
    }
  }
  if ( Destination.Buffer )
  {
    ExFreePoolWithTag(Destination.Buffer, 0);
    Destination.Buffer = 0;
  }
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_f1d0093ed16337749994f41f70b429cb_Traceguids, v2);
    CscStoreDereferenceEntry(&v17);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      51,
      WPP_f1d0093ed16337749994f41f70b429cb_Traceguids,
      InformationEntry,
      v6);
  return InformationEntry;
}

```

## disassembly

```asm
0x140051340  mov     [rsp-8+arg_10], rbx
0x140051345  push    rbp
0x140051346  push    rsi
0x140051347  push    rdi
0x140051348  push    r12
0x14005134a  push    r13
0x14005134c  push    r14
0x14005134e  push    r15
0x140051350  lea     rbp, [rsp-27h]
0x140051355  sub     rsp, 100h
0x14005135c  mov     rax, cs:__security_cookie
0x140051363  xor     rax, rsp
0x140051366  mov     [rbp+57h+var_40], rax
0x14005136a  xorps   xmm0, xmm0
0x14005136d  xor     r15d, r15d
0x140051370  mov     r12, rdx
0x140051373  mov     [rsp+130h+var_F0], r15
0x140051378  mov     r13, rcx
0x14005137b  xor     eax, eax
0x14005137d  xor     edx, edx; Val
0x14005137f  mov     [rbp+57h+var_A0], rax
0x140051383  lea     r8d, [r15+50h]; Size
0x140051387  lea     rcx, [rbp+57h+var_90]; void *
0x14005138b  movups  [rbp+57h+var_D0], xmm0
0x14005138f  movups  [rbp+57h+var_C0], xmm0
0x140051393  movups  [rbp+57h+var_B0], xmm0
0x140051397  call    memset
0x14005139c  mov     rax, cs:CscDeviceObject
0x1400513a3  xor     esi, esi
0x1400513a5  cmp     [r13+50h], rax
0x1400513a9  xorps   xmm0, xmm0
0x1400513ac  mov     r14, [r13+288h]
0x1400513b3  mov     rdi, [r13+290h]
0x1400513ba  setnz   bl
0x1400513bd  mov     [rsp+130h+var_D8], r14
0x1400513c2  movups  xmmword ptr [rsp+130h+Destination.Length], xmm0
0x1400513c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400513ce  lea     rax, WPP_GLOBAL_Control
0x1400513d5  cmp     rcx, rax
0x1400513d8  jz      short loc_140051408
0x1400513da  mov     eax, [rcx+2Ch]
0x1400513dd  test    al, 20h
0x1400513df  jz      short loc_140051408
0x1400513e1  mov     rcx, [rcx+18h]
0x1400513e5  lea     edx, [rsi+2Dh]
0x1400513e8  mov     al, bl
0x1400513ea  mov     [rsp+130h+var_110], r12
0x1400513ef  neg     al
0x1400513f1  lea     r8, WPP_f1d0093ed16337749994f41f70b429cb_Traceguids
0x1400513f8  sbb     r9b, r9b
0x1400513fb  and     r9b, 0Bh
0x1400513ff  add     r9b, 4Eh ; 'N'
0x140051403  call    WPP_SF_cZ
0x140051408  test    bl, bl
0x14005140a  jz      loc_1400514A1
0x140051410  mov     eax, [rdi+38h]
0x140051413  lea     r14, [r13+0B0h]
0x14005141a  xor     ebx, ebx
0x14005141c  test    al, 50h
0x14005141e  jnz     short loc_140051449
0x140051420  mov     ecx, [r14]
0x140051423  call    CscTransitnOKToGoOffline
0x140051428  test    al, al
0x14005142a  jnz     short loc_140051449
0x14005142c  mov     eax, [r14]
0x14005142f  cmp     eax, 0C000003Ah
0x140051434  jz      short loc_140051449
0x140051436  cmp     eax, 0C0000034h
0x14005143b  jz      short loc_140051449
0x14005143d  xor     dil, dil
0x140051440  mov     ebx, eax
0x140051442  mov     esi, 13EDh
0x140051447  jmp     short loc_14005144C
0x140051449  mov     dil, 1
0x14005144c  mov     rcx, cs:WPP_GLOBAL_Control
0x140051453  lea     rax, WPP_GLOBAL_Control
0x14005145a  cmp     rcx, rax
0x14005145d  jz      short loc_140051493
0x14005145f  mov     eax, [rcx+2Ch]
0x140051462  test    al, 20h
0x140051464  jz      short loc_140051493
0x140051466  mov     r9d, [r14]
0x140051469  mov     al, dil
0x14005146c  mov     rcx, [rcx+18h]
0x140051470  neg     al
0x140051472  mov     edx, 2Eh ; '.'
0x140051477  sbb     r8b, r8b
0x14005147a  and     r8b, 0Bh
0x14005147e  add     r8b, 4Eh ; 'N'
0x140051482  mov     byte ptr [rsp+130h+var_110], r8b
0x140051487  lea     r8, WPP_f1d0093ed16337749994f41f70b429cb_Traceguids
0x14005148e  call    WPP_SF_Dc
0x140051493  test    dil, dil
0x140051496  jz      loc_14005160C
0x14005149c  mov     r14, [rsp+130h+var_D8]
0x1400514a1  movzx   ecx, word ptr [r12]
0x1400514a6  xor     edi, edi
0x1400514a8  test    cx, cx
0x1400514ab  jz      loc_140051642
0x1400514b1  mov     rax, [r14+58h]
0x1400514b5  add     cx, 2
0x1400514b9  mov     r8d, 72447343h
0x1400514bf  add     cx, [rax]
0x1400514c2  movzx   edx, cx
0x1400514c5  mov     ecx, 102h
0x1400514ca  mov     [rsp+130h+Destination.MaximumLength], dx
0x1400514cf  call    cs:__imp_ExAllocatePool2
0x1400514d6  nop     dword ptr [rax+rax+00h]
0x1400514db  mov     [rsp+130h+Destination.Buffer], rax
0x1400514e0  test    rax, rax
0x1400514e3  jz      loc_140051636
0x1400514e9  mov     rdx, [r14+58h]; Source
0x1400514ed  lea     rcx, [rsp+130h+Destination]; Destination
0x1400514f2  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400514f9  nop     dword ptr [rax+rax+00h]
0x1400514fe  mov     rdx, r12; Source
0x140051501  lea     rcx, [rsp+130h+Destination]; Destination
0x140051506  call    cs:__imp_RtlAppendUnicodeStringToString
0x14005150d  nop     dword ptr [rax+rax+00h]
0x140051512  lea     r8, [rsp+130h+Destination]
0x140051517  xor     edx, edx
0x140051519  lea     rcx, [rsp+130h+var_F0]
0x14005151e  call    CscStoreFindEntry
0x140051523  test    eax, eax
0x140051525  jnz     loc_140051617
0x14005152b  mov     rcx, cs:WPP_GLOBAL_Control
0x140051532  lea     r14, WPP_GLOBAL_Control
0x140051539  mov     r15, [rsp+130h+var_F0]
0x14005153e  cmp     rcx, r14
0x140051541  jz      short loc_140051560
0x140051543  mov     eax, [rcx+2Ch]
0x140051546  test    al, 40h
0x140051548  jz      short loc_140051560
0x14005154a  mov     rcx, [rcx+18h]
0x14005154e  lea     edx, [rdi+2Fh]
0x140051551  mov     r9, r15
0x140051554  lea     r8, WPP_f1d0093ed16337749994f41f70b429cb_Traceguids
0x14005155b  call    WPP_SF_q
0x140051560  mov     [rsp+130h+var_100], rdi
0x140051565  lea     r9, [rbp+57h+var_D0]
0x140051569  mov     [rsp+130h+var_108], rdi
0x14005156e  lea     r8, [rbp+57h+var_90]
0x140051572  xor     edx, edx
0x140051574  mov     [rsp+130h+var_110], rdi
0x140051579  mov     rcx, r15
0x14005157c  call    CscStoreQueryInformationEntryEx
0x140051581  mov     ebx, eax
0x140051583  test    eax, eax
0x140051585  jnz     loc_140051610
0x14005158b  mov     r9, [rbp+57h+var_A0]
0x14005158f  mov     r8d, [rbp+57h+var_90]
0x140051593  test    r9b, 10h
0x140051597  jz      short loc_1400515D3
0x140051599  test    r8b, 10h
0x14005159d  jnz     short loc_1400515D3
0x14005159f  mov     ebx, edi
0x1400515a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400515a8  cmp     rcx, r14
0x1400515ab  jz      loc_14005164C
0x1400515b1  mov     eax, [rcx+2Ch]
0x1400515b4  test    al, 40h
0x1400515b6  jz      loc_14005164C
0x1400515bc  mov     rcx, [rcx+18h]
0x1400515c0  lea     r8, WPP_f1d0093ed16337749994f41f70b429cb_Traceguids
0x1400515c7  mov     edx, 30h ; '0'
0x1400515cc  call    WPP_SF_
0x1400515d1  jmp     short loc_14005164C
0x1400515d3  mov     ebx, 0C00000BEh
0x1400515d8  mov     esi, 141Ch
0x1400515dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400515e4  cmp     rcx, r14
0x1400515e7  jz      short loc_14005164C
0x1400515e9  mov     eax, [rcx+2Ch]
0x1400515ec  test    al, 40h
0x1400515ee  jz      short loc_14005164C
0x1400515f0  mov     rcx, [rcx+18h]
0x1400515f4  mov     edx, 31h ; '1'
0x1400515f9  mov     dword ptr [rsp+130h+var_110], r8d
0x1400515fe  lea     r8, WPP_f1d0093ed16337749994f41f70b429cb_Traceguids
0x140051605  call    WPP_SF_Dd
0x14005160a  jmp     short loc_14005164C
0x14005160c  xor     edi, edi
0x14005160e  jmp     short loc_14005164C
0x140051610  mov     esi, 1425h
0x140051615  jmp     short loc_14005164C
0x140051617  mov     eax, [r13+0B0h]
0x14005161e  mov     ebx, 0C00000BEh
0x140051623  mov     r15, [rsp+130h+var_F0]
0x140051628  test    eax, eax
0x14005162a  mov     esi, 1432h
0x14005162f  cmovns  eax, ebx
0x140051632  mov     ebx, eax
0x140051634  jmp     short loc_14005164C
0x140051636  mov     ebx, 0C0000017h
0x14005163b  mov     esi, 1438h
0x140051640  jmp     short loc_14005164C
0x140051642  mov     esi, 1441h
0x140051647  mov     ebx, 0C000000Dh
0x14005164c  mov     rcx, [rsp+130h+Destination.Buffer]; P
0x140051651  test    rcx, rcx
0x140051654  jz      short loc_140051669
0x140051656  xor     edx, edx; Tag
0x140051658  call    cs:__imp_ExFreePoolWithTag
0x14005165f  nop     dword ptr [rax+rax+00h]
0x140051664  mov     [rsp+130h+Destination.Buffer], rdi
0x140051669  test    r15, r15
0x14005166c  jz      short loc_1400516AA
0x14005166e  mov     rcx, cs:WPP_GLOBAL_Control
0x140051675  lea     rax, WPP_GLOBAL_Control
0x14005167c  cmp     rcx, rax
0x14005167f  jz      short loc_1400516A0
0x140051681  mov     eax, [rcx+2Ch]
0x140051684  test    al, 40h
0x140051686  jz      short loc_1400516A0
0x140051688  mov     rcx, [rcx+18h]
0x14005168c  lea     r8, WPP_f1d0093ed16337749994f41f70b429cb_Traceguids
0x140051693  mov     edx, 32h ; '2'
0x140051698  mov     r9, r15
0x14005169b  call    WPP_SF_q
0x1400516a0  lea     rcx, [rsp+130h+var_F0]
0x1400516a5  call    CscStoreDereferenceEntry
0x1400516aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400516b1  lea     rax, WPP_GLOBAL_Control
0x1400516b8  cmp     rcx, rax
0x1400516bb  jz      short loc_1400516E0
0x1400516bd  mov     eax, [rcx+2Ch]
0x1400516c0  test    al, 20h
0x1400516c2  jz      short loc_1400516E0
0x1400516c4  mov     rcx, [rcx+18h]
0x1400516c8  lea     r8, WPP_f1d0093ed16337749994f41f70b429cb_Traceguids
0x1400516cf  mov     edx, 33h ; '3'
0x1400516d4  mov     dword ptr [rsp+130h+var_110], esi
0x1400516d8  mov     r9d, ebx
0x1400516db  call    WPP_SF_Dd
0x1400516e0  mov     eax, ebx
0x1400516e2  mov     rcx, [rbp+57h+var_40]
0x1400516e6  xor     rcx, rsp; StackCookie
0x1400516e9  call    __security_check_cookie
0x1400516ee  mov     rbx, [rsp+130h+arg_10]
0x1400516f6  add     rsp, 100h
0x1400516fd  pop     r15
0x1400516ff  pop     r14
0x140051701  pop     r13
0x140051703  pop     r12
0x140051705  pop     rdi
0x140051706  pop     rsi
0x140051707  pop     rbp
0x140051708  retn
```
