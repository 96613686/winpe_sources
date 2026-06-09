# NPOpenEnum

- ea: `0x180002970`
- end: `0x1800033e0`
- name: `NPOpenEnum`
- size: `2672`
- prototype: `DWORD __stdcall(DWORD dwScope, DWORD dwType, DWORD dwUsage, LPNETRESOURCEW lpNetResource, LPHANDLE lphEnum)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x180002970`
- `0x1800033f0`
- `0x18000e494`
- `0x180010a14`
- `0x180010a3c`
- `0x180010a80`
- `0x180010aec`
- `0x180010b78`
- `0x180010be8`
- `0x180010c28`
- `0x180010e68`
- `0x180011244`
- `0x1800112fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ecc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003277`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ecc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003277`
- `KERNEL32!LocalAlloc` at `0x180002a66`
- `KERNEL32!LocalAlloc` at `0x180003269`
- `KERNEL32!LocalAlloc` at `0x180002a66`
- `KERNEL32!LocalAlloc` at `0x180003269`
- `KERNEL32!LocalFree` at `0x180002ab1`
- `KERNEL32!LocalFree` at `0x1800033a5`
- `KERNEL32!LocalFree` at `0x180002ab1`
- `KERNEL32!LocalFree` at `0x1800033a5`
- `DAVHLPR!DavCheckAndConvertHttpUrlToUncName` at `0x180002fae`
- `DAVHLPR!DavCheckAndConvertHttpUrlToUncName` at `0x180003145`
- `DAVHLPR!DavCheckAndConvertHttpUrlToUncName` at `0x180002fae`
- `DAVHLPR!DavCheckAndConvertHttpUrlToUncName` at `0x180003145`

## string_xrefs

- `0x180002d8a`: `lpNetResource in NPOpenEnum`
- `0x180003312`: `DavEnumNode in NPOpenEnum`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
DWORD __stdcall NPOpenEnum(DWORD dwScope, DWORD dwType, DWORD dwUsage, LPNETRESOURCEW lpNetResource, LPHANDLE lphEnum)
{
  DWORD v7; // esi
  DWORD v8; // r15d
  _QWORD *v9; // rcx
  _QWORD *v10; // rcx
  LPHANDLE v11; // rdi
  DWORD v12; // ebx
  __int64 v13; // rdx
  __int64 v14; // r8
  _DWORD *v15; // r14
  _BYTE *v16; // rcx
  __int64 v18; // rdx
  unsigned int *v19; // rdi
  char v20; // al
  DWORD LastError; // eax
  LPWSTR v22; // rax
  unsigned int v23; // eax
  LPWSTR lpRemoteName; // r10
  DWORD v25; // eax
  unsigned int v26; // eax
  int v27; // eax
  _DWORD *v28; // rax
  _DWORD *v29; // rsi
  DWORD v30; // eax
  int v31; // [rsp+50h] [rbp-38h] BYREF
  int v32; // [rsp+54h] [rbp-34h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-30h] BYREF
  char v34; // [rsp+A8h] [rbp+20h] BYREF

  v7 = dwType;
  v32 = 0;
  v8 = dwUsage;
  hMem = 0;
  v34 = 0;
  v31 = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      WPP_SF_DDDq(*((_QWORD *)WPP_GLOBAL_Control + 2), dwType, dwUsage, dwScope, dwType, dwUsage, lpNetResource);
      v9 = WPP_GLOBAL_Control;
    }
    if ( v9 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v9 + 28) & 0x20) != 0 )
      {
        WPP_SF_S(v9[2], 234, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, L"lpNetResource in NPOpenEnum");
        v9 = WPP_GLOBAL_Control;
      }
      if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 2) != 0 )
      {
        WPP_SF_q(v9[2], 235, *(_QWORD *)&dwUsage, lpNetResource);
        v9 = WPP_GLOBAL_Control;
      }
    }
  }
  if ( lpNetResource && v9 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v9 + 28) & 2) != 0 )
    {
      WPP_SF_DDDD(
        v9[2],
        *(_QWORD *)&dwType,
        *(_QWORD *)&dwUsage,
        lpNetResource->dwScope,
        lpNetResource->dwType,
        lpNetResource->dwUsage,
        lpNetResource->dwDisplayType);
      v9 = WPP_GLOBAL_Control;
    }
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 2) != 0 )
      WPP_SF_SSSS(
        v9[2],
        237,
        dwUsage,
        lpNetResource->lpLocalName,
        (__int64)lpNetResource->lpRemoteName,
        (__int64)lpNetResource->lpComment,
        (__int64)lpNetResource->lpProvider);
  }
  if ( !(unsigned int)DavWorkstationStarted((__int64)v9, *(__int64 *)&dwType, *(__int64 *)&dwUsage) )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids);
      v10 = WPP_GLOBAL_Control;
    }
    v11 = lphEnum;
    v12 = 1222;
    if ( lphEnum )
      goto LABEL_30;
    goto LABEL_32;
  }
  v11 = lphEnum;
  if ( !lphEnum )
  {
    v12 = 87;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, 87);
      goto LABEL_31;
    }
    goto LABEL_32;
  }
  if ( (v7 & 0xFFFFFFEF) != 0 )
  {
    if ( (v7 & 0xFFFFFFFE) != 0 )
    {
      v12 = 87;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, 87);
      goto LABEL_30;
    }
  }
  else
  {
    v7 = 1;
  }
  v15 = LocalAlloc(0x40u, 0x20u);
  if ( !v15 )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, LastError);
    goto LABEL_30;
  }
  if ( dwScope != 1 )
  {
    switch ( dwScope )
    {
      case 2u:
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids);
          v16 = WPP_GLOBAL_Control;
        }
        v20 = 19;
        if ( v8 )
          v20 = v8;
        if ( (v20 & 0x13) != 0 )
        {
          v8 = v20 & 3;
          if ( lpNetResource && (lpRemoteName = lpNetResource->lpRemoteName) != 0 )
          {
            if ( (v20 & 1) == 0 )
            {
              v12 = 87;
              if ( v16 == (_BYTE *)&WPP_GLOBAL_Control || (v16[28] & 1) == 0 )
                goto LABEL_28;
              v18 = 117;
              break;
            }
            v25 = lpNetResource->dwUsage;
            if ( v25 && (v25 & 2) == 0 )
            {
              v12 = 1207;
              if ( v16 == (_BYTE *)&WPP_GLOBAL_Control || (v16[28] & 1) == 0 )
                goto LABEL_28;
              v18 = 118;
              break;
            }
            if ( (unsigned int)DavCheckAndConvertHttpUrlToUncName(lpRemoteName, &hMem, &v34, &v31, 0)
              || (unsigned int)(v31 - 1) > 1 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 119, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids);
                v12 = 67;
                goto LABEL_28;
              }
              goto LABEL_110;
            }
            v26 = DavServerExists(hMem, 0, &v32, 0);
            if ( !v32 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, v14, v26);
                v12 = 67;
                goto LABEL_28;
              }
              goto LABEL_110;
            }
            v27 = 2;
          }
          else
          {
            if ( (v20 & 2) == 0 )
            {
              v12 = 87;
              if ( v16 == (_BYTE *)&WPP_GLOBAL_Control || (v16[28] & 1) == 0 )
                goto LABEL_28;
              v18 = 116;
              break;
            }
            v27 = 3;
          }
          *v15 = v27;
          goto LABEL_43;
        }
        v12 = 87;
        if ( v16 == (_BYTE *)&WPP_GLOBAL_Control || (v16[28] & 1) == 0 )
          goto LABEL_28;
        v18 = 115;
        break;
      case 5u:
        v12 = 50;
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_28;
        v18 = 109;
        break;
      case 6u:
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids);
          v16 = WPP_GLOBAL_Control;
        }
        if ( lpNetResource && (v22 = lpNetResource->lpRemoteName) != 0 )
        {
          if ( !(unsigned int)DavCheckAndConvertHttpUrlToUncName(v22, &hMem, &v34, &v31, 0) && v31 == 1 )
          {
            v23 = DavServerExists(hMem, 0, &v32, 0);
            if ( v32 )
            {
              *v15 = 2;
              goto LABEL_43;
            }
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, v23);
LABEL_110:
            v12 = 67;
LABEL_28:
            LocalFree(v15);
LABEL_30:
            *v11 = 0;
LABEL_31:
            v10 = WPP_GLOBAL_Control;
            goto LABEL_32;
          }
          v12 = 67;
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_28;
          v18 = 112;
        }
        else
        {
          v12 = 87;
          if ( v16 == (_BYTE *)&WPP_GLOBAL_Control || (v16[28] & 1) == 0 )
            goto LABEL_28;
          v18 = 111;
        }
        break;
      default:
        v12 = 87;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids);
        goto LABEL_28;
    }
LABEL_115:
    WPP_SF_d(*((_QWORD *)v16 + 2), v18, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, v12);
    goto LABEL_28;
  }
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids);
    v16 = WPP_GLOBAL_Control;
  }
  if ( lpNetResource )
  {
    v12 = 87;
    if ( v16 == (_BYTE *)&WPP_GLOBAL_Control || (v16[28] & 1) == 0 )
      goto LABEL_28;
    v18 = 108;
    goto LABEL_115;
  }
  *v15 = 0;
LABEL_43:
  v15[1] = dwScope;
  v15[2] = v7;
  v15[3] = v8;
  *((_QWORD *)v15 + 2) = 0;
  if ( lpNetResource )
  {
    v28 = LocalAlloc(0x40u, 0x30u);
    v29 = v28;
    if ( !v28 )
    {
      v30 = GetLastError();
      v12 = v30;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 123, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, v30);
      goto LABEL_28;
    }
    *v28 = lpNetResource->dwScope;
    v28[1] = lpNetResource->dwType;
    v28[2] = lpNetResource->dwDisplayType;
    v28[3] = lpNetResource->dwUsage;
    *((_QWORD *)v28 + 3) = hMem;
    hMem = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        124,
        WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids,
        *((_QWORD *)v28 + 3));
    *((_QWORD *)v15 + 3) = v29;
  }
  *v11 = v15;
  v12 = 0;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        238,
        WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids,
        L"DavEnumNode in NPOpenEnum");
      v10 = WPP_GLOBAL_Control;
    }
    if ( v10 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v10 + 28) & 2) != 0 )
      {
        WPP_SF_q(v10[2], 239, v14, v15);
        v10 = WPP_GLOBAL_Control;
      }
      if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 2) != 0 )
      {
        WPP_SF_DDDddd(v10[2], v13, v14, (unsigned int)v15[1], v15[2], v15[3], *v15, v15[4], v15[5]);
        v10 = WPP_GLOBAL_Control;
      }
    }
  }
  v19 = (unsigned int *)*((_QWORD *)v15 + 3);
  if ( v10 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v10 + 28) & 0x20) != 0 )
    {
      WPP_SF_S(v10[2], 234, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, L"lpNetResource in enumNode");
      v10 = WPP_GLOBAL_Control;
    }
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 2) != 0 )
    {
      WPP_SF_q(v10[2], 235, v14, v19);
      v10 = WPP_GLOBAL_Control;
    }
  }
  if ( v19 )
  {
    if ( v10 == &WPP_GLOBAL_Control )
      goto LABEL_32;
    if ( (*((_BYTE *)v10 + 28) & 2) != 0 )
    {
      WPP_SF_DDDD(v10[2], v13, v14, *v19, v19[1], v19[3], v19[2]);
      v10 = WPP_GLOBAL_Control;
    }
    if ( v10 == &WPP_GLOBAL_Control )
      goto LABEL_32;
    if ( (*((_BYTE *)v10 + 28) & 2) != 0 )
    {
      WPP_SF_SSSS(
        v10[2],
        237,
        v14,
        *((_QWORD *)v19 + 2),
        *((_QWORD *)v19 + 3),
        *((_QWORD *)v19 + 4),
        *((_QWORD *)v19 + 5));
      v10 = WPP_GLOBAL_Control;
    }
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 2) != 0 )
  {
    WPP_SF_q(v10[2], 125, v14, v15);
    goto LABEL_31;
  }
LABEL_32:
  if ( hMem )
  {
    LocalFree(hMem);
    v10 = WPP_GLOBAL_Control;
    hMem = 0;
  }
  if ( v10 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v10 + 28) & 0x40) != 0 )
    {
      WPP_SF_d(v10[2], 126, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, v12);
      v10 = WPP_GLOBAL_Control;
    }
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x20) != 0 )
      WPP_SF_(v10[2], 241, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids);
  }
  return v12;
}

```

## disassembly

```asm
0x180002970  mov     rax, rsp
0x180002973  push    rbx
0x180002974  push    r12
0x180002976  sub     rsp, 78h
0x18000297a  mov     [rax+8], rbp
0x18000297e  mov     rbx, r9
0x180002981  mov     [rax+10h], rsi
0x180002985  mov     ebp, ecx
0x180002987  mov     [rax-18h], r13
0x18000298b  mov     esi, edx
0x18000298d  xor     r13d, r13d
0x180002990  mov     [rax-28h], r15
0x180002994  mov     [rax-34h], r13d
0x180002998  mov     r15d, r8d
0x18000299b  mov     [rax-30h], r13
0x18000299f  mov     [rax+20h], r13b
0x1800029a3  mov     [rax-38h], r13d
0x1800029a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800029ae  lea     r12, WPP_GLOBAL_Control
0x1800029b5  cmp     rcx, r12
0x1800029b8  jz      short loc_1800029E2
0x1800029ba  test    byte ptr [rcx+1Ch], 20h
0x1800029be  jnz     loc_180002D60
0x1800029c4  cmp     rcx, r12
0x1800029c7  jz      short loc_1800029E2
0x1800029c9  test    byte ptr [rcx+1Ch], 20h
0x1800029cd  jnz     loc_180002D86
0x1800029d3  cmp     rcx, r12
0x1800029d6  jz      short loc_1800029E2
0x1800029d8  test    byte ptr [rcx+1Ch], 2
0x1800029dc  jnz     loc_180002DAE
0x1800029e2  test    rbx, rbx
0x1800029e5  jz      short loc_1800029F0
0x1800029e7  cmp     rcx, r12
0x1800029ea  jnz     loc_180002DCB
0x1800029f0  mov     [rsp+88h+arg_10], rdi
0x1800029f8  mov     [rsp+88h+var_20], r14
0x1800029fd  call    DavWorkstationStarted
0x180002a02  test    eax, eax
0x180002a04  jnz     short loc_180002A37
0x180002a06  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a0d  cmp     rcx, r12
0x180002a10  jz      short loc_180002A1C
0x180002a12  test    byte ptr [rcx+1Ch], 1
0x180002a16  jnz     loc_180002E3E
0x180002a1c  mov     rdi, [rsp+88h+lphEnum]
0x180002a24  mov     ebx, 4C6h
0x180002a29  test    rdi, rdi
0x180002a2c  jz      loc_180002AD8
0x180002a32  jmp     loc_180002ACE
0x180002a37  mov     rdi, [rsp+88h+lphEnum]
0x180002a3f  test    rdi, rdi
0x180002a42  jz      loc_180002E5F
0x180002a48  test    esi, 0FFFFFFEFh
0x180002a4e  jz      loc_180002E9B
0x180002a54  test    esi, 0FFFFFFFEh
0x180002a5a  jnz     short loc_180002AB9
0x180002a5c  mov     edx, 20h ; ' '; uBytes
0x180002a61  mov     ecx, 40h ; '@'; uFlags
0x180002a66  call    cs:__imp_LocalAlloc
0x180002a6c  mov     r14, rax
0x180002a6f  test    rax, rax
0x180002a72  jz      loc_180002ECC
0x180002a78  cmp     ebp, 1
0x180002a7b  jnz     loc_180002B20
0x180002a81  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a88  cmp     rcx, r12
0x180002a8b  jz      short loc_180002A97
0x180002a8d  test    byte ptr [rcx+1Ch], 2
0x180002a91  jnz     loc_18000322F
0x180002a97  test    rbx, rbx
0x180002a9a  jz      loc_180002B5D
0x180002aa0  mov     ebx, 57h ; 'W'
0x180002aa5  cmp     rcx, r12
0x180002aa8  jnz     loc_180003250
0x180002aae  mov     rcx, r14; hMem
0x180002ab1  call    cs:__imp_LocalFree
0x180002ab7  jmp     short loc_180002ACE
0x180002ab9  mov     ebx, 57h ; 'W'
0x180002abe  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ac5  cmp     rcx, r12
0x180002ac8  jnz     loc_180002EA5
0x180002ace  mov     [rdi], r13
0x180002ad1  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ad8  mov     rax, [rsp+88h+hMem]
0x180002add  mov     r15, [rsp+88h+var_28]
0x180002ae2  mov     r14, [rsp+88h+var_20]
0x180002ae7  mov     rdi, [rsp+88h+arg_10]
0x180002aef  mov     rsi, [rsp+88h+arg_8]
0x180002af7  mov     rbp, [rsp+88h+arg_0]
0x180002aff  test    rax, rax
0x180002b02  jnz     loc_1800033A2
0x180002b08  mov     r13, [rsp+88h+var_18]
0x180002b0d  cmp     rcx, r12
0x180002b10  jnz     loc_180002CD6
0x180002b16  mov     eax, ebx
0x180002b18  add     rsp, 78h
0x180002b1c  pop     r12
0x180002b1e  pop     rbx
0x180002b1f  retn
0x180002b20  mov     eax, ebp
0x180002b22  sub     eax, 2
0x180002b25  jz      loc_180002C76
0x180002b2b  sub     eax, 3
0x180002b2e  jnz     loc_180002F0B
0x180002b34  mov     ebx, 32h ; '2'
0x180002b39  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b40  cmp     rcx, r12
0x180002b43  jz      loc_180002AAE
0x180002b49  test    byte ptr [rcx+1Ch], 1
0x180002b4d  jz      loc_180002AAE
0x180002b53  mov     edx, 6Dh ; 'm'
0x180002b58  jmp     loc_180003045
0x180002b5d  mov     [r14], r13d
0x180002b60  jmp     short loc_180002B6E
0x180002b62  mov     [r14], eax
0x180002b65  cmp     eax, 2
0x180002b68  jnz     loc_180003202
0x180002b6e  mov     [r14+4], ebp
0x180002b72  mov     [r14+8], esi
0x180002b76  mov     [r14+0Ch], r15d
0x180002b7a  mov     [r14+10h], r13
0x180002b7e  test    rbx, rbx
0x180002b81  jnz     loc_18000325F
0x180002b87  mov     [rdi], r14
0x180002b8a  mov     ebx, r13d
0x180002b8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b94  cmp     rcx, r12
0x180002b97  jz      short loc_180002BAC
0x180002b99  test    byte ptr [rcx+1Ch], 20h
0x180002b9d  jnz     loc_18000330E
0x180002ba3  cmp     rcx, r12
0x180002ba6  jnz     loc_180003336
0x180002bac  mov     rdi, [r14+18h]
0x180002bb0  cmp     rcx, r12
0x180002bb3  jz      short loc_180002BCE
0x180002bb5  test    byte ptr [rcx+1Ch], 20h
0x180002bb9  jnz     loc_18000335D
0x180002bbf  cmp     rcx, r12
0x180002bc2  jz      short loc_180002BCE
0x180002bc4  test    byte ptr [rcx+1Ch], 2
0x180002bc8  jnz     loc_180003385
0x180002bce  test    rdi, rdi
0x180002bd1  jz      short loc_180002C4D
0x180002bd3  cmp     rcx, r12
0x180002bd6  jz      loc_180002AD8
0x180002bdc  test    byte ptr [rcx+1Ch], 2
0x180002be0  jz      short loc_180002C0A
0x180002be2  mov     eax, [rdi+8]
0x180002be5  mov     r9d, [rdi]
0x180002be8  mov     rcx, [rcx+10h]
0x180002bec  mov     dword ptr [rsp+88h+var_58], eax
0x180002bf0  mov     eax, [rdi+0Ch]
0x180002bf3  mov     dword ptr [rsp+88h+var_60], eax
0x180002bf7  mov     eax, [rdi+4]
0x180002bfa  mov     dword ptr [rsp+88h+var_68], eax
0x180002bfe  call    WPP_SF_DDDD
0x180002c03  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c0a  cmp     rcx, r12
0x180002c0d  jz      loc_180002AD8
0x180002c13  test    byte ptr [rcx+1Ch], 2
0x180002c17  jz      short loc_180002C4D
0x180002c19  mov     rax, [rdi+28h]
0x180002c1d  mov     edx, 0EDh
0x180002c22  mov     r9, [rdi+10h]
0x180002c26  mov     rcx, [rcx+10h]
0x180002c2a  mov     [rsp+88h+var_58], rax
0x180002c2f  mov     rax, [rdi+20h]
0x180002c33  mov     [rsp+88h+var_60], rax
0x180002c38  mov     rax, [rdi+18h]
0x180002c3c  mov     [rsp+88h+var_68], rax
0x180002c41  call    WPP_SF_SSSS
0x180002c46  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c4d  cmp     rcx, r12
0x180002c50  jz      loc_180002AD8
0x180002c56  test    byte ptr [rcx+1Ch], 2
0x180002c5a  jz      loc_180002AD8
0x180002c60  mov     rcx, [rcx+10h]
0x180002c64  mov     edx, 7Dh ; '}'
0x180002c69  mov     r9, r14
0x180002c6c  call    WPP_SF_q
0x180002c71  jmp     loc_180002AD1
0x180002c76  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c7d  cmp     rcx, r12
0x180002c80  jnz     loc_18000307C
0x180002c86  test    r15d, r15d
0x180002c89  mov     eax, 13h
0x180002c8e  cmovnz  eax, r15d
0x180002c92  mov     r15d, eax
0x180002c95  test    al, 13h
0x180002c97  jz      loc_1800030A7
0x180002c9d  and     r15d, 3
0x180002ca1  test    rbx, rbx
0x180002ca4  jnz     loc_1800030C9
0x180002caa  test    r15b, 2
0x180002cae  jnz     loc_1800031F8
0x180002cb4  mov     ebx, 57h ; 'W'
0x180002cb9  cmp     rcx, r12
0x180002cbc  jz      loc_180002AAE
0x180002cc2  test    byte ptr [rcx+1Ch], 1
0x180002cc6  jz      loc_180002AAE
0x180002ccc  mov     edx, 74h ; 't'
0x180002cd1  jmp     loc_180003045
0x180002cd6  test    byte ptr [rcx+1Ch], 40h
0x180002cda  jnz     loc_1800033BC
0x180002ce0  cmp     rcx, r12
0x180002ce3  jz      loc_180002B16
0x180002ce9  test    byte ptr [rcx+1Ch], 20h
0x180002ced  jz      loc_180002B16
0x180002cf3  mov     rcx, [rcx+10h]
0x180002cf7  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x180002cfe  mov     edx, 0F1h
0x180002d03  call    WPP_SF_
0x180002d08  jmp     loc_180002B16
0x180002d0d  cmp     rcx, r12
0x180002d10  jz      loc_180002BAC
0x180002d16  test    byte ptr [rcx+1Ch], 2
0x180002d1a  jz      loc_180002BAC
0x180002d20  mov     eax, [r14+14h]
0x180002d24  mov     r9d, [r14+4]
0x180002d28  mov     rcx, [rcx+10h]
0x180002d2c  mov     [rsp+88h+var_48], eax
0x180002d30  mov     eax, [r14+10h]
0x180002d34  mov     [rsp+88h+var_50], eax
0x180002d38  mov     eax, [r14]
0x180002d3b  mov     dword ptr [rsp+88h+var_58], eax
0x180002d3f  mov     eax, [r14+0Ch]
0x180002d43  mov     dword ptr [rsp+88h+var_60], eax
0x180002d47  mov     eax, [r14+8]
0x180002d4b  mov     dword ptr [rsp+88h+var_68], eax
0x180002d4f  call    WPP_SF_DDDddd
0x180002d54  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d5b  jmp     loc_180002BAC
0x180002d60  mov     rcx, [rcx+10h]
0x180002d64  mov     r9d, ebp
0x180002d67  mov     [rsp+88h+var_58], rbx
0x180002d6c  mov     dword ptr [rsp+88h+var_60], r15d
0x180002d71  mov     dword ptr [rsp+88h+var_68], esi
0x180002d75  call    WPP_SF_DDDq
0x180002d7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d81  jmp     loc_1800029C4
0x180002d86  mov     rcx, [rcx+10h]
0x180002d8a  lea     r9, aLpnetresourceI_0; "lpNetResource in NPOpenEnum"
0x180002d91  mov     edx, 0EAh
0x180002d96  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x180002d9d  call    WPP_SF_S
0x180002da2  mov     rcx, cs:WPP_GLOBAL_Control
0x180002da9  jmp     loc_1800029D3
0x180002dae  mov     rcx, [rcx+10h]
0x180002db2  mov     edx, 0EBh
0x180002db7  mov     r9, rbx
0x180002dba  call    WPP_SF_q
0x180002dbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180002dc6  jmp     loc_1800029E2
0x180002dcb  test    byte ptr [rcx+1Ch], 2
0x180002dcf  jz      short loc_180002DF9
0x180002dd1  mov     eax, [rbx+8]
0x180002dd4  mov     r9d, [rbx]
0x180002dd7  mov     rcx, [rcx+10h]
0x180002ddb  mov     dword ptr [rsp+88h+var_58], eax
0x180002ddf  mov     eax, [rbx+0Ch]
0x180002de2  mov     dword ptr [rsp+88h+var_60], eax
0x180002de6  mov     eax, [rbx+4]
0x180002de9  mov     dword ptr [rsp+88h+var_68], eax
0x180002ded  call    WPP_SF_DDDD
0x180002df2  mov     rcx, cs:WPP_GLOBAL_Control
0x180002df9  cmp     rcx, r12
0x180002dfc  jz      loc_1800029F0
0x180002e02  test    byte ptr [rcx+1Ch], 2
0x180002e06  jz      loc_1800029F0
0x180002e0c  mov     rax, [rbx+28h]
0x180002e10  mov     edx, 0EDh
0x180002e15  mov     r9, [rbx+10h]
0x180002e19  mov     rcx, [rcx+10h]
0x180002e1d  mov     [rsp+88h+var_58], rax
0x180002e22  mov     rax, [rbx+20h]
0x180002e26  mov     [rsp+88h+var_60], rax
0x180002e2b  mov     rax, [rbx+18h]
0x180002e2f  mov     [rsp+88h+var_68], rax
0x180002e34  call    WPP_SF_SSSS
0x180002e39  jmp     loc_1800029F0
0x180002e3e  mov     rcx, [rcx+10h]
0x180002e42  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x180002e49  mov     edx, 67h ; 'g'
0x180002e4e  call    WPP_SF_
0x180002e53  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e5a  jmp     loc_180002A1C
0x180002e5f  mov     ebx, 57h ; 'W'
0x180002e64  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e6b  cmp     rcx, r12
0x180002e6e  jz      loc_180002AD8
0x180002e74  test    byte ptr [rcx+1Ch], 1
0x180002e78  jz      loc_180002AD8
0x180002e7e  mov     rcx, [rcx+10h]
0x180002e82  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x180002e89  mov     edx, 68h ; 'h'
0x180002e8e  mov     r9d, ebx
0x180002e91  call    WPP_SF_d
0x180002e96  jmp     loc_180002AD1
0x180002e9b  mov     esi, 1
  ... truncated ...
```
