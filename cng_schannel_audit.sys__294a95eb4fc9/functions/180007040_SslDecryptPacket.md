# SslDecryptPacket

- ea: `0x180007040`
- end: `0x1800071a7`
- name: `SslDecryptPacket`
- size: `359`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180007040`
- `0x18000743c`
- `0x1800082b0`
- `0x18009d860`

## string_xrefs

- `0x180007069`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x1800070bd`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x180007177`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

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
0x180007040  sub     rsp, 58h
0x180007044  mov     r10, rdx
0x180007047  test    rcx, rcx
0x18000704a  jz      short loc_180007063
0x18000704c  cmp     dword ptr [rcx], 1B0h
0x180007052  jb      short loc_180007063
0x180007054  cmp     dword ptr [rcx+4], 44444441h
0x18000705b  jnz     short loc_180007063
0x18000705d  cmp     dword ptr [rcx+0Ch], 0
0x180007061  jz      short loc_18000708C
0x180007063  mov     r9d, 400h
0x180007069  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007070  lea     rdx, aStatus; "Status"
0x180007077  mov     ecx, 80090026h
0x18000707c  call    DebugTraceError
0x180007081  mov     eax, 80090026h
0x180007086  add     rsp, 58h
0x18000708a  retn
0x18000708c  test    r10, r10
0x18000708f  jz      short loc_18000709F
0x180007091  cmp     dword ptr [rdx], 20h ; ' '
0x180007094  jb      short loc_18000709F
0x180007096  cmp     dword ptr [rdx+4], 44444442h
0x18000709d  jz      short loc_1800070F0
0x18000709f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800070a6  lea     rax, WPP_GLOBAL_Control
0x1800070ad  cmp     rcx, rax
0x1800070b0  jz      short loc_1800070E5
0x1800070b2  mov     eax, [rcx+2Ch]
0x1800070b5  test    al, 1
0x1800070b7  jz      short loc_1800070E5
0x1800070b9  mov     rcx, [rcx+18h]
0x1800070bd  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800070c4  mov     dword ptr [rsp+58h+var_28], 408h
0x1800070cc  lea     r9, aStatus; "Status"
0x1800070d3  mov     [rsp+58h+var_30], r8
0x1800070d8  mov     dword ptr [rsp+58h+var_38], 80090026h
0x1800070e0  call    WPP_SF_sDsd
0x1800070e5  mov     eax, 80090026h
0x1800070ea  add     rsp, 58h
0x1800070ee  retn
0x1800070f0  mov     edx, [rsp+58h+arg_40]
0x1800070f7  mov     rax, [rcx+50h]
0x1800070fb  mov     rcx, [rcx+1A8h]
0x180007102  mov     [rsp+58h+var_18], edx
0x180007106  mov     rdx, [rsp+58h+arg_38]
0x18000710e  mov     [rsp+58h+var_20], rdx
0x180007113  mov     rdx, [rsp+58h+arg_30]
0x18000711b  mov     [rsp+58h+var_28], rdx
0x180007120  mov     edx, [rsp+58h+arg_28]
0x180007127  mov     dword ptr [rsp+58h+var_30], edx
0x18000712b  mov     rdx, [rsp+58h+arg_20]
0x180007133  mov     [rsp+58h+var_38], rdx
0x180007138  mov     rdx, [r10+10h]
0x18000713c  mov     [rsp+58h+var_8], rbx
0x180007141  call    _guard_dispatch_icall
0x180007146  mov     ebx, eax
0x180007148  test    eax, eax
0x18000714a  js      short loc_180007158
0x18000714c  mov     rbx, [rsp+58h+var_8]
0x180007151  xor     eax, eax
0x180007153  jmp     loc_180007086
0x180007158  mov     rcx, cs:WPP_GLOBAL_Control
0x18000715f  lea     rax, WPP_GLOBAL_Control
0x180007166  cmp     rcx, rax
0x180007169  jz      short loc_18000719B
0x18000716b  mov     edx, [rcx+2Ch]
0x18000716e  test    dl, 1
0x180007171  jz      short loc_18000719B
0x180007173  mov     rcx, [rcx+18h]
0x180007177  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000717e  mov     dword ptr [rsp+58h+var_28], 41Dh
0x180007186  lea     r9, aStatus; "Status"
0x18000718d  mov     [rsp+58h+var_30], r8
0x180007192  mov     dword ptr [rsp+58h+var_38], ebx
0x180007196  call    WPP_SF_sDsd
0x18000719b  mov     eax, ebx
0x18000719d  mov     rbx, [rsp+58h+var_8]
0x1800071a2  jmp     loc_180007086
```
