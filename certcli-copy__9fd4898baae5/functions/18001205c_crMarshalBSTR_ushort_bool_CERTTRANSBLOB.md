# crMarshalBSTR(ushort *,bool,_CERTTRANSBLOB *)

- ea: `0x18001205c`
- end: `0x18001210b`
- name: `?crMarshalBSTR@@YAJPEAG_NPEAU_CERTTRANSBLOB@@@Z`
- size: `175`
- prototype: `__int64 __fastcall(unsigned __int16 *, bool, struct _CERTTRANSBLOB *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011548`

## callees

- `0x180002306`
- `0x18001205c`
- `0x18001e170`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800120bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800120bd`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800120aa`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800120aa`

## pseudocode

```c
__int64 __fastcall crMarshalBSTR(unsigned __int16 *a1, char a2, struct _CERTTRANSBLOB *a3)
{
  size_t v5; // rbx
  unsigned int v6; // ebx
  unsigned int v7; // ecx
  unsigned int v8; // eax
  BYTE *v9; // rax
  size_t Size; // [rsp+38h] [rbp+10h] BYREF
  void *Src; // [rsp+40h] [rbp+18h] BYREF

  Src = 0;
  LODWORD(Size) = 0;
  myGetBStrBuffer(a1, (unsigned int *)&Size, (unsigned __int8 **)&Src);
  v5 = (unsigned int)Size;
  a3->cb = Size;
  if ( a2 )
  {
    if ( (v5 & 1) != 0 )
    {
      v6 = -2147024883;
      v7 = 85787332;
LABEL_4:
      CSPrintErrorLineFile(v7, v6);
      return v6;
    }
    v8 = v5 + 2;
    a3->cb = v5 + 2;
  }
  else
  {
    v8 = v5;
  }
  v9 = (BYTE *)CoTaskMemAlloc(v8);
  a3->pb = v9;
  if ( !v9 )
  {
    v6 = -2147024882;
    v7 = 86311620;
    goto LABEL_4;
  }
  memcpy_0(v9, Src, v5);
  if ( a2 )
    *(_WORD *)&a3->pb[v5] = 0;
  return 0;
}

```

## disassembly

```asm
0x18001205c  mov     rax, rsp
0x18001205f  mov     [rax+8], rbx
0x180012063  mov     [rax+20h], rsi
0x180012067  push    rdi
0x180012068  sub     rsp, 20h
0x18001206c  mov     rdi, r8
0x18001206f  mov     qword ptr [rax+18h], 0
0x180012077  mov     sil, dl
0x18001207a  mov     dword ptr [rax+10h], 0
0x180012081  lea     r8, [rax+18h]; unsigned __int8 **
0x180012085  lea     rdx, [rax+10h]; unsigned int *
0x180012089  call    ?myGetBStrBuffer@@YAXPEAGPEAKPEAPEAE@Z; myGetBStrBuffer(ushort *,ulong *,uchar * *)
0x18001208e  mov     ebx, dword ptr [rsp+28h+Size]
0x180012092  mov     [rdi], ebx
0x180012094  test    sil, sil
0x180012097  jz      short loc_1800120B9
0x180012099  test    bl, 1
0x18001209c  jz      short loc_1800120B2
0x18001209e  mov     ebx, 8007000Dh
0x1800120a3  mov     ecx, 51D02C4h
0x1800120a8  mov     edx, ebx
0x1800120aa  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800120b0  jmp     short loc_1800120F9
0x1800120b2  lea     eax, [rbx+2]
0x1800120b5  mov     [rdi], eax
0x1800120b7  jmp     short loc_1800120BB
0x1800120b9  mov     eax, ebx
0x1800120bb  mov     ecx, eax; cb
0x1800120bd  call    cs:__imp_CoTaskMemAlloc
0x1800120c3  mov     [rdi+8], rax
0x1800120c7  test    rax, rax
0x1800120ca  jnz     short loc_1800120D8
0x1800120cc  mov     ebx, 8007000Eh
0x1800120d1  mov     ecx, 52502C4h
0x1800120d6  jmp     short loc_1800120A8
0x1800120d8  mov     rdx, [rsp+28h+Src]; Src
0x1800120dd  mov     r8, rbx; Size
0x1800120e0  mov     rcx, rax; void *
0x1800120e3  call    memcpy_0
0x1800120e8  test    sil, sil
0x1800120eb  jz      short loc_1800120F7
0x1800120ed  mov     rcx, [rdi+8]
0x1800120f1  xor     eax, eax
0x1800120f3  mov     [rbx+rcx], ax
0x1800120f7  xor     ebx, ebx
0x1800120f9  mov     rsi, [rsp+28h+arg_18]
0x1800120fe  mov     eax, ebx
0x180012100  mov     rbx, [rsp+28h+arg_0]
0x180012105  add     rsp, 20h
0x180012109  pop     rdi
0x18001210a  retn
```
