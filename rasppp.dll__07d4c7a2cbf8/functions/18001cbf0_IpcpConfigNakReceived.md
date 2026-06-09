# IpcpConfigNakReceived

- ea: `0x18001cbf0`
- end: `0x18001ce54`
- name: `IpcpConfigNakReceived`
- size: `612`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18001cbf0`
- `0x180033010`

## string_xrefs

- `0x18001cc33`: `IPCP: IpcpConfigNakReceived`

## pseudocode

```c
__int64 __fastcall IpcpConfigNakReceived(__int64 a1, unsigned __int8 *a2)
{
  unsigned __int8 *v2; // rdi
  unsigned __int16 v5; // bp
  __int64 v6; // r9
  __int64 v7; // r9
  unsigned __int16 v8; // dx
  unsigned __int8 v9; // al
  int v10; // eax
  __int64 v11; // rcx

  v2 = a2 + 4;
  v5 = a2[3] - 4 + (a2[2] << 8);
  if ( *((_QWORD *)&xmmword_18004C860 + 1) )
  {
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      *((_QWORD *)&xmmword_18004C860 + 1),
      L"IPCP: IpcpConfigNakReceived");
    if ( *((_QWORD *)&xmmword_18004C860 + 1) )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
        gRasIpcpEtwContext,
        *((_QWORD *)&xmmword_18004C860 + 1),
        L"IPCP: Nak received...");
  }
  if ( qword_18004C880 )
  {
    if ( a2 )
      v6 = a2[3] + (a2[2] << 8);
    else
      v6 = 0;
    ((void (__fastcall *)(__int64, __int64, const wchar_t *, __int64, unsigned __int8 *))gRasIpcpByteTemplateFunc)(
      gRasIpcpEtwContext,
      qword_18004C880,
      L"DumpingBytes Nak ",
      v6,
      a2);
  }
  v7 = xmmword_18004C860;
  *(_DWORD *)(a1 + 92) = 0;
  while ( v5 >= 2u )
  {
    v8 = v2[1];
    if ( v5 < v8 )
      return 722;
    if ( *v2 == 2 )
    {
      if ( (_BYTE)v8 != 6 )
        return 722;
      if ( (v2[2] << 8) + v2[3] == 45 )
      {
        v9 = v2[4];
        if ( v9 <= *(_BYTE *)(a1 + 178) )
          *(_BYTE *)(a1 + 178) = v9;
        if ( *(_BYTE *)(a1 + 179) )
          *(_BYTE *)(a1 + 179) = v2[5];
      }
    }
    else if ( !*(_DWORD *)a1 || *(_DWORD *)(a1 + 2088) == 2 )
    {
      switch ( *v2 )
      {
        case 3u:
          if ( (_BYTE)v8 != 6 )
            return 722;
          v10 = *(_DWORD *)(v2 + 2);
          if ( !v10 )
          {
            if ( !*(_DWORD *)(a1 + 144) )
              return 738;
            return 735;
          }
          if ( *(_DWORD *)(a1 + 144) )
            return 735;
          *(_DWORD *)(a1 + 144) = v10;
          break;
        case 0x81u:
          if ( (_BYTE)v8 != 6 )
            return 722;
          if ( !*(_DWORD *)(a1 + 40) )
            *(_DWORD *)(a1 + 104) = *(_DWORD *)(v2 + 2);
          break;
        case 0x82u:
          if ( (_BYTE)v8 != 6 )
            return 722;
          if ( !*(_DWORD *)(a1 + 44) )
            *(_DWORD *)(a1 + 96) = *(_DWORD *)(v2 + 2);
          break;
        case 0x83u:
          if ( (_BYTE)v8 != 6 )
            return 722;
          if ( !*(_DWORD *)(a1 + 48) )
            *(_DWORD *)(a1 + 108) = *(_DWORD *)(v2 + 2);
          break;
        case 0x84u:
          if ( (_BYTE)v8 != 6 )
            return 722;
          if ( !*(_DWORD *)(a1 + 52) )
            *(_DWORD *)(a1 + 100) = *(_DWORD *)(v2 + 2);
          break;
        default:
          if ( v7 )
          {
            ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(
              gRasIpcpEtwContext,
              v7,
              L"IPCP: Unrequested option NAKed?");
            v7 = xmmword_18004C860;
          }
          break;
      }
    }
    v11 = v2[1];
    if ( (_BYTE)v11 && (unsigned __int16)v11 < v5 )
      v5 -= v11;
    else
      v5 = 0;
    v2 += v11;
  }
  return 0;
}

```

## disassembly

```asm
0x18001cbf0  push    rbx
0x18001cbf2  push    rbp
0x18001cbf3  push    rsi
0x18001cbf4  push    rdi
0x18001cbf5  push    r12
0x18001cbf7  push    r15
0x18001cbf9  sub     rsp, 38h
0x18001cbfd  movzx   ebp, byte ptr [rdx+2]
0x18001cc01  lea     rdi, [rdx+4]
0x18001cc05  movzx   eax, byte ptr [rdx+3]
0x18001cc09  mov     r12d, 100h
0x18001cc0f  imul    ebp, r12d
0x18001cc13  sub     ax, 4
0x18001cc17  mov     rsi, rdx
0x18001cc1a  mov     rbx, rcx
0x18001cc1d  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001cc24  add     bp, ax
0x18001cc27  test    rdx, rdx
0x18001cc2a  jz      short loc_18001CC6C
0x18001cc2c  mov     rcx, cs:gRasIpcpEtwContext
0x18001cc33  lea     r8, aIpcpIpcpconfig_0; "IPCP: IpcpConfigNakReceived"
0x18001cc3a  mov     rax, cs:gRasIpcpTemplateFunc
0x18001cc41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc46  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001cc4d  test    rdx, rdx
0x18001cc50  jz      short loc_18001CC6C
0x18001cc52  mov     rcx, cs:gRasIpcpEtwContext
0x18001cc59  lea     r8, aIpcpNakReceive; "IPCP: Nak received..."
0x18001cc60  mov     rax, cs:gRasIpcpTemplateFunc
0x18001cc67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc6c  mov     rdx, cs:qword_18004C880
0x18001cc73  test    rdx, rdx
0x18001cc76  jz      short loc_18001CCB1
0x18001cc78  test    rsi, rsi
0x18001cc7b  jz      short loc_18001CC8F
0x18001cc7d  movzx   r9d, byte ptr [rsi+2]
0x18001cc82  movzx   eax, byte ptr [rsi+3]
0x18001cc86  shl     r9d, 8
0x18001cc8a  add     r9d, eax
0x18001cc8d  jmp     short loc_18001CC92
0x18001cc8f  xor     r9d, r9d
0x18001cc92  mov     rcx, cs:gRasIpcpEtwContext
0x18001cc99  lea     r8, aDumpingbytesNa; "DumpingBytes Nak "
0x18001cca0  mov     rax, cs:gRasIpcpByteTemplateFunc
0x18001cca7  mov     [rsp+68h+var_48], rsi
0x18001ccac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ccb1  mov     r9, qword ptr cs:xmmword_18004C860
0x18001ccb8  mov     r15d, 2
0x18001ccbe  mov     dword ptr [rbx+5Ch], 0
0x18001ccc5  mov     sil, 6
0x18001ccc8  cmp     bp, r15w
0x18001cccc  jb      loc_18001CE45
0x18001ccd2  movzx   edx, byte ptr [rdi+1]
0x18001ccd6  cmp     bp, dx
0x18001ccd9  jb      loc_18001CE3E
0x18001ccdf  cmp     [rdi], r15b
0x18001cce2  jnz     short loc_18001CD35
0x18001cce4  cmp     dl, sil
0x18001cce7  jnz     loc_18001CE3E
0x18001cced  movzx   edx, byte ptr [rdi+2]
0x18001ccf1  movzx   r8d, byte ptr [rdi+3]
0x18001ccf6  imul    edx, r12d
0x18001ccfa  add     r8w, dx
0x18001ccfe  cmp     r8w, 2Dh ; '-'
0x18001cd03  jnz     loc_18001CE05
0x18001cd09  mov     al, [rdi+4]
0x18001cd0c  cmp     al, [rbx+0B2h]
0x18001cd12  ja      short loc_18001CD1A
0x18001cd14  mov     [rbx+0B2h], al
0x18001cd1a  cmp     byte ptr [rbx+0B3h], 0
0x18001cd21  jz      loc_18001CE05
0x18001cd27  mov     al, [rdi+5]
0x18001cd2a  mov     [rbx+0B3h], al
0x18001cd30  jmp     loc_18001CE05
0x18001cd35  cmp     dword ptr [rbx], 0
0x18001cd38  jz      short loc_18001CD47
0x18001cd3a  cmp     [rbx+828h], r15d
0x18001cd41  jnz     loc_18001CE05
0x18001cd47  movzx   ecx, byte ptr [rdi]
0x18001cd4a  sub     ecx, 3
0x18001cd4d  jz      loc_18001CDEA
0x18001cd53  sub     ecx, 7Eh ; '~'
0x18001cd56  jz      short loc_18001CDD7
0x18001cd58  sub     ecx, 1
0x18001cd5b  jz      short loc_18001CDC4
0x18001cd5d  sub     ecx, 1
0x18001cd60  jz      short loc_18001CDAD
0x18001cd62  cmp     ecx, 1
0x18001cd65  jz      short loc_18001CD96
0x18001cd67  test    r9, r9
0x18001cd6a  jz      loc_18001CE05
0x18001cd70  mov     rcx, cs:gRasIpcpEtwContext
0x18001cd77  lea     r8, aIpcpUnrequeste_0; "IPCP: Unrequested option NAKed?"
0x18001cd7e  mov     rax, cs:gRasIpcpTemplateFunc
0x18001cd85  mov     rdx, r9
0x18001cd88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd8d  mov     r9, qword ptr cs:xmmword_18004C860
0x18001cd94  jmp     short loc_18001CE05
0x18001cd96  cmp     dl, sil
0x18001cd99  jnz     loc_18001CE3E
0x18001cd9f  cmp     dword ptr [rbx+34h], 0
0x18001cda3  jnz     short loc_18001CE05
0x18001cda5  mov     eax, [rdi+2]
0x18001cda8  mov     [rbx+64h], eax
0x18001cdab  jmp     short loc_18001CE05
0x18001cdad  cmp     dl, sil
0x18001cdb0  jnz     loc_18001CE3E
0x18001cdb6  cmp     dword ptr [rbx+30h], 0
0x18001cdba  jnz     short loc_18001CE05
0x18001cdbc  mov     eax, [rdi+2]
0x18001cdbf  mov     [rbx+6Ch], eax
0x18001cdc2  jmp     short loc_18001CE05
0x18001cdc4  cmp     dl, sil
0x18001cdc7  jnz     short loc_18001CE3E
0x18001cdc9  cmp     dword ptr [rbx+2Ch], 0
0x18001cdcd  jnz     short loc_18001CE05
0x18001cdcf  mov     eax, [rdi+2]
0x18001cdd2  mov     [rbx+60h], eax
0x18001cdd5  jmp     short loc_18001CE05
0x18001cdd7  cmp     dl, sil
0x18001cdda  jnz     short loc_18001CE3E
0x18001cddc  cmp     dword ptr [rbx+28h], 0
0x18001cde0  jnz     short loc_18001CE05
0x18001cde2  mov     eax, [rdi+2]
0x18001cde5  mov     [rbx+68h], eax
0x18001cde8  jmp     short loc_18001CE05
0x18001cdea  cmp     dl, sil
0x18001cded  jnz     short loc_18001CE3E
0x18001cdef  mov     eax, [rdi+2]
0x18001cdf2  test    eax, eax
0x18001cdf4  jz      short loc_18001CE27
0x18001cdf6  cmp     dword ptr [rbx+90h], 0
0x18001cdfd  jnz     short loc_18001CE37
0x18001cdff  mov     [rbx+90h], eax
0x18001ce05  movzx   ecx, byte ptr [rdi+1]
0x18001ce09  test    cl, cl
0x18001ce0b  jz      short loc_18001CE1A
0x18001ce0d  movzx   eax, cx
0x18001ce10  cmp     cx, bp
0x18001ce13  jnb     short loc_18001CE1A
0x18001ce15  sub     bp, ax
0x18001ce18  jmp     short loc_18001CE1F
0x18001ce1a  xor     eax, eax
0x18001ce1c  movzx   ebp, ax
0x18001ce1f  add     rdi, rcx
0x18001ce22  jmp     loc_18001CCC8
0x18001ce27  cmp     dword ptr [rbx+90h], 0
0x18001ce2e  jnz     short loc_18001CE37
0x18001ce30  mov     eax, 2E2h
0x18001ce35  jmp     short loc_18001CE47
0x18001ce37  mov     eax, 2DFh
0x18001ce3c  jmp     short loc_18001CE47
0x18001ce3e  mov     eax, 2D2h
0x18001ce43  jmp     short loc_18001CE47
0x18001ce45  xor     eax, eax
0x18001ce47  add     rsp, 38h
0x18001ce4b  pop     r15
0x18001ce4d  pop     r12
0x18001ce4f  pop     rdi
0x18001ce50  pop     rsi
0x18001ce51  pop     rbp
0x18001ce52  pop     rbx
0x18001ce53  retn
```
