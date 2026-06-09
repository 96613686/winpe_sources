# DnsLogEvent

- ea: `0x18009fa80`
- end: `0x18009fbdd`
- name: `DnsLogEvent`
- size: `349`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180083954`
- `0x180084c4c`
- `0x18008b5f0`
- `0x18009fa80`
- `0x1800dc9e0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18009fb87`
- `ntdll!EtwEventWrite` at `0x18009fb87`
- `ntdll!EtwEventEnabled` at `0x18009fb04`
- `ntdll!EtwEventEnabled` at `0x18009fb04`

## pseudocode

```c
void __fastcall DnsLogEvent(__int64 a1, unsigned int a2, __int64 a3, int a4)
{
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  unsigned int v10; // r9d
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rax
  REGHANDLE v16; // rcx
  unsigned int v17; // eax
  _QWORD v18[40]; // [rsp+20h] [rbp-168h] BYREF
  LPCSTR retaddr; // [rsp+188h] [rbp+0h]
  int v20; // [rsp+1A8h] [rbp+20h] BYREF

  v20 = a4;
  if ( g_fVelocitySuppressInternalExports && !g_DnsIsCache && !(unsigned int)Dns_IsCallerDns(retaddr) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v7);
    return;
  }
  if ( a2 >= 0x14 )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
      return;
    v8 = 40;
    v9 = a2;
    goto LABEL_17;
  }
  if ( (unsigned __int8)EtwEventEnabled(DNS_CLIENT_Context, a1) )
  {
    v10 = 0;
    if ( a2 )
    {
      v11 = 0;
      do
      {
        v12 = *(_QWORD *)(a3 + 8 * v11);
        v13 = -1;
        do
          ++v13;
        while ( *(_WORD *)(v12 + 2 * v13) );
        v14 = 2 * v11;
        ++v10;
        ++v11;
        v18[v14] = v12;
        LODWORD(v18[v14 + 1]) = 2 * v13 + 2;
        HIDWORD(v18[v14 + 1]) = 0;
      }
      while ( v10 < a2 );
    }
    v15 = 2LL * v10;
    v18[v15] = &v20;
    v16 = DNS_CLIENT_Context;
    v18[v15 + 1] = 4;
    v17 = EtwEventWrite(v16, a1, a2 + 1, v18);
    if ( v17 )
    {
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      {
        v8 = 41;
        v9 = v17;
LABEL_17:
        WPP_SF_d(1035, v8, WPP_d982d6bc31e73d929163a0dfdffe34f3_Traceguids, v9);
      }
    }
  }
}

```

## disassembly

```asm
0x18009fa80  mov     [rsp+arg_10], rbx
0x18009fa85  mov     [rsp+arg_18], r9d
0x18009fa8a  push    rbp
0x18009fa8b  push    rsi
0x18009fa8c  push    rdi
0x18009fa8d  sub     rsp, 170h
0x18009fa94  mov     rax, cs:__security_cookie
0x18009fa9b  xor     rax, rsp
0x18009fa9e  mov     [rsp+188h+var_28], rax
0x18009faa6  xor     ebp, ebp
0x18009faa8  mov     rsi, r8
0x18009faab  cmp     cs:g_fVelocitySuppressInternalExports, ebp
0x18009fab1  mov     ebx, edx
0x18009fab3  mov     rdi, rcx
0x18009fab6  jz      short loc_18009FADB
0x18009fab8  cmp     cs:g_DnsIsCache, ebp
0x18009fabe  jnz     short loc_18009FADB
0x18009fac0  mov     rcx, [rsp+188h]; lpModuleName
0x18009fac8  call    Dns_IsCallerDns
0x18009facd  test    eax, eax
0x18009facf  jnz     short loc_18009FADB
0x18009fad1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009fad6  jmp     loc_18009FBB9
0x18009fadb  cmp     ebx, 14h
0x18009fade  jb      short loc_18009FAFA
0x18009fae0  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18009fae7  jz      loc_18009FBB9
0x18009faed  mov     edx, 28h ; '('
0x18009faf2  mov     r9d, ebx
0x18009faf5  jmp     loc_18009FBA8
0x18009fafa  mov     rcx, cs:DNS_CLIENT_Context
0x18009fb01  mov     rdx, rdi
0x18009fb04  call    cs:__imp_EtwEventEnabled
0x18009fb0b  nop     dword ptr [rax+rax+00h]
0x18009fb10  test    al, al
0x18009fb12  jz      loc_18009FBB9
0x18009fb18  mov     r9d, ebp
0x18009fb1b  test    ebx, ebx
0x18009fb1d  jz      short loc_18009FB58
0x18009fb1f  mov     r8, rbp
0x18009fb22  mov     rdx, [rsi+r8*8]
0x18009fb26  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009fb2a  inc     rax
0x18009fb2d  cmp     [rdx+rax*2], bp
0x18009fb31  jnz     short loc_18009FB2A
0x18009fb33  mov     rcx, r8
0x18009fb36  lea     eax, ds:2[rax*2]
0x18009fb3d  add     rcx, rcx
0x18009fb40  inc     r9d
0x18009fb43  inc     r8
0x18009fb46  mov     [rsp+rcx*8+188h+var_168], rdx
0x18009fb4b  mov     dword ptr [rsp+rcx*8+188h+var_160], eax
0x18009fb4f  mov     dword ptr [rsp+rcx*8+188h+var_160+4], ebp
0x18009fb53  cmp     r9d, ebx
0x18009fb56  jb      short loc_18009FB22
0x18009fb58  mov     eax, r9d
0x18009fb5b  lea     rcx, [rsp+188h+arg_18]
0x18009fb63  add     rax, rax
0x18009fb66  lea     r8d, [rbx+1]
0x18009fb6a  lea     r9, [rsp+188h+var_168]
0x18009fb6f  mov     rdx, rdi
0x18009fb72  mov     [rsp+rax*8+188h+var_168], rcx
0x18009fb77  mov     rcx, cs:DNS_CLIENT_Context
0x18009fb7e  mov     [rsp+rax*8+188h+var_160], 4
0x18009fb87  call    cs:__imp_EtwEventWrite
0x18009fb8e  nop     dword ptr [rax+rax+00h]
0x18009fb93  test    eax, eax
0x18009fb95  jz      short loc_18009FBB9
0x18009fb97  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18009fb9e  jz      short loc_18009FBB9
0x18009fba0  mov     edx, 29h ; ')'
0x18009fba5  mov     r9d, eax
0x18009fba8  lea     r8, WPP_d982d6bc31e73d929163a0dfdffe34f3_Traceguids
0x18009fbaf  mov     ecx, 40Bh
0x18009fbb4  call    WPP_SF_d
0x18009fbb9  mov     rcx, [rsp+188h+var_28]
0x18009fbc1  xor     rcx, rsp; StackCookie
0x18009fbc4  call    __security_check_cookie
0x18009fbc9  mov     rbx, [rsp+188h+arg_10]
0x18009fbd1  add     rsp, 170h
0x18009fbd8  pop     rdi
0x18009fbd9  pop     rsi
0x18009fbda  pop     rbp
0x18009fbdb  retn
```
