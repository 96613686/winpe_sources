# _CryptGetAppContainerUserPath

- ea: `0x180017500`
- end: `0x180017649`
- name: `_CryptGetAppContainerUserPath`
- size: `329`
- prototype: `_WORD *__fastcall(_WORD *Src)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180006710`

## callees

- `0x180005940`
- `0x180017500`
- `0x180026552`
- `0x1800265b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017637`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017637`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180017543`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180017543`

## pseudocode

```c
_WORD *__fastcall CryptGetAppContainerUserPath(_WORD *Src)
{
  _WORD *v2; // r15
  int BasicProfileFolderPath; // eax
  __int64 v4; // rcx
  _WORD *v5; // rax
  signed int v6; // ecx
  _WORD *v7; // rdi
  _WORD *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r14
  __int64 v11; // rax
  __int64 v12; // rsi
  _WORD *v13; // rax
  _BYTE Srca[784]; // [rsp+20h] [rbp-338h] BYREF

  v2 = 0;
  BasicProfileFolderPath = GetBasicProfileFolderPath(6, 0, Srca, 388);
  if ( BasicProfileFolderPath < 0 )
  {
    v6 = BasicProfileFolderPath;
LABEL_21:
    SetLastError(v6);
    return v2;
  }
  v4 = 388;
  v5 = Srca;
  while ( *v5 )
  {
    ++v5;
    if ( !--v4 )
      goto LABEL_5;
  }
  v7 = 0;
  if ( Src )
    v7 = Src;
  if ( !v7 )
  {
LABEL_5:
    v6 = -2147024809;
    goto LABEL_21;
  }
  v8 = v7;
  v9 = 260;
  v10 = 388 - v4;
  while ( *v8 )
  {
    ++v8;
    if ( !--v9 )
    {
      v11 = 0;
      v6 = -2147024809;
      v12 = 0;
      goto LABEL_14;
    }
  }
  v12 = 2 * (260 - v9);
  v11 = 260 - v9;
  v6 = 0;
LABEL_14:
  if ( v6 < 0 )
    goto LABEL_21;
  v13 = (_WORD *)PkiNonzeroAlloc(2 * (v11 + v10) + 4);
  v2 = v13;
  if ( v13 )
  {
    memcpy_0(v13, Srca, 2 * v10);
    if ( *v7 != 92 )
      v2[v10++] = 92;
    memcpy_0(&v2[v10], v7, v12 + 2);
  }
  return v2;
}

```

## disassembly

```asm
0x180017500  mov     [rsp+arg_8], rbx
0x180017505  mov     [rsp+arg_10], rsi
0x18001750a  push    rdi
0x18001750b  push    r14
0x18001750d  push    r15
0x18001750f  sub     rsp, 340h
0x180017516  mov     rax, cs:__security_cookie
0x18001751d  xor     rax, rsp
0x180017520  mov     [rsp+358h+var_28], rax
0x180017528  mov     rbx, rcx
0x18001752b  lea     r8, [rsp+358h+Src]
0x180017530  mov     r14d, 184h
0x180017536  xor     r15d, r15d
0x180017539  mov     r9d, r14d
0x18001753c  xor     edx, edx
0x18001753e  mov     ecx, 6
0x180017543  call    cs:__imp_GetBasicProfileFolderPath
0x180017549  test    eax, eax
0x18001754b  js      loc_180017635
0x180017551  mov     ecx, r14d
0x180017554  lea     rax, [rsp+358h+Src]
0x180017559  nop     dword ptr [rax+00000000h]
0x180017560  cmp     [rax], r15w
0x180017564  jz      short loc_18001757A
0x180017566  add     rax, 2
0x18001756a  sub     rcx, 1
0x18001756e  jnz     short loc_180017560
0x180017570  mov     ecx, 80070057h
0x180017575  jmp     loc_180017637
0x18001757a  xor     edi, edi
0x18001757c  test    rbx, rbx
0x18001757f  cmovnz  rdi, rbx
0x180017583  test    rdi, rdi
0x180017586  jz      short loc_180017570
0x180017588  mov     esi, 104h
0x18001758d  mov     rax, rdi
0x180017590  mov     edx, esi
0x180017592  sub     r14, rcx
0x180017595  cmp     [rax], r15w
0x180017599  jz      short loc_1800175B0
0x18001759b  add     rax, 2
0x18001759f  sub     rdx, 1
0x1800175a3  jnz     short loc_180017595
0x1800175a5  xor     eax, eax
0x1800175a7  mov     ecx, 80070057h
0x1800175ac  xor     esi, esi
0x1800175ae  jmp     short loc_1800175BE
0x1800175b0  mov     rax, rsi
0x1800175b3  sub     rsi, rdx
0x1800175b6  add     rsi, rsi
0x1800175b9  sub     rax, rdx
0x1800175bc  xor     ecx, ecx
0x1800175be  test    ecx, ecx
0x1800175c0  js      short loc_180017637
0x1800175c2  lea     rcx, [rax+r14]
0x1800175c6  lea     rcx, ds:4[rcx*2]; uBytes
0x1800175ce  call    PkiNonzeroAlloc
0x1800175d3  mov     r15, rax
0x1800175d6  test    rax, rax
0x1800175d9  jz      short loc_180017609
0x1800175db  lea     rbx, [r14+r14]
0x1800175df  mov     rcx, rax; void *
0x1800175e2  mov     r8, rbx; Size
0x1800175e5  lea     rdx, [rsp+358h+Src]; Src
0x1800175ea  call    memcpy_0
0x1800175ef  mov     eax, 5Ch ; '\'
0x1800175f4  cmp     ax, [rdi]
0x1800175f7  jnz     short loc_18001763F
0x1800175f9  lea     r8, [rsi+2]; Size
0x1800175fd  mov     rdx, rdi; Src
0x180017600  lea     rcx, [r15+r14*2]; void *
0x180017604  call    memcpy_0
0x180017609  mov     rax, r15
0x18001760c  mov     rcx, [rsp+358h+var_28]
0x180017614  xor     rcx, rsp; StackCookie
0x180017617  call    __security_check_cookie
0x18001761c  lea     r11, [rsp+358h+var_18]
0x180017624  mov     rbx, [r11+28h]
0x180017628  mov     rsi, [r11+30h]
0x18001762c  mov     rsp, r11
0x18001762f  pop     r15
0x180017631  pop     r14
0x180017633  pop     rdi
0x180017634  retn
0x180017635  mov     ecx, eax; dwErrCode
0x180017637  call    cs:__imp_SetLastError
0x18001763d  jmp     short loc_180017609
0x18001763f  mov     [rbx+r15], ax
0x180017644  inc     r14
0x180017647  jmp     short loc_1800175F9
```
