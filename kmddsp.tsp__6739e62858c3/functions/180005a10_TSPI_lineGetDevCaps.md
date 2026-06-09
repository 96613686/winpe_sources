# TSPI_lineGetDevCaps

- ea: `0x180005a10`
- end: `0x180005bb6`
- name: `TSPI_lineGetDevCaps`
- size: `422`
- prototype: `LONG __stdcall(DWORD dwDeviceID, DWORD dwTSPIVersion, DWORD dwExtVersion, LPLINEDEVCAPS lpLineDevCaps)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002ad0`
- `0x180003488`
- `0x180005a10`
- `0x180007df8`
- `0x180008091`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180005a7e`
- `KERNEL32!LeaveCriticalSection` at `0x180005ab9`
- `KERNEL32!LeaveCriticalSection` at `0x180005af4`
- `KERNEL32!LeaveCriticalSection` at `0x180005b7b`
- `KERNEL32!LeaveCriticalSection` at `0x180005b9a`
- `KERNEL32!LeaveCriticalSection` at `0x180005a7e`
- `KERNEL32!LeaveCriticalSection` at `0x180005ab9`
- `KERNEL32!LeaveCriticalSection` at `0x180005af4`
- `KERNEL32!LeaveCriticalSection` at `0x180005b7b`
- `KERNEL32!LeaveCriticalSection` at `0x180005b9a`
- `KERNEL32!EnterCriticalSection` at `0x180005a5f`
- `KERNEL32!EnterCriticalSection` at `0x180005a5f`

## string_xrefs

- `0x180005aa5`: `GetDevCaps: tspi version(%x) not matchthe committed one(%x)`
- `0x180005ae0`: `GetDevCaps: ext version(%x) not match the committed one(%x)`

## pseudocode

```c
LONG __stdcall TSPI_lineGetDevCaps(
        DWORD dwDeviceID,
        DWORD dwTSPIVersion,
        DWORD dwExtVersion,
        LPLINEDEVCAPS lpLineDevCaps)
{
  __int64 LineDevNode; // rax
  __int64 v9; // rbx
  int v11; // r9d
  int v12; // r9d
  __int64 LineDevCaps; // rax
  const void *v14; // rdx
  __int64 v15; // rax
  DWORD *p_dwNeededSize; // rcx
  DWORD dwTotalSize; // eax
  DWORD dwUsedSize; // eax
  size_t v19; // r8

  TspLog(
    8,
    "lineGetDevCaps(%d): deviceID(%x), TSPIV(%x), ExtV(%x)",
    ++dword_18000E258,
    dwDeviceID,
    dwTSPIVersion,
    dwExtVersion);
  EnterCriticalSection(&stru_18000E3B0);
  LineDevNode = GetLineDevNode(dwDeviceID);
  v9 = LineDevNode;
  if ( !LineDevNode )
    goto LABEL_2;
  v11 = *(_DWORD *)(LineDevNode + 24);
  if ( v11 && dwTSPIVersion != v11 )
  {
    TspLog(1, "GetDevCaps: tspi version(%x) not matchthe committed one(%x)", dwTSPIVersion, v11);
    LeaveCriticalSection(&stru_18000E3B0);
    return -2147483636;
  }
  v12 = *(_DWORD *)(LineDevNode + 32);
  if ( v12 && dwExtVersion != v12 )
  {
    TspLog(1, "GetDevCaps: ext version(%x) not match the committed one(%x)", dwExtVersion, v12);
    LeaveCriticalSection(&stru_18000E3B0);
    return -2147483635;
  }
  LineDevCaps = *(_QWORD *)(LineDevNode + 8);
  if ( !LineDevCaps )
  {
    LineDevCaps = GetLineDevCaps(dwDeviceID, dwExtVersion);
    *(_QWORD *)(v9 + 8) = LineDevCaps;
    if ( !LineDevCaps )
    {
LABEL_2:
      LeaveCriticalSection(&stru_18000E3B0);
      return -2147483580;
    }
  }
  v14 = (const void *)(LineDevCaps + 4);
  v15 = *(unsigned int *)(LineDevCaps + 4);
  p_dwNeededSize = &lpLineDevCaps->dwNeededSize;
  if ( (unsigned int)v15 <= lpLineDevCaps->dwTotalSize )
  {
    v19 = v15 - 4;
  }
  else
  {
    *p_dwNeededSize = v15;
    dwTotalSize = 268;
    if ( lpLineDevCaps->dwTotalSize < 0x10C )
      dwTotalSize = lpLineDevCaps->dwTotalSize;
    lpLineDevCaps->dwUsedSize = dwTotalSize;
    *(_OWORD *)&lpLineDevCaps->dwProviderInfoSize = 0;
    *(_OWORD *)&lpLineDevCaps->dwSwitchInfoOffset = 0;
    dwUsedSize = lpLineDevCaps->dwUsedSize;
    lpLineDevCaps->dwPermanentLineID = *(_DWORD *)(*(_QWORD *)(v9 + 8) + 28LL);
    if ( dwUsedSize < 0x28 )
    {
      LeaveCriticalSection(&stru_18000E3B0);
      return -2147483598;
    }
    p_dwNeededSize = &lpLineDevCaps->dwStringFormat;
    v19 = dwUsedSize - 40;
    v14 = (const void *)(*(_QWORD *)(v9 + 8) + 40LL);
  }
  memcpy_0(p_dwNeededSize, v14, v19);
  LeaveCriticalSection(&stru_18000E3B0);
  return 0;
}

```

## disassembly

```asm
0x180005a10  push    rbx
0x180005a12  push    rbp
0x180005a13  push    rsi
0x180005a14  push    rdi
0x180005a15  push    r14
0x180005a17  push    r15
0x180005a19  sub     rsp, 38h
0x180005a1d  mov     esi, r8d
0x180005a20  mov     rdi, r9
0x180005a23  mov     r8d, cs:dword_18000E258
0x180005a2a  mov     ebp, edx
0x180005a2c  inc     r8d
0x180005a2f  mov     [rsp+68h+var_40], esi
0x180005a33  mov     [rsp+68h+var_48], edx
0x180005a37  mov     r14d, ecx
0x180005a3a  mov     r9d, ecx
0x180005a3d  mov     cs:dword_18000E258, r8d
0x180005a44  lea     rdx, aLinegetdevcaps; "lineGetDevCaps(%d): deviceID(%x), TSPIV"...
0x180005a4b  mov     ecx, 8
0x180005a50  call    TspLog
0x180005a55  lea     r15, stru_18000E3B0
0x180005a5c  mov     rcx, r15; lpCriticalSection
0x180005a5f  call    cs:__imp_EnterCriticalSection
0x180005a66  nop     dword ptr [rax+rax+00h]
0x180005a6b  mov     ecx, r14d
0x180005a6e  call    GetLineDevNode
0x180005a73  mov     rbx, rax
0x180005a76  test    rax, rax
0x180005a79  jnz     short loc_180005A94
0x180005a7b  mov     rcx, r15; lpCriticalSection
0x180005a7e  call    cs:__imp_LeaveCriticalSection
0x180005a85  nop     dword ptr [rax+rax+00h]
0x180005a8a  mov     eax, 80000044h
0x180005a8f  jmp     loc_180005BA8
0x180005a94  mov     r9d, [rax+18h]
0x180005a98  test    r9d, r9d
0x180005a9b  jz      short loc_180005ACF
0x180005a9d  cmp     ebp, r9d
0x180005aa0  jz      short loc_180005ACF
0x180005aa2  mov     r8d, ebp
0x180005aa5  lea     rdx, aGetdevcapsTspi; "GetDevCaps: tspi version(%x) not matcht"...
0x180005aac  mov     ecx, 1
0x180005ab1  call    TspLog
0x180005ab6  mov     rcx, r15; lpCriticalSection
0x180005ab9  call    cs:__imp_LeaveCriticalSection
0x180005ac0  nop     dword ptr [rax+rax+00h]
0x180005ac5  mov     eax, 8000000Ch
0x180005aca  jmp     loc_180005BA8
0x180005acf  mov     r9d, [rax+20h]
0x180005ad3  test    r9d, r9d
0x180005ad6  jz      short loc_180005B0A
0x180005ad8  cmp     esi, r9d
0x180005adb  jz      short loc_180005B0A
0x180005add  mov     r8d, esi
0x180005ae0  lea     rdx, aGetdevcapsExtV; "GetDevCaps: ext version(%x) not match t"...
0x180005ae7  mov     ecx, 1
0x180005aec  call    TspLog
0x180005af1  mov     rcx, r15; lpCriticalSection
0x180005af4  call    cs:__imp_LeaveCriticalSection
0x180005afb  nop     dword ptr [rax+rax+00h]
0x180005b00  mov     eax, 8000000Dh
0x180005b05  jmp     loc_180005BA8
0x180005b0a  mov     rax, [rax+8]
0x180005b0e  test    rax, rax
0x180005b11  jnz     short loc_180005B2A
0x180005b13  mov     edx, esi
0x180005b15  mov     ecx, r14d
0x180005b18  call    GetLineDevCaps
0x180005b1d  mov     [rbx+8], rax
0x180005b21  test    rax, rax
0x180005b24  jz      loc_180005A7B
0x180005b2a  lea     rdx, [rax+4]; Src
0x180005b2e  mov     eax, [rdx]
0x180005b30  lea     rcx, [rdi+4]; void *
0x180005b34  cmp     eax, [rdi]
0x180005b36  jbe     short loc_180005B8E
0x180005b38  mov     [rcx], eax
0x180005b3a  xorps   xmm0, xmm0
0x180005b3d  mov     eax, 10Ch
0x180005b42  cmp     [rdi], eax
0x180005b44  cmovb   eax, [rdi]
0x180005b47  mov     [rdi+8], eax
0x180005b4a  movups  xmmword ptr [rdi+0Ch], xmm0
0x180005b4e  movups  xmmword ptr [rdi+18h], xmm0
0x180005b52  mov     rax, [rbx+8]
0x180005b56  mov     ecx, [rax+1Ch]
0x180005b59  mov     eax, [rdi+8]
0x180005b5c  mov     [rdi+1Ch], ecx
0x180005b5f  cmp     eax, 28h ; '('
0x180005b62  jb      short loc_180005B78
0x180005b64  mov     rdx, [rbx+8]
0x180005b68  lea     rcx, [rdi+28h]
0x180005b6c  add     eax, 0FFFFFFD8h
0x180005b6f  mov     r8d, eax
0x180005b72  add     rdx, 28h ; '('
0x180005b76  jmp     short loc_180005B92
0x180005b78  mov     rcx, r15; lpCriticalSection
0x180005b7b  call    cs:__imp_LeaveCriticalSection
0x180005b82  nop     dword ptr [rax+rax+00h]
0x180005b87  mov     eax, 80000032h
0x180005b8c  jmp     short loc_180005BA8
0x180005b8e  lea     r8, [rax-4]; Size
0x180005b92  call    memcpy_0
0x180005b97  mov     rcx, r15; lpCriticalSection
0x180005b9a  call    cs:__imp_LeaveCriticalSection
0x180005ba1  nop     dword ptr [rax+rax+00h]
0x180005ba6  xor     eax, eax
0x180005ba8  add     rsp, 38h
0x180005bac  pop     r15
0x180005bae  pop     r14
0x180005bb0  pop     rdi
0x180005bb1  pop     rsi
0x180005bb2  pop     rbp
0x180005bb3  pop     rbx
0x180005bb4  retn
```
