# DiskFlushAsyncComplete

- ea: `0x140002720`
- end: `0x1400028a9`
- name: `DiskFlushAsyncComplete`
- size: `393`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140002720`
- `0x14000420c`
- `0x14000431c`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14000280d`
- `ntoskrnl!IofCallDriver` at `0x14000280d`

## pseudocode

```c
__int64 __fastcall DiskFlushAsyncComplete(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rsi
  __int64 v5; // rbx
  __int64 v6; // rbp
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v11; // rax

  v3 = *(_QWORD *)(a1 + 64);
  v5 = *(_QWORD *)(v3 + 96);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_0d021951613e35be7880fae860fb7f50_Traceguids, a1, a2);
  }
  v6 = *(int *)(a2 + 48);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, a2, a3, *(unsigned __int8 *)(v5 + 163));
  }
  if ( *(_BYTE *)(*(_QWORD *)(v3 + 528) + 30LL) == 1 )
  {
    *(_DWORD *)(v5 + 180) = 8;
    *(_DWORD *)(v5 + 216) = 0;
    *(_DWORD *)(v5 + 280) = 0;
    v7 = *(_QWORD *)(v5 + 128);
    *(_DWORD *)(v5 + 184) |= 0x20000000u;
    *(_QWORD *)(v5 + 240) = v7;
    *(_BYTE *)(v5 + 163) = 0;
  }
  else
  {
    *(_BYTE *)(v5 + 162) = 8;
    *(_BYTE *)(v5 + 170) = 0;
    v11 = *(_QWORD *)(v5 + 128);
    *(_DWORD *)(v5 + 172) |= 0x20000000u;
    *(_QWORD *)(v5 + 208) = v11;
    *(_WORD *)(v5 + 163) = 0;
    *(_QWORD *)(v5 + 192) = 0;
    *(_BYTE *)(v5 + 171) = 0;
  }
  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v5 + 128) + 184LL) + 32LL) = 0;
  v8 = *(_QWORD *)(*(_QWORD *)(v5 + 128) + 184LL);
  *(_BYTE *)(v8 - 72) = 15;
  *(_QWORD *)(v8 - 64) = v5 + 160;
  v9 = *(_QWORD *)(*(_QWORD *)(v5 + 128) + 184LL);
  *(_QWORD *)(v9 - 16) = DiskFlushComplete;
  *(_QWORD *)(v9 - 8) = v6;
  *(_BYTE *)(v9 - 69) = -32;
  IofCallDriver(*(PDEVICE_OBJECT *)(v3 + 16), *(PIRP *)(v5 + 128));
  return 3221225494LL;
}

```

## disassembly

```asm
0x140002720  push    rbx
0x140002722  push    rbp
0x140002723  push    rsi
0x140002724  push    rdi
0x140002725  push    r14
0x140002727  sub     rsp, 30h
0x14000272b  mov     rsi, [rcx+40h]
0x14000272f  mov     rdi, rdx
0x140002732  mov     r9, rcx
0x140002735  mov     rbx, [rsi+60h]
0x140002739  mov     rcx, cs:WPP_GLOBAL_Control
0x140002740  lea     r14, WPP_GLOBAL_Control
0x140002747  cmp     rcx, r14
0x14000274a  jz      short loc_140002757
0x14000274c  mov     eax, [rcx+2Ch]
0x14000274f  test    al, 1
0x140002751  jnz     loc_140002880
0x140002757  movsxd  rbp, dword ptr [rdi+30h]
0x14000275b  lea     rdi, [rbx+0A0h]
0x140002762  mov     rcx, cs:WPP_GLOBAL_Control
0x140002769  cmp     rcx, r14
0x14000276c  jnz     loc_140002856
0x140002772  mov     rax, [rsi+210h]
0x140002779  xor     ecx, ecx
0x14000277b  cmp     byte ptr [rax+1Eh], 1
0x14000277f  jnz     loc_14000282A
0x140002785  mov     dword ptr [rbx+0B4h], 8
0x14000278f  mov     [rbx+0D8h], ecx
0x140002795  mov     [rbx+118h], ecx
0x14000279b  mov     rax, [rbx+80h]
0x1400027a2  or      dword ptr [rbx+0B8h], 20000000h
0x1400027ac  mov     [rbx+0F0h], rax
0x1400027b3  mov     [rbx+0A3h], cl
0x1400027b9  mov     rax, [rbx+80h]
0x1400027c0  mov     rdx, [rax+0B8h]
0x1400027c7  mov     [rdx+20h], rcx
0x1400027cb  mov     rax, [rbx+80h]
0x1400027d2  mov     rdx, [rax+0B8h]
0x1400027d9  mov     byte ptr [rdx-48h], 0Fh
0x1400027dd  mov     [rdx-40h], rdi
0x1400027e1  mov     rax, [rbx+80h]
0x1400027e8  mov     rdx, [rax+0B8h]
0x1400027ef  lea     rax, DiskFlushComplete
0x1400027f6  mov     [rdx-10h], rax
0x1400027fa  mov     [rdx-8], rbp
0x1400027fe  mov     byte ptr [rdx-45h], 0E0h
0x140002802  mov     rdx, [rbx+80h]; Irp
0x140002809  mov     rcx, [rsi+10h]; DeviceObject
0x14000280d  call    cs:__imp_IofCallDriver
0x140002814  nop     dword ptr [rax+rax+00h]
0x140002819  mov     eax, 0C0000016h
0x14000281e  add     rsp, 30h
0x140002822  pop     r14
0x140002824  pop     rdi
0x140002825  pop     rsi
0x140002826  pop     rbp
0x140002827  pop     rbx
0x140002828  retn
0x14000282a  mov     byte ptr [rdi+2], 8
0x14000282e  mov     byte ptr [rdi+0Ah], 0
0x140002832  mov     rax, [rbx+80h]
0x140002839  or      dword ptr [rdi+0Ch], 20000000h
0x140002840  mov     [rdi+30h], rax
0x140002844  mov     word ptr [rdi+3], 0
0x14000284a  mov     [rdi+20h], rcx
0x14000284e  mov     [rdi+0Bh], cl
0x140002851  jmp     loc_1400027B9
0x140002856  test    dword ptr [rcx+2Ch], 20000h
0x14000285d  jz      loc_140002772
0x140002863  cmp     byte ptr [rcx+29h], 5
0x140002867  jb      loc_140002772
0x14000286d  movzx   r9d, byte ptr [rdi+3]
0x140002872  mov     rcx, [rcx+18h]
0x140002876  call    WPP_SF_d
0x14000287b  jmp     loc_140002772
0x140002880  cmp     byte ptr [rcx+29h], 5
0x140002884  jb      loc_140002757
0x14000288a  mov     rcx, [rcx+18h]
0x14000288e  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x140002895  mov     edx, 24h ; '$'
0x14000289a  mov     [rsp+58h+var_38], rdi
0x14000289f  call    WPP_SF_qq
0x1400028a4  jmp     loc_140002757
```
