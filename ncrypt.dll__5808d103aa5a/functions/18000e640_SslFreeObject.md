# SslFreeObject

- ea: `0x18000e640`
- end: `0x18000ed2e`
- name: `SslFreeObject`
- size: `1774`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007ca0`
- `0x18000a770`
- `0x18000d02c`
- `0x18000e120`
- `0x18000e640`
- `0x18000f5c0`
- `0x18001f175`
- `0x180020010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000e6bf`
- `ntdll!RtlFreeHeap` at `0x18000e8c1`
- `ntdll!RtlFreeHeap` at `0x18000e6bf`
- `ntdll!RtlFreeHeap` at `0x18000e8c1`

## string_xrefs

- `0x18000e7e4`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000e83c`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000e96b`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000eb32`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000eb96`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000ebd6`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000ebf6`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
__int64 __fastcall SslFreeObject(_DWORD *P, int a2)
{
  int v3; // eax
  unsigned int *v4; // rsi
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rcx
  _BYTE *v8; // rax
  __int64 result; // rax
  int v10; // eax
  int v11; // eax
  __int64 v12; // rcx
  _BYTE *v13; // rax

  if ( !P )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        100);
    return 2148073510LL;
  }
  v3 = P[1];
  if ( v3 == 1145324610 )
  {
    if ( *P < 0x20u )
    {
      v6 = -2146893786;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v6;
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        125);
      return 2148073510LL;
    }
    v4 = (unsigned int *)*((_QWORD *)P + 3);
    v5 = (*((__int64 (__fastcall **)(_QWORD))v4 + 15))(*((_QWORD *)P + 2));
    v6 = v5;
    if ( v5 < 0 )
      DebugTraceError((unsigned int)v5, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 1951);
    v7 = (unsigned int)*P;
    v8 = P;
    if ( *P )
    {
      do
      {
        *v8++ = 0;
        --v7;
      }
      while ( v7 );
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4 + 4, 0xFFFFFFFF) > 1 )
    {
LABEL_9:
      if ( (v6 & 0x1FFF0000) == 0x90000 || (v6 & 0x1FFF0000) == 0x100000 )
        return v6;
      if ( !v6 )
        return 0;
      if ( v6 <= 0x216 )
      {
        if ( v6 == 534 )
          return 2147942934LL;
        switch ( v6 )
        {
          case 2u:
          case 3u:
            result = 2148073489LL;
            break;
          case 5u:
            result = 2148073488LL;
            break;
          case 8u:
          case 0xEu:
            return 2148073486LL;
          case 0x57u:
            return 2148073511LL;
          case 0x70u:
            result = 2147942512LL;
            break;
          case 0x7Au:
            return 2148073512LL;
          case 0xB7u:
            result = 2148073487LL;
            break;
          default:
            return v6;
        }
        return result;
      }
      if ( v6 > 0xC000007B )
      {
        if ( v6 <= 0xC0000135 )
        {
          if ( v6 == -1073741515 )
            return 2148073502LL;
          if ( v6 == -1073741637 )
            return 2148073513LL;
          if ( v6 != -1073741670 )
          {
            if ( v6 != -1073741595 )
              return v6;
            return 2148073517LL;
          }
          return 2148073486LL;
        }
        if ( v6 != -1073741502 && v6 != -1073741511 )
        {
          if ( v6 != -1073700864 )
            return v6;
          return 2148073478LL;
        }
      }
      else if ( v6 != -1073741701 )
      {
        if ( v6 != -1073741816 )
        {
          if ( v6 <= 0xC0000008 )
          {
            if ( v6 == -2147023680 )
              return 2147943616LL;
            if ( v6 != 1359 )
            {
              if ( v6 == -2147023673 )
                return 2147943623LL;
              if ( v6 != -2147023496 )
                return v6;
              return 2147943800LL;
            }
            return 2148073517LL;
          }
          if ( v6 == -1073741811 )
            return 2148073511LL;
          if ( v6 != -1073741801 )
          {
            if ( v6 != -1073741789 )
              return v6;
            return 2148073512LL;
          }
          return 2148073486LL;
        }
        return 2148073510LL;
      }
      return 2148073501LL;
    }
LABEL_41:
    if ( v4[3] )
    {
      (*((void (__fastcall **)(_QWORD, _QWORD))v4 + 15))(*((_QWORD *)v4 + 53), 0);
      UnloadProvider(*((_QWORD *)v4 + 3));
      memset_0(v4, 0, *v4);
      MSCryptFree(v4);
    }
    goto LABEL_9;
  }
  v10 = v3 - 1145324609;
  if ( v10 )
  {
    if ( v10 != 2 )
    {
      v6 = -2146893786;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v6;
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        147);
      return 2148073510LL;
    }
    if ( *P < 0x20u )
    {
      v6 = -2146893786;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v6;
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
        138);
      return 2148073510LL;
    }
    v4 = (unsigned int *)*((_QWORD *)P + 3);
    v11 = (*((__int64 (__fastcall **)(_QWORD))v4 + 15))(*((_QWORD *)P + 2));
    v6 = v11;
    if ( v11 < 0 )
      DebugTraceError((unsigned int)v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 1966);
    v12 = (unsigned int)*P;
    v13 = P;
    if ( *P )
    {
      do
      {
        *v13++ = 0;
        --v12;
      }
      while ( v12 );
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4 + 4, 0xFFFFFFFF) > 1 )
      goto LABEL_9;
    goto LABEL_41;
  }
  if ( *P >= 0x1B0u && !P[3] )
  {
    DereferenceSslProvHandle(P);
    return 0;
  }
  DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 1905);
  return 2148073510LL;
}

```

## disassembly

```asm
0x18000e640  mov     [rsp+arg_0], rbx
0x18000e645  mov     [rsp+arg_8], rsi
0x18000e64a  push    rdi
0x18000e64b  sub     rsp, 40h
0x18000e64f  mov     rdi, rcx
0x18000e652  test    rcx, rcx
0x18000e655  jz      loc_18000E94E
0x18000e65b  mov     eax, [rcx+4]
0x18000e65e  cmp     eax, 44444442h
0x18000e663  jnz     loc_18000E81E
0x18000e669  cmp     dword ptr [rcx], 20h ; ' '
0x18000e66c  jb      loc_18000E7BA
0x18000e672  mov     rsi, [rcx+18h]
0x18000e676  mov     rcx, [rcx+10h]
0x18000e67a  mov     rax, [rsi+78h]
0x18000e67e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e683  mov     ebx, eax
0x18000e685  test    eax, eax
0x18000e687  js      loc_18000EBF0
0x18000e68d  mov     ecx, [rdi]
0x18000e68f  mov     rax, rdi
0x18000e692  test    rcx, rcx
0x18000e695  jz      short loc_18000E6AD
0x18000e697  nop     word ptr [rax+rax+00000000h]
0x18000e6a0  mov     byte ptr [rax], 0
0x18000e6a3  lea     rax, [rax+1]
0x18000e6a7  sub     rcx, 1
0x18000e6ab  jnz     short loc_18000E6A0
0x18000e6ad  mov     rcx, gs:60h
0x18000e6b6  mov     r8, rdi; P
0x18000e6b9  xor     edx, edx; Flags
0x18000e6bb  mov     rcx, [rcx+30h]; HeapHandle
0x18000e6bf  call    cs:__imp_RtlFreeHeap
0x18000e6c5  mov     eax, 0FFFFFFFFh
0x18000e6ca  lock xadd [rsi+10h], eax
0x18000e6cf  sub     eax, 1
0x18000e6d2  jle     loc_18000E8DA
0x18000e6d8  mov     eax, ebx
0x18000e6da  and     eax, 1FFF0000h
0x18000e6df  cmp     eax, 90000h
0x18000e6e4  jz      short def_18000E736; jumptable 000000018000E736 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000e6e6  cmp     eax, 100000h
0x18000e6eb  jz      short def_18000E736; jumptable 000000018000E736 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000e6ed  test    ebx, ebx
0x18000e6ef  jnz     short loc_18000E705
0x18000e6f1  xor     ebx, ebx
0x18000e6f3  mov     eax, ebx; jumptable 000000018000E736 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000e6f5  mov     rbx, [rsp+48h+arg_0]
0x18000e6fa  mov     rsi, [rsp+48h+arg_8]
0x18000e6ff  add     rsp, 40h
0x18000e703  pop     rdi
0x18000e704  retn
0x18000e705  cmp     ebx, 216h
0x18000e70b  ja      short loc_18000E74F
0x18000e70d  jz      loc_18000EA41
0x18000e713  lea     eax, [rbx-2]; switch 182 cases
0x18000e716  cmp     eax, 0B5h
0x18000e71b  ja      short def_18000E736; jumptable 000000018000E736 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000e71d  lea     rdx, __ImageBase
0x18000e724  movzx   eax, ds:(byte_18000EC78 - 180000000h)[rdx+rax]
0x18000e72c  mov     ecx, ds:(jpt_18000E736 - 180000000h)[rdx+rax*4]
0x18000e733  add     rcx, rdx
0x18000e736  jmp     rcx; switch jump
0x18000e738  mov     ebx, 80090027h; jumptable 000000018000E736 case 87
0x18000e73d  mov     eax, ebx
0x18000e73f  mov     rbx, [rsp+48h+arg_0]
0x18000e744  mov     rsi, [rsp+48h+arg_8]
0x18000e749  add     rsp, 40h
0x18000e74d  pop     rdi
0x18000e74e  retn
0x18000e74f  cmp     ebx, 0C000007Bh
0x18000e755  ja      loc_18000E919
0x18000e75b  jz      loc_18000EAE2
0x18000e761  cmp     ebx, 0C0000008h
0x18000e767  jz      loc_18000E993
0x18000e76d  ja      loc_18000EC10
0x18000e773  cmp     ebx, 800704C0h
0x18000e779  jz      loc_18000E9E5
0x18000e77f  cmp     ebx, 54Fh
0x18000e785  jz      loc_18000EA86
0x18000e78b  cmp     ebx, 800704C7h
0x18000e791  jz      loc_18000EA9D
0x18000e797  cmp     ebx, 80070578h
0x18000e79d  jnz     def_18000E736; jumptable 000000018000E736 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000e7a3  mov     ebx, 80070578h
0x18000e7a8  mov     eax, ebx
0x18000e7aa  mov     rbx, [rsp+48h+arg_0]
0x18000e7af  mov     rsi, [rsp+48h+arg_8]
0x18000e7b4  add     rsp, 40h
0x18000e7b8  pop     rdi
0x18000e7b9  retn
0x18000e7ba  mov     ebx, 80090026h
0x18000e7bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e7c6  lea     rax, WPP_GLOBAL_Control
0x18000e7cd  cmp     rcx, rax
0x18000e7d0  jz      def_18000E736; jumptable 000000018000E736 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000e7d6  test    byte ptr [rcx+1Ch], 1
0x18000e7da  jz      def_18000E736; jumptable 000000018000E736 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000e7e0  mov     rcx, [rcx+10h]
0x18000e7e4  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e7eb  mov     [rsp+48h+var_18], 77Dh
0x18000e7f3  lea     r9, aStatus; "Status"
0x18000e7fa  mov     [rsp+48h+var_20], r8
0x18000e7ff  mov     [rsp+48h+var_28], 80090026h
0x18000e807  call    WPP_SF_sDsd
0x18000e80c  mov     eax, ebx
0x18000e80e  mov     rbx, [rsp+48h+arg_0]
0x18000e813  mov     rsi, [rsp+48h+arg_8]
0x18000e818  add     rsp, 40h
0x18000e81c  pop     rdi
0x18000e81d  retn
0x18000e81e  sub     eax, 44444441h
0x18000e823  jnz     short loc_18000E86B
0x18000e825  cmp     dword ptr [rcx], 1B0h
0x18000e82b  jb      short loc_18000E836
0x18000e82d  cmp     [rcx+0Ch], eax
0x18000e830  jz      loc_18000EAF9
0x18000e836  mov     r9d, 771h
0x18000e83c  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e843  lea     rdx, aStatus; "Status"
0x18000e84a  mov     ecx, 80090026h
0x18000e84f  mov     ebx, 80090026h
0x18000e854  call    DebugTraceError
0x18000e859  mov     eax, ebx
0x18000e85b  mov     rbx, [rsp+48h+arg_0]
0x18000e860  mov     rsi, [rsp+48h+arg_8]
0x18000e865  add     rsp, 40h
0x18000e869  pop     rdi
0x18000e86a  retn
0x18000e86b  cmp     eax, 2
0x18000e86e  jnz     loc_18000EB6C
0x18000e874  cmp     dword ptr [rcx], 20h ; ' '
0x18000e877  jb      loc_18000EB08
0x18000e87d  mov     rsi, [rcx+18h]
0x18000e881  mov     rcx, [rcx+10h]
0x18000e885  mov     rax, [rsi+78h]
0x18000e889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e88e  mov     ebx, eax
0x18000e890  test    eax, eax
0x18000e892  js      loc_18000EBD0
0x18000e898  mov     ecx, [rdi]
0x18000e89a  mov     rax, rdi
0x18000e89d  test    rcx, rcx
0x18000e8a0  jz      short loc_18000E8AF
0x18000e8a2  mov     byte ptr [rax], 0
0x18000e8a5  lea     rax, [rax+1]
0x18000e8a9  sub     rcx, 1
0x18000e8ad  jnz     short loc_18000E8A2
0x18000e8af  mov     rcx, gs:60h
0x18000e8b8  mov     r8, rdi; P
0x18000e8bb  xor     edx, edx; Flags
0x18000e8bd  mov     rcx, [rcx+30h]; HeapHandle
0x18000e8c1  call    cs:__imp_RtlFreeHeap
0x18000e8c7  mov     eax, 0FFFFFFFFh
0x18000e8cc  lock xadd [rsi+10h], eax
0x18000e8d1  sub     eax, 1
0x18000e8d4  jg      loc_18000E6D8
0x18000e8da  cmp     dword ptr [rsi+0Ch], 0
0x18000e8de  jz      loc_18000E6D8
0x18000e8e4  mov     rcx, [rsi+1A8h]
0x18000e8eb  xor     edx, edx
0x18000e8ed  mov     rax, [rsi+78h]
0x18000e8f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8f6  mov     rcx, [rsi+18h]
0x18000e8fa  call    UnloadProvider
0x18000e8ff  mov     r8d, [rsi]; Size
0x18000e902  xor     edx, edx; Val
0x18000e904  mov     rcx, rsi; void *
0x18000e907  call    memset_0
0x18000e90c  mov     rcx, rsi
0x18000e90f  call    MSCryptFree
0x18000e914  jmp     loc_18000E6D8
0x18000e919  cmp     ebx, 0C0000135h
0x18000e91f  ja      loc_18000E9AA
0x18000e925  jz      loc_18000EACB
0x18000e92b  cmp     ebx, 0C00000BBh
0x18000e931  jnz     loc_18000EC39
0x18000e937  mov     ebx, 80090029h
0x18000e93c  mov     eax, ebx
0x18000e93e  mov     rbx, [rsp+48h+arg_0]
0x18000e943  mov     rsi, [rsp+48h+arg_8]
0x18000e948  add     rsp, 40h
0x18000e94c  pop     rdi
0x18000e94d  retn
0x18000e94e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e955  lea     rax, WPP_GLOBAL_Control
0x18000e95c  cmp     rcx, rax
0x18000e95f  jz      short loc_18000E993
0x18000e961  test    byte ptr [rcx+1Ch], 1
0x18000e965  jz      short loc_18000E993
0x18000e967  mov     rcx, [rcx+10h]
0x18000e96b  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e972  mov     [rsp+48h+var_18], 764h
0x18000e97a  lea     r9, aStatus; "Status"
0x18000e981  mov     [rsp+48h+var_20], r8
0x18000e986  mov     [rsp+48h+var_28], 0C0000008h
0x18000e98e  call    WPP_SF_sDsd
0x18000e993  mov     ebx, 80090026h
0x18000e998  mov     eax, ebx
0x18000e99a  mov     rbx, [rsp+48h+arg_0]
0x18000e99f  mov     rsi, [rsp+48h+arg_8]
0x18000e9a4  add     rsp, 40h
0x18000e9a8  pop     rdi
0x18000e9a9  retn
0x18000e9aa  cmp     ebx, 0C0000142h
0x18000e9b0  jz      loc_18000EAE2
0x18000e9b6  cmp     ebx, 0C0000139h
0x18000e9bc  jz      loc_18000EAE2
0x18000e9c2  cmp     ebx, 0C000A000h
0x18000e9c8  jnz     def_18000E736; jumptable 000000018000E736 default case, cases 4,6,7,9-13,15-86,88-111,113-121,123-182
0x18000e9ce  mov     ebx, 80090006h
0x18000e9d3  mov     eax, ebx
0x18000e9d5  mov     rbx, [rsp+48h+arg_0]
0x18000e9da  mov     rsi, [rsp+48h+arg_8]
0x18000e9df  add     rsp, 40h
0x18000e9e3  pop     rdi
0x18000e9e4  retn
0x18000e9e5  mov     ebx, 800704C0h
0x18000e9ea  mov     eax, ebx
0x18000e9ec  mov     rbx, [rsp+48h+arg_0]
0x18000e9f1  mov     rsi, [rsp+48h+arg_8]
0x18000e9f6  add     rsp, 40h
0x18000e9fa  pop     rdi
0x18000e9fb  retn
0x18000e9fc  mov     ebx, 80090028h; jumptable 000000018000E736 case 122
0x18000ea01  mov     eax, ebx
0x18000ea03  mov     rbx, [rsp+48h+arg_0]
0x18000ea08  mov     rsi, [rsp+48h+arg_8]
0x18000ea0d  add     rsp, 40h
0x18000ea11  pop     rdi
0x18000ea12  retn
0x18000ea13  mov     ebx, 80090011h; jumptable 000000018000E736 cases 2,3
0x18000ea18  mov     eax, ebx
0x18000ea1a  mov     rbx, [rsp+48h+arg_0]
0x18000ea1f  mov     rsi, [rsp+48h+arg_8]
0x18000ea24  add     rsp, 40h
0x18000ea28  pop     rdi
0x18000ea29  retn
0x18000ea2a  mov     ebx, 80070070h; jumptable 000000018000E736 case 112
0x18000ea2f  mov     eax, ebx
0x18000ea31  mov     rbx, [rsp+48h+arg_0]
0x18000ea36  mov     rsi, [rsp+48h+arg_8]
0x18000ea3b  add     rsp, 40h
0x18000ea3f  pop     rdi
0x18000ea40  retn
0x18000ea41  mov     ebx, 80070216h
0x18000ea46  mov     eax, ebx
0x18000ea48  mov     rbx, [rsp+48h+arg_0]
0x18000ea4d  mov     rsi, [rsp+48h+arg_8]
0x18000ea52  add     rsp, 40h
0x18000ea56  pop     rdi
0x18000ea57  retn
0x18000ea58  mov     ebx, 80090010h; jumptable 000000018000E736 case 5
0x18000ea5d  mov     eax, ebx
0x18000ea5f  mov     rbx, [rsp+48h+arg_0]
0x18000ea64  mov     rsi, [rsp+48h+arg_8]
0x18000ea69  add     rsp, 40h
0x18000ea6d  pop     rdi
0x18000ea6e  retn
0x18000ea6f  mov     ebx, 8009000Fh; jumptable 000000018000E736 case 183
0x18000ea74  mov     eax, ebx
0x18000ea76  mov     rbx, [rsp+48h+arg_0]
0x18000ea7b  mov     rsi, [rsp+48h+arg_8]
0x18000ea80  add     rsp, 40h
0x18000ea84  pop     rdi
0x18000ea85  retn
0x18000ea86  mov     ebx, 8009002Dh
0x18000ea8b  mov     eax, ebx
0x18000ea8d  mov     rbx, [rsp+48h+arg_0]
0x18000ea92  mov     rsi, [rsp+48h+arg_8]
0x18000ea97  add     rsp, 40h
0x18000ea9b  pop     rdi
0x18000ea9c  retn
0x18000ea9d  mov     ebx, 800704C7h
0x18000eaa2  mov     eax, ebx
0x18000eaa4  mov     rbx, [rsp+48h+arg_0]
0x18000eaa9  mov     rsi, [rsp+48h+arg_8]
0x18000eaae  add     rsp, 40h
0x18000eab2  pop     rdi
0x18000eab3  retn
0x18000eab4  mov     ebx, 8009000Eh; jumptable 000000018000E736 cases 8,14
0x18000eab9  mov     eax, ebx
0x18000eabb  mov     rbx, [rsp+48h+arg_0]
0x18000eac0  mov     rsi, [rsp+48h+arg_8]
0x18000eac5  add     rsp, 40h
0x18000eac9  pop     rdi
0x18000eaca  retn
0x18000eacb  mov     ebx, 8009001Eh
0x18000ead0  mov     eax, ebx
0x18000ead2  mov     rbx, [rsp+48h+arg_0]
0x18000ead7  mov     rsi, [rsp+48h+arg_8]
0x18000eadc  add     rsp, 40h
0x18000eae0  pop     rdi
0x18000eae1  retn
0x18000eae2  mov     ebx, 8009001Dh
0x18000eae7  mov     eax, ebx
0x18000eae9  mov     rbx, [rsp+48h+arg_0]
0x18000eaee  mov     rsi, [rsp+48h+arg_8]
0x18000eaf3  add     rsp, 40h
0x18000eaf7  pop     rdi
  ... truncated ...
```
