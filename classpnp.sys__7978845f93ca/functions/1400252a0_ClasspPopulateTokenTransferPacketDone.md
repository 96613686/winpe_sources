# ClasspPopulateTokenTransferPacketDone

- ea: `0x1400252a0`
- end: `0x140025332`
- name: `ClasspPopulateTokenTransferPacketDone`
- size: `146`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1400206f8`
- `0x140023d08`
- `0x1400252a0`
- `0x1400270fc`

## pseudocode

```c
NTSTATUS __fastcall ClasspPopulateTokenTransferPacketDone(_QWORD *P, __int64 a2, __int64 a3)
{
  char *v3; // rax
  __int64 v5; // rdx
  NTSTATUS v6; // edi

  v3 = (char *)P[28];
  v5 = P[29];
  P[29] = 0;
  if ( !v3 )
    v3 = (char *)(P + 2);
  v6 = *((_DWORD *)v3 + 12);
  if ( v6 >= 0 )
    return ClasspReceivePopulateTokenInformation(P);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qDDq(WPP_GLOBAL_Control->AttachedDevice, v5, a3, *P, *((_DWORD *)P + 63), v6, v5);
  }
  return ClasspCompleteOffloadRead((struct _DEVICE_OBJECT **)P, v6);
}

```

## disassembly

```asm
0x1400252a0  mov     [rsp+arg_0], rbx
0x1400252a5  push    rdi
0x1400252a6  sub     rsp, 40h
0x1400252aa  mov     rax, [rcx+0E0h]
0x1400252b1  mov     rbx, rcx
0x1400252b4  mov     rdx, [rcx+0E8h]
0x1400252bb  mov     qword ptr [rcx+0E8h], 0
0x1400252c6  test    rax, rax
0x1400252c9  jnz     short loc_1400252CF
0x1400252cb  lea     rax, [rcx+10h]
0x1400252cf  mov     edi, [rax+30h]
0x1400252d2  test    edi, edi
0x1400252d4  jns     short loc_140025321
0x1400252d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400252dd  lea     rax, WPP_GLOBAL_Control
0x1400252e4  cmp     rcx, rax
0x1400252e7  jz      short loc_140025315
0x1400252e9  mov     eax, [rcx+2Ch]
0x1400252ec  test    al, 10h
0x1400252ee  jz      short loc_140025315
0x1400252f0  cmp     byte ptr [rcx+29h], 2
0x1400252f4  jb      short loc_140025315
0x1400252f6  mov     eax, [rbx+0FCh]
0x1400252fc  mov     r9, [rbx]
0x1400252ff  mov     rcx, [rcx+18h]
0x140025303  mov     [rsp+48h+var_18], rdx
0x140025308  mov     [rsp+48h+var_20], edi
0x14002530c  mov     [rsp+48h+var_28], eax
0x140025310  call    WPP_SF_qDDq
0x140025315  mov     edx, edi
0x140025317  mov     rcx, rbx; P
0x14002531a  call    ClasspCompleteOffloadRead
0x14002531f  jmp     short loc_140025326
0x140025321  call    ClasspReceivePopulateTokenInformation
0x140025326  mov     rbx, [rsp+48h+arg_0]
0x14002532b  add     rsp, 40h
0x14002532f  pop     rdi
0x140025330  retn
```
