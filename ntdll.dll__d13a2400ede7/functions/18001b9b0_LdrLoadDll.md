# LdrLoadDll

- ea: `0x18001b9b0`
- end: `0x18001bca0`
- name: `LdrLoadDll`
- size: `752`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x1800010fc`
- `0x18001d4b0`
- `0x18002630c`
- `0x18011fe54`

## callees

- `0x18001b9b0`
- `0x18001eb80`
- `0x180023e10`
- `0x18002aef0`
- `0x18002b9f0`
- `0x1800709e0`
- `0x180162810`
- `0x18016f030`

## string_xrefs

- `0x18001ba75`: `LdrLoadDll`
- `0x18001baa4`: `LdrLoadDll`
- `0x18001bb78`: `LdrLoadDll`
- `0x18001bba6`: `LdrLoadDll`
- `0x18001bc24`: `LdrLoadDll`
- `0x18001ba5e`: `DLL name: %wZ\n`
- `0x18001bc1a`: `Nonpackaged process attempted to load a packaged DLL.\n`
- `0x18001bc54`: `DLL search path passed in externally: %ws\n`
- `0x18001bc6b`: `LdrpInitializeDllPath`

## pseudocode

```c
__int64 __fastcall LdrLoadDll(__int64 ArgList, int *a2, __int64 a3, _QWORD *a4)
{
  int v7; // r9d
  int v8; // ecx
  char v9; // dl
  char v10; // r8
  char v11; // cl
  char v12; // si
  __int64 v13; // rbp
  int Dll; // ebx
  __int64 v16; // rcx
  char ArgLista; // [rsp+28h] [rbp-C0h]
  __int128 v18; // [rsp+40h] [rbp-A8h] BYREF
  __int128 v19; // [rsp+50h] [rbp-98h]
  __int128 v20; // [rsp+60h] [rbp-88h]
  __int128 v21; // [rsp+70h] [rbp-78h]
  __int128 v22; // [rsp+80h] [rbp-68h]
  __int128 v23; // [rsp+90h] [rbp-58h]
  __int128 v24; // [rsp+A0h] [rbp-48h]
  __int128 v25; // [rsp+B0h] [rbp-38h]

  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  if ( a2 )
  {
    v7 = *a2;
    v8 = 2 * (*a2 & 4);
    v9 = v8 | 0x40;
    if ( (v7 & 2) == 0 )
      v9 = v8;
    v10 = v9 | 0x80;
    if ( (v7 & 0x800000) == 0 )
      v10 = v9;
    v11 = v10;
    if ( (v7 & 0x1000) == 0 )
      v11 = v10;
    v12 = v11;
    if ( v7 >= 0 )
      v12 = v11;
  }
  else
  {
    v12 = 0;
  }
  LdrpLogInternal((int)"minkernel\\ldr\\ldrapi.c", 1345, (int)"LdrLoadDll", 3, "DLL name: %wZ\n", a3);
  LdrpLogInternal((int)"minkernel\\ldr\\ldrapi.c", 1346, (int)"LdrLoadDll", 5, "%wZ\n", a3);
  if ( (LdrpPolicyBits & 4) == 0 && (ArgList & 0x401) == 0x401 )
    return 3221225485LL;
  if ( (v12 & 8) == 0 || (LdrpPolicyBits & 8) != 0 )
  {
    if ( (NtCurrentTeb()->SameTebFlags & 0x2000) != 0 )
    {
      Dll = -1073740004;
    }
    else
    {
      v13 = *(_QWORD *)(a3 + 8);
      memset_thunk_772440563353939046(&v18, 0, 0x80u);
      if ( (ArgList & 1) != 0 || !ArgList )
      {
        *(_QWORD *)&v20 = v13;
        DWORD2(v19) = ArgList & 0xFFFFFFFE;
      }
      else
      {
        *(_QWORD *)&v18 = ArgList;
        LdrpLogInternal(
          (int)"minkernel\\ldr\\ldrutil.c",
          1552,
          (int)"LdrpInitializeDllPath",
          2,
          "DLL search path passed in externally: %ws\n",
          ArgList);
        LdrpLogDllStateEx2(v16, v13, v18, 5312);
      }
      Dll = LdrpLoadDll(a3);
      LdrpReleaseDllPath(&v18);
      if ( Dll >= 0 )
      {
        *a4 = MEMORY[0x30];
        LdrpDereferenceModule(0);
      }
    }
  }
  else
  {
    LdrpLogInternal(
      (int)"minkernel\\ldr\\ldrapi.c",
      1369,
      (int)"LdrLoadDll",
      0,
      "Nonpackaged process attempted to load a packaged DLL.\n",
      ArgLista);
    Dll = -1073741398;
  }
  LdrpLogInternal((int)"minkernel\\ldr\\ldrapi.c", 1403, (int)"LdrLoadDll", 4, "Status: 0x%08lx\n", Dll);
  LdrpLogInternal((int)"minkernel\\ldr\\ldrapi.c", 1404, (int)"LdrLoadDll", 6, "%x\n", Dll);
  return (unsigned int)Dll;
}

```

## disassembly

```asm
0x18001b9b0  mov     r11, rsp
0x18001b9b3  mov     [r11+10h], rbx
0x18001b9b7  push    rsi
0x18001b9b8  push    rdi
0x18001b9b9  push    r14
0x18001b9bb  sub     rsp, 0D0h
0x18001b9c2  mov     rax, cs:__security_cookie
0x18001b9c9  xor     rax, rsp
0x18001b9cc  mov     [rsp+0E8h+var_28], rax
0x18001b9d4  mov     [rsp+0E8h+var_B8], 0
0x18001b9dd  xorps   xmm0, xmm0
0x18001b9e0  mov     r14, r9
0x18001b9e3  mov     rbx, r8
0x18001b9e6  mov     rdi, rcx
0x18001b9e9  movups  [rsp+0E8h+var_A8], xmm0
0x18001b9ee  movups  [rsp+0E8h+var_98], xmm0
0x18001b9f3  movups  [rsp+0E8h+var_88], xmm0
0x18001b9f8  movups  [rsp+0E8h+var_78], xmm0
0x18001b9fd  movups  xmmword ptr [r11-68h], xmm0
0x18001ba02  movups  xmmword ptr [r11-58h], xmm0
0x18001ba07  movups  xmmword ptr [r11-48h], xmm0
0x18001ba0c  movups  xmmword ptr [r11-38h], xmm0
0x18001ba11  test    rdx, rdx
0x18001ba14  jz      loc_18001BC0A
0x18001ba1a  mov     r9d, [rdx]
0x18001ba1d  mov     ecx, r9d
0x18001ba20  and     ecx, 4
0x18001ba23  add     ecx, ecx
0x18001ba25  mov     edx, ecx
0x18001ba27  or      edx, 40h
0x18001ba2a  test    r9b, 2
0x18001ba2e  cmovz   edx, ecx
0x18001ba31  mov     r8d, edx
0x18001ba34  bts     r8d, 7
0x18001ba39  bt      r9d, 17h
0x18001ba3e  cmovnb  r8d, edx
0x18001ba42  mov     ecx, r8d
0x18001ba45  bts     ecx, 8
0x18001ba49  bt      r9d, 0Ch
0x18001ba4e  cmovnb  ecx, r8d
0x18001ba52  mov     esi, ecx
0x18001ba54  bts     esi, 16h
0x18001ba58  test    r9d, r9d
0x18001ba5b  cmovns  esi, ecx
0x18001ba5e  lea     rax, aDllNameWz; "DLL name: %wZ\n"
0x18001ba65  mov     qword ptr [rsp+0E8h+ArgList], rbx; ArgList
0x18001ba6a  mov     r9d, 3; int
0x18001ba70  mov     [rsp+0E8h+Format], rax; Format
0x18001ba75  lea     r8, aLdrloaddll_0; "LdrLoadDll"
0x18001ba7c  mov     edx, 541h; int
0x18001ba81  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x18001ba88  call    LdrpLogInternal
0x18001ba8d  lea     rax, aWz_0; "%wZ\n"
0x18001ba94  mov     qword ptr [rsp+0E8h+ArgList], rbx; ArgList
0x18001ba99  mov     r9d, 5; int
0x18001ba9f  mov     [rsp+0E8h+Format], rax; Format
0x18001baa4  lea     r8, aLdrloaddll_0; "LdrLoadDll"
0x18001baab  mov     edx, 542h; int
0x18001bab0  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x18001bab7  call    LdrpLogInternal
0x18001babc  mov     ecx, cs:LdrpPolicyBits
0x18001bac2  test    cl, 4
0x18001bac5  jz      loc_18001BBE5
0x18001bacb  test    sil, 8
0x18001bacf  jnz     loc_18001BC11
0x18001bad5  mov     rax, gs:30h
0x18001bade  mov     ecx, 2000h
0x18001bae3  test    [rax+17EEh], cx
0x18001baea  jnz     loc_18001BC00
0x18001baf0  mov     [rsp+0E8h+arg_0], rbp
0x18001baf8  lea     rcx, [rsp+0E8h+var_A8]; void *
0x18001bafd  mov     rbp, [rbx+8]
0x18001bb01  xor     edx, edx; Val
0x18001bb03  mov     r8d, 80h; Size
0x18001bb09  call    memset$thunk$772440563353939046
0x18001bb0e  test    dil, 1
0x18001bb12  jz      loc_18001BC4B
0x18001bb18  and     edi, 0FFFFFFFEh
0x18001bb1b  mov     qword ptr [rsp+0E8h+var_88], rbp
0x18001bb20  mov     dword ptr [rsp+0E8h+var_98+8], edi
0x18001bb24  lea     r9, [rsp+0E8h+var_B8]
0x18001bb29  mov     r8d, esi
0x18001bb2c  lea     rdx, [rsp+0E8h+var_A8]
0x18001bb31  mov     rcx, rbx; ArgList
0x18001bb34  call    LdrpLoadDll
0x18001bb39  lea     rcx, [rsp+0E8h+var_A8]
0x18001bb3e  mov     ebx, eax
0x18001bb40  call    LdrpReleaseDllPath
0x18001bb45  mov     rbp, [rsp+0E8h+arg_0]
0x18001bb4d  test    ebx, ebx
0x18001bb4f  js      short loc_18001BB62
0x18001bb51  mov     rcx, [rsp+0E8h+var_B8]
0x18001bb56  mov     rax, [rcx+30h]
0x18001bb5a  mov     [r14], rax
0x18001bb5d  call    LdrpDereferenceModule
0x18001bb62  lea     rax, aStatus0x08lx; "Status: 0x%08lx\n"
0x18001bb69  mov     dword ptr [rsp+0E8h+ArgList], ebx; ArgList
0x18001bb6d  mov     r9d, 4; int
0x18001bb73  mov     [rsp+0E8h+Format], rax; Format
0x18001bb78  lea     r8, aLdrloaddll_0; "LdrLoadDll"
0x18001bb7f  mov     edx, 57Bh; int
0x18001bb84  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x18001bb8b  call    LdrpLogInternal
0x18001bb90  lea     rax, asc_180175AB4; "%x\n"
0x18001bb97  mov     dword ptr [rsp+0E8h+ArgList], ebx; ArgList
0x18001bb9b  mov     r9d, 6; int
0x18001bba1  mov     [rsp+0E8h+Format], rax; Format
0x18001bba6  lea     r8, aLdrloaddll_0; "LdrLoadDll"
0x18001bbad  mov     edx, 57Ch; int
0x18001bbb2  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x18001bbb9  call    LdrpLogInternal
0x18001bbbe  mov     eax, ebx
0x18001bbc0  mov     rcx, [rsp+0E8h+var_28]
0x18001bbc8  xor     rcx, rsp; StackCookie
0x18001bbcb  call    __security_check_cookie
0x18001bbd0  mov     rbx, [rsp+0E8h+arg_8]
0x18001bbd8  add     rsp, 0D0h
0x18001bbdf  pop     r14
0x18001bbe1  pop     rdi
0x18001bbe2  pop     rsi
0x18001bbe3  retn
0x18001bbe5  mov     rax, rdi
0x18001bbe8  and     eax, 401h
0x18001bbed  cmp     rax, 401h
0x18001bbf3  jnz     loc_18001BACB
0x18001bbf9  mov     eax, 0C000000Dh
0x18001bbfe  jmp     short loc_18001BBC0
0x18001bc00  mov     ebx, 0C000071Ch
0x18001bc05  jmp     loc_18001BB62
0x18001bc0a  xor     esi, esi
0x18001bc0c  jmp     loc_18001BA5E
0x18001bc11  test    cl, 8
0x18001bc14  jnz     loc_18001BAD5
0x18001bc1a  lea     rax, aNonpackagedPro; "Nonpackaged process attempted to load a"...
0x18001bc21  xor     r9d, r9d; int
0x18001bc24  lea     r8, aLdrloaddll_0; "LdrLoadDll"
0x18001bc2b  mov     [rsp+0E8h+Format], rax; Format
0x18001bc30  mov     edx, 559h; int
0x18001bc35  lea     rcx, aMinkernelLdrLd_3; "minkernel\\ldr\\ldrapi.c"
0x18001bc3c  call    LdrpLogInternal
0x18001bc41  mov     ebx, 0C00001AAh
0x18001bc46  jmp     loc_18001BB62
0x18001bc4b  test    rdi, rdi
0x18001bc4e  jz      loc_18001BB18
0x18001bc54  lea     rax, aDllSearchPathP; "DLL search path passed in externally: %"...
0x18001bc5b  mov     qword ptr [rsp+0E8h+ArgList], rdi; ArgList
0x18001bc60  mov     r9d, 2; int
0x18001bc66  mov     [rsp+0E8h+Format], rax; Format
0x18001bc6b  lea     r8, aLdrpinitialize_12; "LdrpInitializeDllPath"
0x18001bc72  mov     qword ptr [rsp+0E8h+var_A8], rdi
0x18001bc77  mov     edx, 610h; int
0x18001bc7c  lea     rcx, aMinkernelLdrLd_2; "minkernel\\ldr\\ldrutil.c"
0x18001bc83  call    LdrpLogInternal
0x18001bc88  mov     r8, qword ptr [rsp+0E8h+var_A8]
0x18001bc8d  mov     r9d, 14C0h
0x18001bc93  mov     rdx, rbp
0x18001bc96  call    LdrpLogDllStateEx2
0x18001bc9b  jmp     loc_18001BB24
```
