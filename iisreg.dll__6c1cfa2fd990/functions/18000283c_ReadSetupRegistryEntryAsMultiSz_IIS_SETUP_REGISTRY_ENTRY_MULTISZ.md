# ReadSetupRegistryEntryAsMultiSz(IIS_SETUP_REGISTRY_ENTRY *,MULTISZ *)

- ea: `0x18000283c`
- end: `0x1800029bd`
- name: `?ReadSetupRegistryEntryAsMultiSz@@YAJPEAUIIS_SETUP_REGISTRY_ENTRY@@PEAVMULTISZ@@@Z`
- size: `385`
- prototype: `int(struct IIS_SETUP_REGISTRY_ENTRY *, struct MULTISZ *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x180001d7c`
- `0x18000200c`

## callees

- `0x180001afc`
- `0x18000283c`
- `0x180002ff8`
- `0x1800030b8`
- `0x1800033ac`
- `0x180003611`
- `0x180003650`

## import_xrefs

- `msvcrt!wcspbrk` at `0x180002918`
- `msvcrt!wcspbrk` at `0x180002941`
- `msvcrt!wcspbrk` at `0x180002918`
- `msvcrt!wcspbrk` at `0x180002941`
- `KERNEL32!GetLastError` at `0x180002967`
- `KERNEL32!GetLastError` at `0x180002967`

## pseudocode

```c
__int64 __fastcall ReadSetupRegistryEntryAsMultiSz(struct IIS_SETUP_REGISTRY_ENTRY *a1, struct MULTISZ *a2)
{
  const unsigned __int8 *v4; // rbx
  __int64 v5; // r8
  signed int v6; // ebx
  wchar_t *v7; // rax
  unsigned int v8; // r14d
  signed int LastError; // eax
  _BYTE v11[32]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *String; // [rsp+50h] [rbp-B0h]
  int v13; // [rsp+58h] [rbp-A8h]
  __int16 v14; // [rsp+5Ch] [rbp-A4h]
  unsigned int v15; // [rsp+60h] [rbp-A0h]
  __int16 v16; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v17[510]; // [rsp+72h] [rbp-8Eh] BYREF

  memset_0(v17, 0, sizeof(v17));
  v13 = 512;
  v14 = 256;
  String = (wchar_t *)&v16;
  v15 = 0;
  v16 = 0;
  if ( a1
    && a2
    && (v4 = (const unsigned __int8 *)*((_QWORD *)a1 + 5)) != 0
    && *((_QWORD *)a1 + 7)
    && ConvertStringToType(*((wchar_t **)a1 + 4)) == 7 )
  {
    v5 = -1;
    do
      ++v5;
    while ( *(_WORD *)&v4[2 * v5] );
    v6 = STRU::AuxAppend((STRU *)v11, v4, (unsigned int)(2 * v5), 0, 1);
    if ( v6 >= 0 )
    {
      v7 = wcspbrk(String, *((const wchar_t **)a1 + 7));
      v8 = v15;
      while ( v7 )
      {
        *v7 = 0;
        if ( (unsigned int)(v7 - String) >= v8 )
          break;
        v7 = wcspbrk(v7 + 1, *((const wchar_t **)a1 + 7));
      }
      if ( !(unsigned int)MULTISZ::AuxAppend(a2, String, 2 * v8, 1) )
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  else
  {
    v6 = -2147024809;
  }
  if ( (_BYTE)v14 )
    BUFFER::FreeMemoryInternal((BUFFER *)v11);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000283c  mov     [rsp-8+arg_10], rbx
0x180002841  push    rbp
0x180002842  push    rdi
0x180002843  push    r12
0x180002845  push    r14
0x180002847  push    r15
0x180002849  lea     rbp, [rsp-180h]
0x180002851  sub     rsp, 280h
0x180002858  mov     rax, cs:__security_cookie
0x18000285f  xor     rax, rsp
0x180002862  mov     [rbp+1A0h+var_30], rax
0x180002869  mov     r15, rdx
0x18000286c  mov     rdi, rcx
0x18000286f  xor     edx, edx; Val
0x180002871  lea     rcx, [rsp+2A0h+var_22E]; void *
0x180002876  mov     r8d, 1FEh; Size
0x18000287c  call    memset_0
0x180002881  xor     r12d, r12d
0x180002884  mov     [rsp+2A0h+var_248], 200h
0x18000288c  mov     [rsp+2A0h+var_244], 100h
0x180002893  lea     rax, [rsp+2A0h+var_230]
0x180002898  mov     [rsp+2A0h+String], rax
0x18000289d  mov     [rsp+2A0h+var_240], r12d
0x1800028a2  mov     [rsp+2A0h+var_230], r12w
0x1800028a8  test    rdi, rdi
0x1800028ab  jz      loc_18000297E
0x1800028b1  test    r15, r15
0x1800028b4  jz      loc_18000297E
0x1800028ba  mov     rbx, [rdi+28h]
0x1800028be  test    rbx, rbx
0x1800028c1  jz      loc_18000297E
0x1800028c7  cmp     [rdi+38h], r12
0x1800028cb  jz      loc_18000297E
0x1800028d1  mov     rcx, [rdi+20h]; String1
0x1800028d5  call    ?ConvertStringToType@@YAKPEAG@Z; ConvertStringToType(ushort *)
0x1800028da  cmp     eax, 7
0x1800028dd  jnz     loc_18000297E
0x1800028e3  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800028e7  inc     r8
0x1800028ea  cmp     [rbx+r8*2], r12w
0x1800028ef  jnz     short loc_1800028E7
0x1800028f1  add     r8d, r8d; Size
0x1800028f4  mov     [rsp+2A0h+var_280], 1; bool
0x1800028f9  xor     r9d, r9d; unsigned int
0x1800028fc  lea     rcx, [rsp+2A0h+var_270]; this
0x180002901  mov     rdx, rbx; Src
0x180002904  call    ?AuxAppend@STRU@@AEAAJPEBEKK_N@Z; STRU::AuxAppend(uchar const *,ulong,ulong,bool)
0x180002909  mov     ebx, eax
0x18000290b  test    eax, eax
0x18000290d  js      short loc_180002983
0x18000290f  mov     rdx, [rdi+38h]; Control
0x180002913  mov     rcx, [rsp+2A0h+String]; String
0x180002918  call    cs:__imp_wcspbrk
0x18000291e  mov     r14d, [rsp+2A0h+var_240]
0x180002923  jmp     short loc_180002947
0x180002925  mov     rcx, rax
0x180002928  mov     [rax], r12w
0x18000292c  sub     rcx, [rsp+2A0h+String]
0x180002931  sar     rcx, 1
0x180002934  cmp     ecx, r14d
0x180002937  jnb     short loc_18000294C
0x180002939  mov     rdx, [rdi+38h]; Control
0x18000293d  lea     rcx, [rax+2]; String
0x180002941  call    cs:__imp_wcspbrk
0x180002947  test    rax, rax
0x18000294a  jnz     short loc_180002925
0x18000294c  mov     rdx, [rsp+2A0h+String]; Src
0x180002951  lea     r8d, [r14+r14]; Size
0x180002955  mov     r9d, 1; int
0x18000295b  mov     rcx, r15; this
0x18000295e  call    ?AuxAppend@MULTISZ@@AEAAHPEBGIH@Z; MULTISZ::AuxAppend(ushort const *,uint,int)
0x180002963  test    eax, eax
0x180002965  jnz     short loc_180002983
0x180002967  call    cs:__imp_GetLastError
0x18000296d  mov     ebx, eax
0x18000296f  test    eax, eax
0x180002971  jle     short loc_180002983
0x180002973  movzx   ebx, ax
0x180002976  or      ebx, 80070000h
0x18000297c  jmp     short loc_180002983
0x18000297e  mov     ebx, 80070057h
0x180002983  cmp     byte ptr [rsp+2A0h+var_244], r12b
0x180002988  jz      short loc_180002994
0x18000298a  lea     rcx, [rsp+2A0h+var_270]; this
0x18000298f  call    ?FreeMemoryInternal@BUFFER@@AEAAXXZ; BUFFER::FreeMemoryInternal(void)
0x180002994  mov     eax, ebx
0x180002996  mov     rcx, [rbp+1A0h+var_30]
0x18000299d  xor     rcx, rsp; StackCookie
0x1800029a0  call    __security_check_cookie
0x1800029a5  mov     rbx, [rsp+2A0h+arg_10]
0x1800029ad  add     rsp, 280h
0x1800029b4  pop     r15
0x1800029b6  pop     r14
0x1800029b8  pop     r12
0x1800029ba  pop     rdi
0x1800029bb  pop     rbp
0x1800029bc  retn
```
