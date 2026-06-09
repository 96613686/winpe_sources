# CKeyInSeq::LoadQueueFormat(void *)

- ea: `0x18006772c`
- end: `0x180067875`
- name: `?LoadQueueFormat@CKeyInSeq@@AEAAHPEAX@Z`
- size: `329`
- prototype: `int(CKeyInSeq *__hidden this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18006753c`

## callees

- `0x18000f35c`
- `0x18006772c`
- `0x18009bd1c`

## import_xrefs

- `msvcrt!free` at `0x18006784e`
- `msvcrt!free` at `0x18006785f`
- `msvcrt!free` at `0x18006784e`
- `msvcrt!free` at `0x18006785f`
- `KERNEL32!ReadFile` at `0x180067762`
- `KERNEL32!ReadFile` at `0x1800677f3`
- `KERNEL32!ReadFile` at `0x180067831`
- `KERNEL32!ReadFile` at `0x180067762`
- `KERNEL32!ReadFile` at `0x1800677f3`
- `KERNEL32!ReadFile` at `0x180067831`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CKeyInSeq::LoadQueueFormat(CKeyInSeq *this, void *a2)
{
  unsigned __int8 *v3; // rdi
  __int64 v4; // r9
  void *v5; // rbx
  DWORD NumberOfBytesRead; // [rsp+50h] [rbp+20h] BYREF
  DWORD Buffer; // [rsp+60h] [rbp+30h] BYREF
  void *v9; // [rsp+68h] [rbp+38h]

  NumberOfBytesRead = 0;
  v3 = (unsigned __int8 *)this + 16;
  if ( ReadFile(a2, (char *)this + 16, 0x20u, &NumberOfBytesRead, 0) && NumberOfBytesRead == 32 )
  {
    v4 = *v3;
    if ( (_DWORD)v4 != 3 )
    {
      if ( (unsigned int)(v4 - 1) > 1 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 42), 10, &WPP_d47abf12d2c63181d11479d5f9b3f4aa_Traceguids, v4);
        return 0;
      }
      return 1;
    }
    Buffer = 0;
    if ( ReadFile(a2, &Buffer, 4u, &NumberOfBytesRead, 0) && NumberOfBytesRead == 4 )
    {
      v9 = 0;
      v5 = MmAllocate(Buffer);
      v9 = v5;
      if ( ReadFile(a2, v5, Buffer, &NumberOfBytesRead, 0) && Buffer == NumberOfBytesRead )
      {
        *(_WORD *)v3 = 3;
        *((_QWORD *)v3 + 1) = v5;
        free(0);
        return 1;
      }
      free(v5);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18006772c  mov     [rsp-18h+arg_8], rbx
0x180067731  push    rbp
0x180067732  push    rsi
0x180067733  push    rdi
0x180067734  mov     rbp, rsp
0x180067737  sub     rsp, 30h
0x18006773b  mov     rsi, rdx
0x18006773e  mov     [rbp+NumberOfBytesRead], 0
0x180067745  lea     rdi, [rcx+10h]
0x180067749  mov     [rsp+30h+lpOverlapped], 0; lpOverlapped
0x180067752  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180067756  mov     r8d, 20h ; ' '; nNumberOfBytesToRead
0x18006775c  mov     rdx, rdi; lpBuffer
0x18006775f  mov     rcx, rsi; hFile
0x180067762  call    cs:__imp_ReadFile
0x180067768  test    eax, eax
0x18006776a  jz      loc_180067866
0x180067770  cmp     [rbp+NumberOfBytesRead], 20h ; ' '
0x180067774  jnz     loc_180067866
0x18006777a  movzx   r9d, byte ptr [rdi]
0x18006777e  cmp     r9d, 3
0x180067782  jz      short loc_1800677D2
0x180067784  lea     eax, [r9-1]
0x180067788  cmp     eax, 1
0x18006778b  jbe     loc_180067855
0x180067791  lea     rax, WPP_GLOBAL_Control
0x180067798  mov     rcx, cs:WPP_GLOBAL_Control
0x18006779f  cmp     rcx, rax
0x1800677a2  jz      loc_180067866
0x1800677a8  test    byte ptr [rcx+15Ch], 1
0x1800677af  jz      loc_180067866
0x1800677b5  mov     edx, 0Ah
0x1800677ba  lea     r8, WPP_d47abf12d2c63181d11479d5f9b3f4aa_Traceguids
0x1800677c1  mov     rcx, [rcx+150h]
0x1800677c8  call    WPP_SF_d
0x1800677cd  jmp     loc_180067866
0x1800677d2  mov     [rbp+Buffer], 0
0x1800677d9  mov     [rsp+30h+lpOverlapped], 0; lpOverlapped
0x1800677e2  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800677e6  mov     r8d, 4; nNumberOfBytesToRead
0x1800677ec  lea     rdx, [rbp+Buffer]; lpBuffer
0x1800677f0  mov     rcx, rsi; hFile
0x1800677f3  call    cs:__imp_ReadFile
0x1800677f9  test    eax, eax
0x1800677fb  jz      short loc_180067866
0x1800677fd  cmp     [rbp+NumberOfBytesRead], 4
0x180067801  jnz     short loc_180067866
0x180067803  mov     [rbp+arg_18], 0
0x18006780b  mov     ecx, [rbp+Buffer]; unsigned __int64
0x18006780e  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180067813  mov     rbx, rax
0x180067816  mov     [rbp+arg_18], rax
0x18006781a  mov     [rsp+30h+lpOverlapped], 0; lpOverlapped
0x180067823  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180067827  mov     r8d, [rbp+Buffer]; nNumberOfBytesToRead
0x18006782b  mov     rdx, rax; lpBuffer
0x18006782e  mov     rcx, rsi; hFile
0x180067831  call    cs:__imp_ReadFile
0x180067837  test    eax, eax
0x180067839  jz      short loc_18006785C
0x18006783b  mov     ecx, [rbp+NumberOfBytesRead]
0x18006783e  cmp     [rbp+Buffer], ecx
0x180067841  jnz     short loc_18006785C
0x180067843  mov     word ptr [rdi], 3
0x180067848  mov     [rdi+8], rbx
0x18006784c  xor     ecx, ecx; Block
0x18006784e  call    cs:__imp_free
0x180067854  nop
0x180067855  mov     eax, 1
0x18006785a  jmp     short loc_180067868
0x18006785c  mov     rcx, rbx; Block
0x18006785f  call    cs:__imp_free
0x180067865  nop
0x180067866  xor     eax, eax
0x180067868  mov     rbx, [rsp+30h+arg_8]
0x18006786d  add     rsp, 30h
0x180067871  pop     rdi
0x180067872  pop     rsi
0x180067873  pop     rbp
0x180067874  retn
```
