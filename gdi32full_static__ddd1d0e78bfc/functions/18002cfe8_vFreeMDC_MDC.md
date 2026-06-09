# vFreeMDC(MDC *)

- ea: `0x18002cfe8`
- end: `0x18002d168`
- name: `?vFreeMDC@@YAXPEAVMDC@@@Z`
- size: `384`
- prototype: `void __fastcall(struct MDC *this)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800315b0`
- `0x180033650`
- `0x180033728`
- `0x1800521b8`

## callees

- `0x18002cfe8`
- `0x18002d170`
- `0x1800524d0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d07b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d0b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d0f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d11e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d07b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d0b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d0f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d11e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002d157`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002d157`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d12f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d12f`
- `ntdll!RtlFreeHeap` at `0x18002d0e7`
- `ntdll!RtlFreeHeap` at `0x18002d0e7`

## pseudocode

```c
void __fastcall vFreeMDC(struct MDC *this)
{
  void *v2; // rcx
  _QWORD *v3; // rdi
  _QWORD *v4; // rsi
  unsigned int i; // edi
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // r8

  if ( !gbDisableMetaFiles )
  {
    v2 = (void *)*((_QWORD *)this + 21);
    if ( v2 )
      LocalFree(v2);
    v3 = (_QWORD *)((char *)this + 744);
    v4 = (_QWORD *)*((_QWORD *)this + 93);
    while ( v4 != v3 )
    {
      v8 = v4;
      v4 = (_QWORD *)*v4;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
    }
    *((_QWORD *)this + 94) = (char *)this + 744;
    *v3 = v3;
    if ( *((_QWORD *)this + 19) )
    {
      for ( i = 1; i < *((_DWORD *)this + 36); ++i )
      {
        if ( *(_QWORD *)(*((_QWORD *)this + 19) + 24LL * i) )
          vFreeMHE(*((void **)this + 95), i);
      }
      LocalFree(*((HLOCAL *)this + 19));
    }
    v6 = (void *)*((_QWORD *)this + 2);
    if ( v6 )
    {
      if ( *((char *)this + 32) >= 0 )
        LocalFree(v6);
      else
        MDC::CompleteEMFData(this, 0);
    }
    v7 = (void *)*((_QWORD *)this + 1);
    if ( v7 != (void *)-1LL && CloseHandle(v7) )
      *((_QWORD *)this + 1) = 0;
    if ( (*((_BYTE *)this + 32) & 3) == 3 )
      DeleteFileW((LPCWSTR)this + 108);
    *(_DWORD *)this = 0;
    LocalFree(this);
  }
}

```

## disassembly

```asm
0x18002cfe8  mov     [rsp+arg_0], rbx
0x18002cfed  mov     [rsp+arg_8], rsi
0x18002cff2  push    rdi
0x18002cff3  sub     rsp, 20h
0x18002cff7  cmp     cs:gbDisableMetaFiles, 0
0x18002cffe  mov     rbx, rcx
0x18002d001  jnz     loc_18002D0C1
0x18002d007  mov     rcx, [rcx+0A8h]; hMem
0x18002d00e  test    rcx, rcx
0x18002d011  jnz     loc_18002D0F8
0x18002d017  lea     rdi, [rbx+2E8h]
0x18002d01e  mov     rsi, [rdi]
0x18002d021  cmp     rsi, rdi
0x18002d024  jnz     loc_18002D0D2
0x18002d02a  mov     [rdi+8], rdi
0x18002d02e  mov     [rdi], rdi
0x18002d031  cmp     qword ptr [rbx+98h], 0
0x18002d039  jz      short loc_18002D087
0x18002d03b  mov     edi, 1
0x18002d040  cmp     [rbx+90h], edi
0x18002d046  jbe     short loc_18002D074
0x18002d048  mov     eax, edi
0x18002d04a  lea     rcx, [rax+rax*2]
0x18002d04e  mov     rax, [rbx+98h]
0x18002d055  cmp     qword ptr [rax+rcx*8], 0
0x18002d05a  jz      short loc_18002D06A
0x18002d05c  mov     rcx, [rbx+2F8h]; void *
0x18002d063  mov     edx, edi; unsigned int
0x18002d065  call    ?vFreeMHE@@YAXPEAXK@Z; vFreeMHE(void *,ulong)
0x18002d06a  inc     edi
0x18002d06c  cmp     edi, [rbx+90h]
0x18002d072  jb      short loc_18002D048
0x18002d074  mov     rcx, [rbx+98h]; hMem
0x18002d07b  call    cs:__imp_LocalFree
0x18002d082  nop     dword ptr [rax+rax+00h]
0x18002d087  mov     rcx, [rbx+10h]; hMem
0x18002d08b  test    rcx, rcx
0x18002d08e  jnz     short loc_18002D109
0x18002d090  mov     rcx, [rbx+8]; hObject
0x18002d094  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002d098  jnz     loc_18002D12F
0x18002d09e  mov     eax, [rbx+20h]
0x18002d0a1  and     eax, 3
0x18002d0a4  cmp     al, 3
0x18002d0a6  jz      loc_18002D150
0x18002d0ac  mov     rcx, rbx; hMem
0x18002d0af  mov     dword ptr [rbx], 0
0x18002d0b5  call    cs:__imp_LocalFree
0x18002d0bc  nop     dword ptr [rax+rax+00h]
0x18002d0c1  mov     rbx, [rsp+28h+arg_0]
0x18002d0c6  mov     rsi, [rsp+28h+arg_8]
0x18002d0cb  add     rsp, 20h
0x18002d0cf  pop     rdi
0x18002d0d0  retn
0x18002d0d2  mov     rcx, gs:60h
0x18002d0db  mov     r8, rsi; P
0x18002d0de  mov     rsi, [rsi]
0x18002d0e1  xor     edx, edx; Flags
0x18002d0e3  mov     rcx, [rcx+30h]; HeapHandle
0x18002d0e7  call    cs:__imp_RtlFreeHeap
0x18002d0ee  nop     dword ptr [rax+rax+00h]
0x18002d0f3  jmp     loc_18002D021
0x18002d0f8  call    cs:__imp_LocalFree
0x18002d0ff  nop     dword ptr [rax+rax+00h]
0x18002d104  jmp     loc_18002D017
0x18002d109  test    byte ptr [rbx+20h], 80h
0x18002d10d  jz      short loc_18002D11E
0x18002d10f  xor     edx, edx; int
0x18002d111  mov     rcx, rbx; this
0x18002d114  call    ?CompleteEMFData@MDC@@QEAAPEAXH@Z; MDC::CompleteEMFData(int)
0x18002d119  jmp     loc_18002D090
0x18002d11e  call    cs:__imp_LocalFree
0x18002d125  nop     dword ptr [rax+rax+00h]
0x18002d12a  jmp     loc_18002D090
0x18002d12f  call    cs:__imp_CloseHandle
0x18002d136  nop     dword ptr [rax+rax+00h]
0x18002d13b  test    eax, eax
0x18002d13d  jz      loc_18002D09E
0x18002d143  mov     qword ptr [rbx+8], 0
0x18002d14b  jmp     loc_18002D09E
0x18002d150  lea     rcx, [rbx+0D8h]; lpFileName
0x18002d157  call    cs:__imp_DeleteFileW
0x18002d15e  nop     dword ptr [rax+rax+00h]
0x18002d163  jmp     loc_18002D0AC
```
