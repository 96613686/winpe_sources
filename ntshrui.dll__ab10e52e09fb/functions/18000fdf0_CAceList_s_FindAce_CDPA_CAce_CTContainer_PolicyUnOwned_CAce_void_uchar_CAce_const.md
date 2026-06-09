# CAceList::s_FindAce(CDPA<CAce,CTContainer_PolicyUnOwned<CAce>> &,void *,uchar,CAce const *)

- ea: `0x18000fdf0`
- end: `0x18000ff9a`
- name: `?s_FindAce@CAceList@@AEAAPEAVCAce@@AEAV?$CDPA@VCAce@@V?$CTContainer_PolicyUnOwned@VCAce@@@@@@PEAXEPEBV2@@Z`
- size: `426`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180059214`
- `0x180059a80`
- `0x18005a044`
- `0x18005a6d8`
- `0x18005ae40`
- `0x18005b360`
- `0x18005b5e4`
- `0x18005c4a4`

## callees

- `0x18000f7a0`
- `0x18000fdf0`
- `0x180026370`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ff17`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ff17`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000fe7c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000fee7`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000fe7c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000fee7`

## pseudocode

```c
__int64 __fastcall CAceList::s_FindAce(__int64 a1, _DWORD **a2, void *a3, char a4, __int64 a5)
{
  _DWORD *v5; // rdi
  int i; // ebx
  _DWORD *v10; // rsi
  __int64 v11; // rsi
  bool v12; // cl
  BOOL v13; // edx
  BOOL v14; // eax

  v5 = *a2;
  if ( *a2 )
    LODWORD(v5) = *v5;
  for ( i = 0; ; ++i )
  {
    if ( i >= (int)v5 )
      return 0;
    v10 = *a2;
    if ( qword_180095A20 == (__int64 (__fastcall *)(_QWORD, _QWORD))-1LL )
    {
      if ( !g_hinstCC )
      {
        DelayLoadCC();
        if ( !g_hinstCC )
        {
          qword_180095A20 = 0;
          goto LABEL_30;
        }
      }
      qword_180095A20 = (__int64 (__fastcall *)(_QWORD, _QWORD))GetProcAddress(g_hinstCC, (LPCSTR)0x14C);
    }
    if ( qword_180095A20 )
    {
      v11 = qword_180095A20(v10, i);
      goto LABEL_8;
    }
LABEL_30:
    v11 = 0;
LABEL_8:
    if ( a5 )
      break;
    if ( !*(_DWORD *)(v11 + 24) && (a4 == -1 || *(_BYTE *)(v11 + 1) == a4) )
    {
      v14 = EqualSid(*(PSID *)(v11 + 8), a3);
      goto LABEL_18;
    }
LABEL_19:
    ;
  }
  v12 = 0;
  if ( *(int *)(a5 + 28) < 0 && *(int *)(v11 + 28) < 0 )
  {
    v12 = EqualSid(*(PSID *)(a5 + 8), *(PSID *)(v11 + 8))
       && *(_DWORD *)(a5 + 28) == *(_DWORD *)(v11 + 28)
       && *(_DWORD *)(a5 + 4) == *(_DWORD *)(v11 + 4)
       && *(_BYTE *)(a5 + 1) == *(_BYTE *)(v11 + 1)
       && *(_BYTE *)a5 == *(_BYTE *)v11
       && *(_DWORD *)(a5 + 24) == *(_DWORD *)(v11 + 24);
    v13 = 0;
    if ( *(_QWORD *)(v11 + 16) )
      v13 = v12;
    if ( v13 )
      v12 = memcmp_0(*(const void **)(v11 + 16), *(const void **)(a5 + 16), *(unsigned int *)(v11 + 24)) == 0;
  }
  v14 = v12;
LABEL_18:
  if ( !v14 )
    goto LABEL_19;
  return v11;
}

```

## disassembly

```asm
0x18000fdf0  mov     [rsp+arg_8], rbx
0x18000fdf5  mov     [rsp+arg_10], rbp
0x18000fdfa  push    rdi
0x18000fdfb  push    r12
0x18000fdfd  push    r13
0x18000fdff  push    r14
0x18000fe01  push    r15
0x18000fe03  sub     rsp, 20h
0x18000fe07  mov     rdi, [rdx]
0x18000fe0a  xor     r15d, r15d
0x18000fe0d  movzx   r12d, r9b
0x18000fe11  mov     r13, r8
0x18000fe14  mov     r14, rdx
0x18000fe17  test    rdi, rdi
0x18000fe1a  jz      loc_18000FF37
0x18000fe20  mov     edi, [rdi]
0x18000fe22  mov     rbp, [rsp+48h+arg_20]
0x18000fe27  xor     ebx, ebx
0x18000fe29  mov     [rsp+48h+arg_0], rsi
0x18000fe2e  cmp     ebx, edi
0x18000fe30  jge     short loc_18000FEAE
0x18000fe32  cmp     cs:qword_180095A20, 0FFFFFFFFFFFFFFFFh
0x18000fe3a  mov     rsi, [r14]
0x18000fe3d  jz      loc_18000FEF4
0x18000fe43  mov     rax, cs:qword_180095A20
0x18000fe4a  test    rax, rax
0x18000fe4d  jz      loc_18000FF30
0x18000fe53  movsxd  rdx, ebx
0x18000fe56  mov     rcx, rsi
0x18000fe59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe5e  mov     rsi, rax
0x18000fe61  test    rbp, rbp
0x18000fe64  jz      short loc_18000FECE
0x18000fe66  xor     cl, cl
0x18000fe68  cmp     [rbp+1Ch], r15d
0x18000fe6c  jge     short loc_18000FEA3
0x18000fe6e  cmp     [rsi+1Ch], r15d
0x18000fe72  jge     short loc_18000FEA3
0x18000fe74  mov     rdx, [rsi+8]; pSid2
0x18000fe78  mov     rcx, [rbp+8]; pSid1
0x18000fe7c  call    cs:__imp_EqualSid
0x18000fe82  test    eax, eax
0x18000fe84  jnz     loc_18000FF3C
0x18000fe8a  xor     cl, cl
0x18000fe8c  mov     r9, [rsi+10h]
0x18000fe90  xor     edx, edx
0x18000fe92  test    r9, r9
0x18000fe95  movzx   eax, cl
0x18000fe98  cmovnz  edx, eax
0x18000fe9b  test    edx, edx
0x18000fe9d  jnz     loc_18000FF80
0x18000fea3  movzx   eax, cl
0x18000fea6  test    eax, eax
0x18000fea8  jnz     short loc_18000FEEF
0x18000feaa  inc     ebx
0x18000feac  jmp     short loc_18000FE2E
0x18000feae  mov     rax, r15
0x18000feb1  mov     rsi, [rsp+48h+arg_0]
0x18000feb6  mov     rbx, [rsp+48h+arg_8]
0x18000febb  mov     rbp, [rsp+48h+arg_10]
0x18000fec0  add     rsp, 20h
0x18000fec4  pop     r15
0x18000fec6  pop     r14
0x18000fec8  pop     r13
0x18000feca  pop     r12
0x18000fecc  pop     rdi
0x18000fecd  retn
0x18000fece  cmp     [rsi+18h], r15d
0x18000fed2  jnz     short loc_18000FEAA
0x18000fed4  cmp     r12b, 0FFh
0x18000fed8  jz      short loc_18000FEE0
0x18000feda  cmp     [rsi+1], r12b
0x18000fede  jnz     short loc_18000FEAA
0x18000fee0  mov     rcx, [rsi+8]; pSid1
0x18000fee4  mov     rdx, r13; pSid2
0x18000fee7  call    cs:__imp_EqualSid
0x18000feed  jmp     short loc_18000FEA6
0x18000feef  mov     rax, rsi
0x18000fef2  jmp     short loc_18000FEB1
0x18000fef4  cmp     cs:g_hinstCC, r15
0x18000fefb  jnz     short loc_18000FF0B
0x18000fefd  call    DelayLoadCC
0x18000ff02  cmp     cs:g_hinstCC, r15
0x18000ff09  jz      short loc_18000FF29
0x18000ff0b  mov     rcx, cs:g_hinstCC; hModule
0x18000ff12  mov     edx, 14Ch; lpProcName
0x18000ff17  call    cs:__imp_GetProcAddress
0x18000ff1d  mov     cs:qword_180095A20, rax
0x18000ff24  jmp     loc_18000FE43
0x18000ff29  mov     cs:qword_180095A20, r15
0x18000ff30  xor     esi, esi
0x18000ff32  jmp     loc_18000FE61
0x18000ff37  jmp     loc_18000FE22
0x18000ff3c  mov     eax, [rsi+1Ch]
0x18000ff3f  cmp     [rbp+1Ch], eax
0x18000ff42  jnz     loc_18000FE8A
0x18000ff48  mov     eax, [rsi+4]
0x18000ff4b  cmp     [rbp+4], eax
0x18000ff4e  jnz     loc_18000FE8A
0x18000ff54  movzx   eax, byte ptr [rsi+1]
0x18000ff58  cmp     [rbp+1], al
0x18000ff5b  jnz     loc_18000FE8A
0x18000ff61  movzx   eax, byte ptr [rsi]
0x18000ff64  cmp     [rbp+0], al
0x18000ff67  jnz     loc_18000FE8A
0x18000ff6d  mov     eax, [rsi+18h]
0x18000ff70  cmp     [rbp+18h], eax
0x18000ff73  jnz     loc_18000FE8A
0x18000ff79  mov     cl, 1
0x18000ff7b  jmp     loc_18000FE8C
0x18000ff80  mov     r8d, [rsi+18h]; Size
0x18000ff84  mov     rcx, r9; Buf1
0x18000ff87  mov     rdx, [rbp+10h]; Buf2
0x18000ff8b  call    memcmp_0
0x18000ff90  test    eax, eax
0x18000ff92  setz    cl
0x18000ff95  jmp     loc_18000FEA3
```
