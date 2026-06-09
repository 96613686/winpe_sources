# QuicPathInitialize

- ea: `0x1400078c8`
- end: `0x1400079dc`
- name: `QuicPathInitialize`
- size: `276`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140007b30`
- `0x14002fbf8`

## callees

- `0x1400078c8`
- `0x140033810`
- `0x14003c8e0`
- `0x14003ce00`
- `0x14003ec10`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14000799a`
- `ntoskrnl!_snprintf_s` at `0x14000799a`

## string_xrefs

- `0x140007986`: `Path[%hhu] Initialized`

## pseudocode

```c
char __fastcall QuicPathInitialize(__int64 a1, unsigned __int8 *a2)
{
  unsigned __int64 v4; // rcx
  char result; // al
  __int64 v6; // rcx
  char DstBuf[128]; // [rsp+30h] [rbp-98h] BYREF

  memset(a2, 0, 0xF0u);
  *a2 = (*(_BYTE *)(a1 + 276))++;
  a2[1] |= 1u;
  *((_QWORD *)a2 + 21) = 0xFFFFFFFFLL;
  *((_WORD *)a2 + 8) = *(_WORD *)(a1 + 224);
  v4 = (unsigned int)(1000 * *(_DWORD *)(a1 + 192));
  *((_QWORD *)a2 + 19) = v4;
  *((_QWORD *)a2 + 23) = v4 >> 1;
  result = a2[2] & 0xE7;
  a2[2] = result | ((*(_BYTE *)(a1 + 236) & 1) == 0 ? 0x18 : 0);
  if ( (*(_BYTE *)(a1 + 237) & 1) != 0 )
    result = CxPlatRandom(4u);
  if ( byte_14005C48B < 0 )
  {
    _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Path[%hhu] Initialized", *a2);
    return McTemplateU0ps_EtwWriteTransfer(v6, QuicConnLogInfo, a1, DstBuf);
  }
  return result;
}

```

## disassembly

```asm
0x1400078c8  mov     [rsp+arg_10], rbx
0x1400078cd  push    rdi
0x1400078ce  sub     rsp, 0C0h
0x1400078d5  mov     rax, cs:__security_cookie
0x1400078dc  xor     rax, rsp
0x1400078df  mov     [rsp+0C8h+var_18], rax
0x1400078e7  mov     rbx, rdx
0x1400078ea  mov     rdi, rcx
0x1400078ed  mov     rcx, rbx; void *
0x1400078f0  xor     edx, edx; Val
0x1400078f2  mov     r8d, 0F0h; Size
0x1400078f8  call    memset
0x1400078fd  mov     al, [rdi+114h]
0x140007903  mov     dl, 1
0x140007905  mov     [rbx], al
0x140007907  mov     eax, 0FFFFFFFFh
0x14000790c  add     [rdi+114h], dl
0x140007912  or      [rbx+1], dl
0x140007915  mov     [rbx+0A8h], rax
0x14000791c  movzx   eax, word ptr [rdi+0E0h]
0x140007923  mov     [rbx+10h], ax
0x140007927  imul    ecx, [rdi+0C0h], 3E8h
0x140007931  mov     [rbx+98h], rcx
0x140007938  shr     rcx, 1
0x14000793b  mov     [rbx+0B8h], rcx
0x140007942  mov     al, [rdi+0ECh]
0x140007948  and     al, dl
0x14000794a  neg     al
0x14000794c  mov     al, [rbx+2]
0x14000794f  sbb     cl, cl
0x140007951  and     al, 0E7h
0x140007953  not     cl
0x140007955  and     cl, 18h
0x140007958  or      cl, al
0x14000795a  mov     [rbx+2], cl
0x14000795d  test    [rdi+0EDh], dl
0x140007963  jz      short loc_140007976
0x140007965  lea     rdx, [rbx+8Ch]
0x14000796c  mov     ecx, 4; cbBuffer
0x140007971  call    CxPlatRandom
0x140007976  mov     edx, 80h; SizeInBytes
0x14000797b  test    cs:byte_14005C48B, dl
0x140007981  jz      short loc_1400079BA
0x140007983  movzx   eax, byte ptr [rbx]
0x140007986  lea     r9, aPathHhuInitial; "Path[%hhu] Initialized"
0x14000798d  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140007991  mov     [rsp+0C8h+var_A8], eax
0x140007995  lea     rcx, [rsp+0C8h+DstBuf]; DstBuf
0x14000799a  call    cs:__imp__snprintf_s
0x1400079a1  nop     dword ptr [rax+rax+00h]
0x1400079a6  lea     r9, [rsp+0C8h+DstBuf]
0x1400079ab  mov     r8, rdi
0x1400079ae  lea     rdx, QuicConnLogInfo
0x1400079b5  call    McTemplateU0ps_EtwWriteTransfer
0x1400079ba  mov     rcx, [rsp+0C8h+var_18]
0x1400079c2  xor     rcx, rsp; StackCookie
0x1400079c5  call    __security_check_cookie
0x1400079ca  mov     rbx, [rsp+0C8h+arg_10]
0x1400079d2  add     rsp, 0C0h
0x1400079d9  pop     rdi
0x1400079da  retn
```
