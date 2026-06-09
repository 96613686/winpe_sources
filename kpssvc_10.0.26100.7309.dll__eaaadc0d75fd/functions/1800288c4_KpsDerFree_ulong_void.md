# KpsDerFree(ulong,void *)

- ea: `0x1800288c4`
- end: `0x1800289f1`
- name: `?KpsDerFree@@YAXKPEAX@Z`
- size: `301`
- prototype: `void __fastcall(unsigned int, void *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x1800203ac`
- `0x1800285a0`
- `0x18002aae8`
- `0x18002b4e0`

## callees

- `0x18001ae38`
- `0x180026d9c`
- `0x1800288c4`
- `0x18002c458`

## import_xrefs

- `MSASN1!ASN1_CloseDecoder` at `0x1800289a7`
- `MSASN1!ASN1_CloseDecoder` at `0x1800289a7`
- `MSASN1!ASN1_FreeDecoded` at `0x180028987`
- `MSASN1!ASN1_FreeDecoded` at `0x180028987`
- `MSASN1!ASN1_CreateDecoder` at `0x180028934`
- `MSASN1!ASN1_CreateDecoder` at `0x180028934`

## pseudocode

```c
void __fastcall KpsDerFree(unsigned int a1, void *a2)
{
  unsigned int v2; // esi
  _QWORD *v5; // rcx
  unsigned int v6; // eax
  int v7; // r8d
  unsigned int v8; // ebx
  __int64 v9; // [rsp+58h] [rbp+10h] BYREF

  v2 = 0;
  v9 = 0;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids, a2);
    v5 = WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    v6 = ASN1_CreateDecoder(KRB5_Module, &v9, 0, 0);
    v8 = v6;
    if ( v6 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_dsd(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, v7, v6, 0, 80);
        v5 = WPP_GLOBAL_Control;
      }
      v2 = v8;
    }
    else
    {
      ASN1_FreeDecoded(v9, a2, a1);
      v5 = WPP_GLOBAL_Control;
    }
  }
  if ( v9 )
  {
    ASN1_CloseDecoder(v9);
    v5 = WPP_GLOBAL_Control;
  }
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x20) != 0 )
    WPP_SF_D(v5[2], 74, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids, v2);
}

```

## disassembly

```asm
0x1800288c4  mov     [rsp+arg_0], rbx
0x1800288c9  mov     [rsp+arg_10], rbp
0x1800288ce  push    rsi
0x1800288cf  push    rdi
0x1800288d0  push    r14
0x1800288d2  sub     rsp, 30h
0x1800288d6  xor     esi, esi
0x1800288d8  mov     rdi, rdx
0x1800288db  and     [rsp+48h+arg_8], rsi
0x1800288e0  mov     ebp, ecx
0x1800288e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800288e9  lea     r14, WPP_GLOBAL_Control
0x1800288f0  cmp     rcx, r14
0x1800288f3  jz      short loc_180028918
0x1800288f5  test    byte ptr [rcx+1Ch], 20h
0x1800288f9  jz      short loc_180028918
0x1800288fb  mov     rcx, [rcx+10h]
0x1800288ff  lea     edx, [rsi+48h]
0x180028902  mov     r9, rdi
0x180028905  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x18002890c  call    WPP_SF_q
0x180028911  mov     rcx, cs:WPP_GLOBAL_Control
0x180028918  test    rdi, rdi
0x18002891b  jz      short loc_18002899A
0x18002891d  mov     rcx, cs:KRB5_Module
0x180028924  lea     rdx, [rsp+48h+arg_8]
0x180028929  and     [rsp+48h+var_28], rsi
0x18002892e  xor     r9d, r9d
0x180028931  xor     r8d, r8d
0x180028934  call    cs:__imp_ASN1_CreateDecoder
0x18002893b  nop     dword ptr [rax+rax+00h]
0x180028940  mov     ebx, eax
0x180028942  test    eax, eax
0x180028944  jz      short loc_18002897C
0x180028946  mov     rcx, cs:WPP_GLOBAL_Control
0x18002894d  cmp     rcx, r14
0x180028950  jz      short loc_180028978
0x180028952  test    byte ptr [rcx+1Ch], 1
0x180028956  jz      short loc_180028978
0x180028958  mov     rcx, [rcx+10h]
0x18002895c  mov     edx, 49h ; 'I'
0x180028961  mov     r9d, eax
0x180028964  mov     [rsp+48h+var_20], 550h
0x18002896c  call    WPP_SF_dsd
0x180028971  mov     rcx, cs:WPP_GLOBAL_Control
0x180028978  mov     esi, ebx
0x18002897a  jmp     short loc_18002899A
0x18002897c  mov     rcx, [rsp+48h+arg_8]
0x180028981  mov     r8d, ebp
0x180028984  mov     rdx, rdi
0x180028987  call    cs:__imp_ASN1_FreeDecoded
0x18002898e  nop     dword ptr [rax+rax+00h]
0x180028993  mov     rcx, cs:WPP_GLOBAL_Control
0x18002899a  mov     rax, [rsp+48h+arg_8]
0x18002899f  test    rax, rax
0x1800289a2  jz      short loc_1800289BA
0x1800289a4  mov     rcx, rax
0x1800289a7  call    cs:__imp_ASN1_CloseDecoder
0x1800289ae  nop     dword ptr [rax+rax+00h]
0x1800289b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800289ba  cmp     rcx, r14
0x1800289bd  jz      short loc_1800289DD
0x1800289bf  test    byte ptr [rcx+1Ch], 20h
0x1800289c3  jz      short loc_1800289DD
0x1800289c5  mov     rcx, [rcx+10h]
0x1800289c9  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x1800289d0  mov     edx, 4Ah ; 'J'
0x1800289d5  mov     r9d, esi
0x1800289d8  call    WPP_SF_D
0x1800289dd  mov     rbx, [rsp+48h+arg_0]
0x1800289e2  mov     rbp, [rsp+48h+arg_10]
0x1800289e7  add     rsp, 30h
0x1800289eb  pop     r14
0x1800289ed  pop     rdi
0x1800289ee  pop     rsi
0x1800289ef  retn
```
