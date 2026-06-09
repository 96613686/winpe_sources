# appIsolation::InboxAppContainerManager::ValidateAppContainerOperation(void *,int,int,_SID *,_SID *,int *)

- ea: `0x1800bdad0`
- end: `0x1800bde71`
- name: `?ValidateAppContainerOperation@InboxAppContainerManager@appIsolation@@QEAAKPEAXHHPEAU_SID@@1PEAH@Z`
- size: `929`
- prototype: `__int64 __fastcall(appIsolation::InboxAppContainerManager *this, void *, int, int, struct _SID *, struct _SID *Sid1, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800620b8`

## callees

- `0x18000af3c`
- `0x18006f520`
- `0x1800bdad0`

## import_xrefs

- `ntdll!RtlIsParentOfChildAppContainer` at `0x1800bde19`
- `ntdll!RtlIsParentOfChildAppContainer` at `0x1800bde19`
- `ntdll!RtlEqualSid` at `0x1800bdb5c`
- `ntdll!RtlEqualSid` at `0x1800bdbe6`
- `ntdll!RtlEqualSid` at `0x1800bdcdd`
- `ntdll!RtlEqualSid` at `0x1800bdb5c`
- `ntdll!RtlEqualSid` at `0x1800bdbe6`
- `ntdll!RtlEqualSid` at `0x1800bdcdd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bdc20`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bdd67`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bdc20`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bdd67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bdc07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bdd4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bdc07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bdd4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bdc2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bdd71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bdc2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bdd71`
- `RPCRT4!RpcRevertToSelf` at `0x1800bdcbc`
- `RPCRT4!RpcRevertToSelf` at `0x1800bddf5`
- `RPCRT4!RpcRevertToSelf` at `0x1800bdcbc`
- `RPCRT4!RpcRevertToSelf` at `0x1800bddf5`
- `RPCRT4!RpcImpersonateClient` at `0x1800bdb80`
- `RPCRT4!RpcImpersonateClient` at `0x1800bdcfd`
- `RPCRT4!RpcImpersonateClient` at `0x1800bdb80`
- `RPCRT4!RpcImpersonateClient` at `0x1800bdcfd`
- `fwbase!FwHResultToWindowsError` at `0x1800bdcc4`
- `fwbase!FwHResultToWindowsError` at `0x1800bdcc4`
- `fwbase!FwGetTokenInformation` at `0x1800bdc74`
- `fwbase!FwGetTokenInformation` at `0x1800bddb4`
- `fwbase!FwGetTokenInformation` at `0x1800bdc74`
- `fwbase!FwGetTokenInformation` at `0x1800bddb4`
- `fwbase!FwCloseHandle` at `0x1800bdbcd`
- `fwbase!FwCloseHandle` at `0x1800bdcb6`
- `fwbase!FwCloseHandle` at `0x1800bdd43`
- `fwbase!FwCloseHandle` at `0x1800bddef`
- `fwbase!FwCloseHandle` at `0x1800bdbcd`
- `fwbase!FwCloseHandle` at `0x1800bdcb6`
- `fwbase!FwCloseHandle` at `0x1800bdd43`
- `fwbase!FwCloseHandle` at `0x1800bddef`
- `fwbase!FwFree` at `0x1800bde2e`
- `fwbase!FwFree` at `0x1800bde39`
- `fwbase!FwFree` at `0x1800bde2e`
- `fwbase!FwFree` at `0x1800bde39`

## pseudocode

```c
__int64 __fastcall appIsolation::InboxAppContainerManager::ValidateAppContainerOperation(
        appIsolation::InboxAppContainerManager *this,
        void *a2,
        int a3,
        int a4,
        struct _SID *a5,
        struct _SID *Sid1,
        int *a7)
{
  unsigned int v9; // edi
  unsigned int v10; // ebx
  __int64 v11; // rsi
  RPC_STATUS v12; // eax
  unsigned int v13; // ebx
  __int64 result; // rax
  HANDLE v15; // rax
  signed int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r9
  int v20; // eax
  unsigned int v21; // ebx
  RPC_STATUS v22; // eax
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // r9
  int TokenInformation; // eax
  void *TokenHandle; // [rsp+28h] [rbp-60h] BYREF
  _QWORD *v31; // [rsp+30h] [rbp-58h] BYREF
  PSID *v32; // [rsp+38h] [rbp-50h] BYREF

  *a7 = 1;
  v32 = 0;
  v31 = 0;
  if ( a5 && Sid1 )
  {
    v9 = *((_DWORD *)this + 14);
    v10 = 0;
    v11 = *((_QWORD *)this + 6);
    if ( v9 )
    {
      while ( RtlEqualSid(Sid1, *(PSID *)(v11 + 16LL * v10)) != 1 )
      {
        if ( ++v10 >= v9 )
          goto LABEL_6;
      }
      if ( !RtlEqualSid(a5, gSidManager[1]) )
      {
        if ( a3 != 1 )
          return 5;
        goto LABEL_57;
      }
    }
LABEL_6:
    if ( a3 )
      goto LABEL_55;
    TokenHandle = 0;
    v12 = RpcImpersonateClient(a2);
    v13 = v12;
    if ( v12 )
    {
      if ( v12 > 0 )
        v13 = (unsigned __int16)v12 | 0x80070000;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 22, WPP_f89b9f9d100e330640241b1b67db84b7_Traceguids, v13);
      FwCloseHandle(TokenHandle);
LABEL_29:
      result = FwHResultToWindowsError(v13);
      if ( (_DWORD)result )
        return result;
      if ( !RtlEqualSid(a5, *v32) )
        goto LABEL_31;
      TokenHandle = 0;
      v22 = RpcImpersonateClient(a2);
      v21 = v22;
      if ( v22 )
      {
        if ( v22 > 0 )
          v21 = (unsigned __int16)v22 | 0x80070000;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 25, WPP_f89b9f9d100e330640241b1b67db84b7_Traceguids, v21);
        FwCloseHandle(TokenHandle);
LABEL_51:
        if ( v21 )
          goto LABEL_56;
        if ( *v31 && (!a4 || !(unsigned __int8)RtlIsParentOfChildAppContainer(*v31, Sid1)) )
        {
LABEL_31:
          v21 = 5;
LABEL_56:
          FwFree(v31);
          FwFree(v32);
          return v21;
        }
LABEL_55:
        v21 = 0;
        goto LABEL_56;
      }
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
      {
        TokenInformation = FwGetTokenInformation(TokenHandle, 31, &v31, 0);
        v21 = TokenInformation;
        if ( TokenInformation >= 0 )
          goto LABEL_50;
        v25 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_50;
        v26 = 27;
        v27 = (unsigned int)TokenInformation;
      }
      else
      {
        LastError = GetLastError();
        v21 = LastError;
        if ( LastError > 0 )
          v21 = (unsigned __int16)LastError | 0x80070000;
        v25 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_50;
        v26 = 26;
        v27 = v21;
      }
      WPP_SF_d(*(_QWORD *)(v25 + 16), v26, WPP_f89b9f9d100e330640241b1b67db84b7_Traceguids, v27);
LABEL_50:
      FwCloseHandle(TokenHandle);
      RpcRevertToSelf();
      goto LABEL_51;
    }
    v15 = GetCurrentThread();
    if ( OpenThreadToken(v15, 8u, 1, &TokenHandle) )
    {
      v20 = FwGetTokenInformation(TokenHandle, 1, &v32, 0);
      v13 = v20;
      if ( v20 >= 0 )
        goto LABEL_28;
      v17 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_28;
      v18 = 24;
      v19 = (unsigned int)v20;
    }
    else
    {
      v16 = GetLastError();
      v13 = v16;
      if ( v16 > 0 )
        v13 = (unsigned __int16)v16 | 0x80070000;
      v17 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_28;
      v18 = 23;
      v19 = v13;
    }
    WPP_SF_d(*(_QWORD *)(v17 + 16), v18, WPP_f89b9f9d100e330640241b1b67db84b7_Traceguids, v19);
LABEL_28:
    FwCloseHandle(TokenHandle);
    RpcRevertToSelf();
    goto LABEL_29;
  }
LABEL_57:
  *a7 = 0;
  return 0;
}

```

## disassembly

```asm
0x1800bdad0  mov     [rsp+arg_10], rbx
0x1800bdad5  push    rbp
0x1800bdad6  push    rsi
0x1800bdad7  push    rdi
0x1800bdad8  push    r12
0x1800bdada  push    r13
0x1800bdadc  push    r14
0x1800bdade  push    r15
0x1800bdae0  sub     rsp, 50h
0x1800bdae4  mov     rax, cs:__security_cookie
0x1800bdaeb  xor     rax, rsp
0x1800bdaee  mov     [rsp+88h+var_48], rax
0x1800bdaf3  mov     r14, [rsp+88h+arg_30]
0x1800bdafb  mov     ebp, r8d
0x1800bdafe  mov     r12, [rsp+88h+arg_20]
0x1800bdb06  mov     r13, rdx
0x1800bdb09  mov     r15, [rsp+88h+Sid1]
0x1800bdb11  mov     [rsp+88h+var_68], r9d
0x1800bdb16  mov     dword ptr [r14], 1
0x1800bdb1d  mov     [rsp+88h+var_50], 0
0x1800bdb26  mov     [rsp+88h+var_58], 0
0x1800bdb2f  test    r12, r12
0x1800bdb32  jz      loc_1800BDE43
0x1800bdb38  test    r15, r15
0x1800bdb3b  jz      loc_1800BDE43
0x1800bdb41  mov     edi, [rcx+38h]
0x1800bdb44  xor     ebx, ebx
0x1800bdb46  nop
0x1800bdb47  mov     rsi, [rcx+30h]
0x1800bdb4b  test    edi, edi
0x1800bdb4d  jz      short loc_1800BDB6C
0x1800bdb4f  nop
0x1800bdb50  mov     edx, ebx
0x1800bdb52  mov     rcx, r15; Sid1
0x1800bdb55  add     rdx, rdx
0x1800bdb58  mov     rdx, [rsi+rdx*8]; Sid2
0x1800bdb5c  call    cs:__imp_RtlEqualSid
0x1800bdb62  cmp     al, 1
0x1800bdb64  jz      short loc_1800BDBD8
0x1800bdb66  inc     ebx
0x1800bdb68  cmp     ebx, edi
0x1800bdb6a  jb      short loc_1800BDB50
0x1800bdb6c  test    ebp, ebp
0x1800bdb6e  jnz     loc_1800BDE27
0x1800bdb74  mov     rcx, r13; BindingHandle
0x1800bdb77  mov     [rsp+88h+TokenHandle], 0
0x1800bdb80  call    cs:__imp_RpcImpersonateClient
0x1800bdb86  mov     ebx, eax
0x1800bdb88  test    eax, eax
0x1800bdb8a  jz      short loc_1800BDC07
0x1800bdb8c  jle     short loc_1800BDB97
0x1800bdb8e  movzx   ebx, ax
0x1800bdb91  or      ebx, 80070000h
0x1800bdb97  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bdb9e  lea     rdi, WPP_GLOBAL_Control
0x1800bdba5  cmp     rcx, rdi
0x1800bdba8  jz      short loc_1800BDBC8
0x1800bdbaa  test    byte ptr [rcx+1Ch], 1
0x1800bdbae  jz      short loc_1800BDBC8
0x1800bdbb0  mov     rcx, [rcx+10h]
0x1800bdbb4  lea     r8, WPP_f89b9f9d100e330640241b1b67db84b7_Traceguids
0x1800bdbbb  mov     edx, 16h
0x1800bdbc0  mov     r9d, ebx
0x1800bdbc3  call    WPP_SF_d
0x1800bdbc8  mov     rcx, [rsp+88h+TokenHandle]
0x1800bdbcd  call    cs:__imp_FwCloseHandle
0x1800bdbd3  jmp     loc_1800BDCC2
0x1800bdbd8  mov     rdx, cs:?gSidManager@@3V?$unique_ptr@VSidManagement@appIsolation@@U?$default_delete@VSidManagement@appIsolation@@@wistd@@@wistd@@A; wistd::unique_ptr<appIsolation::SidManagement,wistd::default_delete<appIsolation::SidManagement>> gSidManager
0x1800bdbdf  mov     rcx, r12; Sid1
0x1800bdbe2  mov     rdx, [rdx+8]; Sid2
0x1800bdbe6  call    cs:__imp_RtlEqualSid
0x1800bdbec  test    al, al
0x1800bdbee  jnz     loc_1800BDB6C
0x1800bdbf4  cmp     ebp, 1
0x1800bdbf7  jz      loc_1800BDE43
0x1800bdbfd  mov     eax, 5
0x1800bdc02  jmp     loc_1800BDE4C
0x1800bdc07  call    cs:__imp_GetCurrentThread
0x1800bdc0d  lea     r9, [rsp+88h+TokenHandle]; TokenHandle
0x1800bdc12  mov     edx, 8; DesiredAccess
0x1800bdc17  mov     rcx, rax; ThreadHandle
0x1800bdc1a  mov     r8d, 1; OpenAsSelf
0x1800bdc20  call    cs:__imp_OpenThreadToken
0x1800bdc26  test    eax, eax
0x1800bdc28  jnz     short loc_1800BDC62
0x1800bdc2a  call    cs:__imp_GetLastError
0x1800bdc30  mov     ebx, eax
0x1800bdc32  test    eax, eax
0x1800bdc34  jle     short loc_1800BDC3F
0x1800bdc36  movzx   ebx, ax
0x1800bdc39  or      ebx, 80070000h
0x1800bdc3f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bdc46  lea     rdi, WPP_GLOBAL_Control
0x1800bdc4d  cmp     rcx, rdi
0x1800bdc50  jz      short loc_1800BDCB1
0x1800bdc52  test    byte ptr [rcx+1Ch], 1
0x1800bdc56  jz      short loc_1800BDCB1
0x1800bdc58  mov     edx, 17h
0x1800bdc5d  mov     r9d, ebx
0x1800bdc60  jmp     short loc_1800BDCA1
0x1800bdc62  mov     rcx, [rsp+88h+TokenHandle]
0x1800bdc67  lea     r8, [rsp+88h+var_50]
0x1800bdc6c  xor     r9d, r9d
0x1800bdc6f  mov     edx, 1
0x1800bdc74  call    cs:__imp_FwGetTokenInformation
0x1800bdc7a  lea     rdi, WPP_GLOBAL_Control
0x1800bdc81  mov     ebx, eax
0x1800bdc83  test    eax, eax
0x1800bdc85  jns     short loc_1800BDCB1
0x1800bdc87  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bdc8e  cmp     rcx, rdi
0x1800bdc91  jz      short loc_1800BDCB1
0x1800bdc93  test    byte ptr [rcx+1Ch], 1
0x1800bdc97  jz      short loc_1800BDCB1
0x1800bdc99  mov     edx, 18h
0x1800bdc9e  mov     r9d, eax
0x1800bdca1  mov     rcx, [rcx+10h]
0x1800bdca5  lea     r8, WPP_f89b9f9d100e330640241b1b67db84b7_Traceguids
0x1800bdcac  call    WPP_SF_d
0x1800bdcb1  mov     rcx, [rsp+88h+TokenHandle]
0x1800bdcb6  call    cs:__imp_FwCloseHandle
0x1800bdcbc  call    cs:__imp_RpcRevertToSelf
0x1800bdcc2  mov     ecx, ebx
0x1800bdcc4  call    cs:__imp_FwHResultToWindowsError
0x1800bdcca  test    eax, eax
0x1800bdccc  jnz     loc_1800BDE4C
0x1800bdcd2  mov     rdx, [rsp+88h+var_50]
0x1800bdcd7  mov     rcx, r12; Sid1
0x1800bdcda  mov     rdx, [rdx]; Sid2
0x1800bdcdd  call    cs:__imp_RtlEqualSid
0x1800bdce3  test    al, al
0x1800bdce5  jnz     short loc_1800BDCF1
0x1800bdce7  mov     ebx, 5
0x1800bdcec  jmp     loc_1800BDE29
0x1800bdcf1  mov     rcx, r13; BindingHandle
0x1800bdcf4  mov     [rsp+88h+TokenHandle], 0
0x1800bdcfd  call    cs:__imp_RpcImpersonateClient
0x1800bdd03  mov     ebx, eax
0x1800bdd05  test    eax, eax
0x1800bdd07  jz      short loc_1800BDD4E
0x1800bdd09  jle     short loc_1800BDD14
0x1800bdd0b  movzx   ebx, ax
0x1800bdd0e  or      ebx, 80070000h
0x1800bdd14  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bdd1b  cmp     rcx, rdi
0x1800bdd1e  jz      short loc_1800BDD3E
0x1800bdd20  test    byte ptr [rcx+1Ch], 1
0x1800bdd24  jz      short loc_1800BDD3E
0x1800bdd26  mov     rcx, [rcx+10h]
0x1800bdd2a  lea     r8, WPP_f89b9f9d100e330640241b1b67db84b7_Traceguids
0x1800bdd31  mov     edx, 19h
0x1800bdd36  mov     r9d, ebx
0x1800bdd39  call    WPP_SF_d
0x1800bdd3e  mov     rcx, [rsp+88h+TokenHandle]
0x1800bdd43  call    cs:__imp_FwCloseHandle
0x1800bdd49  jmp     loc_1800BDDFB
0x1800bdd4e  call    cs:__imp_GetCurrentThread
0x1800bdd54  lea     r9, [rsp+88h+TokenHandle]; TokenHandle
0x1800bdd59  mov     edx, 8; DesiredAccess
0x1800bdd5e  mov     rcx, rax; ThreadHandle
0x1800bdd61  mov     r8d, 1; OpenAsSelf
0x1800bdd67  call    cs:__imp_OpenThreadToken
0x1800bdd6d  test    eax, eax
0x1800bdd6f  jnz     short loc_1800BDDA2
0x1800bdd71  call    cs:__imp_GetLastError
0x1800bdd77  mov     ebx, eax
0x1800bdd79  test    eax, eax
0x1800bdd7b  jle     short loc_1800BDD86
0x1800bdd7d  movzx   ebx, ax
0x1800bdd80  or      ebx, 80070000h
0x1800bdd86  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bdd8d  cmp     rcx, rdi
0x1800bdd90  jz      short loc_1800BDDEA
0x1800bdd92  test    byte ptr [rcx+1Ch], 1
0x1800bdd96  jz      short loc_1800BDDEA
0x1800bdd98  mov     edx, 1Ah
0x1800bdd9d  mov     r9d, ebx
0x1800bdda0  jmp     short loc_1800BDDDA
0x1800bdda2  mov     rcx, [rsp+88h+TokenHandle]
0x1800bdda7  lea     r8, [rsp+88h+var_58]
0x1800bddac  xor     r9d, r9d
0x1800bddaf  mov     edx, 1Fh
0x1800bddb4  call    cs:__imp_FwGetTokenInformation
0x1800bddba  mov     ebx, eax
0x1800bddbc  test    eax, eax
0x1800bddbe  jns     short loc_1800BDDEA
0x1800bddc0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bddc7  cmp     rcx, rdi
0x1800bddca  jz      short loc_1800BDDEA
0x1800bddcc  test    byte ptr [rcx+1Ch], 1
0x1800bddd0  jz      short loc_1800BDDEA
0x1800bddd2  mov     edx, 1Bh
0x1800bddd7  mov     r9d, eax
0x1800bddda  mov     rcx, [rcx+10h]
0x1800bddde  lea     r8, WPP_f89b9f9d100e330640241b1b67db84b7_Traceguids
0x1800bdde5  call    WPP_SF_d
0x1800bddea  mov     rcx, [rsp+88h+TokenHandle]
0x1800bddef  call    cs:__imp_FwCloseHandle
0x1800bddf5  call    cs:__imp_RpcRevertToSelf
0x1800bddfb  test    ebx, ebx
0x1800bddfd  jnz     short loc_1800BDE29
0x1800bddff  mov     rax, [rsp+88h+var_58]
0x1800bde04  mov     rcx, [rax]
0x1800bde07  test    rcx, rcx
0x1800bde0a  jz      short loc_1800BDE27
0x1800bde0c  cmp     [rsp+88h+var_68], ebx
0x1800bde10  jz      loc_1800BDCE7
0x1800bde16  mov     rdx, r15
0x1800bde19  call    cs:__imp_RtlIsParentOfChildAppContainer
0x1800bde1f  test    al, al
0x1800bde21  jz      loc_1800BDCE7
0x1800bde27  xor     ebx, ebx
0x1800bde29  mov     rcx, [rsp+88h+var_58]
0x1800bde2e  call    cs:__imp_FwFree
0x1800bde34  mov     rcx, [rsp+88h+var_50]
0x1800bde39  call    cs:__imp_FwFree
0x1800bde3f  mov     eax, ebx
0x1800bde41  jmp     short loc_1800BDE4C
0x1800bde43  mov     dword ptr [r14], 0
0x1800bde4a  xor     eax, eax
0x1800bde4c  mov     rcx, [rsp+88h+var_48]
0x1800bde51  xor     rcx, rsp; StackCookie
0x1800bde54  call    __security_check_cookie
0x1800bde59  mov     rbx, [rsp+88h+arg_10]
0x1800bde61  add     rsp, 50h
0x1800bde65  pop     r15
0x1800bde67  pop     r14
0x1800bde69  pop     r13
0x1800bde6b  pop     r12
0x1800bde6d  pop     rdi
0x1800bde6e  pop     rsi
0x1800bde6f  pop     rbp
0x1800bde70  retn
```
