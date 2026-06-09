# DaRpcListConnectedDevice

- ea: `0x140008b50`
- end: `0x140009174`
- name: `DaRpcListConnectedDevice`
- size: `1572`
- prototype: `__int64 __fastcall(__int64, _DWORD *, unsigned int, _QWORD *, unsigned int *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, service_task`

## callees

- `0x140002bd8`
- `0x140002c00`
- `0x140002fbc`
- `0x140004bd4`
- `0x140008b50`
- `0x140009b80`
- `0x140009e0c`
- `0x14000a0b0`
- `0x14000a100`
- `0x14000a364`
- `0x14001830e`
- `0x140018326`
- `0x140018350`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x140008cf4`
- `KERNEL32!EnterCriticalSection` at `0x140008cf4`
- `KERNEL32!LeaveCriticalSection` at `0x140009103`
- `KERNEL32!LeaveCriticalSection` at `0x140009103`
- `KERNEL32!QueryDosDeviceW` at `0x140008d8e`
- `KERNEL32!QueryDosDeviceW` at `0x140008d8e`
- `msvcrt!towupper` at `0x140008dbd`
- `msvcrt!towupper` at `0x140008e63`
- `msvcrt!towupper` at `0x140008dbd`
- `msvcrt!towupper` at `0x140008e63`
- `RPCRT4!RpcImpersonateClient` at `0x140008bf8`
- `RPCRT4!RpcImpersonateClient` at `0x140008d74`
- `RPCRT4!RpcImpersonateClient` at `0x140008bf8`
- `RPCRT4!RpcImpersonateClient` at `0x140008d74`

## pseudocode

```c
__int64 __fastcall DaRpcListConnectedDevice(__int64 a1, _DWORD *a2, unsigned int a3, _QWORD *a4, unsigned int *a5)
{
  __int64 v5; // rsi
  unsigned int v7; // eax
  __int64 v9; // rcx
  void *v10; // rcx
  unsigned int v11; // eax
  __int64 v12; // r8
  unsigned int v13; // ebx
  int v14; // r13d
  char *v15; // rbx
  unsigned int v16; // edi
  wint_t *v17; // rcx
  __int64 v18; // rcx
  wint_t v19; // ax
  unsigned int v20; // r12d
  _QWORD *v21; // r14
  __int64 v22; // r8
  _QWORD *v23; // rcx
  _DWORD *v24; // rsi
  int v25; // r15d
  wint_t *v26; // rcx
  unsigned int v27; // esi
  __int64 v28; // r9
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rax
  __int64 v32; // r8
  _QWORD *v33; // rcx
  unsigned __int64 v34; // r15
  _DWORD v35[41]; // [rsp+0h] [rbp-184h]
  struct _LUID DestinationLuid; // [rsp+B4h] [rbp-D0h] BYREF
  __int64 v37; // [rsp+BCh] [rbp-C8h]
  unsigned int v38; // [rsp+C4h] [rbp-C0h]
  unsigned int *v39; // [rsp+CCh] [rbp-B8h]
  unsigned __int64 v40; // [rsp+D4h] [rbp-B0h]
  char *v41; // [rsp+DCh] [rbp-A8h]
  _DWORD *v42; // [rsp+E4h] [rbp-A0h]
  __int128 v43; // [rsp+ECh] [rbp-98h] BYREF
  char v44[112]; // [rsp+104h] [rbp-80h] BYREF
  char v45[32]; // [rsp+174h] [rbp-10h] BYREF
  WCHAR TargetPath[264]; // [rsp+194h] [rbp+10h] BYREF

  v5 = a3;
  strcpy(v45, "DaRpcListConnectedDevice");
  v40 = (unsigned __int64)a4;
  v38 = a3;
  v43 = 0;
  v42 = a2;
  v39 = a5;
  DestinationLuid = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids);
  *a5 = 0;
  v7 = RpcImpersonateClient(0);
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids, v7);
    return 5;
  }
  if ( (int)GetLuid(&DestinationLuid) < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids);
    SafeRpcRevertToSelf(v10, 895);
    return 5;
  }
  v11 = SafeRpcRevertToSelf(v9, 899);
  v13 = v11;
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        60,
        (unsigned int)&WPP_4b94345935ba3175354bb878a9e98408_Traceguids,
        (unsigned int)v45,
        v11);
    return v13;
  }
  v14 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_DD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      61,
      v12,
      (unsigned int)DestinationLuid.HighPart,
      DestinationLuid.LowPart);
  EnterCriticalSection(&DeviceListCS);
  memset_0(v44, 0, 0x68u);
  v15 = (char *)pDeviceList;
  v16 = 0;
  if ( pDeviceList )
  {
    while ( 1 )
    {
      if ( DestinationLuid.LowPart == *(_DWORD *)v15 && DestinationLuid.HighPart == *((_DWORD *)v15 + 1) )
      {
        v17 = (wint_t *)*((_QWORD *)v15 + 4);
        if ( v17 )
          goto LABEL_31;
      }
      if ( DaServiceLuid == *(_QWORD *)v15 )
      {
        if ( *((_QWORD *)v15 + 4) )
        {
          memset_0(TargetPath, 0, 0x208u);
          v16 = RpcImpersonateClient(0);
          if ( !v16 )
          {
            QueryDosDeviceW(*((LPCWSTR *)v15 + 4), TargetPath, 0x104u);
            SafeRpcRevertToSelf(v18, 943);
            if ( wcsncmp_0(TargetPath, L"\\Device\\MRxNfs", 0xFu) )
              break;
          }
        }
      }
LABEL_33:
      v15 = (char *)*((_QWORD *)v15 + 8);
      if ( !v15 )
      {
        if ( v16 )
          goto LABEL_88;
        v15 = (char *)pDeviceList;
        goto LABEL_36;
      }
    }
    v17 = (wint_t *)*((_QWORD *)v15 + 4);
LABEL_31:
    v19 = towupper(*v17);
    if ( (unsigned __int16)(v19 - 65) > 0x19u )
    {
      v16 = 87;
      goto LABEL_88;
    }
    v35[v19] = 1;
    goto LABEL_33;
  }
LABEL_36:
  v41 = (char *)a4 + v5;
  v20 = 0;
  v37 = (__int64)a4 + v5;
  v21 = a4;
  v22 = (__int64)a4 + v5;
  if ( !v15 )
    goto LABEL_88;
  v23 = WPP_GLOBAL_Control;
  while ( 1 )
  {
    v24 = v15 + 4;
    if ( DestinationLuid.LowPart != *(_DWORD *)v15 || DestinationLuid.HighPart != *v24 )
    {
      v25 = 0;
      if ( DaServiceLuid != *(_QWORD *)v15 )
        goto LABEL_44;
      v26 = (wint_t *)*((_QWORD *)v15 + 4);
      if ( !v26 )
        goto LABEL_44;
      if ( v35[towupper(*v26)] == 1 )
      {
        v22 = v37;
        v25 = 0;
        goto LABEL_44;
      }
      v23 = WPP_GLOBAL_Control;
    }
    v25 = 1;
    v20 += 24;
    if ( v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 8) != 0 )
    {
      WPP_SF_DD(v23[2], 62, v22, (unsigned int)*v24, *(_DWORD *)v15);
      v23 = WPP_GLOBAL_Control;
    }
    v28 = *((_QWORD *)v15 + 4);
    if ( v28 )
    {
      v29 = -1;
      do
        ++v29;
      while ( *(_WORD *)(v28 + 2 * v29) );
      v20 += 2 * v29 + 2;
    }
    v30 = *((_QWORD *)v15 + 5);
    if ( v30 )
    {
      v31 = -1;
      do
        ++v31;
      while ( *(_WORD *)(v30 + 2 * v31) );
      v20 += 2 * v31 + 2;
    }
    if ( v23 == &WPP_GLOBAL_Control )
      goto LABEL_68;
    if ( (*((_BYTE *)v23 + 28) & 8) != 0 )
    {
      WPP_SF_S(v23[2], 63, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids, v28);
      v23 = WPP_GLOBAL_Control;
    }
    if ( v23 == &WPP_GLOBAL_Control || (*((_BYTE *)v23 + 28) & 8) == 0 )
    {
LABEL_68:
      v22 = v37;
    }
    else
    {
      WPP_SF_S(v23[2], 64, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids, *((_QWORD *)v15 + 5));
      v22 = v37;
    }
LABEL_44:
    v27 = v38;
    *v39 = v20;
    if ( v20 <= v27 )
      break;
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids, v20);
      v23 = WPP_GLOBAL_Control;
    }
    v16 = 234;
LABEL_82:
    v15 = (char *)*((_QWORD *)v15 + 8);
    if ( !v15 )
      goto LABEL_88;
    v22 = v37;
  }
  if ( v25 != 1 )
  {
LABEL_81:
    v23 = WPP_GLOBAL_Control;
    goto LABEL_82;
  }
  v43 = *((_OWORD *)v15 + 2);
  v37 = PackString(&v43, v21, &ConnectedDeviceStrings, v22);
  v33 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids, *v21);
      v33 = WPP_GLOBAL_Control;
    }
    if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 8) != 0 )
    {
      WPP_SF_S(v33[2], 67, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids, v21[1]);
      v33 = WPP_GLOBAL_Control;
    }
  }
  v34 = v40;
  if ( (unsigned __int64)v21 >= v40 && v21 <= (_QWORD *)v41 - 3 )
  {
    if ( *v21 )
      *v21 -= v40;
    v21[1] -= v34;
    ++v14;
    v21 += 3;
    goto LABEL_81;
  }
  if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 2) != 0 )
    WPP_SF_qqD(v33[2], 68, v32, v21, v40, v27);
  v16 = 59;
LABEL_88:
  LeaveCriticalSection(&DeviceListCS);
  if ( v16 )
    v14 = 0;
  *v42 = v14;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids, v16);
  return v16;
}

```

## disassembly

```asm
0x140008b50  mov     [rsp-8+arg_0], rbx
0x140008b55  push    rbp
0x140008b56  push    rsi
0x140008b57  push    rdi
0x140008b58  push    r12
0x140008b5a  push    r13
0x140008b5c  push    r14
0x140008b5e  push    r15
0x140008b60  lea     rbp, [rsp-230h]
0x140008b68  sub     rsp, 330h
0x140008b6f  mov     rax, cs:__security_cookie
0x140008b76  xor     rax, rsp
0x140008b79  mov     [rbp+260h+var_40], rax
0x140008b80  movups  xmm0, xmmword ptr cs:aDarpclistconne; "DaRpcListConnectedDevice"
0x140008b87  mov     rbx, [rbp+260h+arg_20]
0x140008b8e  xor     r14d, r14d
0x140008b91  movups  xmm1, xmmword ptr cs:aDarpclistconne+9; "ConnectedDevice"
0x140008b98  mov     esi, r8d
0x140008b9b  mov     r15, r9
0x140008b9e  movups  xmmword ptr [rbp+260h+var_270], xmm0
0x140008ba2  mov     [rsp+360h+var_310], r9
0x140008ba7  xorps   xmm0, xmm0
0x140008baa  mov     [rsp+360h+var_320], esi
0x140008bae  movups  [rsp+360h+var_2F8], xmm0
0x140008bb3  mov     [rsp+360h+var_300], rdx
0x140008bb8  mov     [rsp+360h+var_318], rbx
0x140008bbd  movups  xmmword ptr [rbp+260h+var_270+9], xmm1
0x140008bc1  mov     qword ptr [rsp+360h+DestinationLuid.LowPart], r14
0x140008bc6  mov     rcx, cs:WPP_GLOBAL_Control
0x140008bcd  lea     rdi, WPP_GLOBAL_Control
0x140008bd4  cmp     rcx, rdi
0x140008bd7  jz      short loc_140008BF3
0x140008bd9  test    byte ptr [rcx+1Ch], 1
0x140008bdd  jz      short loc_140008BF3
0x140008bdf  mov     rcx, [rcx+10h]
0x140008be3  lea     edx, [r14+39h]
0x140008be7  lea     r8, WPP_4b94345935ba3175354bb878a9e98408_Traceguids
0x140008bee  call    WPP_SF_
0x140008bf3  xor     ecx, ecx; BindingHandle
0x140008bf5  mov     [rbx], r14d
0x140008bf8  call    cs:__imp_RpcImpersonateClient
0x140008bfe  test    eax, eax
0x140008c00  jz      short loc_140008C36
0x140008c02  mov     rcx, cs:WPP_GLOBAL_Control
0x140008c09  cmp     rcx, rdi
0x140008c0c  jz      short loc_140008C2C
0x140008c0e  test    byte ptr [rcx+1Ch], 2
0x140008c12  jz      short loc_140008C2C
0x140008c14  mov     rcx, [rcx+10h]
0x140008c18  lea     r8, WPP_4b94345935ba3175354bb878a9e98408_Traceguids
0x140008c1f  mov     edx, 3Ah ; ':'
0x140008c24  mov     r9d, eax
0x140008c27  call    WPP_SF_d
0x140008c2c  mov     eax, 5
0x140008c31  jmp     loc_14000914A
0x140008c36  lea     rcx, [rsp+360h+DestinationLuid]; DestinationLuid
0x140008c3b  call    GetLuid
0x140008c40  test    eax, eax
0x140008c42  jns     short loc_140008C77
0x140008c44  mov     rcx, cs:WPP_GLOBAL_Control
0x140008c4b  cmp     rcx, rdi
0x140008c4e  jz      short loc_140008C6B
0x140008c50  test    byte ptr [rcx+1Ch], 2
0x140008c54  jz      short loc_140008C6B
0x140008c56  mov     rcx, [rcx+10h]
0x140008c5a  lea     r8, WPP_4b94345935ba3175354bb878a9e98408_Traceguids
0x140008c61  mov     edx, 3Bh ; ';'
0x140008c66  call    WPP_SF_
0x140008c6b  mov     edx, 37Fh
0x140008c70  call    SafeRpcRevertToSelf
0x140008c75  jmp     short loc_140008C2C
0x140008c77  mov     edx, 383h
0x140008c7c  call    SafeRpcRevertToSelf
0x140008c81  mov     ebx, eax
0x140008c83  test    eax, eax
0x140008c85  jz      short loc_140008CBD
0x140008c87  mov     rcx, cs:WPP_GLOBAL_Control
0x140008c8e  cmp     rcx, rdi
0x140008c91  jz      short loc_140008CB6
0x140008c93  test    byte ptr [rcx+1Ch], 2
0x140008c97  jz      short loc_140008CB6
0x140008c99  mov     rcx, [rcx+10h]
0x140008c9d  lea     r9, [rbp+260h+var_270]
0x140008ca1  mov     edx, 3Ch ; '<'
0x140008ca6  mov     dword ptr [rsp+360h+var_340], eax
0x140008caa  lea     r8, WPP_4b94345935ba3175354bb878a9e98408_Traceguids
0x140008cb1  call    WPP_SF_sd
0x140008cb6  mov     eax, ebx
0x140008cb8  jmp     loc_14000914A
0x140008cbd  mov     rcx, cs:WPP_GLOBAL_Control
0x140008cc4  mov     r13d, r14d
0x140008cc7  cmp     rcx, rdi
0x140008cca  jz      short loc_140008CED
0x140008ccc  test    byte ptr [rcx+1Ch], 8
0x140008cd0  jz      short loc_140008CED
0x140008cd2  mov     eax, [rsp+360h+DestinationLuid.LowPart]
0x140008cd6  mov     edx, 3Dh ; '='
0x140008cdb  mov     r9d, [rsp+360h+DestinationLuid.HighPart]
0x140008ce0  mov     rcx, [rcx+10h]
0x140008ce4  mov     dword ptr [rsp+360h+var_340], eax
0x140008ce8  call    WPP_SF_DD
0x140008ced  lea     rcx, DeviceListCS; lpCriticalSection
0x140008cf4  call    cs:__imp_EnterCriticalSection
0x140008cfa  xor     edx, edx; Val
0x140008cfc  lea     rcx, [rbp+260h+var_2E0]; void *
0x140008d00  lea     r8d, [rdx+68h]; Size
0x140008d04  call    memset_0
0x140008d09  mov     rbx, cs:pDeviceList
0x140008d10  mov     edi, r14d
0x140008d13  mov     r12d, 41h ; 'A'
0x140008d19  test    rbx, rbx
0x140008d1c  jz      loc_140008E00
0x140008d22  mov     edx, [rbx]
0x140008d24  cmp     [rsp+360h+DestinationLuid.LowPart], edx
0x140008d28  jnz     short loc_140008D3C
0x140008d2a  mov     eax, [rbx+4]
0x140008d2d  cmp     [rsp+360h+DestinationLuid.HighPart], eax
0x140008d31  jnz     short loc_140008D3C
0x140008d33  mov     rcx, [rbx+20h]
0x140008d37  test    rcx, rcx
0x140008d3a  jnz     short loc_140008DBA
0x140008d3c  cmp     dword ptr cs:DaServiceLuid, edx
0x140008d42  jnz     loc_140008DE2
0x140008d48  mov     eax, [rbx+4]
0x140008d4b  cmp     dword ptr cs:DaServiceLuid+4, eax
0x140008d51  jnz     loc_140008DE2
0x140008d57  cmp     [rbx+20h], r14
0x140008d5b  jz      loc_140008DE2
0x140008d61  xor     edx, edx; Val
0x140008d63  lea     rcx, [rbp+260h+TargetPath]; void *
0x140008d67  mov     r8d, 208h; Size
0x140008d6d  call    memset_0
0x140008d72  xor     ecx, ecx; BindingHandle
0x140008d74  call    cs:__imp_RpcImpersonateClient
0x140008d7a  mov     edi, eax
0x140008d7c  test    eax, eax
0x140008d7e  jnz     short loc_140008DE2
0x140008d80  mov     rcx, [rbx+20h]; lpDeviceName
0x140008d84  lea     rdx, [rbp+260h+TargetPath]; lpTargetPath
0x140008d88  mov     r8d, 104h; ucchMax
0x140008d8e  call    cs:__imp_QueryDosDeviceW
0x140008d94  mov     edx, 3AFh
0x140008d99  call    SafeRpcRevertToSelf
0x140008d9e  lea     r8d, [rdi+0Fh]; MaxCount
0x140008da2  lea     rdx, aDeviceMrxnfs; "\\Device\\MRxNfs"
0x140008da9  lea     rcx, [rbp+260h+TargetPath]; String1
0x140008dad  call    wcsncmp_0
0x140008db2  test    eax, eax
0x140008db4  jz      short loc_140008DE2
0x140008db6  mov     rcx, [rbx+20h]
0x140008dba  movzx   ecx, word ptr [rcx]; C
0x140008dbd  call    cs:__imp_towupper
0x140008dc3  movzx   ecx, ax
0x140008dc6  sub     cx, r12w
0x140008dca  cmp     cx, 19h
0x140008dce  ja      loc_140008EDB
0x140008dd4  movzx   eax, ax
0x140008dd7  mov     [rbp+rax*4+260h+var_3E4], 1
0x140008de2  mov     rbx, [rbx+40h]
0x140008de6  mov     eax, edi
0x140008de8  test    rbx, rbx
0x140008deb  jnz     loc_140008D22
0x140008df1  test    eax, eax
0x140008df3  jnz     loc_1400090FC
0x140008df9  mov     rbx, cs:pDeviceList
0x140008e00  lea     rax, [r15+rsi]
0x140008e04  xor     r10d, r10d
0x140008e07  mov     [rsp+360h+var_308], rax
0x140008e0c  mov     r12d, r14d
0x140008e0f  mov     [rsp+360h+var_328], rax
0x140008e14  mov     r14, r15
0x140008e17  mov     r8, rax
0x140008e1a  test    rbx, rbx
0x140008e1d  jz      loc_1400090F9
0x140008e23  mov     rcx, cs:WPP_GLOBAL_Control
0x140008e2a  mov     edx, [rbx]
0x140008e2c  lea     rsi, [rbx+4]
0x140008e30  cmp     [rsp+360h+DestinationLuid.LowPart], edx
0x140008e34  jnz     short loc_140008E42
0x140008e36  mov     eax, [rsi]
0x140008e38  cmp     [rsp+360h+DestinationLuid.HighPart], eax
0x140008e3c  jz      loc_140008EEC
0x140008e42  cmp     dword ptr cs:DaServiceLuid, edx
0x140008e48  mov     r15d, r10d
0x140008e4b  jnz     short loc_140008E81
0x140008e4d  mov     eax, [rsi]
0x140008e4f  cmp     dword ptr cs:DaServiceLuid+4, eax
0x140008e55  jnz     short loc_140008E81
0x140008e57  mov     rcx, [rbx+20h]
0x140008e5b  test    rcx, rcx
0x140008e5e  jz      short loc_140008E81
0x140008e60  movzx   ecx, word ptr [rcx]; C
0x140008e63  call    cs:__imp_towupper
0x140008e69  movzx   eax, ax
0x140008e6c  xor     r10d, r10d
0x140008e6f  cmp     [rbp+rax*4+260h+var_3E4], 1
0x140008e77  jnz     short loc_140008EE5
0x140008e79  mov     r8, [rsp+360h+var_328]
0x140008e7e  mov     r15d, r10d
0x140008e81  lea     r11, WPP_GLOBAL_Control
0x140008e88  mov     rax, [rsp+360h+var_318]
0x140008e8d  mov     esi, [rsp+360h+var_320]
0x140008e91  mov     [rax], r12d
0x140008e94  cmp     r12d, esi
0x140008e97  jbe     loc_140008FD9
0x140008e9d  mov     rcx, cs:WPP_GLOBAL_Control
0x140008ea4  cmp     rcx, r11
0x140008ea7  jz      short loc_140008ECE
0x140008ea9  test    byte ptr [rcx+1Ch], 2
0x140008ead  jz      short loc_140008ECE
0x140008eaf  mov     rcx, [rcx+10h]
0x140008eb3  lea     r8, WPP_4b94345935ba3175354bb878a9e98408_Traceguids
0x140008eba  mov     edx, 41h ; 'A'
0x140008ebf  mov     r9d, r12d
0x140008ec2  call    WPP_SF_d
0x140008ec7  mov     rcx, cs:WPP_GLOBAL_Control
0x140008ece  mov     edi, 0EAh
0x140008ed3  xor     r10d, r10d
0x140008ed6  jmp     loc_1400090BC
0x140008edb  mov     edi, 57h ; 'W'
0x140008ee0  jmp     loc_1400090FC
0x140008ee5  mov     rcx, cs:WPP_GLOBAL_Control
0x140008eec  mov     r15d, 1
0x140008ef2  add     r12d, 18h
0x140008ef6  lea     r11, WPP_GLOBAL_Control
0x140008efd  cmp     rcx, r11
0x140008f00  jz      short loc_140008F2F
0x140008f02  test    byte ptr [rcx+1Ch], 8
0x140008f06  jz      short loc_140008F2F
0x140008f08  mov     eax, [rbx]
0x140008f0a  lea     edx, [r15+3Dh]
0x140008f0e  mov     r9d, [rsi]
0x140008f11  mov     rcx, [rcx+10h]
0x140008f15  mov     dword ptr [rsp+360h+var_340], eax
0x140008f19  call    WPP_SF_DD
0x140008f1e  mov     rcx, cs:WPP_GLOBAL_Control
0x140008f25  lea     r11, WPP_GLOBAL_Control
0x140008f2c  xor     r10d, r10d
0x140008f2f  mov     r9, [rbx+20h]
0x140008f33  test    r9, r9
0x140008f36  jz      short loc_140008F4E
0x140008f38  or      rax, 0FFFFFFFFFFFFFFFFh
0x140008f3c  inc     rax
0x140008f3f  cmp     [r9+rax*2], r10w
0x140008f44  jnz     short loc_140008F3C
0x140008f46  lea     r12d, [r12+rax*2]
0x140008f4a  add     r12d, 2
0x140008f4e  mov     rdx, [rbx+28h]
0x140008f52  test    rdx, rdx
0x140008f55  jz      short loc_140008F6D
0x140008f57  or      rax, 0FFFFFFFFFFFFFFFFh
0x140008f5b  inc     rax
0x140008f5e  cmp     [rdx+rax*2], r10w
0x140008f63  jnz     short loc_140008F5B
0x140008f65  lea     r12d, [r12+rax*2]
0x140008f69  add     r12d, 2
0x140008f6d  cmp     rcx, r11
0x140008f70  jz      short loc_140008FCF
0x140008f72  test    byte ptr [rcx+1Ch], 8
0x140008f76  jz      short loc_140008F9E
0x140008f78  mov     rcx, [rcx+10h]
0x140008f7c  lea     r8, WPP_4b94345935ba3175354bb878a9e98408_Traceguids
0x140008f83  mov     edx, 3Fh ; '?'
0x140008f88  call    WPP_SF_S
0x140008f8d  mov     rcx, cs:WPP_GLOBAL_Control
0x140008f94  lea     r11, WPP_GLOBAL_Control
0x140008f9b  xor     r10d, r10d
0x140008f9e  cmp     rcx, r11
0x140008fa1  jz      short loc_140008FCF
0x140008fa3  test    byte ptr [rcx+1Ch], 8
0x140008fa7  jz      short loc_140008FCF
0x140008fa9  mov     r9, [rbx+28h]
0x140008fad  lea     r8, WPP_4b94345935ba3175354bb878a9e98408_Traceguids
0x140008fb4  mov     rcx, [rcx+10h]
0x140008fb8  mov     edx, 40h ; '@'
0x140008fbd  call    WPP_SF_S
0x140008fc2  mov     r8, [rsp+360h+var_328]
0x140008fc7  xor     r10d, r10d
0x140008fca  jmp     loc_140008E81
0x140008fcf  mov     r8, [rsp+360h+var_328]
0x140008fd4  jmp     loc_140008E88
0x140008fd9  cmp     r15d, 1
0x140008fdd  jnz     loc_1400090B5
0x140008fe3  mov     rax, [rbx+20h]
0x140008fe7  lea     rcx, [rsp+360h+var_2F8]
0x140008fec  mov     qword ptr [rsp+360h+var_2F8], rax
0x140008ff1  mov     r9, r8
0x140008ff4  mov     rax, [rbx+28h]
0x140008ff8  lea     r8, ConnectedDeviceStrings
0x140008fff  mov     rdx, r14
0x140009002  mov     qword ptr [rsp+360h+var_2F8+8], rax
0x140009007  call    PackString
0x14000900c  mov     [rsp+360h+var_328], rax
0x140009011  mov     rcx, cs:WPP_GLOBAL_Control
0x140009018  lea     rdx, WPP_GLOBAL_Control
0x14000901f  cmp     rcx, rdx
0x140009022  jz      short loc_140009081
0x140009024  test    byte ptr [rcx+1Ch], 8
0x140009028  jz      short loc_14000904F
0x14000902a  mov     r9, [r14]
  ... truncated ...
```
