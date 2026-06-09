# AttemptFormatMessage(ulong,ushort const *,ushort * *,int)

- ea: `0x18000ca0c`
- end: `0x18000cabf`
- name: `?AttemptFormatMessage@@YAHKPEBGPEAPEAGH@Z`
- size: `179`
- prototype: `__int64 __fastcall(CDllCache *dwMessageId, unsigned __int16 *, LPWSTR lpBuffer, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d814`
- `0x18001f9cc`

## callees

- `0x18000c368`
- `0x18000c684`
- `0x18000c8b8`
- `0x18000ca0c`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x18000ca64`
- `KERNEL32!FormatMessageW` at `0x18000ca64`

## pseudocode

```c
__int64 __fastcall AttemptFormatMessage(CDllCache *dwMessageId, unsigned __int16 *a2, LPWSTR lpBuffer, int a4)
{
  DWORD v7; // r14d
  unsigned int v8; // edi
  DWORD v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  LPCVOID lpSource; // [rsp+70h] [rbp+18h] BYREF

  v7 = (unsigned int)dwMessageId;
  v8 = 0;
  lpSource = 0;
  *(_QWORD *)lpBuffer = 0;
  CDllCache::Fetch(dwMessageId, a2, (struct CSafeCacheHandle *)&lpSource);
  if ( lpSource )
  {
    v9 = FormatMessageW(0xBFFu, lpSource, v7, 0, lpBuffer, 0x100u, 0);
    if ( v9 )
    {
      v8 = 1;
      v10 = *(_QWORD *)lpBuffer;
      if ( *(_QWORD *)lpBuffer )
      {
        v11 = v9 - 1;
        if ( *(_WORD *)(v10 + 2 * v11) == 32 )
          *(_WORD *)(v10 + 2 * v11) = 0;
      }
      if ( a4 )
        AppendRedirectionURLText(a2);
    }
  }
  CSafeCacheHandle::~CSafeCacheHandle((CSafeCacheHandle *)&lpSource);
  return v8;
}

```

## disassembly

```asm
0x18000ca0c  mov     rax, rsp
0x18000ca0f  mov     [rax+8], rbx
0x18000ca13  mov     [rax+10h], rbp
0x18000ca17  push    rsi
0x18000ca18  push    rdi
0x18000ca19  push    r14
0x18000ca1b  sub     rsp, 40h
0x18000ca1f  mov     ebp, r9d
0x18000ca22  mov     rbx, r8
0x18000ca25  mov     rsi, rdx
0x18000ca28  mov     r14d, ecx
0x18000ca2b  xor     edi, edi
0x18000ca2d  mov     [rax+18h], rdi
0x18000ca31  mov     [r8], rdi
0x18000ca34  lea     r8, [rax+18h]; struct CSafeCacheHandle *
0x18000ca38  call    ?Fetch@CDllCache@@QEAAJPEBGPEAVCSafeCacheHandle@@@Z; CDllCache::Fetch(ushort const *,CSafeCacheHandle *)
0x18000ca3d  mov     rdx, [rsp+58h+lpSource]; lpSource
0x18000ca42  test    rdx, rdx
0x18000ca45  jz      short loc_18000CAA0
0x18000ca47  mov     [rsp+58h+Arguments], rdi; Arguments
0x18000ca4c  mov     [rsp+58h+nSize], 100h; nSize
0x18000ca54  mov     [rsp+58h+lpBuffer], rbx; lpBuffer
0x18000ca59  xor     r9d, r9d; dwLanguageId
0x18000ca5c  mov     r8d, r14d; dwMessageId
0x18000ca5f  mov     ecx, 0BFFh; dwFlags
0x18000ca64  call    cs:__imp_FormatMessageW
0x18000ca6a  test    eax, eax
0x18000ca6c  jz      short loc_18000CAA0
0x18000ca6e  mov     edi, 1
0x18000ca73  mov     rdx, [rbx]
0x18000ca76  test    rdx, rdx
0x18000ca79  jz      short loc_18000CA90
0x18000ca7b  lea     r8d, [rax-1]
0x18000ca7f  lea     eax, [rdi+1Fh]
0x18000ca82  cmp     ax, [rdx+r8*2]
0x18000ca87  jnz     short loc_18000CA90
0x18000ca89  xor     ecx, ecx
0x18000ca8b  mov     [rdx+r8*2], cx
0x18000ca90  test    ebp, ebp
0x18000ca92  jz      short loc_18000CAA0
0x18000ca94  mov     rdx, rbx
0x18000ca97  mov     rcx, rsi; unsigned __int16 *
0x18000ca9a  call    AppendRedirectionURLText
0x18000ca9f  nop
0x18000caa0  lea     rcx, [rsp+58h+lpSource]; this
0x18000caa5  call    ??1CSafeCacheHandle@@QEAA@XZ; CSafeCacheHandle::~CSafeCacheHandle(void)
0x18000caaa  mov     eax, edi
0x18000caac  mov     rbx, [rsp+58h+arg_0]
0x18000cab1  mov     rbp, [rsp+58h+arg_8]
0x18000cab6  add     rsp, 40h
0x18000caba  pop     r14
0x18000cabc  pop     rdi
0x18000cabd  pop     rsi
0x18000cabe  retn
```
