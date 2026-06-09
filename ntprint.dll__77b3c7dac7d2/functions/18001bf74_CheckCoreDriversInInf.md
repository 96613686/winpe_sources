# CheckCoreDriversInInf

- ea: `0x18001bf74`
- end: `0x18001c1ff`
- name: `CheckCoreDriversInInf`
- size: `651`
- prototype: `__int64 __fastcall(int, int, int, int, FILETIME FileTime1, __int64, __int64)`
- caller_count: `3`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18001b648`
- `0x18001d13c`
- `0x180023318`

## callees

- `0x180002300`
- `0x180002f48`
- `0x180012b28`
- `0x18001bf74`
- `0x180020330`
- `0x180026d10`
- `0x180026ed4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001c10d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001c10d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c1a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c1b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c1a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001c1b8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c025`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c042`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c025`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001c042`
- `KERNEL32!lstrcmpiW` at `0x18001c120`
- `KERNEL32!lstrcmpiW` at `0x18001c120`
- `SETUPAPI!SetupDiEnumDriverInfoW` at `0x18001c0c5`
- `SETUPAPI!SetupDiEnumDriverInfoW` at `0x18001c0c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c18f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c18f`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x18001c067`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x18001c067`

## pseudocode

```c
__int64 __fastcall CheckCoreDriversInInf(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4,
        FILETIME FileTime1,
        DWORDLONG a6,
        _DWORD *a7)
{
  _DWORD *v7; // rbx
  __int64 v11; // r12
  LPOLESTR *v13; // r14
  __int64 v14; // rdi
  HRESULT v15; // eax
  unsigned int v16; // ebx
  DWORD v17; // edi
  int v18; // r13d
  int v19; // eax
  __int64 v20; // rdi
  _DWORD *v21; // rax
  DWORDLONG v22; // r12
  __int64 v23; // rdi
  LPOLESTR v24; // rcx
  LONG v27; // [rsp+30h] [rbp-D0h]
  int v28; // [rsp+34h] [rbp-CCh]
  _DWORD *hMem; // [rsp+38h] [rbp-C8h]
  HDEVINFO DeviceInfoSet; // [rsp+40h] [rbp-C0h] BYREF
  int *v31; // [rsp+48h] [rbp-B8h]
  struct _SP_DRVINFO_DATA_V2_W DriverInfoData; // [rsp+50h] [rbp-B0h] BYREF

  v7 = a7;
  v31 = a7;
  v11 = -1;
  DeviceInfoSet = (HDEVINFO)-1LL;
  memset_0(&DriverInfoData.DriverType, 0, 0x61Cu);
  if ( (unsigned int)ValidPlatform(a2) && a1 && a3 && a4 && v7 )
  {
    *v7 = 0;
    DriverInfoData.cbSize = 1568;
    hMem = LocalAlloc(0x40u, 4 * a3);
    if ( hMem )
    {
      v13 = (LPOLESTR *)LocalAlloc(0x40u, 8 * a3);
      if ( v13 )
      {
        v14 = 0;
        while ( (unsigned int)v14 < a3 )
        {
          v15 = StringFromIID((const IID *const)(a4 + 16LL * (unsigned int)v14), &v13[v14]);
          v14 = (unsigned int)(v14 + 1);
          v16 = v15;
          if ( v15 < 0 )
            goto LABEL_30;
        }
        v17 = 0;
        v28 = 0;
        v18 = 0;
        v19 = CreateAndBuildDriverListFromInf(a2, a1, &DeviceInfoSet);
        v11 = (__int64)DeviceInfoSet;
        v16 = v19;
        if ( v19 >= 0 )
        {
LABEL_13:
          if ( !v18 && SetupDiEnumDriverInfoW((HDEVINFO)v11, 0, 1u, v17, &DriverInfoData) )
          {
            v18 = 1;
            v20 = 0;
            v21 = hMem;
            v22 = a6;
            while ( 1 )
            {
              if ( !v21[v20] )
              {
                if ( !(unsigned int)IsInboxCorePrinterDriver(v13[v20]) )
                  goto LABEL_25;
                v27 = CompareFileTime(&FileTime1, &DriverInfoData.DriverDate);
                if ( lstrcmpiW(v13[v20], DriverInfoData.Description)
                  || v27 != -1 && (v27 || v22 > DriverInfoData.DriverVersion) )
                {
                  v18 = 0;
LABEL_25:
                  v21 = hMem;
                  goto LABEL_26;
                }
                v21 = hMem;
                hMem[v20] = 1;
              }
LABEL_26:
              v20 = (unsigned int)(v20 + 1);
              if ( (unsigned int)v20 >= a3 )
              {
                v11 = (__int64)DeviceInfoSet;
                v17 = v28 + 1;
                DriverInfoData.cbSize = 1568;
                ++v28;
                goto LABEL_13;
              }
            }
          }
          *v31 = v18;
        }
LABEL_30:
        v23 = 0;
        do
        {
          v24 = v13[v23];
          if ( v24 )
          {
            CoTaskMemFree(v24);
            v13[v23] = 0;
          }
          v23 = (unsigned int)(v23 + 1);
        }
        while ( (unsigned int)v23 < a3 );
        LocalFree(v13);
      }
      else
      {
        v16 = -2147024882;
      }
      LocalFree(hMem);
      if ( v11 != -1 )
        DestroyOnlyPrinterDeviceInfoList(v11);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v16;
}

```

## disassembly

```asm
0x18001bf74  push    rbp
0x18001bf76  push    rbx
0x18001bf77  push    rsi
0x18001bf78  push    rdi
0x18001bf79  push    r12
0x18001bf7b  push    r13
0x18001bf7d  push    r14
0x18001bf7f  push    r15
0x18001bf81  lea     rbp, [rsp-588h]
0x18001bf89  sub     rsp, 688h
0x18001bf90  mov     rax, cs:__security_cookie
0x18001bf97  xor     rax, rsp
0x18001bf9a  mov     [rbp+5C0h+var_50], rax
0x18001bfa1  mov     rbx, [rbp+5C0h+arg_30]
0x18001bfa8  mov     esi, r8d
0x18001bfab  mov     edi, edx
0x18001bfad  mov     [rsp+6C0h+var_690], edx
0x18001bfb1  mov     r15, rcx
0x18001bfb4  mov     [rsp+6C0h+var_678], rbx
0x18001bfb9  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001bfbd  lea     rcx, [rsp+6C0h+var_670.DriverType]; void *
0x18001bfc2  xor     edx, edx; Val
0x18001bfc4  mov     [rsp+6C0h+DeviceInfoSet], r12
0x18001bfc9  mov     r8d, 61Ch; Size
0x18001bfcf  mov     r13, r9
0x18001bfd2  call    memset_0
0x18001bfd7  mov     ecx, edi
0x18001bfd9  call    ValidPlatform
0x18001bfde  test    eax, eax
0x18001bfe0  jz      loc_18001C1D5
0x18001bfe6  test    r15, r15
0x18001bfe9  jz      loc_18001C1D5
0x18001bfef  test    esi, esi
0x18001bff1  jz      loc_18001C1D5
0x18001bff7  test    r13, r13
0x18001bffa  jz      loc_18001C1D5
0x18001c000  test    rbx, rbx
0x18001c003  jz      loc_18001C1D5
0x18001c009  mov     dword ptr [rbx], 0
0x18001c00f  lea     edx, ds:0[rsi*4]; uBytes
0x18001c016  lea     ebx, [r12+41h]
0x18001c01b  mov     [rsp+6C0h+var_670.cbSize], 620h
0x18001c023  mov     ecx, ebx; uFlags
0x18001c025  call    cs:__imp_LocalAlloc
0x18001c02b  mov     [rsp+6C0h+hMem], rax
0x18001c030  test    rax, rax
0x18001c033  jz      loc_18001C1CE
0x18001c039  lea     edx, ds:0[rsi*8]; uBytes
0x18001c040  mov     ecx, ebx; uFlags
0x18001c042  call    cs:__imp_LocalAlloc
0x18001c048  mov     r14, rax
0x18001c04b  test    rax, rax
0x18001c04e  jz      loc_18001C1AE
0x18001c054  xor     edi, edi
0x18001c056  cmp     edi, esi
0x18001c058  jnb     short loc_18001C07A
0x18001c05a  mov     ecx, edi
0x18001c05c  lea     rdx, [r14+rdi*8]; lplpsz
0x18001c060  shl     rcx, 4
0x18001c064  add     rcx, r13; rclsid
0x18001c067  call    cs:__imp_StringFromIID
0x18001c06d  inc     edi
0x18001c06f  mov     ebx, eax
0x18001c071  test    eax, eax
0x18001c073  jns     short loc_18001C056
0x18001c075  jmp     loc_18001C180
0x18001c07a  mov     ecx, [rsp+6C0h+var_690]
0x18001c07e  lea     r8, [rsp+6C0h+DeviceInfoSet]
0x18001c083  xor     edi, edi
0x18001c085  mov     rdx, r15
0x18001c088  mov     [rsp+6C0h+var_68C], edi
0x18001c08c  xor     r13d, r13d
0x18001c08f  call    CreateAndBuildDriverListFromInf
0x18001c094  mov     r12, [rsp+6C0h+DeviceInfoSet]
0x18001c099  mov     ebx, eax
0x18001c09b  test    eax, eax
0x18001c09d  js      loc_18001C180
0x18001c0a3  test    r13d, r13d
0x18001c0a6  jnz     loc_18001C178
0x18001c0ac  mov     r9d, edi; MemberIndex
0x18001c0af  lea     rax, [rsp+6C0h+var_670]
0x18001c0b4  lea     edi, [r13+1]
0x18001c0b8  mov     [rsp+6C0h+DriverInfoData], rax; DriverInfoData
0x18001c0bd  mov     r8d, edi; DriverType
0x18001c0c0  xor     edx, edx; DeviceInfoData
0x18001c0c2  mov     rcx, r12; DeviceInfoSet
0x18001c0c5  call    cs:__imp_SetupDiEnumDriverInfoW
0x18001c0cb  test    eax, eax
0x18001c0cd  jz      loc_18001C178
0x18001c0d3  mov     r13d, edi
0x18001c0d6  xor     edi, edi
0x18001c0d8  test    esi, esi
0x18001c0da  jz      loc_18001C161
0x18001c0e0  mov     rax, [rsp+6C0h+hMem]
0x18001c0e5  mov     r12, [rbp+5C0h+arg_28]
0x18001c0ec  cmp     dword ptr [rax+rdi*4], 0
0x18001c0f0  jnz     short loc_18001C156
0x18001c0f2  mov     rcx, [r14+rdi*8]; lpString1
0x18001c0f6  call    IsInboxCorePrinterDriver
0x18001c0fb  test    eax, eax
0x18001c0fd  jz      short loc_18001C151
0x18001c0ff  lea     rdx, [rbp+5C0h+var_670.DriverDate]; lpFileTime2
0x18001c106  lea     rcx, [rbp+5C0h+FileTime1]; lpFileTime1
0x18001c10d  call    cs:__imp_CompareFileTime
0x18001c113  mov     rcx, [r14+rdi*8]; lpString1
0x18001c117  lea     rdx, [rsp+6C0h+var_670.Description]; lpString2
0x18001c11c  mov     [rsp+6C0h+var_690], eax
0x18001c120  call    cs:__imp_lstrcmpiW
0x18001c126  test    eax, eax
0x18001c128  jnz     short loc_18001C14E
0x18001c12a  mov     eax, [rsp+6C0h+var_690]
0x18001c12e  cmp     eax, 0FFFFFFFFh
0x18001c131  jz      short loc_18001C140
0x18001c133  test    eax, eax
0x18001c135  jnz     short loc_18001C14E
0x18001c137  cmp     r12, [rbp+5C0h+var_670.DriverVersion]
0x18001c13e  ja      short loc_18001C14E
0x18001c140  mov     rax, [rsp+6C0h+hMem]
0x18001c145  mov     dword ptr [rax+rdi*4], 1
0x18001c14c  jmp     short loc_18001C156
0x18001c14e  xor     r13d, r13d
0x18001c151  mov     rax, [rsp+6C0h+hMem]
0x18001c156  inc     edi
0x18001c158  cmp     edi, esi
0x18001c15a  jb      short loc_18001C0EC
0x18001c15c  mov     r12, [rsp+6C0h+DeviceInfoSet]
0x18001c161  mov     edi, [rsp+6C0h+var_68C]
0x18001c165  inc     edi
0x18001c167  mov     [rsp+6C0h+var_670.cbSize], 620h
0x18001c16f  mov     [rsp+6C0h+var_68C], edi
0x18001c173  jmp     loc_18001C0A3
0x18001c178  mov     rax, [rsp+6C0h+var_678]
0x18001c17d  mov     [rax], r13d
0x18001c180  xor     edi, edi
0x18001c182  test    esi, esi
0x18001c184  jz      short loc_18001C1A3
0x18001c186  mov     rcx, [r14+rdi*8]; pv
0x18001c18a  test    rcx, rcx
0x18001c18d  jz      short loc_18001C19D
0x18001c18f  call    cs:__imp_CoTaskMemFree
0x18001c195  mov     qword ptr [r14+rdi*8], 0
0x18001c19d  inc     edi
0x18001c19f  cmp     edi, esi
0x18001c1a1  jb      short loc_18001C186
0x18001c1a3  mov     rcx, r14; hMem
0x18001c1a6  call    cs:__imp_LocalFree
0x18001c1ac  jmp     short loc_18001C1B3
0x18001c1ae  mov     ebx, 8007000Eh
0x18001c1b3  mov     rcx, [rsp+6C0h+hMem]; hMem
0x18001c1b8  call    cs:__imp_LocalFree
0x18001c1be  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x18001c1c2  jz      short loc_18001C1DA
0x18001c1c4  mov     rcx, r12
0x18001c1c7  call    DestroyOnlyPrinterDeviceInfoList
0x18001c1cc  jmp     short loc_18001C1DA
0x18001c1ce  mov     ebx, 8007000Eh
0x18001c1d3  jmp     short loc_18001C1DA
0x18001c1d5  mov     ebx, 80070057h
0x18001c1da  mov     eax, ebx
0x18001c1dc  mov     rcx, [rbp+5C0h+var_50]
0x18001c1e3  xor     rcx, rsp; StackCookie
0x18001c1e6  call    __security_check_cookie
0x18001c1eb  add     rsp, 688h
0x18001c1f2  pop     r15
0x18001c1f4  pop     r14
0x18001c1f6  pop     r13
0x18001c1f8  pop     r12
0x18001c1fa  pop     rdi
0x18001c1fb  pop     rsi
0x18001c1fc  pop     rbx
0x18001c1fd  pop     rbp
0x18001c1fe  retn
```
