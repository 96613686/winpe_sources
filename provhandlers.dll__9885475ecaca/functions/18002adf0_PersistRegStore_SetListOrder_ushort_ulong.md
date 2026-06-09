# PersistRegStore::SetListOrder(ushort * *,ulong)

- ea: `0x18002adf0`
- end: `0x18002b039`
- name: `?SetListOrder@PersistRegStore@@UEAAJPEAPEAGK@Z`
- size: `585`
- prototype: `__int64 __fastcall(PersistRegStore *__hidden this, unsigned __int16 **, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180007ed4`
- `0x18002adf0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002ae2d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002ae2d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002aff3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002aff3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b010`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b019`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b010`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b019`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ae72`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002af71`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ae72`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002af71`

## pseudocode

```c
__int64 __fastcall PersistRegStore::SetListOrder(HKEY *this, unsigned __int16 **a2, unsigned int a3)
{
  unsigned __int16 **v4; // rbx
  BYTE *lpData; // r13
  _QWORD *v6; // r12
  LSTATUS v7; // eax
  signed int v8; // ebx
  unsigned __int64 v9; // rdx
  int v10; // r10d
  unsigned __int16 *v11; // r9
  _QWORD *v12; // rcx
  __int64 v13; // r8
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rdi
  unsigned __int64 v16; // rax
  DWORD cbData; // r14d
  BYTE *v18; // rax
  unsigned __int16 *v19; // r11
  unsigned int i; // ebp
  __int64 v21; // r11
  __int64 v22; // rdx

  v4 = a2;
  lpData = 0;
  v6 = 0;
  if ( a3 )
  {
    if ( !a2 )
    {
      v8 = -2147467261;
      goto LABEL_41;
    }
    v6 = LocalAlloc(0x40u, 8LL * a3);
    if ( !v6 )
      goto LABEL_9;
    v9 = 0;
    v10 = 0;
    if ( !a3 )
    {
LABEL_30:
      v15 = v9 + 1;
      if ( v9 + 1 < v9 || v15 > 0xFFFFFFFF || (v16 = 2LL * (unsigned int)v15, v16 > 0xFFFFFFFF) )
      {
LABEL_40:
        v8 = -2147024362;
        goto LABEL_41;
      }
      cbData = 2 * v15;
      v18 = (BYTE *)LocalAlloc(0x40u, (unsigned int)v16);
      lpData = v18;
      if ( v18 )
      {
        v8 = 0;
        v19 = (unsigned __int16 *)v18;
        for ( i = 0; i < a3; v19 = (unsigned __int16 *)(v21 + 2 * v22 + 2) )
        {
          v8 = StringCchCopyW(v19, v15, a2[i]);
          if ( v8 < 0 )
            goto LABEL_41;
          v22 = v6[i++];
          v15 += -1 - v22;
        }
        *v19 = 0;
        v7 = RegSetValueExW(this[2], L"PersistListOrder", 0, 7u, lpData, cbData);
        if ( !v7 )
          goto LABEL_41;
        if ( v7 <= 0 )
          goto LABEL_29;
LABEL_4:
        v8 = (unsigned __int16)v7 | 0x80070000;
        goto LABEL_41;
      }
LABEL_9:
      v8 = -2147024882;
      goto LABEL_41;
    }
    while ( 1 )
    {
      v11 = v4[v10];
      v12 = &v6[v10];
      if ( !v11 )
        break;
      v13 = 0x7FFFFFFF;
      do
      {
        if ( !*v11 )
          break;
        ++v11;
        --v13;
      }
      while ( v13 );
      v8 = v13 == 0 ? 0x80070057 : 0;
      if ( !v12 )
      {
        if ( v13 )
          goto LABEL_22;
        v7 = v13 == 0 ? 0x80070057 : 0;
        goto LABEL_21;
      }
      if ( !v13 )
      {
        *v12 = 0;
        v7 = -2147024809;
LABEL_28:
        *v12 = 0;
LABEL_29:
        v8 = v7;
        goto LABEL_41;
      }
      *v12 = 0x7FFFFFFF - v13;
LABEL_22:
      if ( v8 < 0 )
        goto LABEL_41;
      v14 = v9 + *v12;
      if ( v14 < v9 )
        goto LABEL_40;
      v9 = v14 + 1;
      if ( v14 + 1 < v14 )
        goto LABEL_40;
      if ( ++v10 >= a3 )
        goto LABEL_30;
      v4 = a2;
    }
    v8 = -2147024809;
    v7 = -2147024809;
LABEL_21:
    if ( v12 )
      goto LABEL_28;
    goto LABEL_22;
  }
  v7 = RegDeleteValueW(this[2], L"PersistListOrder");
  v8 = v7;
  if ( !v7 )
  {
    v8 = 0;
    goto LABEL_41;
  }
  if ( v7 > 0 )
    goto LABEL_4;
LABEL_41:
  LocalFree(lpData);
  LocalFree(v6);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002adf0  mov     [rsp+arg_10], rbx
0x18002adf5  mov     [rsp+arg_8], rdx
0x18002adfa  mov     [rsp+arg_0], rcx
0x18002adff  push    rbp
0x18002ae00  push    rsi
0x18002ae01  push    rdi
0x18002ae02  push    r12
0x18002ae04  push    r13
0x18002ae06  push    r14
0x18002ae08  push    r15
0x18002ae0a  sub     rsp, 30h
0x18002ae0e  xor     r15d, r15d
0x18002ae11  mov     esi, r8d
0x18002ae14  mov     rbx, rdx
0x18002ae17  mov     r13d, r15d
0x18002ae1a  mov     r12d, r15d
0x18002ae1d  test    r8d, r8d
0x18002ae20  jnz     short loc_18002AE55
0x18002ae22  mov     rcx, [rcx+10h]; hKey
0x18002ae26  lea     rdx, aPersistlistord; "PersistListOrder"
0x18002ae2d  call    cs:__imp_RegDeleteValueW
0x18002ae33  mov     ebx, eax
0x18002ae35  test    eax, eax
0x18002ae37  jz      short loc_18002AE4D
0x18002ae39  jle     loc_18002B00D
0x18002ae3f  movzx   ebx, ax
0x18002ae42  or      ebx, 80070000h
0x18002ae48  jmp     loc_18002B00D
0x18002ae4d  mov     ebx, r15d
0x18002ae50  jmp     loc_18002B00D
0x18002ae55  test    rdx, rdx
0x18002ae58  jnz     short loc_18002AE64
0x18002ae5a  mov     ebx, 80004003h
0x18002ae5f  jmp     loc_18002B00D
0x18002ae64  mov     rdx, rsi
0x18002ae67  mov     ebp, 40h ; '@'
0x18002ae6c  shl     rdx, 3; uBytes
0x18002ae70  mov     ecx, ebp; uFlags
0x18002ae72  call    cs:__imp_LocalAlloc
0x18002ae78  mov     r12, rax
0x18002ae7b  test    rax, rax
0x18002ae7e  jnz     short loc_18002AE8A
0x18002ae80  mov     ebx, 8007000Eh
0x18002ae85  jmp     loc_18002B00D
0x18002ae8a  mov     rdx, r15
0x18002ae8d  mov     r10d, r15d
0x18002ae90  test    esi, esi
0x18002ae92  jz      loc_18002AF41
0x18002ae98  mov     edi, 7FFFFFFFh
0x18002ae9d  mov     r11d, 80070057h
0x18002aea3  mov     eax, r10d
0x18002aea6  mov     r9, [rbx+rax*8]
0x18002aeaa  lea     rcx, [r12+rax*8]
0x18002aeae  test    r9, r9
0x18002aeb1  jz      short loc_18002AEF1
0x18002aeb3  mov     r8, rdi
0x18002aeb6  cmp     [r9], r15w
0x18002aeba  jz      short loc_18002AEC6
0x18002aebc  add     r9, 2
0x18002aec0  sub     r8, 1
0x18002aec4  jnz     short loc_18002AEB6
0x18002aec6  mov     rax, r8
0x18002aec9  neg     rax
0x18002aecc  sbb     ebx, ebx
0x18002aece  not     ebx
0x18002aed0  and     ebx, r11d
0x18002aed3  test    rcx, rcx
0x18002aed6  jz      short loc_18002AEE8
0x18002aed8  test    r8, r8
0x18002aedb  jz      short loc_18002AF32
0x18002aedd  mov     rax, rdi
0x18002aee0  sub     rax, r8
0x18002aee3  mov     [rcx], rax
0x18002aee6  jmp     short loc_18002AEFC
0x18002aee8  test    r8, r8
0x18002aeeb  jnz     short loc_18002AEFC
0x18002aeed  mov     eax, ebx
0x18002aeef  jmp     short loc_18002AEF7
0x18002aef1  mov     ebx, r11d
0x18002aef4  mov     eax, r11d
0x18002aef7  test    rcx, rcx
0x18002aefa  jnz     short loc_18002AF37
0x18002aefc  test    ebx, ebx
0x18002aefe  js      loc_18002B00D
0x18002af04  mov     rcx, [rcx]
0x18002af07  add     rcx, rdx
0x18002af0a  cmp     rcx, rdx
0x18002af0d  jb      loc_18002B008
0x18002af13  lea     rdx, [rcx+1]
0x18002af17  cmp     rdx, rcx
0x18002af1a  jb      loc_18002B008
0x18002af20  inc     r10d
0x18002af23  cmp     r10d, esi
0x18002af26  jnb     short loc_18002AF41
0x18002af28  mov     rbx, [rsp+68h+arg_8]
0x18002af2d  jmp     loc_18002AEA3
0x18002af32  mov     [rcx], r15
0x18002af35  mov     eax, ebx
0x18002af37  mov     [rcx], r15
0x18002af3a  mov     ebx, eax
0x18002af3c  jmp     loc_18002B00D
0x18002af41  lea     rdi, [rdx+1]
0x18002af45  cmp     rdi, rdx
0x18002af48  jb      loc_18002B008
0x18002af4e  mov     edx, 0FFFFFFFFh
0x18002af53  cmp     rdi, rdx
0x18002af56  ja      loc_18002B008
0x18002af5c  mov     eax, edi
0x18002af5e  add     rax, rax
0x18002af61  cmp     rax, rdx
0x18002af64  ja      loc_18002B008
0x18002af6a  mov     edx, eax; uBytes
0x18002af6c  mov     ecx, ebp; uFlags
0x18002af6e  mov     r14d, eax
0x18002af71  call    cs:__imp_LocalAlloc
0x18002af77  mov     r13, rax
0x18002af7a  test    rax, rax
0x18002af7d  jz      loc_18002AE80
0x18002af83  mov     ebx, r15d
0x18002af86  mov     r11, rax
0x18002af89  mov     ebp, r15d
0x18002af8c  test    esi, esi
0x18002af8e  jz      short loc_18002AFCC
0x18002af90  mov     rax, [rsp+68h+arg_8]
0x18002af95  mov     rdx, rdi; unsigned __int64
0x18002af98  mov     r15d, ebp
0x18002af9b  mov     rcx, r11; unsigned __int16 *
0x18002af9e  mov     r8, [rax+r15*8]; unsigned __int16 *
0x18002afa2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002afa7  mov     ebx, eax
0x18002afa9  test    eax, eax
0x18002afab  js      short loc_18002B00D
0x18002afad  mov     rdx, [r12+r15*8]
0x18002afb1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002afb5  sub     rcx, rdx
0x18002afb8  inc     ebp
0x18002afba  add     rdi, rcx
0x18002afbd  lea     r11, [r11+rdx*2]
0x18002afc1  add     r11, 2
0x18002afc5  cmp     ebp, esi
0x18002afc7  jb      short loc_18002AF90
0x18002afc9  xor     r15d, r15d
0x18002afcc  mov     rcx, [rsp+68h+arg_0]
0x18002afd1  lea     rdx, aPersistlistord; "PersistListOrder"
0x18002afd8  mov     [r11], r15w
0x18002afdc  mov     r9d, 7; dwType
0x18002afe2  mov     [rsp+68h+cbData], r14d; cbData
0x18002afe7  xor     r8d, r8d; Reserved
0x18002afea  mov     [rsp+68h+lpData], r13; lpData
0x18002afef  mov     rcx, [rcx+10h]; hKey
0x18002aff3  call    cs:__imp_RegSetValueExW
0x18002aff9  test    eax, eax
0x18002affb  jz      short loc_18002B00D
0x18002affd  jg      loc_18002AE3F
0x18002b003  jmp     loc_18002AF3A
0x18002b008  mov     ebx, 80070216h
0x18002b00d  mov     rcx, r13; hMem
0x18002b010  call    cs:__imp_LocalFree
0x18002b016  mov     rcx, r12; hMem
0x18002b019  call    cs:__imp_LocalFree
0x18002b01f  mov     eax, ebx
0x18002b021  mov     rbx, [rsp+68h+arg_10]
0x18002b029  add     rsp, 30h
0x18002b02d  pop     r15
0x18002b02f  pop     r14
0x18002b031  pop     r13
0x18002b033  pop     r12
0x18002b035  pop     rdi
0x18002b036  pop     rsi
0x18002b037  pop     rbp
0x18002b038  retn
```
