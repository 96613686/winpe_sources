# DiscpAddSendTargetPortal

- ea: `0x180001df4`
- end: `0x180001faf`
- name: `DiscpAddSendTargetPortal`
- size: `443`
- prototype: `__int64 __fastcall(_OWORD *, int, _WORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004980`

## callees

- `0x180001cfe`
- `0x180001df4`
- `0x1800026f8`
- `0x180016de8`

## import_xrefs

- `ISCSIUM!DiscpAllocMemory` at `0x180001e36`
- `ISCSIUM!DiscpAllocMemory` at `0x180001e36`
- `ISCSIUM!DiscpSetRegistryValue` at `0x180001f76`
- `ISCSIUM!DiscpSetRegistryValue` at `0x180001f76`
- `ISCSIUM!DiscpFreeMemory` at `0x180001f86`
- `ISCSIUM!DiscpFreeMemory` at `0x180001f8f`
- `ISCSIUM!DiscpFreeMemory` at `0x180001f86`
- `ISCSIUM!DiscpFreeMemory` at `0x180001f8f`

## pseudocode

```c
__int64 __fastcall DiscpAddSendTargetPortal(_OWORD *a1, int a2, _WORD *a3, __int64 a4, __int64 a5)
{
  unsigned int v9; // ebp
  char *v10; // rax
  char *v11; // rbx
  _WORD *v12; // r8
  __int64 v13; // rdi
  _OWORD *v14; // rcx
  _OWORD *v15; // rax
  __int128 v16; // xmm1
  _WORD *v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rax
  _WORD *v20; // rcx
  unsigned int PortalName; // edi
  __int64 v23; // [rsp+A8h] [rbp+20h] BYREF

  v23 = 0;
  if ( a4 )
    v9 = *(_DWORD *)(a4 + 40) + *(_DWORD *)(a4 + 36) + 1672;
  else
    v9 = 1608;
  v10 = (char *)DiscpAllocMemory(v9);
  v11 = v10;
  if ( v10 )
  {
    memset_0(v10, 0, v9);
    v13 = 8;
    v14 = v11;
    v15 = a1;
    do
    {
      *v14 = *v15;
      v14[1] = v15[1];
      v14[2] = v15[2];
      v14[3] = v15[3];
      v14[4] = v15[4];
      v14[5] = v15[5];
      v14[6] = v15[6];
      v16 = v15[7];
      v15 += 8;
      v14[7] = v16;
      v14 += 8;
      --v13;
    }
    while ( v13 );
    v17 = v11 + 1026;
    *(_WORD *)v14 = *(_WORD *)v15;
    if ( a3 )
    {
      v18 = 2147483646;
      v12 = a3;
      v19 = 256;
      do
      {
        if ( !v18 )
          break;
        if ( !*v12 )
          break;
        *v17++ = *v12++;
        --v18;
        --v19;
      }
      while ( v19 );
      v20 = v17 - 1;
      if ( v19 )
        v20 = v17;
      *v20 = 0;
    }
    else
    {
      *v17 = 0;
    }
    *((_QWORD *)v11 + 193) = a5;
    *((_DWORD *)v11 + 385) = a2;
    if ( a4 )
      DiscpCopyLoginOptionsToStatic(v11 + 1552, a4, v12);
    PortalName = DiscpCreatePortalName((_DWORD)a1, (_DWORD)a3, a2, 0, (__int64)&v23);
    if ( !PortalName )
    {
      PortalName = DiscpSetRegistryValue(
                     0,
                     L"Software\\Microsoft\\Windows NT\\CurrentVersion\\iSCSI\\Discovery\\Send Targets",
                     v23,
                     3,
                     v11,
                     v9,
                     1);
      DiscpFreeMemory(v23);
    }
    DiscpFreeMemory(v11);
  }
  else
  {
    return 8;
  }
  return PortalName;
}

```

## disassembly

```asm
0x180001df4  mov     rax, rsp
0x180001df7  push    rbx
0x180001df8  push    rbp
0x180001df9  push    rsi
0x180001dfa  push    rdi
0x180001dfb  push    r12
0x180001dfd  push    r13
0x180001dff  push    r14
0x180001e01  push    r15
0x180001e03  sub     rsp, 48h
0x180001e07  xor     r13d, r13d
0x180001e0a  mov     rsi, r9
0x180001e0d  mov     [rax+20h], r13
0x180001e11  mov     r14, r8
0x180001e14  mov     r15d, edx
0x180001e17  mov     r12, rcx
0x180001e1a  test    r9, r9
0x180001e1d  jz      short loc_180001E2F
0x180001e1f  mov     ebp, [r9+24h]
0x180001e23  add     ebp, 688h
0x180001e29  add     ebp, [r9+28h]
0x180001e2d  jmp     short loc_180001E34
0x180001e2f  mov     ebp, 648h
0x180001e34  mov     ecx, ebp
0x180001e36  call    cs:__imp_DiscpAllocMemory
0x180001e3c  mov     rbx, rax
0x180001e3f  test    rax, rax
0x180001e42  jz      loc_180001F97
0x180001e48  mov     r8d, ebp; Size
0x180001e4b  xor     edx, edx; Val
0x180001e4d  mov     rcx, rax; void *
0x180001e50  call    memset_0
0x180001e55  mov     edi, 8
0x180001e5a  mov     rcx, rbx
0x180001e5d  mov     rax, r12
0x180001e60  lea     edx, [rdi+78h]
0x180001e63  movups  xmm0, xmmword ptr [rax]
0x180001e66  movups  xmmword ptr [rcx], xmm0
0x180001e69  movups  xmm1, xmmword ptr [rax+10h]
0x180001e6d  movups  xmmword ptr [rcx+10h], xmm1
0x180001e71  movups  xmm0, xmmword ptr [rax+20h]
0x180001e75  movups  xmmword ptr [rcx+20h], xmm0
0x180001e79  movups  xmm1, xmmword ptr [rax+30h]
0x180001e7d  movups  xmmword ptr [rcx+30h], xmm1
0x180001e81  movups  xmm0, xmmword ptr [rax+40h]
0x180001e85  movups  xmmword ptr [rcx+40h], xmm0
0x180001e89  movups  xmm1, xmmword ptr [rax+50h]
0x180001e8d  movups  xmmword ptr [rcx+50h], xmm1
0x180001e91  movups  xmm0, xmmword ptr [rax+60h]
0x180001e95  movups  xmmword ptr [rcx+60h], xmm0
0x180001e99  movups  xmm1, xmmword ptr [rax+70h]
0x180001e9d  add     rax, rdx
0x180001ea0  movups  xmmword ptr [rcx+70h], xmm1
0x180001ea4  add     rcx, rdx
0x180001ea7  sub     rdi, 1
0x180001eab  jnz     short loc_180001E63
0x180001ead  movzx   eax, word ptr [rax]
0x180001eb0  lea     rdx, [rbx+402h]
0x180001eb7  mov     [rcx], ax
0x180001eba  test    r14, r14
0x180001ebd  jz      short loc_180001F01
0x180001ebf  mov     ecx, 7FFFFFFEh
0x180001ec4  mov     r8, r14
0x180001ec7  mov     eax, 100h
0x180001ecc  test    rcx, rcx
0x180001ecf  jz      short loc_180001EF0
0x180001ed1  movzx   r9d, word ptr [r8]
0x180001ed5  test    r9w, r9w
0x180001ed9  jz      short loc_180001EF0
0x180001edb  mov     [rdx], r9w
0x180001edf  add     r8, 2
0x180001ee3  add     rdx, 2
0x180001ee7  dec     rcx
0x180001eea  sub     rax, 1
0x180001eee  jnz     short loc_180001ECC
0x180001ef0  test    rax, rax
0x180001ef3  lea     rcx, [rdx-2]
0x180001ef7  cmovnz  rcx, rdx
0x180001efb  mov     [rcx], r13w
0x180001eff  jmp     short loc_180001F05
0x180001f01  mov     [rdx], r13w
0x180001f05  mov     rax, [rsp+88h+arg_20]
0x180001f0d  mov     [rbx+608h], rax
0x180001f14  mov     [rbx+604h], r15d
0x180001f1b  test    rsi, rsi
0x180001f1e  jz      short loc_180001F2F
0x180001f20  lea     rcx, [rbx+610h]
0x180001f27  mov     rdx, rsi
0x180001f2a  call    DiscpCopyLoginOptionsToStatic
0x180001f2f  lea     rax, [rsp+88h+arg_18]
0x180001f37  xor     r9d, r9d
0x180001f3a  mov     r8d, r15d
0x180001f3d  mov     [rsp+88h+var_68], rax
0x180001f42  mov     rdx, r14
0x180001f45  mov     rcx, r12
0x180001f48  call    DiscpCreatePortalName
0x180001f4d  mov     edi, eax
0x180001f4f  test    eax, eax
0x180001f51  jnz     short loc_180001F8C
0x180001f53  mov     r8, [rsp+88h+arg_18]
0x180001f5b  lea     r9d, [rax+3]
0x180001f5f  mov     [rsp+88h+var_58], 1
0x180001f64  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows NT\\Curren"...
0x180001f6b  mov     [rsp+88h+var_60], ebp
0x180001f6f  xor     ecx, ecx
0x180001f71  mov     [rsp+88h+var_68], rbx
0x180001f76  call    cs:__imp_DiscpSetRegistryValue
0x180001f7c  mov     rcx, [rsp+88h+arg_18]
0x180001f84  mov     edi, eax
0x180001f86  call    cs:__imp_DiscpFreeMemory
0x180001f8c  mov     rcx, rbx
0x180001f8f  call    cs:__imp_DiscpFreeMemory
0x180001f95  jmp     short loc_180001F9C
0x180001f97  mov     edi, 8
0x180001f9c  mov     eax, edi
0x180001f9e  add     rsp, 48h
0x180001fa2  pop     r15
0x180001fa4  pop     r14
0x180001fa6  pop     r13
0x180001fa8  pop     r12
0x180001faa  pop     rdi
0x180001fab  pop     rsi
0x180001fac  pop     rbp
0x180001fad  pop     rbx
0x180001fae  retn
```
