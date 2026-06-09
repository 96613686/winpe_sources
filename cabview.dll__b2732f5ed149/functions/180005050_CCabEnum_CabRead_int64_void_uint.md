# CCabEnum::CabRead(__int64,void *,uint)

- ea: `0x180005050`
- end: `0x1800050b2`
- name: `?CabRead@CCabEnum@@KAI_JPEAXI@Z`
- size: `98`
- prototype: `UINT __cdecl(INT_PTR hf, void *pv, UINT cb)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005050`
- `0x180012a8c`

## import_xrefs

- `KERNEL32!_lread` at `0x18000509d`
- `KERNEL32!_lread` at `0x18000509d`

## pseudocode

```c
__int64 __fastcall CCabEnum::CabRead(INT_PTR hf, void *pv, UINT cb)
{
  _QWORD *v3; // rax
  unsigned int v4; // ebx

  v3 = *(_QWORD **)(hf + 8);
  v4 = cb;
  if ( v3 )
  {
    if ( *v3 )
    {
      if ( cb > *(_DWORD *)(hf + 16) - *(_DWORD *)(hf + 20) )
        v4 = *(_DWORD *)(hf + 16) - *(_DWORD *)(hf + 20);
      memmove_0(pv, (const void *)(*v3 + *(int *)(hf + 20)), v4);
      *(_DWORD *)(hf + 20) += v4;
    }
    else
    {
      return (unsigned int)-1;
    }
  }
  else
  {
    return _lread(*(_DWORD *)hf, pv, cb);
  }
  return v4;
}

```

## disassembly

```asm
0x180005050  mov     [rsp+arg_0], rbx
0x180005055  push    rdi
0x180005056  sub     rsp, 20h
0x18000505a  mov     rax, [rcx+8]
0x18000505e  mov     ebx, r8d
0x180005061  mov     r9, rdx
0x180005064  mov     rdi, rcx
0x180005067  test    rax, rax
0x18000506a  jz      short loc_18000509B
0x18000506c  mov     rcx, [rax]
0x18000506f  test    rcx, rcx
0x180005072  jnz     short loc_180005079
0x180005074  or      ebx, 0FFFFFFFFh
0x180005077  jmp     short loc_1800050A5
0x180005079  mov     eax, [rdi+10h]
0x18000507c  sub     eax, [rdi+14h]
0x18000507f  movsxd  rdx, dword ptr [rdi+14h]
0x180005083  cmp     ebx, eax
0x180005085  cmova   ebx, eax
0x180005088  add     rdx, rcx; Src
0x18000508b  mov     r8d, ebx; Size
0x18000508e  mov     rcx, r9; void *
0x180005091  call    memmove_0
0x180005096  add     [rdi+14h], ebx
0x180005099  jmp     short loc_1800050A5
0x18000509b  mov     ecx, [rcx]; hFile
0x18000509d  call    cs:__imp__lread
0x1800050a3  mov     ebx, eax
0x1800050a5  mov     eax, ebx
0x1800050a7  mov     rbx, [rsp+28h+arg_0]
0x1800050ac  add     rsp, 20h
0x1800050b0  pop     rdi
0x1800050b1  retn
```
