# SPSslDecryptPacket

- ea: `0x1800115b0`
- end: `0x180011873`
- name: `SPSslDecryptPacket`
- size: `707`
- prototype: `__int64 __fastcall(int, int, int, int, PUCHAR, ULONG, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18001155c`
- `0x1800115b0`
- `0x180011880`
- `0x1800123d0`
- `0x1800484b0`
- `0x18008b618`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1800117d6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800117d6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800117eb`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800117eb`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a5dc7`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a5dc7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a5dd3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a5dd3`

## string_xrefs

- `0x18001165b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18001174e`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18001178e`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800117bc`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18001181e`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180011851`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslDecryptPacket(
        _DWORD *a1,
        _DWORD *a2,
        unsigned __int64 a3,
        unsigned int a4,
        PUCHAR a5,
        ULONG a6,
        ULONG *a7,
        unsigned __int64 a8,
        int a9)
{
  unsigned int v13; // ebx
  _QWORD *v14; // rcx
  int v15; // eax
  int v16; // eax
  __int64 v18; // r9
  char v19; // [rsp+30h] [rbp-38h]

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
      if ( a3 && a4 - 1 <= 0xFFFF )
      {
        if ( !a5 || !a7 )
        {
          v13 = -2146893785;
          DebugTraceError(
            2148073511LL,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
            1743);
          return v13;
        }
        if ( !a9 )
        {
          v15 = a2[2];
          if ( v15 == 2 )
          {
            v13 = -2146893783;
            DebugTraceError(
              2148073513LL,
              "Status",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
              1763);
            return v13;
          }
          if ( v15 == 772 )
          {
            v16 = Tls13DecryptPacket((__int64)a1, (__int64)a2, a3, a4, a5, a6, a7, a8);
            v13 = v16;
            if ( v16 >= 0 )
              return v13;
            v18 = 1779;
          }
          else
          {
            v16 = TlsDecryptPacket(a1, a2, a3, a4);
            v13 = v16;
            if ( v16 >= 0 )
              return v13;
            v18 = 1796;
          }
          DebugTraceError(
            (unsigned int)v16,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
            v18);
          return v13;
        }
        v13 = -2146893815;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            (_DWORD)a7,
            a3,
            (unsigned int)"Status",
            9,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
            214);
      }
      else
      {
        v13 = -2146893785;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            (_DWORD)a2,
            a3,
            (unsigned int)"Status",
            39,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
            200);
      }
    }
    else
    {
      v13 = -2146893786;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      {
        v19 = -63;
        goto LABEL_14;
      }
    }
  }
  else
  {
    v13 = -2146893786;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
    {
      v19 = -72;
LABEL_14:
      WPP_SF_sDsd(
        v14[3],
        (_DWORD)a2,
        a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        v19);
    }
  }
  return v13;
}

```

## disassembly

```asm
0x1800115b0  push    rbx
0x1800115b2  push    rbp
0x1800115b3  push    rsi
0x1800115b4  push    rdi
0x1800115b5  sub     rsp, 48h
0x1800115b9  cmp     cs:dword_1800D40E4, 0
0x1800115c0  mov     ebp, r9d
0x1800115c3  mov     rsi, r8
0x1800115c6  mov     rbx, rdx
0x1800115c9  mov     rdi, rcx
0x1800115cc  jz      loc_1800117D6
0x1800115d2  test    rdi, rdi
0x1800115d5  jz      short loc_1800115E8
0x1800115d7  cmp     dword ptr [rdi], 390h
0x1800115dd  jb      short loc_1800115E8
0x1800115df  cmp     dword ptr [rdi+4], 73736C31h
0x1800115e6  jz      short loc_180011619
0x1800115e8  mov     ebx, 80090026h
0x1800115ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800115f4  lea     rax, WPP_GLOBAL_Control
0x1800115fb  cmp     rcx, rax
0x1800115fe  jz      loc_18001171B
0x180011604  mov     eax, [rcx+2Ch]
0x180011607  test    al, 1
0x180011609  jz      loc_18001171B
0x18001160f  mov     dword ptr [rsp+68h+var_38], 6B8h
0x180011617  jmp     short loc_18001165B
0x180011619  test    rbx, rbx
0x18001161c  jz      short loc_18001162C
0x18001161e  cmp     dword ptr [rbx], 70h ; 'p'
0x180011621  jb      short loc_18001162C
0x180011623  cmp     dword ptr [rbx+4], 73736C33h
0x18001162a  jz      short loc_180011684
0x18001162c  mov     ebx, 80090026h
0x180011631  mov     rcx, cs:WPP_GLOBAL_Control
0x180011638  lea     rax, WPP_GLOBAL_Control
0x18001163f  cmp     rcx, rax
0x180011642  jz      loc_18001171B
0x180011648  mov     eax, [rcx+2Ch]
0x18001164b  test    al, 1
0x18001164d  jz      loc_18001171B
0x180011653  mov     dword ptr [rsp+68h+var_38], 6C1h
0x18001165b  lea     rax, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011662  mov     qword ptr [rsp+68h+var_40], rax
0x180011667  mov     dword ptr [rsp+68h+var_48], 80090026h
0x18001166f  mov     rcx, [rcx+18h]
0x180011673  lea     r9, aStatus; "Status"
0x18001167a  call    WPP_SF_sDsd
0x18001167f  jmp     loc_18001171B
0x180011684  test    rsi, rsi
0x180011687  jz      loc_180011767
0x18001168d  lea     eax, [rbp-1]
0x180011690  cmp     eax, 0FFFFh
0x180011695  ja      loc_180011767
0x18001169b  mov     rcx, [rsp+68h+arg_20]
0x1800116a3  test    rcx, rcx
0x1800116a6  jz      loc_18001184B
0x1800116ac  mov     rdx, [rsp+68h+arg_30]
0x1800116b4  test    rdx, rdx
0x1800116b7  jz      loc_18001184B
0x1800116bd  cmp     [rsp+68h+arg_40], 0
0x1800116c5  jnz     short loc_180011727
0x1800116c7  mov     eax, [rbx+8]
0x1800116ca  cmp     eax, 2
0x1800116cd  jz      loc_180011818
0x1800116d3  cmp     eax, 304h
0x1800116d8  mov     r9d, ebp; int
0x1800116db  mov     rax, [rsp+68h+arg_38]
0x1800116e3  mov     r8, rsi; int
0x1800116e6  mov     [rsp+68h+var_30], rax; __int64
0x1800116eb  mov     eax, [rsp+68h+arg_28]
0x1800116f2  mov     [rsp+68h+var_38], rdx; __int64
0x1800116f7  mov     rdx, rbx; int
0x1800116fa  mov     [rsp+68h+var_40], eax; ULONG
0x1800116fe  mov     [rsp+68h+var_48], rcx; PUCHAR
0x180011703  mov     rcx, rdi; int
0x180011706  jnz     loc_1800117A7
0x18001170c  call    Tls13DecryptPacket
0x180011711  mov     ebx, eax
0x180011713  test    eax, eax
0x180011715  js      loc_180011840
0x18001171b  mov     eax, ebx
0x18001171d  add     rsp, 48h
0x180011721  pop     rdi
0x180011722  pop     rsi
0x180011723  pop     rbp
0x180011724  pop     rbx
0x180011725  retn
0x180011727  mov     ebx, 80090009h
0x18001172c  mov     rcx, cs:WPP_GLOBAL_Control
0x180011733  lea     rax, WPP_GLOBAL_Control
0x18001173a  cmp     rcx, rax
0x18001173d  jz      short loc_18001171B
0x18001173f  mov     eax, [rcx+2Ch]
0x180011742  test    al, 1
0x180011744  jz      short loc_18001171B
0x180011746  mov     dword ptr [rsp+68h+var_38], 6D6h
0x18001174e  lea     rax, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011755  mov     qword ptr [rsp+68h+var_40], rax
0x18001175a  mov     dword ptr [rsp+68h+var_48], 80090009h
0x180011762  jmp     loc_18001166F
0x180011767  mov     ebx, 80090027h
0x18001176c  mov     rcx, cs:WPP_GLOBAL_Control
0x180011773  lea     rax, WPP_GLOBAL_Control
0x18001177a  cmp     rcx, rax
0x18001177d  jz      short loc_18001171B
0x18001177f  mov     eax, [rcx+2Ch]
0x180011782  test    al, 1
0x180011784  jz      short loc_18001171B
0x180011786  mov     dword ptr [rsp+68h+var_38], 6C8h
0x18001178e  lea     rax, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011795  mov     qword ptr [rsp+68h+var_40], rax
0x18001179a  mov     dword ptr [rsp+68h+var_48], 80090027h
0x1800117a2  jmp     loc_18001166F
0x1800117a7  call    TlsDecryptPacket
0x1800117ac  mov     ebx, eax
0x1800117ae  test    eax, eax
0x1800117b0  jns     loc_18001171B
0x1800117b6  mov     r9d, 704h
0x1800117bc  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800117c3  mov     ecx, eax
0x1800117c5  lea     rdx, aStatus; "Status"
0x1800117cc  call    DebugTraceError
0x1800117d1  jmp     loc_18001171B
0x1800117d6  call    cs:__imp_KeEnterCriticalRegion
0x1800117dd  nop     dword ptr [rax+rax+00h]
0x1800117e2  mov     dl, 1; Wait
0x1800117e4  lea     rcx, Resource; Resource
0x1800117eb  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1800117f2  nop     dword ptr [rax+rax+00h]
0x1800117f7  cmp     cs:dword_1800D40E4, 0
0x1800117fe  jnz     loc_1800A5DC0
0x180011804  call    GetExternalSchannelAlgorithms
0x180011809  mov     cs:dword_1800D40E4, 1
0x180011813  jmp     loc_1800A5DC0
0x180011818  mov     r9d, 6E3h
0x18001181e  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011825  lea     rdx, aStatus; "Status"
0x18001182c  mov     ecx, 80090029h
0x180011831  mov     ebx, 80090029h
0x180011836  call    DebugTraceError
0x18001183b  jmp     loc_18001171B
0x180011840  mov     r9d, 6F3h
0x180011846  jmp     loc_1800117BC
0x18001184b  mov     r9d, 6CFh
0x180011851  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011858  lea     rdx, aStatus; "Status"
0x18001185f  mov     ecx, 80090027h
0x180011864  mov     ebx, 80090027h
0x180011869  call    DebugTraceError
0x18001186e  jmp     loc_18001171B
0x1800a5dc0  lea     rcx, Resource; Resource
0x1800a5dc7  call    cs:__imp_ExReleaseResourceLite
0x1800a5dce  nop     dword ptr [rax+rax+00h]
0x1800a5dd3  call    cs:__imp_KeLeaveCriticalRegion
0x1800a5dda  nop     dword ptr [rax+rax+00h]
0x1800a5ddf  nop
0x1800a5de0  jmp     loc_1800115D2
```
