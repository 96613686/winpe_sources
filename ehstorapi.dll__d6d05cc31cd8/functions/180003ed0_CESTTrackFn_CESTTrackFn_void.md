# CESTTrackFn::~CESTTrackFn(void)

- ea: `0x180003ed0`
- end: `0x180003f5d`
- name: `??1CESTTrackFn@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(CESTTrackFn *__hidden this)`
- caller_count: `28`
- callee_count: `3`
- tags: ``

## callers

- `0x180003f64`
- `0x1800042f4`
- `0x180004380`
- `0x1800046b4`
- `0x180004a60`
- `0x18000521c`
- `0x180005960`
- `0x180005d50`
- `0x180006400`
- `0x18000664c`
- `0x180006a64`
- `0x180006af0`
- `0x180007090`
- `0x1800071c0`
- `0x180007290`
- `0x180007430`
- `0x180007840`
- `0x1800079d0`
- `0x180007f00`
- `0x1800082b0`
- `0x18000c9ae`
- `0x18000ca57`
- `0x18000cadb`
- `0x18000caed`
- `0x18000cbeb`
- `0x18000cbfd`
- `0x18000cc8d`
- `0x18000cc9f`

## callees

- `0x180003ce0`
- `0x180003ed0`
- `0x180006254`

## pseudocode

```c
void __fastcall CESTTrackFn::~CESTTrackFn(CESTTrackFn *this)
{
  _DWORD *v1; // rax

  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    _InterlockedDecrement((volatile signed __int32 *)this + 65);
    v1 = (_DWORD *)*((_QWORD *)this + 33);
    if ( v1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)&WPP_GLOBAL_Control,
          (_DWORD)WPP_GLOBAL_Control,
          (_DWORD)this,
          *v1);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_1ced0896021d321125604b18ca1017e5_Traceguids, this);
    }
  }
}

```

## disassembly

```asm
0x180003ed0  sub     rsp, 38h
0x180003ed4  mov     rax, cs:WPP_GLOBAL_Control
0x180003edb  mov     r9b, 10h
0x180003ede  test    [rax+1Ch], r9b
0x180003ee2  jz      short loc_180003F58
0x180003ee4  lock dec dword ptr [rcx+104h]
0x180003eeb  mov     rax, [rcx+108h]
0x180003ef2  test    rax, rax
0x180003ef5  jz      short loc_180003F27
0x180003ef7  mov     r8, cs:WPP_GLOBAL_Control
0x180003efe  lea     rdx, WPP_GLOBAL_Control
0x180003f05  cmp     r8, rdx
0x180003f08  jz      short loc_180003F58
0x180003f0a  test    [r8+1Ch], r9b
0x180003f0e  jz      short loc_180003F58
0x180003f10  mov     eax, [rax]
0x180003f12  mov     r9, rcx
0x180003f15  mov     rcx, [r8+10h]
0x180003f19  mov     [rsp+38h+var_18], eax
0x180003f1d  call    WPP_SF_sd
0x180003f22  add     rsp, 38h
0x180003f26  retn
0x180003f27  mov     rax, cs:WPP_GLOBAL_Control
0x180003f2e  lea     rdx, WPP_GLOBAL_Control
0x180003f35  cmp     rax, rdx
0x180003f38  jz      short loc_180003F58
0x180003f3a  test    [rax+1Ch], r9b
0x180003f3e  jz      short loc_180003F58
0x180003f40  mov     r9, rcx
0x180003f43  lea     r8, WPP_1ced0896021d321125604b18ca1017e5_Traceguids
0x180003f4a  mov     rcx, [rax+10h]
0x180003f4e  mov     edx, 0Bh
0x180003f53  call    WPP_SF_s
0x180003f58  add     rsp, 38h
0x180003f5c  retn
```
