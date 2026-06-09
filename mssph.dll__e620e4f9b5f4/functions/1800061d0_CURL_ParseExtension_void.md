# CURL::ParseExtension(void)

- ea: `0x1800061d0`
- end: `0x1800062f6`
- name: `?ParseExtension@CURL@@IEAAXXZ`
- size: `294`
- prototype: `void __fastcall(CURL *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800052a0`

## callees

- `0x1800061d0`
- `0x180007810`
- `0x1800080b0`
- `0x18000e878`
- `0x18001e194`

## string_xrefs

- `0x180006262`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`

## pseudocode

```c
void __fastcall CURL::ParseExtension(CURL *this, __int64 a2)
{
  __int16 v2; // ax
  __int16 v4; // ax
  unsigned __int64 v5; // r10
  __int64 v6; // r8
  unsigned __int64 v7; // rcx
  __int64 i; // rax
  int v9; // eax
  __int16 v10; // dx
  __int64 v11; // rdi
  unsigned int v12; // r11d
  int v13; // r11d
  unsigned int v14; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = *((_WORD *)this + 231);
  if ( (v2 & 0x10) != 0 )
  {
    v4 = v2 & 0xFFEF;
    *((_WORD *)this + 231) = v4;
    if ( (v4 & 8) != 0 )
    {
      *((_WORD *)this + 231) = v4 & 0xFFF7;
      CURL::ParseHost(this);
      *((_WORD *)this + 226) = *((_WORD *)this + 227) - *((_WORD *)this + 225);
    }
    v5 = *((unsigned __int16 *)this + 225);
    v6 = *((unsigned __int16 *)this + 226);
    v7 = v5 + v6;
    if ( v5 + v6 < v5 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v7, a2);
    if ( v7 > *((unsigned int *)this + 11) )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x40C,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\lmstr.hxx",
        (const char *)0xCE,
        v14);
    for ( i = (unsigned int)(v5 + v6 - 1); (unsigned int)i >= (unsigned int)v5; i = (unsigned int)(i - 1) )
    {
      if ( (int)i < 0 )
        break;
      if ( *(_WORD *)(*((_QWORD *)this + 4) + 2 * i) == 46 )
        break;
    }
    v9 = i - v5;
    if ( v9 != -1 )
    {
      v10 = v9 + 1;
      if ( v9 + 1 >= (unsigned int)v6 )
        goto LABEL_19;
      v11 = *((_QWORD *)this + 4);
      v12 = v9 + 1;
      while ( !(unsigned int)IsSlash(*(_WORD *)(v11 + 2LL * ((unsigned int)v5 + v12))) )
      {
        v12 = v13 + 1;
        if ( v12 >= (unsigned int)v6 )
          goto LABEL_19;
      }
      if ( v13 == -1 )
      {
LABEL_19:
        *((_WORD *)this + 229) = v5 + v10;
        *((_WORD *)this + 230) = v6 - v10;
      }
    }
  }
}

```

## disassembly

```asm
0x1800061d0  push    rbx; unsigned int
0x1800061d2  sub     rsp, 20h
0x1800061d6  movzx   eax, word ptr [rcx+1CEh]
0x1800061dd  mov     rbx, rcx
0x1800061e0  test    al, 10h
0x1800061e2  jz      loc_1800062F0
0x1800061e8  mov     ecx, 0FFEFh
0x1800061ed  mov     [rsp+28h+arg_0], rsi
0x1800061f2  and     ax, cx
0x1800061f5  mov     [rsp+28h+arg_8], rdi
0x1800061fa  mov     [rbx+1CEh], ax
0x180006201  test    al, 8
0x180006203  jz      short loc_180006231
0x180006205  mov     ecx, 0FFF7h
0x18000620a  and     ax, cx
0x18000620d  mov     rcx, rbx; this
0x180006210  mov     [rbx+1CEh], ax
0x180006217  call    ?ParseHost@CURL@@IEAAXXZ; CURL::ParseHost(void)
0x18000621c  movzx   eax, word ptr [rbx+1C6h]
0x180006223  sub     ax, [rbx+1C2h]
0x18000622a  mov     [rbx+1C4h], ax
0x180006231  movzx   r10d, word ptr [rbx+1C2h]
0x180006239  movzx   r8d, word ptr [rbx+1C4h]
0x180006241  mov     rsi, [rsp+28h+arg_0]
0x180006246  lea     rcx, [r10+r8]
0x18000624a  cmp     rcx, r10
0x18000624d  jnb     short loc_180006255
0x18000624f  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x180006255  mov     eax, [rbx+2Ch]
0x180006258  cmp     rcx, rax
0x18000625b  jbe     short loc_18000627A
0x18000625d  mov     rcx, [rsp+28h]; this
0x180006262  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180006269  mov     r9d, 0CEh; char *
0x18000626f  mov     edx, 40Ch; void *
0x180006274  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18000627a  lea     eax, [r8-1]
0x18000627e  add     eax, r10d
0x180006281  cmp     eax, r10d
0x180006284  jb      short loc_18000629C
0x180006286  test    eax, eax
0x180006288  js      short loc_18000629C
0x18000628a  mov     rcx, [rbx+20h]
0x18000628e  cmp     word ptr [rcx+rax*2], 2Eh ; '.'
0x180006293  jz      short loc_18000629C
0x180006295  dec     eax
0x180006297  cmp     eax, r10d
0x18000629a  jnb     short loc_180006286
0x18000629c  sub     eax, r10d
0x18000629f  cmp     eax, 0FFFFFFFFh
0x1800062a2  jz      short loc_1800062EB
0x1800062a4  lea     edx, [rax+1]
0x1800062a7  cmp     edx, r8d
0x1800062aa  jnb     short loc_1800062D4
0x1800062ac  mov     rdi, [rbx+20h]
0x1800062b0  mov     r11d, edx
0x1800062b3  lea     eax, [r10+r11]
0x1800062b7  movzx   ecx, word ptr [rdi+rax*2]; wchar_t
0x1800062bb  call    ?IsSlash@@YAH_W@Z; IsSlash(wchar_t)
0x1800062c0  test    eax, eax
0x1800062c2  jnz     short loc_1800062CE
0x1800062c4  inc     r11d
0x1800062c7  cmp     r11d, r8d
0x1800062ca  jb      short loc_1800062B3
0x1800062cc  jmp     short loc_1800062D4
0x1800062ce  cmp     r11d, 0FFFFFFFFh
0x1800062d2  jnz     short loc_1800062EB
0x1800062d4  lea     eax, [r10+rdx]
0x1800062d8  sub     r8w, dx
0x1800062dc  mov     [rbx+1CAh], ax
0x1800062e3  mov     [rbx+1CCh], r8w
0x1800062eb  mov     rdi, [rsp+28h+arg_8]
0x1800062f0  add     rsp, 20h
0x1800062f4  pop     rbx
0x1800062f5  retn
```
