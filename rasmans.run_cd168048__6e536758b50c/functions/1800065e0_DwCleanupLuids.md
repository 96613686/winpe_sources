# DwCleanupLuids

- ea: `0x1800065e0`
- end: `0x1800069d2`
- name: `DwCleanupLuids`
- size: `1010`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800073ac`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x1800065e0`
- `0x18004c5f0`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180006658`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180006658`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006770`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800068cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006770`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800068cc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000675c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000675c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006988`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006988`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006745`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006974`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006745`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006974`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006691`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006691`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x18000690b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x18000690b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800066fd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800067d1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800066fd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800067d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000695c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000695c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800068a0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800068a0`

## string_xrefs

- `0x180006673`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\Parameters`
- `0x180006664`: `SYSTEM\CurrentControlSet\Services\RasMan\Parameters`

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
0x1800065e0  push    rbp
0x1800065e2  push    rbx
0x1800065e3  push    rsi
0x1800065e4  push    rdi
0x1800065e5  push    r12
0x1800065e7  push    r13
0x1800065e9  push    r14
0x1800065eb  mov     rbp, rsp
0x1800065ee  sub     rsp, 50h
0x1800065f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800065f9  lea     r13, WPP_GLOBAL_Control
0x180006600  lea     rdi, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids
0x180006607  mov     r12d, 2000h
0x18000660d  cmp     rcx, r13
0x180006610  jz      short loc_18000662F
0x180006612  test    [rcx+1Ch], r12d
0x180006616  jz      short loc_18000662F
0x180006618  cmp     byte ptr [rcx+19h], 6
0x18000661c  jb      short loc_18000662F
0x18000661e  mov     rcx, [rcx+10h]
0x180006622  mov     edx, 0E0h
0x180006627  mov     r8, rdi
0x18000662a  call    WPP_SF_
0x18000662f  mov     [rbp+hDevice], 0FFFFFFFFFFFFFFFFh
0x180006637  xor     r14d, r14d
0x18000663a  mov     [rbp+OutBuffer], 0
0x180006642  mov     [rbp+cbData], 0
0x180006649  mov     [rbp+BytesReturned], 0
0x180006650  mov     [rbp+hKey], 0
0x180006658  call    cs:__imp_RtlIsStateSeparationEnabled
0x18000665f  nop     dword ptr [rax+rax+00h]
0x180006664  lea     rcx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x18000666b  mov     r9d, 20007h; samDesired
0x180006671  test    al, al
0x180006673  lea     rdx, aOsdataSystemCu_3; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x18000667a  lea     rax, [rbp+hKey]
0x18000667e  cmovz   rdx, rcx; lpSubKey
0x180006682  mov     [rsp+50h+phkResult], rax; phkResult
0x180006687  xor     r8d, r8d; ulOptions
0x18000668a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006691  call    cs:__imp_RegOpenKeyExW
0x180006698  nop     dword ptr [rax+rax+00h]
0x18000669d  test    eax, eax
0x18000669f  jz      short loc_1800066DE
0x1800066a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800066a8  cmp     rcx, r13
0x1800066ab  jz      loc_180006900
0x1800066b1  test    [rcx+1Ch], r12d
0x1800066b5  jz      loc_180006900
0x1800066bb  cmp     byte ptr [rcx+19h], 2
0x1800066bf  jb      loc_180006900
0x1800066c5  mov     edx, 0E1h
0x1800066ca  mov     rcx, [rcx+10h]
0x1800066ce  mov     r9d, eax
0x1800066d1  mov     r8, rdi
0x1800066d4  call    WPP_SF_d
0x1800066d9  jmp     loc_180006900
0x1800066de  mov     rcx, [rbp+hKey]; hKey
0x1800066e2  lea     rax, [rbp+cbData]
0x1800066e6  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1800066eb  lea     rdx, ValueName; "AllocatedLuids"
0x1800066f2  xor     r9d, r9d; lpType
0x1800066f5  mov     [rsp+50h+phkResult], r14; lpData
0x1800066fa  xor     r8d, r8d; lpReserved
0x1800066fd  call    cs:__imp_RegQueryValueExA
0x180006704  nop     dword ptr [rax+rax+00h]
0x180006709  test    eax, eax
0x18000670b  jz      short loc_180006738
0x18000670d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006714  cmp     rcx, r13
0x180006717  jz      loc_180006900
0x18000671d  test    [rcx+1Ch], r12d
0x180006721  jz      loc_180006900
0x180006727  cmp     byte ptr [rcx+19h], 2
0x18000672b  jb      loc_180006900
0x180006731  mov     edx, 0E2h
0x180006736  jmp     short loc_1800066CA
0x180006738  mov     eax, [rbp+cbData]
0x18000673b  test    eax, eax
0x18000673d  jz      loc_18000680F
0x180006743  mov     ebx, eax
0x180006745  call    cs:__imp_GetProcessHeap
0x18000674c  nop     dword ptr [rax+rax+00h]
0x180006751  mov     r8d, ebx; dwBytes
0x180006754  mov     edx, 8; dwFlags
0x180006759  mov     rcx, rax; hHeap
0x18000675c  call    cs:__imp_HeapAlloc
0x180006763  nop     dword ptr [rax+rax+00h]
0x180006768  mov     r14, rax
0x18000676b  test    rax, rax
0x18000676e  jnz     short loc_1800067B2
0x180006770  call    cs:__imp_GetLastError
0x180006777  nop     dword ptr [rax+rax+00h]
0x18000677c  test    eax, eax
0x18000677e  jz      loc_180006900
0x180006784  mov     rcx, cs:WPP_GLOBAL_Control
0x18000678b  cmp     rcx, r13
0x18000678e  jz      loc_180006900
0x180006794  test    [rcx+1Ch], r12d
0x180006798  jz      loc_180006900
0x18000679e  cmp     byte ptr [rcx+19h], 2
0x1800067a2  jb      loc_180006900
0x1800067a8  mov     edx, 0E3h
0x1800067ad  jmp     loc_1800066CA
0x1800067b2  mov     rcx, [rbp+hKey]; hKey
0x1800067b6  lea     rax, [rbp+cbData]
0x1800067ba  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1800067bf  lea     rdx, ValueName; "AllocatedLuids"
0x1800067c6  xor     r9d, r9d; lpType
0x1800067c9  mov     [rsp+50h+phkResult], r14; lpData
0x1800067ce  xor     r8d, r8d; lpReserved
0x1800067d1  call    cs:__imp_RegQueryValueExA
0x1800067d8  nop     dword ptr [rax+rax+00h]
0x1800067dd  test    eax, eax
0x1800067df  jz      short loc_18000680F
0x1800067e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800067e8  cmp     rcx, r13
0x1800067eb  jz      loc_180006900
0x1800067f1  test    [rcx+1Ch], r12d
0x1800067f5  jz      loc_180006900
0x1800067fb  cmp     byte ptr [rcx+19h], 2
0x1800067ff  jb      loc_180006900
0x180006805  mov     edx, 0E4h
0x18000680a  jmp     loc_1800066CA
0x18000680f  lea     rcx, [rbp+hDevice]
0x180006813  call    WanarpDeviceOpen
0x180006818  test    eax, eax
0x18000681a  jz      short loc_18000684A
0x18000681c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006823  cmp     rcx, r13
0x180006826  jz      loc_180006900
0x18000682c  test    [rcx+1Ch], r12d
0x180006830  jz      loc_180006900
0x180006836  cmp     byte ptr [rcx+19h], 2
0x18000683a  jb      loc_180006900
0x180006840  mov     edx, 0E5h
0x180006845  jmp     loc_1800066CA
0x18000684a  mov     edi, [rbp+cbData]
0x18000684d  xor     esi, esi
0x18000684f  shr     edi, 2
0x180006852  test    edi, edi
0x180006854  jz      loc_1800068F9
0x18000685a  mov     [rsp+50h+lpOverlapped], 0; lpOverlapped
0x180006863  lea     r8, [rbp+OutBuffer]; lpInBuffer
0x180006867  mov     eax, 17h
0x18000686c  mov     r9d, 8; nInBufferSize
0x180006872  mov     word ptr [rbp+OutBuffer], ax
0x180006876  mov     edx, 90018020h; dwIoControlCode
0x18000687b  mov     ecx, [r14+rsi*4]
0x18000687f  lea     rax, [rbp+BytesReturned]
0x180006883  mov     [rsp+50h+lpBytesReturned], rax; lpBytesReturned
0x180006888  lea     rax, [rbp+OutBuffer]
0x18000688c  mov     dword ptr [rbp+OutBuffer+4], ecx
0x18000688f  mov     rcx, [rbp+hDevice]; hDevice
0x180006893  mov     dword ptr [rsp+50h+lpcbData], 8; nOutBufferSize
0x18000689b  mov     [rsp+50h+phkResult], rax; lpOutBuffer
0x1800068a0  call    cs:__imp_DeviceIoControl
0x1800068a7  nop     dword ptr [rax+rax+00h]
0x1800068ac  test    eax, eax
0x1800068ae  jnz     short loc_1800068EF
0x1800068b0  mov     rbx, cs:WPP_GLOBAL_Control
0x1800068b7  cmp     rbx, r13
0x1800068ba  jz      short loc_1800068EF
0x1800068bc  test    [rbx+1Ch], r12d
0x1800068c0  jz      short loc_1800068EF
0x1800068c2  cmp     byte ptr [rbx+19h], 2
0x1800068c6  jb      short loc_1800068EF
0x1800068c8  mov     rbx, [rbx+10h]
0x1800068cc  call    cs:__imp_GetLastError
0x1800068d3  nop     dword ptr [rax+rax+00h]
0x1800068d8  mov     edx, 0E6h
0x1800068dd  lea     r8, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids
0x1800068e4  mov     r9d, eax
0x1800068e7  mov     rcx, rbx
0x1800068ea  call    WPP_SF_d
0x1800068ef  inc     esi
0x1800068f1  cmp     esi, edi
0x1800068f3  jb      loc_18000685A
0x1800068f9  lea     rdi, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids
0x180006900  mov     rcx, [rbp+hKey]; hKey
0x180006904  lea     rdx, ValueName; "AllocatedLuids"
0x18000690b  call    cs:__imp_RegDeleteValueA
0x180006912  nop     dword ptr [rax+rax+00h]
0x180006917  mov     ebx, eax
0x180006919  test    eax, eax
0x18000691b  jz      short loc_180006949
0x18000691d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006924  cmp     rcx, r13
0x180006927  jz      short loc_180006950
0x180006929  test    [rcx+1Ch], r12d
0x18000692d  jz      short loc_180006950
0x18000692f  cmp     byte ptr [rcx+19h], 2
0x180006933  jb      short loc_180006950
0x180006935  mov     rcx, [rcx+10h]
0x180006939  mov     edx, 0E7h
0x18000693e  mov     r9d, eax
0x180006941  mov     r8, rdi
0x180006944  call    WPP_SF_d
0x180006949  mov     rcx, cs:WPP_GLOBAL_Control
0x180006950  mov     rax, [rbp+hKey]
0x180006954  test    rax, rax
0x180006957  jz      short loc_18000696F
0x180006959  mov     rcx, rax; hKey
0x18000695c  call    cs:__imp_RegCloseKey
0x180006963  nop     dword ptr [rax+rax+00h]
0x180006968  mov     rcx, cs:WPP_GLOBAL_Control
0x18000696f  test    r14, r14
0x180006972  jz      short loc_18000699B
0x180006974  call    cs:__imp_GetProcessHeap
0x18000697b  nop     dword ptr [rax+rax+00h]
0x180006980  mov     r8, r14; lpMem
0x180006983  xor     edx, edx; dwFlags
0x180006985  mov     rcx, rax; hHeap
0x180006988  call    cs:__imp_HeapFree
0x18000698f  nop     dword ptr [rax+rax+00h]
0x180006994  mov     rcx, cs:WPP_GLOBAL_Control
0x18000699b  cmp     rcx, r13
0x18000699e  jz      short loc_1800069C0
0x1800069a0  test    [rcx+1Ch], r12d
0x1800069a4  jz      short loc_1800069C0
0x1800069a6  cmp     byte ptr [rcx+19h], 6
0x1800069aa  jb      short loc_1800069C0
0x1800069ac  mov     rcx, [rcx+10h]
0x1800069b0  mov     edx, 0E8h
0x1800069b5  mov     r9d, ebx
0x1800069b8  mov     r8, rdi
0x1800069bb  call    WPP_SF_d
0x1800069c0  mov     eax, ebx
0x1800069c2  add     rsp, 50h
0x1800069c6  pop     r14
0x1800069c8  pop     r13
0x1800069ca  pop     r12
0x1800069cc  pop     rdi
0x1800069cd  pop     rsi
0x1800069ce  pop     rbx
0x1800069cf  pop     rbp
0x1800069d0  retn
```
