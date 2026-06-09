# CNetDiagClient::ShowHelpTopic(ushort const *)

- ea: `0x18000f468`
- end: `0x18000f58a`
- name: `?ShowHelpTopic@CNetDiagClient@@SAJPEBG@Z`
- size: `290`
- prototype: `__int64 __fastcall(OLECHAR *psz)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800097b0`
- `0x180010440`

## callees

- `0x18000f468`
- `0x180021010`

## import_xrefs

- `USER32!GetDesktopWindow` at `0x18000f511`
- `USER32!GetDesktopWindow` at `0x18000f511`
- `ole32!CoCreateInstance` at `0x18000f4cf`
- `ole32!CoCreateInstance` at `0x18000f4cf`
- `ole32!CoInitialize` at `0x18000f485`
- `ole32!CoInitialize` at `0x18000f485`
- `ole32!CoUninitialize` at `0x18000f579`
- `ole32!CoUninitialize` at `0x18000f579`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f4e2`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f4e2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f553`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f553`
- `COMCTL32!__imp_TaskDialog` at `0x18000f54a`
- `COMCTL32!__imp_TaskDialog` at `0x18000f54a`

## pseudocode

```c
__int64 __fastcall CNetDiagClient::ShowHelpTopic(OLECHAR *psz)
{
  unsigned int v3; // esi
  HRESULT v4; // edi
  OLECHAR *v5; // rbp
  HINSTANCE v6; // rbx
  HWND DesktopWindow; // rax
  LPVOID ppv; // [rsp+70h] [rbp+8h] BYREF

  if ( !psz )
    return 2147942487LL;
  v3 = CoInitialize(0);
  if ( (int)(v3 + 0x80000000) < 0 || v3 == -2147417850 )
  {
    ppv = 0;
    v4 = CoCreateInstance(
           &GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee,
           0,
           1u,
           &GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee,
           &ppv);
    if ( v4 >= 0 )
    {
      v5 = SysAllocString(psz);
      if ( v5 )
      {
        v4 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *))(*(_QWORD *)ppv + 24LL))(ppv, v5);
        if ( v4 < 0 )
        {
          v6 = g_hinstDll;
          DesktopWindow = GetDesktopWindow();
          TaskDialog(DesktopWindow, v6, (PCWSTR)0x9C41, (PCWSTR)0x9C72, 0, 1, (PCWSTR)0xFFFE, 0);
        }
        SysFreeString(v5);
      }
      else
      {
        v4 = -2147024882;
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    if ( v3 != -2147417850 )
      CoUninitialize();
  }
  else
  {
    return v3;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000f468  push    rbx
0x18000f46a  push    rbp
0x18000f46b  push    rsi
0x18000f46c  push    rdi
0x18000f46d  sub     rsp, 48h
0x18000f471  mov     rbx, rcx
0x18000f474  test    rcx, rcx
0x18000f477  jnz     short loc_18000F483
0x18000f479  mov     eax, 80070057h
0x18000f47e  jmp     loc_18000F581
0x18000f483  xor     ecx, ecx; pvReserved
0x18000f485  call    cs:__imp_CoInitialize
0x18000f48b  mov     esi, eax
0x18000f48d  mov     eax, 80000000h
0x18000f492  lea     ecx, [rsi+rax]
0x18000f495  test    eax, ecx
0x18000f497  jnz     short loc_18000F4A8
0x18000f499  cmp     esi, 80010106h
0x18000f49f  jz      short loc_18000F4A8
0x18000f4a1  mov     edi, esi
0x18000f4a3  jmp     loc_18000F57F
0x18000f4a8  xor     edx, edx; pUnkOuter
0x18000f4aa  mov     [rsp+68h+arg_0], 0
0x18000f4b3  lea     rax, [rsp+68h+arg_0]
0x18000f4b8  lea     r9, _GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee; riid
0x18000f4bf  mov     [rsp+68h+ppv], rax; ppv
0x18000f4c4  lea     rcx, _GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee; rclsid
0x18000f4cb  lea     r8d, [rdx+1]; dwClsContext
0x18000f4cf  call    cs:__imp_CoCreateInstance
0x18000f4d5  mov     edi, eax
0x18000f4d7  test    eax, eax
0x18000f4d9  js      loc_18000F571
0x18000f4df  mov     rcx, rbx; psz
0x18000f4e2  call    cs:__imp_SysAllocString
0x18000f4e8  mov     rbp, rax
0x18000f4eb  test    rax, rax
0x18000f4ee  jz      short loc_18000F55B
0x18000f4f0  mov     rcx, [rsp+68h+arg_0]
0x18000f4f5  mov     rdx, [rcx]
0x18000f4f8  mov     rax, [rdx+18h]
0x18000f4fc  mov     rdx, rbp
0x18000f4ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f504  mov     edi, eax
0x18000f506  test    eax, eax
0x18000f508  jns     short loc_18000F550
0x18000f50a  mov     rbx, cs:?g_hinstDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinstDll
0x18000f511  call    cs:__imp_GetDesktopWindow
0x18000f517  mov     [rsp+68h+pnButton], 0; pnButton
0x18000f520  mov     r9d, 9C72h; pszMainInstruction
0x18000f526  mov     [rsp+68h+pszIcon], 0FFFEh; pszIcon
0x18000f52f  mov     rdx, rbx; hInstance
0x18000f532  mov     [rsp+68h+dwCommonButtons], 1; dwCommonButtons
0x18000f53a  mov     rcx, rax; hwndOwner
0x18000f53d  mov     [rsp+68h+ppv], 0; pszContent
0x18000f546  lea     r8d, [r9-31h]; pszWindowTitle
0x18000f54a  call    cs:__imp_TaskDialog
0x18000f550  mov     rcx, rbp; bstrString
0x18000f553  call    cs:__imp_SysFreeString
0x18000f559  jmp     short loc_18000F560
0x18000f55b  mov     edi, 8007000Eh
0x18000f560  mov     rcx, [rsp+68h+arg_0]
0x18000f565  mov     rax, [rcx]
0x18000f568  mov     rax, [rax+10h]
0x18000f56c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f571  cmp     esi, 80010106h
0x18000f577  jz      short loc_18000F57F
0x18000f579  call    cs:__imp_CoUninitialize
0x18000f57f  mov     eax, edi
0x18000f581  add     rsp, 48h
0x18000f585  pop     rdi
0x18000f586  pop     rsi
0x18000f587  pop     rbp
0x18000f588  pop     rbx
0x18000f589  retn
```
