# SameBitness(HWND__ *,int *)

- ea: `0x18000c594`
- end: `0x18000c699`
- name: `?SameBitness@@YAJPEAUHWND__@@PEAH@Z`
- size: `261`
- prototype: `__int64 __fastcall(HWND, int *)`
- caller_count: `11`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800097e0`
- `0x18000d1cc`
- `0x180019d38`
- `0x180026150`
- `0x180026230`
- `0x180026308`
- `0x1800263e8`
- `0x1800264cc`
- `0x1800265ec`
- `0x1800266cc`
- `0x1800267c0`

## callees

- `0x18000c594`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c677`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c677`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000c5eb`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000c5eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c637`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c637`
- `USER32!GetWindowThreadProcessId` at `0x18000c5d1`
- `USER32!GetWindowThreadProcessId` at `0x18000c5d1`
- `USER32!GetDesktopWindow` at `0x18000c66c`
- `USER32!GetDesktopWindow` at `0x18000c66c`

## pseudocode

```c
__int64 __fastcall SameBitness(HWND a1, int *a2)
{
  int v2; // eax
  BOOL v3; // ebx
  HANDLE v6; // rdi
  int v7; // ebx
  __int64 v8; // rax
  DWORD dwProcessId; // [rsp+58h] [rbp+10h] BYREF
  __int64 v11; // [rsp+60h] [rbp+18h] BYREF

  v2 = dword_180061968;
  v3 = 1;
  *a2 = 1;
  if ( !v2 )
  {
    v2 = 2;
    dword_180061968 = 2;
  }
  if ( v2 == 1 )
    return 0;
  dwProcessId = 0;
  if ( GetWindowThreadProcessId(a1, &dwProcessId) )
  {
    v6 = OpenProcess(0x400u, 0, dwProcessId);
    if ( v6 )
    {
      v11 = 0;
      if ( lpfnNtQueryInformationProcess )
        v7 = lpfnNtQueryInformationProcess(v6, 26, &v11, 8u, 0);
      else
        v7 = -1;
      CloseHandle(v6);
      if ( (v7 & 0xC0000000) == 0xC0000000 )
        v8 = 0;
      else
        v8 = v11;
      v3 = v8 == 0;
      goto LABEL_11;
    }
    if ( a1 == GetDesktopWindow() )
    {
LABEL_11:
      *a2 = v3;
      return 0;
    }
    GetLastError();
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x18000c594  mov     [rsp+arg_0], rbx
0x18000c599  push    rsi
0x18000c59a  push    rdi
0x18000c59b  push    r14
0x18000c59d  sub     rsp, 30h
0x18000c5a1  mov     eax, cs:dword_180061968
0x18000c5a7  mov     ebx, 1
0x18000c5ac  mov     [rdx], ebx
0x18000c5ae  mov     r14, rdx
0x18000c5b1  mov     rsi, rcx
0x18000c5b4  test    eax, eax
0x18000c5b6  jz      loc_18000C684
0x18000c5bc  cmp     eax, ebx
0x18000c5be  jz      loc_18000C655
0x18000c5c4  lea     rdx, [rsp+48h+dwProcessId]; lpdwProcessId
0x18000c5c9  mov     [rsp+48h+dwProcessId], 0
0x18000c5d1  call    cs:__imp_GetWindowThreadProcessId
0x18000c5d7  test    eax, eax
0x18000c5d9  jz      loc_18000C67D
0x18000c5df  mov     r8d, [rsp+48h+dwProcessId]; dwProcessId
0x18000c5e4  xor     edx, edx; bInheritHandle
0x18000c5e6  mov     ecx, 400h; dwDesiredAccess
0x18000c5eb  call    cs:__imp_OpenProcess
0x18000c5f1  mov     rdi, rax
0x18000c5f4  test    rax, rax
0x18000c5f7  jz      short loc_18000C66C
0x18000c5f9  mov     rax, cs:?lpfnNtQueryInformationProcess@@3P6AJPEAXH0KPEAK@ZEA; long (*lpfnNtQueryInformationProcess)(void *,int,void *,ulong,ulong *)
0x18000c600  mov     [rsp+48h+arg_10], 0
0x18000c609  test    rax, rax
0x18000c60c  jz      loc_18000C694
0x18000c612  mov     r9d, 8
0x18000c618  mov     [rsp+48h+var_28], 0
0x18000c621  lea     r8, [rsp+48h+arg_10]
0x18000c626  mov     rcx, rdi
0x18000c629  lea     edx, [r9+12h]
0x18000c62d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c632  mov     ebx, eax
0x18000c634  mov     rcx, rdi; hObject
0x18000c637  call    cs:__imp_CloseHandle
0x18000c63d  mov     eax, 0C0000000h
0x18000c642  and     ebx, eax
0x18000c644  cmp     ebx, eax
0x18000c646  jnz     short loc_18000C665
0x18000c648  xor     eax, eax
0x18000c64a  xor     ebx, ebx
0x18000c64c  test    rax, rax
0x18000c64f  setz    bl
0x18000c652  mov     [r14], ebx
0x18000c655  xor     eax, eax
0x18000c657  mov     rbx, [rsp+48h+arg_0]
0x18000c65c  add     rsp, 30h
0x18000c660  pop     r14
0x18000c662  pop     rdi
0x18000c663  pop     rsi
0x18000c664  retn
0x18000c665  mov     rax, [rsp+48h+arg_10]
0x18000c66a  jmp     short loc_18000C64A
0x18000c66c  call    cs:__imp_GetDesktopWindow
0x18000c672  cmp     rsi, rax
0x18000c675  jz      short loc_18000C652
0x18000c677  call    cs:__imp_GetLastError
0x18000c67d  mov     eax, 80004005h
0x18000c682  jmp     short loc_18000C657
0x18000c684  mov     eax, 2
0x18000c689  mov     cs:dword_180061968, eax
0x18000c68f  jmp     loc_18000C5BC
0x18000c694  or      ebx, 0FFFFFFFFh
0x18000c697  jmp     short loc_18000C634
```
