# CURL::GetPath(void)

- ea: `0x1800076a0`
- end: `0x180007800`
- name: `?GetPath@CURL@@QEAA?AVCLMSubStr@@XZ`
- size: `352`
- prototype: `__int64 __fastcall(_WORD *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003970`

## callees

- `0x1800076a0`
- `0x180007810`
- `0x18000e878`
- `0x1800101a0`
- `0x1800103cc`
- `0x180010434`
- `0x18001e194`

## string_xrefs

- `0x1800077e8`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`

## pseudocode

```c
__int64 __fastcall CURL::GetPath(_WORD *a1, __int64 a2)
{
  __int16 v2; // ax
  _WORD *v3; // rbp
  unsigned __int64 v6; // rcx
  _WORD *v7; // rdi
  __int64 v8; // rax
  unsigned int v10; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = a1[231];
  v3 = a1 + 225;
  if ( (v2 & 8) != 0 )
  {
    a1[231] = v2 & 0xFFF7;
    CURL::ParseHost((CURL *)a1);
    a1[226] = a1[227] - *v3;
  }
  if ( a1[226] || !a1[220] )
  {
    v6 = (unsigned __int16)*v3;
    v7 = a1 + 12;
    v8 = (unsigned int)(*((_DWORD *)v7 + 5) - v6);
    if ( v8 + v6 < v6 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v6, v8);
    if ( v8 + v6 > *((unsigned int *)v7 + 5) )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x40C,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\lmstr.hxx",
        (const char *)0xCE,
        v10);
    *(_DWORD *)a2 = v6;
    *(_DWORD *)(a2 + 4) = v8;
    *(_QWORD *)(a2 + 8) = v7;
  }
  else
  {
    if ( __TSS0__1__GetPath_CURL__QEAA_AVCLMSubStr__XZ_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                         + (unsigned int)tls_index)
                                                                       + 4LL) )
    {
      Init_thread_header(&__TSS0__1__GetPath_CURL__QEAA_AVCLMSubStr__XZ_4HA);
      if ( __TSS0__1__GetPath_CURL__QEAA_AVCLMSubStr__XZ_4HA == -1 )
      {
        dword_180036674 = 1;
        qword_180036668 = (__int64)L"/";
        dword_180036670 = 1;
        `CURL::GetPath'::`2'::slash = (__int64)&CConstString::`vftable';
        atexit(`CURL::GetPath'::`2'::`dynamic atexit destructor for 'slash'');
        Init_thread_footer(&__TSS0__1__GetPath_CURL__QEAA_AVCLMSubStr__XZ_4HA);
      }
    }
    *(_DWORD *)(a2 + 4) = dword_180036674;
    *(_QWORD *)(a2 + 8) = &`CURL::GetPath'::`2'::slash;
    *(_DWORD *)a2 = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x1800076a0  push    rbx
0x1800076a2  push    rbp
0x1800076a3  push    rsi
0x1800076a4  push    rdi
0x1800076a5  sub     rsp, 28h
0x1800076a9  movzx   eax, word ptr [rcx+1CEh]
0x1800076b0  lea     rbp, [rcx+1C2h]
0x1800076b7  mov     rbx, rdx
0x1800076ba  mov     rdi, rcx
0x1800076bd  test    al, 8
0x1800076bf  jnz     short loc_180007709
0x1800076c1  cmp     word ptr [rdi+1C4h], 0
0x1800076c9  jz      short loc_180007734
0x1800076cb  movzx   ecx, word ptr [rbp+0]
0x1800076cf  add     rdi, 18h
0x1800076d3  mov     r8d, [rdi+14h]
0x1800076d7  mov     eax, r8d
0x1800076da  sub     eax, ecx
0x1800076dc  mov     edx, eax
0x1800076de  lea     r9, [rax+rcx]
0x1800076e2  cmp     r9, rcx
0x1800076e5  jb      loc_1800077DD
0x1800076eb  cmp     r9, r8
0x1800076ee  ja      loc_1800077E3
0x1800076f4  mov     [rbx], ecx
0x1800076f6  mov     [rbx+4], edx
0x1800076f9  mov     [rbx+8], rdi
0x1800076fd  mov     rax, rbx
0x180007700  add     rsp, 28h
0x180007704  pop     rdi
0x180007705  pop     rsi
0x180007706  pop     rbp
0x180007707  pop     rbx
0x180007708  retn
0x180007709  mov     ecx, 0FFF7h
0x18000770e  and     ax, cx
0x180007711  mov     rcx, rdi; this
0x180007714  mov     [rdi+1CEh], ax
0x18000771b  call    ?ParseHost@CURL@@IEAAXXZ; CURL::ParseHost(void)
0x180007720  movzx   eax, word ptr [rdi+1C6h]
0x180007727  sub     ax, [rbp+0]
0x18000772b  mov     [rdi+1C4h], ax
0x180007732  jmp     short loc_1800076C1
0x180007734  cmp     word ptr [rdi+1B8h], 0
0x18000773c  jz      short loc_1800076CB
0x18000773e  mov     ecx, cs:_tls_index
0x180007744  mov     rax, gs:58h
0x18000774d  mov     edx, 4
0x180007752  mov     rax, [rax+rcx*8]
0x180007756  mov     eax, [rdx+rax]
0x180007759  cmp     cs:?$TSS0@?1??GetPath@CURL@@QEAA?AVCLMSubStr@@XZ@4HA, eax
0x18000775f  jle     short loc_1800077BE
0x180007761  lea     rcx, ?$TSS0@?1??GetPath@CURL@@QEAA?AVCLMSubStr@@XZ@4HA
0x180007768  call    _Init_thread_header
0x18000776d  cmp     cs:?$TSS0@?1??GetPath@CURL@@QEAA?AVCLMSubStr@@XZ@4HA, 0FFFFFFFFh
0x180007774  jnz     short loc_1800077BE
0x180007776  lea     rax, asc_18002B504; "/"
0x18000777d  mov     cs:dword_180036674, 1
0x180007787  mov     cs:qword_180036668, rax
0x18000778e  lea     rcx, ??__Fslash@?1??GetPath@CURL@@QEAA?AVCLMSubStr@@XZ@YAXXZ; void (__cdecl *)()
0x180007795  lea     rax, ??_7CConstString@@6B@; const CConstString::`vftable'
0x18000779c  mov     cs:dword_180036670, 1
0x1800077a6  mov     cs:?slash@?1??GetPath@CURL@@QEAA?AVCLMSubStr@@XZ@4VCConstString@@A, rax; CConstString `CURL::GetPath(void)'::`2'::slash
0x1800077ad  call    atexit
0x1800077b2  lea     rcx, ?$TSS0@?1??GetPath@CURL@@QEAA?AVCLMSubStr@@XZ@4HA
0x1800077b9  call    _Init_thread_footer
0x1800077be  mov     eax, cs:dword_180036674
0x1800077c4  mov     [rbx+4], eax
0x1800077c7  lea     rax, ?slash@?1??GetPath@CURL@@QEAA?AVCLMSubStr@@XZ@4VCConstString@@A; CConstString `CURL::GetPath(void)'::`2'::slash
0x1800077ce  mov     [rbx+8], rax
0x1800077d2  mov     dword ptr [rbx], 0
0x1800077d8  jmp     loc_1800076FD
0x1800077dd  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x1800077e3  mov     rcx, [rsp+48h]; this
0x1800077e8  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1800077ef  mov     r9d, 0CEh; char *
0x1800077f5  mov     edx, 40Ch; void *
0x1800077fa  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
