# QueryV2Provider

- ea: `0x180012604`
- end: `0x1800126c1`
- name: `QueryV2Provider`
- size: `189`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, struct EXT_OBJ_LIST *@<rdx>, unsigned int@<r8d>, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180004f00`

## callees

- `0x180008050`
- `0x180012604`
- `0x180015250`
- `0x18001e431`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012632`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012632`

## pseudocode

```c
__int64 __fastcall QueryV2Provider(
        unsigned __int16 *a1,
        struct EXT_OBJ_LIST *a2,
        unsigned int a3,
        unsigned int a4,
        void **a5,
        _DWORD *a6)
{
  DWORD CurrentThreadId; // eax
  unsigned int V2Provider; // edi
  size_t Size; // [rsp+40h] [rbp-38h] BYREF
  void *Src; // [rsp+48h] [rbp-30h] BYREF

  Src = 0;
  Size = 0;
  CurrentThreadId = GetCurrentThreadId();
  V2Provider = PerflibciQueryV2Provider(
                 CurrentThreadId,
                 a1,
                 a2,
                 a3,
                 (unsigned __int8 **)&Src,
                 (unsigned int *)&Size,
                 (unsigned int *)&Size + 1);
  if ( !V2Provider && (_DWORD)Size )
  {
    if ( a4 < (unsigned int)Size )
    {
      V2Provider = 234;
    }
    else
    {
      memcpy_0(*a5, Src, (unsigned int)Size);
      *a5 = (char *)*a5 + (unsigned int)Size;
      *a6 += HIDWORD(Size);
    }
  }
  operator delete(Src);
  return V2Provider;
}

```

## disassembly

```asm
0x180012604  push    rbx
0x180012606  push    rbp
0x180012607  push    rsi
0x180012608  push    rdi
0x180012609  sub     rsp, 58h
0x18001260d  mov     ebp, r9d
0x180012610  mov     [rsp+78h+Src], 0
0x180012619  mov     ebx, r8d
0x18001261c  mov     dword ptr [rsp+78h+Size], 0
0x180012624  mov     rdi, rdx
0x180012627  mov     dword ptr [rsp+78h+Size+4], 0
0x18001262f  mov     rsi, rcx
0x180012632  call    cs:__imp_GetCurrentThreadId
0x180012638  mov     r9d, ebx; unsigned int
0x18001263b  mov     r8, rdi; struct EXT_OBJ_LIST *
0x18001263e  mov     ecx, eax; unsigned int
0x180012640  mov     rdx, rsi; unsigned __int16 *
0x180012643  lea     rax, [rsp+78h+Size+4]
0x180012648  mov     [rsp+78h+var_48], rax; unsigned int *
0x18001264d  lea     rax, [rsp+78h+Size]
0x180012652  mov     [rsp+78h+var_50], rax; unsigned int *
0x180012657  lea     rax, [rsp+78h+Src]
0x18001265c  mov     [rsp+78h+var_58], rax; unsigned __int8 **
0x180012661  call    ?PerflibciQueryV2Provider@@YAKKPEBGPEAUEXT_OBJ_LIST@@KPEAPEAEPEAK3@Z; PerflibciQueryV2Provider(ulong,ushort const *,EXT_OBJ_LIST *,ulong,uchar * *,ulong *,ulong *)
0x180012666  mov     edi, eax
0x180012668  test    eax, eax
0x18001266a  jnz     short loc_1800126AC
0x18001266c  mov     ecx, dword ptr [rsp+78h+Size]
0x180012670  test    ecx, ecx
0x180012672  jz      short loc_1800126AC
0x180012674  cmp     ebp, ecx
0x180012676  jb      short loc_1800126A7
0x180012678  mov     rbx, [rsp+78h+arg_20]
0x180012680  mov     r8d, ecx; Size
0x180012683  mov     rdx, [rsp+78h+Src]; Src
0x180012688  mov     rcx, [rbx]; void *
0x18001268b  call    memcpy_0
0x180012690  mov     eax, dword ptr [rsp+78h+Size]
0x180012694  add     [rbx], rax
0x180012697  mov     rcx, [rsp+78h+arg_28]
0x18001269f  mov     eax, dword ptr [rsp+78h+Size+4]
0x1800126a3  add     [rcx], eax
0x1800126a5  jmp     short loc_1800126AC
0x1800126a7  mov     edi, 0EAh
0x1800126ac  mov     rcx, [rsp+78h+Src]; Block
0x1800126b1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800126b6  mov     eax, edi
0x1800126b8  add     rsp, 58h
0x1800126bc  pop     rdi
0x1800126bd  pop     rsi
0x1800126be  pop     rbp
0x1800126bf  pop     rbx
0x1800126c0  retn
```
