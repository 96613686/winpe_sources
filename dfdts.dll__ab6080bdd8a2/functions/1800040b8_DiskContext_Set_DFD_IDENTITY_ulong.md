# DiskContext::Set(DFD_IDENTITY,ulong)

- ea: `0x1800040b8`
- end: `0x180004546`
- name: `?Set@DiskContext@@QEAAKW4DFD_IDENTITY@@K@Z`
- size: `1166`
- prototype: `__int64 __fastcall(__int64, int, DWORD)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callers

- `0x180002ed8`
- `0x180007970`

## callees

- `0x180001064`
- `0x180002c68`
- `0x180002c90`
- `0x180003924`
- `0x180003984`
- `0x180003f2c`
- `0x1800040b8`
- `0x1800047ec`
- `0x180008370`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1800043be`
- `KERNEL32!CreateFileW` at `0x1800043be`
- `KERNEL32!HeapAlloc` at `0x1800041c1`
- `KERNEL32!HeapAlloc` at `0x1800042ac`
- `KERNEL32!HeapAlloc` at `0x1800041c1`
- `KERNEL32!HeapAlloc` at `0x1800042ac`
- `KERNEL32!GetProcessHeap` at `0x1800041ac`
- `KERNEL32!GetProcessHeap` at `0x18000429d`
- `KERNEL32!GetProcessHeap` at `0x180004508`
- `KERNEL32!GetProcessHeap` at `0x1800041ac`
- `KERNEL32!GetProcessHeap` at `0x18000429d`
- `KERNEL32!GetProcessHeap` at `0x180004508`
- `KERNEL32!HeapFree` at `0x180004516`
- `KERNEL32!HeapFree` at `0x180004516`
- `KERNEL32!GetLastError` at `0x180004125`
- `KERNEL32!GetLastError` at `0x18000422b`
- `KERNEL32!GetLastError` at `0x180004316`
- `KERNEL32!GetLastError` at `0x1800043ce`
- `KERNEL32!GetLastError` at `0x180004125`
- `KERNEL32!GetLastError` at `0x18000422b`
- `KERNEL32!GetLastError` at `0x180004316`
- `KERNEL32!GetLastError` at `0x1800043ce`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x180004114`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x180004114`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x180004221`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18000430c`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x180004221`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18000430c`

## pseudocode

```c
__int64 __fastcall DiskContext::Set(__int64 a1, int a2, DWORD a3)
{
  void *v5; // rcx
  DWORD LastError; // eax
  unsigned int v7; // edi
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  HANDLE ProcessHeap; // rax
  _DWORD *v13; // rax
  void *v14; // rcx
  SIZE_T v15; // rbx
  HANDLE v16; // rax
  struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *v17; // rax
  WCHAR *v18; // r15
  DWORD v19; // eax
  DWORD v20; // edx
  HANDLE FileW; // rax
  DWORD v22; // eax
  int v23; // ebp
  _WORD *v24; // rax
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  _WORD *v27; // rax
  HANDLE v28; // rax
  DWORD RequiredSize; // [rsp+40h] [rbp-78h] BYREF
  _WORD *v31; // [rsp+48h] [rbp-70h]
  struct _SP_DEVICE_INTERFACE_DATA DeviceInterfaceData; // [rsp+50h] [rbp-68h] BYREF

  v5 = *(void **)a1;
  memset(&DeviceInterfaceData, 0, sizeof(DeviceInterfaceData));
  DeviceInterfaceData.cbSize = 32;
  if ( !SetupDiEnumDeviceInterfaces(v5, 0, &GUID_DEVINTERFACE_DISK, a3, &DeviceInterfaceData) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError == 259 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v9 = 10;
LABEL_6:
        WPP_SF_(v8[2], v9, &WPP_6840784a3f2339c3fb8e3bd3d3f5f082_Traceguids);
        return v7;
      }
      return v7;
    }
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v7;
    v11 = 11;
LABEL_10:
    WPP_SF_d(v10[2], v11, &WPP_6840784a3f2339c3fb8e3bd3d3f5f082_Traceguids, LastError);
    return v7;
  }
  ProcessHeap = GetProcessHeap();
  v13 = HeapAlloc(ProcessHeap, 8u, 0x20u);
  *(_QWORD *)(a1 + 16) = v13;
  if ( v13 )
  {
    *v13 = 32;
    v14 = *(void **)a1;
    RequiredSize = 0;
    if ( !SetupDiGetDeviceInterfaceDetailW(v14, &DeviceInterfaceData, 0, 0, &RequiredSize, 0) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError != 122 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v7;
        v11 = 13;
        goto LABEL_10;
      }
    }
    LastError = RequiredSize;
    if ( RequiredSize < 8 )
    {
      v7 = 122;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v7;
      v11 = 14;
      goto LABEL_10;
    }
    v15 = RequiredSize;
    v16 = GetProcessHeap();
    v17 = (struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *)HeapAlloc(v16, 8u, v15);
    v18 = (WCHAR *)v17;
    if ( !v17 )
    {
      v7 = 8;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v9 = 15;
        goto LABEL_6;
      }
      return v7;
    }
    v17->cbSize = 8;
    if ( SetupDiGetDeviceInterfaceDetailW(
           *(HDEVINFO *)a1,
           &DeviceInterfaceData,
           v17,
           RequiredSize,
           &RequiredSize,
           *(PSP_DEVINFO_DATA *)(a1 + 16)) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_6840784a3f2339c3fb8e3bd3d3f5f082_Traceguids, v18 + 2);
      if ( !a2 || (v20 = 0, a2 == 2) )
        v20 = -1073741824;
      FileW = CreateFileW(v18 + 2, v20, 0, 0, 3u, 0, 0);
      *(_QWORD *)(a1 + 8) = FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        v22 = GetLastError();
        v7 = v22;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            (unsigned int)&WPP_6840784a3f2339c3fb8e3bd3d3f5f082_Traceguids,
            (_DWORD)v18 + 4,
            v22);
        goto LABEL_64;
      }
      v7 = 0;
      if ( a2 )
      {
        v23 = a2 - 1;
        if ( v23 )
        {
          if ( v23 == 1 )
            DiskContext::SetSMARTCapability((DiskContext *)a1);
          goto LABEL_64;
        }
        if ( *(_DWORD *)(a1 + 628) != 1 )
          DiskContext::HasSMARTFailurePredicted((DiskContext *)a1, v18 + 2);
        v24 = operator new(0x20u);
        v31 = v24;
        if ( v24 )
        {
          *(_QWORD *)v24 = *(_QWORD *)(a1 + 8);
          v24[4] = 0;
          *((_QWORD *)v24 + 3) = 0;
          *((_QWORD *)v24 + 2) = 0;
        }
        else
        {
          v24 = 0;
        }
        *(_QWORD *)(a1 + 24) = v24;
        if ( v24 )
          goto LABEL_64;
        v7 = 14;
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_64;
        v26 = 20;
      }
      else
      {
        if ( !(unsigned int)DiskContext::HasSMARTFailurePredicted((DiskContext *)a1, v18 + 2) )
          goto LABEL_64;
        v27 = operator new(0x20u);
        v31 = v27;
        if ( v27 )
        {
          *(_QWORD *)v27 = *(_QWORD *)(a1 + 8);
          v27[4] = 0;
          *((_QWORD *)v27 + 3) = 0;
          *((_QWORD *)v27 + 2) = 0;
        }
        else
        {
          v27 = 0;
        }
        *(_QWORD *)(a1 + 24) = v27;
        if ( v27 )
          goto LABEL_64;
        v7 = 14;
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_64;
        v26 = 19;
      }
      WPP_SF_(v25[2], v26, &WPP_6840784a3f2339c3fb8e3bd3d3f5f082_Traceguids);
    }
    else
    {
      v19 = GetLastError();
      v7 = v19;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_6840784a3f2339c3fb8e3bd3d3f5f082_Traceguids, v19);
    }
LABEL_64:
    v28 = GetProcessHeap();
    HeapFree(v28, 0, v18);
    return v7;
  }
  v7 = 8;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v9 = 12;
    goto LABEL_6;
  }
  return v7;
}

```

## disassembly

```asm
0x1800040b8  mov     [rsp+arg_8], rbx
0x1800040bd  push    rbp
0x1800040be  push    rsi
0x1800040bf  push    rdi
0x1800040c0  push    r12
0x1800040c2  push    r13
0x1800040c4  push    r14
0x1800040c6  push    r15
0x1800040c8  sub     rsp, 80h
0x1800040cf  mov     rax, cs:__security_cookie
0x1800040d6  xor     rax, rsp
0x1800040d9  mov     [rsp+0B8h+var_48], rax
0x1800040de  xorps   xmm0, xmm0
0x1800040e1  lea     rax, [rsp+0B8h+var_68]
0x1800040e6  mov     ebp, edx
0x1800040e8  mov     [rsp+0B8h+DeviceInterfaceData], rax; DeviceInterfaceData
0x1800040ed  mov     rsi, rcx
0x1800040f0  mov     r9d, r8d; MemberIndex
0x1800040f3  mov     rcx, [rcx]; DeviceInfoSet
0x1800040f6  lea     r8, GUID_DEVINTERFACE_DISK; InterfaceClassGuid
0x1800040fd  movups  xmmword ptr [rsp+0B8h+var_68.cbSize], xmm0
0x180004102  mov     r13d, 20h ; ' '
0x180004108  xor     edx, edx; DeviceInfoData
0x18000410a  mov     [rsp+0B8h+var_68.cbSize], r13d
0x18000410f  movups  xmmword ptr [rsp+0B8h+var_68.InterfaceClassGuid.Data4+4], xmm0
0x180004114  call    cs:__imp_SetupDiEnumDeviceInterfaces
0x18000411a  xor     r12d, r12d
0x18000411d  test    eax, eax
0x18000411f  jnz     loc_1800041AC
0x180004125  call    cs:__imp_GetLastError
0x18000412b  mov     edi, eax
0x18000412d  cmp     eax, 103h
0x180004132  jnz     short loc_18000416E
0x180004134  mov     rcx, cs:WPP_GLOBAL_Control
0x18000413b  lea     rbx, WPP_GLOBAL_Control
0x180004142  cmp     rcx, rbx
0x180004145  jz      loc_18000451C
0x18000414b  test    byte ptr [rcx+1Ch], 4
0x18000414f  jz      loc_18000451C
0x180004155  lea     edx, [r13-16h]
0x180004159  mov     rcx, [rcx+10h]
0x18000415d  lea     r8, WPP_6840784a3f2339c3fb8e3bd3d3f5f082_Traceguids
0x180004164  call    WPP_SF_
0x180004169  jmp     loc_18000451C
0x18000416e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004175  lea     rbx, WPP_GLOBAL_Control
0x18000417c  cmp     rcx, rbx
0x18000417f  jz      loc_18000451C
0x180004185  test    byte ptr [rcx+1Ch], 1
0x180004189  jz      loc_18000451C
0x18000418f  mov     edx, 0Bh
0x180004194  mov     rcx, [rcx+10h]
0x180004198  lea     r8, WPP_6840784a3f2339c3fb8e3bd3d3f5f082_Traceguids
0x18000419f  mov     r9d, eax
0x1800041a2  call    WPP_SF_d
0x1800041a7  jmp     loc_18000451C
0x1800041ac  call    cs:__imp_GetProcessHeap
0x1800041b2  mov     r14d, 8
0x1800041b8  mov     r8, r13; dwBytes
0x1800041bb  mov     rcx, rax; hHeap
0x1800041be  mov     edx, r14d; dwFlags
0x1800041c1  call    cs:__imp_HeapAlloc
0x1800041c7  mov     [rsi+10h], rax
0x1800041cb  test    rax, rax
0x1800041ce  jnz     short loc_1800041FC
0x1800041d0  mov     edi, r14d
0x1800041d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800041da  lea     rbx, WPP_GLOBAL_Control
0x1800041e1  cmp     rcx, rbx
0x1800041e4  jz      loc_18000451C
0x1800041ea  test    byte ptr [rcx+1Ch], 1
0x1800041ee  jz      loc_18000451C
0x1800041f4  lea     edx, [rax+0Ch]
0x1800041f7  jmp     loc_180004159
0x1800041fc  mov     [rax], r13d
0x1800041ff  lea     rdx, [rsp+0B8h+var_68]; DeviceInterfaceData
0x180004204  mov     rcx, [rsi]; DeviceInfoSet
0x180004207  lea     rax, [rsp+0B8h+RequiredSize]
0x18000420c  mov     [rsp+0B8h+DeviceInfoData], r12; DeviceInfoData
0x180004211  xor     r9d, r9d; DeviceInterfaceDetailDataSize
0x180004214  xor     r8d, r8d; DeviceInterfaceDetailData
0x180004217  mov     [rsp+0B8h+DeviceInterfaceData], rax; RequiredSize
0x18000421c  mov     [rsp+0B8h+RequiredSize], r12d
0x180004221  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x180004227  test    eax, eax
0x180004229  jnz     short loc_180004263
0x18000422b  call    cs:__imp_GetLastError
0x180004231  mov     edi, eax
0x180004233  cmp     eax, 7Ah ; 'z'
0x180004236  jz      short loc_180004263
0x180004238  mov     rcx, cs:WPP_GLOBAL_Control
0x18000423f  lea     rbx, WPP_GLOBAL_Control
0x180004246  cmp     rcx, rbx
0x180004249  jz      loc_18000451C
0x18000424f  test    byte ptr [rcx+1Ch], 1
0x180004253  jz      loc_18000451C
0x180004259  mov     edx, 0Dh
0x18000425e  jmp     loc_180004194
0x180004263  mov     eax, [rsp+0B8h+RequiredSize]
0x180004267  cmp     eax, r14d
0x18000426a  jnb     short loc_18000429A
0x18000426c  mov     edi, 7Ah ; 'z'
0x180004271  mov     rcx, cs:WPP_GLOBAL_Control
0x180004278  lea     rbx, WPP_GLOBAL_Control
0x18000427f  cmp     rcx, rbx
0x180004282  jz      loc_18000451C
0x180004288  test    byte ptr [rcx+1Ch], 1
0x18000428c  jz      loc_18000451C
0x180004292  lea     edx, [rdi-6Ch]
0x180004295  jmp     loc_180004194
0x18000429a  mov     rbx, rax
0x18000429d  call    cs:__imp_GetProcessHeap
0x1800042a3  mov     r8, rbx; dwBytes
0x1800042a6  mov     edx, r14d; dwFlags
0x1800042a9  mov     rcx, rax; hHeap
0x1800042ac  call    cs:__imp_HeapAlloc
0x1800042b2  mov     r15, rax
0x1800042b5  test    rax, rax
0x1800042b8  jnz     short loc_1800042E6
0x1800042ba  mov     edi, r14d
0x1800042bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800042c4  lea     rbx, WPP_GLOBAL_Control
0x1800042cb  cmp     rcx, rbx
0x1800042ce  jz      loc_18000451C
0x1800042d4  test    byte ptr [rcx+1Ch], 1
0x1800042d8  jz      loc_18000451C
0x1800042de  lea     edx, [rax+0Fh]
0x1800042e1  jmp     loc_180004159
0x1800042e6  mov     [rax], r14d
0x1800042e9  lea     rdx, [rsp+0B8h+var_68]; DeviceInterfaceData
0x1800042ee  mov     rax, [rsi+10h]
0x1800042f2  mov     r8, r15; DeviceInterfaceDetailData
0x1800042f5  mov     r9d, [rsp+0B8h+RequiredSize]; DeviceInterfaceDetailDataSize
0x1800042fa  mov     rcx, [rsi]; DeviceInfoSet
0x1800042fd  mov     [rsp+0B8h+DeviceInfoData], rax; DeviceInfoData
0x180004302  lea     rax, [rsp+0B8h+RequiredSize]
0x180004307  mov     [rsp+0B8h+DeviceInterfaceData], rax; RequiredSize
0x18000430c  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x180004312  test    eax, eax
0x180004314  jnz     short loc_18000435C
0x180004316  call    cs:__imp_GetLastError
0x18000431c  mov     edi, eax
0x18000431e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004325  lea     rbx, WPP_GLOBAL_Control
0x18000432c  cmp     rcx, rbx
0x18000432f  jz      loc_180004508
0x180004335  test    byte ptr [rcx+1Ch], 1
0x180004339  jz      loc_180004508
0x18000433f  mov     rcx, [rcx+10h]
0x180004343  lea     r8, WPP_6840784a3f2339c3fb8e3bd3d3f5f082_Traceguids
0x18000434a  mov     edx, 10h
0x18000434f  mov     r9d, eax
0x180004352  call    WPP_SF_d
0x180004357  jmp     loc_180004508
0x18000435c  mov     rcx, cs:WPP_GLOBAL_Control
0x180004363  lea     rbx, WPP_GLOBAL_Control
0x18000436a  cmp     rcx, rbx
0x18000436d  jz      short loc_18000438E
0x18000436f  test    byte ptr [rcx+1Ch], 4
0x180004373  jz      short loc_18000438E
0x180004375  mov     rcx, [rcx+10h]
0x180004379  lea     r9, [r15+4]
0x18000437d  mov     edx, 11h
0x180004382  lea     r8, WPP_6840784a3f2339c3fb8e3bd3d3f5f082_Traceguids
0x180004389  call    WPP_SF_S
0x18000438e  test    ebp, ebp
0x180004390  jz      short loc_18000439A
0x180004392  mov     edx, r12d
0x180004395  cmp     ebp, 2
0x180004398  jnz     short loc_18000439F
0x18000439a  mov     edx, 0C0000000h; dwDesiredAccess
0x18000439f  mov     [rsp+0B8h+hTemplateFile], r12; hTemplateFile
0x1800043a4  lea     r14, [r15+4]
0x1800043a8  mov     rcx, r14; lpFileName
0x1800043ab  mov     dword ptr [rsp+0B8h+DeviceInfoData], r12d; dwFlagsAndAttributes
0x1800043b0  xor     r9d, r9d; lpSecurityAttributes
0x1800043b3  mov     dword ptr [rsp+0B8h+DeviceInterfaceData], 3; dwCreationDisposition
0x1800043bb  xor     r8d, r8d; dwShareMode
0x1800043be  call    cs:__imp_CreateFileW
0x1800043c4  mov     [rsi+8], rax
0x1800043c8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800043cc  jnz     short loc_180004411
0x1800043ce  call    cs:__imp_GetLastError
0x1800043d4  mov     edi, eax
0x1800043d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800043dd  cmp     rcx, rbx
0x1800043e0  jz      loc_180004508
0x1800043e6  test    byte ptr [rcx+1Ch], 1
0x1800043ea  jz      loc_180004508
0x1800043f0  mov     rcx, [rcx+10h]
0x1800043f4  lea     r8, WPP_6840784a3f2339c3fb8e3bd3d3f5f082_Traceguids
0x1800043fb  mov     edx, 12h
0x180004400  mov     dword ptr [rsp+0B8h+DeviceInterfaceData], eax
0x180004404  mov     r9, r14
0x180004407  call    WPP_SF_Sd
0x18000440c  jmp     loc_180004508
0x180004411  mov     edi, r12d
0x180004414  test    ebp, ebp
0x180004416  jz      loc_18000449D
0x18000441c  sub     ebp, 1
0x18000441f  jz      short loc_180004437
0x180004421  cmp     ebp, 1
0x180004424  jnz     loc_180004508
0x18000442a  mov     rcx, rsi; this
0x18000442d  call    ?SetSMARTCapability@DiskContext@@AEAAXXZ; DiskContext::SetSMARTCapability(void)
0x180004432  jmp     loc_180004508
0x180004437  cmp     dword ptr [rsi+274h], 1
0x18000443e  jz      short loc_18000444B
0x180004440  mov     rdx, r14; unsigned __int16 *
0x180004443  mov     rcx, rsi; this
0x180004446  call    ?HasSMARTFailurePredicted@DiskContext@@AEAAHPEAG@Z; DiskContext::HasSMARTFailurePredicted(ushort *)
0x18000444b  mov     rcx, r13; Size
0x18000444e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004453  mov     [rsp+0B8h+var_70], rax
0x180004458  test    rax, rax
0x18000445b  jz      short loc_180004473
0x18000445d  mov     rcx, [rsi+8]
0x180004461  mov     [rax], rcx
0x180004464  mov     [rax+8], r12w
0x180004469  mov     [rax+18h], r12
0x18000446d  mov     [rax+10h], r12
0x180004471  jmp     short loc_180004476
0x180004473  mov     rax, r12
0x180004476  mov     [rsi+18h], rax
0x18000447a  test    rax, rax
0x18000447d  jnz     loc_180004508
0x180004483  lea     edi, [rax+0Eh]
0x180004486  mov     rcx, cs:WPP_GLOBAL_Control
0x18000448d  cmp     rcx, rbx
0x180004490  jz      short loc_180004508
0x180004492  test    byte ptr [rcx+1Ch], 1
0x180004496  jz      short loc_180004508
0x180004498  lea     edx, [rax+14h]
0x18000449b  jmp     short loc_1800044F8
0x18000449d  mov     rdx, r14; unsigned __int16 *
0x1800044a0  mov     rcx, rsi; this
0x1800044a3  call    ?HasSMARTFailurePredicted@DiskContext@@AEAAHPEAG@Z; DiskContext::HasSMARTFailurePredicted(ushort *)
0x1800044a8  test    eax, eax
0x1800044aa  jz      short loc_180004508
0x1800044ac  mov     rcx, r13; Size
0x1800044af  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800044b4  mov     [rsp+0B8h+var_70], rax
0x1800044b9  test    rax, rax
0x1800044bc  jz      short loc_1800044D4
0x1800044be  mov     rcx, [rsi+8]
0x1800044c2  mov     [rax], rcx
0x1800044c5  mov     [rax+8], r12w
0x1800044ca  mov     [rax+18h], r12
0x1800044ce  mov     [rax+10h], r12
0x1800044d2  jmp     short loc_1800044D7
0x1800044d4  mov     rax, r12
0x1800044d7  mov     [rsi+18h], rax
0x1800044db  test    rax, rax
0x1800044de  jnz     short loc_180004508
0x1800044e0  lea     edi, [rax+0Eh]
0x1800044e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044ea  cmp     rcx, rbx
0x1800044ed  jz      short loc_180004508
0x1800044ef  test    byte ptr [rcx+1Ch], 1
0x1800044f3  jz      short loc_180004508
0x1800044f5  lea     edx, [rax+13h]
0x1800044f8  mov     rcx, [rcx+10h]
0x1800044fc  lea     r8, WPP_6840784a3f2339c3fb8e3bd3d3f5f082_Traceguids
0x180004503  call    WPP_SF_
0x180004508  call    cs:__imp_GetProcessHeap
0x18000450e  mov     r8, r15; lpMem
0x180004511  xor     edx, edx; dwFlags
0x180004513  mov     rcx, rax; hHeap
0x180004516  call    cs:__imp_HeapFree
0x18000451c  mov     eax, edi
0x18000451e  mov     rcx, [rsp+0B8h+var_48]
0x180004523  xor     rcx, rsp; StackCookie
0x180004526  call    __security_check_cookie
0x18000452b  mov     rbx, [rsp+0B8h+arg_8]
0x180004533  add     rsp, 80h
0x18000453a  pop     r15
0x18000453c  pop     r14
0x18000453e  pop     r13
0x180004540  pop     r12
0x180004542  pop     rdi
0x180004543  pop     rsi
0x180004544  pop     rbp
0x180004545  retn
```
