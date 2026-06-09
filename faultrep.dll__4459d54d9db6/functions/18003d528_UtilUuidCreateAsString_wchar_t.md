# UtilUuidCreateAsString(wchar_t *)

- ea: `0x18003d528`
- end: `0x18003d5d3`
- name: `?UtilUuidCreateAsString@@YAJPEA_W@Z`
- size: `171`
- prototype: `__int64 __fastcall(wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18003cc4c`

## callees

- `0x180002890`
- `0x18000e30c`
- `0x180038eac`
- `0x18003d528`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18003d578`
- `RPCRT4!UuidCreate` at `0x18003d578`

## string_xrefs

- `0x18003d558`: `onecore\windows\feedback\core\common\lib\utilitydownlevel.cpp`

## pseudocode

```c
__int64 __fastcall UtilUuidCreateAsString(wchar_t *a1)
{
  unsigned int v2; // ebx
  __int64 v3; // rdx
  RPC_STATUS v5; // eax
  __int64 v6; // r8
  UUID Uuid; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !a1 )
  {
    v2 = -2147024809;
    v3 = 1396;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\windows\\feedback\\core\\common\\lib\\utilitydownlevel.cpp",
      (const char *)v2,
      Uuid.Data1);
    return v2;
  }
  Uuid = 0;
  v5 = UuidCreate(&Uuid);
  v2 = v5;
  if ( v5 && v5 != 1824 )
  {
    if ( v5 > 0 )
      v2 = (unsigned __int16)v5 | 0x80070000;
    v3 = 1402;
    if ( (v2 & 0x80000000) == 0 )
      v2 = -2147467259;
    goto LABEL_3;
  }
  LOBYTE(v6) = 1;
  tlx::guid_to_string_lower<wchar_t>(a1, &Uuid, v6);
  return 0;
}

```

## disassembly

```asm
0x18003d528  mov     [rsp+arg_8], rbx
0x18003d52d  push    rdi
0x18003d52e  sub     rsp, 40h
0x18003d532  mov     rax, cs:__security_cookie
0x18003d539  xor     rax, rsp
0x18003d53c  mov     [rsp+48h+var_18], rax
0x18003d541  mov     rdi, rcx
0x18003d544  test    rcx, rcx
0x18003d547  jnz     short loc_18003D56B
0x18003d549  mov     ebx, 80070057h
0x18003d54e  mov     edx, 574h; void *
0x18003d553  mov     rcx, [rsp+48h]; this
0x18003d558  lea     r8, aOnecoreWindows_0; "onecore\\windows\\feedback\\core\\commo"...
0x18003d55f  mov     r9d, ebx; char *
0x18003d562  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d567  mov     eax, ebx
0x18003d569  jmp     short loc_18003D5BB
0x18003d56b  xorps   xmm0, xmm0
0x18003d56e  lea     rcx, [rsp+48h+Uuid]; Uuid
0x18003d573  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x18003d578  call    cs:__imp_UuidCreate
0x18003d57e  mov     ebx, eax
0x18003d580  test    eax, eax
0x18003d582  jz      short loc_18003D5A9
0x18003d584  cmp     eax, 720h
0x18003d589  jz      short loc_18003D5A9
0x18003d58b  test    eax, eax
0x18003d58d  jle     short loc_18003D598
0x18003d58f  movzx   ebx, ax
0x18003d592  or      ebx, 80070000h
0x18003d598  test    ebx, ebx
0x18003d59a  mov     eax, 80004005h
0x18003d59f  mov     edx, 57Ah
0x18003d5a4  cmovns  ebx, eax
0x18003d5a7  jmp     short loc_18003D553
0x18003d5a9  mov     r8b, 1
0x18003d5ac  lea     rdx, [rsp+48h+Uuid]
0x18003d5b1  mov     rcx, rdi
0x18003d5b4  call    ??$guid_to_string_lower@_W@tlx@@YAXPEA_WAEBU_GUID@@_N@Z; tlx::guid_to_string_lower<wchar_t>(wchar_t *,_GUID const &,bool)
0x18003d5b9  xor     eax, eax
0x18003d5bb  mov     rcx, [rsp+48h+var_18]
0x18003d5c0  xor     rcx, rsp; StackCookie
0x18003d5c3  call    __security_check_cookie
0x18003d5c8  mov     rbx, [rsp+48h+arg_8]
0x18003d5cd  add     rsp, 40h
0x18003d5d1  pop     rdi
0x18003d5d2  retn
```
