# NsiCliGetLinkSpeedFromInterfaceIpAddress

- ea: `0x1400072fc`
- end: `0x140007399`
- name: `NsiCliGetLinkSpeedFromInterfaceIpAddress`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140014da0`

## callees

- `0x140007274`
- `0x1400072fc`

## import_xrefs

- `NETIO!FreeMibTable` at `0x14000737a`
- `NETIO!FreeMibTable` at `0x14000737a`
- `NETIO!GetUnicastIpAddressTable` at `0x140007328`
- `NETIO!GetUnicastIpAddressTable` at `0x140007328`

## pseudocode

```c
__int64 __fastcall NsiCliGetLinkSpeedFromInterfaceIpAddress(int a1, _DWORD *a2)
{
  NTSTATUS UnicastIpAddressTable; // eax
  PVOID v5; // rcx
  unsigned int v6; // ebx
  __int64 i; // r8
  unsigned int InterfaceSpeed; // eax
  PVOID Memory; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  Memory = 0;
  UnicastIpAddressTable = GetUnicastIpAddressTable(2u, (PMIB_UNICASTIPADDRESS_TABLE *)&Memory);
  v5 = Memory;
  v6 = UnicastIpAddressTable;
  if ( UnicastIpAddressTable >= 0 )
  {
    v6 = -1073741275;
    for ( i = 0; (unsigned int)i < *(_DWORD *)Memory; i = (unsigned int)(i + 1) )
    {
      if ( *((_DWORD *)Memory + 20 * i + 3) == a1 )
      {
        InterfaceSpeed = NsiCliGetInterfaceSpeed(*((unsigned int *)Memory + 20 * i + 12), a2);
        v5 = Memory;
        v6 = InterfaceSpeed;
        break;
      }
    }
  }
  if ( v5 )
    FreeMibTable(v5);
  return v6;
}

```

## disassembly

```asm
0x1400072fc  mov     rax, rsp
0x1400072ff  mov     [rax+8], rbx
0x140007303  mov     [rax+18h], rsi
0x140007307  push    rdi
0x140007308  sub     rsp, 20h
0x14000730c  mov     rdi, rdx
0x14000730f  mov     dword ptr [rdx], 0
0x140007315  mov     esi, ecx
0x140007317  mov     qword ptr [rax+10h], 0
0x14000731f  mov     ecx, 2; Family
0x140007324  lea     rdx, [rax+10h]; Table
0x140007328  call    cs:__imp_GetUnicastIpAddressTable
0x14000732f  nop     dword ptr [rax+rax+00h]
0x140007334  mov     rcx, [rsp+28h+Memory]
0x140007339  mov     ebx, eax
0x14000733b  test    eax, eax
0x14000733d  js      short loc_140007375
0x14000733f  mov     edx, [rcx]
0x140007341  mov     ebx, 0C0000225h
0x140007346  xor     r8d, r8d
0x140007349  cmp     r8d, edx
0x14000734c  jnb     short loc_140007375
0x14000734e  lea     r9, [r8+r8*4]
0x140007352  add     r9, r9
0x140007355  cmp     [rcx+r9*8+0Ch], esi
0x14000735a  jz      short loc_140007361
0x14000735c  inc     r8d
0x14000735f  jmp     short loc_140007349
0x140007361  mov     ecx, [rcx+r9*8+30h]
0x140007366  mov     rdx, rdi
0x140007369  call    NsiCliGetInterfaceSpeed
0x14000736e  mov     rcx, [rsp+28h+Memory]; Memory
0x140007373  mov     ebx, eax
0x140007375  test    rcx, rcx
0x140007378  jz      short loc_140007386
0x14000737a  call    cs:__imp_FreeMibTable
0x140007381  nop     dword ptr [rax+rax+00h]
0x140007386  mov     rsi, [rsp+28h+arg_10]
0x14000738b  mov     eax, ebx
0x14000738d  mov     rbx, [rsp+28h+arg_0]
0x140007392  add     rsp, 20h
0x140007396  pop     rdi
0x140007397  retn
```
