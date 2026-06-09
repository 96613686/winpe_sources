# wil::details::HrToNtStatus(long)

- ea: `0x180024d90`
- end: `0x180024f15`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `389`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180021950`
- `0x1800219f0`
- `0x180021a50`
- `0x180021b20`
- `0x180023e70`
- `0x1800254a0`

## callees

- `0x180024d90`

## pseudocode

```c
__int64 __fastcall wil::details::HrToNtStatus(wil::details *this)
{
  unsigned int v1; // edx
  __int64 result; // rax
  unsigned int v3; // edx

  v1 = (unsigned int)this;
  if ( (int)this <= -2147024895 )
  {
    if ( (_DWORD)this == -2147024895 )
      return 3221225474LL;
    if ( (_DWORD)this == -2147467259 )
      return 3221225473LL;
    goto LABEL_34;
  }
  if ( (int)this > -2147024362 )
  {
    if ( (int)this > -2147023746 )
    {
      switch ( (_DWORD)this )
      {
        case 0x8007050C:
          return (unsigned int)-1073740757;
        case 0x8007054F:
          return 3221225701LL;
        case 0x800705B9:
          return 3221266563LL;
        case 0:
          return 0;
      }
    }
    else
    {
      switch ( (_DWORD)this )
      {
        case 0x8007047E:
          return 3221225561LL;
        case 0x8007023E:
          return 3221225509LL;
        case 0x80070246:
          return 3221225825LL;
        case 0x80070247:
          return 3221225827LL;
        case 0x80070272:
          return 3221226099LL;
      }
    }
LABEL_34:
    if ( ((unsigned int)this & 0x10000000) != 0 )
      return (unsigned int)this & 0xEFFFFFFF;
    if ( ((unsigned int)this & 0x1FFF0000) == 0x70000 )
    {
      v3 = (unsigned __int16)this;
      if ( (_WORD)this )
        return (unsigned __int16)this | 0xC0070000;
      return v3;
    }
    if ( ((unsigned int)this & 0x1FFF0000) == 0x90000 )
    {
      if ( (int)this > 0 )
        return (unsigned __int16)this | 0xC0090000;
      return v1;
    }
    return 3221225701LL;
  }
  if ( (_DWORD)this == -2147024362 )
    return 3221225621LL;
  switch ( (unsigned int)this )
  {
    case 0x80070002:
      result = 3221225524LL;
      break;
    case 0x80070003:
      result = 3221225530LL;
      break;
    case 0x8007000E:
      result = 3221225495LL;
      break;
    case 0x80070057:
      result = 3221225485LL;
      break;
    case 0x80070070:
      result = 3221225599LL;
      break;
    case 0x8007007A:
      result = 3221225507LL;
      break;
    case 0x8007007B:
      result = 3221225523LL;
      break;
    case 0x8007007E:
      result = 3221225781LL;
      break;
    case 0x800700EA:
      result = 2147483653LL;
      break;
    default:
      goto LABEL_34;
  }
  return result;
}

```

## disassembly

```asm
0x180024d90  mov     edx, ecx
0x180024d92  cmp     ecx, 80070001h
0x180024d98  jg      short loc_180024DB8
0x180024d9a  jz      short loc_180024DB0
0x180024d9c  cmp     ecx, 80004005h
0x180024da2  jnz     def_180024DF4; jumptable 0000000180024DF4 default case, cases -2147024892--2147024883,-2147024881--2147024810,-2147024808--2147024785,-2147024783--2147024775,-2147024772,-2147024771,-2147024769--2147024663
0x180024da8  mov     edx, 0C0000001h
0x180024dad  mov     eax, edx
0x180024daf  retn
0x180024db0  mov     edx, 0C0000002h
0x180024db5  mov     eax, edx
0x180024db7  retn
0x180024db8  cmp     edx, 80070216h
0x180024dbe  jg      loc_180024E46
0x180024dc4  jz      short loc_180024E3E
0x180024dc6  lea     eax, [rcx+7FF8FFFEh]; switch 233 cases
0x180024dcc  cmp     eax, 0E8h
0x180024dd1  ja      def_180024DF4; jumptable 0000000180024DF4 default case, cases -2147024892--2147024883,-2147024881--2147024810,-2147024808--2147024785,-2147024783--2147024775,-2147024772,-2147024771,-2147024769--2147024663
0x180024dd7  lea     r8, __ImageBase
0x180024dde  cdqe
0x180024de0  movzx   eax, ds:(byte_180024F40 - 180000000h)[r8+rax]
0x180024de9  mov     ecx, ds:(jpt_180024DF4 - 180000000h)[r8+rax*4]
0x180024df1  add     rcx, r8
0x180024df4  jmp     rcx; switch jump
0x180024df6  mov     edx, 0C000000Dh; jumptable 0000000180024DF4 case -2147024809
0x180024dfb  mov     eax, edx
0x180024dfd  retn
0x180024dfe  mov     edx, 0C0000017h; jumptable 0000000180024DF4 case -2147024882
0x180024e03  mov     eax, edx
0x180024e05  retn
0x180024e06  mov     edx, 0C000003Ah; jumptable 0000000180024DF4 case -2147024893
0x180024e0b  mov     eax, edx
0x180024e0d  retn
0x180024e0e  mov     edx, 0C0000034h; jumptable 0000000180024DF4 case -2147024894
0x180024e13  mov     eax, edx
0x180024e15  retn
0x180024e16  mov     edx, 80000005h; jumptable 0000000180024DF4 case -2147024662
0x180024e1b  mov     eax, edx
0x180024e1d  retn
0x180024e1e  mov     edx, 0C0000023h; jumptable 0000000180024DF4 case -2147024774
0x180024e23  mov     eax, edx
0x180024e25  retn
0x180024e26  mov     edx, 0C000007Fh; jumptable 0000000180024DF4 case -2147024784
0x180024e2b  mov     eax, edx
0x180024e2d  retn
0x180024e2e  mov     edx, 0C0000033h; jumptable 0000000180024DF4 case -2147024773
0x180024e33  mov     eax, edx
0x180024e35  retn
0x180024e36  mov     edx, 0C0000135h; jumptable 0000000180024DF4 case -2147024770
0x180024e3b  mov     eax, edx
0x180024e3d  retn
0x180024e3e  mov     edx, 0C0000095h
0x180024e43  mov     eax, edx
0x180024e45  retn
0x180024e46  cmp     edx, 8007047Eh
0x180024e4c  jg      short loc_180024E98
0x180024e4e  jz      short loc_180024E90
0x180024e50  cmp     edx, 8007023Eh
0x180024e56  jz      short loc_180024E88
0x180024e58  cmp     edx, 80070246h
0x180024e5e  jz      short loc_180024E80
0x180024e60  cmp     edx, 80070247h
0x180024e66  jz      short loc_180024E78
0x180024e68  cmp     edx, 80070272h
0x180024e6e  jnz     short def_180024DF4; jumptable 0000000180024DF4 default case, cases -2147024892--2147024883,-2147024881--2147024810,-2147024808--2147024785,-2147024783--2147024775,-2147024772,-2147024771,-2147024769--2147024663
0x180024e70  mov     edx, 0C0000273h
0x180024e75  mov     eax, edx
0x180024e77  retn
0x180024e78  mov     edx, 0C0000163h
0x180024e7d  mov     eax, edx
0x180024e7f  retn
0x180024e80  mov     edx, 0C0000161h
0x180024e85  mov     eax, edx
0x180024e87  retn
0x180024e88  mov     edx, 0C0000025h
0x180024e8d  mov     eax, edx
0x180024e8f  retn
0x180024e90  mov     edx, 0C0000059h
0x180024e95  mov     eax, edx
0x180024e97  retn
0x180024e98  cmp     edx, 8007050Ch
0x180024e9e  jz      short loc_180024F0D
0x180024ea0  cmp     edx, 8007054Fh
0x180024ea6  jz      short loc_180024F05
0x180024ea8  cmp     edx, 800705B9h
0x180024eae  jz      short loc_180024EFD
0x180024eb0  test    edx, edx
0x180024eb2  jz      short loc_180024EF8
0x180024eb4  bt      edx, 1Ch; jumptable 0000000180024DF4 default case, cases -2147024892--2147024883,-2147024881--2147024810,-2147024808--2147024785,-2147024783--2147024775,-2147024772,-2147024771,-2147024769--2147024663
0x180024eb8  jnb     short loc_180024EC1
0x180024eba  btr     edx, 1Ch
0x180024ebe  mov     eax, edx
0x180024ec0  retn
0x180024ec1  mov     eax, edx
0x180024ec3  and     eax, 1FFF0000h
0x180024ec8  cmp     eax, 70000h
0x180024ecd  jnz     short loc_180024EE1
0x180024ecf  movzx   edx, dx
0x180024ed2  mov     eax, edx
0x180024ed4  or      eax, 0C0070000h
0x180024ed9  test    edx, edx
0x180024edb  cmovnz  edx, eax
0x180024ede  mov     eax, edx
0x180024ee0  retn
0x180024ee1  cmp     eax, 90000h
0x180024ee6  jnz     short loc_180024F05
0x180024ee8  test    edx, edx
0x180024eea  jle     short loc_180024F12
0x180024eec  movzx   edx, dx
0x180024eef  or      edx, 0C0090000h
0x180024ef5  mov     eax, edx
0x180024ef7  retn
0x180024ef8  xor     edx, edx
0x180024efa  mov     eax, edx
0x180024efc  retn
0x180024efd  mov     edx, 0C000A083h
0x180024f02  mov     eax, edx
0x180024f04  retn
0x180024f05  mov     edx, 0C00000E5h
0x180024f0a  mov     eax, edx
0x180024f0c  retn
0x180024f0d  mov     edx, 0C000042Bh
0x180024f12  mov     eax, edx
0x180024f14  retn
```
