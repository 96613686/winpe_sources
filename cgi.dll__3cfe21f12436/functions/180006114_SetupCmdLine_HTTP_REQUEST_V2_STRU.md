# SetupCmdLine(_HTTP_REQUEST_V2 *,STRU *)

- ea: `0x180006114`
- end: `0x18000620b`
- name: `?SetupCmdLine@@YAJPEAU_HTTP_REQUEST_V2@@PEAVSTRU@@@Z`
- size: `247`
- prototype: `__int64 __fastcall(struct _HTTP_REQUEST_V2 *, struct STRU *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18000337c`

## callees

- `0x180006114`
- `0x180006e52`
- `0x180006e90`

## import_xrefs

- `msvcrt!wcschr` at `0x1800061b1`
- `msvcrt!wcschr` at `0x1800061b1`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x1800061cf`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x1800061cf`
- `iisutil!?Unescape@STRU@@QEAAJXZ` at `0x1800061c1`
- `iisutil!?Unescape@STRU@@QEAAJXZ` at `0x1800061c1`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180006186`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180006186`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006197`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800061de`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180006197`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800061de`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180006160`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180006160`

## pseudocode

```c
__int64 __fastcall SetupCmdLine(struct _HTTP_REQUEST_V2 *a1, struct STRU *a2)
{
  int v4; // ebx
  _BYTE v6[32]; // [rsp+20h] [rbp-268h] BYREF
  wchar_t *Str; // [rsp+40h] [rbp-248h]
  int v8; // [rsp+50h] [rbp-238h]
  unsigned __int16 v9[264]; // [rsp+60h] [rbp-228h] BYREF

  memset_0(v9, 0, 0x208u);
  STRU::STRU((STRU *)v6, v9, 0x104u);
  if ( a1->CookedUrl.QueryStringLength )
  {
    v4 = STRU::Copy((STRU *)v6, a1->CookedUrl.pQueryString + 1, (a1->CookedUrl.QueryStringLength >> 1) - 1);
    if ( v4 < 0 )
      goto LABEL_3;
  }
  if ( v8 && !wcschr(Str, 0x3Du) )
  {
    STRU::Unescape((STRU *)v6);
    v4 = STRU::Append(a2, (const struct STRU *)v6);
LABEL_3:
    STRU::~STRU((STRU *)v6);
    return (unsigned int)v4;
  }
  STRU::~STRU((STRU *)v6);
  return 0;
}

```

## disassembly

```asm
0x180006114  mov     [rsp+arg_10], rbx
0x180006119  mov     [rsp+arg_18], rsi
0x18000611e  push    rdi
0x18000611f  sub     rsp, 280h
0x180006126  mov     rax, cs:__security_cookie
0x18000612d  xor     rax, rsp
0x180006130  mov     [rsp+288h+var_18], rax
0x180006138  mov     rdi, rdx
0x18000613b  mov     rbx, rcx
0x18000613e  xor     edx, edx; Val
0x180006140  lea     rcx, [rsp+288h+var_228]; void *
0x180006145  mov     r8d, 208h; Size
0x18000614b  call    memset_0
0x180006150  mov     r8d, 104h
0x180006156  lea     rdx, [rsp+288h+var_228]
0x18000615b  lea     rcx, [rsp+288h+var_268]
0x180006160  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180006166  xor     esi, esi
0x180006168  cmp     [rbx+46h], si
0x18000616c  jbe     short loc_1800061A1
0x18000616e  movzx   r8d, word ptr [rbx+46h]
0x180006173  lea     rcx, [rsp+288h+var_268]
0x180006178  mov     rdx, [rbx+60h]
0x18000617c  shr     r8d, 1
0x18000617f  add     rdx, 2
0x180006183  dec     r8d
0x180006186  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18000618c  mov     ebx, eax
0x18000618e  test    eax, eax
0x180006190  jns     short loc_1800061A1
0x180006192  lea     rcx, [rsp+288h+var_268]
0x180006197  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000619d  mov     eax, ebx
0x18000619f  jmp     short loc_1800061E6
0x1800061a1  cmp     [rsp+288h+var_238], esi
0x1800061a5  jz      short loc_1800061D9
0x1800061a7  mov     rcx, [rsp+288h+Str]; Str
0x1800061ac  mov     edx, 3Dh ; '='; Ch
0x1800061b1  call    cs:__imp_wcschr
0x1800061b7  test    rax, rax
0x1800061ba  jnz     short loc_1800061D9
0x1800061bc  lea     rcx, [rsp+288h+var_268]
0x1800061c1  call    cs:__imp_?Unescape@STRU@@QEAAJXZ; STRU::Unescape(void)
0x1800061c7  lea     rdx, [rsp+288h+var_268]
0x1800061cc  mov     rcx, rdi
0x1800061cf  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x1800061d5  mov     ebx, eax
0x1800061d7  jmp     short loc_180006192
0x1800061d9  lea     rcx, [rsp+288h+var_268]
0x1800061de  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800061e4  xor     eax, eax
0x1800061e6  mov     rcx, [rsp+288h+var_18]
0x1800061ee  xor     rcx, rsp; StackCookie
0x1800061f1  call    __security_check_cookie
0x1800061f6  lea     r11, [rsp+288h+var_8]
0x1800061fe  mov     rbx, [r11+20h]
0x180006202  mov     rsi, [r11+28h]
0x180006206  mov     rsp, r11
0x180006209  pop     rdi
0x18000620a  retn
```
