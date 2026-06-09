# IpcpConfigAckReceived

- ea: `0x18001c8e0`
- end: `0x18001cbe7`
- name: `IpcpConfigAckReceived`
- size: `775`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18001c8e0`
- `0x18002a138`
- `0x180033010`

## string_xrefs

- `0x18001c98b`: `IPCP: IpcpConfigAckReceived...`
- `0x18001c9bb`: `DumpingBytes IpcpConfigAckReceived`
- `0x18001cb82`: `IPCP: IpcpConfigAckReceived done(%d)`

## pseudocode

```c
__int64 __fastcall IpcpConfigAckReceived(__int64 a1, unsigned __int8 *a2)
{
  unsigned __int8 *v2; // r14
  int v3; // r13d
  unsigned __int16 v6; // si
  unsigned __int16 v7; // bp
  BOOL v8; // r15d
  int v9; // r12d
  __int64 v10; // r9
  unsigned __int16 v11; // r8
  int v12; // eax
  unsigned int v14; // ebx
  int v15; // [rsp+30h] [rbp-858h]
  int v16; // [rsp+34h] [rbp-854h]
  int v17; // [rsp+38h] [rbp-850h]
  int v18; // [rsp+40h] [rbp-848h] BYREF
  _BYTE v19[2044]; // [rsp+44h] [rbp-844h] BYREF

  v2 = a2 + 4;
  v3 = *(_DWORD *)(a1 + 32);
  v6 = (a2[2] << 8) + a2[3];
  v7 = v6 - 4;
  v8 = *(_DWORD *)(a1 + 36) || *(_DWORD *)(a1 + 60);
  v9 = *(_DWORD *)(a1 + 40);
  v15 = *(_DWORD *)(a1 + 44);
  v16 = *(_DWORD *)(a1 + 48);
  v17 = *(_DWORD *)(a1 + 52);
  v18 = 0;
  memset_0(v19, 0, sizeof(v19));
  v10 = *((_QWORD *)&xmmword_18004C860 + 1);
  if ( *((_QWORD *)&xmmword_18004C860 + 1) )
  {
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      *((_QWORD *)&xmmword_18004C860 + 1),
      L"IPCP: IpcpConfigAckReceived...");
    v10 = *((_QWORD *)&xmmword_18004C860 + 1);
  }
  if ( qword_18004C880 )
  {
    ((void (__fastcall *)(__int64, __int64, const wchar_t *, _QWORD, unsigned __int8 *))gRasIpcpByteTemplateFunc)(
      gRasIpcpEtwContext,
      qword_18004C880,
      L"DumpingBytes IpcpConfigAckReceived",
      v6,
      a2);
    v10 = *((_QWORD *)&xmmword_18004C860 + 1);
  }
  *(_DWORD *)(a1 + 92) = 0;
  while ( v7 >= 2u )
  {
    v11 = v2[1];
    if ( v7 < v11 )
      return 722;
    if ( *v2 == 2 )
    {
      if ( (_BYTE)v11 != 6
        || v2[3] + (v2[2] << 8) != *(_WORD *)(a1 + 176)
        || v2[4] != *(_BYTE *)(a1 + 178)
        || v2[5] != *(_BYTE *)(a1 + 179) )
      {
        return 722;
      }
      v3 = 1;
    }
    else if ( *v2 == 3 )
    {
      if ( (_BYTE)v11 != 6 )
        return 722;
      v12 = *(_DWORD *)(v2 + 2);
      if ( v12 && v12 == *(_DWORD *)(a1 + 144) )
        v8 = 1;
    }
    else
    {
      if ( *(_DWORD *)a1 )
        goto LABEL_41;
      switch ( *v2 )
      {
        case 0x81u:
          if ( (_BYTE)v11 != 6 )
            return 722;
          if ( *(_DWORD *)(v2 + 2) == *(_DWORD *)(a1 + 104) )
            v9 = 1;
          break;
        case 0x82u:
          if ( (_BYTE)v11 != 6 )
            return 722;
          if ( *(_DWORD *)(v2 + 2) == *(_DWORD *)(a1 + 96) )
            v15 = 1;
          break;
        case 0x83u:
          if ( (_BYTE)v11 != 6 )
            return 722;
          if ( *(_DWORD *)(v2 + 2) == *(_DWORD *)(a1 + 108) )
            v16 = 1;
          break;
        case 0x84u:
          if ( (_BYTE)v11 != 6 )
            return 722;
          if ( *(_DWORD *)(v2 + 2) == *(_DWORD *)(a1 + 100) )
            v17 = 1;
          break;
        default:
LABEL_41:
          if ( (_QWORD)xmmword_18004C860 )
            ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
              gRasIpcpEtwContext,
              xmmword_18004C860,
              L"IPCP: Unrecognized option ACKed?");
          return 722;
      }
    }
    v2 += 6;
    v7 = v11 < v7 ? v7 - v11 : 0;
  }
  if ( !v3 || !v8 || (v14 = 0, !*(_DWORD *)a1) && (!v9 || !v15 || !v16 || !v17) )
    v14 = 722;
  if ( v10 )
  {
    LOWORD(v18) = 0;
    FormatRRASErrorString(&v18, L"IPCP: IpcpConfigAckReceived done(%d)", v14);
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      *((_QWORD *)&xmmword_18004C860 + 1),
      &v18);
  }
  return v14;
}

```

## disassembly

```asm
0x18001c8e0  mov     [rsp+arg_10], rbx
0x18001c8e5  push    rbp
0x18001c8e6  push    rsi
0x18001c8e7  push    rdi
0x18001c8e8  push    r12
0x18001c8ea  push    r13
0x18001c8ec  push    r14
0x18001c8ee  push    r15
0x18001c8f0  sub     rsp, 850h
0x18001c8f7  mov     rax, cs:__security_cookie
0x18001c8fe  xor     rax, rsp
0x18001c901  mov     [rsp+888h+var_48], rax
0x18001c909  movzx   esi, byte ptr [rdx+3]
0x18001c90d  lea     r14, [rdx+4]
0x18001c911  movzx   r8d, byte ptr [rdx+2]
0x18001c916  mov     eax, 100h
0x18001c91b  mov     r13d, [rcx+20h]
0x18001c91f  mov     rbx, rdx
0x18001c922  imul    r8d, eax
0x18001c926  mov     rdi, rcx
0x18001c929  add     si, r8w
0x18001c92d  cmp     dword ptr [rcx+24h], 0
0x18001c931  lea     ebp, [rsi-4]
0x18001c934  jnz     short loc_18001C941
0x18001c936  cmp     dword ptr [rcx+3Ch], 0
0x18001c93a  jnz     short loc_18001C941
0x18001c93c  xor     r15d, r15d
0x18001c93f  jmp     short loc_18001C947
0x18001c941  mov     r15d, 1
0x18001c947  mov     eax, [rcx+2Ch]
0x18001c94a  xor     edx, edx; Val
0x18001c94c  mov     r12d, [rcx+28h]
0x18001c950  mov     r8d, 7FCh; Size
0x18001c956  mov     [rsp+888h+var_858], eax
0x18001c95a  mov     eax, [rcx+30h]
0x18001c95d  mov     [rsp+888h+var_854], eax
0x18001c961  mov     eax, [rcx+34h]
0x18001c964  lea     rcx, [rsp+888h+var_844]; void *
0x18001c969  mov     [rsp+888h+var_850], eax
0x18001c96d  xor     eax, eax
0x18001c96f  mov     [rsp+888h+var_848], eax
0x18001c973  call    memset_0
0x18001c978  mov     r9, qword ptr cs:xmmword_18004C860+8
0x18001c97f  test    r9, r9
0x18001c982  jz      short loc_18001C9A8
0x18001c984  mov     rcx, cs:gRasIpcpEtwContext
0x18001c98b  lea     r8, aIpcpIpcpconfig; "IPCP: IpcpConfigAckReceived..."
0x18001c992  mov     rax, cs:gRasIpcpTemplateFunc
0x18001c999  mov     rdx, r9
0x18001c99c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c9a1  mov     r9, qword ptr cs:xmmword_18004C860+8
0x18001c9a8  mov     rdx, cs:qword_18004C880
0x18001c9af  test    rdx, rdx
0x18001c9b2  jz      short loc_18001C9DE
0x18001c9b4  mov     rcx, cs:gRasIpcpEtwContext
0x18001c9bb  lea     r8, aDumpingbytesIp; "DumpingBytes IpcpConfigAckReceived"
0x18001c9c2  mov     rax, cs:gRasIpcpByteTemplateFunc
0x18001c9c9  movzx   r9d, si
0x18001c9cd  mov     [rsp+888h+var_868], rbx
0x18001c9d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c9d7  mov     r9, qword ptr cs:xmmword_18004C860+8
0x18001c9de  mov     dword ptr [rdi+5Ch], 0
0x18001c9e5  mov     r10d, 1
0x18001c9eb  mov     r11d, 100h
0x18001c9f1  cmp     bp, 2
0x18001c9f5  jb      loc_18001CB4F
0x18001c9fb  movzx   r8d, byte ptr [r14+1]
0x18001ca00  cmp     bp, r8w
0x18001ca04  jb      loc_18001CB48
0x18001ca0a  cmp     byte ptr [r14], 2
0x18001ca0e  jnz     short loc_18001CA60
0x18001ca10  cmp     r8b, 6
0x18001ca14  jnz     loc_18001CB48
0x18001ca1a  movzx   edx, byte ptr [r14+2]
0x18001ca1f  movzx   eax, byte ptr [r14+3]
0x18001ca24  imul    edx, r11d
0x18001ca28  add     dx, ax
0x18001ca2b  cmp     dx, [rdi+0B0h]
0x18001ca32  jnz     loc_18001CB48
0x18001ca38  mov     al, [rdi+0B2h]
0x18001ca3e  cmp     [r14+4], al
0x18001ca42  jnz     loc_18001CB48
0x18001ca48  mov     al, [rdi+0B3h]
0x18001ca4e  cmp     [r14+5], al
0x18001ca52  jnz     loc_18001CB48
0x18001ca58  mov     r13d, r10d
0x18001ca5b  jmp     loc_18001CB08
0x18001ca60  cmp     byte ptr [r14], 3
0x18001ca64  jnz     short loc_18001CA8D
0x18001ca66  cmp     r8b, 6
0x18001ca6a  jnz     loc_18001CB48
0x18001ca70  mov     eax, [r14+2]
0x18001ca74  test    eax, eax
0x18001ca76  jz      loc_18001CB08
0x18001ca7c  cmp     eax, [rdi+90h]
0x18001ca82  jnz     loc_18001CB08
0x18001ca88  mov     r15d, r10d
0x18001ca8b  jmp     short loc_18001CB08
0x18001ca8d  cmp     dword ptr [rdi], 0
0x18001ca90  jnz     loc_18001CB22
0x18001ca96  movzx   ecx, byte ptr [r14]
0x18001ca9a  sub     ecx, 81h
0x18001caa0  jz      short loc_18001CAF7
0x18001caa2  sub     ecx, r10d
0x18001caa5  jz      short loc_18001CAE1
0x18001caa7  sub     ecx, r10d
0x18001caaa  jz      short loc_18001CACB
0x18001caac  cmp     ecx, r10d
0x18001caaf  jnz     short loc_18001CB22
0x18001cab1  cmp     r8b, 6
0x18001cab5  jnz     loc_18001CB48
0x18001cabb  mov     eax, [rdi+64h]
0x18001cabe  cmp     [r14+2], eax
0x18001cac2  jnz     short loc_18001CB08
0x18001cac4  mov     [rsp+888h+var_850], r10d
0x18001cac9  jmp     short loc_18001CB08
0x18001cacb  cmp     r8b, 6
0x18001cacf  jnz     short loc_18001CB48
0x18001cad1  mov     eax, [rdi+6Ch]
0x18001cad4  cmp     [r14+2], eax
0x18001cad8  jnz     short loc_18001CB08
0x18001cada  mov     [rsp+888h+var_854], r10d
0x18001cadf  jmp     short loc_18001CB08
0x18001cae1  cmp     r8b, 6
0x18001cae5  jnz     short loc_18001CB48
0x18001cae7  mov     eax, [rdi+60h]
0x18001caea  cmp     [r14+2], eax
0x18001caee  jnz     short loc_18001CB08
0x18001caf0  mov     [rsp+888h+var_858], r10d
0x18001caf5  jmp     short loc_18001CB08
0x18001caf7  cmp     r8b, 6
0x18001cafb  jnz     short loc_18001CB48
0x18001cafd  mov     eax, [rdi+68h]
0x18001cb00  cmp     [r14+2], eax
0x18001cb04  cmovz   r12d, r10d
0x18001cb08  movzx   eax, bp
0x18001cb0b  add     r14, 6
0x18001cb0f  sub     ax, r8w
0x18001cb13  cmp     r8w, bp
0x18001cb17  sbb     bp, bp
0x18001cb1a  and     bp, ax
0x18001cb1d  jmp     loc_18001C9F1
0x18001cb22  mov     rdx, qword ptr cs:xmmword_18004C860
0x18001cb29  test    rdx, rdx
0x18001cb2c  jz      short loc_18001CB48
0x18001cb2e  mov     rcx, cs:gRasIpcpEtwContext
0x18001cb35  lea     r8, aIpcpUnrecogniz; "IPCP: Unrecognized option ACKed?"
0x18001cb3c  mov     rax, cs:gRasIpcpTemplateFunc
0x18001cb43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb48  mov     eax, 2D2h
0x18001cb4d  jmp     short loc_18001CBBC
0x18001cb4f  test    r13d, r13d
0x18001cb52  jz      short loc_18001CB76
0x18001cb54  test    r15d, r15d
0x18001cb57  jz      short loc_18001CB76
0x18001cb59  xor     ebx, ebx
0x18001cb5b  cmp     [rdi], ebx
0x18001cb5d  jnz     short loc_18001CB7B
0x18001cb5f  test    r12d, r12d
0x18001cb62  jz      short loc_18001CB76
0x18001cb64  cmp     [rsp+888h+var_858], ebx
0x18001cb68  jz      short loc_18001CB76
0x18001cb6a  cmp     [rsp+888h+var_854], ebx
0x18001cb6e  jz      short loc_18001CB76
0x18001cb70  cmp     [rsp+888h+var_850], ebx
0x18001cb74  jnz     short loc_18001CB7B
0x18001cb76  mov     ebx, 2D2h
0x18001cb7b  test    r9, r9
0x18001cb7e  jz      short loc_18001CBBA
0x18001cb80  xor     ecx, ecx
0x18001cb82  lea     rdx, aIpcpIpcpconfig_2; "IPCP: IpcpConfigAckReceived done(%d)"
0x18001cb89  mov     word ptr [rsp+888h+var_848], cx
0x18001cb8e  mov     r8d, ebx
0x18001cb91  lea     rcx, [rsp+888h+var_848]
0x18001cb96  call    FormatRRASErrorString
0x18001cb9b  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001cba2  lea     r8, [rsp+888h+var_848]
0x18001cba7  mov     rcx, cs:gRasIpcpEtwContext
0x18001cbae  mov     rax, cs:gRasIpcpTemplateFunc
0x18001cbb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cbba  mov     eax, ebx
0x18001cbbc  mov     rcx, [rsp+888h+var_48]
0x18001cbc4  xor     rcx, rsp; StackCookie
0x18001cbc7  call    __security_check_cookie
0x18001cbcc  mov     rbx, [rsp+888h+arg_10]
0x18001cbd4  add     rsp, 850h
0x18001cbdb  pop     r15
0x18001cbdd  pop     r14
0x18001cbdf  pop     r13
0x18001cbe1  pop     r12
0x18001cbe3  pop     rdi
0x18001cbe4  pop     rsi
0x18001cbe5  pop     rbp
0x18001cbe6  retn
```
