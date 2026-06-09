# Smb2ComputeOutgoingSignatureSimple

- ea: `0x1400334b4`
- end: `0x1400336a3`
- name: `Smb2ComputeOutgoingSignatureSimple`
- size: `495`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14000e220`

## callees

- `0x14000b760`
- `0x140017c70`
- `0x140029764`
- `0x1400297fc`
- `0x140029840`
- `0x1400334b4`
- `0x140037120`

## import_xrefs

- `ksecdd!BCryptHashData` at `0x14003359c`
- `ksecdd!BCryptHashData` at `0x14003359c`
- `ksecdd!BCryptFinishHash` at `0x1400335eb`
- `ksecdd!BCryptFinishHash` at `0x1400335eb`
- `mrxsmb!SmbCseDestroyHashHandle` at `0x140033639`
- `mrxsmb!SmbCseDestroyHashHandle` at `0x140033639`

## pseudocode

```c
__int64 __fastcall Smb2ComputeOutgoingSignatureSimple(__int64 a1, __int64 a2, ULONG a3)
{
  __int64 v6; // rdx
  NTSTATUS v7; // edi
  int HashHandleForOutgoingSignature; // eax
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  UCHAR pbOutput[16]; // [rsp+30h] [rbp-48h] BYREF
  __int128 v13; // [rsp+40h] [rbp-38h]

  *(_OWORD *)pbOutput = 0;
  v13 = 0;
  if ( (unsigned __int8)Smb2EndpointWillEncrypt() )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        11,
        WPP_60db1590be613abca80435fd5891bee8_Traceguids,
        *(_QWORD *)(a1 + 56));
    }
    return 0;
  }
  HashHandleForOutgoingSignature = Smb2GenerateHashHandleForOutgoingSignature(a1, v6);
  v7 = HashHandleForOutgoingSignature;
  if ( HashHandleForOutgoingSignature < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        12,
        WPP_60db1590be613abca80435fd5891bee8_Traceguids,
        *(_QWORD *)(a1 + 56),
        HashHandleForOutgoingSignature);
    }
    goto LABEL_23;
  }
  v7 = BCryptHashData(*(BCRYPT_HASH_HANDLE *)(a1 + 792), (PUCHAR)a2, a3, 0);
  if ( v7 >= 0 )
  {
    v7 = BCryptFinishHash(*(BCRYPT_HASH_HANDLE *)(a1 + 792), pbOutput, *(_DWORD *)(a1 + 800), 0);
    if ( v7 >= 0 )
    {
      *(_OWORD *)(a2 + 48) = *(_OWORD *)pbOutput;
      return (unsigned int)v7;
    }
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_23;
    }
    v10 = 14;
    goto LABEL_22;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    v10 = 13;
LABEL_22:
    WPP_SF_q(v9->AttachedDevice, v10, WPP_60db1590be613abca80435fd5891bee8_Traceguids, *(_QWORD *)(a1 + 56));
  }
LABEL_23:
  SmbCseDestroyHashHandle(a1);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_60db1590be613abca80435fd5891bee8_Traceguids, (unsigned int)v7);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400334b4  mov     [rsp+arg_18], rbx
0x1400334b9  push    rsi
0x1400334ba  push    rdi
0x1400334bb  push    r14
0x1400334bd  sub     rsp, 60h
0x1400334c1  mov     rax, cs:__security_cookie
0x1400334c8  xor     rax, rsp
0x1400334cb  mov     [rsp+78h+var_28], rax
0x1400334d0  xorps   xmm0, xmm0
0x1400334d3  mov     r14d, r8d
0x1400334d6  movups  xmmword ptr [rsp+78h+pbOutput], xmm0
0x1400334db  mov     rbx, rdx
0x1400334de  mov     rsi, rcx
0x1400334e1  movups  [rsp+78h+var_38], xmm0
0x1400334e6  call    Smb2EndpointWillEncrypt
0x1400334eb  test    al, al
0x1400334ed  jz      short loc_14003352F
0x1400334ef  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400334f6  lea     rbx, WPP_GLOBAL_Control
0x1400334fd  cmp     rcx, rbx
0x140033500  jz      short loc_140033528
0x140033502  mov     eax, [rcx+2Ch]
0x140033505  test    al, 8
0x140033507  jz      short loc_140033528
0x140033509  cmp     byte ptr [rcx+29h], 4
0x14003350d  jb      short loc_140033528
0x14003350f  mov     r9, [rsi+38h]
0x140033513  lea     r8, WPP_60db1590be613abca80435fd5891bee8_Traceguids
0x14003351a  mov     rcx, [rcx+18h]
0x14003351e  mov     edx, 0Bh
0x140033523  call    WPP_SF_q
0x140033528  xor     edi, edi
0x14003352a  jmp     loc_140033682
0x14003352f  mov     rcx, rsi
0x140033532  call    Smb2GenerateHashHandleForOutgoingSignature
0x140033537  mov     edi, eax
0x140033539  test    eax, eax
0x14003353b  jns     short loc_14003358C
0x14003353d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140033544  lea     rbx, WPP_GLOBAL_Control
0x14003354b  cmp     rcx, rbx
0x14003354e  jz      loc_140033636
0x140033554  mov     edx, [rcx+2Ch]
0x140033557  test    dl, 8
0x14003355a  jz      loc_140033636
0x140033560  cmp     byte ptr [rcx+29h], 4
0x140033564  jb      loc_140033636
0x14003356a  mov     r9, [rsi+38h]
0x14003356e  lea     r8, WPP_60db1590be613abca80435fd5891bee8_Traceguids
0x140033575  mov     rcx, [rcx+18h]
0x140033579  mov     edx, 0Ch
0x14003357e  mov     [rsp+78h+var_58], eax
0x140033582  call    WPP_SF_qD
0x140033587  jmp     loc_140033636
0x14003358c  mov     rcx, [rsi+318h]; hHash
0x140033593  xor     r9d, r9d; dwFlags
0x140033596  mov     r8d, r14d; cbInput
0x140033599  mov     rdx, rbx; pbInput
0x14003359c  call    cs:__imp_BCryptHashData
0x1400335a3  nop     dword ptr [rax+rax+00h]
0x1400335a8  mov     edi, eax
0x1400335aa  test    eax, eax
0x1400335ac  jns     short loc_1400335D5
0x1400335ae  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400335b5  lea     rbx, WPP_GLOBAL_Control
0x1400335bc  cmp     rcx, rbx
0x1400335bf  jz      short loc_140033636
0x1400335c1  mov     eax, [rcx+2Ch]
0x1400335c4  test    al, 1
0x1400335c6  jz      short loc_140033636
0x1400335c8  cmp     byte ptr [rcx+29h], 1
0x1400335cc  jb      short loc_140033636
0x1400335ce  mov     edx, 0Dh
0x1400335d3  jmp     short loc_140033622
0x1400335d5  mov     r8d, [rsi+320h]; cbOutput
0x1400335dc  lea     rdx, [rsp+78h+pbOutput]; pbOutput
0x1400335e1  mov     rcx, [rsi+318h]; hHash
0x1400335e8  xor     r9d, r9d; dwFlags
0x1400335eb  call    cs:__imp_BCryptFinishHash
0x1400335f2  nop     dword ptr [rax+rax+00h]
0x1400335f7  mov     edi, eax
0x1400335f9  test    eax, eax
0x1400335fb  jns     short loc_140033678
0x1400335fd  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140033604  lea     rbx, WPP_GLOBAL_Control
0x14003360b  cmp     rcx, rbx
0x14003360e  jz      short loc_140033636
0x140033610  mov     eax, [rcx+2Ch]
0x140033613  test    al, 1
0x140033615  jz      short loc_140033636
0x140033617  cmp     byte ptr [rcx+29h], 1
0x14003361b  jb      short loc_140033636
0x14003361d  mov     edx, 0Eh
0x140033622  mov     r9, [rsi+38h]
0x140033626  lea     r8, WPP_60db1590be613abca80435fd5891bee8_Traceguids
0x14003362d  mov     rcx, [rcx+18h]
0x140033631  call    WPP_SF_q
0x140033636  mov     rcx, rsi
0x140033639  call    cs:__imp_SmbCseDestroyHashHandle
0x140033640  nop     dword ptr [rax+rax+00h]
0x140033645  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003364c  cmp     rcx, rbx
0x14003364f  jz      short loc_140033682
0x140033651  mov     eax, [rcx+2Ch]
0x140033654  test    al, 1
0x140033656  jz      short loc_140033682
0x140033658  cmp     byte ptr [rcx+29h], 1
0x14003365c  jb      short loc_140033682
0x14003365e  mov     rcx, [rcx+18h]
0x140033662  lea     r8, WPP_60db1590be613abca80435fd5891bee8_Traceguids
0x140033669  mov     edx, 0Fh
0x14003366e  mov     r9d, edi
0x140033671  call    WPP_SF_d
0x140033676  jmp     short loc_140033682
0x140033678  movups  xmm0, xmmword ptr [rsp+78h+pbOutput]
0x14003367d  movdqu  xmmword ptr [rbx+30h], xmm0
0x140033682  mov     eax, edi
0x140033684  mov     rcx, [rsp+78h+var_28]
0x140033689  xor     rcx, rsp; StackCookie
0x14003368c  call    __security_check_cookie
0x140033691  mov     rbx, [rsp+78h+arg_18]
0x140033699  add     rsp, 60h
0x14003369d  pop     r14
0x14003369f  pop     rdi
0x1400336a0  pop     rsi
0x1400336a1  retn
```
