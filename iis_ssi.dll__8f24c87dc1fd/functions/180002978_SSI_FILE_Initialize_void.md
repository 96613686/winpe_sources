# SSI_FILE::Initialize(void)

- ea: `0x180002978`
- end: `0x180002a2f`
- name: `?Initialize@SSI_FILE@@AEAAJXZ`
- size: `183`
- prototype: `__int64 __fastcall(SSI_FILE *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180002648`

## callees

- `0x180001008`
- `0x180001048`
- `0x180002978`
- `0x180002a38`
- `0x180002b7c`
- `0x180002dc0`
- `0x180006010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x1800029ca`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800029ca`

## pseudocode

```c
__int64 __fastcall SSI_FILE::Initialize(SSI_FILE *this)
{
  int v2; // edi
  char *v3; // rax
  char *v4; // rbx

  if ( *((_QWORD *)this + 3)
    || (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 72LL))(*((_QWORD *)this + 2))
    || (v2 = SSI_FILE::SSIReadFile(this), v2 >= 0) )
  {
    v3 = (char *)operator new(0x160u);
    v4 = v3;
    if ( v3 )
    {
      STRU::STRU((STRU *)(v3 + 32));
      *((_DWORD *)v4 + 86) = 0;
      *((_QWORD *)v4 + 2) = v4 + 8;
      *((_QWORD *)v4 + 1) = v4 + 8;
      *(_DWORD *)v4 = 541869395;
      v2 = SSI_ELEMENT_LIST::Initialize((SSI_ELEMENT_LIST *)v4, this);
      if ( v2 >= 0 )
      {
        v2 = 0;
LABEL_10:
        *((_QWORD *)this + 4) = v4;
        return (unsigned int)v2;
      }
      SSI_ELEMENT_LIST::~SSI_ELEMENT_LIST((SSI_ELEMENT_LIST *)v4);
      operator delete(v4);
    }
    else
    {
      v2 = -2147024882;
    }
    v4 = 0;
    goto LABEL_10;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180002978  mov     [rsp+arg_0], rbx
0x18000297d  mov     [rsp+arg_8], rsi
0x180002982  push    rdi
0x180002983  sub     rsp, 20h
0x180002987  cmp     qword ptr [rcx+18h], 0
0x18000298c  mov     rsi, rcx
0x18000298f  jnz     short loc_1800029B4
0x180002991  mov     rcx, [rcx+10h]
0x180002995  mov     rax, [rcx]
0x180002998  mov     rax, [rax+48h]
0x18000299c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029a1  test    rax, rax
0x1800029a4  jnz     short loc_1800029B4
0x1800029a6  mov     rcx, rsi; this
0x1800029a9  call    ?SSIReadFile@SSI_FILE@@AEAAJXZ; SSI_FILE::SSIReadFile(void)
0x1800029ae  mov     edi, eax
0x1800029b0  test    eax, eax
0x1800029b2  js      short loc_180002A1D
0x1800029b4  mov     ecx, 160h; Size
0x1800029b9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800029be  mov     rbx, rax
0x1800029c1  test    rax, rax
0x1800029c4  jz      short loc_180002A12
0x1800029c6  lea     rcx, [rax+20h]
0x1800029ca  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800029d0  lea     rcx, [rbx+8]
0x1800029d4  mov     dword ptr [rbx+158h], 0
0x1800029de  mov     [rcx+8], rcx
0x1800029e2  mov     rdx, rsi; struct SSI_FILE *
0x1800029e5  mov     [rcx], rcx
0x1800029e8  mov     rcx, rbx; this
0x1800029eb  mov     dword ptr [rbx], 204C4553h
0x1800029f1  call    ?Initialize@SSI_ELEMENT_LIST@@AEAAJPEAVSSI_FILE@@@Z; SSI_ELEMENT_LIST::Initialize(SSI_FILE *)
0x1800029f6  mov     edi, eax
0x1800029f8  test    eax, eax
0x1800029fa  jns     short loc_180002A0E
0x1800029fc  mov     rcx, rbx; this
0x1800029ff  call    ??1SSI_ELEMENT_LIST@@QEAA@XZ; SSI_ELEMENT_LIST::~SSI_ELEMENT_LIST(void)
0x180002a04  mov     rcx, rbx; Block
0x180002a07  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002a0c  jmp     short loc_180002A17
0x180002a0e  xor     edi, edi
0x180002a10  jmp     short loc_180002A19
0x180002a12  mov     edi, 8007000Eh
0x180002a17  xor     ebx, ebx
0x180002a19  mov     [rsi+20h], rbx
0x180002a1d  mov     rbx, [rsp+28h+arg_0]
0x180002a22  mov     eax, edi
0x180002a24  mov     rsi, [rsp+28h+arg_8]
0x180002a29  add     rsp, 20h
0x180002a2d  pop     rdi
0x180002a2e  retn
```
