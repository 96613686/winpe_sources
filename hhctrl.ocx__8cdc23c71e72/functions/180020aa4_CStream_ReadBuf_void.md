# CStream::ReadBuf(void)

- ea: `0x180020aa4`
- end: `0x180020b70`
- name: `?ReadBuf@CStream@@QEAADXZ`
- size: `204`
- prototype: `char __fastcall(CStream *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180020bc4`
- `0x18002cf10`

## callees

- `0x180020aa4`
- `0x180020b78`

## import_xrefs

- `KERNEL32!ReleaseSemaphore` at `0x180020aef`
- `KERNEL32!ReleaseSemaphore` at `0x180020b08`
- `KERNEL32!ReleaseSemaphore` at `0x180020aef`
- `KERNEL32!ReleaseSemaphore` at `0x180020b08`
- `KERNEL32!_lread` at `0x180020b47`
- `KERNEL32!_lread` at `0x180020b47`

## pseudocode

```c
char __fastcall CStream::ReadBuf(CStream *this)
{
  void *v2; // rax
  signed int v3; // edi
  HANDLE v4; // rcx
  int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // rcx
  char result; // al
  char *v9; // rcx

  if ( *((_DWORD *)this + 19) )
  {
    CStream::WaitForReadAhead(this);
    v2 = Block;
    v3 = *((_DWORD *)this + 15);
    if ( *((void **)this + 5) == Block )
      v2 = lpBuffer;
    v4 = hSemaphore;
    *((_QWORD *)this + 5) = v2;
    *((_DWORD *)this + 15) = -2;
    ReleaseSemaphore(v4, 1, 0);
    if ( v3 == -1 )
      return -1;
    ReleaseSemaphore(hHandle, 1, 0);
  }
  else
  {
    v3 = _lread(*((_DWORD *)this + 7), *((LPVOID *)this + 5), *((_DWORD *)this + 14));
    if ( v3 == -1 )
      return -1;
  }
  v5 = *((_DWORD *)this + 8);
  v6 = *((_QWORD *)this + 5);
  *((_DWORD *)this + 9) = v5;
  *((_DWORD *)this + 8) = v3 + v5;
  *((_QWORD *)this + 1) = v6;
  v7 = v3 + v6;
  *((_QWORD *)this + 2) = v7;
  *(_BYTE *)(v7 + 1) = 0;
  if ( !v3 )
  {
    *((_DWORD *)this + 6) = 1;
    return -1;
  }
  v9 = (char *)*((_QWORD *)this + 1);
  result = *v9;
  *((_QWORD *)this + 1) = v9 + 1;
  return result;
}

```

## disassembly

```asm
0x180020aa4  mov     [rsp+arg_0], rbx
0x180020aa9  push    rdi
0x180020aaa  sub     rsp, 20h
0x180020aae  cmp     dword ptr [rcx+4Ch], 0
0x180020ab2  mov     rbx, rcx
0x180020ab5  jz      loc_180020B3C
0x180020abb  call    ?WaitForReadAhead@CStream@@IEAAXXZ; CStream::WaitForReadAhead(void)
0x180020ac0  mov     rax, cs:Block
0x180020ac7  cmp     [rbx+28h], rax
0x180020acb  mov     edi, [rbx+3Ch]
0x180020ace  cmovz   rax, cs:lpBuffer
0x180020ad6  xor     r8d, r8d; lpPreviousCount
0x180020ad9  mov     rcx, cs:hSemaphore; hSemaphore
0x180020ae0  mov     [rbx+28h], rax
0x180020ae4  mov     dword ptr [rbx+3Ch], 0FFFFFFFEh
0x180020aeb  lea     edx, [r8+1]; lReleaseCount
0x180020aef  call    cs:__imp_ReleaseSemaphore
0x180020af5  cmp     edi, 0FFFFFFFFh
0x180020af8  jz      short loc_180020B54
0x180020afa  mov     rcx, cs:hHandle; hSemaphore
0x180020b01  xor     r8d, r8d; lpPreviousCount
0x180020b04  lea     edx, [r8+1]; lReleaseCount
0x180020b08  call    cs:__imp_ReleaseSemaphore
0x180020b0e  mov     eax, [rbx+20h]
0x180020b11  mov     rcx, [rbx+28h]
0x180020b15  mov     [rbx+24h], eax
0x180020b18  add     eax, edi
0x180020b1a  mov     [rbx+20h], eax
0x180020b1d  mov     [rbx+8], rcx
0x180020b21  movsxd  rax, edi
0x180020b24  add     rcx, rax
0x180020b27  mov     [rbx+10h], rcx
0x180020b2b  mov     byte ptr [rcx+1], 0
0x180020b2f  test    edi, edi
0x180020b31  jnz     short loc_180020B58
0x180020b33  mov     dword ptr [rbx+18h], 1
0x180020b3a  jmp     short loc_180020B54
0x180020b3c  mov     r8d, [rcx+38h]; uBytes
0x180020b40  mov     rdx, [rcx+28h]; lpBuffer
0x180020b44  mov     ecx, [rcx+1Ch]; hFile
0x180020b47  call    cs:__imp__lread
0x180020b4d  mov     edi, eax
0x180020b4f  cmp     eax, 0FFFFFFFFh
0x180020b52  jnz     short loc_180020B0E
0x180020b54  mov     al, 0FFh
0x180020b56  jmp     short loc_180020B65
0x180020b58  mov     rcx, [rbx+8]
0x180020b5c  mov     al, [rcx]
0x180020b5e  inc     rcx
0x180020b61  mov     [rbx+8], rcx
0x180020b65  mov     rbx, [rsp+28h+arg_0]
0x180020b6a  add     rsp, 20h
0x180020b6e  pop     rdi
0x180020b6f  retn
```
