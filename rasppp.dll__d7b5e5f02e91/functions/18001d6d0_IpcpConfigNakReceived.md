# IpcpConfigNakReceived

- ea: `0x18001d6d0`
- end: `0x18001d935`
- name: `IpcpConfigNakReceived`
- size: `613`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18001d6d0`
- `0x180034010`

## string_xrefs

- `0x18001d713`: `IPCP: IpcpConfigNakReceived`

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
  if ( *((_QWORD *)&xmmword_18004D860 + 1) )
  {
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      *((_QWORD *)&xmmword_18004D860 + 1),
      L"IPCP: IpcpConfigNakReceived");
    if ( *((_QWORD *)&xmmword_18004D860 + 1) )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
        gRasIpcpEtwContext,
        *((_QWORD *)&xmmword_18004D860 + 1),
        L"IPCP: Nak received...");
  }
  if ( qword_18004D880 )
  {
    if ( a2 )
      v6 = a2[3] + (a2[2] << 8);
    else
      v6 = 0;
    ((void (__fastcall *)(__int64, __int64, const wchar_t *, __int64, unsigned __int8 *))gRasIpcpByteTemplateFunc)(
      gRasIpcpEtwContext,
      qword_18004D880,
      L"DumpingBytes Nak ",
      v6,
      a2);
  }
  v7 = xmmword_18004D860;
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
            v7 = xmmword_18004D860;
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
0x18001d6d0  push    rbx
0x18001d6d2  push    rbp
0x18001d6d3  push    rsi
0x18001d6d4  push    rdi
0x18001d6d5  push    r12
0x18001d6d7  push    r15
0x18001d6d9  sub     rsp, 38h
0x18001d6dd  movzx   ebp, byte ptr [rdx+2]
0x18001d6e1  lea     rdi, [rdx+4]
0x18001d6e5  movzx   eax, byte ptr [rdx+3]
0x18001d6e9  mov     r12d, 100h
0x18001d6ef  imul    ebp, r12d
0x18001d6f3  sub     ax, 4
0x18001d6f7  mov     rsi, rdx
0x18001d6fa  mov     rbx, rcx
0x18001d6fd  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001d704  add     bp, ax
0x18001d707  test    rdx, rdx
0x18001d70a  jz      short loc_18001D74C
0x18001d70c  mov     rcx, cs:gRasIpcpEtwContext
0x18001d713  lea     r8, aIpcpIpcpconfig_0; "IPCP: IpcpConfigNakReceived"
0x18001d71a  mov     rax, cs:gRasIpcpTemplateFunc
0x18001d721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d726  mov     rdx, qword ptr cs:xmmword_18004D860+8
0x18001d72d  test    rdx, rdx
0x18001d730  jz      short loc_18001D74C
0x18001d732  mov     rcx, cs:gRasIpcpEtwContext
0x18001d739  lea     r8, aIpcpNakReceive; "IPCP: Nak received..."
0x18001d740  mov     rax, cs:gRasIpcpTemplateFunc
0x18001d747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d74c  mov     rdx, cs:qword_18004D880
0x18001d753  test    rdx, rdx
0x18001d756  jz      short loc_18001D791
0x18001d758  test    rsi, rsi
0x18001d75b  jz      short loc_18001D76F
0x18001d75d  movzx   r9d, byte ptr [rsi+2]
0x18001d762  movzx   eax, byte ptr [rsi+3]
0x18001d766  shl     r9d, 8
0x18001d76a  add     r9d, eax
0x18001d76d  jmp     short loc_18001D772
0x18001d76f  xor     r9d, r9d
0x18001d772  mov     rcx, cs:gRasIpcpEtwContext
0x18001d779  lea     r8, aDumpingbytesNa; "DumpingBytes Nak "
0x18001d780  mov     rax, cs:gRasIpcpByteTemplateFunc
0x18001d787  mov     [rsp+68h+var_48], rsi
0x18001d78c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d791  mov     r9, qword ptr cs:xmmword_18004D860
0x18001d798  mov     r15d, 2
0x18001d79e  mov     dword ptr [rbx+5Ch], 0
0x18001d7a5  mov     sil, 6
0x18001d7a8  cmp     bp, r15w
0x18001d7ac  jb      loc_18001D925
0x18001d7b2  movzx   edx, byte ptr [rdi+1]
0x18001d7b6  cmp     bp, dx
0x18001d7b9  jb      loc_18001D91E
0x18001d7bf  cmp     [rdi], r15b
0x18001d7c2  jnz     short loc_18001D815
0x18001d7c4  cmp     dl, sil
0x18001d7c7  jnz     loc_18001D91E
0x18001d7cd  movzx   edx, byte ptr [rdi+2]
0x18001d7d1  movzx   r8d, byte ptr [rdi+3]
0x18001d7d6  imul    edx, r12d
0x18001d7da  add     r8w, dx
0x18001d7de  cmp     r8w, 2Dh ; '-'
0x18001d7e3  jnz     loc_18001D8E5
0x18001d7e9  mov     al, [rdi+4]
0x18001d7ec  cmp     al, [rbx+0B2h]
0x18001d7f2  ja      short loc_18001D7FA
0x18001d7f4  mov     [rbx+0B2h], al
0x18001d7fa  cmp     byte ptr [rbx+0B3h], 0
0x18001d801  jz      loc_18001D8E5
0x18001d807  mov     al, [rdi+5]
0x18001d80a  mov     [rbx+0B3h], al
0x18001d810  jmp     loc_18001D8E5
0x18001d815  cmp     dword ptr [rbx], 0
0x18001d818  jz      short loc_18001D827
0x18001d81a  cmp     [rbx+828h], r15d
0x18001d821  jnz     loc_18001D8E5
0x18001d827  movzx   ecx, byte ptr [rdi]
0x18001d82a  sub     ecx, 3
0x18001d82d  jz      loc_18001D8CA
0x18001d833  sub     ecx, 7Eh ; '~'
0x18001d836  jz      short loc_18001D8B7
0x18001d838  sub     ecx, 1
0x18001d83b  jz      short loc_18001D8A4
0x18001d83d  sub     ecx, 1
0x18001d840  jz      short loc_18001D88D
0x18001d842  cmp     ecx, 1
0x18001d845  jz      short loc_18001D876
0x18001d847  test    r9, r9
0x18001d84a  jz      loc_18001D8E5
0x18001d850  mov     rcx, cs:gRasIpcpEtwContext
0x18001d857  lea     r8, aIpcpUnrequeste_0; "IPCP: Unrequested option NAKed?"
0x18001d85e  mov     rax, cs:gRasIpcpTemplateFunc
0x18001d865  mov     rdx, r9
0x18001d868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d86d  mov     r9, qword ptr cs:xmmword_18004D860
0x18001d874  jmp     short loc_18001D8E5
0x18001d876  cmp     dl, sil
0x18001d879  jnz     loc_18001D91E
0x18001d87f  cmp     dword ptr [rbx+34h], 0
0x18001d883  jnz     short loc_18001D8E5
0x18001d885  mov     eax, [rdi+2]
0x18001d888  mov     [rbx+64h], eax
0x18001d88b  jmp     short loc_18001D8E5
0x18001d88d  cmp     dl, sil
0x18001d890  jnz     loc_18001D91E
0x18001d896  cmp     dword ptr [rbx+30h], 0
0x18001d89a  jnz     short loc_18001D8E5
0x18001d89c  mov     eax, [rdi+2]
0x18001d89f  mov     [rbx+6Ch], eax
0x18001d8a2  jmp     short loc_18001D8E5
0x18001d8a4  cmp     dl, sil
0x18001d8a7  jnz     short loc_18001D91E
0x18001d8a9  cmp     dword ptr [rbx+2Ch], 0
0x18001d8ad  jnz     short loc_18001D8E5
0x18001d8af  mov     eax, [rdi+2]
0x18001d8b2  mov     [rbx+60h], eax
0x18001d8b5  jmp     short loc_18001D8E5
0x18001d8b7  cmp     dl, sil
0x18001d8ba  jnz     short loc_18001D91E
0x18001d8bc  cmp     dword ptr [rbx+28h], 0
0x18001d8c0  jnz     short loc_18001D8E5
0x18001d8c2  mov     eax, [rdi+2]
0x18001d8c5  mov     [rbx+68h], eax
0x18001d8c8  jmp     short loc_18001D8E5
0x18001d8ca  cmp     dl, sil
0x18001d8cd  jnz     short loc_18001D91E
0x18001d8cf  mov     eax, [rdi+2]
0x18001d8d2  test    eax, eax
0x18001d8d4  jz      short loc_18001D907
0x18001d8d6  cmp     dword ptr [rbx+90h], 0
0x18001d8dd  jnz     short loc_18001D917
0x18001d8df  mov     [rbx+90h], eax
0x18001d8e5  movzx   ecx, byte ptr [rdi+1]
0x18001d8e9  test    cl, cl
0x18001d8eb  jz      short loc_18001D8FA
0x18001d8ed  movzx   eax, cx
0x18001d8f0  cmp     cx, bp
0x18001d8f3  jnb     short loc_18001D8FA
0x18001d8f5  sub     bp, ax
0x18001d8f8  jmp     short loc_18001D8FF
0x18001d8fa  xor     eax, eax
0x18001d8fc  movzx   ebp, ax
0x18001d8ff  add     rdi, rcx
0x18001d902  jmp     loc_18001D7A8
0x18001d907  cmp     dword ptr [rbx+90h], 0
0x18001d90e  jnz     short loc_18001D917
0x18001d910  mov     eax, 2E2h
0x18001d915  jmp     short loc_18001D927
0x18001d917  mov     eax, 2DFh
0x18001d91c  jmp     short loc_18001D927
0x18001d91e  mov     eax, 2D2h
0x18001d923  jmp     short loc_18001D927
0x18001d925  xor     eax, eax
0x18001d927  add     rsp, 38h
0x18001d92b  pop     r15
0x18001d92d  pop     r12
0x18001d92f  pop     rdi
0x18001d930  pop     rsi
0x18001d931  pop     rbp
0x18001d932  pop     rbx
0x18001d933  retn
```
