# lldpDetachAllPortsFromBinding

- ea: `0x140012640`
- end: `0x1400126fc`
- name: `lldpDetachAllPortsFromBinding`
- size: `188`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140012000`
- `0x1400125f0`
- `0x140012790`

## callees

- `0x140003d80`
- `0x140004510`
- `0x140010998`
- `0x140010aec`
- `0x140012640`

## pseudocode

```c
void __fastcall lldpDetachAllPortsFromBinding(__int64 a1)
{
  __int64 v1; // rbx
  __int64 *v2; // rdi
  __int64 v3; // rax
  __int64 *v4; // rcx
  __int32 v5; // ecx
  __int32 v6; // ecx

  v1 = *(_QWORD *)(a1 + 120);
  v2 = (__int64 *)(a1 + 120);
  if ( v1 )
  {
    v3 = *(_QWORD *)(a1 + 120);
    do
    {
      v4 = v2;
      while ( v3 != v1 )
      {
        v4 = (__int64 *)(v3 + 40);
        v3 = *(_QWORD *)(v3 + 32);
        if ( !v3 )
          goto LABEL_8;
      }
      *v4 = *(_QWORD *)(v1 + 40);
LABEL_8:
      lldpDetachPortFromBinding(v1);
      v5 = _InterlockedExchange((volatile __int32 *)(v1 + 52), 7) - 3;
      if ( !v5 || (v6 = v5 - 1) == 0 || (unsigned int)(v6 - 1) <= 1 )
        lldpQueueChangeNotificationEx((PVOID)v1, 0, 0x80000000);
      if ( *(_BYTE *)(v1 + 150) )
      {
        lldpRemovePortFromDriver((struct _LIST_ENTRY *)v1);
        *(_BYTE *)(v1 + 150) = 0;
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 48), 0xFFFFFFFF) == 1 )
        lldpDeletePort((char *)v1);
      v1 = *v2;
      v3 = *v2;
    }
    while ( *v2 );
  }
}

```

## disassembly

```asm
0x140012640  mov     [rsp+arg_0], rbx
0x140012645  push    rdi
0x140012646  sub     rsp, 20h
0x14001264a  mov     rbx, [rcx+78h]
0x14001264e  lea     rdi, [rcx+78h]
0x140012652  test    rbx, rbx
0x140012655  jz      loc_1400126F0
0x14001265b  mov     rax, rbx
0x14001265e  xchg    ax, ax
0x140012660  mov     rcx, rdi
0x140012663  cmp     rax, rbx
0x140012666  jz      short loc_140012677
0x140012668  lea     rcx, [rax+28h]
0x14001266c  mov     rax, [rax+20h]
0x140012670  test    rax, rax
0x140012673  jnz     short loc_140012663
0x140012675  jmp     short loc_14001267E
0x140012677  mov     rax, [rbx+28h]
0x14001267b  mov     [rcx], rax
0x14001267e  mov     rcx, rbx
0x140012681  call    lldpDetachPortFromBinding
0x140012686  mov     ecx, 7
0x14001268b  xchg    ecx, [rbx+34h]
0x14001268e  sub     ecx, 3
0x140012691  jz      short loc_1400126A2
0x140012693  sub     ecx, 1
0x140012696  jz      short loc_1400126A2
0x140012698  sub     ecx, 1
0x14001269b  jz      short loc_1400126A2
0x14001269d  cmp     ecx, 1
0x1400126a0  jnz     short loc_1400126B2
0x1400126a2  xor     edx, edx
0x1400126a4  mov     r8d, 80000000h
0x1400126aa  mov     rcx, rbx; Context
0x1400126ad  call    lldpQueueChangeNotificationEx
0x1400126b2  cmp     byte ptr [rbx+96h], 0
0x1400126b9  jz      short loc_1400126CA
0x1400126bb  mov     rcx, rbx
0x1400126be  call    lldpRemovePortFromDriver
0x1400126c3  mov     byte ptr [rbx+96h], 0
0x1400126ca  mov     eax, 0FFFFFFFFh
0x1400126cf  lock xadd [rbx+30h], eax
0x1400126d4  cmp     eax, 1
0x1400126d7  jnz     short loc_1400126E1
0x1400126d9  mov     rcx, rbx; Context
0x1400126dc  call    lldpDeletePort
0x1400126e1  mov     rbx, [rdi]
0x1400126e4  mov     rax, rbx
0x1400126e7  test    rbx, rbx
0x1400126ea  jnz     loc_140012660
0x1400126f0  mov     rbx, [rsp+28h+arg_0]
0x1400126f5  add     rsp, 20h
0x1400126f9  pop     rdi
0x1400126fa  retn
```
