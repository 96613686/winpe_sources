# SslComputeSessionHash

- ea: `0x180013630`
- end: `0x180013781`
- name: `SslComputeSessionHash`
- size: `337`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x18000c8e0`
- `0x18000d02c`
- `0x18000e120`
- `0x180013630`
- `0x180020010`

## string_xrefs

- `0x180013684`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x180013742`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x180013767`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslComputeSessionHash(
        __int64 a1,
        __int64 a2,
        NCryptKeyName **a3,
        NCryptAlgorithmName **a4,
        BYTE *a5,
        __int64 a6,
        DWORD *a7)
{
  unsigned int v7; // ebx
  int v8; // eax

  if ( a1 && *(_DWORD *)a1 >= 0x1B0u && *(_DWORD *)(a1 + 4) == 1145324609 && !*(_DWORD *)(a1 + 12) )
  {
    if ( a2 && *(_DWORD *)a2 >= 0x20u && *(_DWORD *)(a2 + 4) == 1145324611 )
    {
      if ( *(_WORD *)(a1 + 32) < 3u )
      {
        v7 = -2146893783;
        DebugTraceError(2148073513LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 3395);
      }
      else
      {
        v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(a1 + 248))(*(_QWORD *)(a1 + 424), *(_QWORD *)(a2 + 16));
        v7 = v8;
        if ( v8 < 0 )
          DebugTraceError(
            (unsigned int)v8,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
            3413);
      }
    }
    else
    {
      v7 = -2146893786;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          a2,
          (_DWORD)a3,
          (unsigned int)"Status",
          38,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
          53);
    }
  }
  else
  {
    v7 = -2146893786;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        45);
  }
  return NormalizeNteStatus(v7, (NCRYPT_KEY_HANDLE *)a2, a3, a4, a5, a6, a7);
}

```

## disassembly

```asm
0x180013630  push    rbx
0x180013632  sub     rsp, 40h
0x180013636  test    rcx, rcx
0x180013639  jz      short loc_180013656
0x18001363b  cmp     dword ptr [rcx], 1B0h
0x180013641  jb      short loc_180013656
0x180013643  cmp     dword ptr [rcx+4], 44444441h
0x18001364a  jnz     short loc_180013656
0x18001364c  cmp     dword ptr [rcx+0Ch], 0
0x180013650  jz      loc_1800136FE
0x180013656  mov     ebx, 80090026h
0x18001365b  mov     rcx, cs:WPP_GLOBAL_Control
0x180013662  lea     rax, WPP_GLOBAL_Control
0x180013669  cmp     rcx, rax
0x18001366c  jz      loc_1800136F2
0x180013672  test    byte ptr [rcx+1Ch], 1
0x180013676  jz      short loc_1800136F2
0x180013678  mov     [rsp+48h+var_18], 0D2Dh
0x180013680  mov     rcx, [rcx+10h]
0x180013684  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001368b  mov     [rsp+48h+var_20], rax
0x180013690  lea     r9, aStatus; "Status"
0x180013697  mov     [rsp+48h+var_28], 80090026h
0x18001369f  call    WPP_SF_sDsd
0x1800136a4  jmp     short loc_1800136F2
0x1800136a6  mov     eax, 3
0x1800136ab  cmp     ax, [rcx+20h]
0x1800136af  ja      loc_18001373C
0x1800136b5  mov     r10, [rcx+0F8h]
0x1800136bc  mov     eax, [rsp+48h+arg_30]
0x1800136c3  mov     rdx, [rdx+10h]
0x1800136c7  mov     rcx, [rcx+1A8h]
0x1800136ce  mov     [rsp+48h+var_18], eax
0x1800136d2  mov     rax, [rsp+48h+arg_28]
0x1800136d7  mov     [rsp+48h+var_20], rax
0x1800136dc  mov     eax, dword ptr [rsp+48h+arg_20]
0x1800136e0  mov     [rsp+48h+var_28], eax
0x1800136e4  mov     rax, r10
0x1800136e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800136ec  mov     ebx, eax
0x1800136ee  test    eax, eax
0x1800136f0  js      short loc_180013761
0x1800136f2  mov     ecx, ebx
0x1800136f4  add     rsp, 40h
0x1800136f8  pop     rbx
0x1800136f9  jmp     NormalizeNteStatus
0x1800136fe  test    rdx, rdx
0x180013701  jz      short loc_180013711
0x180013703  cmp     dword ptr [rdx], 20h ; ' '
0x180013706  jb      short loc_180013711
0x180013708  cmp     dword ptr [rdx+4], 44444443h
0x18001370f  jz      short loc_1800136A6
0x180013711  mov     ebx, 80090026h
0x180013716  mov     rcx, cs:WPP_GLOBAL_Control
0x18001371d  lea     rax, WPP_GLOBAL_Control
0x180013724  cmp     rcx, rax
0x180013727  jz      short loc_1800136F2
0x180013729  test    byte ptr [rcx+1Ch], 1
0x18001372d  jz      short loc_1800136F2
0x18001372f  mov     [rsp+48h+var_18], 0D35h
0x180013737  jmp     loc_180013680
0x18001373c  mov     r9d, 0D43h
0x180013742  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180013749  lea     rdx, aStatus; "Status"
0x180013750  mov     ecx, 80090029h
0x180013755  mov     ebx, 80090029h
0x18001375a  call    DebugTraceError
0x18001375f  jmp     short loc_1800136F2
0x180013761  mov     r9d, 0D55h
0x180013767  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001376e  lea     rdx, aStatus; "Status"
0x180013775  mov     ecx, eax
0x180013777  call    DebugTraceError
0x18001377c  jmp     loc_1800136F2
```
