# _BuildNt5Ace

- ea: `0x1800241c8`
- end: `0x18002433d`
- name: `_BuildNt5Ace`
- size: `373`
- prototype: `__int64 __fastcall(int, int, int, int, PACL pAcl)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180024b90`

## callees

- `0x180004074`
- `0x1800049ac`
- `0x180017430`
- `0x1800241c8`
- `0x18002535c`

## import_xrefs

- `ADVAPI32!AddAccessDeniedAce` at `0x180024300`
- `ADVAPI32!AddAccessDeniedAce` at `0x180024300`
- `ADVAPI32!AddAccessAllowedAce` at `0x180024289`
- `ADVAPI32!AddAccessAllowedAce` at `0x180024289`
- `KERNEL32!GetLastError` at `0x180024297`
- `KERNEL32!GetLastError` at `0x18002430a`
- `KERNEL32!GetLastError` at `0x180024297`
- `KERNEL32!GetLastError` at `0x18002430a`

## pseudocode

```c
__int64 __fastcall BuildNt5Ace(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, PACL pAcl)
{
  DWORD v5; // eax
  char v6; // r10
  void *v7; // r11
  unsigned int v8; // eax
  DWORD LastError; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int16 v13; // [rsp+60h] [rbp-18h] BYREF
  int v14[4]; // [rsp+68h] [rbp-10h] BYREF

  v5 = MapNt4RightsToNt5Ace(a1, a4);
  if ( !v5 )
  {
    v13 = 70;
    v14[0] = -1072821220;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v8 = mqwcslen(L"acssctrl/secd4to5");
      CMSMQTrace::MSMQTraceEvent(
        g_pMSMQErrorLoggingTrace,
        1,
        1,
        2LL * (v8 + 1),
        L"acssctrl/secd4to5",
        2,
        &v13,
        4,
        v14,
        0,
        0);
    }
    return 3222146076LL;
  }
  if ( v6 )
  {
    if ( v6 == 1 && !AddAccessDeniedAce(pAcl, 4u, v5, v7) )
    {
      LastError = GetLastError();
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) == 0 )
        goto LABEL_11;
      v12 = 28;
      goto LABEL_10;
    }
    return 0;
  }
  if ( AddAccessAllowedAce(pAcl, 4u, v5, v7) )
    return 0;
  LastError = GetLastError();
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) == 0 )
    goto LABEL_11;
  v12 = 27;
LABEL_10:
  WPP_SF_d(v11[32], v12, &WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids, LastError);
LABEL_11:
  if ( (int)LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return LastError;
}

```

## disassembly

```asm
0x1800241c8  push    rbx
0x1800241ca  sub     rsp, 70h
0x1800241ce  mov     r10b, dl
0x1800241d1  mov     r11, r8
0x1800241d4  mov     edx, r9d
0x1800241d7  call    _MapNt4RightsToNt5Ace
0x1800241dc  test    eax, eax
0x1800241de  jnz     loc_180024271
0x1800241e4  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x1800241ec  mov     eax, 46h ; 'F'
0x1800241f1  mov     [rsp+78h+var_18], ax
0x1800241f6  mov     [rsp+78h+var_10], 0C00E0C1Ch
0x1800241fe  jz      short loc_180024267
0x180024200  lea     rbx, aAcssctrlSecd4t; "acssctrl/secd4to5"
0x180024207  mov     rcx, rbx; wchar_t *
0x18002420a  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18002420f  mov     [rsp+78h+var_28], 0
0x180024218  lea     rcx, [rsp+78h+var_18]
0x18002421d  mov     [rsp+78h+var_30], 0
0x180024226  mov     edx, 1
0x18002422b  mov     r8d, edx
0x18002422e  lea     r9d, [rax+1]
0x180024232  lea     rax, [rsp+78h+var_10]
0x180024237  add     r9, r9
0x18002423a  mov     [rsp+78h+var_38], rax
0x18002423f  mov     [rsp+78h+var_40], 4
0x180024248  mov     [rsp+78h+var_48], rcx
0x18002424d  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180024254  mov     [rsp+78h+var_50], 2
0x18002425d  mov     [rsp+78h+var_58], rbx
0x180024262  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x180024267  mov     eax, 0C00E0C1Ch
0x18002426c  jmp     loc_180024337
0x180024271  test    r10b, r10b
0x180024274  jnz     short loc_1800242E7
0x180024276  mov     rcx, [rsp+78h+pAcl]; pAcl
0x18002427e  mov     r9, r11; pSid
0x180024281  mov     r8d, eax; AccessMask
0x180024284  mov     edx, 4; dwAceRevision
0x180024289  call    cs:__imp_AddAccessAllowedAce
0x18002428f  test    eax, eax
0x180024291  jnz     loc_180024335
0x180024297  call    cs:__imp_GetLastError
0x18002429d  mov     ebx, eax
0x18002429f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800242a6  lea     rax, WPP_GLOBAL_Control
0x1800242ad  cmp     rcx, rax
0x1800242b0  jz      short loc_1800242D6
0x1800242b2  test    byte ptr [rcx+10Ch], 1
0x1800242b9  jz      short loc_1800242D6
0x1800242bb  mov     edx, 1Bh
0x1800242c0  mov     rcx, [rcx+100h]
0x1800242c7  lea     r8, WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids
0x1800242ce  mov     r9d, ebx
0x1800242d1  call    WPP_SF_d
0x1800242d6  test    ebx, ebx
0x1800242d8  jle     short loc_1800242E3
0x1800242da  movzx   ebx, bx
0x1800242dd  or      ebx, 80070000h
0x1800242e3  mov     eax, ebx
0x1800242e5  jmp     short loc_180024337
0x1800242e7  cmp     r10b, 1
0x1800242eb  jnz     short loc_180024335
0x1800242ed  mov     rcx, [rsp+78h+pAcl]; pAcl
0x1800242f5  mov     r9, r11; pSid
0x1800242f8  mov     r8d, eax; AccessMask
0x1800242fb  mov     edx, 4; dwAceRevision
0x180024300  call    cs:__imp_AddAccessDeniedAce
0x180024306  test    eax, eax
0x180024308  jnz     short loc_180024335
0x18002430a  call    cs:__imp_GetLastError
0x180024310  mov     ebx, eax
0x180024312  mov     rcx, cs:WPP_GLOBAL_Control
0x180024319  lea     rax, WPP_GLOBAL_Control
0x180024320  cmp     rcx, rax
0x180024323  jz      short loc_1800242D6
0x180024325  test    byte ptr [rcx+10Ch], 1
0x18002432c  jz      short loc_1800242D6
0x18002432e  mov     edx, 1Ch
0x180024333  jmp     short loc_1800242C0
0x180024335  xor     eax, eax
0x180024337  add     rsp, 70h
0x18002433b  pop     rbx
0x18002433c  retn
```
