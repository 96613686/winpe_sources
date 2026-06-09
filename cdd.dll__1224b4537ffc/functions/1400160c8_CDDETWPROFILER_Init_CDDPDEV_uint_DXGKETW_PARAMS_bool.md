# CDDETWPROFILER::Init(CDDPDEV *,uint,_DXGKETW_PARAMS *,bool)

- ea: `0x1400160c8`
- end: `0x140016100`
- name: `?Init@CDDETWPROFILER@@QEAAXPEAUCDDPDEV@@IPEAU_DXGKETW_PARAMS@@_N@Z`
- size: `56`
- prototype: `void __fastcall(CDDETWPROFILER *__hidden this, struct CDDPDEV *, unsigned int, struct _DXGKETW_PARAMS *, bool)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x140002504`
- `0x140004904`
- `0x140005cc0`
- `0x140006a70`
- `0x140007b00`
- `0x14000a254`
- `0x14000d63c`
- `0x140015f00`
- `0x1400161b0`
- `0x140017518`
- `0x140019458`
- `0x140022e70`
- `0x1400235c0`
- `0x140023e60`
- `0x14002fbd4`

## callees

- `0x1400372d0`

## pseudocode

```c
void __fastcall CDDETWPROFILER::Init(
        CDDETWPROFILER *this,
        struct CDDPDEV *a2,
        unsigned int a3,
        struct _DXGKETW_PARAMS *a4,
        bool a5)
{
  *(_QWORD *)this = a2;
  *((_DWORD *)this + 2) = a3;
  *((_DWORD *)this + 6) = a5;
  *((_QWORD *)this + 2) = a4;
  (*((void (__fastcall **)(_QWORD, bool, struct _DXGKETW_PARAMS *))a2 + 33))(a3, !a5, a4);
}

```

## disassembly

```asm
0x1400160c8  sub     rsp, 28h
0x1400160cc  mov     [rcx], rdx
0x1400160cf  mov     r10, rdx
0x1400160d2  movzx   edx, [rsp+28h+arg_20]
0x1400160d7  mov     r11d, r8d
0x1400160da  mov     [rcx+8], r8d
0x1400160de  mov     r8, r9
0x1400160e1  mov     [rcx+18h], edx
0x1400160e4  xor     dl, 1
0x1400160e7  mov     [rcx+10h], r9
0x1400160eb  mov     ecx, r11d
0x1400160ee  mov     rax, [r10+108h]
0x1400160f5  call    _guard_dispatch_icall
0x1400160fa  add     rsp, 28h
0x1400160fe  retn
```
