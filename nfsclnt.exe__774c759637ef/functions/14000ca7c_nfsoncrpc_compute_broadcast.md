# nfsoncrpc_compute_broadcast

- ea: `0x14000ca7c`
- end: `0x14000cb6e`
- name: `nfsoncrpc_compute_broadcast`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000cca4`

## callees

- `0x14000ca7c`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x14000ca91`
- `KERNEL32!GlobalAlloc` at `0x14000cadb`
- `KERNEL32!GlobalAlloc` at `0x14000ca91`
- `KERNEL32!GlobalAlloc` at `0x14000cadb`
- `KERNEL32!GlobalFree` at `0x14000caf0`
- `KERNEL32!GlobalFree` at `0x14000cb13`
- `KERNEL32!GlobalFree` at `0x14000cb1c`
- `KERNEL32!GlobalFree` at `0x14000caf0`
- `KERNEL32!GlobalFree` at `0x14000cb13`
- `KERNEL32!GlobalFree` at `0x14000cb1c`

## pseudocode

```c
_QWORD *__fastcall nfsoncrpc_compute_broadcast(__int64 a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rbx
  SIZE_T v5; // rdx
  char *v6; // rax
  char *v7; // rdx
  _WORD *v8; // rax

  v2 = GlobalAlloc(0x40u, 0x30u);
  v3 = v2;
  if ( !v2 )
    return 0;
  v2[3] = 0;
  v2[5] = 0;
  *(_DWORD *)v2 = 0;
  *((_DWORD *)v2 + 1) = *(_DWORD *)(a1 + 4);
  *((_DWORD *)v2 + 3) = *(_DWORD *)(a1 + 12);
  *((_DWORD *)v2 + 2) = *(_DWORD *)(a1 + 8);
  v5 = *(_QWORD *)(a1 + 16);
  v2[2] = v5;
  v6 = (char *)GlobalAlloc(0x40u, v5);
  v3[4] = v6;
  v7 = v6;
  if ( !v6 )
  {
    GlobalFree(v3);
    return 0;
  }
  v8 = *(_WORD **)(a1 + 32);
  if ( *v8 == 2 )
  {
    *(_DWORD *)v7 = 2;
    *((_QWORD *)v7 + 1) = 0;
    *((_DWORD *)v7 + 1) = -1;
  }
  else if ( *v8 == 23 )
  {
    *(_DWORD *)v7 = 23;
    *((_DWORD *)v7 + 1) = *(_DWORD *)(*(_QWORD *)(a1 + 32) + 4LL);
    *((_DWORD *)v7 + 6) = *(_DWORD *)(*(_QWORD *)(a1 + 32) + 24LL);
    *(_OWORD *)(v7 + 8) = 0;
    *((_WORD *)v7 + 4) = -254;
    *((_WORD *)v7 + 11) = 1;
  }
  else
  {
    GlobalFree(v7);
    GlobalFree(v3);
    return 0;
  }
  return v3;
}

```

## disassembly

```asm
0x14000ca7c  mov     [rsp+arg_0], rbx
0x14000ca81  push    rdi
0x14000ca82  sub     rsp, 20h
0x14000ca86  mov     edx, 30h ; '0'; dwBytes
0x14000ca8b  mov     rdi, rcx
0x14000ca8e  lea     ecx, [rdx+10h]; uFlags
0x14000ca91  call    cs:__imp_GlobalAlloc
0x14000ca97  mov     rbx, rax
0x14000ca9a  test    rax, rax
0x14000ca9d  jnz     short loc_14000CAA6
0x14000ca9f  xor     eax, eax
0x14000caa1  jmp     loc_14000CB63
0x14000caa6  mov     qword ptr [rax+18h], 0
0x14000caae  mov     ecx, 40h ; '@'; uFlags
0x14000cab3  mov     qword ptr [rax+28h], 0
0x14000cabb  mov     dword ptr [rax], 0
0x14000cac1  mov     eax, [rdi+4]
0x14000cac4  mov     [rbx+4], eax
0x14000cac7  mov     eax, [rdi+0Ch]
0x14000caca  mov     [rbx+0Ch], eax
0x14000cacd  mov     eax, [rdi+8]
0x14000cad0  mov     [rbx+8], eax
0x14000cad3  mov     rdx, [rdi+10h]; dwBytes
0x14000cad7  mov     [rbx+10h], rdx
0x14000cadb  call    cs:__imp_GlobalAlloc
0x14000cae1  mov     [rbx+20h], rax
0x14000cae5  mov     rdx, rax
0x14000cae8  test    rax, rax
0x14000caeb  jnz     short loc_14000CAF8
0x14000caed  mov     rcx, rbx; hMem
0x14000caf0  call    cs:__imp_GlobalFree
0x14000caf6  jmp     short loc_14000CA9F
0x14000caf8  mov     rax, [rdi+20h]
0x14000cafc  mov     ecx, 2
0x14000cb01  cmp     [rax], cx
0x14000cb04  jz      short loc_14000CB51
0x14000cb06  mov     ecx, 17h
0x14000cb0b  cmp     [rax], cx
0x14000cb0e  jz      short loc_14000CB26
0x14000cb10  mov     rcx, rdx; hMem
0x14000cb13  call    cs:__imp_GlobalFree
0x14000cb19  mov     rcx, rbx; hMem
0x14000cb1c  call    cs:__imp_GlobalFree
0x14000cb22  xor     ebx, ebx
0x14000cb24  jmp     short loc_14000CB60
0x14000cb26  mov     [rdx], ecx
0x14000cb28  xorps   xmm0, xmm0
0x14000cb2b  mov     rax, [rdi+20h]
0x14000cb2f  mov     ecx, [rax+4]
0x14000cb32  mov     [rdx+4], ecx
0x14000cb35  mov     rax, [rdi+20h]
0x14000cb39  mov     ecx, [rax+18h]
0x14000cb3c  mov     [rdx+18h], ecx
0x14000cb3f  movups  xmmword ptr [rdx+8], xmm0
0x14000cb43  mov     word ptr [rdx+8], 0FF02h
0x14000cb49  mov     word ptr [rdx+16h], 1
0x14000cb4f  jmp     short loc_14000CB60
0x14000cb51  xor     eax, eax
0x14000cb53  mov     [rdx], ecx
0x14000cb55  mov     [rdx+8], rax
0x14000cb59  mov     dword ptr [rdx+4], 0FFFFFFFFh
0x14000cb60  mov     rax, rbx
0x14000cb63  mov     rbx, [rsp+28h+arg_0]
0x14000cb68  add     rsp, 20h
0x14000cb6c  pop     rdi
0x14000cb6d  retn
```
