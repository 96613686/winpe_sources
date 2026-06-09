# DhcpSetMSFTVendorSpecificOptions

- ea: `0x18000b9d0`
- end: `0x18000bcae`
- name: `DhcpSetMSFTVendorSpecificOptions`
- size: `734`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x180002160`
- `0x180002620`
- `0x180002760`
- `0x1800048c0`
- `0x180005a20`
- `0x18000b9d0`
- `0x18000f4ec`
- `0x180010a40`
- `0x1800127f0`
- `0x180012850`
- `0x180012a00`
- `0x180012ad0`
- `0x180012d20`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000bb96`
- `RPCRT4!NdrClientCall3` at `0x18000bb96`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000bb38`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000bbb2`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000bbe0`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000bb38`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000bbb2`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000bbe0`

## pseudocode

```c
__int64 __fastcall DhcpSetMSFTVendorSpecificOptions(int a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned int v9; // edi
  __int64 v10; // rcx
  __int128 *v11; // rax
  __int64 v12; // rcx
  char *v13; // rax
  unsigned int Pointer; // ebx
  unsigned __int16 i; // cx
  __int64 v16; // rax
  __int64 v17; // rdx
  LPWSTR CommandLineW; // rax
  int v19; // ecx
  CLIENT_CALL_RETURN v20; // rax
  LPWSTR v21; // rax
  int v22; // ecx
  __int128 v24; // [rsp+58h] [rbp-1080h] BYREF
  _QWORD v25[2]; // [rsp+68h] [rbp-1070h] BYREF
  CLIENT_CALL_RETURN v26; // [rsp+78h] [rbp-1060h]
  __int64 v27; // [rsp+80h] [rbp-1058h]
  __int64 v28; // [rsp+88h] [rbp-1050h]
  char v29; // [rsp+90h] [rbp-1048h] BYREF

  v27 = a2;
  v28 = a4;
  v25[1] = a5;
  v9 = 0;
  v25[0] = 0;
  v24 = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_S(1028, 185, WPP_e15037783097355a5233924022d92169_Traceguids, a2);
  v10 = 16;
  v11 = &v24;
  do
  {
    *(_BYTE *)v11 = 0;
    v11 = (__int128 *)((char *)v11 + 1);
    --v10;
  }
  while ( v10 );
  v12 = 4096;
  v13 = &v29;
  do
  {
    *v13++ = 0;
    --v12;
  }
  while ( v12 );
  if ( (unsigned int)DhcpIsFSEGuestSystem() )
  {
    Pointer = 50;
    if ( (xmmword_18001E1E0 & 2) != 0 )
      WPP_SF_d(1025, 186, WPP_e15037783097355a5233924022d92169_Traceguids, 50);
  }
  else if ( a2
         && (unsigned int)(a1 - 1) <= 2
         && (!a3 || !*(_DWORD *)a3 && *(_QWORD *)(a3 + 8) && *(_DWORD *)(a3 + 16))
         && (*(_DWORD *)a4 && *(_QWORD *)(a4 + 8) || a1 == 2) )
  {
    Pointer = DhcpAdapterNameToIfId(a2, v25);
    if ( !Pointer )
    {
      if ( a1 == 1 )
      {
        for ( i = 0; (unsigned int)i < *(_DWORD *)a4; ++i )
        {
          v16 = 32LL * i;
          v17 = *(_QWORD *)(a4 + 8);
          if ( !*(_DWORD *)(v16 + v17 + 24) || !*(_QWORD *)(v16 + v17 + 16) )
            goto LABEL_9;
        }
      }
      Pointer = ConvertToInternalParamsArray(a4, &v24);
      if ( !Pointer )
      {
        if ( (xmmword_18001E1E0 & 0x10) != 0 )
        {
          CommandLineW = GetCommandLineW();
          WPP_SF_SS(v19, 187, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a2, (__int64)CommandLineW);
        }
        v26.Simple = 0;
        v20.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x19u, 0).Pointer;
        Pointer = (unsigned int)v20.Pointer;
        v26.Pointer = v20.Pointer;
        if ( (xmmword_18001E1E0 & 0x10) != 0 )
        {
          v21 = GetCommandLineW();
          WPP_SF_DSS(v22, 188, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, Pointer, a2, (__int64)v21);
        }
      }
    }
  }
  else
  {
LABEL_9:
    Pointer = 87;
  }
  if ( *((_QWORD *)&v24 + 1) )
  {
    if ( *(_DWORD *)a4 )
    {
      do
        DhcpFree(*((_QWORD *)&v24 + 1) + 8 * (3LL * v9++ + 2));
      while ( v9 < *(_DWORD *)a4 );
    }
    DhcpFree((char *)&v24 + 8);
  }
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_SD(1028, 189, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a2, Pointer);
  return Pointer;
}

```

## disassembly

```asm
0x18000b9d0  push    rbx
0x18000b9d2  push    rsi
0x18000b9d3  push    rdi
0x18000b9d4  push    r12
0x18000b9d6  push    r13
0x18000b9d8  push    r14
0x18000b9da  push    r15
0x18000b9dc  mov     eax, 10A0h
0x18000b9e1  call    _alloca_probe
0x18000b9e6  sub     rsp, rax
0x18000b9e9  mov     rax, cs:__security_cookie
0x18000b9f0  xor     rax, rsp
0x18000b9f3  mov     [rsp+10D8h+var_48], rax
0x18000b9fb  mov     r14, r9
0x18000b9fe  mov     r12, r8
0x18000ba01  mov     r15, rdx
0x18000ba04  mov     r13d, ecx
0x18000ba07  mov     [rsp+10D8h+var_1058], rdx
0x18000ba0f  mov     [rsp+10D8h+var_1050], r9
0x18000ba17  mov     rax, [rsp+10D8h+arg_20]
0x18000ba1f  mov     [rsp+10D8h+var_1068], rax
0x18000ba24  xor     edi, edi
0x18000ba26  mov     [rsp+10D8h+var_1070], rdi
0x18000ba2b  xorps   xmm0, xmm0
0x18000ba2e  movups  [rsp+10D8h+var_1080], xmm0
0x18000ba33  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000ba3a  jz      short loc_18000BA55
0x18000ba3c  mov     edx, 0B9h
0x18000ba41  mov     ecx, 404h
0x18000ba46  mov     r9, r15
0x18000ba49  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000ba50  call    WPP_SF_S
0x18000ba55  mov     ecx, 10h
0x18000ba5a  lea     rax, [rsp+10D8h+var_1080]
0x18000ba5f  lea     esi, [rcx-0Fh]
0x18000ba62  mov     [rax], dil
0x18000ba65  add     rax, rsi
0x18000ba68  sub     rcx, rsi
0x18000ba6b  jnz     short loc_18000BA62
0x18000ba6d  mov     ecx, 1000h
0x18000ba72  lea     rax, [rsp+10D8h+var_1048]
0x18000ba7a  mov     [rax], dil
0x18000ba7d  add     rax, rsi
0x18000ba80  sub     rcx, rsi
0x18000ba83  jnz     short loc_18000BA7A
0x18000ba85  call    DhcpIsFSEGuestSystem
0x18000ba8a  test    eax, eax
0x18000ba8c  jnz     loc_18000BC06
0x18000ba92  test    r15, r15
0x18000ba95  jnz     short loc_18000BAA1
0x18000ba97  mov     ebx, 57h ; 'W'
0x18000ba9c  jmp     loc_18000BC2E
0x18000baa1  lea     eax, [r13-1]
0x18000baa5  cmp     eax, 2
0x18000baa8  ja      short loc_18000BA97
0x18000baaa  test    r12, r12
0x18000baad  jz      short loc_18000BAC3
0x18000baaf  cmp     [r12], edi
0x18000bab3  jnz     short loc_18000BA97
0x18000bab5  cmp     [r12+8], rdi
0x18000baba  jz      short loc_18000BA97
0x18000babc  cmp     [r12+10h], edi
0x18000bac1  jbe     short loc_18000BA97
0x18000bac3  cmp     [r14], edi
0x18000bac6  jbe     short loc_18000BACE
0x18000bac8  cmp     [r14+8], rdi
0x18000bacc  jnz     short loc_18000BAD4
0x18000bace  cmp     r13d, 2
0x18000bad2  jnz     short loc_18000BA97
0x18000bad4  lea     rdx, [rsp+10D8h+var_1070]
0x18000bad9  mov     rcx, r15
0x18000badc  call    DhcpAdapterNameToIfId
0x18000bae1  mov     ebx, eax
0x18000bae3  test    eax, eax
0x18000bae5  jnz     loc_18000BC2E
0x18000baeb  cmp     r13d, esi
0x18000baee  jnz     short loc_18000BB18
0x18000baf0  movzx   ecx, di
0x18000baf3  movzx   eax, cx
0x18000baf6  cmp     eax, [r14]
0x18000baf9  jnb     short loc_18000BB18
0x18000bafb  movzx   eax, cx
0x18000bafe  shl     rax, 5
0x18000bb02  mov     rdx, [r14+8]
0x18000bb06  cmp     [rax+rdx+18h], edi
0x18000bb0a  jbe     short loc_18000BA97
0x18000bb0c  cmp     [rax+rdx+10h], rdi
0x18000bb11  jz      short loc_18000BA97
0x18000bb13  add     cx, si
0x18000bb16  jmp     short loc_18000BAF3
0x18000bb18  lea     rdx, [rsp+10D8h+var_1080]
0x18000bb1d  mov     rcx, r14
0x18000bb20  call    ConvertToInternalParamsArray
0x18000bb25  mov     ebx, eax
0x18000bb27  test    eax, eax
0x18000bb29  jnz     loc_18000BC2E
0x18000bb2f  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000bb36  jz      short loc_18000BB58
0x18000bb38  call    cs:__imp_GetCommandLineW
0x18000bb3e  mov     edx, 0BBh
0x18000bb43  mov     [rsp+10D8h+var_10B8], rax
0x18000bb48  mov     r9, r15
0x18000bb4b  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000bb52  call    WPP_SF_SS
0x18000bb57  nop
0x18000bb58  mov     [rsp+10D8h+var_1060], rdi
0x18000bb5d  mov     rax, [rsp+10D8h+var_1068]
0x18000bb62  mov     [rsp+10D8h+var_1098], rax
0x18000bb67  lea     rax, [rsp+10D8h+var_1080]
0x18000bb6c  mov     [rsp+10D8h+var_10A0], rax
0x18000bb71  mov     [rsp+10D8h+var_10A8], r12
0x18000bb76  lea     rax, [rsp+10D8h+var_1070]
0x18000bb7b  mov     [rsp+10D8h+var_10B0], rax
0x18000bb80  mov     dword ptr [rsp+10D8h+var_10B8], r13d
0x18000bb85  xor     r9d, r9d
0x18000bb88  xor     r8d, r8d; pReturnValue
0x18000bb8b  lea     edx, [r9+19h]; nProcNum
0x18000bb8f  lea     rcx, pProxyInfo; pProxyInfo
0x18000bb96  call    cs:__imp_NdrClientCall3
0x18000bb9c  mov     rbx, rax
0x18000bb9f  mov     [rsp+10D8h+var_1060], rax
0x18000bba4  mov     [rsp+10D8h+var_1088], eax
0x18000bba8  jmp     short loc_18000BBD7
0x18000bbaa  mov     edi, eax
0x18000bbac  mov     ebx, eax
0x18000bbae  mov     [rsp+10D8h+var_1088], eax
0x18000bbb2  call    cs:__imp_GetCommandLineW
0x18000bbb8  mov     rdx, rax
0x18000bbbb  mov     ecx, ebx
0x18000bbbd  call    TraceRpcException
0x18000bbc2  xor     edi, edi
0x18000bbc4  lea     esi, [rdi+1]
0x18000bbc7  mov     r15, [rsp+10D8h+var_1058]
0x18000bbcf  mov     r14, [rsp+10D8h+var_1050]
0x18000bbd7  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000bbde  jz      short loc_18000BC2E
0x18000bbe0  call    cs:__imp_GetCommandLineW
0x18000bbe6  mov     edx, 0BCh
0x18000bbeb  mov     [rsp+10D8h+var_10B0], rax
0x18000bbf0  mov     [rsp+10D8h+var_10B8], r15
0x18000bbf5  mov     r9d, ebx
0x18000bbf8  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000bbff  call    WPP_SF_DSS
0x18000bc04  jmp     short loc_18000BC2E
0x18000bc06  mov     r9d, 32h ; '2'
0x18000bc0c  mov     ebx, r9d
0x18000bc0f  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000bc16  jz      short loc_18000BC2E
0x18000bc18  mov     edx, 0BAh
0x18000bc1d  mov     ecx, 401h
0x18000bc22  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000bc29  call    WPP_SF_d
0x18000bc2e  cmp     qword ptr [rsp+10D8h+var_1080+8], rdi
0x18000bc33  jz      short loc_18000BC63
0x18000bc35  cmp     [r14], edi
0x18000bc38  jbe     short loc_18000BC59
0x18000bc3a  mov     eax, edi
0x18000bc3c  lea     rcx, [rax+rax*2]
0x18000bc40  mov     rax, qword ptr [rsp+10D8h+var_1080+8]
0x18000bc45  lea     rcx, [rcx+2]
0x18000bc49  lea     rcx, [rax+rcx*8]
0x18000bc4d  call    DhcpFree
0x18000bc52  add     edi, esi
0x18000bc54  cmp     edi, [r14]
0x18000bc57  jb      short loc_18000BC3A
0x18000bc59  lea     rcx, [rsp+10D8h+var_1080+8]
0x18000bc5e  call    DhcpFree
0x18000bc63  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000bc6a  jz      short loc_18000BC89
0x18000bc6c  mov     edx, 0BDh
0x18000bc71  mov     ecx, 404h
0x18000bc76  mov     dword ptr [rsp+10D8h+var_10B8], ebx
0x18000bc7a  mov     r9, r15
0x18000bc7d  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000bc84  call    WPP_SF_SD
0x18000bc89  mov     eax, ebx
0x18000bc8b  mov     rcx, [rsp+10D8h+var_48]
0x18000bc93  xor     rcx, rsp; StackCookie
0x18000bc96  call    __security_check_cookie
0x18000bc9b  add     rsp, 10A0h
0x18000bca2  pop     r15
0x18000bca4  pop     r14
0x18000bca6  pop     r13
0x18000bca8  pop     r12
0x18000bcaa  pop     rdi
0x18000bcab  pop     rsi
0x18000bcac  pop     rbx
0x18000bcad  retn
0x180010cec  push    rbp
0x180010cee  sub     rsp, 50h
0x180010cf2  mov     rbp, rdx
0x180010cf5  mov     rcx, [rcx]
0x180010cf8  mov     ecx, [rcx]; ExceptionCode
0x180010cfa  call    cs:__imp_I_RpcExceptionFilter
0x180010d00  nop
0x180010d01  add     rsp, 50h
0x180010d05  pop     rbp
0x180010d06  retn
```
