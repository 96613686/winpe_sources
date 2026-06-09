# ClasspWritePnPResultEvent

- ea: `0x1400180f4`
- end: `0x14001817a`
- name: `ClasspWritePnPResultEvent`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140005190`

## callees

- `0x1400180f4`
- `0x14002249c`
- `0x140026804`
- `0x14003c0d4`

## pseudocode

```c
NTSTATUS __fastcall ClasspWritePnPResultEvent(const GUID *a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rbp
  __int64 v6; // rdi
  NTSTATUS result; // eax
  int v8; // ecx

  v4 = *(_QWORD *)(a2 + 64);
  v6 = *(_QWORD *)(a3 + 184);
  if ( *(int *)(a3 + 48) < 0 )
    result = (unsigned int)ClasspWritePnPFailureEvent((int)a1, a2, a3);
  if ( *(_BYTE *)(v6 + 1) != 7 || *(_DWORD *)(v6 + 8) )
  {
    if ( (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x10) != 0 )
      return McTemplateK0qpd_EtwWriteTransfer(
               (__int64)a1,
               (const EVENT_DESCRIPTOR *)EventPnpRequestComplete,
               a1,
               *(_DWORD *)(v4 + 588),
               a3,
               *(_DWORD *)(a3 + 48));
  }
  else if ( (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x20) != 0 )
  {
    if ( a3 == -56 )
      v8 = 0;
    else
      v8 = *(_DWORD *)(a3 + 56);
    return McTemplateK0qpqd_EtwWriteTransfer(v8, a2, (_DWORD)a1, *(_DWORD *)(v4 + 588), a3, v8, *(_DWORD *)(a3 + 48));
  }
  return result;
}

```

## disassembly

```asm
0x1400180f4  push    rbx
0x1400180f6  push    rbp
0x1400180f7  push    rsi
0x1400180f8  push    rdi
0x1400180f9  sub     rsp, 48h
0x1400180fd  cmp     dword ptr [r8+30h], 0
0x140018102  mov     rbx, r8
0x140018105  mov     rbp, [rdx+40h]
0x140018109  mov     rsi, rcx
0x14001810c  mov     rdi, [r8+0B8h]
0x140018113  jge     short loc_14001811A
0x140018115  call    ClasspWritePnPFailureEvent
0x14001811a  cmp     byte ptr [rdi+1], 7
0x14001811e  jz      short loc_140018133
0x140018120  test    byte ptr cs:WPP_MAIN_CB.Queue+3Ah, 10h
0x140018127  jnz     short loc_140018156
0x140018129  add     rsp, 48h
0x14001812d  pop     rdi
0x14001812e  pop     rsi
0x14001812f  pop     rbp
0x140018130  pop     rbx
0x140018131  retn
0x140018133  cmp     dword ptr [rdi+8], 0
0x140018137  jnz     short loc_140018120
0x140018139  test    byte ptr cs:WPP_MAIN_CB.Queue+3Ah, 20h
0x140018140  jz      short loc_140018129
0x140018142  lea     rax, [rbx+38h]
0x140018146  test    rax, rax
0x140018149  jz      loc_1400411C2
0x14001814f  mov     ecx, [rax]
0x140018151  jmp     loc_1400411C4
0x140018156  mov     eax, [rbx+30h]
0x140018159  lea     rdx, EventPnpRequestComplete
0x140018160  mov     r9d, [rbp+24Ch]
0x140018167  mov     r8, rsi
0x14001816a  mov     [rsp+68h+var_40], eax
0x14001816e  mov     [rsp+68h+var_48], rbx
0x140018173  call    McTemplateK0qpd_EtwWriteTransfer
0x140018178  jmp     short loc_140018129
0x1400411c2  xor     ecx, ecx
0x1400411c4  mov     eax, [rbx+30h]
0x1400411c7  mov     r8, rsi
0x1400411ca  mov     r9d, [rbp+24Ch]
0x1400411d1  mov     [rsp+68h+var_38], eax
0x1400411d5  mov     [rsp+68h+var_40], ecx
0x1400411d9  mov     [rsp+68h+var_48], rbx
0x1400411de  call    McTemplateK0qpqd_EtwWriteTransfer
0x1400411e3  nop
0x1400411e4  jmp     loc_140018129
```
