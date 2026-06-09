# HandleNTLMBlocking

- ea: `0x140025b70`
- end: `0x140025dea`
- name: `HandleNTLMBlocking`
- size: `634`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14000e800`

## callees

- `0x14001b4c0`
- `0x140025b70`
- `0x14002e584`
- `0x14002ebe0`
- `0x14002ed54`
- `0x140037120`

## import_xrefs

- `ksecdd!SspiExcludePackage` at `0x140025bc7`
- `ksecdd!SspiExcludePackage` at `0x140025bc7`
- `ksecdd!MapSecurityError` at `0x140025bd8`
- `ksecdd!MapSecurityError` at `0x140025bd8`

## pseudocode

```c
__int64 __fastcall HandleNTLMBlocking(__int64 a1, void **a2, __int64 a3, int a4)
{
  void *v5; // rcx
  unsigned int v8; // ebx
  SECURITY_STATUS v9; // r15d
  NTSTATUS v10; // eax
  PDEVICE_OBJECT *v11; // rdx
  char v13; // [rsp+30h] [rbp-49h] BYREF
  __int64 v14; // [rsp+38h] [rbp-41h] BYREF
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE ppNewAuthIdentity; // [rsp+40h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+50h] [rbp-29h] BYREF
  __int64 *v17; // [rsp+70h] [rbp-9h]
  __int64 v18; // [rsp+78h] [rbp-1h]
  char *v19; // [rsp+80h] [rbp+7h]
  __int64 v20; // [rsp+88h] [rbp+Fh]

  v5 = *a2;
  ppNewAuthIdentity = 0;
  if ( !v5 )
  {
    v8 = 0;
    *a2 = Smb2NoNetNtlmAuthData;
    goto LABEL_9;
  }
  v9 = SspiExcludePackage(v5, L"netntlm", &ppNewAuthIdentity);
  v10 = MapSecurityError(v9);
  v8 = v10;
  if ( v10 >= 0 )
  {
    *a2 = ppNewAuthIdentity;
LABEL_9:
    v11 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_981a12f1532a3df13e243e2e48204374_Traceguids, a1);
    }
    if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x80000000) != 0 )
      McTemplateK0qhzr1_EtwWriteTransfer(*(_WORD *)a1 >> 1, (_DWORD)v11, a3, a4, *(_WORD *)a1 >> 1, *(_QWORD *)(a1 + 8));
    if ( a4 )
    {
      if ( a4 == 1 && !Smb2NoNetNtlmFromGlobalSettingTelemtryLogged )
      {
        if ( (unsigned int)dword_140046050 > 5
          && (qword_140046060 & 0x400000000000LL) != 0
          && (qword_140046068 & 0x400000000000LL) == qword_140046068 )
        {
          v14 = 1;
          v17 = &v14;
          v18 = 8;
          v19 = &v13;
          v13 = 1;
          v20 = 1;
          tlgWriteAgg(0x400000000000LL, (unsigned __int8 *)&word_140040376, a3, 4u, (unsigned __int8 *)&v16);
        }
        Smb2NoNetNtlmFromGlobalSettingTelemtryLogged = 1;
      }
    }
    else if ( !Smb2NoNetNtlmFromNetUseSettingTelemtryLogged )
    {
      if ( (unsigned int)dword_140046050 > 5
        && (qword_140046060 & 0x400000000000LL) != 0
        && (qword_140046068 & 0x400000000000LL) == qword_140046068 )
      {
        v14 = 1;
        v17 = &v14;
        v18 = 8;
        v19 = &v13;
        v13 = 1;
        v20 = 1;
        tlgWriteAgg(0x400000000000LL, (unsigned __int8 *)&byte_1400403B9, a3, 4u, (unsigned __int8 *)&v16);
      }
      Smb2NoNetNtlmFromNetUseSettingTelemtryLogged = 1;
    }
    return v8;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_LL(WPP_GLOBAL_Control->AttachedDevice, 13, a3, (unsigned int)v10, v9);
  }
  return v8;
}

```

## disassembly

```asm
0x140025b70  push    rbp
0x140025b72  push    rbx
0x140025b73  push    rsi
0x140025b74  push    rdi
0x140025b75  push    r12
0x140025b77  push    r14
0x140025b79  push    r15
0x140025b7b  lea     rbp, [rsp-27h]
0x140025b80  sub     rsp, 0A0h
0x140025b87  mov     rax, cs:__security_cookie
0x140025b8e  xor     rax, rsp
0x140025b91  mov     [rbp+57h+var_40], rax
0x140025b95  xor     r12d, r12d
0x140025b98  mov     r14, rcx
0x140025b9b  mov     rcx, [rdx]; AuthIdentity
0x140025b9e  mov     edi, r9d
0x140025ba1  mov     [rbp+57h+ppNewAuthIdentity], r12
0x140025ba5  mov     rsi, rdx
0x140025ba8  test    rcx, rcx
0x140025bab  jnz     short loc_140025BBC
0x140025bad  lea     rax, Smb2NoNetNtlmAuthData
0x140025bb4  mov     ebx, r12d
0x140025bb7  mov     [rdx], rax
0x140025bba  jmp     short loc_140025C39
0x140025bbc  lea     r8, [rbp+57h+ppNewAuthIdentity]; ppNewAuthIdentity
0x140025bc0  lea     rdx, pszPackageName; "netntlm"
0x140025bc7  call    cs:__imp_SspiExcludePackage
0x140025bce  nop     dword ptr [rax+rax+00h]
0x140025bd3  mov     ecx, eax; SecStatus
0x140025bd5  mov     r15d, eax
0x140025bd8  call    cs:__imp_MapSecurityError
0x140025bdf  nop     dword ptr [rax+rax+00h]
0x140025be4  mov     ebx, eax
0x140025be6  test    eax, eax
0x140025be8  jns     short loc_140025C32
0x140025bea  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140025bf1  lea     rdx, WPP_GLOBAL_Control
0x140025bf8  cmp     rcx, rdx
0x140025bfb  jz      loc_140025DC9
0x140025c01  mov     edx, [rcx+2Ch]
0x140025c04  test    dl, 1
0x140025c07  jz      loc_140025DC9
0x140025c0d  cmp     byte ptr [rcx+29h], 1
0x140025c11  jb      loc_140025DC9
0x140025c17  mov     rcx, [rcx+18h]
0x140025c1b  mov     edx, 0Dh
0x140025c20  mov     r9d, eax
0x140025c23  mov     dword ptr [rsp+0D0h+var_B0], r15d
0x140025c28  call    WPP_SF_LL
0x140025c2d  jmp     loc_140025DC9
0x140025c32  mov     rax, [rbp+57h+ppNewAuthIdentity]
0x140025c36  mov     [rsi], rax
0x140025c39  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140025c40  lea     rdx, WPP_GLOBAL_Control
0x140025c47  cmp     rcx, rdx
0x140025c4a  jz      short loc_140025C71
0x140025c4c  mov     eax, [rcx+2Ch]
0x140025c4f  test    al, 8
0x140025c51  jz      short loc_140025C71
0x140025c53  cmp     byte ptr [rcx+29h], 4
0x140025c57  jb      short loc_140025C71
0x140025c59  mov     rcx, [rcx+18h]
0x140025c5d  lea     r8, WPP_981a12f1532a3df13e243e2e48204374_Traceguids
0x140025c64  mov     edx, 0Eh
0x140025c69  mov     r9, r14
0x140025c6c  call    WPP_SF_Z
0x140025c71  cmp     byte ptr cs:WPP_MAIN_CB.Queue+13h, r12b
0x140025c78  jge     short loc_140025C97
0x140025c7a  movzx   ecx, word ptr [r14]
0x140025c7e  mov     r9d, edi
0x140025c81  mov     rax, [r14+8]
0x140025c85  shr     cx, 1
0x140025c88  mov     [rsp+0D0h+var_A8], rax
0x140025c8d  mov     word ptr [rsp+0D0h+var_B0], cx
0x140025c92  call    McTemplateK0qhzr1_EtwWriteTransfer
0x140025c97  test    edi, edi
0x140025c99  jnz     loc_140025D32
0x140025c9f  cmp     cs:Smb2NoNetNtlmFromNetUseSettingTelemtryLogged, r12b
0x140025ca6  jnz     loc_140025DC9
0x140025cac  mov     eax, cs:dword_140046050
0x140025cb2  cmp     eax, 5
0x140025cb5  jbe     short loc_140025D26
0x140025cb7  mov     rdx, cs:qword_140046068
0x140025cbe  mov     rcx, 400000000000h; int
0x140025cc8  mov     rax, cs:qword_140046060
0x140025ccf  test    rcx, rax
0x140025cd2  jz      short loc_140025D26
0x140025cd4  mov     rax, rdx
0x140025cd7  and     rax, rcx
0x140025cda  cmp     rax, rdx
0x140025cdd  jnz     short loc_140025D26
0x140025cdf  lea     rax, [rbp+57h+var_98]
0x140025ce3  mov     [rbp+57h+var_98], 1
0x140025ceb  mov     [rbp+57h+var_60], rax
0x140025cef  lea     rdx, byte_1400403B9; int
0x140025cf6  lea     rax, [rbp+57h+var_A0]
0x140025cfa  mov     [rbp+57h+var_58], 8
0x140025d02  mov     [rbp+57h+var_50], rax
0x140025d06  mov     r9d, 4; int
0x140025d0c  lea     rax, [rbp+57h+var_80]
0x140025d10  mov     [rbp+57h+var_A0], 1
0x140025d14  mov     [rsp+0D0h+var_B0], rax; PEVENT_DATA_DESCRIPTOR
0x140025d19  mov     [rbp+57h+var_48], 1
0x140025d21  call    _tlgWriteAgg
0x140025d26  mov     cs:Smb2NoNetNtlmFromNetUseSettingTelemtryLogged, 1
0x140025d2d  jmp     loc_140025DC9
0x140025d32  cmp     edi, 1
0x140025d35  jnz     loc_140025DC9
0x140025d3b  cmp     cs:Smb2NoNetNtlmFromGlobalSettingTelemtryLogged, r12b
0x140025d42  jnz     loc_140025DC9
0x140025d48  mov     eax, cs:dword_140046050
0x140025d4e  cmp     eax, 5
0x140025d51  jbe     short loc_140025DC2
0x140025d53  mov     rdx, cs:qword_140046068
0x140025d5a  mov     rcx, 400000000000h; int
0x140025d64  mov     rax, cs:qword_140046060
0x140025d6b  test    rcx, rax
0x140025d6e  jz      short loc_140025DC2
0x140025d70  mov     rax, rdx
0x140025d73  and     rax, rcx
0x140025d76  cmp     rax, rdx
0x140025d79  jnz     short loc_140025DC2
0x140025d7b  lea     rax, [rbp+57h+var_98]
0x140025d7f  mov     [rbp+57h+var_98], 1
0x140025d87  mov     [rbp+57h+var_60], rax
0x140025d8b  lea     rdx, word_140040376; int
0x140025d92  lea     rax, [rbp+57h+var_A0]
0x140025d96  mov     [rbp+57h+var_58], 8
0x140025d9e  mov     [rbp+57h+var_50], rax
0x140025da2  mov     r9d, 4; int
0x140025da8  lea     rax, [rbp+57h+var_80]
0x140025dac  mov     [rbp+57h+var_A0], dil
0x140025db0  mov     [rsp+0D0h+var_B0], rax; PEVENT_DATA_DESCRIPTOR
0x140025db5  mov     [rbp+57h+var_48], 1
0x140025dbd  call    _tlgWriteAgg
0x140025dc2  mov     cs:Smb2NoNetNtlmFromGlobalSettingTelemtryLogged, 1
0x140025dc9  mov     eax, ebx
0x140025dcb  mov     rcx, [rbp+57h+var_40]
0x140025dcf  xor     rcx, rsp; StackCookie
0x140025dd2  call    __security_check_cookie
0x140025dd7  add     rsp, 0A0h
0x140025dde  pop     r15
0x140025de0  pop     r14
0x140025de2  pop     r12
0x140025de4  pop     rdi
0x140025de5  pop     rsi
0x140025de6  pop     rbx
0x140025de7  pop     rbp
0x140025de8  retn
```
