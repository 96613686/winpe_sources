# DpspAddRegisteredEventToScenario(HKEY__ *,__SCENARIOINFO *,ushort *,ulong)

- ea: `0x18000c9cc`
- end: `0x18000cc1b`
- name: `?DpspAddRegisteredEventToScenario@@YAJPEAUHKEY__@@PEAU__SCENARIOINFO@@PEAGK@Z`
- size: `591`
- prototype: `__int64 __fastcall(HKEY hKey, struct __SCENARIOINFO *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000ce94`

## callees

- `0x1800013a0`
- `0x180008ea0`
- `0x180009090`
- `0x18000bc1c`
- `0x18000c9cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cbe3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cbe3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cb2e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cb2e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000cb9f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000cb9f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ca4f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ca4f`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000ca63`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000ca63`

## pseudocode

```c
__int64 __fastcall DpspAddRegisteredEventToScenario(
        HKEY hKey,
        struct __SCENARIOINFO *a2,
        unsigned __int16 *a3,
        unsigned int a4)
{
  unsigned __int16 *v4; // rbp
  unsigned __int64 v7; // r14
  HKEY v8; // rdi
  unsigned int v9; // r15d
  int v10; // ebx
  __int64 v11; // rax
  unsigned __int64 v12; // rax
  int v13; // r12d
  unsigned __int64 v14; // rax
  void *v15; // rbx
  unsigned int v16; // edi
  HANDLE ProcessHeap; // rax
  LPVOID v18; // rax
  unsigned __int16 *v19; // rax
  int v20; // r8d
  int v21; // eax
  LSTATUS v22; // eax
  DWORD cbData; // [rsp+30h] [rbp-48h] BYREF
  HKEY hKeya; // [rsp+38h] [rbp-40h] BYREF
  int Data; // [rsp+98h] [rbp+20h] BYREF

  hKeya = 0;
  v4 = 0;
  Data = 0;
  cbData = 4;
  v7 = a4;
  v8 = hKey;
  v9 = 2 * a4;
  if ( a4 != (2 * a4) >> 1 )
  {
    v10 = -2147024362;
    goto LABEL_28;
  }
  v11 = *((unsigned int *)a2 + 4);
  if ( *((_DWORD *)a2 + 5) < (unsigned int)v11 )
    goto LABEL_9;
  v12 = 2 * v11;
  if ( v12 > 0xFFFFFFFF )
  {
    v20 = 200;
  }
  else
  {
    v13 = v12;
    v14 = 16LL * (unsigned int)v12;
    if ( v14 <= 0xFFFFFFFF )
    {
      v15 = (void *)*((_QWORD *)a2 + 6);
      v16 = v14;
      ProcessHeap = GetProcessHeap();
      v18 = HeapReAlloc(ProcessHeap, 8u, v15, v16);
      if ( !v18 )
      {
        v10 = -2147024882;
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
          (int)L"DpspAddRegisteredEventToScenario",
          208,
          (int)L"Error = %d",
          14);
        goto LABEL_26;
      }
      v8 = hKey;
      *((_QWORD *)a2 + 6) = v18;
      *((_DWORD *)a2 + 4) = v13;
LABEL_9:
      v19 = (unsigned __int16 *)WdipAlloc(v9);
      v4 = v19;
      if ( v19 )
      {
        v21 = StringCchCopyW(v19, v7, a3);
        v10 = v21;
        if ( v21 >= 0 )
        {
          v22 = RegOpenKeyExW(v8, a3, 0, 0x20019u, &hKeya);
          v10 = v22;
          if ( v22 > 0 )
            v10 = (unsigned __int16)v22 | 0x80070000;
          if ( v10 >= 0 )
          {
            if ( hKeya )
            {
              v10 = RegQueryValueExW(hKeya, L"SuppressEvent", 0, 0, (LPBYTE)&Data, &cbData);
              if ( !v10 )
                *(_DWORD *)(*((_QWORD *)a2 + 6) + 16LL * *((unsigned int *)a2 + 5) + 8) = Data == 1;
              *(_QWORD *)(*((_QWORD *)a2 + 6) + 16LL * (unsigned int)(*((_DWORD *)a2 + 5))++) = v4;
              v4 = 0;
            }
            else
            {
              v10 = -2147467259;
              WdipTraceError(
                (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
                (int)L"DpspAddRegisteredEventToScenario",
                234,
                (int)L"Error = %d",
                5);
            }
          }
          else
          {
            WdipTraceError(
              (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
              (int)L"DpspAddRegisteredEventToScenario",
              233,
              (int)L"Error = %d",
              v10);
          }
        }
        else
        {
          WdipTraceError(
            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
            (int)L"DpspAddRegisteredEventToScenario",
            222,
            (int)L"Error = %d",
            v21);
        }
      }
      else
      {
        v10 = -2147024882;
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
          (int)L"DpspAddRegisteredEventToScenario",
          216,
          (int)L"Error = %d",
          14);
      }
      goto LABEL_26;
    }
    v20 = 205;
  }
  v10 = -2147024362;
  WdipTraceError(
    (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
    (int)L"DpspAddRegisteredEventToScenario",
    v20,
    (int)L"Error = %d",
    22);
LABEL_26:
  if ( hKeya )
  {
    RegCloseKey(hKeya);
    hKeya = 0;
  }
LABEL_28:
  WdipFree(v4);
  WdipFree(0);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000c9cc  mov     rax, rsp
0x18000c9cf  mov     [rax+10h], rbx
0x18000c9d3  mov     [rax+8], rcx
0x18000c9d7  push    rbp
0x18000c9d8  push    rsi
0x18000c9d9  push    rdi
0x18000c9da  push    r12
0x18000c9dc  push    r13
0x18000c9de  push    r14
0x18000c9e0  push    r15
0x18000c9e2  sub     rsp, 40h
0x18000c9e6  mov     qword ptr [rax-40h], 0
0x18000c9ee  xor     ebp, ebp
0x18000c9f0  mov     dword ptr [rax+20h], 0
0x18000c9f7  mov     r13, r8
0x18000c9fa  mov     dword ptr [rax-48h], 4
0x18000ca01  mov     rsi, rdx
0x18000ca04  mov     r14d, r9d
0x18000ca07  mov     rdi, rcx
0x18000ca0a  lea     r15d, [r14+r14]
0x18000ca0e  mov     eax, r15d
0x18000ca11  shr     eax, 1
0x18000ca13  cmp     r9d, eax
0x18000ca16  jz      short loc_18000CA22
0x18000ca18  mov     ebx, 80070216h
0x18000ca1d  jmp     loc_18000CBF2
0x18000ca22  mov     eax, [rdx+10h]
0x18000ca25  cmp     [rdx+14h], eax
0x18000ca28  jb      short loc_18000CA93
0x18000ca2a  add     rax, rax
0x18000ca2d  mov     ecx, 0FFFFFFFFh
0x18000ca32  cmp     rax, rcx
0x18000ca35  ja      loc_18000CAC0
0x18000ca3b  mov     r12d, eax
0x18000ca3e  mov     eax, eax
0x18000ca40  shl     rax, 4
0x18000ca44  cmp     rax, rcx
0x18000ca47  ja      short loc_18000CAB8
0x18000ca49  mov     rbx, [rdx+30h]
0x18000ca4d  mov     edi, eax
0x18000ca4f  call    cs:__imp_GetProcessHeap
0x18000ca55  mov     r9d, edi; dwBytes
0x18000ca58  mov     r8, rbx; lpMem
0x18000ca5b  mov     rcx, rax; hHeap
0x18000ca5e  mov     edx, 8; dwFlags
0x18000ca63  call    cs:__imp_HeapReAlloc
0x18000ca69  test    rax, rax
0x18000ca6c  jnz     short loc_18000CA83
0x18000ca6e  mov     ebx, 8007000Eh
0x18000ca73  mov     dword ptr [rsp+78h+phkResult], 0Eh
0x18000ca7b  mov     r8d, 0D0h
0x18000ca81  jmp     short loc_18000CAD3
0x18000ca83  mov     rdi, [rsp+78h+arg_0]
0x18000ca8b  mov     [rsi+30h], rax
0x18000ca8f  mov     [rsi+10h], r12d
0x18000ca93  mov     ecx, r15d
0x18000ca96  call    WdipAlloc
0x18000ca9b  mov     rbp, rax
0x18000ca9e  test    rax, rax
0x18000caa1  jnz     short loc_18000CAF2
0x18000caa3  mov     ebx, 8007000Eh
0x18000caa8  mov     dword ptr [rsp+78h+phkResult], 0Eh
0x18000cab0  mov     r8d, 0D8h
0x18000cab6  jmp     short loc_18000CAD3
0x18000cab8  mov     r8d, 0CDh
0x18000cabe  jmp     short loc_18000CAC6
0x18000cac0  mov     r8d, 0C8h; int
0x18000cac6  mov     dword ptr [rsp+78h+phkResult], 216h; Args
0x18000cace  mov     ebx, 80070216h
0x18000cad3  lea     r9, aErrorD; "Error = %d"
0x18000cada  lea     rdx, aDpspaddregiste; "DpspAddRegisteredEventToScenario"
0x18000cae1  lea     rcx, aClientcoreBase_8; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000cae8  call    WdipTraceError
0x18000caed  jmp     loc_18000CBD9
0x18000caf2  mov     rdx, r14; unsigned __int64
0x18000caf5  mov     r8, r13; unsigned __int16 *
0x18000caf8  mov     rcx, rbp; unsigned __int16 *
0x18000cafb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000cb00  mov     ebx, eax
0x18000cb02  test    eax, eax
0x18000cb04  jns     short loc_18000CB15
0x18000cb06  movzx   ecx, ax
0x18000cb09  mov     r8d, 0DEh
0x18000cb0f  mov     dword ptr [rsp+78h+phkResult], ecx
0x18000cb13  jmp     short loc_18000CAD3
0x18000cb15  lea     rax, [rsp+78h+hKey]
0x18000cb1a  mov     r9d, 20019h; samDesired
0x18000cb20  xor     r8d, r8d; ulOptions
0x18000cb23  mov     [rsp+78h+phkResult], rax; phkResult
0x18000cb28  mov     rdx, r13; lpSubKey
0x18000cb2b  mov     rcx, rdi; hKey
0x18000cb2e  call    cs:__imp_RegOpenKeyExW
0x18000cb34  mov     ebx, eax
0x18000cb36  test    eax, eax
0x18000cb38  jle     short loc_18000CB43
0x18000cb3a  movzx   ebx, ax
0x18000cb3d  or      ebx, 80070000h
0x18000cb43  test    ebx, ebx
0x18000cb45  jns     short loc_18000CB59
0x18000cb47  movzx   eax, bx
0x18000cb4a  mov     r8d, 0E9h
0x18000cb50  mov     dword ptr [rsp+78h+phkResult], eax
0x18000cb54  jmp     loc_18000CAD3
0x18000cb59  mov     rcx, [rsp+78h+hKey]; hKey
0x18000cb5e  test    rcx, rcx
0x18000cb61  jnz     short loc_18000CB7B
0x18000cb63  mov     ebx, 80004005h
0x18000cb68  mov     dword ptr [rsp+78h+phkResult], 4005h
0x18000cb70  mov     r8d, 0EAh
0x18000cb76  jmp     loc_18000CAD3
0x18000cb7b  lea     rax, [rsp+78h+cbData]
0x18000cb80  xor     r9d, r9d; lpType
0x18000cb83  mov     [rsp+78h+lpcbData], rax; lpcbData
0x18000cb88  lea     rdx, aSuppressevent; "SuppressEvent"
0x18000cb8f  lea     rax, [rsp+78h+Data]
0x18000cb97  xor     r8d, r8d; lpReserved
0x18000cb9a  mov     [rsp+78h+phkResult], rax; lpData
0x18000cb9f  call    cs:__imp_RegQueryValueExW
0x18000cba5  mov     ebx, eax
0x18000cba7  test    eax, eax
0x18000cba9  jnz     short loc_18000CBC6
0x18000cbab  mov     ecx, [rsi+14h]
0x18000cbae  xor     edx, edx
0x18000cbb0  cmp     [rsp+78h+Data], 1
0x18000cbb8  mov     rax, [rsi+30h]
0x18000cbbc  setz    dl
0x18000cbbf  add     rcx, rcx
0x18000cbc2  mov     [rax+rcx*8+8], edx
0x18000cbc6  mov     ecx, [rsi+14h]
0x18000cbc9  mov     rax, [rsi+30h]
0x18000cbcd  add     rcx, rcx
0x18000cbd0  mov     [rax+rcx*8], rbp
0x18000cbd4  inc     dword ptr [rsi+14h]
0x18000cbd7  xor     ebp, ebp
0x18000cbd9  mov     rcx, [rsp+78h+hKey]; hKey
0x18000cbde  test    rcx, rcx
0x18000cbe1  jz      short loc_18000CBF2
0x18000cbe3  call    cs:__imp_RegCloseKey
0x18000cbe9  mov     [rsp+78h+hKey], 0
0x18000cbf2  mov     rcx, rbp
0x18000cbf5  call    WdipFree
0x18000cbfa  xor     ecx, ecx
0x18000cbfc  call    WdipFree
0x18000cc01  mov     eax, ebx
0x18000cc03  mov     rbx, [rsp+78h+arg_8]
0x18000cc0b  add     rsp, 40h
0x18000cc0f  pop     r15
0x18000cc11  pop     r14
0x18000cc13  pop     r13
0x18000cc15  pop     r12
0x18000cc17  pop     rdi
0x18000cc18  pop     rsi
0x18000cc19  pop     rbp
0x18000cc1a  retn
```
