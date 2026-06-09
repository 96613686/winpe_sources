# DhcpStaticRefreshParamsInternal

- ea: `0x18000bd64`
- end: `0x18000be9e`
- name: `DhcpStaticRefreshParamsInternal`
- size: `314`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000bcc0`

## callees

- `0x180002620`
- `0x18000bd64`
- `0x18000f4ec`
- `0x180012850`
- `0x180012ad0`
- `0x180012d20`
- `0x180013070`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000be0d`
- `RPCRT4!NdrClientCall3` at `0x18000be0d`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000bdc6`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000be29`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000be47`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000bdc6`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000be29`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000be47`

## pseudocode

```c
__int64 __fastcall DhcpStaticRefreshParamsInternal(__int64 a1, __int64 a2, int a3)
{
  unsigned int Pointer; // ebx
  LPWSTR CommandLineW; // rax
  int v6; // ecx
  CLIENT_CALL_RETURN v7; // rax
  LPWSTR v8; // rax
  int v9; // ecx
  __int64 v11; // [rsp+60h] [rbp+18h] BYREF
  CLIENT_CALL_RETURN v12; // [rsp+68h] [rbp+20h]

  v11 = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_Sl(a1, 60, a3, a1, 1);
  if ( a1 )
  {
    Pointer = DhcpAdapterNameToIfId(a1, &v11);
    if ( Pointer )
      goto LABEL_9;
  }
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_SS(v6, 61, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, (__int64)CommandLineW);
  }
  v12.Simple = 0;
  v7.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0xAu, 0).Pointer;
  Pointer = (unsigned int)v7.Pointer;
  v12.Pointer = v7.Pointer;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    v8 = GetCommandLineW();
    WPP_SF_DSS(v9, 62, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, Pointer, a1, (__int64)v8);
LABEL_9:
    if ( (xmmword_18001E1E0 & 0x10) != 0 )
      WPP_SF_SD(1028, 63, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, Pointer);
  }
  return Pointer;
}

```

## disassembly

```asm
0x18000bd64  mov     rax, rsp
0x18000bd67  mov     [rax+10h], rbx
0x18000bd6b  mov     [rax+8], rcx
0x18000bd6f  push    rdi
0x18000bd70  sub     rsp, 40h
0x18000bd74  mov     rdi, rcx
0x18000bd77  mov     qword ptr [rax+18h], 0
0x18000bd7f  xor     ebx, ebx
0x18000bd81  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000bd88  jz      short loc_18000BD9C
0x18000bd8a  lea     edx, [rbx+3Ch]
0x18000bd8d  mov     dword ptr [rax-28h], 1
0x18000bd94  mov     r9, rcx
0x18000bd97  call    WPP_SF_Sl
0x18000bd9c  test    rdi, rdi
0x18000bd9f  jz      short loc_18000BDBD
0x18000bda1  lea     rdx, [rsp+48h+arg_10]
0x18000bda6  mov     rcx, rdi
0x18000bda9  call    DhcpAdapterNameToIfId
0x18000bdae  mov     ebx, eax
0x18000bdb0  test    eax, eax
0x18000bdb2  jnz     loc_18000BE6B
0x18000bdb8  lea     rbx, [rsp+48h+arg_10]
0x18000bdbd  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000bdc4  jz      short loc_18000BDE6
0x18000bdc6  call    cs:__imp_GetCommandLineW
0x18000bdcc  mov     edx, 3Dh ; '='
0x18000bdd1  mov     [rsp+48h+var_28], rax
0x18000bdd6  mov     r9, rdi
0x18000bdd9  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000bde0  call    WPP_SF_SS
0x18000bde5  nop
0x18000bde6  mov     [rsp+48h+arg_18], 0
0x18000bdef  mov     dword ptr [rsp+48h+var_20], 1
0x18000bdf7  mov     [rsp+48h+var_28], rbx
0x18000bdfc  xor     r9d, r9d
0x18000bdff  xor     r8d, r8d; pReturnValue
0x18000be02  lea     edx, [r9+0Ah]; nProcNum
0x18000be06  lea     rcx, pProxyInfo; pProxyInfo
0x18000be0d  call    cs:__imp_NdrClientCall3
0x18000be13  mov     rbx, rax
0x18000be16  mov     [rsp+48h+arg_18], rax
0x18000be1b  mov     [rsp+48h+var_18], eax
0x18000be1f  jmp     short loc_18000BE3E
0x18000be21  mov     edi, eax
0x18000be23  mov     ebx, eax
0x18000be25  mov     [rsp+48h+var_18], eax
0x18000be29  call    cs:__imp_GetCommandLineW
0x18000be2f  mov     rdx, rax
0x18000be32  mov     ecx, ebx
0x18000be34  call    TraceRpcException
0x18000be39  mov     rdi, [rsp+48h+arg_0]
0x18000be3e  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000be45  jz      short loc_18000BE91
0x18000be47  call    cs:__imp_GetCommandLineW
0x18000be4d  mov     edx, 3Eh ; '>'
0x18000be52  mov     [rsp+48h+var_20], rax
0x18000be57  mov     [rsp+48h+var_28], rdi
0x18000be5c  mov     r9d, ebx
0x18000be5f  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000be66  call    WPP_SF_DSS
0x18000be6b  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000be72  jz      short loc_18000BE91
0x18000be74  mov     edx, 3Fh ; '?'
0x18000be79  mov     ecx, 404h
0x18000be7e  mov     dword ptr [rsp+48h+var_28], ebx
0x18000be82  mov     r9, rdi
0x18000be85  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000be8c  call    WPP_SF_SD
0x18000be91  mov     eax, ebx
0x18000be93  mov     rbx, [rsp+48h+arg_8]
0x18000be98  add     rsp, 40h
0x18000be9c  pop     rdi
0x18000be9d  retn
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
