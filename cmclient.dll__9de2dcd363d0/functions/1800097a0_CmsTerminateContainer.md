# CmsTerminateContainer

- ea: `0x1800097a0`
- end: `0x1800097f4`
- name: `CmsTerminateContainer`
- size: `84`
- prototype: `__int64 __fastcall(__int64, int, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180002e8c`
- `0x1800066e4`
- `0x1800097a0`

## string_xrefs

- `0x1800097d4`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsTerminateContainer(__int64 a1, int a2, int a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v8; // [rsp+30h] [rbp+8h] BYREF
  int v9; // [rsp+38h] [rbp+10h] BYREF
  int v10; // [rsp+40h] [rbp+18h] BYREF

  v10 = a3;
  v9 = a2;
  v8 = *(_QWORD *)(a1 + 24);
  v3 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,enum _CMS_CLIENT_REQUESTED_TERMINATE_REASON,enum _CMS_TERMINATE_FLAGS),void *,enum _CMS_CLIENT_REQUESTED_TERMINATE_REASON &,enum _CMS_TERMINATE_FLAGS &>(
         a1,
         &v8,
         &v9,
         &v10);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x18A,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
    (const char *)(unsigned int)v3,
    v6);
  return v4;
}

```

## disassembly

```asm
0x1800097a0  mov     r11, rsp
0x1800097a3  mov     [r11+18h], r8d
0x1800097a7  mov     [rsp+arg_8], edx
0x1800097ab  push    rbx; int
0x1800097ac  sub     rsp, 20h
0x1800097b0  mov     rax, [rcx+18h]
0x1800097b4  lea     r9, [r11+18h]
0x1800097b8  lea     r8, [r11+10h]
0x1800097bc  mov     [r11+8], rax
0x1800097c0  lea     rdx, [r11+8]
0x1800097c4  call    ??$InvokeStubFunction@P6AJPEAXW4_CMS_CLIENT_REQUESTED_TERMINATE_REASON@@W4_CMS_TERMINATE_FLAGS@@@ZPEAXAEAW41@AEAW42@@Rpc@Manager@Container@@YAJP6AJPEAXW4_CMS_CLIENT_REQUESTED_TERMINATE_REASON@@W4_CMS_TERMINATE_FLAGS@@@Z$$QEAPEAXAEAW43@AEAW44@@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_CLIENT_REQUESTED_TERMINATE_REASON,_CMS_TERMINATE_FLAGS),void *,_CMS_CLIENT_REQUESTED_TERMINATE_REASON &,_CMS_TERMINATE_FLAGS &>(long (*)(void *,_CMS_CLIENT_REQUESTED_TERMINATE_REASON,_CMS_TERMINATE_FLAGS),void * &&,_CMS_CLIENT_REQUESTED_TERMINATE_REASON &,_CMS_TERMINATE_FLAGS &)
0x1800097c9  mov     ebx, eax
0x1800097cb  test    eax, eax
0x1800097cd  jns     short loc_1800097EC
0x1800097cf  mov     rcx, [rsp+28h]; this
0x1800097d4  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x1800097db  mov     r9d, eax; char *
0x1800097de  mov     edx, 18Ah; void *
0x1800097e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800097e8  mov     eax, ebx
0x1800097ea  jmp     short loc_1800097EE
0x1800097ec  xor     eax, eax
0x1800097ee  add     rsp, 20h
0x1800097f2  pop     rbx
0x1800097f3  retn
```
