# SPSslDecryptPacket

- ea: `0x180007490`
- end: `0x180007753`
- name: `SPSslDecryptPacket`
- size: `707`
- prototype: `__int64 __fastcall(int, int, int, int, PUCHAR, ULONG, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000743c`
- `0x180007490`
- `0x180007760`
- `0x1800082b0`
- `0x18003f080`
- `0x180082418`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1800076b6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800076b6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800076cb`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800076cb`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a0e59`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800a0e59`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a0e65`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800a0e65`

## string_xrefs

- `0x18000753b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000762e`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000766e`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000769c`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800076fe`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180007731`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

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

  if ( !dword_1800CE0E4 )
  {
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(&Resource, 1u);
    if ( !dword_1800CE0E4 )
    {
      GetExternalSchannelAlgorithms();
      dword_1800CE0E4 = 1;
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
0x180007490  push    rbx
0x180007492  push    rbp
0x180007493  push    rsi
0x180007494  push    rdi
0x180007495  sub     rsp, 48h
0x180007499  cmp     cs:dword_1800CE0E4, 0
0x1800074a0  mov     ebp, r9d
0x1800074a3  mov     rsi, r8
0x1800074a6  mov     rbx, rdx
0x1800074a9  mov     rdi, rcx
0x1800074ac  jz      loc_1800076B6
0x1800074b2  test    rdi, rdi
0x1800074b5  jz      short loc_1800074C8
0x1800074b7  cmp     dword ptr [rdi], 390h
0x1800074bd  jb      short loc_1800074C8
0x1800074bf  cmp     dword ptr [rdi+4], 73736C31h
0x1800074c6  jz      short loc_1800074F9
0x1800074c8  mov     ebx, 80090026h
0x1800074cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800074d4  lea     rax, WPP_GLOBAL_Control
0x1800074db  cmp     rcx, rax
0x1800074de  jz      loc_1800075FB
0x1800074e4  mov     eax, [rcx+2Ch]
0x1800074e7  test    al, 1
0x1800074e9  jz      loc_1800075FB
0x1800074ef  mov     dword ptr [rsp+68h+var_38], 6B8h
0x1800074f7  jmp     short loc_18000753B
0x1800074f9  test    rbx, rbx
0x1800074fc  jz      short loc_18000750C
0x1800074fe  cmp     dword ptr [rbx], 70h ; 'p'
0x180007501  jb      short loc_18000750C
0x180007503  cmp     dword ptr [rbx+4], 73736C33h
0x18000750a  jz      short loc_180007564
0x18000750c  mov     ebx, 80090026h
0x180007511  mov     rcx, cs:WPP_GLOBAL_Control
0x180007518  lea     rax, WPP_GLOBAL_Control
0x18000751f  cmp     rcx, rax
0x180007522  jz      loc_1800075FB
0x180007528  mov     eax, [rcx+2Ch]
0x18000752b  test    al, 1
0x18000752d  jz      loc_1800075FB
0x180007533  mov     dword ptr [rsp+68h+var_38], 6C1h
0x18000753b  lea     rax, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007542  mov     qword ptr [rsp+68h+var_40], rax
0x180007547  mov     dword ptr [rsp+68h+var_48], 80090026h
0x18000754f  mov     rcx, [rcx+18h]
0x180007553  lea     r9, aStatus; "Status"
0x18000755a  call    WPP_SF_sDsd
0x18000755f  jmp     loc_1800075FB
0x180007564  test    rsi, rsi
0x180007567  jz      loc_180007647
0x18000756d  lea     eax, [rbp-1]
0x180007570  cmp     eax, 0FFFFh
0x180007575  ja      loc_180007647
0x18000757b  mov     rcx, [rsp+68h+arg_20]
0x180007583  test    rcx, rcx
0x180007586  jz      loc_18000772B
0x18000758c  mov     rdx, [rsp+68h+arg_30]
0x180007594  test    rdx, rdx
0x180007597  jz      loc_18000772B
0x18000759d  cmp     [rsp+68h+arg_40], 0
0x1800075a5  jnz     short loc_180007607
0x1800075a7  mov     eax, [rbx+8]
0x1800075aa  cmp     eax, 2
0x1800075ad  jz      loc_1800076F8
0x1800075b3  cmp     eax, 304h
0x1800075b8  mov     r9d, ebp; int
0x1800075bb  mov     rax, [rsp+68h+arg_38]
0x1800075c3  mov     r8, rsi; int
0x1800075c6  mov     [rsp+68h+var_30], rax; __int64
0x1800075cb  mov     eax, [rsp+68h+arg_28]
0x1800075d2  mov     [rsp+68h+var_38], rdx; __int64
0x1800075d7  mov     rdx, rbx; int
0x1800075da  mov     [rsp+68h+var_40], eax; ULONG
0x1800075de  mov     [rsp+68h+var_48], rcx; PUCHAR
0x1800075e3  mov     rcx, rdi; int
0x1800075e6  jnz     loc_180007687
0x1800075ec  call    Tls13DecryptPacket
0x1800075f1  mov     ebx, eax
0x1800075f3  test    eax, eax
0x1800075f5  js      loc_180007720
0x1800075fb  mov     eax, ebx
0x1800075fd  add     rsp, 48h
0x180007601  pop     rdi
0x180007602  pop     rsi
0x180007603  pop     rbp
0x180007604  pop     rbx
0x180007605  retn
0x180007607  mov     ebx, 80090009h
0x18000760c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007613  lea     rax, WPP_GLOBAL_Control
0x18000761a  cmp     rcx, rax
0x18000761d  jz      short loc_1800075FB
0x18000761f  mov     eax, [rcx+2Ch]
0x180007622  test    al, 1
0x180007624  jz      short loc_1800075FB
0x180007626  mov     dword ptr [rsp+68h+var_38], 6D6h
0x18000762e  lea     rax, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007635  mov     qword ptr [rsp+68h+var_40], rax
0x18000763a  mov     dword ptr [rsp+68h+var_48], 80090009h
0x180007642  jmp     loc_18000754F
0x180007647  mov     ebx, 80090027h
0x18000764c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007653  lea     rax, WPP_GLOBAL_Control
0x18000765a  cmp     rcx, rax
0x18000765d  jz      short loc_1800075FB
0x18000765f  mov     eax, [rcx+2Ch]
0x180007662  test    al, 1
0x180007664  jz      short loc_1800075FB
0x180007666  mov     dword ptr [rsp+68h+var_38], 6C8h
0x18000766e  lea     rax, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007675  mov     qword ptr [rsp+68h+var_40], rax
0x18000767a  mov     dword ptr [rsp+68h+var_48], 80090027h
0x180007682  jmp     loc_18000754F
0x180007687  call    TlsDecryptPacket
0x18000768c  mov     ebx, eax
0x18000768e  test    eax, eax
0x180007690  jns     loc_1800075FB
0x180007696  mov     r9d, 704h
0x18000769c  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800076a3  mov     ecx, eax
0x1800076a5  lea     rdx, aStatus; "Status"
0x1800076ac  call    DebugTraceError
0x1800076b1  jmp     loc_1800075FB
0x1800076b6  call    cs:__imp_KeEnterCriticalRegion
0x1800076bd  nop     dword ptr [rax+rax+00h]
0x1800076c2  mov     dl, 1; Wait
0x1800076c4  lea     rcx, Resource; Resource
0x1800076cb  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1800076d2  nop     dword ptr [rax+rax+00h]
0x1800076d7  cmp     cs:dword_1800CE0E4, 0
0x1800076de  jnz     loc_1800A0E52
0x1800076e4  call    GetExternalSchannelAlgorithms
0x1800076e9  mov     cs:dword_1800CE0E4, 1
0x1800076f3  jmp     loc_1800A0E52
0x1800076f8  mov     r9d, 6E3h
0x1800076fe  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007705  lea     rdx, aStatus; "Status"
0x18000770c  mov     ecx, 80090029h
0x180007711  mov     ebx, 80090029h
0x180007716  call    DebugTraceError
0x18000771b  jmp     loc_1800075FB
0x180007720  mov     r9d, 6F3h
0x180007726  jmp     loc_18000769C
0x18000772b  mov     r9d, 6CFh
0x180007731  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007738  lea     rdx, aStatus; "Status"
0x18000773f  mov     ecx, 80090027h
0x180007744  mov     ebx, 80090027h
0x180007749  call    DebugTraceError
0x18000774e  jmp     loc_1800075FB
0x1800a0e52  lea     rcx, Resource; Resource
0x1800a0e59  call    cs:__imp_ExReleaseResourceLite
0x1800a0e60  nop     dword ptr [rax+rax+00h]
0x1800a0e65  call    cs:__imp_KeLeaveCriticalRegion
0x1800a0e6c  nop     dword ptr [rax+rax+00h]
0x1800a0e71  nop
0x1800a0e72  jmp     loc_1800074B2
```
