# PSetupSetSelectDevTitleAndInstructions

- ea: `0x180028040`
- end: `0x180028198`
- name: `PSetupSetSelectDevTitleAndInstructions`
- size: `344`
- prototype: `__int64 __fastcall(HDEVINFO DeviceInfoSet, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180002300`
- `0x180002f48`
- `0x180007944`
- `0x180028040`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800280df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800280df`
- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x180028172`
- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x180028172`
- `SETUPAPI!SetupDiGetClassInstallParamsW` at `0x180028111`
- `SETUPAPI!SetupDiGetClassInstallParamsW` at `0x180028111`

## pseudocode

```c
BOOL __fastcall PSetupSetSelectDevTitleAndInstructions(
        HDEVINFO DeviceInfoSet,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rax
  struct _SP_CLASSINSTALL_HEADER ClassInstallParams; // [rsp+30h] [rbp-508h] BYREF
  unsigned __int16 v13[60]; // [rsp+38h] [rbp-500h] BYREF
  unsigned __int16 v14[286]; // [rsp+B0h] [rbp-488h] BYREF
  unsigned __int16 v15[258]; // [rsp+2ECh] [rbp-24Ch] BYREF

  memset_0(v13, 0, 0x4B4u);
  v8 = -1;
  if ( a2 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a2[v9] );
    if ( (unsigned __int64)(v9 + 1) > 0x3C )
      goto LABEL_12;
  }
  if ( a3 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a3[v10] );
    if ( (unsigned __int64)(v10 + 1) > 0x100 )
      goto LABEL_12;
  }
  if ( a4 )
  {
    do
      ++v8;
    while ( a4[v8] );
    if ( (unsigned __int64)(v8 + 1) > 0x100 )
    {
LABEL_12:
      SetLastError(0x57u);
      return 0;
    }
  }
  ClassInstallParams.cbSize = 8;
  ClassInstallParams.InstallFunction = 1;
  if ( !SetupDiGetClassInstallParamsW(DeviceInfoSet, 0, &ClassInstallParams, 0x4BCu, 0) )
    return 0;
  if ( a2 )
    StringCchCopyW(v13, 0x3Cu, a2);
  if ( a3 )
    StringCchCopyW(v15, 0x100u, a3);
  if ( a4 )
    StringCchCopyW(v14, 0x100u, a4);
  return SetupDiSetClassInstallParamsW(DeviceInfoSet, 0, &ClassInstallParams, 0x4BCu);
}

```

## disassembly

```asm
0x180028040  push    rbx
0x180028042  push    rbp
0x180028043  push    rsi
0x180028044  push    rdi
0x180028045  push    r14
0x180028047  push    r15
0x180028049  sub     rsp, 508h
0x180028050  mov     rax, cs:__security_cookie
0x180028057  xor     rax, rsp
0x18002805a  mov     [rsp+538h+var_48], rax
0x180028062  mov     rdi, r8
0x180028065  mov     rsi, rdx
0x180028068  mov     rbp, rcx
0x18002806b  xor     edx, edx; Val
0x18002806d  mov     r8d, 4B4h; Size
0x180028073  lea     rcx, [rsp+538h+var_500]; void *
0x180028078  mov     rbx, r9
0x18002807b  call    memset_0
0x180028080  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180028084  xor     r14d, r14d
0x180028087  test    rsi, rsi
0x18002808a  jz      short loc_1800280A2
0x18002808c  mov     rax, rcx
0x18002808f  inc     rax
0x180028092  cmp     [rsi+rax*2], r14w
0x180028097  jnz     short loc_18002808F
0x180028099  inc     rax
0x18002809c  cmp     rax, 3Ch ; '<'
0x1800280a0  ja      short loc_1800280DA
0x1800280a2  mov     r15d, 100h
0x1800280a8  test    rdi, rdi
0x1800280ab  jz      short loc_1800280C2
0x1800280ad  mov     rax, rcx
0x1800280b0  inc     rax
0x1800280b3  cmp     [rdi+rax*2], r14w
0x1800280b8  jnz     short loc_1800280B0
0x1800280ba  inc     rax
0x1800280bd  cmp     rax, r15
0x1800280c0  ja      short loc_1800280DA
0x1800280c2  test    rbx, rbx
0x1800280c5  jz      short loc_1800280EC
0x1800280c7  inc     rcx
0x1800280ca  cmp     [rbx+rcx*2], r14w
0x1800280cf  jnz     short loc_1800280C7
0x1800280d1  lea     rax, [rcx+1]
0x1800280d5  cmp     rax, r15
0x1800280d8  jbe     short loc_1800280EC
0x1800280da  mov     ecx, 57h ; 'W'; dwErrCode
0x1800280df  call    cs:__imp_SetLastError
0x1800280e5  xor     eax, eax
0x1800280e7  jmp     loc_180028178
0x1800280ec  mov     r9d, 4BCh; ClassInstallParamsSize
0x1800280f2  mov     [rsp+538h+ClassInstallParams.cbSize], 8
0x1800280fa  lea     r8, [rsp+538h+ClassInstallParams]; ClassInstallParams
0x1800280ff  mov     [rsp+538h+ClassInstallParams.InstallFunction], 1
0x180028107  xor     edx, edx; DeviceInfoData
0x180028109  mov     [rsp+538h+RequiredSize], r14; RequiredSize
0x18002810e  mov     rcx, rbp; DeviceInfoSet
0x180028111  call    cs:__imp_SetupDiGetClassInstallParamsW
0x180028117  test    eax, eax
0x180028119  jz      short loc_1800280E5
0x18002811b  test    rsi, rsi
0x18002811e  jz      short loc_180028132
0x180028120  mov     r8, rsi; unsigned __int16 *
0x180028123  lea     rcx, [rsp+538h+var_500]; unsigned __int16 *
0x180028128  mov     edx, 3Ch ; '<'; unsigned __int64
0x18002812d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180028132  test    rdi, rdi
0x180028135  jz      short loc_18002814A
0x180028137  mov     r8, rdi; unsigned __int16 *
0x18002813a  lea     rcx, [rsp+538h+var_24C]; unsigned __int16 *
0x180028142  mov     rdx, r15; unsigned __int64
0x180028145  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002814a  test    rbx, rbx
0x18002814d  jz      short loc_180028162
0x18002814f  mov     r8, rbx; unsigned __int16 *
0x180028152  lea     rcx, [rsp+538h+var_488]; unsigned __int16 *
0x18002815a  mov     rdx, r15; unsigned __int64
0x18002815d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180028162  mov     r9d, 4BCh; ClassInstallParamsSize
0x180028168  lea     r8, [rsp+538h+ClassInstallParams]; ClassInstallParams
0x18002816d  xor     edx, edx; DeviceInfoData
0x18002816f  mov     rcx, rbp; DeviceInfoSet
0x180028172  call    cs:__imp_SetupDiSetClassInstallParamsW
0x180028178  mov     rcx, [rsp+538h+var_48]
0x180028180  xor     rcx, rsp; StackCookie
0x180028183  call    __security_check_cookie
0x180028188  add     rsp, 508h
0x18002818f  pop     r15
0x180028191  pop     r14
0x180028193  pop     rdi
0x180028194  pop     rsi
0x180028195  pop     rbp
0x180028196  pop     rbx
0x180028197  retn
```
