# DhcpRequestCachedParams

- ea: `0x18000a950`
- end: `0x18000ac3b`
- name: `DhcpRequestCachedParams`
- size: `747`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180001f90`
- `0x180002160`
- `0x180002620`
- `0x180002c50`
- `0x18000a950`
- `0x18000f4ec`
- `0x180010aac`
- `0x1800127f0`
- `0x180012850`
- `0x180012ad0`
- `0x180012d20`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000aae0`
- `RPCRT4!NdrClientCall3` at `0x18000aae0`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000aa91`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000aafc`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000ab2c`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000aa91`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000aafc`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000ab2c`

## pseudocode

```c
__int64 __fastcall DhcpRequestCachedParams(int a1, __int64 a2, __int64 a3, unsigned int *a4)
{
  unsigned int v8; // edi
  unsigned int Pointer; // ebx
  __int64 v10; // r15
  __int64 v11; // r14
  __int64 v12; // rbx
  _BYTE *v13; // rax
  unsigned int i; // r9d
  __int64 v15; // r8
  __int64 v16; // rdx
  LPWSTR CommandLineW; // rax
  int v18; // ecx
  CLIENT_CALL_RETURN v19; // rax
  CLIENT_CALL_RETURN v20; // rdx
  CLIENT_CALL_RETURN v21; // r8
  LPWSTR v22; // rax
  int v23; // ecx
  unsigned int j; // esi
  void *v25; // rax
  __int64 v26; // r12
  __int64 v28; // [rsp+48h] [rbp-50h] BYREF
  CLIENT_CALL_RETURN v29; // [rsp+50h] [rbp-48h]
  __int64 v30; // [rsp+58h] [rbp-40h]
  __int128 v31; // [rsp+60h] [rbp-38h] BYREF
  int v32; // [rsp+A8h] [rbp+10h]

  v32 = a2;
  v8 = 0;
  v28 = 0;
  v31 = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_S(1028, 190, WPP_e15037783097355a5233924022d92169_Traceguids, a2);
  if ( !a1
    && (!a3 || !*(_DWORD *)a3 && *(_QWORD *)(a3 + 8) && *(_DWORD *)(a3 + 16))
    && (v10 = *a4, (_DWORD)v10)
    && (v11 = *((_QWORD *)a4 + 1), (v30 = v11) != 0) )
  {
    LODWORD(v31) = v10;
    v12 = (unsigned int)v10;
    v13 = (_BYTE *)DhcpAlloc(24 * v10, a2, a3);
    *((_QWORD *)&v31 + 1) = v13;
    if ( v13 )
    {
      do
      {
        *v13++ = 0;
        --v12;
      }
      while ( v12 );
      for ( i = 0; i < (unsigned int)v10; ++i )
      {
        v15 = 32LL * i;
        if ( *(_DWORD *)(v15 + v11 + 24) || *(_QWORD *)(v15 + v11 + 16) || *(_DWORD *)(v15 + v11) )
          goto LABEL_4;
        v16 = 3LL * i;
        *(_DWORD *)(*((_QWORD *)&v31 + 1) + 8 * v16 + 4) = *(_DWORD *)(v15 + v11 + 4);
        *(_DWORD *)(*((_QWORD *)&v31 + 1) + 8 * v16 + 8) = *(_DWORD *)(v15 + v11 + 8);
      }
      Pointer = DhcpAdapterNameToIfId(a2, &v28);
      if ( !Pointer )
      {
        if ( (xmmword_18001E1E0 & 0x10) != 0 )
        {
          CommandLineW = GetCommandLineW();
          WPP_SF_SS(v18, 191, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a2, (__int64)CommandLineW);
        }
        v29.Simple = 0;
        v19.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x1Au, 0).Pointer;
        Pointer = (unsigned int)v19.Pointer;
        v29.Pointer = v19.Pointer;
        if ( (xmmword_18001E1E0 & 0x10) != 0 )
        {
          v22 = GetCommandLineW();
          WPP_SF_DSS(v23, 192, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, Pointer, a2, (__int64)v22);
        }
        if ( !Pointer )
        {
          for ( j = 0; j < (unsigned int)v31 && j < (unsigned int)v10; ++j )
          {
            if ( *(_QWORD *)(*((_QWORD *)&v31 + 1) + 24LL * j + 16) )
            {
              v25 = (void *)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))DhcpAlloc)(
                              *(unsigned int *)(*((_QWORD *)&v31 + 1) + 24LL * j + 12),
                              (CLIENT_CALL_RETURN)v20.Simple,
                              (CLIENT_CALL_RETURN)v21.Simple);
              v26 = 32LL * j;
              *(_QWORD *)(v26 + v11 + 16) = v25;
              if ( !v25 )
                goto LABEL_32;
              Pointer = 0;
              *(_DWORD *)(v26 + v11 + 24) = *(_DWORD *)(*((_QWORD *)&v31 + 1) + 24LL * j + 12);
              memcpy_0(
                v25,
                *(const void **)(*((_QWORD *)&v31 + 1) + 24LL * j + 16),
                *(unsigned int *)(*((_QWORD *)&v31 + 1) + 24LL * j + 12));
            }
          }
        }
      }
    }
    else
    {
LABEL_32:
      Pointer = 8;
    }
  }
  else
  {
LABEL_4:
    Pointer = 87;
  }
  if ( *((_QWORD *)&v31 + 1) && (_DWORD)v31 )
  {
    do
      DhcpMidlUserFree(*((_QWORD *)&v31 + 1) + 8 * (3LL * v8++ + 2));
    while ( v8 < (unsigned int)v31 );
  }
  DhcpFree((char *)&v31 + 8);
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_SD(1028, 193, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, v32, Pointer);
  return Pointer;
}

```

## disassembly

```asm
0x18000a950  mov     rax, rsp
0x18000a953  mov     [rax+18h], rbx
0x18000a957  mov     [rax+20h], rsi
0x18000a95b  mov     [rax+10h], rdx
0x18000a95f  push    rdi
0x18000a960  push    r12
0x18000a962  push    r13
0x18000a964  push    r14
0x18000a966  push    r15
0x18000a968  sub     rsp, 70h
0x18000a96c  mov     r14, r9
0x18000a96f  mov     rsi, r8
0x18000a972  mov     r12, rdx
0x18000a975  mov     ebx, ecx
0x18000a977  xor     edi, edi
0x18000a979  mov     [rax-50h], rdi
0x18000a97d  xorps   xmm0, xmm0
0x18000a980  movups  xmmword ptr [rax-38h], xmm0
0x18000a984  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000a98b  jz      short loc_18000A9A6
0x18000a98d  mov     edx, 0BEh
0x18000a992  mov     ecx, 404h
0x18000a997  mov     r9, r12
0x18000a99a  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000a9a1  call    WPP_SF_S
0x18000a9a6  test    ebx, ebx
0x18000a9a8  jz      short loc_18000A9B4
0x18000a9aa  mov     ebx, 57h ; 'W'
0x18000a9af  jmp     loc_18000ABBD
0x18000a9b4  test    rsi, rsi
0x18000a9b7  jz      short loc_18000A9C8
0x18000a9b9  cmp     [rsi], edi
0x18000a9bb  jnz     short loc_18000A9AA
0x18000a9bd  cmp     [rsi+8], rdi
0x18000a9c1  jz      short loc_18000A9AA
0x18000a9c3  cmp     [rsi+10h], edi
0x18000a9c6  jbe     short loc_18000A9AA
0x18000a9c8  mov     r15d, [r14]
0x18000a9cb  mov     [rsp+98h+arg_0], r15d
0x18000a9d3  test    r15d, r15d
0x18000a9d6  jz      short loc_18000A9AA
0x18000a9d8  mov     r14, [r14+8]
0x18000a9dc  mov     [rsp+98h+var_40], r14
0x18000a9e1  test    r14, r14
0x18000a9e4  jz      short loc_18000A9AA
0x18000a9e6  mov     [rsp+98h+var_38], r15d
0x18000a9eb  mov     ebx, r15d
0x18000a9ee  lea     rcx, [r15+r15*2]
0x18000a9f2  shl     rcx, 3
0x18000a9f6  call    DhcpAlloc
0x18000a9fb  mov     [rsp+98h+var_30], rax
0x18000aa00  test    rax, rax
0x18000aa03  jz      loc_18000ABB8
0x18000aa09  test    r15d, r15d
0x18000aa0c  jz      short loc_18000AA1A
0x18000aa0e  mov     [rax], dil
0x18000aa11  inc     rax
0x18000aa14  sub     rbx, 1
0x18000aa18  jnz     short loc_18000AA0E
0x18000aa1a  mov     r9d, edi
0x18000aa1d  cmp     r9d, r15d
0x18000aa20  jnb     short loc_18000AA71
0x18000aa22  mov     eax, r9d
0x18000aa25  mov     r8d, r9d
0x18000aa28  shl     r8, 5
0x18000aa2c  cmp     [r8+r14+18h], edi
0x18000aa31  jnz     loc_18000A9AA
0x18000aa37  cmp     [r8+r14+10h], rdi
0x18000aa3c  jnz     loc_18000A9AA
0x18000aa42  cmp     [r8+r14], edi
0x18000aa46  jnz     loc_18000A9AA
0x18000aa4c  lea     rdx, [rax+rax*2]
0x18000aa50  mov     ecx, [r8+r14+4]
0x18000aa55  mov     rax, [rsp+98h+var_30]
0x18000aa5a  mov     [rax+rdx*8+4], ecx
0x18000aa5e  mov     ecx, [r8+r14+8]
0x18000aa63  mov     rax, [rsp+98h+var_30]
0x18000aa68  mov     [rax+rdx*8+8], ecx
0x18000aa6c  inc     r9d
0x18000aa6f  jmp     short loc_18000AA1D
0x18000aa71  lea     rdx, [rsp+98h+var_50]
0x18000aa76  mov     rcx, r12
0x18000aa79  call    DhcpAdapterNameToIfId
0x18000aa7e  mov     ebx, eax
0x18000aa80  test    eax, eax
0x18000aa82  jnz     loc_18000ABBD
0x18000aa88  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000aa8f  jz      short loc_18000AAB1
0x18000aa91  call    cs:__imp_GetCommandLineW
0x18000aa97  mov     edx, 0BFh
0x18000aa9c  mov     [rsp+98h+var_78], rax
0x18000aaa1  mov     r9, r12
0x18000aaa4  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000aaab  call    WPP_SF_SS
0x18000aab0  nop
0x18000aab1  mov     [rsp+98h+var_48], rdi
0x18000aab6  lea     rax, [rsp+98h+var_38]
0x18000aabb  mov     [rsp+98h+var_68], rax
0x18000aac0  mov     [rsp+98h+var_70], rsi
0x18000aac5  lea     rax, [rsp+98h+var_50]
0x18000aaca  mov     [rsp+98h+var_78], rax
0x18000aacf  xor     r9d, r9d
0x18000aad2  xor     r8d, r8d; pReturnValue
0x18000aad5  lea     edx, [r9+1Ah]; nProcNum
0x18000aad9  lea     rcx, pProxyInfo; pProxyInfo
0x18000aae0  call    cs:__imp_NdrClientCall3
0x18000aae6  mov     rbx, rax
0x18000aae9  mov     [rsp+98h+var_48], rax
0x18000aaee  mov     [rsp+98h+var_58], eax
0x18000aaf2  jmp     short loc_18000AB23
0x18000aaf4  mov     edi, eax
0x18000aaf6  mov     ebx, eax
0x18000aaf8  mov     [rsp+98h+var_58], eax
0x18000aafc  call    cs:__imp_GetCommandLineW
0x18000ab02  mov     rdx, rax
0x18000ab05  mov     ecx, ebx
0x18000ab07  call    TraceRpcException
0x18000ab0c  xor     edi, edi
0x18000ab0e  mov     r15d, [rsp+98h+arg_0]
0x18000ab16  mov     r14, [rsp+98h+var_40]
0x18000ab1b  mov     r12, [rsp+98h+arg_8]
0x18000ab23  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000ab2a  jz      short loc_18000AB50
0x18000ab2c  call    cs:__imp_GetCommandLineW
0x18000ab32  mov     edx, 0C0h
0x18000ab37  mov     [rsp+98h+var_70], rax
0x18000ab3c  mov     [rsp+98h+var_78], r12
0x18000ab41  mov     r9d, ebx
0x18000ab44  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000ab4b  call    WPP_SF_DSS
0x18000ab50  test    ebx, ebx
0x18000ab52  jnz     short loc_18000ABBD
0x18000ab54  mov     esi, edi
0x18000ab56  cmp     esi, [rsp+98h+var_38]
0x18000ab5a  jnb     short loc_18000ABBD
0x18000ab5c  cmp     esi, r15d
0x18000ab5f  jnb     short loc_18000ABBD
0x18000ab61  mov     r12d, esi
0x18000ab64  lea     r13, [r12+r12*2]
0x18000ab68  mov     rax, [rsp+98h+var_30]
0x18000ab6d  cmp     [rax+r13*8+10h], rdi
0x18000ab72  jz      short loc_18000ABB4
0x18000ab74  mov     ecx, [rax+r13*8+0Ch]
0x18000ab79  call    DhcpAlloc
0x18000ab7e  shl     r12, 5
0x18000ab82  mov     [r12+r14+10h], rax
0x18000ab87  test    rax, rax
0x18000ab8a  jz      short loc_18000ABB8
0x18000ab8c  mov     ebx, edi
0x18000ab8e  mov     rcx, [rsp+98h+var_30]
0x18000ab93  mov     edx, [rcx+r13*8+0Ch]
0x18000ab98  mov     [r12+r14+18h], edx
0x18000ab9d  mov     rdx, [rsp+98h+var_30]
0x18000aba2  mov     r8d, [rdx+r13*8+0Ch]; Size
0x18000aba7  mov     rdx, [rdx+r13*8+10h]; Src
0x18000abac  mov     rcx, rax; void *
0x18000abaf  call    memcpy_0
0x18000abb4  inc     esi
0x18000abb6  jmp     short loc_18000AB56
0x18000abb8  mov     ebx, 8
0x18000abbd  cmp     [rsp+98h+var_30], rdi
0x18000abc2  jz      short loc_18000ABEA
0x18000abc4  cmp     [rsp+98h+var_38], edi
0x18000abc8  jbe     short loc_18000ABEA
0x18000abca  mov     eax, edi
0x18000abcc  lea     rcx, [rax+rax*2]
0x18000abd0  mov     rax, [rsp+98h+var_30]
0x18000abd5  lea     rcx, [rcx+2]
0x18000abd9  lea     rcx, [rax+rcx*8]
0x18000abdd  call    DhcpMidlUserFree
0x18000abe2  inc     edi
0x18000abe4  cmp     edi, [rsp+98h+var_38]
0x18000abe8  jb      short loc_18000ABCA
0x18000abea  lea     rcx, [rsp+98h+var_30]
0x18000abef  call    DhcpFree
0x18000abf4  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000abfb  jz      short loc_18000AC1F
0x18000abfd  mov     edx, 0C1h
0x18000ac02  mov     ecx, 404h
0x18000ac07  mov     dword ptr [rsp+98h+var_78], ebx
0x18000ac0b  mov     r9, [rsp+98h+arg_8]
0x18000ac13  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000ac1a  call    WPP_SF_SD
0x18000ac1f  mov     eax, ebx
0x18000ac21  lea     r11, [rsp+98h+var_28]
0x18000ac26  mov     rbx, [r11+40h]
0x18000ac2a  mov     rsi, [r11+48h]
0x18000ac2e  mov     rsp, r11
0x18000ac31  pop     r15
0x18000ac33  pop     r14
0x18000ac35  pop     r13
0x18000ac37  pop     r12
0x18000ac39  pop     rdi
0x18000ac3a  retn
0x180010d30  push    rbp
0x180010d32  sub     rsp, 40h
0x180010d36  mov     rbp, rdx
0x180010d39  mov     rcx, [rcx]
0x180010d3c  mov     ecx, [rcx]; ExceptionCode
0x180010d3e  call    cs:__imp_I_RpcExceptionFilter
0x180010d44  nop
0x180010d45  add     rsp, 40h
0x180010d49  pop     rbp
0x180010d4a  retn
```
