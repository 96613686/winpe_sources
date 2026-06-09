# XdrDecodeNfs3PathConf

- ea: `0x14000c818`
- end: `0x14000c8d0`
- name: `XdrDecodeNfs3PathConf`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000c8d8`

## callees

- `0x14000c818`
- `0x140011f84`
- `0x140025004`

## pseudocode

```c
bool __fastcall XdrDecodeNfs3PathConf(__int64 a1, _DWORD *a2)
{
  if ( *(int *)(a1 + 264) >= 0 )
  {
    if ( (unsigned int)XdrBytesLeft() >= 0x18 )
    {
      *a2 = XdrDecodeInt(a1);
      a2[1] = XdrDecodeInt(a1);
      a2[2] = XdrDecodeInt(a1) != 0;
      a2[3] = XdrDecodeInt(a1) != 0;
      a2[4] = XdrDecodeInt(a1) != 0;
      a2[5] = XdrDecodeInt(a1) != 0;
    }
    else
    {
      *(_DWORD *)(a1 + 264) = -1073741789;
    }
  }
  if ( *(int *)(a1 + 264) < 0 )
  {
    *(_OWORD *)a2 = 0;
    *((_QWORD *)a2 + 2) = 0;
  }
  return *(_DWORD *)(a1 + 264) >= 0;
}

```

## disassembly

```asm
0x14000c818  mov     [rsp+arg_0], rbx
0x14000c81d  push    rdi
0x14000c81e  sub     rsp, 20h
0x14000c822  cmp     dword ptr [rcx+108h], 0
0x14000c829  mov     rdi, rdx
0x14000c82c  mov     rbx, rcx
0x14000c82f  jl      short loc_14000C8A4
0x14000c831  call    XdrBytesLeft
0x14000c836  cmp     eax, 18h
0x14000c839  jnb     short loc_14000C847
0x14000c83b  mov     dword ptr [rbx+108h], 0C0000023h
0x14000c845  jmp     short loc_14000C8A4
0x14000c847  mov     rcx, rbx
0x14000c84a  call    XdrDecodeInt
0x14000c84f  mov     rcx, rbx
0x14000c852  mov     [rdi], eax
0x14000c854  call    XdrDecodeInt
0x14000c859  mov     rcx, rbx
0x14000c85c  mov     [rdi+4], eax
0x14000c85f  call    XdrDecodeInt
0x14000c864  xor     ecx, ecx
0x14000c866  test    eax, eax
0x14000c868  setnz   cl
0x14000c86b  mov     [rdi+8], ecx
0x14000c86e  mov     rcx, rbx
0x14000c871  call    XdrDecodeInt
0x14000c876  xor     ecx, ecx
0x14000c878  test    eax, eax
0x14000c87a  setnz   cl
0x14000c87d  mov     [rdi+0Ch], ecx
0x14000c880  mov     rcx, rbx
0x14000c883  call    XdrDecodeInt
0x14000c888  xor     ecx, ecx
0x14000c88a  test    eax, eax
0x14000c88c  setnz   cl
0x14000c88f  mov     [rdi+10h], ecx
0x14000c892  mov     rcx, rbx
0x14000c895  call    XdrDecodeInt
0x14000c89a  xor     ecx, ecx
0x14000c89c  test    eax, eax
0x14000c89e  setnz   cl
0x14000c8a1  mov     [rdi+14h], ecx
0x14000c8a4  cmp     dword ptr [rbx+108h], 0
0x14000c8ab  jge     short loc_14000C8B9
0x14000c8ad  xorps   xmm0, xmm0
0x14000c8b0  xor     eax, eax
0x14000c8b2  movups  xmmword ptr [rdi], xmm0
0x14000c8b5  mov     [rdi+10h], rax
0x14000c8b9  mov     eax, [rbx+108h]
0x14000c8bf  mov     rbx, [rsp+28h+arg_0]
0x14000c8c4  shr     eax, 1Fh
0x14000c8c7  xor     al, 1
0x14000c8c9  add     rsp, 20h
0x14000c8cd  pop     rdi
0x14000c8ce  retn
```
