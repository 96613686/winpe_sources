# PlumbDirectoryPolicy

- ea: `0x18002c9b0`
- end: `0x18002cd17`
- name: `PlumbDirectoryPolicy`
- size: `871`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, loader_planting`

## callers

- `0x180001590`
- `0x18000adac`

## callees

- `0x180006f60`
- `0x1800080e0`
- `0x180008280`
- `0x18000afe8`
- `0x18000b29c`
- `0x18000c904`
- `0x18000e078`
- `0x18000e510`
- `0x18000f638`
- `0x18002b688`
- `0x18002c1ec`
- `0x18002c9b0`
- `0x18003c2d4`
- `0x180042e20`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18002ca02`
- `ntdll!EtwEventWrite` at `0x18002cc85`
- `ntdll!EtwEventWrite` at `0x18002ccf7`
- `ntdll!EtwEventWrite` at `0x18002ca02`
- `ntdll!EtwEventWrite` at `0x18002cc85`
- `ntdll!EtwEventWrite` at `0x18002ccf7`

## pseudocode

```c
__int64 __fastcall PlumbDirectoryPolicy(_QWORD *a1)
{
  LPVOID *v1; // rsi
  _DWORD *v2; // r14
  int v4; // r13d
  unsigned int v5; // r12d
  _QWORD *v6; // rcx
  DWORD DirectoryPolicyDN; // eax
  DWORD dwMessageId; // ebx
  unsigned __int16 *v9; // rdi
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rbx
  LPVOID *v13; // rcx
  _DWORD *v14; // rcx
  void *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  DWORD v21; // ebx
  __int64 v22; // [rsp+40h] [rbp-10h] BYREF
  DWORD v23; // [rsp+98h] [rbp+48h] BYREF
  LPVOID lpMem; // [rsp+A0h] [rbp+50h] BYREF
  LPVOID *v25; // [rsp+A8h] [rbp+58h] BYREF

  v1 = 0;
  lpMem = 0;
  v2 = 0;
  v25 = 0;
  v22 = 0;
  v23 = 0;
  v4 = 1;
  v5 = 1;
  if ( g_Provider )
    EtwEventWrite(g_Provider, IPSEC_SVC_ApplyDomainPolicy_Begin, 0, 0);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 )
      WPP_SF_(v6[2], 16, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids);
  }
  DirectoryPolicyDN = GetDirectoryPolicyDN((__int64 *)&lpMem);
  dwMessageId = DirectoryPolicyDN;
  if ( DirectoryPolicyDN )
  {
    v4 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_e815f316f4bb38f383997e5feee741ae_Traceguids,
        DirectoryPolicyDN);
    v9 = (unsigned __int16 *)lpMem;
    goto LABEL_37;
  }
  v9 = (unsigned __int16 *)lpMem;
  dwMessageId = LoadDirectoryPolicy((__int64)lpMem, &v25);
  if ( dwMessageId )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, dwMessageId);
    v1 = v25;
    goto LABEL_37;
  }
  v1 = v25;
  dwMessageId = ProcessNFAs(v25, 1, &v23, &v22);
  if ( dwMessageId )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, dwMessageId);
    v2 = (_DWORD *)v22;
    goto LABEL_37;
  }
  v12 = v22;
  AuditIPSecPolicyEventOld(v11, v10, 1269629039, *(_QWORD *)(v22 + 48));
  v13 = (LPVOID *)a1[4];
  if ( v13 )
    FreeIpsecPolicyObject(v13);
  v14 = (_DWORD *)a1[5];
  if ( v14 )
    FreeIpsecPolicyData(v14);
  v15 = (void *)a1[1];
  if ( v15 )
    IpsecFreeMem(v15);
  a1[4] = v1;
  a1[1] = v9;
  v1 = 0;
  v9 = 0;
  a1[5] = v12;
  dwMessageId = ApplyLoadedDirectoryPolicy((__int64)a1);
  if ( dwMessageId )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids);
    DeletePolicyInformation(a1[5]);
    v5 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, dwMessageId);
LABEL_37:
    SetSpdStateOnError(3, v5, dwMessageId, a1);
    if ( v4 )
    {
      if ( !v9 )
      {
LABEL_43:
        if ( v1 )
          FreeIpsecPolicyObject(v1);
        if ( v2 )
          FreeIpsecPolicyData(v2);
        if ( g_Provider )
          EtwEventWrite(g_Provider, IPSEC_SVC_ApplyDomainPolicy_End, 0, 0);
        return dwMessageId;
      }
      if ( v5 == 1 )
        AuditIPSecPolicyErrorEventOld(v19, v18, 0x4BAD0070u, v9, dwMessageId);
    }
    if ( v9 )
      IpsecFreeMem(v9);
    goto LABEL_43;
  }
  v21 = v23;
  if ( v23 )
  {
    AuditIPSecPolicyErrorEventOld(v17, v16, 0x4BAD0007u, *(unsigned __int16 **)(a1[5] + 48LL), v23);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, v21);
  }
  if ( g_Provider )
    EtwEventWrite(g_Provider, IPSEC_SVC_ApplyDomainPolicy_End, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x18002c9b0  mov     [rsp-38h+arg_0], rbx
0x18002c9b5  push    rbp
0x18002c9b6  push    rsi
0x18002c9b7  push    rdi
0x18002c9b8  push    r12
0x18002c9ba  push    r13
0x18002c9bc  push    r14
0x18002c9be  push    r15
0x18002c9c0  mov     rbp, rsp
0x18002c9c3  sub     rsp, 50h
0x18002c9c7  xor     esi, esi
0x18002c9c9  mov     [rbp+lpMem], 0
0x18002c9d1  xor     r14d, r14d
0x18002c9d4  mov     [rbp+arg_18], rsi
0x18002c9d8  mov     r15, rcx
0x18002c9db  mov     [rbp+var_10], r14
0x18002c9df  mov     rcx, cs:g_Provider
0x18002c9e6  mov     [rbp+arg_8], esi
0x18002c9e9  lea     r13d, [rsi+1]
0x18002c9ed  mov     r12d, r13d
0x18002c9f0  test    rcx, rcx
0x18002c9f3  jz      short loc_18002CA08
0x18002c9f5  xor     r9d, r9d
0x18002c9f8  lea     rdx, IPSEC_SVC_ApplyDomainPolicy_Begin
0x18002c9ff  xor     r8d, r8d
0x18002ca02  call    cs:__imp_EtwEventWrite
0x18002ca08  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ca0f  lea     rdi, WPP_GLOBAL_Control
0x18002ca16  cmp     rcx, rdi
0x18002ca19  jz      short loc_18002CA5D
0x18002ca1b  test    byte ptr [rcx+1Ch], 4
0x18002ca1f  jz      short loc_18002CA3D
0x18002ca21  mov     rcx, [rcx+10h]
0x18002ca25  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002ca2c  mov     edx, 0Fh
0x18002ca31  call    WPP_SF_
0x18002ca36  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ca3d  cmp     rcx, rdi
0x18002ca40  jz      short loc_18002CA5D
0x18002ca42  test    byte ptr [rcx+1Ch], 4
0x18002ca46  jz      short loc_18002CA5D
0x18002ca48  mov     rcx, [rcx+10h]
0x18002ca4c  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002ca53  mov     edx, 10h
0x18002ca58  call    WPP_SF_
0x18002ca5d  lea     rcx, [rbp+lpMem]
0x18002ca61  call    GetDirectoryPolicyDN
0x18002ca66  mov     ebx, eax
0x18002ca68  test    eax, eax
0x18002ca6a  jz      short loc_18002CAA1
0x18002ca6c  xor     r13d, r13d
0x18002ca6f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ca76  cmp     rcx, rdi
0x18002ca79  jz      short loc_18002CA98
0x18002ca7b  test    byte ptr [rcx+1Ch], 10h
0x18002ca7f  jz      short loc_18002CA98
0x18002ca81  mov     rcx, [rcx+10h]
0x18002ca85  lea     edx, [r13+11h]
0x18002ca89  mov     r9d, eax
0x18002ca8c  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002ca93  call    WPP_SF_d
0x18002ca98  mov     rdi, [rbp+lpMem]
0x18002ca9c  jmp     loc_18002CC10
0x18002caa1  mov     rdi, [rbp+lpMem]
0x18002caa5  lea     rdx, [rbp+arg_18]
0x18002caa9  mov     rcx, rdi; int
0x18002caac  call    LoadDirectoryPolicy
0x18002cab1  mov     ebx, eax
0x18002cab3  test    eax, eax
0x18002cab5  jz      short loc_18002CAF1
0x18002cab7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cabe  lea     rax, WPP_GLOBAL_Control
0x18002cac5  cmp     rcx, rax
0x18002cac8  jz      short loc_18002CAE8
0x18002caca  test    byte ptr [rcx+1Ch], 10h
0x18002cace  jz      short loc_18002CAE8
0x18002cad0  mov     rcx, [rcx+10h]
0x18002cad4  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002cadb  mov     edx, 12h
0x18002cae0  mov     r9d, ebx
0x18002cae3  call    WPP_SF_d
0x18002cae8  mov     rsi, [rbp+arg_18]
0x18002caec  jmp     loc_18002CC10
0x18002caf1  mov     rsi, [rbp+arg_18]
0x18002caf5  lea     r9, [rbp+var_10]
0x18002caf9  mov     rcx, rsi
0x18002cafc  lea     r8, [rbp+arg_8]
0x18002cb00  mov     edx, r12d
0x18002cb03  call    ProcessNFAs
0x18002cb08  mov     ebx, eax
0x18002cb0a  test    eax, eax
0x18002cb0c  jz      short loc_18002CB48
0x18002cb0e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cb15  lea     rax, WPP_GLOBAL_Control
0x18002cb1c  cmp     rcx, rax
0x18002cb1f  jz      short loc_18002CB3F
0x18002cb21  test    byte ptr [rcx+1Ch], 10h
0x18002cb25  jz      short loc_18002CB3F
0x18002cb27  mov     rcx, [rcx+10h]
0x18002cb2b  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002cb32  mov     edx, 13h
0x18002cb37  mov     r9d, ebx
0x18002cb3a  call    WPP_SF_d
0x18002cb3f  mov     r14, [rbp+var_10]
0x18002cb43  jmp     loc_18002CC10
0x18002cb48  mov     rbx, [rbp+var_10]
0x18002cb4c  mov     r8d, 4BAD006Fh
0x18002cb52  mov     r9, [rbx+30h]
0x18002cb56  call    AuditIPSecPolicyEventOld
0x18002cb5b  mov     rcx, [r15+20h]; lpMem
0x18002cb5f  test    rcx, rcx
0x18002cb62  jz      short loc_18002CB69
0x18002cb64  call    FreeIpsecPolicyObject
0x18002cb69  mov     rcx, [r15+28h]; lpMem
0x18002cb6d  test    rcx, rcx
0x18002cb70  jz      short loc_18002CB77
0x18002cb72  call    FreeIpsecPolicyData
0x18002cb77  mov     rcx, [r15+8]; lpMem
0x18002cb7b  test    rcx, rcx
0x18002cb7e  jz      short loc_18002CB85
0x18002cb80  call    IpsecFreeMem
0x18002cb85  mov     [r15+20h], rsi
0x18002cb89  mov     rcx, r15
0x18002cb8c  mov     [r15+8], rdi
0x18002cb90  xor     esi, esi
0x18002cb92  xor     edi, edi
0x18002cb94  mov     [r15+28h], rbx
0x18002cb98  call    ApplyLoadedDirectoryPolicy
0x18002cb9d  mov     ebx, eax
0x18002cb9f  test    eax, eax
0x18002cba1  jz      loc_18002CC8F
0x18002cba7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cbae  lea     rax, WPP_GLOBAL_Control
0x18002cbb5  cmp     rcx, rax
0x18002cbb8  jz      short loc_18002CBD3
0x18002cbba  test    byte ptr [rcx+1Ch], 4
0x18002cbbe  jz      short loc_18002CBD3
0x18002cbc0  mov     rcx, [rcx+10h]
0x18002cbc4  lea     edx, [rsi+14h]
0x18002cbc7  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002cbce  call    WPP_SF_
0x18002cbd3  mov     rcx, [r15+28h]
0x18002cbd7  call    DeletePolicyInformation
0x18002cbdc  xor     r12d, r12d
0x18002cbdf  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cbe6  lea     rax, WPP_GLOBAL_Control
0x18002cbed  cmp     rcx, rax
0x18002cbf0  jz      short loc_18002CC10
0x18002cbf2  test    byte ptr [rcx+1Ch], 10h
0x18002cbf6  jz      short loc_18002CC10
0x18002cbf8  mov     rcx, [rcx+10h]
0x18002cbfc  lea     edx, [r12+15h]
0x18002cc01  mov     r9d, ebx
0x18002cc04  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002cc0b  call    WPP_SF_d
0x18002cc10  mov     r9, r15
0x18002cc13  mov     r8d, ebx
0x18002cc16  mov     edx, r12d
0x18002cc19  mov     ecx, 3
0x18002cc1e  call    SetSpdStateOnError
0x18002cc23  test    r13d, r13d
0x18002cc26  jz      short loc_18002CC45
0x18002cc28  test    rdi, rdi
0x18002cc2b  jz      short loc_18002CC52
0x18002cc2d  cmp     r12d, 1
0x18002cc31  jnz     short loc_18002CC45
0x18002cc33  mov     r9, rdi; int
0x18002cc36  mov     [rsp+50h+dwMessageId], ebx; dwMessageId
0x18002cc3a  mov     r8d, 4BAD0070h; int
0x18002cc40  call    AuditIPSecPolicyErrorEventOld
0x18002cc45  test    rdi, rdi
0x18002cc48  jz      short loc_18002CC52
0x18002cc4a  mov     rcx, rdi; lpMem
0x18002cc4d  call    IpsecFreeMem
0x18002cc52  test    rsi, rsi
0x18002cc55  jz      short loc_18002CC5F
0x18002cc57  mov     rcx, rsi; lpMem
0x18002cc5a  call    FreeIpsecPolicyObject
0x18002cc5f  test    r14, r14
0x18002cc62  jz      short loc_18002CC6C
0x18002cc64  mov     rcx, r14; lpMem
0x18002cc67  call    FreeIpsecPolicyData
0x18002cc6c  mov     rcx, cs:g_Provider
0x18002cc73  test    rcx, rcx
0x18002cc76  jz      short loc_18002CC8B
0x18002cc78  xor     r9d, r9d
0x18002cc7b  lea     rdx, IPSEC_SVC_ApplyDomainPolicy_End
0x18002cc82  xor     r8d, r8d
0x18002cc85  call    cs:__imp_EtwEventWrite
0x18002cc8b  mov     eax, ebx
0x18002cc8d  jmp     short loc_18002CCFF
0x18002cc8f  mov     ebx, [rbp+arg_8]
0x18002cc92  test    ebx, ebx
0x18002cc94  jz      short loc_18002CCDE
0x18002cc96  mov     r9, [r15+28h]
0x18002cc9a  mov     r8d, 4BAD0007h; int
0x18002cca0  mov     [rsp+50h+dwMessageId], ebx; dwMessageId
0x18002cca4  mov     r9, [r9+30h]; int
0x18002cca8  call    AuditIPSecPolicyErrorEventOld
0x18002ccad  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ccb4  lea     rax, WPP_GLOBAL_Control
0x18002ccbb  cmp     rcx, rax
0x18002ccbe  jz      short loc_18002CCDE
0x18002ccc0  test    byte ptr [rcx+1Ch], 8
0x18002ccc4  jz      short loc_18002CCDE
0x18002ccc6  mov     rcx, [rcx+10h]
0x18002ccca  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002ccd1  mov     edx, 16h
0x18002ccd6  mov     r9d, ebx
0x18002ccd9  call    WPP_SF_d
0x18002ccde  mov     rcx, cs:g_Provider
0x18002cce5  test    rcx, rcx
0x18002cce8  jz      short loc_18002CCFD
0x18002ccea  xor     r9d, r9d
0x18002cced  lea     rdx, IPSEC_SVC_ApplyDomainPolicy_End
0x18002ccf4  xor     r8d, r8d
0x18002ccf7  call    cs:__imp_EtwEventWrite
0x18002ccfd  xor     eax, eax
0x18002ccff  mov     rbx, [rsp+50h+arg_0]
0x18002cd07  add     rsp, 50h
0x18002cd0b  pop     r15
0x18002cd0d  pop     r14
0x18002cd0f  pop     r13
0x18002cd11  pop     r12
0x18002cd13  pop     rdi
0x18002cd14  pop     rsi
0x18002cd15  pop     rbp
0x18002cd16  retn
```
