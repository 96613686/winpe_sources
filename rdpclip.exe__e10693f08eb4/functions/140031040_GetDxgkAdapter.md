# GetDxgkAdapter

- ea: `0x140031040`
- end: `0x1400313e2`
- name: `GetDxgkAdapter`
- size: `930`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140031684`

## callees

- `0x1400030d3`
- `0x140005750`
- `0x140031040`
- `0x1400319dc`
- `0x14006a120`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003109b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031132`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400311ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400311f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003109b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031132`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400311ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400311f8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140031222`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140031222`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140031214`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140031280`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140031349`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140031214`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140031280`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140031349`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003128e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140031357`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003128e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140031357`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x140031275`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x140031275`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1400311e7`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x140031260`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1400311e7`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x140031260`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1400311ba`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1400311ba`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1400313b4`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1400313b4`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x140031087`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x140031087`
- `DEVOBJ!DevObjGetClassDevs` at `0x140031128`
- `DEVOBJ!DevObjGetClassDevs` at `0x140031128`

## string_xrefs

- `0x1400310e1`: `DevObjCreateDeviceInfoList`
- `0x14003131b`: `Failed to copy graphics adapter device name`

## pseudocode

```c
__int64 __fastcall GetDxgkAdapter(__int64 a1, wchar_t *a2)
{
  unsigned int v3; // r15d
  __int64 DeviceInfoList; // rdi
  signed int LastError; // eax
  signed int v6; // ecx
  signed int v7; // eax
  signed int v8; // ecx
  unsigned int i; // r14d
  signed int v10; // eax
  signed int v11; // ecx
  unsigned int v12; // ebx
  HANDLE ProcessHeap; // rax
  wchar_t *v14; // rax
  wchar_t *v15; // rbx
  HANDLE v16; // rax
  int v17; // edx
  __int64 v18; // rcx
  HRESULT v19; // r11d
  HANDLE v20; // rax
  __int64 v22; // [rsp+28h] [rbp-38h]
  __int64 v23; // [rsp+28h] [rbp-38h]
  __int64 v24; // [rsp+28h] [rbp-38h]
  SIZE_T dwBytes; // [rsp+30h] [rbp-30h] BYREF
  __int128 v26; // [rsp+38h] [rbp-28h] BYREF
  __int128 v27; // [rsp+48h] [rbp-18h]

  v3 = 0;
  v26 = 0;
  v27 = 0;
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  if ( DeviceInfoList == -1 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          (unsigned int)&WPP_42a33f02ea92324bb459c59c3f9ce2d6_Traceguids,
          -1,
          (__int64)"DevObjCreateDeviceInfoList",
          v6);
      }
      return v3;
    }
  }
  if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_INDIRECT_DISPLAY_DEVICE_ARRIVAL, 0, 18, 0, 0) )
  {
    v7 = GetLastError();
    v8 = v7;
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LODWORD(v22) = v8;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          (unsigned int)&WPP_42a33f02ea92324bb459c59c3f9ce2d6_Traceguids,
          -1,
          (__int64)"DevObjGetClassDevs",
          v22);
      }
      goto LABEL_43;
    }
  }
  for ( i = 0; ; ++i )
  {
    v26 = 0;
    LODWORD(v26) = 32;
    v27 = 0;
    if ( !(unsigned int)DevObjEnumDeviceInterfaces(DeviceInfoList, 0, &GUID_INDIRECT_DISPLAY_DEVICE_ARRIVAL, i, &v26) )
      goto LABEL_43;
    LODWORD(dwBytes) = 0;
    DevObjGetDeviceInterfaceDetail(DeviceInfoList, &v26, 0, 0, &dwBytes, 0);
    if ( GetLastError() != 122 )
    {
      v10 = GetLastError();
      v11 = v10;
      if ( v10 > 0 )
        v11 = (unsigned __int16)v10 | 0x80070000;
      if ( v11 < 0 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_43;
        }
        LODWORD(v23) = v11;
        v17 = 20;
        v18 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        goto LABEL_42;
      }
    }
    v12 = dwBytes;
    ProcessHeap = GetProcessHeap();
    v14 = (wchar_t *)HeapAlloc(ProcessHeap, 0, v12);
    v15 = v14;
    if ( !v14 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_43;
      }
      v18 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v17 = 21;
      LODWORD(v23) = -2147024882;
LABEL_42:
      WPP_SF_DsD(
        v18,
        v17,
        (unsigned int)&WPP_42a33f02ea92324bb459c59c3f9ce2d6_Traceguids,
        -1,
        (__int64)"DevObjGetDeviceInterfaceDetail",
        v23);
      goto LABEL_43;
    }
    memset_0(v14, 0, (unsigned int)dwBytes);
    *(_DWORD *)v15 = 8;
    if ( (unsigned int)DevObjGetDeviceInterfaceDetail(DeviceInfoList, &v26, v15, (unsigned int)dwBytes, 0, 0) )
    {
      if ( StrStrIW(v15 + 2, L"RdpIdd_IndirectDisplay") )
        break;
    }
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v15);
  }
  v19 = StringCchCopyW(a2, 0x104u, v15 + 2);
  if ( v19 >= 0 )
  {
    v3 = 1;
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LODWORD(v24) = v19;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      (unsigned int)&WPP_42a33f02ea92324bb459c59c3f9ce2d6_Traceguids,
      -1,
      (__int64)"Failed to copy graphics adapter device name",
      v24);
  }
  v20 = GetProcessHeap();
  HeapFree(v20, 0, v15);
LABEL_43:
  if ( DeviceInfoList != -1 )
    DevObjDestroyDeviceInfoList(DeviceInfoList);
  return v3;
}

```

## disassembly

```asm
0x140031040  mov     [rsp-28h+arg_0], rbx
0x140031045  mov     [rsp-28h+arg_10], rsi
0x14003104a  push    rbp
0x14003104b  push    rdi
0x14003104c  push    r12
0x14003104e  push    r14
0x140031050  push    r15
0x140031052  mov     rbp, rsp
0x140031055  sub     rsp, 60h
0x140031059  mov     rax, cs:__security_cookie
0x140031060  xor     rax, rsp
0x140031063  mov     [rbp+var_8], rax
0x140031067  xorps   xmm0, xmm0
0x14003106a  mov     r12, rdx
0x14003106d  xor     r15d, r15d
0x140031070  xor     edx, edx
0x140031072  xor     r9d, r9d
0x140031075  mov     [rsp+60h+var_40], r15
0x14003107a  xor     r8d, r8d
0x14003107d  xor     ecx, ecx
0x14003107f  movups  [rbp+var_28], xmm0
0x140031083  movups  [rbp+var_18], xmm0
0x140031087  call    cs:__imp_DevObjCreateDeviceInfoList
0x14003108d  mov     rdi, rax
0x140031090  mov     ebx, 80070000h
0x140031095  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140031099  jnz     short loc_14003110B
0x14003109b  call    cs:__imp_GetLastError
0x1400310a1  mov     ecx, eax
0x1400310a3  test    eax, eax
0x1400310a5  jle     short loc_1400310AC
0x1400310a7  movzx   ecx, ax
0x1400310aa  or      ecx, ebx
0x1400310ac  test    ecx, ecx
0x1400310ae  jns     short loc_14003110B
0x1400310b0  mov     r10, cs:WPP_GLOBAL_Control
0x1400310b7  lea     rax, WPP_GLOBAL_Control
0x1400310be  cmp     r10, rax
0x1400310c1  jz      loc_1400313BA
0x1400310c7  test    byte ptr [r10+1Ch], 8
0x1400310cc  jz      loc_1400313BA
0x1400310d2  cmp     byte ptr [r10+19h], 2
0x1400310d7  jb      loc_1400313BA
0x1400310dd  mov     dword ptr [rsp+60h+var_38], ecx
0x1400310e1  lea     rax, aDevobjcreatede_1; "DevObjCreateDeviceInfoList"
0x1400310e8  mov     rcx, [r10+10h]
0x1400310ec  lea     r8, WPP_42a33f02ea92324bb459c59c3f9ce2d6_Traceguids
0x1400310f3  mov     edx, 12h
0x1400310f8  mov     [rsp+60h+var_40], rax
0x1400310fd  or      r9d, 0FFFFFFFFh
0x140031101  call    WPP_SF_DsD
0x140031106  jmp     loc_1400313BA
0x14003110b  mov     [rsp+60h+var_38], r15
0x140031110  lea     rdx, GUID_INDIRECT_DISPLAY_DEVICE_ARRIVAL
0x140031117  mov     r9d, 12h
0x14003111d  mov     [rsp+60h+var_40], r15
0x140031122  xor     r8d, r8d
0x140031125  mov     rcx, rdi
0x140031128  call    cs:__imp_DevObjGetClassDevs
0x14003112e  test    eax, eax
0x140031130  jnz     short loc_14003118D
0x140031132  call    cs:__imp_GetLastError
0x140031138  mov     ecx, eax
0x14003113a  test    eax, eax
0x14003113c  jle     short loc_140031143
0x14003113e  movzx   ecx, ax
0x140031141  or      ecx, ebx
0x140031143  test    ecx, ecx
0x140031145  jns     short loc_14003118D
0x140031147  mov     r10, cs:WPP_GLOBAL_Control
0x14003114e  lea     rax, WPP_GLOBAL_Control
0x140031155  cmp     r10, rax
0x140031158  jz      loc_1400313AB
0x14003115e  test    byte ptr [r10+1Ch], 8
0x140031163  jz      loc_1400313AB
0x140031169  cmp     byte ptr [r10+19h], 2
0x14003116e  jb      loc_1400313AB
0x140031174  mov     dword ptr [rsp+60h+var_38], ecx
0x140031178  lea     rax, aDevobjgetclass_0; "DevObjGetClassDevs"
0x14003117f  mov     rcx, [r10+10h]
0x140031183  mov     edx, 13h
0x140031188  jmp     loc_140031396
0x14003118d  xor     r14d, r14d
0x140031190  xorps   xmm0, xmm0
0x140031193  lea     rax, [rbp+var_28]
0x140031197  movups  [rbp+var_28], xmm0
0x14003119b  mov     r9d, r14d
0x14003119e  mov     dword ptr [rbp+var_28], 20h ; ' '
0x1400311a5  lea     r8, GUID_INDIRECT_DISPLAY_DEVICE_ARRIVAL
0x1400311ac  mov     [rsp+60h+var_40], rax
0x1400311b1  xor     edx, edx
0x1400311b3  mov     rcx, rdi
0x1400311b6  movups  [rbp+var_18], xmm0
0x1400311ba  call    cs:__imp_DevObjEnumDeviceInterfaces
0x1400311c0  test    eax, eax
0x1400311c2  jz      loc_1400313AB
0x1400311c8  lea     rax, [rbp+dwBytes]
0x1400311cc  mov     [rsp+60h+var_38], r15
0x1400311d1  xor     r9d, r9d
0x1400311d4  mov     [rsp+60h+var_40], rax
0x1400311d9  xor     r8d, r8d
0x1400311dc  mov     dword ptr [rbp+dwBytes], r15d
0x1400311e0  lea     rdx, [rbp+var_28]
0x1400311e4  mov     rcx, rdi
0x1400311e7  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x1400311ed  call    cs:__imp_GetLastError
0x1400311f3  cmp     eax, 7Ah ; 'z'
0x1400311f6  jz      short loc_140031211
0x1400311f8  call    cs:__imp_GetLastError
0x1400311fe  mov     ecx, eax
0x140031200  test    eax, eax
0x140031202  jle     short loc_140031209
0x140031204  movzx   ecx, ax
0x140031207  or      ecx, ebx
0x140031209  test    ecx, ecx
0x14003120b  js      loc_1400312A1
0x140031211  mov     ebx, dword ptr [rbp+dwBytes]
0x140031214  call    cs:__imp_GetProcessHeap
0x14003121a  mov     r8d, ebx; dwBytes
0x14003121d  xor     edx, edx; dwFlags
0x14003121f  mov     rcx, rax; hHeap
0x140031222  call    cs:__imp_HeapAlloc
0x140031228  mov     rbx, rax
0x14003122b  test    rax, rax
0x14003122e  jz      loc_14003135F
0x140031234  mov     r8d, dword ptr [rbp+dwBytes]; Size
0x140031238  xor     edx, edx; Val
0x14003123a  mov     rcx, rax; void *
0x14003123d  call    memset_0
0x140031242  mov     dword ptr [rbx], 8
0x140031248  lea     rdx, [rbp+var_28]
0x14003124c  mov     r9d, dword ptr [rbp+dwBytes]
0x140031250  mov     r8, rbx
0x140031253  mov     rcx, rdi
0x140031256  mov     [rsp+60h+var_38], r15
0x14003125b  mov     [rsp+60h+var_40], r15
0x140031260  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x140031266  test    eax, eax
0x140031268  jz      short loc_140031280
0x14003126a  lea     rdx, pszSrch; "RdpIdd_IndirectDisplay"
0x140031271  lea     rcx, [rbx+4]; pszFirst
0x140031275  call    cs:__imp_StrStrIW
0x14003127b  test    rax, rax
0x14003127e  jnz     short loc_1400312E0
0x140031280  call    cs:__imp_GetProcessHeap
0x140031286  mov     r8, rbx; lpMem
0x140031289  xor     edx, edx; dwFlags
0x14003128b  mov     rcx, rax; hHeap
0x14003128e  call    cs:__imp_HeapFree
0x140031294  inc     r14d
0x140031297  mov     ebx, 80070000h
0x14003129c  jmp     loc_140031190
0x1400312a1  mov     r10, cs:WPP_GLOBAL_Control
0x1400312a8  lea     rax, WPP_GLOBAL_Control
0x1400312af  cmp     r10, rax
0x1400312b2  jz      loc_1400313AB
0x1400312b8  test    byte ptr [r10+1Ch], 8
0x1400312bd  jz      loc_1400313AB
0x1400312c3  cmp     byte ptr [r10+19h], 2
0x1400312c8  jb      loc_1400313AB
0x1400312ce  mov     dword ptr [rsp+60h+var_38], ecx
0x1400312d2  mov     edx, 14h
0x1400312d7  mov     rcx, [r10+10h]
0x1400312db  jmp     loc_14003138F
0x1400312e0  lea     r8, [rbx+4]; pszSrc
0x1400312e4  mov     edx, 104h; cchDest
0x1400312e9  mov     rcx, r12; pszDest
0x1400312ec  call    StringCchCopyW
0x1400312f1  mov     r11d, eax
0x1400312f4  test    eax, eax
0x1400312f6  jns     short loc_140031343
0x1400312f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400312ff  lea     rax, WPP_GLOBAL_Control
0x140031306  cmp     rcx, rax
0x140031309  jz      short loc_140031349
0x14003130b  test    byte ptr [rcx+1Ch], 8
0x14003130f  jz      short loc_140031349
0x140031311  cmp     byte ptr [rcx+19h], 2
0x140031315  jb      short loc_140031349
0x140031317  mov     rcx, [rcx+10h]
0x14003131b  lea     rax, aFailedToCopyGr; "Failed to copy graphics adapter device "...
0x140031322  mov     dword ptr [rsp+60h+var_38], r11d
0x140031327  lea     r8, WPP_42a33f02ea92324bb459c59c3f9ce2d6_Traceguids
0x14003132e  mov     edx, 16h
0x140031333  mov     [rsp+60h+var_40], rax
0x140031338  or      r9d, 0FFFFFFFFh
0x14003133c  call    WPP_SF_DsD
0x140031341  jmp     short loc_140031349
0x140031343  mov     r15d, 1
0x140031349  call    cs:__imp_GetProcessHeap
0x14003134f  mov     r8, rbx; lpMem
0x140031352  xor     edx, edx; dwFlags
0x140031354  mov     rcx, rax; hHeap
0x140031357  call    cs:__imp_HeapFree
0x14003135d  jmp     short loc_1400313AB
0x14003135f  mov     rcx, cs:WPP_GLOBAL_Control
0x140031366  lea     rax, WPP_GLOBAL_Control
0x14003136d  cmp     rcx, rax
0x140031370  jz      short loc_1400313AB
0x140031372  test    byte ptr [rcx+1Ch], 8
0x140031376  jz      short loc_1400313AB
0x140031378  cmp     byte ptr [rcx+19h], 2
0x14003137c  jb      short loc_1400313AB
0x14003137e  mov     rcx, [rcx+10h]
0x140031382  mov     edx, 15h
0x140031387  mov     dword ptr [rsp+60h+var_38], 8007000Eh
0x14003138f  lea     rax, aDevobjgetdevic_2; "DevObjGetDeviceInterfaceDetail"
0x140031396  or      r9d, 0FFFFFFFFh
0x14003139a  mov     [rsp+60h+var_40], rax
0x14003139f  lea     r8, WPP_42a33f02ea92324bb459c59c3f9ce2d6_Traceguids
0x1400313a6  call    WPP_SF_DsD
0x1400313ab  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1400313af  jz      short loc_1400313BA
0x1400313b1  mov     rcx, rdi
0x1400313b4  call    cs:__imp_DevObjDestroyDeviceInfoList
0x1400313ba  mov     eax, r15d
0x1400313bd  mov     rcx, [rbp+var_8]
0x1400313c1  xor     rcx, rsp; StackCookie
0x1400313c4  call    __security_check_cookie
0x1400313c9  lea     r11, [rsp+60h+var_s0]
0x1400313ce  mov     rbx, [r11+30h]
0x1400313d2  mov     rsi, [r11+40h]
0x1400313d6  mov     rsp, r11
0x1400313d9  pop     r15
0x1400313db  pop     r14
0x1400313dd  pop     r12
0x1400313df  pop     rdi
0x1400313e0  pop     rbp
0x1400313e1  retn
```
