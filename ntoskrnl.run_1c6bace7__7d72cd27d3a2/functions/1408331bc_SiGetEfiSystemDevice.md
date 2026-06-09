# SiGetEfiSystemDevice

- ea: `0x1408331bc`
- end: `0x14083336c`
- name: `SiGetEfiSystemDevice`
- size: `432`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x140832ee0`
- `0x140832f20`

## callees

- `0x1403887e8`
- `0x1406dc8c0`
- `0x14072d7ac`
- `0x1408330e4`
- `0x1408331bc`
- `0x140833374`
- `0x140ad73e8`
- `0x140bb1410`
- `0x140bb19f0`

## string_xrefs

- `0x1408332c3`: `Attempting Disambiguation of system device. Found %lu ESP partitions and %lu Virtual ESP partitions.`
- `0x140833350`: `System Device Path Found. Device Path: %ws`
- `0x14083331e`: `Disambiguation successful. Device Path: %ws`

## pseudocode

```c
__int64 __fastcall SiGetEfiSystemDevice(unsigned int a1, __int64 a2, wchar_t **a3)
{
  wchar_t *Pool2; // rbx
  int v6; // edi
  int EspFromFirmware; // eax
  wchar_t *v9; // [rsp+30h] [rbp-20h] BYREF
  __int128 v10; // [rsp+38h] [rbp-18h] BYREF

  v10 = 0;
  Pool2 = (wchar_t *)ExAllocatePool2(256, 106, 0x4B505953u);
  if ( !Pool2 )
  {
    v6 = -1073741801;
    goto LABEL_3;
  }
  v6 = SiDisambiguateSystemDevice((char *)&v10 + 8, (char *)&v10 + 12);
  if ( v6 >= 0 )
  {
    SiLogMessage(2, L"Found stored disambiguated system device to disk %lu, partition %lu.", DWORD2(v10), HIDWORD(v10));
LABEL_17:
    HIDWORD(v10) &= -(a1 != 0);
    RtlStringCbPrintfW(Pool2, 0x6Au, L"\\Device\\Harddisk%lu\\Partition%lu", DWORD2(v10), HIDWORD(v10));
    SiLogMessage(2, L"System Device Path Found. Device Path: %ws", Pool2);
    goto LABEL_18;
  }
  v6 = SyspartEnumerateDisks(SyspartResolveEfiEspCallback, &v10);
  if ( v6 >= 0 )
  {
    if ( (_DWORD)v10 )
    {
      if ( (unsigned int)v10 <= 1 || DWORD1(v10) == 1 )
      {
        v6 = 0;
        goto LABEL_17;
      }
      SiLogMessage(
        3,
        L"Attempting Disambiguation of system device. Found %lu ESP partitions and %lu Virtual ESP partitions.");
      ExFreePoolWithTag(Pool2, 0);
      v9 = 0;
      EspFromFirmware = SiGetEspFromFirmware(a1, &v9);
      v6 = EspFromFirmware;
      if ( EspFromFirmware >= 0 )
      {
        Pool2 = v9;
        SiLogMessage(2, L"Disambiguation successful. Device Path: %ws", v9);
LABEL_18:
        *a3 = Pool2;
        return (unsigned int)v6;
      }
      SiLogMessage(4, L"Disambiguation of system device failed. Status: %x", (unsigned int)EspFromFirmware);
      Pool2 = v9;
      v6 = -1073740719;
    }
    else
    {
      v6 = -1073740718;
    }
  }
LABEL_3:
  SiLogMessage(4, L"GetEfiSystemDevice Failed. Status: %x", (unsigned int)v6);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1408331bc  mov     [rsp-18h+arg_8], rbx
0x1408331c1  mov     [rsp-18h+arg_18], rsi
0x1408331c6  push    rbp
0x1408331c7  push    rdi
0x1408331c8  push    r14
0x1408331ca  mov     rbp, rsp
0x1408331cd  sub     rsp, 50h
0x1408331d1  mov     rax, cs:__security_cookie
0x1408331d8  xor     rax, rsp
0x1408331db  mov     [rbp+var_8], rax
0x1408331df  mov     rsi, r8
0x1408331e2  mov     r14d, ecx
0x1408331e5  xorps   xmm0, xmm0
0x1408331e8  mov     ecx, 100h
0x1408331ed  mov     r8d, 4B505953h
0x1408331f3  mov     edx, 6Ah ; 'j'
0x1408331f8  movups  [rbp+var_18], xmm0
0x1408331fc  call    ExAllocatePool2
0x140833201  mov     rbx, rax
0x140833204  test    rax, rax
0x140833207  jnz     short loc_140833255
0x140833209  mov     edi, 0C0000017h
0x14083320e  mov     r8d, edi
0x140833211  lea     rdx, aGetefisystemde; "GetEfiSystemDevice Failed. Status: %x"
0x140833218  mov     ecx, 4
0x14083321d  call    SiLogMessage
0x140833222  test    rbx, rbx
0x140833225  jz      short loc_140833231
0x140833227  xor     edx, edx; Tag
0x140833229  mov     rcx, rbx; P
0x14083322c  call    ExFreePoolWithTag
0x140833231  mov     eax, edi
0x140833233  mov     rcx, [rbp+var_8]
0x140833237  xor     rcx, rsp; StackCookie
0x14083323a  call    __security_check_cookie
0x14083323f  lea     r11, [rsp+50h+var_s0]
0x140833244  mov     rbx, [r11+28h]
0x140833248  mov     rsi, [r11+38h]
0x14083324c  mov     rsp, r11
0x14083324f  pop     r14
0x140833251  pop     rdi
0x140833252  pop     rbp
0x140833253  retn
0x140833255  lea     rdx, [rbp+var_18+0Ch]
0x140833259  lea     rcx, [rbp+var_18+8]
0x14083325d  call    SiDisambiguateSystemDevice
0x140833262  mov     edi, eax
0x140833264  test    eax, eax
0x140833266  js      short loc_140833286
0x140833268  mov     r9d, dword ptr [rbp+var_18+0Ch]
0x14083326c  lea     rdx, aFoundStoredDis; "Found stored disambiguated system devic"...
0x140833273  mov     r8d, dword ptr [rbp+var_18+8]
0x140833277  mov     ecx, 2
0x14083327c  call    SiLogMessage
0x140833281  jmp     loc_140833329
0x140833286  lea     rdx, [rbp+var_18]
0x14083328a  lea     rcx, SyspartResolveEfiEspCallback
0x140833291  call    SyspartEnumerateDisks
0x140833296  mov     edi, eax
0x140833298  test    eax, eax
0x14083329a  js      loc_14083320E
0x1408332a0  mov     r8d, dword ptr [rbp+var_18]
0x1408332a4  test    r8d, r8d
0x1408332a7  jnz     short loc_1408332B3
0x1408332a9  mov     edi, 0C0000452h
0x1408332ae  jmp     loc_14083320E
0x1408332b3  cmp     r8d, 1
0x1408332b7  jbe     short loc_140833327
0x1408332b9  mov     r9d, dword ptr [rbp+var_18+4]
0x1408332bd  cmp     r9d, 1
0x1408332c1  jz      short loc_140833327
0x1408332c3  lea     rdx, aAttemptingDisa; "Attempting Disambiguation of system dev"...
0x1408332ca  mov     ecx, 3
0x1408332cf  call    SiLogMessage
0x1408332d4  xor     edx, edx; Tag
0x1408332d6  mov     rcx, rbx; P
0x1408332d9  call    ExFreePoolWithTag
0x1408332de  lea     rdx, [rbp+var_20]
0x1408332e2  mov     [rbp+var_20], 0
0x1408332ea  mov     ecx, r14d
0x1408332ed  call    SiGetEspFromFirmware
0x1408332f2  mov     edi, eax
0x1408332f4  test    eax, eax
0x1408332f6  jns     short loc_14083331A
0x1408332f8  mov     r8d, eax
0x1408332fb  lea     rdx, aDisambiguation; "Disambiguation of system device failed."...
0x140833302  mov     ecx, 4
0x140833307  call    SiLogMessage
0x14083330c  mov     rbx, [rbp+var_20]
0x140833310  mov     edi, 0C0000451h
0x140833315  jmp     loc_14083320E
0x14083331a  mov     rbx, [rbp+var_20]
0x14083331e  lea     rdx, aDisambiguation_0; "Disambiguation successful. Device Path:"...
0x140833325  jmp     short loc_140833357
0x140833327  xor     edi, edi
0x140833329  mov     r9d, dword ptr [rbp+var_18+8]
0x14083332d  lea     r8, aDeviceHarddisk_4; "\\Device\\Harddisk%lu\\Partition%lu"
0x140833334  neg     r14d
0x140833337  mov     edx, 6Ah ; 'j'; cbDest
0x14083333c  mov     rcx, rbx; pszDest
0x14083333f  sbb     eax, eax
0x140833341  and     eax, dword ptr [rbp+var_18+0Ch]
0x140833344  mov     dword ptr [rbp+var_18+0Ch], eax
0x140833347  mov     [rsp+50h+var_30], eax
0x14083334b  call    RtlStringCbPrintfW
0x140833350  lea     rdx, aSystemDevicePa; "System Device Path Found. Device Path: "...
0x140833357  mov     r8, rbx
0x14083335a  mov     ecx, 2
0x14083335f  call    SiLogMessage
0x140833364  mov     [rsi], rbx
0x140833367  jmp     loc_140833231
```
