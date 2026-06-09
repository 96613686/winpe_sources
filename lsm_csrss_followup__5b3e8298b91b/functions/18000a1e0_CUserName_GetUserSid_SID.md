# CUserName::GetUserSid(_SID * *)

- ea: `0x18000a1e0`
- end: `0x18000a29c`
- name: `?GetUserSid@CUserName@@UEAAJPEAPEAU_SID@@@Z`
- size: `188`
- prototype: `__int64 __fastcall(CUserName *__hidden this, struct _SID **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800074c0`
- `0x180008b20`
- `0x18000a1e0`
- `0x18009404c`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18000a209`
- `ntdll!RtlLengthSid` at `0x18000a209`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a213`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a213`

## string_xrefs

- `0x18000a27d`: `No token`
- `0x18000a25e`: `CUserName::GetUserSid`

## pseudocode

```c
__int64 __fastcall CUserName::GetUserSid(CUserName *this, struct _SID **a2)
{
  int v2; // eax
  ULONG v5; // edi
  struct _SID *v6; // rax
  int v8; // eax
  unsigned int v9; // edi

  v2 = *((_DWORD *)this + 400);
  if ( (v2 & 2) == 0 )
  {
    if ( (v2 & 1) == 0 )
    {
      _DbgPrintMessage(8, "No token");
      return 2147943408LL;
    }
    v8 = CUserName::InitializeUserName(this, *((void **)this + 199));
    v9 = v8;
    if ( v8 < 0 )
    {
      _DbgPrintMessage(8, "InitializeUserName failed: 0x%x in %s", v8, "CUserName::GetUserSid");
      return v9;
    }
  }
  v5 = RtlLengthSid(**((PSID **)this + 201));
  v6 = (struct _SID *)CoTaskMemAlloc(v5);
  if ( !v6 )
    return 2147942414LL;
  *a2 = v6;
  memcpy_0(v6, **((const void ***)this + 201), v5);
  return 0;
}

```

## disassembly

```asm
0x18000a1e0  mov     [rsp+arg_0], rbx
0x18000a1e5  mov     [rsp+arg_8], rsi
0x18000a1ea  push    rdi
0x18000a1eb  sub     rsp, 20h
0x18000a1ef  mov     eax, [rcx+640h]
0x18000a1f5  mov     rsi, rdx
0x18000a1f8  mov     rbx, rcx
0x18000a1fb  test    al, 2
0x18000a1fd  jz      short loc_18000A248
0x18000a1ff  mov     rcx, [rbx+648h]
0x18000a206  mov     rcx, [rcx]; Sid
0x18000a209  call    cs:__imp_RtlLengthSid
0x18000a20f  mov     ecx, eax; cb
0x18000a211  mov     edi, eax
0x18000a213  call    cs:__imp_CoTaskMemAlloc
0x18000a219  test    rax, rax
0x18000a21c  jz      short loc_18000A295
0x18000a21e  mov     [rsi], rax
0x18000a221  mov     r8d, edi; Size
0x18000a224  mov     rdx, [rbx+648h]
0x18000a22b  mov     rcx, rax; void *
0x18000a22e  mov     rdx, [rdx]; Src
0x18000a231  call    memcpy_0
0x18000a236  xor     eax, eax
0x18000a238  mov     rbx, [rsp+28h+arg_0]
0x18000a23d  mov     rsi, [rsp+28h+arg_8]
0x18000a242  add     rsp, 20h
0x18000a246  pop     rdi
0x18000a247  retn
0x18000a248  test    al, 1
0x18000a24a  jz      short loc_18000A27D
0x18000a24c  mov     rdx, [rcx+638h]; void *
0x18000a253  call    ?InitializeUserName@CUserName@@AEAAJPEAX@Z; CUserName::InitializeUserName(void *)
0x18000a258  mov     edi, eax
0x18000a25a  test    eax, eax
0x18000a25c  jns     short loc_18000A1FF
0x18000a25e  lea     r9, aCusernameGetus_0; "CUserName::GetUserSid"
0x18000a265  mov     r8d, eax
0x18000a268  lea     rdx, aInitializeuser; "InitializeUserName failed: 0x%x in %s"
0x18000a26f  mov     ecx, 8; int
0x18000a274  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000a279  mov     eax, edi
0x18000a27b  jmp     short loc_18000A238
0x18000a27d  lea     rdx, aNoToken; "No token"
0x18000a284  mov     ecx, 8; int
0x18000a289  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000a28e  mov     eax, 800703F0h
0x18000a293  jmp     short loc_18000A238
0x18000a295  mov     eax, 8007000Eh
0x18000a29a  jmp     short loc_18000A238
```
