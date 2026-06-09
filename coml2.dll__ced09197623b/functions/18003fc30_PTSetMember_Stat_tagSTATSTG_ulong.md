# PTSetMember::Stat(tagSTATSTG *,ulong)

- ea: `0x18003fc30`
- end: `0x18003fd51`
- name: `?Stat@PTSetMember@@QEAAJPEAUtagSTATSTG@@K@Z`
- size: `289`
- prototype: `__int64 __fastcall(PTSetMember *__hidden this, struct tagSTATSTG *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180022338`
- `0x18003fa80`

## callees

- `0x18002eac0`
- `0x18003fc30`
- `0x18006141c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003fd16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003fd16`

## pseudocode

```c
__int64 __fastcall PTSetMember::Stat(PTSetMember *this, struct tagSTATSTG *a2, char a3)
{
  int v3; // eax
  unsigned __int64 v7; // rbp
  __int64 result; // rax
  int v9; // ecx
  __int64 v10; // rax
  void *v11; // rax

  v3 = *((unsigned __int16 *)this + 47);
  *((_DWORD *)a2 + 2) = v3;
  if ( (v3 & 3) == 1 )
  {
    v7 = ((unsigned __int64)this - 16) & -(__int64)(this != 0);
    result = PTimeEntry::GetTime(v7, 0, (char *)a2 + 32);
    if ( (int)result < 0 )
      return result;
    result = PTimeEntry::GetTime(v7, 2, (char *)a2 + 40);
    if ( (int)result < 0 )
      return result;
    result = PTimeEntry::GetTime(v7, 1, (char *)a2 + 24);
    if ( (int)result < 0 )
      return result;
    *(_OWORD *)((char *)a2 + 56) = *(_OWORD *)(v7 + 216);
    v9 = *(_DWORD *)(v7 + 232);
    *((_QWORD *)a2 + 2) = 0;
  }
  else
  {
    v10 = (__int64)this + 96;
    if ( !this )
      v10 = 112;
    v9 = 0;
    *((_QWORD *)a2 + 2) = *(_QWORD *)v10;
    *((_QWORD *)a2 + 4) = 0;
    *((_QWORD *)a2 + 5) = 0;
    *((_QWORD *)a2 + 3) = 0;
    *(GUID *)((char *)a2 + 56) = GUID_NULL;
  }
  *((_DWORD *)a2 + 18) = v9;
  if ( (a3 & 1) != 0 )
  {
    *(_QWORD *)a2 = 0;
  }
  else
  {
    v11 = CoTaskMemAlloc(*((unsigned __int16 *)this + 46));
    *(_QWORD *)a2 = v11;
    if ( !v11 )
      return 2147680264LL;
    memcpy_0(v11, (char *)this + 28, *((unsigned __int16 *)this + 46));
  }
  return 0;
}

```

## disassembly

```asm
0x18003fc30  push    rbx
0x18003fc32  push    rbp
0x18003fc33  push    rsi
0x18003fc34  push    r14
0x18003fc36  sub     rsp, 28h
0x18003fc3a  movzx   eax, word ptr [rcx+5Eh]
0x18003fc3e  mov     r14d, r8d
0x18003fc41  mov     [rdx+8], eax
0x18003fc44  mov     rbx, rdx
0x18003fc47  and     al, 3
0x18003fc49  mov     rsi, rcx
0x18003fc4c  cmp     al, 1
0x18003fc4e  jnz     short loc_18003FCC4
0x18003fc50  mov     rax, rcx
0x18003fc53  lea     r9, [rcx-10h]
0x18003fc57  neg     rax
0x18003fc5a  lea     r8, [rdx+20h]
0x18003fc5e  sbb     rbp, rbp
0x18003fc61  xor     edx, edx
0x18003fc63  and     rbp, r9
0x18003fc66  mov     rcx, rbp
0x18003fc69  call    ?GetTime@PTimeEntry@@QEAAJW4WHICHTIME@@PEAU_FILETIME@@@Z; PTimeEntry::GetTime(WHICHTIME,_FILETIME *)
0x18003fc6e  test    eax, eax
0x18003fc70  js      loc_18003FD47
0x18003fc76  lea     r8, [rbx+28h]
0x18003fc7a  mov     edx, 2
0x18003fc7f  mov     rcx, rbp
0x18003fc82  call    ?GetTime@PTimeEntry@@QEAAJW4WHICHTIME@@PEAU_FILETIME@@@Z; PTimeEntry::GetTime(WHICHTIME,_FILETIME *)
0x18003fc87  test    eax, eax
0x18003fc89  js      loc_18003FD47
0x18003fc8f  lea     r8, [rbx+18h]
0x18003fc93  mov     edx, 1
0x18003fc98  mov     rcx, rbp
0x18003fc9b  call    ?GetTime@PTimeEntry@@QEAAJW4WHICHTIME@@PEAU_FILETIME@@@Z; PTimeEntry::GetTime(WHICHTIME,_FILETIME *)
0x18003fca0  test    eax, eax
0x18003fca2  js      loc_18003FD47
0x18003fca8  movups  xmm0, xmmword ptr [rbp+0D8h]
0x18003fcaf  movdqu  xmmword ptr [rbx+38h], xmm0
0x18003fcb4  mov     ecx, [rbp+0E8h]
0x18003fcba  mov     qword ptr [rbx+10h], 0
0x18003fcc2  jmp     short loc_18003FD01
0x18003fcc4  test    rsi, rsi
0x18003fcc7  lea     rax, [rcx+60h]
0x18003fccb  mov     edx, 70h ; 'p'
0x18003fcd0  cmovz   rax, rdx
0x18003fcd4  xor     ecx, ecx
0x18003fcd6  mov     rax, [rax]
0x18003fcd9  mov     [rbx+10h], rax
0x18003fcdd  mov     qword ptr [rbx+20h], 0
0x18003fce5  mov     qword ptr [rbx+28h], 0
0x18003fced  mov     qword ptr [rbx+18h], 0
0x18003fcf5  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003fcfc  movdqu  xmmword ptr [rbx+38h], xmm0
0x18003fd01  mov     eax, 48h ; 'H'
0x18003fd06  mov     rdx, rbx
0x18003fd09  mov     [rbx+rax], ecx
0x18003fd0c  test    r14b, 1
0x18003fd10  jnz     short loc_18003FD3E
0x18003fd12  movzx   ecx, word ptr [rsi+5Ch]; cb
0x18003fd16  call    cs:__imp_CoTaskMemAlloc
0x18003fd1c  mov     [rbx], rax
0x18003fd1f  test    rax, rax
0x18003fd22  jnz     short loc_18003FD2B
0x18003fd24  mov     eax, 80030008h
0x18003fd29  jmp     short loc_18003FD47
0x18003fd2b  movzx   r8d, word ptr [rsi+5Ch]; Size
0x18003fd30  lea     rdx, [rsi+1Ch]; Src
0x18003fd34  mov     rcx, rax; void *
0x18003fd37  call    memcpy_0
0x18003fd3c  jmp     short loc_18003FD45
0x18003fd3e  mov     qword ptr [rbx], 0
0x18003fd45  xor     eax, eax
0x18003fd47  add     rsp, 28h
0x18003fd4b  pop     r14
0x18003fd4d  pop     rsi
0x18003fd4e  pop     rbp
0x18003fd4f  pop     rbx
0x18003fd50  retn
```
