# SslDecryptPacket

- ea: `0x180011160`
- end: `0x1800112c7`
- name: `SslDecryptPacket`
- size: `359`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180011160`
- `0x18001155c`
- `0x1800123d0`
- `0x1800a4300`

## string_xrefs

- `0x180011189`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x1800111dd`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x180011297`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
__int64 __fastcall SslDecryptPacket(__int64 a1, __int64 a2)
{
  int v3; // ebx
  int v4; // edx

  if ( a1 && *(_DWORD *)a1 >= 0x1B0u && *(_DWORD *)(a1 + 4) == 1145324609 && !*(_DWORD *)(a1 + 12) )
  {
    if ( a2 && *(_DWORD *)a2 >= 0x20u && *(_DWORD *)(a2 + 4) == 1145324610 )
    {
      v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(a1 + 80))(*(_QWORD *)(a1 + 424), *(_QWORD *)(a2 + 16));
      if ( v3 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          v4 = *((_DWORD *)WPP_GLOBAL_Control + 11);
          if ( (v4 & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              v4,
              (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
              (unsigned int)"Status",
              v3,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
              29);
        }
        return (unsigned int)v3;
      }
      else
      {
        return 0;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          a2,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
          (unsigned int)"Status",
          38,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
          8);
      return 2148073510LL;
    }
  }
  else
  {
    DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 1024);
    return 2148073510LL;
  }
}

```

## disassembly

```asm
0x180011160  sub     rsp, 58h
0x180011164  mov     r10, rdx
0x180011167  test    rcx, rcx
0x18001116a  jz      short loc_180011183
0x18001116c  cmp     dword ptr [rcx], 1B0h
0x180011172  jb      short loc_180011183
0x180011174  cmp     dword ptr [rcx+4], 44444441h
0x18001117b  jnz     short loc_180011183
0x18001117d  cmp     dword ptr [rcx+0Ch], 0
0x180011181  jz      short loc_1800111AC
0x180011183  mov     r9d, 400h
0x180011189  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011190  lea     rdx, aStatus; "Status"
0x180011197  mov     ecx, 80090026h
0x18001119c  call    DebugTraceError
0x1800111a1  mov     eax, 80090026h
0x1800111a6  add     rsp, 58h
0x1800111aa  retn
0x1800111ac  test    r10, r10
0x1800111af  jz      short loc_1800111BF
0x1800111b1  cmp     dword ptr [rdx], 20h ; ' '
0x1800111b4  jb      short loc_1800111BF
0x1800111b6  cmp     dword ptr [rdx+4], 44444442h
0x1800111bd  jz      short loc_180011210
0x1800111bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800111c6  lea     rax, WPP_GLOBAL_Control
0x1800111cd  cmp     rcx, rax
0x1800111d0  jz      short loc_180011205
0x1800111d2  mov     eax, [rcx+2Ch]
0x1800111d5  test    al, 1
0x1800111d7  jz      short loc_180011205
0x1800111d9  mov     rcx, [rcx+18h]
0x1800111dd  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800111e4  mov     dword ptr [rsp+58h+var_28], 408h
0x1800111ec  lea     r9, aStatus; "Status"
0x1800111f3  mov     [rsp+58h+var_30], r8
0x1800111f8  mov     dword ptr [rsp+58h+var_38], 80090026h
0x180011200  call    WPP_SF_sDsd
0x180011205  mov     eax, 80090026h
0x18001120a  add     rsp, 58h
0x18001120e  retn
0x180011210  mov     edx, [rsp+58h+arg_40]
0x180011217  mov     rax, [rcx+50h]
0x18001121b  mov     rcx, [rcx+1A8h]
0x180011222  mov     [rsp+58h+var_18], edx
0x180011226  mov     rdx, [rsp+58h+arg_38]
0x18001122e  mov     [rsp+58h+var_20], rdx
0x180011233  mov     rdx, [rsp+58h+arg_30]
0x18001123b  mov     [rsp+58h+var_28], rdx
0x180011240  mov     edx, [rsp+58h+arg_28]
0x180011247  mov     dword ptr [rsp+58h+var_30], edx
0x18001124b  mov     rdx, [rsp+58h+arg_20]
0x180011253  mov     [rsp+58h+var_38], rdx
0x180011258  mov     rdx, [r10+10h]
0x18001125c  mov     [rsp+58h+var_8], rbx
0x180011261  call    _guard_dispatch_icall
0x180011266  mov     ebx, eax
0x180011268  test    eax, eax
0x18001126a  js      short loc_180011278
0x18001126c  mov     rbx, [rsp+58h+var_8]
0x180011271  xor     eax, eax
0x180011273  jmp     loc_1800111A6
0x180011278  mov     rcx, cs:WPP_GLOBAL_Control
0x18001127f  lea     rax, WPP_GLOBAL_Control
0x180011286  cmp     rcx, rax
0x180011289  jz      short loc_1800112BB
0x18001128b  mov     edx, [rcx+2Ch]
0x18001128e  test    dl, 1
0x180011291  jz      short loc_1800112BB
0x180011293  mov     rcx, [rcx+18h]
0x180011297  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001129e  mov     dword ptr [rsp+58h+var_28], 41Dh
0x1800112a6  lea     r9, aStatus; "Status"
0x1800112ad  mov     [rsp+58h+var_30], r8
0x1800112b2  mov     dword ptr [rsp+58h+var_38], ebx
0x1800112b6  call    WPP_SF_sDsd
0x1800112bb  mov     eax, ebx
0x1800112bd  mov     rbx, [rsp+58h+var_8]
0x1800112c2  jmp     loc_1800111A6
```
