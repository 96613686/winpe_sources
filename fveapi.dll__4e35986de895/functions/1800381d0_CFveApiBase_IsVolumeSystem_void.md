# CFveApiBase::IsVolumeSystem(void)

- ea: `0x1800381d0`
- end: `0x180038481`
- name: `?IsVolumeSystem@CFveApiBase@@MEAAJXZ`
- size: `689`
- prototype: `__int64 __fastcall(CFveApiBase *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005410`
- `0x1800195cc`
- `0x1800381d0`
- `0x180038488`
- `0x18011efce`
- `0x18011f010`
- `0x180129010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180038341`
- `ntdll!RtlNtStatusToDosError` at `0x180038341`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003829a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003829a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180038315`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180038315`

## pseudocode

```c
__int64 __fastcall CFveApiBase::IsVolumeSystem(CFveApiBase *this)
{
  int v2; // esi
  int v3; // eax
  int LastHresultError; // ebx
  unsigned int v5; // eax
  signed int v6; // eax
  __int64 v8; // rax
  unsigned int v9; // [rsp+44h] [rbp-464h] BYREF
  int v10; // [rsp+48h] [rbp-460h]
  CFveApiBase *v11; // [rsp+50h] [rbp-458h]
  HANDLE hDevice; // [rsp+58h] [rbp-450h] BYREF
  DWORD BytesReturned[4]; // [rsp+60h] [rbp-448h] BYREF
  unsigned __int16 OutBuffer; // [rsp+70h] [rbp-438h] BYREF
  WCHAR String1[263]; // [rsp+72h] [rbp-436h] BYREF
  WCHAR String2[264]; // [rsp+280h] [rbp-228h] BYREF

  v11 = this;
  memset_0(&OutBuffer, 0, 0x20Au);
  BytesReturned[0] = 0;
  hDevice = (HANDLE)-1LL;
  v2 = 0;
  v10 = 0;
  v9 = 0;
  if ( !(*(unsigned __int8 (__fastcall **)(CFveApiBase *))(*(_QWORD *)this + 104LL))(this) )
  {
    LastHresultError = -2147024890;
    goto LABEL_25;
  }
  v3 = (*(__int64 (__fastcall **)(CFveApiBase *, HANDLE *))(*(_QWORD *)this + 216LL))(this, &hDevice);
  LastHresultError = v3;
  if ( v3 < 0 )
  {
    if ( v3 != -2147024891 )
      goto LABEL_25;
    if ( !*((_DWORD *)this + 250) )
      goto LABEL_25;
    LastHresultError = (*(__int64 (__fastcall **)(CFveApiBase *, _QWORD, HANDLE *))(*(_QWORD *)this + 208LL))(
                         this,
                         0,
                         &hDevice);
    if ( LastHresultError < 0 )
      goto LABEL_25;
    v2 = 1;
    v10 = 1;
  }
  if ( !DeviceIoControl(hDevice, 0x4D0008u, 0, 0, &OutBuffer, 0x208u, BytesReturned, 0) )
  {
    LastHresultError = GetLastHresultError();
    goto LABEL_25;
  }
  v5 = OutBuffer >> 1;
  if ( v5 > 0x104 )
  {
    LastHresultError = -2147467259;
    goto LABEL_25;
  }
  String1[v5] = 0;
  LastHresultError = GetSystemPartition(0x104u, String2);
  if ( LastHresultError >= 0 )
  {
    if ( ((*(unsigned __int8 (__fastcall **)(CFveApiBase *))(*(_QWORD *)this + 72LL))(this)
       || CompareStringOrdinal(String1, -1, String2, -1, 1) == 2)
      && ((int)ReadReg32Bit(L"Software\\Policies\\Microsoft\\FVE", L"AllowSystemVolumeEncryption", 0, &v9) < 0
       || v9 - 1 > 1) )
    {
      LastHresultError = -2144272366;
      goto LABEL_25;
    }
LABEL_8:
    LastHresultError = 0;
    goto LABEL_25;
  }
  v6 = RtlNtStatusToDosError(-1073740718);
  if ( v6 > 0 )
    v6 = (unsigned __int16)v6 | 0x80070000;
  if ( LastHresultError == v6
    && (int)ReadReg32Bit(L"Software\\Policies\\Microsoft\\FVE", L"AllowSystemVolumeEncryption", 0, &v9) >= 0
    && v9 - 1 <= 1 )
  {
    goto LABEL_8;
  }
LABEL_25:
  if ( hDevice != (HANDLE)-1LL )
  {
    v8 = *(_QWORD *)this;
    if ( v2 )
      (*(void (__fastcall **)(CFveApiBase *))(v8 + 224))(this);
    else
      (*(void (__fastcall **)(CFveApiBase *))(v8 + 232))(this);
  }
  return (unsigned int)LastHresultError;
}

```

## disassembly

```asm
0x1800381d0  mov     [rsp+arg_8], rbx
0x1800381d5  mov     [rsp+arg_10], rsi
0x1800381da  push    rdi
0x1800381db  sub     rsp, 4A0h
0x1800381e2  mov     rax, cs:__security_cookie
0x1800381e9  xor     rax, rsp
0x1800381ec  mov     [rsp+4A8h+var_18], rax
0x1800381f4  mov     rdi, rcx
0x1800381f7  mov     [rsp+4A8h+var_458], rcx
0x1800381fc  xor     edx, edx; Val
0x1800381fe  mov     r8d, 20Ah; Size
0x180038204  lea     rcx, [rsp+4A8h+OutBuffer]; void *
0x180038209  call    memset_0
0x18003820e  mov     [rsp+4A8h+BytesReturned], 0
0x180038216  mov     [rsp+4A8h+hDevice], 0FFFFFFFFFFFFFFFFh
0x18003821f  xor     esi, esi
0x180038221  mov     [rsp+4A8h+var_460], esi
0x180038225  mov     [rsp+4A8h+var_464], esi
0x180038229  mov     rax, [rdi]
0x18003822c  mov     rcx, rdi
0x18003822f  mov     rax, [rax+68h]
0x180038233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038238  test    al, al
0x18003823a  jz      loc_180038335
0x180038240  mov     rax, [rdi]
0x180038243  lea     rdx, [rsp+4A8h+hDevice]
0x180038248  mov     rcx, rdi
0x18003824b  mov     rax, [rax+0D8h]
0x180038252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038257  mov     ebx, eax
0x180038259  mov     [rsp+4A8h+var_468], eax
0x18003825d  test    eax, eax
0x18003825f  js      loc_180038395
0x180038265  mov     [rsp+4A8h+lpOverlapped], 0; lpOverlapped
0x18003826e  lea     rax, [rsp+4A8h+BytesReturned]
0x180038273  mov     [rsp+4A8h+lpBytesReturned], rax; lpBytesReturned
0x180038278  mov     [rsp+4A8h+nOutBufferSize], 208h; nOutBufferSize
0x180038280  lea     rax, [rsp+4A8h+OutBuffer]
0x180038285  mov     [rsp+4A8h+lpOutBuffer], rax; lpOutBuffer
0x18003828a  xor     r9d, r9d; nInBufferSize
0x18003828d  xor     r8d, r8d; lpInBuffer
0x180038290  mov     edx, 4D0008h; dwIoControlCode
0x180038295  mov     rcx, [rsp+4A8h+hDevice]; hDevice
0x18003829a  call    cs:__imp_DeviceIoControl
0x1800382a1  nop     dword ptr [rax+rax+00h]
0x1800382a6  test    eax, eax
0x1800382a8  jz      loc_1800383DE
0x1800382ae  movzx   eax, [rsp+4A8h+OutBuffer]
0x1800382b3  shr     eax, 1
0x1800382b5  mov     ecx, 104h; unsigned int
0x1800382ba  cmp     eax, ecx
0x1800382bc  ja      loc_1800383EB
0x1800382c2  mov     edx, eax
0x1800382c4  xor     eax, eax
0x1800382c6  mov     [rsp+rdx*2+4A8h+String1], ax
0x1800382cb  lea     rdx, [rsp+4A8h+String2]; unsigned __int16 *
0x1800382d3  call    ?GetSystemPartition@@YAJKPEAG@Z; GetSystemPartition(ulong,ushort *)
0x1800382d8  mov     ebx, eax
0x1800382da  mov     [rsp+4A8h+var_468], eax
0x1800382de  test    eax, eax
0x1800382e0  js      short loc_18003833C
0x1800382e2  mov     rax, [rdi]
0x1800382e5  mov     rcx, rdi
0x1800382e8  mov     rax, [rax+48h]
0x1800382ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800382f1  test    al, al
0x1800382f3  jnz     loc_1800383F5
0x1800382f9  mov     dword ptr [rsp+4A8h+lpOutBuffer], 1; bIgnoreCase
0x180038301  or      r9d, 0FFFFFFFFh; cchCount2
0x180038305  lea     r8, [rsp+4A8h+String2]; lpString2
0x18003830d  or      edx, r9d; cchCount1
0x180038310  lea     rcx, [rsp+4A8h+String1]; lpString1
0x180038315  call    cs:__imp_CompareStringOrdinal
0x18003831c  nop     dword ptr [rax+rax+00h]
0x180038321  cmp     eax, 2
0x180038324  jz      loc_1800383F5
0x18003832a  xor     ebx, ebx
0x18003832c  mov     [rsp+4A8h+var_468], ebx
0x180038330  jmp     loc_18003842D
0x180038335  mov     ebx, 80070006h
0x18003833a  jmp     short loc_18003832C
0x18003833c  mov     ecx, 0C0000452h; Status
0x180038341  call    cs:__imp_RtlNtStatusToDosError
0x180038348  nop     dword ptr [rax+rax+00h]
0x18003834d  test    eax, eax
0x18003834f  jle     short loc_180038359
0x180038351  movzx   eax, ax
0x180038354  or      eax, 80070000h
0x180038359  cmp     ebx, eax
0x18003835b  jnz     loc_18003842D
0x180038361  lea     r9, [rsp+4A8h+var_464]; unsigned int *
0x180038366  xor     r8d, r8d; unsigned int
0x180038369  lea     rdx, aAllowsystemvol; "AllowSystemVolumeEncryption"
0x180038370  lea     rcx, aSoftwarePolici; "Software\\Policies\\Microsoft\\FVE"
0x180038377  call    ?ReadReg32Bit@@YAJPEBG0KPEAK@Z; ReadReg32Bit(ushort const *,ushort const *,ulong,ulong *)
0x18003837c  test    eax, eax
0x18003837e  js      loc_18003842D
0x180038384  mov     eax, [rsp+4A8h+var_464]
0x180038388  dec     eax
0x18003838a  cmp     eax, 1
0x18003838d  ja      loc_18003842D
0x180038393  jmp     short loc_18003832A
0x180038395  cmp     eax, 80070005h
0x18003839a  jnz     loc_18003842D
0x1800383a0  cmp     dword ptr [rdi+3E8h], 0
0x1800383a7  jz      loc_18003842D
0x1800383ad  mov     rax, [rdi]
0x1800383b0  lea     r8, [rsp+4A8h+hDevice]
0x1800383b5  xor     edx, edx
0x1800383b7  mov     rcx, rdi
0x1800383ba  mov     rax, [rax+0D0h]
0x1800383c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800383c6  mov     ebx, eax
0x1800383c8  mov     [rsp+4A8h+var_468], eax
0x1800383cc  test    eax, eax
0x1800383ce  js      short loc_18003842D
0x1800383d0  mov     esi, 1
0x1800383d5  mov     [rsp+4A8h+var_460], esi
0x1800383d9  jmp     loc_180038265
0x1800383de  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x1800383e3  mov     ebx, eax
0x1800383e5  mov     [rsp+4A8h+var_468], eax
0x1800383e9  jmp     short loc_18003842D
0x1800383eb  mov     ebx, 80004005h
0x1800383f0  jmp     loc_18003832C
0x1800383f5  lea     r9, [rsp+4A8h+var_464]; unsigned int *
0x1800383fa  xor     r8d, r8d; unsigned int
0x1800383fd  lea     rdx, aAllowsystemvol; "AllowSystemVolumeEncryption"
0x180038404  lea     rcx, aSoftwarePolici; "Software\\Policies\\Microsoft\\FVE"
0x18003840b  call    ?ReadReg32Bit@@YAJPEBG0KPEAK@Z; ReadReg32Bit(ushort const *,ushort const *,ulong,ulong *)
0x180038410  test    eax, eax
0x180038412  js      short loc_180038423
0x180038414  mov     eax, [rsp+4A8h+var_464]
0x180038418  dec     eax
0x18003841a  cmp     eax, 1
0x18003841d  jbe     loc_18003832A
0x180038423  mov     ebx, 80310012h
0x180038428  jmp     loc_18003832C
0x18003842d  mov     rdx, [rsp+4A8h+hDevice]
0x180038432  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180038436  jnz     short loc_180038460
0x180038438  mov     eax, ebx
0x18003843a  mov     rcx, [rsp+4A8h+var_18]
0x180038442  xor     rcx, rsp; StackCookie
0x180038445  call    __security_check_cookie
0x18003844a  lea     r11, [rsp+4A8h+var_8]
0x180038452  mov     rbx, [r11+18h]
0x180038456  mov     rsi, [r11+20h]
0x18003845a  mov     rsp, r11
0x18003845d  pop     rdi
0x18003845e  retn
0x180038460  mov     rax, [rdi]
0x180038463  mov     rcx, rdi
0x180038466  test    esi, esi
0x180038468  jnz     short loc_180038478
0x18003846a  mov     rax, [rax+0E8h]
0x180038471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038476  jmp     short loc_180038438
0x180038478  mov     rax, [rax+0E0h]
0x18003847f  jmp     short loc_180038471
0x1801204be  push    rbp
0x1801204c0  sub     rsp, 40h
0x1801204c4  mov     rbp, rdx
0x1801204c7  mov     rdx, [rbp+58h]
0x1801204cb  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x1801204cf  jz      short loc_1801204F4
0x1801204d1  mov     rcx, [rbp+50h]
0x1801204d5  mov     rax, [rcx]
0x1801204d8  cmp     dword ptr [rbp+48h], 0
0x1801204dc  jz      short loc_1801204E7
0x1801204de  mov     rax, [rax+0E0h]
0x1801204e5  jmp     short loc_1801204EE
0x1801204e7  mov     rax, [rax+0E8h]
0x1801204ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801204f3  nop
0x1801204f4  add     rsp, 40h
0x1801204f8  pop     rbp
0x1801204f9  retn
```
