# LdrpLoadWow64

- ea: `0x1800c0ca0`
- end: `0x1800c0e40`
- name: `LdrpLoadWow64`
- size: `416`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x180050718`

## callees

- `0x18001eb80`
- `0x180023e10`
- `0x18002b9f0`
- `0x180036fa0`
- `0x1800709e0`
- `0x1800773d0`
- `0x180083780`
- `0x1800c0ca0`
- `0x1800c0e50`
- `0x1800c0e80`
- `0x180162810`
- `0x18016f030`

## string_xrefs

- `0x1800c0d06`: `wow64.dll`
- `0x1800c0dc4`: `Locating procedure "%Z" in WOW64 image management DLL "%wZ" failed with status 0x%08lx\n`
- `0x1800c0e1e`: `Loading WOW64 image management DLL "%wZ" failed with status 0x%08lx\n`

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
      Dll = LdrGetProcedureAddress(*(_QWORD *)(v3 + 48), off_180170BD0[2 * i], 0, off_180170BD0[2 * i + 1]);
      if ( Dll < 0 )
      {
        LdrpLogInternal(
          (int)"minkernel\\ldr\\ldrinit.c",
          4563,
          (int)"LdrpLoadWow64",
          0,
          "Locating procedure \"%Z\" in WOW64 image management DLL \"%wZ\" failed with status 0x%08lx\n",
          (char)off_180170BD0[2 * i]);
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
0x1800c0ca0  push    rbp
0x1800c0ca2  push    rbx
0x1800c0ca3  push    rsi
0x1800c0ca4  push    rdi
0x1800c0ca5  push    r14
0x1800c0ca7  push    r15
0x1800c0ca9  lea     rbp, [rsp-208h]
0x1800c0cb1  sub     rsp, 308h
0x1800c0cb8  mov     rax, cs:__security_cookie
0x1800c0cbf  xor     rax, rsp
0x1800c0cc2  mov     [rbp+230h+var_40], rax
0x1800c0cc9  mov     rbx, rcx
0x1800c0ccc  mov     qword ptr [rsp+330h+var_2F0], 2080000h
0x1800c0cd5  lea     rcx, [rsp+330h+var_2D0]; void *
0x1800c0cda  xor     edx, edx; Val
0x1800c0cdc  mov     r8d, 80h; Size
0x1800c0ce2  call    memset$thunk$772440563353939046
0x1800c0ce7  lea     rax, [rbp+230h+var_250]
0x1800c0ceb  mov     [rsp+330h+var_2E0], 0
0x1800c0cf4  mov     rdx, rbx
0x1800c0cf7  mov     [rsp+330h+var_2E8], rax
0x1800c0cfc  lea     rcx, [rsp+330h+var_2F0]
0x1800c0d01  call    RtlAppendUnicodeStringToString
0x1800c0d06  lea     rdx, aWow64Dll; "wow64.dll"
0x1800c0d0d  lea     rcx, [rsp+330h+var_2F0]
0x1800c0d12  call    RtlAppendUnicodeToString
0x1800c0d17  mov     rcx, [rsp+330h+var_2E8]
0x1800c0d1c  lea     r8, [rsp+330h+var_2D0]
0x1800c0d21  mov     edx, 4001h
0x1800c0d26  call    LdrpInitializeDllPath
0x1800c0d2b  lea     r9, [rsp+330h+var_2E0]
0x1800c0d30  mov     r8d, 800h
0x1800c0d36  lea     rdx, [rsp+330h+var_2D0]
0x1800c0d3b  lea     rcx, [rsp+330h+var_2F0]; ArgList
0x1800c0d40  call    LdrpLoadDll
0x1800c0d45  lea     rcx, [rsp+330h+var_2D0]
0x1800c0d4a  mov     ebx, eax
0x1800c0d4c  call    LdrpReleaseDllPath
0x1800c0d51  test    ebx, ebx
0x1800c0d53  js      loc_1800C0E09
0x1800c0d59  xor     ecx, ecx
0x1800c0d5b  call    LdrProtectMrdata
0x1800c0d60  mov     r14, [rsp+330h+var_2E0]
0x1800c0d65  lea     r15, off_180170BD0
0x1800c0d6c  xor     edi, edi
0x1800c0d6e  cmp     edi, 6
0x1800c0d71  jnb     short loc_1800C0DD5
0x1800c0d73  mov     rcx, [r14+30h]
0x1800c0d77  xor     r8d, r8d
0x1800c0d7a  mov     esi, edi
0x1800c0d7c  add     rsi, rsi
0x1800c0d7f  mov     r9, [r15+rsi*8+8]
0x1800c0d84  mov     rdx, [r15+rsi*8]
0x1800c0d88  call    LdrGetProcedureAddress
0x1800c0d8d  mov     ebx, eax
0x1800c0d8f  test    eax, eax
0x1800c0d91  js      short loc_1800C0D97
0x1800c0d93  inc     edi
0x1800c0d95  jmp     short loc_1800C0D6E
0x1800c0d97  mov     [rsp+330h+var_2F8], eax
0x1800c0d9b  lea     r8, aLdrploadwow64; "LdrpLoadWow64"
0x1800c0da2  lea     rax, [rsp+330h+var_2F0]
0x1800c0da7  xor     r9d, r9d; int
0x1800c0daa  mov     [rsp+330h+var_300], rax
0x1800c0daf  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x1800c0db6  mov     rax, [r15+rsi*8]
0x1800c0dba  mov     edx, 11D3h; int
0x1800c0dbf  mov     qword ptr [rsp+330h+ArgList], rax; ArgList
0x1800c0dc4  lea     rax, aLocatingProced_1; "Locating procedure \"%Z\" in WOW64 imag"...
0x1800c0dcb  mov     [rsp+330h+Format], rax; Format
0x1800c0dd0  call    LdrpLogInternal
0x1800c0dd5  mov     ecx, 1
0x1800c0dda  call    LdrProtectMrdata
0x1800c0ddf  mov     rcx, r14
0x1800c0de2  call    LdrpDereferenceModule
0x1800c0de7  mov     eax, ebx
0x1800c0de9  mov     rcx, [rbp+230h+var_40]
0x1800c0df0  xor     rcx, rsp; StackCookie
0x1800c0df3  call    __security_check_cookie
0x1800c0df8  add     rsp, 308h
0x1800c0dff  pop     r15
0x1800c0e01  pop     r14
0x1800c0e03  pop     rdi
0x1800c0e04  pop     rsi
0x1800c0e05  pop     rbx
0x1800c0e06  pop     rbp
0x1800c0e07  retn
0x1800c0e09  lea     rax, [rsp+330h+var_2F0]
0x1800c0e0e  mov     dword ptr [rsp+330h+var_300], ebx
0x1800c0e12  mov     qword ptr [rsp+330h+ArgList], rax; ArgList
0x1800c0e17  lea     r8, aLdrploadwow64; "LdrpLoadWow64"
0x1800c0e1e  lea     rax, aLoadingWow64Im; "Loading WOW64 image management DLL \"%w"...
0x1800c0e25  xor     r9d, r9d; int
0x1800c0e28  mov     edx, 11BCh; int
0x1800c0e2d  mov     [rsp+330h+Format], rax; Format
0x1800c0e32  lea     rcx, aMinkernelLdrLd_7; "minkernel\\ldr\\ldrinit.c"
0x1800c0e39  call    LdrpLogInternal
0x1800c0e3e  jmp     short loc_1800C0DE7
```
