# CUserProfileRoamingProvider::_IsBypassPathNeeded(int,int *)

- ea: `0x180016a1c`
- end: `0x180016b62`
- name: `?_IsBypassPathNeeded@CUserProfileRoamingProvider@@AEAAJHPEAH@Z`
- size: `326`
- prototype: `int __fastcall(CUserProfileRoamingProvider *this, int, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180008258`
- `0x180011880`

## callees

- `0x180005960`
- `0x180006774`
- `0x180006a9c`
- `0x180006b18`
- `0x18000a520`
- `0x180016158`
- `0x180016a1c`

## import_xrefs

- `ext-ms-win-fs-cscapi-l1-1-1!OfflineFilesQueryStatus` at `0x180016aa0`
- `ext-ms-win-fs-cscapi-l1-1-1!OfflineFilesQueryStatus` at `0x180016aa0`

## string_xrefs

- `0x180016aae`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`
- `0x180016ae7`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`

## pseudocode

```c
int __fastcall CUserProfileRoamingProvider::_IsBypassPathNeeded(CUserProfileRoamingProvider *this, int a2, int *a3)
{
  int v6; // ecx
  int IsShareAutoCached; // ebx
  int v8; // r8d
  DWORD v9; // eax
  __int64 v11; // rdx
  unsigned int v12; // [rsp+20h] [rbp-40h]
  int v13; // [rsp+30h] [rbp-30h] BYREF
  BOOL pbActive; // [rsp+34h] [rbp-2Ch] BYREF
  int v15; // [rsp+38h] [rbp-28h] BYREF
  unsigned int v16[4]; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  *a3 = 0;
  v13 = 0;
  IsShareAutoCached = CUserProfileRoamingProvider::_IsShareAutoCached(this, &v13);
  if ( IsShareAutoCached >= 0 && v13 && a2 && (Microsoft_Windows_User_Profiles_ServiceEnableBits & 4) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(v6, (unsigned int)EVENT_CSC_ON_PROFILE_SHARE, v8, 1, (__int64)v16);
  pbActive = 0;
  v9 = OfflineFilesQueryStatus(&pbActive, 0);
  if ( v9 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x23A,
             (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
             (const char *)v9,
             v12);
  if ( pbActive )
  {
    if ( IsShareAutoCached == -2147024843 || IsShareAutoCached == -2147022586 )
      return IsShareAutoCached;
    if ( IsShareAutoCached < 0 )
    {
      v11 = 578;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
        (const char *)(unsigned int)IsShareAutoCached,
        v12);
      return IsShareAutoCached;
    }
    if ( v13 )
      goto LABEL_20;
    v13 = 0;
    v15 = 0;
    IsShareAutoCached = CUserProfileRoamingProvider::_GetCscStatusOfProfilePath(this, &v13, &v15);
    if ( IsShareAutoCached < 0 )
    {
      v11 = 589;
      goto LABEL_13;
    }
    if ( v13 || v15 )
LABEL_20:
      *a3 = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180016a1c  mov     [rsp-18h+arg_8], rbx
0x180016a21  mov     [rsp-18h+arg_18], rsi
0x180016a26  push    rbp
0x180016a27  push    r14
0x180016a29  push    r15
0x180016a2b  mov     rbp, rsp
0x180016a2e  sub     rsp, 60h
0x180016a32  mov     rax, cs:__security_cookie
0x180016a39  xor     rax, rsp
0x180016a3c  mov     [rbp+var_10], rax
0x180016a40  mov     esi, edx
0x180016a42  mov     dword ptr [r8], 0
0x180016a49  lea     rdx, [rbp+var_30]; int *
0x180016a4d  mov     [rbp+var_30], 0
0x180016a54  mov     r14, r8
0x180016a57  mov     r15, rcx
0x180016a5a  call    ?_IsShareAutoCached@CUserProfileRoamingProvider@@AEAAJPEAH@Z; CUserProfileRoamingProvider::_IsShareAutoCached(int *)
0x180016a5f  mov     ebx, eax
0x180016a61  test    eax, eax
0x180016a63  js      short loc_180016A93
0x180016a65  cmp     [rbp+var_30], 0
0x180016a69  jz      short loc_180016A93
0x180016a6b  test    esi, esi
0x180016a6d  jz      short loc_180016A93
0x180016a6f  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 4
0x180016a76  jz      short loc_180016A93
0x180016a78  lea     rax, [rbp+var_20]
0x180016a7c  mov     r9d, 1
0x180016a82  lea     rdx, EVENT_CSC_ON_PROFILE_SHARE
0x180016a89  mov     qword ptr [rsp+60h+var_40], rax; int
0x180016a8e  call    McGenEventWrite_EtwEventWriteTransfer
0x180016a93  xor     edx, edx; pbEnabled
0x180016a95  mov     [rbp+pbActive], 0
0x180016a9c  lea     rcx, [rbp+pbActive]; pbActive
0x180016aa0  call    cs:__imp_OfflineFilesQueryStatus
0x180016aa6  test    eax, eax
0x180016aa8  jz      short loc_180016AC4
0x180016aaa  mov     rcx, [rbp+18h]; this
0x180016aae  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180016ab5  mov     r9d, eax; char *
0x180016ab8  mov     edx, 23Ah; void *
0x180016abd  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180016ac2  jmp     short loc_180016B40
0x180016ac4  cmp     [rbp+pbActive], 0
0x180016ac8  jz      short loc_180016B3E
0x180016aca  cmp     ebx, 80070035h
0x180016ad0  jz      short loc_180016AF6
0x180016ad2  cmp     ebx, 80070906h
0x180016ad8  jz      short loc_180016AF6
0x180016ada  test    ebx, ebx
0x180016adc  jns     short loc_180016AFA
0x180016ade  mov     edx, 242h; void *
0x180016ae3  mov     rcx, [rbp+18h]; this
0x180016ae7  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180016aee  mov     r9d, ebx; char *
0x180016af1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016af6  mov     eax, ebx
0x180016af8  jmp     short loc_180016B40
0x180016afa  cmp     [rbp+var_30], 0
0x180016afe  jnz     short loc_180016B37
0x180016b00  lea     r8, [rbp+var_28]; int *
0x180016b04  mov     [rbp+var_30], 0
0x180016b0b  lea     rdx, [rbp+var_30]; int *
0x180016b0f  mov     [rbp+var_28], 0
0x180016b16  mov     rcx, r15; this
0x180016b19  call    ?_GetCscStatusOfProfilePath@CUserProfileRoamingProvider@@AEAAJPEAH0@Z; CUserProfileRoamingProvider::_GetCscStatusOfProfilePath(int *,int *)
0x180016b1e  mov     ebx, eax
0x180016b20  test    eax, eax
0x180016b22  jns     short loc_180016B2B
0x180016b24  mov     edx, 24Dh
0x180016b29  jmp     short loc_180016AE3
0x180016b2b  cmp     [rbp+var_30], 0
0x180016b2f  jnz     short loc_180016B37
0x180016b31  cmp     [rbp+var_28], 0
0x180016b35  jz      short loc_180016B3E
0x180016b37  mov     dword ptr [r14], 1
0x180016b3e  xor     eax, eax
0x180016b40  mov     rcx, [rbp+var_10]
0x180016b44  xor     rcx, rsp; StackCookie
0x180016b47  call    __security_check_cookie
0x180016b4c  lea     r11, [rsp+60h+var_s0]
0x180016b51  mov     rbx, [r11+28h]
0x180016b55  mov     rsi, [r11+38h]
0x180016b59  mov     rsp, r11
0x180016b5c  pop     r15
0x180016b5e  pop     r14
0x180016b60  pop     rbp
0x180016b61  retn
```
