# IsTokenMember(void *,WELL_KNOWN_SID_TYPE,int *)

- ea: `0x180025f20`
- end: `0x180026193`
- name: `?IsTokenMember@@YAJPEAXW4WELL_KNOWN_SID_TYPE@@PEAH@Z`
- size: `627`
- prototype: `__int64 __fastcall(HANDLE hExistingToken, enum WELL_KNOWN_SID_TYPE, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180025e6c`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18001a630`
- `0x180025f20`
- `0x180067b0a`
- `0x180067b30`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002606d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800260d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002606d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800260d1`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002603e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180026157`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002603e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180026157`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180025ff8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180025ff8`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180025fc0`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180025fc0`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800260fe`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800260fe`

## string_xrefs

- `0x180025f48`: `IsTokenMember`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IsTokenMember(HANDLE hExistingToken, enum WELL_KNOWN_SID_TYPE a2, int *a3)
{
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  __int16 v13; // ax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  __int16 v18; // ax
  unsigned int LastFailureAsHRESULT; // ebx
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  WINBOOL IsMember; // [rsp+30h] [rbp-69h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-61h] BYREF
  DWORD ReturnLength; // [rsp+40h] [rbp-59h] BYREF
  int TokenInformation; // [rsp+44h] [rbp-55h] BYREF
  int v33; // [rsp+48h] [rbp-51h] BYREF
  __int16 v34; // [rsp+4Ch] [rbp-4Dh]
  __int16 v35; // [rsp+4Eh] [rbp-4Bh]
  DWORD cbSid[4]; // [rsp+80h] [rbp-19h] BYREF
  _BYTE pSid[80]; // [rsp+90h] [rbp-9h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v33, "IsTokenMember", 0x11Au, 1u);
  IsMember = 0;
  memset_0(pSid, 0, 0x48u);
  cbSid[0] = 72;
  hObject = 0;
  TokenInformation = 1;
  ReturnLength = 0;
  if ( !hExistingToken )
  {
    LastFailureAsHRESULT = -2147024809;
    v35 = 291;
    v33 = -2147024809;
    goto LABEL_12;
  }
  v33 = 0;
  v34 = 291;
  if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pSid, cbSid) )
  {
    v33 = 0;
    v34 = 293;
    if ( GetTokenInformation(hExistingToken, TokenType, &TokenInformation, 4u, &ReturnLength) )
    {
      v34 = 294;
      v13 = 295;
      if ( ReturnLength == 4 )
      {
        v33 = 0;
        v34 = 295;
        if ( TokenInformation == 2 )
        {
          if ( CheckTokenMembership(hExistingToken, pSid, &IsMember) )
          {
            v18 = 303;
LABEL_8:
            LastFailureAsHRESULT = 0;
            v34 = v18;
            v33 = 0;
            *a3 = IsMember;
            goto LABEL_9;
          }
          LastFailureAsHRESULT = GetLastFailureAsHRESULT(v15, v14, v16, v17);
          v33 = LastFailureAsHRESULT;
          v13 = 303;
        }
        else
        {
          if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          {
            CloseHandle(hObject);
            hObject = 0;
          }
          if ( DuplicateTokenEx(hExistingToken, 0, 0, SecurityImpersonation, TokenImpersonation, &hObject) )
          {
            v33 = 0;
            v34 = 298;
            if ( CheckTokenMembership(hObject, pSid, &IsMember) )
            {
              v18 = 299;
              goto LABEL_8;
            }
            LastFailureAsHRESULT = GetLastFailureAsHRESULT(v26, v25, v27, v28);
            v33 = LastFailureAsHRESULT;
            v13 = 299;
          }
          else
          {
            LastFailureAsHRESULT = GetLastFailureAsHRESULT(v22, v21, v23, v24);
            v33 = LastFailureAsHRESULT;
            v13 = 298;
          }
        }
      }
      else
      {
        LastFailureAsHRESULT = -2147467259;
        v33 = -2147467259;
      }
    }
    else
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v10, v9, v11, v12);
      v33 = LastFailureAsHRESULT;
      v13 = 294;
    }
  }
  else
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v6, v5, v7, v8);
    v33 = LastFailureAsHRESULT;
    v13 = 293;
  }
  v35 = v13;
LABEL_9:
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
LABEL_12:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v33);
  return LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x180025f20  mov     [rsp-8+arg_8], rbx
0x180025f25  mov     [rsp-8+arg_18], rdi
0x180025f2a  push    rbp
0x180025f2b  lea     rbp, [rsp-57h]
0x180025f30  sub     rsp, 0F0h
0x180025f37  mov     rax, cs:__security_cookie
0x180025f3e  xor     rax, rsp
0x180025f41  mov     [rbp+57h+var_10], rax
0x180025f45  mov     rdi, r8
0x180025f48  lea     rdx, aIstokenmember; "IsTokenMember"
0x180025f4f  mov     rbx, rcx
0x180025f52  mov     r8d, 11Ah; unsigned __int16
0x180025f58  lea     rcx, [rbp+57h+var_A8]; this
0x180025f5c  mov     r9d, 1; unsigned __int16
0x180025f62  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180025f67  xor     edx, edx; Val
0x180025f69  mov     [rbp+57h+IsMember], 0
0x180025f70  lea     rcx, [rbp+57h+pSid]; void *
0x180025f74  lea     r8d, [rdx+48h]; Size
0x180025f78  call    memset_0
0x180025f7d  mov     [rbp+57h+cbSid], 48h ; 'H'
0x180025f84  mov     eax, 123h
0x180025f89  mov     [rbp+57h+hObject], 0
0x180025f91  mov     [rbp+57h+TokenInformation], 1
0x180025f98  mov     [rbp+57h+var_B0], 0
0x180025f9f  test    rbx, rbx
0x180025fa2  jz      loc_18002607D
0x180025fa8  xor     edx, edx; DomainSid
0x180025faa  mov     [rbp+57h+var_A8], 0
0x180025fb1  lea     r9, [rbp+57h+cbSid]; cbSid
0x180025fb5  mov     [rbp+57h+var_A4], ax
0x180025fb9  lea     r8, [rbp+57h+pSid]; pSid
0x180025fbd  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x180025fc0  call    cs:__imp_CreateWellKnownSid
0x180025fc6  test    eax, eax
0x180025fc8  jz      loc_180026119
0x180025fce  mov     r9d, 4; TokenInformationLength
0x180025fd4  mov     [rbp+57h+var_A8], 0
0x180025fdb  mov     eax, 125h
0x180025fe0  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180025fe4  mov     [rbp+57h+var_A4], ax
0x180025fe8  mov     rcx, rbx; TokenHandle
0x180025feb  lea     rax, [rbp+57h+var_B0]
0x180025fef  lea     edx, [r9+4]; TokenInformationClass
0x180025ff3  mov     [rsp+0F0h+ReturnLength], rax; ReturnLength
0x180025ff8  call    cs:__imp_GetTokenInformation
0x180025ffe  test    eax, eax
0x180026000  jz      loc_18002612A
0x180026006  cmp     [rbp+57h+var_B0], 4
0x18002600a  mov     eax, 126h
0x18002600f  mov     [rbp+57h+var_A4], ax
0x180026013  mov     eax, 127h
0x180026018  jnz     loc_1800260B5
0x18002601e  cmp     [rbp+57h+TokenInformation], 2
0x180026022  mov     [rbp+57h+var_A8], 0
0x180026029  mov     [rbp+57h+var_A4], ax
0x18002602d  jnz     loc_1800260C3
0x180026033  lea     r8, [rbp+57h+IsMember]; IsMember
0x180026037  mov     rcx, rbx; TokenHandle
0x18002603a  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x18002603e  call    cs:__imp_CheckTokenMembership
0x180026044  test    eax, eax
0x180026046  jz      loc_18002617F
0x18002604c  mov     eax, 12Fh
0x180026051  xor     ebx, ebx
0x180026053  mov     [rbp+57h+var_A4], ax
0x180026057  mov     eax, [rbp+57h+IsMember]
0x18002605a  mov     [rbp+57h+var_A8], ebx
0x18002605d  mov     [rdi], eax
0x18002605f  mov     rcx, [rbp+57h+hObject]; hObject
0x180026063  lea     rdx, [rcx-1]
0x180026067  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002606b  ja      short loc_180026089
0x18002606d  call    cs:__imp_CloseHandle
0x180026073  mov     [rbp+57h+hObject], 0
0x18002607b  jmp     short loc_180026089
0x18002607d  mov     ebx, 80070057h
0x180026082  mov     [rbp+57h+var_A2], ax
0x180026086  mov     [rbp+57h+var_A8], ebx
0x180026089  lea     rcx, [rbp+57h+var_A8]; this
0x18002608d  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180026092  mov     eax, ebx
0x180026094  mov     rcx, [rbp+57h+var_10]
0x180026098  xor     rcx, rsp; StackCookie
0x18002609b  call    __security_check_cookie
0x1800260a0  lea     r11, [rsp+0F0h+var_s0]
0x1800260a8  mov     rbx, [r11+18h]
0x1800260ac  mov     rdi, [r11+28h]
0x1800260b0  mov     rsp, r11
0x1800260b3  pop     rbp
0x1800260b4  retn
0x1800260b5  mov     ebx, 80004005h
0x1800260ba  mov     [rbp+57h+var_A8], ebx
0x1800260bd  mov     [rbp+57h+var_A2], ax
0x1800260c1  jmp     short loc_18002605F
0x1800260c3  mov     rcx, [rbp+57h+hObject]; hObject
0x1800260c7  lea     rax, [rcx-1]
0x1800260cb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800260cf  ja      short loc_1800260DF
0x1800260d1  call    cs:__imp_CloseHandle
0x1800260d7  mov     [rbp+57h+hObject], 0
0x1800260df  lea     rax, [rbp+57h+hObject]
0x1800260e3  mov     r9d, 2; ImpersonationLevel
0x1800260e9  mov     [rsp+0F0h+phNewToken], rax; phNewToken
0x1800260ee  xor     r8d, r8d; lpTokenAttributes
0x1800260f1  xor     edx, edx; dwDesiredAccess
0x1800260f3  mov     dword ptr [rsp+0F0h+ReturnLength], 2; TokenType
0x1800260fb  mov     rcx, rbx; hExistingToken
0x1800260fe  call    cs:__imp_DuplicateTokenEx
0x180026104  test    eax, eax
0x180026106  jnz     short loc_18002613B
0x180026108  call    GetLastFailureAsHRESULT
0x18002610d  mov     ebx, eax
0x18002610f  mov     [rbp+57h+var_A8], eax
0x180026112  mov     eax, 12Ah
0x180026117  jmp     short loc_1800260BD
0x180026119  call    GetLastFailureAsHRESULT
0x18002611e  mov     ebx, eax
0x180026120  mov     [rbp+57h+var_A8], eax
0x180026123  mov     eax, 125h
0x180026128  jmp     short loc_1800260BD
0x18002612a  call    GetLastFailureAsHRESULT
0x18002612f  mov     ebx, eax
0x180026131  mov     [rbp+57h+var_A8], eax
0x180026134  mov     eax, 126h
0x180026139  jmp     short loc_1800260BD
0x18002613b  mov     rcx, [rbp+57h+hObject]; TokenHandle
0x18002613f  lea     r8, [rbp+57h+IsMember]; IsMember
0x180026143  mov     eax, 12Ah
0x180026148  mov     [rbp+57h+var_A8], 0
0x18002614f  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x180026153  mov     [rbp+57h+var_A4], ax
0x180026157  call    cs:__imp_CheckTokenMembership
0x18002615d  test    eax, eax
0x18002615f  jnz     short loc_180026175
0x180026161  call    GetLastFailureAsHRESULT
0x180026166  mov     ebx, eax
0x180026168  mov     [rbp+57h+var_A8], eax
0x18002616b  mov     eax, 12Bh
0x180026170  jmp     loc_1800260BD
0x180026175  mov     eax, 12Bh
0x18002617a  jmp     loc_180026051
0x18002617f  call    GetLastFailureAsHRESULT
0x180026184  mov     ebx, eax
0x180026186  mov     [rbp+57h+var_A8], eax
0x180026189  mov     eax, 12Fh
0x18002618e  jmp     loc_1800260BD
```
