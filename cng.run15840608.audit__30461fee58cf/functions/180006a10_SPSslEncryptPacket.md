# SPSslEncryptPacket

- ea: `0x180006a10`
- end: `0x180006cdd`
- name: `SPSslEncryptPacket`
- size: `717`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180006a10`
- `0x180006cf0`
- `0x18000743c`
- `0x1800082b0`
- `0x18003e9dc`
- `0x180081428`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x180006c40`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180006c40`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180006c55`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180006c55`
- `ntoskrnl!ExReleaseResourceLite` at `0x18009ee29`
- `ntoskrnl!ExReleaseResourceLite` at `0x18009ee29`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18009ee35`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18009ee35`

## string_xrefs

- `0x180006abb`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180006bb7`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180006be1`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180006c27`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180006c88`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180006cbb`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslEncryptPacket(
        _DWORD *a1,
        _DWORD *a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        int a6,
        __int64 a7,
        __int64 a8,
        int a9,
        int a10)
{
  unsigned int v14; // ebx
  _QWORD *v15; // rcx
  int v16; // eax
  int v17; // eax
  __int64 v19; // r9
  char v20; // [rsp+30h] [rbp-48h]

  if ( !dword_1800CC0A4 )
  {
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(&Resource, 1u);
    if ( !dword_1800CC0A4 )
    {
      GetExternalSchannelAlgorithms();
      dword_1800CC0A4 = 1;
    }
    ExReleaseResourceLite(&Resource);
    KeLeaveCriticalRegion();
  }
  if ( a1 && *a1 >= 0x390u && a1[1] == 1936944177 )
  {
    if ( a2 && *a2 >= 0x70u && a2[1] == 1936944179 )
    {
      if ( a3 && a4 <= 0x8000 )
      {
        if ( !a5 || !a7 )
        {
          v14 = -2146893785;
          DebugTraceError(
            2148073511LL,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
            1867);
          return v14;
        }
        if ( !a10 )
        {
          v16 = a2[2];
          if ( v16 == 2 )
          {
            v14 = -2146893783;
            DebugTraceError(
              2148073513LL,
              "Status",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
              1887);
            return v14;
          }
          if ( v16 == 772 )
          {
            v17 = Tls13EncryptPacket(a1, a2, a3, a4, a5, a6, a7, a8, a9);
            v14 = v17;
            if ( v17 >= 0 )
              return v14;
            v19 = 1904;
          }
          else
          {
            v17 = TlsEncryptPacket(a1, a2, a3, a4, a5, a6, a7, a8, a9);
            v14 = v17;
            if ( v17 >= 0 )
              return v14;
            v19 = 1922;
          }
          DebugTraceError(
            (unsigned int)v17,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
            v19);
          return v14;
        }
        v14 = -2146893815;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            a7,
            a3,
            (unsigned int)"Status",
            9,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
            82);
      }
      else
      {
        v14 = -2146893785;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            (_DWORD)a2,
            a3,
            (unsigned int)"Status",
            39,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
            68);
      }
    }
    else
    {
      v14 = -2146893786;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      {
        v20 = 61;
        goto LABEL_14;
      }
    }
  }
  else
  {
    v14 = -2146893786;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
    {
      v20 = 52;
LABEL_14:
      WPP_SF_sDsd(
        v15[3],
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        v20);
    }
  }
  return v14;
}

```

## disassembly

```asm
0x180006a10  push    rbx
0x180006a12  push    rbp
0x180006a13  push    rsi
0x180006a14  push    rdi
0x180006a15  sub     rsp, 58h
0x180006a19  cmp     cs:dword_1800CC0A4, 0
0x180006a20  mov     esi, r9d
0x180006a23  mov     rbp, r8
0x180006a26  mov     rbx, rdx
0x180006a29  mov     rdi, rcx
0x180006a2c  jz      loc_180006C40
0x180006a32  test    rdi, rdi
0x180006a35  jz      short loc_180006A48
0x180006a37  cmp     dword ptr [rdi], 390h
0x180006a3d  jb      short loc_180006A48
0x180006a3f  cmp     dword ptr [rdi+4], 73736C31h
0x180006a46  jz      short loc_180006A79
0x180006a48  mov     ebx, 80090026h
0x180006a4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a54  lea     rax, WPP_GLOBAL_Control
0x180006a5b  cmp     rcx, rax
0x180006a5e  jz      loc_180006B84
0x180006a64  mov     eax, [rcx+2Ch]
0x180006a67  test    al, 1
0x180006a69  jz      loc_180006B84
0x180006a6f  mov     dword ptr [rsp+78h+var_48], 734h
0x180006a77  jmp     short loc_180006ABB
0x180006a79  test    rbx, rbx
0x180006a7c  jz      short loc_180006A8C
0x180006a7e  cmp     dword ptr [rbx], 70h ; 'p'
0x180006a81  jb      short loc_180006A8C
0x180006a83  cmp     dword ptr [rbx+4], 73736C33h
0x180006a8a  jz      short loc_180006AE4
0x180006a8c  mov     ebx, 80090026h
0x180006a91  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a98  lea     rax, WPP_GLOBAL_Control
0x180006a9f  cmp     rcx, rax
0x180006aa2  jz      loc_180006B84
0x180006aa8  mov     eax, [rcx+2Ch]
0x180006aab  test    al, 1
0x180006aad  jz      loc_180006B84
0x180006ab3  mov     dword ptr [rsp+78h+var_48], 73Dh
0x180006abb  lea     rax, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006ac2  mov     [rsp+78h+var_50], rax
0x180006ac7  mov     dword ptr [rsp+78h+var_58], 80090026h
0x180006acf  mov     rcx, [rcx+18h]
0x180006ad3  lea     r9, aStatus; "Status"
0x180006ada  call    WPP_SF_sDsd
0x180006adf  jmp     loc_180006B84
0x180006ae4  test    rbp, rbp
0x180006ae7  jz      loc_180006B90
0x180006aed  cmp     esi, 8000h
0x180006af3  ja      loc_180006B90
0x180006af9  mov     rcx, [rsp+78h+arg_20]
0x180006b01  test    rcx, rcx
0x180006b04  jz      loc_180006CB5
0x180006b0a  mov     rdx, [rsp+78h+arg_30]
0x180006b12  test    rdx, rdx
0x180006b15  jz      loc_180006CB5
0x180006b1b  cmp     [rsp+78h+arg_48], 0
0x180006b23  jnz     loc_180006BF8
0x180006b29  mov     eax, [rbx+8]
0x180006b2c  cmp     eax, 2
0x180006b2f  jz      loc_180006C82
0x180006b35  cmp     eax, 304h
0x180006b3a  mov     r9d, esi
0x180006b3d  mov     eax, [rsp+78h+arg_40]
0x180006b44  mov     r8, rbp
0x180006b47  mov     [rsp+78h+var_38], eax
0x180006b4b  mov     rax, [rsp+78h+arg_38]
0x180006b53  mov     [rsp+78h+var_40], rax
0x180006b58  mov     eax, [rsp+78h+arg_28]
0x180006b5f  mov     [rsp+78h+var_48], rdx
0x180006b64  mov     rdx, rbx
0x180006b67  mov     dword ptr [rsp+78h+var_50], eax
0x180006b6b  mov     [rsp+78h+var_58], rcx
0x180006b70  mov     rcx, rdi
0x180006b73  jnz     short loc_180006BD0
0x180006b75  call    Tls13EncryptPacket
0x180006b7a  mov     ebx, eax
0x180006b7c  test    eax, eax
0x180006b7e  js      loc_180006CAA
0x180006b84  mov     eax, ebx
0x180006b86  add     rsp, 58h
0x180006b8a  pop     rdi
0x180006b8b  pop     rsi
0x180006b8c  pop     rbp
0x180006b8d  pop     rbx
0x180006b8e  retn
0x180006b90  mov     ebx, 80090027h
0x180006b95  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b9c  lea     rax, WPP_GLOBAL_Control
0x180006ba3  cmp     rcx, rax
0x180006ba6  jz      short loc_180006B84
0x180006ba8  mov     eax, [rcx+2Ch]
0x180006bab  test    al, 1
0x180006bad  jz      short loc_180006B84
0x180006baf  mov     dword ptr [rsp+78h+var_48], 744h
0x180006bb7  lea     rax, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006bbe  mov     [rsp+78h+var_50], rax
0x180006bc3  mov     dword ptr [rsp+78h+var_58], 80090027h
0x180006bcb  jmp     loc_180006ACF
0x180006bd0  call    TlsEncryptPacket
0x180006bd5  mov     ebx, eax
0x180006bd7  test    eax, eax
0x180006bd9  jns     short loc_180006B84
0x180006bdb  mov     r9d, 782h
0x180006be1  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006be8  mov     ecx, eax
0x180006bea  lea     rdx, aStatus; "Status"
0x180006bf1  call    DebugTraceError
0x180006bf6  jmp     short loc_180006B84
0x180006bf8  mov     ebx, 80090009h
0x180006bfd  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c04  lea     rax, WPP_GLOBAL_Control
0x180006c0b  cmp     rcx, rax
0x180006c0e  jz      loc_180006B84
0x180006c14  mov     eax, [rcx+2Ch]
0x180006c17  test    al, 1
0x180006c19  jz      loc_180006B84
0x180006c1f  mov     dword ptr [rsp+78h+var_48], 752h
0x180006c27  lea     rax, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006c2e  mov     [rsp+78h+var_50], rax
0x180006c33  mov     dword ptr [rsp+78h+var_58], 80090009h
0x180006c3b  jmp     loc_180006ACF
0x180006c40  call    cs:__imp_KeEnterCriticalRegion
0x180006c47  nop     dword ptr [rax+rax+00h]
0x180006c4c  mov     dl, 1; Wait
0x180006c4e  lea     rcx, Resource; Resource
0x180006c55  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180006c5c  nop     dword ptr [rax+rax+00h]
0x180006c61  cmp     cs:dword_1800CC0A4, 0
0x180006c68  jnz     loc_18009EE22
0x180006c6e  call    GetExternalSchannelAlgorithms
0x180006c73  mov     cs:dword_1800CC0A4, 1
0x180006c7d  jmp     loc_18009EE22
0x180006c82  mov     r9d, 75Fh
0x180006c88  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006c8f  lea     rdx, aStatus; "Status"
0x180006c96  mov     ecx, 80090029h
0x180006c9b  mov     ebx, 80090029h
0x180006ca0  call    DebugTraceError
0x180006ca5  jmp     loc_180006B84
0x180006caa  mov     r9d, 770h
0x180006cb0  jmp     loc_180006BE1
0x180006cb5  mov     r9d, 74Bh
0x180006cbb  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006cc2  lea     rdx, aStatus; "Status"
0x180006cc9  mov     ecx, 80090027h
0x180006cce  mov     ebx, 80090027h
0x180006cd3  call    DebugTraceError
0x180006cd8  jmp     loc_180006B84
0x18009ee22  lea     rcx, Resource; Resource
0x18009ee29  call    cs:__imp_ExReleaseResourceLite
0x18009ee30  nop     dword ptr [rax+rax+00h]
0x18009ee35  call    cs:__imp_KeLeaveCriticalRegion
0x18009ee3c  nop     dword ptr [rax+rax+00h]
0x18009ee41  nop
0x18009ee42  jmp     loc_180006A32
```
