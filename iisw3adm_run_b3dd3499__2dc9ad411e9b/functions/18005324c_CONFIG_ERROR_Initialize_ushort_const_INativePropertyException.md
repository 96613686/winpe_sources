# CONFIG_ERROR::Initialize(ushort const *,INativePropertyException *)

- ea: `0x18005324c`
- end: `0x1800535a2`
- name: `?Initialize@CONFIG_ERROR@@AEAAJPEBGPEAVINativePropertyException@@@Z`
- size: `854`
- prototype: `__int64 __fastcall(CONFIG_ERROR *__hidden this, const unsigned __int16 *, struct INativePropertyException *)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180052d90`
- `0x1800535a8`
- `0x180053670`
- `0x180053738`
- `0x180053818`

## callees

- `0x180001280`
- `0x18005324c`
- `0x180062010`

## import_xrefs

- `iisutil!PuDbgPrintError` at `0x1800532dd`
- `iisutil!PuDbgPrintError` at `0x18005356a`
- `iisutil!PuDbgPrintError` at `0x1800532dd`
- `iisutil!PuDbgPrintError` at `0x18005356a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180053299`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180053328`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180053396`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180053445`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180053299`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180053328`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180053396`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180053445`

## string_xrefs

- `0x1800532d6`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_error.cxx`
- `0x180053559`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\config_error.cxx`
- `0x1800532b2`: ` Failed to copy property name\n`
- `0x1800532cf`: `CONFIG_ERROR::Initialize`
- `0x18005354d`: `CONFIG_ERROR::Initialize`
- `0x180053341`: ` Failed to copy error string for native property exception\n`
- `0x1800533af`: ` Failed to copy filename for native property exception\n`
- `0x18005345e`: ` Failed to copy the invalid value string for native property exception\n`

## pseudocode

```c
__int64 __fastcall CONFIG_ERROR::Initialize(
        CONFIG_ERROR *this,
        const unsigned __int16 *a2,
        struct INativePropertyException *a3)
{
  int v5; // ebx
  const char *v6; // rax
  __int64 v7; // r8
  unsigned __int64 v8; // kr00_8
  void *v9; // rax
  __int64 i; // r14
  const unsigned __int16 *v12; // [rsp+40h] [rbp-20h] BYREF
  const unsigned __int16 *v13; // [rsp+48h] [rbp-18h] BYREF
  const unsigned __int16 *v14; // [rsp+50h] [rbp-10h] BYREF
  __int64 v15; // [rsp+58h] [rbp-8h] BYREF
  int v16; // [rsp+80h] [rbp+20h] BYREF
  unsigned int v17; // [rsp+98h] [rbp+38h] BYREF

  v12 = 0;
  v13 = 0;
  v16 = 0;
  v14 = 0;
  v17 = 0;
  v15 = 0;
  v5 = STRU::Copy((CONFIG_ERROR *)((char *)this + 16), a2);
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(struct INativePropertyException *, const unsigned __int16 **))(*(_QWORD *)a3 + 32LL))(
           a3,
           &v12);
    if ( v5 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        return (unsigned int)v5;
      v6 = " Failed to get error string for native property exception\n";
      v7 = 377;
      goto LABEL_4;
    }
    v5 = STRU::Copy((CONFIG_ERROR *)((char *)this + 200), v12);
    if ( v5 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        return (unsigned int)v5;
      v6 = " Failed to copy error string for native property exception\n";
      v7 = 387;
      goto LABEL_4;
    }
    v5 = (*(__int64 (__fastcall **)(struct INativePropertyException *, const unsigned __int16 **))(*(_QWORD *)a3 + 64LL))(
           a3,
           &v13);
    if ( v5 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        return (unsigned int)v5;
      v6 = " Failed to get filename for native property exception\n";
      v7 = 397;
      goto LABEL_4;
    }
    v5 = STRU::Copy((CONFIG_ERROR *)((char *)this + 256), v13);
    if ( v5 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        return (unsigned int)v5;
      v6 = " Failed to copy filename for native property exception\n";
      v7 = 407;
      goto LABEL_4;
    }
    v5 = (*(__int64 (__fastcall **)(struct INativePropertyException *, int *))(*(_QWORD *)a3 + 56LL))(a3, &v16);
    if ( v5 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        return (unsigned int)v5;
      v6 = " Failed to get line number for native property exception\n";
      v7 = 417;
      goto LABEL_4;
    }
    *((_DWORD *)this + 49) = v16;
    v5 = (*(__int64 (__fastcall **)(struct INativePropertyException *, const unsigned __int16 **))(*(_QWORD *)a3 + 24LL))(
           a3,
           &v14);
    if ( v5 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        return (unsigned int)v5;
      v6 = " Failed to get the invalid value string for native property exception\n";
      v7 = 429;
      goto LABEL_4;
    }
    v5 = STRU::Copy((CONFIG_ERROR *)((char *)this + 128), v14);
    if ( v5 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        return (unsigned int)v5;
      v6 = " Failed to copy the invalid value string for native property exception\n";
      v7 = 439;
      goto LABEL_4;
    }
    v5 = (*(__int64 (__fastcall **)(struct INativePropertyException *, unsigned int *))(*(_QWORD *)a3 + 40LL))(a3, &v17);
    if ( v5 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) == 0 )
        return (unsigned int)v5;
      v6 = " Failed to get validation parameter count for native property exception\n";
      v7 = 449;
      goto LABEL_4;
    }
    v8 = v17;
    *((_DWORD *)this + 48) = v17;
    v9 = operator new[](saturated_mul(v8, 8u));
    *((_QWORD *)this + 23) = v9;
    if ( v9 )
    {
      for ( i = 0; (unsigned int)i < *((_DWORD *)this + 48); i = (unsigned int)(i + 1) )
      {
        v5 = (*(__int64 (__fastcall **)(struct INativePropertyException *, _QWORD, __int64 *))(*(_QWORD *)a3 + 48LL))(
               a3,
               (unsigned int)i,
               &v15);
        if ( v5 < 0 && (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_error.cxx",
            475,
            "CONFIG_ERROR::Initialize",
            v5,
            " Failed to get validation failure parameter '%d' for native property exception\n",
            i);
        *(_QWORD *)(*((_QWORD *)this + 23) + 8 * i) = v15;
      }
    }
    else
    {
      v5 = -2147024882;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_error.cxx",
          461,
          "CONFIG_ERROR::Initialize",
          -2147024882,
          " Out of memory trying to allocate paramter validation array\n");
    }
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    v6 = " Failed to copy property name\n";
    v7 = 367;
LABEL_4:
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\config_error.cxx",
      v7,
      "CONFIG_ERROR::Initialize",
      v5,
      v6);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18005324c  mov     [rsp-18h+arg_8], rbx
0x180053251  mov     [rsp-18h+arg_10], rsi
0x180053256  push    rbp
0x180053257  push    rdi
0x180053258  push    r14
0x18005325a  mov     rbp, rsp
0x18005325d  sub     rsp, 60h
0x180053261  mov     rsi, rcx
0x180053264  mov     [rbp+var_20], 0
0x18005326c  add     rcx, 10h
0x180053270  mov     [rbp+var_18], 0
0x180053278  mov     rdi, r8
0x18005327b  mov     [rbp+arg_0], 0
0x180053282  mov     [rbp+var_10], 0
0x18005328a  mov     [rbp+arg_18], 0
0x180053291  mov     [rbp+var_8], 0
0x180053299  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18005329f  mov     ebx, eax
0x1800532a1  test    eax, eax
0x1800532a3  jns     short loc_1800532E8
0x1800532a5  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800532ac  jz      loc_18005358B
0x1800532b2  lea     rax, aFailedToCopyPr; " Failed to copy property name\n"
0x1800532b9  mov     r8d, 16Fh
0x1800532bf  mov     [rsp+60h+var_38], rax
0x1800532c4  mov     [rsp+60h+var_40], ebx
0x1800532c8  mov     rcx, cs:g_pDebug
0x1800532cf  lea     r9, aConfigErrorIni_2; "CONFIG_ERROR::Initialize"
0x1800532d6  lea     rdx, aServercommonIn_53; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800532dd  call    cs:__imp_PuDbgPrintError
0x1800532e3  jmp     loc_18005358B
0x1800532e8  mov     rax, [rdi]
0x1800532eb  lea     rdx, [rbp+var_20]
0x1800532ef  mov     rcx, rdi
0x1800532f2  mov     rax, [rax+20h]
0x1800532f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800532fb  mov     ebx, eax
0x1800532fd  test    eax, eax
0x1800532ff  jns     short loc_18005331D
0x180053301  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180053308  jz      loc_18005358B
0x18005330e  lea     rax, aFailedToGetErr_4; " Failed to get error string for native "...
0x180053315  mov     r8d, 179h
0x18005331b  jmp     short loc_1800532BF
0x18005331d  mov     rdx, [rbp+var_20]
0x180053321  lea     rcx, [rsi+0C8h]
0x180053328  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18005332e  mov     ebx, eax
0x180053330  test    eax, eax
0x180053332  jns     short loc_180053353
0x180053334  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005333b  jz      loc_18005358B
0x180053341  lea     rax, aFailedToCopyEr; " Failed to copy error string for native"...
0x180053348  mov     r8d, 183h
0x18005334e  jmp     loc_1800532BF
0x180053353  mov     rax, [rdi]
0x180053356  lea     rdx, [rbp+var_18]
0x18005335a  mov     rcx, rdi
0x18005335d  mov     rax, [rax+40h]
0x180053361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053366  mov     ebx, eax
0x180053368  test    eax, eax
0x18005336a  jns     short loc_18005338B
0x18005336c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180053373  jz      loc_18005358B
0x180053379  lea     rax, aFailedToGetFil; " Failed to get filename for native prop"...
0x180053380  mov     r8d, 18Dh
0x180053386  jmp     loc_1800532BF
0x18005338b  mov     rdx, [rbp+var_18]
0x18005338f  lea     rcx, [rsi+100h]
0x180053396  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18005339c  mov     ebx, eax
0x18005339e  test    eax, eax
0x1800533a0  jns     short loc_1800533C1
0x1800533a2  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800533a9  jz      loc_18005358B
0x1800533af  lea     rax, aFailedToCopyFi; " Failed to copy filename for native pro"...
0x1800533b6  mov     r8d, 197h
0x1800533bc  jmp     loc_1800532BF
0x1800533c1  mov     rax, [rdi]
0x1800533c4  lea     rdx, [rbp+arg_0]
0x1800533c8  mov     rcx, rdi
0x1800533cb  mov     rax, [rax+38h]
0x1800533cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800533d4  mov     ebx, eax
0x1800533d6  test    eax, eax
0x1800533d8  jns     short loc_1800533F9
0x1800533da  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800533e1  jz      loc_18005358B
0x1800533e7  lea     rax, aFailedToGetLin; " Failed to get line number for native p"...
0x1800533ee  mov     r8d, 1A1h
0x1800533f4  jmp     loc_1800532BF
0x1800533f9  mov     eax, [rbp+arg_0]
0x1800533fc  lea     rdx, [rbp+var_10]
0x180053400  mov     [rsi+0C4h], eax
0x180053406  mov     rcx, rdi
0x180053409  mov     rax, [rdi]
0x18005340c  mov     rax, [rax+18h]
0x180053410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053415  mov     ebx, eax
0x180053417  test    eax, eax
0x180053419  jns     short loc_18005343A
0x18005341b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180053422  jz      loc_18005358B
0x180053428  lea     rax, aFailedToGetThe_3; " Failed to get the invalid value string"...
0x18005342f  mov     r8d, 1ADh
0x180053435  jmp     loc_1800532BF
0x18005343a  mov     rdx, [rbp+var_10]
0x18005343e  lea     rcx, [rsi+80h]
0x180053445  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18005344b  mov     ebx, eax
0x18005344d  test    eax, eax
0x18005344f  jns     short loc_180053470
0x180053451  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180053458  jz      loc_18005358B
0x18005345e  lea     rax, aFailedToCopyTh; " Failed to copy the invalid value strin"...
0x180053465  mov     r8d, 1B7h
0x18005346b  jmp     loc_1800532BF
0x180053470  mov     rax, [rdi]
0x180053473  lea     rdx, [rbp+arg_18]
0x180053477  mov     rcx, rdi
0x18005347a  mov     rax, [rax+28h]
0x18005347e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053483  mov     ebx, eax
0x180053485  test    eax, eax
0x180053487  jns     short loc_1800534A8
0x180053489  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180053490  jz      loc_18005358B
0x180053496  lea     rax, aFailedToGetVal_0; " Failed to get validation parameter cou"...
0x18005349d  mov     r8d, 1C1h
0x1800534a3  jmp     loc_1800532BF
0x1800534a8  mov     ecx, [rbp+arg_18]
0x1800534ab  mov     eax, 8
0x1800534b0  mul     rcx
0x1800534b3  mov     [rsi+0C0h], ecx
0x1800534b9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800534c0  cmovb   rax, rcx
0x1800534c4  mov     rcx, rax; unsigned __int64
0x1800534c7  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800534cc  mov     [rsi+0B8h], rax
0x1800534d3  test    rax, rax
0x1800534d6  jnz     short loc_180053509
0x1800534d8  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800534df  mov     ebx, 8007000Eh
0x1800534e4  jz      loc_18005358B
0x1800534ea  lea     rax, aOutOfMemoryTry; " Out of memory trying to allocate param"...
0x1800534f1  mov     r8d, 1CDh
0x1800534f7  mov     [rsp+60h+var_38], rax
0x1800534fc  mov     [rsp+60h+var_40], 8007000Eh
0x180053504  jmp     loc_1800532C8
0x180053509  xor     r14d, r14d
0x18005350c  cmp     [rsi+0C0h], r14d
0x180053513  jbe     short loc_18005358B
0x180053515  mov     rax, [rdi]
0x180053518  lea     r8, [rbp+var_8]
0x18005351c  mov     edx, r14d
0x18005351f  mov     rcx, rdi
0x180053522  mov     rax, [rax+30h]
0x180053526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005352b  mov     ebx, eax
0x18005352d  test    eax, eax
0x18005352f  jns     short loc_180053570
0x180053531  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180053538  jz      short loc_180053570
0x18005353a  mov     rcx, cs:g_pDebug
0x180053541  lea     rax, aFailedToGetVal; " Failed to get validation failure param"...
0x180053548  mov     [rsp+60h+var_30], r14d
0x18005354d  lea     r9, aConfigErrorIni_2; "CONFIG_ERROR::Initialize"
0x180053554  mov     [rsp+60h+var_38], rax
0x180053559  lea     rdx, aServercommonIn_53; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180053560  mov     r8d, 1DBh
0x180053566  mov     [rsp+60h+var_40], ebx
0x18005356a  call    cs:__imp_PuDbgPrintError
0x180053570  mov     rcx, [rsi+0B8h]
0x180053577  mov     rax, [rbp+var_8]
0x18005357b  mov     [rcx+r14*8], rax
0x18005357f  inc     r14d
0x180053582  cmp     r14d, [rsi+0C0h]
0x180053589  jb      short loc_180053515
0x18005358b  lea     r11, [rsp+60h+var_s0]
0x180053590  mov     eax, ebx
0x180053592  mov     rbx, [r11+28h]
0x180053596  mov     rsi, [r11+30h]
0x18005359a  mov     rsp, r11
0x18005359d  pop     r14
0x18005359f  pop     rdi
0x1800535a0  pop     rbp
0x1800535a1  retn
```
