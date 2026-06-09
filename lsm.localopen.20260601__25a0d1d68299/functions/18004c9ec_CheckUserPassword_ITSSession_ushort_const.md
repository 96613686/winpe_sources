# CheckUserPassword(ITSSession *,ushort const *)

- ea: `0x18004c9ec`
- end: `0x18004cb6d`
- name: `?CheckUserPassword@@YAJPEAUITSSession@@PEBG@Z`
- size: `385`
- prototype: `__int64 __fastcall(struct ITSSession *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18005e678`

## callees

- `0x1800077a0`
- `0x18000c684`
- `0x180012650`
- `0x18004c9ec`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004caf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004caf5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004cb2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004cb42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004cb2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004cb42`
- `SspiCli!LogonUserExExW` at `0x18004cae5`
- `SspiCli!LogonUserExExW` at `0x18004cae5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CheckUserPassword(struct ITSSession *a1, const unsigned __int16 *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v5; // eax
  int v6; // eax
  signed int LastError; // eax
  _QWORD v9[2]; // [rsp+60h] [rbp-10h] BYREF
  __int64 v10; // [rsp+90h] [rbp+20h] BYREF
  LPVOID pv; // [rsp+A0h] [rbp+30h] BYREF
  LPVOID v12; // [rsp+A8h] [rbp+38h] BYREF

  pv = 0;
  v12 = 0;
  v10 = 0;
  v9[0] = 0;
  v3 = (*(__int64 (__fastcall **)(struct ITSSession *, __int64 *))(*(_QWORD *)a1 + 96LL))(a1, &v10);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v10 + 40LL))(v10, &pv);
    v4 = v5;
    if ( v5 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v10 + 48LL))(v10, &v12);
      v4 = v6;
      if ( v6 >= 0 )
      {
        if ( !(unsigned int)LogonUserExExW(pv, v12, a2, 2, 0, 0, v9, 0, 0, 0, 0) )
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError > 0 )
            v4 = (unsigned __int16)LastError | 0x80070000;
          _DbgPrintMessage(8, "LogonUserExExW failed: 0x%x", v4);
        }
      }
      else
      {
        _DbgPrintMessage(8, "UserName->GetDomain failed: 0x%x in %s", (unsigned int)v6, "CheckUserPassword");
      }
    }
    else
    {
      _DbgPrintMessage(8, "UserName->GetUserStr failed: 0x%x in %s", (unsigned int)v5, "CheckUserPassword");
    }
  }
  else
  {
    _DbgPrintMessage(8, "Session->getUserName failed: 0x%x in %s", (unsigned int)v3, "CheckUserPassword");
  }
  if ( pv )
    CoTaskMemFree(pv);
  if ( v12 )
    CoTaskMemFree(v12);
  SmartHANDLE::~SmartHANDLE((SmartHANDLE *)v9);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v10);
  return v4;
}

```

## disassembly

```asm
0x18004c9ec  push    rbp
0x18004c9ee  push    rbx
0x18004c9ef  push    rdi
0x18004c9f0  mov     rbp, rsp
0x18004c9f3  sub     rsp, 70h
0x18004c9f7  mov     rdi, rdx
0x18004c9fa  mov     [rbp+pv], 0
0x18004ca02  mov     [rbp+arg_18], 0
0x18004ca0a  mov     [rbp+arg_0], 0
0x18004ca12  mov     [rbp+var_10], 0
0x18004ca1a  mov     rax, [rcx]
0x18004ca1d  lea     rdx, [rbp+arg_0]
0x18004ca21  mov     rax, [rax+60h]
0x18004ca25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca2a  mov     ebx, eax
0x18004ca2c  test    eax, eax
0x18004ca2e  jns     short loc_18004CA50
0x18004ca30  lea     rdx, aSessionGetuser; "Session->getUserName failed: 0x%x in %s"
0x18004ca37  lea     r9, aCheckuserpassw_0; "CheckUserPassword"
0x18004ca3e  mov     r8d, eax
0x18004ca41  mov     ecx, 8; int
0x18004ca46  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004ca4b  jmp     loc_18004CB24
0x18004ca50  mov     rcx, [rbp+arg_0]
0x18004ca54  mov     rax, [rcx]
0x18004ca57  lea     rdx, [rbp+pv]
0x18004ca5b  mov     rax, [rax+28h]
0x18004ca5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca64  mov     ebx, eax
0x18004ca66  test    eax, eax
0x18004ca68  jns     short loc_18004CA73
0x18004ca6a  lea     rdx, aUsernameGetuse_0; "UserName->GetUserStr failed: 0x%x in %s"
0x18004ca71  jmp     short loc_18004CA37
0x18004ca73  mov     rcx, [rbp+arg_0]
0x18004ca77  mov     rax, [rcx]
0x18004ca7a  lea     rdx, [rbp+arg_18]
0x18004ca7e  mov     rax, [rax+30h]
0x18004ca82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca87  mov     ebx, eax
0x18004ca89  test    eax, eax
0x18004ca8b  jns     short loc_18004CA96
0x18004ca8d  lea     rdx, aUsernameGetdom; "UserName->GetDomain failed: 0x%x in %s"
0x18004ca94  jmp     short loc_18004CA37
0x18004ca96  mov     [rsp+70h+var_20], 0
0x18004ca9f  mov     [rsp+70h+var_28], 0
0x18004caa8  mov     [rsp+70h+var_30], 0
0x18004cab1  mov     [rsp+70h+var_38], 0
0x18004caba  lea     rax, [rbp+var_10]
0x18004cabe  mov     [rsp+70h+var_40], rax
0x18004cac3  mov     [rsp+70h+var_48], 0
0x18004cacc  mov     [rsp+70h+var_50], 0
0x18004cad4  mov     r9d, 2
0x18004cada  mov     r8, rdi
0x18004cadd  mov     rdx, [rbp+arg_18]
0x18004cae1  mov     rcx, [rbp+pv]
0x18004cae5  call    cs:__imp_LogonUserExExW
0x18004caec  nop     dword ptr [rax+rax+00h]
0x18004caf1  test    eax, eax
0x18004caf3  jnz     short loc_18004CB24
0x18004caf5  call    cs:__imp_GetLastError
0x18004cafc  nop     dword ptr [rax+rax+00h]
0x18004cb01  mov     ebx, eax
0x18004cb03  test    eax, eax
0x18004cb05  jle     short loc_18004CB10
0x18004cb07  movzx   ebx, ax
0x18004cb0a  or      ebx, 80070000h
0x18004cb10  mov     r8d, ebx
0x18004cb13  lea     rdx, aLogonuserexexw_0; "LogonUserExExW failed: 0x%x"
0x18004cb1a  mov     ecx, 8; int
0x18004cb1f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004cb24  mov     rcx, [rbp+pv]; pv
0x18004cb28  test    rcx, rcx
0x18004cb2b  jz      short loc_18004CB39
0x18004cb2d  call    cs:__imp_CoTaskMemFree
0x18004cb34  nop     dword ptr [rax+rax+00h]
0x18004cb39  mov     rcx, [rbp+arg_18]; pv
0x18004cb3d  test    rcx, rcx
0x18004cb40  jz      short loc_18004CB4F
0x18004cb42  call    cs:__imp_CoTaskMemFree
0x18004cb49  nop     dword ptr [rax+rax+00h]
0x18004cb4e  nop
0x18004cb4f  lea     rcx, [rbp+var_10]; this
0x18004cb53  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x18004cb58  nop
0x18004cb59  lea     rcx, [rbp+arg_0]
0x18004cb5d  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x18004cb62  mov     eax, ebx
0x18004cb64  add     rsp, 70h
0x18004cb68  pop     rdi
0x18004cb69  pop     rbx
0x18004cb6a  pop     rbp
0x18004cb6b  retn
```
