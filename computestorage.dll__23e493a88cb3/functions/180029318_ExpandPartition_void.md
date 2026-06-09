# ExpandPartition(void *)

- ea: `0x180029318`
- end: `0x1800296cb`
- name: `?ExpandPartition@@YA_JPEAX@Z`
- size: `947`
- prototype: `__int64 __fastcall(HANDLE hDevice)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800296d4`

## callees

- `0x180002690`
- `0x1800032b8`
- `0x180012818`
- `0x1800136f8`
- `0x18002375c`
- `0x180028acc`
- `0x180029318`
- `0x18002a4cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800293af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800293af`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002939b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180029408`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800294e6`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002960a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002939b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180029408`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800294e6`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002960a`

## string_xrefs

- `0x180029638`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x180029657`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x18002966f`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x180029688`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x18002969a`: `onecore\vm\compute\shared\storage\diskutilities.cpp`
- `0x1800296b9`: `onecore\vm\compute\shared\storage\diskutilities.cpp`

## pseudocode

```c
__int64 __fastcall ExpandPartition(HANDLE hDevice)
{
  DWORD LastError; // eax
  const char *v3; // r9
  const char *v4; // r9
  __int64 v5; // rbx
  char *v7; // rbx
  const char *v8; // r9
  _BYTE *v9; // rcx
  int v10; // edx
  __int64 v11; // r9
  __int64 v12; // r8
  _BYTE *v13; // rdx
  __int64 v14; // rax
  __int64 v15; // r8
  __int64 v16; // rax
  __int64 v17; // rdi
  __int64 v18; // rdi
  const char *v19; // r9
  unsigned int lpOutBuffer; // [rsp+20h] [rbp-E0h]
  void *v21[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v22; // [rsp+50h] [rbp-B0h]
  DWORD BytesReturned; // [rsp+58h] [rbp-A8h] BYREF
  DWORD lpBytesReturned; // [rsp+5Ch] [rbp-A4h] BYREF
  _QWORD InBuffer[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE OutBuffer[336]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  BytesReturned = 0;
  *(_OWORD *)v21 = 0;
  v22 = 0;
  memset_0(OutBuffer, 0, sizeof(OutBuffer));
  if ( !DeviceIoControl(hDevice, 0x70050u, 0, 0, OutBuffer, 0x150u, &BytesReturned, 0) )
  {
    LastError = GetLastError();
    if ( LastError == 1 )
    {
      InBuffer[0] = 0;
      lpBytesReturned = 0;
      if ( !DeviceIoControl(hDevice, 0x7405Cu, 0, 0, InBuffer, 8u, &lpBytesReturned, 0) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x2B2,
          (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
          v4);
      v5 = InBuffer[0];
      goto LABEL_5;
    }
    if ( LastError != 122 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x2B9,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
        v3);
    LODWORD(v7) = v21[1];
    if ( (void *)((char *)v21[1] - (char *)v21[0]) > (void *)0x1000 )
    {
      v7 = (char *)v21[0] + 4096;
LABEL_13:
      v21[1] = v7;
      goto LABEL_14;
    }
    if ( (void *)((char *)v21[1] - (char *)v21[0]) < (void *)0x1000 )
    {
      if ( v22 - (unsigned __int64)v21[0] >= 0x1000 )
      {
        memset_0(v21[1], 0, 4096 - (unsigned __int64)((char *)v21[1] - (char *)v21[0]));
        v7 = (char *)v21[0] + 4096;
        goto LABEL_13;
      }
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v21);
      LODWORD(v7) = v21[1];
    }
LABEL_14:
    if ( !DeviceIoControl(hDevice, 0x70050u, 0, 0, v21[0], (_DWORD)v7 - LODWORD(v21[0]), &BytesReturned, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x2C6,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
        v8);
    v9 = v21[0];
    goto LABEL_17;
  }
  v9 = OutBuffer;
LABEL_17:
  if ( *(_DWORD *)v9 != 1 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x2D5,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
      (const char *)0x57,
      lpOutBuffer);
  v10 = *((_DWORD *)v9 + 1) - 1;
  if ( v10 < 0 )
    goto LABEL_41;
  v11 = *(_QWORD *)PARTITION_BASIC_DATA_GUID.Data4;
  while ( 1 )
  {
    v12 = 144LL * v10;
    if ( *(_QWORD *)&v9[v12 + 80] == *(_QWORD *)&PARTITION_BASIC_DATA_GUID.Data1
      && *(_QWORD *)&v9[v12 + 88] == *(_QWORD *)PARTITION_BASIC_DATA_GUID.Data4 )
    {
      break;
    }
    if ( --v10 < 0 )
      goto LABEL_41;
  }
  v13 = &v9[v12 + 48];
  if ( !v13 )
LABEL_41:
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x2E4,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
      (const char *)0x57,
      lpOutBuffer);
  v14 = *((_QWORD *)v13 + 1);
  v5 = *((_QWORD *)v13 + 2);
  v15 = v5 + v14;
  if ( v14 < 0 )
  {
    if ( v5 < 0 && v15 > v14 )
      goto LABEL_42;
  }
  else if ( v5 >= 0 && v15 < v14 )
  {
    goto LABEL_42;
  }
  v16 = *((_QWORD *)v9 + 3);
  v11 = *((_QWORD *)v9 + 4);
  v17 = v11 + v16;
  if ( v16 >= 0 )
  {
    if ( v11 < 0 || v17 >= v16 )
      goto LABEL_34;
LABEL_42:
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v9, v13, v15, v11);
  }
  if ( v11 < 0 && v17 > v16 )
    goto LABEL_42;
LABEL_34:
  if ( v15 < v17 )
  {
    HIDWORD(InBuffer[0]) = 0;
    LODWORD(InBuffer[0]) = *((_DWORD *)v13 + 6);
    v18 = v17 - v15;
    InBuffer[1] = v18;
    if ( !DeviceIoControl(hDevice, 0x7C0D0u, InBuffer, 0x10u, 0, 0, &BytesReturned, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x303,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\diskutilities.cpp",
        v19);
    v5 += v18;
  }
LABEL_5:
  std::vector<unsigned char>::~vector<unsigned char>(v21);
  return v5;
}

```

## disassembly

```asm
0x180029318  push    rbp
0x18002931a  push    rbx
0x18002931b  push    rsi
0x18002931c  push    rdi
0x18002931d  lea     rbp, [rsp-0D8h]
0x180029325  sub     rsp, 1D8h
0x18002932c  mov     rax, cs:__security_cookie
0x180029333  xor     rax, rsp
0x180029336  mov     [rbp+0F0h+var_30], rax
0x18002933d  mov     rsi, rcx
0x180029340  mov     [rsp+1F0h+BytesReturned], 0
0x180029348  xor     eax, eax
0x18002934a  xorps   xmm1, xmm1
0x18002934d  movdqu  xmmword ptr [rsp+1F0h+var_1B0], xmm1
0x180029353  mov     [rsp+1F0h+var_1A0], rax
0x180029358  mov     ebx, 150h
0x18002935d  mov     r8d, ebx; Size
0x180029360  xor     edx, edx; Val
0x180029362  lea     rcx, [rsp+1F0h+OutBuffer]; void *
0x180029367  call    memset_0
0x18002936c  mov     [rsp+1F0h+lpOverlapped], 0; lpOverlapped
0x180029375  lea     rax, [rsp+1F0h+BytesReturned]
0x18002937a  mov     [rsp+1F0h+lpBytesReturned], rax; lpBytesReturned
0x18002937f  mov     [rsp+1F0h+nOutBufferSize], ebx; nOutBufferSize
0x180029383  lea     rax, [rsp+1F0h+OutBuffer]
0x180029388  mov     [rsp+1F0h+lpOutBuffer], rax; unsigned int
0x18002938d  xor     r9d, r9d; nInBufferSize
0x180029390  xor     r8d, r8d; lpInBuffer
0x180029393  mov     edx, 70050h; dwIoControlCode
0x180029398  mov     rcx, rsi; hDevice
0x18002939b  call    cs:__imp_DeviceIoControl
0x1800293a2  nop     dword ptr [rax+rax+00h]
0x1800293a7  test    eax, eax
0x1800293a9  jnz     loc_180029508
0x1800293af  call    cs:__imp_GetLastError
0x1800293b6  nop     dword ptr [rax+rax+00h]
0x1800293bb  cmp     eax, 1
0x1800293be  jnz     loc_180029451
0x1800293c4  mov     [rsp+1F0h+InBuffer], 0
0x1800293cd  mov     [rsp+1F0h+var_194], 0
0x1800293d5  mov     [rsp+1F0h+lpOverlapped], 0; lpOverlapped
0x1800293de  lea     rax, [rsp+1F0h+var_194]
0x1800293e3  mov     [rsp+1F0h+lpBytesReturned], rax; lpBytesReturned
0x1800293e8  mov     [rsp+1F0h+nOutBufferSize], 8; nOutBufferSize
0x1800293f0  lea     rax, [rsp+1F0h+InBuffer]
0x1800293f5  mov     [rsp+1F0h+lpOutBuffer], rax; lpOutBuffer
0x1800293fa  xor     r9d, r9d; nInBufferSize
0x1800293fd  xor     r8d, r8d; lpInBuffer
0x180029400  mov     edx, 7405Ch; dwIoControlCode
0x180029405  mov     rcx, rsi; hDevice
0x180029408  call    cs:__imp_DeviceIoControl
0x18002940f  nop     dword ptr [rax+rax+00h]
0x180029414  mov     rcx, [rbp+0F8h]; this
0x18002941b  test    eax, eax
0x18002941d  jz      loc_18002966F
0x180029423  mov     rbx, [rsp+1F0h+InBuffer]
0x180029428  lea     rcx, [rsp+1F0h+var_1B0]
0x18002942d  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180029432  mov     rax, rbx
0x180029435  mov     rcx, [rbp+0F0h+var_30]
0x18002943c  xor     rcx, rsp; StackCookie
0x18002943f  call    __security_check_cookie
0x180029444  add     rsp, 1D8h
0x18002944b  pop     rdi
0x18002944c  pop     rsi
0x18002944d  pop     rbx
0x18002944e  pop     rbp
0x18002944f  retn
0x180029451  cmp     eax, 7Ah ; 'z'
0x180029454  jnz     loc_180029681
0x18002945a  mov     rdx, [rsp+1F0h+var_1B0]
0x18002945f  mov     rbx, [rsp+1F0h+var_1B0+8]
0x180029464  mov     rcx, rbx
0x180029467  sub     rcx, rdx
0x18002946a  mov     edi, 1000h
0x18002946f  cmp     rcx, rdi
0x180029472  jbe     short loc_18002947D
0x180029474  lea     rbx, [rdx+1000h]
0x18002947b  jmp     short loc_1800294B0
0x18002947d  jnb     short loc_1800294B5
0x18002947f  mov     rax, [rsp+1F0h+var_1A0]
0x180029484  sub     rax, rdx
0x180029487  cmp     rax, rdi
0x18002948a  jnb     short loc_18002949D
0x18002948c  lea     rcx, [rsp+1F0h+var_1B0]
0x180029491  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180029496  mov     rbx, [rsp+1F0h+var_1B0+8]
0x18002949b  jmp     short loc_1800294B5
0x18002949d  sub     rdi, rcx
0x1800294a0  mov     r8, rdi; Size
0x1800294a3  xor     edx, edx; Val
0x1800294a5  mov     rcx, rbx; void *
0x1800294a8  call    memset_0
0x1800294ad  add     rbx, rdi
0x1800294b0  mov     [rsp+1F0h+var_1B0+8], rbx
0x1800294b5  mov     rax, [rsp+1F0h+var_1B0]
0x1800294ba  sub     ebx, eax
0x1800294bc  mov     [rsp+1F0h+lpOverlapped], 0; lpOverlapped
0x1800294c5  lea     rcx, [rsp+1F0h+BytesReturned]
0x1800294ca  mov     [rsp+1F0h+lpBytesReturned], rcx; lpBytesReturned
0x1800294cf  mov     [rsp+1F0h+nOutBufferSize], ebx; nOutBufferSize
0x1800294d3  mov     [rsp+1F0h+lpOutBuffer], rax; lpOutBuffer
0x1800294d8  xor     r9d, r9d; nInBufferSize
0x1800294db  xor     r8d, r8d; lpInBuffer
0x1800294de  mov     edx, 70050h; dwIoControlCode
0x1800294e3  mov     rcx, rsi; hDevice
0x1800294e6  call    cs:__imp_DeviceIoControl
0x1800294ed  nop     dword ptr [rax+rax+00h]
0x1800294f2  mov     rcx, [rbp+0F8h]; this
0x1800294f9  test    eax, eax
0x1800294fb  jz      loc_18002969A
0x180029501  mov     rcx, [rsp+1F0h+var_1B0]
0x180029506  jmp     short loc_18002950D
0x180029508  lea     rcx, [rsp+1F0h+OutBuffer]
0x18002950d  cmp     dword ptr [rcx], 1
0x180029510  jnz     loc_1800296AC
0x180029516  mov     edx, [rcx+4]
0x180029519  sub     edx, 1
0x18002951c  js      loc_18002964A
0x180029522  mov     r9, qword ptr cs:PARTITION_BASIC_DATA_GUID.Data4
0x180029529  mov     r10, qword ptr cs:PARTITION_BASIC_DATA_GUID.Data1
0x180029530  movsxd  rax, edx
0x180029533  lea     r8, [rax+rax*8]
0x180029537  shl     r8, 4
0x18002953b  cmp     [r8+rcx+50h], r10
0x180029540  jnz     short loc_180029549
0x180029542  cmp     [r8+rcx+58h], r9
0x180029547  jz      short loc_180029554
0x180029549  sub     edx, 1
0x18002954c  js      loc_18002964A
0x180029552  jmp     short loc_180029530
0x180029554  lea     rdx, [rcx+30h]
0x180029558  add     rdx, r8
0x18002955b  jz      loc_18002964A
0x180029561  mov     rax, [rdx+8]
0x180029565  mov     rbx, [rdx+10h]
0x180029569  lea     r8, [rbx+rax]
0x18002956d  test    rax, rax
0x180029570  js      short loc_180029582
0x180029572  test    rbx, rbx
0x180029575  js      short loc_180029590
0x180029577  cmp     r8, rax
0x18002957a  jl      loc_180029669
0x180029580  jmp     short loc_180029590
0x180029582  test    rbx, rbx
0x180029585  jns     short loc_180029590
0x180029587  cmp     r8, rax
0x18002958a  jg      loc_180029669
0x180029590  mov     rax, [rcx+18h]
0x180029594  mov     r9, [rcx+20h]
0x180029598  lea     rdi, [r9+rax]
0x18002959c  test    rax, rax
0x18002959f  js      loc_180029629
0x1800295a5  test    r9, r9
0x1800295a8  js      short loc_1800295B3
0x1800295aa  cmp     rdi, rax
0x1800295ad  jl      loc_180029669
0x1800295b3  cmp     r8, rdi
0x1800295b6  jge     loc_180029428
0x1800295bc  mov     dword ptr [rsp+1F0h+InBuffer+4], 0
0x1800295c4  mov     eax, [rdx+18h]
0x1800295c7  mov     dword ptr [rsp+1F0h+InBuffer], eax
0x1800295cb  sub     rdi, r8
0x1800295ce  mov     [rsp+1F0h+var_188], rdi
0x1800295d3  mov     [rsp+1F0h+lpOverlapped], 0; lpOverlapped
0x1800295dc  lea     rax, [rsp+1F0h+BytesReturned]
0x1800295e1  mov     [rsp+1F0h+lpBytesReturned], rax; lpBytesReturned
0x1800295e6  mov     [rsp+1F0h+nOutBufferSize], 0; nOutBufferSize
0x1800295ee  mov     [rsp+1F0h+lpOutBuffer], 0; lpOutBuffer
0x1800295f7  mov     r9d, 10h; nInBufferSize
0x1800295fd  lea     r8, [rsp+1F0h+InBuffer]; lpInBuffer
0x180029602  mov     edx, 7C0D0h; dwIoControlCode
0x180029607  mov     rcx, rsi; hDevice
0x18002960a  call    cs:__imp_DeviceIoControl
0x180029611  nop     dword ptr [rax+rax+00h]
0x180029616  mov     rcx, [rbp+0F8h]; this
0x18002961d  test    eax, eax
0x18002961f  jz      short loc_180029638
0x180029621  add     rbx, rdi
0x180029624  jmp     loc_180029428
0x180029629  test    r9, r9
0x18002962c  jns     short loc_1800295B3
0x18002962e  cmp     rdi, rax
0x180029631  jg      short loc_180029669
0x180029633  jmp     loc_1800295B3
0x180029638  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\shared\\storage\\"...
0x18002963f  mov     edx, 303h; void *
0x180029644  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002964a  mov     rcx, [rbp+0F8h]; this
0x180029651  mov     r9d, 57h ; 'W'; char *
0x180029657  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\shared\\storage\\"...
0x18002965e  mov     edx, 2E4h; void *
0x180029663  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180029669  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x18002966f  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\shared\\storage\\"...
0x180029676  mov     edx, 2B2h; void *
0x18002967b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180029681  mov     rcx, [rbp+0F8h]; this
0x180029688  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\shared\\storage\\"...
0x18002968f  mov     edx, 2B9h; void *
0x180029694  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002969a  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\shared\\storage\\"...
0x1800296a1  mov     edx, 2C6h; void *
0x1800296a6  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800296ac  mov     rcx, [rbp+0F8h]; this
0x1800296b3  mov     r9d, 57h ; 'W'; char *
0x1800296b9  lea     r8, aOnecoreVmCompu_3; "onecore\\vm\\compute\\shared\\storage\\"...
0x1800296c0  mov     edx, 2D5h; void *
0x1800296c5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
