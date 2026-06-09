# DhcpGetClassId

- ea: `0x180006e10`
- end: `0x180007008`
- name: `DhcpGetClassId`
- size: `504`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002620`
- `0x180002c50`
- `0x180006e10`
- `0x18000f4ec`
- `0x180010aac`
- `0x1800127f0`
- `0x180012850`
- `0x180012ad0`
- `0x180012d20`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180006f15`
- `RPCRT4!NdrClientCall3` at `0x180006f15`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180006ec1`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180006f34`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180006f67`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180006ec1`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180006f34`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180006f67`

## pseudocode

```c
__int64 __fastcall DhcpGetClassId(__int64 a1, __int64 a2)
{
  unsigned int Pointer; // ebx
  _DWORD *v5; // r14
  LPWSTR CommandLineW; // rax
  int v7; // ecx
  CLIENT_CALL_RETURN v8; // rax
  LPWSTR v9; // rax
  int v10; // ecx
  unsigned int v11; // eax
  bool v12; // cf
  void *Src[2]; // [rsp+48h] [rbp-40h] BYREF
  size_t Size; // [rsp+58h] [rbp-30h]
  __int64 v16; // [rsp+A0h] [rbp+18h] BYREF
  CLIENT_CALL_RETURN v17; // [rsp+A8h] [rbp+20h]

  v16 = 0;
  *(_OWORD *)Src = 0;
  Size = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_S(1028, 159, WPP_e15037783097355a5233924022d92169_Traceguids, a1);
  if ( a1 && a2 && (v5 = (_DWORD *)(a2 + 16), (*(_QWORD *)(a2 + 8) == 0) == (*(_DWORD *)(a2 + 16) == 0)) )
  {
    Pointer = DhcpAdapterNameToIfId(a1, &v16);
    if ( !Pointer )
    {
      if ( (xmmword_18001E1E0 & 0x10) != 0 )
      {
        CommandLineW = GetCommandLineW();
        WPP_SF_SS(v7, 160, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, (__int64)CommandLineW);
      }
      v17.Simple = 0;
      v8.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x14u, 0).Pointer;
      Pointer = (unsigned int)v8.Pointer;
      v17.Pointer = v8.Pointer;
      if ( (xmmword_18001E1E0 & 0x10) != 0 )
      {
        v9 = GetCommandLineW();
        WPP_SF_DSS(v10, 161, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, Pointer, a1, (__int64)v9);
      }
      if ( !Pointer )
      {
        *(_DWORD *)a2 = Src[0];
        if ( *v5 )
        {
          v11 = Size;
          v12 = *v5 < (unsigned int)Size;
          *v5 = Size;
          if ( v12 )
            Pointer = 234;
          else
            memcpy_0(*(void **)(a2 + 8), Src[1], v11);
        }
        else
        {
          *(_DWORD *)a2 = Src[0];
          *v5 = Size;
        }
      }
    }
  }
  else
  {
    Pointer = 87;
  }
  DhcpMidlUserFree(&Src[1]);
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_SD(1028, 162, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, Pointer);
  return Pointer;
}

```

## disassembly

```asm
0x180006e10  mov     r11, rsp
0x180006e13  mov     [r11+10h], rdx
0x180006e17  mov     [r11+8], rcx
0x180006e1b  push    rbx
0x180006e1c  push    rsi
0x180006e1d  push    rdi
0x180006e1e  push    r14
0x180006e20  push    r15
0x180006e22  sub     rsp, 60h
0x180006e26  mov     rsi, rdx
0x180006e29  mov     rdi, rcx
0x180006e2c  mov     qword ptr [r11+18h], 0
0x180006e34  xorps   xmm0, xmm0
0x180006e37  xor     eax, eax
0x180006e39  movups  xmmword ptr [rsp+88h+Src], xmm0
0x180006e3e  mov     [r11-30h], rax
0x180006e42  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180006e49  jz      short loc_180006E64
0x180006e4b  mov     edx, 9Fh
0x180006e50  mov     ecx, 404h
0x180006e55  mov     r9, rdi
0x180006e58  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180006e5f  call    WPP_SF_S
0x180006e64  test    rdi, rdi
0x180006e67  jnz     short loc_180006E73
0x180006e69  mov     ebx, 57h ; 'W'
0x180006e6e  jmp     loc_180006FCA
0x180006e73  test    rsi, rsi
0x180006e76  jz      short loc_180006E69
0x180006e78  lea     r15, [rsi+8]
0x180006e7c  mov     [rsp+88h+var_50], r15
0x180006e81  lea     r14, [rsi+10h]
0x180006e85  mov     [rsp+88h+var_48], r14
0x180006e8a  xor     ecx, ecx
0x180006e8c  cmp     [r15], rcx
0x180006e8f  setz    cl
0x180006e92  xor     eax, eax
0x180006e94  cmp     [r14], eax
0x180006e97  setz    al
0x180006e9a  cmp     ecx, eax
0x180006e9c  jnz     short loc_180006E69
0x180006e9e  lea     rdx, [rsp+88h+arg_10]
0x180006ea6  mov     rcx, rdi
0x180006ea9  call    DhcpAdapterNameToIfId
0x180006eae  mov     ebx, eax
0x180006eb0  test    eax, eax
0x180006eb2  jnz     loc_180006FCA
0x180006eb8  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180006ebf  jz      short loc_180006EE1
0x180006ec1  call    cs:__imp_GetCommandLineW
0x180006ec7  mov     edx, 0A0h
0x180006ecc  mov     [rsp+88h+var_68], rax
0x180006ed1  mov     r9, rdi
0x180006ed4  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180006edb  call    WPP_SF_SS
0x180006ee0  nop
0x180006ee1  mov     [rsp+88h+arg_18], 0
0x180006eed  lea     rax, [rsp+88h+Src]
0x180006ef2  mov     [rsp+88h+var_60], rax
0x180006ef7  lea     rax, [rsp+88h+arg_10]
0x180006eff  mov     [rsp+88h+var_68], rax
0x180006f04  xor     r9d, r9d
0x180006f07  xor     r8d, r8d; pReturnValue
0x180006f0a  lea     edx, [r9+14h]; nProcNum
0x180006f0e  lea     rcx, pProxyInfo; pProxyInfo
0x180006f15  call    cs:__imp_NdrClientCall3
0x180006f1b  mov     rbx, rax
0x180006f1e  mov     [rsp+88h+arg_18], rax
0x180006f26  mov     [rsp+88h+var_58], eax
0x180006f2a  jmp     short loc_180006F5E
0x180006f2c  mov     edi, eax
0x180006f2e  mov     ebx, eax
0x180006f30  mov     [rsp+88h+var_58], eax
0x180006f34  call    cs:__imp_GetCommandLineW
0x180006f3a  mov     rdx, rax
0x180006f3d  mov     ecx, ebx
0x180006f3f  call    TraceRpcException
0x180006f44  mov     rsi, [rsp+88h+arg_8]
0x180006f4c  mov     rdi, [rsp+88h+arg_0]
0x180006f54  mov     r15, [rsp+88h+var_50]
0x180006f59  mov     r14, [rsp+88h+var_48]
0x180006f5e  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180006f65  jz      short loc_180006F8B
0x180006f67  call    cs:__imp_GetCommandLineW
0x180006f6d  mov     edx, 0A1h
0x180006f72  mov     [rsp+88h+var_60], rax
0x180006f77  mov     [rsp+88h+var_68], rdi
0x180006f7c  mov     r9d, ebx
0x180006f7f  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180006f86  call    WPP_SF_DSS
0x180006f8b  test    ebx, ebx
0x180006f8d  jnz     short loc_180006FCA
0x180006f8f  mov     eax, dword ptr [rsp+88h+Src]
0x180006f93  mov     [rsi], eax
0x180006f95  cmp     [r14], ebx
0x180006f98  jnz     short loc_180006FA6
0x180006f9a  mov     [rsi], eax
0x180006f9c  mov     rax, [rsp+88h+Size]
0x180006fa1  mov     [r14], eax
0x180006fa4  jmp     short loc_180006FCA
0x180006fa6  mov     rax, [rsp+88h+Size]
0x180006fab  cmp     [r14], eax
0x180006fae  mov     [r14], eax
0x180006fb1  jnb     short loc_180006FBA
0x180006fb3  mov     ebx, 0EAh
0x180006fb8  jmp     short loc_180006FCA
0x180006fba  mov     r8d, eax; Size
0x180006fbd  mov     rdx, [rsp+88h+Src+8]; Src
0x180006fc2  mov     rcx, [r15]; void *
0x180006fc5  call    memcpy_0
0x180006fca  lea     rcx, [rsp+88h+Src+8]
0x180006fcf  call    DhcpMidlUserFree
0x180006fd4  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180006fdb  jz      short loc_180006FFA
0x180006fdd  mov     edx, 0A2h
0x180006fe2  mov     ecx, 404h
0x180006fe7  mov     dword ptr [rsp+88h+var_68], ebx
0x180006feb  mov     r9, rdi
0x180006fee  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180006ff5  call    WPP_SF_SD
0x180006ffa  mov     eax, ebx
0x180006ffc  add     rsp, 60h
0x180007000  pop     r15
0x180007002  pop     r14
0x180007004  pop     rdi
0x180007005  pop     rsi
0x180007006  pop     rbx
0x180007007  retn
0x180010c20  push    rbp
0x180010c22  sub     rsp, 30h
0x180010c26  mov     rbp, rdx
0x180010c29  mov     rcx, [rcx]
0x180010c2c  mov     ecx, [rcx]; ExceptionCode
0x180010c2e  call    cs:__imp_I_RpcExceptionFilter
0x180010c34  nop
0x180010c35  add     rsp, 30h
0x180010c39  pop     rbp
0x180010c3a  retn
```
