# IntersectHandler

- ea: `0x140008100`
- end: `0x1400081fe`
- name: `IntersectHandler`
- size: `254`
- prototype: `__int64 __usercall@<rax>(PKSFILTER Filter@<rcx>, int, int, void *, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1400012c0`
- `0x140008100`

## import_xrefs

- `ks!KsFilterGetFirstChildPin` at `0x14000811c`
- `ks!KsFilterGetFirstChildPin` at `0x140008139`
- `ks!KsFilterGetFirstChildPin` at `0x14000811c`
- `ks!KsFilterGetFirstChildPin` at `0x140008139`

## pseudocode

```c
__int64 __fastcall IntersectHandler(
        PKSFILTER Filter,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        int a5,
        unsigned int a6,
        void *a7,
        _DWORD *a8)
{
  PKSPIN FirstChildPin; // rdx
  LONGLONG *ConnectionFormat; // rcx
  __int64 v13; // r8
  __int64 v14; // r8
  size_t v15; // rcx

  FirstChildPin = KsFilterGetFirstChildPin(Filter, *(_DWORD *)(a3 + 24));
  if ( !FirstChildPin )
  {
    FirstChildPin = KsFilterGetFirstChildPin(Filter, *(_DWORD *)(a3 + 24) ^ 1u);
    if ( !FirstChildPin )
      return 3221226098LL;
  }
  ConnectionFormat = (LONGLONG *)FirstChildPin->ConnectionFormat;
  v13 = a4[4];
  if ( (v13 != ConnectionFormat[4] || a4[5] != ConnectionFormat[5])
    && (v13 != *(_QWORD *)&GUID_NULL.Data1 || a4[5] != *(_QWORD *)GUID_NULL.Data4) )
  {
    return 3221226098LL;
  }
  v14 = a4[6];
  if ( (v14 != ConnectionFormat[6] || a4[7] != ConnectionFormat[7])
    && (v14 != *(_QWORD *)&GUID_NULL.Data1 || a4[7] != *(_QWORD *)GUID_NULL.Data4) )
  {
    return 3221226098LL;
  }
  v15 = *(unsigned int *)ConnectionFormat;
  if ( a6 )
  {
    if ( a6 >= (unsigned int)v15 )
    {
      *a8 = v15;
      memmove(a7, FirstChildPin->ConnectionFormat, v15);
      return 0;
    }
    else
    {
      return 3221225507LL;
    }
  }
  else
  {
    *a8 = v15;
    return 2147483653LL;
  }
}

```

## disassembly

```asm
0x140008100  mov     [rsp+arg_0], rbx
0x140008105  mov     [rsp+arg_8], rsi
0x14000810a  push    rdi
0x14000810b  sub     rsp, 20h
0x14000810f  mov     edx, [r8+18h]; PinId
0x140008113  mov     rbx, r9
0x140008116  mov     rdi, r8
0x140008119  mov     rsi, rcx
0x14000811c  call    cs:__imp_KsFilterGetFirstChildPin
0x140008123  nop     dword ptr [rax+rax+00h]
0x140008128  mov     rdx, rax
0x14000812b  test    rax, rax
0x14000812e  jnz     short loc_140008151
0x140008130  mov     edx, [rdi+18h]
0x140008133  mov     rcx, rsi; Filter
0x140008136  xor     edx, 1; PinId
0x140008139  call    cs:__imp_KsFilterGetFirstChildPin
0x140008140  nop     dword ptr [rax+rax+00h]
0x140008145  mov     rdx, rax
0x140008148  test    rax, rax
0x14000814b  jz      loc_1400081E8
0x140008151  mov     rcx, [rdx+60h]
0x140008155  mov     r8, [rbx+20h]
0x140008159  cmp     r8, [rcx+20h]
0x14000815d  jnz     short loc_140008169
0x14000815f  mov     rax, [rcx+28h]
0x140008163  cmp     [rbx+28h], rax
0x140008167  jz      short loc_14000817F
0x140008169  cmp     r8, qword ptr cs:GUID_NULL.Data1
0x140008170  jnz     short loc_1400081E8
0x140008172  mov     rax, qword ptr cs:GUID_NULL.Data4
0x140008179  cmp     [rbx+28h], rax
0x14000817d  jnz     short loc_1400081E8
0x14000817f  mov     r8, [rbx+30h]
0x140008183  cmp     r8, [rcx+30h]
0x140008187  jnz     short loc_140008193
0x140008189  mov     rax, [rcx+38h]
0x14000818d  cmp     [rbx+38h], rax
0x140008191  jz      short loc_1400081A9
0x140008193  cmp     r8, qword ptr cs:GUID_NULL.Data1
0x14000819a  jnz     short loc_1400081E8
0x14000819c  mov     rax, qword ptr cs:GUID_NULL.Data4
0x1400081a3  cmp     [rbx+38h], rax
0x1400081a7  jnz     short loc_1400081E8
0x1400081a9  mov     eax, [rsp+28h+arg_28]
0x1400081ad  mov     ecx, [rcx]
0x1400081af  test    eax, eax
0x1400081b1  jnz     short loc_1400081C1
0x1400081b3  mov     rax, [rsp+28h+arg_38]
0x1400081b8  mov     [rax], ecx
0x1400081ba  mov     eax, 80000005h
0x1400081bf  jmp     short loc_1400081ED
0x1400081c1  cmp     eax, ecx
0x1400081c3  jnb     short loc_1400081CC
0x1400081c5  mov     eax, 0C0000023h
0x1400081ca  jmp     short loc_1400081ED
0x1400081cc  mov     rax, [rsp+28h+arg_38]
0x1400081d1  mov     r8, rcx; Size
0x1400081d4  mov     [rax], ecx
0x1400081d6  mov     rdx, [rdx+60h]; Src
0x1400081da  mov     rcx, [rsp+28h+arg_30]; void *
0x1400081df  call    memmove
0x1400081e4  xor     eax, eax
0x1400081e6  jmp     short loc_1400081ED
0x1400081e8  mov     eax, 0C0000272h
0x1400081ed  mov     rbx, [rsp+28h+arg_0]
0x1400081f2  mov     rsi, [rsp+28h+arg_8]
0x1400081f7  add     rsp, 20h
0x1400081fb  pop     rdi
0x1400081fc  retn
```
