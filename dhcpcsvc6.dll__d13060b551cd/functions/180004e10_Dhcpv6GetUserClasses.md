# Dhcpv6GetUserClasses

- ea: `0x180004e10`
- end: `0x18000502c`
- name: `Dhcpv6GetUserClasses`
- size: `540`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, unsigned int *, __int64)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180001e30`
- `0x180001e70`
- `0x180001ff0`
- `0x180002650`
- `0x180004820`
- `0x180004e10`
- `0x1800072fc`
- `0x1800074a8`
- `0x1800081c0`
- `0x180008310`
- `0x1800083c0`
- `0x180008490`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180004edf`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180004f2f`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180004f60`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180004edf`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180004f2f`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180004f60`
- `WS2_32!__imp_ntohl` at `0x180004fa2`
- `WS2_32!__imp_ntohl` at `0x180004fbe`
- `WS2_32!__imp_ntohl` at `0x180004fa2`
- `WS2_32!__imp_ntohl` at `0x180004fbe`

## pseudocode

```c
__int64 __fastcall Dhcpv6GetUserClasses(__int64 a1, const WCHAR *a2, unsigned int *a3, __int64 a4)
{
  int v7; // ebx
  _WORD *v8; // rax
  unsigned int v9; // ebx
  int v10; // ecx
  LPWSTR CommandLineW; // rax
  int v12; // ecx
  LPWSTR v13; // rax
  int v14; // ecx
  int v15; // r8d
  __int64 v16; // r14
  u_long v17; // eax
  unsigned int v18; // ebx
  int v19; // ecx
  NET_LUID v21; // [rsp+38h] [rbp-60h] BYREF
  __int128 v22; // [rsp+40h] [rbp-58h] BYREF
  LPVOID v23[9]; // [rsp+50h] [rbp-48h] BYREF

  v7 = a1;
  v22 = 0;
  memset(v23, 0, 32);
  v21.Value = 0;
  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_S(a1, 67, WPP_cb48999f8e5838f952918348529d50de_Traceguids, a2);
  if ( !v7 && a2 && a3 && (a4 || !*a3) )
  {
    LODWORD(v23[0]) = 1;
    v8 = DhcpAlloc(2u);
    v23[1] = v8;
    if ( v8 )
    {
      *v8 = 15;
      v9 = Dhcpv6AdapterNameToIfId(a2, &v21);
      if ( !v9 )
      {
        if ( (xmmword_18000F160 & 0x10) != 0 )
        {
          CommandLineW = GetCommandLineW();
          WPP_SF_SS(
            v12,
            68,
            (unsigned int)WPP_cb48999f8e5838f952918348529d50de_Traceguids,
            (_DWORD)a2,
            (__int64)CommandLineW);
        }
        v9 = RpcCliRequestParams(v10, (unsigned int)&v21, 0, 1, (__int64)v23, (__int64)&v22);
        if ( (xmmword_18000F160 & 0x10) != 0 )
        {
          v13 = GetCommandLineW();
          WPP_SF_DSS(v14, 69, v15, v9, (__int64)a2, (__int64)v13);
        }
        if ( !v9 )
        {
          if ( (_DWORD)v22 )
          {
            if ( (unsigned int)v22 >= 0xC
              && (v16 = *((_QWORD *)&v22 + 1), v17 = ntohl(*(_DWORD *)(*((_QWORD *)&v22 + 1) + 8LL)), (v18 = v17) != 0)
              && (unsigned int)v22 >= (unsigned __int64)v17 + 12 )
            {
              *(_DWORD *)v16 = ntohl(*(_DWORD *)v16);
              v9 = ConvertFromBufferToClassInfo((unsigned __int8 *)(v16 + 12), v18, a4, a3);
            }
            else
            {
              v9 = 1359;
            }
          }
          else
          {
            *a3 = 0;
          }
        }
      }
    }
    else
    {
      v9 = 14;
    }
  }
  else
  {
    v9 = 87;
  }
  DhcpFree(&v23[1]);
  DhcpMidlUserFree((void **)&v22 + 1);
  LODWORD(v22) = 0;
  if ( (xmmword_18000F160 & 0x10) != 0 )
    WPP_SF_SD(v19, 70, (unsigned int)WPP_cb48999f8e5838f952918348529d50de_Traceguids, (_DWORD)a2, v9);
  return v9;
}

```

## disassembly

```asm
0x180004e10  mov     rax, rsp
0x180004e13  mov     [rax+20h], r9
0x180004e17  mov     [rax+18h], r8
0x180004e1b  mov     [rax+10h], rdx
0x180004e1f  push    rbx
0x180004e20  push    rsi
0x180004e21  push    rdi
0x180004e22  push    r14
0x180004e24  push    r15
0x180004e26  sub     rsp, 70h
0x180004e2a  mov     r15, r9
0x180004e2d  mov     rsi, r8
0x180004e30  mov     rdi, rdx
0x180004e33  mov     ebx, ecx
0x180004e35  xorps   xmm0, xmm0
0x180004e38  movups  xmmword ptr [rax-58h], xmm0
0x180004e3c  xorps   xmm1, xmm1
0x180004e3f  movups  xmmword ptr [rax-48h], xmm1
0x180004e43  movups  xmmword ptr [rax-38h], xmm1
0x180004e47  mov     qword ptr [rax-60h], 0
0x180004e4f  test    byte ptr cs:xmmword_18000F160, 10h
0x180004e56  jz      short loc_180004E6C
0x180004e58  mov     edx, 43h ; 'C'
0x180004e5d  mov     r9, rdi
0x180004e60  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180004e67  call    WPP_SF_S
0x180004e6c  test    ebx, ebx
0x180004e6e  jnz     loc_180004FDC
0x180004e74  test    rdi, rdi
0x180004e77  jz      loc_180004FDC
0x180004e7d  test    rsi, rsi
0x180004e80  jz      loc_180004FDC
0x180004e86  test    r15, r15
0x180004e89  jnz     short loc_180004E94
0x180004e8b  cmp     [rsi], r15d
0x180004e8e  jnz     loc_180004FDC
0x180004e94  mov     r14d, 1
0x180004e9a  mov     [rsp+98h+var_48], r14d
0x180004e9f  lea     ecx, [r14+1]
0x180004ea3  call    DhcpAlloc
0x180004ea8  mov     [rsp+98h+var_40], rax
0x180004ead  test    rax, rax
0x180004eb0  jnz     short loc_180004EBA
0x180004eb2  lea     ebx, [rax+0Eh]
0x180004eb5  jmp     loc_180004FE1
0x180004eba  mov     word ptr [rax], 0Fh
0x180004ebf  lea     rdx, [rsp+98h+var_60]
0x180004ec4  mov     rcx, rdi
0x180004ec7  call    Dhcpv6AdapterNameToIfId
0x180004ecc  mov     ebx, eax
0x180004ece  test    eax, eax
0x180004ed0  jnz     loc_180004FE1
0x180004ed6  test    byte ptr cs:xmmword_18000F160, 10h
0x180004edd  jz      short loc_180004EFD
0x180004edf  call    cs:__imp_GetCommandLineW
0x180004ee5  lea     edx, [rbx+44h]
0x180004ee8  mov     [rsp+98h+var_78], rax
0x180004eed  mov     r9, rdi
0x180004ef0  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180004ef7  call    WPP_SF_SS
0x180004efc  nop
0x180004efd  lea     rax, [rsp+98h+var_58]
0x180004f02  mov     [rsp+98h+var_70], rax
0x180004f07  lea     rax, [rsp+98h+var_48]
0x180004f0c  mov     [rsp+98h+var_78], rax
0x180004f11  mov     r9d, r14d
0x180004f14  xor     r8d, r8d
0x180004f17  lea     rdx, [rsp+98h+var_60]
0x180004f1c  call    RpcCliRequestParams
0x180004f21  mov     ebx, eax
0x180004f23  mov     [rsp+98h+var_68], eax
0x180004f27  jmp     short loc_180004F57
0x180004f29  mov     ebx, eax
0x180004f2b  mov     [rsp+98h+var_68], eax
0x180004f2f  call    cs:__imp_GetCommandLineW
0x180004f35  mov     rdx, rax
0x180004f38  mov     ecx, ebx
0x180004f3a  call    TraceRpcException
0x180004f3f  mov     r15, [rsp+98h+arg_18]
0x180004f47  mov     rsi, [rsp+98h+arg_10]
0x180004f4f  mov     rdi, [rsp+98h+arg_8]
0x180004f57  test    byte ptr cs:xmmword_18000F160, 10h
0x180004f5e  jz      short loc_180004F7D
0x180004f60  call    cs:__imp_GetCommandLineW
0x180004f66  mov     edx, 45h ; 'E'
0x180004f6b  mov     [rsp+98h+var_70], rax
0x180004f70  mov     [rsp+98h+var_78], rdi
0x180004f75  mov     r9d, ebx
0x180004f78  call    WPP_SF_DSS
0x180004f7d  test    ebx, ebx
0x180004f7f  jnz     short loc_180004FE1
0x180004f81  mov     eax, [rsp+98h+var_58]
0x180004f85  test    eax, eax
0x180004f87  jnz     short loc_180004F8D
0x180004f89  mov     [rsi], eax
0x180004f8b  jmp     short loc_180004FE1
0x180004f8d  cmp     eax, 0Ch
0x180004f90  jnb     short loc_180004F99
0x180004f92  mov     ebx, 54Fh
0x180004f97  jmp     short loc_180004FE1
0x180004f99  mov     r14, [rsp+98h+var_50]
0x180004f9e  mov     ecx, [r14+8]; netlong
0x180004fa2  call    cs:__imp_ntohl
0x180004fa8  mov     ebx, eax
0x180004faa  test    eax, eax
0x180004fac  jz      short loc_180004F92
0x180004fae  lea     rcx, [rbx+0Ch]
0x180004fb2  mov     eax, [rsp+98h+var_58]
0x180004fb6  cmp     rax, rcx
0x180004fb9  jb      short loc_180004F92
0x180004fbb  mov     ecx, [r14]; netlong
0x180004fbe  call    cs:__imp_ntohl
0x180004fc4  mov     [r14], eax
0x180004fc7  lea     rcx, [r14+0Ch]
0x180004fcb  mov     r9, rsi
0x180004fce  mov     r8, r15
0x180004fd1  mov     edx, ebx
0x180004fd3  call    ConvertFromBufferToClassInfo
0x180004fd8  mov     ebx, eax
0x180004fda  jmp     short loc_180004FE1
0x180004fdc  mov     ebx, 57h ; 'W'
0x180004fe1  lea     rcx, [rsp+98h+var_40]
0x180004fe6  call    DhcpFree
0x180004feb  lea     rcx, [rsp+98h+var_50]
0x180004ff0  call    DhcpMidlUserFree
0x180004ff5  mov     [rsp+98h+var_58], 0
0x180004ffd  test    byte ptr cs:xmmword_18000F160, 10h
0x180005004  jz      short loc_18000501E
0x180005006  mov     edx, 46h ; 'F'
0x18000500b  mov     dword ptr [rsp+98h+var_78], ebx
0x18000500f  mov     r9, rdi
0x180005012  lea     r8, WPP_cb48999f8e5838f952918348529d50de_Traceguids
0x180005019  call    WPP_SF_SD
0x18000501e  mov     eax, ebx
0x180005020  add     rsp, 70h
0x180005024  pop     r15
0x180005026  pop     r14
0x180005028  pop     rdi
0x180005029  pop     rsi
0x18000502a  pop     rbx
0x18000502b  retn
0x180007a0c  push    rbp
0x180007a0e  sub     rsp, 30h
0x180007a12  mov     rbp, rdx
0x180007a15  mov     rcx, [rcx]
0x180007a18  mov     ecx, [rcx]; ExceptionCode
0x180007a1a  call    cs:__imp_I_RpcExceptionFilter
0x180007a20  nop
0x180007a21  add     rsp, 30h
0x180007a25  pop     rbp
0x180007a26  retn
```
