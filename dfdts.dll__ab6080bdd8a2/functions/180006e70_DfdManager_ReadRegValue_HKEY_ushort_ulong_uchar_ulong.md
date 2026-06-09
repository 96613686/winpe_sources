# DfdManager::ReadRegValue(HKEY__ *,ushort *,ulong,uchar * *,ulong *)

- ea: `0x180006e70`
- end: `0x180006ff0`
- name: `?ReadRegValue@DfdManager@@AEAAJPEAUHKEY__@@PEAGKPEAPEAEPEAK@Z`
- size: `384`
- prototype: `__int64 __fastcall(DfdManager *this, HKEY, unsigned __int16 *, int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800061f4`

## callees

- `0x180002c90`
- `0x180006e70`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180006f12`
- `KERNEL32!HeapAlloc` at `0x180006f12`
- `KERNEL32!GetProcessHeap` at `0x180006f01`
- `KERNEL32!GetProcessHeap` at `0x180006faa`
- `KERNEL32!GetProcessHeap` at `0x180006f01`
- `KERNEL32!GetProcessHeap` at `0x180006faa`
- `KERNEL32!HeapFree` at `0x180006fb8`
- `KERNEL32!HeapFree` at `0x180006fb8`
- `ADVAPI32!RegQueryValueExW` at `0x180006ec1`
- `ADVAPI32!RegQueryValueExW` at `0x180006f65`
- `ADVAPI32!RegQueryValueExW` at `0x180006ec1`
- `ADVAPI32!RegQueryValueExW` at `0x180006f65`

## pseudocode

```c
__int64 __fastcall DfdManager::ReadRegValue(
        DfdManager *this,
        HKEY a2,
        unsigned __int16 *a3,
        int a4,
        unsigned __int8 **a5,
        unsigned int *a6)
{
  unsigned int Value; // eax
  unsigned __int8 **v8; // rsi
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  unsigned int v12; // ebx
  HANDLE ProcessHeap; // rax
  BYTE *lpData; // rax
  __int64 v15; // r9
  unsigned __int8 *v16; // rdi
  HANDLE v17; // rax
  DWORD Type[6]; // [rsp+30h] [rbp-18h] BYREF
  SIZE_T dwBytes; // [rsp+68h] [rbp+20h] BYREF

  LODWORD(dwBytes) = a4;
  Type[0] = 3;
  if ( a2 )
  {
    LODWORD(dwBytes) = 0;
    Value = RegQueryValueExW(a2, L"DiskUniqueID", 0, Type, 0, (LPDWORD)&dwBytes);
    v8 = a5;
    v9 = Value;
    if ( Value )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_16;
      v11 = 29;
    }
    else
    {
      v12 = dwBytes;
      ProcessHeap = GetProcessHeap();
      lpData = (BYTE *)HeapAlloc(ProcessHeap, 8u, v12);
      *v8 = lpData;
      if ( !lpData )
      {
        v9 = 14;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_16;
        v11 = 30;
        v15 = 14;
        goto LABEL_15;
      }
      Value = RegQueryValueExW(a2, L"DiskUniqueID", 0, Type, lpData, (LPDWORD)&dwBytes);
      v9 = Value;
      if ( !Value )
      {
        if ( a6 )
          *a6 = dwBytes;
        return v9;
      }
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_16:
        v16 = *v8;
        if ( *v8 )
        {
          v17 = GetProcessHeap();
          HeapFree(v17, 0, v16);
          *v8 = 0;
        }
        return v9;
      }
      v11 = 31;
    }
    v15 = Value;
LABEL_15:
    WPP_SF_d(v10[2], v11, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids, v15);
    goto LABEL_16;
  }
  return 87;
}

```

## disassembly

```asm
0x180006e70  mov     r11, rsp
0x180006e73  mov     [r11+8], rbx
0x180006e77  mov     [r11+10h], rsi
0x180006e7b  mov     [r11+20h], r9d
0x180006e7f  push    rdi
0x180006e80  sub     rsp, 40h
0x180006e84  mov     [rsp+48h+Type], 3
0x180006e8c  mov     rdi, rdx
0x180006e8f  test    rdx, rdx
0x180006e92  jz      loc_180006FDB
0x180006e98  lea     rax, [r11+20h]
0x180006e9c  mov     dword ptr [rsp+48h+dwBytes], 0
0x180006ea4  mov     [r11-20h], rax
0x180006ea8  lea     r9, [r11-18h]; lpType
0x180006eac  xor     r8d, r8d; lpReserved
0x180006eaf  mov     qword ptr [r11-28h], 0
0x180006eb7  lea     rdx, ValueName; "DiskUniqueID"
0x180006ebe  mov     rcx, rdi; hKey
0x180006ec1  call    cs:__imp_RegQueryValueExW
0x180006ec7  mov     rsi, [rsp+48h+arg_20]
0x180006ecc  mov     ebx, eax
0x180006ece  test    eax, eax
0x180006ed0  jz      short loc_180006EFD
0x180006ed2  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ed9  lea     rdx, WPP_GLOBAL_Control
0x180006ee0  cmp     rcx, rdx
0x180006ee3  jz      loc_180006FA2
0x180006ee9  test    byte ptr [rcx+1Ch], 1
0x180006eed  jz      loc_180006FA2
0x180006ef3  mov     edx, 1Dh
0x180006ef8  jmp     loc_180006F8F
0x180006efd  mov     ebx, dword ptr [rsp+48h+dwBytes]
0x180006f01  call    cs:__imp_GetProcessHeap
0x180006f07  mov     r8d, ebx; dwBytes
0x180006f0a  mov     edx, 8; dwFlags
0x180006f0f  mov     rcx, rax; hHeap
0x180006f12  call    cs:__imp_HeapAlloc
0x180006f18  mov     [rsi], rax
0x180006f1b  test    rax, rax
0x180006f1e  jnz     short loc_180006F44
0x180006f20  lea     ebx, [rax+0Eh]
0x180006f23  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f2a  lea     rdx, WPP_GLOBAL_Control
0x180006f31  cmp     rcx, rdx
0x180006f34  jz      short loc_180006FA2
0x180006f36  test    byte ptr [rcx+1Ch], 1
0x180006f3a  jz      short loc_180006FA2
0x180006f3c  lea     edx, [rax+1Eh]
0x180006f3f  mov     r9d, ebx
0x180006f42  jmp     short loc_180006F92
0x180006f44  lea     rcx, [rsp+48h+dwBytes]
0x180006f49  xor     r8d, r8d; lpReserved
0x180006f4c  mov     [rsp+48h+lpcbData], rcx; lpcbData
0x180006f51  lea     r9, [rsp+48h+Type]; lpType
0x180006f56  mov     rcx, rdi; hKey
0x180006f59  mov     [rsp+48h+lpData], rax; lpData
0x180006f5e  lea     rdx, ValueName; "DiskUniqueID"
0x180006f65  call    cs:__imp_RegQueryValueExW
0x180006f6b  mov     ebx, eax
0x180006f6d  test    eax, eax
0x180006f6f  jz      short loc_180006FC7
0x180006f71  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f78  lea     rdx, WPP_GLOBAL_Control
0x180006f7f  cmp     rcx, rdx
0x180006f82  jz      short loc_180006FA2
0x180006f84  test    byte ptr [rcx+1Ch], 1
0x180006f88  jz      short loc_180006FA2
0x180006f8a  mov     edx, 1Fh
0x180006f8f  mov     r9d, eax
0x180006f92  mov     rcx, [rcx+10h]
0x180006f96  lea     r8, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids
0x180006f9d  call    WPP_SF_d
0x180006fa2  mov     rdi, [rsi]
0x180006fa5  test    rdi, rdi
0x180006fa8  jz      short loc_180006FD7
0x180006faa  call    cs:__imp_GetProcessHeap
0x180006fb0  mov     r8, rdi; lpMem
0x180006fb3  xor     edx, edx; dwFlags
0x180006fb5  mov     rcx, rax; hHeap
0x180006fb8  call    cs:__imp_HeapFree
0x180006fbe  mov     qword ptr [rsi], 0
0x180006fc5  jmp     short loc_180006FD7
0x180006fc7  mov     rcx, [rsp+48h+arg_28]
0x180006fcc  test    rcx, rcx
0x180006fcf  jz      short loc_180006FD7
0x180006fd1  mov     eax, dword ptr [rsp+48h+dwBytes]
0x180006fd5  mov     [rcx], eax
0x180006fd7  mov     eax, ebx
0x180006fd9  jmp     short loc_180006FE0
0x180006fdb  mov     eax, 57h ; 'W'
0x180006fe0  mov     rbx, [rsp+48h+arg_0]
0x180006fe5  mov     rsi, [rsp+48h+arg_8]
0x180006fea  add     rsp, 40h
0x180006fee  pop     rdi
0x180006fef  retn
```
