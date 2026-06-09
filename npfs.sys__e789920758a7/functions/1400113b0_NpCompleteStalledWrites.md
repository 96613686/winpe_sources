# NpCompleteStalledWrites

- ea: `0x1400113b0`
- end: `0x140011481`
- name: `NpCompleteStalledWrites`
- size: `209`
- prototype: `__int64 __fastcall(__int64 **, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001520`
- `0x14000e1b0`
- `0x140010310`

## callees

- `0x1400113b0`

## pseudocode

```c
__int64 __fastcall NpCompleteStalledWrites(__int64 **a1, __int64 a2)
{
  unsigned int v3; // r10d
  int v5; // ecx
  __int64 **v6; // rax
  __int64 *v7; // r9
  __int64 result; // rax
  unsigned int v9; // ebx
  unsigned int v10; // r11d
  unsigned int v11; // edx
  __int64 v12; // rcx
  _QWORD *v13; // rdx

  v3 = *((_DWORD *)a1 + 7) - *((_DWORD *)a1 + 8);
  v5 = *((_DWORD *)a1 + 9);
  v6 = (__int64 **)*a1;
  if ( *a1 != (__int64 *)a1 )
  {
    while ( v3 )
    {
      if ( !*((_DWORD *)v6 + 8) )
      {
        v7 = v6[2];
        if ( v7 )
        {
          v9 = *((_DWORD *)v6 + 9);
          v10 = *((_DWORD *)v6 + 10) - v5;
          if ( v9 < v10 )
          {
            v11 = v3;
            if ( v10 - v9 <= v3 )
              v11 = v10 - v9;
            v3 -= v11;
            *((_DWORD *)v6 + 9) = v11 + v9;
            if ( v11 + v9 == v10 && _InterlockedExchange64(v7 + 13, 0) )
            {
              v12 = *((unsigned int *)v6 + 10);
              v6[2] = 0;
              v7[7] = v12;
              *((_DWORD *)v7 + 12) = 0;
              v13 = *(_QWORD **)(a2 + 8);
              if ( *v13 != a2 )
                __fastfail(3u);
              v7[21] = a2;
              v7[22] = (__int64)v13;
              *v13 = v7 + 21;
              *(_QWORD *)(a2 + 8) = v7 + 21;
            }
          }
        }
      }
      v6 = (__int64 **)*v6;
      if ( v6 == a1 )
        break;
      v5 = 0;
    }
  }
  result = *((_DWORD *)a1 + 7) - v3;
  *((_DWORD *)a1 + 8) = result;
  return result;
}

```

## disassembly

```asm
0x1400113b0  mov     [rsp+arg_0], rbx
0x1400113b5  mov     [rsp+arg_8], rdi
0x1400113ba  mov     r10d, [rcx+1Ch]
0x1400113be  mov     r8, rcx
0x1400113c1  sub     r10d, [rcx+20h]
0x1400113c5  mov     rdi, rdx
0x1400113c8  mov     ecx, [rcx+24h]
0x1400113cb  mov     rax, [r8]
0x1400113ce  cmp     rax, r8
0x1400113d1  jz      short loc_1400113F3
0x1400113d3  test    r10d, r10d
0x1400113d6  jz      short loc_1400113F3
0x1400113d8  cmp     dword ptr [rax+20h], 0
0x1400113dc  jnz     short loc_1400113E7
0x1400113de  mov     r9, [rax+10h]
0x1400113e2  test    r9, r9
0x1400113e5  jnz     short loc_14001140A
0x1400113e7  mov     rax, [rax]
0x1400113ea  cmp     rax, r8
0x1400113ed  jz      short loc_1400113F3
0x1400113ef  xor     ecx, ecx
0x1400113f1  jmp     short loc_1400113D3
0x1400113f3  mov     eax, [r8+1Ch]
0x1400113f7  mov     rbx, [rsp+arg_0]
0x1400113fc  sub     eax, r10d
0x1400113ff  mov     rdi, [rsp+arg_8]
0x140011404  mov     [r8+20h], eax
0x140011408  retn
0x14001140a  mov     r11d, [rax+28h]
0x14001140e  mov     ebx, [rax+24h]
0x140011411  sub     r11d, ecx
0x140011414  cmp     ebx, r11d
0x140011417  jnb     short loc_1400113E7
0x140011419  mov     edx, r10d
0x14001141c  mov     ecx, r11d
0x14001141f  sub     ecx, ebx
0x140011421  cmp     ecx, r10d
0x140011424  cmovbe  edx, ecx
0x140011427  sub     r10d, edx
0x14001142a  lea     ecx, [rdx+rbx]
0x14001142d  mov     [rax+24h], ecx
0x140011430  cmp     ecx, r11d
0x140011433  jnz     short loc_1400113E7
0x140011435  xor     ecx, ecx
0x140011437  xchg    rcx, [r9+68h]
0x14001143b  test    rcx, rcx
0x14001143e  jz      short loc_1400113E7
0x140011440  mov     ecx, [rax+28h]
0x140011443  mov     qword ptr [rax+10h], 0
0x14001144b  mov     [r9+38h], rcx
0x14001144f  mov     dword ptr [r9+30h], 0
0x140011457  mov     rdx, [rdi+8]
0x14001145b  cmp     [rdx], rdi
0x14001145e  jnz     short loc_14001147A
0x140011460  lea     rcx, [r9+0A8h]
0x140011467  mov     [rcx], rdi
0x14001146a  mov     [rcx+8], rdx
0x14001146e  mov     [rdx], rcx
0x140011471  mov     [rdi+8], rcx
0x140011475  jmp     loc_1400113E7
0x14001147a  mov     ecx, 3
0x14001147f  int     29h; Win8: RtlFailFast(ecx)
```
