# TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)

- ea: `0x14001cb38`
- end: `0x14001cbe2`
- name: `??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z`
- size: `170`
- prototype: `__int64 __fastcall(HMODULE, unsigned int, __int64, void *, int, void **Src)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140018d60`

## callees

- `0x14001cb38`
- `0x14001cc38`
- `0x14001cc68`
- `0x14001e012`

## pseudocode

```c
__int64 __fastcall TResourceStringAllocCopyEx<unsigned short *>(
        HMODULE a1,
        unsigned int a2,
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
  v7 = ResourceStringFindAndSizeEx(a1, a2, a3, (unsigned __int64 *)&Src, &v10);
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
0x14001cb38  mov     r11, rsp
0x14001cb3b  mov     [r11+8], rbx
0x14001cb3f  mov     [r11+10h], rsi
0x14001cb43  mov     [r11+20h], r9
0x14001cb47  mov     [r11+18h], r8w
0x14001cb4c  push    rdi
0x14001cb4d  sub     rsp, 30h
0x14001cb51  mov     rsi, [rsp+38h+Src]
0x14001cb56  lea     r9, [r11+30h]
0x14001cb5a  xor     eax, eax
0x14001cb5c  mov     qword ptr [r11+30h], 0
0x14001cb64  mov     [rsp+38h+arg_10], ax
0x14001cb69  lea     rax, [r11+18h]
0x14001cb6d  mov     [r11-18h], rax
0x14001cb71  mov     qword ptr [rsi], 0
0x14001cb78  call    ResourceStringFindAndSizeEx
0x14001cb7d  mov     ebx, eax
0x14001cb7f  test    eax, eax
0x14001cb81  js      short loc_14001CBD0
0x14001cb83  movzx   eax, [rsp+38h+arg_10]
0x14001cb88  lea     r8, [rsp+38h+arg_18]
0x14001cb8d  xor     ecx, ecx
0x14001cb8f  mov     [rsp+38h+arg_18], 0
0x14001cb98  lea     rdi, [rax+rax]
0x14001cb9c  lea     rdx, [rdi+2]
0x14001cba0  call    _ResourceStringAllocCopyExCoAlloc
0x14001cba5  mov     ebx, eax
0x14001cba7  test    eax, eax
0x14001cba9  js      short loc_14001CBD0
0x14001cbab  mov     rdx, [rsp+38h+Src]; Src
0x14001cbb0  mov     r8, rdi; Size
0x14001cbb3  mov     rcx, [rsp+38h+arg_18]; void *
0x14001cbb8  call    memcpy_0
0x14001cbbd  mov     rax, [rsp+38h+arg_18]
0x14001cbc2  xor     ecx, ecx
0x14001cbc4  mov     [rdi+rax], cx
0x14001cbc8  mov     rax, [rsp+38h+arg_18]
0x14001cbcd  mov     [rsi], rax
0x14001cbd0  mov     rsi, [rsp+38h+arg_8]
0x14001cbd5  mov     eax, ebx
0x14001cbd7  mov     rbx, [rsp+38h+arg_0]
0x14001cbdc  add     rsp, 30h
0x14001cbe0  pop     rdi
0x14001cbe1  retn
```
