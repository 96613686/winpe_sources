# CUserName::IsEqual(IUserName *)

- ea: `0x18002ca10`
- end: `0x18002cae4`
- name: `?IsEqual@CUserName@@UEAAJPEAUIUserName@@@Z`
- size: `212`
- prototype: `__int64 __fastcall(CUserName *__hidden this, struct IUserName *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800074c0`
- `0x180008b20`
- `0x18002ca10`
- `0x180097010`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x18002cab5`
- `ntdll!RtlEqualSid` at `0x18002cab5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cacc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cacc`

## string_xrefs

- `0x18002ca3c`: `No token`
- `0x18002ca9d`: `GetUserSid failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CUserName::IsEqual(CUserName *this, struct IUserName *a2)
{
  int v2; // eax
  unsigned int v5; // ebx
  int v6; // eax
  int v7; // eax
  PSID Sid2; // [rsp+30h] [rbp+8h] BYREF

  v2 = *((_DWORD *)this + 400);
  Sid2 = 0;
  if ( (v2 & 2) != 0 )
    goto LABEL_7;
  if ( (v2 & 1) == 0 )
  {
    _DbgPrintMessage(8, "No token");
    v5 = -2147023888;
    goto LABEL_10;
  }
  v6 = CUserName::InitializeUserName(this, *((void **)this + 199));
  v5 = v6;
  if ( v6 >= 0 )
  {
LABEL_7:
    v7 = (*(__int64 (__fastcall **)(struct IUserName *, PSID *))(*(_QWORD *)a2 + 72LL))(a2, &Sid2);
    v5 = v7;
    if ( v7 >= 0 )
      v5 = RtlEqualSid(**((PSID **)this + 201), Sid2) == 0;
    else
      _DbgPrintMessage(8, "GetUserSid failed: 0x%x in %s", (unsigned int)v7, "CUserName::IsEqual");
  }
  else
  {
    _DbgPrintMessage(8, "InitializeUserName failed: 0x%x in %s", (unsigned int)v6, "CUserName::IsEqual");
  }
LABEL_10:
  if ( Sid2 )
    CoTaskMemFree(Sid2);
  return v5;
}

```

## disassembly

```asm
0x18002ca10  mov     [rsp+arg_8], rbx
0x18002ca15  mov     [rsp+arg_10], rsi
0x18002ca1a  push    rdi
0x18002ca1b  sub     rsp, 20h
0x18002ca1f  mov     eax, [rcx+640h]
0x18002ca25  mov     rsi, rdx
0x18002ca28  mov     [rsp+28h+Sid2], 0
0x18002ca31  mov     rdi, rcx
0x18002ca34  test    al, 2
0x18002ca36  jnz     short loc_18002CA83
0x18002ca38  test    al, 1
0x18002ca3a  jnz     short loc_18002CA54
0x18002ca3c  lea     rdx, aNoToken; "No token"
0x18002ca43  mov     ecx, 8; int
0x18002ca48  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002ca4d  mov     ebx, 800703F0h
0x18002ca52  jmp     short loc_18002CAC2
0x18002ca54  mov     rdx, [rcx+638h]; void *
0x18002ca5b  call    ?InitializeUserName@CUserName@@AEAAJPEAX@Z; CUserName::InitializeUserName(void *)
0x18002ca60  mov     ebx, eax
0x18002ca62  test    eax, eax
0x18002ca64  jns     short loc_18002CA83
0x18002ca66  lea     rdx, aInitializeuser; "InitializeUserName failed: 0x%x in %s"
0x18002ca6d  mov     r8d, eax
0x18002ca70  lea     r9, aCusernameIsequ; "CUserName::IsEqual"
0x18002ca77  mov     ecx, 8; int
0x18002ca7c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002ca81  jmp     short loc_18002CAC2
0x18002ca83  mov     rax, [rsi]
0x18002ca86  lea     rdx, [rsp+28h+Sid2]
0x18002ca8b  mov     rcx, rsi
0x18002ca8e  mov     rax, [rax+48h]
0x18002ca92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ca97  mov     ebx, eax
0x18002ca99  test    eax, eax
0x18002ca9b  jns     short loc_18002CAA6
0x18002ca9d  lea     rdx, aGetusersidFail_0; "GetUserSid failed: 0x%x in %s"
0x18002caa4  jmp     short loc_18002CA6D
0x18002caa6  mov     rcx, [rdi+648h]
0x18002caad  mov     rdx, [rsp+28h+Sid2]; Sid2
0x18002cab2  mov     rcx, [rcx]; Sid1
0x18002cab5  call    cs:__imp_RtlEqualSid
0x18002cabb  xor     ebx, ebx
0x18002cabd  test    al, al
0x18002cabf  setz    bl
0x18002cac2  mov     rcx, [rsp+28h+Sid2]; pv
0x18002cac7  test    rcx, rcx
0x18002caca  jz      short loc_18002CAD2
0x18002cacc  call    cs:__imp_CoTaskMemFree
0x18002cad2  mov     rsi, [rsp+28h+arg_10]
0x18002cad7  mov     eax, ebx
0x18002cad9  mov     rbx, [rsp+28h+arg_8]
0x18002cade  add     rsp, 20h
0x18002cae2  pop     rdi
0x18002cae3  retn
```
