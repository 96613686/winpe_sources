# NsiCliDeleteHostRouteHelper

- ea: `0x1400070f0`
- end: `0x1400071ba`
- name: `NsiCliDeleteHostRouteHelper`
- size: `202`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400070cc`
- `0x1400071c0`

## callees

- `0x140006ea0`
- `0x1400070f0`

## import_xrefs

- `NETIO!FreeMibTable` at `0x14000719b`
- `NETIO!FreeMibTable` at `0x14000719b`
- `NETIO!DeleteIpForwardEntry2` at `0x140007179`
- `NETIO!DeleteIpForwardEntry2` at `0x140007179`
- `NETIO!GetIpForwardTable2` at `0x140007112`
- `NETIO!GetIpForwardTable2` at `0x140007112`

## pseudocode

```c
__int64 __fastcall NsiCliDeleteHostRouteHelper(ADDRESS_FAMILY a1, __int64 a2)
{
  NTSTATUS IpForwardTable2; // eax
  char *v5; // r9
  unsigned int v6; // ebx
  unsigned int v7; // ebx
  unsigned int i; // r10d
  char *v9; // r11
  __int64 v10; // rdx
  const MIB_IPFORWARD_ROW2 *v11; // r11
  NTSTATUS v12; // eax
  PVOID Memory; // [rsp+40h] [rbp+18h] BYREF

  Memory = 0;
  IpForwardTable2 = GetIpForwardTable2(a1, (PMIB_IPFORWARD_TABLE2 *)&Memory);
  v5 = (char *)Memory;
  v6 = IpForwardTable2;
  if ( IpForwardTable2 >= 0 )
  {
    v7 = *(_DWORD *)Memory;
    for ( i = 0; i < v7; ++i )
    {
      v9 = &v5[104 * i + 8];
      if ( *((_DWORD *)v9 + 22) == 3 )
      {
        v10 = 20;
        if ( *((_WORD *)v9 + 6) != 23 )
          v10 = 16;
        if ( (unsigned __int8)INET_ADDR_EQUAL(a1, &v9[v10], a2) )
        {
          if ( v11 )
          {
            v12 = DeleteIpForwardEntry2(v11);
            v5 = (char *)Memory;
            v6 = v12;
            goto LABEL_12;
          }
          break;
        }
      }
    }
    v6 = -1073741275;
  }
LABEL_12:
  if ( v5 )
    FreeMibTable(v5);
  return v6;
}

```

## disassembly

```asm
0x1400070f0  mov     rax, rsp
0x1400070f3  mov     [rax+8], rbx
0x1400070f7  mov     [rax+10h], rsi
0x1400070fb  push    rdi
0x1400070fc  sub     rsp, 20h
0x140007100  mov     rsi, rdx
0x140007103  mov     qword ptr [rax+18h], 0
0x14000710b  lea     rdx, [rax+18h]; Table
0x14000710f  movzx   edi, cx
0x140007112  call    cs:__imp_GetIpForwardTable2
0x140007119  nop     dword ptr [rax+rax+00h]
0x14000711e  mov     r9, [rsp+28h+Memory]
0x140007123  mov     ebx, eax
0x140007125  test    eax, eax
0x140007127  js      short loc_140007193
0x140007129  mov     ebx, [r9]
0x14000712c  xor     r10d, r10d
0x14000712f  cmp     r10d, ebx
0x140007132  jnb     short loc_14000718E
0x140007134  mov     eax, r10d
0x140007137  imul    r11, rax, 68h ; 'h'
0x14000713b  add     r11, 8
0x14000713f  add     r11, r9
0x140007142  cmp     dword ptr [r11+58h], 3
0x140007147  jnz     short loc_14000716C
0x140007149  cmp     word ptr [r11+0Ch], 17h
0x14000714f  mov     edx, 14h
0x140007154  mov     r8, rsi
0x140007157  movzx   ecx, di
0x14000715a  lea     eax, [rdx-4]
0x14000715d  cmovnz  edx, eax
0x140007160  add     rdx, r11
0x140007163  call    INET_ADDR_EQUAL
0x140007168  test    al, al
0x14000716a  jnz     short loc_140007171
0x14000716c  inc     r10d
0x14000716f  jmp     short loc_14000712F
0x140007171  test    r11, r11
0x140007174  jz      short loc_14000718E
0x140007176  mov     rcx, r11; Row
0x140007179  call    cs:__imp_DeleteIpForwardEntry2
0x140007180  nop     dword ptr [rax+rax+00h]
0x140007185  mov     r9, [rsp+28h+Memory]
0x14000718a  mov     ebx, eax
0x14000718c  jmp     short loc_140007193
0x14000718e  mov     ebx, 0C0000225h
0x140007193  test    r9, r9
0x140007196  jz      short loc_1400071A7
0x140007198  mov     rcx, r9; Memory
0x14000719b  call    cs:__imp_FreeMibTable
0x1400071a2  nop     dword ptr [rax+rax+00h]
0x1400071a7  mov     rsi, [rsp+28h+arg_8]
0x1400071ac  mov     eax, ebx
0x1400071ae  mov     rbx, [rsp+28h+arg_0]
0x1400071b3  add     rsp, 20h
0x1400071b7  pop     rdi
0x1400071b8  retn
```
