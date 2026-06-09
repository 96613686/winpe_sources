# MRxSmb2SessionSetup

- ea: `0x140055fb0`
- end: `0x1400560d2`
- name: `MRxSmb2SessionSetup`
- size: `290`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x14001fc10`
- `0x140055fb0`

## import_xrefs

- `mrxsmb!SmbCeInitiateExchange` at `0x140056095`
- `mrxsmb!SmbCeInitiateExchange` at `0x140056095`
- `mrxsmb!SmbCeInitializeExchange` at `0x140055ff8`
- `mrxsmb!SmbCeInitializeExchange` at `0x140055ff8`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140056070`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140056070`
- `mrxsmb!SmbCeCheckServerEntryDialect` at `0x140056055`
- `mrxsmb!SmbCeCheckServerEntryDialect` at `0x140056055`

## pseudocode

```c
__int64 __fastcall MRxSmb2SessionSetup(__int64 a1, __int64 a2, char a3, __int64 a4)
{
  __int64 result; // rax
  __int64 v9; // rcx
  _QWORD v10[7]; // [rsp+40h] [rbp-38h] BYREF

  v10[0] = 0;
  result = SmbCeInitializeExchange(v10, 0, a2, 0, a1, 0, 1104, &SessionSetupDispatch);
  if ( !(_DWORD)result )
  {
    _InterlockedOr((volatile signed __int32 *)(v10[0] + 68LL), 0x2090u);
    *(_QWORD *)(v10[0] + 1072LL) = a4;
    *(_BYTE *)(v10[0] + 1083LL) = a3;
    *(_BYTE *)(v10[0] + 1080LL) = 1;
    if ( (unsigned __int8)SmbCeCheckServerEntryDialect(*(_QWORD *)(a1 + 384), 3, 0, 0)
      && (unsigned int)(*(_DWORD *)(a1 + 12) - 3) <= 1 )
    {
      *(_DWORD *)(a1 + 576) = *(_DWORD *)(MRxSmbGetConfigurationBlock(v9) + 28);
    }
    if ( a3 )
    {
      Smb2InitializeBindingObjectHash(a2, (UCHAR *)(a1 + 608));
      _InterlockedOr((volatile signed __int32 *)(v10[0] + 68LL), 0x800u);
    }
    else if ( *(_DWORD *)(a1 + 12) == 4 )
    {
      *(_BYTE *)(v10[0] + 1081LL) = 1;
    }
    return SmbCeInitiateExchange(v10[0]);
  }
  return result;
}

```

## disassembly

```asm
0x140055fb0  push    rbx
0x140055fb2  push    rbp
0x140055fb3  push    rsi
0x140055fb4  push    rdi
0x140055fb5  sub     rsp, 58h
0x140055fb9  mov     rbx, rcx
0x140055fbc  lea     rax, SessionSetupDispatch
0x140055fc3  mov     [rsp+78h+var_40], rax
0x140055fc8  xor     ecx, ecx
0x140055fca  mov     [rsp+78h+var_48], 450h
0x140055fd2  movzx   edi, r8b
0x140055fd6  mov     [rsp+78h+var_50], rcx
0x140055fdb  mov     rbp, r9
0x140055fde  mov     rsi, rdx
0x140055fe1  mov     [rsp+78h+var_38], rcx
0x140055fe6  mov     r8, rdx
0x140055fe9  mov     [rsp+78h+var_58], rbx
0x140055fee  lea     rcx, [rsp+78h+var_38]
0x140055ff3  xor     r9d, r9d
0x140055ff6  xor     edx, edx
0x140055ff8  call    cs:__imp_SmbCeInitializeExchange
0x140055fff  nop     dword ptr [rax+rax+00h]
0x140056004  test    eax, eax
0x140056006  jz      short loc_140056012
0x140056008  add     rsp, 58h
0x14005600c  pop     rdi
0x14005600d  pop     rsi
0x14005600e  pop     rbp
0x14005600f  pop     rbx
0x140056010  retn
0x140056012  mov     rax, [rsp+78h+var_38]
0x140056017  lock or dword ptr [rax+44h], 2090h
0x14005601f  mov     rax, [rsp+78h+var_38]
0x140056024  xor     r9d, r9d
0x140056027  xor     r8d, r8d
0x14005602a  mov     edx, 3
0x14005602f  mov     [rax+430h], rbp
0x140056036  mov     rax, [rsp+78h+var_38]
0x14005603b  mov     [rax+43Bh], dil
0x140056042  mov     rax, [rsp+78h+var_38]
0x140056047  mov     byte ptr [rax+438h], 1
0x14005604e  mov     rcx, [rbx+180h]
0x140056055  call    cs:__imp_SmbCeCheckServerEntryDialect
0x14005605c  nop     dword ptr [rax+rax+00h]
0x140056061  test    al, al
0x140056063  jz      short loc_140056085
0x140056065  mov     eax, [rbx+0Ch]
0x140056068  sub     eax, 3
0x14005606b  cmp     eax, 1
0x14005606e  ja      short loc_140056085
0x140056070  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140056077  nop     dword ptr [rax+rax+00h]
0x14005607c  mov     ecx, [rax+1Ch]
0x14005607f  mov     [rbx+240h], ecx
0x140056085  test    dil, dil
0x140056088  jnz     short loc_1400560A6
0x14005608a  cmp     dword ptr [rbx+0Ch], 4
0x14005608e  jz      short loc_1400560C4
0x140056090  mov     rcx, [rsp+78h+var_38]
0x140056095  call    cs:__imp_SmbCeInitiateExchange
0x14005609c  nop     dword ptr [rax+rax+00h]
0x1400560a1  jmp     loc_140056008
0x1400560a6  lea     rdx, [rbx+260h]
0x1400560ad  mov     rcx, rsi
0x1400560b0  call    Smb2InitializeBindingObjectHash
0x1400560b5  mov     rax, [rsp+78h+var_38]
0x1400560ba  lock or dword ptr [rax+44h], 800h
0x1400560c2  jmp     short loc_140056090
0x1400560c4  mov     rax, [rsp+78h+var_38]
0x1400560c9  mov     byte ptr [rax+439h], 1
0x1400560d0  jmp     short loc_140056090
```
