# IASCloneAttribute

- ea: `0x18000ae5c`
- end: `0x18000b023`
- name: `IASCloneAttribute`
- size: `455`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012740`

## callees

- `0x180001f26`
- `0x18000ae5c`
- `0x18000b02c`

## import_xrefs

- `msvcrt!strcpy_s` at `0x18000af5d`
- `msvcrt!strcpy_s` at `0x18000af5d`
- `msvcrt!wcscpy_s` at `0x18000af10`
- `msvcrt!wcscpy_s` at `0x18000af10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ae92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000aef7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000af40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000af74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000afae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ae92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000aef7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000af40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000af74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000afae`

## pseudocode

```c
_QWORD *__fastcall IASCloneAttribute(__int64 a1)
{
  int v3; // ebx
  _OWORD *v4; // rax
  _QWORD *v5; // rdi
  int v6; // eax
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // r14
  wchar_t *v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rax
  unsigned int v13; // r14d
  char *v14; // rax
  void *v15; // rax
  _OWORD *v16; // rcx
  _OWORD *v17; // rax

  if ( !a1 )
    return 0;
  v3 = 0;
  v4 = CoTaskMemAlloc(0x28u);
  v5 = v4;
  if ( !v4 )
    goto LABEL_4;
  *v4 = *(_OWORD *)a1;
  v4[1] = *(_OWORD *)(a1 + 16);
  *((_QWORD *)v4 + 4) = *(_QWORD *)(a1 + 32);
  v6 = *(_DWORD *)(a1 + 16);
  if ( v6 == 5 )
  {
    v7 = *(_QWORD *)(a1 + 32);
    if ( v7 )
    {
      v8 = -1;
      do
        ++v8;
      while ( *(_WORD *)(v7 + 2 * v8) );
      v9 = (unsigned int)(v8 + 1);
      v10 = (wchar_t *)CoTaskMemAlloc(2 * v9);
      v5[4] = v10;
      if ( v10 )
      {
        wcscpy_s(v10, (unsigned int)v9, *(const wchar_t **)(a1 + 32));
        v5[3] = 0;
LABEL_24:
        *(_DWORD *)v5 = 1;
        goto LABEL_25;
      }
    }
    else
    {
      v11 = *(_QWORD *)(a1 + 24);
      if ( !v11 )
        goto LABEL_24;
      v12 = -1;
      do
        ++v12;
      while ( *(_BYTE *)(v11 + v12) );
      v13 = v12 + 1;
      v14 = (char *)CoTaskMemAlloc((unsigned int)(v12 + 1));
      v5[3] = v14;
      if ( v14 )
      {
        strcpy_s(v14, v13, *(const char **)(a1 + 24));
        v5[4] = 0;
        goto LABEL_24;
      }
    }
  }
  else if ( v6 == 6 )
  {
    v15 = CoTaskMemAlloc(*(unsigned int *)(a1 + 24));
    v5[4] = v15;
    if ( v15 )
    {
      memcpy_0(v15, *(const void **)(a1 + 32), *(unsigned int *)(a1 + 24));
      goto LABEL_24;
    }
  }
  else
  {
    if ( v6 != 4 && v6 != 10 || !*(_QWORD *)(a1 + 24) )
      goto LABEL_24;
    v16 = CoTaskMemAlloc(0x80u);
    v5[3] = v16;
    if ( v16 )
    {
      v17 = *(_OWORD **)(a1 + 24);
      *v16 = *v17;
      v16[1] = v17[1];
      v16[2] = v17[2];
      v16[3] = v17[3];
      v16[4] = v17[4];
      v16[5] = v17[5];
      v16[6] = v17[6];
      v16[7] = v17[7];
      goto LABEL_24;
    }
  }
LABEL_4:
  v3 = -2147024882;
LABEL_25:
  if ( v3 < 0 )
  {
    IASFreeAttribute(v5);
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x18000ae5c  push    rbx
0x18000ae5e  push    rsi
0x18000ae5f  push    rdi
0x18000ae60  push    r14
0x18000ae62  push    r15
0x18000ae64  sub     rsp, 30h
0x18000ae68  mov     rsi, rcx
0x18000ae6b  xor     r15d, r15d
0x18000ae6e  test    rcx, rcx
0x18000ae71  jnz     short loc_18000AE81
0x18000ae73  xor     eax, eax
0x18000ae75  add     rsp, 30h
0x18000ae79  pop     r15
0x18000ae7b  pop     r14
0x18000ae7d  pop     rdi
0x18000ae7e  pop     rsi
0x18000ae7f  pop     rbx
0x18000ae80  retn
0x18000ae81  mov     ebx, r15d
0x18000ae84  mov     [rsp+58h+var_38], ebx
0x18000ae88  mov     [rsp+58h+var_30], r15
0x18000ae8d  mov     ecx, 28h ; '('; cb
0x18000ae92  call    cs:__imp_CoTaskMemAlloc
0x18000ae98  mov     rdi, rax
0x18000ae9b  mov     [rsp+58h+var_30], rax
0x18000aea0  test    rax, rax
0x18000aea3  jnz     short loc_18000AEB3
0x18000aea5  mov     ebx, 8007000Eh
0x18000aeaa  mov     [rsp+58h+var_38], ebx
0x18000aeae  jmp     loc_18000B00C
0x18000aeb3  movups  xmm0, xmmword ptr [rsi]
0x18000aeb6  movups  xmmword ptr [rax], xmm0
0x18000aeb9  movups  xmm1, xmmword ptr [rsi+10h]
0x18000aebd  movups  xmmword ptr [rax+10h], xmm1
0x18000aec1  movsd   xmm0, qword ptr [rsi+20h]
0x18000aec6  movsd   qword ptr [rax+20h], xmm0
0x18000aecb  mov     eax, [rsi+10h]
0x18000aece  cmp     eax, 5
0x18000aed1  jnz     loc_18000AF6C
0x18000aed7  mov     rcx, [rsi+20h]
0x18000aedb  test    rcx, rcx
0x18000aede  jz      short loc_18000AF1F
0x18000aee0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000aee4  inc     rax
0x18000aee7  cmp     [rcx+rax*2], r15w
0x18000aeec  jnz     short loc_18000AEE4
0x18000aeee  inc     eax
0x18000aef0  mov     r14d, eax
0x18000aef3  lea     rcx, [rax+rax]; cb
0x18000aef7  call    cs:__imp_CoTaskMemAlloc
0x18000aefd  mov     [rdi+20h], rax
0x18000af01  test    rax, rax
0x18000af04  jz      short loc_18000AEA5
0x18000af06  mov     r8, [rsi+20h]; Source
0x18000af0a  mov     edx, r14d; SizeInWords
0x18000af0d  mov     rcx, rax; Destination
0x18000af10  call    cs:__imp_wcscpy_s
0x18000af16  mov     [rdi+18h], r15
0x18000af1a  jmp     loc_18000B006
0x18000af1f  mov     rcx, [rsi+18h]
0x18000af23  test    rcx, rcx
0x18000af26  jz      loc_18000B006
0x18000af2c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000af30  inc     rax
0x18000af33  cmp     [rcx+rax], r15b
0x18000af37  jnz     short loc_18000AF30
0x18000af39  inc     eax
0x18000af3b  mov     r14d, eax
0x18000af3e  mov     ecx, eax; cb
0x18000af40  call    cs:__imp_CoTaskMemAlloc
0x18000af46  mov     [rdi+18h], rax
0x18000af4a  test    rax, rax
0x18000af4d  jz      loc_18000AEA5
0x18000af53  mov     r8, [rsi+18h]; Source
0x18000af57  mov     edx, r14d; SizeInBytes
0x18000af5a  mov     rcx, rax; Destination
0x18000af5d  call    cs:__imp_strcpy_s
0x18000af63  mov     [rdi+20h], r15
0x18000af67  jmp     loc_18000B006
0x18000af6c  cmp     eax, 6
0x18000af6f  jnz     short loc_18000AF99
0x18000af71  mov     ecx, [rsi+18h]; cb
0x18000af74  call    cs:__imp_CoTaskMemAlloc
0x18000af7a  mov     [rdi+20h], rax
0x18000af7e  test    rax, rax
0x18000af81  jz      loc_18000AEA5
0x18000af87  mov     r8d, [rsi+18h]; Size
0x18000af8b  mov     rdx, [rsi+20h]; Src
0x18000af8f  mov     rcx, rax; void *
0x18000af92  call    memcpy_0
0x18000af97  jmp     short loc_18000B006
0x18000af99  cmp     eax, 4
0x18000af9c  jz      short loc_18000AFA3
0x18000af9e  cmp     eax, 0Ah
0x18000afa1  jnz     short loc_18000B006
0x18000afa3  cmp     [rsi+18h], r15
0x18000afa7  jz      short loc_18000B006
0x18000afa9  mov     ecx, 80h; cb
0x18000afae  call    cs:__imp_CoTaskMemAlloc
0x18000afb4  mov     rcx, rax
0x18000afb7  mov     [rdi+18h], rax
0x18000afbb  test    rax, rax
0x18000afbe  jz      loc_18000AEA5
0x18000afc4  mov     rax, [rsi+18h]
0x18000afc8  movups  xmm0, xmmword ptr [rax]
0x18000afcb  movups  xmmword ptr [rcx], xmm0
0x18000afce  movups  xmm1, xmmword ptr [rax+10h]
0x18000afd2  movups  xmmword ptr [rcx+10h], xmm1
0x18000afd6  movups  xmm0, xmmword ptr [rax+20h]
0x18000afda  movups  xmmword ptr [rcx+20h], xmm0
0x18000afde  movups  xmm1, xmmword ptr [rax+30h]
0x18000afe2  movups  xmmword ptr [rcx+30h], xmm1
0x18000afe6  movups  xmm0, xmmword ptr [rax+40h]
0x18000afea  movups  xmmword ptr [rcx+40h], xmm0
0x18000afee  movups  xmm1, xmmword ptr [rax+50h]
0x18000aff2  movups  xmmword ptr [rcx+50h], xmm1
0x18000aff6  movups  xmm0, xmmword ptr [rax+60h]
0x18000affa  movups  xmmword ptr [rcx+60h], xmm0
0x18000affe  movups  xmm1, xmmword ptr [rax+70h]
0x18000b002  movups  xmmword ptr [rcx+70h], xmm1
0x18000b006  mov     dword ptr [rdi], 1
0x18000b00c  test    ebx, ebx
0x18000b00e  jns     short loc_18000B01B
0x18000b010  mov     rcx, rdi; pv
0x18000b013  call    IASFreeAttribute
0x18000b018  mov     rdi, r15
0x18000b01b  mov     rax, rdi
0x18000b01e  jmp     loc_18000AE75
```
