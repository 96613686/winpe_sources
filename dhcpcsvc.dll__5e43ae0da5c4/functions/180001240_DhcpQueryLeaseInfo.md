# DhcpQueryLeaseInfo

- ea: `0x180001240`
- end: `0x180001483`
- name: `DhcpQueryLeaseInfo`
- size: `579`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180001240`
- `0x180002620`
- `0x1800027b0`
- `0x1800048c0`
- `0x180005162`
- `0x18000f4ec`
- `0x1800127f0`
- `0x180012850`
- `0x180012ad0`
- `0x180012d20`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180001356`
- `RPCRT4!NdrClientCall3` at `0x180001356`
- `RPCRT4!I_RpcExceptionFilter` at `0x180010b6e`
- `RPCRT4!I_RpcExceptionFilter` at `0x180010b6e`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180001301`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180001372`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180001395`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180001301`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180001372`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180001395`

## pseudocode

```c
__int64 __fastcall DhcpQueryLeaseInfo(__int64 a1, _OWORD *a2)
{
  unsigned int Pointer; // ebx
  LPWSTR CommandLineW; // rax
  int v6; // ecx
  CLIENT_CALL_RETURN v7; // rax
  LPWSTR v8; // rax
  int v9; // ecx
  _DWORD v11[2]; // [rsp+40h] [rbp-D8h] BYREF
  __int64 v12; // [rsp+48h] [rbp-D0h] BYREF
  CLIENT_CALL_RETURN v13; // [rsp+50h] [rbp-C8h]
  __int64 v14; // [rsp+58h] [rbp-C0h]
  _OWORD *v15; // [rsp+60h] [rbp-B8h]
  _OWORD v16[7]; // [rsp+70h] [rbp-A8h] BYREF
  __int64 v17; // [rsp+E0h] [rbp-38h]

  v14 = a1;
  v15 = a2;
  v12 = 0;
  v11[0] = 0;
  memset_0(v16, 0, 0x78u);
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_S(1028, 143, WPP_e15037783097355a5233924022d92169_Traceguids, a1);
  if ( a2 )
  {
    memset_0(a2, 0, 0x78u);
    if ( a1 )
    {
      Pointer = DhcpAdapterNameToIfId(a1, &v12);
      if ( !Pointer )
      {
        if ( (xmmword_18001E1E0 & 0x10) != 0 )
        {
          CommandLineW = GetCommandLineW();
          WPP_SF_SS(v6, 144, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, (__int64)CommandLineW);
        }
        v13.Simple = 0;
        v7.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x11u, 0, 0, &v12, v16, v11).Pointer;
        Pointer = (unsigned int)v7.Pointer;
        v13.Pointer = v7.Pointer;
        v11[1] = v7.Pointer;
        if ( (xmmword_18001E1E0 & 0x10) != 0 )
        {
          v8 = GetCommandLineW();
          WPP_SF_DSS(v9, 145, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, Pointer, a1, (__int64)v8);
        }
        if ( !Pointer )
        {
          *a2 = v16[0];
          a2[1] = v16[1];
          a2[2] = v16[2];
          a2[3] = v16[3];
          a2[4] = v16[4];
          a2[5] = v16[5];
          a2[6] = v16[6];
          *((_QWORD *)a2 + 14) = v17;
          memset_0(v16, 0, 0x78u);
        }
      }
    }
    else
    {
      Pointer = 87;
    }
  }
  else
  {
    Pointer = 87;
  }
  DhcpFreeLeaseInfo(v16);
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_SD(1028, 146, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, Pointer);
  return Pointer;
}

```

## disassembly

```asm
0x180001240  mov     [rsp+arg_10], rbx
0x180001245  push    rsi
0x180001246  push    rdi
0x180001247  push    r14
0x180001249  sub     rsp, 100h
0x180001250  mov     rax, cs:__security_cookie
0x180001257  xor     rax, rsp
0x18000125a  mov     [rsp+118h+var_28], rax
0x180001262  mov     rdi, rdx
0x180001265  mov     rsi, rcx
0x180001268  mov     [rsp+118h+var_C0], rcx
0x18000126d  mov     [rsp+118h+var_B8], rdx
0x180001272  xor     r14d, r14d
0x180001275  mov     [rsp+118h+var_D0], r14
0x18000127a  mov     [rsp+118h+var_D8], r14d
0x18000127f  xor     edx, edx; Val
0x180001281  mov     r8d, 78h ; 'x'; Size
0x180001287  lea     rcx, [rsp+118h+var_A8]; void *
0x18000128c  call    memset_0
0x180001291  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180001298  jz      short loc_1800012B3
0x18000129a  mov     edx, 8Fh
0x18000129f  mov     ecx, 404h
0x1800012a4  mov     r9, rsi
0x1800012a7  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x1800012ae  call    WPP_SF_S
0x1800012b3  test    rdi, rdi
0x1800012b6  jnz     short loc_1800012C2
0x1800012b8  mov     ebx, 57h ; 'W'
0x1800012bd  jmp     loc_18000142D
0x1800012c2  xor     edx, edx; Val
0x1800012c4  mov     r8d, 78h ; 'x'; Size
0x1800012ca  mov     rcx, rdi; void *
0x1800012cd  call    memset_0
0x1800012d2  test    rsi, rsi
0x1800012d5  jnz     short loc_1800012E1
0x1800012d7  mov     ebx, 57h ; 'W'
0x1800012dc  jmp     loc_18000142D
0x1800012e1  lea     rdx, [rsp+118h+var_D0]
0x1800012e6  mov     rcx, rsi
0x1800012e9  call    DhcpAdapterNameToIfId
0x1800012ee  mov     ebx, eax
0x1800012f0  test    eax, eax
0x1800012f2  jnz     loc_18000142D
0x1800012f8  test    byte ptr cs:xmmword_18001E1E0, 10h
0x1800012ff  jz      short loc_180001321
0x180001301  call    cs:__imp_GetCommandLineW
0x180001307  mov     edx, 90h
0x18000130c  mov     [rsp+118h+var_F8], rax
0x180001311  mov     r9, rsi
0x180001314  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000131b  call    WPP_SF_SS
0x180001320  nop
0x180001321  mov     [rsp+118h+var_C8], r14
0x180001326  lea     rax, [rsp+118h+var_D8]
0x18000132b  mov     [rsp+118h+var_E8], rax
0x180001330  lea     rax, [rsp+118h+var_A8]
0x180001335  mov     [rsp+118h+var_F0], rax
0x18000133a  lea     rax, [rsp+118h+var_D0]
0x18000133f  mov     [rsp+118h+var_F8], rax
0x180001344  xor     r9d, r9d
0x180001347  xor     r8d, r8d; pReturnValue
0x18000134a  mov     edx, 11h; nProcNum
0x18000134f  lea     rcx, pProxyInfo; pProxyInfo
0x180001356  call    cs:__imp_NdrClientCall3
0x18000135c  mov     rbx, rax
0x18000135f  mov     [rsp+118h+var_C8], rax
0x180001364  mov     [rsp+118h+var_D4], eax
0x180001368  jmp     short loc_18000138C
0x18000136a  mov     edi, eax
0x18000136c  mov     ebx, eax
0x18000136e  mov     [rsp+118h+var_D4], eax
0x180001372  call    cs:__imp_GetCommandLineW
0x180001378  mov     rdx, rax
0x18000137b  mov     ecx, ebx
0x18000137d  call    TraceRpcException
0x180001382  mov     rsi, [rsp+118h+var_C0]
0x180001387  mov     rdi, [rsp+118h+var_B8]
0x18000138c  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180001393  jz      short loc_1800013B9
0x180001395  call    cs:__imp_GetCommandLineW
0x18000139b  mov     edx, 91h
0x1800013a0  mov     [rsp+118h+var_F0], rax
0x1800013a5  mov     [rsp+118h+var_F8], rsi
0x1800013aa  mov     r9d, ebx
0x1800013ad  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x1800013b4  call    WPP_SF_DSS
0x1800013b9  test    ebx, ebx
0x1800013bb  jnz     short loc_18000142D
0x1800013bd  movaps  xmm0, [rsp+118h+var_A8]
0x1800013c2  movups  xmmword ptr [rdi], xmm0
0x1800013c5  movaps  xmm1, [rsp+118h+var_98]
0x1800013cd  movups  xmmword ptr [rdi+10h], xmm1
0x1800013d1  movaps  xmm0, [rsp+118h+var_88]
0x1800013d9  movups  xmmword ptr [rdi+20h], xmm0
0x1800013dd  movaps  xmm1, [rsp+118h+var_78]
0x1800013e5  movups  xmmword ptr [rdi+30h], xmm1
0x1800013e9  movaps  xmm0, [rsp+118h+var_68]
0x1800013f1  movups  xmmword ptr [rdi+40h], xmm0
0x1800013f5  movaps  xmm1, [rsp+118h+var_58]
0x1800013fd  movups  xmmword ptr [rdi+50h], xmm1
0x180001401  movaps  xmm0, [rsp+118h+var_48]
0x180001409  movups  xmmword ptr [rdi+60h], xmm0
0x18000140d  movsd   xmm1, [rsp+118h+var_38]
0x180001416  movsd   qword ptr [rdi+70h], xmm1
0x18000141b  xor     edx, edx; Val
0x18000141d  mov     r8d, 78h ; 'x'; Size
0x180001423  lea     rcx, [rsp+118h+var_A8]; void *
0x180001428  call    memset_0
0x18000142d  lea     rcx, [rsp+118h+var_A8]; void *
0x180001432  call    DhcpFreeLeaseInfo
0x180001437  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000143e  jz      short loc_18000145D
0x180001440  mov     edx, 92h
0x180001445  mov     ecx, 404h
0x18000144a  mov     dword ptr [rsp+118h+var_F8], ebx
0x18000144e  mov     r9, rsi
0x180001451  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180001458  call    WPP_SF_SD
0x18000145d  mov     eax, ebx
0x18000145f  mov     rcx, [rsp+118h+var_28]
0x180001467  xor     rcx, rsp; StackCookie
0x18000146a  call    __security_check_cookie
0x18000146f  mov     rbx, [rsp+118h+arg_10]
0x180001477  add     rsp, 100h
0x18000147e  pop     r14
0x180001480  pop     rdi
0x180001481  pop     rsi
0x180001482  retn
0x180010b60  push    rbp
0x180010b62  sub     rsp, 40h
0x180010b66  mov     rbp, rdx
0x180010b69  mov     rcx, [rcx]
0x180010b6c  mov     ecx, [rcx]; ExceptionCode
0x180010b6e  call    cs:__imp_I_RpcExceptionFilter
0x180010b74  nop
0x180010b75  add     rsp, 40h
0x180010b79  pop     rbp
0x180010b7a  retn
```
