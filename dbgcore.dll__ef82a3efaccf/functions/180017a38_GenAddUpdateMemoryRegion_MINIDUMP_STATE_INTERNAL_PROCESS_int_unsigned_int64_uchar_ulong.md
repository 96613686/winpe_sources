# GenAddUpdateMemoryRegion(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,int,unsigned __int64,uchar *,ulong)

- ea: `0x180017a38`
- end: `0x180017b85`
- name: `?GenAddUpdateMemoryRegion@@YAHPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@H_KPEAEK@Z`
- size: `333`
- prototype: `__int64 __fastcall(struct _MINIDUMP_STATE *, struct _INTERNAL_PROCESS *, int, unsigned __int64, unsigned __int8 *Src, unsigned int Size)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180016f50`
- `0x18001cd50`

## callees

- `0x180003424`
- `0x180016b74`
- `0x180017a38`
- `0x18001bf10`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall GenAddUpdateMemoryRegion(
        struct _MINIDUMP_STATE *a1,
        struct _INTERNAL_PROCESS *a2,
        int a3,
        unsigned __int64 a4,
        unsigned __int8 *Src,
        unsigned int Size)
{
  _QWORD *v6; // rdi
  unsigned int v10; // ebp
  __int64 result; // rax
  _QWORD *i; // rbx
  void *v13; // rsi
  void *v14; // rax

  v6 = (_QWORD *)*((_QWORD *)a2 + 9148);
  v10 = 1;
  if ( !a3 || (result = GenUpdatePdbNameInCvRecord(Src, Size, 0), (v10 = result) != 0) )
  {
    i = 0;
    if ( v6 )
    {
      if ( v6[2] <= a4 )
      {
        for ( i = (_QWORD *)*v6; i && i[2] <= a4; i = (_QWORD *)*i )
          v6 = i;
        if ( v6[2] + (unsigned __int64)*((unsigned int *)v6 + 6) > a4 )
          return 0;
      }
      else
      {
        i = (_QWORD *)*((_QWORD *)a2 + 9148);
        v6 = 0;
      }
      if ( !v10 )
        return v10;
      if ( i && a4 + Size > i[2] )
        return 0;
    }
    v10 = 0;
    v13 = AllocMemory(a1, 0x20u);
    if ( v13 )
    {
      v14 = AllocMemory(a1, Size);
      *((_QWORD *)v13 + 1) = v14;
      if ( v14 )
      {
        *((_QWORD *)v13 + 2) = a4;
        *((_DWORD *)v13 + 6) = Size;
        v10 = 1;
        memcpy_0(v14, Src, Size);
        if ( a3 )
          GenUpdatePdbNameInCvRecord(*((void **)v13 + 1), *((_DWORD *)v13 + 6), 1);
        if ( v6 )
          *v6 = v13;
        else
          *((_QWORD *)a2 + 9148) = v13;
        *(_QWORD *)v13 = i;
      }
      else
      {
        (*(void (__fastcall **)(_QWORD, void *))(**((_QWORD **)a1 + 4) + 24LL))(*((_QWORD *)a1 + 4), v13);
      }
    }
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x180017a38  mov     [rsp+arg_10], r8d
0x180017a3d  push    rbx
0x180017a3e  push    rbp
0x180017a3f  push    rsi
0x180017a40  push    rdi
0x180017a41  push    r12
0x180017a43  push    r13
0x180017a45  push    r14
0x180017a47  push    r15
0x180017a49  sub     rsp, 28h
0x180017a4d  mov     rdi, [rdx+11DE0h]
0x180017a54  mov     r14, r9
0x180017a57  mov     r15d, dword ptr [rsp+68h+Size]
0x180017a5f  mov     r13, rdx
0x180017a62  mov     r12, rcx
0x180017a65  mov     ebp, 1
0x180017a6a  test    r8d, r8d
0x180017a6d  jz      short loc_180017A8C
0x180017a6f  mov     rcx, [rsp+68h+Src]; void *
0x180017a77  xor     r8d, r8d; int
0x180017a7a  mov     edx, r15d; unsigned int
0x180017a7d  call    ?GenUpdatePdbNameInCvRecord@@YAHPEAXKH@Z; GenUpdatePdbNameInCvRecord(void *,ulong,int)
0x180017a82  mov     ebp, eax
0x180017a84  test    eax, eax
0x180017a86  jz      loc_180017B74
0x180017a8c  xor     ebx, ebx
0x180017a8e  test    rdi, rdi
0x180017a91  jz      short loc_180017AE4
0x180017a93  cmp     [rdi+10h], r14
0x180017a97  jbe     short loc_180017AA4
0x180017a99  mov     rbx, [r13+11DE0h]
0x180017aa0  xor     edi, edi
0x180017aa2  jmp     short loc_180017AC6
0x180017aa4  mov     rbx, [rdi]
0x180017aa7  jmp     short loc_180017AB5
0x180017aa9  cmp     [rbx+10h], r14
0x180017aad  ja      short loc_180017ABA
0x180017aaf  mov     rdi, rbx
0x180017ab2  mov     rbx, [rbx]
0x180017ab5  test    rbx, rbx
0x180017ab8  jnz     short loc_180017AA9
0x180017aba  mov     eax, [rdi+18h]
0x180017abd  add     rax, [rdi+10h]
0x180017ac1  cmp     rax, r14
0x180017ac4  ja      short loc_180017ADD
0x180017ac6  test    ebp, ebp
0x180017ac8  jz      loc_180017B72
0x180017ace  test    rbx, rbx
0x180017ad1  jz      short loc_180017AE4
0x180017ad3  lea     rax, [r14+r15]
0x180017ad7  cmp     rax, [rbx+10h]
0x180017adb  jbe     short loc_180017AE4
0x180017add  xor     ebp, ebp
0x180017adf  jmp     loc_180017B72
0x180017ae4  xor     ebp, ebp
0x180017ae6  mov     rcx, r12; struct _MINIDUMP_STATE *
0x180017ae9  lea     edx, [rbp+20h]; unsigned int
0x180017aec  call    ?AllocMemory@@YAPEAXPEAU_MINIDUMP_STATE@@K@Z; AllocMemory(_MINIDUMP_STATE *,ulong)
0x180017af1  mov     rsi, rax
0x180017af4  test    rax, rax
0x180017af7  jz      short loc_180017B72
0x180017af9  mov     edx, r15d; unsigned int
0x180017afc  mov     rcx, r12; struct _MINIDUMP_STATE *
0x180017aff  call    ?AllocMemory@@YAPEAXPEAU_MINIDUMP_STATE@@K@Z; AllocMemory(_MINIDUMP_STATE *,ulong)
0x180017b04  mov     [rsi+8], rax
0x180017b08  test    rax, rax
0x180017b0b  jz      short loc_180017B5E
0x180017b0d  mov     rdx, [rsp+68h+Src]; Src
0x180017b15  lea     r12d, [rbp+1]
0x180017b19  mov     r8, r15; Size
0x180017b1c  mov     [rsi+10h], r14
0x180017b20  mov     rcx, rax; void *
0x180017b23  mov     [rsi+18h], r15d
0x180017b27  mov     ebp, r12d
0x180017b2a  call    memcpy_0
0x180017b2f  cmp     [rsp+68h+arg_10], 0
0x180017b37  jz      short loc_180017B48
0x180017b39  mov     edx, [rsi+18h]; unsigned int
0x180017b3c  mov     r8d, r12d; int
0x180017b3f  mov     rcx, [rsi+8]; void *
0x180017b43  call    ?GenUpdatePdbNameInCvRecord@@YAHPEAXKH@Z; GenUpdatePdbNameInCvRecord(void *,ulong,int)
0x180017b48  test    rdi, rdi
0x180017b4b  jnz     short loc_180017B56
0x180017b4d  mov     [r13+11DE0h], rsi
0x180017b54  jmp     short loc_180017B59
0x180017b56  mov     [rdi], rsi
0x180017b59  mov     [rsi], rbx
0x180017b5c  jmp     short loc_180017B72
0x180017b5e  mov     rcx, [r12+20h]
0x180017b63  mov     rdx, rsi
0x180017b66  mov     rax, [rcx]
0x180017b69  mov     rax, [rax+18h]
0x180017b6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b72  mov     eax, ebp
0x180017b74  add     rsp, 28h
0x180017b78  pop     r15
0x180017b7a  pop     r14
0x180017b7c  pop     r13
0x180017b7e  pop     r12
0x180017b80  pop     rdi
0x180017b81  pop     rsi
0x180017b82  pop     rbp
0x180017b83  pop     rbx
0x180017b84  retn
```
