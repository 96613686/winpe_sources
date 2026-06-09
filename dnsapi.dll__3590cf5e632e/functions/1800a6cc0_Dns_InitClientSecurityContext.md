# Dns_InitClientSecurityContext

- ea: `0x1800a6cc0`
- end: `0x1800a7189`
- name: `Dns_InitClientSecurityContext`
- size: `1225`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x18006adbc`

## callees

- `0x180029d80`
- `0x18006b704`
- `0x180076188`
- `0x18008b5f0`
- `0x18008bf98`
- `0x1800a6cc0`
- `0x1800a7650`
- `0x1800a77c4`
- `0x1800cafe0`
- `0x1800d4408`
- `0x1800d4918`
- `0x1800d49fc`
- `0x1800dbe9c`
- `0x1800dc9e0`
- `0x1800ddfa8`
- `0x1800de650`
- `0x1800dfcac`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a6e85`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a6f42`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a6e85`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800a6f42`
- `SspiCli!QueryContextAttributesW` at `0x1800a702a`
- `SspiCli!QueryContextAttributesW` at `0x1800a702a`
- `SspiCli!InitializeSecurityContextW` at `0x1800a6f2b`
- `SspiCli!InitializeSecurityContextW` at `0x1800a6f2b`

## string_xrefs

- `0x1800a6d37`: `InitClientSecurityContext() at top. `
- `0x1800a6eb6`: `Before call to InitClientSecurityContextW(). `
- `0x1800a7141`: `Security Context`
- `0x1800a7150`: `Security Session Packet Info`

## pseudocode

```c
int __fastcall Dns_InitClientSecurityContext(__int64 *a1, __int64 a2, int *a3)
{
  __int64 v5; // rsi
  int result; // eax
  const void *v7; // rcx
  unsigned int v8; // eax
  SECURITY_STATUS DefaultCredentialsHandle; // ebx
  void *v10; // rax
  size_t v11; // r8
  _DWORD *v12; // r15
  int v13; // r14d
  DWORD TickCount; // eax
  struct _SecBufferDesc *v15; // rcx
  int v16; // eax
  struct _SecHandle *v17; // rdx
  int v18; // edx
  int v19; // ecx
  DWORD v20; // eax
  int v21; // edx
  int v22; // ecx
  int v23; // r8d
  unsigned int v24; // r8d
  int v25; // edx
  SECURITY_STATUS v26; // eax
  __int64 v27; // r9
  int pInput; // [rsp+30h] [rbp-D0h]
  int Reserved2; // [rsp+38h] [rbp-C8h]
  int phNewContext; // [rsp+40h] [rbp-C0h]
  PCredHandle phCredential; // [rsp+60h] [rbp-A0h] BYREF
  struct _SecBufferDesc pOutput; // [rsp+68h] [rbp-98h] BYREF
  struct _SecBufferDesc v33; // [rsp+78h] [rbp-88h] BYREF
  unsigned int pfContextAttr; // [rsp+88h] [rbp-78h] BYREF
  SECURITY_INTEGER ptsExpiry; // [rsp+90h] [rbp-70h] BYREF
  __int128 pBuffer; // [rsp+98h] [rbp-68h] BYREF
  SEC_WCHAR pszTargetName[264]; // [rsp+B0h] [rbp-50h] BYREF

  ptsExpiry.QuadPart = 0;
  pOutput = 0;
  pfContextAttr = 0;
  v33 = 0;
  phCredential = 0;
  if ( (BYTE1(xmmword_1801119E0) & 0x40) != 0 )
    WPP_SF_(1038, 27, WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids);
  DnsPrint_SecurityPacketInfo("InitClientSecurityContext() at top. ", a1);
  v5 = *a1;
  if ( !*a1 )
  {
    if ( (BYTE1(xmmword_1801119E0) & 0x40) != 0 )
      WPP_SF_(1038, 28, WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids);
    return 14;
  }
  if ( *(_DWORD *)(v5 + 148) )
  {
    v7 = (const void *)a1[4];
    if ( !v7
      || (v8 = *((_DWORD *)a1 + 6), v8 != *((_DWORD *)a1 + 2))
      || (result = memcmp_0(v7, (const void *)a1[2], v8)) != 0 )
    {
      if ( SBYTE3(xmmword_1801119E0) < 0 )
        WPP_SF_q(1055, 29, WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids, v5);
      return 9017;
    }
    return result;
  }
  if ( *(_DWORD *)(v5 + 140) )
  {
    phCredential = (PCredHandle)(v5 + 112);
    goto LABEL_17;
  }
  DefaultCredentialsHandle = getDefaultCredentialsHandle(&phCredential);
  if ( !DefaultCredentialsHandle )
  {
LABEL_17:
    v10 = (void *)a1[4];
    if ( !v10 )
    {
      v10 = (void *)Dns_Allocate((unsigned int)g_SecurityTokenMaxLength);
      if ( !v10 )
      {
        DefaultCredentialsHandle = 14;
        goto LABEL_67;
      }
      a1[4] = (__int64)v10;
      *((_DWORD *)a1 + 7) = 2;
    }
    v11 = (unsigned int)g_SecurityTokenMaxLength;
    v12 = a1 + 3;
    v13 = 1;
    *((_DWORD *)a1 + 6) = g_SecurityTokenMaxLength;
    pOutput.cBuffers = 1;
    pOutput.pBuffers = (PSecBuffer)(a1 + 3);
    pOutput.ulVersion = 0;
    memset_0(v10, 0, v11);
    if ( a1[2] )
    {
      v33.ulVersion = 0;
      v33.pBuffers = (PSecBuffer)(a1 + 1);
      v33.cBuffers = 1;
    }
    if ( (unsigned int)MakeKerberosName(pszTargetName) )
    {
      DefaultCredentialsHandle = 13;
      goto LABEL_67;
    }
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    {
      TickCount = GetTickCount();
      WPP_SF_dS(
        1035,
        30,
        (unsigned int)WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids,
        TickCount,
        (__int64)pszTargetName);
    }
    DnsPrint_SecurityPacketInfo("Before call to InitClientSecurityContextW(). ", a1);
    if ( *(_DWORD *)(v5 + 144) )
    {
      v15 = &v33;
      v16 = 0;
    }
    else
    {
      v16 = 1;
      v15 = 0;
    }
    v17 = 0;
    if ( !v16 )
      v17 = (struct _SecHandle *)(v5 + 8);
    DefaultCredentialsHandle = InitializeSecurityContextW(
                                 phCredential,
                                 v17,
                                 pszTargetName,
                                 0x10007u,
                                 0,
                                 0x10u,
                                 v15,
                                 0,
                                 (PCtxtHandle)(v5 + 8),
                                 &pOutput,
                                 &pfContextAttr,
                                 &ptsExpiry);
    if ( (BYTE1(xmmword_1801119E0) & 0x40) != 0 )
    {
      v20 = GetTickCount();
      WPP_SF_dSDdD(
        v22,
        v21,
        v23,
        v20,
        (__int64)pszTargetName,
        pfContextAttr,
        DefaultCredentialsHandle,
        DefaultCredentialsHandle);
    }
    v24 = pfContextAttr;
    if ( g_fVelocityDisableInternalExports )
    {
      if ( DefaultCredentialsHandle )
      {
        if ( ((DefaultCredentialsHandle - 590610) & 0xFFFFFFFD) == 0 )
          goto LABEL_44;
      }
      else
      {
        v19 = 65538;
        if ( (pfContextAttr & 0x10002) == 0x10002 )
        {
LABEL_44:
          *(_DWORD *)(v5 + 144) = 1;
          if ( (BYTE1(xmmword_1801119E0) & 0x40) != 0 )
            WPP_SF_Ddqdqqd(
              v19,
              v18,
              v24,
              DefaultCredentialsHandle,
              DefaultCredentialsHandle,
              v5 + 8,
              pOutput.cBuffers,
              (__int64)pOutput.pBuffers,
              a1[4],
              *v12);
          if ( DefaultCredentialsHandle )
            goto LABEL_59;
          pBuffer = 0;
          v26 = QueryContextAttributesW((PCtxtHandle)(v5 + 8), 0, &pBuffer);
          DefaultCredentialsHandle = v26;
          if ( g_fVelocityDisableInternalExports )
          {
            if ( v26 )
              goto LABEL_67;
          }
          else if ( v26 < 0 )
          {
            goto LABEL_67;
          }
          v27 = (unsigned int)g_SignatureMaxLength;
          if ( DWORD1(pBuffer) > g_SignatureMaxLength )
          {
            v27 = DWORD1(pBuffer);
            g_SignatureMaxLength = DWORD1(pBuffer);
          }
          if ( (BYTE1(xmmword_1801119E0) & 0x40) != 0 )
            WPP_SF_d(1038, 35, WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids, v27);
          if ( DefaultCredentialsHandle )
          {
LABEL_59:
            if ( (BYTE1(xmmword_1801119E0) & 0x40) != 0 )
              WPP_SF_d(1038, 36, WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids, DefaultCredentialsHandle == 590612);
            DefaultCredentialsHandle = 9801;
            *(_DWORD *)(v5 + 148) = 0;
            v13 = 0;
          }
          else
          {
            *(_DWORD *)(v5 + 148) = 1;
            if ( *v12 )
              DefaultCredentialsHandle = 9801;
          }
          *a3 = v13;
          goto LABEL_67;
        }
      }
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      {
        v25 = 32;
LABEL_65:
        WPP_SF_dddddddd(
          v19,
          v25,
          pfContextAttr,
          DefaultCredentialsHandle,
          DefaultCredentialsHandle,
          pfContextAttr,
          pInput,
          Reserved2,
          phNewContext,
          SBYTE4(ptsExpiry.QuadPart),
          ptsExpiry.QuadPart);
      }
    }
    else
    {
      if ( DefaultCredentialsHandle >= 0 )
      {
        if ( DefaultCredentialsHandle )
          goto LABEL_44;
        v19 = 65538;
        if ( (pfContextAttr & 0x10002) == 0x10002 )
          goto LABEL_44;
      }
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      {
        v25 = 33;
        goto LABEL_65;
      }
    }
    DefaultCredentialsHandle = 9017;
  }
LABEL_67:
  if ( (BYTE1(xmmword_1801119E0) & 0x40) != 0 )
    WPP_SF_Dd(
      1038,
      37,
      WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids,
      (unsigned int)DefaultCredentialsHandle,
      DefaultCredentialsHandle);
  DnsPrint_SecurityContext("Security Context", v5);
  DnsPrint_SecurityPacketInfo("Security Session Packet Info", a1);
  return DefaultCredentialsHandle;
}

```

## disassembly

```asm
0x1800a6cc0  mov     [rsp-8+arg_18], rbx
0x1800a6cc5  push    rbp
0x1800a6cc6  push    rsi
0x1800a6cc7  push    rdi
0x1800a6cc8  push    r12
0x1800a6cca  push    r13
0x1800a6ccc  push    r14
0x1800a6cce  push    r15
0x1800a6cd0  lea     rbp, [rsp-1D0h]
0x1800a6cd8  sub     rsp, 2D0h
0x1800a6cdf  mov     rax, cs:__security_cookie
0x1800a6ce6  xor     rax, rsp
0x1800a6ce9  mov     [rbp+200h+var_40], rax
0x1800a6cf0  xor     ebx, ebx
0x1800a6cf2  xorps   xmm0, xmm0
0x1800a6cf5  xorps   xmm1, xmm1
0x1800a6cf8  mov     qword ptr [rbp+200h+var_270], rbx
0x1800a6cfc  movups  xmmword ptr [rsp+300h+var_298.ulVersion], xmm0
0x1800a6d01  mov     [rbp+200h+var_278], ebx
0x1800a6d04  mov     r13, r8
0x1800a6d07  movups  xmmword ptr [rsp+300h+var_288.ulVersion], xmm1
0x1800a6d0c  mov     [rsp+300h+phCredential], rbx
0x1800a6d11  mov     r12, rdx
0x1800a6d14  mov     rdi, rcx
0x1800a6d17  test    byte ptr cs:xmmword_1801119E0+1, 40h
0x1800a6d1e  jz      short loc_1800A6D34
0x1800a6d20  lea     edx, [rbx+1Bh]
0x1800a6d23  mov     ecx, 40Eh
0x1800a6d28  lea     r8, WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids
0x1800a6d2f  call    WPP_SF_
0x1800a6d34  mov     rdx, rdi
0x1800a6d37  lea     rcx, aInitclientsecu; "InitClientSecurityContext() at top. "
0x1800a6d3e  call    DnsPrint_SecurityPacketInfo
0x1800a6d43  mov     rsi, [rdi]
0x1800a6d46  test    rsi, rsi
0x1800a6d49  jnz     short loc_1800A6D72
0x1800a6d4b  test    byte ptr cs:xmmword_1801119E0+1, 40h
0x1800a6d52  jz      short loc_1800A6D68
0x1800a6d54  lea     edx, [rsi+1Ch]
0x1800a6d57  mov     ecx, 40Eh
0x1800a6d5c  lea     r8, WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids
0x1800a6d63  call    WPP_SF_
0x1800a6d68  mov     eax, 0Eh
0x1800a6d6d  jmp     loc_1800A715E
0x1800a6d72  cmp     [rsi+94h], ebx
0x1800a6d78  jz      short loc_1800A6DCA
0x1800a6d7a  mov     rcx, [rdi+20h]; Buf1
0x1800a6d7e  test    rcx, rcx
0x1800a6d81  jz      short loc_1800A6D9F
0x1800a6d83  mov     eax, [rdi+18h]
0x1800a6d86  cmp     eax, [rdi+8]
0x1800a6d89  jnz     short loc_1800A6D9F
0x1800a6d8b  mov     rdx, [rdi+10h]; Buf2
0x1800a6d8f  mov     r8d, eax; Size
0x1800a6d92  call    memcmp_0
0x1800a6d97  test    eax, eax
0x1800a6d99  jz      loc_1800A715E
0x1800a6d9f  cmp     byte ptr cs:xmmword_1801119E0+3, bl
0x1800a6da5  jge     short loc_1800A6DC0
0x1800a6da7  mov     edx, 1Dh
0x1800a6dac  lea     r8, WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids
0x1800a6db3  mov     ecx, 41Fh
0x1800a6db8  mov     r9, rsi
0x1800a6dbb  call    WPP_SF_q
0x1800a6dc0  mov     eax, 2339h
0x1800a6dc5  jmp     loc_1800A715E
0x1800a6dca  cmp     [rsi+8Ch], ebx
0x1800a6dd0  jz      short loc_1800A6DDD
0x1800a6dd2  lea     rax, [rsi+70h]
0x1800a6dd6  mov     [rsp+300h+phCredential], rax
0x1800a6ddb  jmp     short loc_1800A6DF3
0x1800a6ddd  lea     rcx, [rsp+300h+phCredential]
0x1800a6de2  call    getDefaultCredentialsHandle
0x1800a6de7  mov     ebx, eax
0x1800a6de9  test    eax, eax
0x1800a6deb  jnz     loc_1800A7118
0x1800a6df1  xor     ebx, ebx
0x1800a6df3  mov     rax, [rdi+20h]
0x1800a6df7  test    rax, rax
0x1800a6dfa  jnz     short loc_1800A6E1F
0x1800a6dfc  mov     ecx, cs:g_SecurityTokenMaxLength
0x1800a6e02  call    Dns_Allocate
0x1800a6e07  test    rax, rax
0x1800a6e0a  jnz     short loc_1800A6E14
0x1800a6e0c  lea     ebx, [rax+0Eh]
0x1800a6e0f  jmp     loc_1800A7118
0x1800a6e14  mov     [rdi+20h], rax
0x1800a6e18  mov     dword ptr [rdi+1Ch], 2
0x1800a6e1f  mov     r8d, cs:g_SecurityTokenMaxLength; Size
0x1800a6e26  lea     r15, [rdi+18h]
0x1800a6e2a  mov     r14d, 1
0x1800a6e30  mov     [r15], r8d
0x1800a6e33  xor     edx, edx; Val
0x1800a6e35  mov     [rsp+300h+var_298.cBuffers], r14d
0x1800a6e3a  mov     rcx, rax; void *
0x1800a6e3d  mov     [rsp+300h+var_298.pBuffers], r15
0x1800a6e42  mov     [rsp+300h+var_298.ulVersion], ebx
0x1800a6e46  call    memset_0
0x1800a6e4b  cmp     [rdi+10h], rbx
0x1800a6e4f  jz      short loc_1800A6E62
0x1800a6e51  lea     rax, [rdi+8]
0x1800a6e55  mov     [rsp+300h+var_288.ulVersion], ebx
0x1800a6e59  mov     [rbp+200h+var_288.pBuffers], rax
0x1800a6e5d  mov     [rsp+300h+var_288.cBuffers], r14d
0x1800a6e62  mov     r8, r12
0x1800a6e65  lea     rcx, [rbp+200h+pszTargetName]; pszSpn
0x1800a6e69  call    MakeKerberosName
0x1800a6e6e  test    eax, eax
0x1800a6e70  jz      short loc_1800A6E7C
0x1800a6e72  mov     ebx, 0Dh
0x1800a6e77  jmp     loc_1800A7118
0x1800a6e7c  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800a6e83  jz      short loc_1800A6EB3
0x1800a6e85  call    cs:__imp_GetTickCount
0x1800a6e8c  nop     dword ptr [rax+rax+00h]
0x1800a6e91  mov     edx, 1Eh
0x1800a6e96  lea     r8, WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids
0x1800a6e9d  mov     r9d, eax
0x1800a6ea0  mov     ecx, 40Bh
0x1800a6ea5  lea     rax, [rbp+200h+pszTargetName]
0x1800a6ea9  mov     qword ptr [rsp+300h+Reserved1], rax
0x1800a6eae  call    WPP_SF_dS
0x1800a6eb3  mov     rdx, rdi
0x1800a6eb6  lea     rcx, aBeforeCallToIn; "Before call to InitClientSecurityContex"...
0x1800a6ebd  call    DnsPrint_SecurityPacketInfo
0x1800a6ec2  cmp     [rsi+90h], ebx
0x1800a6ec8  jz      short loc_1800A6ED3
0x1800a6eca  lea     rcx, [rsp+300h+var_288]
0x1800a6ecf  mov     eax, ebx
0x1800a6ed1  jmp     short loc_1800A6ED9
0x1800a6ed3  mov     eax, r14d
0x1800a6ed6  mov     rcx, rbx
0x1800a6ed9  test    eax, eax
0x1800a6edb  lea     r12, [rsi+8]
0x1800a6edf  lea     rax, [rbp+200h+var_270]
0x1800a6ee3  mov     rdx, rbx
0x1800a6ee6  mov     [rsp+300h+ptsExpiry], rax; ptsExpiry
0x1800a6eeb  lea     r8, [rbp+200h+pszTargetName]; pszTargetName
0x1800a6eef  lea     rax, [rbp+200h+var_278]
0x1800a6ef3  cmovz   rdx, r12; phContext
0x1800a6ef7  mov     [rsp+300h+pfContextAttr], rax; pfContextAttr
0x1800a6efc  mov     r9d, 10007h; fContextReq
0x1800a6f02  lea     rax, [rsp+300h+var_298]
0x1800a6f07  mov     [rsp+300h+pOutput], rax; pOutput
0x1800a6f0c  mov     [rsp+300h+phNewContext], r12; phNewContext
0x1800a6f11  mov     [rsp+300h+Reserved2], ebx; Reserved2
0x1800a6f15  mov     [rsp+300h+pInput], rcx; pInput
0x1800a6f1a  mov     rcx, [rsp+300h+phCredential]; phCredential
0x1800a6f1f  mov     [rsp+300h+TargetDataRep], 10h; TargetDataRep
0x1800a6f27  mov     [rsp+300h+Reserved1], ebx; Reserved1
0x1800a6f2b  call    cs:__imp_InitializeSecurityContextW
0x1800a6f32  nop     dword ptr [rax+rax+00h]
0x1800a6f37  mov     ebx, eax
0x1800a6f39  test    byte ptr cs:xmmword_1801119E0+1, 40h
0x1800a6f40  jz      short loc_1800A6F6E
0x1800a6f42  call    cs:__imp_GetTickCount
0x1800a6f49  nop     dword ptr [rax+rax+00h]
0x1800a6f4e  mov     r9d, eax
0x1800a6f51  mov     [rsp+300h+Reserved2], ebx
0x1800a6f55  mov     eax, [rbp+200h+var_278]
0x1800a6f58  mov     dword ptr [rsp+300h+pInput], ebx
0x1800a6f5c  mov     [rsp+300h+TargetDataRep], eax
0x1800a6f60  lea     rax, [rbp+200h+pszTargetName]
0x1800a6f64  mov     qword ptr [rsp+300h+Reserved1], rax
0x1800a6f69  call    WPP_SF_dSDdD
0x1800a6f6e  cmp     cs:g_fVelocityDisableInternalExports, 0
0x1800a6f75  mov     r8d, [rbp+200h+var_278]
0x1800a6f79  jz      short loc_1800A6FB3
0x1800a6f7b  test    ebx, ebx
0x1800a6f7d  jz      short loc_1800A6F8E
0x1800a6f7f  lea     eax, [rbx-90312h]
0x1800a6f85  test    eax, 0FFFFFFFDh
0x1800a6f8a  jnz     short loc_1800A6F9C
0x1800a6f8c  jmp     short loc_1800A6FCF
0x1800a6f8e  mov     ecx, 10002h
0x1800a6f93  mov     eax, r8d
0x1800a6f96  and     eax, ecx
0x1800a6f98  cmp     eax, ecx
0x1800a6f9a  jz      short loc_1800A6FCF
0x1800a6f9c  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800a6fa3  jz      loc_1800A7113
0x1800a6fa9  mov     edx, 20h ; ' '
0x1800a6fae  jmp     loc_1800A70F4
0x1800a6fb3  test    ebx, ebx
0x1800a6fb5  js      loc_1800A70E6
0x1800a6fbb  jnz     short loc_1800A6FCF
0x1800a6fbd  mov     ecx, 10002h
0x1800a6fc2  mov     eax, r8d
0x1800a6fc5  and     eax, ecx
0x1800a6fc7  cmp     eax, ecx
0x1800a6fc9  jnz     loc_1800A70E6
0x1800a6fcf  mov     [rsi+90h], r14d
0x1800a6fd6  test    byte ptr cs:xmmword_1801119E0+1, 40h
0x1800a6fdd  jz      short loc_1800A7012
0x1800a6fdf  mov     eax, [r15]
0x1800a6fe2  mov     r9d, ebx
0x1800a6fe5  mov     dword ptr [rsp+300h+pOutput], eax
0x1800a6fe9  mov     rax, [rdi+20h]
0x1800a6fed  mov     [rsp+300h+phNewContext], rax
0x1800a6ff2  mov     rax, [rsp+300h+var_298.pBuffers]
0x1800a6ff7  mov     qword ptr [rsp+300h+Reserved2], rax
0x1800a6ffc  mov     eax, [rsp+300h+var_298.cBuffers]
0x1800a7000  mov     dword ptr [rsp+300h+pInput], eax
0x1800a7004  mov     qword ptr [rsp+300h+TargetDataRep], r12
0x1800a7009  mov     [rsp+300h+Reserved1], ebx
0x1800a700d  call    WPP_SF_Ddqdqqd
0x1800a7012  test    ebx, ebx
0x1800a7014  jnz     loc_1800A70A2
0x1800a701a  xorps   xmm0, xmm0
0x1800a701d  lea     r8, [rbp+200h+pBuffer]; pBuffer
0x1800a7021  xor     edx, edx; ulAttribute
0x1800a7023  mov     rcx, r12; phContext
0x1800a7026  movups  [rbp+200h+pBuffer], xmm0
0x1800a702a  call    cs:__imp_QueryContextAttributesW
0x1800a7031  nop     dword ptr [rax+rax+00h]
0x1800a7036  cmp     cs:g_fVelocityDisableInternalExports, 0
0x1800a703d  mov     ebx, eax
0x1800a703f  jz      short loc_1800A704B
0x1800a7041  test    eax, eax
0x1800a7043  jnz     loc_1800A7118
0x1800a7049  jmp     short loc_1800A7053
0x1800a704b  test    ebx, ebx
0x1800a704d  js      loc_1800A7118
0x1800a7053  mov     r9d, cs:g_SignatureMaxLength
0x1800a705a  cmp     dword ptr [rbp+200h+pBuffer+4], r9d
0x1800a705e  jbe     short loc_1800A706B
0x1800a7060  mov     r9d, dword ptr [rbp+200h+pBuffer+4]
0x1800a7064  mov     cs:g_SignatureMaxLength, r9d
0x1800a706b  test    byte ptr cs:xmmword_1801119E0+1, 40h
0x1800a7072  jz      short loc_1800A708A
0x1800a7074  mov     edx, 23h ; '#'
0x1800a7079  lea     r8, WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids
0x1800a7080  mov     ecx, 40Eh
0x1800a7085  call    WPP_SF_d
0x1800a708a  test    ebx, ebx
0x1800a708c  jnz     short loc_1800A70A2
0x1800a708e  mov     [rsi+94h], r14d
0x1800a7095  mov     eax, 2649h
0x1800a709a  cmp     [r15], ebx
0x1800a709d  cmovnz  ebx, eax
0x1800a70a0  jmp     short loc_1800A70E0
0x1800a70a2  test    byte ptr cs:xmmword_1801119E0+1, 40h
0x1800a70a9  jz      short loc_1800A70CE
0x1800a70ab  xor     r9d, r9d
0x1800a70ae  lea     r8, WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids
0x1800a70b5  cmp     ebx, 90314h
0x1800a70bb  mov     edx, 24h ; '$'
0x1800a70c0  mov     ecx, 40Eh
0x1800a70c5  setz    r9b
0x1800a70c9  call    WPP_SF_d
0x1800a70ce  mov     ebx, 2649h
0x1800a70d3  mov     dword ptr [rsi+94h], 0
0x1800a70dd  xor     r14d, r14d
0x1800a70e0  mov     [r13+0], r14d
0x1800a70e4  jmp     short loc_1800A7118
0x1800a70e6  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800a70ed  jz      short loc_1800A7113
0x1800a70ef  mov     edx, 21h ; '!'
0x1800a70f4  mov     eax, dword ptr [rbp+200h+var_270]
0x1800a70f7  mov     r9d, ebx
0x1800a70fa  mov     dword ptr [rsp+300h+pfContextAttr], eax
0x1800a70fe  mov     eax, dword ptr [rbp+200h+var_270+4]
0x1800a7101  mov     dword ptr [rsp+300h+pOutput], eax
0x1800a7105  mov     [rsp+300h+TargetDataRep], r8d
0x1800a710a  mov     [rsp+300h+Reserved1], ebx
0x1800a710e  call    WPP_SF_dddddddd
0x1800a7113  mov     ebx, 2339h
0x1800a7118  test    byte ptr cs:xmmword_1801119E0+1, 40h
0x1800a711f  jz      short loc_1800A713E
0x1800a7121  mov     edx, 25h ; '%'
0x1800a7126  mov     [rsp+300h+Reserved1], ebx
0x1800a712a  mov     ecx, 40Eh
0x1800a712f  lea     r8, WPP_ec2a7cdd084b3685bb39ee61a3a9182c_Traceguids
0x1800a7136  mov     r9d, ebx
0x1800a7139  call    WPP_SF_Dd
0x1800a713e  mov     rdx, rsi
0x1800a7141  lea     rcx, aSecurityContex_1; "Security Context"
0x1800a7148  call    DnsPrint_SecurityContext
0x1800a714d  mov     rdx, rdi
0x1800a7150  lea     rcx, aSecuritySessio; "Security Session Packet Info"
0x1800a7157  call    DnsPrint_SecurityPacketInfo
0x1800a715c  mov     eax, ebx
0x1800a715e  mov     rcx, [rbp+200h+var_40]
0x1800a7165  xor     rcx, rsp; StackCookie
0x1800a7168  call    __security_check_cookie
0x1800a716d  mov     rbx, [rsp+300h+arg_18]
0x1800a7175  add     rsp, 2D0h
0x1800a717c  pop     r15
0x1800a717e  pop     r14
0x1800a7180  pop     r13
0x1800a7182  pop     r12
0x1800a7184  pop     rdi
0x1800a7185  pop     rsi
0x1800a7186  pop     rbp
0x1800a7187  retn
```
