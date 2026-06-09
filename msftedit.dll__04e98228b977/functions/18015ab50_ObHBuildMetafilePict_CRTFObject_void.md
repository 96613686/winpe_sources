# ObHBuildMetafilePict(CRTFObject *,void * &)

- ea: `0x18015ab50`
- end: `0x18015ac51`
- name: `?ObHBuildMetafilePict@@YAPEAXPEAVCRTFObject@@AEAPEAX@Z`
- size: `257`
- prototype: `void *__fastcall(struct CRTFObject *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18008a47c`
- `0x18015ab50`
- `0x180209568`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18015ab67`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18015ab67`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18015abe3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18015abf9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18015ac2e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18015abe3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18015abf9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18015ac2e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18015ab82`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18015abaf`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18015ab82`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18015abaf`
- `ext-ms-win-gdi-metafile-l1-1-0!SetMetaFileBitsEx` at `0x18015abd0`
- `ext-ms-win-gdi-metafile-l1-1-0!SetMetaFileBitsEx` at `0x18015abd0`
- `ext-ms-win-gdi-metafile-l1-1-0!DeleteMetaFile` at `0x18015ac1f`
- `ext-ms-win-gdi-metafile-l1-1-0!DeleteMetaFile` at `0x18015ac1f`

## pseudocode

```c
void *__fastcall ObHBuildMetafilePict(struct CRTFObject *a1, void **a2)
{
  HGLOBAL v4; // rax
  void *v5; // rbx
  _DWORD *v6; // rax
  _DWORD *v7; // rdi
  const BYTE *v8; // rbp
  UINT v9; // eax
  HMETAFILE v10; // rcx

  v4 = GlobalAlloc(0x42u, 0x18u);
  v5 = v4;
  if ( v4 )
  {
    v6 = GlobalLock(v4);
    v7 = v6;
    if ( v6 )
    {
      *v6 = *((__int16 *)a1 + 1);
      v6[1] = *((_DWORD *)a1 + 5);
      v6[2] = *((_DWORD *)a1 + 6);
      v8 = (const BYTE *)GlobalLock(*a2);
      if ( v8 )
      {
        v9 = CW32System::GlobalSize(*a2);
        *((_QWORD *)v7 + 2) = SetMetaFileBitsEx(v9, v8);
        GlobalUnlock(*a2);
        if ( *((_QWORD *)v7 + 2) )
        {
          GlobalUnlock(v5);
          CW32System::GlobalFree(*a2);
          *a2 = 0;
          return v5;
        }
      }
      v10 = (HMETAFILE)*((_QWORD *)v7 + 2);
      if ( v10 )
        DeleteMetaFile(v10);
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
0x18015ab50  push    rbx
0x18015ab52  push    rbp
0x18015ab53  push    rsi
0x18015ab54  push    rdi
0x18015ab55  sub     rsp, 28h
0x18015ab59  mov     rsi, rdx
0x18015ab5c  mov     rbp, rcx
0x18015ab5f  mov     edx, 18h; dwBytes
0x18015ab64  lea     ecx, [rdx+2Ah]; uFlags
0x18015ab67  call    cs:__imp_GlobalAlloc
0x18015ab6e  nop     dword ptr [rax+rax+00h]
0x18015ab73  mov     rbx, rax
0x18015ab76  test    rax, rax
0x18015ab79  jz      loc_18015AC44
0x18015ab7f  mov     rcx, rax; hMem
0x18015ab82  call    cs:__imp_GlobalLock
0x18015ab89  nop     dword ptr [rax+rax+00h]
0x18015ab8e  mov     rdi, rax
0x18015ab91  test    rax, rax
0x18015ab94  jz      loc_18015AC3A
0x18015ab9a  movsx   ecx, word ptr [rbp+2]
0x18015ab9e  mov     [rax], ecx
0x18015aba0  mov     ecx, [rbp+14h]
0x18015aba3  mov     [rax+4], ecx
0x18015aba6  mov     ecx, [rbp+18h]
0x18015aba9  mov     [rax+8], ecx
0x18015abac  mov     rcx, [rsi]; hMem
0x18015abaf  call    cs:__imp_GlobalLock
0x18015abb6  nop     dword ptr [rax+rax+00h]
0x18015abbb  mov     rbp, rax
0x18015abbe  test    rax, rax
0x18015abc1  jz      short loc_18015AC16
0x18015abc3  mov     rcx, [rsi]; void *
0x18015abc6  call    ?GlobalSize@CW32System@@SAKPEAX@Z; CW32System::GlobalSize(void *)
0x18015abcb  mov     rdx, rbp; lpData
0x18015abce  mov     ecx, eax; cbBuffer
0x18015abd0  call    cs:__imp_SetMetaFileBitsEx
0x18015abd7  nop     dword ptr [rax+rax+00h]
0x18015abdc  mov     [rdi+10h], rax
0x18015abe0  mov     rcx, [rsi]; hMem
0x18015abe3  call    cs:__imp_GlobalUnlock
0x18015abea  nop     dword ptr [rax+rax+00h]
0x18015abef  cmp     qword ptr [rdi+10h], 0
0x18015abf4  jz      short loc_18015AC16
0x18015abf6  mov     rcx, rbx; hMem
0x18015abf9  call    cs:__imp_GlobalUnlock
0x18015ac00  nop     dword ptr [rax+rax+00h]
0x18015ac05  mov     rcx, [rsi]; void *
0x18015ac08  call    ?GlobalFree@CW32System@@SAPEAXPEAX@Z; CW32System::GlobalFree(void *)
0x18015ac0d  mov     qword ptr [rsi], 0
0x18015ac14  jmp     short loc_18015AC44
0x18015ac16  mov     rcx, [rdi+10h]; hmf
0x18015ac1a  test    rcx, rcx
0x18015ac1d  jz      short loc_18015AC2B
0x18015ac1f  call    cs:__imp_DeleteMetaFile
0x18015ac26  nop     dword ptr [rax+rax+00h]
0x18015ac2b  mov     rcx, rbx; hMem
0x18015ac2e  call    cs:__imp_GlobalUnlock
0x18015ac35  nop     dword ptr [rax+rax+00h]
0x18015ac3a  mov     rcx, rbx; void *
0x18015ac3d  call    ?GlobalFree@CW32System@@SAPEAXPEAX@Z; CW32System::GlobalFree(void *)
0x18015ac42  xor     ebx, ebx
0x18015ac44  mov     rax, rbx
0x18015ac47  add     rsp, 28h
0x18015ac4b  pop     rdi
0x18015ac4c  pop     rsi
0x18015ac4d  pop     rbp
0x18015ac4e  pop     rbx
0x18015ac4f  retn
```
