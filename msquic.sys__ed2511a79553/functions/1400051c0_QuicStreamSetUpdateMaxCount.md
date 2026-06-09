# QuicStreamSetUpdateMaxCount

- ea: `0x1400051c0`
- end: `0x140005243`
- name: `QuicStreamSetUpdateMaxCount`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x140005aa4`

## callees

- `0x1400051c0`
- `0x14000d490`
- `0x14003c8e0`
- `0x14003ec10`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14003d551`
- `ntoskrnl!_snprintf_s` at `0x14003d551`

## string_xrefs

- `0x14003d53d`: `App configured max stream count of %hu (type=%hhu).`

## pseudocode

```c
void __fastcall QuicStreamSetUpdateMaxCount(__int64 a1, unsigned __int8 a2, unsigned __int16 a3)
{
  __int64 v3; // r14
  __int64 v5; // rbp
  _WORD *v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rax
  char DstBuf[128]; // [rsp+30h] [rbp-C8h] BYREF

  v3 = a2;
  v5 = a3;
  if ( byte_14005C48B < 0 )
  {
    _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "App configured max stream count of %hu (type=%hhu).", a3, a2);
    McTemplateU0ps_EtwWriteTransfer(v7, QuicConnLogInfo, a1 - 2032, DstBuf);
  }
  v6 = (_WORD *)(a1 + 16 + 24 * v3);
  if ( (*(_BYTE *)(a1 - 1784) & 4) != 0 )
  {
    v8 = (unsigned __int16)*v6;
    if ( (unsigned __int16)v5 >= (unsigned __int16)v8 )
    {
      *(_QWORD *)(a1 + 24 * v3) += v5 - v8;
      QuicSendSetSendFlag(a1 + 1384, (v3 & 2) != 0 ? 128 : 64);
    }
  }
  else
  {
    *(_QWORD *)(a1 + 24 * v3) = v5;
  }
  *v6 = v5;
}

```

## disassembly

```asm
0x1400051c0  push    rbx
0x1400051c2  push    rbp
0x1400051c3  push    rsi
0x1400051c4  push    rdi
0x1400051c5  push    r12
0x1400051c7  push    r14
0x1400051c9  push    r15
0x1400051cb  sub     rsp, 0C0h
0x1400051d2  mov     rax, cs:__security_cookie
0x1400051d9  xor     rax, rsp
0x1400051dc  mov     [rsp+0F8h+var_48], rax
0x1400051e4  movzx   r14d, dl
0x1400051e8  mov     rdi, rcx
0x1400051eb  mov     edx, 80h; SizeInBytes
0x1400051f0  movzx   ebp, r8w
0x1400051f4  test    cs:byte_14005C48B, dl
0x1400051fa  lea     rsi, [r14+r14*2]
0x1400051fe  jnz     loc_14003D538
0x140005204  test    byte ptr [rdi-6F8h], 4
0x14000520b  lea     rbx, [rdi+10h]
0x14000520f  lea     rbx, [rbx+rsi*8]
0x140005213  jnz     loc_14003D57B
0x140005219  mov     [rdi+rsi*8], rbp
0x14000521d  mov     [rbx], bp
0x140005220  mov     rcx, [rsp+0F8h+var_48]
0x140005228  xor     rcx, rsp; StackCookie
0x14000522b  call    __security_check_cookie
0x140005230  add     rsp, 0C0h
0x140005237  pop     r15
0x140005239  pop     r14
0x14000523b  pop     r12
0x14000523d  pop     rdi
0x14000523e  pop     rsi
0x14000523f  pop     rbp
0x140005240  pop     rbx
0x140005241  retn
0x14003d538  mov     [rsp+0F8h+var_D0], r14d
0x14003d53d  lea     r9, aAppConfiguredM; "App configured max stream count of %hu "...
0x14003d544  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14003d548  mov     [rsp+0F8h+var_D8], ebp
0x14003d54c  lea     rcx, [rsp+0F8h+DstBuf]; DstBuf
0x14003d551  call    cs:__imp__snprintf_s
0x14003d558  nop     dword ptr [rax+rax+00h]
0x14003d55d  lea     r9, [rsp+0F8h+DstBuf]
0x14003d562  lea     r8, [rdi-7F0h]
0x14003d569  lea     rdx, QuicConnLogInfo
0x14003d570  call    McTemplateU0ps_EtwWriteTransfer
0x14003d575  nop
0x14003d576  jmp     loc_140005204
0x14003d57b  movzx   eax, word ptr [rbx]
0x14003d57e  cmp     bp, ax
0x14003d581  jb      loc_14000521D
0x14003d587  and     r14b, 2
0x14003d58b  mov     rcx, rbp
0x14003d58e  sub     rcx, rax
0x14003d591  add     [rdi+rsi*8], rcx
0x14003d595  lea     rcx, [rdi+568h]
0x14003d59c  neg     r14b
0x14003d59f  sbb     edx, edx
0x14003d5a1  and     edx, 40h
0x14003d5a4  add     edx, 40h ; '@'
0x14003d5a7  call    QuicSendSetSendFlag
0x14003d5ac  nop
0x14003d5ad  jmp     loc_14000521D
```
