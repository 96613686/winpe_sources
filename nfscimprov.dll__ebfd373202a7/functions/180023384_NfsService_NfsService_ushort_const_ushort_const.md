# NfsService::NfsService(ushort const *,ushort const *)

- ea: `0x180023384`
- end: `0x18002347b`
- name: `??0NfsService@@QEAA@PEBG0@Z`
- size: `247`
- prototype: `NfsService *__fastcall(LPCWSTR lpServiceName, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800103cc`
- `0x180010f28`
- `0x18001323c`
- `0x180013378`
- `0x1800134b4`
- `0x1800135ec`

## callees

- `0x180006a54`
- `0x180023384`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002340f`
- `KERNEL32!GetLastError` at `0x18002340f`
- `ADVAPI32!OpenSCManagerW` at `0x1800233fd`
- `ADVAPI32!OpenSCManagerW` at `0x1800233fd`
- `ADVAPI32!OpenServiceW` at `0x180023438`
- `ADVAPI32!OpenServiceW` at `0x180023455`
- `ADVAPI32!OpenServiceW` at `0x180023438`
- `ADVAPI32!OpenServiceW` at `0x180023455`

## string_xrefs

- `0x1800233f4`: `ServicesActive`

## pseudocode

```c
NfsService *__fastcall NfsService::NfsService(
        WCHAR *lpServiceName,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  signed int v4; // ebx
  const unsigned __int16 *v5; // r11
  SC_HANDLE v6; // rax
  signed int LastError; // eax
  SC_HANDLE v8; // rax
  SC_HANDLE v9; // rcx
  NfsService *result; // rax

  *((_QWORD *)lpServiceName + 128) = 0;
  *((_QWORD *)lpServiceName + 129) = 0;
  *((_QWORD *)lpServiceName + 130) = 0;
  v4 = StringCchCopyW(lpServiceName, 0x100u, a2);
  if ( v4 >= 0 )
  {
    v4 = StringCchCopyW(lpServiceName + 256, 0x100u, v5);
    if ( v4 >= 0 )
    {
      v6 = OpenSCManagerW(0, L"ServicesActive", 1u);
      *((_QWORD *)lpServiceName + 128) = v6;
      if ( v6 )
        goto LABEL_7;
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( v4 >= 0 )
      {
LABEL_7:
        v8 = OpenServiceW(*((SC_HANDLE *)lpServiceName + 128), lpServiceName, 0x34u);
        v9 = (SC_HANDLE)*((_QWORD *)lpServiceName + 128);
        *((_QWORD *)lpServiceName + 129) = v8;
        *((_QWORD *)lpServiceName + 130) = OpenServiceW(v9, lpServiceName + 256, 0x34u);
      }
    }
  }
  result = (NfsService *)lpServiceName;
  *((_DWORD *)lpServiceName + 262) = v4;
  return result;
}

```

## disassembly

```asm
0x180023384  mov     [rsp+arg_0], rbx
0x180023389  mov     [rsp+arg_8], rsi
0x18002338e  push    rdi
0x18002338f  sub     rsp, 20h
0x180023393  mov     r11, r8
0x180023396  mov     qword ptr [rcx+400h], 0
0x1800233a1  mov     r8, rdx; unsigned __int16 *
0x1800233a4  mov     qword ptr [rcx+408h], 0
0x1800233af  mov     edx, 100h; unsigned __int64
0x1800233b4  mov     qword ptr [rcx+410h], 0
0x1800233bf  mov     rdi, rcx
0x1800233c2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800233c7  mov     ebx, eax
0x1800233c9  test    eax, eax
0x1800233cb  js      loc_180023462
0x1800233d1  lea     rsi, [rdi+200h]
0x1800233d8  mov     r8, r11; unsigned __int16 *
0x1800233db  mov     rcx, rsi; unsigned __int16 *
0x1800233de  mov     edx, 100h; unsigned __int64
0x1800233e3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800233e8  mov     ebx, eax
0x1800233ea  test    eax, eax
0x1800233ec  js      short loc_180023462
0x1800233ee  mov     r8d, 1; dwDesiredAccess
0x1800233f4  lea     rdx, DatabaseName; "ServicesActive"
0x1800233fb  xor     ecx, ecx; lpMachineName
0x1800233fd  call    cs:__imp_OpenSCManagerW
0x180023403  mov     [rdi+400h], rax
0x18002340a  test    rax, rax
0x18002340d  jnz     short loc_180023428
0x18002340f  call    cs:__imp_GetLastError
0x180023415  mov     ebx, eax
0x180023417  test    eax, eax
0x180023419  jle     short loc_180023424
0x18002341b  movzx   ebx, ax
0x18002341e  or      ebx, 80070000h
0x180023424  test    ebx, ebx
0x180023426  js      short loc_180023462
0x180023428  mov     rcx, [rdi+400h]; hSCManager
0x18002342f  mov     r8d, 34h ; '4'; dwDesiredAccess
0x180023435  mov     rdx, rdi; lpServiceName
0x180023438  call    cs:__imp_OpenServiceW
0x18002343e  mov     rcx, [rdi+400h]; hSCManager
0x180023445  mov     r8d, 34h ; '4'; dwDesiredAccess
0x18002344b  mov     rdx, rsi; lpServiceName
0x18002344e  mov     [rdi+408h], rax
0x180023455  call    cs:__imp_OpenServiceW
0x18002345b  mov     [rdi+410h], rax
0x180023462  mov     rsi, [rsp+28h+arg_8]
0x180023467  mov     rax, rdi
0x18002346a  mov     [rdi+418h], ebx
0x180023470  mov     rbx, [rsp+28h+arg_0]
0x180023475  add     rsp, 20h
0x180023479  pop     rdi
0x18002347a  retn
```
