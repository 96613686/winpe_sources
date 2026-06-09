# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)

- ea: `0x180003648`
- end: `0x1800036ac`
- name: `??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `__int64 __fastcall(char **)`
- caller_count: `82`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800036b4`
- `0x180003930`
- `0x180005ea0`
- `0x18000668c`
- `0x1800069c0`
- `0x180006ac0`
- `0x180006b60`
- `0x180006d20`
- `0x180006fb0`
- `0x1800070f0`
- `0x180007220`
- `0x180007340`
- `0x180007490`
- `0x1800076f0`
- `0x180007dc0`
- `0x180007e20`
- `0x1800081d8`
- `0x180008248`
- `0x1800083c8`
- `0x180008540`
- `0x1800085ac`
- `0x1800088dc`
- `0x180008c24`
- `0x180008d80`
- `0x180008fd8`
- `0x180009c20`
- `0x180009da4`
- `0x180009eac`
- `0x18000a09c`
- `0x18000a400`
- `0x18000a904`
- `0x18000b164`
- `0x18000b84c`
- `0x18000bcac`
- `0x18000be70`
- `0x18000c060`
- `0x18000c8e0`
- `0x18000ccc0`
- `0x18000cee0`
- `0x18000d200`
- `0x18000d340`
- `0x18000d590`
- `0x18000d7f0`
- `0x18000e094`
- `0x18000e0a0`
- `0x18000e0c8`
- `0x18000e188`
- `0x18000e228`
- `0x18000e458`
- `0x18000ff88`

## callees

- `0x180001564`
- `0x180003648`

## pseudocode

```c
__int64 __fastcall std::wstring::~wstring(char **a1)
{
  unsigned __int64 v1; // rdx
  char *v3; // rax
  unsigned __int64 v4; // rdx
  char *v5; // rcx
  __int64 result; // rax

  v1 = (unsigned __int64)a1[3];
  if ( v1 > 7 )
  {
    v3 = *a1;
    v4 = 2 * v1 + 2;
    if ( v4 < 0x1000 )
    {
      v5 = *a1;
    }
    else
    {
      v5 = (char *)*((_QWORD *)v3 - 1);
      if ( (unsigned __int64)(v3 - v5 - 8) > 0x1F )
        __fastfail(5u);
      v4 += 39LL;
    }
    operator delete(v5, v4);
  }
  result = 0;
  a1[3] = (char *)7;
  a1[2] = 0;
  *(_WORD *)a1 = 0;
  return result;
}

```

## disassembly

```asm
0x180003648  push    rbx
0x18000364a  sub     rsp, 20h
0x18000364e  mov     rdx, [rcx+18h]
0x180003652  mov     rbx, rcx
0x180003655  cmp     rdx, 7
0x180003659  jbe     short loc_180003695
0x18000365b  mov     rax, [rcx]
0x18000365e  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x180003666  cmp     rdx, 1000h
0x18000366d  jb      short loc_18000368D
0x18000366f  mov     rcx, [rax-8]
0x180003673  sub     rax, rcx
0x180003676  sub     rax, 8
0x18000367a  cmp     rax, 1Fh
0x18000367e  ja      short loc_180003686
0x180003680  add     rdx, 27h ; '''
0x180003684  jmp     short loc_180003690
0x180003686  mov     ecx, 5
0x18000368b  int     29h; Win8: RtlFailFast(ecx)
0x18000368d  mov     rcx, rax; void *
0x180003690  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003695  xor     eax, eax
0x180003697  mov     qword ptr [rbx+18h], 7
0x18000369f  mov     [rbx+10h], rax
0x1800036a3  mov     [rbx], ax
0x1800036a6  add     rsp, 20h
0x1800036aa  pop     rbx
0x1800036ab  retn
```
