# WSManPluginShell(void *,_WSMAN_PLUGIN_REQUEST *,ulong,_WSMAN_SHELL_STARTUP_INFO_V10 *,_WSMAN_DATA *)

- ea: `0x180004750`
- end: `0x180004826`
- name: `?WSManPluginShell@@YAXPEAXPEAU_WSMAN_PLUGIN_REQUEST@@KPEAU_WSMAN_SHELL_STARTUP_INFO_V10@@PEAU_WSMAN_DATA@@@Z`
- size: `214`
- prototype: `void __fastcall(struct PwrshPlugIn *, struct _WSMAN_PLUGIN_REQUEST *, unsigned int, struct _WSMAN_SHELL_STARTUP_INFO_V10 *, struct _WSMAN_DATA *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180002980`
- `0x180002fac`
- `0x1800040d0`
- `0x180004750`

## import_xrefs

- `OLE32!CoInitializeEx` at `0x180004799`
- `OLE32!CoInitializeEx` at `0x180004799`
- `OLE32!CoUninitialize` at `0x1800047ae`
- `OLE32!CoUninitialize` at `0x1800047eb`
- `OLE32!CoUninitialize` at `0x1800047ae`
- `OLE32!CoUninitialize` at `0x1800047eb`

## pseudocode

```c
void __fastcall WSManPluginShell(
        struct PwrshPlugIn *a1,
        struct _WSMAN_PLUGIN_REQUEST *a2,
        unsigned int a3,
        struct _WSMAN_SHELL_STARTUP_INFO_V10 *a4,
        struct _WSMAN_DATA *a5)
{
  PwrshPlugInMediator *PwrshPlugInMediator; // r14
  HRESULT v10; // eax
  DWORD v11; // edx
  char v12; // bl
  DWORD v13; // edi
  _QWORD *v14; // rbx
  __int64 v15; // [rsp+30h] [rbp-38h] BYREF
  char v16; // [rsp+70h] [rbp+8h]

  v16 = 0;
  if ( !a1 )
  {
    ReportOperationComplete(a2, 0x805403E9);
    return;
  }
  try
  {
    PwrshPlugInMediator = PwrshPlugInMediator::GetPwrshPlugInMediator(0);
    v10 = CoInitializeEx(0, 0);
    v11 = v10;
    v12 = 1;
    if ( v10 )
    {
      if ( v10 == 1 )
      {
        CoUninitialize();
      }
      else if ( v10 != -2147417850 )
      {
        if ( (v10 & 0x1FFF0000) == 0x70000 )
          v11 = (unsigned __int16)v10;
        ReportOperationComplete(a2, v11);
        return;
      }
      v12 = 0;
    }
    v16 = v12;
    PwrshPlugInMediator::CreateShell(PwrshPlugInMediator, a1, a2, a3, a4, a5);
    if ( v12 )
    {
      CoUninitialize();
      v16 = 0;
    }
  }
  catch ( PlugInException *v15 )
  {
    v13 = 1101;
    v14 = (_QWORD *)v15;
    if ( v15 )
    {
      v13 = *(_DWORD *)v15;
      if ( *(_QWORD *)(v15 + 8) )
      {
        operator delete[](*(void **)(v15 + 8));
        v14[1] = 0;
      }
      operator delete(v14);
    }
    if ( v16 )
      CoUninitialize();
    ReportOperationComplete(a2, v13);
  }
}

```

## disassembly

```asm
0x180004750  mov     [rsp+arg_10], rbx
0x180004755  mov     [rsp+arg_8], rdx
0x18000475a  push    rsi
0x18000475b  push    rdi
0x18000475c  push    r12
0x18000475e  push    r14
0x180004760  push    r15
0x180004762  sub     rsp, 40h
0x180004766  mov     r15, r9
0x180004769  mov     r12d, r8d
0x18000476c  mov     rdi, rdx
0x18000476f  mov     rsi, rcx
0x180004772  mov     [rsp+68h+arg_0], 0
0x180004777  test    rcx, rcx
0x18000477a  jnz     short loc_18000478B
0x18000477c  mov     edx, 805403E9h; errorCode
0x180004781  mov     rcx, rdi; requestDetails
0x180004784  call    ?ReportOperationComplete@@YAKPEAU_WSMAN_PLUGIN_REQUEST@@K@Z; ReportOperationComplete(_WSMAN_PLUGIN_REQUEST *,ulong)
0x180004789  jmp     short loc_1800047F6
0x18000478b  xor     ecx, ecx; unsigned __int16 *
0x18000478d  call    ?GetPwrshPlugInMediator@PwrshPlugInMediator@@SAPEAV1@PEBG@Z; PwrshPlugInMediator::GetPwrshPlugInMediator(ushort const *)
0x180004792  mov     r14, rax
0x180004795  xor     edx, edx; dwCoInit
0x180004797  xor     ecx, ecx; pvReserved
0x180004799  call    cs:__imp_CoInitializeEx
0x18000479f  mov     edx, eax
0x1800047a1  mov     ebx, 1
0x1800047a6  test    eax, eax
0x1800047a8  jz      short loc_1800047C0
0x1800047aa  cmp     eax, ebx
0x1800047ac  jnz     short loc_1800047B6
0x1800047ae  call    cs:__imp_CoUninitialize
0x1800047b4  jmp     short loc_1800047BE
0x1800047b6  cmp     edx, 80010106h
0x1800047bc  jnz     short loc_18000480B
0x1800047be  xor     bl, bl
0x1800047c0  mov     [rsp+68h+arg_0], bl
0x1800047c4  mov     rax, [rsp+68h+arg_20]
0x1800047cc  mov     [rsp+68h+var_40], rax; struct _WSMAN_DATA *
0x1800047d1  mov     [rsp+68h+var_48], r15; struct _WSMAN_SHELL_STARTUP_INFO_V10 *
0x1800047d6  mov     r9d, r12d; unsigned int
0x1800047d9  mov     r8, rdi; struct _WSMAN_PLUGIN_REQUEST *
0x1800047dc  mov     rdx, rsi; struct PwrshPlugIn *
0x1800047df  mov     rcx, r14; this
0x1800047e2  call    ?CreateShell@PwrshPlugInMediator@@QEAAXPEAVPwrshPlugIn@@PEAU_WSMAN_PLUGIN_REQUEST@@KPEAU_WSMAN_SHELL_STARTUP_INFO_V10@@PEAU_WSMAN_DATA@@@Z; PwrshPlugInMediator::CreateShell(PwrshPlugIn *,_WSMAN_PLUGIN_REQUEST *,ulong,_WSMAN_SHELL_STARTUP_INFO_V10 *,_WSMAN_DATA *)
0x1800047e7  test    bl, bl
0x1800047e9  jz      short loc_1800047F6
0x1800047eb  call    cs:__imp_CoUninitialize
0x1800047f1  mov     [rsp+68h+arg_0], 0
0x1800047f6  mov     rbx, [rsp+68h+arg_10]
0x1800047fe  add     rsp, 40h
0x180004802  pop     r15
0x180004804  pop     r14
0x180004806  pop     r12
0x180004808  pop     rdi
0x180004809  pop     rsi
0x18000480a  retn
0x18000480b  and     eax, 1FFF0000h
0x180004810  cmp     eax, 70000h
0x180004815  jnz     short loc_18000481A
0x180004817  movzx   edx, dx; errorCode
0x18000481a  mov     rcx, rdi; requestDetails
0x18000481d  call    ?ReportOperationComplete@@YAKPEAU_WSMAN_PLUGIN_REQUEST@@K@Z; ReportOperationComplete(_WSMAN_PLUGIN_REQUEST *,ulong)
0x180004822  jmp     short loc_1800047F6
```
