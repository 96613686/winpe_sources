# CheckCommonDriversInInf(ushort const *,PLATFORM,ulong,ushort * *,int *)

- ea: `0x180009a10`
- end: `0x180009b76`
- name: `?CheckCommonDriversInInf@@YAJPEBGW4PLATFORM@@KPEAPEAGPEAH@Z`
- size: `358`
- prototype: `int __high(const unsigned __int16 *, enum PLATFORM, unsigned int, unsigned __int16 **, int *)`
- caller_count: `3`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800093a4`
- `0x180009724`
- `0x18000cc8c`

## callees

- `0x180002300`
- `0x180002f48`
- `0x180009a10`
- `0x18000b11c`
- `0x180012b28`
- `0x180026d10`
- `0x180026ed4`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180009afb`
- `KERNEL32!lstrcmpiW` at `0x180009afb`
- `SETUPAPI!SetupDiEnumDriverInfoW` at `0x180009adc`
- `SETUPAPI!SetupDiEnumDriverInfoW` at `0x180009adc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009b09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009b09`

## pseudocode

```c
__int64 __fastcall CheckCommonDriversInInf(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned __int16 **a4,
        _DWORD *a5)
{
  DWORD v9; // r13d
  int v10; // edi
  __int64 v11; // rbx
  const WCHAR *v12; // rcx
  HDEVINFO DeviceInfoSet[2]; // [rsp+30h] [rbp-678h] BYREF
  struct _SP_DRVINFO_DATA_V2_W DriverInfoData; // [rsp+40h] [rbp-668h] BYREF

  DeviceInfoSet[0] = (HDEVINFO)-1LL;
  memset_0(&DriverInfoData.DriverType, 0, 0x61Cu);
  if ( a1 && (unsigned int)ValidPlatform(a2) && a3 && a4 && a5 && !*a5 )
  {
    DriverInfoData.cbSize = 1568;
    v9 = 0;
    v10 = CreateAndBuildDriverListFromInf(a2, a1, DeviceInfoSet);
    if ( v10 >= 0 )
    {
      while ( !*a5 && SetupDiEnumDriverInfoW(DeviceInfoSet[0], 0, 1u, v9, &DriverInfoData) )
      {
        v11 = 0;
        do
        {
          v12 = a4[v11];
          if ( v12 )
          {
            if ( !lstrcmpiW(v12, DriverInfoData.Description) )
            {
              CoTaskMemFree(a4[v11]);
              a4[v11] = 0;
            }
          }
          v11 = (unsigned int)(v11 + 1);
        }
        while ( (unsigned int)v11 < a3 );
        *a5 = FoundAllCommonDrivers(a3, a4);
        ++v9;
        DriverInfoData.cbSize = 1568;
      }
    }
    if ( DeviceInfoSet[0] != (HDEVINFO)-1LL )
      DestroyOnlyPrinterDeviceInfoList(DeviceInfoSet[0]);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180009a10  push    rbx
0x180009a12  push    rsi
0x180009a13  push    rdi
0x180009a14  push    r12
0x180009a16  push    r13
0x180009a18  push    r14
0x180009a1a  push    r15
0x180009a1c  sub     rsp, 670h
0x180009a23  mov     rax, cs:__security_cookie
0x180009a2a  xor     rax, rsp
0x180009a2d  mov     [rsp+6A8h+var_48], rax
0x180009a35  mov     rsi, [rsp+6A8h+arg_20]
0x180009a3d  mov     r12d, r8d
0x180009a40  mov     ebx, edx
0x180009a42  mov     [rsp+6A8h+DeviceInfoSet], 0FFFFFFFFFFFFFFFFh
0x180009a4b  mov     rdi, rcx
0x180009a4e  xor     edx, edx; Val
0x180009a50  mov     r8d, 61Ch; Size
0x180009a56  lea     rcx, [rsp+6A8h+var_668.DriverType]; void *
0x180009a5b  mov     r14, r9
0x180009a5e  call    memset_0
0x180009a63  test    rdi, rdi
0x180009a66  jz      loc_180009B4C
0x180009a6c  mov     ecx, ebx
0x180009a6e  call    ValidPlatform
0x180009a73  test    eax, eax
0x180009a75  jz      loc_180009B4C
0x180009a7b  test    r12d, r12d
0x180009a7e  jz      loc_180009B4C
0x180009a84  test    r14, r14
0x180009a87  jz      loc_180009B4C
0x180009a8d  test    rsi, rsi
0x180009a90  jz      loc_180009B4C
0x180009a96  cmp     dword ptr [rsi], 0
0x180009a99  jnz     loc_180009B4C
0x180009a9f  lea     r8, [rsp+6A8h+DeviceInfoSet]
0x180009aa4  mov     [rsp+6A8h+var_668.cbSize], 620h
0x180009aac  mov     rdx, rdi
0x180009aaf  mov     ecx, ebx
0x180009ab1  xor     r13d, r13d
0x180009ab4  call    CreateAndBuildDriverListFromInf
0x180009ab9  mov     edi, eax
0x180009abb  test    eax, eax
0x180009abd  js      short loc_180009B38
0x180009abf  cmp     dword ptr [rsi], 0
0x180009ac2  jnz     short loc_180009B38
0x180009ac4  mov     rcx, [rsp+6A8h+DeviceInfoSet]; DeviceInfoSet
0x180009ac9  lea     rax, [rsp+6A8h+var_668]
0x180009ace  xor     edx, edx; DeviceInfoData
0x180009ad0  mov     [rsp+6A8h+DriverInfoData], rax; DriverInfoData
0x180009ad5  mov     r9d, r13d; MemberIndex
0x180009ad8  lea     r8d, [rdx+1]; DriverType
0x180009adc  call    cs:__imp_SetupDiEnumDriverInfoW
0x180009ae2  test    eax, eax
0x180009ae4  jz      short loc_180009B38
0x180009ae6  xor     ebx, ebx
0x180009ae8  test    r12d, r12d
0x180009aeb  jz      short loc_180009B1E
0x180009aed  mov     rcx, [r14+rbx*8]; lpString1
0x180009af1  test    rcx, rcx
0x180009af4  jz      short loc_180009B17
0x180009af6  lea     rdx, [rsp+6A8h+var_668.Description]; lpString2
0x180009afb  call    cs:__imp_lstrcmpiW
0x180009b01  test    eax, eax
0x180009b03  jnz     short loc_180009B17
0x180009b05  mov     rcx, [r14+rbx*8]; pv
0x180009b09  call    cs:__imp_CoTaskMemFree
0x180009b0f  mov     qword ptr [r14+rbx*8], 0
0x180009b17  inc     ebx
0x180009b19  cmp     ebx, r12d
0x180009b1c  jb      short loc_180009AED
0x180009b1e  mov     rdx, r14; unsigned __int16 **
0x180009b21  mov     ecx, r12d; unsigned int
0x180009b24  call    ?FoundAllCommonDrivers@@YAHKPEAPEAG@Z; FoundAllCommonDrivers(ulong,ushort * *)
0x180009b29  mov     [rsi], eax
0x180009b2b  inc     r13d
0x180009b2e  mov     [rsp+6A8h+var_668.cbSize], 620h
0x180009b36  jmp     short loc_180009ABF
0x180009b38  cmp     [rsp+6A8h+DeviceInfoSet], 0FFFFFFFFFFFFFFFFh
0x180009b3e  jz      short loc_180009B51
0x180009b40  mov     rcx, [rsp+6A8h+DeviceInfoSet]
0x180009b45  call    DestroyOnlyPrinterDeviceInfoList
0x180009b4a  jmp     short loc_180009B51
0x180009b4c  mov     edi, 80070057h
0x180009b51  mov     eax, edi
0x180009b53  mov     rcx, [rsp+6A8h+var_48]
0x180009b5b  xor     rcx, rsp; StackCookie
0x180009b5e  call    __security_check_cookie
0x180009b63  add     rsp, 670h
0x180009b6a  pop     r15
0x180009b6c  pop     r14
0x180009b6e  pop     r13
0x180009b70  pop     r12
0x180009b72  pop     rdi
0x180009b73  pop     rsi
0x180009b74  pop     rbx
0x180009b75  retn
```
