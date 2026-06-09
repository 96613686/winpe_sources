# IpcpConfigAckReceived

- ea: `0x18001d3c0`
- end: `0x18001d6c8`
- name: `IpcpConfigAckReceived`
- size: `776`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18001d3c0`
- `0x18002b0dc`
- `0x180034010`

## string_xrefs

- `0x18001d46b`: `IPCP: IpcpConfigAckReceived...`
- `0x18001d49b`: `DumpingBytes IpcpConfigAckReceived`
- `0x18001d662`: `IPCP: IpcpConfigAckReceived done(%d)`

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
  v10 = *((_QWORD *)&xmmword_18004D860 + 1);
  if ( *((_QWORD *)&xmmword_18004D860 + 1) )
  {
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      *((_QWORD *)&xmmword_18004D860 + 1),
      L"IPCP: IpcpConfigAckReceived...");
    v10 = *((_QWORD *)&xmmword_18004D860 + 1);
  }
  if ( qword_18004D880 )
  {
    ((void (__fastcall *)(__int64, __int64, const wchar_t *, _QWORD, unsigned __int8 *))gRasIpcpByteTemplateFunc)(
      gRasIpcpEtwContext,
      qword_18004D880,
      L"DumpingBytes IpcpConfigAckReceived",
      v6,
      a2);
    v10 = *((_QWORD *)&xmmword_18004D860 + 1);
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
          if ( (_QWORD)xmmword_18004D860 )
            ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
              gRasIpcpEtwContext,
              xmmword_18004D860,
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
    FormatRRASErrorString((wchar_t *)&v18, L"IPCP: IpcpConfigAckReceived done(%d)", v14);
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      *((_QWORD *)&xmmword_18004D860 + 1),
      &v18);
  }
  return v14;
}

```

## disassembly

```asm
0x18001d3c0  mov     [rsp+arg_10], rbx
0x18001d3c5  push    rbp
0x18001d3c6  push    rsi
0x18001d3c7  push    rdi
0x18001d3c8  push    r12
0x18001d3ca  push    r13
0x18001d3cc  push    r14
0x18001d3ce  push    r15
0x18001d3d0  sub     rsp, 850h
0x18001d3d7  mov     rax, cs:__security_cookie
0x18001d3de  xor     rax, rsp
0x18001d3e1  mov     [rsp+888h+var_48], rax
0x18001d3e9  movzx   esi, byte ptr [rdx+3]
0x18001d3ed  lea     r14, [rdx+4]
0x18001d3f1  movzx   r8d, byte ptr [rdx+2]
0x18001d3f6  mov     eax, 100h
0x18001d3fb  mov     r13d, [rcx+20h]
0x18001d3ff  mov     rbx, rdx
0x18001d402  imul    r8d, eax
0x18001d406  mov     rdi, rcx
0x18001d409  add     si, r8w
0x18001d40d  cmp     dword ptr [rcx+24h], 0
0x18001d411  lea     ebp, [rsi-4]
0x18001d414  jnz     short loc_18001D421
0x18001d416  cmp     dword ptr [rcx+3Ch], 0
0x18001d41a  jnz     short loc_18001D421
0x18001d41c  xor     r15d, r15d
0x18001d41f  jmp     short loc_18001D427
0x18001d421  mov     r15d, 1
0x18001d427  mov     eax, [rcx+2Ch]
0x18001d42a  xor     edx, edx; Val
0x18001d42c  mov     r12d, [rcx+28h]
0x18001d430  mov     r8d, 7FCh; Size
0x18001d436  mov     [rsp+888h+var_858], eax
0x18001d43a  mov     eax, [rcx+30h]
0x18001d43d  mov     [rsp+888h+var_854], eax
0x18001d441  mov     eax, [rcx+34h]
0x18001d444  lea     rcx, [rsp+888h+var_844]; void *
0x18001d449  mov     [rsp+888h+var_850], eax
0x18001d44d  xor     eax, eax
0x18001d44f  mov     [rsp+888h+var_848], eax
0x18001d453  call    memset_0
0x18001d458  mov     r9, qword ptr cs:xmmword_18004D860+8
0x18001d45f  test    r9, r9
0x18001d462  jz      short loc_18001D488
0x18001d464  mov     rcx, cs:gRasIpcpEtwContext
0x18001d46b  lea     r8, aIpcpIpcpconfig; "IPCP: IpcpConfigAckReceived..."
0x18001d472  mov     rax, cs:gRasIpcpTemplateFunc
0x18001d479  mov     rdx, r9
0x18001d47c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d481  mov     r9, qword ptr cs:xmmword_18004D860+8
0x18001d488  mov     rdx, cs:qword_18004D880
0x18001d48f  test    rdx, rdx
0x18001d492  jz      short loc_18001D4BE
0x18001d494  mov     rcx, cs:gRasIpcpEtwContext
0x18001d49b  lea     r8, aDumpingbytesIp; "DumpingBytes IpcpConfigAckReceived"
0x18001d4a2  mov     rax, cs:gRasIpcpByteTemplateFunc
0x18001d4a9  movzx   r9d, si
0x18001d4ad  mov     [rsp+888h+var_868], rbx
0x18001d4b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4b7  mov     r9, qword ptr cs:xmmword_18004D860+8
0x18001d4be  mov     dword ptr [rdi+5Ch], 0
0x18001d4c5  mov     r10d, 1
0x18001d4cb  mov     r11d, 100h
0x18001d4d1  cmp     bp, 2
0x18001d4d5  jb      loc_18001D62F
0x18001d4db  movzx   r8d, byte ptr [r14+1]
0x18001d4e0  cmp     bp, r8w
0x18001d4e4  jb      loc_18001D628
0x18001d4ea  cmp     byte ptr [r14], 2
0x18001d4ee  jnz     short loc_18001D540
0x18001d4f0  cmp     r8b, 6
0x18001d4f4  jnz     loc_18001D628
0x18001d4fa  movzx   edx, byte ptr [r14+2]
0x18001d4ff  movzx   eax, byte ptr [r14+3]
0x18001d504  imul    edx, r11d
0x18001d508  add     dx, ax
0x18001d50b  cmp     dx, [rdi+0B0h]
0x18001d512  jnz     loc_18001D628
0x18001d518  mov     al, [rdi+0B2h]
0x18001d51e  cmp     [r14+4], al
0x18001d522  jnz     loc_18001D628
0x18001d528  mov     al, [rdi+0B3h]
0x18001d52e  cmp     [r14+5], al
0x18001d532  jnz     loc_18001D628
0x18001d538  mov     r13d, r10d
0x18001d53b  jmp     loc_18001D5E8
0x18001d540  cmp     byte ptr [r14], 3
0x18001d544  jnz     short loc_18001D56D
0x18001d546  cmp     r8b, 6
0x18001d54a  jnz     loc_18001D628
0x18001d550  mov     eax, [r14+2]
0x18001d554  test    eax, eax
0x18001d556  jz      loc_18001D5E8
0x18001d55c  cmp     eax, [rdi+90h]
0x18001d562  jnz     loc_18001D5E8
0x18001d568  mov     r15d, r10d
0x18001d56b  jmp     short loc_18001D5E8
0x18001d56d  cmp     dword ptr [rdi], 0
0x18001d570  jnz     loc_18001D602
0x18001d576  movzx   ecx, byte ptr [r14]
0x18001d57a  sub     ecx, 81h
0x18001d580  jz      short loc_18001D5D7
0x18001d582  sub     ecx, r10d
0x18001d585  jz      short loc_18001D5C1
0x18001d587  sub     ecx, r10d
0x18001d58a  jz      short loc_18001D5AB
0x18001d58c  cmp     ecx, r10d
0x18001d58f  jnz     short loc_18001D602
0x18001d591  cmp     r8b, 6
0x18001d595  jnz     loc_18001D628
0x18001d59b  mov     eax, [rdi+64h]
0x18001d59e  cmp     [r14+2], eax
0x18001d5a2  jnz     short loc_18001D5E8
0x18001d5a4  mov     [rsp+888h+var_850], r10d
0x18001d5a9  jmp     short loc_18001D5E8
0x18001d5ab  cmp     r8b, 6
0x18001d5af  jnz     short loc_18001D628
0x18001d5b1  mov     eax, [rdi+6Ch]
0x18001d5b4  cmp     [r14+2], eax
0x18001d5b8  jnz     short loc_18001D5E8
0x18001d5ba  mov     [rsp+888h+var_854], r10d
0x18001d5bf  jmp     short loc_18001D5E8
0x18001d5c1  cmp     r8b, 6
0x18001d5c5  jnz     short loc_18001D628
0x18001d5c7  mov     eax, [rdi+60h]
0x18001d5ca  cmp     [r14+2], eax
0x18001d5ce  jnz     short loc_18001D5E8
0x18001d5d0  mov     [rsp+888h+var_858], r10d
0x18001d5d5  jmp     short loc_18001D5E8
0x18001d5d7  cmp     r8b, 6
0x18001d5db  jnz     short loc_18001D628
0x18001d5dd  mov     eax, [rdi+68h]
0x18001d5e0  cmp     [r14+2], eax
0x18001d5e4  cmovz   r12d, r10d
0x18001d5e8  movzx   eax, bp
0x18001d5eb  add     r14, 6
0x18001d5ef  sub     ax, r8w
0x18001d5f3  cmp     r8w, bp
0x18001d5f7  sbb     bp, bp
0x18001d5fa  and     bp, ax
0x18001d5fd  jmp     loc_18001D4D1
0x18001d602  mov     rdx, qword ptr cs:xmmword_18004D860
0x18001d609  test    rdx, rdx
0x18001d60c  jz      short loc_18001D628
0x18001d60e  mov     rcx, cs:gRasIpcpEtwContext
0x18001d615  lea     r8, aIpcpUnrecogniz; "IPCP: Unrecognized option ACKed?"
0x18001d61c  mov     rax, cs:gRasIpcpTemplateFunc
0x18001d623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d628  mov     eax, 2D2h
0x18001d62d  jmp     short loc_18001D69C
0x18001d62f  test    r13d, r13d
0x18001d632  jz      short loc_18001D656
0x18001d634  test    r15d, r15d
0x18001d637  jz      short loc_18001D656
0x18001d639  xor     ebx, ebx
0x18001d63b  cmp     [rdi], ebx
0x18001d63d  jnz     short loc_18001D65B
0x18001d63f  test    r12d, r12d
0x18001d642  jz      short loc_18001D656
0x18001d644  cmp     [rsp+888h+var_858], ebx
0x18001d648  jz      short loc_18001D656
0x18001d64a  cmp     [rsp+888h+var_854], ebx
0x18001d64e  jz      short loc_18001D656
0x18001d650  cmp     [rsp+888h+var_850], ebx
0x18001d654  jnz     short loc_18001D65B
0x18001d656  mov     ebx, 2D2h
0x18001d65b  test    r9, r9
0x18001d65e  jz      short loc_18001D69A
0x18001d660  xor     ecx, ecx
0x18001d662  lea     rdx, aIpcpIpcpconfig_2; "IPCP: IpcpConfigAckReceived done(%d)"
0x18001d669  mov     word ptr [rsp+888h+var_848], cx
0x18001d66e  mov     r8d, ebx
0x18001d671  lea     rcx, [rsp+888h+var_848]
0x18001d676  call    FormatRRASErrorString
0x18001d67b  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001d682  lea     r8, [rsp+888h+var_848]
0x18001d687  mov     rcx, cs:gRasIpcpEtwContext
0x18001d68e  mov     rax, cs:gRasIpcpTemplateFunc
0x18001d695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d69a  mov     eax, ebx
0x18001d69c  mov     rcx, [rsp+888h+var_48]
0x18001d6a4  xor     rcx, rsp; StackCookie
0x18001d6a7  call    __security_check_cookie
0x18001d6ac  mov     rbx, [rsp+888h+arg_10]
0x18001d6b4  add     rsp, 850h
0x18001d6bb  pop     r15
0x18001d6bd  pop     r14
0x18001d6bf  pop     r13
0x18001d6c1  pop     r12
0x18001d6c3  pop     rdi
0x18001d6c4  pop     rsi
0x18001d6c5  pop     rbp
0x18001d6c6  retn
```
