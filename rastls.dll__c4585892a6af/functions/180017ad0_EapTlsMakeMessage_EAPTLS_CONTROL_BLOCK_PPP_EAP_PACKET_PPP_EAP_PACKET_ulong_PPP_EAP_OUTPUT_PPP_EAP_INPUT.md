# EapTlsMakeMessage(_EAPTLS_CONTROL_BLOCK *,_PPP_EAP_PACKET *,_PPP_EAP_PACKET *,ulong,_PPP_EAP_OUTPUT *,_PPP_EAP_INPUT *)

- ea: `0x180017ad0`
- end: `0x180017ecb`
- name: `?EapTlsMakeMessage@@YAKPEAU_EAPTLS_CONTROL_BLOCK@@PEAU_PPP_EAP_PACKET@@1KPEAU_PPP_EAP_OUTPUT@@PEAU_PPP_EAP_INPUT@@@Z`
- size: `1019`
- prototype: `unsigned int __usercall@<eax>(struct _EAPTLS_CONTROL_BLOCK *@<rcx>, struct _PPP_EAP_PACKET *@<rdx>, struct _PPP_EAP_PACKET *@<r8>, unsigned int@<r9d>, struct _PPP_EAP_OUTPUT *, struct _PPP_EAP_INPUT *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005ceb0`

## callees

- `0x180005010`
- `0x180007d00`
- `0x180010140`
- `0x180017ad0`
- `0x180017ee0`
- `0x180018080`
- `0x180052198`
- `0x180053c60`
- `0x18005de34`
- `0x180072e98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017de9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017de9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e83`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180017d3f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180017dd0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180017d3f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180017dd0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180017e62`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180017e62`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180017d02`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180017d02`
- `eapputil!EapConvertWireToHostFormat32` at `0x180017bf1`
- `eapputil!EapConvertWireToHostFormat32` at `0x180017bf1`
- `eapputil!EapConvertWireToHostFormat16` at `0x180017b86`
- `eapputil!EapConvertWireToHostFormat16` at `0x180017b86`

## pseudocode

```c
__int64 __fastcall EapTlsMakeMessage(
        struct _EAPTLS_CONTROL_BLOCK *a1,
        struct _PPP_EAP_PACKET *a2,
        struct _PPP_EAP_PACKET *a3,
        unsigned int a4,
        struct _PPP_EAP_OUTPUT *a5,
        struct _PPP_EAP_INPUT *a6)
{
  const WCHAR *v10; // r9
  BYTE Code; // r15
  BYTE v12; // al
  int v13; // edx
  int v14; // r8d
  int v15; // eax
  char v16; // al
  const char *v17; // rdi
  const char *v18; // r11
  const char *v19; // rax
  int v21; // eax
  int v22; // r15d
  int v23; // edi
  void *v24; // rcx
  DWORD LastError; // edi
  __int64 v26; // r8
  struct _EAPTLS_CONTROL_BLOCK *v27; // rcx
  __int64 v28; // rdx
  DWORD v29; // eax
  __int64 v30; // rdx
  struct _PPP_EAP_INPUT *v31; // [rsp+28h] [rbp-90h]
  int v32; // [rsp+70h] [rbp-48h]
  char v33; // [rsp+74h] [rbp-44h]
  char v34; // [rsp+78h] [rbp-40h]
  char v35; // [rsp+C0h] [rbp+8h]
  int v36; // [rsp+C8h] [rbp+10h]
  int v37; // [rsp+D0h] [rbp+18h]

  if ( a1 && a5 )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v10 = &String;
      if ( a1 != (struct _EAPTLS_CONTROL_BLOCK *)-16LL )
        v10 = (const WCHAR *)((char *)a1 + 16);
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v10);
    }
    if ( a2 )
    {
      Code = 0;
      v34 = 0;
      v33 = 0;
      if ( a2->Code <= 4u )
        Code = a2->Code;
      v35 = EapConvertWireToHostFormat16(a2->Length);
      if ( (unsigned int)FValidPacket((struct _EAPTLS_PACKET *)a2)
        && (unsigned __int8)(a2->Code - 1) <= 1u
        && a2->Data[0] == 13 )
      {
        v12 = a2[1].Code;
        v34 = 13;
        v13 = v12 & 0x80;
        v14 = v12 & 0x40;
        v37 = v13;
        v15 = v12 & 0x20;
        v32 = v14;
        v36 = a2[1].Code & 0x20;
        if ( v13 )
        {
          v16 = EapConvertWireToHostFormat32(&a2[1].Id);
          v13 = v37;
          v14 = v32;
          v33 = v16;
          v15 = v36;
        }
      }
      else
      {
        v15 = 0;
        v13 = 0;
        v14 = 0;
      }
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v17 = "S";
        if ( !v15 )
          v17 = (const char *)&dword_180087A9C;
        v18 = "M";
        v19 = "L";
        if ( !v14 )
          v18 = (const char *)&dword_180087A9C;
        if ( !v13 )
          v19 = (const char *)&dword_180087A9C;
        WPP_SF_ssdddddsss(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (__int64)off_1800842B0[Code],
          a2->Code,
          a2->Id,
          v35,
          v34,
          v33,
          (__int64)v19,
          (__int64)v18,
          (__int64)v17);
      }
    }
    if ( !(unsigned int)FValidPacket((struct _EAPTLS_PACKET *)a2) )
    {
      a5->Action = EAPACTION_NoAction;
      return 722;
    }
    v21 = *((_DWORD *)a1 + 1);
    v22 = v21 & 2;
    v23 = v21 & 1;
    if ( (v21 & 1) == 0 && (v21 & 2) == 0 && (v21 & 0x4C04) == 0 )
    {
      v24 = (void *)*((_QWORD *)a1 + 1);
      if ( v24 )
      {
        if ( !ImpersonateLoggedOnUser(v24) )
        {
          LastError = GetLastError();
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          {
            v28 = 67;
LABEL_37:
            WPP_SF_qD(*((_QWORD *)v27 + 2), v28, v26, *((_QWORD *)a1 + 1), LastError);
            goto LABEL_38;
          }
          goto LABEL_38;
        }
      }
    }
    if ( (*((_BYTE *)a1 + 4) & 4) != 0 && !SetThreadToken(0, *((HANDLE *)a1 + 1)) )
    {
      LastError = GetLastError();
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v28 = 68;
        goto LABEL_37;
      }
LABEL_38:
      a5->Action = EAPACTION_NoAction;
      return LastError;
    }
    if ( v23 )
    {
      LastError = EapTlsSMakeMessage(a1, (struct _EAPTLS_PACKET *)a2, (struct _EAPTLS_PACKET *)a3, a4, a5, v31);
    }
    else
    {
      LastError = EapTlsCMakeMessage(a1, (struct _EAPTLS_PACKET *)a2, (struct _EAPTLS_PACKET *)a3, a4, a5, a6);
      if ( *(_QWORD *)&a5->Action == 2 && (*((_DWORD *)a1 + 1) & 0x2000) == 0 )
        SetCachedCredentials(a1);
      if ( !v22 )
      {
        if ( (*((_BYTE *)a1 + 4) & 4) != 0 )
        {
LABEL_43:
          if ( SetThreadToken(0, 0) || WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            return LastError;
          v29 = GetLastError();
          v30 = 70;
LABEL_46:
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v30, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v29);
          return LastError;
        }
        if ( !RevertToSelf() )
        {
          if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            return LastError;
          v29 = GetLastError();
          v30 = 69;
          goto LABEL_46;
        }
      }
    }
    if ( (*((_BYTE *)a1 + 4) & 4) == 0 )
      return LastError;
    goto LABEL_43;
  }
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
  return 87;
}

```

## disassembly

```asm
0x180017ad0  push    rbx
0x180017ad2  push    rbp
0x180017ad3  push    rsi
0x180017ad4  push    r12
0x180017ad6  push    r13
0x180017ad8  push    r14
0x180017ada  sub     rsp, 88h
0x180017ae1  mov     r12d, r9d
0x180017ae4  mov     r13, r8
0x180017ae7  mov     r14, rdx
0x180017aea  mov     rbx, rcx
0x180017aed  test    rcx, rcx
0x180017af0  jz      loc_180017E99
0x180017af6  mov     rsi, [rsp+0B8h+arg_20]
0x180017afe  test    rsi, rsi
0x180017b01  jz      loc_180017E99
0x180017b07  mov     rcx, cs:WPP_GLOBAL_Control
0x180017b0e  lea     rbp, WPP_GLOBAL_Control
0x180017b15  cmp     rcx, rbp
0x180017b18  jz      short loc_180017B41
0x180017b1a  mov     rcx, [rcx+10h]
0x180017b1e  lea     rax, [rbx+10h]
0x180017b22  test    rax, rax
0x180017b25  lea     r9, String
0x180017b2c  mov     edx, 42h ; 'B'
0x180017b31  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x180017b38  cmovnz  r9, rax
0x180017b3c  call    WPP_SF_S
0x180017b41  mov     [rsp+0B8h+arg_18], rdi
0x180017b49  mov     [rsp+0B8h+var_38], r15
0x180017b51  test    r14, r14
0x180017b54  jz      loc_180017CC3
0x180017b5a  movzx   eax, byte ptr [r14]
0x180017b5e  lea     rcx, [r14+2]
0x180017b62  xor     r15d, r15d
0x180017b65  mov     [rsp+0B8h+arg_8], 0
0x180017b70  cmp     al, 4
0x180017b72  mov     dword ptr [rsp+0B8h+var_40], 0
0x180017b7a  mov     dword ptr [rsp+0B8h+var_44], 0
0x180017b82  cmovbe  r15d, eax
0x180017b86  call    cs:__imp_EapConvertWireToHostFormat16
0x180017b8d  nop     dword ptr [rax+rax+00h]
0x180017b92  mov     rcx, r14; struct _EAPTLS_PACKET *
0x180017b95  mov     [rsp+0B8h+arg_0], ax
0x180017b9d  call    ?FValidPacket@@YAHPEAU_EAPTLS_PACKET@@@Z; FValidPacket(_EAPTLS_PACKET *)
0x180017ba2  test    eax, eax
0x180017ba4  jz      short loc_180017C16
0x180017ba6  movzx   eax, byte ptr [r14]
0x180017baa  dec     al
0x180017bac  cmp     al, 1
0x180017bae  ja      short loc_180017C16
0x180017bb0  cmp     byte ptr [r14+4], 0Dh
0x180017bb5  jnz     short loc_180017C16
0x180017bb7  movzx   eax, byte ptr [r14+5]
0x180017bbc  mov     edx, eax
0x180017bbe  mov     dword ptr [rsp+0B8h+var_40], 0Dh
0x180017bc6  mov     r8d, eax
0x180017bc9  and     edx, 80h
0x180017bcf  and     r8d, 40h
0x180017bd3  mov     [rsp+0B8h+arg_10], edx
0x180017bda  and     eax, 20h
0x180017bdd  mov     [rsp+0B8h+var_48], r8d
0x180017be2  mov     [rsp+0B8h+arg_8], eax
0x180017be9  test    edx, edx
0x180017beb  jz      short loc_180017C22
0x180017bed  lea     rcx, [r14+6]
0x180017bf1  call    cs:__imp_EapConvertWireToHostFormat32
0x180017bf8  nop     dword ptr [rax+rax+00h]
0x180017bfd  mov     edx, [rsp+0B8h+arg_10]
0x180017c04  mov     r8d, [rsp+0B8h+var_48]
0x180017c09  mov     dword ptr [rsp+0B8h+var_44], eax
0x180017c0d  mov     eax, [rsp+0B8h+arg_8]
0x180017c14  jmp     short loc_180017C22
0x180017c16  mov     eax, [rsp+0B8h+arg_8]
0x180017c1d  mov     edx, eax
0x180017c1f  mov     r8d, eax
0x180017c22  mov     rcx, cs:WPP_GLOBAL_Control
0x180017c29  cmp     rcx, rbp
0x180017c2c  jz      loc_180017CC3
0x180017c32  mov     rcx, [rcx+10h]; LoggerHandle
0x180017c36  lea     r9, dword_180087A9C
0x180017c3d  test    eax, eax
0x180017c3f  movzx   r10d, r15b
0x180017c43  lea     rdi, aS; "S"
0x180017c4a  cmovz   rdi, r9
0x180017c4e  lea     r11, aM; "M"
0x180017c55  mov     [rsp+0B8h+var_58], rdi; __int64
0x180017c5a  lea     rax, asc_180087A88; "L"
0x180017c61  test    r8d, r8d
0x180017c64  lea     r15, off_1800842B0; "Unknown"
0x180017c6b  movzx   r8d, byte ptr [r14+1]
0x180017c70  cmovz   r11, r9
0x180017c74  test    edx, edx
0x180017c76  movzx   edx, [rsp+0B8h+arg_0]
0x180017c7e  mov     [rsp+0B8h+var_60], r11; __int64
0x180017c83  cmovz   rax, r9
0x180017c87  movzx   r9d, byte ptr [r14]
0x180017c8b  mov     [rsp+0B8h+var_68], rax; __int64
0x180017c90  mov     eax, dword ptr [rsp+0B8h+var_44]
0x180017c94  mov     dword ptr [rsp+0B8h+var_70], eax; char
0x180017c98  mov     eax, dword ptr [rsp+0B8h+var_40]
0x180017c9c  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x180017ca0  mov     rax, [r15+r10*8]
0x180017ca4  mov     dword ptr [rsp+0B8h+var_80], edx; char
0x180017ca8  mov     dword ptr [rsp+0B8h+var_88], r8d; char
0x180017cad  mov     dword ptr [rsp+0B8h+var_90], r9d; struct _PPP_EAP_INPUT *
0x180017cb2  lea     r9, aReceived; ">> Received"
0x180017cb9  mov     [rsp+0B8h+var_98], rax; __int64
0x180017cbe  call    WPP_SF_ssdddddsss
0x180017cc3  mov     rcx, r14; struct _EAPTLS_PACKET *
0x180017cc6  call    ?FValidPacket@@YAHPEAU_EAPTLS_PACKET@@@Z; FValidPacket(_EAPTLS_PACKET *)
0x180017ccb  test    eax, eax
0x180017ccd  jnz     short loc_180017CDC
0x180017ccf  mov     [rsi+4], eax
0x180017cd2  mov     eax, 2D2h
0x180017cd7  jmp     loc_180017D88
0x180017cdc  mov     eax, [rbx+4]
0x180017cdf  mov     r15d, eax
0x180017ce2  and     r15d, 2
0x180017ce6  mov     edi, eax
0x180017ce8  and     edi, 1
0x180017ceb  jnz     short loc_180017D33
0x180017ced  test    r15d, r15d
0x180017cf0  jnz     short loc_180017D33
0x180017cf2  test    eax, 4C04h
0x180017cf7  jnz     short loc_180017D33
0x180017cf9  mov     rcx, [rbx+8]; hToken
0x180017cfd  test    rcx, rcx
0x180017d00  jz      short loc_180017D33
0x180017d02  call    cs:__imp_ImpersonateLoggedOnUser
0x180017d09  nop     dword ptr [rax+rax+00h]
0x180017d0e  test    eax, eax
0x180017d10  jnz     short loc_180017D33
0x180017d12  call    cs:__imp_GetLastError
0x180017d19  nop     dword ptr [rax+rax+00h]
0x180017d1e  mov     edi, eax
0x180017d20  mov     rcx, cs:WPP_GLOBAL_Control
0x180017d27  cmp     rcx, rbp
0x180017d2a  jz      short loc_180017D7F
0x180017d2c  mov     edx, 43h ; 'C'
0x180017d31  jmp     short loc_180017D6E
0x180017d33  test    byte ptr [rbx+4], 4
0x180017d37  jz      short loc_180017DAA
0x180017d39  mov     rdx, [rbx+8]; Token
0x180017d3d  xor     ecx, ecx; Thread
0x180017d3f  call    cs:__imp_SetThreadToken
0x180017d46  nop     dword ptr [rax+rax+00h]
0x180017d4b  test    eax, eax
0x180017d4d  jnz     short loc_180017DAA
0x180017d4f  call    cs:__imp_GetLastError
0x180017d56  nop     dword ptr [rax+rax+00h]
0x180017d5b  mov     edi, eax
0x180017d5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180017d64  cmp     rcx, rbp
0x180017d67  jz      short loc_180017D7F
0x180017d69  mov     edx, 44h ; 'D'
0x180017d6e  mov     r9, [rbx+8]
0x180017d72  mov     rcx, [rcx+10h]
0x180017d76  mov     dword ptr [rsp+0B8h+var_98], edi
0x180017d7a  call    WPP_SF_qD
0x180017d7f  mov     dword ptr [rsi+4], 0
0x180017d86  mov     eax, edi
0x180017d88  mov     rdi, [rsp+0B8h+arg_18]
0x180017d90  mov     r15, [rsp+0B8h+var_38]
0x180017d98  add     rsp, 88h
0x180017d9f  pop     r14
0x180017da1  pop     r13
0x180017da3  pop     r12
0x180017da5  pop     rsi
0x180017da6  pop     rbp
0x180017da7  pop     rbx
0x180017da8  retn
0x180017daa  mov     r9d, r12d; unsigned int
0x180017dad  mov     r8, r13; struct _EAPTLS_PACKET *
0x180017db0  mov     rdx, r14; struct _EAPTLS_PACKET *
0x180017db3  mov     rcx, rbx; struct _EAPTLS_CONTROL_BLOCK *
0x180017db6  test    edi, edi
0x180017db8  jz      short loc_180017E19
0x180017dba  mov     [rsp+0B8h+var_98], rsi; struct _PPP_EAP_OUTPUT *
0x180017dbf  call    ?EapTlsSMakeMessage@@YAKPEAU_EAPTLS_CONTROL_BLOCK@@PEAU_EAPTLS_PACKET@@1KPEAU_PPP_EAP_OUTPUT@@PEAU_PPP_EAP_INPUT@@@Z; EapTlsSMakeMessage(_EAPTLS_CONTROL_BLOCK *,_EAPTLS_PACKET *,_EAPTLS_PACKET *,ulong,_PPP_EAP_OUTPUT *,_PPP_EAP_INPUT *)
0x180017dc4  mov     edi, eax
0x180017dc6  test    byte ptr [rbx+4], 4
0x180017dca  jz      short loc_180017D86
0x180017dcc  xor     edx, edx; Token
0x180017dce  xor     ecx, ecx; Thread
0x180017dd0  call    cs:__imp_SetThreadToken
0x180017dd7  nop     dword ptr [rax+rax+00h]
0x180017ddc  test    eax, eax
0x180017dde  jnz     short loc_180017D86
0x180017de0  cmp     cs:WPP_GLOBAL_Control, rbp
0x180017de7  jz      short loc_180017D86
0x180017de9  call    cs:__imp_GetLastError
0x180017df0  nop     dword ptr [rax+rax+00h]
0x180017df5  mov     edx, 46h ; 'F'
0x180017dfa  mov     rcx, cs:WPP_GLOBAL_Control
0x180017e01  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x180017e08  mov     r9d, eax
0x180017e0b  mov     rcx, [rcx+10h]
0x180017e0f  call    WPP_SF_d
0x180017e14  jmp     loc_180017D86
0x180017e19  mov     rax, [rsp+0B8h+arg_28]
0x180017e21  mov     [rsp+0B8h+var_90], rax; struct _PPP_EAP_INPUT *
0x180017e26  mov     [rsp+0B8h+var_98], rsi; struct _PPP_EAP_OUTPUT *
0x180017e2b  call    ?EapTlsCMakeMessage@@YAKPEAU_EAPTLS_CONTROL_BLOCK@@PEAU_EAPTLS_PACKET@@1KPEAU_PPP_EAP_OUTPUT@@PEAU_PPP_EAP_INPUT@@@Z; EapTlsCMakeMessage(_EAPTLS_CONTROL_BLOCK *,_EAPTLS_PACKET *,_EAPTLS_PACKET *,ulong,_PPP_EAP_OUTPUT *,_PPP_EAP_INPUT *)
0x180017e30  cmp     dword ptr [rsi+4], 2
0x180017e34  mov     edi, eax
0x180017e36  jnz     short loc_180017E4F
0x180017e38  cmp     dword ptr [rsi+8], 0
0x180017e3c  jnz     short loc_180017E4F
0x180017e3e  test    dword ptr [rbx+4], 2000h
0x180017e45  jnz     short loc_180017E4F
0x180017e47  mov     rcx, rbx; struct _EAPTLS_CONTROL_BLOCK *
0x180017e4a  call    ?SetCachedCredentials@@YAXPEAU_EAPTLS_CONTROL_BLOCK@@@Z; SetCachedCredentials(_EAPTLS_CONTROL_BLOCK *)
0x180017e4f  test    r15d, r15d
0x180017e52  jnz     loc_180017DC6
0x180017e58  test    byte ptr [rbx+4], 4
0x180017e5c  jnz     loc_180017DCC
0x180017e62  call    cs:__imp_RevertToSelf
0x180017e69  nop     dword ptr [rax+rax+00h]
0x180017e6e  test    eax, eax
0x180017e70  jnz     loc_180017DC6
0x180017e76  cmp     cs:WPP_GLOBAL_Control, rbp
0x180017e7d  jz      loc_180017D86
0x180017e83  call    cs:__imp_GetLastError
0x180017e8a  nop     dword ptr [rax+rax+00h]
0x180017e8f  mov     edx, 45h ; 'E'
0x180017e94  jmp     loc_180017DFA
0x180017e99  mov     rcx, cs:WPP_GLOBAL_Control
0x180017ea0  lea     rbp, WPP_GLOBAL_Control
0x180017ea7  cmp     rcx, rbp
0x180017eaa  jz      short loc_180017EC1
0x180017eac  mov     rcx, [rcx+10h]
0x180017eb0  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x180017eb7  mov     edx, 41h ; 'A'
0x180017ebc  call    WPP_SF_
0x180017ec1  mov     eax, 57h ; 'W'
0x180017ec6  jmp     loc_180017D98
```
