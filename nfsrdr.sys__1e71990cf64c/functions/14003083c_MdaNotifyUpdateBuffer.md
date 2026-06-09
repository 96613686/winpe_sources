# MdaNotifyUpdateBuffer

- ea: `0x14003083c`
- end: `0x14003092b`
- name: `MdaNotifyUpdateBuffer`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14002fe10`

## callees

- `0x1400159cc`
- `0x14003083c`
- `0x14003adc0`

## pseudocode

```c
char __fastcall MdaNotifyUpdateBuffer(_DWORD *a1, int a2, const void **a3, const void **a4, int a5, int a6)
{
  __int64 v10; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_ddc2de19639338fa7e5ec9349090cc7f_Traceguids);
  *a1 = 0;
  a1[1] = a2;
  a1[2] = a6 - 12;
  v10 = 0;
  if ( *(_WORD *)a3 )
  {
    memmove(a1 + 3, a3[1], *(unsigned __int16 *)a3);
    *(_WORD *)((char *)a1 + *(unsigned __int16 *)a3 + 12) = 92;
    v10 = *(unsigned __int16 *)a3 + 2LL;
  }
  memmove((char *)a1 + v10 + 12, a4[1], *(unsigned __int16 *)a4);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_ddc2de19639338fa7e5ec9349090cc7f_Traceguids);
  return 1;
}

```

## disassembly

```asm
0x14003083c  push    rbx
0x14003083e  push    rsi
0x14003083f  push    rdi
0x140030840  push    r14
0x140030842  push    r15
0x140030844  sub     rsp, 30h
0x140030848  mov     r14, r9
0x14003084b  mov     rsi, r8
0x14003084e  mov     r15d, edx
0x140030851  mov     rbx, rcx
0x140030854  lea     rdi, WPP_GLOBAL_Control
0x14003085b  mov     rcx, cs:WPP_GLOBAL_Control
0x140030862  cmp     rcx, rdi
0x140030865  jz      short loc_140030886
0x140030867  test    dword ptr [rcx+2Ch], 80000h
0x14003086e  jz      short loc_140030886
0x140030870  mov     edx, 1Fh
0x140030875  lea     r8, WPP_ddc2de19639338fa7e5ec9349090cc7f_Traceguids
0x14003087c  mov     rcx, [rcx+18h]
0x140030880  call    WPP_SF_
0x140030885  nop
0x140030886  xor     edx, edx
0x140030888  mov     [rbx], edx
0x14003088a  mov     [rbx+4], r15d
0x14003088e  mov     eax, [rsp+58h+arg_28]
0x140030895  add     eax, 0FFFFFFF4h
0x140030898  mov     [rbx+8], eax
0x14003089b  movzx   ecx, word ptr [rsi]
0x14003089e  mov     eax, edx
0x1400308a0  test    cx, cx
0x1400308a3  jz      short loc_1400308C9
0x1400308a5  mov     r8d, ecx; Size
0x1400308a8  lea     rcx, [rbx+0Ch]; void *
0x1400308ac  mov     rdx, [rsi+8]; Src
0x1400308b0  call    memmove
0x1400308b5  movzx   eax, word ptr [rsi]
0x1400308b8  mov     ecx, 5Ch ; '\'
0x1400308bd  mov     [rax+rbx+0Ch], cx
0x1400308c2  movzx   eax, word ptr [rsi]
0x1400308c5  add     rax, 2
0x1400308c9  movzx   r8d, word ptr [r14]; Size
0x1400308cd  lea     rcx, [rbx+0Ch]
0x1400308d1  add     rcx, rax; void *
0x1400308d4  mov     rdx, [r14+8]; Src
0x1400308d8  call    memmove
0x1400308dd  mov     bl, 1
0x1400308df  mov     [rsp+58h+var_38], bl
0x1400308e3  jmp     short loc_1400308F2
0x1400308e5  xor     bl, bl
0x1400308e7  mov     [rsp+58h+var_38], bl
0x1400308eb  lea     rdi, WPP_GLOBAL_Control
0x1400308f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400308f9  cmp     rcx, rdi
0x1400308fc  jz      short loc_14003091C
0x1400308fe  test    dword ptr [rcx+2Ch], 80000h
0x140030905  jz      short loc_14003091C
0x140030907  mov     edx, 20h ; ' '
0x14003090c  lea     r8, WPP_ddc2de19639338fa7e5ec9349090cc7f_Traceguids
0x140030913  mov     rcx, [rcx+18h]
0x140030917  call    WPP_SF_
0x14003091c  mov     al, bl
0x14003091e  add     rsp, 30h
0x140030922  pop     r15
0x140030924  pop     r14
0x140030926  pop     rdi
0x140030927  pop     rsi
0x140030928  pop     rbx
0x140030929  retn
```
