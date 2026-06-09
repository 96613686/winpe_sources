# CConfig::~CConfig(void)

- ea: `0x14000704c`
- end: `0x1400070e3`
- name: `??1CConfig@@QEAA@XZ`
- size: `151`
- prototype: `void __fastcall(CConfig *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x14000d734`
- `0x140029ddb`

## callees

- `0x140001fcc`
- `0x140006f58`
- `0x14000704c`

## pseudocode

```c
void __fastcall CConfig::~CConfig(CConfig *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx

  v2 = *(_QWORD *)this;
  if ( v2 )
    operator delete((void *)(v2 - 8));
  v3 = *((_QWORD *)this + 9);
  if ( v3 )
    operator delete((void *)(v3 - 8));
  v4 = *((_QWORD *)this + 29);
  if ( v4 )
    operator delete((void *)(v4 - 8));
  v5 = *((_QWORD *)this + 30);
  if ( v5 )
    operator delete((void *)(v5 - 8));
  v6 = *((_QWORD *)this + 10);
  if ( v6 )
    operator delete((void *)(v6 - 8));
  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>((char *)this + 256);
  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>((char *)this + 160);
  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>((char *)this + 88);
  CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>((char *)this + 8);
}

```

## disassembly

```asm
0x14000704c  push    rbx
0x14000704e  sub     rsp, 20h
0x140007052  mov     rbx, rcx
0x140007055  mov     rcx, [rcx]
0x140007058  test    rcx, rcx
0x14000705b  jz      short loc_140007066
0x14000705d  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x140007061  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140007066  mov     rcx, [rbx+48h]
0x14000706a  test    rcx, rcx
0x14000706d  jz      short loc_140007078
0x14000706f  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x140007073  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140007078  mov     rcx, [rbx+0E8h]
0x14000707f  test    rcx, rcx
0x140007082  jz      short loc_14000708D
0x140007084  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x140007088  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000708d  mov     rcx, [rbx+0F0h]
0x140007094  test    rcx, rcx
0x140007097  jz      short loc_1400070A2
0x140007099  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x14000709d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400070a2  mov     rcx, [rbx+50h]
0x1400070a6  test    rcx, rcx
0x1400070a9  jz      short loc_1400070B4
0x1400070ab  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x1400070af  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400070b4  lea     rcx, [rbx+100h]
0x1400070bb  call    ??1?$CCbsArrayBase@PEA_WVCCbsStringArray@@@@MEAA@XZ; CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(void)
0x1400070c0  lea     rcx, [rbx+0A0h]
0x1400070c7  call    ??1?$CCbsArrayBase@PEA_WVCCbsStringArray@@@@MEAA@XZ; CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(void)
0x1400070cc  lea     rcx, [rbx+58h]
0x1400070d0  call    ??1?$CCbsArrayBase@PEA_WVCCbsStringArray@@@@MEAA@XZ; CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(void)
0x1400070d5  lea     rcx, [rbx+8]
0x1400070d9  add     rsp, 20h
0x1400070dd  pop     rbx
0x1400070de  jmp     ??1?$CCbsArrayBase@PEA_WVCCbsStringArray@@@@MEAA@XZ; CCbsArrayBase<wchar_t *,CCbsStringArray>::~CCbsArrayBase<wchar_t *,CCbsStringArray>(void)
```
