# MCIDestroyCompressionGlobal

- ea: `0x180014088`
- end: `0x180014139`
- name: `MCIDestroyCompressionGlobal`
- size: `177`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180013f34`
- `0x1800146f0`

## callees

- `0x180012578`
- `0x180014088`
- `0x180016db8`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall MCIDestroyCompressionGlobal(__int64 a1)
{
  unsigned int v2; // edi
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  __int64 v6; // rax
  int v7; // eax
  __int64 v8; // rax

  v2 = 1;
  v3 = *(_WORD *)(a1 + 676) & 0xF;
  if ( !v3 )
    goto LABEL_10;
  v4 = v3 - 1;
  if ( v4 )
  {
    v5 = v4 - 2;
    if ( v5 )
    {
      if ( v5 != 12 )
      {
        v6 = *(_QWORD *)(a1 + 88);
        *(_QWORD *)v6 = 5;
        *(_DWORD *)(v6 + 8) = 1;
      }
      goto LABEL_10;
    }
    v7 = LCIDestroyCompression(*(_QWORD *)(a1 + 8));
  }
  else
  {
    v7 = MCIDestroyCompression(*(_QWORD *)(a1 + 8));
  }
  if ( v7 )
  {
    v8 = *(_QWORD *)(a1 + 88);
    *(_DWORD *)(v8 + 8) = 1;
    v2 = 0;
    *(_QWORD *)v8 = 8;
  }
LABEL_10:
  if ( *(_QWORD *)(a1 + 688) )
  {
    (*(void (**)(void))(a1 + 24))();
    *(_QWORD *)(a1 + 688) = 0;
  }
  if ( *(_QWORD *)(a1 + 680) )
  {
    (*(void (**)(void))(a1 + 24))();
    *(_QWORD *)(a1 + 680) = 0;
  }
  return v2;
}

```

## disassembly

```asm
0x180014088  mov     [rsp+arg_0], rbx
0x18001408d  push    rdi
0x18001408e  sub     rsp, 20h
0x180014092  mov     rbx, rcx
0x180014095  mov     edi, 1
0x18001409a  movzx   ecx, word ptr [rcx+2A4h]
0x1800140a1  and     ecx, 0Fh
0x1800140a4  jz      short loc_1800140EC
0x1800140a6  sub     ecx, edi
0x1800140a8  jz      short loc_1800140CF
0x1800140aa  sub     ecx, 2
0x1800140ad  jz      short loc_1800140C4
0x1800140af  cmp     ecx, 0Ch
0x1800140b2  jz      short loc_1800140EC
0x1800140b4  mov     rax, [rbx+58h]
0x1800140b8  mov     qword ptr [rax], 5
0x1800140bf  mov     [rax+8], edi
0x1800140c2  jmp     short loc_1800140EC
0x1800140c4  mov     rcx, [rbx+8]
0x1800140c8  call    LCIDestroyCompression
0x1800140cd  jmp     short loc_1800140D8
0x1800140cf  mov     rcx, [rbx+8]
0x1800140d3  call    MCIDestroyCompression
0x1800140d8  test    eax, eax
0x1800140da  jz      short loc_1800140EC
0x1800140dc  mov     rax, [rbx+58h]
0x1800140e0  mov     [rax+8], edi
0x1800140e3  xor     edi, edi
0x1800140e5  mov     qword ptr [rax], 8
0x1800140ec  mov     rcx, [rbx+2B0h]
0x1800140f3  test    rcx, rcx
0x1800140f6  jz      short loc_18001410C
0x1800140f8  mov     rax, [rbx+18h]
0x1800140fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014101  mov     qword ptr [rbx+2B0h], 0
0x18001410c  mov     rcx, [rbx+2A8h]
0x180014113  test    rcx, rcx
0x180014116  jz      short loc_18001412C
0x180014118  mov     rax, [rbx+18h]
0x18001411c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014121  mov     qword ptr [rbx+2A8h], 0
0x18001412c  mov     rbx, [rsp+28h+arg_0]
0x180014131  mov     eax, edi
0x180014133  add     rsp, 20h
0x180014137  pop     rdi
0x180014138  retn
```
