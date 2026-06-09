# PeapEapInfoInvokeClientConfigUI(HWND__ *,_PEAP_EAP_INFO *,ulong)

- ea: `0x18006bb1c`
- end: `0x18006bc7c`
- name: `?PeapEapInfoInvokeClientConfigUI@@YAKPEAUHWND__@@PEAU_PEAP_EAP_INFO@@K@Z`
- size: `352`
- prototype: `unsigned int __fastcall(HWND, struct _PEAP_EAP_INFO *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18006ac00`
- `0x18006b550`

## callees

- `0x18003623c`
- `0x18006bb1c`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006bb52`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006bb66`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006bb52`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006bb66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bc4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bc4d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006bc18`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006bc18`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bbf6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bbf6`

## string_xrefs

- `0x18006bb44`: `RasEapInvokeConfigUI`

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
0x18006bb1c  mov     rax, rsp
0x18006bb1f  mov     [rax+8], rbx
0x18006bb23  mov     [rax+18h], rbp
0x18006bb27  push    rsi
0x18006bb28  push    rdi
0x18006bb29  push    r14
0x18006bb2b  sub     rsp, 40h
0x18006bb2f  mov     rbx, rdx
0x18006bb32  mov     qword ptr [rax+20h], 0
0x18006bb3a  mov     r14, rcx
0x18006bb3d  mov     dword ptr [rax+10h], 0
0x18006bb44  lea     rdx, aRaseapinvokeco_0; "RasEapInvokeConfigUI"
0x18006bb4b  mov     ebp, r8d
0x18006bb4e  mov     rcx, [rbx+50h]; hModule
0x18006bb52  call    cs:__imp_GetProcAddress
0x18006bb58  mov     rcx, [rbx+50h]; hModule
0x18006bb5c  lea     rdx, ProcName; "RasEapFreeMemory"
0x18006bb63  mov     rdi, rax
0x18006bb66  call    cs:__imp_GetProcAddress
0x18006bb6c  mov     rsi, rax
0x18006bb6f  test    rdi, rdi
0x18006bb72  jz      loc_18006BC4D
0x18006bb78  test    rax, rax
0x18006bb7b  jz      loc_18006BC4D
0x18006bb81  mov     r9, [rbx+98h]
0x18006bb88  mov     rcx, r9
0x18006bb8b  neg     rcx
0x18006bb8e  sbb     rdx, rdx
0x18006bb91  and     edx, 10h
0x18006bb94  mov     eax, [rdx+rbx+90h]
0x18006bb9b  test    r9, r9
0x18006bb9e  jnz     short loc_18006BBA7
0x18006bba0  mov     r9, [rbx+88h]
0x18006bba7  lea     rcx, [rsp+58h+uBytes]
0x18006bbac  mov     r8d, ebp
0x18006bbaf  mov     [rsp+58h+var_28], rcx
0x18006bbb4  mov     rdx, r14
0x18006bbb7  lea     rcx, [rsp+58h+Src]
0x18006bbbc  mov     [rsp+58h+var_30], rcx
0x18006bbc1  mov     ecx, [rbx+8]
0x18006bbc4  mov     [rsp+58h+var_38], eax
0x18006bbc8  mov     rax, rdi
0x18006bbcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bbd0  mov     edi, eax
0x18006bbd2  test    eax, eax
0x18006bbd4  jnz     short loc_18006BC55
0x18006bbd6  cmp     [rsp+58h+Src], 0
0x18006bbdc  jz      loc_18006BC67
0x18006bbe2  mov     eax, dword ptr [rsp+58h+uBytes]
0x18006bbe6  test    eax, eax
0x18006bbe8  jz      short loc_18006BC55
0x18006bbea  mov     rcx, [rbx+98h]; hMem
0x18006bbf1  test    rcx, rcx
0x18006bbf4  jz      short loc_18006BC11
0x18006bbf6  call    cs:__imp_LocalFree
0x18006bbfc  mov     eax, dword ptr [rsp+58h+uBytes]
0x18006bc00  mov     qword ptr [rbx+98h], 0
0x18006bc0b  mov     [rbx+0A0h], edi
0x18006bc11  mov     edx, eax; uBytes
0x18006bc13  mov     ecx, 40h ; '@'; uFlags
0x18006bc18  call    cs:__imp_LocalAlloc
0x18006bc1e  mov     [rbx+98h], rax
0x18006bc25  test    rax, rax
0x18006bc28  jnz     short loc_18006BC2F
0x18006bc2a  lea     edi, [rax+0Eh]
0x18006bc2d  jmp     short loc_18006BC55
0x18006bc2f  mov     r8d, dword ptr [rsp+58h+uBytes]; Size
0x18006bc34  mov     rcx, rax; void *
0x18006bc37  mov     rdx, [rsp+58h+Src]; Src
0x18006bc3c  call    memcpy_0
0x18006bc41  mov     eax, dword ptr [rsp+58h+uBytes]
0x18006bc45  mov     [rbx+0A0h], eax
0x18006bc4b  jmp     short loc_18006BC55
0x18006bc4d  call    cs:__imp_GetLastError
0x18006bc53  mov     edi, eax
0x18006bc55  mov     rcx, [rsp+58h+Src]
0x18006bc5a  test    rcx, rcx
0x18006bc5d  jz      short loc_18006BC67
0x18006bc5f  mov     rax, rsi
0x18006bc62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bc67  mov     rbx, [rsp+58h+arg_0]
0x18006bc6c  mov     eax, edi
0x18006bc6e  mov     rbp, [rsp+58h+arg_10]
0x18006bc73  add     rsp, 40h
0x18006bc77  pop     r14
0x18006bc79  pop     rdi
0x18006bc7a  pop     rsi
0x18006bc7b  retn
```
