# AhgpManifestRead

- ea: `0x18000b048`
- end: `0x18000b1e9`
- name: `AhgpManifestRead`
- size: `417`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180009fe8`
- `0x18000ae60`

## callees

- `0x18000b048`
- `0x18000e240`

## import_xrefs

- `KERNEL32!QueryActCtxW` at `0x18000b08d`
- `KERNEL32!QueryActCtxW` at `0x18000b14e`
- `KERNEL32!QueryActCtxW` at `0x18000b08d`
- `KERNEL32!QueryActCtxW` at `0x18000b14e`
- `KERNEL32!GetLastError` at `0x18000b096`
- `KERNEL32!GetLastError` at `0x18000b158`
- `KERNEL32!GetLastError` at `0x18000b096`
- `KERNEL32!GetLastError` at `0x18000b158`
- `ntdll!RtlFreeHeap` at `0x18000b1d3`
- `ntdll!RtlFreeHeap` at `0x18000b1d3`
- `ntdll!RtlAllocateHeap` at `0x18000b0eb`
- `ntdll!RtlAllocateHeap` at `0x18000b0eb`

## string_xrefs

- `0x18000b0b0`: `Failed to read activation context [%d]`
- `0x18000b168`: `Failed to read activation context [%d]`
- `0x18000b0bb`: `AhgpManifestRead`
- `0x18000b10d`: `AhgpManifestRead`
- `0x18000b175`: `AhgpManifestRead`
- `0x18000b1a8`: `AhgpManifestRead`
- `0x18000b19d`: `Exception while reading manifest [%d]`

## pseudocode

```c
__int64 __fastcall AhgpManifestRead(_QWORD *a1, void *a2, ULONG a3)
{
  PVOID pvBuffer; // rdi
  BOOL v7; // r12d
  DWORD LastError; // eax
  DWORD v9; // ebx
  SIZE_T Size; // [rsp+A0h] [rbp+8h] BYREF

  Size = 0;
  pvBuffer = 0;
  *a1 = 0;
  v7 = QueryActCtxW(0x80000000, a2, 0, a3, 0, 0, &Size);
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError == 122 || v7 )
  {
    v9 = 8;
    pvBuffer = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, Size);
    if ( pvBuffer )
    {
      if ( QueryActCtxW(0x80000000, a2, 0, a3, pvBuffer, Size, &Size) )
      {
        *a1 = pvBuffer;
        pvBuffer = 0;
        v9 = 0;
      }
      else
      {
        v9 = GetLastError();
        AslLogCallPrintf(1, "AhgpManifestRead", 108, "Failed to read activation context [%d]", v9);
      }
    }
    else
    {
      AslLogCallPrintf(1, "AhgpManifestRead", 90, "Out of memory");
    }
  }
  else
  {
    AslLogCallPrintf(3, "AhgpManifestRead", 82, "Failed to read activation context [%d]", LastError);
  }
  if ( pvBuffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, pvBuffer);
  return v9;
}

```

## disassembly

```asm
0x18000b048  mov     r11, rsp
0x18000b04b  push    rbx
0x18000b04c  push    rsi
0x18000b04d  push    rdi
0x18000b04e  push    r12
0x18000b050  push    r14
0x18000b052  push    r15
0x18000b054  sub     rsp, 68h
0x18000b058  mov     r14d, r8d
0x18000b05b  mov     r15, rdx
0x18000b05e  mov     rsi, rcx
0x18000b061  mov     qword ptr [r11+8], 0
0x18000b069  xor     edi, edi
0x18000b06b  mov     [r11-48h], rdi
0x18000b06f  mov     [rcx], rdi
0x18000b072  lea     rax, [r11+8]
0x18000b076  mov     [r11-68h], rax
0x18000b07a  mov     [r11-70h], rdi
0x18000b07e  mov     [r11-78h], rdi
0x18000b082  mov     r9d, r8d; ulInfoClass
0x18000b085  xor     r8d, r8d; pvSubInstance
0x18000b088  mov     ecx, 80000000h; dwFlags
0x18000b08d  call    cs:__imp_QueryActCtxW
0x18000b093  mov     r12d, eax
0x18000b096  call    cs:__imp_GetLastError
0x18000b09c  mov     ebx, eax
0x18000b09e  mov     [rsp+98h+var_58], eax
0x18000b0a2  cmp     eax, 7Ah ; 'z'
0x18000b0a5  jz      short loc_18000B0CF
0x18000b0a7  test    r12d, r12d
0x18000b0aa  jnz     short loc_18000B0CF
0x18000b0ac  mov     dword ptr [rsp+98h+pvBuffer], eax
0x18000b0b0  lea     r9, aFailedToReadAc; "Failed to read activation context [%d]"
0x18000b0b7  lea     r8d, [rdi+52h]
0x18000b0bb  lea     rdx, aAhgpmanifestre; "AhgpManifestRead"
0x18000b0c2  lea     ecx, [rdi+3]
0x18000b0c5  call    AslLogCallPrintf
0x18000b0ca  jmp     loc_18000B1BC
0x18000b0cf  mov     rcx, gs:60h
0x18000b0d8  mov     r8, [rsp+98h+Size]; Size
0x18000b0e0  mov     ebx, 8
0x18000b0e5  mov     edx, ebx; Flags
0x18000b0e7  mov     rcx, [rcx+30h]; HeapHandle
0x18000b0eb  call    cs:__imp_RtlAllocateHeap
0x18000b0f1  mov     rdi, rax
0x18000b0f4  mov     [rsp+98h+var_48], rax
0x18000b0f9  test    rax, rax
0x18000b0fc  jnz     short loc_18000B121
0x18000b0fe  mov     [rsp+98h+var_58], ebx
0x18000b102  lea     r9, aOutOfMemory; "Out of memory"
0x18000b109  lea     r8d, [rbx+52h]
0x18000b10d  lea     rdx, aAhgpmanifestre; "AhgpManifestRead"
0x18000b114  lea     ecx, [rbx-7]
0x18000b117  call    AslLogCallPrintf
0x18000b11c  jmp     loc_18000B1BC
0x18000b121  lea     rax, [rsp+98h+Size]
0x18000b129  mov     [rsp+98h+pcbWrittenOrRequired], rax; pcbWrittenOrRequired
0x18000b12e  mov     rax, [rsp+98h+Size]
0x18000b136  mov     [rsp+98h+cbBuffer], rax; cbBuffer
0x18000b13b  mov     [rsp+98h+pvBuffer], rdi; pvBuffer
0x18000b140  mov     r9d, r14d; ulInfoClass
0x18000b143  xor     r8d, r8d; pvSubInstance
0x18000b146  mov     rdx, r15; hActCtx
0x18000b149  mov     ecx, 80000000h; dwFlags
0x18000b14e  call    cs:__imp_QueryActCtxW
0x18000b154  test    eax, eax
0x18000b156  jnz     short loc_18000B187
0x18000b158  call    cs:__imp_GetLastError
0x18000b15e  mov     ebx, eax
0x18000b160  mov     [rsp+98h+var_58], eax
0x18000b164  mov     dword ptr [rsp+98h+pvBuffer], eax
0x18000b168  lea     r9, aFailedToReadAc; "Failed to read activation context [%d]"
0x18000b16f  mov     r8d, 6Ch ; 'l'
0x18000b175  lea     rdx, aAhgpmanifestre; "AhgpManifestRead"
0x18000b17c  lea     ecx, [r8-6Bh]
0x18000b180  call    AslLogCallPrintf
0x18000b185  jmp     short loc_18000B1BC
0x18000b187  mov     [rsi], rdi
0x18000b18a  xor     edi, edi
0x18000b18c  xor     ebx, ebx
0x18000b18e  jmp     short loc_18000B1BC
0x18000b190  mov     ebx, 1Eh
0x18000b195  mov     [rsp+98h+var_58], ebx
0x18000b199  mov     dword ptr [rsp+98h+pvBuffer], ebx
0x18000b19d  lea     r9, aExceptionWhile; "Exception while reading manifest [%d]"
0x18000b1a4  lea     r8d, [rbx+54h]
0x18000b1a8  lea     rdx, aAhgpmanifestre; "AhgpManifestRead"
0x18000b1af  lea     ecx, [rbx-1Dh]
0x18000b1b2  call    AslLogCallPrintf
0x18000b1b7  mov     rdi, [rsp+98h+var_48]
0x18000b1bc  test    rdi, rdi
0x18000b1bf  jz      short loc_18000B1D9
0x18000b1c1  mov     rcx, gs:60h
0x18000b1ca  mov     r8, rdi; P
0x18000b1cd  xor     edx, edx; Flags
0x18000b1cf  mov     rcx, [rcx+30h]; HeapHandle
0x18000b1d3  call    cs:__imp_RtlFreeHeap
0x18000b1d9  mov     eax, ebx
0x18000b1db  add     rsp, 68h
0x18000b1df  pop     r15
0x18000b1e1  pop     r14
0x18000b1e3  pop     r12
0x18000b1e5  pop     rdi
0x18000b1e6  pop     rsi
0x18000b1e7  pop     rbx
0x18000b1e8  retn
0x1800196a1  push    rbp
0x1800196a3  sub     rsp, 40h
0x1800196a7  mov     rbp, rdx
0x1800196aa  mov     [rbp+48h], rcx
0x1800196ae  mov     rax, [rbp+48h]
0x1800196b2  mov     rcx, [rax]
0x1800196b5  cmp     dword ptr [rcx], 0C0000006h
0x1800196bb  jz      short loc_1800196D5
0x1800196bd  mov     rax, [rbp+48h]
0x1800196c1  mov     rcx, [rax]
0x1800196c4  cmp     dword ptr [rcx], 0C0000005h
0x1800196ca  jz      short loc_1800196D5
0x1800196cc  mov     dword ptr [rbp+44h], 0
0x1800196d3  jmp     short loc_1800196DC
0x1800196d5  mov     dword ptr [rbp+44h], 1
0x1800196dc  mov     eax, [rbp+44h]
0x1800196df  add     rsp, 40h
0x1800196e3  pop     rbp
0x1800196e4  retn
```
