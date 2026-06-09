# PeapEapInfoInvokeClientConfigUI(HWND__ *,_PEAP_EAP_INFO *,ulong)

- ea: `0x18007022c`
- end: `0x1800703af`
- name: `?PeapEapInfoInvokeClientConfigUI@@YAKPEAUHWND__@@PEAU_PEAP_EAP_INFO@@K@Z`
- size: `387`
- prototype: `unsigned int __fastcall(HWND, struct _PEAP_EAP_INFO *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18006f154`
- `0x18006fb8c`

## callees

- `0x180038e4c`
- `0x18007022c`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180070262`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007027c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180070262`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007027c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070379`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070379`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007033e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007033e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070316`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070316`

## string_xrefs

- `0x180070254`: `RasEapInvokeConfigUI`

## pseudocode

```c
__int64 __fastcall PeapEapInfoInvokeClientConfigUI(HWND a1, HMODULE *a2, unsigned int a3)
{
  FARPROC ProcAddress; // rdi
  FARPROC v7; // rax
  void (*v8)(void); // rsi
  HMODULE v9; // r9
  DWORD LastError; // edi
  unsigned int v11; // eax
  HMODULE v12; // rcx
  HMODULE v13; // rax
  SIZE_T uBytes; // [rsp+68h] [rbp+10h] BYREF
  void *Src; // [rsp+78h] [rbp+20h] BYREF

  Src = 0;
  LODWORD(uBytes) = 0;
  ProcAddress = GetProcAddress(a2[10], "RasEapInvokeConfigUI");
  v7 = GetProcAddress(a2[10], "RasEapFreeMemory");
  v8 = (void (*)(void))v7;
  if ( ProcAddress && v7 )
  {
    v9 = a2[19];
    if ( !v9 )
      v9 = a2[17];
    LastError = ((__int64 (__fastcall *)(_QWORD, HWND, _QWORD, HMODULE, _DWORD, void **, SIZE_T *))ProcAddress)(
                  *((unsigned int *)a2 + 2),
                  a1,
                  a3,
                  v9,
                  *(_DWORD *)((char *)a2 + (a2[19] != 0 ? 0x10 : 0) + 144),
                  &Src,
                  &uBytes);
    if ( !LastError )
    {
      if ( !Src )
        return LastError;
      v11 = uBytes;
      if ( (_DWORD)uBytes )
      {
        v12 = a2[19];
        if ( v12 )
        {
          LocalFree(v12);
          v11 = uBytes;
          a2[19] = 0;
          *((_DWORD *)a2 + 40) = LastError;
        }
        v13 = (HMODULE)LocalAlloc(0x40u, v11);
        a2[19] = v13;
        if ( v13 )
        {
          memcpy_0(v13, Src, (unsigned int)uBytes);
          *((_DWORD *)a2 + 40) = uBytes;
        }
        else
        {
          LastError = 14;
        }
      }
    }
  }
  else
  {
    LastError = GetLastError();
  }
  if ( Src )
    v8();
  return LastError;
}

```

## disassembly

```asm
0x18007022c  mov     rax, rsp
0x18007022f  mov     [rax+8], rbx
0x180070233  mov     [rax+18h], rbp
0x180070237  push    rsi
0x180070238  push    rdi
0x180070239  push    r14
0x18007023b  sub     rsp, 40h
0x18007023f  mov     rbx, rdx
0x180070242  mov     qword ptr [rax+20h], 0
0x18007024a  mov     r14, rcx
0x18007024d  mov     dword ptr [rax+10h], 0
0x180070254  lea     rdx, aRaseapinvokeco_0; "RasEapInvokeConfigUI"
0x18007025b  mov     ebp, r8d
0x18007025e  mov     rcx, [rbx+50h]; hModule
0x180070262  call    cs:__imp_GetProcAddress
0x180070269  nop     dword ptr [rax+rax+00h]
0x18007026e  mov     rcx, [rbx+50h]; hModule
0x180070272  lea     rdx, ProcName; "RasEapFreeMemory"
0x180070279  mov     rdi, rax
0x18007027c  call    cs:__imp_GetProcAddress
0x180070283  nop     dword ptr [rax+rax+00h]
0x180070288  mov     rsi, rax
0x18007028b  test    rdi, rdi
0x18007028e  jz      loc_180070379
0x180070294  test    rax, rax
0x180070297  jz      loc_180070379
0x18007029d  mov     r9, [rbx+98h]
0x1800702a4  mov     rcx, r9
0x1800702a7  neg     rcx
0x1800702aa  sbb     rdx, rdx
0x1800702ad  and     edx, 10h
0x1800702b0  mov     eax, [rdx+rbx+90h]
0x1800702b7  test    r9, r9
0x1800702ba  jnz     short loc_1800702C3
0x1800702bc  mov     r9, [rbx+88h]
0x1800702c3  lea     rcx, [rsp+58h+uBytes]
0x1800702c8  mov     r8d, ebp
0x1800702cb  mov     [rsp+58h+var_28], rcx
0x1800702d0  mov     rdx, r14
0x1800702d3  lea     rcx, [rsp+58h+Src]
0x1800702d8  mov     [rsp+58h+var_30], rcx
0x1800702dd  mov     ecx, [rbx+8]
0x1800702e0  mov     [rsp+58h+var_38], eax
0x1800702e4  mov     rax, rdi
0x1800702e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800702ec  mov     edi, eax
0x1800702ee  test    eax, eax
0x1800702f0  jnz     loc_180070387
0x1800702f6  cmp     [rsp+58h+Src], 0
0x1800702fc  jz      loc_180070399
0x180070302  mov     eax, dword ptr [rsp+58h+uBytes]
0x180070306  test    eax, eax
0x180070308  jz      short loc_180070387
0x18007030a  mov     rcx, [rbx+98h]; hMem
0x180070311  test    rcx, rcx
0x180070314  jz      short loc_180070337
0x180070316  call    cs:__imp_LocalFree
0x18007031d  nop     dword ptr [rax+rax+00h]
0x180070322  mov     eax, dword ptr [rsp+58h+uBytes]
0x180070326  mov     qword ptr [rbx+98h], 0
0x180070331  mov     [rbx+0A0h], edi
0x180070337  mov     edx, eax; uBytes
0x180070339  mov     ecx, 40h ; '@'; uFlags
0x18007033e  call    cs:__imp_LocalAlloc
0x180070345  nop     dword ptr [rax+rax+00h]
0x18007034a  mov     [rbx+98h], rax
0x180070351  test    rax, rax
0x180070354  jnz     short loc_18007035B
0x180070356  lea     edi, [rax+0Eh]
0x180070359  jmp     short loc_180070387
0x18007035b  mov     r8d, dword ptr [rsp+58h+uBytes]; Size
0x180070360  mov     rcx, rax; void *
0x180070363  mov     rdx, [rsp+58h+Src]; Src
0x180070368  call    memcpy_0
0x18007036d  mov     eax, dword ptr [rsp+58h+uBytes]
0x180070371  mov     [rbx+0A0h], eax
0x180070377  jmp     short loc_180070387
0x180070379  call    cs:__imp_GetLastError
0x180070380  nop     dword ptr [rax+rax+00h]
0x180070385  mov     edi, eax
0x180070387  mov     rcx, [rsp+58h+Src]
0x18007038c  test    rcx, rcx
0x18007038f  jz      short loc_180070399
0x180070391  mov     rax, rsi
0x180070394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070399  mov     rbx, [rsp+58h+arg_0]
0x18007039e  mov     eax, edi
0x1800703a0  mov     rbp, [rsp+58h+arg_10]
0x1800703a5  add     rsp, 40h
0x1800703a9  pop     r14
0x1800703ab  pop     rdi
0x1800703ac  pop     rsi
0x1800703ad  retn
```
