# UtilStringCopyWithAlloc(ushort * *,uint,ushort const *)

- ea: `0x180007294`
- end: `0x180007331`
- name: `?UtilStringCopyWithAlloc@@YAJPEAPEAGIPEBG@Z`
- size: `157`
- prototype: `int(unsigned __int16 **, unsigned int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005c64`
- `0x18002bc60`

## callees

- `0x180006fa0`
- `0x180007014`
- `0x180007294`
- `0x18002c802`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800072d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800072d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000730f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000730f`

## pseudocode

```c
__int64 __fastcall UtilStringCopyWithAlloc(unsigned __int16 **a1, unsigned int a2, const unsigned __int16 *a3)
{
  int v5; // edi
  unsigned __int64 v6; // rdi
  SIZE_T v7; // rsi
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rbx
  unsigned __int64 v11; // [rsp+58h] [rbp+20h] BYREF

  v11 = 0;
  v5 = StringCchLengthW(a3, a2, &v11);
  if ( v5 >= 0 )
  {
    v6 = v11 + 1;
    v7 = 2 * (v11 + 1);
    v8 = (unsigned __int16 *)CoTaskMemAlloc(v7);
    v9 = v8;
    if ( v8 )
    {
      memset_0(v8, 0, v7);
      v5 = StringCchCopyW(v9, v6, a3);
      if ( v5 < 0 )
        CoTaskMemFree(v9);
      else
        *a1 = v9;
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180007294  mov     rax, rsp
0x180007297  mov     [rax+8], rbx
0x18000729b  mov     [rax+10h], rbp
0x18000729f  push    rsi
0x1800072a0  push    rdi
0x1800072a1  push    r14
0x1800072a3  sub     rsp, 20h
0x1800072a7  mov     rbp, r8
0x1800072aa  mov     edx, edx; unsigned __int64
0x1800072ac  mov     r14, rcx
0x1800072af  mov     qword ptr [rax+20h], 0
0x1800072b7  mov     rcx, rbp; unsigned __int16 *
0x1800072ba  lea     r8, [rax+20h]; unsigned __int64 *
0x1800072be  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800072c3  mov     edi, eax
0x1800072c5  test    eax, eax
0x1800072c7  js      short loc_18000731C
0x1800072c9  mov     rdi, [rsp+38h+arg_18]
0x1800072ce  inc     rdi
0x1800072d1  lea     rsi, [rdi+rdi]
0x1800072d5  mov     rcx, rsi; cb
0x1800072d8  call    cs:__imp_CoTaskMemAlloc
0x1800072de  mov     rbx, rax
0x1800072e1  test    rax, rax
0x1800072e4  jz      short loc_180007317
0x1800072e6  mov     r8, rsi; Size
0x1800072e9  xor     edx, edx; Val
0x1800072eb  mov     rcx, rax; void *
0x1800072ee  call    memset_0
0x1800072f3  mov     r8, rbp; unsigned __int16 *
0x1800072f6  mov     rdx, rdi; unsigned __int64
0x1800072f9  mov     rcx, rbx; unsigned __int16 *
0x1800072fc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007301  mov     edi, eax
0x180007303  test    eax, eax
0x180007305  js      short loc_18000730C
0x180007307  mov     [r14], rbx
0x18000730a  jmp     short loc_18000731C
0x18000730c  mov     rcx, rbx; pv
0x18000730f  call    cs:__imp_CoTaskMemFree
0x180007315  jmp     short loc_18000731C
0x180007317  mov     edi, 8007000Eh
0x18000731c  mov     rbx, [rsp+38h+arg_0]
0x180007321  mov     eax, edi
0x180007323  mov     rbp, [rsp+38h+arg_8]
0x180007328  add     rsp, 20h
0x18000732c  pop     r14
0x18000732e  pop     rdi
0x18000732f  pop     rsi
0x180007330  retn
```
