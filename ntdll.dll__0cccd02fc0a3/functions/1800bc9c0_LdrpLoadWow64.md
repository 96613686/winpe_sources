# LdrpLoadWow64

- ea: `0x1800bc9c0`
- end: `0x1800bcb60`
- name: `LdrpLoadWow64`
- size: `416`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x1800d6508`

## callees

- `0x18001eb80`
- `0x180023e20`
- `0x18002ad90`
- `0x18002c6f0`
- `0x180054000`
- `0x18005a9f0`
- `0x180066da0`
- `0x1800bc9c0`
- `0x1800bcb70`
- `0x1800bcba0`
- `0x180162000`
- `0x18016f030`

## string_xrefs

- `0x1800bca26`: `wow64.dll`
- `0x1800bcae4`: `Locating procedure "%Z" in WOW64 image management DLL "%wZ" failed with status 0x%08lx\n`
- `0x1800bcb3e`: `Loading WOW64 image management DLL "%wZ" failed with status 0x%08lx\n`

## pseudocode

```c
__int64 __fastcall LdrpLoadWow64(__int64 a1)
{
  int Dll; // ebx
  __int64 v3; // r14
  unsigned int i; // edi
  char v6[8]; // [rsp+40h] [rbp-C0h] BYREF
  char *v7; // [rsp+48h] [rbp-B8h]
  __int64 v8; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v9[128]; // [rsp+60h] [rbp-A0h] BYREF
  char v10; // [rsp+E0h] [rbp-20h] BYREF

  *(_QWORD *)v6 = 34078720;
  memset_thunk_772440563353939046(v9, 0, 0x80u);
  v8 = 0;
  v7 = &v10;
  RtlAppendUnicodeStringToString(v6, a1);
  RtlAppendUnicodeToString(v6, L"wow64.dll");
  LdrpInitializeDllPath(v7, 16385, v9);
  Dll = LdrpLoadDll((unsigned __int16 *)v6, (__int64)v9, 0x800u, (__int64)&v8);
  LdrpReleaseDllPath(v9);
  if ( Dll < 0 )
  {
    LdrpLogInternal(
      (int)"minkernel\\ldr\\ldrinit.c",
      4540,
      (int)"LdrpLoadWow64",
      0,
      "Loading WOW64 image management DLL \"%wZ\" failed with status 0x%08lx\n",
      (char)v6);
  }
  else
  {
    LdrProtectMrdata(0);
    v3 = v8;
    for ( i = 0; i < 6; ++i )
    {
      Dll = LdrGetProcedureAddress(*(_QWORD *)(v3 + 48), off_180170C40[2 * i], 0, off_180170C40[2 * i + 1]);
      if ( Dll < 0 )
      {
        LdrpLogInternal(
          (int)"minkernel\\ldr\\ldrinit.c",
          4563,
          (int)"LdrpLoadWow64",
          0,
          "Locating procedure \"%Z\" in WOW64 image management DLL \"%wZ\" failed with status 0x%08lx\n",
          (char)off_180170C40[2 * i]);
        break;
      }
    }
    LdrProtectMrdata(1);
    LdrpDereferenceModule(v3);
  }
  return (unsigned int)Dll;
}

```

## disassembly

```asm
0x1800bc9c0  push    rbp
0x1800bc9c2  push    rbx
0x1800bc9c3  push    rsi
0x1800bc9c4  push    rdi
0x1800bc9c5  push    r14
0x1800bc9c7  push    r15
0x1800bc9c9  lea     rbp, [rsp-208h]
0x1800bc9d1  sub     rsp, 308h
0x1800bc9d8  mov     rax, cs:__security_cookie
0x1800bc9df  xor     rax, rsp
0x1800bc9e2  mov     [rbp+230h+var_40], rax
0x1800bc9e9  mov     rbx, rcx
0x1800bc9ec  mov     qword ptr [rsp+330h+var_2F0], 2080000h
0x1800bc9f5  lea     rcx, [rsp+330h+var_2D0]; void *
0x1800bc9fa  xor     edx, edx; Val
0x1800bc9fc  mov     r8d, 80h; Size
0x1800bca02  call    memset$thunk$772440563353939046
0x1800bca07  lea     rax, [rbp+230h+var_250]
0x1800bca0b  mov     [rsp+330h+var_2E0], 0
0x1800bca14  mov     rdx, rbx
0x1800bca17  mov     [rsp+330h+var_2E8], rax
0x1800bca1c  lea     rcx, [rsp+330h+var_2F0]
0x1800bca21  call    RtlAppendUnicodeStringToString
0x1800bca26  lea     rdx, aWow64Dll; "wow64.dll"
0x1800bca2d  lea     rcx, [rsp+330h+var_2F0]
0x1800bca32  call    RtlAppendUnicodeToString
0x1800bca37  mov     rcx, [rsp+330h+var_2E8]
0x1800bca3c  lea     r8, [rsp+330h+var_2D0]
0x1800bca41  mov     edx, 4001h
0x1800bca46  call    LdrpInitializeDllPath
0x1800bca4b  lea     r9, [rsp+330h+var_2E0]
0x1800bca50  mov     r8d, 800h
0x1800bca56  lea     rdx, [rsp+330h+var_2D0]
0x1800bca5b  lea     rcx, [rsp+330h+var_2F0]; ArgList
0x1800bca60  call    LdrpLoadDll
0x1800bca65  lea     rcx, [rsp+330h+var_2D0]
0x1800bca6a  mov     ebx, eax
0x1800bca6c  call    LdrpReleaseDllPath
0x1800bca71  test    ebx, ebx
0x1800bca73  js      loc_1800BCB29
0x1800bca79  xor     ecx, ecx
0x1800bca7b  call    LdrProtectMrdata
0x1800bca80  mov     r14, [rsp+330h+var_2E0]
0x1800bca85  lea     r15, off_180170C40
0x1800bca8c  xor     edi, edi
0x1800bca8e  cmp     edi, 6
0x1800bca91  jnb     short loc_1800BCAF5
0x1800bca93  mov     rcx, [r14+30h]
0x1800bca97  xor     r8d, r8d
0x1800bca9a  mov     esi, edi
0x1800bca9c  add     rsi, rsi
0x1800bca9f  mov     r9, [r15+rsi*8+8]
0x1800bcaa4  mov     rdx, [r15+rsi*8]
0x1800bcaa8  call    LdrGetProcedureAddress
0x1800bcaad  mov     ebx, eax
0x1800bcaaf  test    eax, eax
0x1800bcab1  js      short loc_1800BCAB7
0x1800bcab3  inc     edi
0x1800bcab5  jmp     short loc_1800BCA8E
0x1800bcab7  mov     [rsp+330h+var_2F8], eax
0x1800bcabb  lea     r8, aLdrploadwow64; "LdrpLoadWow64"
0x1800bcac2  lea     rax, [rsp+330h+var_2F0]
0x1800bcac7  xor     r9d, r9d; int
0x1800bcaca  mov     [rsp+330h+var_300], rax
0x1800bcacf  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x1800bcad6  mov     rax, [r15+rsi*8]
0x1800bcada  mov     edx, 11D3h; int
0x1800bcadf  mov     qword ptr [rsp+330h+ArgList], rax; ArgList
0x1800bcae4  lea     rax, aLocatingProced_1; "Locating procedure \"%Z\" in WOW64 imag"...
0x1800bcaeb  mov     [rsp+330h+Format], rax; Format
0x1800bcaf0  call    LdrpLogInternal
0x1800bcaf5  mov     ecx, 1
0x1800bcafa  call    LdrProtectMrdata
0x1800bcaff  mov     rcx, r14
0x1800bcb02  call    LdrpDereferenceModule
0x1800bcb07  mov     eax, ebx
0x1800bcb09  mov     rcx, [rbp+230h+var_40]
0x1800bcb10  xor     rcx, rsp; StackCookie
0x1800bcb13  call    __security_check_cookie
0x1800bcb18  add     rsp, 308h
0x1800bcb1f  pop     r15
0x1800bcb21  pop     r14
0x1800bcb23  pop     rdi
0x1800bcb24  pop     rsi
0x1800bcb25  pop     rbx
0x1800bcb26  pop     rbp
0x1800bcb27  retn
0x1800bcb29  lea     rax, [rsp+330h+var_2F0]
0x1800bcb2e  mov     dword ptr [rsp+330h+var_300], ebx
0x1800bcb32  mov     qword ptr [rsp+330h+ArgList], rax; ArgList
0x1800bcb37  lea     r8, aLdrploadwow64; "LdrpLoadWow64"
0x1800bcb3e  lea     rax, aLoadingWow64Im; "Loading WOW64 image management DLL \"%w"...
0x1800bcb45  xor     r9d, r9d; int
0x1800bcb48  mov     edx, 11BCh; int
0x1800bcb4d  mov     [rsp+330h+Format], rax; Format
0x1800bcb52  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x1800bcb59  call    LdrpLogInternal
0x1800bcb5e  jmp     short loc_1800BCB07
```
