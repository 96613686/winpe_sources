# AhgGetPeHeaderInfo

- ea: `0x18000a96c`
- end: `0x18000aaed`
- name: `AhgGetPeHeaderInfo`
- size: `385`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, PVOID BaseAddress)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x18000a208`

## callees

- `0x18000a96c`
- `0x18000aaf4`
- `0x18000abf8`
- `0x18000e240`

## import_xrefs

- `msvcrt!sscanf_s` at `0x18000aaa3`
- `msvcrt!sscanf_s` at `0x18000aaa3`
- `ntdll!RtlImageRvaToVa` at `0x18000aa85`
- `ntdll!RtlImageRvaToVa` at `0x18000aa85`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18000aa67`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18000aa67`

## string_xrefs

- `0x18000a9bb`: `Failed to read PE header. Could be a corrupted image or 16-bit app.`
- `0x18000a9f1`: `Failed to read TimeDataStampYear in PE header.`

## pseudocode

```c
__int64 __fastcall AhgGetPeHeaderInfo(_DWORD *a1, _DWORD *a2, _DWORD *a3, _DWORD *a4, int *a5, PVOID BaseAddress)
{
  int v6; // ebx
  int v7; // r15d
  int v8; // edi
  int v9; // r13d
  __int64 v10; // rax
  __int64 v11; // r14
  unsigned int TimeDateStampYear; // esi
  unsigned int v13; // r13d
  _DWORD *v14; // rax
  const char *v15; // rax
  int v17; // [rsp+20h] [rbp-20h] BYREF
  int v18; // [rsp+24h] [rbp-1Ch]
  int v19; // [rsp+28h] [rbp-18h]
  int v20; // [rsp+2Ch] [rbp-14h] BYREF
  ULONG Size[4]; // [rsp+30h] [rbp-10h] BYREF

  v6 = 0;
  v7 = 0;
  v18 = 0;
  v8 = 0;
  v20 = 0;
  v19 = 0;
  v9 = 0;
  v17 = 0;
  Size[0] = 0;
  v10 = RtlpImageNtHeader(BaseAddress);
  v11 = v10;
  if ( v10 )
  {
    TimeDateStampYear = AhgpGetTimeDateStampYear(&v20, *(unsigned int *)(v10 + 8));
    if ( TimeDateStampYear )
    {
      AslLogCallPrintf(1, "AhgGetPeHeaderInfo", 200, "Failed to read TimeDataStampYear in PE header.");
    }
    else
    {
      v13 = *(unsigned __int16 *)(v11 + 94);
      v7 = v20;
      if ( *(_DWORD *)(v11 + 8) == 708992537 )
        v7 = 0;
      v18 = *(_DWORD *)(v11 + 64);
      v19 = *(_DWORD *)(v11 + 72);
      v9 = (v13 >> 8) & 1;
      v14 = RtlImageDirectoryEntryToData(BaseAddress, 0, 0xEu, Size);
      if ( v14 )
      {
        if ( Size[0] )
        {
          v15 = (const char *)RtlImageRvaToVa((PIMAGE_NT_HEADERS)v11, BaseAddress, v14[2], 0);
          if ( v15 )
          {
            if ( sscanf_s(v15 + 16, "v%hd.%hd", &v17, (char *)&v17 + 2) != 2 )
              v17 = 0;
          }
        }
      }
      v6 = v18;
      TimeDateStampYear = 0;
      v8 = v19;
    }
  }
  else
  {
    AslLogCallPrintf(
      2,
      "AhgGetPeHeaderInfo",
      185,
      "Failed to read PE header. Could be a corrupted image or 16-bit app.");
    TimeDateStampYear = 30;
  }
  *a1 = v7;
  *a2 = v6;
  *a3 = v8;
  *a4 = v17;
  *a5 = v9;
  return TimeDateStampYear;
}

```

## disassembly

```asm
0x18000a96c  mov     rax, rsp
0x18000a96f  mov     [rax+20h], r9
0x18000a973  mov     [rax+18h], r8
0x18000a977  mov     [rax+10h], rdx
0x18000a97b  mov     [rax+8], rcx
0x18000a97f  push    rbp
0x18000a980  push    rbx
0x18000a981  push    rsi
0x18000a982  push    rdi
0x18000a983  push    r13
0x18000a985  push    r14
0x18000a987  push    r15
0x18000a989  mov     rbp, rsp
0x18000a98c  sub     rsp, 40h
0x18000a990  mov     rcx, [rbp+BaseAddress]
0x18000a994  xor     ebx, ebx
0x18000a996  xor     r15d, r15d
0x18000a999  mov     [rbp+var_1C], ebx
0x18000a99c  xor     edi, edi
0x18000a99e  mov     [rbp+var_14], r15d
0x18000a9a2  mov     [rbp+var_18], edi
0x18000a9a5  xor     r13d, r13d
0x18000a9a8  mov     [rbp+var_20], ebx
0x18000a9ab  mov     [rbp+Size], ebx
0x18000a9ae  call    RtlpImageNtHeader
0x18000a9b3  mov     r14, rax
0x18000a9b6  test    rax, rax
0x18000a9b9  jnz     short loc_18000A9DF
0x18000a9bb  lea     r9, aFailedToReadPe_0; "Failed to read PE header. Could be a co"...
0x18000a9c2  mov     r8d, 0B9h
0x18000a9c8  lea     rdx, aAhggetpeheader; "AhgGetPeHeaderInfo"
0x18000a9cf  lea     ecx, [rbx+2]
0x18000a9d2  call    AslLogCallPrintf
0x18000a9d7  lea     esi, [rbx+1Eh]
0x18000a9da  jmp     loc_18000AAB9
0x18000a9df  mov     edx, [rax+8]
0x18000a9e2  lea     rcx, [rbp+var_14]
0x18000a9e6  call    AhgpGetTimeDateStampYear
0x18000a9eb  mov     esi, eax
0x18000a9ed  test    eax, eax
0x18000a9ef  jz      short loc_18000AA14
0x18000a9f1  lea     r9, aFailedToReadTi; "Failed to read TimeDataStampYear in PE "...
0x18000a9f8  mov     r8d, 0C8h
0x18000a9fe  lea     rdx, aAhggetpeheader; "AhgGetPeHeaderInfo"
0x18000aa05  mov     ecx, 1
0x18000aa0a  call    AslLogCallPrintf
0x18000aa0f  jmp     loc_18000AAB9
0x18000aa14  movzx   r13d, word ptr [r14+5Eh]
0x18000aa19  lea     r9, [rbp+Size]; Size
0x18000aa1d  mov     r15d, [rbp+var_14]
0x18000aa21  xor     eax, eax
0x18000aa23  cmp     dword ptr [r14+8], 2A425E19h
0x18000aa2b  mov     r8d, 0Eh; Directory
0x18000aa31  mov     rcx, [rbp+BaseAddress]; BaseAddress
0x18000aa35  cmovz   r15d, eax
0x18000aa39  movzx   eax, word ptr [r14+40h]
0x18000aa3e  mov     word ptr [rbp+var_1C], ax
0x18000aa42  xor     edx, edx; MappedAsImage
0x18000aa44  movzx   eax, word ptr [r14+42h]
0x18000aa49  mov     word ptr [rbp+var_1C+2], ax
0x18000aa4d  movzx   eax, word ptr [r14+48h]
0x18000aa52  mov     word ptr [rbp+var_18], ax
0x18000aa56  movzx   eax, word ptr [r14+4Ah]
0x18000aa5b  shr     r13d, 8
0x18000aa5f  mov     word ptr [rbp+var_18+2], ax
0x18000aa63  and     r13d, 1
0x18000aa67  call    cs:__imp_RtlImageDirectoryEntryToData
0x18000aa6d  test    rax, rax
0x18000aa70  jz      short loc_18000AAB1
0x18000aa72  cmp     [rbp+Size], ebx
0x18000aa75  jz      short loc_18000AAB1
0x18000aa77  mov     r8d, [rax+8]; Rva
0x18000aa7b  xor     r9d, r9d; SectionHeader
0x18000aa7e  mov     rdx, [rbp+BaseAddress]; BaseAddress
0x18000aa82  mov     rcx, r14; NtHeader
0x18000aa85  call    cs:__imp_RtlImageRvaToVa
0x18000aa8b  test    rax, rax
0x18000aa8e  jz      short loc_18000AAB1
0x18000aa90  lea     rcx, [rax+10h]; Buffer
0x18000aa94  lea     r9, [rbp+var_20+2]
0x18000aa98  lea     r8, [rbp+var_20]
0x18000aa9c  lea     rdx, Format; "v%hd.%hd"
0x18000aaa3  call    cs:__imp_sscanf_s
0x18000aaa9  cmp     eax, 2
0x18000aaac  jz      short loc_18000AAB1
0x18000aaae  mov     [rbp+var_20], ebx
0x18000aab1  mov     ebx, [rbp+var_1C]
0x18000aab4  xor     esi, esi
0x18000aab6  mov     edi, [rbp+var_18]
0x18000aab9  mov     rax, [rbp+arg_0]
0x18000aabd  mov     rcx, [rbp+arg_18]
0x18000aac1  mov     [rax], r15d
0x18000aac4  mov     rax, [rbp+arg_8]
0x18000aac8  mov     [rax], ebx
0x18000aaca  mov     rax, [rbp+arg_10]
0x18000aace  mov     [rax], edi
0x18000aad0  mov     eax, [rbp+var_20]
0x18000aad3  mov     [rcx], eax
0x18000aad5  mov     rax, [rbp+arg_20]
0x18000aad9  mov     [rax], r13d
0x18000aadc  mov     eax, esi
0x18000aade  add     rsp, 40h
0x18000aae2  pop     r15
0x18000aae4  pop     r14
0x18000aae6  pop     r13
0x18000aae8  pop     rdi
0x18000aae9  pop     rsi
0x18000aaea  pop     rbx
0x18000aaeb  pop     rbp
0x18000aaec  retn
```
