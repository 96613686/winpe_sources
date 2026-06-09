# CFileRecord::Delete(void)

- ea: `0x180007efc`
- end: `0x180007f91`
- name: `?Delete@CFileRecord@@QEAAJXZ`
- size: `149`
- prototype: `__int64 __fastcall(CFileRecord *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000c450`

## callees

- `0x180007ecc`
- `0x180007efc`
- `0x18000935c`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall CFileRecord::Delete(CFileRecord *this)
{
  int v2; // edi

  v2 = 0;
  if ( *((_DWORD *)this + 4) == -1 )
    goto LABEL_7;
  v2 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 160LL))(*(_QWORD *)this);
  if ( v2 >= 0 )
  {
    *((_DWORD *)this + 4) = -1;
    CCatalogStatistics::DecrementFileRecordCount(*((_QWORD *)this + 1), *((unsigned __int16 *)this + 36));
    *((_WORD *)this + 36) = 0;
LABEL_7:
    *((_DWORD *)this + 19) = 0;
    return (unsigned int)v2;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      WPP_d0c10813b8dd33525641bcb4dab89869_Traceguids,
      *((unsigned int *)this + 4),
      v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180007efc  mov     [rsp+arg_0], rbx
0x180007f01  push    rdi
0x180007f02  sub     rsp, 30h
0x180007f06  mov     rbx, rcx
0x180007f09  xor     edi, edi
0x180007f0b  mov     edx, [rcx+10h]
0x180007f0e  cmp     edx, 0FFFFFFFFh
0x180007f11  jz      short loc_180007F7D
0x180007f13  mov     rcx, [rcx]
0x180007f16  mov     rax, [rcx]
0x180007f19  mov     rax, [rax+0A0h]
0x180007f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f25  mov     edi, eax
0x180007f27  test    eax, eax
0x180007f29  jns     short loc_180007F63
0x180007f2b  lea     rax, WPP_GLOBAL_Control
0x180007f32  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f39  cmp     rcx, rax
0x180007f3c  jz      short loc_180007F84
0x180007f3e  test    byte ptr [rcx+1Ch], 1
0x180007f42  jz      short loc_180007F84
0x180007f44  mov     edx, 11h
0x180007f49  mov     [rsp+38h+var_18], edi
0x180007f4d  mov     r9d, [rbx+10h]
0x180007f51  lea     r8, WPP_d0c10813b8dd33525641bcb4dab89869_Traceguids
0x180007f58  mov     rcx, [rcx+10h]
0x180007f5c  call    WPP_SF_dd
0x180007f61  jmp     short loc_180007F84
0x180007f63  mov     dword ptr [rbx+10h], 0FFFFFFFFh
0x180007f6a  movzx   edx, word ptr [rbx+48h]
0x180007f6e  mov     rcx, [rbx+8]
0x180007f72  call    ?DecrementFileRecordCount@CCatalogStatistics@@QEAAXW4FhFileState@@@Z; CCatalogStatistics::DecrementFileRecordCount(FhFileState)
0x180007f77  xor     eax, eax
0x180007f79  mov     [rbx+48h], ax
0x180007f7d  mov     dword ptr [rbx+4Ch], 0
0x180007f84  mov     eax, edi
0x180007f86  mov     rbx, [rsp+38h+arg_0]
0x180007f8b  add     rsp, 30h
0x180007f8f  pop     rdi
0x180007f90  retn
```
