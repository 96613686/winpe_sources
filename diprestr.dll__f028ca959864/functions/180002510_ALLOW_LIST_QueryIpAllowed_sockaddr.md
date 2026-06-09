# ALLOW_LIST::QueryIpAllowed(sockaddr *)

- ea: `0x180002510`
- end: `0x1800025fd`
- name: `?QueryIpAllowed@ALLOW_LIST@@QEAAHPEAUsockaddr@@@Z`
- size: `237`
- prototype: `__int64 __fastcall(ALLOW_LIST *__hidden this, struct sockaddr *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800047a4`
- `0x180005ab8`

## callees

- `0x180002510`

## pseudocode

```c
__int64 __fastcall ALLOW_LIST::QueryIpAllowed(ALLOW_LIST *this, struct sockaddr *a2)
{
  unsigned int v2; // esi
  unsigned int v3; // r11d
  __int64 v5; // r14
  __int64 v6; // rdi
  __int64 v7; // rcx
  __int16 *v8; // r8
  __int16 v9; // ax
  bool v10; // zf
  BOOL v11; // edx
  __int64 v12; // r9

  v2 = *((_DWORD *)this + 5);
  v3 = 0;
  if ( v2 )
  {
    v5 = *((_QWORD *)this + 1);
    v6 = 0;
    while ( 1 )
    {
      v7 = *(_QWORD *)(v5 + 8 * v6);
      v8 = *(__int16 **)(v7 + 24);
      v9 = *v8;
      if ( *(_DWORD *)(v7 + 8) )
        break;
      if ( a2->sa_family != v9 )
        goto LABEL_18;
      if ( a2->sa_family != 2 )
      {
        if ( a2->sa_family == 23 )
        {
          v12 = 0;
          while ( (*(_WORD *)(*(_QWORD *)(v7 + 120) + 2 * v12 + 8) & *(_WORD *)&a2->sa_data[2 * v12 + 6]) == (*(_WORD *)(*(_QWORD *)(v7 + 120) + 2 * v12 + 8) & (unsigned __int16)v8[v12 + 4]) )
          {
            v12 = (unsigned int)(v12 + 1);
            if ( (unsigned int)v12 >= 8 )
              return 1;
          }
        }
        goto LABEL_18;
      }
      v11 = (*(_DWORD *)&a2->sa_data[2] & *(_DWORD *)(*(_QWORD *)(v7 + 120) + 4LL)) == (*(_DWORD *)(*(_QWORD *)(v7 + 120)
                                                                                                  + 4LL)
                                                                                      & *((_DWORD *)v8 + 1));
LABEL_17:
      if ( v11 )
        return 1;
LABEL_18:
      v6 = (unsigned int)(v6 + 1);
      if ( (unsigned int)v6 >= v2 )
        return v3;
    }
    if ( a2->sa_family == 23 )
    {
      if ( v9 == 23
        && *(_DWORD *)&a2[1].sa_data[6] == *((_DWORD *)v8 + 6)
        && *(_QWORD *)&a2[1].sa_family == *((_QWORD *)v8 + 2) )
      {
        v10 = *(_QWORD *)&a2->sa_data[6] == *((_QWORD *)v8 + 1);
        goto LABEL_9;
      }
    }
    else if ( v9 == 2 )
    {
      v10 = *(_DWORD *)&a2->sa_data[2] == *((_DWORD *)v8 + 1);
LABEL_9:
      if ( v10 )
      {
        v11 = 1;
        goto LABEL_17;
      }
    }
    v11 = 0;
    goto LABEL_17;
  }
  return v3;
}

```

## disassembly

```asm
0x180002510  push    rbx
0x180002512  push    rsi
0x180002513  push    rdi
0x180002514  push    r14
0x180002516  mov     esi, [rcx+14h]
0x180002519  xor     r11d, r11d
0x18000251c  mov     r10, rdx
0x18000251f  test    esi, esi
0x180002521  jz      loc_1800025F4
0x180002527  mov     r14, [rcx+8]
0x18000252b  xor     edi, edi
0x18000252d  mov     rcx, [r14+rdi*8]
0x180002531  mov     r8, [rcx+18h]
0x180002535  movzx   eax, word ptr [r8]
0x180002539  cmp     [rcx+8], r11d
0x18000253d  jz      short loc_180002585
0x18000253f  cmp     word ptr [r10], 17h
0x180002544  jnz     short loc_180002571
0x180002546  cmp     ax, 17h
0x18000254a  jnz     short loc_180002581
0x18000254c  mov     eax, [r8+18h]
0x180002550  cmp     [r10+18h], eax
0x180002554  jnz     short loc_180002581
0x180002556  mov     rax, [r8+10h]
0x18000255a  cmp     [r10+10h], rax
0x18000255e  jnz     short loc_180002581
0x180002560  mov     rax, [r8+8]
0x180002564  cmp     [r10+8], rax
0x180002568  jnz     short loc_180002581
0x18000256a  mov     edx, 1
0x18000256f  jmp     short loc_1800025AA
0x180002571  cmp     ax, 2
0x180002575  jnz     short loc_180002581
0x180002577  mov     eax, [r8+4]
0x18000257b  cmp     [r10+4], eax
0x18000257f  jmp     short loc_180002568
0x180002581  xor     edx, edx
0x180002583  jmp     short loc_1800025AA
0x180002585  cmp     [r10], ax
0x180002589  jnz     short loc_1800025AE
0x18000258b  cmp     word ptr [r10], 2
0x180002590  jnz     short loc_1800025BA
0x180002592  mov     rax, [rcx+78h]
0x180002596  xor     edx, edx
0x180002598  mov     ecx, [rax+4]
0x18000259b  mov     eax, [r8+4]
0x18000259f  and     eax, ecx
0x1800025a1  and     ecx, [r10+4]
0x1800025a5  cmp     ecx, eax
0x1800025a7  setz    dl
0x1800025aa  test    edx, edx
0x1800025ac  jnz     short loc_1800025EE
0x1800025ae  inc     edi
0x1800025b0  cmp     edi, esi
0x1800025b2  jb      loc_18000252D
0x1800025b8  jmp     short loc_1800025F4
0x1800025ba  cmp     word ptr [r10], 17h
0x1800025bf  jnz     short loc_1800025AE
0x1800025c1  mov     rbx, [rcx+78h]
0x1800025c5  xor     r9d, r9d
0x1800025c8  movzx   ecx, word ptr [r8+r9*2+8]
0x1800025ce  movzx   eax, word ptr [r10+r9*2+8]
0x1800025d4  and     cx, [rbx+r9*2+8]
0x1800025da  and     ax, [rbx+r9*2+8]
0x1800025e0  cmp     ax, cx
0x1800025e3  jnz     short loc_1800025AE
0x1800025e5  inc     r9d
0x1800025e8  cmp     r9d, 8
0x1800025ec  jb      short loc_1800025C8
0x1800025ee  mov     r11d, 1
0x1800025f4  mov     eax, r11d
0x1800025f7  pop     r14
0x1800025f9  pop     rdi
0x1800025fa  pop     rsi
0x1800025fb  pop     rbx
0x1800025fc  retn
```
