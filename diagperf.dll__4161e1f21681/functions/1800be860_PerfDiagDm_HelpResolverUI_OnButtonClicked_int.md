# PerfDiagDm::HelpResolverUI::OnButtonClicked(int)

- ea: `0x1800be860`
- end: `0x1800be956`
- name: `?OnButtonClicked@HelpResolverUI@PerfDiagDm@@MEAAJH@Z`
- size: `246`
- prototype: `__int64 __fastcall(PerfDiagDm::HelpResolverUI *__hidden this, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18002cfe4`
- `0x1800bdab8`
- `0x1800be860`
- `0x1800d6010`

## import_xrefs

- `ntdll!WinSqmAddToStream` at `0x1800be90b`
- `ntdll!WinSqmAddToStream` at `0x1800be90b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be946`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be946`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800be937`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800be937`
- `wdi!WdiQueueCurrentResolution` at `0x1800be8ba`
- `wdi!WdiQueueCurrentResolution` at `0x1800be8ba`

## pseudocode

```c
__int64 __fastcall PerfDiagDm::HelpResolverUI::OnButtonClicked(PerfDiagDm::HelpResolverUI *this, int a2)
{
  struct _FILETIME *v3; // rdx
  int v4; // edx
  __int64 v5; // rbx
  const wchar_t *v7; // rcx
  bool v8; // zf
  const wchar_t *v9; // rax
  unsigned int v10; // edi
  HANDLE Thread; // rax
  int v12; // [rsp+30h] [rbp-18h] BYREF
  const wchar_t *v13; // [rsp+38h] [rbp-10h]
  __int64 v14; // [rsp+60h] [rbp+18h] BYREF

  v3 = (struct _FILETIME *)(unsigned int)(a2 - 1);
  if ( !(_DWORD)v3 )
  {
LABEL_5:
    v5 = *((_QWORD *)this + 1);
    v14 = 0;
    if ( (int)PerfDiagDm::GetExpirationDate((PerfDiagDm *)&v14, v3) >= 0 )
      WdiQueueCurrentResolution(v5, 32, v14);
    return 0;
  }
  v4 = (_DWORD)v3 - 1000;
  if ( v4 )
  {
    if ( v4 != 1 || (*(unsigned __int8 (__fastcall **)(PerfDiagDm::HelpResolverUI *))(*(_QWORD *)this + 56LL))(this) )
      return 0;
    goto LABEL_5;
  }
  if ( *((_DWORD *)this + 16) )
  {
    v7 = (const wchar_t *)*((_QWORD *)this + 9);
    if ( v7 )
    {
      v8 = *v7 == 0;
      v9 = L"(null)";
      v12 = 2;
      if ( !v8 )
        v9 = v7;
      v13 = v9;
      WinSqmAddToStream(0, 911, 1, &v12);
    }
    v10 = *((_DWORD *)this + 16);
    if ( (int)PerfDiagDm::HelpResolverUI::EnsureLaunchThreadDone(this) >= 0 )
    {
      Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)PerfDiagDm::LaunchHelpThread, (LPVOID)v10, 0, 0);
      *((_QWORD *)this + 11) = Thread;
      if ( !Thread )
        GetLastError();
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800be860  mov     [rsp+arg_0], rbx
0x1800be865  mov     [rsp+arg_8], rsi
0x1800be86a  push    rdi
0x1800be86b  sub     rsp, 40h
0x1800be86f  xor     esi, esi
0x1800be871  mov     rbx, rcx
0x1800be874  sub     edx, 1
0x1800be877  jz      short loc_1800BE896
0x1800be879  sub     edx, 3E8h
0x1800be87f  jz      short loc_1800BE8D2
0x1800be881  cmp     edx, 1
0x1800be884  jnz     short loc_1800BE8C0
0x1800be886  mov     rax, [rcx]
0x1800be889  mov     rax, [rax+38h]
0x1800be88d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be892  test    al, al
0x1800be894  jnz     short loc_1800BE8C0
0x1800be896  mov     rbx, [rbx+8]
0x1800be89a  lea     rcx, [rsp+48h+arg_10]; this
0x1800be89f  mov     [rsp+48h+arg_10], rsi
0x1800be8a4  call    ?GetExpirationDate@PerfDiagDm@@YAJAEAU_FILETIME@@@Z; PerfDiagDm::GetExpirationDate(_FILETIME &)
0x1800be8a9  test    eax, eax
0x1800be8ab  js      short loc_1800BE8C0
0x1800be8ad  mov     r8, [rsp+48h+arg_10]
0x1800be8b2  mov     edx, 20h ; ' '
0x1800be8b7  mov     rcx, rbx
0x1800be8ba  call    cs:__imp_WdiQueueCurrentResolution
0x1800be8c0  xor     eax, eax
0x1800be8c2  mov     rbx, [rsp+48h+arg_0]
0x1800be8c7  mov     rsi, [rsp+48h+arg_8]
0x1800be8cc  add     rsp, 40h
0x1800be8d0  pop     rdi
0x1800be8d1  retn
0x1800be8d2  cmp     [rcx+40h], esi
0x1800be8d5  jz      short loc_1800BE94C
0x1800be8d7  mov     rcx, [rcx+48h]
0x1800be8db  test    rcx, rcx
0x1800be8de  jz      short loc_1800BE911
0x1800be8e0  cmp     [rcx], si
0x1800be8e3  lea     rax, aNull; "(null)"
0x1800be8ea  lea     r9, [rsp+48h+var_18]
0x1800be8ef  mov     [rsp+48h+var_18], 2
0x1800be8f7  cmovnz  rax, rcx
0x1800be8fb  mov     edx, 38Fh
0x1800be900  xor     ecx, ecx
0x1800be902  mov     [rsp+48h+var_10], rax
0x1800be907  lea     r8d, [rcx+1]
0x1800be90b  call    cs:__imp_WinSqmAddToStream
0x1800be911  mov     edi, [rbx+40h]
0x1800be914  mov     rcx, rbx; this
0x1800be917  call    ?EnsureLaunchThreadDone@HelpResolverUI@PerfDiagDm@@AEAAJXZ; PerfDiagDm::HelpResolverUI::EnsureLaunchThreadDone(void)
0x1800be91c  test    eax, eax
0x1800be91e  js      short loc_1800BE94C
0x1800be920  mov     r9d, edi; lpParameter
0x1800be923  mov     [rsp+48h+lpThreadId], rsi; lpThreadId
0x1800be928  lea     r8, ?LaunchHelpThread@PerfDiagDm@@YAKPEAX@Z; lpStartAddress
0x1800be92f  mov     [rsp+48h+dwCreationFlags], esi; dwCreationFlags
0x1800be933  xor     edx, edx; dwStackSize
0x1800be935  xor     ecx, ecx; lpThreadAttributes
0x1800be937  call    cs:__imp_CreateThread
0x1800be93d  mov     [rbx+58h], rax
0x1800be941  test    rax, rax
0x1800be944  jnz     short loc_1800BE94C
0x1800be946  call    cs:__imp_GetLastError
0x1800be94c  mov     eax, 1
0x1800be951  jmp     loc_1800BE8C2
```
