# CWxRpcBinding::Initialize(void *,ushort const *,void *,void *,int)

- ea: `0x1800600c4`
- end: `0x1800603e5`
- name: `?Initialize@CWxRpcBinding@@AEAAJPEAXPEBG00H@Z`
- size: `801`
- prototype: `int(CWxRpcBinding *__hidden this, void *, const unsigned __int16 *, void *, void *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180062788`

## callees

- `0x1800600c4`
- `0x18008b5f0`
- `0x1800cd238`
- `0x1800dc9e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060265`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060292`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060265`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060292`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180060393`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180060393`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180060246`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180060246`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006021d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006021d`
- `RPCRT4!RpcBindingBind` at `0x1800602f6`
- `RPCRT4!RpcBindingBind` at `0x1800602f6`
- `RPCRT4!RpcBindingFree` at `0x180060350`
- `RPCRT4!RpcBindingFree` at `0x1800603b6`
- `RPCRT4!RpcBindingFree` at `0x180060350`
- `RPCRT4!RpcBindingFree` at `0x1800603b6`
- `RPCRT4!RpcBindingCreateW` at `0x1800602d7`
- `RPCRT4!RpcBindingCreateW` at `0x1800602d7`

## pseudocode

```c
__int64 __fastcall CWxRpcBinding::Initialize(CWxRpcBinding *this, void *a2, unsigned __int16 *a3, void *a4, void *a5)
{
  signed int v9; // ebx
  int v10; // r14d
  bool v11; // sf
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  unsigned int v14; // eax
  int v15; // edi
  RPC_STATUS v16; // eax
  RPC_BINDING_HANDLE v18; // [rsp+30h] [rbp-D0h] BYREF
  _OWORD v19[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v20; // [rsp+58h] [rbp-A8h]
  void *v21; // [rsp+68h] [rbp-98h]
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+70h] [rbp-90h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+98h] [rbp-68h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+D0h] [rbp-30h] BYREF
  void *TokenHandle; // [rsp+D8h] [rbp-28h] BYREF
  RPC_BINDING_HANDLE_OPTIONS_V1 Options; // [rsp+E0h] [rbp-20h] BYREF

  HIDWORD(v18) = 0;
  v21 = 0;
  v9 = 0;
  memset(&Template, 0, sizeof(Template));
  Binding = 0;
  v10 = 0;
  TokenHandle = 0;
  Options = 0;
  memset(&Security, 0, sizeof(Security));
  memset(v19, 0, sizeof(v19));
  v20 = 0;
  if ( (BYTE3(xmmword_1801119E0) & 0x20) != 0 )
    WPP_SF_Sl(1053, 13, (unsigned int)WPP_ac4a4d64d6e53010ffafd67edb3b5487_Traceguids, (_DWORD)a3, 1);
  v21 = a4;
  Template.Version = 1;
  Template.ProtocolSequence = 3;
  Template.StringEndpoint = a3;
  Options.Version = 1;
  Options.ComTimeout = 5;
  *(_QWORD *)&v19[0] = 5;
  Options.Flags = 1;
  *((_QWORD *)&v19[0] + 1) = 0x300000001LL;
  if ( a5 )
  {
    *(_QWORD *)&v20 = a5;
    DWORD1(v19[0]) = 17;
  }
  Security.Version = 1;
  Security.SecurityQos = (RPC_SECURITY_QOS *)v19;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 20;
  while ( 1 )
  {
    v14 = RpcBindingCreateW(&Template, &Security, &Options, &Binding);
    v15 = v14;
    if ( !v14 )
      break;
    if ( (byte_1801119D3 & 0x20) != 0 )
      WPP_SF_d(541, 14, WPP_ac4a4d64d6e53010ffafd67edb3b5487_Traceguids, v14);
    if ( v10 )
    {
      v11 = v9 < 0;
      if ( v9 > 0 )
      {
        v9 = (unsigned __int16)v9 | 0x80070000;
        v11 = v9 < 0;
      }
      if ( v11 )
      {
        HIDWORD(v18) = 129;
        goto LABEL_34;
      }
    }
    CurrentThread = GetCurrentThread();
    v10 = 1;
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      v9 = v15;
      if ( v15 > 0 )
        v9 = (unsigned __int16)v15 | 0x80070000;
      if ( v9 < 0 )
      {
        HIDWORD(v18) = 152;
        goto LABEL_34;
      }
    }
    if ( GetLastError() == 1008 )
    {
      v9 = v15;
      if ( v15 > 0 )
        v9 = (unsigned __int16)v15 | 0x80070000;
      if ( v9 < 0 )
      {
        HIDWORD(v18) = 157;
        goto LABEL_34;
      }
    }
    v9 = v15;
    if ( (byte_1801119D3 & 0x20) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(541, 15, WPP_ac4a4d64d6e53010ffafd67edb3b5487_Traceguids, LastError);
    }
    *(_QWORD *)&v19[0] = 1;
    v21 = 0;
    *(_QWORD *)&v20 = 0;
  }
  v16 = RpcBindingBind(0, Binding, a2);
  v9 = v16;
  if ( v16 > 0 )
    v9 = (unsigned __int16)v16 | 0x80070000;
  if ( v9 >= 0 )
  {
    if ( *((_QWORD *)this + 1) )
    {
      v18 = (RPC_BINDING_HANDLE)*((_QWORD *)this + 1);
      RpcBindingFree(&v18);
    }
    *((_QWORD *)this + 1) = Binding;
    Binding = 0;
  }
  else
  {
    HIDWORD(v18) = 175;
  }
LABEL_34:
  if ( (BYTE3(xmmword_1801119E0) & 0x20) != 0 )
    WPP_SF_d(1053, 16, WPP_ac4a4d64d6e53010ffafd67edb3b5487_Traceguids, (unsigned int)v9);
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  if ( Binding )
  {
    v18 = Binding;
    RpcBindingFree(&v18);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800600c4  push    rbp
0x1800600c6  push    rbx
0x1800600c7  push    rsi
0x1800600c8  push    rdi
0x1800600c9  push    r12
0x1800600cb  push    r13
0x1800600cd  push    r14
0x1800600cf  push    r15
0x1800600d1  lea     rbp, [rsp-8]
0x1800600d6  sub     rsp, 108h
0x1800600dd  mov     rax, cs:__security_cookie
0x1800600e4  xor     rax, rsp
0x1800600e7  mov     [rbp+40h+var_50], rax
0x1800600eb  mov     rdi, [rbp+40h+arg_20]
0x1800600ef  xorps   xmm0, xmm0
0x1800600f2  xorps   xmm1, xmm1
0x1800600f5  mov     r13, rcx
0x1800600f8  xor     ecx, ecx
0x1800600fa  mov     r15, r9
0x1800600fd  xor     eax, eax
0x1800600ff  mov     dword ptr [rsp+140h+var_110+4], ecx
0x180060103  mov     qword ptr [rbp+40h+Template.ObjectUuid.Data4], rax
0x180060107  mov     rsi, r8
0x18006010a  mov     [rbp+40h+Security.SecurityQos], rax
0x18006010e  mov     r12, rdx
0x180060111  mov     [rsp+140h+var_D8], rax
0x180060116  mov     ebx, ecx
0x180060118  movups  xmmword ptr [rbp+40h+Template.Version], xmm0
0x18006011c  mov     [rbp+40h+Binding], rcx
0x180060120  mov     r14d, ecx
0x180060123  movups  xmmword ptr [rbp+40h+Template.NetworkAddress], xmm0
0x180060127  mov     [rbp+40h+TokenHandle], rcx
0x18006012b  movups  xmmword ptr [rbp+40h+Template.u1], xmm0
0x18006012f  movups  xmmword ptr [rbp+40h+Options.Version], xmm0
0x180060133  movups  xmmword ptr [rsp+140h+Security.Version], xmm1
0x180060138  movups  xmmword ptr [rbp+40h+Security.AuthnLevel], xmm1
0x18006013c  movups  [rsp+140h+var_108], xmm0
0x180060141  movups  [rsp+140h+var_F8], xmm0
0x180060146  movups  [rsp+140h+var_E8], xmm0
0x18006014b  test    byte ptr cs:xmmword_1801119E0+3, 20h
0x180060152  lea     r8d, [rcx+1]
0x180060156  jz      short loc_18006017A
0x180060158  lea     edx, [rcx+0Dh]
0x18006015b  mov     [rsp+140h+var_120], r8d
0x180060160  mov     ecx, 41Dh
0x180060165  lea     r8, WPP_ac4a4d64d6e53010ffafd67edb3b5487_Traceguids
0x18006016c  mov     r9, rsi
0x18006016f  call    WPP_SF_Sl
0x180060174  mov     r8d, 1
0x18006017a  mov     ecx, 3
0x18006017f  mov     [rsp+140h+var_D8], r15
0x180060184  xor     r15d, r15d
0x180060187  mov     [rbp+40h+Template.Version], r8d
0x18006018b  mov     [rbp+40h+Template.ProtocolSequence], ecx
0x18006018e  mov     [rbp+40h+Template.StringEndpoint], rsi
0x180060192  mov     [rbp+40h+Options.Version], r8d
0x180060196  lea     eax, [rcx+2]
0x180060199  mov     [rbp+40h+Options.ComTimeout], eax
0x18006019c  mov     qword ptr [rsp+140h+var_108], rax
0x1800601a1  mov     [rbp+40h+Options.Flags], r8d
0x1800601a5  mov     dword ptr [rsp+140h+var_108+8], r8d
0x1800601aa  mov     dword ptr [rsp+140h+var_108+0Ch], ecx
0x1800601ae  test    rdi, rdi
0x1800601b1  jz      short loc_1800601C0
0x1800601b3  mov     qword ptr [rsp+140h+var_E8], rdi
0x1800601b8  mov     dword ptr [rsp+140h+var_108+4], 11h
0x1800601c0  lea     rax, [rsp+140h+var_108]
0x1800601c5  mov     [rsp+140h+Security.Version], r8d
0x1800601ca  mov     [rbp+40h+Security.SecurityQos], rax
0x1800601ce  mov     [rbp+40h+Security.AuthnLevel], 6
0x1800601d5  mov     [rbp+40h+Security.AuthnSvc], 14h
0x1800601dc  jmp     loc_1800602C6
0x1800601e1  test    cs:byte_1801119D3, 20h
0x1800601e8  jz      short loc_180060203
0x1800601ea  mov     edx, 0Eh
0x1800601ef  lea     r8, WPP_ac4a4d64d6e53010ffafd67edb3b5487_Traceguids
0x1800601f6  mov     ecx, 21Dh
0x1800601fb  mov     r9d, edi
0x1800601fe  call    WPP_SF_d
0x180060203  test    r14d, r14d
0x180060206  jz      short loc_18006021D
0x180060208  test    ebx, ebx
0x18006020a  jle     short loc_180060217
0x18006020c  movzx   ebx, bx
0x18006020f  or      ebx, 80070000h
0x180060215  test    ebx, ebx
0x180060217  js      loc_18006031F
0x18006021d  call    cs:__imp_GetCurrentThread
0x180060224  nop     dword ptr [rax+rax+00h]
0x180060229  mov     r14d, 1
0x18006022f  movzx   esi, di
0x180060232  lea     r9, [rbp+40h+TokenHandle]; TokenHandle
0x180060236  mov     r8d, r14d; OpenAsSelf
0x180060239  mov     rcx, rax; ThreadHandle
0x18006023c  or      esi, 80070000h
0x180060242  lea     edx, [r14+7]; DesiredAccess
0x180060246  call    cs:__imp_OpenThreadToken
0x18006024d  nop     dword ptr [rax+rax+00h]
0x180060252  test    eax, eax
0x180060254  jz      short loc_180060265
0x180060256  test    edi, edi
0x180060258  mov     ebx, edi
0x18006025a  cmovg   ebx, esi
0x18006025d  test    ebx, ebx
0x18006025f  js      loc_180060329
0x180060265  call    cs:__imp_GetLastError
0x18006026c  nop     dword ptr [rax+rax+00h]
0x180060271  cmp     eax, 3F0h
0x180060276  jnz     short loc_180060287
0x180060278  test    edi, edi
0x18006027a  mov     ebx, edi
0x18006027c  cmovg   ebx, esi
0x18006027f  test    ebx, ebx
0x180060281  js      loc_180060333
0x180060287  mov     ebx, edi
0x180060289  test    cs:byte_1801119D3, 20h
0x180060290  jz      short loc_1800602B7
0x180060292  call    cs:__imp_GetLastError
0x180060299  nop     dword ptr [rax+rax+00h]
0x18006029e  mov     edx, 0Fh
0x1800602a3  lea     r8, WPP_ac4a4d64d6e53010ffafd67edb3b5487_Traceguids
0x1800602aa  mov     r9d, eax
0x1800602ad  mov     ecx, 21Dh
0x1800602b2  call    WPP_SF_d
0x1800602b7  mov     qword ptr [rsp+140h+var_108], r14
0x1800602bc  mov     [rsp+140h+var_D8], r15
0x1800602c1  mov     qword ptr [rsp+140h+var_E8], r15
0x1800602c6  lea     r9, [rbp+40h+Binding]; Binding
0x1800602ca  lea     r8, [rbp+40h+Options]; Options
0x1800602ce  lea     rdx, [rsp+140h+Security]; Security
0x1800602d3  lea     rcx, [rbp+40h+Template]; Template
0x1800602d7  call    cs:__imp_RpcBindingCreateW
0x1800602de  nop     dword ptr [rax+rax+00h]
0x1800602e3  mov     edi, eax
0x1800602e5  test    eax, eax
0x1800602e7  jnz     loc_1800601E1
0x1800602ed  mov     rdx, [rbp+40h+Binding]; Binding
0x1800602f1  mov     r8, r12; IfSpec
0x1800602f4  xor     ecx, ecx; pAsync
0x1800602f6  call    cs:__imp_RpcBindingBind
0x1800602fd  nop     dword ptr [rax+rax+00h]
0x180060302  mov     ebx, eax
0x180060304  test    eax, eax
0x180060306  jle     short loc_180060311
0x180060308  movzx   ebx, ax
0x18006030b  or      ebx, 80070000h
0x180060311  test    ebx, ebx
0x180060313  jns     short loc_18006033D
0x180060315  mov     dword ptr [rsp+140h+var_110+4], 0AFh
0x18006031d  jmp     short loc_180060368
0x18006031f  mov     dword ptr [rsp+140h+var_110+4], 81h
0x180060327  jmp     short loc_180060368
0x180060329  mov     dword ptr [rsp+140h+var_110+4], 98h
0x180060331  jmp     short loc_180060368
0x180060333  mov     dword ptr [rsp+140h+var_110+4], 9Dh
0x18006033b  jmp     short loc_180060368
0x18006033d  mov     rax, [r13+8]
0x180060341  test    rax, rax
0x180060344  jz      short loc_18006035C
0x180060346  lea     rcx, [rsp+140h+var_110]; Binding
0x18006034b  mov     [rsp+140h+var_110], rax
0x180060350  call    cs:__imp_RpcBindingFree
0x180060357  nop     dword ptr [rax+rax+00h]
0x18006035c  mov     rax, [rbp+40h+Binding]
0x180060360  mov     [r13+8], rax
0x180060364  mov     [rbp+40h+Binding], r15
0x180060368  test    byte ptr cs:xmmword_1801119E0+3, 20h
0x18006036f  jz      short loc_18006038A
0x180060371  mov     edx, 10h
0x180060376  lea     r8, WPP_ac4a4d64d6e53010ffafd67edb3b5487_Traceguids
0x18006037d  mov     ecx, 41Dh
0x180060382  mov     r9d, ebx
0x180060385  call    WPP_SF_d
0x18006038a  mov     rcx, [rbp+40h+TokenHandle]; hObject
0x18006038e  test    rcx, rcx
0x180060391  jz      short loc_1800603A3
0x180060393  call    cs:__imp_CloseHandle
0x18006039a  nop     dword ptr [rax+rax+00h]
0x18006039f  mov     [rbp+40h+TokenHandle], r15
0x1800603a3  mov     rcx, [rbp+40h+Binding]
0x1800603a7  test    rcx, rcx
0x1800603aa  jz      short loc_1800603C2
0x1800603ac  mov     [rsp+140h+var_110], rcx
0x1800603b1  lea     rcx, [rsp+140h+var_110]; Binding
0x1800603b6  call    cs:__imp_RpcBindingFree
0x1800603bd  nop     dword ptr [rax+rax+00h]
0x1800603c2  mov     eax, ebx
0x1800603c4  mov     rcx, [rbp+40h+var_50]
0x1800603c8  xor     rcx, rsp; StackCookie
0x1800603cb  call    __security_check_cookie
0x1800603d0  add     rsp, 108h
0x1800603d7  pop     r15
0x1800603d9  pop     r14
0x1800603db  pop     r13
0x1800603dd  pop     r12
0x1800603df  pop     rdi
0x1800603e0  pop     rsi
0x1800603e1  pop     rbx
0x1800603e2  pop     rbp
0x1800603e3  retn
```
