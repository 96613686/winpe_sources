# MmsCreate

- ea: `0x18003de94`
- end: `0x18003dfce`
- name: `MmsCreate`
- size: `314`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800199f8`

## callees

- `0x180003474`
- `0x18003de94`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18003def0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18003def0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003df8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003df8e`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18003df7f`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18003df7f`

## pseudocode

```c
signed int __fastcall MmsCreate(__int64 a1)
{
  __int128 v2; // xmm1
  __int128 v3; // xmm0
  __int128 v4; // xmm1
  __int128 v5; // xmm0
  DWORD dwAllocationGranularity; // edx
  signed int result; // eax
  int v8; // ecx
  int v9; // ecx
  HANDLE FileMappingW; // rax
  struct _SYSTEM_INFO SystemInfo; // [rsp+30h] [rbp-50h] BYREF
  __int128 v12; // [rsp+60h] [rbp-20h]
  __int128 v13; // [rsp+70h] [rbp-10h]

  memset_0(&SystemInfo, 0, 0x50u);
  v2 = *(_OWORD *)&SystemInfo.lpMaximumApplicationAddress;
  *(_OWORD *)a1 = *(_OWORD *)&SystemInfo.dwOemId;
  v3 = *(_OWORD *)&SystemInfo.dwNumberOfProcessors;
  *(_OWORD *)(a1 + 16) = v2;
  v4 = v12;
  *(_OWORD *)(a1 + 32) = v3;
  v5 = v13;
  *(_OWORD *)(a1 + 48) = v4;
  *(_OWORD *)(a1 + 64) = v5;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  GetSystemInfo(&SystemInfo);
  dwAllocationGranularity = SystemInfo.dwAllocationGranularity;
  if ( ((SystemInfo.dwAllocationGranularity - 1) & 0x4000000) != 0 )
    return -2147023764;
  v8 = 1;
  while ( 1 << v8 != SystemInfo.dwPageSize )
  {
    if ( (unsigned int)++v8 >= 0x20 )
    {
      LOBYTE(v8) = 0;
      break;
    }
  }
  *(_BYTE *)(a1 + 72) = v8;
  if ( !(_BYTE)v8 )
    return -2147023434;
  v9 = 1;
  while ( 1 << v9 != dwAllocationGranularity )
  {
    if ( (unsigned int)++v9 >= 0x20 )
    {
      LOBYTE(v9) = 0;
      break;
    }
  }
  *(_BYTE *)(a1 + 73) = v9;
  if ( !(_BYTE)v9 )
    return -2147023434;
  *(_DWORD *)(a1 + 44) = 2;
  *(_DWORD *)(a1 + 40) = 0;
  FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0x4000004u, 2u, 0, 0);
  *(_QWORD *)(a1 + 8) = FileMappingW;
  if ( FileMappingW )
  {
    *(_QWORD *)(a1 + 16) = 0x4000000;
    *(_QWORD *)a1 = off_18004C750;
    return 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18003de94  mov     [rsp-8+arg_0], rbx
0x18003de99  push    rbp
0x18003de9a  mov     rbp, rsp
0x18003de9d  sub     rsp, 80h
0x18003dea4  xor     edx, edx; Val
0x18003dea6  mov     rbx, rcx
0x18003dea9  lea     rcx, [rbp+SystemInfo]; void *
0x18003dead  lea     r8d, [rdx+50h]; Size
0x18003deb1  call    memset_0
0x18003deb6  movups  xmm0, xmmword ptr [rbp+SystemInfo]
0x18003deba  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x18003debe  movups  xmm1, xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress]
0x18003dec2  movaps  xmmword ptr [rbx], xmm0
0x18003dec5  movups  xmm0, xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors]
0x18003dec9  movaps  xmmword ptr [rbx+10h], xmm1
0x18003decd  movups  xmm1, [rbp+var_20]
0x18003ded1  movaps  xmmword ptr [rbx+20h], xmm0
0x18003ded5  movups  xmm0, [rbp+var_10]
0x18003ded9  movaps  xmmword ptr [rbx+30h], xmm1
0x18003dedd  xorps   xmm1, xmm1
0x18003dee0  movaps  xmmword ptr [rbx+40h], xmm0
0x18003dee4  movups  xmmword ptr [rbp+SystemInfo], xmm1
0x18003dee8  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm1
0x18003deec  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm1
0x18003def0  call    cs:__imp_GetSystemInfo
0x18003def6  mov     edx, [rbp+SystemInfo.dwAllocationGranularity]
0x18003def9  lea     eax, [rdx-1]
0x18003defc  bt      eax, 1Ah
0x18003df00  jnb     short loc_18003DF0C
0x18003df02  mov     eax, 8007046Ch
0x18003df07  jmp     loc_18003DFBD
0x18003df0c  mov     r8d, 1
0x18003df12  mov     ecx, r8d
0x18003df15  mov     eax, r8d
0x18003df18  shl     eax, cl
0x18003df1a  cmp     eax, [rbp+SystemInfo.dwPageSize]
0x18003df1d  jz      short loc_18003DF29
0x18003df1f  add     ecx, r8d
0x18003df22  cmp     ecx, 20h ; ' '
0x18003df25  jb      short loc_18003DF15
0x18003df27  xor     ecx, ecx
0x18003df29  mov     [rbx+48h], cl
0x18003df2c  test    cl, cl
0x18003df2e  jz      loc_18003DFB8
0x18003df34  mov     ecx, r8d
0x18003df37  mov     eax, r8d
0x18003df3a  shl     eax, cl
0x18003df3c  cmp     eax, edx
0x18003df3e  jz      short loc_18003DF4A
0x18003df40  add     ecx, r8d
0x18003df43  cmp     ecx, 20h ; ' '
0x18003df46  jb      short loc_18003DF37
0x18003df48  xor     ecx, ecx
0x18003df4a  mov     [rbx+49h], cl
0x18003df4d  test    cl, cl
0x18003df4f  jz      short loc_18003DFB8
0x18003df51  mov     r9d, 2; dwMaximumSizeHigh
0x18003df57  mov     [rsp+80h+lpName], 0; lpName
0x18003df60  xor     edx, edx; lpFileMappingAttributes
0x18003df62  mov     [rbx+2Ch], r9d
0x18003df66  mov     r8d, 4000004h; flProtect
0x18003df6c  mov     dword ptr [rbx+28h], 0
0x18003df73  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18003df77  mov     [rsp+80h+dwMaximumSizeLow], 0; dwMaximumSizeLow
0x18003df7f  call    cs:__imp_CreateFileMappingW
0x18003df85  mov     [rbx+8], rax
0x18003df89  test    rax, rax
0x18003df8c  jnz     short loc_18003DFA2
0x18003df8e  call    cs:__imp_GetLastError
0x18003df94  test    eax, eax
0x18003df96  jle     short loc_18003DFBD
0x18003df98  movzx   eax, ax
0x18003df9b  or      eax, 80070000h
0x18003dfa0  jmp     short loc_18003DFBD
0x18003dfa2  lea     rax, off_18004C750
0x18003dfa9  mov     qword ptr [rbx+10h], 4000000h
0x18003dfb1  mov     [rbx], rax
0x18003dfb4  xor     eax, eax
0x18003dfb6  jmp     short loc_18003DFBD
0x18003dfb8  mov     eax, 800705B6h
0x18003dfbd  mov     rbx, [rsp+80h+arg_0]
0x18003dfc5  add     rsp, 80h
0x18003dfcc  pop     rbp
0x18003dfcd  retn
```
