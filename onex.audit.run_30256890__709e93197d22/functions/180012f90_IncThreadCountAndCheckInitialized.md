# IncThreadCountAndCheckInitialized

- ea: `0x180012f90`
- end: `0x180013048`
- name: `IncThreadCountAndCheckInitialized`
- size: `184`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x180012cc0`
- `0x180023d80`
- `0x18002c010`
- `0x18002c1f0`
- `0x18002c8d0`
- `0x18002cae0`
- `0x18002cd10`
- `0x18002d020`

## callees

- `0x180005440`
- `0x180010ae0`
- `0x180012f90`
- `0x18002d9a8`

## pseudocode

```c
__int64 __fastcall IncThreadCountAndCheckInitialized(int a1, char a2, int a3)
{
  __int64 v3; // r9
  _QWORD *v4; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x400) != 0 )
    WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 7), 29, a3, a1, a2);
  v3 = (unsigned int)_InterlockedIncrement((volatile signed __int32 *)&qword_18003DD5C);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x400) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 30, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids, v3);
    v4 = WPP_GLOBAL_Control;
  }
  if ( HIDWORD(qword_18003DD5C) )
    return 0;
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 68) & 1) != 0 )
    WPP_SF_(v4[7], 31, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids);
  return 21;
}

```

## disassembly

```asm
0x180012f90  push    rbx
0x180012f92  sub     rsp, 30h
0x180012f96  mov     eax, edx
0x180012f98  mov     r9, rcx
0x180012f9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180012fa2  lea     rbx, WPP_GLOBAL_Control
0x180012fa9  cmp     rcx, rbx
0x180012fac  jnz     short loc_180012FDD
0x180012fae  mov     r9d, 1
0x180012fb4  lock xadd dword ptr cs:qword_18003DD5C, r9d
0x180012fbd  inc     r9d
0x180012fc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180012fc7  cmp     rcx, rbx
0x180012fca  jnz     short loc_180012FFA
0x180012fcc  cmp     dword ptr cs:qword_18003DD5C+4, 0
0x180012fd3  jz      short loc_180013021
0x180012fd5  xor     eax, eax
0x180012fd7  add     rsp, 30h
0x180012fdb  pop     rbx
0x180012fdc  retn
0x180012fdd  test    dword ptr [rcx+44h], 400h
0x180012fe4  jz      short loc_180012FAE
0x180012fe6  mov     rcx, [rcx+38h]
0x180012fea  mov     edx, 1Dh
0x180012fef  mov     [rsp+38h+var_18], eax
0x180012ff3  call    WPP_SF_sd
0x180012ff8  jmp     short loc_180012FAE
0x180012ffa  test    dword ptr [rcx+44h], 400h
0x180013001  jz      short loc_180012FCC
0x180013003  mov     rcx, [rcx+38h]
0x180013007  lea     r8, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids
0x18001300e  mov     edx, 1Eh
0x180013013  call    WPP_SF_d
0x180013018  mov     rcx, cs:WPP_GLOBAL_Control
0x18001301f  jmp     short loc_180012FCC
0x180013021  cmp     rcx, rbx
0x180013024  jz      short loc_180013041
0x180013026  test    byte ptr [rcx+44h], 1
0x18001302a  jz      short loc_180013041
0x18001302c  mov     rcx, [rcx+38h]
0x180013030  lea     r8, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids
0x180013037  mov     edx, 1Fh
0x18001303c  call    WPP_SF_
0x180013041  mov     eax, 15h
0x180013046  jmp     short loc_180012FD7
```
