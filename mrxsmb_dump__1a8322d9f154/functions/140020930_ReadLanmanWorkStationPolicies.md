# ReadLanmanWorkStationPolicies

- ea: `0x140020930`
- end: `0x140020c48`
- name: `ReadLanmanWorkStationPolicies`
- size: `792`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14008fb70`
- `0x1400926ac`

## callees

- `0x140020930`
- `0x14003838c`
- `0x14003b788`
- `0x14003ba3c`
- `0x140059dc0`
- `0x140090470`
- `0x140092810`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x14005e7ae`
- `ntoskrnl!ZwOpenKey` at `0x14005e7ae`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x14005e704`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x14005e704`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x14002099a`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x14002099a`
- `ntoskrnl!ZwClose` at `0x14005eab9`
- `ntoskrnl!ZwClose` at `0x14005eab9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005eb25`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005eba2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005eb25`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005eba2`

## string_xrefs

- `0x1400209f8`: `\Registry\Machine\Software\Policies\Microsoft\Windows`
- `0x14005e6e3`: `\Registry\Machine\Software\Policies\Microsoft\Windows`
- `0x14005eacc`: `\Registry\Machine\Software\Policies\Microsoft\Windows\LanmanWorkstation`
- `0x14005eb3d`: `\Registry\Machine\Software\Policies\Microsoft\Windows\LanmanWorkstation`
- `0x14005e854`: `EnableCompressedTraffic`
- `0x14005e897`: `DisableCompression`

## pseudocode

```c
void __fastcall ReadLanmanWorkStationPolicies(_DWORD *a1)
{
  const wchar_t *v2; // rdx
  unsigned __int64 v3; // r8
  __int64 v4; // r11
  char *v5; // r9
  __int64 v6; // rcx
  int PersistedStateLocation; // ebx
  __int16 v8; // r10
  unsigned __int16 v9; // r10
  unsigned __int64 v10; // r10
  const wchar_t *v11; // rcx
  __int16 v12; // r9
  char *v13; // r8
  unsigned __int64 v14; // rdx
  PDEVICE_OBJECT v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  PDEVICE_OBJECT v18; // rcx
  __int64 v19; // rdx
  int v20; // edx
  int v21; // r8d
  int v22; // edx
  int v23; // r8d
  PVOID v24; // rbx
  PVOID v25; // rbx
  void *KeyHandle; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v27; // [rsp+50h] [rbp-B0h] BYREF
  char *v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+60h] [rbp-A0h] BYREF
  PVOID P; // [rsp+68h] [rbp-98h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  char v32; // [rsp+A0h] [rbp-60h] BYREF

  v27 = 34078720;
  KeyHandle = 0;
  P = 0;
  v28 = &v32;
  memset(&ObjectAttributes, 0, 32);
  *a1 = 0;
  *(_OWORD *)(&ObjectAttributes.Attributes + 1) = 0;
  v29 = 0;
  if ( (unsigned __int8)RtlIsStateSeparationEnabled() )
  {
    PersistedStateLocation = RtlGetPersistedStateLocation(
                               L"PoliciesWindows",
                               0,
                               L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows",
                               0,
                               v28,
                               WORD1(v27),
                               &v29);
    if ( PersistedStateLocation >= 0 )
    {
      v9 = v29 - 2;
      v4 = 0x7FFF;
      LOWORD(v27) = v29 - 2;
      goto LABEL_10;
    }
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v19 = 34;
      v17 = (unsigned int)PersistedStateLocation;
      goto LABEL_60;
    }
LABEL_24:
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v16 = 38;
      goto LABEL_112;
    }
    return;
  }
  if ( (v27 & 1) != 0
    || (v27 & 0x10000) != 0
    || (unsigned __int16)v27 > WORD1(v27)
    || WORD1(v27) == 0xFFFF
    || !v28 && (_DWORD)v27 )
  {
    PersistedStateLocation = -1073741811;
    goto LABEL_27;
  }
  v2 = L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows";
  v3 = (unsigned __int64)WORD1(v27) >> 1;
  v4 = 0x7FFF;
  v5 = v28;
  v6 = 0x7FFF;
  PersistedStateLocation = 0;
  v8 = 0;
  if ( v3 )
  {
    while ( v6 && *v2 )
    {
      *(_WORD *)v5 = *v2++;
      v5 += 2;
      --v6;
      ++v8;
      if ( !--v3 )
      {
        if ( !v6 || !*v2 )
          break;
        goto LABEL_8;
      }
    }
  }
  else
  {
LABEL_8:
    PersistedStateLocation = -2147483643;
  }
  v9 = 2 * v8;
  LOWORD(v27) = v9;
  if ( PersistedStateLocation < 0 )
  {
LABEL_27:
    v17 = (unsigned int)PersistedStateLocation;
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v19 = 35;
LABEL_60:
      WPP_SF_d(v18->AttachedDevice, v19, WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids, v17);
      goto LABEL_24;
    }
    goto LABEL_24;
  }
LABEL_10:
  if ( (unsigned __int64)v9 + 2 > WORD1(v27) )
  {
    PersistedStateLocation = -1073741789;
    goto LABEL_24;
  }
  *(_WORD *)&v28[v9] = 0;
  if ( (v27 & 1) != 0
    || (v27 & 0x10000) != 0
    || (unsigned __int16)v27 > WORD1(v27)
    || WORD1(v27) == 0xFFFF
    || !v28 && (_DWORD)v27 )
  {
    PersistedStateLocation = -1073741811;
  }
  else
  {
    v10 = (unsigned __int64)(unsigned __int16)v27 >> 1;
    v11 = L"\\LanmanWorkstation";
    PersistedStateLocation = 0;
    v12 = 0;
    v13 = &v28[2 * v10];
    v14 = ((unsigned __int64)WORD1(v27) >> 1) - v10;
    if ( (unsigned __int64)WORD1(v27) >> 1 == v10 )
    {
LABEL_17:
      PersistedStateLocation = -2147483643;
    }
    else
    {
      while ( v4 )
      {
        if ( !*v11 )
        {
          if ( v14 )
            break;
LABEL_42:
          if ( !v4 || !*v11 )
            break;
          goto LABEL_17;
        }
        *(_WORD *)v13 = *v11++;
        v13 += 2;
        --v4;
        ++v12;
        if ( !--v14 )
          goto LABEL_42;
      }
    }
    LOWORD(v27) = 2 * (v10 + v12);
    if ( PersistedStateLocation >= 0 )
    {
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&v27;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
      {
        if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
          byte_14007D16D = 1;
        byte_14007D16D = 0;
        if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
          byte_14007D16E = 1;
        byte_14007D16E = 0;
        if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
        {
          *a1 |= 1u;
          byte_14007D164 = 0;
        }
        if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
        {
          *a1 |= 2u;
          word_14007D1CA &= ~1u;
        }
        if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
        {
          *a1 |= 4u;
          word_14007D1CA &= ~2u;
        }
        if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
        {
          *a1 |= 8u;
          if ( word_14007D15C )
          {
            if ( (byte_1400712A3 & 8) != 0 )
              McTemplateK0zdd_EtwWriteTransfer(
                (unsigned __int16)word_14007D15C,
                v20,
                v21,
                (unsigned int)L"MaxSmb2Dialect",
                word_14007D15C,
                0);
            word_14007D15C = 0;
          }
        }
        if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
        {
          *a1 |= 0x10u;
          if ( word_14007D15E )
          {
            if ( (byte_1400712A3 & 8) != 0 )
              McTemplateK0zdd_EtwWriteTransfer(
                (unsigned __int16)word_14007D15E,
                v22,
                v23,
                (unsigned int)L"MinSmb2Dialect",
                word_14007D15E,
                0);
            word_14007D15E = 0;
          }
        }
        if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
        {
          *a1 |= 0x20u;
          byte_14007D244 = 0;
        }
        if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
        {
          *a1 |= 0x40u;
          byte_14007D13D = 0;
        }
        if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
        {
          *a1 |= 0x80u;
          byte_14007D25B = 0;
        }
        if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
        {
          *a1 |= 0x100u;
          byte_14007D25C = 0;
        }
        if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
        {
          *a1 |= 0x200u;
          byte_14007D25D = 0;
        }
        if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
        {
          *a1 |= 0x400u;
          byte_14007D25E = 0;
        }
        if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
        {
          *a1 |= 0x1000u;
          byte_14007D260 = 0;
        }
        ZwClose(KeyHandle);
      }
      if ( (int)RfsRegGetMultiSZList(
                  &P,
                  L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows\\LanmanWorkstation",
                  L"BlockNTLMServerExceptionList") >= 0 )
      {
        v24 = P;
        if ( P )
        {
          if ( *(_QWORD *)P
            && (int)ReadTargetServerExceptionList(P, &qword_14007D250, byte_14007D258, &qword_14007D248) >= 0 )
          {
            *a1 |= 0x800u;
          }
          if ( v24 )
            ExFreePoolWithTag(v24, 0x52736652u);
          P = 0;
        }
      }
      if ( (int)RfsRegGetMultiSZList(
                  &P,
                  L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows\\LanmanWorkstation",
                  L"DisabledSMBQUICServerExceptionList") >= 0 )
      {
        v25 = P;
        if ( P )
        {
          if ( *(_QWORD *)P
            && (int)ReadTargetServerExceptionList(P, &qword_14007D270, &word_14007D278, &qword_14007D268) >= 0 )
          {
            *a1 |= 0x2000u;
          }
          if ( v25 )
            ExFreePoolWithTag(v25, 0x52736652u);
        }
      }
      return;
    }
  }
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    v16 = 39;
LABEL_112:
    WPP_SF_d(
      v15->AttachedDevice,
      v16,
      WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids,
      (unsigned int)PersistedStateLocation);
  }
}

```

## disassembly

```asm
0x140020930  push    rbp
0x140020932  push    rbx
0x140020933  push    rsi
0x140020934  push    rdi
0x140020935  push    r14
0x140020937  push    r15
0x140020939  lea     rbp, [rsp-1C8h]
0x140020941  sub     rsp, 2C8h
0x140020948  mov     rax, cs:__security_cookie
0x14002094f  xor     rax, rsp
0x140020952  mov     [rbp+1F0h+var_40], rax
0x140020959  xor     r15d, r15d
0x14002095c  mov     [rsp+2F0h+var_2A0], 2080000h
0x140020965  xorps   xmm0, xmm0
0x140020968  mov     [rsp+2F0h+KeyHandle], r15
0x14002096d  xor     eax, eax
0x14002096f  mov     [rsp+2F0h+var_2B0], r15d
0x140020974  lea     rax, [rbp+1F0h+var_250]
0x140020978  mov     [rsp+2F0h+P], r15
0x14002097d  movups  xmmword ptr [rbp+1F0h+ObjectAttributes.ObjectName], xmm0
0x140020981  mov     [rsp+2F0h+var_298], rax
0x140020986  mov     r14, rcx
0x140020989  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.Length], xmm0
0x14002098e  mov     [rcx], r15d
0x140020991  movups  xmmword ptr [rbp+1F0h+ObjectAttributes+1Ch], xmm0
0x140020995  mov     [rsp+2F0h+var_290], r15d
0x14002099a  call    cs:__imp_RtlIsStateSeparationEnabled
0x1400209a1  nop     dword ptr [rax+rax+00h]
0x1400209a6  lea     rdi, WPP_GLOBAL_Control
0x1400209ad  test    al, al
0x1400209af  jnz     loc_14005E6D4
0x1400209b5  movzx   ecx, word ptr [rsp+2F0h+var_2A0]
0x1400209ba  test    cl, 1
0x1400209bd  jnz     loc_140020B2E
0x1400209c3  movzx   eax, word ptr [rsp+2F0h+var_2A0+2]
0x1400209c8  test    al, 1
0x1400209ca  jnz     loc_140020B2E
0x1400209d0  cmp     cx, ax
0x1400209d3  ja      loc_140020B2E
0x1400209d9  mov     esi, 0FFFEh
0x1400209de  cmp     ax, si
0x1400209e1  ja      loc_140020B2E
0x1400209e7  cmp     [rsp+2F0h+var_298], r15
0x1400209ec  jz      loc_140020BFB
0x1400209f2  movzx   r8d, word ptr [rsp+2F0h+var_2A0+2]
0x1400209f8  lea     rdx, aRegistryMachin_10; "\\Registry\\Machine\\Software\\Policies"...
0x1400209ff  shr     r8, 1
0x140020a02  mov     r11d, 7FFFh
0x140020a08  mov     r9, [rsp+2F0h+var_298]
0x140020a0d  mov     ecx, r11d
0x140020a10  mov     ebx, r15d
0x140020a13  mov     r10, r15
0x140020a16  jnz     loc_140020B63
0x140020a1c  mov     ebx, 80000005h
0x140020a21  add     r10w, r10w
0x140020a25  mov     word ptr [rsp+2F0h+var_2A0], r10w
0x140020a2b  test    ebx, ebx
0x140020a2d  js      loc_140020B33
0x140020a33  movzx   eax, word ptr [rsp+2F0h+var_2A0+2]
0x140020a38  movzx   edx, r10w
0x140020a3c  lea     rcx, [rdx+2]
0x140020a40  cmp     rcx, rax
0x140020a43  ja      loc_140020AF9
0x140020a49  mov     rax, [rsp+2F0h+var_298]
0x140020a4e  mov     [rdx+rax], r15w
0x140020a53  movzx   ecx, word ptr [rsp+2F0h+var_2A0]
0x140020a58  test    cl, 1
0x140020a5b  jnz     loc_140020B59
0x140020a61  movzx   eax, word ptr [rsp+2F0h+var_2A0+2]
0x140020a66  test    al, 1
0x140020a68  jnz     loc_140020B59
0x140020a6e  cmp     cx, ax
0x140020a71  ja      loc_140020B59
0x140020a77  cmp     ax, si
0x140020a7a  ja      loc_140020B59
0x140020a80  mov     r8, [rsp+2F0h+var_298]
0x140020a85  test    r8, r8
0x140020a88  jz      loc_140020C12
0x140020a8e  mov     r10, rcx
0x140020a91  mov     rdx, rax
0x140020a94  shr     r10, 1
0x140020a97  lea     rcx, aLanmanworkstat_1; "\\LanmanWorkstation"
0x140020a9e  shr     rdx, 1
0x140020aa1  mov     ebx, r15d
0x140020aa4  mov     r9, r15
0x140020aa7  lea     r8, [r8+r10*2]
0x140020aab  sub     rdx, r10
0x140020aae  jnz     loc_140020BB0
0x140020ab4  mov     ebx, 80000005h
0x140020ab9  add     r9w, r10w
0x140020abd  add     r9w, r9w
0x140020ac1  mov     word ptr [rsp+2F0h+var_2A0], r9w
0x140020ac7  test    ebx, ebx
0x140020ac9  jns     loc_14005E77A
0x140020acf  mov     rcx, cs:WPP_GLOBAL_Control
0x140020ad6  lea     rdi, WPP_GLOBAL_Control
0x140020add  cmp     rcx, rdi
0x140020ae0  jz      short loc_140020B0E
0x140020ae2  mov     eax, [rcx+2Ch]
0x140020ae5  test    al, 1
0x140020ae7  jz      short loc_140020B0E
0x140020ae9  cmp     byte ptr [rcx+29h], 1
0x140020aed  jb      short loc_140020B0E
0x140020aef  mov     edx, 27h ; '''
0x140020af4  jmp     loc_14005EBB4
0x140020af9  mov     ebx, 0C0000023h
0x140020afe  mov     rcx, cs:WPP_GLOBAL_Control
0x140020b05  cmp     rcx, rdi
0x140020b08  jnz     loc_140020C29
0x140020b0e  mov     rcx, [rbp+1F0h+var_40]
0x140020b15  xor     rcx, rsp; StackCookie
0x140020b18  call    __security_check_cookie
0x140020b1d  add     rsp, 2C8h
0x140020b24  pop     r15
0x140020b26  pop     r14
0x140020b28  pop     rdi
0x140020b29  pop     rsi
0x140020b2a  pop     rbx
0x140020b2b  pop     rbp
0x140020b2c  retn
0x140020b2e  mov     ebx, 0C000000Dh
0x140020b33  mov     r9d, ebx
0x140020b36  mov     rcx, cs:WPP_GLOBAL_Control
0x140020b3d  cmp     rcx, rdi
0x140020b40  jz      short loc_140020AFE
0x140020b42  mov     eax, [rcx+2Ch]
0x140020b45  test    al, 1
0x140020b47  jz      short loc_140020AFE
0x140020b49  cmp     byte ptr [rcx+29h], 1
0x140020b4d  jb      short loc_140020AFE
0x140020b4f  mov     edx, 23h ; '#'
0x140020b54  jmp     loc_14005E764
0x140020b59  mov     ebx, 0C000000Dh
0x140020b5e  jmp     loc_140020ACF
0x140020b63  test    rcx, rcx
0x140020b66  jz      loc_140020A21
0x140020b6c  movzx   eax, word ptr [rdx]
0x140020b6f  test    ax, ax
0x140020b72  jz      short loc_140020BA3
0x140020b74  mov     [r9], ax
0x140020b78  add     rdx, 2
0x140020b7c  add     r9, 2
0x140020b80  dec     rcx
0x140020b83  inc     r10
0x140020b86  sub     r8, 1
0x140020b8a  jnz     short loc_140020B63
0x140020b8c  test    rcx, rcx
0x140020b8f  jz      loc_140020A21
0x140020b95  cmp     [rdx], bx
0x140020b98  jz      loc_140020A21
0x140020b9e  jmp     loc_140020A1C
0x140020ba3  test    r8, r8
0x140020ba6  jnz     loc_140020A21
0x140020bac  jmp     short loc_140020B8C
0x140020bb0  test    r11, r11
0x140020bb3  jz      loc_140020AB9
0x140020bb9  movzx   eax, word ptr [rcx]
0x140020bbc  test    ax, ax
0x140020bbf  jz      short loc_140020BF0
0x140020bc1  mov     [r8], ax
0x140020bc5  add     rcx, 2
0x140020bc9  add     r8, 2
0x140020bcd  dec     r11
0x140020bd0  inc     r9
0x140020bd3  sub     rdx, 1
0x140020bd7  jnz     short loc_140020BB0
0x140020bd9  test    r11, r11
0x140020bdc  jz      loc_140020AB9
0x140020be2  cmp     [rcx], bx
0x140020be5  jz      loc_140020AB9
0x140020beb  jmp     loc_140020AB4
0x140020bf0  test    rdx, rdx
0x140020bf3  jnz     loc_140020AB9
0x140020bf9  jmp     short loc_140020BD9
0x140020bfb  test    cx, cx
0x140020bfe  jnz     loc_140020B2E
0x140020c04  test    ax, ax
0x140020c07  jnz     loc_140020B2E
0x140020c0d  jmp     loc_1400209F2
0x140020c12  test    cx, cx
0x140020c15  jnz     loc_140020B59
0x140020c1b  test    ax, ax
0x140020c1e  jnz     loc_140020B59
0x140020c24  jmp     loc_140020A8E
0x140020c29  mov     eax, [rcx+2Ch]
0x140020c2c  test    al, 1
0x140020c2e  jz      loc_140020B0E
0x140020c34  cmp     byte ptr [rcx+29h], 1
0x140020c38  jb      loc_140020B0E
0x140020c3e  mov     edx, 26h ; '&'
0x140020c43  jmp     loc_14005EBB4
0x14005e6d4  movzx   eax, word ptr [rsp+2F0h+var_2A0+2]
0x14005e6d9  lea     rcx, [rsp+2F0h+var_290]
0x14005e6de  mov     [rsp+2F0h+var_2C0], rcx
0x14005e6e3  lea     r8, aRegistryMachin_10; "\\Registry\\Machine\\Software\\Policies"...
0x14005e6ea  mov     [rsp+2F0h+var_2C8], eax
0x14005e6ee  lea     rcx, aPolicieswindow; "PoliciesWindows"
0x14005e6f5  mov     rax, [rsp+2F0h+var_298]
0x14005e6fa  xor     r9d, r9d
0x14005e6fd  xor     edx, edx
0x14005e6ff  mov     [rsp+2F0h+var_2D0], rax
0x14005e704  call    cs:__imp_RtlGetPersistedStateLocation
0x14005e70b  nop     dword ptr [rax+rax+00h]
0x14005e710  mov     ebx, eax
0x14005e712  test    eax, eax
0x14005e714  js      short loc_14005E737
0x14005e716  movzx   r10d, word ptr [rsp+2F0h+var_290]
0x14005e71c  mov     esi, 0FFFEh
0x14005e721  sub     r10w, 2
0x14005e726  mov     r11d, 7FFFh
0x14005e72c  mov     word ptr [rsp+2F0h+var_2A0], r10w
0x14005e732  jmp     loc_140020A33
0x14005e737  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e73e  cmp     rcx, rdi
0x14005e741  jz      loc_140020AFE
0x14005e747  mov     eax, [rcx+2Ch]
0x14005e74a  test    al, 1
0x14005e74c  jz      loc_140020AFE
0x14005e752  cmp     byte ptr [rcx+29h], 1
0x14005e756  jb      loc_140020AFE
0x14005e75c  mov     edx, 22h ; '"'
0x14005e761  mov     r9d, ebx
0x14005e764  mov     rcx, [rcx+18h]
0x14005e768  lea     r8, WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids
0x14005e76f  call    WPP_SF_d
0x14005e774  nop
0x14005e775  jmp     loc_140020AFE
0x14005e77a  lea     rax, [rsp+2F0h+var_2A0]
0x14005e77f  mov     [rsp+2F0h+ObjectAttributes.Length], 30h ; '0'
0x14005e787  xorps   xmm0, xmm0
0x14005e78a  mov     [rbp+1F0h+ObjectAttributes.ObjectName], rax
0x14005e78e  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x14005e793  mov     [rsp+2F0h+ObjectAttributes.RootDirectory], r15
0x14005e798  mov     edx, 20019h; DesiredAccess
0x14005e79d  mov     [rbp+1F0h+ObjectAttributes.Attributes], 240h
0x14005e7a4  lea     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x14005e7a9  movdqu  xmmword ptr [rbp+1F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14005e7ae  call    cs:__imp_ZwOpenKey
0x14005e7b5  nop     dword ptr [rax+rax+00h]
0x14005e7ba  test    eax, eax
0x14005e7bc  js      loc_14005EAC5
0x14005e7c2  mov     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x14005e7c7  lea     r8, [rsp+2F0h+var_2B0]
0x14005e7cc  lea     rdx, aAllowofflinefi; "AllowOfflineFilesForCAShares"
0x14005e7d3  call    MRxSmbGetUlongRegistryParameter
0x14005e7d8  test    eax, eax
0x14005e7da  js      short loc_14005E7EA
0x14005e7dc  mov     cs:byte_14007D16D, 1
0x14005e7e3  cmp     [rsp+2F0h+var_2B0], r15d
0x14005e7e8  ja      short loc_14005E7F1
0x14005e7ea  mov     cs:byte_14007D16D, r15b
0x14005e7f1  mov     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x14005e7f6  lea     r8, [rsp+2F0h+var_2B0]
0x14005e7fb  lea     rdx, aEnablehandleca; "EnableHandleCachingForCAFiles"
0x14005e802  call    MRxSmbGetUlongRegistryParameter
0x14005e807  test    eax, eax
0x14005e809  js      short loc_14005E819
0x14005e80b  mov     cs:byte_14007D16E, 1
0x14005e812  cmp     [rsp+2F0h+var_2B0], r15d
0x14005e817  ja      short loc_14005E820
0x14005e819  mov     cs:byte_14007D16E, r15b
0x14005e820  mov     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x14005e825  lea     r8, [rsp+2F0h+var_2B0]
0x14005e82a  lea     rdx, aAllowinsecureg; "AllowInsecureGuestAuth"
0x14005e831  call    MRxSmbGetUlongRegistryParameter
0x14005e836  test    eax, eax
0x14005e838  js      short loc_14005E84A
0x14005e83a  or      dword ptr [r14], 1
0x14005e83e  cmp     [rsp+2F0h+var_2B0], r15d
0x14005e843  setnbe  cs:byte_14007D164
0x14005e84a  mov     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x14005e84f  lea     r8, [rsp+2F0h+var_2B0]
0x14005e854  lea     rdx, aEnablecompress; "EnableCompressedTraffic"
0x14005e85b  call    MRxSmbGetUlongRegistryParameter
0x14005e860  test    eax, eax
0x14005e862  js      short loc_14005E88D
0x14005e864  or      dword ptr [r14], 2
0x14005e868  mov     eax, 1
0x14005e86d  cmp     [rsp+2F0h+var_2B0], r15d
0x14005e872  mov     ecx, r15d
0x14005e875  cmovnz  cx, ax
0x14005e879  movzx   eax, cs:word_14007D1CA
0x14005e880  and     ax, si
0x14005e883  or      ax, cx
0x14005e886  mov     cs:word_14007D1CA, ax
0x14005e88d  mov     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x14005e892  lea     r8, [rsp+2F0h+var_2B0]
0x14005e897  lea     rdx, aDisablecompres; "DisableCompression"
0x14005e89e  call    MRxSmbGetUlongRegistryParameter
0x14005e8a3  test    eax, eax
0x14005e8a5  js      short loc_14005E8D5
0x14005e8a7  or      dword ptr [r14], 4
0x14005e8ab  mov     eax, 2
0x14005e8b0  cmp     [rsp+2F0h+var_2B0], r15d
0x14005e8b5  mov     ecx, r15d
0x14005e8b8  mov     edx, 0FFFDh
0x14005e8bd  cmovnz  cx, ax
0x14005e8c1  movzx   eax, cs:word_14007D1CA
0x14005e8c8  and     ax, dx
0x14005e8cb  or      ax, cx
  ... truncated ...
```
