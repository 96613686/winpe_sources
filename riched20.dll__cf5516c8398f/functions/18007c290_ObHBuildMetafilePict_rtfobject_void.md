# ObHBuildMetafilePict(_rtfobject *,void * &)

- ea: `0x18007c290`
- end: `0x18007c358`
- name: `?ObHBuildMetafilePict@@YAPEAXPEAU_rtfobject@@AEAPEAX@Z`
- size: `200`
- prototype: `void *__fastcall(struct _rtfobject *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18004a8fc`
- `0x18007c290`

## import_xrefs

- `KERNEL32!GlobalSize` at `0x18007c2ec`
- `KERNEL32!GlobalSize` at `0x18007c2ec`
- `KERNEL32!GlobalAlloc` at `0x18007c2a8`
- `KERNEL32!GlobalAlloc` at `0x18007c2a8`
- `KERNEL32!GlobalLock` at `0x18007c2bd`
- `KERNEL32!GlobalLock` at `0x18007c2e0`
- `KERNEL32!GlobalLock` at `0x18007c2bd`
- `KERNEL32!GlobalLock` at `0x18007c2e0`
- `KERNEL32!GlobalUnlock` at `0x18007c30a`
- `KERNEL32!GlobalUnlock` at `0x18007c313`
- `KERNEL32!GlobalUnlock` at `0x18007c33b`
- `KERNEL32!GlobalUnlock` at `0x18007c30a`
- `KERNEL32!GlobalUnlock` at `0x18007c313`
- `KERNEL32!GlobalUnlock` at `0x18007c33b`
- `GDI32!DeleteMetaFile` at `0x18007c332`
- `GDI32!DeleteMetaFile` at `0x18007c332`
- `GDI32!SetMetaFileBitsEx` at `0x18007c2f8`
- `GDI32!SetMetaFileBitsEx` at `0x18007c2f8`

## pseudocode

```c
void *__fastcall ObHBuildMetafilePict(struct _rtfobject *a1, void **a2)
{
  HGLOBAL v4; // rax
  void *v5; // rdi
  _DWORD *v6; // rax
  _DWORD *v7; // r14
  const BYTE *v8; // rbx
  UINT v9; // eax
  HMETAFILE v10; // rax

  v4 = GlobalAlloc(0x42u, 0x18u);
  v5 = v4;
  if ( v4 )
  {
    v6 = GlobalLock(v4);
    v7 = v6;
    if ( v6 )
    {
      *v6 = *((__int16 *)a1 + 1);
      v6[1] = *((_DWORD *)a1 + 4);
      v6[2] = *((_DWORD *)a1 + 5);
      v8 = (const BYTE *)GlobalLock(*a2);
      v9 = GlobalSize(*a2);
      v10 = SetMetaFileBitsEx(v9, v8);
      *((_QWORD *)v7 + 2) = v10;
      if ( v10 )
      {
        GlobalUnlock(v5);
        GlobalUnlock(*a2);
        CW32System::GlobalFree(*a2);
        *a2 = 0;
        return v5;
      }
      GlobalUnlock(v5);
    }
    CW32System::GlobalFree(v5);
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x18007c290  push    rbx
0x18007c292  push    rsi
0x18007c293  push    rdi
0x18007c294  push    r14
0x18007c296  sub     rsp, 28h
0x18007c29a  mov     rsi, rdx
0x18007c29d  mov     rbx, rcx
0x18007c2a0  mov     edx, 18h; dwBytes
0x18007c2a5  lea     ecx, [rdx+2Ah]; uFlags
0x18007c2a8  call    cs:__imp_GlobalAlloc
0x18007c2ae  mov     rdi, rax
0x18007c2b1  test    rax, rax
0x18007c2b4  jz      loc_18007C34B
0x18007c2ba  mov     rcx, rax; hMem
0x18007c2bd  call    cs:__imp_GlobalLock
0x18007c2c3  mov     r14, rax
0x18007c2c6  test    rax, rax
0x18007c2c9  jz      short loc_18007C341
0x18007c2cb  movsx   ecx, word ptr [rbx+2]
0x18007c2cf  mov     [rax], ecx
0x18007c2d1  mov     ecx, [rbx+10h]
0x18007c2d4  mov     [rax+4], ecx
0x18007c2d7  mov     ecx, [rbx+14h]
0x18007c2da  mov     [rax+8], ecx
0x18007c2dd  mov     rcx, [rsi]; hMem
0x18007c2e0  call    cs:__imp_GlobalLock
0x18007c2e6  mov     rcx, [rsi]; hMem
0x18007c2e9  mov     rbx, rax
0x18007c2ec  call    cs:__imp_GlobalSize
0x18007c2f2  mov     rcx, rax; cbBuffer
0x18007c2f5  mov     rdx, rbx; lpData
0x18007c2f8  call    cs:__imp_SetMetaFileBitsEx
0x18007c2fe  mov     [r14+10h], rax
0x18007c302  test    rax, rax
0x18007c305  jz      short loc_18007C32A
0x18007c307  mov     rcx, rdi; hMem
0x18007c30a  call    cs:__imp_GlobalUnlock
0x18007c310  mov     rcx, [rsi]; hMem
0x18007c313  call    cs:__imp_GlobalUnlock
0x18007c319  mov     rcx, [rsi]; void *
0x18007c31c  call    ?GlobalFree@CW32System@@SAPEAXPEAX@Z; CW32System::GlobalFree(void *)
0x18007c321  mov     qword ptr [rsi], 0
0x18007c328  jmp     short loc_18007C34B
0x18007c32a  mov     rcx, rax; hmf
0x18007c32d  test    rax, rax
0x18007c330  jz      short loc_18007C338
0x18007c332  call    cs:__imp_DeleteMetaFile
0x18007c338  mov     rcx, rdi; hMem
0x18007c33b  call    cs:__imp_GlobalUnlock
0x18007c341  mov     rcx, rdi; void *
0x18007c344  call    ?GlobalFree@CW32System@@SAPEAXPEAX@Z; CW32System::GlobalFree(void *)
0x18007c349  xor     edi, edi
0x18007c34b  mov     rax, rdi
0x18007c34e  add     rsp, 28h
0x18007c352  pop     r14
0x18007c354  pop     rdi
0x18007c355  pop     rsi
0x18007c356  pop     rbx
0x18007c357  retn
```
