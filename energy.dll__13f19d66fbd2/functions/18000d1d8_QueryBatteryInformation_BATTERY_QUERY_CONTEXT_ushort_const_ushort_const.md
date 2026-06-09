# QueryBatteryInformation(BATTERY_QUERY_CONTEXT *,ushort const *,ushort const *)

- ea: `0x18000d1d8`
- end: `0x18000d84e`
- name: `?QueryBatteryInformation@@YAJPEAUBATTERY_QUERY_CONTEXT@@PEBG1@Z`
- size: `1654`
- prototype: `int(struct BATTERY_QUERY_CONTEXT *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x180044d90`

## callees

- `0x18000b6f0`
- `0x18000d1d8`
- `0x18001ce44`
- `0x18001cefc`
- `0x180020454`
- `0x180035f98`
- `0x180037458`
- `0x18003bb60`
- `0x18003bce0`
- `0x180042fe8`
- `0x18004424c`
- `0x180044608`
- `0x18004ca90`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000d441`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000d4da`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000d5e3`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000d630`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000d6a8`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000d720`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000d441`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000d4da`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000d5e3`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000d630`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000d6a8`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000d720`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000d3cb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000d3cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d44b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d45e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d4e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d44b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d45e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d4e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d7e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d7e5`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18000d3a1`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18000d3a1`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x18000d364`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x18000d364`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall QueryBatteryInformation(
        struct BATTERY_QUERY_CONTEXT *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // r8
  HANDLE FileW; // rdi
  signed int LastError; // eax
  unsigned int v9; // ebx
  signed int v10; // eax
  signed int v11; // eax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rbx
  DWORD BytesReturned; // [rsp+40h] [rbp-2A8h] BYREF
  int v17; // [rsp+44h] [rbp-2A4h]
  unsigned int v18; // [rsp+48h] [rbp-2A0h]
  int InBuffer; // [rsp+4Ch] [rbp-29Ch] BYREF
  __int64 v20; // [rsp+50h] [rbp-298h]
  HANDLE v21; // [rsp+58h] [rbp-290h]
  __int64 OutBuffer; // [rsp+60h] [rbp-288h] BYREF
  int v23; // [rsp+68h] [rbp-280h]
  __int128 v24; // [rsp+70h] [rbp-278h] BYREF
  __int128 v25; // [rsp+80h] [rbp-268h]
  __int128 v26; // [rsp+90h] [rbp-258h] BYREF
  __int128 v27; // [rsp+A0h] [rbp-248h]
  int v28; // [rsp+B0h] [rbp-238h]
  DEVPROPGUID fmtid; // [rsp+B8h] [rbp-230h]
  __int128 pid; // [rsp+C8h] [rbp-220h]
  _QWORD v31[4]; // [rsp+E0h] [rbp-208h] BYREF
  _QWORD v32[4]; // [rsp+100h] [rbp-1E8h] BYREF
  _QWORD v33[4]; // [rsp+120h] [rbp-1C8h] BYREF
  _QWORD v34[4]; // [rsp+140h] [rbp-1A8h] BYREF
  _OWORD v35[2]; // [rsp+160h] [rbp-188h] BYREF
  int v36; // [rsp+180h] [rbp-168h]
  char v37; // [rsp+184h] [rbp-164h]
  int v38; // [rsp+188h] [rbp-160h]
  int v39; // [rsp+18Ch] [rbp-15Ch]
  int v40; // [rsp+190h] [rbp-158h]
  int v41; // [rsp+194h] [rbp-154h]
  int v42; // [rsp+198h] [rbp-150h] BYREF
  _BYTE v43[272]; // [rsp+1A0h] [rbp-148h] BYREF

  std::wstring::wstring(v31);
  std::wstring::wstring(v32);
  std::wstring::wstring(v33);
  std::wstring::wstring(v34);
  std::string::string(v35);
  OutBuffer = 0;
  v23 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  fmtid = 0;
  pid = 0;
  v20 = 0;
  v18 = 0;
  BytesReturned = 0;
  InBuffer = 0;
  if ( a3 )
  {
    v24 = 0;
    v25 = 0;
    v6 = -1;
    do
      ++v6;
    while ( a3[v6] );
    std::wstring::_Construct<1,unsigned short const *>(&v24, a3, v6);
    std::wstring::operator=(v32, &v24);
    if ( *((_QWORD *)&v25 + 1) > 7u )
      std::_Deallocate<16>((void *)v24, 2LL * *((_QWORD *)&v25 + 1) + 2);
    v36 = 0;
    v37 = 0;
    fmtid = DEVPKEY_Device_UINumber.fmtid;
    pid = DEVPKEY_Device_UINumber.pid;
    if ( (int)DevGetObjectProperties(3, a3, 0) >= 0 )
      DevFreeObjectProperties(v18, v20);
  }
  FileW = CreateFileW(a2, 0xC0000000, 3u, 0, 3u, 0x80u, 0);
  v21 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    *(_BYTE *)(*((_QWORD *)a1 + 2) + 272LL) = 1;
    InBuffer = 0;
    if ( DeviceIoControl(FileW, 0x294040u, &InBuffer, 4u, &OutBuffer, 4u, &BytesReturned, 0) )
    {
      v26 = 0;
      v27 = 0;
      v28 = 0;
      HIDWORD(OutBuffer) = 0;
      if ( DeviceIoControl(FileW, 0x294044u, &OutBuffer, 0xCu, &v26, 0x24u, &BytesReturned, 0) )
      {
        v38 = v26;
        v40 = HIDWORD(v26);
        v41 = v27;
        v39 = v28;
        v24 = 0;
        v25 = 0;
        try
        {
          std::string::_Construct<1,char const *>();
          std::string::_Tidy_deallocate(v35);
          v35[0] = v24;
          v35[1] = v25;
          HIDWORD(OutBuffer) = 5;
          if ( !DeviceIoControl(FileW, 0x294044u, &OutBuffer, 0xCu, &v42, 4u, &BytesReturned, 0) )
            v42 = 0;
          HIDWORD(OutBuffer) = 4;
          if ( DeviceIoControl(FileW, 0x294044u, &OutBuffer, 0xCu, v43, 0x100u, &BytesReturned, 0) )
          {
            v12 = std::wstring::wstring(&v24, v43, (unsigned __int64)BytesReturned >> 1);
            std::wstring::operator=(v31, v12);
            std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(&v24);
          }
          HIDWORD(OutBuffer) = 6;
          if ( DeviceIoControl(FileW, 0x294044u, &OutBuffer, 0xCu, v43, 0x100u, &BytesReturned, 0) )
          {
            v13 = std::wstring::wstring(&v24, v43, (unsigned __int64)BytesReturned >> 1);
            std::wstring::operator=(v33, v13);
            std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(&v24);
          }
          HIDWORD(OutBuffer) = 8;
          if ( DeviceIoControl(FileW, 0x294044u, &OutBuffer, 0xCu, v43, 0x100u, &BytesReturned, 0) )
          {
            v24 = 0;
            v25 = 0;
            std::wstring::_Construct<1,unsigned short const *>(&v24, v43, (unsigned __int64)BytesReturned >> 1);
            std::wstring::operator=(v34, &v24);
            if ( *((_QWORD *)&v25 + 1) > 7u )
              std::_Deallocate<16>((void *)v24, 2LL * *((_QWORD *)&v25 + 1) + 2);
          }
          v14 = *((_QWORD *)a1 + 2);
          if ( *(_QWORD *)(v14 + 256) == *(_QWORD *)(v14 + 264) )
          {
            std::vector<BatteryInfo>::_Emplace_reallocate<BatteryInfo const &>(v14 + 248, *(_QWORD *)(v14 + 256), v31);
          }
          else
          {
            BatteryInfo::BatteryInfo(*(BatteryInfo **)(v14 + 256), (const struct BatteryInfo *)v31);
            *(_QWORD *)(v14 + 256) += 192LL;
          }
          v9 = 0;
        }
        catch ( std::bad_alloc )
        {
          v17 = -2147024882;
          v9 = -2147024882;
          FileW = v21;
        }
        catch ( ... )
        {
          v17 = -2147467259;
          v9 = -2147467259;
          FileW = v21;
        }
      }
      else
      {
        v11 = GetLastError();
        v9 = v11;
        if ( v11 > 0 )
          v9 = (unsigned __int16)v11 | 0x80070000;
      }
    }
    else if ( GetLastError() == 2 )
    {
      v9 = 0;
    }
    else
    {
      v10 = GetLastError();
      v9 = v10;
      if ( v10 > 0 )
        v9 = (unsigned __int16)v10 | 0x80070000;
    }
    CloseHandle(FileW);
  }
  std::string::_Tidy_deallocate(v35);
  std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v34);
  std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v33);
  std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v32);
  std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v31);
  return v9;
}

```

## disassembly

```asm
0x18000d1d8  push    rbx
0x18000d1da  push    rsi
0x18000d1db  push    rdi
0x18000d1dc  push    r14
0x18000d1de  push    r15
0x18000d1e0  sub     rsp, 2C0h
0x18000d1e7  mov     rax, cs:__security_cookie
0x18000d1ee  xor     rax, rsp
0x18000d1f1  mov     [rsp+2E8h+var_38], rax
0x18000d1f9  mov     rbx, r8
0x18000d1fc  mov     rdi, rdx
0x18000d1ff  mov     rsi, rcx
0x18000d202  lea     rcx, [rsp+2E8h+var_208]; void *
0x18000d20a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000d20f  lea     rcx, [rsp+2E8h+var_1E8]; void *
0x18000d217  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000d21c  lea     rcx, [rsp+2E8h+var_1C8]; void *
0x18000d224  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000d229  lea     rcx, [rsp+2E8h+var_1A8]; void *
0x18000d231  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000d236  lea     rcx, [rsp+2E8h+var_188]
0x18000d23e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x18000d243  nop
0x18000d244  xor     eax, eax
0x18000d246  mov     [rsp+2E8h+OutBuffer], rax
0x18000d24b  mov     [rsp+2E8h+var_280], eax
0x18000d24f  xorps   xmm0, xmm0
0x18000d252  movups  [rsp+2E8h+var_258], xmm0
0x18000d25a  movups  [rsp+2E8h+var_248], xmm0
0x18000d262  mov     [rsp+2E8h+var_238], eax
0x18000d269  movups  [rsp+2E8h+var_230], xmm0
0x18000d271  movups  [rsp+2E8h+var_220], xmm0
0x18000d279  xor     r14d, r14d
0x18000d27c  mov     [rsp+2E8h+var_298], r14
0x18000d281  mov     [rsp+2E8h+var_2A0], r14d
0x18000d286  mov     [rsp+2E8h+BytesReturned], r14d
0x18000d28b  mov     [rsp+2E8h+InBuffer], r14d
0x18000d290  test    rbx, rbx
0x18000d293  jz      loc_18000D3A7
0x18000d299  movups  [rsp+2E8h+var_278], xmm0
0x18000d29e  xorps   xmm1, xmm1
0x18000d2a1  movdqu  [rsp+2E8h+var_268], xmm1
0x18000d2aa  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000d2ae  inc     r8
0x18000d2b1  cmp     [rbx+r8*2], r14w
0x18000d2b6  jnz     short loc_18000D2AE
0x18000d2b8  mov     rdx, rbx
0x18000d2bb  lea     rcx, [rsp+2E8h+var_278]
0x18000d2c0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000d2c5  lea     rdx, [rsp+2E8h+var_278]
0x18000d2ca  lea     rcx, [rsp+2E8h+var_1E8]
0x18000d2d2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000d2d7  mov     rdx, qword ptr [rsp+2E8h+var_268+8]
0x18000d2df  cmp     rdx, 7
0x18000d2e3  jbe     short loc_18000D2F7
0x18000d2e5  lea     rdx, ds:2[rdx*2]
0x18000d2ed  mov     rcx, qword ptr [rsp+2E8h+var_278]
0x18000d2f2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000d2f7  mov     [rsp+2E8h+var_168], r14d
0x18000d2ff  mov     [rsp+2E8h+var_164], r14b
0x18000d307  mov     qword ptr [rsp+2E8h+var_220+8], r14
0x18000d30f  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_UINumber.fmtid.Data1
0x18000d316  movups  [rsp+2E8h+var_230], xmm0
0x18000d31e  mov     eax, cs:DEVPKEY_Device_UINumber.pid
0x18000d324  mov     dword ptr [rsp+2E8h+var_220], eax
0x18000d32b  mov     dword ptr [rsp+2E8h+var_220+4], r14d
0x18000d333  lea     rax, [rsp+2E8h+var_298]
0x18000d338  mov     [rsp+2E8h+hTemplateFile], rax
0x18000d33d  lea     rax, [rsp+2E8h+var_2A0]
0x18000d342  mov     qword ptr [rsp+2E8h+dwFlagsAndAttributes], rax
0x18000d347  lea     rax, [rsp+2E8h+var_230]
0x18000d34f  mov     qword ptr [rsp+2E8h+dwCreationDisposition], rax
0x18000d354  mov     r9d, 1
0x18000d35a  xor     r8d, r8d
0x18000d35d  mov     rdx, rbx
0x18000d360  lea     ecx, [r9+2]
0x18000d364  call    cs:__imp_DevGetObjectProperties
0x18000d36a  test    eax, eax
0x18000d36c  js      short loc_18000D3A7
0x18000d36e  mov     r8d, [rsp+2E8h+var_2A0]
0x18000d373  mov     rdx, [rsp+2E8h+var_298]
0x18000d378  test    r8d, r8d
0x18000d37b  jz      short loc_18000D39E
0x18000d37d  cmp     dword ptr [rdx+20h], 7
0x18000d381  jnz     short loc_18000D39E
0x18000d383  cmp     dword ptr [rdx+24h], 4
0x18000d387  jnz     short loc_18000D39E
0x18000d389  mov     rax, [rdx+28h]
0x18000d38d  mov     ecx, [rax]
0x18000d38f  mov     [rsp+2E8h+var_168], ecx
0x18000d396  mov     [rsp+2E8h+var_164], 1
0x18000d39e  mov     ecx, r8d
0x18000d3a1  call    cs:__imp_DevFreeObjectProperties
0x18000d3a7  mov     [rsp+2E8h+hTemplateFile], r14; hTemplateFile
0x18000d3ac  mov     [rsp+2E8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000d3b4  mov     [rsp+2E8h+dwCreationDisposition], 3; dwCreationDisposition
0x18000d3bc  xor     r9d, r9d; lpSecurityAttributes
0x18000d3bf  mov     edx, 0C0000000h; dwDesiredAccess
0x18000d3c4  lea     r8d, [r9+3]; dwShareMode
0x18000d3c8  mov     rcx, rdi; lpFileName
0x18000d3cb  call    cs:__imp_CreateFileW
0x18000d3d1  mov     rdi, rax
0x18000d3d4  mov     [rsp+2E8h+var_290], rax
0x18000d3d9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000d3dd  jnz     short loc_18000D3FD
0x18000d3df  call    cs:__imp_GetLastError
0x18000d3e5  mov     ebx, eax
0x18000d3e7  test    eax, eax
0x18000d3e9  jle     loc_18000D7EC
0x18000d3ef  movzx   ebx, ax
0x18000d3f2  or      ebx, 80070000h
0x18000d3f8  jmp     loc_18000D7EC
0x18000d3fd  mov     rax, [rsi+10h]
0x18000d401  mov     byte ptr [rax+110h], 1
0x18000d408  mov     [rsp+2E8h+InBuffer], r14d
0x18000d40d  mov     [rsp+2E8h+lpOverlapped], r14; lpOverlapped
0x18000d412  lea     rax, [rsp+2E8h+BytesReturned]
0x18000d417  mov     [rsp+2E8h+hTemplateFile], rax; lpBytesReturned
0x18000d41c  mov     [rsp+2E8h+dwFlagsAndAttributes], 4; nOutBufferSize
0x18000d424  lea     rax, [rsp+2E8h+OutBuffer]
0x18000d429  mov     qword ptr [rsp+2E8h+dwCreationDisposition], rax; lpOutBuffer
0x18000d42e  mov     r9d, 4; nInBufferSize
0x18000d434  lea     r8, [rsp+2E8h+InBuffer]; lpInBuffer
0x18000d439  mov     edx, 294040h; dwIoControlCode
0x18000d43e  mov     rcx, rdi; hDevice
0x18000d441  call    cs:__imp_DeviceIoControl
0x18000d447  test    eax, eax
0x18000d449  jnz     short loc_18000D47C
0x18000d44b  call    cs:__imp_GetLastError
0x18000d451  cmp     eax, 2
0x18000d454  jnz     short loc_18000D45E
0x18000d456  mov     ebx, r14d
0x18000d459  jmp     loc_18000D7E2
0x18000d45e  call    cs:__imp_GetLastError
0x18000d464  mov     ebx, eax
0x18000d466  test    eax, eax
0x18000d468  jle     loc_18000D7E2
0x18000d46e  movzx   ebx, ax
0x18000d471  or      ebx, 80070000h
0x18000d477  jmp     loc_18000D7E2
0x18000d47c  xorps   xmm0, xmm0
0x18000d47f  xor     eax, eax
0x18000d481  movups  [rsp+2E8h+var_258], xmm0
0x18000d489  movups  [rsp+2E8h+var_248], xmm0
0x18000d491  mov     [rsp+2E8h+var_238], eax
0x18000d498  mov     dword ptr [rsp+2E8h+OutBuffer+4], r14d
0x18000d49d  mov     [rsp+2E8h+lpOverlapped], r14; lpOverlapped
0x18000d4a2  lea     rax, [rsp+2E8h+BytesReturned]
0x18000d4a7  mov     [rsp+2E8h+hTemplateFile], rax; lpBytesReturned
0x18000d4ac  mov     [rsp+2E8h+dwFlagsAndAttributes], 24h ; '$'; nOutBufferSize
0x18000d4b4  lea     rax, [rsp+2E8h+var_258]
0x18000d4bc  mov     qword ptr [rsp+2E8h+dwCreationDisposition], rax; lpOutBuffer
0x18000d4c1  mov     ebx, 0Ch
0x18000d4c6  mov     r9d, ebx; nInBufferSize
0x18000d4c9  lea     r8, [rsp+2E8h+OutBuffer]; lpInBuffer
0x18000d4ce  mov     r15d, 294044h
0x18000d4d4  mov     edx, r15d; dwIoControlCode
0x18000d4d7  mov     rcx, rdi; hDevice
0x18000d4da  call    cs:__imp_DeviceIoControl
0x18000d4e0  test    eax, eax
0x18000d4e2  jnz     short loc_18000D4FE
0x18000d4e4  call    cs:__imp_GetLastError
0x18000d4ea  mov     ebx, eax
0x18000d4ec  test    eax, eax
0x18000d4ee  jle     short loc_18000D4F9
0x18000d4f0  movzx   ebx, ax
0x18000d4f3  or      ebx, 80070000h
0x18000d4f9  jmp     loc_18000D7E2
0x18000d4fe  mov     eax, dword ptr [rsp+2E8h+var_258]
0x18000d505  mov     [rsp+2E8h+var_160], eax
0x18000d50c  mov     eax, dword ptr [rsp+2E8h+var_258+0Ch]
0x18000d513  mov     [rsp+2E8h+var_158], eax
0x18000d51a  mov     eax, dword ptr [rsp+2E8h+var_248]
0x18000d521  mov     [rsp+2E8h+var_154], eax
0x18000d528  mov     eax, [rsp+2E8h+var_238]
0x18000d52f  mov     [rsp+2E8h+var_15C], eax
0x18000d536  xorps   xmm0, xmm0
0x18000d539  movups  [rsp+2E8h+var_278], xmm0
0x18000d53e  xorps   xmm1, xmm1
0x18000d541  movdqu  [rsp+2E8h+var_268], xmm1
0x18000d54a  mov     r8d, 4
0x18000d550  lea     rdx, [rsp+2E8h+var_258+8]
0x18000d558  lea     rcx, [rsp+2E8h+var_278]
0x18000d55d  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18000d562  lea     rcx, [rsp+2E8h+var_188]
0x18000d56a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18000d56f  mov     rax, qword ptr [rsp+2E8h+var_278]
0x18000d574  mov     qword ptr [rsp+2E8h+var_188], rax
0x18000d57c  mov     rax, qword ptr [rsp+2E8h+var_278+8]
0x18000d581  mov     qword ptr [rsp+2E8h+var_188+8], rax
0x18000d589  mov     rax, qword ptr [rsp+2E8h+var_268]
0x18000d591  mov     qword ptr [rsp+2E8h+var_178], rax
0x18000d599  mov     rax, qword ptr [rsp+2E8h+var_268+8]
0x18000d5a1  mov     qword ptr [rsp+2E8h+var_178+8], rax
0x18000d5a9  mov     dword ptr [rsp+2E8h+OutBuffer+4], 5
0x18000d5b1  mov     [rsp+2E8h+lpOverlapped], r14; lpOverlapped
0x18000d5b6  lea     rax, [rsp+2E8h+BytesReturned]
0x18000d5bb  mov     [rsp+2E8h+hTemplateFile], rax; lpBytesReturned
0x18000d5c0  mov     [rsp+2E8h+dwFlagsAndAttributes], 4; nOutBufferSize
0x18000d5c8  lea     rax, [rsp+2E8h+var_150]
0x18000d5d0  mov     qword ptr [rsp+2E8h+dwCreationDisposition], rax; lpOutBuffer
0x18000d5d5  mov     r9d, ebx; nInBufferSize
0x18000d5d8  lea     r8, [rsp+2E8h+OutBuffer]; lpInBuffer
0x18000d5dd  mov     edx, r15d; dwIoControlCode
0x18000d5e0  mov     rcx, rdi; hDevice
0x18000d5e3  call    cs:__imp_DeviceIoControl
0x18000d5e9  test    eax, eax
0x18000d5eb  jnz     short loc_18000D5F6
0x18000d5ed  xor     eax, eax
0x18000d5ef  mov     [rsp+2E8h+var_150], eax
0x18000d5f6  mov     dword ptr [rsp+2E8h+OutBuffer+4], 4
0x18000d5fe  mov     [rsp+2E8h+lpOverlapped], r14; lpOverlapped
0x18000d603  lea     rax, [rsp+2E8h+BytesReturned]
0x18000d608  mov     [rsp+2E8h+hTemplateFile], rax; lpBytesReturned
0x18000d60d  mov     [rsp+2E8h+dwFlagsAndAttributes], 100h; nOutBufferSize
0x18000d615  lea     rax, [rsp+2E8h+var_148]
0x18000d61d  mov     qword ptr [rsp+2E8h+dwCreationDisposition], rax; lpOutBuffer
0x18000d622  mov     r9d, ebx; nInBufferSize
0x18000d625  lea     r8, [rsp+2E8h+OutBuffer]; lpInBuffer
0x18000d62a  mov     edx, r15d; dwIoControlCode
0x18000d62d  mov     rcx, rdi; hDevice
0x18000d630  call    cs:__imp_DeviceIoControl
0x18000d636  test    eax, eax
0x18000d638  jz      short loc_18000D66E
0x18000d63a  mov     r8d, [rsp+2E8h+BytesReturned]
0x18000d63f  shr     r8, 1
0x18000d642  lea     rdx, [rsp+2E8h+var_148]
0x18000d64a  lea     rcx, [rsp+2E8h+var_278]
0x18000d64f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x18000d654  mov     rdx, rax
0x18000d657  lea     rcx, [rsp+2E8h+var_208]
0x18000d65f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000d664  lea     rcx, [rsp+2E8h+var_278]; void *
0x18000d669  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring const,ulong>::~pair<std::wstring const,ulong>(void)
0x18000d66e  mov     dword ptr [rsp+2E8h+OutBuffer+4], 6
0x18000d676  mov     [rsp+2E8h+lpOverlapped], r14; lpOverlapped
0x18000d67b  lea     rax, [rsp+2E8h+BytesReturned]
0x18000d680  mov     [rsp+2E8h+hTemplateFile], rax; lpBytesReturned
0x18000d685  mov     [rsp+2E8h+dwFlagsAndAttributes], 100h; nOutBufferSize
0x18000d68d  lea     rax, [rsp+2E8h+var_148]
0x18000d695  mov     qword ptr [rsp+2E8h+dwCreationDisposition], rax; lpOutBuffer
0x18000d69a  mov     r9d, ebx; nInBufferSize
0x18000d69d  lea     r8, [rsp+2E8h+OutBuffer]; lpInBuffer
0x18000d6a2  mov     edx, r15d; dwIoControlCode
0x18000d6a5  mov     rcx, rdi; hDevice
0x18000d6a8  call    cs:__imp_DeviceIoControl
0x18000d6ae  test    eax, eax
0x18000d6b0  jz      short loc_18000D6E6
0x18000d6b2  mov     r8d, [rsp+2E8h+BytesReturned]
0x18000d6b7  shr     r8, 1
0x18000d6ba  lea     rdx, [rsp+2E8h+var_148]
0x18000d6c2  lea     rcx, [rsp+2E8h+var_278]
0x18000d6c7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x18000d6cc  mov     rdx, rax
0x18000d6cf  lea     rcx, [rsp+2E8h+var_1C8]
0x18000d6d7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000d6dc  lea     rcx, [rsp+2E8h+var_278]; void *
0x18000d6e1  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring const,ulong>::~pair<std::wstring const,ulong>(void)
0x18000d6e6  mov     dword ptr [rsp+2E8h+OutBuffer+4], 8
0x18000d6ee  mov     [rsp+2E8h+lpOverlapped], r14; lpOverlapped
0x18000d6f3  lea     rax, [rsp+2E8h+BytesReturned]
0x18000d6f8  mov     [rsp+2E8h+hTemplateFile], rax; lpBytesReturned
0x18000d6fd  mov     [rsp+2E8h+dwFlagsAndAttributes], 100h; nOutBufferSize
0x18000d705  lea     rax, [rsp+2E8h+var_148]
0x18000d70d  mov     qword ptr [rsp+2E8h+dwCreationDisposition], rax; lpOutBuffer
0x18000d712  mov     r9d, ebx; nInBufferSize
0x18000d715  lea     r8, [rsp+2E8h+OutBuffer]; lpInBuffer
0x18000d71a  mov     edx, r15d; dwIoControlCode
0x18000d71d  mov     rcx, rdi; hDevice
0x18000d720  call    cs:__imp_DeviceIoControl
0x18000d726  test    eax, eax
0x18000d728  jz      short loc_18000D78A
0x18000d72a  xorps   xmm0, xmm0
0x18000d72d  movups  [rsp+2E8h+var_278], xmm0
0x18000d732  xorps   xmm1, xmm1
0x18000d735  movdqu  [rsp+2E8h+var_268], xmm1
0x18000d73e  mov     r8d, [rsp+2E8h+BytesReturned]
0x18000d743  shr     r8, 1
0x18000d746  lea     rdx, [rsp+2E8h+var_148]
0x18000d74e  lea     rcx, [rsp+2E8h+var_278]
0x18000d753  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000d758  lea     rdx, [rsp+2E8h+var_278]
0x18000d75d  lea     rcx, [rsp+2E8h+var_1A8]
0x18000d765  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000d76a  mov     rdx, qword ptr [rsp+2E8h+var_268+8]
0x18000d772  cmp     rdx, 7
0x18000d776  jbe     short loc_18000D78A
0x18000d778  lea     rdx, ds:2[rdx*2]
0x18000d780  mov     rcx, qword ptr [rsp+2E8h+var_278]
0x18000d785  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000d78a  mov     rbx, [rsi+10h]
0x18000d78e  mov     rax, [rbx+100h]
0x18000d795  cmp     rax, [rbx+108h]
0x18000d79c  jz      short loc_18000D7BB
0x18000d79e  lea     rdx, [rsp+2E8h+var_208]; struct BatteryInfo *
0x18000d7a6  mov     rcx, rax; this
0x18000d7a9  call    ??0BatteryInfo@@QEAA@AEBU0@@Z; BatteryInfo::BatteryInfo(BatteryInfo const &)
0x18000d7ae  add     qword ptr [rbx+100h], 0C0h
0x18000d7b9  jmp     short loc_18000D7D2
0x18000d7bb  lea     r8, [rsp+2E8h+var_208]
  ... truncated ...
```
