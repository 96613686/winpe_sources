# SslLookupCipherSuiteInfo

- ea: `0x180013790`
- end: `0x18001386d`
- name: `SslLookupCipherSuiteInfo`
- size: `221`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x18000c8e0`
- `0x18000d02c`
- `0x180013790`
- `0x180020010`

## string_xrefs

- `0x1800137db`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18001385b`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslLookupCipherSuiteInfo(
        __int64 a1,
        NCRYPT_KEY_HANDLE *a2,
        NCryptKeyName **a3,
        NCryptAlgorithmName **a4,
        BYTE *a5,
        DWORD *a6,
        DWORD *a7)
{
  int v7; // ebx

  if ( a1 && *(_DWORD *)a1 >= 0x1B0u && *(_DWORD *)(a1 + 4) == 1145324609 && !*(_DWORD *)(a1 + 12) )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD))(a1 + 184))(*(_QWORD *)(a1 + 424));
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)a2,
          (_DWORD)a3,
          (unsigned int)"Status",
          v7,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
          12);
    }
    else
    {
      v7 = 0;
    }
  }
  else
  {
    v7 = -2146893786;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        251);
  }
  return NormalizeNteStatus((unsigned int)v7, a2, a3, a4, a5, a6, a7);
}

```

## disassembly

```asm
0x180013790  push    rbx
0x180013792  sub     rsp, 40h
0x180013796  mov     rax, rcx
0x180013799  test    rcx, rcx
0x18001379c  jz      short loc_1800137B5
0x18001379e  cmp     dword ptr [rcx], 1B0h
0x1800137a4  jb      short loc_1800137B5
0x1800137a6  cmp     dword ptr [rcx+4], 44444441h
0x1800137ad  jnz     short loc_1800137B5
0x1800137af  cmp     dword ptr [rcx+0Ch], 0
0x1800137b3  jz      short loc_180013801
0x1800137b5  mov     ebx, 80090026h
0x1800137ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800137c1  lea     rax, WPP_GLOBAL_Control
0x1800137c8  cmp     rcx, rax
0x1800137cb  jz      short loc_18001382E
0x1800137cd  test    byte ptr [rcx+1Ch], 1
0x1800137d1  jz      short loc_18001382E
0x1800137d3  mov     [rsp+48h+var_18], 0AFBh
0x1800137db  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800137e2  mov     [rsp+48h+var_20], rax
0x1800137e7  mov     dword ptr [rsp+48h+var_28], 80090026h
0x1800137ef  mov     rcx, [rcx+10h]
0x1800137f3  lea     r9, aStatus; "Status"
0x1800137fa  call    WPP_SF_sDsd
0x1800137ff  jmp     short loc_18001382E
0x180013801  mov     ecx, [rsp+48h+arg_28]
0x180013805  mov     dword ptr [rsp+48h+var_20], ecx
0x180013809  mov     rcx, [rsp+48h+arg_20]
0x18001380e  mov     [rsp+48h+var_28], rcx
0x180013813  mov     rcx, [rax+1A8h]
0x18001381a  mov     rax, [rax+0B8h]
0x180013821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013826  mov     ebx, eax
0x180013828  test    eax, eax
0x18001382a  js      short loc_18001383A
0x18001382c  xor     ebx, ebx
0x18001382e  mov     ecx, ebx
0x180013830  add     rsp, 40h
0x180013834  pop     rbx
0x180013835  jmp     NormalizeNteStatus
0x18001383a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013841  lea     rax, WPP_GLOBAL_Control
0x180013848  cmp     rcx, rax
0x18001384b  jz      short loc_18001382E
0x18001384d  test    byte ptr [rcx+1Ch], 1
0x180013851  jz      short loc_18001382E
0x180013853  mov     [rsp+48h+var_18], 0B0Ch
0x18001385b  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180013862  mov     [rsp+48h+var_20], rax
0x180013867  mov     dword ptr [rsp+48h+var_28], ebx
0x18001386b  jmp     short loc_1800137EF
```
