# OfflineFilesStart

- ea: `0x180007950`
- end: `0x180007bc4`
- name: `OfflineFilesStart`
- size: `628`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callees

- `0x180004f10`
- `0x1800052f0`
- `0x1800057f0`
- `0x180007950`
- `0x180007bcc`
- `0x180007bf4`
- `0x180009490`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007b01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007b01`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180007af3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180007af3`
- `ntdll!RtlPublishWnfStateData` at `0x180007a24`
- `ntdll!RtlPublishWnfStateData` at `0x180007a24`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x180007ab0`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x180007ab0`

## string_xrefs

- `0x180007a78`: `CscService`

## pseudocode

```c
__int64 OfflineFilesStart()
{
  unsigned int v0; // ebx
  unsigned int v1; // eax
  int v2; // edi
  _QWORD *v3; // rcx
  unsigned int i; // edi
  int v5; // eax
  DWORD LastError; // eax
  DWORD v7; // edi
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-50h] BYREF
  DWORD v10; // [rsp+34h] [rbp-4Ch] BYREF
  int v11; // [rsp+38h] [rbp-48h] BYREF
  SC_HANDLE hService; // [rsp+40h] [rbp-40h] BYREF
  BYTE Buffer[16]; // [rsp+48h] [rbp-38h] BYREF
  __int128 v14; // [rsp+58h] [rbp-28h]
  int v15; // [rsp+68h] [rbp-18h]

  v11 = 0;
  LODWORD(hService) = 0;
  v0 = 1058;
  v10 = 0;
  pcbBytesNeeded = 0;
  if ( (unsigned int)QueryDriverAndServiceStartType(&v10, &pcbBytesNeeded)
    || (unsigned int)QueryDriverAndServiceState(&v11, &hService)
    || v10 != 1
    || v11 != 4 )
  {
    goto LABEL_33;
  }
  if ( (_DWORD)hService == 4 )
  {
    v0 = 0;
    goto LABEL_33;
  }
  if ( pcbBytesNeeded - 2 > 1 )
    goto LABEL_33;
  pcbBytesNeeded = 0;
  v15 = 0;
  *(_OWORD *)Buffer = 0;
  v14 = 0;
  v1 = RtlPublishWnfStateData(WNF_CSC_SERVICE_START, 0, 0, 0, 0);
  v2 = v1;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 22), 39, WPP_00d7c4231f3f33ca0a28c368a7ccec1f_Traceguids, v1);
    v3 = WPP_GLOBAL_Control;
  }
  if ( v2 < 0 )
    goto LABEL_34;
  hService = 0;
  if ( OpenDriverOrService(L"CscService", 0x80000000, &hService) )
  {
LABEL_33:
    v3 = WPP_GLOBAL_Control;
LABEL_34:
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 188) & 2) != 0 )
      WPP_SF_d(v3[22], 43, WPP_00d7c4231f3f33ca0a28c368a7ccec1f_Traceguids, v0);
    return v0;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= 0x1E )
    {
      v5 = *(_DWORD *)&Buffer[4];
      goto LABEL_28;
    }
    if ( !QueryServiceStatusEx(hService, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
      break;
    v5 = *(_DWORD *)&Buffer[4];
    if ( *(_DWORD *)&Buffer[4] == 4 )
    {
      v0 = 0;
LABEL_28:
      v3 = WPP_GLOBAL_Control;
      goto LABEL_29;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 22),
        41,
        WPP_00d7c4231f3f33ca0a28c368a7ccec1f_Traceguids,
        *(unsigned int *)&Buffer[4]);
    Sleep(0x3E8u);
  }
  LastError = GetLastError();
  v7 = LastError;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 22), 40, WPP_00d7c4231f3f33ca0a28c368a7ccec1f_Traceguids, LastError);
    v3 = WPP_GLOBAL_Control;
  }
  if ( v7 )
    goto LABEL_34;
  v5 = *(_DWORD *)&Buffer[4];
LABEL_29:
  if ( v5 == 4 )
    goto LABEL_34;
  v0 = 1062;
  if ( v3 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v3 + 188) & 1) == 0 )
      goto LABEL_34;
    WPP_SF_(v3[22], 42, WPP_00d7c4231f3f33ca0a28c368a7ccec1f_Traceguids);
    goto LABEL_33;
  }
  return v0;
}

```

## disassembly

```asm
0x180007950  push    rbp
0x180007952  push    rbx
0x180007953  push    rdi
0x180007954  push    r12
0x180007956  push    r15
0x180007958  mov     rbp, rsp
0x18000795b  sub     rsp, 80h
0x180007962  mov     rax, cs:__security_cookie
0x180007969  xor     rax, rsp
0x18000796c  mov     [rbp+var_10], rax
0x180007970  lea     rdx, [rbp+var_50]
0x180007974  mov     [rbp+var_48], 0
0x18000797b  lea     rcx, [rbp+var_4C]
0x18000797f  mov     dword ptr [rbp+hService], 0
0x180007986  mov     ebx, 422h
0x18000798b  mov     [rbp+var_4C], 0
0x180007992  mov     [rbp+var_50], 0
0x180007999  call    _QueryDriverAndServiceStartType
0x18000799e  lea     r15, WPP_GLOBAL_Control
0x1800079a5  lea     r12, WPP_00d7c4231f3f33ca0a28c368a7ccec1f_Traceguids
0x1800079ac  test    eax, eax
0x1800079ae  jnz     loc_180007B7B
0x1800079b4  lea     rdx, [rbp+hService]
0x1800079b8  lea     rcx, [rbp+var_48]
0x1800079bc  call    _QueryDriverAndServiceState
0x1800079c1  test    eax, eax
0x1800079c3  jnz     loc_180007B7B
0x1800079c9  cmp     [rbp+var_4C], 1
0x1800079cd  jnz     loc_180007B7B
0x1800079d3  cmp     [rbp+var_48], 4
0x1800079d7  jnz     loc_180007B7B
0x1800079dd  cmp     dword ptr [rbp+hService], 4
0x1800079e1  jnz     short loc_1800079EA
0x1800079e3  xor     ebx, ebx
0x1800079e5  jmp     loc_180007B7B
0x1800079ea  mov     eax, [rbp+var_50]
0x1800079ed  add     eax, 0FFFFFFFEh
0x1800079f0  cmp     eax, 1
0x1800079f3  ja      loc_180007B7B
0x1800079f9  mov     rcx, cs:WNF_CSC_SERVICE_START
0x180007a00  xorps   xmm0, xmm0
0x180007a03  xor     eax, eax
0x180007a05  mov     [rbp+var_50], 0
0x180007a0c  xor     r9d, r9d
0x180007a0f  mov     [rbp+var_18], eax
0x180007a12  xor     r8d, r8d
0x180007a15  mov     [rsp+80h+pcbBytesNeeded], rax
0x180007a1a  xor     edx, edx
0x180007a1c  movups  xmmword ptr [rbp+Buffer], xmm0
0x180007a20  movups  [rbp+var_28], xmm0
0x180007a24  call    cs:__imp_RtlPublishWnfStateData
0x180007a2a  mov     edi, eax
0x180007a2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a33  cmp     rcx, r15
0x180007a36  jz      short loc_180007A5F
0x180007a38  test    byte ptr [rcx+0BCh], 1
0x180007a3f  jz      short loc_180007A5F
0x180007a41  mov     rcx, [rcx+0B0h]
0x180007a48  mov     edx, 27h ; '''
0x180007a4d  mov     r9d, eax
0x180007a50  mov     r8, r12
0x180007a53  call    WPP_SF_d
0x180007a58  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a5f  test    edi, edi
0x180007a61  js      loc_180007B82
0x180007a67  lea     r8, [rbp+hService]
0x180007a6b  mov     [rbp+hService], 0
0x180007a73  mov     edx, 80000000h; dwDesiredAccess
0x180007a78  lea     rcx, g_szCscServiceName; "CscService"
0x180007a7f  call    _OpenDriverOrService
0x180007a84  test    eax, eax
0x180007a86  jnz     loc_180007B7B
0x180007a8c  xor     edi, edi
0x180007a8e  cmp     edi, 1Eh
0x180007a91  jnb     loc_180007B45
0x180007a97  mov     rcx, [rbp+hService]; hService
0x180007a9b  lea     rax, [rbp+var_50]
0x180007a9f  mov     r9d, 24h ; '$'; cbBufSize
0x180007aa5  mov     [rsp+80h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180007aaa  lea     r8, [rbp+Buffer]; lpBuffer
0x180007aae  xor     edx, edx; InfoLevel
0x180007ab0  call    cs:__imp_QueryServiceStatusEx
0x180007ab6  test    eax, eax
0x180007ab8  jz      short loc_180007B01
0x180007aba  mov     eax, dword ptr [rbp+Buffer+4]
0x180007abd  cmp     eax, 4
0x180007ac0  jz      short loc_180007AFD
0x180007ac2  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ac9  cmp     rcx, r15
0x180007acc  jz      short loc_180007AEE
0x180007ace  test    byte ptr [rcx+0BCh], 1
0x180007ad5  jz      short loc_180007AEE
0x180007ad7  mov     rcx, [rcx+0B0h]
0x180007ade  mov     edx, 29h ; ')'
0x180007ae3  mov     r9d, eax
0x180007ae6  mov     r8, r12
0x180007ae9  call    WPP_SF_d
0x180007aee  mov     ecx, 3E8h; dwMilliseconds
0x180007af3  call    cs:__imp_Sleep
0x180007af9  inc     edi
0x180007afb  jmp     short loc_180007A8E
0x180007afd  xor     ebx, ebx
0x180007aff  jmp     short loc_180007B48
0x180007b01  call    cs:__imp_GetLastError
0x180007b07  mov     edi, eax
0x180007b09  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b10  cmp     rcx, r15
0x180007b13  jz      short loc_180007B3C
0x180007b15  test    byte ptr [rcx+0BCh], 1
0x180007b1c  jz      short loc_180007B3C
0x180007b1e  mov     rcx, [rcx+0B0h]
0x180007b25  mov     edx, 28h ; '('
0x180007b2a  mov     r9d, eax
0x180007b2d  mov     r8, r12
0x180007b30  call    WPP_SF_d
0x180007b35  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b3c  test    edi, edi
0x180007b3e  jnz     short loc_180007B82
0x180007b40  mov     eax, dword ptr [rbp+Buffer+4]
0x180007b43  jmp     short loc_180007B4F
0x180007b45  mov     eax, dword ptr [rbp+Buffer+4]
0x180007b48  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b4f  cmp     eax, 4
0x180007b52  jz      short loc_180007B82
0x180007b54  mov     ebx, 426h
0x180007b59  cmp     rcx, r15
0x180007b5c  jz      short loc_180007BA7
0x180007b5e  test    byte ptr [rcx+0BCh], 1
0x180007b65  jz      short loc_180007B82
0x180007b67  mov     rcx, [rcx+0B0h]
0x180007b6e  mov     edx, 2Ah ; '*'
0x180007b73  mov     r8, r12
0x180007b76  call    WPP_SF_
0x180007b7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b82  cmp     rcx, r15
0x180007b85  jz      short loc_180007BA7
0x180007b87  test    byte ptr [rcx+0BCh], 2
0x180007b8e  jz      short loc_180007BA7
0x180007b90  mov     rcx, [rcx+0B0h]
0x180007b97  mov     edx, 2Bh ; '+'
0x180007b9c  mov     r9d, ebx
0x180007b9f  mov     r8, r12
0x180007ba2  call    WPP_SF_d
0x180007ba7  mov     eax, ebx
0x180007ba9  mov     rcx, [rbp+var_10]
0x180007bad  xor     rcx, rsp; StackCookie
0x180007bb0  call    __security_check_cookie
0x180007bb5  add     rsp, 80h
0x180007bbc  pop     r15
0x180007bbe  pop     r12
0x180007bc0  pop     rdi
0x180007bc1  pop     rbx
0x180007bc2  pop     rbp
0x180007bc3  retn
```
