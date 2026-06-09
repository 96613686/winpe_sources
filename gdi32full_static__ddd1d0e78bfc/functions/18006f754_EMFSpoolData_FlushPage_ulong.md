# EMFSpoolData::FlushPage(ulong)

- ea: `0x18006f754`
- end: `0x18006f82a`
- name: `?FlushPage@EMFSpoolData@@QEAAHK@Z`
- size: `214`
- prototype: `__int64 __fastcall(EMFSpoolData *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180099e04`

## callees

- `0x18006f754`
- `0x18006f830`
- `0x18007dd58`
- `0x18007e148`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18006f7be`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18006f7be`
- `ntdll!RtlDecodePointer` at `0x18006f7d1`
- `ntdll!RtlDecodePointer` at `0x18006f7d1`

## pseudocode

```c
int __fastcall EMFSpoolData::FlushPage(EMFSpoolData *this, int a2)
{
  int result; // eax
  unsigned int v4; // edi
  PVOID v5; // rax
  __int64 v6; // rsi
  _DWORD v7[2]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v8; // [rsp+28h] [rbp-10h]

  v7[1] = 8;
  v7[0] = 14 - (a2 != 10);
  v8 = *((_QWORD *)this + 6) + *((unsigned int *)this + 15) - *((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = -1;
  result = EMFSpoolData::WriteData(this, v7, 0x10u);
  if ( result )
  {
    v4 = *((_DWORD *)this + 12) + *((_DWORD *)this + 15) - *((_DWORD *)this + 6);
    SetFilePointerEx(*((HANDLE *)this + 2), *(LARGE_INTEGER *)((char *)this + 24), 0, 0);
    v5 = RtlDecodePointer(fpCommitSpoolData);
    v6 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))v5)(*((_QWORD *)this + 1), *((_QWORD *)this + 2), v4);
    if ( v6 == *((_QWORD *)this + 2) )
    {
      *((_QWORD *)this + 3) += v4;
      return 1;
    }
    else
    {
      EMFSpoolData::UnmapFile(this, 0);
      *((_QWORD *)this + 2) = v6;
      return EMFSpoolData::MapFile(this);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18006f754  mov     r11, rsp
0x18006f757  mov     [r11+8], rbx
0x18006f75b  mov     [r11+10h], rsi
0x18006f75f  push    rdi
0x18006f760  sub     rsp, 30h
0x18006f764  sub     edx, 0Ah
0x18006f767  mov     [rsp+38h+var_14], 8
0x18006f76f  neg     edx
0x18006f771  mov     r8d, 10h; unsigned int
0x18006f777  lea     rdx, [r11-18h]; void *
0x18006f77b  mov     rbx, rcx
0x18006f77e  sbb     eax, eax
0x18006f780  add     eax, 0Eh
0x18006f783  mov     [rsp+38h+var_18], eax
0x18006f787  mov     eax, [rcx+3Ch]
0x18006f78a  sub     rax, [rcx+20h]
0x18006f78e  add     rax, [rcx+30h]
0x18006f792  mov     [r11-10h], rax
0x18006f796  mov     qword ptr [rcx+20h], 0FFFFFFFFFFFFFFFFh
0x18006f79e  call    ?WriteData@EMFSpoolData@@QEAAHPEAXK@Z; EMFSpoolData::WriteData(void *,ulong)
0x18006f7a3  test    eax, eax
0x18006f7a5  jz      short loc_18006F819
0x18006f7a7  mov     edi, [rbx+3Ch]
0x18006f7aa  xor     r9d, r9d; dwMoveMethod
0x18006f7ad  sub     edi, [rbx+18h]
0x18006f7b0  xor     r8d, r8d; lpNewFilePointer
0x18006f7b3  mov     rdx, [rbx+18h]; liDistanceToMove
0x18006f7b7  mov     rcx, [rbx+10h]; hFile
0x18006f7bb  add     edi, [rbx+30h]
0x18006f7be  call    cs:__imp_SetFilePointerEx
0x18006f7c5  nop     dword ptr [rax+rax+00h]
0x18006f7ca  mov     rcx, cs:fpCommitSpoolData; Pointer
0x18006f7d1  call    cs:__imp_RtlDecodePointer
0x18006f7d8  nop     dword ptr [rax+rax+00h]
0x18006f7dd  mov     rdx, [rbx+10h]
0x18006f7e1  mov     r8d, edi
0x18006f7e4  mov     rcx, [rbx+8]
0x18006f7e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f7ed  mov     rsi, rax
0x18006f7f0  cmp     rax, [rbx+10h]
0x18006f7f4  jnz     short loc_18006F803
0x18006f7f6  mov     eax, edi
0x18006f7f8  add     [rbx+18h], rax
0x18006f7fc  mov     eax, 1
0x18006f801  jmp     short loc_18006F819
0x18006f803  xor     edx, edx; int
0x18006f805  mov     rcx, rbx; this
0x18006f808  call    ?UnmapFile@EMFSpoolData@@QEAAXH@Z; EMFSpoolData::UnmapFile(int)
0x18006f80d  mov     rcx, rbx; this
0x18006f810  mov     [rbx+10h], rsi
0x18006f814  call    ?MapFile@EMFSpoolData@@QEAAHXZ; EMFSpoolData::MapFile(void)
0x18006f819  mov     rbx, [rsp+38h+arg_0]
0x18006f81e  mov     rsi, [rsp+38h+arg_8]
0x18006f823  add     rsp, 30h
0x18006f827  pop     rdi
0x18006f828  retn
```
