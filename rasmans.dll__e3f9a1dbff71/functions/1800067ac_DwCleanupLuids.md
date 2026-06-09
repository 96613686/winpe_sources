# DwCleanupLuids

- ea: `0x1800067ac`
- end: `0x180006b4f`
- name: `DwCleanupLuids`
- size: `931`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800074c8`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x1800067ac`
- `0x18004a1a8`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180006824`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180006824`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000691e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000691e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006b0c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006b0c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800068ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006afe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800068ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006afe`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006910`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006910`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800068bd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180006979`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800068bd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180006979`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006857`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006857`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006aec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006aec`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x180006aa1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x180006aa1`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180006a42`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180006a42`

## string_xrefs

- `0x180006839`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\Parameters`
- `0x18000682a`: `SYSTEM\CurrentControlSet\Services\RasMan\Parameters`

## pseudocode

```c
__int64 DwCleanupLuids()
{
  struct _LIST_ENTRY *v0; // rcx
  BYTE *v1; // r14
  char IsStateSeparationEnabled; // al
  const WCHAR *v3; // rdx
  DWORD LastError; // eax
  struct _LIST_ENTRY *v5; // rcx
  __int64 v6; // rdx
  DWORD v7; // ebx
  HANDLE ProcessHeap; // rax
  __int64 v9; // rsi
  DWORD i; // edi
  struct _LIST_ENTRY *Flink; // rbx
  DWORD v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // ebx
  struct _LIST_ENTRY *v15; // rcx
  HANDLE v16; // rax
  HANDLE hDevice[2]; // [rsp+40h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+90h] [rbp+40h] BYREF
  DWORD BytesReturned; // [rsp+98h] [rbp+48h] BYREF
  HKEY hKey; // [rsp+A0h] [rbp+50h] BYREF
  __int64 OutBuffer; // [rsp+A8h] [rbp+58h] BYREF

  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 224, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids);
  }
  hDevice[0] = (HANDLE)-1LL;
  v1 = 0;
  OutBuffer = 0;
  cbData = 0;
  BytesReturned = 0;
  hKey = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(v0);
  v3 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\Parameters";
  if ( !IsStateSeparationEnabled )
    v3 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Parameters";
  LastError = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x20007u, &hKey);
  if ( LastError )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v6 = 225;
LABEL_12:
      WPP_SF_d(v5[1].Flink, v6, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids, LastError);
    }
  }
  else
  {
    LastError = RegQueryValueExA(hKey, "AllocatedLuids", 0, 0, 0, &cbData);
    if ( !LastError )
    {
      if ( cbData )
      {
        v7 = cbData;
        ProcessHeap = GetProcessHeap();
        v1 = (BYTE *)HeapAlloc(ProcessHeap, 8u, v7);
        if ( !v1 )
        {
          LastError = GetLastError();
          if ( LastError )
          {
            v5 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              v6 = 227;
              goto LABEL_12;
            }
          }
          goto LABEL_42;
        }
        LastError = RegQueryValueExA(hKey, "AllocatedLuids", 0, 0, v1, &cbData);
        if ( LastError )
        {
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            v6 = 228;
            goto LABEL_12;
          }
          goto LABEL_42;
        }
      }
      LastError = WanarpDeviceOpen(hDevice);
      if ( LastError )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          v6 = 229;
          goto LABEL_12;
        }
      }
      else
      {
        v9 = 0;
        for ( i = cbData >> 2; (unsigned int)v9 < i; v9 = (unsigned int)(v9 + 1) )
        {
          LOWORD(OutBuffer) = 23;
          HIDWORD(OutBuffer) = *(_DWORD *)&v1[4 * v9];
          if ( !DeviceIoControl(hDevice[0], 0x90018020, &OutBuffer, 8u, &OutBuffer, 8u, &BytesReturned, 0)
            && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            Flink = WPP_GLOBAL_Control[1].Flink;
            v12 = GetLastError();
            WPP_SF_d(Flink, 230, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids, v12);
          }
        }
      }
      goto LABEL_42;
    }
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v6 = 226;
      goto LABEL_12;
    }
  }
LABEL_42:
  v13 = RegDeleteValueA(hKey, "AllocatedLuids");
  v14 = v13;
  if ( !v13 )
  {
LABEL_47:
    v15 = WPP_GLOBAL_Control;
    goto LABEL_48;
  }
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 231, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids, v13);
    goto LABEL_47;
  }
LABEL_48:
  if ( hKey )
  {
    RegCloseKey(hKey);
    v15 = WPP_GLOBAL_Control;
  }
  if ( v1 )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v1);
    v15 = WPP_GLOBAL_Control;
  }
  if ( v15 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v15[1].Blink) & 0x2000) != 0
    && BYTE1(v15[1].Blink) >= 6u )
  {
    WPP_SF_d(v15[1].Flink, 232, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids, v14);
  }
  return v14;
}

```

## disassembly

```asm
0x1800067ac  push    rbp
0x1800067ae  push    rbx
0x1800067af  push    rsi
0x1800067b0  push    rdi
0x1800067b1  push    r12
0x1800067b3  push    r13
0x1800067b5  push    r14
0x1800067b7  mov     rbp, rsp
0x1800067ba  sub     rsp, 50h
0x1800067be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800067c5  lea     r13, WPP_GLOBAL_Control
0x1800067cc  lea     rdi, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids
0x1800067d3  mov     r12d, 2000h
0x1800067d9  cmp     rcx, r13
0x1800067dc  jz      short loc_1800067FB
0x1800067de  test    [rcx+1Ch], r12d
0x1800067e2  jz      short loc_1800067FB
0x1800067e4  cmp     byte ptr [rcx+19h], 6
0x1800067e8  jb      short loc_1800067FB
0x1800067ea  mov     rcx, [rcx+10h]
0x1800067ee  mov     edx, 0E0h
0x1800067f3  mov     r8, rdi
0x1800067f6  call    WPP_SF_
0x1800067fb  mov     [rbp+hDevice], 0FFFFFFFFFFFFFFFFh
0x180006803  xor     r14d, r14d
0x180006806  mov     [rbp+OutBuffer], 0
0x18000680e  mov     [rbp+cbData], 0
0x180006815  mov     [rbp+BytesReturned], 0
0x18000681c  mov     [rbp+hKey], 0
0x180006824  call    cs:__imp_RtlIsStateSeparationEnabled
0x18000682a  lea     rcx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x180006831  mov     r9d, 20007h; samDesired
0x180006837  test    al, al
0x180006839  lea     rdx, aOsdataSystemCu_3; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x180006840  lea     rax, [rbp+hKey]
0x180006844  cmovz   rdx, rcx; lpSubKey
0x180006848  mov     [rsp+50h+phkResult], rax; phkResult
0x18000684d  xor     r8d, r8d; ulOptions
0x180006850  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006857  call    cs:__imp_RegOpenKeyExW
0x18000685d  test    eax, eax
0x18000685f  jz      short loc_18000689E
0x180006861  mov     rcx, cs:WPP_GLOBAL_Control
0x180006868  cmp     rcx, r13
0x18000686b  jz      loc_180006A96
0x180006871  test    [rcx+1Ch], r12d
0x180006875  jz      loc_180006A96
0x18000687b  cmp     byte ptr [rcx+19h], 2
0x18000687f  jb      loc_180006A96
0x180006885  mov     edx, 0E1h
0x18000688a  mov     rcx, [rcx+10h]
0x18000688e  mov     r9d, eax
0x180006891  mov     r8, rdi
0x180006894  call    WPP_SF_d
0x180006899  jmp     loc_180006A96
0x18000689e  mov     rcx, [rbp+hKey]; hKey
0x1800068a2  lea     rax, [rbp+cbData]
0x1800068a6  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1800068ab  lea     rdx, ValueName; "AllocatedLuids"
0x1800068b2  xor     r9d, r9d; lpType
0x1800068b5  mov     [rsp+50h+phkResult], r14; lpData
0x1800068ba  xor     r8d, r8d; lpReserved
0x1800068bd  call    cs:__imp_RegQueryValueExA
0x1800068c3  test    eax, eax
0x1800068c5  jz      short loc_1800068F2
0x1800068c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800068ce  cmp     rcx, r13
0x1800068d1  jz      loc_180006A96
0x1800068d7  test    [rcx+1Ch], r12d
0x1800068db  jz      loc_180006A96
0x1800068e1  cmp     byte ptr [rcx+19h], 2
0x1800068e5  jb      loc_180006A96
0x1800068eb  mov     edx, 0E2h
0x1800068f0  jmp     short loc_18000688A
0x1800068f2  mov     eax, [rbp+cbData]
0x1800068f5  test    eax, eax
0x1800068f7  jz      loc_1800069B1
0x1800068fd  mov     ebx, eax
0x1800068ff  call    cs:__imp_GetProcessHeap
0x180006905  mov     r8d, ebx; dwBytes
0x180006908  mov     edx, 8; dwFlags
0x18000690d  mov     rcx, rax; hHeap
0x180006910  call    cs:__imp_HeapAlloc
0x180006916  mov     r14, rax
0x180006919  test    rax, rax
0x18000691c  jnz     short loc_18000695A
0x18000691e  call    cs:__imp_GetLastError
0x180006924  test    eax, eax
0x180006926  jz      loc_180006A96
0x18000692c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006933  cmp     rcx, r13
0x180006936  jz      loc_180006A96
0x18000693c  test    [rcx+1Ch], r12d
0x180006940  jz      loc_180006A96
0x180006946  cmp     byte ptr [rcx+19h], 2
0x18000694a  jb      loc_180006A96
0x180006950  mov     edx, 0E3h
0x180006955  jmp     loc_18000688A
0x18000695a  mov     rcx, [rbp+hKey]; hKey
0x18000695e  lea     rax, [rbp+cbData]
0x180006962  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180006967  lea     rdx, ValueName; "AllocatedLuids"
0x18000696e  xor     r9d, r9d; lpType
0x180006971  mov     [rsp+50h+phkResult], r14; lpData
0x180006976  xor     r8d, r8d; lpReserved
0x180006979  call    cs:__imp_RegQueryValueExA
0x18000697f  test    eax, eax
0x180006981  jz      short loc_1800069B1
0x180006983  mov     rcx, cs:WPP_GLOBAL_Control
0x18000698a  cmp     rcx, r13
0x18000698d  jz      loc_180006A96
0x180006993  test    [rcx+1Ch], r12d
0x180006997  jz      loc_180006A96
0x18000699d  cmp     byte ptr [rcx+19h], 2
0x1800069a1  jb      loc_180006A96
0x1800069a7  mov     edx, 0E4h
0x1800069ac  jmp     loc_18000688A
0x1800069b1  lea     rcx, [rbp+hDevice]
0x1800069b5  call    WanarpDeviceOpen
0x1800069ba  test    eax, eax
0x1800069bc  jz      short loc_1800069EC
0x1800069be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800069c5  cmp     rcx, r13
0x1800069c8  jz      loc_180006A96
0x1800069ce  test    [rcx+1Ch], r12d
0x1800069d2  jz      loc_180006A96
0x1800069d8  cmp     byte ptr [rcx+19h], 2
0x1800069dc  jb      loc_180006A96
0x1800069e2  mov     edx, 0E5h
0x1800069e7  jmp     loc_18000688A
0x1800069ec  mov     edi, [rbp+cbData]
0x1800069ef  xor     esi, esi
0x1800069f1  shr     edi, 2
0x1800069f4  test    edi, edi
0x1800069f6  jz      loc_180006A8F
0x1800069fc  mov     [rsp+50h+lpOverlapped], 0; lpOverlapped
0x180006a05  lea     r8, [rbp+OutBuffer]; lpInBuffer
0x180006a09  mov     eax, 17h
0x180006a0e  mov     r9d, 8; nInBufferSize
0x180006a14  mov     word ptr [rbp+OutBuffer], ax
0x180006a18  mov     edx, 90018020h; dwIoControlCode
0x180006a1d  mov     ecx, [r14+rsi*4]
0x180006a21  lea     rax, [rbp+BytesReturned]
0x180006a25  mov     [rsp+50h+lpBytesReturned], rax; lpBytesReturned
0x180006a2a  lea     rax, [rbp+OutBuffer]
0x180006a2e  mov     dword ptr [rbp+OutBuffer+4], ecx
0x180006a31  mov     rcx, [rbp+hDevice]; hDevice
0x180006a35  mov     dword ptr [rsp+50h+lpcbData], 8; nOutBufferSize
0x180006a3d  mov     [rsp+50h+phkResult], rax; lpOutBuffer
0x180006a42  call    cs:__imp_DeviceIoControl
0x180006a48  test    eax, eax
0x180006a4a  jnz     short loc_180006A85
0x180006a4c  mov     rbx, cs:WPP_GLOBAL_Control
0x180006a53  cmp     rbx, r13
0x180006a56  jz      short loc_180006A85
0x180006a58  test    [rbx+1Ch], r12d
0x180006a5c  jz      short loc_180006A85
0x180006a5e  cmp     byte ptr [rbx+19h], 2
0x180006a62  jb      short loc_180006A85
0x180006a64  mov     rbx, [rbx+10h]
0x180006a68  call    cs:__imp_GetLastError
0x180006a6e  mov     edx, 0E6h
0x180006a73  lea     r8, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids
0x180006a7a  mov     r9d, eax
0x180006a7d  mov     rcx, rbx
0x180006a80  call    WPP_SF_d
0x180006a85  inc     esi
0x180006a87  cmp     esi, edi
0x180006a89  jb      loc_1800069FC
0x180006a8f  lea     rdi, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids
0x180006a96  mov     rcx, [rbp+hKey]; hKey
0x180006a9a  lea     rdx, ValueName; "AllocatedLuids"
0x180006aa1  call    cs:__imp_RegDeleteValueA
0x180006aa7  mov     ebx, eax
0x180006aa9  test    eax, eax
0x180006aab  jz      short loc_180006AD9
0x180006aad  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ab4  cmp     rcx, r13
0x180006ab7  jz      short loc_180006AE0
0x180006ab9  test    [rcx+1Ch], r12d
0x180006abd  jz      short loc_180006AE0
0x180006abf  cmp     byte ptr [rcx+19h], 2
0x180006ac3  jb      short loc_180006AE0
0x180006ac5  mov     rcx, [rcx+10h]
0x180006ac9  mov     edx, 0E7h
0x180006ace  mov     r9d, eax
0x180006ad1  mov     r8, rdi
0x180006ad4  call    WPP_SF_d
0x180006ad9  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ae0  mov     rax, [rbp+hKey]
0x180006ae4  test    rax, rax
0x180006ae7  jz      short loc_180006AF9
0x180006ae9  mov     rcx, rax; hKey
0x180006aec  call    cs:__imp_RegCloseKey
0x180006af2  mov     rcx, cs:WPP_GLOBAL_Control
0x180006af9  test    r14, r14
0x180006afc  jz      short loc_180006B19
0x180006afe  call    cs:__imp_GetProcessHeap
0x180006b04  mov     r8, r14; lpMem
0x180006b07  xor     edx, edx; dwFlags
0x180006b09  mov     rcx, rax; hHeap
0x180006b0c  call    cs:__imp_HeapFree
0x180006b12  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b19  cmp     rcx, r13
0x180006b1c  jz      short loc_180006B3E
0x180006b1e  test    [rcx+1Ch], r12d
0x180006b22  jz      short loc_180006B3E
0x180006b24  cmp     byte ptr [rcx+19h], 6
0x180006b28  jb      short loc_180006B3E
0x180006b2a  mov     rcx, [rcx+10h]
0x180006b2e  mov     edx, 0E8h
0x180006b33  mov     r9d, ebx
0x180006b36  mov     r8, rdi
0x180006b39  call    WPP_SF_d
0x180006b3e  mov     eax, ebx
0x180006b40  add     rsp, 50h
0x180006b44  pop     r14
0x180006b46  pop     r13
0x180006b48  pop     r12
0x180006b4a  pop     rdi
0x180006b4b  pop     rsi
0x180006b4c  pop     rbx
0x180006b4d  pop     rbp
0x180006b4e  retn
```
