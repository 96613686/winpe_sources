# IsInUseByRRAS(ushort *)

- ea: `0x1800463bc`
- end: `0x18004653c`
- name: `?IsInUseByRRAS@@YAHPEAG@Z`
- size: `384`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800462b4`

## callees

- `0x1800463bc`

## import_xrefs

- `MPRAPI!MprConfigServerConnect` at `0x1800463e2`
- `MPRAPI!MprConfigServerConnect` at `0x1800463e2`
- `MPRAPI!MprConfigInterfaceEnum` at `0x180046422`
- `MPRAPI!MprConfigInterfaceEnum` at `0x180046422`
- `MPRAPI!MprConfigInterfaceTransportGetHandle` at `0x180046495`
- `MPRAPI!MprConfigInterfaceTransportGetHandle` at `0x180046495`
- `MPRAPI!MprConfigInterfaceTransportGetInfo` at `0x1800464c9`
- `MPRAPI!MprConfigInterfaceTransportGetInfo` at `0x1800464c9`
- `MPRAPI!MprInfoBlockFind` at `0x1800464fa`
- `MPRAPI!MprInfoBlockFind` at `0x1800464fa`
- `MPRAPI!MprConfigBufferFree` at `0x18004650c`
- `MPRAPI!MprConfigBufferFree` at `0x180046516`
- `MPRAPI!MprConfigBufferFree` at `0x18004650c`
- `MPRAPI!MprConfigBufferFree` at `0x180046516`
- `MPRAPI!MprConfigServerDisconnect` at `0x180046520`
- `MPRAPI!MprConfigServerDisconnect` at `0x180046520`

## pseudocode

```c
__int64 __fastcall IsInUseByRRAS(BYTE *a1)
{
  unsigned int v2; // ebx
  LPBYTE v3; // rcx
  DWORD i; // edx
  __int64 v5; // rdi
  BYTE *v6; // rax
  int v7; // r9d
  int v8; // r8d
  DWORD dwItemCount; // [rsp+40h] [rbp-30h] BYREF
  LPBYTE lpBuffer; // [rsp+48h] [rbp-28h] BYREF
  HANDLE phMprConfig; // [rsp+50h] [rbp-20h] BYREF
  LPBYTE ppInterfaceInfo; // [rsp+58h] [rbp-18h] BYREF
  HANDLE phRouterIfTransport; // [rsp+60h] [rbp-10h] BYREF
  LPBYTE lpItemData; // [rsp+68h] [rbp-8h] BYREF
  DWORD dwInterfaceInfoSize; // [rsp+A8h] [rbp+38h] BYREF
  DWORD dwEntriesRead; // [rsp+B0h] [rbp+40h] BYREF
  DWORD dwTotalEntries; // [rsp+B8h] [rbp+48h] BYREF

  v2 = 0;
  phMprConfig = 0;
  MprConfigServerConnect(0, &phMprConfig);
  if ( phMprConfig )
  {
    dwEntriesRead = 0;
    dwTotalEntries = 0;
    lpBuffer = 0;
    MprConfigInterfaceEnum(phMprConfig, 0, &lpBuffer, 0xFFFFFFFF, &dwEntriesRead, &dwTotalEntries, 0);
    v3 = lpBuffer;
    if ( lpBuffer )
    {
      for ( i = 0; i < dwEntriesRead; ++i )
      {
        v5 = 552LL * i;
        v6 = a1;
        do
        {
          v7 = *(unsigned __int16 *)&v6[&lpBuffer[v5] - a1];
          v8 = *(unsigned __int16 *)v6 - v7;
          if ( v8 )
            break;
          v6 += 2;
        }
        while ( v7 );
        if ( !v8 )
        {
          phRouterIfTransport = 0;
          MprConfigInterfaceTransportGetHandle(phMprConfig, *(HANDLE *)&lpBuffer[v5 + 520], 0x21u, &phRouterIfTransport);
          if ( phRouterIfTransport )
          {
            dwInterfaceInfoSize = 0;
            ppInterfaceInfo = 0;
            MprConfigInterfaceTransportGetInfo(
              phMprConfig,
              *(HANDLE *)&lpBuffer[v5 + 520],
              phRouterIfTransport,
              &ppInterfaceInfo,
              &dwInterfaceInfoSize);
            if ( ppInterfaceInfo )
            {
              dwItemCount = 0;
              dwInterfaceInfoSize = 0;
              lpItemData = 0;
              MprInfoBlockFind(ppInterfaceInfo, 0x81372715, &dwInterfaceInfoSize, &dwItemCount, &lpItemData);
              if ( lpItemData )
                v2 = 1;
              MprConfigBufferFree(ppInterfaceInfo);
            }
          }
          v3 = lpBuffer;
          break;
        }
      }
      MprConfigBufferFree(v3);
    }
    MprConfigServerDisconnect(phMprConfig);
  }
  return v2;
}

```

## disassembly

```asm
0x1800463bc  mov     [rsp-28h+arg_0], rbx
0x1800463c1  push    rbp
0x1800463c2  push    rsi
0x1800463c3  push    rdi
0x1800463c4  push    r14
0x1800463c6  push    r15
0x1800463c8  mov     rbp, rsp
0x1800463cb  sub     rsp, 70h
0x1800463cf  mov     rsi, rcx
0x1800463d2  lea     rdx, [rbp+phMprConfig]; phMprConfig
0x1800463d6  xor     r14d, r14d
0x1800463d9  xor     ecx, ecx; lpwsServerName
0x1800463db  mov     ebx, r14d
0x1800463de  mov     [rbp+phMprConfig], r14
0x1800463e2  call    cs:__imp_MprConfigServerConnect
0x1800463e8  mov     rcx, [rbp+phMprConfig]; hMprConfig
0x1800463ec  test    rcx, rcx
0x1800463ef  jz      loc_180046526
0x1800463f5  lea     rax, [rbp+dwTotalEntries]
0x1800463f9  mov     [rsp+70h+lpdwResumeHandle], r14; lpdwResumeHandle
0x1800463fe  mov     [rsp+70h+lpdwTotalEntries], rax; lpdwTotalEntries
0x180046403  lea     r8, [rbp+lpBuffer]; lplpBuffer
0x180046407  lea     rax, [rbp+dwEntriesRead]
0x18004640b  mov     [rbp+dwEntriesRead], r14d
0x18004640f  or      r9d, 0FFFFFFFFh; dwPrefMaxLen
0x180046413  mov     [rsp+70h+lpdwEntriesRead], rax; lpdwEntriesRead
0x180046418  xor     edx, edx; dwLevel
0x18004641a  mov     [rbp+dwTotalEntries], r14d
0x18004641e  mov     [rbp+lpBuffer], r14
0x180046422  call    cs:__imp_MprConfigInterfaceEnum
0x180046428  mov     rcx, [rbp+lpBuffer]
0x18004642c  test    rcx, rcx
0x18004642f  jz      loc_18004651C
0x180046435  mov     edx, r14d
0x180046438  lea     r15d, [r14+1]
0x18004643c  cmp     edx, [rbp+dwEntriesRead]
0x18004643f  jnb     loc_180046516
0x180046445  mov     eax, edx
0x180046447  imul    rdi, rax, 228h
0x18004644e  mov     rax, rsi
0x180046451  lea     r11, [rdi+rcx]
0x180046455  mov     r10, r11
0x180046458  sub     r10, rsi
0x18004645b  movzx   r8d, word ptr [rax]
0x18004645f  movzx   r9d, word ptr [rax+r10]
0x180046464  sub     r8d, r9d
0x180046467  jnz     short loc_180046472
0x180046469  add     rax, 2
0x18004646d  test    r9d, r9d
0x180046470  jnz     short loc_18004645B
0x180046472  test    r8d, r8d
0x180046475  jz      short loc_18004647C
0x180046477  add     edx, r15d
0x18004647a  jmp     short loc_18004643C
0x18004647c  mov     rcx, [rbp+phMprConfig]; hMprConfig
0x180046480  lea     r9, [rbp+phRouterIfTransport]; phRouterIfTransport
0x180046484  mov     [rbp+phRouterIfTransport], r14
0x180046488  mov     r8d, 21h ; '!'; dwTransportId
0x18004648e  mov     rdx, [r11+208h]; hRouterInterface
0x180046495  call    cs:__imp_MprConfigInterfaceTransportGetHandle
0x18004649b  mov     r8, [rbp+phRouterIfTransport]; hRouterIfTransport
0x18004649f  test    r8, r8
0x1800464a2  jz      short loc_180046512
0x1800464a4  mov     rdx, [rbp+lpBuffer]
0x1800464a8  lea     rax, [rbp+dwInterfaceInfoSize]
0x1800464ac  mov     rcx, [rbp+phMprConfig]; hMprConfig
0x1800464b0  lea     r9, [rbp+ppInterfaceInfo]; ppInterfaceInfo
0x1800464b4  mov     [rbp+dwInterfaceInfoSize], r14d
0x1800464b8  mov     [rbp+ppInterfaceInfo], r14
0x1800464bc  mov     rdx, [rdi+rdx+208h]; hRouterInterface
0x1800464c4  mov     [rsp+70h+lpdwEntriesRead], rax; lpdwInterfaceInfoSize
0x1800464c9  call    cs:__imp_MprConfigInterfaceTransportGetInfo
0x1800464cf  mov     rcx, [rbp+ppInterfaceInfo]; lpHeader
0x1800464d3  test    rcx, rcx
0x1800464d6  jz      short loc_180046512
0x1800464d8  lea     rax, [rbp+lpItemData]
0x1800464dc  mov     [rbp+dwItemCount], r14d
0x1800464e0  lea     r9, [rbp+dwItemCount]; lpdwItemCount
0x1800464e4  mov     [rsp+70h+lpdwEntriesRead], rax; lplpItemData
0x1800464e9  lea     r8, [rbp+dwInterfaceInfoSize]; lpdwItemSize
0x1800464ed  mov     [rbp+dwInterfaceInfoSize], r14d
0x1800464f1  mov     edx, 81372715h; dwInfoType
0x1800464f6  mov     [rbp+lpItemData], r14
0x1800464fa  call    cs:__imp_MprInfoBlockFind
0x180046500  cmp     [rbp+lpItemData], r14
0x180046504  mov     rcx, [rbp+ppInterfaceInfo]; pBuffer
0x180046508  cmovnz  ebx, r15d
0x18004650c  call    cs:__imp_MprConfigBufferFree
0x180046512  mov     rcx, [rbp+lpBuffer]; pBuffer
0x180046516  call    cs:__imp_MprConfigBufferFree
0x18004651c  mov     rcx, [rbp+phMprConfig]; hMprConfig
0x180046520  call    cs:__imp_MprConfigServerDisconnect
0x180046526  mov     eax, ebx
0x180046528  mov     rbx, [rsp+70h+arg_0]
0x180046530  add     rsp, 70h
0x180046534  pop     r15
0x180046536  pop     r14
0x180046538  pop     rdi
0x180046539  pop     rsi
0x18004653a  pop     rbp
0x18004653b  retn
```
