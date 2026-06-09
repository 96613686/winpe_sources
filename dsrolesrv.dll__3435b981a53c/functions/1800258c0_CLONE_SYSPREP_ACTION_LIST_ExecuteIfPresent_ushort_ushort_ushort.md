# CLONE_SYSPREP_ACTION_LIST::ExecuteIfPresent(ushort *,ushort *,ushort *)

- ea: `0x1800258c0`
- end: `0x180025a6e`
- name: `?ExecuteIfPresent@CLONE_SYSPREP_ACTION_LIST@@QEAAKPEAG00@Z`
- size: `430`
- prototype: `__int64 __fastcall(wchar_t **this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180026914`

## callees

- `0x180025848`
- `0x180025890`
- `0x1800258c0`
- `0x180025b94`
- `0x1800260b4`
- `0x18002c01e`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800259c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800259c5`
- `WDSCORE!WdsSetupLogMessageW` at `0x180025a40`
- `WDSCORE!WdsSetupLogMessageW` at `0x180025a40`
- `WDSCORE!CurrentIP` at `0x1800259cd`
- `WDSCORE!CurrentIP` at `0x1800259cd`

## string_xrefs

- `0x1800259e3`: `Skipping calling %ws:%hs because the component is not installed`
- `0x18002593e`: `$(runtime.windows)\system32\capisp.dll`
- `0x180025967`: `$(runtime.windows)\system32\capisp.dll`

## pseudocode

```c
__int64 __fastcall CLONE_SYSPREP_ACTION_LIST::ExecuteIfPresent(
        wchar_t **this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  unsigned int v5; // esi
  int i; // ebx
  DWORD LastError; // edi
  __int64 v8; // rbx
  struct tagLOG_PARTIAL_MSG *v9; // rax
  WCHAR Dst[260]; // [rsp+70h] [rbp-638h] BYREF
  _BYTE v12[264]; // [rsp+278h] [rbp-430h] BYREF
  wchar_t String2[260]; // [rsp+380h] [rbp-328h] BYREF
  _BYTE v14[264]; // [rsp+588h] [rbp-120h] BYREF

  memset_0(String2, 0, sizeof(String2));
  memset_0(v14, 0, 0x100u);
  memset_0(Dst, 0, sizeof(Dst));
  memset_0(v12, 0, 0x100u);
  v5 = CLONE_SYSPREP_MODULE::InitializeSysprepModule(
         String2,
         (wchar_t *)L"$(runtime.windows)\\system32\\capisp.dll",
         L"CryptoSysPrep_Specialize");
  if ( !v5 )
  {
    v5 = CLONE_SYSPREP_MODULE::InitializeSysprepModule(
           Dst,
           (wchar_t *)L"$(runtime.windows)\\system32\\capisp.dll",
           L"CryptoSysPrep_Specialize_Clone");
    if ( !v5 )
    {
      for ( i = 0; i < *((_DWORD *)this + 1024); ++i )
      {
        if ( !CLONE_SYSPREP_MODULE::CompareSysprepModule(this[i], String2) )
          return CLONE_SYSPREP_MODULE::ExecuteModule((CLONE_SYSPREP_MODULE *)Dst);
      }
      LastError = GetLastError();
      v8 = CurrentIP();
      v9 = ConstructPartialMsgW(0x4000000, "Skipping calling %ws:%hs because the component is not installed", Dst, v12);
      WdsSetupLogMessageW(
        v9,
        983040,
        L"D",
        0,
        603,
        L"ds\\ds\\src\\util\\clonelib\\clsysprep.cxx",
        L"CLONE_SYSPREP_ACTION_LIST::ExecuteIfPresent",
        v8,
        LastError,
        0,
        0);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800258c0  mov     [rsp+arg_8], rbx
0x1800258c5  mov     [rsp+arg_10], rsi
0x1800258ca  push    rdi
0x1800258cb  sub     rsp, 6A0h
0x1800258d2  mov     rax, cs:__security_cookie
0x1800258d9  xor     rax, rsp
0x1800258dc  mov     [rsp+6A8h+var_18], rax
0x1800258e4  mov     rdi, rcx
0x1800258e7  mov     esi, 208h
0x1800258ec  mov     r8d, esi; Size
0x1800258ef  xor     edx, edx; Val
0x1800258f1  lea     rcx, [rsp+6A8h+String2]; void *
0x1800258f9  call    memset_0
0x1800258fe  mov     ebx, 100h
0x180025903  mov     r8d, ebx; Size
0x180025906  xor     edx, edx; Val
0x180025908  lea     rcx, [rsp+6A8h+var_120]; void *
0x180025910  call    memset_0
0x180025915  mov     r8d, esi; Size
0x180025918  xor     edx, edx; Val
0x18002591a  lea     rcx, [rsp+6A8h+Dst]; void *
0x18002591f  call    memset_0
0x180025924  mov     r8d, ebx; Size
0x180025927  xor     edx, edx; Val
0x180025929  lea     rcx, [rsp+6A8h+var_430]; void *
0x180025931  call    memset_0
0x180025936  nop
0x180025937  lea     r8, WideCharStr; "CryptoSysPrep_Specialize"
0x18002593e  lea     rdx, aRuntimeWindows; "$(runtime.windows)\\system32\\capisp.dl"...
0x180025945  lea     rcx, [rsp+6A8h+String2]; lpDst
0x18002594d  call    ?InitializeSysprepModule@CLONE_SYSPREP_MODULE@@QEAAKPEAG0@Z; CLONE_SYSPREP_MODULE::InitializeSysprepModule(ushort *,ushort *)
0x180025952  mov     esi, eax
0x180025954  mov     [rsp+6A8h+var_648], eax
0x180025958  test    eax, eax
0x18002595a  jnz     loc_180025A47
0x180025960  lea     r8, aCryptosysprepS_0; "CryptoSysPrep_Specialize_Clone"
0x180025967  lea     rdx, aRuntimeWindows; "$(runtime.windows)\\system32\\capisp.dl"...
0x18002596e  lea     rcx, [rsp+6A8h+Dst]; lpDst
0x180025973  call    ?InitializeSysprepModule@CLONE_SYSPREP_MODULE@@QEAAKPEAG0@Z; CLONE_SYSPREP_MODULE::InitializeSysprepModule(ushort *,ushort *)
0x180025978  mov     esi, eax
0x18002597a  mov     [rsp+6A8h+var_648], eax
0x18002597e  test    eax, eax
0x180025980  jnz     loc_180025A47
0x180025986  xor     ebx, ebx
0x180025988  mov     [rsp+6A8h+var_644], ebx
0x18002598c  cmp     ebx, [rdi+1000h]
0x180025992  jge     short loc_1800259C5
0x180025994  movsxd  rcx, ebx
0x180025997  lea     rdx, [rsp+6A8h+String2]; String2
0x18002599f  mov     rcx, [rdi+rcx*8]; String1
0x1800259a3  call    ?CompareSysprepModule@CLONE_SYSPREP_MODULE@@SAHPEBV1@0@Z; CLONE_SYSPREP_MODULE::CompareSysprepModule(CLONE_SYSPREP_MODULE const *,CLONE_SYSPREP_MODULE const *)
0x1800259a8  test    eax, eax
0x1800259aa  jnz     short loc_1800259C1
0x1800259ac  lea     rcx, [rsp+6A8h+Dst]; this
0x1800259b1  call    ?ExecuteModule@CLONE_SYSPREP_MODULE@@QEAAKXZ; CLONE_SYSPREP_MODULE::ExecuteModule(void)
0x1800259b6  mov     esi, eax
0x1800259b8  mov     [rsp+6A8h+var_648], eax
0x1800259bc  jmp     loc_180025A47
0x1800259c1  inc     ebx
0x1800259c3  jmp     short loc_180025988
0x1800259c5  call    cs:__imp_GetLastError
0x1800259cb  mov     edi, eax
0x1800259cd  call    cs:__imp_CurrentIP
0x1800259d3  mov     rbx, rax
0x1800259d6  lea     r9, [rsp+6A8h+var_430]
0x1800259de  lea     r8, [rsp+6A8h+Dst]
0x1800259e3  lea     rdx, aSkippingCallin; "Skipping calling %ws:%hs because the co"...
0x1800259ea  mov     ecx, 4000000h; unsigned int
0x1800259ef  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800259f4  mov     [rsp+6A8h+var_658], 0
0x1800259fc  mov     [rsp+6A8h+var_660], 0
0x180025a05  mov     [rsp+6A8h+var_668], edi
0x180025a09  mov     [rsp+6A8h+var_670], rbx
0x180025a0e  lea     rcx, aCloneSysprepAc; "CLONE_SYSPREP_ACTION_LIST::ExecuteIfPre"...
0x180025a15  mov     [rsp+6A8h+var_678], rcx
0x180025a1a  lea     rcx, aDsDsSrcUtilClo; "ds\\ds\\src\\util\\clonelib\\clsysprep."...
0x180025a21  mov     [rsp+6A8h+var_680], rcx
0x180025a26  mov     [rsp+6A8h+var_688], 25Bh
0x180025a2e  xor     r9d, r9d
0x180025a31  lea     r8, aD_0; "D"
0x180025a38  mov     edx, 0F0000h
0x180025a3d  mov     rcx, rax
0x180025a40  call    cs:__imp_WdsSetupLogMessageW
0x180025a46  nop
0x180025a47  mov     eax, esi
0x180025a49  mov     rcx, [rsp+6A8h+var_18]
0x180025a51  xor     rcx, rsp; StackCookie
0x180025a54  call    __security_check_cookie
0x180025a59  lea     r11, [rsp+6A8h+var_8]
0x180025a61  mov     rbx, [r11+18h]
0x180025a65  mov     rsi, [r11+20h]
0x180025a69  mov     rsp, r11
0x180025a6c  pop     rdi
0x180025a6d  retn
0x18002c735  push    rbp
0x18002c737  sub     rsp, 60h
0x18002c73b  mov     rbp, rdx
0x18002c73e  add     rsp, 60h
0x18002c742  pop     rbp
0x18002c743  retn
```
