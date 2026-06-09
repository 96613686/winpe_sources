# OneXDuplicateRuntimeState

- ea: `0x18001a198`
- end: `0x18001a348`
- name: `OneXDuplicateRuntimeState`
- size: `432`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180010b20`
- `0x18001e930`

## callees

- `0x180019f7c`
- `0x18001a198`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a270`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a270`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001a266`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001a266`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001a232`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001a23b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001a232`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001a23b`
- `MobileNetworking!SetBufferAndLength` at `0x18001a2ac`
- `MobileNetworking!SetBufferAndLength` at `0x18001a2ac`
- `MobileNetworking!AllocateAndCopyPointerData` at `0x18001a2e0`
- `MobileNetworking!AllocateAndCopyPointerData` at `0x18001a2e0`
- `MobileNetworking!AllocateMemory` at `0x18001a1e9`
- `MobileNetworking!AllocateMemory` at `0x18001a1e9`

## pseudocode

```c
__int64 __fastcall OneXDuplicateRuntimeState(__int64 a1, _QWORD *a2)
{
  DWORD LastError; // r15d
  HANDLE *v5; // rdi
  void *v6; // rsi
  HANDLE CurrentProcess; // rbx
  HANDLE v8; // rax
  __int64 v9; // r9
  __int64 v10; // r8
  __int64 v11; // r8
  __int64 v12; // rdx
  _DWORD *v14; // [rsp+70h] [rbp+30h] BYREF

  v14 = 0;
  *a2 = 0;
  if ( a1 )
  {
    LastError = AllocateMemory(56, &v14, "OneXDuplicateRuntimeState", 228);
    if ( !LastError )
    {
      if ( (*(_BYTE *)a1 & 8) != 0 )
      {
        *v14 |= 8u;
        v14[8] = *(_DWORD *)(a1 + 32);
      }
      v14[9] = *(_DWORD *)(a1 + 36);
      if ( (*(_BYTE *)a1 & 1) != 0 && *(_QWORD *)(a1 + 8) )
      {
        v5 = (HANDLE *)v14;
        v6 = *(void **)(a1 + 8);
        CurrentProcess = GetCurrentProcess();
        v8 = GetCurrentProcess();
        if ( !DuplicateHandle(v8, v6, CurrentProcess, v5 + 1, 0, 0, 2u) )
        {
          LastError = GetLastError();
          if ( LastError )
            goto LABEL_22;
        }
        *v14 |= 1u;
      }
      if ( (*(_BYTE *)a1 & 2) != 0 )
      {
        v9 = *(unsigned int *)(a1 + 16);
        if ( (_DWORD)v9 )
        {
          v10 = *(_QWORD *)(a1 + 24);
          if ( v10 )
          {
            LastError = SetBufferAndLength(v14 + 6, v14 + 4, v10, v9);
            if ( LastError )
              goto LABEL_22;
            *v14 |= 2u;
          }
        }
      }
      if ( (*(_BYTE *)a1 & 4) == 0
        || (v11 = *(unsigned int *)(a1 + 44), !(_DWORD)v11)
        || (v12 = *(_QWORD *)(a1 + 48)) == 0 )
      {
        *a2 = v14;
        return LastError;
      }
      LastError = AllocateAndCopyPointerData(v14 + 12, v12, v11);
      if ( !LastError )
      {
        *v14 |= 4u;
        v14[10] = *(_DWORD *)(a1 + 40);
        v14[11] = *(_DWORD *)(a1 + 44);
        *a2 = v14;
        return LastError;
      }
    }
LABEL_22:
    OneXFreeRuntimeState();
    return LastError;
  }
  return 0;
}

```

## disassembly

```asm
0x18001a198  mov     [rsp-28h+arg_8], rbx
0x18001a19d  mov     [rsp-28h+arg_10], rsi
0x18001a1a2  push    rbp
0x18001a1a3  push    rdi
0x18001a1a4  push    r12
0x18001a1a6  push    r14
0x18001a1a8  push    r15
0x18001a1aa  mov     rbp, rsp
0x18001a1ad  sub     rsp, 40h
0x18001a1b1  mov     [rbp+arg_0], 0
0x18001a1b9  mov     r12, rdx
0x18001a1bc  mov     qword ptr [rdx], 0
0x18001a1c3  mov     r14, rcx
0x18001a1c6  test    rcx, rcx
0x18001a1c9  jnz     short loc_18001A1D3
0x18001a1cb  xor     r15d, r15d
0x18001a1ce  jmp     loc_18001A32C
0x18001a1d3  mov     r9d, 0E4h
0x18001a1d9  lea     r8, aOnexduplicater; "OneXDuplicateRuntimeState"
0x18001a1e0  lea     rdx, [rbp+arg_0]
0x18001a1e4  mov     ecx, 38h ; '8'
0x18001a1e9  call    cs:__imp_AllocateMemory
0x18001a1ef  mov     r15d, eax
0x18001a1f2  test    eax, eax
0x18001a1f4  jnz     loc_18001A323
0x18001a1fa  test    byte ptr [r14], 8
0x18001a1fe  jz      short loc_18001A212
0x18001a200  mov     rcx, [rbp+arg_0]
0x18001a204  or      dword ptr [rcx], 8
0x18001a207  mov     rcx, [rbp+arg_0]
0x18001a20b  mov     edx, [r14+20h]
0x18001a20f  mov     [rcx+20h], edx
0x18001a212  mov     rax, [rbp+arg_0]
0x18001a216  mov     ecx, [r14+24h]
0x18001a21a  mov     [rax+24h], ecx
0x18001a21d  test    byte ptr [r14], 1
0x18001a221  jz      short loc_18001A288
0x18001a223  cmp     qword ptr [r14+8], 0
0x18001a228  jz      short loc_18001A288
0x18001a22a  mov     rdi, [rbp+arg_0]
0x18001a22e  mov     rsi, [r14+8]
0x18001a232  call    cs:__imp_GetCurrentProcess
0x18001a238  mov     rbx, rax
0x18001a23b  call    cs:__imp_GetCurrentProcess
0x18001a241  mov     [rsp+40h+dwOptions], 2; dwOptions
0x18001a249  lea     r9, [rdi+8]; lpTargetHandle
0x18001a24d  mov     rcx, rax; hSourceProcessHandle
0x18001a250  mov     [rsp+40h+bInheritHandle], 0; bInheritHandle
0x18001a258  mov     r8, rbx; hTargetProcessHandle
0x18001a25b  mov     [rsp+40h+dwDesiredAccess], 0; dwDesiredAccess
0x18001a263  mov     rdx, rsi; hSourceHandle
0x18001a266  call    cs:__imp_DuplicateHandle
0x18001a26c  test    eax, eax
0x18001a26e  jnz     short loc_18001A281
0x18001a270  call    cs:__imp_GetLastError
0x18001a276  mov     r15d, eax
0x18001a279  test    eax, eax
0x18001a27b  jnz     loc_18001A323
0x18001a281  mov     rax, [rbp+arg_0]
0x18001a285  or      dword ptr [rax], 1
0x18001a288  test    byte ptr [r14], 2
0x18001a28c  jz      short loc_18001A2C0
0x18001a28e  mov     r9d, [r14+10h]
0x18001a292  test    r9d, r9d
0x18001a295  jz      short loc_18001A2C0
0x18001a297  mov     r8, [r14+18h]
0x18001a29b  test    r8, r8
0x18001a29e  jz      short loc_18001A2C0
0x18001a2a0  mov     rcx, [rbp+arg_0]
0x18001a2a4  lea     rdx, [rcx+10h]
0x18001a2a8  add     rcx, 18h
0x18001a2ac  call    cs:__imp_SetBufferAndLength
0x18001a2b2  mov     r15d, eax
0x18001a2b5  test    eax, eax
0x18001a2b7  jnz     short loc_18001A323
0x18001a2b9  mov     rax, [rbp+arg_0]
0x18001a2bd  or      dword ptr [rax], 2
0x18001a2c0  test    byte ptr [r14], 4
0x18001a2c4  jz      short loc_18001A314
0x18001a2c6  mov     r8d, [r14+2Ch]
0x18001a2ca  test    r8d, r8d
0x18001a2cd  jz      short loc_18001A314
0x18001a2cf  mov     rdx, [r14+30h]
0x18001a2d3  test    rdx, rdx
0x18001a2d6  jz      short loc_18001A314
0x18001a2d8  mov     rcx, [rbp+arg_0]
0x18001a2dc  add     rcx, 30h ; '0'
0x18001a2e0  call    cs:__imp_AllocateAndCopyPointerData
0x18001a2e6  mov     r15d, eax
0x18001a2e9  test    eax, eax
0x18001a2eb  jnz     short loc_18001A323
0x18001a2ed  mov     rax, [rbp+arg_0]
0x18001a2f1  or      dword ptr [rax], 4
0x18001a2f4  mov     ecx, [r14+28h]
0x18001a2f8  mov     rax, [rbp+arg_0]
0x18001a2fc  mov     [rax+28h], ecx
0x18001a2ff  mov     rax, [rbp+arg_0]
0x18001a303  mov     ecx, [r14+2Ch]
0x18001a307  mov     [rax+2Ch], ecx
0x18001a30a  mov     rax, [rbp+arg_0]
0x18001a30e  mov     [r12], rax
0x18001a312  jmp     short loc_18001A32C
0x18001a314  mov     rcx, [rbp+arg_0]
0x18001a318  mov     [r12], rcx
0x18001a31c  test    r15d, r15d
0x18001a31f  jnz     short loc_18001A327
0x18001a321  jmp     short loc_18001A32C
0x18001a323  mov     rcx, [rbp+arg_0]
0x18001a327  call    OneXFreeRuntimeState
0x18001a32c  lea     r11, [rsp+40h+var_s0]
0x18001a331  mov     eax, r15d
0x18001a334  mov     rbx, [r11+38h]
0x18001a338  mov     rsi, [r11+40h]
0x18001a33c  mov     rsp, r11
0x18001a33f  pop     r15
0x18001a341  pop     r14
0x18001a343  pop     r12
0x18001a345  pop     rdi
0x18001a346  pop     rbp
0x18001a347  retn
```
