# CUSTOM_ERROR_HANDLER::WriteDetailedLogonUserMethod(ulong,IHttpUser *,ushort const *,STRU *,ushort const * *)

- ea: `0x18000650c`
- end: `0x1800065e9`
- name: `?WriteDetailedLogonUserMethod@CUSTOM_ERROR_HANDLER@@AEAAJKPEAVIHttpUser@@PEBGPEAVSTRU@@PEAPEBG@Z`
- size: `221`
- prototype: `__int64 __fastcall(CUSTOM_ERROR_HANDLER *__hidden this, unsigned int, struct IHttpUser *, const unsigned __int16 *, struct STRU *, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x180005988`

## callees

- `0x18000650c`
- `0x180008010`

## import_xrefs

- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x18000655d`
- `iisutil!?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z` at `0x18000655d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800065c7`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800065c7`
- `iisutil!?HTMLEncode@STRU@@QEAAJXZ` at `0x1800065d6`
- `iisutil!?HTMLEncode@STRU@@QEAAJXZ` at `0x1800065d6`

## pseudocode

```c
int __fastcall CUSTOM_ERROR_HANDLER::WriteDetailedLogonUserMethod(
        const char **this,
        __int64 a2,
        struct IHttpUser *a3,
        const unsigned __int16 *a4,
        struct STRU *a5,
        const unsigned __int16 **a6)
{
  const unsigned __int16 *v6; // rdi
  int result; // eax
  __int64 v9; // rbx
  __int64 v10; // rax
  const unsigned __int16 *v11; // rax
  const unsigned __int16 **v12; // rcx
  unsigned int v13; // [rsp+58h] [rbp+10h] BYREF
  const unsigned __int16 *v14; // [rsp+60h] [rbp+18h] BYREF

  v6 = a4;
  v14 = 0;
  v13 = 0;
  if ( a3 )
  {
    result = LANG_STRING::GetString((LANG_STRING *)CUSTOM_ERROR_HANDLER::sm_pLangString, 0x2F8Cu, this[4], &v14, &v13);
    if ( result < 0 )
      return result;
    v9 = -1;
    v6 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IHttpUser *))(*(_QWORD *)a3 + 8LL))(a3);
    v10 = -1;
    do
      ++v10;
    while ( v6[v10] );
    if ( !v10 )
      v6 = v14;
    v11 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct IHttpUser *))(*(_QWORD *)a3 + 16LL))(a3);
    v12 = a6;
    *a6 = v11;
    do
      ++v9;
    while ( v11[v9] );
    if ( !v9 )
      *v12 = v14;
  }
  else
  {
    *a6 = a4;
  }
  result = STRU::Copy(a5, v6);
  if ( result >= 0 )
    return STRU::HTMLEncode(a5);
  return result;
}

```

## disassembly

```asm
0x18000650c  mov     rax, rsp
0x18000650f  mov     [rax+8], rbx
0x180006513  mov     [rax+10h], edx
0x180006516  push    rbp
0x180006517  push    rsi
0x180006518  push    rdi
0x180006519  sub     rsp, 30h
0x18000651d  xor     ebp, ebp
0x18000651f  mov     rdi, r9
0x180006522  mov     [rax+18h], rbp
0x180006526  mov     rsi, r8
0x180006529  mov     [rax+10h], ebp
0x18000652c  test    r8, r8
0x18000652f  jnz     short loc_18000653E
0x180006531  mov     rax, [rsp+48h+arg_28]
0x180006536  mov     [rax], r9
0x180006539  jmp     loc_1800065BF
0x18000653e  mov     r8, [rcx+20h]
0x180006542  lea     rax, [rsp+48h+arg_8]
0x180006547  mov     rcx, cs:?sm_pLangString@CUSTOM_ERROR_HANDLER@@2PEAVLANG_STRING@@EA; LANG_STRING * CUSTOM_ERROR_HANDLER::sm_pLangString
0x18000654e  lea     r9, [rsp+48h+arg_10]
0x180006553  mov     edx, 2F8Ch
0x180006558  mov     [rsp+48h+var_28], rax
0x18000655d  call    cs:__imp_?GetString@LANG_STRING@@QEAAJIPEBDPEAPEBGPEAK@Z; LANG_STRING::GetString(uint,char const *,ushort const * *,ulong *)
0x180006563  test    eax, eax
0x180006565  js      short loc_1800065DC
0x180006567  mov     rax, [rsi]
0x18000656a  mov     rcx, rsi
0x18000656d  mov     rax, [rax+8]
0x180006571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006576  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000657a  mov     rdi, rax
0x18000657d  mov     rax, rbx
0x180006580  inc     rax
0x180006583  cmp     [rdi+rax*2], bp
0x180006587  jnz     short loc_180006580
0x180006589  test    rax, rax
0x18000658c  mov     rcx, rsi
0x18000658f  mov     rax, [rsi]
0x180006592  cmovz   rdi, [rsp+48h+arg_10]
0x180006598  mov     rax, [rax+10h]
0x18000659c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065a1  mov     rcx, [rsp+48h+arg_28]
0x1800065a6  mov     [rcx], rax
0x1800065a9  inc     rbx
0x1800065ac  cmp     [rax+rbx*2], bp
0x1800065b0  jnz     short loc_1800065A9
0x1800065b2  test    rbx, rbx
0x1800065b5  jnz     short loc_1800065BF
0x1800065b7  mov     rax, [rsp+48h+arg_10]
0x1800065bc  mov     [rcx], rax
0x1800065bf  mov     rcx, [rsp+48h+arg_20]
0x1800065c4  mov     rdx, rdi
0x1800065c7  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800065cd  test    eax, eax
0x1800065cf  js      short loc_1800065DC
0x1800065d1  mov     rcx, [rsp+48h+arg_20]
0x1800065d6  call    cs:__imp_?HTMLEncode@STRU@@QEAAJXZ; STRU::HTMLEncode(void)
0x1800065dc  mov     rbx, [rsp+48h+arg_0]
0x1800065e1  add     rsp, 30h
0x1800065e5  pop     rdi
0x1800065e6  pop     rsi
0x1800065e7  pop     rbp
0x1800065e8  retn
```
