# _SetDriverOrServiceStartType

- ea: `0x180007ff4`
- end: `0x18000810f`
- name: `_SetDriverOrServiceStartType`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1800073f0`

## callees

- `0x180004f10`
- `0x180007c34`
- `0x180007dd4`
- `0x180007ff4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800080b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800080b3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800080f7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800080f7`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180008079`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180008079`

## pseudocode

```c
__int64 __fastcall SetDriverOrServiceStartType(const WCHAR *a1, DWORD a2)
{
  DWORD LastError; // ebx
  __int64 v5; // r8
  int v6; // r8d
  SC_HANDLE hService; // [rsp+80h] [rbp+18h] BYREF

  hService = 0;
  LastError = OpenDriverOrService(a1, 0x40000000u, &hService);
  if ( !LastError )
  {
    if ( ChangeServiceConfigW(hService, 0xFFFFFFFF, a2, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 22), 14, v5, a1);
    }
    else
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0 )
        WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 22), 15, v6, (_DWORD)a1, LastError);
    }
    CloseServiceHandle(hService);
  }
  return LastError;
}

```

## disassembly

```asm
0x180007ff4  mov     rax, rsp
0x180007ff7  mov     [rax+8], rbx
0x180007ffb  mov     [rax+10h], rsi
0x180007fff  push    rdi
0x180008000  sub     rsp, 60h
0x180008004  mov     esi, edx
0x180008006  mov     qword ptr [rax+18h], 0
0x18000800e  mov     edx, 40000000h; dwDesiredAccess
0x180008013  lea     r8, [rax+18h]
0x180008017  mov     rdi, rcx
0x18000801a  call    _OpenDriverOrService
0x18000801f  mov     ebx, eax
0x180008021  test    eax, eax
0x180008023  jnz     loc_1800080FD
0x180008029  mov     rcx, [rsp+68h+hService]; hService
0x180008031  or      edx, 0FFFFFFFFh; dwServiceType
0x180008034  mov     [rsp+68h+lpDisplayName], 0; lpDisplayName
0x18000803d  mov     r9d, edx; dwErrorControl
0x180008040  mov     [rsp+68h+lpPassword], 0; lpPassword
0x180008049  mov     r8d, esi; dwStartType
0x18000804c  mov     [rsp+68h+lpServiceStartName], 0; lpServiceStartName
0x180008055  mov     [rsp+68h+lpDependencies], 0; lpDependencies
0x18000805e  mov     [rsp+68h+lpdwTagId], 0; lpdwTagId
0x180008067  mov     [rsp+68h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x180008070  mov     [rsp+68h+lpBinaryPathName], 0; lpBinaryPathName
0x180008079  call    cs:__imp_ChangeServiceConfigW
0x18000807f  test    eax, eax
0x180008081  jz      short loc_1800080B3
0x180008083  mov     rcx, cs:WPP_GLOBAL_Control
0x18000808a  lea     rax, WPP_GLOBAL_Control
0x180008091  cmp     rcx, rax
0x180008094  jz      short loc_1800080EF
0x180008096  test    byte ptr [rcx+0BCh], 1
0x18000809d  jz      short loc_1800080EF
0x18000809f  mov     rcx, [rcx+0B0h]
0x1800080a6  lea     edx, [rbx+0Eh]
0x1800080a9  mov     r9, rdi
0x1800080ac  call    WPP_SF_S
0x1800080b1  jmp     short loc_1800080EF
0x1800080b3  call    cs:__imp_GetLastError
0x1800080b9  mov     ebx, eax
0x1800080bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800080c2  lea     rax, WPP_GLOBAL_Control
0x1800080c9  cmp     rcx, rax
0x1800080cc  jz      short loc_1800080EF
0x1800080ce  test    byte ptr [rcx+0BCh], 1
0x1800080d5  jz      short loc_1800080EF
0x1800080d7  mov     rcx, [rcx+0B0h]
0x1800080de  mov     edx, 0Fh
0x1800080e3  mov     r9, rdi
0x1800080e6  mov     dword ptr [rsp+68h+lpBinaryPathName], ebx
0x1800080ea  call    WPP_SF_Sd
0x1800080ef  mov     rcx, [rsp+68h+hService]; hSCObject
0x1800080f7  call    cs:__imp_CloseServiceHandle
0x1800080fd  mov     rsi, [rsp+68h+arg_8]
0x180008102  mov     eax, ebx
0x180008104  mov     rbx, [rsp+68h+arg_0]
0x180008109  add     rsp, 60h
0x18000810d  pop     rdi
0x18000810e  retn
```
