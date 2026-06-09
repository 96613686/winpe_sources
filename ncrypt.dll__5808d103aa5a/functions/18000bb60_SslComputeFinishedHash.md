# SslComputeFinishedHash

- ea: `0x18000bb60`
- end: `0x18000bcb1`
- name: `SslComputeFinishedHash`
- size: `337`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x18000bb60`
- `0x18000c8e0`
- `0x18000d02c`
- `0x18000e120`
- `0x180020010`

## string_xrefs

- `0x18000bbf6`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000bc9a`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslComputeFinishedHash(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        NCryptAlgorithmName **a4,
        BYTE *a5,
        DWORD *a6,
        DWORD *a7)
{
  unsigned int v7; // ebx
  int v8; // eax

  if ( a1 && *(_DWORD *)a1 >= 0x1B0u && *(_DWORD *)(a1 + 4) == 1145324609 && !*(_DWORD *)(a1 + 12) )
  {
    if ( a2 && *(_DWORD *)a2 >= 0x20u && *(_DWORD *)(a2 + 4) == 1145324610 )
    {
      if ( a3 && *(_DWORD *)a3 >= 0x20u && *(_DWORD *)(a3 + 4) == 1145324611 )
      {
        v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(a1 + 56))(
               *(_QWORD *)(a1 + 424),
               *(_QWORD *)(a2 + 16),
               *(_QWORD *)(a3 + 16));
        v7 = v8;
        if ( v8 < 0 )
          DebugTraceError((unsigned int)v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 492);
        else
          v7 = 0;
      }
      else
      {
        v7 = -2146893786;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            a2,
            a3,
            (unsigned int)"Status",
            38,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
            218);
      }
    }
    else
    {
      v7 = -2146893786;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          a2,
          a3,
          (unsigned int)"Status",
          38,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
          210);
    }
  }
  else
  {
    v7 = -2146893786;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        202);
  }
  return NormalizeNteStatus(v7, (NCRYPT_KEY_HANDLE *)a2, (NCryptKeyName **)a3, a4, a5, a6, a7);
}

```

## disassembly

```asm
0x18000bb60  push    rbx
0x18000bb62  sub     rsp, 40h
0x18000bb66  mov     r10, rdx
0x18000bb69  test    rcx, rcx
0x18000bb6c  jz      short loc_18000BB85
0x18000bb6e  cmp     dword ptr [rcx], 1B0h
0x18000bb74  jb      short loc_18000BB85
0x18000bb76  cmp     dword ptr [rcx+4], 44444441h
0x18000bb7d  jnz     short loc_18000BB85
0x18000bb7f  cmp     dword ptr [rcx+0Ch], 0
0x18000bb83  jz      short loc_18000BBB5
0x18000bb85  mov     ebx, 80090026h
0x18000bb8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb91  lea     rax, WPP_GLOBAL_Control
0x18000bb98  cmp     rcx, rax
0x18000bb9b  jz      loc_18000BC48
0x18000bba1  test    byte ptr [rcx+1Ch], 1
0x18000bba5  jz      loc_18000BC48
0x18000bbab  mov     [rsp+48h+var_18], 1CAh
0x18000bbb3  jmp     short loc_18000BBF2
0x18000bbb5  test    r10, r10
0x18000bbb8  jz      short loc_18000BBCC
0x18000bbba  cmp     dword ptr [rdx], 20h ; ' '
0x18000bbbd  jb      short loc_18000BBCC
0x18000bbbf  cmp     dword ptr [rdx+4], 44444442h
0x18000bbc6  jz      loc_18000BC54
0x18000bbcc  mov     ebx, 80090026h
0x18000bbd1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bbd8  lea     rax, WPP_GLOBAL_Control
0x18000bbdf  cmp     rcx, rax
0x18000bbe2  jz      short loc_18000BC48
0x18000bbe4  test    byte ptr [rcx+1Ch], 1
0x18000bbe8  jz      short loc_18000BC48
0x18000bbea  mov     [rsp+48h+var_18], 1D2h
0x18000bbf2  mov     rcx, [rcx+10h]
0x18000bbf6  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000bbfd  mov     [rsp+48h+var_20], rax
0x18000bc02  lea     r9, aStatus; "Status"
0x18000bc09  mov     [rsp+48h+var_28], 80090026h
0x18000bc11  call    WPP_SF_sDsd
0x18000bc16  jmp     short loc_18000BC48
0x18000bc18  mov     edx, [rsp+48h+arg_28]
0x18000bc1c  mov     rax, [rcx+38h]
0x18000bc20  mov     r8, [r8+10h]
0x18000bc24  mov     rcx, [rcx+1A8h]
0x18000bc2b  mov     dword ptr [rsp+48h+var_20], edx
0x18000bc2f  mov     edx, dword ptr [rsp+48h+arg_20]
0x18000bc33  mov     [rsp+48h+var_28], edx
0x18000bc37  mov     rdx, [r10+10h]
0x18000bc3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc40  mov     ebx, eax
0x18000bc42  test    eax, eax
0x18000bc44  js      short loc_18000BC94
0x18000bc46  xor     ebx, ebx
0x18000bc48  mov     ecx, ebx
0x18000bc4a  add     rsp, 40h
0x18000bc4e  pop     rbx
0x18000bc4f  jmp     NormalizeNteStatus
0x18000bc54  test    r8, r8
0x18000bc57  jz      short loc_18000BC69
0x18000bc59  cmp     dword ptr [r8], 20h ; ' '
0x18000bc5d  jb      short loc_18000BC69
0x18000bc5f  cmp     dword ptr [r8+4], 44444443h
0x18000bc67  jz      short loc_18000BC18
0x18000bc69  mov     ebx, 80090026h
0x18000bc6e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bc75  lea     rax, WPP_GLOBAL_Control
0x18000bc7c  cmp     rcx, rax
0x18000bc7f  jz      short loc_18000BC48
0x18000bc81  test    byte ptr [rcx+1Ch], 1
0x18000bc85  jz      short loc_18000BC48
0x18000bc87  mov     [rsp+48h+var_18], 1DAh
0x18000bc8f  jmp     loc_18000BBF2
0x18000bc94  mov     r9d, 1ECh
0x18000bc9a  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000bca1  lea     rdx, aStatus; "Status"
0x18000bca8  mov     ecx, eax
0x18000bcaa  call    DebugTraceError
0x18000bcaf  jmp     short loc_18000BC48
```
