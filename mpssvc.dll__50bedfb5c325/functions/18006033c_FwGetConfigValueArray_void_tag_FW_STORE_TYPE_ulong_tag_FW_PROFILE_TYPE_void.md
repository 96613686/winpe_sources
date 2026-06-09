# FwGetConfigValueArray(void *,_tag_FW_STORE_TYPE,ulong,_tag_FW_PROFILE_TYPE,void * *)

- ea: `0x18006033c`
- end: `0x18006049b`
- name: `?FwGetConfigValueArray@@YAJPEAXW4_tag_FW_STORE_TYPE@@KW4_tag_FW_PROFILE_TYPE@@PEAPEAX@Z`
- size: `351`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180062c84`
- `0x180063034`

## callees

- `0x18000a710`
- `0x18006033c`
- `0x18006a710`
- `0x1800729c0`

## import_xrefs

- `fwbase!FwAlloc` at `0x18006040c`
- `fwbase!FwAlloc` at `0x18006040c`
- `fwbase!FwFree` at `0x1800603fc`
- `fwbase!FwFree` at `0x18006045d`
- `fwbase!FwFree` at `0x1800603fc`
- `fwbase!FwFree` at `0x18006045d`
- `FWPolicyIOMgr!FwGetConfig` at `0x1800603bf`
- `FWPolicyIOMgr!FwGetConfig` at `0x1800603bf`
- `FWPolicyIOMgr!FwGetGlobalConfig` at `0x1800603e4`
- `FWPolicyIOMgr!FwGetGlobalConfig` at `0x1800603e4`

## string_xrefs

- `0x18006038f`: `mpssvc.dll`

## pseudocode

```c
__int64 __fastcall FwGetConfigValueArray(__int64 a1, unsigned int a2, unsigned int a3, unsigned int a4, __int64 *a5)
{
  __int64 v5; // rdi
  bool v10; // zf
  int v11; // eax
  unsigned int v12; // ebx
  unsigned int v14; // [rsp+30h] [rbp-48h] BYREF

  v5 = 0;
  v14 = 0;
  if ( a1 )
  {
    v10 = a2 == 0;
  }
  else
  {
    if ( a2 - 1 <= 1 )
      goto LABEL_7;
    v10 = a2 == 11;
  }
  if ( !v10 )
    MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", a1 == 0, a2);
LABEL_7:
  while ( 1 )
  {
    v11 = a1 ? FwGetConfig(a1, a3, a4, v5, &v14) : FwGetGlobalConfig(1, a2, 0, a3, v5, &v14);
    v12 = v11;
    if ( v11 != -2147024662 )
      break;
    FwFree(v5);
    v5 = FwAlloc(v14);
    if ( !v5 )
    {
      v12 = -2147024882;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          111,
          WPP_3d9dabe50e6b3e70315acf6b635a3004_Traceguids,
          2147942414LL);
      return v12;
    }
  }
  if ( v11 < 0 )
  {
    FwFree(v5);
    v5 = 0;
    if ( v12 == -2147024883 )
      v12 = -2147024894;
  }
  *a5 = v5;
  return v12;
}

```

## disassembly

```asm
0x18006033c  push    rbx
0x18006033e  push    rbp
0x18006033f  push    rsi
0x180060340  push    rdi
0x180060341  push    r12
0x180060343  push    r14
0x180060345  push    r15
0x180060347  sub     rsp, 40h
0x18006034b  mov     rax, cs:__security_cookie
0x180060352  xor     rax, rsp
0x180060355  mov     [rsp+78h+var_40], rax
0x18006035a  mov     r14, [rsp+78h+arg_20]
0x180060362  xor     edi, edi
0x180060364  mov     [rsp+78h+var_48], 0
0x18006036c  mov     r12d, r9d
0x18006036f  mov     r15d, r8d
0x180060372  mov     esi, edx
0x180060374  mov     rbp, rcx
0x180060377  test    rcx, rcx
0x18006037a  jz      short loc_180060380
0x18006037c  test    edx, edx
0x18006037e  jmp     short loc_18006038B
0x180060380  lea     eax, [rdx-1]
0x180060383  cmp     eax, 1
0x180060386  jbe     short loc_1800603A4
0x180060388  cmp     esi, 0Bh
0x18006038b  jz      short loc_1800603A4
0x18006038d  xor     edx, edx; __annotation("Debug", "TelemetryAssert", "(hPolicyStore != NULL && StoreType == FW_STORE_TYPE_INVALID) || (hPolicyStore == NULL && (StoreType == FW_STORE_TYPE_LOCAL || StoreType == FW_STORE_TYPE_GP_RSOP || StoreType == FW_STORE_TYPE_MDM))")
0x18006038f  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x180060396  test    rbp, rbp
0x180060399  mov     r8d, esi
0x18006039c  setz    dl
0x18006039f  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800603a4  lea     rax, [rsp+78h+var_48]
0x1800603a9  test    rbp, rbp
0x1800603ac  jz      short loc_1800603CD
0x1800603ae  mov     r9, rdi
0x1800603b1  mov     [rsp+78h+var_58], rax
0x1800603b6  mov     r8d, r12d
0x1800603b9  mov     edx, r15d
0x1800603bc  mov     rcx, rbp
0x1800603bf  call    cs:__imp_FwGetConfig
0x1800603c6  nop     dword ptr [rax+rax+00h]
0x1800603cb  jmp     short loc_1800603F0
0x1800603cd  mov     [rsp+78h+var_50], rax
0x1800603d2  mov     ecx, 1
0x1800603d7  mov     r9d, r15d
0x1800603da  mov     [rsp+78h+var_58], rdi
0x1800603df  xor     r8d, r8d
0x1800603e2  mov     edx, esi
0x1800603e4  call    cs:__imp_FwGetGlobalConfig
0x1800603eb  nop     dword ptr [rax+rax+00h]
0x1800603f0  mov     ebx, eax
0x1800603f2  cmp     eax, 800700EAh
0x1800603f7  jnz     short loc_180060456
0x1800603f9  mov     rcx, rdi
0x1800603fc  call    cs:__imp_FwFree
0x180060403  nop     dword ptr [rax+rax+00h]
0x180060408  mov     ecx, [rsp+78h+var_48]
0x18006040c  call    cs:__imp_FwAlloc
0x180060413  nop     dword ptr [rax+rax+00h]
0x180060418  mov     rdi, rax
0x18006041b  test    rax, rax
0x18006041e  jnz     short loc_1800603A4
0x180060420  mov     ebx, 8007000Eh
0x180060425  mov     rcx, cs:WPP_GLOBAL_Control
0x18006042c  lea     rax, WPP_GLOBAL_Control
0x180060433  cmp     rcx, rax
0x180060436  jz      short loc_18006047C
0x180060438  test    byte ptr [rcx+1Ch], 1
0x18006043c  jz      short loc_18006047C
0x18006043e  mov     rcx, [rcx+10h]
0x180060442  lea     edx, [rdi+6Fh]
0x180060445  mov     r9d, ebx
0x180060448  lea     r8, WPP_3d9dabe50e6b3e70315acf6b635a3004_Traceguids
0x18006044f  call    WPP_SF_d
0x180060454  jmp     short loc_18006047C
0x180060456  test    ebx, ebx
0x180060458  jns     short loc_180060479
0x18006045a  mov     rcx, rdi
0x18006045d  call    cs:__imp_FwFree
0x180060464  nop     dword ptr [rax+rax+00h]
0x180060469  xor     edi, edi
0x18006046b  mov     eax, 80070002h
0x180060470  cmp     ebx, 8007000Dh
0x180060476  cmovz   ebx, eax
0x180060479  mov     [r14], rdi
0x18006047c  mov     eax, ebx
0x18006047e  mov     rcx, [rsp+78h+var_40]
0x180060483  xor     rcx, rsp; StackCookie
0x180060486  call    __security_check_cookie
0x18006048b  add     rsp, 40h
0x18006048f  pop     r15
0x180060491  pop     r14
0x180060493  pop     r12
0x180060495  pop     rdi
0x180060496  pop     rsi
0x180060497  pop     rbp
0x180060498  pop     rbx
0x180060499  retn
```
