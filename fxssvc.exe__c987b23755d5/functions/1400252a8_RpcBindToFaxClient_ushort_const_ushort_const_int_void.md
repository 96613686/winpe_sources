# RpcBindToFaxClient(ushort const *,ushort const *,int,void * *)

- ea: `0x1400252a8`
- end: `0x14002559a`
- name: `?RpcBindToFaxClient@@YAKPEBG0HPEAPEAX@Z`
- size: `754`
- prototype: `unsigned int __fastcall(wchar_t *String2, RPC_WSTR Endpoint, unsigned int AuthzSvc, RPC_BINDING_HANDLE *Binding)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001186c`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x1400252a8`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400253f3`
- `KERNEL32!GetLastError` at `0x1400253f3`
- `KERNEL32!GetComputerNameW` at `0x140025339`
- `KERNEL32!GetComputerNameW` at `0x140025339`
- `msvcrt!_wcsicmp` at `0x14002534e`
- `msvcrt!_wcsicmp` at `0x14002536d`
- `msvcrt!_wcsicmp` at `0x14002534e`
- `msvcrt!_wcsicmp` at `0x14002536d`
- `RPCRT4!RpcBindingFree` at `0x1400254d6`
- `RPCRT4!RpcBindingFree` at `0x1400254d6`
- `RPCRT4!RpcStringBindingComposeW` at `0x1400253af`
- `RPCRT4!RpcStringBindingComposeW` at `0x1400253af`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x140025439`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x140025439`
- `RPCRT4!RpcStringFreeW` at `0x140025445`
- `RPCRT4!RpcStringFreeW` at `0x140025445`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x140025499`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x140025499`
- `RPCRT4!RpcBindingSetOption` at `0x1400254f6`
- `RPCRT4!RpcBindingSetOption` at `0x1400254f6`

## pseudocode

```c
__int64 __fastcall RpcBindToFaxClient(
        wchar_t *String2,
        RPC_WSTR Endpoint,
        unsigned int AuthzSvc,
        RPC_BINDING_HANDLE *Binding)
{
  unsigned __int16 *v8; // rdx
  unsigned int v9; // eax
  __int64 result; // rax
  DWORD LastError; // eax
  unsigned int v12; // ebx
  unsigned int v13; // ebx
  RPC_BINDING_HANDLE v14; // rcx
  CMapDeviceId *v15; // rcx
  __int64 v16; // rdx
  DWORD nSize; // [rsp+40h] [rbp-19h] BYREF
  RPC_WSTR String; // [rsp+48h] [rbp-11h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+50h] [rbp-9h] BYREF
  WCHAR Buffer[16]; // [rsp+60h] [rbp+7h] BYREF

  String = 0;
  nSize = 16;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids);
  }
  *Binding = 0;
  if ( AuthzSvc )
  {
    String2 = 0;
  }
  else
  {
    if ( !String2 )
      goto LABEL_13;
    if ( !GetComputerNameW(Buffer, &nSize) )
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, LastError);
      }
      return v12;
    }
    if ( !_wcsicmp(Buffer, String2) || *String2 == 92 && String2[1] == 92 && !_wcsicmp(Buffer, String2 + 2) )
LABEL_13:
      String2 = L"127.0.0.1";
  }
  v8 = L"ncalrpc";
  if ( !AuthzSvc )
    v8 = L"ncacn_ip_tcp";
  v9 = RpcStringBindingComposeW(0, v8, String2, Endpoint, (RPC_WSTR)&Class, &String);
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v9);
    }
    return 3221225495LL;
  }
  v13 = RpcBindingFromStringBindingW(String, Binding);
  RpcStringFreeW(&String);
  if ( !v13 )
  {
    v14 = *Binding;
    if ( *Binding )
    {
      if ( AuthzSvc
        || (*(_QWORD *)&SecurityQOS.Version = 1,
            SecurityQOS.IdentityTracking = 0,
            SecurityQOS.ImpersonationType = 2,
            (v12 = RpcBindingSetAuthInfoExW(v14, 0, 6u, 0xAu, 0, 0, &SecurityQOS)) == 0) )
      {
        v12 = RpcBindingSetOption(*Binding, 0xCu, 0x7530u);
        if ( !v12 )
          return 0;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_36;
        }
        v16 = 86;
      }
      else
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_36;
        }
        v16 = 85;
      }
      WPP_SF_d(*((_QWORD *)v15 + 2), v16, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v12);
LABEL_36:
      RpcBindingFree(Binding);
      *Binding = 0;
      return v12;
    }
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v13);
  }
  *Binding = 0;
  result = 1210;
  if ( v13 != 1706 && v13 != 1707 )
    return 3221225495LL;
  return result;
}

```

## disassembly

```asm
0x1400252a8  mov     [rsp-8+arg_10], rbx
0x1400252ad  push    rbp
0x1400252ae  push    rsi
0x1400252af  push    rdi
0x1400252b0  push    r13
0x1400252b2  push    r14
0x1400252b4  lea     rbp, [rsp-37h]
0x1400252b9  sub     rsp, 90h
0x1400252c0  mov     rax, cs:__security_cookie
0x1400252c7  xor     rax, rsp
0x1400252ca  mov     [rbp+57h+var_30], rax
0x1400252ce  mov     rdi, r9
0x1400252d1  mov     [rbp+57h+String], 0
0x1400252d9  mov     esi, r8d
0x1400252dc  mov     [rbp+57h+nSize], 10h
0x1400252e3  mov     r14, rdx
0x1400252e6  mov     rbx, rcx
0x1400252e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400252f0  lea     r13, WPP_GLOBAL_Control
0x1400252f7  cmp     rcx, r13
0x1400252fa  jz      short loc_14002531D
0x1400252fc  test    byte ptr [rcx+1Ch], 4
0x140025300  jz      short loc_14002531D
0x140025302  cmp     byte ptr [rcx+19h], 5
0x140025306  jb      short loc_14002531D
0x140025308  mov     rcx, [rcx+10h]
0x14002530c  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x140025313  mov     edx, 51h ; 'Q'
0x140025318  call    WPP_SF_
0x14002531d  mov     qword ptr [rdi], 0
0x140025324  test    esi, esi
0x140025326  jz      short loc_14002532C
0x140025328  xor     ebx, ebx
0x14002532a  jmp     short loc_14002537E
0x14002532c  test    rbx, rbx
0x14002532f  jz      short loc_140025377
0x140025331  lea     rdx, [rbp+57h+nSize]; nSize
0x140025335  lea     rcx, [rbp+57h+Buffer]; lpBuffer
0x140025339  call    cs:__imp_GetComputerNameW
0x14002533f  test    eax, eax
0x140025341  jz      loc_1400253F3
0x140025347  mov     rdx, rbx; String2
0x14002534a  lea     rcx, [rbp+57h+Buffer]; String1
0x14002534e  call    cs:__imp__wcsicmp
0x140025354  test    eax, eax
0x140025356  jz      short loc_140025377
0x140025358  cmp     word ptr [rbx], 5Ch ; '\'
0x14002535c  jnz     short loc_14002537E
0x14002535e  cmp     word ptr [rbx+2], 5Ch ; '\'
0x140025363  jnz     short loc_14002537E
0x140025365  lea     rdx, [rbx+4]; String2
0x140025369  lea     rcx, [rbp+57h+Buffer]; String1
0x14002536d  call    cs:__imp__wcsicmp
0x140025373  test    eax, eax
0x140025375  jnz     short loc_14002537E
0x140025377  lea     rbx, a127001; "127.0.0.1"
0x14002537e  lea     rax, ProtSeq; "ncacn_ip_tcp"
0x140025385  test    esi, esi
0x140025387  lea     rdx, aNcalrpc; "ncalrpc"
0x14002538e  mov     r9, r14; Endpoint
0x140025391  cmovz   rdx, rax; ProtSeq
0x140025395  mov     r8, rbx; NetworkAddr
0x140025398  lea     rax, [rbp+57h+String]
0x14002539c  xor     ecx, ecx; ObjUuid
0x14002539e  mov     [rsp+0B0h+StringBinding], rax; StringBinding
0x1400253a3  lea     rax, Class
0x1400253aa  mov     [rsp+0B0h+Options], rax; Options
0x1400253af  call    cs:__imp_RpcStringBindingComposeW
0x1400253b5  test    eax, eax
0x1400253b7  jz      short loc_140025432
0x1400253b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400253c0  cmp     rcx, r13
0x1400253c3  jz      short loc_1400253E9
0x1400253c5  test    byte ptr [rcx+1Ch], 4
0x1400253c9  jz      short loc_1400253E9
0x1400253cb  cmp     byte ptr [rcx+19h], 2
0x1400253cf  jb      short loc_1400253E9
0x1400253d1  mov     rcx, [rcx+10h]
0x1400253d5  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x1400253dc  mov     edx, 53h ; 'S'
0x1400253e1  mov     r9d, eax
0x1400253e4  call    WPP_SF_d
0x1400253e9  mov     eax, 0C0000017h
0x1400253ee  jmp     loc_140025577
0x1400253f3  call    cs:__imp_GetLastError
0x1400253f9  mov     ebx, eax
0x1400253fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140025402  cmp     rcx, r13
0x140025405  jz      short loc_14002542B
0x140025407  test    byte ptr [rcx+1Ch], 4
0x14002540b  jz      short loc_14002542B
0x14002540d  cmp     byte ptr [rcx+19h], 2
0x140025411  jb      short loc_14002542B
0x140025413  mov     rcx, [rcx+10h]
0x140025417  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x14002541e  mov     edx, 52h ; 'R'
0x140025423  mov     r9d, eax
0x140025426  call    WPP_SF_d
0x14002542b  mov     eax, ebx
0x14002542d  jmp     loc_140025577
0x140025432  mov     rcx, [rbp+57h+String]; StringBinding
0x140025436  mov     rdx, rdi; Binding
0x140025439  call    cs:__imp_RpcBindingFromStringBindingW
0x14002543f  lea     rcx, [rbp+57h+String]; String
0x140025443  mov     ebx, eax
0x140025445  call    cs:__imp_RpcStringFreeW
0x14002544b  test    ebx, ebx
0x14002544d  jnz     loc_140025525
0x140025453  mov     rcx, [rdi]; Binding
0x140025456  test    rcx, rcx
0x140025459  jz      loc_140025525
0x14002545f  test    esi, esi
0x140025461  jnz     loc_1400254E8
0x140025467  lea     rax, [rbp+57h+var_60]
0x14002546b  mov     qword ptr [rbp+57h+var_60.Version], 1
0x140025473  mov     [rsp+0B0h+SecurityQOS], rax; SecurityQOS
0x140025478  lea     r9d, [rbx+0Ah]; AuthnSvc
0x14002547c  mov     dword ptr [rsp+0B0h+StringBinding], esi; AuthzSvc
0x140025480  lea     r8d, [rbx+6]; AuthnLevel
0x140025484  xor     edx, edx; ServerPrincName
0x140025486  mov     [rsp+0B0h+Options], 0; AuthIdentity
0x14002548f  mov     [rbp+57h+var_60.IdentityTracking], esi
0x140025492  mov     [rbp+57h+var_60.ImpersonationType], 2
0x140025499  call    cs:__imp_RpcBindingSetAuthInfoExW
0x14002549f  mov     ebx, eax
0x1400254a1  test    eax, eax
0x1400254a3  jz      short loc_1400254E8
0x1400254a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400254ac  cmp     rcx, r13
0x1400254af  jz      short loc_1400254D3
0x1400254b1  test    byte ptr [rcx+1Ch], 4
0x1400254b5  jz      short loc_1400254D3
0x1400254b7  cmp     byte ptr [rcx+19h], 2
0x1400254bb  jb      short loc_1400254D3
0x1400254bd  lea     edx, [rsi+55h]
0x1400254c0  mov     rcx, [rcx+10h]
0x1400254c4  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x1400254cb  mov     r9d, ebx
0x1400254ce  call    WPP_SF_d
0x1400254d3  mov     rcx, rdi; Binding
0x1400254d6  call    cs:__imp_RpcBindingFree
0x1400254dc  mov     qword ptr [rdi], 0
0x1400254e3  jmp     loc_14002542B
0x1400254e8  mov     rcx, [rdi]; hBinding
0x1400254eb  mov     edx, 0Ch; option
0x1400254f0  mov     r8d, 7530h; optionValue
0x1400254f6  call    cs:__imp_RpcBindingSetOption
0x1400254fc  mov     ebx, eax
0x1400254fe  test    eax, eax
0x140025500  jz      short loc_140025521
0x140025502  mov     rcx, cs:WPP_GLOBAL_Control
0x140025509  cmp     rcx, r13
0x14002550c  jz      short loc_1400254D3
0x14002550e  test    byte ptr [rcx+1Ch], 4
0x140025512  jz      short loc_1400254D3
0x140025514  cmp     byte ptr [rcx+19h], 2
0x140025518  jb      short loc_1400254D3
0x14002551a  mov     edx, 56h ; 'V'
0x14002551f  jmp     short loc_1400254C0
0x140025521  xor     eax, eax
0x140025523  jmp     short loc_140025577
0x140025525  mov     rcx, cs:WPP_GLOBAL_Control
0x14002552c  cmp     rcx, r13
0x14002552f  jz      short loc_140025555
0x140025531  test    byte ptr [rcx+1Ch], 4
0x140025535  jz      short loc_140025555
0x140025537  cmp     byte ptr [rcx+19h], 2
0x14002553b  jb      short loc_140025555
0x14002553d  mov     rcx, [rcx+10h]
0x140025541  lea     r8, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x140025548  mov     edx, 54h ; 'T'
0x14002554d  mov     r9d, ebx
0x140025550  call    WPP_SF_d
0x140025555  mov     qword ptr [rdi], 0
0x14002555c  mov     eax, 4BAh
0x140025561  cmp     ebx, 6AAh
0x140025567  jz      short loc_140025577
0x140025569  cmp     ebx, 6ABh
0x14002556f  mov     ecx, 0C0000017h
0x140025574  cmovnz  eax, ecx
0x140025577  mov     rcx, [rbp+57h+var_30]
0x14002557b  xor     rcx, rsp; StackCookie
0x14002557e  call    __security_check_cookie
0x140025583  mov     rbx, [rsp+0B0h+arg_10]
0x14002558b  add     rsp, 90h
0x140025592  pop     r14
0x140025594  pop     r13
0x140025596  pop     rdi
0x140025597  pop     rsi
0x140025598  pop     rbp
0x140025599  retn
```
