# SendAdapterIndexCompartmentIdToMiniport

- ea: `0x14000ec48`
- end: `0x14000ed2f`
- name: `SendAdapterIndexCompartmentIdToMiniport`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000e400`

## callees

- `0x1400048c0`
- `0x14000ec48`
- `0x1400161f0`
- `0x140016700`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14000ecbd`
- `ntoskrnl!KeInitializeEvent` at `0x14000ecbd`

## pseudocode

```c
__int64 __fastcall SendAdapterIndexCompartmentIdToMiniport(__int64 a1, unsigned int a2, unsigned int a3)
{
  __int64 v3; // rbx
  unsigned __int64 v7; // [rsp+20h] [rbp-E0h] BYREF
  _OWORD v8[21]; // [rsp+30h] [rbp-D0h] BYREF

  v3 = *(_QWORD *)(a1 + 48);
  memset(v8, 0, 0x148u);
  v7 = 0;
  if ( *(_DWORD *)(*(_QWORD *)(v3 + 72) + 124LL) != 14 )
    return 0;
  v7 = __PAIR64__(a3, a2);
  *(_QWORD *)&v8[1] = 1;
  KeInitializeEvent((PRKEVENT)&v8[19], NotificationEvent, 0);
  *((_QWORD *)&v8[1] + 1) = *(_QWORD *)(v3 + 72);
  *((_QWORD *)&v8[5] + 1) = &v7;
  *(_QWORD *)&v8[3] = 0x100EC0196LL;
  LODWORD(v8[5]) = 67175044;
  LODWORD(v8[6]) = 8;
  *((_QWORD *)&v8[2] + 1) = *(_QWORD *)(v3 + 56);
  return NdisWanSubmitNdisRequest(*(_QWORD *)(v3 + 72), v8);
}

```

## disassembly

```asm
0x14000ec48  mov     [rsp-8+arg_18], rbx
0x14000ec4d  push    rbp
0x14000ec4e  push    rsi
0x14000ec4f  push    rdi
0x14000ec50  lea     rbp, [rsp-90h]
0x14000ec58  sub     rsp, 190h
0x14000ec5f  mov     rax, cs:__security_cookie
0x14000ec66  xor     rax, rsp
0x14000ec69  mov     [rbp+0A0h+var_20], rax
0x14000ec70  mov     rbx, [rcx+30h]
0x14000ec74  mov     esi, r8d
0x14000ec77  mov     edi, edx
0x14000ec79  lea     rcx, [rsp+1A0h+var_170]; void *
0x14000ec7e  xor     edx, edx; Val
0x14000ec80  mov     r8d, 148h; Size
0x14000ec86  call    memset
0x14000ec8b  mov     [rsp+1A0h+var_180], 0
0x14000ec94  mov     rax, [rbx+48h]
0x14000ec98  cmp     dword ptr [rax+7Ch], 0Eh
0x14000ec9c  jz      short loc_14000ECA2
0x14000ec9e  xor     eax, eax
0x14000eca0  jmp     short loc_14000ED0C
0x14000eca2  mov     dword ptr [rsp+1A0h+var_180], edi
0x14000eca6  lea     rcx, [rbp+0A0h+Event]; Event
0x14000ecaa  mov     edi, 1
0x14000ecaf  mov     dword ptr [rsp+1A0h+var_180+4], esi
0x14000ecb3  xor     r8d, r8d; State
0x14000ecb6  mov     [rsp+1A0h+var_160], rdi
0x14000ecbb  xor     edx, edx; Type
0x14000ecbd  call    cs:__imp_KeInitializeEvent
0x14000ecc4  nop     dword ptr [rax+rax+00h]
0x14000ecc9  mov     rax, [rbx+48h]
0x14000eccd  lea     rdx, [rsp+1A0h+var_170]
0x14000ecd2  mov     [rsp+1A0h+var_158], rax
0x14000ecd7  lea     rax, [rsp+1A0h+var_180]
0x14000ecdc  mov     [rbp+0A0h+var_118], rax
0x14000ece0  mov     [rsp+1A0h+var_140], 0EC0196h
0x14000ece8  mov     [rsp+1A0h+var_13C], edi
0x14000ecec  mov     [rbp+0A0h+var_120], 4010284h
0x14000ecf3  mov     [rbp+0A0h+var_110], 8
0x14000ecfa  mov     rax, [rbx+38h]
0x14000ecfe  mov     [rsp+1A0h+var_148], rax
0x14000ed03  mov     rcx, [rbx+48h]
0x14000ed07  call    NdisWanSubmitNdisRequest
0x14000ed0c  mov     rcx, [rbp+0A0h+var_20]
0x14000ed13  xor     rcx, rsp; StackCookie
0x14000ed16  call    __security_check_cookie
0x14000ed1b  mov     rbx, [rsp+1A0h+arg_18]
0x14000ed23  add     rsp, 190h
0x14000ed2a  pop     rdi
0x14000ed2b  pop     rsi
0x14000ed2c  pop     rbp
0x14000ed2d  retn
```
