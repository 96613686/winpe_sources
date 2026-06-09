# NatDeleteAddressPool

- ea: `0x14001379c`
- end: `0x1400138f6`
- name: `NatDeleteAddressPool`
- size: `346`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x14000d50c`
- `0x1400128ec`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x14001379c`
- `0x1400138fc`
- `0x14001d7ac`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400137ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001382d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400137ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001382d`

## pseudocode

```c
__int64 __fastcall NatDeleteAddressPool(__int64 a1)
{
  __int64 i; // rbx
  void *v3; // rcx
  void *v4; // rcx
  __int64 *j; // rbx
  __int64 *v6; // rdx
  _QWORD **v7; // rbx
  _QWORD *v8; // rdx
  _QWORD *v9; // rax
  __int64 v10; // rdx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 80, WPP_96cec5cc952234920ba0014d840adb44_Traceguids);
  }
  for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 132); i = (unsigned int)(i + 1) )
  {
    v3 = *(void **)(*(_QWORD *)(a1 + 136) + 24 * i + 16);
    if ( v3 )
      ExFreePoolWithTag(v3, 0);
  }
  v4 = *(void **)(a1 + 136);
  *(_DWORD *)(a1 + 132) = 0;
  if ( v4 )
    ExFreePoolWithTag(v4, 0);
  *(_QWORD *)(a1 + 136) = 0;
  for ( j = *(__int64 **)(a1 + 168); j != (__int64 *)(a1 + 168); j = (__int64 *)*j )
  {
    if ( (j[6] & 2) != 0 )
    {
      v6 = j;
      j = (__int64 *)j[1];
      NatDeleteTicket(a1, v6);
    }
  }
  v7 = (_QWORD **)(a1 + 152);
  while ( 1 )
  {
    v8 = *v7;
    if ( *v7 == v7 )
      break;
    if ( (_QWORD **)v8[1] != v7 || (v9 = (_QWORD *)*v8, *(_QWORD **)(*v8 + 8LL) != v8) )
      __fastfail(3u);
    *v7 = v9;
    v10 = (__int64)(v8 - 3);
    v9[1] = v7;
    *(_DWORD *)(v10 + 72) |= 0x80000000;
    NatDereferenceAddressPoolEntry(a1, v10);
  }
  *(_QWORD *)(a1 + 144) = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 81, WPP_96cec5cc952234920ba0014d840adb44_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x14001379c  push    rbx
0x14001379e  push    rsi
0x14001379f  push    rdi
0x1400137a0  push    r14
0x1400137a2  sub     rsp, 28h
0x1400137a6  mov     rdi, rcx
0x1400137a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400137b0  lea     r14, WPP_GLOBAL_Control
0x1400137b7  cmp     rcx, r14
0x1400137ba  jz      short loc_1400137DE
0x1400137bc  mov     eax, [rcx+2Ch]
0x1400137bf  test    al, 1
0x1400137c1  jz      short loc_1400137DE
0x1400137c3  cmp     byte ptr [rcx+29h], 6
0x1400137c7  jb      short loc_1400137DE
0x1400137c9  mov     rcx, [rcx+18h]
0x1400137cd  lea     r8, WPP_96cec5cc952234920ba0014d840adb44_Traceguids
0x1400137d4  mov     edx, 50h ; 'P'
0x1400137d9  call    WPP_SF_
0x1400137de  xor     ebx, ebx
0x1400137e0  cmp     [rdi+84h], ebx
0x1400137e6  jbe     short loc_140013815
0x1400137e8  mov     rax, [rdi+88h]
0x1400137ef  lea     rcx, [rbx+rbx*2]
0x1400137f3  mov     rcx, [rax+rcx*8+10h]; P
0x1400137f8  test    rcx, rcx
0x1400137fb  jz      short loc_14001380B
0x1400137fd  xor     edx, edx; Tag
0x1400137ff  call    cs:__imp_ExFreePoolWithTag
0x140013806  nop     dword ptr [rax+rax+00h]
0x14001380b  inc     ebx
0x14001380d  cmp     ebx, [rdi+84h]
0x140013813  jb      short loc_1400137E8
0x140013815  mov     rcx, [rdi+88h]; P
0x14001381c  mov     dword ptr [rdi+84h], 0
0x140013826  test    rcx, rcx
0x140013829  jz      short loc_140013839
0x14001382b  xor     edx, edx; Tag
0x14001382d  call    cs:__imp_ExFreePoolWithTag
0x140013834  nop     dword ptr [rax+rax+00h]
0x140013839  lea     rsi, [rdi+0A8h]
0x140013840  mov     qword ptr [rdi+88h], 0
0x14001384b  mov     rbx, [rsi]
0x14001384e  jmp     short loc_140013869
0x140013850  mov     eax, [rbx+30h]
0x140013853  test    al, 2
0x140013855  jz      short loc_140013866
0x140013857  mov     rdx, rbx
0x14001385a  mov     rcx, rdi
0x14001385d  mov     rbx, [rbx+8]
0x140013861  call    NatDeleteTicket
0x140013866  mov     rbx, [rbx]
0x140013869  cmp     rbx, rsi
0x14001386c  jnz     short loc_140013850
0x14001386e  lea     rbx, [rdi+98h]
0x140013875  mov     rdx, [rbx]
0x140013878  cmp     rdx, rbx
0x14001387b  jz      short loc_1400138AD
0x14001387d  cmp     [rdx+8], rbx
0x140013881  jnz     short loc_1400138A6
0x140013883  mov     rax, [rdx]
0x140013886  cmp     [rax+8], rdx
0x14001388a  jnz     short loc_1400138A6
0x14001388c  mov     [rbx], rax
0x14001388f  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140013893  mov     [rax+8], rbx
0x140013897  mov     rcx, rdi
0x14001389a  bts     dword ptr [rdx+48h], 1Fh
0x14001389f  call    NatDereferenceAddressPoolEntry
0x1400138a4  jmp     short loc_140013875
0x1400138a6  mov     ecx, 3
0x1400138ab  int     29h; Win8: RtlFailFast(ecx)
0x1400138ad  mov     qword ptr [rdi+90h], 0
0x1400138b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400138bf  cmp     rcx, r14
0x1400138c2  jz      short loc_1400138E9
0x1400138c4  mov     eax, [rcx+2Ch]
0x1400138c7  test    al, 1
0x1400138c9  jz      short loc_1400138E9
0x1400138cb  cmp     byte ptr [rcx+29h], 6
0x1400138cf  jb      short loc_1400138E9
0x1400138d1  mov     rcx, [rcx+18h]
0x1400138d5  lea     r8, WPP_96cec5cc952234920ba0014d840adb44_Traceguids
0x1400138dc  mov     edx, 51h ; 'Q'
0x1400138e1  xor     r9d, r9d
0x1400138e4  call    WPP_SF_d
0x1400138e9  xor     eax, eax
0x1400138eb  add     rsp, 28h
0x1400138ef  pop     r14
0x1400138f1  pop     rdi
0x1400138f2  pop     rsi
0x1400138f3  pop     rbx
0x1400138f4  retn
```
