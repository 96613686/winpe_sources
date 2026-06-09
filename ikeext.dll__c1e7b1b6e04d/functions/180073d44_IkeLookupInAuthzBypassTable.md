# IkeLookupInAuthzBypassTable

- ea: `0x180073d44`
- end: `0x18007410f`
- name: `IkeLookupInAuthzBypassTable`
- size: `971`
- prototype: `__int64 __fastcall(PSID *, __int64, int, __int64 *)`
- caller_count: `3`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180072a14`
- `0x180072d38`
- `0x180073820`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x180008240`
- `0x18001b950`
- `0x1800488f0`
- `0x18004890c`
- `0x180050850`
- `0x18005bc40`
- `0x1800737f4`
- `0x1800738c8`
- `0x180073d44`
- `0x180074214`
- `0x18008079c`

## import_xrefs

- `ntdll!RtlGetNextEntryHashTable` at `0x1800740f8`
- `ntdll!RtlGetNextEntryHashTable` at `0x1800740f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180073fd4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180073fd4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180073e75`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180073e75`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180073eda`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180073eda`

## pseudocode

```c
__int64 __fastcall IkeLookupInAuthzBypassTable(PSID *a1, __int64 a2, int a3, __int64 *a4)
{
  unsigned int v4; // r15d
  __int64 v6; // r14
  __int64 v8; // rdi
  __int64 TlsPeerAddr; // rbx
  __int64 v10; // rcx
  int TlsMmLuid; // eax
  __int64 v12; // rcx
  __int64 v13; // rax
  int v14; // r8d
  int v15; // r9d
  __int64 v16; // rbx
  __int64 i; // rax
  PSID *v18; // r14
  __int64 v19; // rcx
  __int64 v20; // rdi
  __int64 v21; // rbx
  __int64 v22; // rcx
  int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rax
  int v26; // r8d
  __int64 v28; // rdi
  __int64 v29; // rbx
  __int64 v30; // rcx
  int v31; // eax
  __int64 v32; // rcx
  __int64 v33; // rax
  int v34; // r8d
  int v35; // r9d
  __int64 v36; // rsi
  __int64 v39; // [rsp+40h] [rbp-69h] BYREF
  __int64 *v40; // [rsp+48h] [rbp-61h] BYREF
  __int128 v41; // [rsp+50h] [rbp-59h] BYREF
  __int64 v42; // [rsp+60h] [rbp-49h]
  _BYTE v43[32]; // [rsp+70h] [rbp-39h] BYREF
  __int64 *v44; // [rsp+90h] [rbp-19h]
  __int64 v45; // [rsp+98h] [rbp-11h]
  _BYTE v46[16]; // [rsp+A0h] [rbp-9h] BYREF
  const char *v47; // [rsp+B0h] [rbp+7h]
  __int64 v48; // [rsp+B8h] [rbp+Fh]

  v4 = 0;
  v40 = a4;
  v42 = 0;
  v6 = a2;
  v41 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v8 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    TlsPeerAddr = IkeGetTlsPeerAddr(a1);
    TlsMmLuid = IkeGetTlsMmLuid(v10);
    WPP_SF_iS(v8, 12, (unsigned int)WPP_79e2b82eafc434f0fa6155cdafc7fda3_Traceguids, TlsMmLuid, TlsPeerAddr);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v39 = IkeGetTlsMmLuid(a1);
    v44 = &v39;
    v45 = 8;
    v13 = IkeGetTlsPeerAddr(v12);
    tlgCreate1Sz_wchar_t(v46, v13);
    v48 = 59;
    v47 = "Looking up matching entry in authZ bypass table for params";
    tlgWriteTransfer_EtwEventWriteTransfer(
      (unsigned int)&dword_180173278,
      (unsigned int)&dword_180153CEC,
      v14,
      v15,
      5,
      (__int64)v43);
  }
  IkeDumpAuthzBypassParams(*a1, a1[1], v6);
  v16 = IkeComputeAuthzBypassHashSignature(v6);
  if ( !a3 )
    EnterCriticalSection(gIkeExtGlobals + 3);
  for ( i = WfpHashtableFind(&gIkeExtGlobals[61].LockCount, v16, &v41);
        ;
        i = RtlGetNextEntryHashTable(&gIkeExtGlobals[61].LockCount, &v41) )
  {
    v36 = i;
    if ( !i )
      break;
    if ( (unsigned int)IkeAddrIsEqual(v6, i + 56) )
    {
      v18 = (PSID *)(v36 + 24);
      if ( (unsigned int)IkeIsAnonymousSid(*a1) || (unsigned int)IkeIsAnonymousSid(*v18) )
      {
        v4 = IsMatchingBypassCertInfo(a1, v36);
        if ( v4 )
          goto LABEL_15;
      }
      else if ( EqualSid(*a1, *v18) )
      {
        v4 = 1;
LABEL_15:
        if ( v40 )
          *v40 = v36;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v20 = *((_QWORD *)WPP_GLOBAL_Control + 2);
          v21 = IkeGetTlsPeerAddr(v19);
          v23 = IkeGetTlsMmLuid(v22);
          WPP_SF_iS(v20, 14, (unsigned int)WPP_79e2b82eafc434f0fa6155cdafc7fda3_Traceguids, v23, v21);
        }
        if ( (unsigned int)dword_180173278 > 4 )
        {
          v40 = (__int64 *)IkeGetTlsMmLuid(v19);
          v44 = (__int64 *)&v40;
          v45 = 8;
          v25 = IkeGetTlsPeerAddr(v24);
          tlgCreate1Sz_wchar_t(v46, v25);
          v48 = 43;
          v47 = "Found matching entry in authZ bypass table";
          tlgWriteTransfer_EtwEventWriteTransfer(
            (unsigned int)&dword_180173278,
            (unsigned int)qword_180153C70,
            v26,
            (unsigned int)"Found matching entry in authZ bypass table",
            5,
            (__int64)v43);
        }
        IkeDumpAuthzBypassParams(*(_QWORD *)(v36 + 24), *(_QWORD *)(v36 + 32), v36 + 56);
        break;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v28 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v29 = IkeGetTlsPeerAddr(v19);
        v31 = IkeGetTlsMmLuid(v30);
        WPP_SF_iS(v28, 13, (unsigned int)WPP_79e2b82eafc434f0fa6155cdafc7fda3_Traceguids, v31, v29);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v39 = IkeGetTlsMmLuid(v19);
        v44 = &v39;
        v45 = 8;
        v33 = IkeGetTlsPeerAddr(v32);
        tlgCreate1Sz_wchar_t(v46, v33);
        v48 = 38;
        v47 = "AuthZ bypass table entry didn't match";
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_180173278,
          (unsigned int)&word_180153CAE,
          v34,
          v35,
          5,
          (__int64)v43);
      }
      IkeDumpAuthzBypassParams(*v18, *(_QWORD *)(v36 + 32), v36 + 56);
      v6 = a2;
    }
  }
  if ( !a3 )
    LeaveCriticalSection(gIkeExtGlobals + 3);
  return v4;
}

```

## disassembly

```asm
0x180073d44  mov     [rsp-8+arg_10], rbx
0x180073d49  push    rbp
0x180073d4a  push    rsi
0x180073d4b  push    rdi
0x180073d4c  push    r12
0x180073d4e  push    r13
0x180073d50  push    r14
0x180073d52  push    r15
0x180073d54  lea     rbp, [rsp-27h]
0x180073d59  sub     rsp, 0D0h
0x180073d60  mov     rax, cs:__security_cookie
0x180073d67  xor     rax, rsp
0x180073d6a  mov     [rbp+57h+var_40], rax
0x180073d6e  xor     r15d, r15d
0x180073d71  mov     [rbp+57h+var_B8], r9
0x180073d75  xor     eax, eax
0x180073d77  mov     [rbp+57h+var_D0], r8d
0x180073d7b  xorps   xmm0, xmm0
0x180073d7e  mov     [rbp+57h+var_A0], rax
0x180073d82  mov     esi, r8d
0x180073d85  mov     [rbp+57h+var_C8], rdx
0x180073d89  mov     r14, rdx
0x180073d8c  mov     r12, rcx
0x180073d8f  movups  [rbp+57h+var_B0], xmm0
0x180073d93  mov     rdi, cs:WPP_GLOBAL_Control
0x180073d9a  lea     rax, WPP_GLOBAL_Control
0x180073da1  cmp     rdi, rax
0x180073da4  jz      short loc_180073DDE
0x180073da6  cmp     byte ptr [rdi+19h], 4
0x180073daa  jb      short loc_180073DDE
0x180073dac  test    byte ptr [rdi+1Ch], 10h
0x180073db0  jz      short loc_180073DDE
0x180073db2  mov     rdi, [rdi+10h]
0x180073db6  call    IkeGetTlsPeerAddr
0x180073dbb  mov     rbx, rax
0x180073dbe  call    IkeGetTlsMmLuid
0x180073dc3  mov     r9, rax
0x180073dc6  mov     [rsp+100h+var_E0], rbx
0x180073dcb  lea     edx, [r15+0Ch]
0x180073dcf  mov     rcx, rdi
0x180073dd2  lea     r8, WPP_79e2b82eafc434f0fa6155cdafc7fda3_Traceguids
0x180073dd9  call    WPP_SF_iS
0x180073dde  mov     eax, cs:dword_180173278
0x180073de4  cmp     eax, 4
0x180073de7  jbe     short loc_180073E4A
0x180073de9  call    IkeGetTlsMmLuid
0x180073dee  mov     [rbp+57h+var_C0], rax
0x180073df2  lea     rax, [rbp+57h+var_C0]
0x180073df6  mov     [rbp+57h+var_70], rax
0x180073dfa  mov     [rbp+57h+var_68], 8
0x180073e02  call    IkeGetTlsPeerAddr
0x180073e07  mov     rdx, rax
0x180073e0a  lea     rcx, [rbp+57h+var_60]
0x180073e0e  call    _tlgCreate1Sz_wchar_t
0x180073e13  lea     rcx, aLookingUpMatch; "Looking up matching entry in authZ bypa"...
0x180073e1a  mov     [rbp+57h+var_48], 3Bh ; ';'
0x180073e22  lea     rax, [rbp+57h+var_90]
0x180073e26  mov     [rbp+57h+var_50], rcx
0x180073e2a  mov     [rsp+100h+var_D8], rax
0x180073e2f  lea     rcx, dword_180173278
0x180073e36  lea     rdx, dword_180153CEC
0x180073e3d  mov     dword ptr [rsp+100h+var_E0], 5
0x180073e45  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180073e4a  mov     rdx, [r12+8]
0x180073e4f  mov     r8, r14
0x180073e52  mov     rcx, [r12]
0x180073e56  call    IkeDumpAuthzBypassParams
0x180073e5b  mov     rcx, r14
0x180073e5e  call    IkeComputeAuthzBypassHashSignature
0x180073e63  mov     rbx, rax
0x180073e66  test    esi, esi
0x180073e68  jnz     short loc_180073E7B
0x180073e6a  mov     rcx, cs:gIkeExtGlobals
0x180073e71  add     rcx, 78h ; 'x'; lpCriticalSection
0x180073e75  call    cs:__imp_EnterCriticalSection
0x180073e7b  mov     rcx, cs:gIkeExtGlobals
0x180073e82  lea     r8, [rbp+57h+var_B0]
0x180073e86  add     rcx, 990h
0x180073e8d  mov     rdx, rbx
0x180073e90  call    WfpHashtableFind
0x180073e95  jmp     loc_1800740FE
0x180073e9a  lea     rdx, [rsi+38h]
0x180073e9e  mov     rcx, r14
0x180073ea1  call    IkeAddrIsEqual
0x180073ea6  test    eax, eax
0x180073ea8  jz      loc_1800740E6
0x180073eae  mov     rcx, [r12]
0x180073eb2  lea     r14, [rsi+18h]
0x180073eb6  call    IkeIsAnonymousSid
0x180073ebb  test    eax, eax
0x180073ebd  jnz     loc_180074004
0x180073ec3  mov     rcx, [r14]
0x180073ec6  call    IkeIsAnonymousSid
0x180073ecb  test    eax, eax
0x180073ecd  jnz     loc_180074004
0x180073ed3  mov     rdx, [r14]; pSid2
0x180073ed6  mov     rcx, [r12]; pSid1
0x180073eda  call    cs:__imp_EqualSid
0x180073ee0  test    eax, eax
0x180073ee2  jz      loc_18007401A
0x180073ee8  mov     r15d, 1
0x180073eee  mov     rax, [rbp+57h+var_B8]
0x180073ef2  test    rax, rax
0x180073ef5  jz      short loc_180073EFA
0x180073ef7  mov     [rax], rsi
0x180073efa  mov     rdi, cs:WPP_GLOBAL_Control
0x180073f01  lea     rax, WPP_GLOBAL_Control
0x180073f08  cmp     rdi, rax
0x180073f0b  jz      short loc_180073F46
0x180073f0d  cmp     byte ptr [rdi+19h], 4
0x180073f11  jb      short loc_180073F46
0x180073f13  test    byte ptr [rdi+1Ch], 10h
0x180073f17  jz      short loc_180073F46
0x180073f19  mov     rdi, [rdi+10h]
0x180073f1d  call    IkeGetTlsPeerAddr
0x180073f22  mov     rbx, rax
0x180073f25  call    IkeGetTlsMmLuid
0x180073f2a  mov     r9, rax
0x180073f2d  mov     [rsp+100h+var_E0], rbx
0x180073f32  mov     edx, 0Eh
0x180073f37  lea     r8, WPP_79e2b82eafc434f0fa6155cdafc7fda3_Traceguids
0x180073f3e  mov     rcx, rdi
0x180073f41  call    WPP_SF_iS
0x180073f46  mov     eax, cs:dword_180173278
0x180073f4c  cmp     eax, 4
0x180073f4f  jbe     short loc_180073FB2
0x180073f51  call    IkeGetTlsMmLuid
0x180073f56  mov     [rbp+57h+var_B8], rax
0x180073f5a  lea     rax, [rbp+57h+var_B8]
0x180073f5e  mov     [rbp+57h+var_70], rax
0x180073f62  mov     [rbp+57h+var_68], 8
0x180073f6a  call    IkeGetTlsPeerAddr
0x180073f6f  mov     rdx, rax
0x180073f72  lea     rcx, [rbp+57h+var_60]
0x180073f76  call    _tlgCreate1Sz_wchar_t
0x180073f7b  lea     rax, [rbp+57h+var_90]
0x180073f7f  mov     [rbp+57h+var_48], 2Bh ; '+'
0x180073f87  lea     r9, aFoundMatchingE; "Found matching entry in authZ bypass ta"...
0x180073f8e  mov     [rsp+100h+var_D8], rax
0x180073f93  lea     rdx, qword_180153C70
0x180073f9a  mov     dword ptr [rsp+100h+var_E0], 5
0x180073fa2  lea     rcx, dword_180173278
0x180073fa9  mov     [rbp+57h+var_50], r9
0x180073fad  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180073fb2  mov     rdx, [rsi+20h]
0x180073fb6  lea     r8, [rsi+38h]
0x180073fba  mov     rcx, [rsi+18h]
0x180073fbe  call    IkeDumpAuthzBypassParams
0x180073fc3  cmp     [rbp+57h+var_D0], 0
0x180073fc7  jnz     short loc_180073FDA
0x180073fc9  mov     rcx, cs:gIkeExtGlobals
0x180073fd0  add     rcx, 78h ; 'x'; lpCriticalSection
0x180073fd4  call    cs:__imp_LeaveCriticalSection
0x180073fda  mov     eax, r15d
0x180073fdd  mov     rcx, [rbp+57h+var_40]
0x180073fe1  xor     rcx, rsp; StackCookie
0x180073fe4  call    __security_check_cookie
0x180073fe9  mov     rbx, [rsp+100h+arg_10]
0x180073ff1  add     rsp, 0D0h
0x180073ff8  pop     r15
0x180073ffa  pop     r14
0x180073ffc  pop     r13
0x180073ffe  pop     r12
0x180074000  pop     rdi
0x180074001  pop     rsi
0x180074002  pop     rbp
0x180074003  retn
0x180074004  mov     rdx, rsi
0x180074007  mov     rcx, r12
0x18007400a  call    IsMatchingBypassCertInfo
0x18007400f  mov     r15d, eax
0x180074012  test    eax, eax
0x180074014  jnz     loc_180073EEE
0x18007401a  mov     rdi, cs:WPP_GLOBAL_Control
0x180074021  lea     rax, WPP_GLOBAL_Control
0x180074028  cmp     rdi, rax
0x18007402b  jz      short loc_180074066
0x18007402d  cmp     byte ptr [rdi+19h], 4
0x180074031  jb      short loc_180074066
0x180074033  test    byte ptr [rdi+1Ch], 10h
0x180074037  jz      short loc_180074066
0x180074039  mov     rdi, [rdi+10h]
0x18007403d  call    IkeGetTlsPeerAddr
0x180074042  mov     rbx, rax
0x180074045  call    IkeGetTlsMmLuid
0x18007404a  mov     r9, rax
0x18007404d  mov     [rsp+100h+var_E0], rbx
0x180074052  mov     edx, 0Dh
0x180074057  lea     r8, WPP_79e2b82eafc434f0fa6155cdafc7fda3_Traceguids
0x18007405e  mov     rcx, rdi
0x180074061  call    WPP_SF_iS
0x180074066  mov     eax, cs:dword_180173278
0x18007406c  cmp     eax, 4
0x18007406f  jbe     short loc_1800740D2
0x180074071  call    IkeGetTlsMmLuid
0x180074076  mov     [rbp+57h+var_C0], rax
0x18007407a  lea     rax, [rbp+57h+var_C0]
0x18007407e  mov     [rbp+57h+var_70], rax
0x180074082  mov     [rbp+57h+var_68], 8
0x18007408a  call    IkeGetTlsPeerAddr
0x18007408f  mov     rdx, rax
0x180074092  lea     rcx, [rbp+57h+var_60]
0x180074096  call    _tlgCreate1Sz_wchar_t
0x18007409b  lea     rcx, aAuthzBypassTab; "AuthZ bypass table entry didn't match"
0x1800740a2  mov     [rbp+57h+var_48], 26h ; '&'
0x1800740aa  lea     rax, [rbp+57h+var_90]
0x1800740ae  mov     [rbp+57h+var_50], rcx
0x1800740b2  mov     [rsp+100h+var_D8], rax
0x1800740b7  lea     rcx, dword_180173278
0x1800740be  lea     rdx, word_180153CAE
0x1800740c5  mov     dword ptr [rsp+100h+var_E0], 5
0x1800740cd  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x1800740d2  mov     rdx, [rsi+20h]
0x1800740d6  lea     r8, [rsi+38h]
0x1800740da  mov     rcx, [r14]
0x1800740dd  call    IkeDumpAuthzBypassParams
0x1800740e2  mov     r14, [rbp+57h+var_C8]
0x1800740e6  mov     rcx, cs:gIkeExtGlobals
0x1800740ed  lea     rdx, [rbp+57h+var_B0]
0x1800740f1  add     rcx, 990h
0x1800740f8  call    cs:__imp_RtlGetNextEntryHashTable
0x1800740fe  mov     rsi, rax
0x180074101  test    rax, rax
0x180074104  jnz     loc_180073E9A
0x18007410a  jmp     loc_180073FC3
```
