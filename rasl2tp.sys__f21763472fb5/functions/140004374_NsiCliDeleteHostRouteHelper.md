# NsiCliDeleteHostRouteHelper

- ea: `0x140004374`
- end: `0x14000443e`
- name: `NsiCliDeleteHostRouteHelper`
- size: `202`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140004350`
- `0x140004444`

## callees

- `0x1400040f8`
- `0x140004374`

## import_xrefs

- `NETIO!FreeMibTable` at `0x14000441f`
- `NETIO!FreeMibTable` at `0x14000441f`
- `NETIO!DeleteIpForwardEntry2` at `0x1400043fd`
- `NETIO!DeleteIpForwardEntry2` at `0x1400043fd`
- `NETIO!GetIpForwardTable2` at `0x140004396`
- `NETIO!GetIpForwardTable2` at `0x140004396`

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
0x140004374  mov     rax, rsp
0x140004377  mov     [rax+8], rbx
0x14000437b  mov     [rax+10h], rsi
0x14000437f  push    rdi
0x140004380  sub     rsp, 20h
0x140004384  mov     rsi, rdx
0x140004387  mov     qword ptr [rax+18h], 0
0x14000438f  lea     rdx, [rax+18h]; Table
0x140004393  movzx   edi, cx
0x140004396  call    cs:__imp_GetIpForwardTable2
0x14000439d  nop     dword ptr [rax+rax+00h]
0x1400043a2  mov     r9, [rsp+28h+Memory]
0x1400043a7  mov     ebx, eax
0x1400043a9  test    eax, eax
0x1400043ab  js      short loc_140004417
0x1400043ad  mov     ebx, [r9]
0x1400043b0  xor     r10d, r10d
0x1400043b3  cmp     r10d, ebx
0x1400043b6  jnb     short loc_140004412
0x1400043b8  mov     eax, r10d
0x1400043bb  imul    r11, rax, 68h ; 'h'
0x1400043bf  add     r11, 8
0x1400043c3  add     r11, r9
0x1400043c6  cmp     dword ptr [r11+58h], 3
0x1400043cb  jnz     short loc_1400043F0
0x1400043cd  cmp     word ptr [r11+0Ch], 17h
0x1400043d3  mov     edx, 14h
0x1400043d8  mov     r8, rsi
0x1400043db  movzx   ecx, di
0x1400043de  lea     eax, [rdx-4]
0x1400043e1  cmovnz  edx, eax
0x1400043e4  add     rdx, r11
0x1400043e7  call    INET_ADDR_EQUAL
0x1400043ec  test    al, al
0x1400043ee  jnz     short loc_1400043F5
0x1400043f0  inc     r10d
0x1400043f3  jmp     short loc_1400043B3
0x1400043f5  test    r11, r11
0x1400043f8  jz      short loc_140004412
0x1400043fa  mov     rcx, r11; Row
0x1400043fd  call    cs:__imp_DeleteIpForwardEntry2
0x140004404  nop     dword ptr [rax+rax+00h]
0x140004409  mov     r9, [rsp+28h+Memory]
0x14000440e  mov     ebx, eax
0x140004410  jmp     short loc_140004417
0x140004412  mov     ebx, 0C0000225h
0x140004417  test    r9, r9
0x14000441a  jz      short loc_14000442B
0x14000441c  mov     rcx, r9; Memory
0x14000441f  call    cs:__imp_FreeMibTable
0x140004426  nop     dword ptr [rax+rax+00h]
0x14000442b  mov     rsi, [rsp+28h+arg_8]
0x140004430  mov     eax, ebx
0x140004432  mov     rbx, [rsp+28h+arg_0]
0x140004437  add     rsp, 20h
0x14000443b  pop     rdi
0x14000443c  retn
```
