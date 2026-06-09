# CCertTypeInfo::_EnumFromDSCache(ulong,CCertTypeInfo * *)

- ea: `0x180031ddc`
- end: `0x180032116`
- name: `?_EnumFromDSCache@CCertTypeInfo@@KAJKPEAPEAV1@@Z`
- size: `826`
- prototype: `__int64 __fastcall(char, struct CCertTypeInfo **, __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000a630`
- `0x18000a920`

## callees

- `0x18000e500`
- `0x180010070`
- `0x180012260`
- `0x18001246c`
- `0x180014fac`
- `0x18002fa14`
- `0x18002fa3c`
- `0x180031ddc`
- `0x1800327c4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031f21`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031f21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800320df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800320df`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800320b0`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800320b0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180031f7e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180031f7e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180031f02`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180031f02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800320fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800320fc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180031eaa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003208d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180031eaa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003208d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800320d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800320d6`

## pseudocode

```c
__int64 __fastcall CCertTypeInfo::_EnumFromDSCache(
        char a1,
        struct CCertTypeInfo **a2,
        __int64 a3,
        unsigned __int16 *a4)
{
  DWORD v5; // esi
  int v7; // r14d
  _BOOL8 v8; // rdi
  signed int v9; // eax
  unsigned int ClientToken; // ebx
  bool v11; // cc
  WCHAR *v12; // r13
  LSTATUS v13; // eax
  CCertTypeInfo *v14; // rax
  CCertTypeInfo *v15; // rbx
  unsigned int v16; // edx
  bool v17; // cc
  unsigned int v18; // edx
  unsigned int lpData; // [rsp+20h] [rbp-59h]
  struct _SECURITY_ATTRIBUTES *lpcbMaxClassLen; // [rsp+30h] [rbp-49h]
  HKEY hKey; // [rsp+60h] [rbp-19h] BYREF
  DWORD cSubKeys; // [rsp+68h] [rbp-11h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp-9h] BYREF
  struct CCertTypeInfo *v24; // [rsp+78h] [rbp-1h] BYREF
  DWORD v25; // [rsp+80h] [rbp+7h] BYREF
  DWORD cchName; // [rsp+84h] [rbp+Bh] BYREF
  BYTE v27[8]; // [rsp+88h] [rbp+Fh] BYREF
  BYTE Data[8]; // [rsp+90h] [rbp+17h] BYREF
  CCertTypeInfo *v29; // [rsp+98h] [rbp+1Fh]
  DWORD cbMaxSubKeyLen; // [rsp+E8h] [rbp+6Fh] BYREF
  DWORD cbData; // [rsp+F0h] [rbp+77h] BYREF
  DWORD Type; // [rsp+F8h] [rbp+7Fh] BYREF

  v5 = 0;
  v24 = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  hKey = 0;
  v25 = 0;
  cbData = 0;
  Type = 0;
  *(_QWORD *)Data = 0;
  *(_QWORD *)v27 = 0;
  hObject = 0;
  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v7 = a1 & 0x20;
  v8 = v7 != 0;
  v9 = ctRegCreateKeyEx(
         (HKEY)(v8 - 0x7FFFFFFF),
         (const unsigned __int16 *)a2,
         a3,
         a4,
         lpData,
         0x20019u,
         lpcbMaxClassLen,
         &hKey,
         &v25);
  ClientToken = v9;
  v11 = v9 <= 0;
  if ( v9
    || (cbData = 8,
        v9 = RegQueryValueExW(hKey, L"Timestamp", 0, &Type, Data, &cbData),
        ClientToken = v9,
        v11 = v9 <= 0,
        v9) )
  {
LABEL_4:
    if ( !v11 )
      ClientToken = (unsigned __int16)v9 | 0x80070000;
    goto LABEL_42;
  }
  if ( Type == 3 )
  {
    v9 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    ClientToken = v9;
    v11 = v9 <= 0;
    if ( !v9 )
    {
      v12 = (WCHAR *)LocalAlloc(0, 2LL * ++cbMaxSubKeyLen);
      if ( v12 )
      {
        ClientToken = myRobustGetClientToken(&hObject);
        if ( !ClientToken )
        {
          while ( v5 < cSubKeys )
          {
            cchName = cbMaxSubKeyLen;
            v13 = RegEnumKeyExW(hKey, v5, v12, &cchName, 0, 0, 0, 0);
            ClientToken = v13;
            if ( v13 )
            {
              v17 = v13 < 0;
              goto LABEL_31;
            }
            v14 = (CCertTypeInfo *)operator new(0xC0u, (const struct std::nothrow_t *)&std::nothrow);
            v29 = v14;
            if ( v14 )
              v15 = CCertTypeInfo::CCertTypeInfo(v14, 1);
            else
              v15 = 0;
            if ( !v15 )
            {
              ClientToken = -2147024882;
              goto LABEL_38;
            }
            if ( (unsigned int)CCertTypeInfo::_LoadCachedCTFromReg(v15, v12, (HKEY)(v8 - 0x7FFFFFFF)) )
            {
              CCertTypeInfo::`scalar deleting destructor'(v15, v16);
            }
            else
            {
              if ( v7 )
                *((_DWORD *)v15 + 31) = 1;
              *((_DWORD *)v15 + 44) = 1;
              if ( !(unsigned int)CCertTypeInfo::AccessCheck(
                                    (PSECURITY_DESCRIPTOR *)v15,
                                    (AUTHZ_CLIENT_CONTEXT_HANDLE)hObject,
                                    1,
                                    0) )
                *((_DWORD *)v15 + 44) |= 2u;
              if ( !(unsigned int)CCertTypeInfo::AccessCheck(
                                    (PSECURITY_DESCRIPTOR *)v15,
                                    (AUTHZ_CLIENT_CONTEXT_HANDLE)hObject,
                                    2,
                                    0) )
                *((_DWORD *)v15 + 44) |= 4u;
              CCertTypeInfo::_Append(&v24, v15);
            }
            ++v5;
          }
          cbData = 8;
          v13 = RegQueryValueExW(hKey, L"TimestampAfter", 0, &Type, v27, &cbData);
          ClientToken = v13;
          v17 = v13 <= 0;
          if ( !v13 )
          {
            if ( Type != 3 || CompareFileTime((const FILETIME *)Data, (const FILETIME *)v27) )
            {
              ClientToken = -2147024883;
            }
            else
            {
              CCertTypeInfo::_Append(a2, v24);
              v24 = 0;
              ClientToken = 0;
            }
            goto LABEL_38;
          }
LABEL_31:
          if ( !v17 )
            ClientToken = (unsigned __int16)v13 | 0x80070000;
        }
LABEL_38:
        if ( hObject )
          CloseHandle(hObject);
        LocalFree(v12);
        if ( v24 )
          CCertTypeInfo::`scalar deleting destructor'(v24, v18);
      }
      else
      {
        ClientToken = -2147024882;
      }
      goto LABEL_42;
    }
    goto LABEL_4;
  }
  ClientToken = -2147024883;
LABEL_42:
  if ( hKey )
    RegCloseKey(hKey);
  return ClientToken;
}

```

## disassembly

```asm
0x180031ddc  push    rbp
0x180031dde  push    rbx
0x180031ddf  push    rsi
0x180031de0  push    rdi
0x180031de1  push    r13
0x180031de3  push    r14
0x180031de5  push    r15
0x180031de7  lea     rbp, [rsp-27h]
0x180031dec  sub     rsp, 0A0h
0x180031df3  mov     r15, rdx
0x180031df6  mov     r14d, ecx
0x180031df9  xor     esi, esi
0x180031dfb  mov     [rbp+57h+var_58], rsi
0x180031dff  mov     [rbp+57h+cSubKeys], esi
0x180031e02  mov     [rbp+57h+cbMaxSubKeyLen], esi
0x180031e05  mov     [rbp+57h+hKey], rsi
0x180031e09  mov     [rbp+57h+var_50], esi
0x180031e0c  mov     [rbp+57h+cbData], esi
0x180031e0f  mov     [rbp+57h+Type], esi
0x180031e12  mov     qword ptr [rbp+57h+Data], rsi
0x180031e16  mov     qword ptr [rbp+57h+var_48], rsi
0x180031e1a  mov     [rbp+57h+hObject], rsi
0x180031e1e  test    rdx, rdx
0x180031e21  jnz     short loc_180031E2D
0x180031e23  mov     eax, 80004003h
0x180031e28  jmp     loc_180032104
0x180031e2d  mov     [rdx], rsi
0x180031e30  and     r14d, 20h
0x180031e34  mov     eax, r14d
0x180031e37  neg     eax
0x180031e39  sbb     rdi, rdi
0x180031e3c  neg     rdi
0x180031e3f  lea     rax, [rbp+57h+var_50]
0x180031e43  mov     [rsp+0D0h+lpcbMaxValueNameLen], rax; LPDWORD
0x180031e48  lea     rax, [rbp+57h+hKey]
0x180031e4c  mov     [rsp+0D0h+lpcValues], rax; PHKEY
0x180031e51  mov     dword ptr [rsp+0D0h+lpcbData], 20019h; samDesired
0x180031e59  lea     rcx, [rdi-7FFFFFFFh]; HKEY
0x180031e60  call    ?ctRegCreateKeyEx@@YAJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; ctRegCreateKeyEx(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x180031e65  mov     ebx, eax
0x180031e67  test    eax, eax
0x180031e69  jz      short loc_180031E7F
0x180031e6b  jle     loc_1800320F3
0x180031e71  movzx   ebx, ax
0x180031e74  or      ebx, 80070000h
0x180031e7a  jmp     loc_1800320F3
0x180031e7f  mov     [rbp+57h+cbData], 8
0x180031e86  lea     rax, [rbp+57h+cbData]
0x180031e8a  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x180031e8f  lea     rax, [rbp+57h+Data]
0x180031e93  mov     [rsp+0D0h+lpData], rax; lpData
0x180031e98  lea     r9, [rbp+57h+Type]; lpType
0x180031e9c  xor     r8d, r8d; lpReserved
0x180031e9f  lea     rdx, aTimestamp; "Timestamp"
0x180031ea6  mov     rcx, [rbp+57h+hKey]; hKey
0x180031eaa  call    cs:__imp_RegQueryValueExW
0x180031eb0  mov     ebx, eax
0x180031eb2  test    eax, eax
0x180031eb4  jnz     short loc_180031E6B
0x180031eb6  cmp     [rbp+57h+Type], 3
0x180031eba  jz      short loc_180031EC6
0x180031ebc  mov     ebx, 8007000Dh
0x180031ec1  jmp     loc_1800320F3
0x180031ec6  mov     [rsp+0D0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x180031ecb  mov     [rsp+0D0h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x180031ed0  mov     [rsp+0D0h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x180031ed5  mov     [rsp+0D0h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x180031eda  mov     [rsp+0D0h+lpcValues], rsi; lpcValues
0x180031edf  mov     [rsp+0D0h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x180031ee4  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x180031ee8  mov     [rsp+0D0h+lpcbData], rax; lpcbMaxSubKeyLen
0x180031eed  lea     rax, [rbp+57h+cSubKeys]
0x180031ef1  mov     [rsp+0D0h+lpData], rax; lpcSubKeys
0x180031ef6  xor     r9d, r9d; lpReserved
0x180031ef9  xor     r8d, r8d; lpcchClass
0x180031efc  xor     edx, edx; lpClass
0x180031efe  mov     rcx, [rbp+57h+hKey]; hKey
0x180031f02  call    cs:__imp_RegQueryInfoKeyW
0x180031f08  mov     ebx, eax
0x180031f0a  test    eax, eax
0x180031f0c  jnz     loc_180031E6B
0x180031f12  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x180031f15  inc     eax
0x180031f17  mov     [rbp+57h+cbMaxSubKeyLen], eax
0x180031f1a  mov     edx, eax
0x180031f1c  add     rdx, rdx; uBytes
0x180031f1f  xor     ecx, ecx; uFlags
0x180031f21  call    cs:__imp_LocalAlloc
0x180031f27  mov     r13, rax
0x180031f2a  test    rax, rax
0x180031f2d  jnz     short loc_180031F39
0x180031f2f  mov     ebx, 8007000Eh
0x180031f34  jmp     loc_1800320F3
0x180031f39  lea     rcx, [rbp+57h+hObject]; void **
0x180031f3d  call    ?myRobustGetClientToken@@YAJPEAPEAX@Z; myRobustGetClientToken(void * *)
0x180031f42  mov     ebx, eax
0x180031f44  test    eax, eax
0x180031f46  jnz     loc_1800320CC
0x180031f4c  mov     rcx, [rbp+57h+hKey]; hKey
0x180031f50  cmp     esi, [rbp+57h+cSubKeys]
0x180031f53  jnb     loc_180032066
0x180031f59  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x180031f5c  mov     [rbp+57h+cchName], eax
0x180031f5f  xor     eax, eax
0x180031f61  mov     [rsp+0D0h+lpcValues], rax; lpftLastWriteTime
0x180031f66  mov     [rsp+0D0h+lpcbMaxClassLen], rax; lpcchClass
0x180031f6b  mov     [rsp+0D0h+lpcbData], rax; lpClass
0x180031f70  mov     [rsp+0D0h+lpData], rax; lpReserved
0x180031f75  lea     r9, [rbp+57h+cchName]; lpcchName
0x180031f79  mov     r8, r13; lpName
0x180031f7c  mov     edx, esi; dwIndex
0x180031f7e  call    cs:__imp_RegEnumKeyExW
0x180031f84  mov     ebx, eax
0x180031f86  test    eax, eax
0x180031f88  jnz     loc_180032055
0x180031f8e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180031f95  mov     ecx, 0C0h; unsigned __int64
0x180031f9a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180031f9f  mov     [rbp+57h+var_38], rax
0x180031fa3  test    rax, rax
0x180031fa6  jz      short loc_180031FB8
0x180031fa8  lea     edx, [rbx+1]; int
0x180031fab  mov     rcx, rax; this
0x180031fae  call    ??0CCertTypeInfo@@QEAA@H@Z; CCertTypeInfo::CCertTypeInfo(int)
0x180031fb3  mov     rbx, rax
0x180031fb6  jmp     short loc_180031FBA
0x180031fb8  xor     ebx, ebx
0x180031fba  test    rbx, rbx
0x180031fbd  jz      loc_18003204C
0x180031fc3  lea     r8, [rdi-7FFFFFFFh]; HKEY
0x180031fca  mov     rdx, r13; Src
0x180031fcd  mov     rcx, rbx; this
0x180031fd0  call    ?_LoadCachedCTFromReg@CCertTypeInfo@@IEAAJPEBGPEAUHKEY__@@@Z; CCertTypeInfo::_LoadCachedCTFromReg(ushort const *,HKEY__ *)
0x180031fd5  test    eax, eax
0x180031fd7  jnz     short loc_18003203D
0x180031fd9  test    r14d, r14d
0x180031fdc  jz      short loc_180031FE5
0x180031fde  mov     dword ptr [rbx+7Ch], 1
0x180031fe5  mov     dword ptr [rbx+0B0h], 1
0x180031fef  xor     r9d, r9d; int
0x180031ff2  mov     r8d, 10001h; unsigned int
0x180031ff8  mov     rdx, [rbp+57h+hObject]; void *
0x180031ffc  mov     rcx, rbx; this
0x180031fff  call    ?AccessCheck@CCertTypeInfo@@QEAAJPEAXKH@Z; CCertTypeInfo::AccessCheck(void *,ulong,int)
0x180032004  test    eax, eax
0x180032006  jnz     short loc_18003200F
0x180032008  or      dword ptr [rbx+0B0h], 2
0x18003200f  xor     r9d, r9d; int
0x180032012  mov     r8d, 10002h; unsigned int
0x180032018  mov     rdx, [rbp+57h+hObject]; void *
0x18003201c  mov     rcx, rbx; this
0x18003201f  call    ?AccessCheck@CCertTypeInfo@@QEAAJPEAXKH@Z; CCertTypeInfo::AccessCheck(void *,ulong,int)
0x180032024  test    eax, eax
0x180032026  jnz     short loc_18003202F
0x180032028  or      dword ptr [rbx+0B0h], 4
0x18003202f  mov     rdx, rbx; struct CCertTypeInfo *
0x180032032  lea     rcx, [rbp+57h+var_58]; struct CCertTypeInfo **
0x180032036  call    ?_Append@CCertTypeInfo@@SAPEAV1@PEAPEAV1@PEAV1@@Z; CCertTypeInfo::_Append(CCertTypeInfo * *,CCertTypeInfo *)
0x18003203b  jmp     short loc_180032045
0x18003203d  mov     rcx, rbx; this
0x180032040  call    ??_GCCertTypeInfo@@QEAAPEAXI@Z; CCertTypeInfo::`scalar deleting destructor'(uint)
0x180032045  inc     esi
0x180032047  jmp     loc_180031F4C
0x18003204c  mov     ebx, 8007000Eh
0x180032051  xor     esi, esi
0x180032053  jmp     short loc_1800320CC
0x180032055  xor     esi, esi
0x180032057  test    eax, eax
0x180032059  jle     short loc_1800320CC
0x18003205b  movzx   ebx, ax
0x18003205e  or      ebx, 80070000h
0x180032064  jmp     short loc_1800320CC
0x180032066  mov     [rbp+57h+cbData], 8
0x18003206d  lea     rax, [rbp+57h+cbData]
0x180032071  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x180032076  lea     rax, [rbp+57h+var_48]
0x18003207a  mov     [rsp+0D0h+lpData], rax; lpData
0x18003207f  lea     r9, [rbp+57h+Type]; lpType
0x180032083  xor     r8d, r8d; lpReserved
0x180032086  lea     rdx, aTimestampafter; "TimestampAfter"
0x18003208d  call    cs:__imp_RegQueryValueExW
0x180032093  mov     ebx, eax
0x180032095  xor     esi, esi
0x180032097  test    eax, eax
0x180032099  jnz     short loc_180032059
0x18003209b  cmp     [rbp+57h+Type], 3
0x18003209f  jz      short loc_1800320A8
0x1800320a1  mov     ebx, 8007000Dh
0x1800320a6  jmp     short loc_1800320CC
0x1800320a8  lea     rdx, [rbp+57h+var_48]; lpFileTime2
0x1800320ac  lea     rcx, [rbp+57h+Data]; lpFileTime1
0x1800320b0  call    cs:__imp_CompareFileTime
0x1800320b6  test    eax, eax
0x1800320b8  jnz     short loc_1800320A1
0x1800320ba  mov     rdx, [rbp+57h+var_58]; struct CCertTypeInfo *
0x1800320be  mov     rcx, r15; struct CCertTypeInfo **
0x1800320c1  call    ?_Append@CCertTypeInfo@@SAPEAV1@PEAPEAV1@PEAV1@@Z; CCertTypeInfo::_Append(CCertTypeInfo * *,CCertTypeInfo *)
0x1800320c6  mov     [rbp+57h+var_58], rsi
0x1800320ca  mov     ebx, esi
0x1800320cc  cmp     [rbp+57h+hObject], rsi
0x1800320d0  jz      short loc_1800320DC
0x1800320d2  mov     rcx, [rbp+57h+hObject]; hObject
0x1800320d6  call    cs:__imp_CloseHandle
0x1800320dc  mov     rcx, r13; hMem
0x1800320df  call    cs:__imp_LocalFree
0x1800320e5  mov     rcx, [rbp+57h+var_58]; this
0x1800320e9  test    rcx, rcx
0x1800320ec  jz      short loc_1800320F3
0x1800320ee  call    ??_GCCertTypeInfo@@QEAAPEAXI@Z; CCertTypeInfo::`scalar deleting destructor'(uint)
0x1800320f3  mov     rcx, [rbp+57h+hKey]; hKey
0x1800320f7  test    rcx, rcx
0x1800320fa  jz      short loc_180032102
0x1800320fc  call    cs:__imp_RegCloseKey
0x180032102  mov     eax, ebx
0x180032104  add     rsp, 0A0h
0x18003210b  pop     r15
0x18003210d  pop     r14
0x18003210f  pop     r13
0x180032111  pop     rdi
0x180032112  pop     rsi
0x180032113  pop     rbx
0x180032114  pop     rbp
0x180032115  retn
```
