# DiscpBuildInitiatorInstanceList

- ea: `0x180005a54`
- end: `0x180005d23`
- name: `DiscpBuildInitiatorInstanceList`
- size: `719`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x180013b24`

## callees

- `0x180001410`
- `0x180001d60`
- `0x180005948`
- `0x180005a54`

## import_xrefs

- `ISCSIUM!DiscpPnpDeviceInterfaceToInstanceName` at `0x180005baa`
- `ISCSIUM!DiscpPnpDeviceInterfaceToInstanceName` at `0x180005baa`
- `ISCSIUM!DiscpAllocMemory` at `0x180005ab3`
- `ISCSIUM!DiscpAllocMemory` at `0x180005ab3`
- `ISCSIUM!DiscpFreeMemory` at `0x180005bf6`
- `ISCSIUM!DiscpFreeMemory` at `0x180005cbd`
- `ISCSIUM!DiscpFreeMemory` at `0x180005cf6`
- `ISCSIUM!DiscpFreeMemory` at `0x180005bf6`
- `ISCSIUM!DiscpFreeMemory` at `0x180005cbd`
- `ISCSIUM!DiscpFreeMemory` at `0x180005cf6`
- `ntdll!RtlLeaveCriticalSection` at `0x180005c91`
- `ntdll!RtlLeaveCriticalSection` at `0x180005c91`
- `ntdll!RtlEnterCriticalSection` at `0x180005c39`
- `ntdll!RtlEnterCriticalSection` at `0x180005c39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005cce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005cdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005cce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005cdd`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180005ad8`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180005ad8`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180005b8f`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180005b8f`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x180005b51`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x180005b51`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180005c20`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180005c20`
- `DEVOBJ!DevObjGetClassDevs` at `0x180005b10`
- `DEVOBJ!DevObjGetClassDevs` at `0x180005b10`

## string_xrefs

- `0x180005ce3`: `DevObjCreateDeviceInfoList -> %d\n`

## pseudocode

```c
__int64 DiscpBuildInitiatorInstanceList()
{
  __int64 v0; // r15
  __int64 DeviceInfoList; // rax
  __int64 v2; // r14
  unsigned int v3; // edi
  int v4; // esi
  __int64 *v5; // rcx
  __int64 v6; // rax
  DWORD v7; // eax
  DWORD v8; // ebx
  __int128 *v9; // rdi
  __int128 *v10; // rax
  volatile signed __int32 *v11; // rdx
  __int128 *v12; // rcx
  DWORD LastError; // eax
  const char *v14; // rcx
  __int128 v16; // [rsp+30h] [rbp-59h] BYREF
  int v17; // [rsp+40h] [rbp-49h] BYREF
  STRSAFE_LPCWSTR pszSrc; // [rsp+48h] [rbp-41h] BYREF
  __int64 v19; // [rsp+50h] [rbp-39h] BYREF
  _OWORD v20[2]; // [rsp+58h] [rbp-31h] BYREF
  _OWORD v21[3]; // [rsp+78h] [rbp-11h] BYREF

  v17 = 0;
  v19 = 0;
  pszSrc = 0;
  memset(v20, 0, sizeof(v20));
  memset(v21, 0, sizeof(v21));
  v16 = 0;
  v0 = DiscpAllocMemory(4096);
  if ( !v0 )
    return 8;
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v2 = DeviceInfoList;
  if ( DeviceInfoList == -1 )
  {
    LastError = GetLastError();
    v14 = "DevObjCreateDeviceInfoList -> %d\n";
  }
  else
  {
    if ( (unsigned int)DevObjGetClassDevs(
                         DeviceInfoList,
                         &GUID_DEVINTERFACE_STORAGEPORT,
                         0,
                         18,
                         0,
                         0,
                         v16,
                         *((_QWORD *)&v16 + 1),
                         v17) )
    {
      v3 = 0;
      *((_QWORD *)&v16 + 1) = &v16;
      v4 = 0;
      *(_QWORD *)&v16 = &v16;
      do
      {
        while ( 1 )
        {
          LODWORD(v20[0]) = 32;
          if ( !(unsigned int)DevObjEnumDeviceInterfaces(v2, 0, &GUID_DEVINTERFACE_STORAGEPORT, v3, v20) )
            break;
          LODWORD(v21[0]) = 48;
          *(_DWORD *)v0 = 8;
          if ( !(unsigned int)DevObjGetDeviceInterfaceDetail(v2, v20, v0, 4096, &v17, v21) )
            break;
          if ( !(unsigned int)DiscpPnpDeviceInterfaceToInstanceName(v0 + 4, 0, MSiSCSI_HBAInformation_GUID, &pszSrc) )
          {
            if ( !(unsigned int)DiscpBuildInitiatorInstanceByPnpName((STRSAFE_LPCWSTR)(v0 + 4), pszSrc, (__int64)&v19) )
            {
              v5 = (__int64 *)*((_QWORD *)&v16 + 1);
              if ( **((__int128 ***)&v16 + 1) != &v16 )
                __fastfail(3u);
              v6 = v19;
              ++v4;
              *(_QWORD *)v19 = &v16;
              *(_QWORD *)(v6 + 8) = v5;
              *v5 = v6;
              *((_QWORD *)&v16 + 1) = v6;
            }
            DiscpFreeMemory(pszSrc);
          }
          ++v3;
        }
        v7 = GetLastError();
        ++v3;
      }
      while ( !v7 );
      v8 = 0;
      if ( v7 != 259 )
        v8 = v7;
      DevObjDestroyDeviceInfoList(v2);
      if ( v8 )
      {
        v9 = (__int128 *)v16;
        while ( v9 != &v16 )
        {
          v10 = v9;
          v11 = (volatile signed __int32 *)v9;
          v12 = v9;
          v9 = *(__int128 **)v9;
          *((_DWORD *)v10 + 5) |= 0x80000000;
          if ( _InterlockedExchangeAdd(v11 + 4, 0xFFFFFFFF) == 1 )
            DiscpFreeMemory(v12);
        }
      }
      else if ( v4 )
      {
        RtlEnterCriticalSection(&DiscpCritSection);
        if ( (__int128 *)v16 == &v16 )
        {
          off_180027008[0] = &DiscpInitiatorInstanceList;
          DiscpInitiatorInstanceList = &DiscpInitiatorInstanceList;
        }
        else
        {
          *(_OWORD *)&DiscpInitiatorInstanceList = v16;
          *(_QWORD *)(v16 + 8) = &DiscpInitiatorInstanceList;
          *off_180027008[0] = &DiscpInitiatorInstanceList;
        }
        DiscpInitiatorInstanceCount = v4;
        RtlLeaveCriticalSection(&DiscpCritSection);
      }
      goto LABEL_31;
    }
    LastError = GetLastError();
    v14 = "DevObjGetClassDevs -> %d\n";
  }
  v8 = LastError;
  printf(v14, LastError);
LABEL_31:
  DiscpFreeMemory(v0);
  return v8;
}

```

## disassembly

```asm
0x180005a54  push    rbp
0x180005a56  push    rbx
0x180005a57  push    rsi
0x180005a58  push    rdi
0x180005a59  push    r12
0x180005a5b  push    r14
0x180005a5d  push    r15
0x180005a5f  lea     rbp, [rsp-27h]
0x180005a64  sub     rsp, 0B0h
0x180005a6b  mov     rax, cs:__security_cookie
0x180005a72  xor     rax, rsp
0x180005a75  mov     [rbp+57h+var_38], rax
0x180005a79  xorps   xmm0, xmm0
0x180005a7c  mov     [rbp+57h+var_A0], 0
0x180005a83  xorps   xmm1, xmm1
0x180005a86  mov     [rbp+57h+var_90], 0
0x180005a8e  mov     ecx, 1000h
0x180005a93  mov     [rbp+57h+pszSrc], 0
0x180005a9b  movups  [rbp+57h+var_88], xmm0
0x180005a9f  movups  [rbp+57h+var_78], xmm0
0x180005aa3  movups  [rbp+57h+var_68], xmm1
0x180005aa7  movups  [rbp+57h+var_58], xmm1
0x180005aab  movups  [rbp+57h+var_48], xmm1
0x180005aaf  movups  [rbp+57h+var_B0], xmm0
0x180005ab3  call    cs:__imp_DiscpAllocMemory
0x180005ab9  mov     r15, rax
0x180005abc  test    rax, rax
0x180005abf  jz      loc_180005CFE
0x180005ac5  xor     r9d, r9d
0x180005ac8  mov     [rsp+0E0h+var_C0], 0
0x180005ad1  xor     r8d, r8d
0x180005ad4  xor     edx, edx
0x180005ad6  xor     ecx, ecx
0x180005ad8  call    cs:__imp_DevObjCreateDeviceInfoList
0x180005ade  mov     r14, rax
0x180005ae1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180005ae5  jz      loc_180005CDD
0x180005aeb  mov     [rsp+0E0h+var_B8], 0
0x180005af4  lea     rdx, GUID_DEVINTERFACE_STORAGEPORT
0x180005afb  mov     r9d, 12h
0x180005b01  mov     [rsp+0E0h+var_C0], 0
0x180005b0a  xor     r8d, r8d
0x180005b0d  mov     rcx, rax
0x180005b10  call    cs:__imp_DevObjGetClassDevs
0x180005b16  test    eax, eax
0x180005b18  jz      loc_180005CCE
0x180005b1e  lea     rax, [rbp+57h+var_B0]
0x180005b22  xor     edi, edi
0x180005b24  mov     qword ptr [rbp+57h+var_B0+8], rax
0x180005b28  xor     esi, esi
0x180005b2a  lea     rax, [rbp+57h+var_B0]
0x180005b2e  mov     qword ptr [rbp+57h+var_B0], rax
0x180005b32  lea     rax, [rbp+57h+var_88]
0x180005b36  mov     dword ptr [rbp+57h+var_88], 20h ; ' '
0x180005b3d  mov     r9d, edi
0x180005b40  mov     [rsp+0E0h+var_C0], rax
0x180005b45  lea     r8, GUID_DEVINTERFACE_STORAGEPORT
0x180005b4c  xor     edx, edx
0x180005b4e  mov     rcx, r14
0x180005b51  call    cs:__imp_DevObjEnumDeviceInterfaces
0x180005b57  test    eax, eax
0x180005b59  jz      loc_180005C03
0x180005b5f  lea     rax, [rbp+57h+var_68]
0x180005b63  mov     dword ptr [rbp+57h+var_68], 30h ; '0'
0x180005b6a  mov     [rsp+0E0h+var_B8], rax
0x180005b6f  lea     rdx, [rbp+57h+var_88]
0x180005b73  lea     rax, [rbp+57h+var_A0]
0x180005b77  mov     dword ptr [r15], 8
0x180005b7e  mov     r9d, 1000h
0x180005b84  mov     [rsp+0E0h+var_C0], rax
0x180005b89  mov     r8, r15
0x180005b8c  mov     rcx, r14
0x180005b8f  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x180005b95  test    eax, eax
0x180005b97  jz      short loc_180005C03
0x180005b99  lea     r9, [rbp+57h+pszSrc]
0x180005b9d  xor     edx, edx
0x180005b9f  lea     r8, MSiSCSI_HBAInformation_GUID
0x180005ba6  lea     rcx, [r15+4]
0x180005baa  call    cs:__imp_DiscpPnpDeviceInterfaceToInstanceName
0x180005bb0  test    eax, eax
0x180005bb2  jnz     short loc_180005BFC
0x180005bb4  mov     rdx, [rbp+57h+pszSrc]; pszSrc
0x180005bb8  lea     r8, [rbp+57h+var_90]; __int64
0x180005bbc  lea     rcx, [r15+4]; STRSAFE_LPCWSTR
0x180005bc0  call    DiscpBuildInitiatorInstanceByPnpName
0x180005bc5  test    eax, eax
0x180005bc7  jnz     short loc_180005BF2
0x180005bc9  mov     rcx, qword ptr [rbp+57h+var_B0+8]
0x180005bcd  lea     rax, [rbp+57h+var_B0]
0x180005bd1  cmp     [rcx], rax
0x180005bd4  jnz     loc_180005C63
0x180005bda  mov     rax, [rbp+57h+var_90]
0x180005bde  lea     rdx, [rbp+57h+var_B0]
0x180005be2  inc     esi
0x180005be4  mov     [rax], rdx
0x180005be7  mov     [rax+8], rcx
0x180005beb  mov     [rcx], rax
0x180005bee  mov     qword ptr [rbp+57h+var_B0+8], rax
0x180005bf2  mov     rcx, [rbp+57h+pszSrc]
0x180005bf6  call    cs:__imp_DiscpFreeMemory
0x180005bfc  inc     edi
0x180005bfe  jmp     loc_180005B32
0x180005c03  call    cs:__imp_GetLastError
0x180005c09  inc     edi
0x180005c0b  test    eax, eax
0x180005c0d  jz      loc_180005B32
0x180005c13  xor     ebx, ebx
0x180005c15  mov     rcx, r14
0x180005c18  cmp     eax, 103h
0x180005c1d  cmovnz  ebx, eax
0x180005c20  call    cs:__imp_DevObjDestroyDeviceInfoList
0x180005c26  test    ebx, ebx
0x180005c28  jnz     short loc_180005C99
0x180005c2a  test    esi, esi
0x180005c2c  jz      loc_180005CF3
0x180005c32  lea     rcx, DiscpCritSection; CriticalSection
0x180005c39  call    cs:__imp_RtlEnterCriticalSection
0x180005c3f  mov     rax, qword ptr [rbp+57h+var_B0]
0x180005c43  lea     rcx, [rbp+57h+var_B0]
0x180005c47  cmp     rax, rcx
0x180005c4a  lea     rcx, DiscpInitiatorInstanceList
0x180005c51  jnz     short loc_180005C6A
0x180005c53  mov     cs:off_180027008, rcx
0x180005c5a  mov     cs:DiscpInitiatorInstanceList, rcx
0x180005c61  jmp     short loc_180005C84
0x180005c63  mov     ecx, 3
0x180005c68  int     29h; Win8: RtlFailFast(ecx)
0x180005c6a  movups  xmm0, [rbp+57h+var_B0]
0x180005c6e  movdqu  xmmword ptr cs:DiscpInitiatorInstanceList, xmm0
0x180005c76  mov     [rax+8], rcx
0x180005c7a  mov     rax, cs:off_180027008
0x180005c81  mov     [rax], rcx
0x180005c84  lea     rcx, DiscpCritSection; CriticalSection
0x180005c8b  mov     cs:DiscpInitiatorInstanceCount, esi
0x180005c91  call    cs:__imp_RtlLeaveCriticalSection
0x180005c97  jmp     short loc_180005CF3
0x180005c99  mov     rdi, qword ptr [rbp+57h+var_B0]
0x180005c9d  jmp     short loc_180005CC3
0x180005c9f  mov     rax, rdi
0x180005ca2  mov     rdx, rdi
0x180005ca5  mov     rcx, rdi
0x180005ca8  mov     rdi, [rdi]
0x180005cab  bts     dword ptr [rax+14h], 1Fh
0x180005cb0  or      eax, 0FFFFFFFFh
0x180005cb3  lock xadd [rdx+10h], eax
0x180005cb8  cmp     eax, 1
0x180005cbb  jnz     short loc_180005CC3
0x180005cbd  call    cs:__imp_DiscpFreeMemory
0x180005cc3  lea     rax, [rbp+57h+var_B0]
0x180005cc7  cmp     rdi, rax
0x180005cca  jnz     short loc_180005C9F
0x180005ccc  jmp     short loc_180005CF3
0x180005cce  call    cs:__imp_GetLastError
0x180005cd4  lea     rcx, aDevobjgetclass; "DevObjGetClassDevs -> %d\n"
0x180005cdb  jmp     short loc_180005CEA
0x180005cdd  call    cs:__imp_GetLastError
0x180005ce3  lea     rcx, Format; "DevObjCreateDeviceInfoList -> %d\n"
0x180005cea  mov     edx, eax
0x180005cec  mov     ebx, eax
0x180005cee  call    printf
0x180005cf3  mov     rcx, r15
0x180005cf6  call    cs:__imp_DiscpFreeMemory
0x180005cfc  jmp     short loc_180005D03
0x180005cfe  mov     ebx, 8
0x180005d03  mov     eax, ebx
0x180005d05  mov     rcx, [rbp+57h+var_38]
0x180005d09  xor     rcx, rsp; StackCookie
0x180005d0c  call    __security_check_cookie
0x180005d11  add     rsp, 0B0h
0x180005d18  pop     r15
0x180005d1a  pop     r14
0x180005d1c  pop     r12
0x180005d1e  pop     rdi
0x180005d1f  pop     rsi
0x180005d20  pop     rbx
0x180005d21  pop     rbp
0x180005d22  retn
```
