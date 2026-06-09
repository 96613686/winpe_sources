# DfscCreateDcContext

- ea: `0x140022710`
- end: `0x1400227ce`
- name: `DfscCreateDcContext`
- size: `190`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140021c60`
- `0x140021e28`
- `0x140022b60`

## callees

- `0x140002570`
- `0x1400025f4`
- `0x140006380`
- `0x140022710`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002272c`
- `ntoskrnl!ExAllocatePool2` at `0x14002272c`

## pseudocode

```c
_DWORD *DfscCreateDcContext()
{
  _DWORD *Pool2; // rax
  _DWORD *v1; // rbx

  Pool2 = (_DWORD *)ExAllocatePool2(258, 72, 1682138692);
  v1 = Pool2;
  if ( Pool2 )
  {
    memset(Pool2, 0, 0x48u);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_25814b49fee93ed9772097e36f5d22dd_Traceguids, v1);
    }
    *v1 = 4751622;
    v1[1] = 1;
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_25814b49fee93ed9772097e36f5d22dd_Traceguids);
  }
  return v1;
}

```

## disassembly

```asm
0x140022710  mov     [rsp+arg_0], rbx
0x140022715  push    rdi
0x140022716  sub     rsp, 20h
0x14002271a  mov     edi, 48h ; 'H'
0x14002271f  mov     r8d, 64436644h
0x140022725  mov     edx, edi
0x140022727  mov     ecx, 102h
0x14002272c  call    cs:__imp_ExAllocatePool2
0x140022733  nop     dword ptr [rax+rax+00h]
0x140022738  mov     rbx, rax
0x14002273b  test    rax, rax
0x14002273e  jz      short loc_14002278E
0x140022740  mov     r8d, edi; Size
0x140022743  xor     edx, edx; Val
0x140022745  mov     rcx, rax; void *
0x140022748  call    memset
0x14002274d  mov     rcx, cs:WPP_GLOBAL_Control
0x140022754  lea     rax, WPP_GLOBAL_Control
0x14002275b  cmp     rcx, rax
0x14002275e  jz      short loc_14002277F
0x140022760  test    dword ptr [rcx+2Ch], 400000h
0x140022767  jz      short loc_14002277F
0x140022769  mov     rcx, [rcx+18h]
0x14002276d  lea     edx, [rdi-34h]
0x140022770  mov     r9, rbx
0x140022773  lea     r8, WPP_25814b49fee93ed9772097e36f5d22dd_Traceguids
0x14002277a  call    WPP_SF_q
0x14002277f  mov     dword ptr [rbx], 488106h
0x140022785  mov     dword ptr [rbx+4], 1
0x14002278c  jmp     short loc_1400227BF
0x14002278e  mov     rcx, cs:WPP_GLOBAL_Control
0x140022795  lea     rax, WPP_GLOBAL_Control
0x14002279c  cmp     rcx, rax
0x14002279f  jz      short loc_1400227BF
0x1400227a1  test    dword ptr [rcx+2Ch], 100000h
0x1400227a8  jz      short loc_1400227BF
0x1400227aa  mov     rcx, [rcx+18h]
0x1400227ae  lea     r8, WPP_25814b49fee93ed9772097e36f5d22dd_Traceguids
0x1400227b5  mov     edx, 15h
0x1400227ba  call    WPP_SF_
0x1400227bf  mov     rax, rbx
0x1400227c2  mov     rbx, [rsp+28h+arg_0]
0x1400227c7  add     rsp, 20h
0x1400227cb  pop     rdi
0x1400227cc  retn
```
