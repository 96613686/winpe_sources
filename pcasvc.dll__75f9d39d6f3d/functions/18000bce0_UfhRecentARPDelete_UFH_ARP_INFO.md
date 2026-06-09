# UfhRecentARPDelete(_UFH_ARP_INFO *)

- ea: `0x18000bce0`
- end: `0x18000bf6b`
- name: `?UfhRecentARPDelete@@YAKPEAU_UFH_ARP_INFO@@@Z`
- size: `651`
- prototype: `unsigned int __fastcall(wchar_t *String2)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180039500`

## callees

- `0x18000bce0`
- `0x18000c018`
- `0x180035738`
- `0x18007a9cf`
- `0x1800f1f10`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000beba`
- `msvcrt!_wcsicmp` at `0x18000bf1a`
- `msvcrt!_wcsicmp` at `0x18000beba`
- `msvcrt!_wcsicmp` at `0x18000bf1a`
- `ntdll!RtlFreeHeap` at `0x18000bf60`
- `ntdll!RtlFreeHeap` at `0x18000bf60`
- `ntdll!RtlAllocateHeap` at `0x18000bdb2`
- `ntdll!RtlAllocateHeap` at `0x18000bdb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bd8b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bf08`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bf46`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bd8b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bf08`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bf46`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bd74`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bd74`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000be07`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000be07`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000bf2e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000bf2e`

## pseudocode

```c
__int64 __fastcall UfhRecentARPDelete(wchar_t *String2)
{
  HKEY v2; // rsi
  const WCHAR *StorePath; // rax
  unsigned int v4; // ebx
  BYTE *lpData; // rdi
  DWORD v6; // r15d
  LSTATUS v7; // eax
  const unsigned __int16 *v8; // r11
  unsigned int v9; // r14d
  __int64 v10; // rbx
  __int64 v11; // r11
  SIZE_T Size; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchValueName; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v16; // [rsp+58h] [rbp-A8h]
  int v17; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v18[3]; // [rsp+68h] [rbp-98h]
  wchar_t v19[260]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t String1[260]; // [rsp+288h] [rbp+188h] BYREF
  char v21; // [rsp+490h] [rbp+390h] BYREF
  WCHAR ValueName[264]; // [rsp+CC0h] [rbp+BC0h] BYREF

  memset_0(v19, 0, 0xC3Au);
  v2 = 0;
  memset_0(ValueName, 0, 0x208u);
  Size = 3130;
  hKey = 0;
  StorePath = (const WCHAR *)UfhpUtilityGetStorePath(0);
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, StorePath, 0, 0xF003Fu, &hKey);
  if ( !v4 )
  {
    v2 = hKey;
    v4 = 0;
  }
  RegCloseKey(HKEY_LOCAL_MACHINE);
  if ( v4 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    lpData = 0;
  }
  else
  {
    v4 = 8;
    lpData = (BYTE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned int)Size);
    if ( lpData )
    {
      v6 = 0;
      while ( 2 )
      {
        cchValueName = 260;
        LODWORD(Size) = 3130;
        v7 = RegEnumValueW(v2, v6, ValueName, &cchValueName, 0, (LPDWORD)&Size + 1, lpData, (LPDWORD)&Size);
        v4 = v7;
        if ( v7 == 259 )
        {
          v4 = 0;
        }
        else if ( !v7 && HIDWORD(Size) == 7 )
        {
          v17 = 1040;
          v18[0] = v19;
          v8 = (const unsigned __int16 *)lpData;
          v9 = 0;
          v18[1] = String1;
          v18[2] = (unsigned __int16 *)&v21;
          v16 = 0x10400000104LL;
          while ( *v8 )
          {
            v10 = -1;
            do
              ++v10;
            while ( v8[v10] );
            if ( v9 >= 3 )
              break;
            if ( (int)StringCchCopyW(v18[v9], *((unsigned int *)&v16 + v9), v8) < 0 )
            {
              v4 = 111;
              goto LABEL_19;
            }
            ++v9;
            v8 = (const unsigned __int16 *)(v11 + 2 * v10 + 2);
          }
          if ( _wcsicmp(String1, String2 + 260) || _wcsicmp(v19, String2) || (v4 = RegDeleteValueW(v2, ValueName)) == 0 )
          {
            ++v6;
            continue;
          }
        }
        break;
      }
    }
  }
LABEL_19:
  if ( v2 )
    RegCloseKey(v2);
  if ( lpData )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, lpData);
  return v4;
}

```

## disassembly

```asm
0x18000bce0  push    rbp
0x18000bce2  push    rbx
0x18000bce3  push    rsi
0x18000bce4  push    rdi
0x18000bce5  push    r12
0x18000bce7  push    r13
0x18000bce9  push    r14
0x18000bceb  push    r15
0x18000bced  lea     rbp, [rsp-0DE8h]
0x18000bcf5  sub     rsp, 0EE8h
0x18000bcfc  mov     rax, cs:__security_cookie
0x18000bd03  xor     rax, rsp
0x18000bd06  mov     [rbp+0E20h+var_50], rax
0x18000bd0d  mov     r13, rcx
0x18000bd10  xor     edx, edx; Val
0x18000bd12  lea     rcx, [rbp+0E20h+var_EA0]; void *
0x18000bd16  mov     r8d, 0C3Ah; Size
0x18000bd1c  call    memset_0
0x18000bd21  xor     r12d, r12d
0x18000bd24  lea     rcx, [rbp+0E20h+ValueName]; void *
0x18000bd2b  xor     edx, edx; Val
0x18000bd2d  mov     r8d, 208h; Size
0x18000bd33  mov     esi, r12d
0x18000bd36  call    memset_0
0x18000bd3b  xor     ecx, ecx
0x18000bd3d  mov     dword ptr [rsp+0F20h+Size+4], r12d
0x18000bd42  mov     dword ptr [rsp+0F20h+Size], 0C3Ah
0x18000bd4a  mov     [rsp+0F20h+hKey], r12
0x18000bd4f  call    ?UfhpUtilityGetStorePath@@YAPEAGW4_UFH_DATA_TYPE@@@Z; UfhpUtilityGetStorePath(_UFH_DATA_TYPE)
0x18000bd54  mov     rdx, rax; lpSubKey
0x18000bd57  mov     rdi, 0FFFFFFFF80000002h
0x18000bd5e  lea     rax, [rsp+0F20h+hKey]
0x18000bd63  mov     r9d, 0F003Fh; samDesired
0x18000bd69  xor     r8d, r8d; ulOptions
0x18000bd6c  mov     [rsp+0F20h+phkResult], rax; phkResult
0x18000bd71  mov     rcx, rdi; hKey
0x18000bd74  call    cs:__imp_RegOpenKeyExW
0x18000bd7a  mov     ebx, eax
0x18000bd7c  test    eax, eax
0x18000bd7e  jnz     short loc_18000BD88
0x18000bd80  mov     rsi, [rsp+0F20h+hKey]
0x18000bd85  mov     ebx, r12d
0x18000bd88  mov     rcx, rdi; hKey
0x18000bd8b  call    cs:__imp_RegCloseKey
0x18000bd91  test    ebx, ebx
0x18000bd93  jnz     loc_18000BEFE
0x18000bd99  mov     rcx, gs:60h
0x18000bda2  mov     ebx, 8
0x18000bda7  mov     r8d, dword ptr [rsp+0F20h+Size]; Size
0x18000bdac  mov     edx, ebx; Flags
0x18000bdae  mov     rcx, [rcx+30h]; HeapHandle
0x18000bdb2  call    cs:__imp_RtlAllocateHeap
0x18000bdb8  mov     rdi, rax
0x18000bdbb  test    rax, rax
0x18000bdbe  jz      loc_18000BECF
0x18000bdc4  mov     r15d, r12d
0x18000bdc7  lea     rax, [rsp+0F20h+Size]
0x18000bdcc  mov     [rsp+0F20h+cchValueName], 104h
0x18000bdd4  mov     [rsp+0F20h+lpcbData], rax; lpcbData
0x18000bdd9  lea     r9, [rsp+0F20h+cchValueName]; lpcchValueName
0x18000bdde  lea     rax, [rsp+0F20h+Size+4]
0x18000bde3  mov     [rsp+0F20h+lpData], rdi; lpData
0x18000bde8  mov     [rsp+0F20h+lpType], rax; lpType
0x18000bded  lea     r8, [rbp+0E20h+ValueName]; lpValueName
0x18000bdf4  mov     edx, r15d; dwIndex
0x18000bdf7  mov     [rsp+0F20h+phkResult], r12; lpReserved
0x18000bdfc  mov     rcx, rsi; hKey
0x18000bdff  mov     dword ptr [rsp+0F20h+Size], 0C3Ah
0x18000be07  call    cs:__imp_RegEnumValueW
0x18000be0d  mov     ebx, eax
0x18000be0f  cmp     eax, 103h
0x18000be14  jz      loc_18000BECC
0x18000be1a  test    eax, eax
0x18000be1c  jnz     loc_18000BECF
0x18000be22  cmp     dword ptr [rsp+0F20h+Size+4], 7
0x18000be27  jnz     loc_18000BECF
0x18000be2d  lea     rax, [rbp+0E20h+var_EA0]
0x18000be31  mov     [rsp+0F20h+var_EC0], 410h
0x18000be39  mov     [rsp+0F20h+var_EB8], rax
0x18000be3e  mov     r11, rdi
0x18000be41  lea     rax, [rbp+0E20h+String1]
0x18000be48  mov     r14d, r12d
0x18000be4b  mov     [rsp+0F20h+var_EB0], rax
0x18000be50  lea     rax, [rbp+0E20h+var_A90]
0x18000be57  mov     [rsp+0F20h+var_EA8], rax
0x18000be5c  mov     eax, 104h
0x18000be61  mov     dword ptr [rsp+0F20h+var_EC8], eax
0x18000be65  mov     dword ptr [rsp+0F20h+var_EC8+4], eax
0x18000be69  cmp     [r11], r12w
0x18000be6d  jz      short loc_18000BEAC
0x18000be6f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000be73  inc     rbx
0x18000be76  cmp     [r11+rbx*2], r12w
0x18000be7b  jnz     short loc_18000BE73
0x18000be7d  cmp     r14d, 3
0x18000be81  jnb     short loc_18000BEAC
0x18000be83  mov     ecx, r14d
0x18000be86  mov     r8, r11; unsigned __int16 *
0x18000be89  mov     edx, dword ptr [rsp+rcx*4+0F20h+var_EC8]; unsigned __int64
0x18000be8d  mov     rcx, [rsp+rcx*8+0F20h+var_EB8]; unsigned __int16 *
0x18000be92  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000be97  test    eax, eax
0x18000be99  js      loc_18000BF3C
0x18000be9f  inc     r14d
0x18000bea2  lea     r11, [r11+rbx*2]
0x18000bea6  add     r11, 2
0x18000beaa  jmp     short loc_18000BE69
0x18000beac  lea     rdx, [r13+208h]; String2
0x18000beb3  lea     rcx, [rbp+0E20h+String1]; String1
0x18000beba  call    cs:__imp__wcsicmp
0x18000bec0  test    eax, eax
0x18000bec2  jz      short loc_18000BF13
0x18000bec4  inc     r15d
0x18000bec7  jmp     loc_18000BDC7
0x18000becc  mov     ebx, r12d
0x18000becf  test    rsi, rsi
0x18000bed2  jnz     short loc_18000BF43
0x18000bed4  test    rdi, rdi
0x18000bed7  jnz     short loc_18000BF4E
0x18000bed9  mov     eax, ebx
0x18000bedb  mov     rcx, [rbp+0E20h+var_50]
0x18000bee2  xor     rcx, rsp; StackCookie
0x18000bee5  call    __security_check_cookie
0x18000beea  add     rsp, 0EE8h
0x18000bef1  pop     r15
0x18000bef3  pop     r14
0x18000bef5  pop     r13
0x18000bef7  pop     r12
0x18000bef9  pop     rdi
0x18000befa  pop     rsi
0x18000befb  pop     rbx
0x18000befc  pop     rbp
0x18000befd  retn
0x18000befe  mov     rcx, [rsp+0F20h+hKey]; hKey
0x18000bf03  test    rcx, rcx
0x18000bf06  jz      short loc_18000BF0E
0x18000bf08  call    cs:__imp_RegCloseKey
0x18000bf0e  mov     rdi, r12
0x18000bf11  jmp     short loc_18000BECF
0x18000bf13  mov     rdx, r13; String2
0x18000bf16  lea     rcx, [rbp+0E20h+var_EA0]; String1
0x18000bf1a  call    cs:__imp__wcsicmp
0x18000bf20  test    eax, eax
0x18000bf22  jnz     short loc_18000BEC4
0x18000bf24  lea     rdx, [rbp+0E20h+ValueName]; lpValueName
0x18000bf2b  mov     rcx, rsi; hKey
0x18000bf2e  call    cs:__imp_RegDeleteValueW
0x18000bf34  mov     ebx, eax
0x18000bf36  test    eax, eax
0x18000bf38  jnz     short loc_18000BECF
0x18000bf3a  jmp     short loc_18000BEC4
0x18000bf3c  mov     ebx, 6Fh ; 'o'
0x18000bf41  jmp     short loc_18000BECF
0x18000bf43  mov     rcx, rsi; hKey
0x18000bf46  call    cs:__imp_RegCloseKey
0x18000bf4c  jmp     short loc_18000BED4
0x18000bf4e  mov     rcx, gs:60h
0x18000bf57  mov     r8, rdi; P
0x18000bf5a  xor     edx, edx; Flags
0x18000bf5c  mov     rcx, [rcx+30h]; HeapHandle
0x18000bf60  call    cs:__imp_RtlFreeHeap
0x18000bf66  jmp     loc_18000BED9
```
