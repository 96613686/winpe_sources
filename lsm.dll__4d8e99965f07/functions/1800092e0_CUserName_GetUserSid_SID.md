# CUserName::GetUserSid(_SID * *)

- ea: `0x1800092e0`
- end: `0x1800093a9`
- name: `?GetUserSid@CUserName@@UEAAJPEAPEAU_SID@@@Z`
- size: `201`
- prototype: `__int64 __fastcall(CUserName *__hidden this, struct _SID **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800077a0`
- `0x180008f40`
- `0x1800092e0`
- `0x18009959c`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x180009309`
- `ntdll!RtlLengthSid` at `0x180009309`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009319`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009319`

## string_xrefs

- `0x18000938a`: `No token`
- `0x18000936b`: `CUserName::GetUserSid`

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
0x1800092e0  mov     [rsp+arg_0], rbx
0x1800092e5  mov     [rsp+arg_8], rsi
0x1800092ea  push    rdi
0x1800092eb  sub     rsp, 20h
0x1800092ef  mov     eax, [rcx+640h]
0x1800092f5  mov     rsi, rdx
0x1800092f8  mov     rbx, rcx
0x1800092fb  test    al, 2
0x1800092fd  jz      short loc_180009355
0x1800092ff  mov     rcx, [rbx+648h]
0x180009306  mov     rcx, [rcx]; Sid
0x180009309  call    cs:__imp_RtlLengthSid
0x180009310  nop     dword ptr [rax+rax+00h]
0x180009315  mov     ecx, eax; cb
0x180009317  mov     edi, eax
0x180009319  call    cs:__imp_CoTaskMemAlloc
0x180009320  nop     dword ptr [rax+rax+00h]
0x180009325  test    rax, rax
0x180009328  jz      short loc_1800093A2
0x18000932a  mov     [rsi], rax
0x18000932d  mov     r8d, edi; Size
0x180009330  mov     rdx, [rbx+648h]
0x180009337  mov     rcx, rax; void *
0x18000933a  mov     rdx, [rdx]; Src
0x18000933d  call    memcpy_0
0x180009342  xor     eax, eax
0x180009344  mov     rbx, [rsp+28h+arg_0]
0x180009349  mov     rsi, [rsp+28h+arg_8]
0x18000934e  add     rsp, 20h
0x180009352  pop     rdi
0x180009353  retn
0x180009355  test    al, 1
0x180009357  jz      short loc_18000938A
0x180009359  mov     rdx, [rcx+638h]; void *
0x180009360  call    ?InitializeUserName@CUserName@@AEAAJPEAX@Z; CUserName::InitializeUserName(void *)
0x180009365  mov     edi, eax
0x180009367  test    eax, eax
0x180009369  jns     short loc_1800092FF
0x18000936b  lea     r9, aCusernameGetus_0; "CUserName::GetUserSid"
0x180009372  mov     r8d, eax
0x180009375  lea     rdx, aInitializeuser; "InitializeUserName failed: 0x%x in %s"
0x18000937c  mov     ecx, 8; int
0x180009381  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180009386  mov     eax, edi
0x180009388  jmp     short loc_180009344
0x18000938a  lea     rdx, aNoToken; "No token"
0x180009391  mov     ecx, 8; int
0x180009396  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000939b  mov     eax, 800703F0h
0x1800093a0  jmp     short loc_180009344
0x1800093a2  mov     eax, 8007000Eh
0x1800093a7  jmp     short loc_180009344
```
