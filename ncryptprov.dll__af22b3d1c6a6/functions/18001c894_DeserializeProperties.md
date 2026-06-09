# DeserializeProperties

- ea: `0x18001c894`
- end: `0x18001cb93`
- name: `DeserializeProperties`
- size: `767`
- prototype: `__int64 __fastcall(__int64, _QWORD *, unsigned int, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180011678`

## callees

- `0x18000af80`
- `0x18000b250`
- `0x18001c894`
- `0x18002095c`
- `0x180038970`
- `0x1800398b0`
- `0x180039bf0`
- `0x180062310`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18001c9c9`
- `ntdll!RtlFreeHeap` at `0x18001c9c9`
- `ntdll!RtlAllocateHeap` at `0x18001c971`
- `ntdll!RtlAllocateHeap` at `0x18001c971`

## string_xrefs

- `0x18001cad8`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x18001cb2b`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x18001cb71`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`

## pseudocode

```c
__int64 __fastcall DeserializeProperties(__int64 a1, _QWORD *a2, unsigned int a3, int a4)
{
  _DWORD *v5; // rbx
  __int64 v6; // rbp
  size_t v7; // r15
  unsigned int v8; // r14d
  int v9; // r12d
  _DWORD *v10; // rdi
  wchar_t *v11; // r13
  wchar_t *Heap; // rax
  int v13; // edx
  size_t v14; // r8
  wchar_t *v15; // rdi
  size_t v16; // rdx
  wchar_t *v17; // rcx
  size_t *v18; // r8
  unsigned int v19; // ebx
  __int64 v21; // r9
  size_t v22; // [rsp+20h] [rbp-108h]
  int v23; // [rsp+40h] [rbp-E8h]
  __int64 v25; // [rsp+48h] [rbp-E0h]
  wchar_t pszSrc[72]; // [rsp+50h] [rbp-D8h] BYREF

  v5 = a2;
  v25 = a1;
  while ( 1 )
  {
    if ( !a3 )
      return 0;
    if ( a3 < 0x14 )
    {
      v21 = 2700;
      goto LABEL_35;
    }
    v6 = (unsigned int)v5[3];
    if ( (unsigned int)v6 > 0x80 )
      break;
    v7 = (unsigned int)v5[4];
    if ( (unsigned int)v7 > 0x100000 )
      break;
    v8 = v7 + v6 + 20;
    if ( a3 < v8 )
    {
      v21 = 2721;
LABEL_35:
      v19 = -2146893798;
      DebugTraceError(2148073498LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c", v21);
      return v19;
    }
    v9 = v5[1];
    if ( (_DWORD)v6 )
    {
      memset_0(pszSrc, 0, 0x82u);
      v10 = v5 + 5;
      memcpy_0(pszSrc, v5 + 5, (unsigned int)v6);
      a1 = v25;
      v11 = pszSrc;
    }
    else
    {
      v11 = 0;
      v10 = v5 + 5;
    }
    if ( v9 != 7 )
    {
      v23 = v5[2];
      Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v7 + 168);
      v15 = Heap;
      if ( Heap )
      {
        *(_DWORD *)Heap = v9;
        if ( !v11 )
        {
LABEL_19:
          *((_DWORD *)v15 + 34) = v7;
          *((_DWORD *)v15 + 35) = 0;
          *((_DWORD *)v15 + 36) = (v23 & 0xC0000000) != 0;
          memcpy_0(v15 + 84, (char *)v5 + v6 + 20, v7);
          *((_DWORD *)v15 + 36) = 1;
          *((_DWORD *)v15 + 37) = a4;
          a2 = *(_QWORD **)(v25 + 296);
          if ( *a2 != v25 + 288 )
            __fastfail(3u);
          *((_QWORD *)v15 + 19) = v25 + 288;
          *((_QWORD *)v15 + 20) = a2;
          *a2 = v15 + 76;
          *(_QWORD *)(v25 + 296) = v15 + 76;
          goto LABEL_21;
        }
        if ( StringValidateDestW(Heap + 2, 0x41u, v14) >= 0 )
        {
          if ( StringCopyWorkerW_0(v17, v16, v18, v11, v22) )
            goto LABEL_14;
          goto LABEL_19;
        }
        *v17 = 0;
LABEL_14:
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
        v19 = -2146893785;
      }
      else
      {
        v19 = -2146893810;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v13,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
          (unsigned int)"Status",
          v19,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
          195);
      return v19;
    }
    if ( v8 >= 0x18 )
      *(_DWORD *)(a1 + 28) = *v10;
LABEL_21:
    a1 = v25;
    v5 = (_DWORD *)((char *)v5 + v8);
    a3 -= v8;
  }
  v19 = -2146893798;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)a2,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
      (unsigned int)"Status",
      26,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
      150);
  return v19;
}

```

## disassembly

```asm
0x18001c894  mov     [rsp+arg_10], rbx
0x18001c899  push    rbp
0x18001c89a  push    rsi
0x18001c89b  push    rdi
0x18001c89c  push    r12
0x18001c89e  push    r13
0x18001c8a0  push    r14
0x18001c8a2  push    r15
0x18001c8a4  sub     rsp, 0F0h
0x18001c8ab  mov     rax, cs:__security_cookie
0x18001c8b2  xor     rax, rsp
0x18001c8b5  mov     [rsp+128h+var_48], rax
0x18001c8bd  mov     [rsp+128h+var_E4], r9d
0x18001c8c2  mov     esi, r8d
0x18001c8c5  mov     rbx, rdx
0x18001c8c8  mov     [rsp+128h+var_E0], rcx
0x18001c8cd  test    esi, esi
0x18001c8cf  jz      loc_18001CB41
0x18001c8d5  cmp     esi, 14h
0x18001c8d8  jb      loc_18001CB6B
0x18001c8de  mov     ebp, [rbx+0Ch]
0x18001c8e1  cmp     ebp, 80h
0x18001c8e7  ja      loc_18001CAFD
0x18001c8ed  mov     r15d, [rbx+10h]
0x18001c8f1  cmp     r15d, 100000h
0x18001c8f8  ja      loc_18001CAFD
0x18001c8fe  lea     r14d, [rbp+14h]
0x18001c902  add     r14d, r15d
0x18001c905  cmp     esi, r14d
0x18001c908  jb      loc_18001CB63
0x18001c90e  mov     r12d, [rbx+4]
0x18001c912  test    ebp, ebp
0x18001c914  jz      loc_18001CA25
0x18001c91a  xor     edx, edx; Val
0x18001c91c  lea     rcx, [rsp+128h+pszSrc]; void *
0x18001c921  mov     r8d, 82h; Size
0x18001c927  call    memset_0
0x18001c92c  lea     rdi, [rbx+14h]
0x18001c930  mov     r8d, ebp; Size
0x18001c933  mov     rdx, rdi; Src
0x18001c936  lea     rcx, [rsp+128h+pszSrc]; void *
0x18001c93b  call    memcpy_0
0x18001c940  mov     rcx, [rsp+128h+var_E0]
0x18001c945  lea     r13, [rsp+128h+pszSrc]
0x18001c94a  cmp     r12d, 7
0x18001c94e  jz      loc_18001CAC3
0x18001c954  mov     rcx, gs:60h
0x18001c95d  lea     r8, [r15+0A8h]; Size
0x18001c964  mov     eax, [rbx+8]
0x18001c967  xor     edx, edx; Flags
0x18001c969  mov     [rsp+128h+var_E8], eax
0x18001c96d  mov     rcx, [rcx+30h]; HeapHandle
0x18001c971  call    cs:__imp_RtlAllocateHeap
0x18001c978  nop     dword ptr [rax+rax+00h]
0x18001c97d  mov     rdi, rax
0x18001c980  test    rax, rax
0x18001c983  jz      loc_18001CB48
0x18001c989  mov     [rax], r12d
0x18001c98c  test    r13, r13
0x18001c98f  jz      loc_18001CA31
0x18001c995  mov     edx, 41h ; 'A'; cchDest
0x18001c99a  lea     rcx, [rax+4]; pszDest
0x18001c99e  call    StringValidateDestW
0x18001c9a3  test    eax, eax
0x18001c9a5  js      loc_18001CB52
0x18001c9ab  mov     r9, r13; pszSrc
0x18001c9ae  call    StringCopyWorkerW_0
0x18001c9b3  test    eax, eax
0x18001c9b5  jz      short loc_18001CA31
0x18001c9b7  mov     rcx, gs:60h
0x18001c9c0  mov     r8, rdi; P
0x18001c9c3  xor     edx, edx; Flags
0x18001c9c5  mov     rcx, [rcx+30h]; HeapHandle
0x18001c9c9  call    cs:__imp_RtlFreeHeap
0x18001c9d0  nop     dword ptr [rax+rax+00h]
0x18001c9d5  mov     ebx, 80090027h
0x18001c9da  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c9e1  lea     rax, WPP_GLOBAL_Control
0x18001c9e8  cmp     rcx, rax
0x18001c9eb  jz      short loc_18001C9F7
0x18001c9ed  test    byte ptr [rcx+1Ch], 1
0x18001c9f1  jnz     loc_18001CAD0
0x18001c9f7  mov     eax, ebx
0x18001c9f9  mov     rcx, [rsp+128h+var_48]
0x18001ca01  xor     rcx, rsp; StackCookie
0x18001ca04  call    __security_check_cookie
0x18001ca09  mov     rbx, [rsp+128h+arg_10]
0x18001ca11  add     rsp, 0F0h
0x18001ca18  pop     r15
0x18001ca1a  pop     r14
0x18001ca1c  pop     r13
0x18001ca1e  pop     r12
0x18001ca20  pop     rdi
0x18001ca21  pop     rsi
0x18001ca22  pop     rbp
0x18001ca23  retn
0x18001ca25  xor     r13d, r13d
0x18001ca28  lea     rdi, [rbx+14h]
0x18001ca2c  jmp     loc_18001C94A
0x18001ca31  test    [rsp+128h+var_E8], 0C0000000h
0x18001ca39  lea     rdx, [rbp+14h]
0x18001ca3d  mov     eax, 0
0x18001ca42  mov     [rdi+88h], r15d
0x18001ca49  setnz   al
0x18001ca4c  mov     dword ptr [rdi+8Ch], 0
0x18001ca56  add     rdx, rbx; Src
0x18001ca59  mov     [rdi+90h], eax
0x18001ca5f  lea     rcx, [rdi+0A8h]; void *
0x18001ca66  mov     r8, r15; Size
0x18001ca69  call    memcpy_0
0x18001ca6e  mov     rcx, [rsp+128h+var_E0]
0x18001ca73  mov     eax, [rsp+128h+var_E4]
0x18001ca77  add     rcx, 120h
0x18001ca7e  mov     dword ptr [rdi+90h], 1
0x18001ca88  mov     [rdi+94h], eax
0x18001ca8e  mov     rdx, [rcx+8]
0x18001ca92  cmp     [rdx], rcx
0x18001ca95  jnz     loc_18001CB5C
0x18001ca9b  lea     rax, [rdi+98h]
0x18001caa2  mov     [rax], rcx
0x18001caa5  mov     [rax+8], rdx
0x18001caa9  mov     [rdx], rax
0x18001caac  mov     [rcx+8], rax
0x18001cab0  mov     rcx, [rsp+128h+var_E0]
0x18001cab5  mov     eax, r14d
0x18001cab8  add     rbx, rax
0x18001cabb  sub     esi, r14d
0x18001cabe  jmp     loc_18001C8CD
0x18001cac3  cmp     r14d, 18h
0x18001cac7  jb      short loc_18001CAB0
0x18001cac9  mov     eax, [rdi]
0x18001cacb  mov     [rcx+1Ch], eax
0x18001cace  jmp     short loc_18001CAB0
0x18001cad0  mov     [rsp+128h+var_F8], 0AC3h
0x18001cad8  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001cadf  mov     [rsp+128h+var_100], r8
0x18001cae4  mov     dword ptr [rsp+128h+var_108], ebx
0x18001cae8  mov     rcx, [rcx+10h]
0x18001caec  lea     r9, aStatus; "Status"
0x18001caf3  call    WPP_SF_sDsd
0x18001caf8  jmp     loc_18001C9F7
0x18001cafd  mov     ebx, 8009001Ah
0x18001cb02  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cb09  lea     rax, WPP_GLOBAL_Control
0x18001cb10  cmp     rcx, rax
0x18001cb13  jz      loc_18001C9F7
0x18001cb19  test    byte ptr [rcx+1Ch], 1
0x18001cb1d  jz      loc_18001C9F7
0x18001cb23  mov     [rsp+128h+var_F8], 0A96h
0x18001cb2b  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001cb32  mov     [rsp+128h+var_100], r8
0x18001cb37  mov     dword ptr [rsp+128h+var_108], 8009001Ah
0x18001cb3f  jmp     short loc_18001CAE8
0x18001cb41  xor     ebx, ebx
0x18001cb43  jmp     loc_18001C9F7
0x18001cb48  mov     ebx, 8009000Eh
0x18001cb4d  jmp     loc_18001C9DA
0x18001cb52  xor     eax, eax
0x18001cb54  mov     [rcx], ax
0x18001cb57  jmp     loc_18001C9B7
0x18001cb5c  mov     ecx, 3
0x18001cb61  int     29h; Win8: RtlFailFast(ecx)
0x18001cb63  mov     r9d, 0AA1h
0x18001cb69  jmp     short loc_18001CB71
0x18001cb6b  mov     r9d, 0A8Ch
0x18001cb71  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001cb78  mov     ecx, 8009001Ah
0x18001cb7d  lea     rdx, aStatus; "Status"
0x18001cb84  mov     ebx, 8009001Ah
0x18001cb89  call    DebugTraceError
0x18001cb8e  jmp     loc_18001C9F7
```
