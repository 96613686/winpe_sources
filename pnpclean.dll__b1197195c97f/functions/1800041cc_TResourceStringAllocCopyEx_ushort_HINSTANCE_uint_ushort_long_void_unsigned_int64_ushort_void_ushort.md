# TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)

- ea: `0x1800041cc`
- end: `0x180004276`
- name: `??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z`
- size: `170`
- prototype: `__int64 __fastcall(HMODULE, __int64, __int64, void *, int, void **Src)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003140`

## callees

- `0x1800041cc`
- `0x18000427c`
- `0x1800042ac`
- `0x180008df2`

## pseudocode

```c
__int64 __fastcall TResourceStringAllocCopyEx<unsigned short *>(
        HMODULE a1,
        __int64 a2,
        __int64 a3,
        void *a4,
        int a5,
        void **Src)
{
  void **v6; // rsi
  int v7; // ebx
  size_t v8; // rdi
  unsigned __int16 v10; // [rsp+50h] [rbp+18h] BYREF
  void *v11; // [rsp+58h] [rbp+20h] BYREF

  v11 = a4;
  v6 = Src;
  Src = 0;
  v10 = 0;
  *v6 = 0;
  v7 = ResourceStringFindAndSizeEx(a1, (__int64)&v10);
  if ( v7 >= 0 )
  {
    v11 = 0;
    v8 = 2LL * v10;
    v7 = ResourceStringAllocCopyExCoAlloc(0, v8 + 2, &v11);
    if ( v7 >= 0 )
    {
      memcpy_0(v11, Src, v8);
      *(_WORD *)((char *)v11 + v8) = 0;
      *v6 = v11;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800041cc  mov     r11, rsp
0x1800041cf  mov     [r11+8], rbx
0x1800041d3  mov     [r11+10h], rsi
0x1800041d7  mov     [r11+20h], r9
0x1800041db  mov     [r11+18h], r8w
0x1800041e0  push    rdi
0x1800041e1  sub     rsp, 30h
0x1800041e5  mov     rsi, [rsp+38h+Src]
0x1800041ea  lea     r9, [r11+30h]
0x1800041ee  xor     eax, eax
0x1800041f0  mov     qword ptr [r11+30h], 0
0x1800041f8  mov     [rsp+38h+arg_10], ax
0x1800041fd  lea     rax, [r11+18h]
0x180004201  mov     [r11-18h], rax
0x180004205  mov     qword ptr [rsi], 0
0x18000420c  call    ResourceStringFindAndSizeEx
0x180004211  mov     ebx, eax
0x180004213  test    eax, eax
0x180004215  js      short loc_180004264
0x180004217  movzx   eax, [rsp+38h+arg_10]
0x18000421c  lea     r8, [rsp+38h+arg_18]
0x180004221  xor     ecx, ecx
0x180004223  mov     [rsp+38h+arg_18], 0
0x18000422c  lea     rdi, [rax+rax]
0x180004230  lea     rdx, [rdi+2]
0x180004234  call    _ResourceStringAllocCopyExCoAlloc
0x180004239  mov     ebx, eax
0x18000423b  test    eax, eax
0x18000423d  js      short loc_180004264
0x18000423f  mov     rdx, [rsp+38h+Src]; Src
0x180004244  mov     r8, rdi; Size
0x180004247  mov     rcx, [rsp+38h+arg_18]; void *
0x18000424c  call    memcpy_0
0x180004251  mov     rax, [rsp+38h+arg_18]
0x180004256  xor     ecx, ecx
0x180004258  mov     [rdi+rax], cx
0x18000425c  mov     rax, [rsp+38h+arg_18]
0x180004261  mov     [rsi], rax
0x180004264  mov     rsi, [rsp+38h+arg_8]
0x180004269  mov     eax, ebx
0x18000426b  mov     rbx, [rsp+38h+arg_0]
0x180004270  add     rsp, 30h
0x180004274  pop     rdi
0x180004275  retn
```
