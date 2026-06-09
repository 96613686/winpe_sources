# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x180007720`
- end: `0x180007784`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `100`
- prototype: `void __fastcall(char **)`
- caller_count: `58`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000763c`
- `0x1800076a4`
- `0x180007798`
- `0x180007dd4`
- `0x180008184`
- `0x1800083ec`
- `0x180008520`
- `0x180008940`
- `0x180009f44`
- `0x18000a8a8`
- `0x18000ac08`
- `0x18000be00`
- `0x18000c634`
- `0x18000c69c`
- `0x18000c718`
- `0x18000c740`
- `0x18000cb50`
- `0x18000cf04`
- `0x18000d9ec`
- `0x18000da88`
- `0x18000dbbc`
- `0x18000de8c`
- `0x18000e284`
- `0x18000eae0`
- `0x18000ee18`
- `0x18000f5c4`
- `0x180010170`
- `0x180010864`
- `0x18001f23b`
- `0x18001f24d`
- `0x18001f25f`
- `0x18001f271`
- `0x18001f283`
- `0x18001f295`
- `0x18001f2a7`
- `0x18001f2b9`
- `0x18001f2cb`
- `0x18001f2dd`
- `0x18001f2ef`
- `0x18001f325`
- `0x18001f349`
- `0x18001f35b`
- `0x18001f391`
- `0x18001f3e2`
- `0x18001f406`
- `0x18001f501`
- `0x18001f5c1`
- `0x18001f662`
- `0x18001f686`
- `0x18001f793`

## callees

- `0x1800026b0`
- `0x180007720`

## pseudocode

```c
void __fastcall std::wstring::~wstring(char **a1)
{
  unsigned __int64 v1; // rdx
  char *v3; // rax
  const struct std::nothrow_t *v4; // rdx
  char *v5; // rcx

  v1 = (unsigned __int64)a1[3];
  if ( v1 > 7 )
  {
    v3 = *a1;
    v4 = (const struct std::nothrow_t *)(2 * v1 + 2);
    if ( (unsigned __int64)v4 < 0x1000 )
    {
      v5 = *a1;
    }
    else
    {
      v5 = (char *)*((_QWORD *)v3 - 1);
      if ( (unsigned __int64)(v3 - v5 - 8) > 0x1F )
        __fastfail(5u);
      v4 = (const struct std::nothrow_t *)((char *)v4 + 39);
    }
    operator delete(v5, v4);
  }
  a1[3] = (char *)7;
  a1[2] = 0;
  *(_WORD *)a1 = 0;
}

```

## disassembly

```asm
0x180007720  push    rbx
0x180007722  sub     rsp, 20h
0x180007726  mov     rdx, [rcx+18h]
0x18000772a  mov     rbx, rcx
0x18000772d  cmp     rdx, 7
0x180007731  jbe     short loc_18000776D
0x180007733  mov     rax, [rcx]
0x180007736  lea     rdx, ds:2[rdx*2]; struct std::nothrow_t *
0x18000773e  cmp     rdx, 1000h
0x180007745  jb      short loc_180007765
0x180007747  mov     rcx, [rax-8]
0x18000774b  sub     rax, rcx
0x18000774e  sub     rax, 8
0x180007752  cmp     rax, 1Fh
0x180007756  ja      short loc_18000775E
0x180007758  add     rdx, 27h ; '''
0x18000775c  jmp     short loc_180007768
0x18000775e  mov     ecx, 5
0x180007763  int     29h; Win8: RtlFailFast(ecx)
0x180007765  mov     rcx, rax; void *
0x180007768  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000776d  xor     eax, eax
0x18000776f  mov     qword ptr [rbx+18h], 7
0x180007777  mov     [rbx+10h], rax
0x18000777b  mov     [rbx], ax
0x18000777e  add     rsp, 20h
0x180007782  pop     rbx
0x180007783  retn
```
