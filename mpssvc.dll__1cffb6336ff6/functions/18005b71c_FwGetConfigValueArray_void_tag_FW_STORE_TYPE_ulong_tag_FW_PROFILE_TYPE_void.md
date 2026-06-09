# FwGetConfigValueArray(void *,_tag_FW_STORE_TYPE,ulong,_tag_FW_PROFILE_TYPE,void * *)

- ea: `0x18005b71c`
- end: `0x18005b85c`
- name: `?FwGetConfigValueArray@@YAJPEAXW4_tag_FW_STORE_TYPE@@KW4_tag_FW_PROFILE_TYPE@@PEAPEAX@Z`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005e920`
- `0x18005ecb0`

## callees

- `0x18000af3c`
- `0x18005b71c`
- `0x1800670c0`
- `0x18006f520`

## import_xrefs

- `fwbase!FwAlloc` at `0x18005b7da`
- `fwbase!FwAlloc` at `0x18005b7da`
- `fwbase!FwFree` at `0x18005b7d0`
- `fwbase!FwFree` at `0x18005b825`
- `fwbase!FwFree` at `0x18005b7d0`
- `fwbase!FwFree` at `0x18005b825`
- `FWPolicyIOMgr!FwGetConfig` at `0x18005b79f`
- `FWPolicyIOMgr!FwGetConfig` at `0x18005b79f`
- `FWPolicyIOMgr!FwGetGlobalConfig` at `0x18005b7be`
- `FWPolicyIOMgr!FwGetGlobalConfig` at `0x18005b7be`

## string_xrefs

- `0x18005b76f`: `mpssvc.dll`

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
          WPP_e2321870bb8f37110138dfc56d389809_Traceguids,
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
0x18005b71c  push    rbx
0x18005b71e  push    rbp
0x18005b71f  push    rsi
0x18005b720  push    rdi
0x18005b721  push    r12
0x18005b723  push    r14
0x18005b725  push    r15
0x18005b727  sub     rsp, 40h
0x18005b72b  mov     rax, cs:__security_cookie
0x18005b732  xor     rax, rsp
0x18005b735  mov     [rsp+78h+var_40], rax
0x18005b73a  mov     r14, [rsp+78h+arg_20]
0x18005b742  xor     edi, edi
0x18005b744  mov     [rsp+78h+var_48], 0
0x18005b74c  mov     r12d, r9d
0x18005b74f  mov     r15d, r8d
0x18005b752  mov     esi, edx
0x18005b754  mov     rbp, rcx
0x18005b757  test    rcx, rcx
0x18005b75a  jz      short loc_18005B760
0x18005b75c  test    edx, edx
0x18005b75e  jmp     short loc_18005B76B
0x18005b760  lea     eax, [rdx-1]
0x18005b763  cmp     eax, 1
0x18005b766  jbe     short loc_18005B784
0x18005b768  cmp     esi, 0Bh
0x18005b76b  jz      short loc_18005B784
0x18005b76d  xor     edx, edx
0x18005b76f  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x18005b776  test    rbp, rbp
0x18005b779  mov     r8d, esi
0x18005b77c  setz    dl
0x18005b77f  call    MicrosoftTelemetryAssertTriggeredArgs
0x18005b784  lea     rax, [rsp+78h+var_48]
0x18005b789  test    rbp, rbp
0x18005b78c  jz      short loc_18005B7A7
0x18005b78e  mov     r9, rdi
0x18005b791  mov     [rsp+78h+var_58], rax
0x18005b796  mov     r8d, r12d
0x18005b799  mov     edx, r15d
0x18005b79c  mov     rcx, rbp
0x18005b79f  call    cs:__imp_FwGetConfig
0x18005b7a5  jmp     short loc_18005B7C4
0x18005b7a7  mov     [rsp+78h+var_50], rax
0x18005b7ac  mov     ecx, 1
0x18005b7b1  mov     r9d, r15d
0x18005b7b4  mov     [rsp+78h+var_58], rdi
0x18005b7b9  xor     r8d, r8d
0x18005b7bc  mov     edx, esi
0x18005b7be  call    cs:__imp_FwGetGlobalConfig
0x18005b7c4  mov     ebx, eax
0x18005b7c6  cmp     eax, 800700EAh
0x18005b7cb  jnz     short loc_18005B81E
0x18005b7cd  mov     rcx, rdi
0x18005b7d0  call    cs:__imp_FwFree
0x18005b7d6  mov     ecx, [rsp+78h+var_48]
0x18005b7da  call    cs:__imp_FwAlloc
0x18005b7e0  mov     rdi, rax
0x18005b7e3  test    rax, rax
0x18005b7e6  jnz     short loc_18005B784
0x18005b7e8  mov     ebx, 8007000Eh
0x18005b7ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b7f4  lea     rax, WPP_GLOBAL_Control
0x18005b7fb  cmp     rcx, rax
0x18005b7fe  jz      short loc_18005B83E
0x18005b800  test    byte ptr [rcx+1Ch], 1
0x18005b804  jz      short loc_18005B83E
0x18005b806  mov     rcx, [rcx+10h]
0x18005b80a  lea     edx, [rdi+6Fh]
0x18005b80d  mov     r9d, ebx
0x18005b810  lea     r8, WPP_e2321870bb8f37110138dfc56d389809_Traceguids
0x18005b817  call    WPP_SF_d
0x18005b81c  jmp     short loc_18005B83E
0x18005b81e  test    ebx, ebx
0x18005b820  jns     short loc_18005B83B
0x18005b822  mov     rcx, rdi
0x18005b825  call    cs:__imp_FwFree
0x18005b82b  xor     edi, edi
0x18005b82d  mov     eax, 80070002h
0x18005b832  cmp     ebx, 8007000Dh
0x18005b838  cmovz   ebx, eax
0x18005b83b  mov     [r14], rdi
0x18005b83e  mov     eax, ebx
0x18005b840  mov     rcx, [rsp+78h+var_40]
0x18005b845  xor     rcx, rsp; StackCookie
0x18005b848  call    __security_check_cookie
0x18005b84d  add     rsp, 40h
0x18005b851  pop     r15
0x18005b853  pop     r14
0x18005b855  pop     r12
0x18005b857  pop     rdi
0x18005b858  pop     rsi
0x18005b859  pop     rbp
0x18005b85a  pop     rbx
0x18005b85b  retn
```
