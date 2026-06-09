# REQUEST_LIST_BLOB::AddString(char const *,ulong)

- ea: `0x180001ac8`
- end: `0x180001bb5`
- name: `?AddString@REQUEST_LIST_BLOB@@QEAAJPEBDK@Z`
- size: `237`
- prototype: `__int64 __fastcall(REQUEST_LIST_BLOB *__hidden this, const char *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180001cb4`

## callees

- `0x180001ac8`
- `0x180002ac4`
- `0x180002d86`
- `0x180002d92`
- `0x180002dd0`

## import_xrefs

- `iisutil!?CopyA@STRU@@QEAAJPEBDK@Z` at `0x180001b21`
- `iisutil!?CopyA@STRU@@QEAAJPEBDK@Z` at `0x180001b21`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001b92`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001b92`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001b10`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001b10`

## pseudocode

```c
__int64 __fastcall REQUEST_LIST_BLOB::AddString(REQUEST_LIST_BLOB *this, const char *a2, unsigned int a3)
{
  int v6; // ebx
  size_t v7; // rbx
  void *v8; // rdx
  _BYTE v10[32]; // [rsp+20h] [rbp-E8h] BYREF
  void *Src; // [rsp+40h] [rbp-C8h]
  int v12; // [rsp+50h] [rbp-B8h]
  unsigned __int16 v13[64]; // [rsp+60h] [rbp-A8h] BYREF

  memset_0(v13, 0, sizeof(v13));
  STRU::STRU((STRU *)v10, v13, 0x40u);
  v6 = STRU::CopyA((STRU *)v10, a2, a3);
  if ( v6 >= 0 )
  {
    v6 = REQUEST_LIST_BLOB::ResizeIfNeeded(this, 2 * v12 + 2);
    if ( v6 >= 0 )
    {
      v7 = (unsigned int)(2 * v12 + 2);
      if ( (unsigned int)(*(_DWORD *)this - *((_DWORD *)this + 1)) < v7 + 4 )
      {
        v6 = -2147024809;
      }
      else
      {
        v8 = Src;
        *(_DWORD *)(*((unsigned int *)this + 1) + *((_QWORD *)this + 1)) = v7;
        *((_DWORD *)this + 1) += 4;
        memcpy_0((void *)(*((_QWORD *)this + 1) + *((unsigned int *)this + 1)), v8, v7);
        *((_DWORD *)this + 1) += v7;
        v6 = 0;
      }
    }
  }
  STRU::~STRU((STRU *)v10);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180001ac8  push    rbx
0x180001aca  push    rsi
0x180001acb  push    rdi
0x180001acc  sub     rsp, 0F0h
0x180001ad3  mov     rax, cs:__security_cookie
0x180001ada  xor     rax, rsp
0x180001add  mov     [rsp+108h+var_28], rax
0x180001ae5  mov     edi, r8d
0x180001ae8  mov     rbx, rdx
0x180001aeb  mov     rsi, rcx
0x180001aee  xor     edx, edx; Val
0x180001af0  mov     r8d, 80h; Size
0x180001af6  lea     rcx, [rsp+108h+var_A8]; void *
0x180001afb  call    memset_0
0x180001b00  mov     r8d, 40h ; '@'
0x180001b06  lea     rdx, [rsp+108h+var_A8]
0x180001b0b  lea     rcx, [rsp+108h+var_E8]
0x180001b10  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180001b16  mov     r8d, edi
0x180001b19  lea     rcx, [rsp+108h+var_E8]
0x180001b1e  mov     rdx, rbx
0x180001b21  call    cs:__imp_?CopyA@STRU@@QEAAJPEBDK@Z; STRU::CopyA(char const *,ulong)
0x180001b27  mov     ebx, eax
0x180001b29  test    eax, eax
0x180001b2b  js      short loc_180001B8D
0x180001b2d  mov     edx, [rsp+108h+var_B8]
0x180001b31  mov     rcx, rsi; this
0x180001b34  lea     edx, ds:2[rdx*2]; unsigned int
0x180001b3b  call    ?ResizeIfNeeded@REQUEST_LIST_BLOB@@AEAAJK@Z; REQUEST_LIST_BLOB::ResizeIfNeeded(ulong)
0x180001b40  mov     ebx, eax
0x180001b42  test    eax, eax
0x180001b44  js      short loc_180001B8D
0x180001b46  mov     eax, [rsp+108h+var_B8]
0x180001b4a  mov     ecx, [rsi]
0x180001b4c  sub     ecx, [rsi+4]
0x180001b4f  lea     ebx, ds:2[rax*2]
0x180001b56  lea     rax, [rbx+4]
0x180001b5a  mov     r8d, ebx; Size
0x180001b5d  cmp     rcx, rax
0x180001b60  jb      short loc_180001B88
0x180001b62  mov     ecx, [rsi+4]
0x180001b65  mov     rax, [rsi+8]
0x180001b69  mov     rdx, [rsp+108h+Src]; Src
0x180001b6e  mov     [rcx+rax], ebx
0x180001b71  add     dword ptr [rsi+4], 4
0x180001b75  mov     ecx, [rsi+4]
0x180001b78  add     rcx, [rsi+8]; void *
0x180001b7c  call    memcpy_0
0x180001b81  add     [rsi+4], ebx
0x180001b84  xor     ebx, ebx
0x180001b86  jmp     short loc_180001B8D
0x180001b88  mov     ebx, 80070057h
0x180001b8d  lea     rcx, [rsp+108h+var_E8]
0x180001b92  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001b98  mov     eax, ebx
0x180001b9a  mov     rcx, [rsp+108h+var_28]
0x180001ba2  xor     rcx, rsp; StackCookie
0x180001ba5  call    __security_check_cookie
0x180001baa  add     rsp, 0F0h
0x180001bb1  pop     rdi
0x180001bb2  pop     rsi
0x180001bb3  pop     rbx
0x180001bb4  retn
```
