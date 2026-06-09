# GetResString2FromModule

- ea: `0x14000d694`
- end: `0x14000d8f7`
- name: `GetResString2FromModule`
- size: `611`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `32`
- callee_count: `7`
- tags: ``

## callers

- `0x140001e90`
- `0x14000263c`
- `0x140002a78`
- `0x140002ce4`
- `0x140002d40`
- `0x1400031f4`
- `0x1400038f8`
- `0x140003c24`
- `0x140003e34`
- `0x14000426c`
- `0x14000456c`
- `0x14000496c`
- `0x140004e84`
- `0x140005ef0`
- `0x1400061e4`
- `0x14000672c`
- `0x140006e6c`
- `0x1400073d4`
- `0x1400075ac`
- `0x14000799c`
- `0x140007cbc`
- `0x140008cbc`
- `0x140009374`
- `0x14000957c`
- `0x140009a50`
- `0x140009b2c`
- `0x140009c68`
- `0x14000a0e0`
- `0x14000a358`
- `0x14000a6d8`
- `0x14000aa4c`
- `0x14000d65c`

## callees

- `0x14000d3e8`
- `0x14000d694`
- `0x14000dab0`
- `0x14000f350`
- `0x14000f4d8`
- `0x14000f638`
- `0x14000f8e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d6b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d79a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d8c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d6b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d79a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d8c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d8da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000d8da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000d85f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000d85f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x14000d788`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x14000d788`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000d7d9`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000d7d9`

## pseudocode

```c
__int64 *__fastcall GetResString2FromModule(__int64 a1, UINT a2, unsigned int a3)
{
  DWORD v5; // ecx
  __int64 v6; // rcx
  unsigned int v7; // edx
  unsigned int Count2; // r10d
  __int64 v9; // rcx
  __int64 v10; // rcx
  unsigned int v11; // ebx
  WCHAR *InternalTemporaryBuffer; // rax
  const WCHAR *v13; // rdi
  unsigned int StringW; // ecx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 Item; // rax
  WCHAR *Buffer; // [rsp+70h] [rbp+8h] BYREF

  Buffer = 0;
  if ( a2 )
  {
    if ( (unsigned int)InitGlobals() )
    {
      Count2 = DynArrayGetCount2(v6, 1);
      if ( Count2 > a3
        || qword_140015218
        && *(_DWORD *)qword_140015218 == 9
        && *(_DWORD *)(qword_140015218 + 4) > v7
        && (v9 = *(_QWORD *)(*(_QWORD *)(qword_140015218 + 8) + 24LL)) != 0
        && (*(_DWORD *)(v9 + 4) == 0x10000 || *(_DWORD *)(v9 + 4) == 0x80000)
        && (v10 = *(_QWORD *)(v9 + 16)) != 0
        && (unsigned int)DynArrayAddColumns(v10, a3 - Count2 + 1) != -1 )
      {
        v11 = 128;
        while ( 1 )
        {
          v11 *= 2;
          InternalTemporaryBuffer = (WCHAR *)GetInternalTemporaryBuffer(4u, 0, v11, 1);
          v13 = InternalTemporaryBuffer;
          if ( !InternalTemporaryBuffer )
            break;
          StringW = LoadStringW(0, a2, InternalTemporaryBuffer, v11);
          if ( !StringW )
          {
            if ( GetLastError() != 1814 )
              return &cwszNullString;
            StringW = FormatMessageW(0xB00u, 0, a2, 0, (LPWSTR)&Buffer, 0, 0);
            if ( !StringW )
              return &cwszNullString;
            v13 = Buffer;
          }
          if ( StringW < v11 - 1 )
          {
            if ( !qword_140015218 )
              break;
            if ( *(_DWORD *)qword_140015218 != 9 )
              break;
            if ( *(_DWORD *)(qword_140015218 + 4) <= 1u )
              break;
            v15 = *(_QWORD *)(*(_QWORD *)(qword_140015218 + 8) + 24LL);
            if ( !v15
              || *(_DWORD *)(v15 + 4) != 0x80000
              || !(unsigned int)DynArraySetString(*(_QWORD *)(v15 + 16), a3, v13, 0) )
            {
              break;
            }
            if ( Buffer )
            {
              LocalFree(Buffer);
              Buffer = 0;
            }
            if ( qword_140015218
              && *(_DWORD *)qword_140015218 == 9
              && *(_DWORD *)(qword_140015218 + 4) > 1u
              && (v16 = *(_QWORD *)(*(_QWORD *)(qword_140015218 + 8) + 24LL)) != 0
              && *(_DWORD *)(v16 + 4) == 0x80000
              && (Item = _DynArrayGetItem(*(_QWORD *)(v16 + 16), a3, 0)) != 0
              && *(_DWORD *)(Item + 4) == 0x20000 )
            {
              return *(__int64 **)(Item + 16);
            }
            else
            {
              return 0;
            }
          }
        }
      }
      if ( !GetLastError() )
      {
        v5 = 8;
        goto LABEL_40;
      }
    }
  }
  else if ( !GetLastError() )
  {
    v5 = 87;
LABEL_40:
    SetLastError(v5);
  }
  return &cwszNullString;
}

```

## disassembly

```asm
0x14000d694  mov     [rsp+Buffer], rcx
0x14000d699  push    rbx
0x14000d69a  push    rbp
0x14000d69b  push    rsi
0x14000d69c  push    rdi
0x14000d69d  sub     rsp, 48h
0x14000d6a1  mov     [rsp+68h+Buffer], 0
0x14000d6aa  mov     ebp, r8d
0x14000d6ad  mov     esi, edx
0x14000d6af  test    edx, edx
0x14000d6b1  jnz     short loc_14000D6CF
0x14000d6b3  call    cs:__imp_GetLastError
0x14000d6ba  nop     dword ptr [rax+rax+00h]
0x14000d6bf  test    eax, eax
0x14000d6c1  jnz     loc_14000D8E6
0x14000d6c7  lea     ecx, [rsi+57h]
0x14000d6ca  jmp     loc_14000D8DA
0x14000d6cf  call    InitGlobals
0x14000d6d4  test    eax, eax
0x14000d6d6  jz      loc_14000D8E6
0x14000d6dc  mov     edx, 1
0x14000d6e1  call    DynArrayGetCount2
0x14000d6e6  mov     r10d, eax
0x14000d6e9  cmp     eax, ebp
0x14000d6eb  ja      short loc_14000D758
0x14000d6ed  mov     rax, cs:qword_140015218
0x14000d6f4  test    rax, rax
0x14000d6f7  jz      loc_14000D8C7
0x14000d6fd  cmp     dword ptr [rax], 9
0x14000d700  jnz     loc_14000D8C7
0x14000d706  cmp     [rax+4], edx
0x14000d709  jbe     loc_14000D8C7
0x14000d70f  mov     rax, [rax+8]
0x14000d713  mov     rcx, [rax+18h]
0x14000d717  test    rcx, rcx
0x14000d71a  jz      loc_14000D8C7
0x14000d720  cmp     dword ptr [rcx+4], 10000h
0x14000d727  jz      short loc_14000D736
0x14000d729  cmp     dword ptr [rcx+4], 80000h
0x14000d730  jnz     loc_14000D8C7
0x14000d736  mov     rcx, [rcx+10h]
0x14000d73a  test    rcx, rcx
0x14000d73d  jz      loc_14000D8C7
0x14000d743  mov     edx, ebp
0x14000d745  sub     edx, r10d
0x14000d748  inc     edx
0x14000d74a  call    DynArrayAddColumns
0x14000d74f  cmp     eax, 0FFFFFFFFh
0x14000d752  jz      loc_14000D8C7
0x14000d758  mov     ebx, 80h
0x14000d75d  xor     edx, edx
0x14000d75f  add     ebx, ebx
0x14000d761  mov     r9d, 1
0x14000d767  mov     r8d, ebx
0x14000d76a  lea     ecx, [rdx+4]
0x14000d76d  call    GetInternalTemporaryBuffer
0x14000d772  mov     rdi, rax
0x14000d775  test    rax, rax
0x14000d778  jz      loc_14000D8C7
0x14000d77e  mov     r9d, ebx; cchBufferMax
0x14000d781  mov     r8, rax; lpBuffer
0x14000d784  mov     edx, esi; uID
0x14000d786  xor     ecx, ecx; hInstance
0x14000d788  call    cs:__imp_LoadStringW
0x14000d78f  nop     dword ptr [rax+rax+00h]
0x14000d794  mov     ecx, eax
0x14000d796  test    eax, eax
0x14000d798  jnz     short loc_14000D7F4
0x14000d79a  call    cs:__imp_GetLastError
0x14000d7a1  nop     dword ptr [rax+rax+00h]
0x14000d7a6  cmp     eax, 716h
0x14000d7ab  jnz     loc_14000D8E6
0x14000d7b1  mov     [rsp+68h+Arguments], 0; Arguments
0x14000d7ba  lea     rax, [rsp+68h+Buffer]
0x14000d7bf  mov     [rsp+68h+nSize], 0; nSize
0x14000d7c7  xor     r9d, r9d; dwLanguageId
0x14000d7ca  mov     r8d, esi; dwMessageId
0x14000d7cd  mov     [rsp+68h+lpBuffer], rax; lpBuffer
0x14000d7d2  xor     edx, edx; lpSource
0x14000d7d4  mov     ecx, 0B00h; dwFlags
0x14000d7d9  call    cs:__imp_FormatMessageW
0x14000d7e0  nop     dword ptr [rax+rax+00h]
0x14000d7e5  mov     ecx, eax
0x14000d7e7  test    eax, eax
0x14000d7e9  jz      loc_14000D8E6
0x14000d7ef  mov     rdi, [rsp+68h+Buffer]
0x14000d7f4  lea     eax, [rbx-1]
0x14000d7f7  cmp     ecx, eax
0x14000d7f9  jnb     loc_14000D75D
0x14000d7ff  mov     rax, cs:qword_140015218
0x14000d806  test    rax, rax
0x14000d809  jz      loc_14000D8C7
0x14000d80f  cmp     dword ptr [rax], 9
0x14000d812  jnz     loc_14000D8C7
0x14000d818  cmp     dword ptr [rax+4], 1
0x14000d81c  jbe     loc_14000D8C7
0x14000d822  mov     rax, [rax+8]
0x14000d826  mov     rcx, [rax+18h]
0x14000d82a  test    rcx, rcx
0x14000d82d  jz      loc_14000D8C7
0x14000d833  cmp     dword ptr [rcx+4], 80000h
0x14000d83a  jnz     loc_14000D8C7
0x14000d840  mov     rcx, [rcx+10h]
0x14000d844  xor     r9d, r9d
0x14000d847  mov     r8, rdi
0x14000d84a  mov     edx, ebp
0x14000d84c  call    DynArraySetString
0x14000d851  test    eax, eax
0x14000d853  jz      short loc_14000D8C7
0x14000d855  mov     rcx, [rsp+68h+Buffer]; hMem
0x14000d85a  test    rcx, rcx
0x14000d85d  jz      short loc_14000D874
0x14000d85f  call    cs:__imp_LocalFree
0x14000d866  nop     dword ptr [rax+rax+00h]
0x14000d86b  mov     [rsp+68h+Buffer], 0
0x14000d874  mov     rax, cs:qword_140015218
0x14000d87b  test    rax, rax
0x14000d87e  jz      short loc_14000D8C3
0x14000d880  cmp     dword ptr [rax], 9
0x14000d883  jnz     short loc_14000D8C3
0x14000d885  cmp     dword ptr [rax+4], 1
0x14000d889  jbe     short loc_14000D8C3
0x14000d88b  mov     rax, [rax+8]
0x14000d88f  mov     rcx, [rax+18h]
0x14000d893  test    rcx, rcx
0x14000d896  jz      short loc_14000D8C3
0x14000d898  cmp     dword ptr [rcx+4], 80000h
0x14000d89f  jnz     short loc_14000D8C3
0x14000d8a1  mov     rcx, [rcx+10h]
0x14000d8a5  xor     r8d, r8d
0x14000d8a8  mov     edx, ebp
0x14000d8aa  call    __DynArrayGetItem
0x14000d8af  test    rax, rax
0x14000d8b2  jz      short loc_14000D8C3
0x14000d8b4  cmp     dword ptr [rax+4], 20000h
0x14000d8bb  jnz     short loc_14000D8C3
0x14000d8bd  mov     rax, [rax+10h]
0x14000d8c1  jmp     short loc_14000D8ED
0x14000d8c3  xor     eax, eax
0x14000d8c5  jmp     short loc_14000D8ED
0x14000d8c7  call    cs:__imp_GetLastError
0x14000d8ce  nop     dword ptr [rax+rax+00h]
0x14000d8d3  test    eax, eax
0x14000d8d5  jnz     short loc_14000D8E6
0x14000d8d7  lea     ecx, [rax+8]; dwErrCode
0x14000d8da  call    cs:__imp_SetLastError
0x14000d8e1  nop     dword ptr [rax+rax+00h]
0x14000d8e6  lea     rax, cwszNullString
0x14000d8ed  add     rsp, 48h
0x14000d8f1  pop     rdi
0x14000d8f2  pop     rsi
0x14000d8f3  pop     rbp
0x14000d8f4  pop     rbx
0x14000d8f5  retn
```
