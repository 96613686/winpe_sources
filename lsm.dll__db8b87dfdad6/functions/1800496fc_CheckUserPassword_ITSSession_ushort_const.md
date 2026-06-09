# CheckUserPassword(ITSSession *,ushort const *)

- ea: `0x1800496fc`
- end: `0x18004986a`
- name: `?CheckUserPassword@@YAJPEAUITSSession@@PEBG@Z`
- size: `366`
- prototype: `__int64 __fastcall(struct ITSSession *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18005ac9c`

## callees

- `0x1800074c0`
- `0x180008f64`
- `0x1800496fc`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800497ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800497ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049850`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049850`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049831`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049840`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049831`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049840`
- `SspiCli!LogonUserExExW` at `0x1800497f5`
- `SspiCli!LogonUserExExW` at `0x1800497f5`

## pseudocode

```c
__int64 __fastcall CheckUserPassword(struct ITSSession *a1, const unsigned __int16 *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v5; // eax
  int v6; // eax
  signed int LastError; // eax
  HANDLE hObject[2]; // [rsp+60h] [rbp-10h] BYREF
  __int64 v10; // [rsp+90h] [rbp+20h] BYREF
  LPVOID pv; // [rsp+A0h] [rbp+30h] BYREF
  LPVOID v12; // [rsp+A8h] [rbp+38h] BYREF

  pv = 0;
  v12 = 0;
  v10 = 0;
  hObject[0] = 0;
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
        if ( !(unsigned int)LogonUserExExW(pv, v12, a2, 2, 0, 0, hObject, 0, 0, 0, 0) )
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
  if ( hObject[0] )
    CloseHandle(hObject[0]);
  SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(&v10);
  return v4;
}

```

## disassembly

```asm
0x1800496fc  push    rbp
0x1800496fe  push    rbx
0x1800496ff  push    rdi
0x180049700  mov     rbp, rsp
0x180049703  sub     rsp, 70h
0x180049707  mov     rdi, rdx
0x18004970a  mov     [rbp+pv], 0
0x180049712  mov     [rbp+arg_18], 0
0x18004971a  mov     [rbp+arg_0], 0
0x180049722  mov     [rbp+hObject], 0
0x18004972a  mov     rax, [rcx]
0x18004972d  lea     rdx, [rbp+arg_0]
0x180049731  mov     rax, [rax+60h]
0x180049735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004973a  mov     ebx, eax
0x18004973c  test    eax, eax
0x18004973e  jns     short loc_180049760
0x180049740  lea     rdx, aSessionGetuser; "Session->getUserName failed: 0x%x in %s"
0x180049747  lea     r9, aCheckuserpassw_0; "CheckUserPassword"
0x18004974e  mov     r8d, eax
0x180049751  mov     ecx, 8; int
0x180049756  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004975b  jmp     loc_180049828
0x180049760  mov     rcx, [rbp+arg_0]
0x180049764  mov     rax, [rcx]
0x180049767  lea     rdx, [rbp+pv]
0x18004976b  mov     rax, [rax+28h]
0x18004976f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049774  mov     ebx, eax
0x180049776  test    eax, eax
0x180049778  jns     short loc_180049783
0x18004977a  lea     rdx, aUsernameGetuse_0; "UserName->GetUserStr failed: 0x%x in %s"
0x180049781  jmp     short loc_180049747
0x180049783  mov     rcx, [rbp+arg_0]
0x180049787  mov     rax, [rcx]
0x18004978a  lea     rdx, [rbp+arg_18]
0x18004978e  mov     rax, [rax+30h]
0x180049792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049797  mov     ebx, eax
0x180049799  test    eax, eax
0x18004979b  jns     short loc_1800497A6
0x18004979d  lea     rdx, aUsernameGetdom; "UserName->GetDomain failed: 0x%x in %s"
0x1800497a4  jmp     short loc_180049747
0x1800497a6  mov     [rsp+70h+var_20], 0
0x1800497af  mov     [rsp+70h+var_28], 0
0x1800497b8  mov     [rsp+70h+var_30], 0
0x1800497c1  mov     [rsp+70h+var_38], 0
0x1800497ca  lea     rax, [rbp+hObject]
0x1800497ce  mov     [rsp+70h+var_40], rax
0x1800497d3  mov     [rsp+70h+var_48], 0
0x1800497dc  mov     [rsp+70h+var_50], 0
0x1800497e4  mov     r9d, 2
0x1800497ea  mov     r8, rdi
0x1800497ed  mov     rdx, [rbp+arg_18]
0x1800497f1  mov     rcx, [rbp+pv]
0x1800497f5  call    cs:__imp_LogonUserExExW
0x1800497fb  test    eax, eax
0x1800497fd  jnz     short loc_180049828
0x1800497ff  call    cs:__imp_GetLastError
0x180049805  mov     ebx, eax
0x180049807  test    eax, eax
0x180049809  jle     short loc_180049814
0x18004980b  movzx   ebx, ax
0x18004980e  or      ebx, 80070000h
0x180049814  mov     r8d, ebx
0x180049817  lea     rdx, aLogonuserexexw_0; "LogonUserExExW failed: 0x%x"
0x18004981e  mov     ecx, 8; int
0x180049823  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180049828  mov     rcx, [rbp+pv]; pv
0x18004982c  test    rcx, rcx
0x18004982f  jz      short loc_180049837
0x180049831  call    cs:__imp_CoTaskMemFree
0x180049837  mov     rcx, [rbp+arg_18]; pv
0x18004983b  test    rcx, rcx
0x18004983e  jz      short loc_180049847
0x180049840  call    cs:__imp_CoTaskMemFree
0x180049846  nop
0x180049847  mov     rcx, [rbp+hObject]; hObject
0x18004984b  test    rcx, rcx
0x18004984e  jz      short loc_180049857
0x180049850  call    cs:__imp_CloseHandle
0x180049856  nop
0x180049857  lea     rcx, [rbp+arg_0]
0x18004985b  call    ??1?$SmartPtr@UITSEventDispatcher@@@@QEAA@XZ; SmartPtr<ITSEventDispatcher>::~SmartPtr<ITSEventDispatcher>(void)
0x180049860  mov     eax, ebx
0x180049862  add     rsp, 70h
0x180049866  pop     rdi
0x180049867  pop     rbx
0x180049868  pop     rbp
0x180049869  retn
```
