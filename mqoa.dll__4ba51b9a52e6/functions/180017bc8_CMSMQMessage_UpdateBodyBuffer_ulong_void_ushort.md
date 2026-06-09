# CMSMQMessage::UpdateBodyBuffer(ulong,void *,ushort)

- ea: `0x180017bc8`
- end: `0x180017cae`
- name: `?UpdateBodyBuffer@CMSMQMessage@@IEAAJKPEAXG@Z`
- size: `230`
- prototype: `__int64 __fastcall(CMSMQMessage *this, unsigned int, void *, __int16)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800160e4`
- `0x180016560`

## callees

- `0x180017bc8`
- `0x180027372`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180017c97`
- `KERNEL32!GetLastError` at `0x180017c97`
- `KERNEL32!GlobalAlloc` at `0x180017c26`
- `KERNEL32!GlobalAlloc` at `0x180017c26`
- `KERNEL32!GlobalLock` at `0x180017c42`
- `KERNEL32!GlobalLock` at `0x180017c42`
- `KERNEL32!GlobalFree` at `0x180017be9`
- `KERNEL32!GlobalFree` at `0x180017c60`
- `KERNEL32!GlobalFree` at `0x180017be9`
- `KERNEL32!GlobalFree` at `0x180017c60`
- `KERNEL32!GlobalUnlock` at `0x180017c8d`
- `KERNEL32!GlobalUnlock` at `0x180017c8d`

## pseudocode

```c
__int64 __fastcall CMSMQMessage::UpdateBodyBuffer(CMSMQMessage *this, unsigned int a2, void *a3, __int16 a4)
{
  SIZE_T v5; // rdi
  void *v6; // rcx
  HGLOBAL v9; // rax
  void *v11; // rax
  void *v12; // rcx
  void *v13; // rcx

  v5 = a2;
  v6 = (void *)*((_QWORD *)this + 30);
  if ( v6 )
  {
    GlobalFree(v6);
    *((_QWORD *)this + 30) = 0;
  }
  *((_QWORD *)this + 28) = 0;
  *((_DWORD *)this + 62) = 0;
  *((_WORD *)this + 116) = a4;
  if ( (_DWORD)v5 )
  {
    v9 = GlobalAlloc(0x22u, v5);
    *((_QWORD *)this + 30) = v9;
    if ( !v9 )
      return 2147942414LL;
    v11 = GlobalLock(v9);
    *((_QWORD *)this + 28) = v11;
    if ( !v11 )
    {
      v12 = (void *)*((_QWORD *)this + 30);
      if ( v12 )
      {
        GlobalFree(v12);
        *((_QWORD *)this + 30) = 0;
      }
      return 2147942414LL;
    }
    memcpy_0(v11, a3, v5);
    v13 = (void *)*((_QWORD *)this + 30);
    if ( v13 && !GlobalUnlock(v13) )
      GetLastError();
    *((_DWORD *)this + 62) = v5;
  }
  return 0;
}

```

## disassembly

```asm
0x180017bc8  push    rbx
0x180017bca  push    rbp
0x180017bcb  push    rsi
0x180017bcc  push    rdi
0x180017bcd  sub     rsp, 28h
0x180017bd1  mov     rbx, rcx
0x180017bd4  mov     edi, edx
0x180017bd6  mov     rcx, [rcx+0F0h]; hMem
0x180017bdd  movzx   esi, r9w
0x180017be1  mov     rbp, r8
0x180017be4  test    rcx, rcx
0x180017be7  jz      short loc_180017BFA
0x180017be9  call    cs:__imp_GlobalFree
0x180017bef  mov     qword ptr [rbx+0F0h], 0
0x180017bfa  mov     qword ptr [rbx+0E0h], 0
0x180017c05  mov     dword ptr [rbx+0F8h], 0
0x180017c0f  mov     [rbx+0E8h], si
0x180017c16  test    edi, edi
0x180017c18  jz      loc_180017CA3
0x180017c1e  mov     rdx, rdi; dwBytes
0x180017c21  mov     ecx, 22h ; '"'; uFlags
0x180017c26  call    cs:__imp_GlobalAlloc
0x180017c2c  mov     [rbx+0F0h], rax
0x180017c33  test    rax, rax
0x180017c36  jnz     short loc_180017C3F
0x180017c38  mov     eax, 8007000Eh
0x180017c3d  jmp     short loc_180017CA5
0x180017c3f  mov     rcx, rax; hMem
0x180017c42  call    cs:__imp_GlobalLock
0x180017c48  mov     [rbx+0E0h], rax
0x180017c4f  test    rax, rax
0x180017c52  jnz     short loc_180017C73
0x180017c54  mov     rcx, [rbx+0F0h]; hMem
0x180017c5b  test    rcx, rcx
0x180017c5e  jz      short loc_180017C38
0x180017c60  call    cs:__imp_GlobalFree
0x180017c66  mov     qword ptr [rbx+0F0h], 0
0x180017c71  jmp     short loc_180017C38
0x180017c73  mov     r8, rdi; Size
0x180017c76  mov     rdx, rbp; Src
0x180017c79  mov     rcx, rax; void *
0x180017c7c  call    memcpy_0
0x180017c81  mov     rcx, [rbx+0F0h]; hMem
0x180017c88  test    rcx, rcx
0x180017c8b  jz      short loc_180017C9D
0x180017c8d  call    cs:__imp_GlobalUnlock
0x180017c93  test    eax, eax
0x180017c95  jnz     short loc_180017C9D
0x180017c97  call    cs:__imp_GetLastError
0x180017c9d  mov     [rbx+0F8h], edi
0x180017ca3  xor     eax, eax
0x180017ca5  add     rsp, 28h
0x180017ca9  pop     rdi
0x180017caa  pop     rsi
0x180017cab  pop     rbp
0x180017cac  pop     rbx
0x180017cad  retn
```
