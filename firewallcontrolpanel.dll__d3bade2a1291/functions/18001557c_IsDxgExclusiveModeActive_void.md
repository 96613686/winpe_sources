# IsDxgExclusiveModeActive(void)

- ea: `0x18001557c`
- end: `0x180015635`
- name: `?IsDxgExclusiveModeActive@@YAHXZ`
- size: `185`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b8b0`
- `0x18000bdd0`

## callees

- `0x18001557c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18001559d`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x1800155cd`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18001559d`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x1800155cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015602`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015614`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015602`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015614`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800155b1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800155e0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800155b1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800155e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001560b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001561d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001560b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001561d`

## pseudocode

```c
__int64 IsDxgExclusiveModeActive(void)
{
  unsigned int v0; // esi
  HANDLE v1; // rax
  void *v2; // rbx
  DWORD v3; // eax
  HANDLE v4; // rax
  void *v5; // rdi
  DWORD v6; // eax

  v0 = 0;
  v1 = OpenMutexW(0x100000u, 0, L"__DDrawCheckExclMode__");
  v2 = v1;
  if ( v1 )
  {
    v3 = WaitForSingleObject(v1, 0x1Eu);
    if ( !v3 || v3 == 128 )
    {
      v4 = OpenMutexW(0x100000u, 0, L"__DDrawExclMode__");
      v5 = v4;
      if ( v4 )
      {
        v6 = WaitForSingleObject(v4, 0);
        if ( !v6 || v6 == 128 )
        {
          ReleaseMutex(v5);
        }
        else if ( v6 == 258 )
        {
          v0 = 1;
        }
        CloseHandle(v5);
      }
      ReleaseMutex(v2);
    }
    CloseHandle(v2);
  }
  return v0;
}

```

## disassembly

```asm
0x18001557c  mov     [rsp+arg_0], rbx
0x180015581  mov     [rsp+arg_8], rsi
0x180015586  push    rdi
0x180015587  sub     rsp, 20h
0x18001558b  mov     edi, 100000h
0x180015590  lea     r8, Name; "__DDrawCheckExclMode__"
0x180015597  mov     ecx, edi; dwDesiredAccess
0x180015599  xor     edx, edx; bInheritHandle
0x18001559b  xor     esi, esi
0x18001559d  call    cs:__imp_OpenMutexW
0x1800155a3  mov     rbx, rax
0x1800155a6  test    rax, rax
0x1800155a9  jz      short loc_180015623
0x1800155ab  lea     edx, [rsi+1Eh]; dwMilliseconds
0x1800155ae  mov     rcx, rax; hHandle
0x1800155b1  call    cs:__imp_WaitForSingleObject
0x1800155b7  test    eax, eax
0x1800155b9  jz      short loc_1800155C2
0x1800155bb  cmp     eax, 80h
0x1800155c0  jnz     short loc_18001561A
0x1800155c2  lea     r8, aDdrawexclmode; "__DDrawExclMode__"
0x1800155c9  xor     edx, edx; bInheritHandle
0x1800155cb  mov     ecx, edi; dwDesiredAccess
0x1800155cd  call    cs:__imp_OpenMutexW
0x1800155d3  mov     rdi, rax
0x1800155d6  test    rax, rax
0x1800155d9  jz      short loc_180015611
0x1800155db  xor     edx, edx; dwMilliseconds
0x1800155dd  mov     rcx, rax; hHandle
0x1800155e0  call    cs:__imp_WaitForSingleObject
0x1800155e6  test    eax, eax
0x1800155e8  jz      short loc_1800155FF
0x1800155ea  cmp     eax, 80h
0x1800155ef  jz      short loc_1800155FF
0x1800155f1  cmp     eax, 102h
0x1800155f6  jnz     short loc_180015608
0x1800155f8  mov     esi, 1
0x1800155fd  jmp     short loc_180015608
0x1800155ff  mov     rcx, rdi; hMutex
0x180015602  call    cs:__imp_ReleaseMutex
0x180015608  mov     rcx, rdi; hObject
0x18001560b  call    cs:__imp_CloseHandle
0x180015611  mov     rcx, rbx; hMutex
0x180015614  call    cs:__imp_ReleaseMutex
0x18001561a  mov     rcx, rbx; hObject
0x18001561d  call    cs:__imp_CloseHandle
0x180015623  mov     rbx, [rsp+28h+arg_0]
0x180015628  mov     eax, esi
0x18001562a  mov     rsi, [rsp+28h+arg_8]
0x18001562f  add     rsp, 20h
0x180015633  pop     rdi
0x180015634  retn
```
