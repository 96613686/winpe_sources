# C2RClientWrapper::GetAreUpdatesLate(int &,ulong)

- ea: `0x180018650`
- end: `0x180018861`
- name: `?GetAreUpdatesLate@C2RClientWrapper@@UEAAJAEAHK@Z`
- size: `529`
- prototype: `__int64 __fastcall(C2RClientWrapper *__hidden this, int *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180017f20`

## callees

- `0x180008f14`
- `0x18000aa64`
- `0x180018650`
- `0x180018e90`
- `0x18003e690`
- `0x1800409e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001881e`
- `KERNEL32!GetLastError` at `0x18001881e`
- `KERNEL32!CompareStringEx` at `0x180018784`
- `KERNEL32!CompareStringEx` at `0x180018810`
- `KERNEL32!CompareStringEx` at `0x180018784`
- `KERNEL32!CompareStringEx` at `0x180018810`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall C2RClientWrapper::GetAreUpdatesLate(C2RClientWrapper *this, int *a2, int a3)
{
  __int64 *RpcClient; // rax
  int v5; // r14d
  unsigned __int64 v6; // rdi
  int cchCount2; // ebx
  int v8; // eax
  int v9; // eax
  int v11; // ebx
  int v12; // eax
  DWORD LastError; // eax
  int v14; // [rsp+50h] [rbp-B0h] BYREF
  int v15; // [rsp+58h] [rbp-A8h] BYREF
  int v16; // [rsp+60h] [rbp-A0h] BYREF
  const WCHAR *v17; // [rsp+68h] [rbp-98h] BYREF
  WCHAR *v18; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v19[7]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v20[2]; // [rsp+B0h] [rbp-50h] BYREF
  int pExceptionObject; // [rsp+C0h] [rbp-40h] BYREF
  __int16 v22; // [rsp+C4h] [rbp-3Ch]
  DWORD v23; // [rsp+2C4h] [rbp+1C4h]
  __int16 v24; // [rsp+2C8h] [rbp+1C8h]
  __int16 v25; // [rsp+3C8h] [rbp+2C8h]
  int v26; // [rsp+448h] [rbp+348h]
  WCHAR String1[4]; // [rsp+450h] [rbp+350h] BYREF
  int v28; // [rsp+458h] [rbp+358h]
  __int16 v29; // [rsp+45Ch] [rbp+35Ch]

  *(_QWORD *)String1 = 0;
  v28 = 0;
  v29 = 0;
  v16 = a3;
  v15 = 7;
  v18 = String1;
  v17 = &LocaleName;
  v14 = 8;
  v19[0] = this;
  v19[1] = &v14;
  v19[2] = &v17;
  v19[3] = &v18;
  v19[4] = &v15;
  v19[5] = &v16;
  v19[6] = v20;
  RpcClient = C2RClientWrapper::get_RpcClient((__int64)this, v20);
  v5 = sub_180018E90(RpcClient, v19);
  if ( v5 >= 0 )
  {
    if ( !String1[0] )
      goto LABEL_7;
    v6 = -1;
    do
      ++v6;
    while ( String1[v6] );
    cchCount2 = OcfxInt32FromSize_t(4u);
    v8 = OcfxInt32FromSize_t(v6);
    v9 = CompareStringEx(&LocaleName, 1u, String1, v8, L"True", cchCount2, 0, 0, 0);
    if ( !v9 )
    {
      v11 = OcfxInt32FromSize_t(4u);
      v12 = OcfxInt32FromSize_t(v6);
      v9 = CompareStringEx(L"en-US", 1u, String1, v12, L"True", v11, 0, 0, 0);
      if ( !v9 )
      {
        LastError = GetLastError();
        pExceptionObject = 15;
        v23 = LastError;
        v26 = 808464432;
        v25 = 0;
        v24 = 0;
        v22 = 0;
        throw (OException *)&pExceptionObject;
      }
    }
    if ( v9 == 2 )
      *a2 = 1;
    else
LABEL_7:
      *a2 = 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180018650  mov     [rsp-8+arg_10], rbx
0x180018655  push    rbp
0x180018656  push    rsi
0x180018657  push    rdi
0x180018658  push    r14
0x18001865a  push    r15
0x18001865c  lea     rbp, [rsp-370h]
0x180018664  sub     rsp, 470h
0x18001866b  mov     rax, cs:__security_cookie
0x180018672  xor     rax, rsp
0x180018675  mov     [rbp+390h+var_30], rax
0x18001867c  mov     rsi, rdx
0x18001867f  xor     eax, eax
0x180018681  mov     qword ptr [rbp+390h+String1], rax
0x180018688  mov     [rbp+390h+var_38], eax
0x18001868e  mov     [rbp+390h+var_34], ax
0x180018695  mov     [rsp+490h+var_430], r8d
0x18001869a  mov     [rsp+490h+var_438], 7
0x1800186a2  lea     rax, [rbp+390h+String1]
0x1800186a9  mov     [rsp+490h+var_420], rax
0x1800186ae  lea     rax, LocaleName
0x1800186b5  mov     [rsp+490h+var_428], rax
0x1800186ba  mov     [rsp+490h+var_440], 8
0x1800186c2  mov     [rsp+490h+var_418], rcx
0x1800186c7  lea     rax, [rsp+490h+var_440]
0x1800186cc  mov     [rbp+390h+var_410], rax
0x1800186d0  lea     rax, [rsp+490h+var_428]
0x1800186d5  mov     [rbp+390h+var_408], rax
0x1800186d9  lea     rax, [rsp+490h+var_420]
0x1800186de  mov     [rbp+390h+var_400], rax
0x1800186e2  lea     rax, [rsp+490h+var_438]
0x1800186e7  mov     [rbp+390h+var_3F8], rax
0x1800186eb  lea     rax, [rsp+490h+var_430]
0x1800186f0  mov     [rbp+390h+var_3F0], rax
0x1800186f4  lea     rax, [rbp+390h+var_3E0]
0x1800186f8  mov     [rbp+390h+var_3E8], rax
0x1800186fc  lea     rdx, [rbp+390h+var_3E0]
0x180018700  call    ?get_RpcClient@C2RClientWrapper@@AEAA?AV?$shared_ptr@VORpcClient@@@std@@XZ; C2RClientWrapper::get_RpcClient(void)
0x180018705  lea     rdx, [rsp+490h+var_418]
0x18001870a  mov     rcx, rax
0x18001870d  call    sub_180018E90
0x180018712  mov     r14d, eax
0x180018715  xor     r15d, r15d
0x180018718  test    eax, eax
0x18001871a  js      short loc_180018796
0x18001871c  cmp     r15w, [rbp+390h+String1]
0x180018724  jz      short loc_180018793
0x180018726  lea     rax, [rbp+390h+String1]
0x18001872d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180018731  inc     rdi
0x180018734  cmp     [rax+rdi*2], r15w
0x180018739  jnz     short loc_180018731
0x18001873b  mov     ecx, 4; unsigned __int64
0x180018740  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x180018745  mov     ebx, eax
0x180018747  mov     rcx, rdi; unsigned __int64
0x18001874a  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x18001874f  mov     [rsp+490h+lParam], r15; lParam
0x180018754  mov     [rsp+490h+lpReserved], r15; lpReserved
0x180018759  mov     [rsp+490h+lpVersionInformation], r15; lpVersionInformation
0x18001875e  mov     [rsp+490h+cchCount2], ebx; cchCount2
0x180018762  lea     rcx, String2; "True"
0x180018769  mov     [rsp+490h+lpString2], rcx; lpString2
0x18001876e  mov     r9d, eax; cchCount1
0x180018771  lea     r8, [rbp+390h+String1]; lpString1
0x180018778  mov     edx, 1; dwCmpFlags
0x18001877d  lea     rcx, LocaleName; lpLocaleName
0x180018784  call    cs:__imp_CompareStringEx
0x18001878a  test    eax, eax
0x18001878c  jz      short loc_1800187C7
0x18001878e  add     eax, 0FFFFFFFEh
0x180018791  jz      short loc_1800187BF
0x180018793  mov     [rsi], r15d
0x180018796  mov     eax, r14d
0x180018799  mov     rcx, [rbp+390h+var_30]
0x1800187a0  xor     rcx, rsp; StackCookie
0x1800187a3  call    __security_check_cookie
0x1800187a8  mov     rbx, [rsp+490h+arg_10]
0x1800187b0  add     rsp, 470h
0x1800187b7  pop     r15
0x1800187b9  pop     r14
0x1800187bb  pop     rdi
0x1800187bc  pop     rsi
0x1800187bd  pop     rbp
0x1800187be  retn
0x1800187bf  mov     dword ptr [rsi], 1
0x1800187c5  jmp     short loc_180018796
0x1800187c7  mov     ecx, 4; unsigned __int64
0x1800187cc  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x1800187d1  mov     ebx, eax
0x1800187d3  mov     rcx, rdi; unsigned __int64
0x1800187d6  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x1800187db  mov     [rsp+490h+lParam], r15; lParam
0x1800187e0  mov     [rsp+490h+lpReserved], r15; lpReserved
0x1800187e5  mov     [rsp+490h+lpVersionInformation], r15; lpVersionInformation
0x1800187ea  mov     [rsp+490h+cchCount2], ebx; cchCount2
0x1800187ee  lea     rcx, String2; "True"
0x1800187f5  mov     [rsp+490h+lpString2], rcx; lpString2
0x1800187fa  mov     r9d, eax; cchCount1
0x1800187fd  lea     r8, [rbp+390h+String1]; lpString1
0x180018804  mov     edx, 1; dwCmpFlags
0x180018809  lea     rcx, aEnUs; "en-US"
0x180018810  call    cs:__imp_CompareStringEx
0x180018816  test    eax, eax
0x180018818  jnz     loc_18001878E
0x18001881e  call    cs:__imp_GetLastError
0x180018824  mov     [rbp+390h+pExceptionObject], 0Fh
0x18001882b  mov     [rbp+390h+var_1CC], eax
0x180018831  mov     [rbp+390h+var_48], 30303030h
0x18001883b  mov     [rbp+390h+var_C8], r15w
0x180018843  mov     [rbp+390h+var_1C8], r15w
0x18001884b  mov     [rbp+390h+var_3CC], r15w
0x180018850  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x180018857  lea     rcx, [rbp+390h+pExceptionObject]; pExceptionObject
0x18001885b  call    _CxxThrowException
```
