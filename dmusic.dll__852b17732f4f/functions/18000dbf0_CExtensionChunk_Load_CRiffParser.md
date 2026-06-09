# CExtensionChunk::Load(CRiffParser *)

- ea: `0x18000dbf0`
- end: `0x18000dcba`
- name: `?Load@CExtensionChunk@@QEAAJPEAVCRiffParser@@@Z`
- size: `202`
- prototype: `__int64 __fastcall(CExtensionChunk *this, struct CRiffParser *)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180009b30`
- `0x18000e178`
- `0x180010938`
- `0x180014834`

## callees

- `0x1800012c4`
- `0x1800012d0`
- `0x180006320`
- `0x18000dbf0`

## pseudocode

```c
__int64 __fastcall CExtensionChunk::Load(CExtensionChunk *this, struct CRiffParser *a2)
{
  _DWORD *v2; // rdi
  unsigned int v5; // r8d
  void *v6; // rcx
  unsigned int v8; // eax
  _DWORD *v9; // rax
  unsigned __int64 v10; // rdx
  int v11; // edi
  void *v12; // rcx

  v2 = (_DWORD *)*((_QWORD *)a2 + 2);
  v5 = v2[1];
  if ( v5 <= 0xFFFFFFEB )
  {
    v8 = 0;
    if ( v5 >= 4 )
      v8 = v5 - 4;
    *((_DWORD *)this + 4) = v8;
    v9 = operator new[]((v8 + 23LL) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)this + 1) = v9;
    if ( v9 )
    {
      *v9 = v2[1];
      *(_DWORD *)(*((_QWORD *)this + 1) + 4LL) = 0;
      *(_DWORD *)(*((_QWORD *)this + 1) + 8LL) = *v2;
      v11 = CRiffParser::Read(a2, (void *)(*((_QWORD *)this + 1) + 12LL), v2[1]);
      if ( v11 >= 0 )
        return (unsigned int)v11;
    }
    else
    {
      v11 = -2147024882;
    }
    v12 = (void *)*((_QWORD *)this + 1);
    if ( v12 )
    {
      operator delete(v12, v10);
      *((_QWORD *)this + 1) = 0;
    }
    return (unsigned int)v11;
  }
  v6 = (void *)*((_QWORD *)this + 1);
  if ( v6 )
  {
    operator delete(v6, (unsigned __int64)a2);
    *((_QWORD *)this + 1) = 0;
  }
  return 1462;
}

```

## disassembly

```asm
0x18000dbf0  mov     [rsp+arg_0], rbx
0x18000dbf5  mov     [rsp+arg_8], rsi
0x18000dbfa  push    rdi
0x18000dbfb  sub     rsp, 20h
0x18000dbff  mov     rdi, [rdx+10h]
0x18000dc03  mov     rsi, rdx
0x18000dc06  mov     rbx, rcx
0x18000dc09  mov     r8d, [rdi+4]
0x18000dc0d  cmp     r8d, 0FFFFFFEBh
0x18000dc11  jbe     short loc_18000DC30
0x18000dc13  mov     rcx, [rcx+8]; void *
0x18000dc17  test    rcx, rcx
0x18000dc1a  jz      short loc_18000DC29
0x18000dc1c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000dc21  mov     qword ptr [rbx+8], 0
0x18000dc29  mov     eax, 5B6h
0x18000dc2e  jmp     short loc_18000DCAA
0x18000dc30  xor     eax, eax
0x18000dc32  lea     ecx, [r8-4]
0x18000dc36  cmp     r8d, 4
0x18000dc3a  cmovnb  eax, ecx
0x18000dc3d  mov     ecx, eax
0x18000dc3f  mov     [rbx+10h], ecx
0x18000dc42  add     rcx, 17h
0x18000dc46  and     rcx, 0FFFFFFFFFFFFFFF8h; unsigned __int64
0x18000dc4a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000dc4f  mov     [rbx+8], rax
0x18000dc53  test    rax, rax
0x18000dc56  jz      short loc_18000DC8D
0x18000dc58  mov     ecx, [rdi+4]
0x18000dc5b  mov     [rax], ecx
0x18000dc5d  mov     rax, [rbx+8]
0x18000dc61  mov     dword ptr [rax+4], 0
0x18000dc68  mov     rcx, [rbx+8]
0x18000dc6c  mov     eax, [rdi]
0x18000dc6e  mov     [rcx+8], eax
0x18000dc71  mov     rcx, rsi; this
0x18000dc74  mov     rdx, [rbx+8]
0x18000dc78  mov     r8d, [rdi+4]; unsigned int
0x18000dc7c  add     rdx, 0Ch; void *
0x18000dc80  call    ?Read@CRiffParser@@QEAAJPEAXK@Z; CRiffParser::Read(void *,ulong)
0x18000dc85  mov     edi, eax
0x18000dc87  test    eax, eax
0x18000dc89  jns     short loc_18000DCA8
0x18000dc8b  jmp     short loc_18000DC92
0x18000dc8d  mov     edi, 8007000Eh
0x18000dc92  mov     rcx, [rbx+8]; void *
0x18000dc96  test    rcx, rcx
0x18000dc99  jz      short loc_18000DCA8
0x18000dc9b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000dca0  mov     qword ptr [rbx+8], 0
0x18000dca8  mov     eax, edi
0x18000dcaa  mov     rbx, [rsp+28h+arg_0]
0x18000dcaf  mov     rsi, [rsp+28h+arg_8]
0x18000dcb4  add     rsp, 20h
0x18000dcb8  pop     rdi
0x18000dcb9  retn
```
