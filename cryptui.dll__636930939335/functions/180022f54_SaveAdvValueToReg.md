# SaveAdvValueToReg

- ea: `0x180022f54`
- end: `0x1800231a6`
- name: `SaveAdvValueToReg`
- size: `594`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f770`

## callees

- `0x180005840`
- `0x180022250`
- `0x180022f54`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002308b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002308b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023171`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023171`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180022fc4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180023077`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180022fc4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180023077`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180023168`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180023168`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002303d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002303d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023180`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002318f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023180`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002318f`

## pseudocode

```c
void __fastcall SaveAdvValueToReg(__int64 a1)
{
  char *lpData; // rdi
  int v3; // ecx
  char *v4; // rax
  unsigned __int64 v5; // r14
  unsigned int v6; // r15d
  __int64 v7; // rsi
  __int64 v8; // rcx
  const char *v9; // r12
  __int64 v10; // rax
  char *v11; // rax
  int Data; // [rsp+A0h] [rbp+48h] BYREF
  DWORD dwDisposition; // [rsp+A8h] [rbp+50h] BYREF
  HKEY hKey; // [rsp+B0h] [rbp+58h] BYREF
  HKEY phkResult; // [rsp+B8h] [rbp+60h] BYREF

  if ( !a1 )
    return;
  hKey = 0;
  phkResult = 0;
  dwDisposition = 0;
  Data = 0;
  lpData = 0;
  if ( !RegCreateKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Cryptography\\UI\\Certmgr\\ExportFormat",
          0,
          0,
          0,
          0xF003Fu,
          0,
          &hKey,
          &dwDisposition) )
  {
    switch ( *(_DWORD *)(a1 + 40) )
    {
      case 1:
        if ( *(_DWORD *)(a1 + 44) )
        {
          Data = 4;
LABEL_14:
          RegSetValueExW(hKey, L"Export", 0, 4u, (const BYTE *)&Data, 4u);
          goto LABEL_15;
        }
        v3 = 1;
        break;
      case 3:
        v3 = *(_DWORD *)(a1 + 44) != 0 ? 6 : 3;
        break;
      case 4:
        v3 = *(_DWORD *)(a1 + 44) != 0 ? 5 : 2;
        break;
      default:
        v3 = Data;
        goto LABEL_13;
    }
    Data = v3;
LABEL_13:
    if ( !v3 )
      goto LABEL_15;
    goto LABEL_14;
  }
LABEL_15:
  dwDisposition = 0;
  if ( !RegCreateKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Cryptography\\UI\\Certmgr\\Purpose",
          0,
          0,
          0,
          0xF003Fu,
          0,
          &phkResult,
          &dwDisposition) )
  {
    v4 = (char *)LocalAlloc(0x40u, 1u);
    lpData = v4;
    if ( v4 )
    {
      v5 = 1;
      *v4 = 0;
      v6 = 0;
      v7 = -1;
      while ( v6 < *(_DWORD *)(a1 + 24) )
      {
        if ( !*(_DWORD *)(*(_QWORD *)(a1 + 32) + 24LL * v6 + 8) )
        {
          if ( v5 > 1 )
            StringCchCatA(lpData, v5, ",");
          v8 = -1;
          v9 = *(const char **)(*(_QWORD *)(a1 + 32) + 24LL * v6 + 16);
          do
            ++v8;
          while ( lpData[v8] );
          if ( v9 )
          {
            v10 = -1;
            do
              ++v10;
            while ( v9[v10] );
          }
          else
          {
            LODWORD(v10) = 0;
          }
          LODWORD(v5) = v8 + v10 + 2;
          v11 = (char *)AggressiveLocalRealloc(lpData, (unsigned int)v5);
          lpData = v11;
          if ( !v11 )
            goto LABEL_34;
          v5 = (int)v5;
          StringCchCatA(v11, (int)v5, v9);
        }
        ++v6;
      }
      do
        ++v7;
      while ( lpData[v7] );
      RegSetValueExA(phkResult, "Purpose", 0, 1u, (const BYTE *)lpData, v7 + 1);
    }
  }
LABEL_34:
  LocalFree(lpData);
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
}

```

## disassembly

```asm
0x180022f54  test    rcx, rcx
0x180022f57  jz      locret_1800231A5
0x180022f5d  mov     r11, rsp
0x180022f60  push    rbp
0x180022f61  push    rbx
0x180022f62  push    rsi
0x180022f63  push    rdi
0x180022f64  push    r12
0x180022f66  push    r13
0x180022f68  push    r14
0x180022f6a  push    r15
0x180022f6c  mov     rbp, rsp
0x180022f6f  sub     rsp, 58h
0x180022f73  xor     r13d, r13d
0x180022f76  lea     rax, [rbp+dwDisposition]
0x180022f7a  mov     [r11-58h], rax
0x180022f7e  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Cryptography\\UI\\"...
0x180022f85  lea     rax, [rbp+hKey]
0x180022f89  mov     [rbp+hKey], r13
0x180022f8d  mov     [r11-60h], rax
0x180022f91  mov     rbx, rcx
0x180022f94  mov     [r11-68h], r13
0x180022f98  mov     esi, 0F003Fh
0x180022f9d  mov     r14, 0FFFFFFFF80000001h
0x180022fa4  mov     [rsp+58h+samDesired], esi; samDesired
0x180022fa8  xor     r9d, r9d; lpClass
0x180022fab  mov     [r11-78h], r13d
0x180022faf  xor     r8d, r8d; Reserved
0x180022fb2  mov     [rbp+arg_18], r13
0x180022fb6  mov     rcx, r14; hKey
0x180022fb9  mov     [rbp+dwDisposition], r13d
0x180022fbd  mov     [rbp+Data], r13d
0x180022fc1  mov     edi, r13d
0x180022fc4  call    cs:__imp_RegCreateKeyExW
0x180022fca  lea     r12d, [r13+1]
0x180022fce  test    eax, eax
0x180022fd0  jnz     short loc_180023043
0x180022fd2  mov     ecx, [rbx+28h]
0x180022fd5  lea     r9d, [r13+4]; dwType
0x180022fd9  sub     ecx, r12d
0x180022fdc  jz      short loc_18002300B
0x180022fde  sub     ecx, 2
0x180022fe1  jz      short loc_180022FFC
0x180022fe3  cmp     ecx, r12d
0x180022fe6  jnz     short loc_180022FF7
0x180022fe8  mov     eax, [rbx+2Ch]
0x180022feb  neg     eax
0x180022fed  sbb     ecx, ecx
0x180022fef  and     ecx, 3
0x180022ff2  add     ecx, 2
0x180022ff5  jmp     short loc_18002301A
0x180022ff7  mov     ecx, [rbp+Data]
0x180022ffa  jmp     short loc_18002301D
0x180022ffc  mov     eax, [rbx+2Ch]
0x180022fff  neg     eax
0x180023001  sbb     ecx, ecx
0x180023003  and     ecx, 3
0x180023006  add     ecx, 3
0x180023009  jmp     short loc_18002301A
0x18002300b  cmp     [rbx+2Ch], r13d
0x18002300f  jz      short loc_180023017
0x180023011  mov     [rbp+Data], r9d
0x180023015  jmp     short loc_180023021
0x180023017  mov     ecx, r12d
0x18002301a  mov     [rbp+Data], ecx
0x18002301d  test    ecx, ecx
0x18002301f  jz      short loc_180023043
0x180023021  mov     rcx, [rbp+hKey]; hKey
0x180023025  lea     rax, [rbp+Data]
0x180023029  mov     [rsp+58h+samDesired], r9d; cbData
0x18002302e  lea     rdx, aExport; "Export"
0x180023035  xor     r8d, r8d; Reserved
0x180023038  mov     [rsp+58h+lpData], rax; lpData
0x18002303d  call    cs:__imp_RegSetValueExW
0x180023043  lea     rax, [rbp+dwDisposition]
0x180023047  mov     [rbp+dwDisposition], r13d
0x18002304b  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x180023050  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Cryptography\\UI\\"...
0x180023057  lea     rax, [rbp+arg_18]
0x18002305b  xor     r9d, r9d; lpClass
0x18002305e  mov     [rsp+58h+phkResult], rax; phkResult
0x180023063  xor     r8d, r8d; Reserved
0x180023066  mov     [rsp+58h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18002306b  mov     rcx, r14; hKey
0x18002306e  mov     [rsp+58h+samDesired], esi; samDesired
0x180023072  mov     dword ptr [rsp+58h+lpData], r13d; dwOptions
0x180023077  call    cs:__imp_RegCreateKeyExW
0x18002307d  test    eax, eax
0x18002307f  jnz     loc_18002316E
0x180023085  mov     rdx, r12; uBytes
0x180023088  lea     ecx, [rax+40h]; uFlags
0x18002308b  call    cs:__imp_LocalAlloc
0x180023091  mov     rdi, rax
0x180023094  test    rax, rax
0x180023097  jz      loc_18002316E
0x18002309d  mov     r14, r12
0x1800230a0  mov     [rax], r13b
0x1800230a3  mov     r15d, r13d
0x1800230a6  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800230aa  cmp     r15d, [rbx+18h]
0x1800230ae  jnb     loc_180023142
0x1800230b4  mov     eax, r15d
0x1800230b7  lea     r12, [rax+rax*2]
0x1800230bb  mov     rax, [rbx+20h]
0x1800230bf  cmp     [rax+r12*8+8], r13d
0x1800230c4  jnz     short loc_180023134
0x1800230c6  cmp     r14, 1
0x1800230ca  jbe     short loc_1800230DE
0x1800230cc  lea     r8, Delimiter; ","
0x1800230d3  mov     rdx, r14; unsigned __int64
0x1800230d6  mov     rcx, rdi; char *
0x1800230d9  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x1800230de  mov     rax, [rbx+20h]
0x1800230e2  mov     rcx, rsi
0x1800230e5  mov     r12, [rax+r12*8+10h]
0x1800230ea  inc     rcx
0x1800230ed  cmp     [rdi+rcx], r13b
0x1800230f1  jnz     short loc_1800230EA
0x1800230f3  test    r12, r12
0x1800230f6  jz      short loc_180023106
0x1800230f8  mov     rax, rsi
0x1800230fb  inc     rax
0x1800230fe  cmp     [r12+rax], r13b
0x180023102  jnz     short loc_1800230FB
0x180023104  jmp     short loc_180023109
0x180023106  mov     eax, r13d
0x180023109  lea     r14d, [rax+2]
0x18002310d  add     r14d, ecx
0x180023110  mov     rcx, rdi; hMem
0x180023113  mov     edx, r14d; uBytes
0x180023116  call    ?AggressiveLocalRealloc@@YAPEAXPEAXK@Z; AggressiveLocalRealloc(void *,ulong)
0x18002311b  mov     rdi, rax
0x18002311e  test    rax, rax
0x180023121  jz      short loc_18002316E
0x180023123  movsxd  r14, r14d
0x180023126  mov     r8, r12; char *
0x180023129  mov     rdx, r14; unsigned __int64
0x18002312c  mov     rcx, rax; char *
0x18002312f  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x180023134  mov     r12d, 1
0x18002313a  add     r15d, r12d
0x18002313d  jmp     loc_1800230AA
0x180023142  inc     rsi
0x180023145  cmp     [rdi+rsi], r13b
0x180023149  jnz     short loc_180023142
0x18002314b  mov     rcx, [rbp+arg_18]; hKey
0x18002314f  lea     eax, [rsi+1]
0x180023152  mov     [rsp+58h+samDesired], eax; cbData
0x180023156  lea     rdx, aPurpose; "Purpose"
0x18002315d  mov     r9d, r12d; dwType
0x180023160  mov     [rsp+58h+lpData], rdi; lpData
0x180023165  xor     r8d, r8d; Reserved
0x180023168  call    cs:__imp_RegSetValueExA
0x18002316e  mov     rcx, rdi; hMem
0x180023171  call    cs:__imp_LocalFree
0x180023177  mov     rcx, [rbp+hKey]; hKey
0x18002317b  test    rcx, rcx
0x18002317e  jz      short loc_180023186
0x180023180  call    cs:__imp_RegCloseKey
0x180023186  mov     rcx, [rbp+arg_18]; hKey
0x18002318a  test    rcx, rcx
0x18002318d  jz      short loc_180023195
0x18002318f  call    cs:__imp_RegCloseKey
0x180023195  add     rsp, 58h
0x180023199  pop     r15
0x18002319b  pop     r14
0x18002319d  pop     r13
0x18002319f  pop     r12
0x1800231a1  pop     rdi
0x1800231a2  pop     rsi
0x1800231a3  pop     rbx
0x1800231a4  pop     rbp
0x1800231a5  retn
```
