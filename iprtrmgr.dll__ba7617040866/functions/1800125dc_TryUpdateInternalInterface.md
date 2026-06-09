# TryUpdateInternalInterface

- ea: `0x1800125dc`
- end: `0x18001290e`
- name: `TryUpdateInternalInterface`
- size: `818`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180024d28`

## callees

- `0x180011790`
- `0x1800125dc`
- `0x18001a110`
- `0x18001be68`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!Sleep` at `0x1800127a5`
- `KERNEL32!Sleep` at `0x1800127a5`

## string_xrefs

- `0x18001268e`: `Entered: TryUpdateInternalInterface`
- `0x1800126ce`: `TryUpdateInternalInterface: Server adapter not init`
- `0x1800127c8`: `TryUpdateInternalInterface: Address already present for %ws`
- `0x180012735`: `TryUpdateInternalInterface: Err %d trying to update binding for %ws`
- `0x180012848`: `TryUpdateInternalInterface: Error %d bringing up server if`
- `0x1800128b7`: `Leaving: TryUpdateInternalInterface`

## pseudocode

```c
__int64 __fastcall TryUpdateInternalInterface(__int64 a1, int a2)
{
  int *v3; // rsi
  __int128 *v4; // r9
  int v5; // r14d
  __int128 *v6; // r9
  __int64 result; // rax
  __int64 v8; // r9
  __int128 *v9; // r9
  __int64 v10; // r8
  __int128 *v11; // r9
  __int128 *v12; // r9
  __int128 *v13; // r9
  __int128 v14; // [rsp+38h] [rbp-C8h] BYREF
  int v15; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v16; // [rsp+4Ch] [rbp-B4h]
  __int128 v17; // [rsp+5Ch] [rbp-A4h]
  int v18; // [rsp+6Ch] [rbp-94h]
  int v19; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v20[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v3 = &g_bUninitServerv4;
  if ( !a2 )
    v3 = &g_bUninitServerv6;
  v19 = 0;
  memset_0(v20, 0, sizeof(v20));
  v15 = 0;
  v16 = 0;
  v18 = 0;
  v17 = 0;
  v14 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v15) = 0;
    v4 = &v14;
    if ( a1 != -688 )
      LODWORD(v4) = a1 + 688;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Entered: TryUpdateInternalInterface",
      (_DWORD)v4,
      *(_QWORD *)(a1 + 72),
      (__int64)&v15);
  }
  v5 = 0;
  while ( *v3 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v6 = &v14;
      LOWORD(v15) = 0;
      if ( a1 != -688 )
        LODWORD(v6) = a1 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)L"TryUpdateInternalInterface: Server adapter not init",
        (_DWORD)v6,
        *(_QWORD *)(a1 + 72),
        (__int64)&v15);
    }
    result = UpdateBindingInformation(a1);
    if ( (_DWORD)result )
    {
      if ( (_DWORD)result == 1227 && *(_DWORD *)(a1 + 512) == 1 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v10 = *(_QWORD *)(a1 + 72);
          LOWORD(v19) = 0;
          LOWORD(v15) = 0;
          FormatRRASErrorString(&v19, L"TryUpdateInternalInterface: Address already present for %ws", v10);
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          {
            v11 = &v14;
            if ( a1 != -688 )
              LODWORD(v11) = a1 + 688;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrmgrParamTraceInfo,
              (unsigned int)&v19,
              (_DWORD)v11,
              *(_QWORD *)(a1 + 72),
              (__int64)&v15);
          }
        }
        *v3 = 0;
        break;
      }
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v8 = *(_QWORD *)(a1 + 72);
        LOWORD(v19) = 0;
        LOWORD(v15) = 0;
        result = FormatRRASErrorString(
                   &v19,
                   L"TryUpdateInternalInterface: Err %d trying to update binding for %ws",
                   (unsigned int)result,
                   v8);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v9 = &v14;
          if ( a1 != -688 )
            LODWORD(v9) = a1 + 688;
          result = McTemplateU0zjzz_EventWriteTransfer(
                     (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                     (unsigned int)RasRtrmgrParamTraceInfo,
                     (unsigned int)&v19,
                     (_DWORD)v9,
                     *(_QWORD *)(a1 + 72),
                     (__int64)&v15);
        }
      }
      if ( ++v5 )
      {
        if ( *v3 )
          goto LABEL_37;
        break;
      }
      Sleep(0xBB8u);
    }
    else
    {
      *v3 = 0;
    }
  }
  result = LanEtcInterfaceDownToUp(a1);
  if ( (_DWORD)result )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v19) = 0;
      LOWORD(v15) = 0;
      result = FormatRRASErrorString(
                 &v19,
                 L"TryUpdateInternalInterface: Error %d bringing up server if",
                 (unsigned int)result);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v12 = &v14;
        if ( a1 != -688 )
          LODWORD(v12) = a1 + 688;
        result = McTemplateU0zjzz_EventWriteTransfer(
                   (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                   (unsigned int)RasRtrMgrParamTraceError,
                   (unsigned int)&v19,
                   (_DWORD)v12,
                   *(_QWORD *)(a1 + 72),
                   (__int64)&v15);
      }
    }
  }
LABEL_37:
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    v13 = &v14;
    LOWORD(v15) = 0;
    if ( a1 != -688 )
      LODWORD(v13) = a1 + 688;
    return McTemplateU0zjzz_EventWriteTransfer(
             (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
             (unsigned int)RasRtrmgrParamTraceInfo,
             (unsigned int)L"Leaving: TryUpdateInternalInterface",
             (_DWORD)v13,
             *(_QWORD *)(a1 + 72),
             (__int64)&v15);
  }
  return result;
}

```

## disassembly

```asm
0x1800125dc  mov     [rsp-8+arg_8], rbx
0x1800125e1  mov     [rsp-8+arg_10], rsi
0x1800125e6  push    rbp
0x1800125e7  push    rdi
0x1800125e8  push    r12
0x1800125ea  push    r13
0x1800125ec  push    r14
0x1800125ee  lea     rbp, [rsp-780h]
0x1800125f6  sub     rsp, 880h
0x1800125fd  mov     rax, cs:__security_cookie
0x180012604  xor     rax, rsp
0x180012607  mov     [rbp+7A0h+var_30], rax
0x18001260e  test    edx, edx
0x180012610  lea     rax, g_bUninitServerv6
0x180012617  mov     rbx, rcx
0x18001261a  lea     rsi, g_bUninitServerv4
0x180012621  cmovz   rsi, rax
0x180012625  lea     rcx, [rsp+8A0h+var_82C]; void *
0x18001262a  xor     eax, eax
0x18001262c  xor     edx, edx; Val
0x18001262e  mov     r8d, 7FCh; Size
0x180012634  mov     [rsp+8A0h+var_830], eax
0x180012638  call    memset_0
0x18001263d  xor     eax, eax
0x18001263f  lea     r13, RasRtrmgrParamTraceInfo
0x180012646  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18001264d  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180012654  xorps   xmm0, xmm0
0x180012657  mov     [rsp+8A0h+var_858], eax
0x18001265b  movups  [rsp+8A0h+var_854], xmm0
0x180012660  mov     [rsp+8A0h+var_834], eax
0x180012664  lea     rdi, [rbx+2B0h]
0x18001266b  movups  [rsp+8A0h+var_844], xmm0
0x180012670  movups  [rsp+8A0h+var_868], xmm0
0x180012675  jz      short loc_1800126AD
0x180012677  mov     word ptr [rsp+8A0h+var_858], ax
0x18001267c  lea     r9, [rsp+8A0h+var_868]
0x180012681  lea     rax, [rsp+8A0h+var_858]
0x180012686  test    rdi, rdi
0x180012689  mov     [rsp+8A0h+var_878], rax
0x18001268e  lea     r8, aEnteredTryupda; "Entered: TryUpdateInternalInterface"
0x180012695  mov     rax, [rbx+48h]
0x180012699  cmovnz  r9, rdi
0x18001269d  mov     rdx, r13
0x1800126a0  mov     [rsp+8A0h+var_880], rax
0x1800126a5  mov     rcx, r12
0x1800126a8  call    McTemplateU0zjzz_EventWriteTransfer
0x1800126ad  xor     r14d, r14d
0x1800126b0  cmp     dword ptr [rsi], 0
0x1800126b3  jz      loc_180012831
0x1800126b9  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x1800126c0  jz      short loc_180012701
0x1800126c2  xor     eax, eax
0x1800126c4  lea     r9, [rsp+8A0h+var_868]
0x1800126c9  mov     word ptr [rsp+8A0h+var_858], ax
0x1800126ce  lea     r8, aTryupdateinter_2; "TryUpdateInternalInterface: Server adap"...
0x1800126d5  lea     rax, [rbx+2B0h]
0x1800126dc  mov     rdx, r13
0x1800126df  test    rax, rax
0x1800126e2  mov     rcx, r12
0x1800126e5  cmovnz  r9, rax
0x1800126e9  lea     rax, [rsp+8A0h+var_858]
0x1800126ee  mov     [rsp+8A0h+var_878], rax
0x1800126f3  mov     rax, [rbx+48h]
0x1800126f7  mov     [rsp+8A0h+var_880], rax
0x1800126fc  call    McTemplateU0zjzz_EventWriteTransfer
0x180012701  mov     rcx, rbx
0x180012704  call    UpdateBindingInformation
0x180012709  mov     r8d, eax
0x18001270c  test    eax, eax
0x18001270e  jz      loc_1800127B0
0x180012714  cmp     eax, 4CBh
0x180012719  jnz     short loc_180012728
0x18001271b  cmp     dword ptr [rbx+200h], 1
0x180012722  jz      loc_1800127BB
0x180012728  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18001272f  jge     short loc_180012793
0x180012731  mov     r9, [rbx+48h]
0x180012735  lea     rdx, aTryupdateinter; "TryUpdateInternalInterface: Err %d tryi"...
0x18001273c  xor     ecx, ecx
0x18001273e  xor     eax, eax
0x180012740  mov     word ptr [rsp+8A0h+var_830], cx
0x180012745  lea     rcx, [rsp+8A0h+var_830]
0x18001274a  mov     word ptr [rsp+8A0h+var_858], ax
0x18001274f  call    FormatRRASErrorString
0x180012754  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18001275b  jge     short loc_180012793
0x18001275d  lea     rax, [rbx+2B0h]
0x180012764  mov     rdx, r13
0x180012767  test    rax, rax
0x18001276a  lea     r9, [rsp+8A0h+var_868]
0x18001276f  lea     r8, [rsp+8A0h+var_830]
0x180012774  mov     rcx, r12
0x180012777  cmovnz  r9, rax
0x18001277b  lea     rax, [rsp+8A0h+var_858]
0x180012780  mov     [rsp+8A0h+var_878], rax
0x180012785  mov     rax, [rbx+48h]
0x180012789  mov     [rsp+8A0h+var_880], rax
0x18001278e  call    McTemplateU0zjzz_EventWriteTransfer
0x180012793  inc     r14d
0x180012796  cmp     r14d, 1
0x18001279a  jnb     loc_18001282C
0x1800127a0  mov     ecx, 0BB8h; dwMilliseconds
0x1800127a5  call    cs:__imp_Sleep
0x1800127ab  jmp     loc_1800126B0
0x1800127b0  mov     dword ptr [rsi], 0
0x1800127b6  jmp     loc_1800126B0
0x1800127bb  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800127c2  jge     short loc_180012824
0x1800127c4  mov     r8, [rbx+48h]
0x1800127c8  lea     rdx, aTryupdateinter_0; "TryUpdateInternalInterface: Address alr"...
0x1800127cf  xor     eax, eax
0x1800127d1  lea     rcx, [rsp+8A0h+var_830]
0x1800127d6  mov     word ptr [rsp+8A0h+var_830], ax
0x1800127db  mov     word ptr [rsp+8A0h+var_858], ax
0x1800127e0  call    FormatRRASErrorString
0x1800127e5  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800127ec  jge     short loc_180012824
0x1800127ee  lea     rax, [rbx+2B0h]
0x1800127f5  mov     rdx, r13
0x1800127f8  test    rax, rax
0x1800127fb  lea     r9, [rsp+8A0h+var_868]
0x180012800  lea     r8, [rsp+8A0h+var_830]
0x180012805  mov     rcx, r12
0x180012808  cmovnz  r9, rax
0x18001280c  lea     rax, [rsp+8A0h+var_858]
0x180012811  mov     [rsp+8A0h+var_878], rax
0x180012816  mov     rax, [rbx+48h]
0x18001281a  mov     [rsp+8A0h+var_880], rax
0x18001281f  call    McTemplateU0zjzz_EventWriteTransfer
0x180012824  mov     dword ptr [rsi], 0
0x18001282a  jmp     short loc_180012831
0x18001282c  cmp     dword ptr [rsi], 0
0x18001282f  jnz     short loc_1800128A2
0x180012831  mov     rcx, rbx
0x180012834  call    LanEtcInterfaceDownToUp
0x180012839  test    eax, eax
0x18001283b  jz      short loc_1800128A2
0x18001283d  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180012844  jz      short loc_1800128A2
0x180012846  xor     ecx, ecx
0x180012848  lea     rdx, aTryupdateinter_1; "TryUpdateInternalInterface: Error %d br"...
0x18001284f  mov     word ptr [rsp+8A0h+var_830], cx
0x180012854  mov     r8d, eax
0x180012857  mov     word ptr [rsp+8A0h+var_858], cx
0x18001285c  lea     rcx, [rsp+8A0h+var_830]
0x180012861  call    FormatRRASErrorString
0x180012866  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001286d  jz      short loc_1800128A2
0x18001286f  lea     rax, [rsp+8A0h+var_858]
0x180012874  test    rdi, rdi
0x180012877  mov     [rsp+8A0h+var_878], rax
0x18001287c  lea     r9, [rsp+8A0h+var_868]
0x180012881  mov     rax, [rbx+48h]
0x180012885  lea     r8, [rsp+8A0h+var_830]
0x18001288a  cmovnz  r9, rdi
0x18001288e  mov     [rsp+8A0h+var_880], rax
0x180012893  lea     rdx, RasRtrMgrParamTraceError
0x18001289a  mov     rcx, r12
0x18001289d  call    McTemplateU0zjzz_EventWriteTransfer
0x1800128a2  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x1800128a9  jz      short loc_1800128E3
0x1800128ab  xor     eax, eax
0x1800128ad  lea     r9, [rsp+8A0h+var_868]
0x1800128b2  mov     word ptr [rsp+8A0h+var_858], ax
0x1800128b7  lea     r8, aLeavingTryupda; "Leaving: TryUpdateInternalInterface"
0x1800128be  lea     rax, [rsp+8A0h+var_858]
0x1800128c3  test    rdi, rdi
0x1800128c6  mov     [rsp+8A0h+var_878], rax
0x1800128cb  mov     rdx, r13
0x1800128ce  mov     rax, [rbx+48h]
0x1800128d2  cmovnz  r9, rdi
0x1800128d6  mov     rcx, r12
0x1800128d9  mov     [rsp+8A0h+var_880], rax
0x1800128de  call    McTemplateU0zjzz_EventWriteTransfer
0x1800128e3  mov     rcx, [rbp+7A0h+var_30]
0x1800128ea  xor     rcx, rsp; StackCookie
0x1800128ed  call    __security_check_cookie
0x1800128f2  lea     r11, [rsp+8A0h+var_20]
0x1800128fa  mov     rbx, [r11+38h]
0x1800128fe  mov     rsi, [r11+40h]
0x180012902  mov     rsp, r11
0x180012905  pop     r14
0x180012907  pop     r13
0x180012909  pop     r12
0x18001290b  pop     rdi
0x18001290c  pop     rbp
0x18001290d  retn
```
