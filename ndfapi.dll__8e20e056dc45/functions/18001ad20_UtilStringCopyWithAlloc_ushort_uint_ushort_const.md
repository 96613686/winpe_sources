# UtilStringCopyWithAlloc(ushort * *,uint,ushort const *)

- ea: `0x18001ad20`
- end: `0x18001adef`
- name: `?UtilStringCopyWithAlloc@@YAJPEAPEAGIPEBG@Z`
- size: `207`
- prototype: `int(unsigned __int16 **, unsigned int, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180015de0`
- `0x180015f90`
- `0x180019590`
- `0x18001977c`
- `0x18001dbb4`
- `0x18001dd0c`

## callees

- `0x18000f78c`
- `0x18001ad20`
- `0x18001f652`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18001ad95`
- `ole32!CoTaskMemAlloc` at `0x18001ad95`
- `ole32!CoTaskMemFree` at `0x18001adcc`
- `ole32!CoTaskMemFree` at `0x18001adcc`

## pseudocode

```c
__int64 __fastcall UtilStringCopyWithAlloc(unsigned __int16 **a1, __int64 a2, const unsigned __int16 *a3)
{
  const unsigned __int16 *v5; // rax
  __int64 v6; // r9
  signed int v7; // ebx
  __int64 v8; // r9
  unsigned __int64 v9; // rbx
  SIZE_T v10; // rbp
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rdi

  if ( a3 && (unsigned int)a2 <= 0x7FFFFFFF )
  {
    a2 = (unsigned int)a2;
    v5 = a3;
    v6 = (unsigned int)a2;
    if ( (_DWORD)a2 )
    {
      do
      {
        if ( !*v5 )
          break;
        ++v5;
        --a2;
      }
      while ( a2 );
    }
    v7 = a2 == 0 ? 0x80070057 : 0;
    if ( a2 )
      v8 = v6 - a2;
    else
      v8 = 0;
    if ( a2 )
    {
      v9 = v8 + 1;
      v10 = 2 * (v8 + 1);
      v11 = (unsigned __int16 *)CoTaskMemAlloc(v10);
      v12 = v11;
      if ( v11 )
      {
        memset_0(v11, 0, v10);
        v7 = StringCchCopyW(v12, v9, a3);
        if ( v7 < 0 )
          CoTaskMemFree(v12);
        else
          *a1 = v12;
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001ad20  push    rbx
0x18001ad22  push    rbp
0x18001ad23  push    rsi
0x18001ad24  push    rdi
0x18001ad25  push    r14
0x18001ad27  push    r15
0x18001ad29  sub     rsp, 28h
0x18001ad2d  xor     r15d, r15d
0x18001ad30  mov     rsi, r8
0x18001ad33  mov     r14, rcx
0x18001ad36  test    r8, r8
0x18001ad39  jz      loc_18001ADDB
0x18001ad3f  cmp     edx, 7FFFFFFFh
0x18001ad45  ja      loc_18001ADDB
0x18001ad4b  mov     edx, edx
0x18001ad4d  mov     rax, r8
0x18001ad50  mov     r9d, edx
0x18001ad53  test    rdx, rdx
0x18001ad56  jz      short loc_18001AD68
0x18001ad58  cmp     [rax], r15w
0x18001ad5c  jz      short loc_18001AD68
0x18001ad5e  add     rax, 2
0x18001ad62  sub     rdx, 1
0x18001ad66  jnz     short loc_18001AD58
0x18001ad68  mov     rax, rdx
0x18001ad6b  neg     rax
0x18001ad6e  sbb     ebx, ebx
0x18001ad70  not     ebx
0x18001ad72  and     ebx, 80070057h
0x18001ad78  test    rdx, rdx
0x18001ad7b  jz      short loc_18001AD82
0x18001ad7d  sub     r9, rdx
0x18001ad80  jmp     short loc_18001AD85
0x18001ad82  mov     r9, r15
0x18001ad85  test    rdx, rdx
0x18001ad88  jz      short loc_18001ADE0
0x18001ad8a  lea     rbx, [r9+1]
0x18001ad8e  lea     rbp, [rbx+rbx]
0x18001ad92  mov     rcx, rbp; cb
0x18001ad95  call    cs:__imp_CoTaskMemAlloc
0x18001ad9b  mov     rdi, rax
0x18001ad9e  test    rax, rax
0x18001ada1  jz      short loc_18001ADD4
0x18001ada3  mov     r8, rbp; Size
0x18001ada6  xor     edx, edx; Val
0x18001ada8  mov     rcx, rax; void *
0x18001adab  call    memset_0
0x18001adb0  mov     r8, rsi; unsigned __int16 *
0x18001adb3  mov     rdx, rbx; unsigned __int64
0x18001adb6  mov     rcx, rdi; unsigned __int16 *
0x18001adb9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001adbe  mov     ebx, eax
0x18001adc0  test    eax, eax
0x18001adc2  js      short loc_18001ADC9
0x18001adc4  mov     [r14], rdi
0x18001adc7  jmp     short loc_18001ADE0
0x18001adc9  mov     rcx, rdi; pv
0x18001adcc  call    cs:__imp_CoTaskMemFree
0x18001add2  jmp     short loc_18001ADE0
0x18001add4  mov     ebx, 8007000Eh
0x18001add9  jmp     short loc_18001ADE0
0x18001addb  mov     ebx, 80070057h
0x18001ade0  mov     eax, ebx
0x18001ade2  add     rsp, 28h
0x18001ade6  pop     r15
0x18001ade8  pop     r14
0x18001adea  pop     rdi
0x18001adeb  pop     rsi
0x18001adec  pop     rbp
0x18001aded  pop     rbx
0x18001adee  retn
```
