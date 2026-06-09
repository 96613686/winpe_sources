# CMFMemoryBuffer::CreateInstance(ulong,ulong,IMFMediaBuffer * *)

- ea: `0x1800658d0`
- end: `0x1800659ae`
- name: `?CreateInstance@CMFMemoryBuffer@@SAJKKPEAPEAUIMFMediaBuffer@@@Z`
- size: `222`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, struct IMFMediaBuffer **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180063370`

## callees

- `0x1800245f0`
- `0x18003a54c`
- `0x180045060`
- `0x180065770`
- `0x1800658d0`

## pseudocode

```c
__int64 __fastcall CMFMemoryBuffer::CreateInstance(unsigned int a1, __int64 a2, struct IMFMediaBuffer **a3)
{
  const struct std::nothrow_t *v3; // rdx
  unsigned int v5; // ebx
  __int64 v6; // rdi
  unsigned __int8 *v7; // rsi
  unsigned int v8; // ebx
  unsigned __int8 *v9; // rax
  __int64 v10; // r8
  int Instance; // eax
  struct IMFBufferReleaseCallback *v13; // [rsp+28h] [rbp-40h]
  void *v14; // [rsp+30h] [rbp-38h]

  v3 = 0;
  v5 = a1;
  if ( CMFMemoryBuffer::g_dwMinAlignment )
    v3 = (const struct std::nothrow_t *)CMFMemoryBuffer::g_dwMinAlignment;
  v6 = (unsigned int)((_DWORD)v3 - 1);
  if ( !(_DWORD)v3 )
    v6 = 0;
  if ( CMFMemoryBuffer::g_dwMinAlignment )
    v5 = ~(_DWORD)v6 & (v6 + a1);
  if ( (unsigned int)v6 + v5 >= (unsigned int)v6 )
  {
    v9 = (unsigned __int8 *)operator new[]((unsigned int)v6 + v5);
    v7 = v9;
    if ( v9 )
    {
      Instance = CMFMemoryBuffer::CreateInstance(
                   ~(unsigned __int64)(unsigned int)v6 & (unsigned __int64)&v9[v6],
                   v5,
                   v10,
                   v9,
                   (unsigned __int8 *)(~(unsigned __int64)(unsigned int)v6 & (unsigned __int64)&v9[v6]),
                   v13,
                   v14,
                   a3);
      v8 = Instance;
      if ( Instance >= 0 )
        return v8;
      if ( g_wppLevels )
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_31a86577f1443cd70cd3725f1d3ba8e4_Traceguids, 0, Instance);
    }
    else
    {
      v8 = -2147024882;
      if ( g_wppLevels )
        WPP_SF_qd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          WPP_31a86577f1443cd70cd3725f1d3ba8e4_Traceguids,
          0,
          -2147024882);
    }
  }
  else
  {
    v7 = 0;
    v8 = -2147467259;
  }
  if ( a3 )
    *a3 = 0;
  operator delete(v7, v3);
  return v8;
}

```

## disassembly

```asm
0x1800658d0  push    rbx
0x1800658d2  push    rsi
0x1800658d3  push    rdi
0x1800658d4  push    r14
0x1800658d6  sub     rsp, 48h
0x1800658da  mov     r9d, cs:?g_dwMinAlignment@CMFMemoryBuffer@@0KA; ulong CMFMemoryBuffer::g_dwMinAlignment
0x1800658e1  xor     edx, edx
0x1800658e3  test    r9d, r9d
0x1800658e6  mov     r14, r8
0x1800658e9  mov     ebx, ecx
0x1800658eb  cmovnz  edx, r9d
0x1800658ef  xor     eax, eax
0x1800658f1  test    edx, edx
0x1800658f3  lea     edi, [rdx-1]
0x1800658f6  cmovz   edi, eax
0x1800658f9  test    r9d, r9d
0x1800658fc  jz      short loc_180065906
0x1800658fe  mov     eax, edi
0x180065900  add     ebx, edi
0x180065902  not     eax
0x180065904  and     ebx, eax
0x180065906  lea     eax, [rdi+rbx]
0x180065909  cmp     eax, edi
0x18006590b  jnb     short loc_180065916
0x18006590d  xor     esi, esi
0x18006590f  mov     ebx, 80004005h
0x180065914  jmp     short loc_18006598E
0x180065916  mov     ecx, eax; unsigned __int64
0x180065918  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006591d  mov     rsi, rax
0x180065920  test    rax, rax
0x180065923  jnz     short loc_18006593C
0x180065925  mov     ebx, 8007000Eh
0x18006592a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180065931  jb      short loc_18006598E
0x180065933  lea     edx, [rax+0Bh]
0x180065936  mov     dword ptr [rsp+68h+var_48], ebx
0x18006593a  jmp     short loc_180065974
0x18006593c  mov     eax, edi
0x18006593e  lea     rcx, [rdi+rsi]
0x180065942  not     rax
0x180065945  mov     [rsp+68h+var_30], r14; struct IMFMediaBuffer **
0x18006594a  and     rcx, rax; int
0x18006594d  mov     r9, rsi; unsigned __int8 *
0x180065950  mov     edx, ebx; unsigned int
0x180065952  mov     [rsp+68h+var_48], rcx; unsigned __int8 *
0x180065957  call    ?CreateInstance@CMFMemoryBuffer@@CAJHKKPEAE0PEAUIMFBufferReleaseCallback@@PEAXPEAPEAUIMFMediaBuffer@@@Z; CMFMemoryBuffer::CreateInstance(int,ulong,ulong,uchar *,uchar *,IMFBufferReleaseCallback *,void *,IMFMediaBuffer * *)
0x18006595c  mov     ebx, eax
0x18006595e  test    eax, eax
0x180065960  jns     short loc_1800659A2
0x180065962  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180065969  jb      short loc_18006598E
0x18006596b  mov     edx, 0Ch
0x180065970  mov     dword ptr [rsp+68h+var_48], eax
0x180065974  mov     rcx, cs:WPP_GLOBAL_Control
0x18006597b  lea     r8, WPP_31a86577f1443cd70cd3725f1d3ba8e4_Traceguids
0x180065982  xor     r9d, r9d
0x180065985  mov     rcx, [rcx+10h]
0x180065989  call    WPP_SF_qd
0x18006598e  test    r14, r14
0x180065991  jz      short loc_18006599A
0x180065993  mov     qword ptr [r14], 0
0x18006599a  mov     rcx, rsi; void *
0x18006599d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800659a2  mov     eax, ebx
0x1800659a4  add     rsp, 48h
0x1800659a8  pop     r14
0x1800659aa  pop     rdi
0x1800659ab  pop     rsi
0x1800659ac  pop     rbx
0x1800659ad  retn
```
