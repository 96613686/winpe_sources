# IpcpConfigRejReceived

- ea: `0x18001d940`
- end: `0x18001dca0`
- name: `IpcpConfigRejReceived`
- size: `864`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001d940`
- `0x180034010`

## string_xrefs

- `0x18001d97f`: `IPCP: IpcpConfigRejReceived`
- `0x18001da47`: `IPCP: IP compression was rejected`

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
  v7 = *((_QWORD *)&xmmword_18004D860 + 1);
  v8 = v4 + v5;
  if ( *((_QWORD *)&xmmword_18004D860 + 1) )
  {
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      *((_QWORD *)&xmmword_18004D860 + 1),
      L"IPCP: IpcpConfigRejReceived");
    v7 = *((_QWORD *)&xmmword_18004D860 + 1);
    if ( *((_QWORD *)&xmmword_18004D860 + 1) )
    {
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
        gRasIpcpEtwContext,
        *((_QWORD *)&xmmword_18004D860 + 1),
        L"IPCP: Rej received...");
      v7 = *((_QWORD *)&xmmword_18004D860 + 1);
    }
  }
  if ( qword_18004D880 )
  {
    if ( a2 )
      v9 = a2[3] + (a2[2] << 8);
    else
      v9 = 0;
    ((void (__fastcall *)(__int64, __int64, const wchar_t *, __int64, unsigned __int8 *))gRasIpcpByteTemplateFunc)(
      gRasIpcpEtwContext,
      qword_18004D880,
      L"DumpingBytes Rej received",
      v9,
      a2);
    v7 = *((_QWORD *)&xmmword_18004D860 + 1);
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
        v7 = *((_QWORD *)&xmmword_18004D860 + 1);
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
        v7 = *((_QWORD *)&xmmword_18004D860 + 1);
      }
LABEL_45:
      a1[9] = 1;
      goto LABEL_48;
    }
    if ( (_QWORD)xmmword_18004D860 )
    {
      v7 = xmmword_18004D860;
LABEL_29:
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(
        gRasIpcpEtwContext,
        v7,
        L"IPCP: Unrequested option rejected?");
      v7 = *((_QWORD *)&xmmword_18004D860 + 1);
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
          v7 = *((_QWORD *)&xmmword_18004D860 + 1);
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
          v7 = *((_QWORD *)&xmmword_18004D860 + 1);
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
          v7 = *((_QWORD *)&xmmword_18004D860 + 1);
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
          v7 = *((_QWORD *)&xmmword_18004D860 + 1);
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
  if ( (_QWORD)xmmword_18004D860 )
  {
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      xmmword_18004D860,
      L"IPCP: IP was rejected");
    v7 = *((_QWORD *)&xmmword_18004D860 + 1);
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
0x18001d940  push    rbx
0x18001d942  push    rbp
0x18001d943  push    rsi
0x18001d944  push    rdi
0x18001d945  push    r15
0x18001d947  sub     rsp, 30h
0x18001d94b  movzx   esi, byte ptr [rdx+2]
0x18001d94f  lea     rbp, [rdx+4]
0x18001d953  movzx   eax, byte ptr [rdx+3]
0x18001d957  mov     rbx, rcx
0x18001d95a  sub     ax, 4
0x18001d95e  mov     ecx, 100h
0x18001d963  imul    esi, ecx
0x18001d966  mov     rdi, rdx
0x18001d969  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001d970  add     si, ax
0x18001d973  test    rdx, rdx
0x18001d976  jz      short loc_18001D9BF
0x18001d978  mov     rcx, cs:gRasIpcpEtwContext
0x18001d97f  lea     r8, aIpcpIpcpconfig_1; "IPCP: IpcpConfigRejReceived"
0x18001d986  mov     rax, cs:gRasIpcpTemplateFunc
0x18001d98d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d992  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001d999  test    rdx, rdx
0x18001d99c  jz      short loc_18001D9BF
0x18001d99e  mov     rcx, cs:gRasIpcpEtwContext
0x18001d9a5  lea     r8, aIpcpRejReceive; "IPCP: Rej received..."
0x18001d9ac  mov     rax, cs:gRasIpcpTemplateFunc
0x18001d9b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9b8  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001d9bf  mov     rcx, cs:qword_18004D880
0x18001d9c6  test    rcx, rcx
0x18001d9c9  jz      short loc_18001DA0E
0x18001d9cb  test    rdi, rdi
0x18001d9ce  jz      short loc_18001D9E2
0x18001d9d0  movzx   r9d, byte ptr [rdi+2]
0x18001d9d5  movzx   eax, byte ptr [rdi+3]
0x18001d9d9  shl     r9d, 8
0x18001d9dd  add     r9d, eax
0x18001d9e0  jmp     short loc_18001D9E5
0x18001d9e2  xor     r9d, r9d
0x18001d9e5  mov     rax, cs:gRasIpcpByteTemplateFunc
0x18001d9ec  lea     r8, aDumpingbytesRe; "DumpingBytes Rej received"
0x18001d9f3  mov     rdx, rcx
0x18001d9f6  mov     [rsp+58h+var_38], rdi
0x18001d9fb  mov     rcx, cs:gRasIpcpEtwContext
0x18001da02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da07  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001da0e  mov     edi, 1
0x18001da13  mov     dword ptr [rbx+5Ch], 0
0x18001da1a  lea     r15d, [rdi+1]
0x18001da1e  cmp     si, r15w
0x18001da22  jb      loc_18001DC70
0x18001da28  movzx   eax, byte ptr [rbp+1]
0x18001da2c  cmp     si, ax
0x18001da2f  jb      loc_18001DC99
0x18001da35  cmp     [rbp+0], r15b
0x18001da39  jnz     short loc_18001DA71
0x18001da3b  test    rdx, rdx
0x18001da3e  jz      short loc_18001DA61
0x18001da40  mov     rcx, cs:gRasIpcpEtwContext
0x18001da47  lea     r8, aIpcpIpCompress; "IPCP: IP compression was rejected"
0x18001da4e  mov     rax, cs:gRasIpcpTemplateFunc
0x18001da55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da5a  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001da61  xor     eax, eax
0x18001da63  mov     [rbx+20h], edi
0x18001da66  mov     [rbx+0B0h], eax
0x18001da6c  jmp     loc_18001DC1A
0x18001da71  cmp     dword ptr [rbx], 0
0x18001da74  jz      short loc_18001DAC9
0x18001da76  cmp     [rbx+828h], r15d
0x18001da7d  jz      short loc_18001DAC9
0x18001da7f  cmp     byte ptr [rbp+0], 3
0x18001da83  jz      short loc_18001DA9A
0x18001da85  mov     rax, qword ptr cs:xmmword_18004D860
0x18001da8c  test    rax, rax
0x18001da8f  jz      loc_18001DC1A
0x18001da95  mov     rdx, rax
0x18001da98  jmp     short loc_18001DAF8
0x18001da9a  test    rdx, rdx
0x18001da9d  jz      loc_18001DC09
0x18001daa3  mov     rcx, cs:gRasIpcpEtwContext
0x18001daaa  lea     r8, aIpcpServerIpAd; "IPCP: Server IP address was rejected"
0x18001dab1  mov     rax, cs:gRasIpcpTemplateFunc
0x18001dab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dabd  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001dac4  jmp     loc_18001DC09
0x18001dac9  movzx   ecx, byte ptr [rbp+0]
0x18001dacd  sub     ecx, 3
0x18001dad0  jz      loc_18001DBD0
0x18001dad6  sub     ecx, 7Eh ; '~'
0x18001dad9  jz      loc_18001DBA5
0x18001dadf  sub     ecx, edi
0x18001dae1  jz      loc_18001DB7A
0x18001dae7  sub     ecx, edi
0x18001dae9  jz      short loc_18001DB4C
0x18001daeb  cmp     ecx, edi
0x18001daed  jz      short loc_18001DB1E
0x18001daef  test    rdx, rdx
0x18001daf2  jz      loc_18001DC1A
0x18001daf8  mov     rcx, cs:gRasIpcpEtwContext
0x18001daff  lea     r8, aIpcpUnrequeste; "IPCP: Unrequested option rejected?"
0x18001db06  mov     rax, cs:gRasIpcpTemplateFunc
0x18001db0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db12  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001db19  jmp     loc_18001DC1A
0x18001db1e  test    rdx, rdx
0x18001db21  jz      short loc_18001DB44
0x18001db23  mov     rcx, cs:gRasIpcpEtwContext
0x18001db2a  lea     r8, aIpcpWinsBackup; "IPCP: WINS backup was rejected"
0x18001db31  mov     rax, cs:gRasIpcpTemplateFunc
0x18001db38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db3d  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001db44  mov     [rbx+34h], edi
0x18001db47  jmp     loc_18001DC1A
0x18001db4c  test    rdx, rdx
0x18001db4f  jz      short loc_18001DB72
0x18001db51  mov     rcx, cs:gRasIpcpEtwContext
0x18001db58  lea     r8, aIpcpDnsBackupW; "IPCP: DNS backup was rejected"
0x18001db5f  mov     rax, cs:gRasIpcpTemplateFunc
0x18001db66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db6b  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001db72  mov     [rbx+30h], edi
0x18001db75  jmp     loc_18001DC1A
0x18001db7a  test    rdx, rdx
0x18001db7d  jz      short loc_18001DBA0
0x18001db7f  mov     rcx, cs:gRasIpcpEtwContext
0x18001db86  lea     r8, aIpcpWinsWasRej; "IPCP: WINS was rejected"
0x18001db8d  mov     rax, cs:gRasIpcpTemplateFunc
0x18001db94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db99  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001dba0  mov     [rbx+2Ch], edi
0x18001dba3  jmp     short loc_18001DC1A
0x18001dba5  test    rdx, rdx
0x18001dba8  jz      short loc_18001DBCB
0x18001dbaa  mov     rcx, cs:gRasIpcpEtwContext
0x18001dbb1  lea     r8, aIpcpDnsWasReje; "IPCP: DNS was rejected"
0x18001dbb8  mov     rax, cs:gRasIpcpTemplateFunc
0x18001dbbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbc4  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001dbcb  mov     [rbx+28h], edi
0x18001dbce  jmp     short loc_18001DC1A
0x18001dbd0  mov     rax, qword ptr cs:xmmword_18004D860
0x18001dbd7  test    rax, rax
0x18001dbda  jz      short loc_18001DC00
0x18001dbdc  mov     rcx, cs:gRasIpcpEtwContext
0x18001dbe3  lea     r8, aIpcpIpWasRejec; "IPCP: IP was rejected"
0x18001dbea  mov     rdx, rax
0x18001dbed  mov     rax, cs:gRasIpcpTemplateFunc
0x18001dbf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbf9  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001dc00  cmp     dword ptr [rbx+90h], 0
0x18001dc07  jz      short loc_18001DC0E
0x18001dc09  mov     [rbx+24h], edi
0x18001dc0c  jmp     short loc_18001DC1A
0x18001dc0e  cmp     [rbx+828h], r15d
0x18001dc15  jnz     short loc_18001DC7E
0x18001dc17  mov     [rbx+3Ch], edi
0x18001dc1a  movzx   ecx, byte ptr [rbp+1]
0x18001dc1e  test    cl, cl
0x18001dc20  jz      short loc_18001DC2F
0x18001dc22  movzx   eax, cx
0x18001dc25  cmp     cx, si
0x18001dc28  ja      short loc_18001DC2F
0x18001dc2a  sub     si, ax
0x18001dc2d  jmp     short loc_18001DC3A
0x18001dc2f  cmp     dword ptr [rbx+38h], 0
0x18001dc33  jz      short loc_18001DC42
0x18001dc35  xor     eax, eax
0x18001dc37  movzx   esi, ax
0x18001dc3a  add     rbp, rcx
0x18001dc3d  jmp     loc_18001DA1E
0x18001dc42  test    rdx, rdx
0x18001dc45  jz      short loc_18001DC61
0x18001dc47  lea     r8, aIpcpTossingMsO_0; "IPCP: Tossing MS options (length)"
0x18001dc4e  mov     rcx, cs:gRasIpcpEtwContext
0x18001dc55  mov     rax, cs:gRasIpcpTemplateFunc
0x18001dc5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc61  mov     [rbx+38h], edi
0x18001dc64  mov     [rbx+28h], edi
0x18001dc67  mov     [rbx+2Ch], edi
0x18001dc6a  mov     [rbx+30h], edi
0x18001dc6d  mov     [rbx+34h], edi
0x18001dc70  xor     eax, eax
0x18001dc72  add     rsp, 30h
0x18001dc76  pop     r15
0x18001dc78  pop     rdi
0x18001dc79  pop     rsi
0x18001dc7a  pop     rbp
0x18001dc7b  pop     rbx
0x18001dc7c  retn
0x18001dc7e  cmp     dword ptr [rbx+38h], 0
0x18001dc82  jz      short loc_18001DC8B
0x18001dc84  mov     eax, 2E2h
0x18001dc89  jmp     short loc_18001DC72
0x18001dc8b  test    rdx, rdx
0x18001dc8e  jz      short loc_18001DC61
0x18001dc90  lea     r8, aIpcpTossingMsO_1; "IPCP: Tossing MS options (no address)"
0x18001dc97  jmp     short loc_18001DC4E
0x18001dc99  mov     eax, 2D2h
0x18001dc9e  jmp     short loc_18001DC72
```
