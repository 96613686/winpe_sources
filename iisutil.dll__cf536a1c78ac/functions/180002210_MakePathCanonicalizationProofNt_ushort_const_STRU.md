# MakePathCanonicalizationProofNt(ushort const *,STRU *)

- ea: `0x180002210`
- end: `0x180002453`
- name: `?MakePathCanonicalizationProofNt@@YAJPEBGPEAVSTRU@@@Z`
- size: `579`
- prototype: `int __fastcall(const unsigned __int16 *, struct STRU *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180002210`
- `0x1800026d0`
- `0x180002da0`
- `0x18002e516`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800023a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800023d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002415`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800023a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800023d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002415`

## pseudocode

```c
int __fastcall MakePathCanonicalizationProofNt(const unsigned __int16 *a1, struct STRU *a2)
{
  const unsigned __int16 *v3; // rbx
  unsigned __int16 v4; // ax
  unsigned int *v5; // rsi
  __int64 v6; // rcx
  __int64 v7; // rbp
  __int64 v8; // rax
  unsigned int v10; // r14d
  __int64 v11; // rcx
  __int64 v12; // rdx
  int result; // eax
  __int64 v14; // rcx
  unsigned __int64 v15; // rdx
  bool v16; // sf
  bool v17; // sf

  v3 = a1;
  if ( *(_DWORD *)a1 == 6029404 )
  {
    v4 = a1[2];
    if ( (v4 == 63 || v4 == 46) && a1[3] == 92 )
    {
      v5 = (unsigned int *)((char *)a2 + 40);
      if ( *((_DWORD *)a2 + 10) >= 0xAu || BUFFER::Resize(a2, 0x88u) )
      {
        **((_QWORD **)a2 + 4) = 0x5C003F003F005CLL;
        v6 = *((_QWORD *)a2 + 4);
        *((_DWORD *)a2 + 12) = 4;
        *(_WORD *)(v6 + 8) = 0;
      }
      else
      {
        result = GetLastError();
        v16 = result < 0;
        if ( result > 0 )
        {
          result = (unsigned __int16)result | 0x80070000;
          v16 = result < 0;
        }
        if ( v16 )
          return result;
      }
      v3 += 4;
    }
    else
    {
      result = STRU::Copy(a2, L"\\??\\UNC\\");
      if ( result < 0 )
        return result;
      v3 += 2;
      v5 = (unsigned int *)((char *)a2 + 40);
    }
    if ( !v3 )
      return 0;
  }
  else
  {
    v5 = (unsigned int *)((char *)a2 + 40);
    if ( *((_DWORD *)a2 + 10) >= 0xAu || BUFFER::Resize(a2, 0x88u) )
    {
      **((_QWORD **)a2 + 4) = 0x5C003F003F005CLL;
      v14 = *((_QWORD *)a2 + 4);
      *((_DWORD *)a2 + 12) = 4;
      *(_WORD *)(v14 + 8) = 0;
    }
    else
    {
      result = GetLastError();
      v17 = result < 0;
      if ( result > 0 )
      {
        result = (unsigned __int16)result | 0x80070000;
        v17 = result < 0;
      }
      if ( v17 )
        return result;
    }
  }
  v7 = (unsigned int)(2 * *((_DWORD *)a2 + 12));
  v8 = -1;
  while ( v3[++v8] != 0 )
    ;
  v10 = 2 * v8;
  if ( *v5 >= (unsigned __int64)(unsigned int)(2 * v8) + v7 + 2 )
    goto LABEL_11;
  v15 = v10 + v7 + 128;
  if ( v15 > 0xFFFFFFFF )
    return -2147024362;
  if ( BUFFER::Resize(a2, v15) )
  {
LABEL_11:
    memcpy_0((void *)((unsigned int)v7 + *((_QWORD *)a2 + 4)), v3, v10);
    v11 = *((_QWORD *)a2 + 4);
    v12 = (v10 + (unsigned int)v7) >> 1;
    result = 0;
    *((_DWORD *)a2 + 12) = v12;
    *(_WORD *)(v11 + 2 * v12) = 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180002210  push    rbx
0x180002212  push    rsi
0x180002213  push    rdi
0x180002214  sub     rsp, 20h
0x180002218  cmp     word ptr [rcx], 5Ch ; '\'
0x18000221c  mov     rdi, rdx
0x18000221f  mov     rbx, rcx
0x180002222  jnz     loc_18000231A
0x180002228  cmp     word ptr [rcx+2], 5Ch ; '\'
0x18000222d  jnz     loc_18000231A
0x180002233  movzx   eax, word ptr [rcx+4]
0x180002237  cmp     ax, 3Fh ; '?'
0x18000223b  jnz     loc_18000234F
0x180002241  cmp     word ptr [rcx+6], 5Ch ; '\'
0x180002246  jnz     loc_180002359
0x18000224c  cmp     dword ptr [rdx+28h], 0Ah
0x180002250  lea     rsi, [rdx+28h]
0x180002254  jb      loc_1800023C2
0x18000225a  mov     rax, [rdi+20h]
0x18000225e  mov     rcx, 5C003F003F005Ch
0x180002268  mov     [rax], rcx
0x18000226b  xor     eax, eax
0x18000226d  mov     rcx, [rdi+20h]
0x180002271  mov     dword ptr [rdi+30h], 4
0x180002278  mov     [rcx+8], ax
0x18000227c  add     rbx, 8
0x180002280  test    rbx, rbx
0x180002283  jz      loc_18000243E
0x180002289  mov     eax, [rdi+30h]
0x18000228c  mov     [rsp+38h+arg_0], rbp
0x180002291  mov     [rsp+38h+arg_8], r12
0x180002296  mov     [rsp+38h+arg_10], r14
0x18000229b  lea     ebp, [rax+rax]
0x18000229e  mov     [rsp+38h+arg_18], r15
0x1800022a3  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800022aa  nop     word ptr [rax+rax+00h]
0x1800022b0  cmp     word ptr [rbx+rax*2+2], 0
0x1800022b6  lea     rax, [rax+1]
0x1800022ba  jnz     short loc_1800022B0
0x1800022bc  lea     r14d, [rax+rax]
0x1800022c0  mov     r15d, ebp
0x1800022c3  mov     eax, [rsi]
0x1800022c5  lea     rcx, [rbp+2]
0x1800022c9  mov     r12d, r14d
0x1800022cc  add     rcx, r12
0x1800022cf  cmp     rax, rcx
0x1800022d2  jb      loc_180002379
0x1800022d8  mov     rcx, [rdi+20h]
0x1800022dc  mov     r8, r12; Size
0x1800022df  add     rcx, r15; void *
0x1800022e2  mov     rdx, rbx; Src
0x1800022e5  call    memcpy_0
0x1800022ea  mov     rcx, [rdi+20h]
0x1800022ee  lea     edx, [r14+rbp]
0x1800022f2  shr     edx, 1
0x1800022f4  xor     eax, eax
0x1800022f6  mov     [rdi+30h], edx
0x1800022f9  mov     [rcx+rdx*2], ax
0x1800022fd  mov     r14, [rsp+38h+arg_10]
0x180002302  mov     r12, [rsp+38h+arg_8]
0x180002307  mov     rbp, [rsp+38h+arg_0]
0x18000230c  mov     r15, [rsp+38h+arg_18]
0x180002311  add     rsp, 20h
0x180002315  pop     rdi
0x180002316  pop     rsi
0x180002317  pop     rbx
0x180002318  retn
0x18000231a  cmp     dword ptr [rdx+28h], 0Ah
0x18000231e  lea     rsi, [rdx+28h]
0x180002322  jb      loc_180002400
0x180002328  mov     rax, [rdi+20h]
0x18000232c  mov     rcx, 5C003F003F005Ch
0x180002336  mov     [rax], rcx
0x180002339  xor     eax, eax
0x18000233b  mov     rcx, [rdi+20h]
0x18000233f  mov     dword ptr [rdi+30h], 4
0x180002346  mov     [rcx+8], ax
0x18000234a  jmp     loc_180002289
0x18000234f  cmp     ax, 2Eh ; '.'
0x180002353  jz      loc_180002241
0x180002359  lea     rdx, aUnc; "\\??\\UNC\\"
0x180002360  mov     rcx, rdi; this
0x180002363  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180002368  test    eax, eax
0x18000236a  js      short loc_180002311
0x18000236c  add     rbx, 4
0x180002370  lea     rsi, [rdi+28h]
0x180002374  jmp     loc_180002280
0x180002379  lea     rdx, [rbp+80h]
0x180002380  mov     eax, 0FFFFFFFFh
0x180002385  add     rdx, r12; unsigned int
0x180002388  cmp     rdx, rax
0x18000238b  ja      loc_180002449
0x180002391  mov     rcx, rdi; this
0x180002394  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180002399  test    al, al
0x18000239b  jnz     loc_1800022D8
0x1800023a1  call    cs:__imp_GetLastError
0x1800023a8  nop     dword ptr [rax+rax+00h]
0x1800023ad  test    eax, eax
0x1800023af  jle     loc_1800022FD
0x1800023b5  movzx   eax, ax
0x1800023b8  or      eax, 80070000h
0x1800023bd  jmp     loc_1800022FD
0x1800023c2  mov     edx, 88h; unsigned int
0x1800023c7  mov     rcx, rdi; this
0x1800023ca  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800023cf  test    al, al
0x1800023d1  jnz     loc_18000225A
0x1800023d7  call    cs:__imp_GetLastError
0x1800023de  nop     dword ptr [rax+rax+00h]
0x1800023e3  test    eax, eax
0x1800023e5  jle     short loc_1800023F1
0x1800023e7  movzx   eax, ax
0x1800023ea  or      eax, 80070000h
0x1800023ef  test    eax, eax
0x1800023f1  jns     loc_18000227C
0x1800023f7  add     rsp, 20h
0x1800023fb  pop     rdi
0x1800023fc  pop     rsi
0x1800023fd  pop     rbx
0x1800023fe  retn
0x180002400  mov     edx, 88h; unsigned int
0x180002405  mov     rcx, rdi; this
0x180002408  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000240d  test    al, al
0x18000240f  jnz     loc_180002328
0x180002415  call    cs:__imp_GetLastError
0x18000241c  nop     dword ptr [rax+rax+00h]
0x180002421  test    eax, eax
0x180002423  jle     short loc_18000242F
0x180002425  movzx   eax, ax
0x180002428  or      eax, 80070000h
0x18000242d  test    eax, eax
0x18000242f  jns     loc_180002289
0x180002435  add     rsp, 20h
0x180002439  pop     rdi
0x18000243a  pop     rsi
0x18000243b  pop     rbx
0x18000243c  retn
0x18000243e  xor     eax, eax
0x180002440  add     rsp, 20h
0x180002444  pop     rdi
0x180002445  pop     rsi
0x180002446  pop     rbx
0x180002447  retn
0x180002449  mov     eax, 80070216h
0x18000244e  jmp     loc_1800022FD
```
