# SupplicantSetAuthParams

- ea: `0x180011310`
- end: `0x1800119d1`
- name: `SupplicantSetAuthParams`
- size: `1729`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x180011190`

## callees

- `0x180005440`
- `0x180007f60`
- `0x1800091c4`
- `0x180010ae0`
- `0x180011310`
- `0x1800119d8`
- `0x180019300`
- `0x18001a6cc`
- `0x1800214f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011661`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011661`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180011657`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180011657`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011763`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011936`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011763`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011936`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180011625`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001162e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180011625`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001162e`
- `MobileNetworking!SetBufferAndLength` at `0x1800113f4`
- `MobileNetworking!SetBufferAndLength` at `0x18001153a`
- `MobileNetworking!SetBufferAndLength` at `0x1800113f4`
- `MobileNetworking!SetBufferAndLength` at `0x18001153a`
- `MobileNetworking!FreeMemory` at `0x18001178e`
- `MobileNetworking!FreeMemory` at `0x1800117bf`
- `MobileNetworking!FreeMemory` at `0x1800117ea`
- `MobileNetworking!FreeMemory` at `0x180011951`
- `MobileNetworking!FreeMemory` at `0x18001196c`
- `MobileNetworking!FreeMemory` at `0x180011984`
- `MobileNetworking!FreeMemory` at `0x18001178e`
- `MobileNetworking!FreeMemory` at `0x1800117bf`
- `MobileNetworking!FreeMemory` at `0x1800117ea`
- `MobileNetworking!FreeMemory` at `0x180011951`
- `MobileNetworking!FreeMemory` at `0x18001196c`
- `MobileNetworking!FreeMemory` at `0x180011984`

## string_xrefs

- `0x180011780`: `SetUserTokenInfo`

## pseudocode

```c
__int64 __fastcall SupplicantSetAuthParams(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v5; // r13d
  _QWORD *v6; // rcx
  unsigned int v7; // edi
  __int64 v8; // rsi
  unsigned int v9; // r14d
  DWORD v10; // eax
  DWORD v11; // edi
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  unsigned int v14; // esi
  __int64 v15; // rdi
  unsigned int v16; // r14d
  DWORD v17; // eax
  DWORD v18; // eax
  void *v19; // rsi
  HANDLE CurrentProcess; // rdi
  HANDLE v21; // rax
  DWORD LastError; // eax
  DWORD v23; // eax
  DWORD UserAndDomainName; // eax
  int v25; // esi
  void *v26; // rcx
  __int64 v27; // r12
  LPWSTR v28; // r14
  PSID *v29; // r15
  HANDLE v30; // rdi
  bool v31; // zf
  _QWORD *v32; // rcx
  __int64 v33; // rdi
  unsigned int v34; // ebx
  DWORD v35; // eax
  _QWORD v37[9]; // [rsp+40h] [rbp-48h] BYREF
  HANDLE TargetHandle; // [rsp+90h] [rbp+8h] BYREF
  PSID *v39; // [rsp+A0h] [rbp+18h] BYREF
  LPWSTR v40; // [rsp+A8h] [rbp+20h] BYREF

  v5 = *(_DWORD *)(*(_QWORD *)(a1 + 88) + 20LL);
  TargetHandle = 0;
  v39 = 0;
  v40 = 0;
  v37[0] = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 70, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  v7 = *(_DWORD *)(a3 + 4);
  v8 = a3 + *(unsigned int *)(a3 + 8);
  v9 = *(_DWORD *)(*(_QWORD *)a1 + 20LL);
  if ( v6 != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)v6 + 17) & 0x800) != 0 )
    {
      WPP_SF_(v6[7], 29, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 68) & 0x10) != 0 )
      WPP_SF_dd(v6[7], 30, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids, v9, v7);
  }
  v10 = SetBufferAndLength(a1 + 360, a1 + 352, v8, v7);
  v11 = v10;
  if ( !v10 )
    goto LABEL_14;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_96;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 31, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids, v9, v10);
LABEL_14:
    v12 = WPP_GLOBAL_Control;
  }
  if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 17) & 0x800) != 0 )
  {
    WPP_SF_D(v12[7], 32, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids, v11);
    v12 = WPP_GLOBAL_Control;
  }
  if ( v11 )
  {
    if ( v12 == &WPP_GLOBAL_Control || (*((_BYTE *)v12 + 68) & 1) == 0 )
      goto LABEL_96;
    v13 = 71;
    goto LABEL_95;
  }
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 68) & 4) != 0 )
    WPP_SF_d(v12[7], 72, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids, v5);
  *(_DWORD *)(a1 + 284) = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 73, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids, v5);
  *(_DWORD *)(a1 + 292) = 0;
  if ( (*(_BYTE *)(a3 + 20) & 4) == 0 )
  {
    v18 = SupplicantSetDefaultUserProfile(a1);
    v11 = v18;
    if ( v18 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 75, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids, v5, v18);
      goto LABEL_96;
    }
    goto LABEL_48;
  }
  v14 = *(_DWORD *)(a3 + 40);
  v15 = a3 + *(unsigned int *)(a3 + 44);
  v16 = *(_DWORD *)(*(_QWORD *)a1 + 20LL);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 40, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids);
  v17 = SetBufferAndLength(a1 + 376, a1 + 368, v15, v14);
  v11 = v17;
  if ( v17 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_96;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_37;
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 41, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids, v16, v17);
  }
  v12 = WPP_GLOBAL_Control;
LABEL_37:
  if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 17) & 0x800) != 0 )
  {
    WPP_SF_D(v12[7], 42, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids, v11);
    v12 = WPP_GLOBAL_Control;
  }
  if ( v11 )
  {
    if ( v12 == &WPP_GLOBAL_Control || (*((_BYTE *)v12 + 68) & 1) == 0 )
      goto LABEL_96;
    v13 = 74;
    goto LABEL_95;
  }
LABEL_48:
  if ( *(_DWORD *)(a3 + 12) == 2 && (*(_BYTE *)(a3 + 20) & 2) != 0 && *(_QWORD *)(a3 + 32) )
  {
    v19 = *(void **)(a3 + 32);
    CurrentProcess = GetCurrentProcess();
    v21 = GetCurrentProcess();
    if ( !DuplicateHandle(v21, v19, CurrentProcess, &TargetHandle, 0, 0, 2u) )
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          WPP_SF_dd(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            76,
            WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids,
            v5,
            LastError);
        goto LABEL_96;
      }
    }
    v23 = OneXGetTokenInformation(TargetHandle, (LPVOID *)&v39);
    v11 = v23;
    if ( v23 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 77, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids, v5, v23);
      goto LABEL_96;
    }
    UserAndDomainName = GetUserAndDomainName(v5, v39, &v40, v37);
    v11 = UserAndDomainName;
    if ( UserAndDomainName )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          78,
          WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids,
          v5,
          UserAndDomainName);
      goto LABEL_96;
    }
  }
  v25 = -1;
  if ( (*(_BYTE *)(a3 + 20) & 1) != 0 )
    v25 = *(_DWORD *)(a3 + 24);
  v26 = *(void **)(a1 + 456);
  v27 = v37[0];
  v28 = v40;
  v29 = v39;
  v30 = TargetHandle;
  *(_DWORD *)(a1 + 444) = *(_DWORD *)(a3 + 12);
  if ( v26 )
    CloseHandle(v26);
  v31 = *(_QWORD *)(a1 + 464) == 0;
  *(_QWORD *)(a1 + 456) = v30;
  if ( !v31 )
    FreeMemory(a1 + 464, "SetUserTokenInfo", 147);
  v31 = *(_QWORD *)(a1 + 472) == 0;
  *(_QWORD *)(a1 + 464) = v29;
  *(_DWORD *)(a1 + 448) = v25;
  if ( !v31 )
    FreeMemory(a1 + 472, "SetUserName", 156);
  v31 = *(_QWORD *)(a1 + 480) == 0;
  *(_QWORD *)(a1 + 472) = v28;
  if ( !v31 )
    FreeMemory(a1 + 480, "SetDomainName", 170);
  *(_QWORD *)(a1 + 480) = v27;
  v32 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 65, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids);
      v32 = WPP_GLOBAL_Control;
    }
    if ( v32 != &WPP_GLOBAL_Control && (*((_DWORD *)v32 + 17) & 0x800) != 0 )
    {
      WPP_SF_D(v32[7], 66, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids, 0);
      v32 = WPP_GLOBAL_Control;
    }
  }
  v33 = a1 + 112;
  v34 = *(_DWORD *)(*(_QWORD *)(a1 + 88) + 20LL);
  if ( v32 != &WPP_GLOBAL_Control && (*((_DWORD *)v32 + 17) & 0x800) != 0 )
    WPP_SF_(v32[7], 67, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids);
  v35 = EapSetAuthParams(v33);
  v11 = v35;
  if ( !v35 )
    goto LABEL_87;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_91;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 68, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids, v34, v35);
LABEL_87:
    v12 = WPP_GLOBAL_Control;
  }
  if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 17) & 0x800) != 0 )
  {
    WPP_SF_D(v12[7], 69, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids, v11);
    v12 = WPP_GLOBAL_Control;
  }
LABEL_91:
  if ( !v11 )
    goto LABEL_99;
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 68) & 1) != 0 )
  {
    v13 = 80;
LABEL_95:
    WPP_SF_dd(v12[7], v13, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids, v5, v11);
  }
LABEL_96:
  if ( TargetHandle )
    CloseHandle(TargetHandle);
  FreeMemory(&v39, "SupplicantSetAuthParams", 607);
  FreeMemory(&v40, "SupplicantSetAuthParams", 608);
  FreeMemory(v37, "SupplicantSetAuthParams", 609);
  v12 = WPP_GLOBAL_Control;
LABEL_99:
  if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 17) & 0x800) != 0 )
    WPP_SF_D(v12[7], 81, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x180011310  mov     r11, rsp
0x180011313  mov     [r11+10h], rbx
0x180011317  push    rbp
0x180011318  push    rsi
0x180011319  push    rdi
0x18001131a  push    r12
0x18001131c  push    r13
0x18001131e  push    r14
0x180011320  push    r15
0x180011322  sub     rsp, 50h
0x180011326  mov     rax, [rcx+58h]
0x18001132a  xor     r12d, r12d
0x18001132d  mov     rbp, r8
0x180011330  mov     rbx, rcx
0x180011333  mov     r13d, [rax+14h]
0x180011337  mov     [r11+8], r12
0x18001133b  mov     [r11+18h], r12
0x18001133f  mov     [r11+20h], r12
0x180011343  mov     [r11-48h], r12
0x180011347  mov     rcx, cs:WPP_GLOBAL_Control
0x18001134e  lea     r15, WPP_GLOBAL_Control
0x180011355  cmp     rcx, r15
0x180011358  jz      short loc_18001137F
0x18001135a  test    dword ptr [rcx+44h], 800h
0x180011361  jz      short loc_18001137F
0x180011363  mov     rcx, [rcx+38h]
0x180011367  lea     r8, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids
0x18001136e  mov     edx, 46h ; 'F'
0x180011373  call    WPP_SF_
0x180011378  mov     rcx, cs:WPP_GLOBAL_Control
0x18001137f  mov     rax, [rbx]
0x180011382  mov     esi, [rbp+8]
0x180011385  mov     edi, [rbp+4]
0x180011388  add     rsi, rbp
0x18001138b  mov     r14d, [rax+14h]
0x18001138f  cmp     rcx, r15
0x180011392  jz      short loc_1800113E0
0x180011394  test    dword ptr [rcx+44h], 800h
0x18001139b  jz      short loc_1800113B9
0x18001139d  mov     rcx, [rcx+38h]
0x1800113a1  lea     r8, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids
0x1800113a8  mov     edx, 1Dh
0x1800113ad  call    WPP_SF_
0x1800113b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800113b9  cmp     rcx, r15
0x1800113bc  jz      short loc_1800113E0
0x1800113be  test    byte ptr [rcx+44h], 10h
0x1800113c2  jz      short loc_1800113E0
0x1800113c4  mov     rcx, [rcx+38h]
0x1800113c8  lea     r8, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids
0x1800113cf  mov     edx, 1Eh
0x1800113d4  mov     [rsp+88h+dwDesiredAccess], edi
0x1800113d8  mov     r9d, r14d
0x1800113db  call    WPP_SF_dd
0x1800113e0  lea     rdx, [rbx+160h]
0x1800113e7  mov     r9d, edi
0x1800113ea  lea     rcx, [rbx+168h]
0x1800113f1  mov     r8, rsi
0x1800113f4  call    cs:__imp_SetBufferAndLength
0x1800113fa  mov     edi, eax
0x1800113fc  test    eax, eax
0x1800113fe  jz      short loc_180011432
0x180011400  mov     rcx, cs:WPP_GLOBAL_Control
0x180011407  cmp     rcx, r15
0x18001140a  jz      loc_180011929
0x180011410  test    byte ptr [rcx+44h], 1
0x180011414  jz      short loc_180011439
0x180011416  mov     rcx, [rcx+38h]
0x18001141a  lea     r8, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids
0x180011421  mov     edx, 1Fh
0x180011426  mov     [rsp+88h+dwDesiredAccess], eax
0x18001142a  mov     r9d, r14d
0x18001142d  call    WPP_SF_dd
0x180011432  mov     rcx, cs:WPP_GLOBAL_Control
0x180011439  cmp     rcx, r15
0x18001143c  jz      short loc_180011466
0x18001143e  test    dword ptr [rcx+44h], 800h
0x180011445  jz      short loc_180011466
0x180011447  mov     rcx, [rcx+38h]
0x18001144b  lea     r8, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids
0x180011452  mov     edx, 20h ; ' '
0x180011457  mov     r9d, edi
0x18001145a  call    WPP_SF_D
0x18001145f  mov     rcx, cs:WPP_GLOBAL_Control
0x180011466  test    edi, edi
0x180011468  jz      short loc_180011487
0x18001146a  cmp     rcx, r15
0x18001146d  jz      loc_180011929
0x180011473  test    byte ptr [rcx+44h], 1
0x180011477  jz      loc_180011929
0x18001147d  mov     edx, 47h ; 'G'
0x180011482  jmp     loc_180011912
0x180011487  cmp     rcx, r15
0x18001148a  jz      short loc_1800114AA
0x18001148c  test    byte ptr [rcx+44h], 4
0x180011490  jz      short loc_1800114AA
0x180011492  mov     rcx, [rcx+38h]
0x180011496  lea     r8, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids
0x18001149d  mov     edx, 48h ; 'H'
0x1800114a2  mov     r9d, r13d
0x1800114a5  call    WPP_SF_d
0x1800114aa  mov     [rbx+11Ch], r12d
0x1800114b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800114b8  cmp     rcx, r15
0x1800114bb  jz      short loc_1800114DB
0x1800114bd  test    byte ptr [rcx+44h], 4
0x1800114c1  jz      short loc_1800114DB
0x1800114c3  mov     rcx, [rcx+38h]
0x1800114c7  lea     r8, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids
0x1800114ce  mov     edx, 49h ; 'I'
0x1800114d3  mov     r9d, r13d
0x1800114d6  call    WPP_SF_d
0x1800114db  mov     [rbx+124h], r12d
0x1800114e2  test    byte ptr [rbp+14h], 4
0x1800114e6  jz      loc_1800115CD
0x1800114ec  mov     rax, [rbx]
0x1800114ef  mov     edi, [rbp+2Ch]
0x1800114f2  mov     esi, [rbp+28h]
0x1800114f5  add     rdi, rbp
0x1800114f8  mov     r14d, [rax+14h]
0x1800114fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180011503  cmp     rcx, r15
0x180011506  jz      short loc_180011526
0x180011508  test    dword ptr [rcx+44h], 800h
0x18001150f  jz      short loc_180011526
0x180011511  mov     rcx, [rcx+38h]
0x180011515  lea     r8, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids
0x18001151c  mov     edx, 28h ; '('
0x180011521  call    WPP_SF_
0x180011526  lea     rdx, [rbx+170h]
0x18001152d  mov     r9d, esi
0x180011530  lea     rcx, [rbx+178h]
0x180011537  mov     r8, rdi
0x18001153a  call    cs:__imp_SetBufferAndLength
0x180011540  mov     edi, eax
0x180011542  test    eax, eax
0x180011544  jz      short loc_180011578
0x180011546  mov     rcx, cs:WPP_GLOBAL_Control
0x18001154d  cmp     rcx, r15
0x180011550  jz      loc_180011929
0x180011556  test    byte ptr [rcx+44h], 1
0x18001155a  jz      short loc_18001157F
0x18001155c  mov     rcx, [rcx+38h]
0x180011560  lea     r8, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids
0x180011567  mov     edx, 29h ; ')'
0x18001156c  mov     [rsp+88h+dwDesiredAccess], eax
0x180011570  mov     r9d, r14d
0x180011573  call    WPP_SF_dd
0x180011578  mov     rcx, cs:WPP_GLOBAL_Control
0x18001157f  cmp     rcx, r15
0x180011582  jz      short loc_1800115AC
0x180011584  test    dword ptr [rcx+44h], 800h
0x18001158b  jz      short loc_1800115AC
0x18001158d  mov     rcx, [rcx+38h]
0x180011591  lea     r8, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids
0x180011598  mov     edx, 2Ah ; '*'
0x18001159d  mov     r9d, edi
0x1800115a0  call    WPP_SF_D
0x1800115a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800115ac  test    edi, edi
0x1800115ae  jz      short loc_180011603
0x1800115b0  cmp     rcx, r15
0x1800115b3  jz      loc_180011929
0x1800115b9  test    byte ptr [rcx+44h], 1
0x1800115bd  jz      loc_180011929
0x1800115c3  mov     edx, 4Ah ; 'J'
0x1800115c8  jmp     loc_180011912
0x1800115cd  mov     rcx, rbx
0x1800115d0  call    SupplicantSetDefaultUserProfile
0x1800115d5  mov     edi, eax
0x1800115d7  test    eax, eax
0x1800115d9  jz      short loc_180011603
0x1800115db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800115e2  cmp     rcx, r15
0x1800115e5  jz      loc_180011929
0x1800115eb  test    byte ptr [rcx+44h], 1
0x1800115ef  jz      loc_180011929
0x1800115f5  mov     edx, 4Bh ; 'K'
0x1800115fa  mov     [rsp+88h+dwDesiredAccess], eax
0x1800115fe  jmp     loc_180011916
0x180011603  cmp     dword ptr [rbp+0Ch], 2
0x180011607  jnz     loc_180011723
0x18001160d  test    byte ptr [rbp+14h], 2
0x180011611  jz      loc_180011723
0x180011617  cmp     [rbp+20h], r12
0x18001161b  jz      loc_180011723
0x180011621  mov     rsi, [rbp+20h]
0x180011625  call    cs:__imp_GetCurrentProcess
0x18001162b  mov     rdi, rax
0x18001162e  call    cs:__imp_GetCurrentProcess
0x180011634  mov     [rsp+88h+dwOptions], 2; dwOptions
0x18001163c  lea     r9, [rsp+88h+TargetHandle]; lpTargetHandle
0x180011644  mov     rcx, rax; hSourceProcessHandle
0x180011647  mov     [rsp+88h+bInheritHandle], r12d; bInheritHandle
0x18001164c  mov     r8, rdi; hTargetProcessHandle
0x18001164f  mov     [rsp+88h+dwDesiredAccess], r12d; dwDesiredAccess
0x180011654  mov     rdx, rsi; hSourceHandle
0x180011657  call    cs:__imp_DuplicateHandle
0x18001165d  test    eax, eax
0x18001165f  jnz     short loc_180011695
0x180011661  call    cs:__imp_GetLastError
0x180011667  mov     edi, eax
0x180011669  test    eax, eax
0x18001166b  jz      short loc_180011695
0x18001166d  mov     rcx, cs:WPP_GLOBAL_Control
0x180011674  cmp     rcx, r15
0x180011677  jz      loc_180011929
0x18001167d  test    byte ptr [rcx+44h], 1
0x180011681  jz      loc_180011929
0x180011687  mov     edx, 4Ch ; 'L'
0x18001168c  mov     [rsp+88h+dwDesiredAccess], eax
0x180011690  jmp     loc_180011916
0x180011695  mov     rcx, [rsp+88h+TargetHandle]; TokenHandle
0x18001169d  lea     rdx, [rsp+88h+arg_10]
0x1800116a5  call    OneXGetTokenInformation
0x1800116aa  mov     edi, eax
0x1800116ac  test    eax, eax
0x1800116ae  jz      short loc_1800116D8
0x1800116b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800116b7  cmp     rcx, r15
0x1800116ba  jz      loc_180011929
0x1800116c0  test    byte ptr [rcx+44h], 1
0x1800116c4  jz      loc_180011929
0x1800116ca  mov     edx, 4Dh ; 'M'
0x1800116cf  mov     [rsp+88h+dwDesiredAccess], eax
0x1800116d3  jmp     loc_180011916
0x1800116d8  mov     rdx, [rsp+88h+arg_10]
0x1800116e0  lea     r9, [rsp+88h+var_48]
0x1800116e5  lea     r8, [rsp+88h+arg_18]
0x1800116ed  mov     ecx, r13d
0x1800116f0  call    GetUserAndDomainName
0x1800116f5  mov     edi, eax
0x1800116f7  test    eax, eax
0x1800116f9  jz      short loc_180011723
0x1800116fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180011702  cmp     rcx, r15
0x180011705  jz      loc_180011929
0x18001170b  test    byte ptr [rcx+44h], 1
0x18001170f  jz      loc_180011929
0x180011715  mov     edx, 4Eh ; 'N'
0x18001171a  mov     [rsp+88h+dwDesiredAccess], eax
0x18001171e  jmp     loc_180011916
0x180011723  test    byte ptr [rbp+14h], 1
0x180011727  mov     esi, 0FFFFFFFFh
0x18001172c  jz      short loc_180011731
0x18001172e  mov     esi, [rbp+18h]
0x180011731  mov     rcx, [rbx+1C8h]; hObject
0x180011738  mov     eax, [rbp+0Ch]
0x18001173b  mov     r12, [rsp+88h+var_48]
0x180011740  mov     r14, [rsp+88h+arg_18]
0x180011748  mov     r15, [rsp+88h+arg_10]
0x180011750  mov     rdi, [rsp+88h+TargetHandle]
0x180011758  mov     [rbx+1BCh], eax
0x18001175e  test    rcx, rcx
0x180011761  jz      short loc_180011769
0x180011763  call    cs:__imp_CloseHandle
0x180011769  cmp     qword ptr [rbx+1D0h], 0
0x180011771  mov     [rbx+1C8h], rdi
0x180011778  jz      short loc_180011794
0x18001177a  mov     r8d, 93h
0x180011780  lea     rdx, aSetusertokenin; "SetUserTokenInfo"
0x180011787  lea     rcx, [rbx+1D0h]
0x18001178e  call    cs:__imp_FreeMemory
0x180011794  cmp     qword ptr [rbx+1D8h], 0
0x18001179c  mov     [rbx+1D0h], r15
0x1800117a3  mov     [rbx+1C0h], esi
0x1800117a9  jz      short loc_1800117C5
0x1800117ab  mov     r8d, 9Ch
0x1800117b1  lea     rdx, aSetusername; "SetUserName"
0x1800117b8  lea     rcx, [rbx+1D8h]
0x1800117bf  call    cs:__imp_FreeMemory
0x1800117c5  cmp     qword ptr [rbx+1E0h], 0
0x1800117cd  mov     [rbx+1D8h], r14
0x1800117d4  jz      short loc_1800117F0
0x1800117d6  mov     r8d, 0AAh
0x1800117dc  lea     rdx, aSetdomainname; "SetDomainName"
0x1800117e3  lea     rcx, [rbx+1E0h]
0x1800117ea  call    cs:__imp_FreeMemory
0x1800117f0  mov     [rbx+1E0h], r12
0x1800117f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800117fe  lea     r15, WPP_GLOBAL_Control
0x180011805  cmp     rcx, r15
0x180011808  jz      short loc_18001185C
0x18001180a  test    dword ptr [rcx+44h], 800h
0x180011811  jz      short loc_18001182F
0x180011813  mov     rcx, [rcx+38h]
0x180011817  lea     r8, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids
0x18001181e  mov     edx, 41h ; 'A'
0x180011823  call    WPP_SF_
0x180011828  mov     rcx, cs:WPP_GLOBAL_Control
0x18001182f  cmp     rcx, r15
0x180011832  jz      short loc_18001185C
0x180011834  test    dword ptr [rcx+44h], 800h
0x18001183b  jz      short loc_18001185C
0x18001183d  mov     rcx, [rcx+38h]
0x180011841  lea     r8, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids
0x180011848  mov     edx, 42h ; 'B'
0x18001184d  xor     r9d, r9d
0x180011850  call    WPP_SF_D
0x180011855  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
