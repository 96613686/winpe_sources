# PROXYPORT::Close(void)

- ea: `0x18009b3c8`
- end: `0x18009b452`
- name: `?Close@PROXYPORT@@QEAAXXZ`
- size: `138`
- prototype: `void __fastcall(PROXYPORT *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18003fb74`
- `0x1800410a4`

## callees

- `0x18009b3c8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009b3dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009b3f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009b3dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009b3f4`
- `ntdll!RtlFreeHeap` at `0x18009b438`
- `ntdll!RtlFreeHeap` at `0x18009b438`
- `ntdll!RtlDeleteCriticalSection` at `0x18009b41a`
- `ntdll!RtlDeleteCriticalSection` at `0x18009b41a`
- `ntdll!RtlLeaveCriticalSection` at `0x18009b407`
- `ntdll!RtlLeaveCriticalSection` at `0x18009b407`

## pseudocode

```c
void __fastcall PROXYPORT::Close(PVOID *this)
{
  void *v2; // rcx
  void *v3; // rcx

  v2 = (void *)*((_QWORD *)*this + 1);
  if ( v2 )
    CloseHandle(v2);
  v3 = *(void **)*this;
  if ( v3 )
    CloseHandle(v3);
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)*this + 16));
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)*this + 16));
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *this);
  *this = 0;
}

```

## disassembly

```asm
0x18009b3c8  push    rbx
0x18009b3ca  sub     rsp, 20h
0x18009b3ce  mov     rax, [rcx]
0x18009b3d1  mov     rbx, rcx
0x18009b3d4  mov     rcx, [rax+8]; hObject
0x18009b3d8  test    rcx, rcx
0x18009b3db  jz      short loc_18009B3E9
0x18009b3dd  call    cs:__imp_CloseHandle
0x18009b3e4  nop     dword ptr [rax+rax+00h]
0x18009b3e9  mov     rax, [rbx]
0x18009b3ec  mov     rcx, [rax]; hObject
0x18009b3ef  test    rcx, rcx
0x18009b3f2  jz      short loc_18009B400
0x18009b3f4  call    cs:__imp_CloseHandle
0x18009b3fb  nop     dword ptr [rax+rax+00h]
0x18009b400  mov     rcx, [rbx]
0x18009b403  add     rcx, 10h; CriticalSection
0x18009b407  call    cs:__imp_RtlLeaveCriticalSection
0x18009b40e  nop     dword ptr [rax+rax+00h]
0x18009b413  mov     rcx, [rbx]
0x18009b416  add     rcx, 10h; CriticalSection
0x18009b41a  call    cs:__imp_RtlDeleteCriticalSection
0x18009b421  nop     dword ptr [rax+rax+00h]
0x18009b426  mov     rcx, gs:60h
0x18009b42f  xor     edx, edx; Flags
0x18009b431  mov     r8, [rbx]; P
0x18009b434  mov     rcx, [rcx+30h]; HeapHandle
0x18009b438  call    cs:__imp_RtlFreeHeap
0x18009b43f  nop     dword ptr [rax+rax+00h]
0x18009b444  mov     qword ptr [rbx], 0
0x18009b44b  add     rsp, 20h
0x18009b44f  pop     rbx
0x18009b450  retn
```
