# ObHBuildMetafilePict(_rtfobject *,void * &)

- ea: `0x18007e610`
- end: `0x18007e713`
- name: `?ObHBuildMetafilePict@@YAPEAXPEAU_rtfobject@@AEAPEAX@Z`
- size: `259`
- prototype: `void *__fastcall(struct _rtfobject *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18004bac8`
- `0x18007e610`

## import_xrefs

- `KERNEL32!GlobalSize` at `0x18007e682`
- `KERNEL32!GlobalSize` at `0x18007e682`
- `KERNEL32!GlobalAlloc` at `0x18007e628`
- `KERNEL32!GlobalAlloc` at `0x18007e628`
- `KERNEL32!GlobalLock` at `0x18007e643`
- `KERNEL32!GlobalLock` at `0x18007e670`
- `KERNEL32!GlobalLock` at `0x18007e643`
- `KERNEL32!GlobalLock` at `0x18007e670`
- `KERNEL32!GlobalUnlock` at `0x18007e6ac`
- `KERNEL32!GlobalUnlock` at `0x18007e6bb`
- `KERNEL32!GlobalUnlock` at `0x18007e6ef`
- `KERNEL32!GlobalUnlock` at `0x18007e6ac`
- `KERNEL32!GlobalUnlock` at `0x18007e6bb`
- `KERNEL32!GlobalUnlock` at `0x18007e6ef`
- `GDI32!DeleteMetaFile` at `0x18007e6e0`
- `GDI32!DeleteMetaFile` at `0x18007e6e0`
- `GDI32!SetMetaFileBitsEx` at `0x18007e694`
- `GDI32!SetMetaFileBitsEx` at `0x18007e694`

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
0x18007e610  push    rbx
0x18007e612  push    rsi
0x18007e613  push    rdi
0x18007e614  push    r14
0x18007e616  sub     rsp, 28h
0x18007e61a  mov     rsi, rdx
0x18007e61d  mov     rbx, rcx
0x18007e620  mov     edx, 18h; dwBytes
0x18007e625  lea     ecx, [rdx+2Ah]; uFlags
0x18007e628  call    cs:__imp_GlobalAlloc
0x18007e62f  nop     dword ptr [rax+rax+00h]
0x18007e634  mov     rdi, rax
0x18007e637  test    rax, rax
0x18007e63a  jz      loc_18007E705
0x18007e640  mov     rcx, rax; hMem
0x18007e643  call    cs:__imp_GlobalLock
0x18007e64a  nop     dword ptr [rax+rax+00h]
0x18007e64f  mov     r14, rax
0x18007e652  test    rax, rax
0x18007e655  jz      loc_18007E6FB
0x18007e65b  movsx   ecx, word ptr [rbx+2]
0x18007e65f  mov     [rax], ecx
0x18007e661  mov     ecx, [rbx+10h]
0x18007e664  mov     [rax+4], ecx
0x18007e667  mov     ecx, [rbx+14h]
0x18007e66a  mov     [rax+8], ecx
0x18007e66d  mov     rcx, [rsi]; hMem
0x18007e670  call    cs:__imp_GlobalLock
0x18007e677  nop     dword ptr [rax+rax+00h]
0x18007e67c  mov     rcx, [rsi]; hMem
0x18007e67f  mov     rbx, rax
0x18007e682  call    cs:__imp_GlobalSize
0x18007e689  nop     dword ptr [rax+rax+00h]
0x18007e68e  mov     rcx, rax; cbBuffer
0x18007e691  mov     rdx, rbx; lpData
0x18007e694  call    cs:__imp_SetMetaFileBitsEx
0x18007e69b  nop     dword ptr [rax+rax+00h]
0x18007e6a0  mov     [r14+10h], rax
0x18007e6a4  test    rax, rax
0x18007e6a7  jz      short loc_18007E6D8
0x18007e6a9  mov     rcx, rdi; hMem
0x18007e6ac  call    cs:__imp_GlobalUnlock
0x18007e6b3  nop     dword ptr [rax+rax+00h]
0x18007e6b8  mov     rcx, [rsi]; hMem
0x18007e6bb  call    cs:__imp_GlobalUnlock
0x18007e6c2  nop     dword ptr [rax+rax+00h]
0x18007e6c7  mov     rcx, [rsi]; void *
0x18007e6ca  call    ?GlobalFree@CW32System@@SAPEAXPEAX@Z; CW32System::GlobalFree(void *)
0x18007e6cf  mov     qword ptr [rsi], 0
0x18007e6d6  jmp     short loc_18007E705
0x18007e6d8  mov     rcx, rax; hmf
0x18007e6db  test    rax, rax
0x18007e6de  jz      short loc_18007E6EC
0x18007e6e0  call    cs:__imp_DeleteMetaFile
0x18007e6e7  nop     dword ptr [rax+rax+00h]
0x18007e6ec  mov     rcx, rdi; hMem
0x18007e6ef  call    cs:__imp_GlobalUnlock
0x18007e6f6  nop     dword ptr [rax+rax+00h]
0x18007e6fb  mov     rcx, rdi; void *
0x18007e6fe  call    ?GlobalFree@CW32System@@SAPEAXPEAX@Z; CW32System::GlobalFree(void *)
0x18007e703  xor     edi, edi
0x18007e705  mov     rax, rdi
0x18007e708  add     rsp, 28h
0x18007e70c  pop     r14
0x18007e70e  pop     rdi
0x18007e70f  pop     rsi
0x18007e710  pop     rbx
0x18007e711  retn
```
