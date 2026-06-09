# SC_DISK::ResetPartitionCache(void)

- ea: `0x14000510c`
- end: `0x1400051b9`
- name: `?ResetPartitionCache@SC_DISK@@QEAAJXZ`
- size: `173`
- prototype: `__int64 __fastcall(SC_DISK *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1400050c0`
- `0x14000a33c`
- `0x14000efb8`
- `0x14000f180`
- `0x14000f7f8`

## callees

- `0x14000510c`
- `0x14000a430`
- `0x140010f60`

## pseudocode

```c
__int64 __fastcall SC_DISK::ResetPartitionCache(SC_DISK *this)
{
  int v2; // edi
  __int64 v3; // rcx

  v2 = (*(__int64 (__fastcall **)(SC_DISK *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)this + 64LL))(
         this,
         0,
         (unsigned int)(1 << *((_DWORD *)this + 60)),
         *((_QWORD *)this + 33));
  if ( v2 >= 0 )
  {
    v3 = *((_QWORD *)this + 33);
    if ( *(_WORD *)(v3 + 510) == 0xAA55 )
    {
      if ( *(_BYTE *)(v3 + 450) != 0xEE || *(_BYTE *)(v3 + 466) || *(_BYTE *)(v3 + 482) || *(_BYTE *)(v3 + 498) )
        *((_DWORD *)this + 64) = SC_DISK::IsVbr(this) != 0 ? 2 : 0;
      else
        *((_DWORD *)this + 64) = 1;
    }
    else
    {
      *((_DWORD *)this + 64) = 2;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14000510c  mov     [rsp+arg_0], rbx
0x140005111  push    rdi
0x140005112  sub     rsp, 30h
0x140005116  mov     rax, [rcx]
0x140005119  mov     rbx, rcx
0x14000511c  mov     ecx, [rcx+0F0h]
0x140005122  mov     r8d, 1
0x140005128  shl     r8d, cl
0x14000512b  xor     edx, edx
0x14000512d  mov     rcx, rbx
0x140005130  mov     rax, [rax+40h]
0x140005134  mov     r9, [rbx+108h]
0x14000513b  call    _guard_dispatch_icall
0x140005140  xor     edx, edx
0x140005142  mov     edi, eax
0x140005144  test    eax, eax
0x140005146  js      short loc_14000517B
0x140005148  mov     rcx, [rbx+108h]
0x14000514f  mov     eax, 0AA55h
0x140005154  cmp     [rcx+1FEh], ax
0x14000515b  jnz     short loc_140005189
0x14000515d  cmp     byte ptr [rcx+1C2h], 0EEh
0x140005164  jz      short loc_140005195
0x140005166  mov     rcx, rbx; this
0x140005169  call    ?IsVbr@SC_DISK@@QEAAEXZ; SC_DISK::IsVbr(void)
0x14000516e  neg     al
0x140005170  sbb     ecx, ecx
0x140005172  and     ecx, 2
0x140005175  mov     [rbx+100h], ecx
0x14000517b  mov     rbx, [rsp+38h+arg_0]
0x140005180  mov     eax, edi
0x140005182  add     rsp, 30h
0x140005186  pop     rdi
0x140005187  retn
0x140005189  mov     dword ptr [rbx+100h], 2
0x140005193  jmp     short loc_14000517B
0x140005195  cmp     [rcx+1D2h], dl
0x14000519b  jnz     short loc_140005166
0x14000519d  cmp     [rcx+1E2h], dl
0x1400051a3  jnz     short loc_140005166
0x1400051a5  cmp     [rcx+1F2h], dl
0x1400051ab  jnz     short loc_140005166
0x1400051ad  mov     dword ptr [rbx+100h], 1
0x1400051b7  jmp     short loc_14000517B
```
