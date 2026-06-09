# std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>::~vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(void)

- ea: `0x18000cc1c`
- end: `0x18000ccd1`
- name: `??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@QEAA@XZ`
- size: `181`
- prototype: `void __fastcall(void **)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000d0f8`
- `0x18000f77c`
- `0x18001562e`
- `0x180015dd3`

## callees

- `0x180002330`
- `0x18000ab70`
- `0x18000cc1c`

## pseudocode

```c
void __fastcall std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::~vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(
        void **a1)
{
  LPCVOID *v1; // rbx
  LPCVOID *v3; // rsi
  char *v4; // rax
  unsigned __int64 v5; // rdx
  _BYTE *v6; // rcx

  v1 = (LPCVOID *)*a1;
  if ( *a1 )
  {
    v3 = (LPCVOID *)a1[1];
    while ( v1 != v3 )
    {
      if ( (unsigned __int64)v1[3] > 7 )
        operator delete(*v1);
      v1[2] = 0;
      *(_WORD *)v1 = 0;
      v1[3] = (LPCVOID)7;
      v1 += 4;
    }
    v4 = (char *)*a1;
    v5 = ((_BYTE *)a1[2] - (_BYTE *)*a1) & 0xFFFFFFFFFFFFFFE0uLL;
    if ( v5 < 0x1000 )
    {
      v6 = *a1;
    }
    else
    {
      v6 = (_BYTE *)*((_QWORD *)v4 - 1);
      if ( (unsigned __int64)(v4 - v6 - 8) > 0x1F )
        __fastfail(5u);
      v5 += 39LL;
    }
    operator delete(v6, v5);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x18000cc1c  mov     [rsp+arg_0], rbx
0x18000cc21  mov     [rsp+arg_8], rsi
0x18000cc26  push    rdi
0x18000cc27  sub     rsp, 20h
0x18000cc2b  mov     rbx, [rcx]
0x18000cc2e  mov     rdi, rcx
0x18000cc31  test    rbx, rbx
0x18000cc34  jz      loc_18000CCC1
0x18000cc3a  mov     rsi, [rcx+8]
0x18000cc3e  jmp     short loc_18000CC68
0x18000cc40  cmp     qword ptr [rbx+18h], 7
0x18000cc45  jbe     short loc_18000CC4F
0x18000cc47  mov     rcx, [rbx]; lpMem
0x18000cc4a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cc4f  xor     eax, eax
0x18000cc51  mov     qword ptr [rbx+10h], 0
0x18000cc59  mov     [rbx], ax
0x18000cc5c  mov     qword ptr [rbx+18h], 7
0x18000cc64  add     rbx, 20h ; ' '
0x18000cc68  cmp     rbx, rsi
0x18000cc6b  jnz     short loc_18000CC40
0x18000cc6d  mov     rax, [rdi]
0x18000cc70  mov     rdx, [rdi+10h]
0x18000cc74  sub     rdx, rax
0x18000cc77  and     rdx, 0FFFFFFFFFFFFFFE0h; unsigned __int64
0x18000cc7b  cmp     rdx, 1000h
0x18000cc82  jb      short loc_18000CCA2
0x18000cc84  mov     rcx, [rax-8]
0x18000cc88  sub     rax, rcx
0x18000cc8b  sub     rax, 8
0x18000cc8f  cmp     rax, 1Fh
0x18000cc93  ja      short loc_18000CC9B
0x18000cc95  add     rdx, 27h ; '''
0x18000cc99  jmp     short loc_18000CCA5
0x18000cc9b  mov     ecx, 5
0x18000cca0  int     29h; Win8: RtlFailFast(ecx)
0x18000cca2  mov     rcx, rax; void *
0x18000cca5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ccaa  mov     qword ptr [rdi], 0
0x18000ccb1  mov     qword ptr [rdi+8], 0
0x18000ccb9  mov     qword ptr [rdi+10h], 0
0x18000ccc1  mov     rbx, [rsp+28h+arg_0]
0x18000ccc6  mov     rsi, [rsp+28h+arg_8]
0x18000cccb  add     rsp, 20h
0x18000cccf  pop     rdi
0x18000ccd0  retn
```
