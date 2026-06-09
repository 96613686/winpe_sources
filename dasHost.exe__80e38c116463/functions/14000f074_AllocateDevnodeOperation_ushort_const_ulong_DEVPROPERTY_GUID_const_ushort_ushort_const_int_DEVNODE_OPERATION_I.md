# AllocateDevnodeOperation(ushort const *,ulong,_DEVPROPERTY *,_GUID const *,ushort *,ushort const *,int,_DEVNODE_OPERATION_INFO * *)

- ea: `0x14000f074`
- end: `0x14000f1b2`
- name: `?AllocateDevnodeOperation@@YAJPEBGKPEAU_DEVPROPERTY@@PEBU_GUID@@PEAG0HPEAPEAU_DEVNODE_OPERATION_INFO@@@Z`
- size: `318`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, struct _DEVPROPERTY *, const struct _GUID *, unsigned __int16 *, unsigned __int16 *, int, struct _DEVNODE_OPERATION_INFO **)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x14000e6a0`
- `0x14000e780`
- `0x14000e9a0`
- `0x14000ea90`
- `0x14000f2c8`
- `0x14000fd20`

## callees

- `0x1400020d0`
- `0x14000f074`
- `0x140019c5c`
- `0x140019db0`
- `0x14001a068`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000f162`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000f162`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000f0c8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000f0c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f0b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f0b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f171`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f171`

## pseudocode

```c
__int64 __fastcall AllocateDevnodeOperation(
        const unsigned __int16 *a1,
        unsigned int a2,
        struct _DEVPROPERTY *a3,
        const struct _GUID *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        int a7,
        struct _DEVNODE_OPERATION_INFO **a8)
{
  struct _DEVPROPERTY *v8; // rsi
  int v12; // eax
  int v13; // ebx
  HANDLE ProcessHeap; // rax
  void *v15; // rax
  void *v16; // rdi
  int v17; // eax
  HANDLE EventW; // rax
  signed int LastError; // eax
  struct _DEVPROPERTY *v21; // [rsp+70h] [rbp+18h] BYREF

  v8 = 0;
  v21 = 0;
  if ( a3 )
  {
    v12 = MidlCopyDevProperties(a3, a2, &v21);
    v8 = v21;
    v13 = v12;
    if ( v12 < 0 )
      goto LABEL_16;
  }
  ProcessHeap = GetProcessHeap();
  v15 = HeapAlloc(ProcessHeap, 0, 0x50u);
  v16 = v15;
  if ( !v15 )
  {
    v13 = -2147024882;
    goto LABEL_16;
  }
  memset_0(v15, 0, 0x50u);
  v17 = a7;
  *((_QWORD *)v16 + 1) = v8;
  v8 = 0;
  *((_DWORD *)v16 + 14) = v17;
  *(_DWORD *)v16 = a2;
  if ( a4 )
    *((struct _GUID *)v16 + 1) = *a4;
  if ( !a6 || (v13 = MidlCopyString(a6, (unsigned __int16 **)v16 + 4), v13 >= 0) )
  {
    if ( !a5 || (v13 = MidlCopyString(a5, (unsigned __int16 **)v16 + 6), v13 >= 0) )
    {
      v13 = MidlCopyString(a1, (unsigned __int16 **)v16 + 5);
      if ( v13 >= 0 )
      {
        EventW = CreateEventW(0, 0, 0, 0);
        *((_QWORD *)v16 + 8) = EventW;
        if ( !EventW )
        {
          LastError = GetLastError();
          v13 = LastError;
          if ( LastError > 0 )
            return (unsigned __int16)LastError | 0x80070000;
          return (unsigned int)v13;
        }
        *a8 = (struct _DEVNODE_OPERATION_INFO *)v16;
LABEL_16:
        if ( v8 )
          MidlFreeDevProperties(v8, a2);
      }
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14000f074  push    rbx
0x14000f076  push    rbp
0x14000f077  push    rsi
0x14000f078  push    rdi
0x14000f079  push    r14
0x14000f07b  push    r15
0x14000f07d  sub     rsp, 28h
0x14000f081  xor     esi, esi
0x14000f083  mov     rbp, r9
0x14000f086  mov     [rsp+58h+arg_10], rsi
0x14000f08b  mov     rax, r8
0x14000f08e  mov     r14d, edx
0x14000f091  mov     r15, rcx
0x14000f094  test    r8, r8
0x14000f097  jz      short loc_14000F0B5
0x14000f099  lea     r8, [rsp+58h+arg_10]; struct _DEVPROPERTY **
0x14000f09e  mov     rcx, rax; struct _DEVPROPERTY *
0x14000f0a1  call    ?MidlCopyDevProperties@@YAJPEAU_DEVPROPERTY@@KPEAPEAU1@@Z; MidlCopyDevProperties(_DEVPROPERTY *,ulong,_DEVPROPERTY * *)
0x14000f0a6  mov     rsi, [rsp+58h+arg_10]
0x14000f0ab  mov     ebx, eax
0x14000f0ad  test    eax, eax
0x14000f0af  js      loc_14000F193
0x14000f0b5  call    cs:__imp_GetProcessHeap
0x14000f0bb  mov     ebx, 50h ; 'P'
0x14000f0c0  xor     edx, edx; dwFlags
0x14000f0c2  mov     rcx, rax; hHeap
0x14000f0c5  mov     r8d, ebx; dwBytes
0x14000f0c8  call    cs:__imp_HeapAlloc
0x14000f0ce  mov     rdi, rax
0x14000f0d1  test    rax, rax
0x14000f0d4  jnz     short loc_14000F0E0
0x14000f0d6  mov     ebx, 8007000Eh
0x14000f0db  jmp     loc_14000F193
0x14000f0e0  mov     r8, rbx; Size
0x14000f0e3  xor     edx, edx; Val
0x14000f0e5  mov     rcx, rdi; void *
0x14000f0e8  call    memset_0
0x14000f0ed  mov     eax, [rsp+58h+arg_30]
0x14000f0f4  mov     [rdi+8], rsi
0x14000f0f8  xor     esi, esi
0x14000f0fa  mov     [rdi+38h], eax
0x14000f0fd  mov     [rdi], r14d
0x14000f100  test    rbp, rbp
0x14000f103  jz      short loc_14000F10E
0x14000f105  movaps  xmm0, xmmword ptr [rbp+0]
0x14000f109  movdqu  xmmword ptr [rdi+10h], xmm0
0x14000f10e  mov     rcx, [rsp+58h+arg_28]; unsigned __int16 *
0x14000f116  test    rcx, rcx
0x14000f119  jz      short loc_14000F12A
0x14000f11b  lea     rdx, [rdi+20h]; unsigned __int16 **
0x14000f11f  call    ?MidlCopyString@@YAJPEBGPEAPEAG@Z; MidlCopyString(ushort const *,ushort * *)
0x14000f124  mov     ebx, eax
0x14000f126  test    eax, eax
0x14000f128  js      short loc_14000F1A3
0x14000f12a  mov     rcx, [rsp+58h+arg_20]; unsigned __int16 *
0x14000f132  test    rcx, rcx
0x14000f135  jz      short loc_14000F146
0x14000f137  lea     rdx, [rdi+30h]; unsigned __int16 **
0x14000f13b  call    ?MidlCopyString@@YAJPEBGPEAPEAG@Z; MidlCopyString(ushort const *,ushort * *)
0x14000f140  mov     ebx, eax
0x14000f142  test    eax, eax
0x14000f144  js      short loc_14000F1A3
0x14000f146  lea     rdx, [rdi+28h]; unsigned __int16 **
0x14000f14a  mov     rcx, r15; unsigned __int16 *
0x14000f14d  call    ?MidlCopyString@@YAJPEBGPEAPEAG@Z; MidlCopyString(ushort const *,ushort * *)
0x14000f152  mov     ebx, eax
0x14000f154  test    eax, eax
0x14000f156  js      short loc_14000F1A3
0x14000f158  xor     r9d, r9d; lpName
0x14000f15b  xor     r8d, r8d; bInitialState
0x14000f15e  xor     edx, edx; bManualReset
0x14000f160  xor     ecx, ecx; lpEventAttributes
0x14000f162  call    cs:__imp_CreateEventW
0x14000f168  mov     [rdi+40h], rax
0x14000f16c  test    rax, rax
0x14000f16f  jnz     short loc_14000F188
0x14000f171  call    cs:__imp_GetLastError
0x14000f177  mov     ebx, eax
0x14000f179  test    eax, eax
0x14000f17b  jle     short loc_14000F1A3
0x14000f17d  movzx   ebx, ax
0x14000f180  or      ebx, 80070000h
0x14000f186  jmp     short loc_14000F1A3
0x14000f188  mov     rax, [rsp+58h+arg_38]
0x14000f190  mov     [rax], rdi
0x14000f193  test    rsi, rsi
0x14000f196  jz      short loc_14000F1A3
0x14000f198  mov     edx, r14d; unsigned int
0x14000f19b  mov     rcx, rsi; struct _DEVPROPERTY *
0x14000f19e  call    ?MidlFreeDevProperties@@YAXPEAU_DEVPROPERTY@@K@Z; MidlFreeDevProperties(_DEVPROPERTY *,ulong)
0x14000f1a3  mov     eax, ebx
0x14000f1a5  add     rsp, 28h
0x14000f1a9  pop     r15
0x14000f1ab  pop     r14
0x14000f1ad  pop     rdi
0x14000f1ae  pop     rsi
0x14000f1af  pop     rbp
0x14000f1b0  pop     rbx
0x14000f1b1  retn
```
