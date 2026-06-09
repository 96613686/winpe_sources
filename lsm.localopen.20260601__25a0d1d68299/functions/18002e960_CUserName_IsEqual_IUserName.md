# CUserName::IsEqual(IUserName *)

- ea: `0x18002e960`
- end: `0x18002ea41`
- name: `?IsEqual@CUserName@@UEAAJPEAUIUserName@@@Z`
- size: `225`
- prototype: `__int64 __fastcall(CUserName *__hidden this, struct IUserName *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800077a0`
- `0x180008f40`
- `0x18002e960`
- `0x18009c010`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x18002ea05`
- `ntdll!RtlEqualSid` at `0x18002ea05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ea22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ea22`

## string_xrefs

- `0x18002e98c`: `No token`
- `0x18002e9ed`: `GetUserSid failed: 0x%x in %s`

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
0x18002e960  mov     [rsp+arg_8], rbx
0x18002e965  mov     [rsp+arg_10], rsi
0x18002e96a  push    rdi
0x18002e96b  sub     rsp, 20h
0x18002e96f  mov     eax, [rcx+640h]
0x18002e975  mov     rsi, rdx
0x18002e978  mov     [rsp+28h+Sid2], 0
0x18002e981  mov     rdi, rcx
0x18002e984  test    al, 2
0x18002e986  jnz     short loc_18002E9D3
0x18002e988  test    al, 1
0x18002e98a  jnz     short loc_18002E9A4
0x18002e98c  lea     rdx, aNoToken; "No token"
0x18002e993  mov     ecx, 8; int
0x18002e998  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002e99d  mov     ebx, 800703F0h
0x18002e9a2  jmp     short loc_18002EA18
0x18002e9a4  mov     rdx, [rcx+638h]; void *
0x18002e9ab  call    ?InitializeUserName@CUserName@@AEAAJPEAX@Z; CUserName::InitializeUserName(void *)
0x18002e9b0  mov     ebx, eax
0x18002e9b2  test    eax, eax
0x18002e9b4  jns     short loc_18002E9D3
0x18002e9b6  lea     rdx, aInitializeuser; "InitializeUserName failed: 0x%x in %s"
0x18002e9bd  mov     r8d, eax
0x18002e9c0  lea     r9, aCusernameIsequ; "CUserName::IsEqual"
0x18002e9c7  mov     ecx, 8; int
0x18002e9cc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002e9d1  jmp     short loc_18002EA18
0x18002e9d3  mov     rax, [rsi]
0x18002e9d6  lea     rdx, [rsp+28h+Sid2]
0x18002e9db  mov     rcx, rsi
0x18002e9de  mov     rax, [rax+48h]
0x18002e9e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e9e7  mov     ebx, eax
0x18002e9e9  test    eax, eax
0x18002e9eb  jns     short loc_18002E9F6
0x18002e9ed  lea     rdx, aGetusersidFail_0; "GetUserSid failed: 0x%x in %s"
0x18002e9f4  jmp     short loc_18002E9BD
0x18002e9f6  mov     rcx, [rdi+648h]
0x18002e9fd  mov     rdx, [rsp+28h+Sid2]; Sid2
0x18002ea02  mov     rcx, [rcx]; Sid1
0x18002ea05  call    cs:__imp_RtlEqualSid
0x18002ea0c  nop     dword ptr [rax+rax+00h]
0x18002ea11  xor     ebx, ebx
0x18002ea13  test    al, al
0x18002ea15  setz    bl
0x18002ea18  mov     rcx, [rsp+28h+Sid2]; pv
0x18002ea1d  test    rcx, rcx
0x18002ea20  jz      short loc_18002EA2E
0x18002ea22  call    cs:__imp_CoTaskMemFree
0x18002ea29  nop     dword ptr [rax+rax+00h]
0x18002ea2e  mov     rsi, [rsp+28h+arg_10]
0x18002ea33  mov     eax, ebx
0x18002ea35  mov     rbx, [rsp+28h+arg_8]
0x18002ea3a  add     rsp, 20h
0x18002ea3e  pop     rdi
0x18002ea3f  retn
```
