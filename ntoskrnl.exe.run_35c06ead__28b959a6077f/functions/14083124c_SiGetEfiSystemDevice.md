# SiGetEfiSystemDevice

- ea: `0x14083124c`
- end: `0x1408313fc`
- name: `SiGetEfiSystemDevice`
- size: `432`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x140830f70`
- `0x140830fb0`

## callees

- `0x1403f4ae8`
- `0x1406d9d70`
- `0x14072964c`
- `0x140831174`
- `0x14083124c`
- `0x140831404`
- `0x140ad2358`
- `0x140bae410`
- `0x140bae8e0`

## string_xrefs

- `0x140831353`: `Attempting Disambiguation of system device. Found %lu ESP partitions and %lu Virtual ESP partitions.`
- `0x1408313ae`: `Disambiguation successful. Device Path: %ws`
- `0x1408313e0`: `System Device Path Found. Device Path: %ws`

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
  Pool2 = (wchar_t *)ExAllocatePool2(256, 106, 1263556947);
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
0x14083124c  mov     [rsp-18h+arg_8], rbx
0x140831251  mov     [rsp-18h+arg_18], rsi
0x140831256  push    rbp
0x140831257  push    rdi
0x140831258  push    r14
0x14083125a  mov     rbp, rsp
0x14083125d  sub     rsp, 50h
0x140831261  mov     rax, cs:__security_cookie
0x140831268  xor     rax, rsp
0x14083126b  mov     [rbp+var_8], rax
0x14083126f  mov     rsi, r8
0x140831272  mov     r14d, ecx
0x140831275  xorps   xmm0, xmm0
0x140831278  mov     ecx, 100h
0x14083127d  mov     r8d, 4B505953h
0x140831283  mov     edx, 6Ah ; 'j'
0x140831288  movups  [rbp+var_18], xmm0
0x14083128c  call    ExAllocatePool2
0x140831291  mov     rbx, rax
0x140831294  test    rax, rax
0x140831297  jnz     short loc_1408312E5
0x140831299  mov     edi, 0C0000017h
0x14083129e  mov     r8d, edi
0x1408312a1  lea     rdx, aGetefisystemde; "GetEfiSystemDevice Failed. Status: %x"
0x1408312a8  mov     ecx, 4
0x1408312ad  call    SiLogMessage
0x1408312b2  test    rbx, rbx
0x1408312b5  jz      short loc_1408312C1
0x1408312b7  xor     edx, edx; Tag
0x1408312b9  mov     rcx, rbx; P
0x1408312bc  call    ExFreePoolWithTag
0x1408312c1  mov     eax, edi
0x1408312c3  mov     rcx, [rbp+var_8]
0x1408312c7  xor     rcx, rsp; StackCookie
0x1408312ca  call    __security_check_cookie
0x1408312cf  lea     r11, [rsp+50h+var_s0]
0x1408312d4  mov     rbx, [r11+28h]
0x1408312d8  mov     rsi, [r11+38h]
0x1408312dc  mov     rsp, r11
0x1408312df  pop     r14
0x1408312e1  pop     rdi
0x1408312e2  pop     rbp
0x1408312e3  retn
0x1408312e5  lea     rdx, [rbp+var_18+0Ch]
0x1408312e9  lea     rcx, [rbp+var_18+8]
0x1408312ed  call    SiDisambiguateSystemDevice
0x1408312f2  mov     edi, eax
0x1408312f4  test    eax, eax
0x1408312f6  js      short loc_140831316
0x1408312f8  mov     r9d, dword ptr [rbp+var_18+0Ch]
0x1408312fc  lea     rdx, aFoundStoredDis; "Found stored disambiguated system devic"...
0x140831303  mov     r8d, dword ptr [rbp+var_18+8]
0x140831307  mov     ecx, 2
0x14083130c  call    SiLogMessage
0x140831311  jmp     loc_1408313B9
0x140831316  lea     rdx, [rbp+var_18]
0x14083131a  lea     rcx, SyspartResolveEfiEspCallback
0x140831321  call    SyspartEnumerateDisks
0x140831326  mov     edi, eax
0x140831328  test    eax, eax
0x14083132a  js      loc_14083129E
0x140831330  mov     r8d, dword ptr [rbp+var_18]
0x140831334  test    r8d, r8d
0x140831337  jnz     short loc_140831343
0x140831339  mov     edi, 0C0000452h
0x14083133e  jmp     loc_14083129E
0x140831343  cmp     r8d, 1
0x140831347  jbe     short loc_1408313B7
0x140831349  mov     r9d, dword ptr [rbp+var_18+4]
0x14083134d  cmp     r9d, 1
0x140831351  jz      short loc_1408313B7
0x140831353  lea     rdx, aAttemptingDisa; "Attempting Disambiguation of system dev"...
0x14083135a  mov     ecx, 3
0x14083135f  call    SiLogMessage
0x140831364  xor     edx, edx; Tag
0x140831366  mov     rcx, rbx; P
0x140831369  call    ExFreePoolWithTag
0x14083136e  lea     rdx, [rbp+var_20]
0x140831372  mov     [rbp+var_20], 0
0x14083137a  mov     ecx, r14d
0x14083137d  call    SiGetEspFromFirmware
0x140831382  mov     edi, eax
0x140831384  test    eax, eax
0x140831386  jns     short loc_1408313AA
0x140831388  mov     r8d, eax
0x14083138b  lea     rdx, aDisambiguation; "Disambiguation of system device failed."...
0x140831392  mov     ecx, 4
0x140831397  call    SiLogMessage
0x14083139c  mov     rbx, [rbp+var_20]
0x1408313a0  mov     edi, 0C0000451h
0x1408313a5  jmp     loc_14083129E
0x1408313aa  mov     rbx, [rbp+var_20]
0x1408313ae  lea     rdx, aDisambiguation_0; "Disambiguation successful. Device Path:"...
0x1408313b5  jmp     short loc_1408313E7
0x1408313b7  xor     edi, edi
0x1408313b9  mov     r9d, dword ptr [rbp+var_18+8]
0x1408313bd  lea     r8, aDeviceHarddisk_4; "\\Device\\Harddisk%lu\\Partition%lu"
0x1408313c4  neg     r14d
0x1408313c7  mov     edx, 6Ah ; 'j'; cbDest
0x1408313cc  mov     rcx, rbx; pszDest
0x1408313cf  sbb     eax, eax
0x1408313d1  and     eax, dword ptr [rbp+var_18+0Ch]
0x1408313d4  mov     dword ptr [rbp+var_18+0Ch], eax
0x1408313d7  mov     [rsp+50h+var_30], eax
0x1408313db  call    RtlStringCbPrintfW
0x1408313e0  lea     rdx, aSystemDevicePa; "System Device Path Found. Device Path: "...
0x1408313e7  mov     r8, rbx
0x1408313ea  mov     ecx, 2
0x1408313ef  call    SiLogMessage
0x1408313f4  mov     [rsi], rbx
0x1408313f7  jmp     loc_1408312C1
```
