# RxAcquireFileForNtCreateSection

- ea: `0x140077390`
- end: `0x140077659`
- name: `RxAcquireFileForNtCreateSection`
- size: `713`
- prototype: `void __stdcall(PFILE_OBJECT FileObject)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x140003410`
- `0x1400037e0`
- `0x140008f60`
- `0x140010d70`
- `0x140017a38`
- `0x14001e510`
- `0x14001e578`
- `0x14004bed8`
- `0x140057660`
- `0x140077390`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x14007752a`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14007752a`

## pseudocode

```c
void __stdcall RxAcquireFileForNtCreateSection(PFILE_OBJECT FileObject)
{
  PVPB Vpb; // rsi
  __int64 v3; // rbx
  enum _RX_BLOCK_CONDITION *RxContext; // rax
  struct _RX_CONTEXT *v5; // rdi
  unsigned int v6; // edi
  BOOLEAN v7; // r15
  unsigned __int8 v8; // di
  int DirectAccessExtentsFsctl; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  const CHAR *FileName; // [rsp+20h] [rbp-48h]
  ULONG v13; // [rsp+28h] [rbp-40h]
  UNICODE_STRING String1; // [rsp+40h] [rbp-28h] BYREF

  Vpb = FileObject->Vpb;
  *(_QWORD *)&String1.Length = 7733364;
  String1.Buffer = L"\\VSMB-{dcc079ae-60ba-4d07-847c-3493609c0870}\\SharedMemory$";
  if ( Vpb )
  {
    v3 = *(_QWORD *)&Vpb->SerialNumber;
    if ( (*(_WORD *)v3 != 0xEC23 || !*(_QWORD *)Vpb->VolumeLabel) && *(_WORD *)v3 == 0xEC22 )
    {
LABEL_5:
      if ( *(_QWORD *)(v3 + 128) )
      {
        RxContext = (enum _RX_BLOCK_CONDITION *)RxCreateRxContext(
                                                  0,
                                                  *(PRDBSS_DEVICE_OBJECT *)(*(_QWORD *)(*(_QWORD *)(v3 + 120) + 32LL)
                                                                          + 48LL),
                                                  2u);
        v5 = (struct _RX_CONTEXT *)RxContext;
        if ( !RxContext )
        {
          v6 = -1073741670;
LABEL_44:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_dq(WPP_GLOBAL_Control->AttachedDevice, 30, &WPP_16f2bee2656c381c8186d78b34bda825_Traceguids, v6, v3);
          }
          return;
        }
        if ( (unsigned __int8)RxWaitForStableLViewOnFcbAndAcquireRundown(RxContext, (PMRX_FCB)v3, 0, 0, 0) == 1 )
          RxRemoveLViewFromRxContextNoRelease(v5);
        RxDereferenceAndDeleteRxContext_Real(v5);
      }
      v6 = _RxAcquireFcb((PFCB)v3, 0, 1u, 0, FileName, v13);
      if ( v6 )
        goto LABEL_44;
      *(_DWORD *)(v3 + 156) |= 0x40u;
      if ( (HIDWORD(FileObject->FsContext) & 0x44) != 0 )
        _InterlockedOr8((volatile signed __int8 *)(v3 + 256), 4u);
      if ( LODWORD(FileObject->FsContext) != 1 )
      {
        v6 = 294;
        goto LABEL_44;
      }
      if ( (*(_DWORD *)(*(_QWORD *)(v3 + 400) + 336LL) & 0x4000) == 0 )
      {
        if ( HIBYTE(Vpb->VolumeLabel[21]) || (v6 = 298, LOBYTE(Vpb->VolumeLabel[23])) )
          v6 = 299;
        goto LABEL_44;
      }
      v7 = RtlEqualUnicodeString(&String1, *(PCUNICODE_STRING *)(*(_QWORD *)(v3 + 120) + 88LL), 0);
      if ( v7 )
      {
        v8 = 0;
      }
      else
      {
        v8 = 1;
        if ( HIBYTE(Vpb->VolumeLabel[21]) || LOBYTE(Vpb->VolumeLabel[23]) )
        {
LABEL_40:
          v6 = (v8 ^ 1) + 298;
          goto LABEL_44;
        }
      }
      if ( (*(_DWORD *)(*(_QWORD *)(v3 + 120) + 56LL) & 0x400) == 0 )
      {
        DirectAccessExtentsFsctl = RxpQueryDirectAccessExtentsFsctl((__int64)Vpb, HIDWORD(FileObject->FsContext), v8);
        if ( DirectAccessExtentsFsctl >= 0 )
        {
          if ( v8 )
          {
            *((_DWORD *)FileObject->FsContext2 + 2) |= 4u;
            *(_DWORD *)(v3 + 736) |= 1u;
          }
          if ( v7 )
          {
            *((_DWORD *)FileObject->FsContext2 + 2) |= 2u;
            *(_DWORD *)(v3 + 736) |= 2u;
          }
          *((_DWORD *)FileObject->FsContext2 + 1) = 12;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_Dqd(WPP_GLOBAL_Control->AttachedDevice, v10, v11, (unsigned int)DirectAccessExtentsFsctl, v3, v8);
        }
      }
      goto LABEL_40;
    }
  }
  else
  {
    v3 = 0;
  }
  if ( LODWORD(FileObject->FsContext) != 1 )
    goto LABEL_5;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_DqqqH(WPP_GLOBAL_Control->AttachedDevice);
  }
}

```

## disassembly

```asm
0x140077390  mov     [rsp+arg_10], rbx
0x140077395  push    rbp
0x140077396  push    rsi
0x140077397  push    r14
0x140077399  sub     rsp, 50h
0x14007739d  mov     rsi, [rcx+10h]
0x1400773a1  lea     rax, aVsmbDcc079ae60; "\\VSMB-{dcc079ae-60ba-4d07-847c-3493609"...
0x1400773a8  mov     qword ptr [rsp+68h+String1.Length], 760074h
0x1400773b1  mov     rbp, rcx
0x1400773b4  mov     [rsp+68h+String1.Buffer], rax
0x1400773b9  test    rsi, rsi
0x1400773bc  jz      short loc_140077433
0x1400773be  mov     rbx, [rsi+18h]
0x1400773c2  mov     ecx, 0EC23h
0x1400773c7  mov     rdx, [rsi+20h]
0x1400773cb  movzx   eax, word ptr [rbx]
0x1400773ce  cmp     ax, cx
0x1400773d1  jnz     short loc_1400773DF
0x1400773d3  test    rdx, rdx
0x1400773d6  jz      short loc_1400773DF
0x1400773d8  mov     ecx, 0EC28h
0x1400773dd  jmp     short loc_14007743C
0x1400773df  mov     r8d, 0EC22h
0x1400773e5  movzx   ecx, ax
0x1400773e8  cmp     ax, r8w
0x1400773ec  jnz     short loc_14007743C
0x1400773ee  cmp     qword ptr [rbx+80h], 0
0x1400773f6  lea     r14, WPP_GLOBAL_Control
0x1400773fd  mov     [rsp+68h+arg_0], rdi
0x140077402  jz      loc_1400774BB
0x140077408  mov     rax, [rbx+78h]
0x14007740c  mov     r8d, 2; InitialContextFlags
0x140077412  xor     ecx, ecx; Irp
0x140077414  mov     rdx, [rax+20h]
0x140077418  mov     rdx, [rdx+30h]; RxDeviceObject
0x14007741c  call    RxCreateRxContext
0x140077421  mov     rdi, rax
0x140077424  test    rax, rax
0x140077427  jnz     short loc_14007748D
0x140077429  mov     edi, 0C000009Ah
0x14007742e  jmp     loc_140077608
0x140077433  xor     ebx, ebx
0x140077435  mov     ecx, 0EC20h
0x14007743a  xor     edx, edx
0x14007743c  cmp     dword ptr [rbp+18h], 1
0x140077440  jnz     short loc_1400773EE
0x140077442  mov     r8, cs:WPP_GLOBAL_Control
0x140077449  lea     r14, WPP_GLOBAL_Control
0x140077450  cmp     r8, r14
0x140077453  jz      short loc_140077483
0x140077455  test    dword ptr [r8+2Ch], 100h
0x14007745d  jz      short loc_140077483
0x14007745f  cmp     byte ptr [r8+29h], 2
0x140077464  jb      short loc_140077483
0x140077466  mov     [rsp+68h+var_30], cx
0x14007746b  mov     rcx, [r8+18h]
0x14007746f  mov     [rsp+68h+var_38], rbx
0x140077474  mov     [rsp+68h+var_40], rdx
0x140077479  mov     [rsp+68h+FileName], rsi
0x14007747e  call    WPP_SF_DqqqH
0x140077483  mov     eax, 0C0000020h
0x140077488  jmp     loc_140077647
0x14007748d  xor     r9d, r9d
0x140077490  mov     [rsp+68h+FileName], 0; __int64
0x140077499  xor     r8d, r8d
0x14007749c  mov     rdx, rbx; MrxFcb
0x14007749f  mov     rcx, rdi; Condition
0x1400774a2  call    RxWaitForStableLViewOnFcbAndAcquireRundown
0x1400774a7  cmp     al, 1
0x1400774a9  jnz     short loc_1400774B3
0x1400774ab  mov     rcx, rdi
0x1400774ae  call    RxRemoveLViewFromRxContextNoRelease
0x1400774b3  mov     rcx, rdi; RxContext
0x1400774b6  call    RxDereferenceAndDeleteRxContext_Real
0x1400774bb  xor     r9d, r9d; LineNumber
0x1400774be  xor     edx, edx; RxContext
0x1400774c0  mov     r8d, 1; Mode
0x1400774c6  mov     rcx, rbx; Fcb
0x1400774c9  call    __RxAcquireFcb
0x1400774ce  mov     edi, eax
0x1400774d0  test    eax, eax
0x1400774d2  jnz     loc_140077608
0x1400774d8  or      dword ptr [rbx+9Ch], 40h
0x1400774df  mov     eax, [rbp+1Ch]
0x1400774e2  test    al, 44h
0x1400774e4  jz      short loc_1400774EE
0x1400774e6  lock or byte ptr [rbx+100h], 4
0x1400774ee  cmp     dword ptr [rbp+18h], 1
0x1400774f2  jz      short loc_1400774FE
0x1400774f4  mov     edi, 126h
0x1400774f9  jmp     loc_140077608
0x1400774fe  mov     rax, [rbx+190h]
0x140077505  test    dword ptr [rax+150h], 4000h
0x14007750f  jz      loc_1400775F2
0x140077515  mov     rdx, [rbx+78h]
0x140077519  lea     rcx, [rsp+68h+String1]; String1
0x14007751e  xor     r8d, r8d; CaseInSensitive
0x140077521  mov     [rsp+68h+arg_8], r15
0x140077526  mov     rdx, [rdx+58h]; String2
0x14007752a  call    cs:__imp_RtlEqualUnicodeString
0x140077531  nop     dword ptr [rax+rax+00h]
0x140077536  movzx   r15d, al
0x14007753a  test    al, al
0x14007753c  jnz     short loc_140077554
0x14007753e  mov     dil, 1
0x140077541  cmp     [rsi+4Bh], al
0x140077544  jnz     loc_1400775DE
0x14007754a  cmp     [rsi+4Eh], al
0x14007754d  jz      short loc_140077557
0x14007754f  jmp     loc_1400775DE
0x140077554  xor     dil, dil
0x140077557  mov     rax, [rbx+78h]
0x14007755b  test    dword ptr [rax+38h], 400h
0x140077562  jnz     short loc_1400775DE
0x140077564  mov     edx, [rbp+1Ch]
0x140077567  movzx   r8d, dil
0x14007756b  mov     rcx, rsi
0x14007756e  call    RxpQueryDirectAccessExtentsFsctl
0x140077573  mov     r9d, eax
0x140077576  test    eax, eax
0x140077578  js      short loc_1400775AD
0x14007757a  test    dil, dil
0x14007757d  jz      short loc_14007758E
0x14007757f  mov     rcx, [rbp+20h]
0x140077583  or      dword ptr [rcx+8], 4
0x140077587  or      dword ptr [rbx+2E0h], 1
0x14007758e  test    r15b, r15b
0x140077591  jz      short loc_1400775A2
0x140077593  mov     rax, [rbp+20h]
0x140077597  or      dword ptr [rax+8], 2
0x14007759b  or      dword ptr [rbx+2E0h], 2
0x1400775a2  mov     rax, [rbp+20h]
0x1400775a6  mov     dword ptr [rax+4], 0Ch
0x1400775ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400775b4  cmp     rcx, r14
0x1400775b7  jz      short loc_1400775DE
0x1400775b9  test    dword ptr [rcx+2Ch], 100h
0x1400775c0  jz      short loc_1400775DE
0x1400775c2  cmp     byte ptr [rcx+29h], 2
0x1400775c6  jb      short loc_1400775DE
0x1400775c8  mov     rcx, [rcx+18h]
0x1400775cc  movzx   eax, dil
0x1400775d0  mov     dword ptr [rsp+68h+var_40], eax
0x1400775d4  mov     [rsp+68h+FileName], rbx
0x1400775d9  call    WPP_SF_Dqd
0x1400775de  mov     r15, [rsp+68h+arg_8]
0x1400775e3  movzx   edi, dil
0x1400775e7  xor     edi, 1
0x1400775ea  add     edi, 12Ah
0x1400775f0  jmp     short loc_140077608
0x1400775f2  cmp     byte ptr [rsi+4Bh], 0
0x1400775f6  jnz     short loc_140077603
0x1400775f8  cmp     byte ptr [rsi+4Eh], 0
0x1400775fc  mov     edi, 12Ah
0x140077601  jz      short loc_140077608
0x140077603  mov     edi, 12Bh
0x140077608  mov     rcx, cs:WPP_GLOBAL_Control
0x14007760f  cmp     rcx, r14
0x140077612  jz      short loc_140077640
0x140077614  test    dword ptr [rcx+2Ch], 100h
0x14007761b  jz      short loc_140077640
0x14007761d  cmp     byte ptr [rcx+29h], 2
0x140077621  jb      short loc_140077640
0x140077623  mov     rcx, [rcx+18h]
0x140077627  lea     r8, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids
0x14007762e  mov     edx, 1Eh
0x140077633  mov     [rsp+68h+FileName], rbx
0x140077638  mov     r9d, edi
0x14007763b  call    WPP_SF_dq
0x140077640  mov     eax, edi
0x140077642  mov     rdi, [rsp+68h+arg_0]
0x140077647  mov     rbx, [rsp+68h+arg_10]
0x14007764f  add     rsp, 50h
0x140077653  pop     r14
0x140077655  pop     rsi
0x140077656  pop     rbp
0x140077657  retn
```
