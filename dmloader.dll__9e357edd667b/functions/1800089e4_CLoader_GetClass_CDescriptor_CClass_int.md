# CLoader::GetClass(CDescriptor *,CClass * *,int)

- ea: `0x1800089e4`
- end: `0x180008adc`
- name: `?GetClass@CLoader@@AEAAJPEAVCDescriptor@@PEAPEAVCClass@@H@Z`
- size: `248`
- prototype: `__int64 __fastcall(CLoader *__hidden this, struct CDescriptor *, struct CClass **, int)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x1800080f0`
- `0x18000828c`
- `0x180008450`
- `0x1800085b0`
- `0x180008710`
- `0x180008bc0`
- `0x180008e90`
- `0x1800099e0`
- `0x180009b20`
- `0x180009d30`

## callees

- `0x1800089e4`
- `0x180009fdc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180008a4c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180008a4c`

## pseudocode

```c
__int64 __fastcall CLoader::GetClass(CLoader *this, struct CDescriptor *a2, struct CClass **a3, int a4)
{
  bool v4; // zf
  __int64 *i; // rcx
  _QWORD *v10; // rax
  _QWORD *v11; // rbx
  __int128 v12; // xmm0

  v4 = (*((_BYTE *)a2 + 8) & 2) == 0;
  *a3 = 0;
  if ( v4 )
    return 2289570176LL;
  for ( i = (__int64 *)*((_QWORD *)this + 3); i; i = (__int64 *)*i )
  {
    if ( *(__int64 *)((char *)i + 36) == *(_QWORD *)((char *)a2 + 28)
      && *(__int64 *)((char *)i + 44) == *(_QWORD *)((char *)a2 + 36) )
    {
      *a3 = (struct CClass *)i;
      return 0;
    }
  }
  if ( !a4 )
    return 2289570181LL;
  v10 = malloc(0xE8u);
  v11 = v10;
  if ( v10 )
  {
    *v10 = 0;
    CDescriptor::CDescriptor((CDescriptor *)(v10 + 1));
    v11[25] = 0;
    *((_DWORD *)v11 + 56) = 0;
    v11[23] = this;
    *((_DWORD *)v11 + 48) = *((_DWORD *)this + 5);
    *((_DWORD *)v11 + 52) = 0;
    v11[27] = 0;
    v12 = *(_OWORD *)((char *)a2 + 28);
    *((_DWORD *)v11 + 4) = 2;
    *a3 = (struct CClass *)v11;
    *(_OWORD *)((char *)v11 + 36) = v12;
    *v11 = *((_QWORD *)this + 3);
    *((_QWORD *)this + 3) = v11;
    return 0;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800089e4  push    rbx
0x1800089e6  push    rsi
0x1800089e7  push    rdi
0x1800089e8  push    r14
0x1800089ea  sub     rsp, 28h
0x1800089ee  test    byte ptr [rdx+8], 2
0x1800089f2  mov     r14, r8
0x1800089f5  mov     rsi, rdx
0x1800089f8  mov     qword ptr [r8], 0
0x1800089ff  mov     rdi, rcx
0x180008a02  jnz     short loc_180008A0E
0x180008a04  mov     eax, 88781180h
0x180008a09  jmp     loc_180008AD2
0x180008a0e  mov     rcx, [rcx+18h]
0x180008a12  jmp     short loc_180008A2B
0x180008a14  mov     rax, [rcx+24h]
0x180008a18  cmp     rax, [rdx+1Ch]
0x180008a1c  jnz     short loc_180008A28
0x180008a1e  mov     rax, [rcx+2Ch]
0x180008a22  cmp     rax, [rdx+24h]
0x180008a26  jz      short loc_180008A32
0x180008a28  mov     rcx, [rcx]
0x180008a2b  test    rcx, rcx
0x180008a2e  jnz     short loc_180008A14
0x180008a30  jmp     short loc_180008A3E
0x180008a32  mov     [r8], rcx
0x180008a35  test    rcx, rcx
0x180008a38  jnz     loc_180008AC2
0x180008a3e  test    r9d, r9d
0x180008a41  jz      loc_180008ACD
0x180008a47  mov     ecx, 0E8h; Size
0x180008a4c  call    cs:__imp_malloc
0x180008a52  mov     rbx, rax
0x180008a55  test    rax, rax
0x180008a58  jz      short loc_180008AC6
0x180008a5a  lea     rcx, [rax+8]; this
0x180008a5e  mov     qword ptr [rax], 0
0x180008a65  call    ??0CDescriptor@@QEAA@XZ; CDescriptor::CDescriptor(void)
0x180008a6a  mov     qword ptr [rbx+0C8h], 0
0x180008a75  mov     dword ptr [rbx+0E0h], 0
0x180008a7f  mov     [rbx+0B8h], rdi
0x180008a86  mov     ecx, [rdi+14h]
0x180008a89  mov     [rbx+0C0h], ecx
0x180008a8f  mov     dword ptr [rbx+0D0h], 0
0x180008a99  mov     qword ptr [rbx+0D8h], 0
0x180008aa4  movups  xmm0, xmmword ptr [rsi+1Ch]
0x180008aa8  mov     dword ptr [rbx+10h], 2
0x180008aaf  mov     [r14], rbx
0x180008ab2  movdqu  xmmword ptr [rbx+24h], xmm0
0x180008ab7  mov     rax, [rdi+18h]
0x180008abb  mov     [rbx], rax
0x180008abe  mov     [rdi+18h], rbx
0x180008ac2  xor     eax, eax
0x180008ac4  jmp     short loc_180008AD2
0x180008ac6  mov     eax, 8007000Eh
0x180008acb  jmp     short loc_180008AD2
0x180008acd  mov     eax, 88781185h
0x180008ad2  add     rsp, 28h
0x180008ad6  pop     r14
0x180008ad8  pop     rdi
0x180008ad9  pop     rsi
0x180008ada  pop     rbx
0x180008adb  retn
```
