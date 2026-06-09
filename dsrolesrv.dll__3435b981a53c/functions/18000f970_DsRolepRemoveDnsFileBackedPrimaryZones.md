# DsRolepRemoveDnsFileBackedPrimaryZones

- ea: `0x18000f970`
- end: `0x18000fb5d`
- name: `DsRolepRemoveDnsFileBackedPrimaryZones`
- size: `493`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180012460`

## callees

- `0x18000f970`
- `0x180020dbc`
- `0x180027fd0`
- `0x1800295c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f9d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f9df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f9e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f9f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f9d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f9df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f9e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f9f8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000fa69`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000faf7`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000fa69`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000faf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fa86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fa86`
- `ntdll!RtlAllocateHeap` at `0x18000faba`
- `ntdll!RtlAllocateHeap` at `0x18000faba`
- `ntdll!RtlFreeHeap` at `0x18000fa15`
- `ntdll!RtlFreeHeap` at `0x18000fb3d`
- `ntdll!RtlFreeHeap` at `0x18000fa15`
- `ntdll!RtlFreeHeap` at `0x18000fb3d`

## string_xrefs

- `0x18000fb22`: `Failed to remove zone %s: 0x%lx\n. Please remove the zone manually`
- `0x18000fb05`: `DeleteZone`

## pseudocode

```c
__int64 __fastcall DsRolepRemoveDnsFileBackedPrimaryZones(int a1, int a2, int a3, int a4)
{
  PVOID lpMultiByteStr; // rdi
  int v5; // eax
  __int64 i; // rsi
  unsigned int v8; // eax
  int v9; // ebx
  __int64 v10; // rbx
  DWORD LastError; // eax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  unsigned int v16; // eax
  int cbMultiByte; // [rsp+28h] [rbp-50h]

  lpMultiByteStr = 0;
  v5 = DnssrvEnumZonesEx(a1, a2, a3, a4);
  if ( v5 != 1722 )
  {
    if ( v5 )
    {
      DsRolepLogPrintRoutine(1, "Get zone list from DNS server failed with %lu\n", v5);
    }
    else
    {
      for ( i = 0; (unsigned int)i < MEMORY[8]; i = (unsigned int)(i + 1) )
      {
        v8 = WideCharToMultiByte(0, 0, *(LPCWCH *)(*(_QWORD *)(8 * i + 0x10) + 8LL), -1, 0, 0, 0, 0);
        v9 = v8;
        if ( v8
          && (lpMultiByteStr = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v8),
              WideCharToMultiByte(
                0,
                0,
                *(LPCWCH *)(*(_QWORD *)(8 * i + 0x10) + 8LL),
                -1,
                (LPSTR)lpMultiByteStr,
                v9,
                0,
                0)) )
        {
          v16 = DnssrvOperationEx(v13, v12, v14, v15, (__int64)lpMultiByteStr, cbMultiByte, "DeleteZone");
          if ( v16 )
          {
            DsRolepLogPrintRoutine(
              2,
              "Failed to remove zone %s: 0x%lx\n. Please remove the zone manually",
              lpMultiByteStr,
              v16);
          }
          else
          {
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, lpMultiByteStr);
            lpMultiByteStr = 0;
          }
        }
        else
        {
          v10 = *(_QWORD *)(*(_QWORD *)(8 * i + 0x10) + 8LL);
          LastError = GetLastError();
          DsRolepLogPrintRoutine(2, "Failed to convert zone name %ws: 0x%lx\n", v10, LastError);
        }
      }
    }
  }
  if ( lpMultiByteStr )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, lpMultiByteStr);
  return 0;
}

```

## disassembly

```asm
0x18000f970  mov     r11, rsp
0x18000f973  push    rbx
0x18000f974  push    rbp
0x18000f975  push    rsi
0x18000f976  push    rdi
0x18000f977  sub     rsp, 58h
0x18000f97b  lea     rax, [r11+8]
0x18000f97f  mov     qword ptr [r11+8], 0
0x18000f987  mov     [r11-50h], rax
0x18000f98b  xor     edi, edi
0x18000f98d  call    DnssrvEnumZonesEx
0x18000f992  cmp     eax, 6BAh
0x18000f997  jz      short loc_18000F9B3
0x18000f999  test    eax, eax
0x18000f99b  jz      loc_18000FA26
0x18000f9a1  mov     r8d, eax
0x18000f9a4  lea     rdx, aGetZoneListFro; "Get zone list from DNS server failed wi"...
0x18000f9ab  lea     ecx, [rdi+1]
0x18000f9ae  call    DsRolepLogPrintRoutine
0x18000f9b3  mov     rbx, [rsp+78h+hMem]
0x18000f9bb  test    rbx, rbx
0x18000f9be  jz      short loc_18000F9FE
0x18000f9c0  xor     esi, esi
0x18000f9c2  cmp     [rbx+8], esi
0x18000f9c5  jbe     short loc_18000F9F5
0x18000f9c7  mov     rbp, [rbx+rsi*8+10h]
0x18000f9cc  test    rbp, rbp
0x18000f9cf  jz      short loc_18000F9EE
0x18000f9d1  mov     rcx, [rbp+8]; hMem
0x18000f9d5  call    cs:__imp_LocalFree
0x18000f9db  mov     rcx, [rbp+20h]; hMem
0x18000f9df  call    cs:__imp_LocalFree
0x18000f9e5  mov     rcx, rbp; hMem
0x18000f9e8  call    cs:__imp_LocalFree
0x18000f9ee  inc     esi
0x18000f9f0  cmp     esi, [rbx+8]
0x18000f9f3  jb      short loc_18000F9C7
0x18000f9f5  mov     rcx, rbx; hMem
0x18000f9f8  call    cs:__imp_LocalFree
0x18000f9fe  test    rdi, rdi
0x18000fa01  jz      short loc_18000FA1B
0x18000fa03  mov     rcx, gs:60h
0x18000fa0c  mov     r8, rdi; P
0x18000fa0f  xor     edx, edx; Flags
0x18000fa11  mov     rcx, [rcx+30h]; HeapHandle
0x18000fa15  call    cs:__imp_RtlFreeHeap
0x18000fa1b  xor     eax, eax
0x18000fa1d  add     rsp, 58h
0x18000fa21  pop     rdi
0x18000fa22  pop     rsi
0x18000fa23  pop     rbp
0x18000fa24  pop     rbx
0x18000fa25  retn
0x18000fa26  mov     rbx, [rsp+78h+hMem]
0x18000fa2e  xor     esi, esi
0x18000fa30  cmp     [rbx+8], esi
0x18000fa33  jbe     short loc_18000F9BB
0x18000fa35  mov     r8, [rbx+rsi*8+10h]
0x18000fa3a  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000fa3e  mov     [rsp+78h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18000fa47  xor     edx, edx; dwFlags
0x18000fa49  mov     [rsp+78h+lpDefaultChar], 0; lpDefaultChar
0x18000fa52  xor     ecx, ecx; CodePage
0x18000fa54  mov     [rsp+78h+cbMultiByte], 0; cbMultiByte
0x18000fa5c  mov     r8, [r8+8]; lpWideCharStr
0x18000fa60  mov     [rsp+78h+lpMultiByteStr], 0; lpMultiByteStr
0x18000fa69  call    cs:__imp_WideCharToMultiByte
0x18000fa6f  mov     ebx, eax
0x18000fa71  test    eax, eax
0x18000fa73  jnz     short loc_18000FAA8
0x18000fa75  mov     rax, [rsp+78h+hMem]
0x18000fa7d  mov     rcx, [rax+rsi*8+10h]
0x18000fa82  mov     rbx, [rcx+8]
0x18000fa86  call    cs:__imp_GetLastError
0x18000fa8c  mov     r8, rbx
0x18000fa8f  lea     rdx, aFailedToConver_0; "Failed to convert zone name %ws: 0x%lx"...
0x18000fa96  mov     r9d, eax
0x18000fa99  mov     ecx, 2
0x18000fa9e  call    DsRolepLogPrintRoutine
0x18000faa3  jmp     loc_18000FB45
0x18000faa8  mov     rcx, gs:60h
0x18000fab1  mov     r8, rbx; Size
0x18000fab4  xor     edx, edx; Flags
0x18000fab6  mov     rcx, [rcx+30h]; HeapHandle
0x18000faba  call    cs:__imp_RtlAllocateHeap
0x18000fac0  mov     rcx, [rsp+78h+hMem]
0x18000fac8  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000facc  mov     [rsp+78h+lpUsedDefaultChar], 0; int
0x18000fad5  xor     edx, edx; dwFlags
0x18000fad7  mov     [rsp+78h+lpDefaultChar], 0; lpDefaultChar
0x18000fae0  mov     rdi, rax
0x18000fae3  mov     [rsp+78h+cbMultiByte], ebx; int
0x18000fae7  mov     r8, [rcx+rsi*8+10h]
0x18000faec  xor     ecx, ecx; CodePage
0x18000faee  mov     [rsp+78h+lpMultiByteStr], rax; lpMultiByteStr
0x18000faf3  mov     r8, [r8+8]; lpWideCharStr
0x18000faf7  call    cs:__imp_WideCharToMultiByte
0x18000fafd  test    eax, eax
0x18000faff  jz      loc_18000FA75
0x18000fb05  lea     rax, aDeletezone; "DeleteZone"
0x18000fb0c  mov     [rsp+78h+lpDefaultChar], rax; String1
0x18000fb11  mov     [rsp+78h+lpMultiByteStr], rdi; __int64
0x18000fb16  call    DnssrvOperationEx
0x18000fb1b  mov     r8, rdi; P
0x18000fb1e  test    eax, eax
0x18000fb20  jz      short loc_18000FB2E
0x18000fb22  lea     rdx, aFailedToRemove_2; "Failed to remove zone %s: 0x%lx\n. Plea"...
0x18000fb29  jmp     loc_18000FA96
0x18000fb2e  mov     rcx, gs:60h
0x18000fb37  xor     edx, edx; Flags
0x18000fb39  mov     rcx, [rcx+30h]; HeapHandle
0x18000fb3d  call    cs:__imp_RtlFreeHeap
0x18000fb43  xor     edi, edi
0x18000fb45  mov     rbx, [rsp+78h+hMem]
0x18000fb4d  inc     esi
0x18000fb4f  cmp     esi, [rbx+8]
0x18000fb52  jb      loc_18000FA35
0x18000fb58  jmp     loc_18000F9BB
```
