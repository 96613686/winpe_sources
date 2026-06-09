# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)

- ea: `0x140005c80`
- end: `0x140005d6a`
- name: `?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z`
- size: `234`
- prototype: `char __fastcall(void *const *, __int64)`
- caller_count: `50`
- callee_count: `6`
- tags: ``

## callers

- `0x140001150`
- `0x140001200`
- `0x140001270`
- `0x1400012e0`
- `0x140001350`
- `0x1400013c0`
- `0x140001430`
- `0x1400014a0`
- `0x140001510`
- `0x140001580`
- `0x1400015f0`
- `0x140001660`
- `0x1400054e8`
- `0x1400070f0`
- `0x1400088a0`
- `0x140009518`
- `0x14000a610`
- `0x14000b4f4`
- `0x14000b7e0`
- `0x14000c308`
- `0x14000cdb0`
- `0x14000d134`
- `0x14000d9a8`
- `0x14000ea0c`
- `0x14000f4f4`
- `0x1400102e0`
- `0x140010378`
- `0x14001088c`
- `0x140013c8c`
- `0x140014910`
- `0x140014af0`
- `0x140014ea4`
- `0x14001604c`
- `0x1400165b4`
- `0x1400176b4`
- `0x1400180b8`
- `0x1400196f4`
- `0x14001a28c`
- `0x14001bd58`
- `0x14001eb64`
- `0x14001f328`
- `0x1400223d0`
- `0x1400249f0`
- `0x1400251d4`
- `0x140025e48`
- `0x140026f30`
- `0x140027d80`
- `0x140029294`
- `0x14002e46e`
- `0x14002f738`

## callees

- `0x1400027d8`
- `0x140005ac4`
- `0x140005bb8`
- `0x140005c58`
- `0x140005c80`
- `0x1400060c4`

## pseudocode

```c
char __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
        void *const *a1,
        __int64 a2)
{
  char v3; // si
  unsigned int v4; // ebx
  HINSTANCE StringResourceInstance; // rax
  const struct ATL::ATLSTRINGRESOURCEIMAGE *StringResourceImage; // rax
  __int64 v7; // r9
  const struct ATL::ATLSTRINGRESOURCEIMAGE *v8; // rbp
  __int64 v9; // rbx
  int v10; // edx
  errno_t v11; // eax

  v3 = 0;
  if ( (unsigned __int64)(a2 - 1) <= 0xFFFE )
  {
    v4 = (unsigned __int16)a2;
    StringResourceInstance = ATL::AtlFindStringResourceInstance((unsigned __int16)a2, a2);
    v3 = 1;
    if ( StringResourceInstance )
    {
      StringResourceImage = ATL::AtlGetStringResourceImage(StringResourceInstance, v4);
      v8 = StringResourceImage;
      if ( StringResourceImage )
      {
        v9 = *(unsigned __int16 *)StringResourceImage;
        v10 = *((_DWORD *)*a1 - 3) - v9;
        if ( (v10 | (1 - *((_DWORD *)*a1 - 2))) < 0 )
          ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(
            a1,
            *(unsigned __int16 *)StringResourceImage,
            v10 | (unsigned int)(1 - *((_DWORD *)*a1 - 2)),
            v7);
        v11 = memcpy_s(*a1, 2 * v9, (char *)v8 + 2, 2LL * *(unsigned __int16 *)v8);
        if ( v11 )
        {
          if ( v11 == 12 )
            ATL::AtlThrowImpl(0x8007000E);
          if ( v11 == 22 || v11 == 34 )
            ATL::AtlThrowImpl(0x80070057);
          if ( v11 != 80 )
            ATL::AtlThrowImpl(0x80004005);
        }
        if ( (int)v9 > *((_DWORD *)*a1 - 3) )
          ATL::AtlThrowImpl(0x80070057);
        *((_DWORD *)*a1 - 4) = v9;
        *((_WORD *)*a1 + v9) = 0;
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x140005c80  push    rbx
0x140005c82  push    rbp
0x140005c83  push    rsi
0x140005c84  push    rdi
0x140005c85  push    r14
0x140005c87  sub     rsp, 20h
0x140005c8b  mov     rdi, rcx
0x140005c8e  xor     sil, sil
0x140005c91  lea     rax, [rdx-1]
0x140005c95  cmp     rax, 0FFFEh
0x140005c9b  ja      loc_140005D30
0x140005ca1  movzx   ebx, dx
0x140005ca4  mov     ecx, ebx; unsigned int
0x140005ca6  call    ?AtlFindStringResourceInstance@ATL@@YAPEAUHINSTANCE__@@IG@Z; ATL::AtlFindStringResourceInstance(uint,ushort)
0x140005cab  mov     esi, 1
0x140005cb0  test    rax, rax
0x140005cb3  jz      short loc_140005D30
0x140005cb5  mov     edx, ebx; unsigned int
0x140005cb7  mov     rcx, rax; hModule
0x140005cba  call    ?AtlGetStringResourceImage@ATL@@YAPEBUATLSTRINGRESOURCEIMAGE@1@PEAUHINSTANCE__@@I@Z; ATL::AtlGetStringResourceImage(HINSTANCE__ *,uint)
0x140005cbf  mov     rbp, rax
0x140005cc2  test    rax, rax
0x140005cc5  jz      short loc_140005D30
0x140005cc7  movzx   ebx, word ptr [rax]
0x140005cca  mov     rcx, [rdi]
0x140005ccd  mov     r8d, esi
0x140005cd0  sub     r8d, [rcx-8]
0x140005cd4  mov     edx, [rcx-0Ch]
0x140005cd7  sub     edx, ebx
0x140005cd9  or      r8d, edx
0x140005cdc  jge     short loc_140005CE8
0x140005cde  mov     edx, ebx
0x140005ce0  mov     rcx, rdi
0x140005ce3  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x140005ce8  lea     r8, [rbp+2]; Source
0x140005cec  lea     r14, [rbx+rbx]
0x140005cf0  movzx   r9d, word ptr [rbp+0]
0x140005cf5  add     r9, r9; SourceSize
0x140005cf8  mov     rdx, r14; DestinationSize
0x140005cfb  mov     rcx, [rdi]; Destination
0x140005cfe  call    memcpy_s
0x140005d03  test    eax, eax
0x140005d05  jz      short loc_140005D1B
0x140005d07  cmp     eax, 0Ch
0x140005d0a  jz      short loc_140005D3E
0x140005d0c  cmp     eax, 16h
0x140005d0f  jz      short loc_140005D5F
0x140005d11  cmp     eax, 22h ; '"'
0x140005d14  jz      short loc_140005D5F
0x140005d16  cmp     eax, 50h ; 'P'
0x140005d19  jnz     short loc_140005D54
0x140005d1b  mov     rax, [rdi]
0x140005d1e  cmp     ebx, [rax-0Ch]
0x140005d21  jg      short loc_140005D49
0x140005d23  mov     [rax-10h], ebx
0x140005d26  mov     rcx, [rdi]
0x140005d29  xor     eax, eax
0x140005d2b  mov     [r14+rcx], ax
0x140005d30  mov     al, sil
0x140005d33  add     rsp, 20h
0x140005d37  pop     r14
0x140005d39  pop     rdi
0x140005d3a  pop     rsi
0x140005d3b  pop     rbp
0x140005d3c  pop     rbx
0x140005d3d  retn
0x140005d3e  mov     ecx, 8007000Eh; unsigned int
0x140005d43  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140005d49  mov     ecx, 80070057h; unsigned int
0x140005d4e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140005d54  mov     ecx, 80004005h; unsigned int
0x140005d59  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140005d5f  mov     ecx, 80070057h; unsigned int
0x140005d64  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
