# IpcpConfigRejReceived

- ea: `0x18001ce60`
- end: `0x18001d1bf`
- name: `IpcpConfigRejReceived`
- size: `863`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001ce60`
- `0x180033010`

## string_xrefs

- `0x18001ce9f`: `IPCP: IpcpConfigRejReceived`
- `0x18001cf67`: `IPCP: IP compression was rejected`

## pseudocode

```c
__int64 __fastcall IpcpConfigRejReceived(_DWORD *a1, unsigned __int8 *a2)
{
  unsigned __int8 *v2; // rbp
  __int16 v4; // ax
  __int16 v5; // si
  __int64 v7; // rdx
  unsigned __int16 v8; // si
  __int64 v9; // r9
  __int64 v10; // rcx
  const wchar_t *v11; // r8

  v2 = a2 + 4;
  v4 = a2[3] - 4;
  v5 = a2[2] << 8;
  v7 = *((_QWORD *)&xmmword_18004C860 + 1);
  v8 = v4 + v5;
  if ( *((_QWORD *)&xmmword_18004C860 + 1) )
  {
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      *((_QWORD *)&xmmword_18004C860 + 1),
      L"IPCP: IpcpConfigRejReceived");
    v7 = *((_QWORD *)&xmmword_18004C860 + 1);
    if ( *((_QWORD *)&xmmword_18004C860 + 1) )
    {
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
        gRasIpcpEtwContext,
        *((_QWORD *)&xmmword_18004C860 + 1),
        L"IPCP: Rej received...");
      v7 = *((_QWORD *)&xmmword_18004C860 + 1);
    }
  }
  if ( qword_18004C880 )
  {
    if ( a2 )
      v9 = a2[3] + (a2[2] << 8);
    else
      v9 = 0;
    ((void (__fastcall *)(__int64, __int64, const wchar_t *, __int64, unsigned __int8 *))gRasIpcpByteTemplateFunc)(
      gRasIpcpEtwContext,
      qword_18004C880,
      L"DumpingBytes Rej received",
      v9,
      a2);
    v7 = *((_QWORD *)&xmmword_18004C860 + 1);
  }
  a1[23] = 0;
  while ( 1 )
  {
    if ( v8 < 2u )
      return 0;
    if ( v8 < v2[1] )
      return 722;
    if ( *v2 == 2 )
    {
      if ( v7 )
      {
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(
          gRasIpcpEtwContext,
          v7,
          L"IPCP: IP compression was rejected");
        v7 = *((_QWORD *)&xmmword_18004C860 + 1);
      }
      a1[8] = 1;
      a1[44] = 0;
      goto LABEL_48;
    }
    if ( !*a1 || a1[522] == 2 )
      break;
    if ( *v2 == 3 )
    {
      if ( v7 )
      {
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(
          gRasIpcpEtwContext,
          v7,
          L"IPCP: Server IP address was rejected");
        v7 = *((_QWORD *)&xmmword_18004C860 + 1);
      }
LABEL_45:
      a1[9] = 1;
      goto LABEL_48;
    }
    if ( (_QWORD)xmmword_18004C860 )
    {
      v7 = xmmword_18004C860;
LABEL_29:
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(
        gRasIpcpEtwContext,
        v7,
        L"IPCP: Unrequested option rejected?");
      v7 = *((_QWORD *)&xmmword_18004C860 + 1);
    }
LABEL_48:
    v10 = v2[1];
    if ( (_BYTE)v10 && (unsigned __int16)v10 <= v8 )
    {
      v8 -= v10;
    }
    else
    {
      if ( !a1[14] )
      {
        if ( v7 )
        {
          v11 = L"IPCP: Tossing MS options (length)";
          goto LABEL_56;
        }
        goto LABEL_57;
      }
      v8 = 0;
    }
    v2 += v10;
  }
  if ( *v2 != 3 )
  {
    switch ( *v2 )
    {
      case 0x81u:
        if ( v7 )
        {
          ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(
            gRasIpcpEtwContext,
            v7,
            L"IPCP: DNS was rejected");
          v7 = *((_QWORD *)&xmmword_18004C860 + 1);
        }
        a1[10] = 1;
        break;
      case 0x82u:
        if ( v7 )
        {
          ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(
            gRasIpcpEtwContext,
            v7,
            L"IPCP: WINS was rejected");
          v7 = *((_QWORD *)&xmmword_18004C860 + 1);
        }
        a1[11] = 1;
        break;
      case 0x83u:
        if ( v7 )
        {
          ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(
            gRasIpcpEtwContext,
            v7,
            L"IPCP: DNS backup was rejected");
          v7 = *((_QWORD *)&xmmword_18004C860 + 1);
        }
        a1[12] = 1;
        break;
      case 0x84u:
        if ( v7 )
        {
          ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(
            gRasIpcpEtwContext,
            v7,
            L"IPCP: WINS backup was rejected");
          v7 = *((_QWORD *)&xmmword_18004C860 + 1);
        }
        a1[13] = 1;
        break;
      default:
        if ( v7 )
          goto LABEL_29;
        break;
    }
    goto LABEL_48;
  }
  if ( (_QWORD)xmmword_18004C860 )
  {
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      xmmword_18004C860,
      L"IPCP: IP was rejected");
    v7 = *((_QWORD *)&xmmword_18004C860 + 1);
  }
  if ( a1[36] )
    goto LABEL_45;
  if ( a1[522] == 2 )
  {
    a1[15] = 1;
    goto LABEL_48;
  }
  if ( !a1[14] )
  {
    if ( v7 )
    {
      v11 = L"IPCP: Tossing MS options (no address)";
LABEL_56:
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(gRasIpcpEtwContext, v7, v11);
    }
LABEL_57:
    a1[14] = 1;
    a1[10] = 1;
    a1[11] = 1;
    a1[12] = 1;
    a1[13] = 1;
    return 0;
  }
  return 738;
}

```

## disassembly

```asm
0x18001ce60  push    rbx
0x18001ce62  push    rbp
0x18001ce63  push    rsi
0x18001ce64  push    rdi
0x18001ce65  push    r15
0x18001ce67  sub     rsp, 30h
0x18001ce6b  movzx   esi, byte ptr [rdx+2]
0x18001ce6f  lea     rbp, [rdx+4]
0x18001ce73  movzx   eax, byte ptr [rdx+3]
0x18001ce77  mov     rbx, rcx
0x18001ce7a  sub     ax, 4
0x18001ce7e  mov     ecx, 100h
0x18001ce83  imul    esi, ecx
0x18001ce86  mov     rdi, rdx
0x18001ce89  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001ce90  add     si, ax
0x18001ce93  test    rdx, rdx
0x18001ce96  jz      short loc_18001CEDF
0x18001ce98  mov     rcx, cs:gRasIpcpEtwContext
0x18001ce9f  lea     r8, aIpcpIpcpconfig_1; "IPCP: IpcpConfigRejReceived"
0x18001cea6  mov     rax, cs:gRasIpcpTemplateFunc
0x18001cead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ceb2  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001ceb9  test    rdx, rdx
0x18001cebc  jz      short loc_18001CEDF
0x18001cebe  mov     rcx, cs:gRasIpcpEtwContext
0x18001cec5  lea     r8, aIpcpRejReceive; "IPCP: Rej received..."
0x18001cecc  mov     rax, cs:gRasIpcpTemplateFunc
0x18001ced3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ced8  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001cedf  mov     rcx, cs:qword_18004C880
0x18001cee6  test    rcx, rcx
0x18001cee9  jz      short loc_18001CF2E
0x18001ceeb  test    rdi, rdi
0x18001ceee  jz      short loc_18001CF02
0x18001cef0  movzx   r9d, byte ptr [rdi+2]
0x18001cef5  movzx   eax, byte ptr [rdi+3]
0x18001cef9  shl     r9d, 8
0x18001cefd  add     r9d, eax
0x18001cf00  jmp     short loc_18001CF05
0x18001cf02  xor     r9d, r9d
0x18001cf05  mov     rax, cs:gRasIpcpByteTemplateFunc
0x18001cf0c  lea     r8, aDumpingbytesRe; "DumpingBytes Rej received"
0x18001cf13  mov     rdx, rcx
0x18001cf16  mov     [rsp+58h+var_38], rdi
0x18001cf1b  mov     rcx, cs:gRasIpcpEtwContext
0x18001cf22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf27  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001cf2e  mov     edi, 1
0x18001cf33  mov     dword ptr [rbx+5Ch], 0
0x18001cf3a  lea     r15d, [rdi+1]
0x18001cf3e  cmp     si, r15w
0x18001cf42  jb      loc_18001D190
0x18001cf48  movzx   eax, byte ptr [rbp+1]
0x18001cf4c  cmp     si, ax
0x18001cf4f  jb      loc_18001D1B8
0x18001cf55  cmp     [rbp+0], r15b
0x18001cf59  jnz     short loc_18001CF91
0x18001cf5b  test    rdx, rdx
0x18001cf5e  jz      short loc_18001CF81
0x18001cf60  mov     rcx, cs:gRasIpcpEtwContext
0x18001cf67  lea     r8, aIpcpIpCompress; "IPCP: IP compression was rejected"
0x18001cf6e  mov     rax, cs:gRasIpcpTemplateFunc
0x18001cf75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf7a  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001cf81  xor     eax, eax
0x18001cf83  mov     [rbx+20h], edi
0x18001cf86  mov     [rbx+0B0h], eax
0x18001cf8c  jmp     loc_18001D13A
0x18001cf91  cmp     dword ptr [rbx], 0
0x18001cf94  jz      short loc_18001CFE9
0x18001cf96  cmp     [rbx+828h], r15d
0x18001cf9d  jz      short loc_18001CFE9
0x18001cf9f  cmp     byte ptr [rbp+0], 3
0x18001cfa3  jz      short loc_18001CFBA
0x18001cfa5  mov     rax, qword ptr cs:xmmword_18004C860
0x18001cfac  test    rax, rax
0x18001cfaf  jz      loc_18001D13A
0x18001cfb5  mov     rdx, rax
0x18001cfb8  jmp     short loc_18001D018
0x18001cfba  test    rdx, rdx
0x18001cfbd  jz      loc_18001D129
0x18001cfc3  mov     rcx, cs:gRasIpcpEtwContext
0x18001cfca  lea     r8, aIpcpServerIpAd; "IPCP: Server IP address was rejected"
0x18001cfd1  mov     rax, cs:gRasIpcpTemplateFunc
0x18001cfd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cfdd  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001cfe4  jmp     loc_18001D129
0x18001cfe9  movzx   ecx, byte ptr [rbp+0]
0x18001cfed  sub     ecx, 3
0x18001cff0  jz      loc_18001D0F0
0x18001cff6  sub     ecx, 7Eh ; '~'
0x18001cff9  jz      loc_18001D0C5
0x18001cfff  sub     ecx, edi
0x18001d001  jz      loc_18001D09A
0x18001d007  sub     ecx, edi
0x18001d009  jz      short loc_18001D06C
0x18001d00b  cmp     ecx, edi
0x18001d00d  jz      short loc_18001D03E
0x18001d00f  test    rdx, rdx
0x18001d012  jz      loc_18001D13A
0x18001d018  mov     rcx, cs:gRasIpcpEtwContext
0x18001d01f  lea     r8, aIpcpUnrequeste; "IPCP: Unrequested option rejected?"
0x18001d026  mov     rax, cs:gRasIpcpTemplateFunc
0x18001d02d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d032  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001d039  jmp     loc_18001D13A
0x18001d03e  test    rdx, rdx
0x18001d041  jz      short loc_18001D064
0x18001d043  mov     rcx, cs:gRasIpcpEtwContext
0x18001d04a  lea     r8, aIpcpWinsBackup; "IPCP: WINS backup was rejected"
0x18001d051  mov     rax, cs:gRasIpcpTemplateFunc
0x18001d058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d05d  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001d064  mov     [rbx+34h], edi
0x18001d067  jmp     loc_18001D13A
0x18001d06c  test    rdx, rdx
0x18001d06f  jz      short loc_18001D092
0x18001d071  mov     rcx, cs:gRasIpcpEtwContext
0x18001d078  lea     r8, aIpcpDnsBackupW; "IPCP: DNS backup was rejected"
0x18001d07f  mov     rax, cs:gRasIpcpTemplateFunc
0x18001d086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d08b  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001d092  mov     [rbx+30h], edi
0x18001d095  jmp     loc_18001D13A
0x18001d09a  test    rdx, rdx
0x18001d09d  jz      short loc_18001D0C0
0x18001d09f  mov     rcx, cs:gRasIpcpEtwContext
0x18001d0a6  lea     r8, aIpcpWinsWasRej; "IPCP: WINS was rejected"
0x18001d0ad  mov     rax, cs:gRasIpcpTemplateFunc
0x18001d0b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0b9  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001d0c0  mov     [rbx+2Ch], edi
0x18001d0c3  jmp     short loc_18001D13A
0x18001d0c5  test    rdx, rdx
0x18001d0c8  jz      short loc_18001D0EB
0x18001d0ca  mov     rcx, cs:gRasIpcpEtwContext
0x18001d0d1  lea     r8, aIpcpDnsWasReje; "IPCP: DNS was rejected"
0x18001d0d8  mov     rax, cs:gRasIpcpTemplateFunc
0x18001d0df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0e4  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001d0eb  mov     [rbx+28h], edi
0x18001d0ee  jmp     short loc_18001D13A
0x18001d0f0  mov     rax, qword ptr cs:xmmword_18004C860
0x18001d0f7  test    rax, rax
0x18001d0fa  jz      short loc_18001D120
0x18001d0fc  mov     rcx, cs:gRasIpcpEtwContext
0x18001d103  lea     r8, aIpcpIpWasRejec; "IPCP: IP was rejected"
0x18001d10a  mov     rdx, rax
0x18001d10d  mov     rax, cs:gRasIpcpTemplateFunc
0x18001d114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d119  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001d120  cmp     dword ptr [rbx+90h], 0
0x18001d127  jz      short loc_18001D12E
0x18001d129  mov     [rbx+24h], edi
0x18001d12c  jmp     short loc_18001D13A
0x18001d12e  cmp     [rbx+828h], r15d
0x18001d135  jnz     short loc_18001D19D
0x18001d137  mov     [rbx+3Ch], edi
0x18001d13a  movzx   ecx, byte ptr [rbp+1]
0x18001d13e  test    cl, cl
0x18001d140  jz      short loc_18001D14F
0x18001d142  movzx   eax, cx
0x18001d145  cmp     cx, si
0x18001d148  ja      short loc_18001D14F
0x18001d14a  sub     si, ax
0x18001d14d  jmp     short loc_18001D15A
0x18001d14f  cmp     dword ptr [rbx+38h], 0
0x18001d153  jz      short loc_18001D162
0x18001d155  xor     eax, eax
0x18001d157  movzx   esi, ax
0x18001d15a  add     rbp, rcx
0x18001d15d  jmp     loc_18001CF3E
0x18001d162  test    rdx, rdx
0x18001d165  jz      short loc_18001D181
0x18001d167  lea     r8, aIpcpTossingMsO_0; "IPCP: Tossing MS options (length)"
0x18001d16e  mov     rcx, cs:gRasIpcpEtwContext
0x18001d175  mov     rax, cs:gRasIpcpTemplateFunc
0x18001d17c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d181  mov     [rbx+38h], edi
0x18001d184  mov     [rbx+28h], edi
0x18001d187  mov     [rbx+2Ch], edi
0x18001d18a  mov     [rbx+30h], edi
0x18001d18d  mov     [rbx+34h], edi
0x18001d190  xor     eax, eax
0x18001d192  add     rsp, 30h
0x18001d196  pop     r15
0x18001d198  pop     rdi
0x18001d199  pop     rsi
0x18001d19a  pop     rbp
0x18001d19b  pop     rbx
0x18001d19c  retn
0x18001d19d  cmp     dword ptr [rbx+38h], 0
0x18001d1a1  jz      short loc_18001D1AA
0x18001d1a3  mov     eax, 2E2h
0x18001d1a8  jmp     short loc_18001D192
0x18001d1aa  test    rdx, rdx
0x18001d1ad  jz      short loc_18001D181
0x18001d1af  lea     r8, aIpcpTossingMsO_1; "IPCP: Tossing MS options (no address)"
0x18001d1b6  jmp     short loc_18001D16E
0x18001d1b8  mov     eax, 2D2h
0x18001d1bd  jmp     short loc_18001D192
```
