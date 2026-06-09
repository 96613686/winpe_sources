# CTscCredentialsQueryUi::CreateInputAuthBlob(ushort *,ushort const *,void * *,ulong *,ulong)

- ea: `0x140093a20`
- end: `0x140093c92`
- name: `?CreateInputAuthBlob@CTscCredentialsQueryUi@@QEAAKPEAGPEBGPEAPEAXPEAKK@Z`
- size: `626`
- prototype: `unsigned int(CTscCredentialsQueryUi *__hidden this, unsigned __int16 *, const unsigned __int16 *, void **, unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140094b10`

## callees

- `0x140004703`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x140093a20`
- `0x1400947cc`
- `0x1400b1d80`
- `0x1401111b2`
- `0x140111220`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140093bd8`
- `KERNEL32!LocalFree` at `0x140093bd8`
- `KERNEL32!GetLastError` at `0x140093b36`
- `KERNEL32!GetLastError` at `0x140093b86`
- `KERNEL32!GetLastError` at `0x140093b36`
- `KERNEL32!GetLastError` at `0x140093b86`
- `ole32!CLSIDFromString` at `0x140093aef`
- `ole32!CLSIDFromString` at `0x140093aef`
- `credui!CredPackAuthenticationBufferW` at `0x140093b2c`
- `credui!CredPackAuthenticationBufferW` at `0x140093b78`
- `credui!CredPackAuthenticationBufferW` at `0x140093b2c`
- `credui!CredPackAuthenticationBufferW` at `0x140093b78`

## pseudocode

```c
__int64 __fastcall CTscCredentialsQueryUi::CreateInputAuthBlob(
        CTscCredentialsQueryUi *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        void **a4,
        unsigned int *a5,
        char a6)
{
  _DWORD *v9; // rax
  _DWORD *v10; // rdi
  DWORD LastError; // ebx
  unsigned int v12; // eax
  DWORD v13; // ebp
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  size_t Size; // [rsp+30h] [rbp-58h] BYREF
  GUID pclsid; // [rsp+38h] [rbp-50h] BYREF

  LODWORD(Size) = 0;
  pclsid = 0;
  if ( a4 && a5 )
  {
    *a4 = 0;
    *a5 = 0;
    if ( (a6 & 1) != 0 )
    {
      LODWORD(Size) = 72;
      v9 = MIDL_user_allocate(0x48u);
      v10 = v9;
      if ( !v9 )
        return 8;
      memset_0(v9, 0, (unsigned int)Size);
      *v10 = 13;
LABEL_7:
      v12 = Size;
      LastError = 0;
      *a4 = v10;
      *a5 = v12;
      return LastError;
    }
    v10 = 0;
    if ( !a2 )
      goto LABEL_7;
    v13 = 0;
    if ( (unsigned int)CTscCredentialsQueryUi::IsOSVersionWin8OrLater()
      && a3
      && CLSIDFromString(a3, &pclsid) >= 0
      && !memcmp_0(&pclsid, &SEC_WINNT_AUTH_DATA_TYPE_PASSWORD, 0x10u) )
    {
      v13 = 8;
    }
    if ( CredPackAuthenticationBufferW(v13, a2, (LPWSTR)&pszPassword, 0, (DWORD *)&Size) )
      goto LABEL_7;
    LastError = GetLastError();
    if ( LastError == 122 )
    {
      v10 = MIDL_user_allocate((unsigned int)Size);
      if ( !v10 )
        return 8;
      if ( CredPackAuthenticationBufferW(v13, a2, (LPWSTR)&pszPassword, (PBYTE)v10, (DWORD *)&Size) )
        goto LABEL_7;
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          36,
          WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids,
          CurrentThreadActivityIdPrefix,
          LastError);
      }
      LocalFree(v10);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids,
        v15,
        LastError);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids, v16);
    }
    return 87;
  }
  return LastError;
}

```

## disassembly

```asm
0x140093a20  push    rbx
0x140093a22  push    rbp
0x140093a23  push    rsi
0x140093a24  push    rdi
0x140093a25  push    r12
0x140093a27  push    r14
0x140093a29  push    r15
0x140093a2b  sub     rsp, 50h
0x140093a2f  mov     rax, cs:__security_cookie
0x140093a36  xor     rax, rsp
0x140093a39  mov     [rsp+88h+var_40], rax
0x140093a3e  mov     r14, [rsp+88h+arg_20]
0x140093a46  xorps   xmm0, xmm0
0x140093a49  mov     dword ptr [rsp+88h+Size], 0
0x140093a51  mov     r15, r9
0x140093a54  mov     rbx, r8
0x140093a57  mov     r12, rdx
0x140093a5a  movups  xmmword ptr [rsp+88h+pclsid.Data1], xmm0
0x140093a5f  test    r9, r9
0x140093a62  jz      loc_140093C2C
0x140093a68  test    r14, r14
0x140093a6b  jz      loc_140093C2C
0x140093a71  test    byte ptr [rsp+88h+arg_28], 1
0x140093a79  mov     qword ptr [r9], 0
0x140093a80  mov     dword ptr [r14], 0
0x140093a87  jz      short loc_140093ACD
0x140093a89  mov     ecx, 48h ; 'H'; size
0x140093a8e  mov     dword ptr [rsp+88h+Size], ecx
0x140093a92  call    MIDL_user_allocate
0x140093a97  mov     rdi, rax
0x140093a9a  test    rax, rax
0x140093a9d  jnz     short loc_140093AA7
0x140093a9f  lea     ebx, [rax+8]
0x140093aa2  jmp     loc_140093C74
0x140093aa7  mov     r8d, dword ptr [rsp+88h+Size]; Size
0x140093aac  xor     edx, edx; Val
0x140093aae  mov     rcx, rdi; void *
0x140093ab1  call    memset_0
0x140093ab6  mov     dword ptr [rdi], 0Dh
0x140093abc  mov     eax, dword ptr [rsp+88h+Size]
0x140093ac0  xor     ebx, ebx
0x140093ac2  mov     [r15], rdi
0x140093ac5  mov     [r14], eax
0x140093ac8  jmp     loc_140093C74
0x140093acd  xor     edi, edi
0x140093acf  test    r12, r12
0x140093ad2  jz      short loc_140093ABC
0x140093ad4  xor     ebp, ebp
0x140093ad6  call    ?IsOSVersionWin8OrLater@CTscCredentialsQueryUi@@CAHXZ; CTscCredentialsQueryUi::IsOSVersionWin8OrLater(void)
0x140093adb  lea     esi, [rdi+8]
0x140093ade  test    eax, eax
0x140093ae0  jz      short loc_140093B13
0x140093ae2  test    rbx, rbx
0x140093ae5  jz      short loc_140093B13
0x140093ae7  lea     rdx, [rsp+88h+pclsid]; pclsid
0x140093aec  mov     rcx, rbx; lpsz
0x140093aef  call    cs:__imp_CLSIDFromString
0x140093af5  test    eax, eax
0x140093af7  js      short loc_140093B13
0x140093af9  lea     r8d, [rdi+10h]; Size
0x140093afd  lea     rdx, SEC_WINNT_AUTH_DATA_TYPE_PASSWORD; Buf2
0x140093b04  lea     rcx, [rsp+88h+pclsid]; Buf1
0x140093b09  call    memcmp_0
0x140093b0e  test    eax, eax
0x140093b10  cmovz   ebp, esi
0x140093b13  lea     rax, [rsp+88h+Size]
0x140093b18  xor     r9d, r9d; pPackedCredentials
0x140093b1b  lea     r8, pszPassword; pszPassword
0x140093b22  mov     [rsp+88h+pcbPackedCredentials], rax; pcbPackedCredentials
0x140093b27  mov     rdx, r12; pszUserName
0x140093b2a  mov     ecx, ebp; dwFlags
0x140093b2c  call    cs:__imp_CredPackAuthenticationBufferW
0x140093b32  test    eax, eax
0x140093b34  jnz     short loc_140093ABC
0x140093b36  call    cs:__imp_GetLastError
0x140093b3c  mov     ebx, eax
0x140093b3e  cmp     eax, 7Ah ; 'z'
0x140093b41  jnz     loc_140093BE3
0x140093b47  mov     ecx, dword ptr [rsp+88h+Size]; size
0x140093b4b  call    MIDL_user_allocate
0x140093b50  mov     rdi, rax
0x140093b53  test    rax, rax
0x140093b56  jnz     short loc_140093B5F
0x140093b58  mov     ebx, esi
0x140093b5a  jmp     loc_140093C74
0x140093b5f  lea     rax, [rsp+88h+Size]
0x140093b64  mov     r9, rdi; pPackedCredentials
0x140093b67  lea     r8, pszPassword; pszPassword
0x140093b6e  mov     [rsp+88h+pcbPackedCredentials], rax; pcbPackedCredentials
0x140093b73  mov     rdx, r12; pszUserName
0x140093b76  mov     ecx, ebp; dwFlags
0x140093b78  call    cs:__imp_CredPackAuthenticationBufferW
0x140093b7e  test    eax, eax
0x140093b80  jnz     loc_140093ABC
0x140093b86  call    cs:__imp_GetLastError
0x140093b8c  mov     ebx, eax
0x140093b8e  mov     rcx, cs:WPP_GLOBAL_Control
0x140093b95  lea     rax, WPP_GLOBAL_Control
0x140093b9c  cmp     rcx, rax
0x140093b9f  jz      short loc_140093BD5
0x140093ba1  test    byte ptr [rcx+1Ch], 1
0x140093ba5  jz      short loc_140093BD5
0x140093ba7  cmp     byte ptr [rcx+19h], 2
0x140093bab  jb      short loc_140093BD5
0x140093bad  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140093bb2  mov     rcx, cs:WPP_GLOBAL_Control
0x140093bb9  lea     r8, WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids
0x140093bc0  mov     edx, 24h ; '$'
0x140093bc5  mov     dword ptr [rsp+88h+pcbPackedCredentials], ebx
0x140093bc9  mov     r9d, eax
0x140093bcc  mov     rcx, [rcx+10h]
0x140093bd0  call    WPP_SF_Dd
0x140093bd5  mov     rcx, rdi; hMem
0x140093bd8  call    cs:__imp_LocalFree
0x140093bde  jmp     loc_140093C74
0x140093be3  mov     rcx, cs:WPP_GLOBAL_Control
0x140093bea  lea     rax, WPP_GLOBAL_Control
0x140093bf1  cmp     rcx, rax
0x140093bf4  jz      short loc_140093C74
0x140093bf6  test    byte ptr [rcx+1Ch], 1
0x140093bfa  jz      short loc_140093C74
0x140093bfc  cmp     byte ptr [rcx+19h], 2
0x140093c00  jb      short loc_140093C74
0x140093c02  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140093c07  mov     rcx, cs:WPP_GLOBAL_Control
0x140093c0e  lea     r8, WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids
0x140093c15  mov     edx, 25h ; '%'
0x140093c1a  mov     dword ptr [rsp+88h+pcbPackedCredentials], ebx
0x140093c1e  mov     r9d, eax
0x140093c21  mov     rcx, [rcx+10h]
0x140093c25  call    WPP_SF_Dd
0x140093c2a  jmp     short loc_140093C74
0x140093c2c  mov     rcx, cs:WPP_GLOBAL_Control
0x140093c33  lea     rax, WPP_GLOBAL_Control
0x140093c3a  cmp     rcx, rax
0x140093c3d  jz      short loc_140093C6F
0x140093c3f  test    byte ptr [rcx+1Ch], 1
0x140093c43  jz      short loc_140093C6F
0x140093c45  cmp     byte ptr [rcx+19h], 2
0x140093c49  jb      short loc_140093C6F
0x140093c4b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140093c50  mov     rcx, cs:WPP_GLOBAL_Control
0x140093c57  lea     r8, WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids
0x140093c5e  mov     edx, 23h ; '#'
0x140093c63  mov     r9d, eax
0x140093c66  mov     rcx, [rcx+10h]
0x140093c6a  call    WPP_SF_d
0x140093c6f  mov     ebx, 57h ; 'W'
0x140093c74  mov     eax, ebx
0x140093c76  mov     rcx, [rsp+88h+var_40]
0x140093c7b  xor     rcx, rsp; StackCookie
0x140093c7e  call    __security_check_cookie
0x140093c83  add     rsp, 50h
0x140093c87  pop     r15
0x140093c89  pop     r14
0x140093c8b  pop     r12
0x140093c8d  pop     rdi
0x140093c8e  pop     rsi
0x140093c8f  pop     rbp
0x140093c90  pop     rbx
0x140093c91  retn
```
