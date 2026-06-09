# CTscCredentialsQueryUi::CreateInputAuthBlob(ushort *,ushort const *,void * *,ulong *,ulong)

- ea: `0x140095b90`
- end: `0x140095e02`
- name: `?CreateInputAuthBlob@CTscCredentialsQueryUi@@QEAAKPEAGPEBGPEAPEAXPEAKK@Z`
- size: `626`
- prototype: `unsigned int(CTscCredentialsQueryUi *__hidden this, unsigned __int16 *, const unsigned __int16 *, void **, unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140096c80`

## callees

- `0x140004703`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x140095b90`
- `0x14009693c`
- `0x1400b3ef0`
- `0x140113322`
- `0x140113390`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140095d48`
- `KERNEL32!LocalFree` at `0x140095d48`
- `KERNEL32!GetLastError` at `0x140095ca6`
- `KERNEL32!GetLastError` at `0x140095cf6`
- `KERNEL32!GetLastError` at `0x140095ca6`
- `KERNEL32!GetLastError` at `0x140095cf6`
- `ole32!CLSIDFromString` at `0x140095c5f`
- `ole32!CLSIDFromString` at `0x140095c5f`
- `credui!CredPackAuthenticationBufferW` at `0x140095c9c`
- `credui!CredPackAuthenticationBufferW` at `0x140095ce8`
- `credui!CredPackAuthenticationBufferW` at `0x140095c9c`
- `credui!CredPackAuthenticationBufferW` at `0x140095ce8`

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
0x140095b90  push    rbx
0x140095b92  push    rbp
0x140095b93  push    rsi
0x140095b94  push    rdi
0x140095b95  push    r12
0x140095b97  push    r14
0x140095b99  push    r15
0x140095b9b  sub     rsp, 50h
0x140095b9f  mov     rax, cs:__security_cookie
0x140095ba6  xor     rax, rsp
0x140095ba9  mov     [rsp+88h+var_40], rax
0x140095bae  mov     r14, [rsp+88h+arg_20]
0x140095bb6  xorps   xmm0, xmm0
0x140095bb9  mov     dword ptr [rsp+88h+Size], 0
0x140095bc1  mov     r15, r9
0x140095bc4  mov     rbx, r8
0x140095bc7  mov     r12, rdx
0x140095bca  movups  xmmword ptr [rsp+88h+pclsid.Data1], xmm0
0x140095bcf  test    r9, r9
0x140095bd2  jz      loc_140095D9C
0x140095bd8  test    r14, r14
0x140095bdb  jz      loc_140095D9C
0x140095be1  test    byte ptr [rsp+88h+arg_28], 1
0x140095be9  mov     qword ptr [r9], 0
0x140095bf0  mov     dword ptr [r14], 0
0x140095bf7  jz      short loc_140095C3D
0x140095bf9  mov     ecx, 48h ; 'H'; size
0x140095bfe  mov     dword ptr [rsp+88h+Size], ecx
0x140095c02  call    MIDL_user_allocate
0x140095c07  mov     rdi, rax
0x140095c0a  test    rax, rax
0x140095c0d  jnz     short loc_140095C17
0x140095c0f  lea     ebx, [rax+8]
0x140095c12  jmp     loc_140095DE4
0x140095c17  mov     r8d, dword ptr [rsp+88h+Size]; Size
0x140095c1c  xor     edx, edx; Val
0x140095c1e  mov     rcx, rdi; void *
0x140095c21  call    memset_0
0x140095c26  mov     dword ptr [rdi], 0Dh
0x140095c2c  mov     eax, dword ptr [rsp+88h+Size]
0x140095c30  xor     ebx, ebx
0x140095c32  mov     [r15], rdi
0x140095c35  mov     [r14], eax
0x140095c38  jmp     loc_140095DE4
0x140095c3d  xor     edi, edi
0x140095c3f  test    r12, r12
0x140095c42  jz      short loc_140095C2C
0x140095c44  xor     ebp, ebp
0x140095c46  call    ?IsOSVersionWin8OrLater@CTscCredentialsQueryUi@@CAHXZ; CTscCredentialsQueryUi::IsOSVersionWin8OrLater(void)
0x140095c4b  lea     esi, [rdi+8]
0x140095c4e  test    eax, eax
0x140095c50  jz      short loc_140095C83
0x140095c52  test    rbx, rbx
0x140095c55  jz      short loc_140095C83
0x140095c57  lea     rdx, [rsp+88h+pclsid]; pclsid
0x140095c5c  mov     rcx, rbx; lpsz
0x140095c5f  call    cs:__imp_CLSIDFromString
0x140095c65  test    eax, eax
0x140095c67  js      short loc_140095C83
0x140095c69  lea     r8d, [rdi+10h]; Size
0x140095c6d  lea     rdx, SEC_WINNT_AUTH_DATA_TYPE_PASSWORD; Buf2
0x140095c74  lea     rcx, [rsp+88h+pclsid]; Buf1
0x140095c79  call    memcmp_0
0x140095c7e  test    eax, eax
0x140095c80  cmovz   ebp, esi
0x140095c83  lea     rax, [rsp+88h+Size]
0x140095c88  xor     r9d, r9d; pPackedCredentials
0x140095c8b  lea     r8, pszPassword; pszPassword
0x140095c92  mov     [rsp+88h+pcbPackedCredentials], rax; pcbPackedCredentials
0x140095c97  mov     rdx, r12; pszUserName
0x140095c9a  mov     ecx, ebp; dwFlags
0x140095c9c  call    cs:__imp_CredPackAuthenticationBufferW
0x140095ca2  test    eax, eax
0x140095ca4  jnz     short loc_140095C2C
0x140095ca6  call    cs:__imp_GetLastError
0x140095cac  mov     ebx, eax
0x140095cae  cmp     eax, 7Ah ; 'z'
0x140095cb1  jnz     loc_140095D53
0x140095cb7  mov     ecx, dword ptr [rsp+88h+Size]; size
0x140095cbb  call    MIDL_user_allocate
0x140095cc0  mov     rdi, rax
0x140095cc3  test    rax, rax
0x140095cc6  jnz     short loc_140095CCF
0x140095cc8  mov     ebx, esi
0x140095cca  jmp     loc_140095DE4
0x140095ccf  lea     rax, [rsp+88h+Size]
0x140095cd4  mov     r9, rdi; pPackedCredentials
0x140095cd7  lea     r8, pszPassword; pszPassword
0x140095cde  mov     [rsp+88h+pcbPackedCredentials], rax; pcbPackedCredentials
0x140095ce3  mov     rdx, r12; pszUserName
0x140095ce6  mov     ecx, ebp; dwFlags
0x140095ce8  call    cs:__imp_CredPackAuthenticationBufferW
0x140095cee  test    eax, eax
0x140095cf0  jnz     loc_140095C2C
0x140095cf6  call    cs:__imp_GetLastError
0x140095cfc  mov     ebx, eax
0x140095cfe  mov     rcx, cs:WPP_GLOBAL_Control
0x140095d05  lea     rax, WPP_GLOBAL_Control
0x140095d0c  cmp     rcx, rax
0x140095d0f  jz      short loc_140095D45
0x140095d11  test    byte ptr [rcx+1Ch], 1
0x140095d15  jz      short loc_140095D45
0x140095d17  cmp     byte ptr [rcx+19h], 2
0x140095d1b  jb      short loc_140095D45
0x140095d1d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140095d22  mov     rcx, cs:WPP_GLOBAL_Control
0x140095d29  lea     r8, WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids
0x140095d30  mov     edx, 24h ; '$'
0x140095d35  mov     dword ptr [rsp+88h+pcbPackedCredentials], ebx
0x140095d39  mov     r9d, eax
0x140095d3c  mov     rcx, [rcx+10h]
0x140095d40  call    WPP_SF_Dd
0x140095d45  mov     rcx, rdi; hMem
0x140095d48  call    cs:__imp_LocalFree
0x140095d4e  jmp     loc_140095DE4
0x140095d53  mov     rcx, cs:WPP_GLOBAL_Control
0x140095d5a  lea     rax, WPP_GLOBAL_Control
0x140095d61  cmp     rcx, rax
0x140095d64  jz      short loc_140095DE4
0x140095d66  test    byte ptr [rcx+1Ch], 1
0x140095d6a  jz      short loc_140095DE4
0x140095d6c  cmp     byte ptr [rcx+19h], 2
0x140095d70  jb      short loc_140095DE4
0x140095d72  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140095d77  mov     rcx, cs:WPP_GLOBAL_Control
0x140095d7e  lea     r8, WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids
0x140095d85  mov     edx, 25h ; '%'
0x140095d8a  mov     dword ptr [rsp+88h+pcbPackedCredentials], ebx
0x140095d8e  mov     r9d, eax
0x140095d91  mov     rcx, [rcx+10h]
0x140095d95  call    WPP_SF_Dd
0x140095d9a  jmp     short loc_140095DE4
0x140095d9c  mov     rcx, cs:WPP_GLOBAL_Control
0x140095da3  lea     rax, WPP_GLOBAL_Control
0x140095daa  cmp     rcx, rax
0x140095dad  jz      short loc_140095DDF
0x140095daf  test    byte ptr [rcx+1Ch], 1
0x140095db3  jz      short loc_140095DDF
0x140095db5  cmp     byte ptr [rcx+19h], 2
0x140095db9  jb      short loc_140095DDF
0x140095dbb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140095dc0  mov     rcx, cs:WPP_GLOBAL_Control
0x140095dc7  lea     r8, WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids
0x140095dce  mov     edx, 23h ; '#'
0x140095dd3  mov     r9d, eax
0x140095dd6  mov     rcx, [rcx+10h]
0x140095dda  call    WPP_SF_d
0x140095ddf  mov     ebx, 57h ; 'W'
0x140095de4  mov     eax, ebx
0x140095de6  mov     rcx, [rsp+88h+var_40]
0x140095deb  xor     rcx, rsp; StackCookie
0x140095dee  call    __security_check_cookie
0x140095df3  add     rsp, 50h
0x140095df7  pop     r15
0x140095df9  pop     r14
0x140095dfb  pop     r12
0x140095dfd  pop     rdi
0x140095dfe  pop     rsi
0x140095dff  pop     rbp
0x140095e00  pop     rbx
0x140095e01  retn
```
