# DhcpGetClientId

- ea: `0x180007010`
- end: `0x1800071f9`
- name: `DhcpGetClientId`
- size: `489`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180002620`
- `0x180002c50`
- `0x180007010`
- `0x18000f4ec`
- `0x180010aac`
- `0x1800127f0`
- `0x180012850`
- `0x180012ad0`
- `0x180012d20`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000710d`
- `RPCRT4!NdrClientCall3` at `0x18000710d`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800070b9`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000712c`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000715f`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800070b9`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000712c`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000715f`

## pseudocode

```c
__int64 __fastcall DhcpGetClientId(__int64 a1, __int64 a2)
{
  unsigned int Pointer; // ebx
  _DWORD *v5; // rsi
  LPWSTR CommandLineW; // rax
  int v7; // ecx
  CLIENT_CALL_RETURN v8; // rax
  LPWSTR v9; // rax
  int v10; // ecx
  bool v11; // cf
  __int128 v13; // [rsp+48h] [rbp-40h] BYREF
  __int64 v14; // [rsp+A0h] [rbp+18h] BYREF
  CLIENT_CALL_RETURN v15; // [rsp+A8h] [rbp+20h]

  v14 = 0;
  v13 = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_S(1028, 170, WPP_e15037783097355a5233924022d92169_Traceguids, a1);
  if ( a1 && a2 && (v5 = (_DWORD *)(a2 + 4), (*(_QWORD *)(a2 + 8) == 0) == (*(_DWORD *)(a2 + 4) == 0)) )
  {
    Pointer = DhcpAdapterNameToIfId(a1, &v14);
    if ( !Pointer )
    {
      if ( (xmmword_18001E1E0 & 0x10) != 0 )
      {
        CommandLineW = GetCommandLineW();
        WPP_SF_SS(v7, 171, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, (__int64)CommandLineW);
      }
      v15.Simple = 0;
      v8.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x16u, 0).Pointer;
      Pointer = (unsigned int)v8.Pointer;
      v15.Pointer = v8.Pointer;
      if ( (xmmword_18001E1E0 & 0x10) != 0 )
      {
        v9 = GetCommandLineW();
        WPP_SF_DSS(v10, 172, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, Pointer, a1, (__int64)v9);
      }
      if ( !Pointer )
      {
        if ( *v5 )
        {
          v11 = *v5 < DWORD1(v13);
          *v5 = DWORD1(v13);
          if ( v11 )
          {
            Pointer = 234;
          }
          else
          {
            *(_BYTE *)a2 = v13;
            memcpy_0(*(void **)(a2 + 8), *((const void **)&v13 + 1), DWORD1(v13));
          }
        }
        else
        {
          *v5 = DWORD1(v13);
        }
      }
    }
  }
  else
  {
    Pointer = 87;
  }
  DhcpMidlUserFree((char *)&v13 + 8);
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_SD(1028, 173, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, Pointer);
  return Pointer;
}

```

## disassembly

```asm
0x180007010  mov     rax, rsp
0x180007013  mov     [rax+10h], rdx
0x180007017  mov     [rax+8], rcx
0x18000701b  push    rbx
0x18000701c  push    rsi
0x18000701d  push    rdi
0x18000701e  push    r14
0x180007020  push    r15
0x180007022  sub     rsp, 60h
0x180007026  mov     r14, rdx
0x180007029  mov     rdi, rcx
0x18000702c  mov     qword ptr [rax+18h], 0
0x180007034  xorps   xmm0, xmm0
0x180007037  movups  xmmword ptr [rax-40h], xmm0
0x18000703b  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180007042  jz      short loc_18000705D
0x180007044  mov     edx, 0AAh
0x180007049  mov     ecx, 404h
0x18000704e  mov     r9, rdi
0x180007051  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180007058  call    WPP_SF_S
0x18000705d  test    rdi, rdi
0x180007060  jnz     short loc_18000706C
0x180007062  mov     ebx, 57h ; 'W'
0x180007067  jmp     loc_1800071BB
0x18000706c  test    r14, r14
0x18000706f  jz      short loc_180007062
0x180007071  lea     r15, [r14+8]
0x180007075  mov     [rsp+88h+var_50], r15
0x18000707a  lea     rsi, [r14+4]
0x18000707e  mov     [rsp+88h+var_48], rsi
0x180007083  xor     ecx, ecx
0x180007085  cmp     [r15], rcx
0x180007088  setz    cl
0x18000708b  xor     eax, eax
0x18000708d  cmp     [rsi], eax
0x18000708f  setz    al
0x180007092  cmp     ecx, eax
0x180007094  jnz     short loc_180007062
0x180007096  lea     rdx, [rsp+88h+arg_10]
0x18000709e  mov     rcx, rdi
0x1800070a1  call    DhcpAdapterNameToIfId
0x1800070a6  mov     ebx, eax
0x1800070a8  test    eax, eax
0x1800070aa  jnz     loc_1800071BB
0x1800070b0  test    byte ptr cs:xmmword_18001E1E0, 10h
0x1800070b7  jz      short loc_1800070D9
0x1800070b9  call    cs:__imp_GetCommandLineW
0x1800070bf  mov     edx, 0ABh
0x1800070c4  mov     [rsp+88h+var_68], rax
0x1800070c9  mov     r9, rdi
0x1800070cc  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x1800070d3  call    WPP_SF_SS
0x1800070d8  nop
0x1800070d9  mov     [rsp+88h+arg_18], 0
0x1800070e5  lea     rax, [rsp+88h+var_40]
0x1800070ea  mov     [rsp+88h+var_60], rax
0x1800070ef  lea     rax, [rsp+88h+arg_10]
0x1800070f7  mov     [rsp+88h+var_68], rax
0x1800070fc  xor     r9d, r9d
0x1800070ff  xor     r8d, r8d; pReturnValue
0x180007102  lea     edx, [r9+16h]; nProcNum
0x180007106  lea     rcx, pProxyInfo; pProxyInfo
0x18000710d  call    cs:__imp_NdrClientCall3
0x180007113  mov     rbx, rax
0x180007116  mov     [rsp+88h+arg_18], rax
0x18000711e  mov     [rsp+88h+var_58], eax
0x180007122  jmp     short loc_180007156
0x180007124  mov     edi, eax
0x180007126  mov     ebx, eax
0x180007128  mov     [rsp+88h+var_58], eax
0x18000712c  call    cs:__imp_GetCommandLineW
0x180007132  mov     rdx, rax
0x180007135  mov     ecx, ebx
0x180007137  call    TraceRpcException
0x18000713c  mov     r14, [rsp+88h+arg_8]
0x180007144  mov     rdi, [rsp+88h+arg_0]
0x18000714c  mov     r15, [rsp+88h+var_50]
0x180007151  mov     rsi, [rsp+88h+var_48]
0x180007156  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000715d  jz      short loc_180007183
0x18000715f  call    cs:__imp_GetCommandLineW
0x180007165  mov     edx, 0ACh
0x18000716a  mov     [rsp+88h+var_60], rax
0x18000716f  mov     [rsp+88h+var_68], rdi
0x180007174  mov     r9d, ebx
0x180007177  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000717e  call    WPP_SF_DSS
0x180007183  test    ebx, ebx
0x180007185  jnz     short loc_1800071BB
0x180007187  cmp     [rsi], ebx
0x180007189  jnz     short loc_180007193
0x18000718b  mov     eax, dword ptr [rsp+88h+Size]
0x18000718f  mov     [rsi], eax
0x180007191  jmp     short loc_1800071BB
0x180007193  mov     ecx, dword ptr [rsp+88h+Size]
0x180007197  cmp     [rsi], ecx
0x180007199  mov     [rsi], ecx
0x18000719b  jnb     short loc_1800071A4
0x18000719d  mov     ebx, 0EAh
0x1800071a2  jmp     short loc_1800071BB
0x1800071a4  mov     al, [rsp+88h+var_40]
0x1800071a8  mov     [r14], al
0x1800071ab  mov     r8, rcx; Size
0x1800071ae  mov     rdx, [rsp+88h+Size+4]; Src
0x1800071b3  mov     rcx, [r15]; void *
0x1800071b6  call    memcpy_0
0x1800071bb  lea     rcx, [rsp+88h+Size+4]
0x1800071c0  call    DhcpMidlUserFree
0x1800071c5  test    byte ptr cs:xmmword_18001E1E0, 10h
0x1800071cc  jz      short loc_1800071EB
0x1800071ce  mov     edx, 0ADh
0x1800071d3  mov     ecx, 404h
0x1800071d8  mov     dword ptr [rsp+88h+var_68], ebx
0x1800071dc  mov     r9, rdi
0x1800071df  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x1800071e6  call    WPP_SF_SD
0x1800071eb  mov     eax, ebx
0x1800071ed  add     rsp, 60h
0x1800071f1  pop     r15
0x1800071f3  pop     r14
0x1800071f5  pop     rdi
0x1800071f6  pop     rsi
0x1800071f7  pop     rbx
0x1800071f8  retn
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
