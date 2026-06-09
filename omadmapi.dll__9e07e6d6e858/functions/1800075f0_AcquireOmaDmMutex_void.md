# AcquireOmaDmMutex(void * *)

- ea: `0x1800075f0`
- end: `0x1800076a3`
- name: `?AcquireOmaDmMutex@@YAJPEAPEAX@Z`
- size: `179`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `21`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ef50`
- `0x18000efe0`
- `0x18000f47c`
- `0x18000fa20`
- `0x180014a60`
- `0x180015120`
- `0x180015b50`
- `0x1800165a0`
- `0x180016700`
- `0x180016a80`
- `0x180016c50`
- `0x180017660`
- `0x180018480`
- `0x1800189b0`
- `0x18001ac30`
- `0x18001b0d0`
- `0x18001b750`
- `0x18001d9c0`
- `0x18001e910`
- `0x18001fa38`
- `0x180020268`

## callees

- `0x1800075f0`
- `0x180007930`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000761c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007664`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000761c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007664`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000763e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000763e`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180007608`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180007608`

## pseudocode

```c
signed int __fastcall AcquireOmaDmMutex(void **a1)
{
  HANDLE MutexW; // rax
  void *v3; // rbx
  signed int result; // eax
  DWORD v5; // eax
  unsigned int v6; // edi
  signed int LastError; // eax

  MutexW = CreateMutexW(0, 0, L"__OMADM_NAMED_MUTEX__");
  v3 = MutexW;
  if ( MutexW )
  {
    v5 = WaitForSingleObject(MutexW, 0xEA60u);
    if ( (v5 & 0xFFFFFF7F) != 0 )
    {
      if ( v5 == 258 )
      {
        v6 = -2147023436;
      }
      else if ( v5 == -1 )
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v6 = -2147418113;
      }
      ReleaseOmaDmMutex(v3);
      return v6;
    }
    else
    {
      *a1 = v3;
      return 0;
    }
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x1800075f0  mov     [rsp+arg_0], rbx
0x1800075f5  push    rdi
0x1800075f6  sub     rsp, 20h
0x1800075fa  mov     rdi, rcx
0x1800075fd  lea     r8, Name; "__OMADM_NAMED_MUTEX__"
0x180007604  xor     ecx, ecx; lpMutexAttributes
0x180007606  xor     edx, edx; bInitialOwner
0x180007608  call    cs:__imp_CreateMutexW
0x18000760f  nop     dword ptr [rax+rax+00h]
0x180007614  mov     rbx, rax
0x180007617  test    rax, rax
0x18000761a  jnz     short loc_180007636
0x18000761c  call    cs:__imp_GetLastError
0x180007623  nop     dword ptr [rax+rax+00h]
0x180007628  test    eax, eax
0x18000762a  jle     short loc_180007697
0x18000762c  movzx   eax, ax
0x18000762f  or      eax, 80070000h
0x180007634  jmp     short loc_180007697
0x180007636  mov     edx, 0EA60h; dwMilliseconds
0x18000763b  mov     rcx, rbx; hHandle
0x18000763e  call    cs:__imp_WaitForSingleObject
0x180007645  nop     dword ptr [rax+rax+00h]
0x18000764a  test    eax, 0FFFFFF7Fh
0x18000764f  jz      short loc_180007692
0x180007651  cmp     eax, 102h
0x180007656  jz      short loc_180007681
0x180007658  cmp     eax, 0FFFFFFFFh
0x18000765b  jz      short loc_180007664
0x18000765d  mov     edi, 8000FFFFh
0x180007662  jmp     short loc_180007686
0x180007664  call    cs:__imp_GetLastError
0x18000766b  nop     dword ptr [rax+rax+00h]
0x180007670  mov     edi, eax
0x180007672  test    eax, eax
0x180007674  jle     short loc_180007686
0x180007676  movzx   edi, ax
0x180007679  or      edi, 80070000h
0x18000767f  jmp     short loc_180007686
0x180007681  mov     edi, 800705B4h
0x180007686  mov     rcx, rbx; hObject
0x180007689  call    ?ReleaseOmaDmMutex@@YAXPEAX@Z; ReleaseOmaDmMutex(void *)
0x18000768e  mov     eax, edi
0x180007690  jmp     short loc_180007697
0x180007692  mov     [rdi], rbx
0x180007695  xor     eax, eax
0x180007697  mov     rbx, [rsp+28h+arg_0]
0x18000769c  add     rsp, 20h
0x1800076a0  pop     rdi
0x1800076a1  retn
```
