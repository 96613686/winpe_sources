# IcpGetKeyHelper(unsigned __int64 *,unsigned __int64,ulong)

- ea: `0x18002a4fc`
- end: `0x18002a6b4`
- name: `?IcpGetKeyHelper@@YAJPEA_K_KK@Z`
- size: `440`
- prototype: `__int64 __fastcall(HCRYPTKEY *phKey, HCRYPTPROV hProv, ALG_ID Algid)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180029fc0`

## callees

- `0x18002937c`
- `0x18002a4fc`

## import_xrefs

- `ADVAPI32!CryptGetUserKey` at `0x18002a54d`
- `ADVAPI32!CryptGetUserKey` at `0x18002a5bf`
- `ADVAPI32!CryptGetUserKey` at `0x18002a54d`
- `ADVAPI32!CryptGetUserKey` at `0x18002a5bf`
- `ADVAPI32!CryptGenKey` at `0x18002a60e`
- `ADVAPI32!CryptGenKey` at `0x18002a60e`
- `KERNEL32!LeaveCriticalSection` at `0x18002a6a3`
- `KERNEL32!LeaveCriticalSection` at `0x18002a6a3`
- `KERNEL32!EnterCriticalSection` at `0x18002a5b1`
- `KERNEL32!EnterCriticalSection` at `0x18002a5b1`
- `IisRTL!PuDbgPrint` at `0x18002a59d`
- `IisRTL!PuDbgPrint` at `0x18002a5fd`
- `IisRTL!PuDbgPrint` at `0x18002a653`
- `IisRTL!PuDbgPrint` at `0x18002a696`
- `IisRTL!PuDbgPrint` at `0x18002a59d`
- `IisRTL!PuDbgPrint` at `0x18002a5fd`
- `IisRTL!PuDbgPrint` at `0x18002a653`
- `IisRTL!PuDbgPrint` at `0x18002a696`

## string_xrefs

- `0x18002a58b`: `IcpGetKeyHelper.CryptGetUserKey (advapi32.dll) failed err=0x%x.toast.\n`
- `0x18002a641`: `IcpGetKeyHelper.CryptGenKey (advapi32.dll) failed err=0x%x.\n`

## pseudocode

```c
__int64 __fastcall IcpGetKeyHelper(HCRYPTKEY *phKey, HCRYPTPROV hProv, ALG_ID Algid)
{
  HCRYPTKEY v6; // rax
  int LastError; // eax
  int v9; // ebx
  int v10; // eax

  if ( dword_180048964 )
  {
    if ( CryptGetUserKey(hProv, Algid, phKey) )
      return 0;
    LastError = IcpGetLastError();
    v9 = LastError;
    if ( LastError == -2146893811 )
    {
      v9 = 0;
      EnterCriticalSection(&IcpGlobals);
      if ( !CryptGetUserKey(hProv, Algid, phKey) )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\mb\\crypto\\key.cxx",
            1594,
            "IcpGetKeyHelper",
            "IcpGetKeyHelper.CryptGetUserKey:failed, lets try to generate another key.\n");
        if ( CryptGenKey(hProv, Algid, 0, phKey) )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "inetsrv\\iis\\mb\\crypto\\key.cxx",
              1608,
              "IcpGetKeyHelper",
              "IcpGetKeyHelper.CryptGenKey:key generated.\n");
        }
        else
        {
          v10 = IcpGetLastError();
          v9 = v10;
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrint(
              g_pDebug,
              "inetsrv\\iis\\mb\\crypto\\key.cxx",
              1604,
              "IcpGetKeyHelper",
              "IcpGetKeyHelper.CryptGenKey (advapi32.dll) failed err=0x%x.\n",
              v10);
          if ( v9 < 0 )
            *phKey = 0;
        }
      }
      LeaveCriticalSection(&IcpGlobals);
    }
    else if ( (g_dwDebugFlags & 3) != 0 )
    {
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\crypto\\key.cxx",
        1563,
        "IcpGetKeyHelper",
        "IcpGetKeyHelper.CryptGetUserKey (advapi32.dll) failed err=0x%x.toast.\n",
        LastError);
    }
    return (unsigned int)v9;
  }
  else
  {
    if ( hProv == 1984918096 )
    {
      v6 = 1801020747;
      if ( Algid != 1 )
        v6 = 1799842131;
      *phKey = v6;
      return 0;
    }
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18002a4fc  push    rbx
0x18002a4fe  push    rbp
0x18002a4ff  push    rsi
0x18002a500  push    rdi
0x18002a501  sub     rsp, 38h
0x18002a505  cmp     cs:dword_180048964, 0
0x18002a50c  mov     ebp, r8d
0x18002a50f  mov     rsi, rdx
0x18002a512  mov     rdi, rcx
0x18002a515  jnz     short loc_18002A545
0x18002a517  cmp     rdx, 764F7250h
0x18002a51e  jnz     short loc_18002A53B
0x18002a520  cmp     r8d, 1
0x18002a524  mov     eax, 6B59654Bh
0x18002a529  mov     ecx, 6B476953h
0x18002a52e  cmovnz  eax, ecx
0x18002a531  mov     [rdi], rax
0x18002a534  xor     eax, eax
0x18002a536  jmp     loc_18002A6AB
0x18002a53b  mov     eax, 80070057h
0x18002a540  jmp     loc_18002A6AB
0x18002a545  mov     r8, rdi; phUserKey
0x18002a548  mov     edx, ebp; dwKeySpec
0x18002a54a  mov     rcx, rsi; hProv
0x18002a54d  call    cs:__imp_CryptGetUserKey
0x18002a553  test    eax, eax
0x18002a555  jnz     short loc_18002A534
0x18002a557  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x18002a55c  mov     ebx, eax
0x18002a55e  cmp     eax, 8009000Dh
0x18002a563  jz      short loc_18002A5A8
0x18002a565  test    byte ptr cs:g_dwDebugFlags, 3
0x18002a56c  jz      loc_18002A6A9
0x18002a572  mov     rcx, cs:g_pDebug
0x18002a579  lea     r9, aIcpgetkeyhelpe_2; "IcpGetKeyHelper"
0x18002a580  mov     [rsp+58h+var_30], eax
0x18002a584  lea     rdx, aInetsrvIisMbCr_1; "inetsrv\\iis\\mb\\crypto\\key.cxx"
0x18002a58b  lea     rax, aIcpgetkeyhelpe_3; "IcpGetKeyHelper.CryptGetUserKey (advapi"...
0x18002a592  mov     r8d, 61Bh
0x18002a598  mov     [rsp+58h+var_38], rax
0x18002a59d  call    cs:__imp_PuDbgPrint
0x18002a5a3  jmp     loc_18002A6A9
0x18002a5a8  lea     rcx, ?IcpGlobals@@3U_IC_GLOBALS@@A; lpCriticalSection
0x18002a5af  xor     ebx, ebx
0x18002a5b1  call    cs:__imp_EnterCriticalSection
0x18002a5b7  mov     r8, rdi; phUserKey
0x18002a5ba  mov     edx, ebp; dwKeySpec
0x18002a5bc  mov     rcx, rsi; hProv
0x18002a5bf  call    cs:__imp_CryptGetUserKey
0x18002a5c5  test    eax, eax
0x18002a5c7  jnz     loc_18002A69C
0x18002a5cd  test    byte ptr cs:g_dwDebugFlags, 3
0x18002a5d4  jz      short loc_18002A603
0x18002a5d6  mov     rcx, cs:g_pDebug
0x18002a5dd  lea     rax, aIcpgetkeyhelpe_1; "IcpGetKeyHelper.CryptGetUserKey:failed,"...
0x18002a5e4  lea     r9, aIcpgetkeyhelpe_2; "IcpGetKeyHelper"
0x18002a5eb  mov     [rsp+58h+var_38], rax
0x18002a5f0  mov     r8d, 63Ah
0x18002a5f6  lea     rdx, aInetsrvIisMbCr_1; "inetsrv\\iis\\mb\\crypto\\key.cxx"
0x18002a5fd  call    cs:__imp_PuDbgPrint
0x18002a603  mov     r9, rdi; phKey
0x18002a606  xor     r8d, r8d; dwFlags
0x18002a609  mov     edx, ebp; Algid
0x18002a60b  mov     rcx, rsi; hProv
0x18002a60e  call    cs:__imp_CryptGenKey
0x18002a614  test    eax, eax
0x18002a616  jnz     short loc_18002A666
0x18002a618  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x18002a61d  test    byte ptr cs:g_dwDebugFlags, 3
0x18002a624  mov     ebx, eax
0x18002a626  jz      short loc_18002A659
0x18002a628  mov     rcx, cs:g_pDebug
0x18002a62f  lea     r9, aIcpgetkeyhelpe_2; "IcpGetKeyHelper"
0x18002a636  mov     [rsp+58h+var_30], eax
0x18002a63a  lea     rdx, aInetsrvIisMbCr_1; "inetsrv\\iis\\mb\\crypto\\key.cxx"
0x18002a641  lea     rax, aIcpgetkeyhelpe; "IcpGetKeyHelper.CryptGenKey (advapi32.d"...
0x18002a648  mov     r8d, 644h
0x18002a64e  mov     [rsp+58h+var_38], rax
0x18002a653  call    cs:__imp_PuDbgPrint
0x18002a659  test    ebx, ebx
0x18002a65b  jns     short loc_18002A69C
0x18002a65d  mov     qword ptr [rdi], 0
0x18002a664  jmp     short loc_18002A69C
0x18002a666  test    byte ptr cs:g_dwDebugFlags, 3
0x18002a66d  jz      short loc_18002A69C
0x18002a66f  mov     rcx, cs:g_pDebug
0x18002a676  lea     rax, aIcpgetkeyhelpe_0; "IcpGetKeyHelper.CryptGenKey:key generat"...
0x18002a67d  lea     r9, aIcpgetkeyhelpe_2; "IcpGetKeyHelper"
0x18002a684  mov     [rsp+58h+var_38], rax
0x18002a689  mov     r8d, 648h
0x18002a68f  lea     rdx, aInetsrvIisMbCr_1; "inetsrv\\iis\\mb\\crypto\\key.cxx"
0x18002a696  call    cs:__imp_PuDbgPrint
0x18002a69c  lea     rcx, ?IcpGlobals@@3U_IC_GLOBALS@@A; lpCriticalSection
0x18002a6a3  call    cs:__imp_LeaveCriticalSection
0x18002a6a9  mov     eax, ebx
0x18002a6ab  add     rsp, 38h
0x18002a6af  pop     rdi
0x18002a6b0  pop     rsi
0x18002a6b1  pop     rbp
0x18002a6b2  pop     rbx
0x18002a6b3  retn
```
