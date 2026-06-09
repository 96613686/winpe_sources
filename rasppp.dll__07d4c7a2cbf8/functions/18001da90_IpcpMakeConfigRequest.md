# IpcpMakeConfigRequest

- ea: `0x18001da90`
- end: `0x18001dcfd`
- name: `IpcpMakeConfigRequest`
- size: `621`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18001da90`
- `0x18002a138`
- `0x180033010`

## string_xrefs

- `0x18001dae9`: `IPCP: IpcpMakeConfigRequest`
- `0x18001dc90`: `IPCP: ConfigRequest...`
- `0x18001dcb6`: `Dumping Bytes ConfigRequest`

## pseudocode

```c
__int64 __fastcall IpcpMakeConfigRequest(__int64 a1, _BYTE *a2)
{
  __int64 v4; // rdx
  unsigned __int16 v6; // si
  _BYTE *v7; // rdi
  __int16 v8; // cx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // [rsp+30h] [rbp-828h] BYREF
  _BYTE v15[2044]; // [rsp+34h] [rbp-824h] BYREF

  v14 = 0;
  memset_0(v15, 0, sizeof(v15));
  v4 = *((_QWORD *)&xmmword_18004C860 + 1);
  if ( *((_QWORD *)&xmmword_18004C860 + 1) )
  {
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpcpTemplateFunc)(
      gRasIpcpEtwContext,
      *((_QWORD *)&xmmword_18004C860 + 1),
      L"IPCP: IpcpMakeConfigRequest");
    v4 = *((_QWORD *)&xmmword_18004C860 + 1);
  }
  if ( *(_DWORD *)(a1 + 1260) )
  {
    if ( (_QWORD)xmmword_18004C860 )
    {
      LOWORD(v14) = 0;
      FormatRRASErrorString(&v14, L"IPCP: Deferred IpcpBegin error=%d");
      ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpcpTemplateFunc)(gRasIpcpEtwContext, xmmword_18004C860, &v14);
    }
    return *(unsigned int *)(a1 + 1260);
  }
  else
  {
    v6 = 4;
    v7 = a2 + 4;
    if ( ++*(_DWORD *)(a1 + 92) >= (unsigned int)DwMaxMSOptionCfgCnt )
    {
      if ( v4 )
      {
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(
          gRasIpcpEtwContext,
          v4,
          L"IPCP: Tossing MS options (request timeouts)");
        v4 = *((_QWORD *)&xmmword_18004C860 + 1);
      }
      *(_DWORD *)(a1 + 56) = 1;
      *(_DWORD *)(a1 + 40) = 1;
      *(_DWORD *)(a1 + 44) = 1;
      *(_DWORD *)(a1 + 48) = 1;
      *(_DWORD *)(a1 + 52) = 1;
    }
    if ( !*(_DWORD *)(a1 + 32) )
    {
      *(_WORD *)v7 = 1538;
      v6 = 10;
      v8 = *(_WORD *)(a1 + 176);
      a2[7] = v8;
      a2[6] = HIBYTE(v8);
      a2[8] = *(_BYTE *)(a1 + 178);
      a2[9] = *(_BYTE *)(a1 + 179);
      v7 = a2 + 10;
    }
    if ( !*(_DWORD *)(a1 + 36) && !*(_DWORD *)(a1 + 60) )
    {
      v9 = *(_DWORD *)(a1 + 144);
      v6 += 6;
      *(_WORD *)v7 = 1539;
      *(_DWORD *)(v7 + 2) = v9;
      v7 += 6;
    }
    if ( !*(_DWORD *)a1 )
    {
      if ( !*(_DWORD *)(a1 + 40) )
      {
        v10 = *(_DWORD *)(a1 + 104);
        v6 += 6;
        *(_WORD *)v7 = 1665;
        *(_DWORD *)(v7 + 2) = v10;
        v7 += 6;
      }
      if ( !*(_DWORD *)(a1 + 44) )
      {
        v11 = *(_DWORD *)(a1 + 96);
        v6 += 6;
        *(_WORD *)v7 = 1666;
        *(_DWORD *)(v7 + 2) = v11;
        v7 += 6;
      }
      if ( !*(_DWORD *)(a1 + 48) )
      {
        v12 = *(_DWORD *)(a1 + 108);
        v6 += 6;
        *(_WORD *)v7 = 1667;
        *(_DWORD *)(v7 + 2) = v12;
        v7 += 6;
      }
      if ( !*(_DWORD *)(a1 + 52) )
      {
        v13 = *(_DWORD *)(a1 + 100);
        v6 += 6;
        *(_WORD *)v7 = 1668;
        *(_DWORD *)(v7 + 2) = v13;
      }
    }
    *a2 = 1;
    a2[2] = HIBYTE(v6);
    a2[3] = v6;
    if ( v4 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpcpTemplateFunc)(
        gRasIpcpEtwContext,
        v4,
        L"IPCP: ConfigRequest...");
    if ( qword_18004C880 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *, _QWORD, _BYTE *))gRasIpcpByteTemplateFunc)(
        gRasIpcpEtwContext,
        qword_18004C880,
        L"Dumping Bytes ConfigRequest",
        v6,
        a2);
    return 0;
  }
}

```

## disassembly

```asm
0x18001da90  mov     [rsp+arg_10], rbx
0x18001da95  mov     [rsp+arg_18], rsi
0x18001da9a  push    rdi
0x18001da9b  push    r14
0x18001da9d  push    r15
0x18001da9f  sub     rsp, 840h
0x18001daa6  mov     rax, cs:__security_cookie
0x18001daad  xor     rax, rsp
0x18001dab0  mov     [rsp+858h+var_28], rax
0x18001dab8  mov     r14, rdx
0x18001dabb  mov     rbx, rcx
0x18001dabe  xor     eax, eax
0x18001dac0  lea     rcx, [rsp+858h+var_824]; void *
0x18001dac5  xor     edx, edx; Val
0x18001dac7  mov     [rsp+858h+var_828], eax
0x18001dacb  mov     r8d, 7FCh; Size
0x18001dad1  call    memset_0
0x18001dad6  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001dadd  test    rdx, rdx
0x18001dae0  jz      short loc_18001DB03
0x18001dae2  mov     rcx, cs:gRasIpcpEtwContext
0x18001dae9  lea     r8, aIpcpIpcpmakeco_0; "IPCP: IpcpMakeConfigRequest"
0x18001daf0  mov     rax, cs:gRasIpcpTemplateFunc
0x18001daf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dafc  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001db03  mov     r8d, [rbx+4ECh]
0x18001db0a  test    r8d, r8d
0x18001db0d  jz      short loc_18001DB5B
0x18001db0f  cmp     qword ptr cs:xmmword_18004C860, 0
0x18001db17  jz      short loc_18001DB50
0x18001db19  xor     eax, eax
0x18001db1b  lea     rdx, aIpcpDeferredIp; "IPCP: Deferred IpcpBegin error=%d"
0x18001db22  lea     rcx, [rsp+858h+var_828]
0x18001db27  mov     word ptr [rsp+858h+var_828], ax
0x18001db2c  call    FormatRRASErrorString
0x18001db31  mov     rdx, qword ptr cs:xmmword_18004C860
0x18001db38  lea     r8, [rsp+858h+var_828]
0x18001db3d  mov     rcx, cs:gRasIpcpEtwContext
0x18001db44  mov     rax, cs:gRasIpcpTemplateFunc
0x18001db4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db50  mov     eax, [rbx+4ECh]
0x18001db56  jmp     loc_18001DCD4
0x18001db5b  mov     esi, 4
0x18001db60  lea     rdi, [r14+4]
0x18001db64  lea     r15d, [rsi-3]
0x18001db68  add     [rbx+5Ch], r15d
0x18001db6c  mov     eax, [rbx+5Ch]
0x18001db6f  cmp     eax, cs:DwMaxMSOptionCfgCnt
0x18001db75  jb      short loc_18001DBB1
0x18001db77  test    rdx, rdx
0x18001db7a  jz      short loc_18001DB9D
0x18001db7c  mov     rcx, cs:gRasIpcpEtwContext
0x18001db83  lea     r8, aIpcpTossingMsO; "IPCP: Tossing MS options (request timeo"...
0x18001db8a  mov     rax, cs:gRasIpcpTemplateFunc
0x18001db91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db96  mov     rdx, qword ptr cs:xmmword_18004C860+8
0x18001db9d  mov     [rbx+38h], r15d
0x18001dba1  mov     [rbx+28h], r15d
0x18001dba5  mov     [rbx+2Ch], r15d
0x18001dba9  mov     [rbx+30h], r15d
0x18001dbad  mov     [rbx+34h], r15d
0x18001dbb1  cmp     dword ptr [rbx+20h], 0
0x18001dbb5  mov     r8d, 6
0x18001dbbb  jnz     short loc_18001DBEF
0x18001dbbd  mov     word ptr [rdi], 602h
0x18001dbc2  lea     esi, [r8+4]
0x18001dbc6  movzx   ecx, word ptr [rbx+0B0h]
0x18001dbcd  mov     [rdi+3], cl
0x18001dbd0  movzx   eax, cx
0x18001dbd3  shr     ax, 8
0x18001dbd7  mov     [rdi+2], al
0x18001dbda  mov     al, [rbx+0B2h]
0x18001dbe0  mov     [rdi+4], al
0x18001dbe3  mov     al, [rbx+0B3h]
0x18001dbe9  mov     [rdi+5], al
0x18001dbec  add     rdi, r8
0x18001dbef  cmp     dword ptr [rbx+24h], 0
0x18001dbf3  jnz     short loc_18001DC10
0x18001dbf5  cmp     dword ptr [rbx+3Ch], 0
0x18001dbf9  jnz     short loc_18001DC10
0x18001dbfb  mov     eax, [rbx+90h]
0x18001dc01  add     si, r8w
0x18001dc05  mov     word ptr [rdi], 603h
0x18001dc0a  mov     [rdi+2], eax
0x18001dc0d  add     rdi, r8
0x18001dc10  cmp     dword ptr [rbx], 0
0x18001dc13  jnz     short loc_18001DC72
0x18001dc15  cmp     dword ptr [rbx+28h], 0
0x18001dc19  jnz     short loc_18001DC2D
0x18001dc1b  mov     eax, [rbx+68h]
0x18001dc1e  add     si, r8w
0x18001dc22  mov     word ptr [rdi], 681h
0x18001dc27  mov     [rdi+2], eax
0x18001dc2a  add     rdi, r8
0x18001dc2d  cmp     dword ptr [rbx+2Ch], 0
0x18001dc31  jnz     short loc_18001DC45
0x18001dc33  mov     eax, [rbx+60h]
0x18001dc36  add     si, r8w
0x18001dc3a  mov     word ptr [rdi], 682h
0x18001dc3f  mov     [rdi+2], eax
0x18001dc42  add     rdi, r8
0x18001dc45  cmp     dword ptr [rbx+30h], 0
0x18001dc49  jnz     short loc_18001DC5D
0x18001dc4b  mov     eax, [rbx+6Ch]
0x18001dc4e  add     si, r8w
0x18001dc52  mov     word ptr [rdi], 683h
0x18001dc57  mov     [rdi+2], eax
0x18001dc5a  add     rdi, r8
0x18001dc5d  cmp     dword ptr [rbx+34h], 0
0x18001dc61  jnz     short loc_18001DC72
0x18001dc63  mov     eax, [rbx+64h]
0x18001dc66  add     si, r8w
0x18001dc6a  mov     word ptr [rdi], 684h
0x18001dc6f  mov     [rdi+2], eax
0x18001dc72  mov     [r14], r15b
0x18001dc75  movzx   eax, si
0x18001dc78  shr     ax, 8
0x18001dc7c  mov     [r14+2], al
0x18001dc80  mov     [r14+3], sil
0x18001dc84  test    rdx, rdx
0x18001dc87  jz      short loc_18001DCA3
0x18001dc89  mov     rcx, cs:gRasIpcpEtwContext
0x18001dc90  lea     r8, aIpcpConfigrequ; "IPCP: ConfigRequest..."
0x18001dc97  mov     rax, cs:gRasIpcpTemplateFunc
0x18001dc9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dca3  mov     rdx, cs:qword_18004C880
0x18001dcaa  test    rdx, rdx
0x18001dcad  jz      short loc_18001DCD2
0x18001dcaf  mov     rcx, cs:gRasIpcpEtwContext
0x18001dcb6  lea     r8, aDumpingBytesCo; "Dumping Bytes ConfigRequest"
0x18001dcbd  mov     rax, cs:gRasIpcpByteTemplateFunc
0x18001dcc4  movzx   r9d, si
0x18001dcc8  mov     [rsp+858h+var_838], r14
0x18001dccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dcd2  xor     eax, eax
0x18001dcd4  mov     rcx, [rsp+858h+var_28]
0x18001dcdc  xor     rcx, rsp; StackCookie
0x18001dcdf  call    __security_check_cookie
0x18001dce4  lea     r11, [rsp+858h+var_18]
0x18001dcec  mov     rbx, [r11+30h]
0x18001dcf0  mov     rsi, [r11+38h]
0x18001dcf4  mov     rsp, r11
0x18001dcf7  pop     r15
0x18001dcf9  pop     r14
0x18001dcfb  pop     rdi
0x18001dcfc  retn
```
