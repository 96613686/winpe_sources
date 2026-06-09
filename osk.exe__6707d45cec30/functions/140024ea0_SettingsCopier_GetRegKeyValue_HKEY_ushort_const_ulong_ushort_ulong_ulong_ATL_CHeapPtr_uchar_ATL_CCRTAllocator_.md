# SettingsCopier::GetRegKeyValue(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong *,ATL::CHeapPtr<uchar,ATL::CCRTAllocator> &,ulong *)

- ea: `0x140024ea0`
- end: `0x14002517c`
- name: `?GetRegKeyValue@SettingsCopier@@CAJPEAUHKEY__@@PEBGKPEAGKPEAKAEAV?$CHeapPtr@EVCCRTAllocator@ATL@@@ATL@@3@Z`
- size: `732`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, DWORD cchValueName, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, registry_config`

## callers

- `0x14002491c`

## callees

- `0x14001c448`
- `0x140024ea0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140024f55`
- `ADVAPI32!RegOpenKeyExW` at `0x140024f55`
- `ADVAPI32!RegCloseKey` at `0x140024fad`
- `ADVAPI32!RegCloseKey` at `0x140025035`
- `ADVAPI32!RegCloseKey` at `0x14002508f`
- `ADVAPI32!RegCloseKey` at `0x1400250d2`
- `ADVAPI32!RegCloseKey` at `0x140024fad`
- `ADVAPI32!RegCloseKey` at `0x140025035`
- `ADVAPI32!RegCloseKey` at `0x14002508f`
- `ADVAPI32!RegCloseKey` at `0x1400250d2`
- `ADVAPI32!RegQueryValueExW` at `0x1400250c6`
- `ADVAPI32!RegQueryValueExW` at `0x1400250c6`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x140024f94`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x140024f94`
- `ADVAPI32!RegEnumValueW` at `0x140024fee`
- `ADVAPI32!RegEnumValueW` at `0x140025076`
- `ADVAPI32!RegEnumValueW` at `0x140024fee`
- `ADVAPI32!RegEnumValueW` at `0x140025076`
- `KERNEL32!WaitForSingleObject` at `0x1400250dd`
- `KERNEL32!WaitForSingleObject` at `0x1400250dd`
- `KERNEL32!GetLastError` at `0x140024f1f`
- `KERNEL32!GetLastError` at `0x140024f1f`
- `KERNEL32!CloseHandle` at `0x140024f64`
- `KERNEL32!CloseHandle` at `0x140024fa3`
- `KERNEL32!CloseHandle` at `0x14002502b`
- `KERNEL32!CloseHandle` at `0x140025085`
- `KERNEL32!CloseHandle` at `0x1400250e8`
- `KERNEL32!CloseHandle` at `0x140024f64`
- `KERNEL32!CloseHandle` at `0x140024fa3`
- `KERNEL32!CloseHandle` at `0x14002502b`
- `KERNEL32!CloseHandle` at `0x140025085`
- `KERNEL32!CloseHandle` at `0x1400250e8`
- `KERNEL32!CreateEventW` at `0x140024f11`
- `KERNEL32!CreateEventW` at `0x140024f11`
- `msvcrt!free` at `0x140024efe`
- `msvcrt!free` at `0x140025098`
- `msvcrt!free` at `0x140025105`
- `msvcrt!free` at `0x14002513c`
- `msvcrt!free` at `0x140024efe`
- `msvcrt!free` at `0x140025098`
- `msvcrt!free` at `0x140025105`
- `msvcrt!free` at `0x14002513c`

## string_xrefs

- `0x1400250bf`: `SymbolicLinkValue`

## pseudocode

```c
signed int __fastcall SettingsCopier::GetRegKeyValue(
        HKEY hKey,
        LPCWSTR lpSubKey,
        DWORD a3,
        WCHAR *a4,
        DWORD cchValueName,
        DWORD *a6,
        void **a7,
        DWORD *a8)
{
  DWORD *v8; // r12
  DWORD *v9; // r13
  void **v11; // rsi
  void *v14; // rcx
  HANDLE EventW; // r14
  signed int result; // eax
  LSTATUS v17; // ebx
  LSTATUS v18; // edi
  LSTATUS v19; // eax
  DWORD v20; // ebx
  BYTE *lpData; // [rsp+30h] [rbp-30h]
  DWORD Type; // [rsp+40h] [rbp-20h] BYREF
  DWORD v23; // [rsp+44h] [rbp-1Ch] BYREF
  DWORD v24; // [rsp+48h] [rbp-18h] BYREF
  HKEY hKeya; // [rsp+50h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+B8h] [rbp+58h] BYREF

  v8 = a6;
  v9 = a8;
  v11 = a7;
  *a4 = 0;
  *v8 = 0;
  *v9 = 0;
  v14 = *v11;
  hKeya = 0;
  cchValueName = 260;
  Type = 0;
  cbData = 0;
  v23 = 0;
  v24 = 0;
  free(v14);
  *v11 = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW )
  {
    v17 = RegOpenKeyExW(hKey, lpSubKey, 8u, 0x20019u, &hKeya);
    if ( v17 )
    {
      CloseHandle(EventW);
      goto LABEL_6;
    }
    v18 = 1;
    v17 = RegNotifyChangeKeyValue(hKeya, 0, 5u, EventW, 1);
    if ( v17 )
      goto LABEL_10;
    cchValueName = 260;
    v19 = RegEnumValueW(hKeya, a3, a4, &cchValueName, 0, &Type, 0, &cbData);
    v17 = v19;
    if ( v19 == 259 )
      goto LABEL_17;
    if ( v19 && v19 != 234 )
    {
LABEL_10:
      CloseHandle(EventW);
      RegCloseKey(hKeya);
      goto LABEL_6;
    }
    if ( cbData )
    {
      if ( !(unsigned __int8)ATL::CHeapPtr<unsigned char,ATL::CCRTAllocator>::Allocate(v11, cbData) )
      {
        v18 = -2147024882;
LABEL_17:
        CloseHandle(EventW);
        RegCloseKey(hKeya);
        return v18;
      }
      lpData = (BYTE *)*v11;
      cchValueName = 260;
      v17 = RegEnumValueW(hKeya, a3, a4, &cchValueName, 0, &Type, lpData, &cbData);
      if ( v17 )
      {
        CloseHandle(EventW);
        RegCloseKey(hKeya);
        free(*v11);
        *v11 = 0;
LABEL_6:
        if ( v17 > 0 )
          return (unsigned __int16)v17 | 0x80070000;
        return v17;
      }
    }
    v18 = RegQueryValueExW(hKeya, L"SymbolicLinkValue", 0, &v23, 0, &v24);
    RegCloseKey(hKeya);
    v20 = WaitForSingleObject(EventW, 0);
    CloseHandle(EventW);
    if ( !v20 )
    {
      v17 = -2147023590;
LABEL_29:
      free(*v11);
      *v11 = 0;
      *a4 = 0;
      return v17;
    }
    if ( v18 )
    {
      if ( v18 != 2 )
      {
        free(*v11);
        *v11 = 0;
        *a4 = 0;
        if ( v18 > 0 )
          return (unsigned __int16)v18 | 0x80070000;
        return v18;
      }
    }
    else if ( v23 == 6 )
    {
      v17 = -2147023432;
      goto LABEL_29;
    }
    *v8 = Type;
    *v9 = cbData;
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140024ea0  mov     [rsp-38h+arg_0], rbx
0x140024ea5  mov     [rsp-38h+dwIndex], r8d
0x140024eaa  push    rbp
0x140024eab  push    rsi
0x140024eac  push    rdi
0x140024ead  push    r12
0x140024eaf  push    r13
0x140024eb1  push    r14
0x140024eb3  push    r15
0x140024eb5  mov     rbp, rsp
0x140024eb8  sub     rsp, 60h
0x140024ebc  mov     r12, [rbp+arg_28]
0x140024ec0  xor     r14d, r14d
0x140024ec3  mov     r13, [rbp+arg_38]
0x140024ec7  mov     rdi, rcx
0x140024eca  mov     rsi, [rbp+arg_30]
0x140024ece  mov     r15, r9
0x140024ed1  mov     [r9], r14w
0x140024ed5  mov     rbx, rdx
0x140024ed8  mov     [r12], r14d
0x140024edc  mov     [r13+0], r14d
0x140024ee0  mov     rcx, [rsi]; Block
0x140024ee3  mov     [rbp+hKey], r14
0x140024ee7  mov     [rbp+cchValueName], 104h
0x140024eee  mov     [rbp+Type], r14d
0x140024ef2  mov     [rbp+cbData], r14d
0x140024ef6  mov     [rbp+var_1C], r14d
0x140024efa  mov     [rbp+var_18], r14d
0x140024efe  call    cs:__imp_free
0x140024f04  xor     r9d, r9d; lpName
0x140024f07  mov     [rsi], r14
0x140024f0a  xor     r8d, r8d; bInitialState
0x140024f0d  xor     edx, edx; bManualReset
0x140024f0f  xor     ecx, ecx; lpEventAttributes
0x140024f11  call    cs:__imp_CreateEventW
0x140024f17  mov     r14, rax
0x140024f1a  test    rax, rax
0x140024f1d  jnz     short loc_140024F3A
0x140024f1f  call    cs:__imp_GetLastError
0x140024f25  test    eax, eax
0x140024f27  jle     loc_140025164
0x140024f2d  movzx   eax, ax
0x140024f30  or      eax, 80070000h
0x140024f35  jmp     loc_140025164
0x140024f3a  lea     rax, [rbp+hKey]
0x140024f3e  mov     r9d, 20019h; samDesired
0x140024f44  mov     r8d, 8; ulOptions
0x140024f4a  mov     [rsp+60h+phkResult], rax; phkResult
0x140024f4f  mov     rdx, rbx; lpSubKey
0x140024f52  mov     rcx, rdi; hKey
0x140024f55  call    cs:__imp_RegOpenKeyExW
0x140024f5b  mov     ebx, eax
0x140024f5d  test    eax, eax
0x140024f5f  jz      short loc_140024F7E
0x140024f61  mov     rcx, r14; hObject
0x140024f64  call    cs:__imp_CloseHandle
0x140024f6a  test    ebx, ebx
0x140024f6c  jle     short loc_140024F77
0x140024f6e  movzx   ebx, bx
0x140024f71  or      ebx, 80070000h
0x140024f77  mov     eax, ebx
0x140024f79  jmp     loc_140025164
0x140024f7e  mov     rcx, [rbp+hKey]; hKey
0x140024f82  mov     edi, 1
0x140024f87  mov     r9, r14; hEvent
0x140024f8a  mov     dword ptr [rsp+60h+phkResult], edi; fAsynchronous
0x140024f8e  xor     edx, edx; bWatchSubtree
0x140024f90  lea     r8d, [rdi+4]; dwNotifyFilter
0x140024f94  call    cs:__imp_RegNotifyChangeKeyValue
0x140024f9a  mov     ebx, eax
0x140024f9c  test    eax, eax
0x140024f9e  jz      short loc_140024FB5
0x140024fa0  mov     rcx, r14; hObject
0x140024fa3  call    cs:__imp_CloseHandle
0x140024fa9  mov     rcx, [rbp+hKey]; hKey
0x140024fad  call    cs:__imp_RegCloseKey
0x140024fb3  jmp     short loc_140024F6A
0x140024fb5  mov     edx, [rbp+dwIndex]; dwIndex
0x140024fb8  lea     rax, [rbp+cbData]
0x140024fbc  mov     rcx, [rbp+hKey]; hKey
0x140024fc0  lea     r9, [rbp+cchValueName]; lpcchValueName
0x140024fc4  mov     [rsp+60h+lpcbData], rax; lpcbData
0x140024fc9  mov     r8, r15; lpValueName
0x140024fcc  lea     rax, [rbp+Type]
0x140024fd0  mov     [rsp+60h+lpData], 0; lpData
0x140024fd9  mov     [rsp+60h+lpType], rax; lpType
0x140024fde  mov     [rsp+60h+phkResult], 0; lpReserved
0x140024fe7  mov     [rbp+cchValueName], 104h
0x140024fee  call    cs:__imp_RegEnumValueW
0x140024ff4  mov     ebx, eax
0x140024ff6  cmp     eax, 103h
0x140024ffb  jz      short loc_140025028
0x140024ffd  xor     edi, edi
0x140024fff  test    eax, eax
0x140025001  jz      short loc_14002500A
0x140025003  cmp     eax, 0EAh
0x140025008  jnz     short loc_140024FA0
0x14002500a  mov     eax, [rbp+cbData]
0x14002500d  test    eax, eax
0x14002500f  jz      loc_1400250A6
0x140025015  mov     edx, eax
0x140025017  mov     rcx, rsi
0x14002501a  call    ?Allocate@?$CHeapPtr@EVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<uchar,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x14002501f  test    al, al
0x140025021  jnz     short loc_140025042
0x140025023  mov     edi, 8007000Eh
0x140025028  mov     rcx, r14; hObject
0x14002502b  call    cs:__imp_CloseHandle
0x140025031  mov     rcx, [rbp+hKey]; hKey
0x140025035  call    cs:__imp_RegCloseKey
0x14002503b  mov     eax, edi
0x14002503d  jmp     loc_140025164
0x140025042  mov     edx, [rbp+dwIndex]; dwIndex
0x140025045  lea     rax, [rbp+cbData]
0x140025049  mov     rcx, [rbp+hKey]; hKey
0x14002504d  lea     r9, [rbp+cchValueName]; lpcchValueName
0x140025051  mov     [rsp+60h+lpcbData], rax; lpcbData
0x140025056  mov     r8, r15; lpValueName
0x140025059  mov     rax, [rsi]
0x14002505c  mov     [rsp+60h+lpData], rax; lpData
0x140025061  lea     rax, [rbp+Type]
0x140025065  mov     [rsp+60h+lpType], rax; lpType
0x14002506a  mov     [rsp+60h+phkResult], rdi; lpReserved
0x14002506f  mov     [rbp+cchValueName], 104h
0x140025076  call    cs:__imp_RegEnumValueW
0x14002507c  mov     ebx, eax
0x14002507e  test    eax, eax
0x140025080  jz      short loc_1400250A6
0x140025082  mov     rcx, r14; hObject
0x140025085  call    cs:__imp_CloseHandle
0x14002508b  mov     rcx, [rbp+hKey]; hKey
0x14002508f  call    cs:__imp_RegCloseKey
0x140025095  mov     rcx, [rsi]; Block
0x140025098  call    cs:__imp_free
0x14002509e  mov     [rsi], rdi
0x1400250a1  jmp     loc_140024F6A
0x1400250a6  mov     rcx, [rbp+hKey]; hKey
0x1400250aa  lea     rax, [rbp+var_18]
0x1400250ae  mov     [rsp+60h+lpType], rax; lpcbData
0x1400250b3  lea     r9, [rbp+var_1C]; lpType
0x1400250b7  xor     r8d, r8d; lpReserved
0x1400250ba  mov     [rsp+60h+phkResult], rdi; lpData
0x1400250bf  lea     rdx, aSymboliclinkva; "SymbolicLinkValue"
0x1400250c6  call    cs:__imp_RegQueryValueExW
0x1400250cc  mov     rcx, [rbp+hKey]; hKey
0x1400250d0  mov     edi, eax
0x1400250d2  call    cs:__imp_RegCloseKey
0x1400250d8  xor     edx, edx; dwMilliseconds
0x1400250da  mov     rcx, r14; hHandle
0x1400250dd  call    cs:__imp_WaitForSingleObject
0x1400250e3  mov     rcx, r14; hObject
0x1400250e6  mov     ebx, eax
0x1400250e8  call    cs:__imp_CloseHandle
0x1400250ee  test    ebx, ebx
0x1400250f0  jnz     short loc_1400250F9
0x1400250f2  mov     ebx, 8007051Ah
0x1400250f7  jmp     short loc_140025139
0x1400250f9  test    edi, edi
0x1400250fb  jz      short loc_14002512E
0x1400250fd  cmp     edi, 2
0x140025100  jz      short loc_140025154
0x140025102  mov     rcx, [rsi]; Block
0x140025105  call    cs:__imp_free
0x14002510b  xor     eax, eax
0x14002510d  mov     qword ptr [rsi], 0
0x140025114  mov     [r15], ax
0x140025118  test    edi, edi
0x14002511a  jle     loc_14002503B
0x140025120  movzx   edi, di
0x140025123  or      edi, 80070000h
0x140025129  jmp     loc_14002503B
0x14002512e  cmp     [rbp+var_1C], 6
0x140025132  jnz     short loc_140025154
0x140025134  mov     ebx, 800705B8h
0x140025139  mov     rcx, [rsi]; Block
0x14002513c  call    cs:__imp_free
0x140025142  xor     ecx, ecx
0x140025144  mov     qword ptr [rsi], 0
0x14002514b  mov     [r15], cx
0x14002514f  jmp     loc_140024F77
0x140025154  mov     eax, [rbp+Type]
0x140025157  mov     [r12], eax
0x14002515b  mov     eax, [rbp+cbData]
0x14002515e  mov     [r13+0], eax
0x140025162  xor     eax, eax
0x140025164  mov     rbx, [rsp+60h+arg_0]
0x14002516c  add     rsp, 60h
0x140025170  pop     r15
0x140025172  pop     r14
0x140025174  pop     r13
0x140025176  pop     r12
0x140025178  pop     rdi
0x140025179  pop     rsi
0x14002517a  pop     rbp
0x14002517b  retn
```
