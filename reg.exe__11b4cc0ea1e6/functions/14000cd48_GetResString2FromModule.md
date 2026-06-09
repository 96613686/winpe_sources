# GetResString2FromModule

- ea: `0x14000cd48`
- end: `0x14000cf80`
- name: `GetResString2FromModule`
- size: `568`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `32`
- callee_count: `7`
- tags: ``

## callers

- `0x140001e90`
- `0x1400024a4`
- `0x140002940`
- `0x140002b70`
- `0x140002bc0`
- `0x1400030b8`
- `0x14000375c`
- `0x140003a58`
- `0x140003c48`
- `0x14000406c`
- `0x140004354`
- `0x140004708`
- `0x140004bbc`
- `0x140005bac`
- `0x140005e84`
- `0x140006394`
- `0x140006a5c`
- `0x140006f9c`
- `0x140007170`
- `0x14000752c`
- `0x140007834`
- `0x140008788`
- `0x140008dfc`
- `0x140008fe8`
- `0x1400094a0`
- `0x140009574`
- `0x1400096a8`
- `0x140009ae4`
- `0x140009d40`
- `0x14000a0a0`
- `0x14000a3f8`
- `0x14000cd10`

## callees

- `0x14000caa8`
- `0x14000cd48`
- `0x14000d114`
- `0x14000e6bc`
- `0x14000e838`
- `0x14000e994`
- `0x14000ec3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cd67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ce42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cf5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cd67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ce42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cf5d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000cf6a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000cf6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000cefb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000cefb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x14000ce36`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x14000ce36`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000ce7b`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000ce7b`

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
  WCHAR *v13; // rdi
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
        || qword_140014218
        && *(_DWORD *)qword_140014218 == 9
        && *(_DWORD *)(qword_140014218 + 4) > v7
        && (v9 = *(_QWORD *)(*(_QWORD *)(qword_140014218 + 8) + 24LL)) != 0
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
            if ( !qword_140014218 )
              break;
            if ( *(_DWORD *)qword_140014218 != 9 )
              break;
            if ( *(_DWORD *)(qword_140014218 + 4) <= 1u )
              break;
            v15 = *(_QWORD *)(*(_QWORD *)(qword_140014218 + 8) + 24LL);
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
            if ( qword_140014218
              && *(_DWORD *)qword_140014218 == 9
              && *(_DWORD *)(qword_140014218 + 4) > 1u
              && (v16 = *(_QWORD *)(*(_QWORD *)(qword_140014218 + 8) + 24LL)) != 0
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
    v5 = a2 + 87;
LABEL_40:
    SetLastError(v5);
  }
  return &cwszNullString;
}

```

## disassembly

```asm
0x14000cd48  mov     [rsp+Buffer], rcx
0x14000cd4d  push    rbx
0x14000cd4e  push    rbp
0x14000cd4f  push    rsi
0x14000cd50  push    rdi
0x14000cd51  sub     rsp, 48h
0x14000cd55  mov     [rsp+68h+Buffer], 0
0x14000cd5e  mov     ebp, r8d
0x14000cd61  mov     esi, edx
0x14000cd63  test    edx, edx
0x14000cd65  jnz     short loc_14000CD7D
0x14000cd67  call    cs:__imp_GetLastError
0x14000cd6d  test    eax, eax
0x14000cd6f  jnz     loc_14000CF70
0x14000cd75  lea     ecx, [rsi+57h]
0x14000cd78  jmp     loc_14000CF6A
0x14000cd7d  call    InitGlobals
0x14000cd82  test    eax, eax
0x14000cd84  jz      loc_14000CF70
0x14000cd8a  mov     edx, 1
0x14000cd8f  call    DynArrayGetCount2
0x14000cd94  mov     r10d, eax
0x14000cd97  cmp     eax, ebp
0x14000cd99  ja      short loc_14000CE06
0x14000cd9b  mov     rax, cs:qword_140014218
0x14000cda2  test    rax, rax
0x14000cda5  jz      loc_14000CF5D
0x14000cdab  cmp     dword ptr [rax], 9
0x14000cdae  jnz     loc_14000CF5D
0x14000cdb4  cmp     [rax+4], edx
0x14000cdb7  jbe     loc_14000CF5D
0x14000cdbd  mov     rax, [rax+8]
0x14000cdc1  mov     rcx, [rax+18h]
0x14000cdc5  test    rcx, rcx
0x14000cdc8  jz      loc_14000CF5D
0x14000cdce  cmp     dword ptr [rcx+4], 10000h
0x14000cdd5  jz      short loc_14000CDE4
0x14000cdd7  cmp     dword ptr [rcx+4], 80000h
0x14000cdde  jnz     loc_14000CF5D
0x14000cde4  mov     rcx, [rcx+10h]
0x14000cde8  test    rcx, rcx
0x14000cdeb  jz      loc_14000CF5D
0x14000cdf1  mov     edx, ebp
0x14000cdf3  sub     edx, r10d
0x14000cdf6  inc     edx
0x14000cdf8  call    DynArrayAddColumns
0x14000cdfd  cmp     eax, 0FFFFFFFFh
0x14000ce00  jz      loc_14000CF5D
0x14000ce06  mov     ebx, 80h
0x14000ce0b  xor     edx, edx
0x14000ce0d  add     ebx, ebx
0x14000ce0f  mov     r9d, 1
0x14000ce15  mov     r8d, ebx
0x14000ce18  lea     ecx, [rdx+4]
0x14000ce1b  call    GetInternalTemporaryBuffer
0x14000ce20  mov     rdi, rax
0x14000ce23  test    rax, rax
0x14000ce26  jz      loc_14000CF5D
0x14000ce2c  mov     r9d, ebx; cchBufferMax
0x14000ce2f  mov     r8, rax; lpBuffer
0x14000ce32  mov     edx, esi; uID
0x14000ce34  xor     ecx, ecx; hInstance
0x14000ce36  call    cs:__imp_LoadStringW
0x14000ce3c  mov     ecx, eax
0x14000ce3e  test    eax, eax
0x14000ce40  jnz     short loc_14000CE90
0x14000ce42  call    cs:__imp_GetLastError
0x14000ce48  cmp     eax, 716h
0x14000ce4d  jnz     loc_14000CF70
0x14000ce53  mov     [rsp+68h+Arguments], 0; Arguments
0x14000ce5c  lea     rax, [rsp+68h+Buffer]
0x14000ce61  mov     [rsp+68h+nSize], 0; nSize
0x14000ce69  xor     r9d, r9d; dwLanguageId
0x14000ce6c  mov     r8d, esi; dwMessageId
0x14000ce6f  mov     [rsp+68h+lpBuffer], rax; lpBuffer
0x14000ce74  xor     edx, edx; lpSource
0x14000ce76  mov     ecx, 0B00h; dwFlags
0x14000ce7b  call    cs:__imp_FormatMessageW
0x14000ce81  mov     ecx, eax
0x14000ce83  test    eax, eax
0x14000ce85  jz      loc_14000CF70
0x14000ce8b  mov     rdi, [rsp+68h+Buffer]
0x14000ce90  lea     eax, [rbx-1]
0x14000ce93  cmp     ecx, eax
0x14000ce95  jnb     loc_14000CE0B
0x14000ce9b  mov     rax, cs:qword_140014218
0x14000cea2  test    rax, rax
0x14000cea5  jz      loc_14000CF5D
0x14000ceab  cmp     dword ptr [rax], 9
0x14000ceae  jnz     loc_14000CF5D
0x14000ceb4  cmp     dword ptr [rax+4], 1
0x14000ceb8  jbe     loc_14000CF5D
0x14000cebe  mov     rax, [rax+8]
0x14000cec2  mov     rcx, [rax+18h]
0x14000cec6  test    rcx, rcx
0x14000cec9  jz      loc_14000CF5D
0x14000cecf  cmp     dword ptr [rcx+4], 80000h
0x14000ced6  jnz     loc_14000CF5D
0x14000cedc  mov     rcx, [rcx+10h]
0x14000cee0  xor     r9d, r9d
0x14000cee3  mov     r8, rdi
0x14000cee6  mov     edx, ebp
0x14000cee8  call    DynArraySetString
0x14000ceed  test    eax, eax
0x14000ceef  jz      short loc_14000CF5D
0x14000cef1  mov     rcx, [rsp+68h+Buffer]; hMem
0x14000cef6  test    rcx, rcx
0x14000cef9  jz      short loc_14000CF0A
0x14000cefb  call    cs:__imp_LocalFree
0x14000cf01  mov     [rsp+68h+Buffer], 0
0x14000cf0a  mov     rax, cs:qword_140014218
0x14000cf11  test    rax, rax
0x14000cf14  jz      short loc_14000CF59
0x14000cf16  cmp     dword ptr [rax], 9
0x14000cf19  jnz     short loc_14000CF59
0x14000cf1b  cmp     dword ptr [rax+4], 1
0x14000cf1f  jbe     short loc_14000CF59
0x14000cf21  mov     rax, [rax+8]
0x14000cf25  mov     rcx, [rax+18h]
0x14000cf29  test    rcx, rcx
0x14000cf2c  jz      short loc_14000CF59
0x14000cf2e  cmp     dword ptr [rcx+4], 80000h
0x14000cf35  jnz     short loc_14000CF59
0x14000cf37  mov     rcx, [rcx+10h]
0x14000cf3b  xor     r8d, r8d
0x14000cf3e  mov     edx, ebp
0x14000cf40  call    __DynArrayGetItem
0x14000cf45  test    rax, rax
0x14000cf48  jz      short loc_14000CF59
0x14000cf4a  cmp     dword ptr [rax+4], 20000h
0x14000cf51  jnz     short loc_14000CF59
0x14000cf53  mov     rax, [rax+10h]
0x14000cf57  jmp     short loc_14000CF77
0x14000cf59  xor     eax, eax
0x14000cf5b  jmp     short loc_14000CF77
0x14000cf5d  call    cs:__imp_GetLastError
0x14000cf63  test    eax, eax
0x14000cf65  jnz     short loc_14000CF70
0x14000cf67  lea     ecx, [rax+8]; dwErrCode
0x14000cf6a  call    cs:__imp_SetLastError
0x14000cf70  lea     rax, cwszNullString
0x14000cf77  add     rsp, 48h
0x14000cf7b  pop     rdi
0x14000cf7c  pop     rsi
0x14000cf7d  pop     rbp
0x14000cf7e  pop     rbx
0x14000cf7f  retn
```
