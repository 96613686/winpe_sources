# GetImageFileIndexInfo(ushort const *,_GUID *,ulong *,ulong)

- ea: `0x1801ad738`
- end: `0x1801ad7e1`
- name: `?GetImageFileIndexInfo@@YAHPEBGPEAU_GUID@@PEAKK@Z`
- size: `169`
- prototype: `int(const unsigned __int16 *, struct _GUID *, unsigned int *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1801adb90`
- `0x1801ae840`

## callees

- `0x1801ad738`
- `0x1801ad7e8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801ad77e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801ad77e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801ad7ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801ad7ce`

## pseudocode

```c
__int64 __fastcall GetImageFileIndexInfo(const unsigned __int16 *a1, struct _GUID *a2, unsigned int *a3, char a4)
{
  HANDLE FileW; // rax
  void *v8; // rdi
  unsigned int v10; // ebx
  unsigned int v11; // eax
  unsigned int v12; // [rsp+40h] [rbp-38h] BYREF
  unsigned int v13[13]; // [rsp+44h] [rbp-34h] BYREF

  v12 = 0;
  v13[0] = 0;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0, 0);
  v8 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return 0;
  v10 = 0;
  if ( (unsigned int)GetImageIndexInfo(FileW, a3, &v12, v13) )
  {
    v11 = v12;
    *a2 = 0;
    a2->Data1 = v11;
    if ( (a4 & 0x10) != 0 )
      *a3 = v13[0];
    v10 = 1;
  }
  CloseHandle(v8);
  return v10;
}

```

## disassembly

```asm
0x1801ad738  mov     rax, rsp
0x1801ad73b  push    rbx
0x1801ad73c  push    rbp
0x1801ad73d  push    rsi
0x1801ad73e  push    rdi
0x1801ad73f  push    r14
0x1801ad741  sub     rsp, 50h
0x1801ad745  mov     qword ptr [rax-48h], 0
0x1801ad74d  mov     ebp, r9d
0x1801ad750  xor     r9d, r9d; lpSecurityAttributes
0x1801ad753  mov     dword ptr [rax-50h], 0
0x1801ad75a  mov     rsi, r8
0x1801ad75d  mov     dword ptr [rax-38h], 0
0x1801ad764  mov     r14, rdx
0x1801ad767  mov     dword ptr [rax-34h], 0
0x1801ad76e  mov     edx, 80000000h; dwDesiredAccess
0x1801ad773  mov     dword ptr [rax-58h], 3
0x1801ad77a  lea     r8d, [r9+1]; dwShareMode
0x1801ad77e  call    cs:__imp_CreateFileW
0x1801ad784  mov     rdi, rax
0x1801ad787  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801ad78b  jnz     short loc_1801AD791
0x1801ad78d  xor     eax, eax
0x1801ad78f  jmp     short loc_1801AD7D6
0x1801ad791  lea     r9, [rsp+78h+var_34]; unsigned int *
0x1801ad796  mov     rdx, rsi; unsigned int *
0x1801ad799  lea     r8, [rsp+78h+var_38]; unsigned int *
0x1801ad79e  mov     rcx, rdi; void *
0x1801ad7a1  xor     ebx, ebx
0x1801ad7a3  call    ?GetImageIndexInfo@@YAHPEAXPEAK11@Z; GetImageIndexInfo(void *,ulong *,ulong *,ulong *)
0x1801ad7a8  test    eax, eax
0x1801ad7aa  jz      short loc_1801AD7CB
0x1801ad7ac  mov     eax, [rsp+78h+var_38]
0x1801ad7b0  xorps   xmm0, xmm0
0x1801ad7b3  movups  xmmword ptr [r14], xmm0
0x1801ad7b7  mov     [r14], eax
0x1801ad7ba  test    bpl, 10h
0x1801ad7be  jz      short loc_1801AD7C6
0x1801ad7c0  mov     eax, [rsp+78h+var_34]
0x1801ad7c4  mov     [rsi], eax
0x1801ad7c6  mov     ebx, 1
0x1801ad7cb  mov     rcx, rdi; hObject
0x1801ad7ce  call    cs:__imp_CloseHandle
0x1801ad7d4  mov     eax, ebx
0x1801ad7d6  add     rsp, 50h
0x1801ad7da  pop     r14
0x1801ad7dc  pop     rdi
0x1801ad7dd  pop     rsi
0x1801ad7de  pop     rbp
0x1801ad7df  pop     rbx
0x1801ad7e0  retn
```
