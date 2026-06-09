# DaRpcAddConnectedDevice

- ea: `0x140007860`
- end: `0x140007dc1`
- name: `DaRpcAddConnectedDevice`
- size: `1377`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140002bd8`
- `0x140002c00`
- `0x140002c40`
- `0x140002fbc`
- `0x140007860`
- `0x140009b80`
- `0x14000a0b0`
- `0x14000a524`
- `0x140018350`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x140007be2`
- `KERNEL32!GlobalAlloc` at `0x140007be2`
- `KERNEL32!EnterCriticalSection` at `0x140007a2e`
- `KERNEL32!EnterCriticalSection` at `0x140007a2e`
- `KERNEL32!LeaveCriticalSection` at `0x140007c21`
- `KERNEL32!LeaveCriticalSection` at `0x140007d29`
- `KERNEL32!LeaveCriticalSection` at `0x140007c21`
- `KERNEL32!LeaveCriticalSection` at `0x140007d29`
- `msvcrt!strcpy_s` at `0x140007d01`
- `msvcrt!strcpy_s` at `0x140007d01`
- `msvcrt!wcstombs` at `0x140007b75`
- `msvcrt!wcstombs` at `0x140007b75`
- `msvcrt!wcschr` at `0x140007b58`
- `msvcrt!wcschr` at `0x140007b58`
- `msvcrt!wcspbrk` at `0x140007b3d`
- `msvcrt!wcspbrk` at `0x140007b3d`
- `msvcrt!wcsncpy_s` at `0x140007afe`
- `msvcrt!wcsncpy_s` at `0x140007afe`
- `msvcrt!_wcsicmp` at `0x140007a61`
- `msvcrt!_wcsicmp` at `0x140007a61`
- `msvcrt!wcscpy_s` at `0x140007c71`
- `msvcrt!wcscpy_s` at `0x140007cdd`
- `msvcrt!wcscpy_s` at `0x140007cee`
- `msvcrt!wcscpy_s` at `0x140007c71`
- `msvcrt!wcscpy_s` at `0x140007cdd`
- `msvcrt!wcscpy_s` at `0x140007cee`
- `ntdll!RtlCopyLuid` at `0x140007c53`
- `ntdll!RtlCopyLuid` at `0x140007c53`
- `RPCRT4!RpcImpersonateClient` at `0x140007958`
- `RPCRT4!RpcImpersonateClient` at `0x140007958`

## pseudocode

```c
__int64 __fastcall DaRpcAddConnectedDevice(
        __int64 a1,
        unsigned int a2,
        const wchar_t *a3,
        unsigned int a4,
        wchar_t *Source,
        int a6,
        wchar_t *String2,
        LONG a8)
{
  const wchar_t *v8; // rsi
  unsigned int v9; // r14d
  const wchar_t *v10; // rax
  RPC_STATUS v11; // eax
  int Luid; // eax
  __int64 v14; // rcx
  void *v15; // rcx
  unsigned int v16; // edi
  _QWORD *v17; // rcx
  int v18; // edx
  HGLOBAL v19; // rdi
  const wchar_t *v20; // rcx
  wchar_t *v21; // rdi
  wchar_t *v22; // rax
  size_t v23; // rax
  __int64 v24; // rcx
  struct _LUID *v25; // rax
  struct _LUID *v26; // rdi
  wchar_t *v27; // rcx
  HGLOBAL v28; // rax
  struct _LUID SourceLuid; // [rsp+48h] [rbp-B8h] BYREF
  rsize_t v31; // [rsp+50h] [rbp-B0h]
  __int64 v32; // [rsp+58h] [rbp-A8h]
  rsize_t SizeInBytes; // [rsp+60h] [rbp-A0h]
  char v34[24]; // [rsp+68h] [rbp-98h] BYREF
  char Dest[272]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t Destination[2]; // [rsp+190h] [rbp+90h] BYREF
  wchar_t String[262]; // [rsp+194h] [rbp+94h] BYREF

  v8 = a3;
  v9 = a2;
  LODWORD(v31) = a6;
  SourceLuid = 0;
  strcpy(v34, "DaRpcAddConnectedDevice");
  if ( a4 && Source && a6 && String2 )
  {
    if ( !a2 || !a3 || !*a3 )
    {
      v8 = 0;
      v9 = 0;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = L"(null)";
      if ( v8 )
        v10 = v8;
      WPP_SF_sSSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v10, (__int64)Source, (__int64)String2);
    }
    v11 = RpcImpersonateClient(0);
    if ( v11 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          (unsigned int)&WPP_4b94345935ba3175354bb878a9e98408_Traceguids,
          (unsigned int)v34,
          v11);
      return 5;
    }
    Luid = GetLuid(&SourceLuid);
    if ( Luid < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          &WPP_4b94345935ba3175354bb878a9e98408_Traceguids,
          (unsigned int)Luid);
      SafeRpcRevertToSelf(v15, 192);
      return 5;
    }
    v16 = SafeRpcRevertToSelf(v14, 199);
    if ( v16 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        return v16;
      v18 = 18;
LABEL_28:
      WPP_SF_sd(v17[2], v18, (unsigned int)&WPP_4b94345935ba3175354bb878a9e98408_Traceguids, (unsigned int)v34, v16);
      return v16;
    }
    EnterCriticalSection(&DeviceListCS);
    v19 = pDeviceList;
    if ( pDeviceList )
    {
      do
      {
        if ( SourceLuid.LowPart == *(_DWORD *)v19 && SourceLuid.HighPart == *((_DWORD *)v19 + 1) )
        {
          v20 = (const wchar_t *)*((_QWORD *)v19 + 6);
          if ( v20 )
          {
            if ( !_wcsicmp(v20, String2) )
              break;
          }
        }
        v19 = (HGLOBAL)*((_QWORD *)v19 + 8);
      }
      while ( v19 );
      if ( v19 )
      {
        if ( v8 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids, v34);
          v16 = 85;
        }
        else
        {
          ++*((_DWORD *)v19 + 2);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids, v34);
          v16 = 0;
        }
LABEL_62:
        LeaveCriticalSection(&DeviceListCS);
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          return v16;
        v18 = 24;
        goto LABEL_28;
      }
    }
    wcsncpy_s(Destination, 0x104u, Source, 0x103u);
    Dest[259] = 0;
    String[257] = 0;
    if ( Destination[0] == 92 && Destination[1] == 92 )
    {
      v21 = String;
      v22 = wcspbrk(String, L"\\/");
    }
    else
    {
      v21 = Destination;
      v22 = wcschr(Destination, 0x3Au);
    }
    if ( v22 )
      *v22 = 0;
    v23 = wcstombs(Dest, v21, 0x103u);
    v24 = -1;
    if ( v23 == -1 )
    {
      v16 = 87;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids);
      goto LABEL_62;
    }
    do
      ++v24;
    while ( Dest[v24] );
    SizeInBytes = (unsigned int)(v24 + 1);
    v32 = v9 + a6 + a4;
    v25 = (struct _LUID *)GlobalAlloc(0x40u, SizeInBytes + 2 * (v32 + 40));
    v26 = v25;
    if ( !v25 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids);
      v16 = 8;
      goto LABEL_62;
    }
    RtlCopyLuid(v25, &SourceLuid);
    if ( v8 )
    {
      v26[4] = (struct _LUID)&v26[10];
      wcscpy_s((wchar_t *)&v26[10], v9, v8);
    }
    else
    {
      v26[4] = 0;
    }
    v26[1].HighPart = a8;
    v26[8] = 0;
    v26[9] = 0;
    v26[2].LowPart = a8 == 2;
    v26[2].HighPart = 0;
    v27 = (wchar_t *)&v26[10] + v9;
    v26[3] = 0;
    v26[1].LowPart = 1;
    v26[5] = (struct _LUID)v27;
    v26[6] = (struct _LUID)((char *)&v26[10] + 2 * a4 + 2 * v9);
    v26[7] = (struct _LUID)((char *)&v26[10] + 2 * v32);
    wcscpy_s(v27, a4, Source);
    wcscpy_s(*(wchar_t **)&v26[6], (unsigned int)v31, String2);
    strcpy_s(*(char **)&v26[7], SizeInBytes, Dest);
    v28 = pDeviceList;
    if ( pDeviceList )
    {
      *((_QWORD *)pDeviceList + 9) = v26;
      v26[8] = (struct _LUID)v28;
    }
    pDeviceList = v26;
    LeaveCriticalSection(&DeviceListCS);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids, v34);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids, v34);
    return 87;
  }
}

```

## disassembly

```asm
0x140007860  mov     [rsp-8+arg_0], rbx
0x140007865  push    rbp
0x140007866  push    rsi
0x140007867  push    rdi
0x140007868  push    r12
0x14000786a  push    r13
0x14000786c  push    r14
0x14000786e  push    r15
0x140007870  lea     rbp, [rsp-2B0h]
0x140007878  sub     rsp, 3B0h
0x14000787f  mov     rax, cs:__security_cookie
0x140007886  xor     rax, rsp
0x140007889  mov     [rbp+2E0h+var_40], rax
0x140007890  movsd   xmm1, qword ptr cs:aDarpcaddconnec+10h; "dDevice"
0x140007898  mov     rsi, r8
0x14000789b  mov     r13d, [rbp+2E0h+arg_28]
0x1400078a2  mov     r14d, edx
0x1400078a5  mov     r12, [rbp+2E0h+Source]
0x1400078ac  mov     r15, [rbp+2E0h+String2]
0x1400078b3  mov     dword ptr [rsp+3E0h+SizeInWords], r9d
0x1400078b8  mov     dword ptr [rsp+3E0h+var_390], r13d
0x1400078bd  movsd   qword ptr [rsp+3E0h+var_378+10h], xmm1
0x1400078c3  mov     qword ptr [rsp+3E0h+SourceLuid.LowPart], 0
0x1400078cc  movups  xmm0, xmmword ptr cs:aDarpcaddconnec; "DaRpcAddConnectedDevice"
0x1400078d3  movups  xmmword ptr [rsp+3E0h+var_378], xmm0
0x1400078d8  test    r9d, r9d
0x1400078db  jz      loc_140007D5F
0x1400078e1  test    r12, r12
0x1400078e4  jz      loc_140007D5F
0x1400078ea  test    r13d, r13d
0x1400078ed  jz      loc_140007D5F
0x1400078f3  test    r15, r15
0x1400078f6  jz      loc_140007D5F
0x1400078fc  test    edx, edx
0x1400078fe  jz      short loc_14000790D
0x140007900  test    r8, r8
0x140007903  jz      short loc_14000790D
0x140007905  xor     eax, eax
0x140007907  cmp     ax, [r8]
0x14000790b  jnz     short loc_140007912
0x14000790d  xor     esi, esi
0x14000790f  xor     r14d, r14d
0x140007912  mov     rcx, cs:WPP_GLOBAL_Control
0x140007919  lea     rbx, WPP_GLOBAL_Control
0x140007920  cmp     rcx, rbx
0x140007923  jz      short loc_140007956
0x140007925  test    byte ptr [rcx+1Ch], 1
0x140007929  jz      short loc_140007956
0x14000792b  mov     rcx, [rcx+10h]; LoggerHandle
0x14000792f  lea     rax, aNull_0; "(null)"
0x140007936  test    rsi, rsi
0x140007939  mov     [rsp+3E0h+var_3B0], r15; __int64
0x14000793e  mov     [rsp+3E0h+var_3B8], r12; __int64
0x140007943  lea     r9, [rsp+3E0h+var_378]
0x140007948  cmovnz  rax, rsi
0x14000794c  mov     [rsp+3E0h+var_3C0], rax; __int64
0x140007951  call    WPP_SF_sSSS
0x140007956  xor     ecx, ecx; BindingHandle
0x140007958  call    cs:__imp_RpcImpersonateClient
0x14000795e  test    eax, eax
0x140007960  jz      short loc_14000799C
0x140007962  mov     rcx, cs:WPP_GLOBAL_Control
0x140007969  cmp     rcx, rbx
0x14000796c  jz      short loc_140007992
0x14000796e  test    byte ptr [rcx+1Ch], 2
0x140007972  jz      short loc_140007992
0x140007974  mov     rcx, [rcx+10h]
0x140007978  lea     r9, [rsp+3E0h+var_378]
0x14000797d  mov     edx, 10h
0x140007982  mov     dword ptr [rsp+3E0h+var_3C0], eax
0x140007986  lea     r8, WPP_4b94345935ba3175354bb878a9e98408_Traceguids
0x14000798d  call    WPP_SF_sd
0x140007992  mov     eax, 5
0x140007997  jmp     loc_140007D97
0x14000799c  lea     rcx, [rsp+3E0h+SourceLuid]; DestinationLuid
0x1400079a1  call    GetLuid
0x1400079a6  test    eax, eax
0x1400079a8  jns     short loc_1400079E0
0x1400079aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400079b1  cmp     rcx, rbx
0x1400079b4  jz      short loc_1400079D4
0x1400079b6  test    byte ptr [rcx+1Ch], 2
0x1400079ba  jz      short loc_1400079D4
0x1400079bc  mov     rcx, [rcx+10h]
0x1400079c0  lea     r8, WPP_4b94345935ba3175354bb878a9e98408_Traceguids
0x1400079c7  mov     edx, 11h
0x1400079cc  mov     r9d, eax
0x1400079cf  call    WPP_SF_d
0x1400079d4  mov     edx, 0C0h
0x1400079d9  call    SafeRpcRevertToSelf
0x1400079de  jmp     short loc_140007992
0x1400079e0  mov     edx, 0C7h
0x1400079e5  call    SafeRpcRevertToSelf
0x1400079ea  mov     edi, eax
0x1400079ec  test    eax, eax
0x1400079ee  jz      short loc_140007A27
0x1400079f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400079f7  cmp     rcx, rbx
0x1400079fa  jz      short loc_140007A20
0x1400079fc  test    byte ptr [rcx+1Ch], 2
0x140007a00  jz      short loc_140007A20
0x140007a02  mov     edx, 12h
0x140007a07  mov     rcx, [rcx+10h]
0x140007a0b  lea     r9, [rsp+3E0h+var_378]
0x140007a10  lea     r8, WPP_4b94345935ba3175354bb878a9e98408_Traceguids
0x140007a17  mov     dword ptr [rsp+3E0h+var_3C0], edi
0x140007a1b  call    WPP_SF_sd
0x140007a20  mov     eax, edi
0x140007a22  jmp     loc_140007D97
0x140007a27  lea     rcx, DeviceListCS; lpCriticalSection
0x140007a2e  call    cs:__imp_EnterCriticalSection
0x140007a34  mov     rdi, cs:pDeviceList
0x140007a3b  test    rdi, rdi
0x140007a3e  jz      loc_140007AEA
0x140007a44  mov     eax, [rdi]
0x140007a46  cmp     [rsp+3E0h+SourceLuid.LowPart], eax
0x140007a4a  jnz     short loc_140007A6B
0x140007a4c  mov     eax, [rdi+4]
0x140007a4f  cmp     [rsp+3E0h+SourceLuid.HighPart], eax
0x140007a53  jnz     short loc_140007A6B
0x140007a55  mov     rcx, [rdi+30h]; String1
0x140007a59  test    rcx, rcx
0x140007a5c  jz      short loc_140007A6B
0x140007a5e  mov     rdx, r15; String2
0x140007a61  call    cs:__imp__wcsicmp
0x140007a67  test    eax, eax
0x140007a69  jz      short loc_140007A74
0x140007a6b  mov     rdi, [rdi+40h]
0x140007a6f  test    rdi, rdi
0x140007a72  jnz     short loc_140007A44
0x140007a74  test    rdi, rdi
0x140007a77  jz      short loc_140007AEA
0x140007a79  test    rsi, rsi
0x140007a7c  jz      short loc_140007AB4
0x140007a7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140007a85  cmp     rcx, rbx
0x140007a88  jz      short loc_140007AAA
0x140007a8a  test    byte ptr [rcx+1Ch], 4
0x140007a8e  jz      short loc_140007AAA
0x140007a90  mov     rcx, [rcx+10h]
0x140007a94  lea     r9, [rsp+3E0h+var_378]
0x140007a99  mov     edx, 13h
0x140007a9e  lea     r8, WPP_4b94345935ba3175354bb878a9e98408_Traceguids
0x140007aa5  call    WPP_SF_s
0x140007aaa  mov     edi, 55h ; 'U'
0x140007aaf  jmp     loc_140007C1A
0x140007ab4  inc     dword ptr [rdi+8]
0x140007ab7  mov     rcx, cs:WPP_GLOBAL_Control
0x140007abe  cmp     rcx, rbx
0x140007ac1  jz      short loc_140007AE3
0x140007ac3  test    byte ptr [rcx+1Ch], 1
0x140007ac7  jz      short loc_140007AE3
0x140007ac9  mov     rcx, [rcx+10h]
0x140007acd  lea     r9, [rsp+3E0h+var_378]
0x140007ad2  mov     edx, 14h
0x140007ad7  lea     r8, WPP_4b94345935ba3175354bb878a9e98408_Traceguids
0x140007ade  call    WPP_SF_s
0x140007ae3  xor     edi, edi
0x140007ae5  jmp     loc_140007C1A
0x140007aea  mov     r9d, 103h; MaxCount
0x140007af0  lea     rcx, [rbp+2E0h+Destination]; Destination
0x140007af7  mov     r8, r12; Source
0x140007afa  lea     edx, [r9+1]; SizeInWords
0x140007afe  call    cs:__imp_wcsncpy_s
0x140007b04  xor     eax, eax
0x140007b06  mov     [rbp+2E0h+var_25D], 0
0x140007b0d  cmp     [rbp+2E0h+Destination], 5Ch ; '\'
0x140007b15  mov     [rbp+2E0h+var_4A], ax
0x140007b1c  jnz     short loc_140007B45
0x140007b1e  cmp     [rbp+2E0h+var_24E], 5Ch ; '\'
0x140007b26  jnz     short loc_140007B45
0x140007b28  lea     rdx, Control; "\\/"
0x140007b2f  lea     rcx, [rbp+2E0h+String]; String
0x140007b36  lea     rdi, [rbp+2E0h+String]
0x140007b3d  call    cs:__imp_wcspbrk
0x140007b43  jmp     short loc_140007B5E
0x140007b45  mov     edx, 3Ah ; ':'; Ch
0x140007b4a  lea     rcx, [rbp+2E0h+Destination]; Str
0x140007b51  lea     rdi, [rbp+2E0h+Destination]
0x140007b58  call    cs:__imp_wcschr
0x140007b5e  test    rax, rax
0x140007b61  jz      short loc_140007B68
0x140007b63  xor     ecx, ecx
0x140007b65  mov     [rax], cx
0x140007b68  mov     r8d, 103h; MaxCount
0x140007b6e  lea     rcx, [rbp+2E0h+Dest]; Dest
0x140007b72  mov     rdx, rdi; Source
0x140007b75  call    cs:__imp_wcstombs
0x140007b7b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140007b7f  cmp     rax, rcx
0x140007b82  jnz     short loc_140007BB2
0x140007b84  lea     edi, [rcx+58h]
0x140007b87  mov     rcx, cs:WPP_GLOBAL_Control
0x140007b8e  cmp     rcx, rbx
0x140007b91  jz      loc_140007C1A
0x140007b97  test    byte ptr [rcx+1Ch], 2
0x140007b9b  jz      short loc_140007C1A
0x140007b9d  mov     rcx, [rcx+10h]
0x140007ba1  lea     edx, [rdi-42h]
0x140007ba4  lea     r8, WPP_4b94345935ba3175354bb878a9e98408_Traceguids
0x140007bab  call    WPP_SF_
0x140007bb0  jmp     short loc_140007C1A
0x140007bb2  lea     rax, [rbp+2E0h+Dest]
0x140007bb6  inc     rcx
0x140007bb9  cmp     byte ptr [rax+rcx], 0
0x140007bbd  jnz     short loc_140007BB6
0x140007bbf  mov     eax, dword ptr [rsp+3E0h+SizeInWords]
0x140007bc3  inc     ecx
0x140007bc5  add     eax, r13d
0x140007bc8  mov     [rsp+3E0h+SizeInBytes], rcx
0x140007bcd  add     eax, r14d
0x140007bd0  mov     [rsp+3E0h+var_388], rax
0x140007bd5  add     rax, 28h ; '('
0x140007bd9  lea     rdx, [rcx+rax*2]; dwBytes
0x140007bdd  mov     ecx, 40h ; '@'; uFlags
0x140007be2  call    cs:__imp_GlobalAlloc
0x140007be8  mov     rdi, rax
0x140007beb  test    rax, rax
0x140007bee  jnz     short loc_140007C4B
0x140007bf0  mov     rcx, cs:WPP_GLOBAL_Control
0x140007bf7  cmp     rcx, rbx
0x140007bfa  jz      short loc_140007C15
0x140007bfc  test    byte ptr [rcx+1Ch], 2
0x140007c00  jz      short loc_140007C15
0x140007c02  mov     rcx, [rcx+10h]
0x140007c06  lea     edx, [rax+16h]
0x140007c09  lea     r8, WPP_4b94345935ba3175354bb878a9e98408_Traceguids
0x140007c10  call    WPP_SF_
0x140007c15  mov     edi, 8
0x140007c1a  lea     rcx, DeviceListCS; lpCriticalSection
0x140007c21  call    cs:__imp_LeaveCriticalSection
0x140007c27  mov     rcx, cs:WPP_GLOBAL_Control
0x140007c2e  cmp     rcx, rbx
0x140007c31  jz      loc_140007A20
0x140007c37  test    byte ptr [rcx+1Ch], 2
0x140007c3b  jz      loc_140007A20
0x140007c41  mov     edx, 18h
0x140007c46  jmp     loc_140007A07
0x140007c4b  lea     rdx, [rsp+3E0h+SourceLuid]; SourceLuid
0x140007c50  mov     rcx, rdi; DestinationLuid
0x140007c53  call    cs:__imp_RtlCopyLuid
0x140007c59  xor     edx, edx
0x140007c5b  mov     r13d, r14d
0x140007c5e  test    rsi, rsi
0x140007c61  jz      short loc_140007C7B
0x140007c63  lea     rcx, [rdi+50h]; Destination
0x140007c67  mov     r8, rsi; Source
0x140007c6a  mov     edx, r13d; SizeInWords
0x140007c6d  mov     [rdi+20h], rcx
0x140007c71  call    cs:__imp_wcscpy_s
0x140007c77  xor     edx, edx
0x140007c79  jmp     short loc_140007C7F
0x140007c7b  mov     [rdi+20h], rdx
0x140007c7f  mov     eax, [rbp+2E0h+arg_38]
0x140007c85  mov     ecx, edx
0x140007c87  cmp     eax, 2
0x140007c8a  mov     [rdi+0Ch], eax
0x140007c8d  mov     [rdi+40h], rdx
0x140007c91  mov     r8, r12; Source
0x140007c94  setz    cl
0x140007c97  mov     [rdi+48h], rdx
0x140007c9b  mov     [rdi+10h], ecx
0x140007c9e  lea     rcx, [r13+28h]
0x140007ca2  mov     [rdi+14h], edx
0x140007ca5  lea     rcx, [rdi+rcx*2]; Destination
0x140007ca9  mov     [rdi+18h], rdx
0x140007cad  mov     edx, dword ptr [rsp+3E0h+SizeInWords]; SizeInWords
0x140007cb1  mov     dword ptr [rdi+8], 1
0x140007cb8  mov     [rdi+28h], rcx
0x140007cbc  lea     r9d, [rdx+r14]
0x140007cc0  lea     r9, [r9+28h]
0x140007cc4  lea     rax, [rdi+r9*2]
0x140007cc8  mov     [rdi+30h], rax
0x140007ccc  mov     rax, [rsp+3E0h+var_388]
0x140007cd1  add     rax, 28h ; '('
0x140007cd5  lea     rax, [rdi+rax*2]
0x140007cd9  mov     [rdi+38h], rax
0x140007cdd  call    cs:__imp_wcscpy_s
0x140007ce3  mov     edx, dword ptr [rsp+3E0h+var_390]; SizeInWords
0x140007ce7  mov     r8, r15; Source
0x140007cea  mov     rcx, [rdi+30h]; Destination
0x140007cee  call    cs:__imp_wcscpy_s
0x140007cf4  mov     rdx, [rsp+3E0h+SizeInBytes]; SizeInBytes
0x140007cf9  lea     r8, [rbp+2E0h+Dest]; Source
0x140007cfd  mov     rcx, [rdi+38h]; Destination
0x140007d01  call    cs:__imp_strcpy_s
0x140007d07  mov     rax, cs:pDeviceList
0x140007d0e  test    rax, rax
0x140007d11  jz      short loc_140007D1B
0x140007d13  mov     [rax+48h], rdi
0x140007d17  mov     [rdi+40h], rax
0x140007d1b  lea     rcx, DeviceListCS; lpCriticalSection
0x140007d22  mov     cs:pDeviceList, rdi
0x140007d29  call    cs:__imp_LeaveCriticalSection
0x140007d2f  mov     rcx, cs:WPP_GLOBAL_Control
0x140007d36  cmp     rcx, rbx
0x140007d39  jz      short loc_140007D5B
0x140007d3b  test    byte ptr [rcx+1Ch], 1
0x140007d3f  jz      short loc_140007D5B
0x140007d41  mov     rcx, [rcx+10h]
  ... truncated ...
```
