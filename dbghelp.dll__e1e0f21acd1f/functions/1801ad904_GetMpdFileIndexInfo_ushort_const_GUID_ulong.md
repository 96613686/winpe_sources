# GetMpdFileIndexInfo(ushort const *,_GUID *,ulong *)

- ea: `0x1801ad904`
- end: `0x1801ad97a`
- name: `?GetMpdFileIndexInfo@@YAHPEBGPEAU_GUID@@PEAK@Z`
- size: `118`
- prototype: `int(const unsigned __int16 *, struct _GUID *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1801adb90`
- `0x1801ae840`

## callees

- `0x1801ad904`
- `0x1801ad980`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801ad93c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801ad93c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801ad962`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801ad962`

## pseudocode

```c
__int64 __fastcall GetMpdFileIndexInfo(const unsigned __int16 *a1, struct _GUID *a2, unsigned int *a3)
{
  HANDLE FileW; // rax
  void *v6; // rdi
  unsigned int MpdIndexInfo; // ebx

  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0, 0);
  v6 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return 0;
  MpdIndexInfo = GetMpdIndexInfo(FileW, a2, a3);
  CloseHandle(v6);
  return MpdIndexInfo;
}

```

## disassembly

```asm
0x1801ad904  mov     rax, rsp
0x1801ad907  mov     [rax+8], rbx
0x1801ad90b  mov     [rax+10h], rsi
0x1801ad90f  push    rdi
0x1801ad910  sub     rsp, 40h
0x1801ad914  mov     qword ptr [rax-18h], 0
0x1801ad91c  xor     r9d, r9d; lpSecurityAttributes
0x1801ad91f  mov     rbx, r8
0x1801ad922  mov     dword ptr [rax-20h], 0
0x1801ad929  mov     rsi, rdx
0x1801ad92c  mov     dword ptr [rax-28h], 3
0x1801ad933  mov     edx, 80000000h; dwDesiredAccess
0x1801ad938  lea     r8d, [r9+1]; dwShareMode
0x1801ad93c  call    cs:__imp_CreateFileW
0x1801ad942  mov     rdi, rax
0x1801ad945  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801ad949  jnz     short loc_1801AD94F
0x1801ad94b  xor     eax, eax
0x1801ad94d  jmp     short loc_1801AD96A
0x1801ad94f  mov     r8, rbx; unsigned int *
0x1801ad952  mov     rdx, rsi; struct _GUID *
0x1801ad955  mov     rcx, rdi; void *
0x1801ad958  call    ?GetMpdIndexInfo@@YAHPEAXPEAU_GUID@@PEAK@Z; GetMpdIndexInfo(void *,_GUID *,ulong *)
0x1801ad95d  mov     rcx, rdi; hObject
0x1801ad960  mov     ebx, eax
0x1801ad962  call    cs:__imp_CloseHandle
0x1801ad968  mov     eax, ebx
0x1801ad96a  mov     rbx, [rsp+48h+arg_0]
0x1801ad96f  mov     rsi, [rsp+48h+arg_8]
0x1801ad974  add     rsp, 40h
0x1801ad978  pop     rdi
0x1801ad979  retn
```
