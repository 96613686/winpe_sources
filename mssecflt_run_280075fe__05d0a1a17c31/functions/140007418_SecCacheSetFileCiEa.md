# SecCacheSetFileCiEa

- ea: `0x140007418`
- end: `0x14000751e`
- name: `SecCacheSetFileCiEa`
- size: `262`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140022c2c`
- `0x14003d558`

## callees

- `0x140007418`
- `0x140009b80`
- `0x140011610`
- `0x1400119c0`
- `0x140030020`
- `0x1400308a0`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x140007470`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140007470`

## pseudocode

```c
__int64 __fastcall SecCacheSetFileCiEa(struct _FILE_OBJECT *a1, __int64 a2)
{
  unsigned int v4; // edi
  char *PoolWithTag; // rax
  char *v6; // rbx
  __int64 v7; // r8

  if ( SecCacheIsFileEaCacheable(a1) )
  {
    if ( qword_140020008 )
      PoolWithTag = (char *)qword_140020008(256, 64, 1366123859);
    else
      PoolWithTag = (char *)ExAllocatePoolWithTag(PagedPool, 0x40u, 0x516D6553u);
    v6 = PoolWithTag;
    if ( PoolWithTag )
    {
      memset(PoolWithTag, 0, 0x40u);
      v6[5] = 31;
      LOBYTE(v7) = 1;
      *((_WORD *)v6 + 3) = 24;
      qmemcpy(v6 + 8, "$Kernel.Purge.SEC.CodeIntegrity", 31);
      *(_OWORD *)(v6 + 40) = *(_OWORD *)a2;
      *((_QWORD *)v6 + 7) = *(_QWORD *)(a2 + 16);
      v4 = SecCacheSetFileKernelEa(a1, v6, v7);
      SecFreePool(v6, 0x516D6553u);
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  else
  {
    return (unsigned int)-1073741637;
  }
  return v4;
}

```

## disassembly

```asm
0x140007418  mov     [rsp+arg_0], rbx
0x14000741d  mov     [rsp+arg_8], rbp
0x140007422  mov     [rsp+arg_10], rsi
0x140007427  push    rdi
0x140007428  sub     rsp, 20h
0x14000742c  mov     rbp, rdx
0x14000742f  mov     rsi, rcx
0x140007432  call    SecCacheIsFileEaCacheable
0x140007437  test    al, al
0x140007439  jnz     short loc_140007445
0x14000743b  mov     edi, 0C00000BBh
0x140007440  jmp     loc_140007506
0x140007445  mov     rax, cs:qword_140020008
0x14000744c  mov     edi, 40h ; '@'
0x140007451  mov     r8d, 516D6553h; Tag
0x140007457  mov     edx, edi; NumberOfBytes
0x140007459  test    rax, rax
0x14000745c  jz      short loc_14000746B
0x14000745e  mov     ecx, 100h
0x140007463  call    cs:__guard_dispatch_icall_fptr
0x140007469  jmp     short loc_14000747C
0x14000746b  mov     ecx, 1; PoolType
0x140007470  call    cs:__imp_ExAllocatePoolWithTag
0x140007477  nop     dword ptr [rax+rax+00h]
0x14000747c  mov     rbx, rax
0x14000747f  test    rax, rax
0x140007482  jnz     short loc_14000748B
0x140007484  mov     edi, 0C000009Ah
0x140007489  jmp     short loc_140007506
0x14000748b  mov     r8, rdi; Size
0x14000748e  xor     edx, edx; Val
0x140007490  mov     rcx, rbx; void *
0x140007493  call    memset
0x140007498  mov     byte ptr [rbx+5], 1Fh
0x14000749c  mov     r8b, 1
0x14000749f  mov     word ptr [rbx+6], 18h
0x1400074a5  mov     rdx, rbx
0x1400074a8  movups  xmm0, xmmword ptr cs:aKernelPurgeSec_1; "$Kernel.Purge.SEC.CodeIntegrity"
0x1400074af  mov     rcx, rsi
0x1400074b2  movups  xmmword ptr [rbx+8], xmm0
0x1400074b6  movsd   xmm0, qword ptr cs:aKernelPurgeSec_1+10h; "C.CodeIntegrity"
0x1400074be  movsd   qword ptr [rbx+18h], xmm0
0x1400074c3  mov     eax, dword ptr cs:aKernelPurgeSec_1+18h; "tegrity"
0x1400074c9  mov     [rbx+20h], eax
0x1400074cc  movzx   eax, word ptr cs:aKernelPurgeSec_1+1Ch; "ity"
0x1400074d3  mov     [rbx+24h], ax
0x1400074d7  mov     al, byte ptr cs:aKernelPurgeSec_1+1Eh; "y"
0x1400074dd  mov     [rbx+26h], al
0x1400074e0  movups  xmm0, xmmword ptr [rbp+0]
0x1400074e4  movups  xmmword ptr [rbx+28h], xmm0
0x1400074e8  movsd   xmm1, qword ptr [rbp+10h]
0x1400074ed  movsd   qword ptr [rbx+38h], xmm1
0x1400074f2  call    SecCacheSetFileKernelEa
0x1400074f7  mov     edi, eax
0x1400074f9  mov     edx, 516D6553h; Tag
0x1400074fe  mov     rcx, rbx; P
0x140007501  call    SecFreePool
0x140007506  mov     rbx, [rsp+28h+arg_0]
0x14000750b  mov     eax, edi
0x14000750d  mov     rbp, [rsp+28h+arg_8]
0x140007512  mov     rsi, [rsp+28h+arg_10]
0x140007517  add     rsp, 20h
0x14000751b  pop     rdi
0x14000751c  retn
```
