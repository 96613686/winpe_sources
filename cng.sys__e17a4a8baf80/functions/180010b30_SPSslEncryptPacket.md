# SPSslEncryptPacket

- ea: `0x180010b30`
- end: `0x180010dfd`
- name: `SPSslEncryptPacket`
- size: `717`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180010b30`
- `0x180010e10`
- `0x18001155c`
- `0x1800123d0`
- `0x18004899c`
- `0x18008b618`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x180010d60`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180010d60`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180010d75`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180010d75`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a5bc7`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a5bc7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a5bd3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a5bd3`

## string_xrefs

- `0x180010bdb`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180010cd7`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180010d01`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180010d47`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180010da8`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180010ddb`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

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

  if ( !dword_1800D40E4 )
  {
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(&Resource, 1u);
    if ( !dword_1800D40E4 )
    {
      GetExternalSchannelAlgorithms();
      dword_1800D40E4 = 1;
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
0x180010b30  push    rbx
0x180010b32  push    rbp
0x180010b33  push    rsi
0x180010b34  push    rdi
0x180010b35  sub     rsp, 58h
0x180010b39  cmp     cs:dword_1800D40E4, 0
0x180010b40  mov     esi, r9d
0x180010b43  mov     rbp, r8
0x180010b46  mov     rbx, rdx
0x180010b49  mov     rdi, rcx
0x180010b4c  jz      loc_180010D60
0x180010b52  test    rdi, rdi
0x180010b55  jz      short loc_180010B68
0x180010b57  cmp     dword ptr [rdi], 390h
0x180010b5d  jb      short loc_180010B68
0x180010b5f  cmp     dword ptr [rdi+4], 73736C31h
0x180010b66  jz      short loc_180010B99
0x180010b68  mov     ebx, 80090026h
0x180010b6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180010b74  lea     rax, WPP_GLOBAL_Control
0x180010b7b  cmp     rcx, rax
0x180010b7e  jz      loc_180010CA4
0x180010b84  mov     eax, [rcx+2Ch]
0x180010b87  test    al, 1
0x180010b89  jz      loc_180010CA4
0x180010b8f  mov     dword ptr [rsp+78h+var_48], 734h
0x180010b97  jmp     short loc_180010BDB
0x180010b99  test    rbx, rbx
0x180010b9c  jz      short loc_180010BAC
0x180010b9e  cmp     dword ptr [rbx], 70h ; 'p'
0x180010ba1  jb      short loc_180010BAC
0x180010ba3  cmp     dword ptr [rbx+4], 73736C33h
0x180010baa  jz      short loc_180010C04
0x180010bac  mov     ebx, 80090026h
0x180010bb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180010bb8  lea     rax, WPP_GLOBAL_Control
0x180010bbf  cmp     rcx, rax
0x180010bc2  jz      loc_180010CA4
0x180010bc8  mov     eax, [rcx+2Ch]
0x180010bcb  test    al, 1
0x180010bcd  jz      loc_180010CA4
0x180010bd3  mov     dword ptr [rsp+78h+var_48], 73Dh
0x180010bdb  lea     rax, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010be2  mov     [rsp+78h+var_50], rax
0x180010be7  mov     dword ptr [rsp+78h+var_58], 80090026h
0x180010bef  mov     rcx, [rcx+18h]
0x180010bf3  lea     r9, aStatus; "Status"
0x180010bfa  call    WPP_SF_sDsd
0x180010bff  jmp     loc_180010CA4
0x180010c04  test    rbp, rbp
0x180010c07  jz      loc_180010CB0
0x180010c0d  cmp     esi, 8000h
0x180010c13  ja      loc_180010CB0
0x180010c19  mov     rcx, [rsp+78h+arg_20]
0x180010c21  test    rcx, rcx
0x180010c24  jz      loc_180010DD5
0x180010c2a  mov     rdx, [rsp+78h+arg_30]
0x180010c32  test    rdx, rdx
0x180010c35  jz      loc_180010DD5
0x180010c3b  cmp     [rsp+78h+arg_48], 0
0x180010c43  jnz     loc_180010D18
0x180010c49  mov     eax, [rbx+8]
0x180010c4c  cmp     eax, 2
0x180010c4f  jz      loc_180010DA2
0x180010c55  cmp     eax, 304h
0x180010c5a  mov     r9d, esi
0x180010c5d  mov     eax, [rsp+78h+arg_40]
0x180010c64  mov     r8, rbp
0x180010c67  mov     [rsp+78h+var_38], eax
0x180010c6b  mov     rax, [rsp+78h+arg_38]
0x180010c73  mov     [rsp+78h+var_40], rax
0x180010c78  mov     eax, [rsp+78h+arg_28]
0x180010c7f  mov     [rsp+78h+var_48], rdx
0x180010c84  mov     rdx, rbx
0x180010c87  mov     dword ptr [rsp+78h+var_50], eax
0x180010c8b  mov     [rsp+78h+var_58], rcx
0x180010c90  mov     rcx, rdi
0x180010c93  jnz     short loc_180010CF0
0x180010c95  call    Tls13EncryptPacket
0x180010c9a  mov     ebx, eax
0x180010c9c  test    eax, eax
0x180010c9e  js      loc_180010DCA
0x180010ca4  mov     eax, ebx
0x180010ca6  add     rsp, 58h
0x180010caa  pop     rdi
0x180010cab  pop     rsi
0x180010cac  pop     rbp
0x180010cad  pop     rbx
0x180010cae  retn
0x180010cb0  mov     ebx, 80090027h
0x180010cb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180010cbc  lea     rax, WPP_GLOBAL_Control
0x180010cc3  cmp     rcx, rax
0x180010cc6  jz      short loc_180010CA4
0x180010cc8  mov     eax, [rcx+2Ch]
0x180010ccb  test    al, 1
0x180010ccd  jz      short loc_180010CA4
0x180010ccf  mov     dword ptr [rsp+78h+var_48], 744h
0x180010cd7  lea     rax, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010cde  mov     [rsp+78h+var_50], rax
0x180010ce3  mov     dword ptr [rsp+78h+var_58], 80090027h
0x180010ceb  jmp     loc_180010BEF
0x180010cf0  call    TlsEncryptPacket
0x180010cf5  mov     ebx, eax
0x180010cf7  test    eax, eax
0x180010cf9  jns     short loc_180010CA4
0x180010cfb  mov     r9d, 782h
0x180010d01  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010d08  mov     ecx, eax
0x180010d0a  lea     rdx, aStatus; "Status"
0x180010d11  call    DebugTraceError
0x180010d16  jmp     short loc_180010CA4
0x180010d18  mov     ebx, 80090009h
0x180010d1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180010d24  lea     rax, WPP_GLOBAL_Control
0x180010d2b  cmp     rcx, rax
0x180010d2e  jz      loc_180010CA4
0x180010d34  mov     eax, [rcx+2Ch]
0x180010d37  test    al, 1
0x180010d39  jz      loc_180010CA4
0x180010d3f  mov     dword ptr [rsp+78h+var_48], 752h
0x180010d47  lea     rax, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010d4e  mov     [rsp+78h+var_50], rax
0x180010d53  mov     dword ptr [rsp+78h+var_58], 80090009h
0x180010d5b  jmp     loc_180010BEF
0x180010d60  call    cs:__imp_KeEnterCriticalRegion
0x180010d67  nop     dword ptr [rax+rax+00h]
0x180010d6c  mov     dl, 1; Wait
0x180010d6e  lea     rcx, Resource; Resource
0x180010d75  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180010d7c  nop     dword ptr [rax+rax+00h]
0x180010d81  cmp     cs:dword_1800D40E4, 0
0x180010d88  jnz     loc_1800A5BC0
0x180010d8e  call    GetExternalSchannelAlgorithms
0x180010d93  mov     cs:dword_1800D40E4, 1
0x180010d9d  jmp     loc_1800A5BC0
0x180010da2  mov     r9d, 75Fh
0x180010da8  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010daf  lea     rdx, aStatus; "Status"
0x180010db6  mov     ecx, 80090029h
0x180010dbb  mov     ebx, 80090029h
0x180010dc0  call    DebugTraceError
0x180010dc5  jmp     loc_180010CA4
0x180010dca  mov     r9d, 770h
0x180010dd0  jmp     loc_180010D01
0x180010dd5  mov     r9d, 74Bh
0x180010ddb  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010de2  lea     rdx, aStatus; "Status"
0x180010de9  mov     ecx, 80090027h
0x180010dee  mov     ebx, 80090027h
0x180010df3  call    DebugTraceError
0x180010df8  jmp     loc_180010CA4
0x1800a5bc0  lea     rcx, Resource; Resource
0x1800a5bc7  call    cs:__imp_ExReleaseResourceLite
0x1800a5bce  nop     dword ptr [rax+rax+00h]
0x1800a5bd3  call    cs:__imp_KeLeaveCriticalRegion
0x1800a5bda  nop     dword ptr [rax+rax+00h]
0x1800a5bdf  nop
0x1800a5be0  jmp     loc_180010B52
```
