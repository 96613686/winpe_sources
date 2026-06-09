# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x180007858`
- end: `0x1800078c1`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `105`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `27`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180009504`
- `0x18000b3e0`
- `0x1800121a0`
- `0x1800145d0`
- `0x18002061c`
- `0x180020c20`
- `0x1800221fa`
- `0x18002220c`
- `0x18002221e`
- `0x180022428`
- `0x18002243a`
- `0x18002246a`
- `0x18002247c`
- `0x18002248e`
- `0x1800224be`
- `0x180022ac4`
- `0x180022ad6`
- `0x180022ae8`
- `0x180022afa`
- `0x180022b0c`
- `0x180022b30`
- `0x180022cb9`
- `0x180022ff6`
- `0x18002305d`
- `0x180023093`
- `0x18002311b`
- `0x1800236d2`

## callees

- `0x180002b0c`
- `0x180007858`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x1800078b4`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x1800078b4`

## pseudocode

```c
__int64 __fastcall std::wstring::~wstring(__int64 a1)
{
  unsigned __int64 v1; // rdx
  char *v3; // rcx
  unsigned __int64 v4; // rdx
  char *v5; // r8
  unsigned __int64 v6; // rdx
  char *v7; // rcx
  __int64 result; // rax

  v1 = *(_QWORD *)(a1 + 24);
  if ( v1 > 7 )
  {
    v3 = *(char **)a1;
    v4 = 2 * v1 + 2;
    if ( v4 >= 0x1000 )
    {
      v5 = (char *)*((_QWORD *)v3 - 1);
      v6 = v4 + 39;
      v7 = (char *)(v3 - v5);
      if ( (unsigned __int64)(v7 - 8) > 0x1F )
      {
        _o__invalid_parameter_noinfo_noreturn(v7, v6);
        __debugbreak();
        JUMPOUT(0x1800078C1LL);
      }
      v3 = v5;
    }
    operator delete(v3);
  }
  result = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_QWORD *)(a1 + 16) = 0;
  *(_WORD *)a1 = 0;
  return result;
}

```

## disassembly

```asm
0x180007858  push    rbx
0x18000785a  sub     rsp, 20h
0x18000785e  mov     rdx, [rcx+18h]
0x180007862  mov     rbx, rcx
0x180007865  cmp     rdx, 7
0x180007869  jbe     short loc_18000789C
0x18000786b  mov     rcx, [rcx]
0x18000786e  lea     rdx, ds:2[rdx*2]
0x180007876  cmp     rdx, 1000h
0x18000787d  jb      short loc_180007897
0x18000787f  mov     r8, [rcx-8]
0x180007883  add     rdx, 27h ; '''; unsigned __int64
0x180007887  sub     rcx, r8
0x18000788a  lea     rax, [rcx-8]
0x18000788e  cmp     rax, 1Fh
0x180007892  ja      short loc_1800078B4
0x180007894  mov     rcx, r8; void *
0x180007897  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000789c  xor     eax, eax
0x18000789e  mov     qword ptr [rbx+18h], 7
0x1800078a6  mov     [rbx+10h], rax
0x1800078aa  mov     [rbx], ax
0x1800078ad  add     rsp, 20h
0x1800078b1  pop     rbx
0x1800078b2  retn
0x1800078b4  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x1800078bb  nop     dword ptr [rax+rax+00h]
0x1800078c0  int     3; Trap to Debugger
```
